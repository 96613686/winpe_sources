# ClatMgrProcessUpdate

- ea: `0x18007cc0c`
- end: `0x18007cead`
- name: `ClatMgrProcessUpdate`
- size: `673`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18007cc00`
- `0x18007cec0`
- `0x18007d290`

## callees

- `0x18000d7c0`
- `0x180047138`
- `0x180047164`
- `0x1800472cc`
- `0x18004b5f0`
- `0x18007be50`
- `0x18007bee0`
- `0x18007c038`
- `0x18007c2d8`
- `0x18007c6f0`
- `0x18007cc0c`
- `0x18007d308`
- `0x18007d350`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cc4d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cc4d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ce83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ce83`
- `NSI!NsiFreeTable` at `0x18007ce74`
- `NSI!NsiFreeTable` at `0x18007ce74`
- `NSI!NsiAllocateAndGetTable` at `0x18007cd58`
- `NSI!NsiAllocateAndGetTable` at `0x18007cd58`
- `IPXLATCFG!IPxlatPolicyMgrReadConfiguration` at `0x18007cc9a`
- `IPXLATCFG!IPxlatPolicyMgrReadConfiguration` at `0x18007cc9a`

## string_xrefs

- `0x18007cc5f`: `Service exit event signalled. Skipping processing.`

## pseudocode

```c
void __fastcall ClatMgrProcessUpdate(__int64 a1)
{
  struct _RTL_CRITICAL_SECTION *v1; // r15
  bool v3; // bl
  char v4; // r14
  unsigned int Table; // eax
  unsigned int i; // edi
  int v7; // eax
  __int64 v8; // rcx
  __int64 Interface; // rbx
  unsigned int v10; // eax
  __int64 *v11; // rbx
  __int64 *v12; // rax
  unsigned int v13; // [rsp+70h] [rbp-19h] BYREF
  __int64 v14; // [rsp+78h] [rbp-11h] BYREF
  __int64 v15; // [rsp+80h] [rbp-9h] BYREF
  __int64 v16; // [rsp+88h] [rbp-1h] BYREF
  __int128 v17; // [rsp+90h] [rbp+7h] BYREF
  int v18; // [rsp+A0h] [rbp+17h]

  v1 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  v14 = 0;
  v16 = 0;
  v15 = 0;
  v13 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( *(_BYTE *)(a1 + 80) )
  {
    EventWrite0(0x4000000, L"Service exit event signalled. Skipping processing.");
    goto LABEL_37;
  }
  v3 = 1;
  if ( (unsigned int)Feature_CLAT_Preview2_GPO__private_IsEnabledDeviceUsageNoInline() )
  {
    v17 = 0;
    v18 = 0;
    IPxlatPolicyMgrReadConfiguration(&v17);
    v4 = (_DWORD)v17 != 0;
    if ( (unsigned int)Feature_CLAT_Preview2_AutoEnable__private_IsEnabledDeviceUsageNoInline() )
      v3 = v18 != 0;
  }
  else
  {
    v4 = ClatMgrCheckPolicy();
  }
  if ( (unsigned int)Feature_CLAT_Preview2_AutoEnable__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( *(_BYTE *)(a1 + 264) && !v3 )
    {
      EventWrite0(0x4000000, L"AutoEnable disabled. Disabling CLAT on all interfaces where it was auto enabled.");
      ClatMgrFlushInterfaces();
    }
    *(_BYTE *)(a1 + 264) = v3;
  }
  if ( v4 && v3 )
  {
    Table = NsiAllocateAndGetTable(1, &NPI_MS_IPV6_MODULEID, 7, &v14, 8, &v16, 240, 0, 0, &v15, 32, &v13, 0);
    if ( Table )
    {
      EventWrite0(0x4000000, L"NsiAllocateAndGetTable failed: Status=%d", Table);
      goto LABEL_37;
    }
    for ( i = 0; i < v13; ++i )
    {
      v7 = *(_DWORD *)(32LL * i + v15 + 4);
      if ( v7 != 24 && v7 != 237 && (unsigned int)(v7 - 243) > 1 )
      {
        Interface = ClatMgrFindInterface(*(_QWORD *)(v14 + 8LL * i));
        if ( !Interface )
        {
          v10 = ClatMgrAddInterface(v8);
          if ( v10 )
          {
            EventWrite0(0x4000000, L"ClatMgrAddInterface failed: Status=%d", v10);
            goto LABEL_37;
          }
          Interface = ClatMgrFindInterface(*(_QWORD *)(v14 + 8LL * i));
        }
        *(_BYTE *)(Interface + 24) = 0;
        if ( (_BYTE)word_1800CBFC9 )
          ClatMgrCheckTriggerPref64Ra(Interface);
        if ( HIBYTE(word_1800CBFC9) )
          ClatMgrCheckTriggerDhcp108(Interface);
        if ( byte_1800CBFCB )
          ClatMgrCheckTriggerNoIpv4(Interface);
      }
    }
  }
  v11 = (__int64 *)qword_1800CBFD0;
  while ( v11 != &qword_1800CBFD0 )
  {
    v12 = v11;
    v11 = (__int64 *)*v11;
    if ( *((_BYTE *)v12 + 24) )
      ClatMgrRemoveInterface(v12);
    else
      *((_BYTE *)v12 + 24) = 1;
  }
LABEL_37:
  if ( v14 )
    NsiFreeTable(v14, v16, 0, v15);
  LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x18007cc0c  push    rbp
0x18007cc0e  push    rbx
0x18007cc0f  push    rdi
0x18007cc10  push    r12
0x18007cc12  push    r14
0x18007cc14  push    r15
0x18007cc16  lea     rbp, [rsp-2Fh]
0x18007cc1b  sub     rsp, 0B8h
0x18007cc22  mov     rax, cs:__security_cookie
0x18007cc29  xor     rax, rsp
0x18007cc2c  mov     [rbp+57h+var_38], rax
0x18007cc30  xor     r12d, r12d
0x18007cc33  lea     r15, [rcx+8]
0x18007cc37  mov     rdi, rcx
0x18007cc3a  mov     [rbp+57h+var_68], r12
0x18007cc3e  mov     rcx, r15; lpCriticalSection
0x18007cc41  mov     [rbp+57h+var_58], r12
0x18007cc45  mov     [rbp+57h+var_60], r12
0x18007cc49  mov     [rbp+57h+var_70], r12d
0x18007cc4d  call    cs:__imp_EnterCriticalSection
0x18007cc54  nop     dword ptr [rax+rax+00h]
0x18007cc59  cmp     [rdi+50h], r12b
0x18007cc5d  jz      short loc_18007CC75
0x18007cc5f  lea     rdx, aServiceExitEve; "Service exit event signalled. Skipping "...
0x18007cc66  mov     ecx, 4000000h
0x18007cc6b  call    EventWrite0
0x18007cc70  jmp     loc_18007CE60
0x18007cc75  mov     bl, 1
0x18007cc77  call    Feature_CLAT_Preview2_GPO__private_IsEnabledDeviceUsageNoInline
0x18007cc7c  test    eax, eax
0x18007cc7e  jnz     short loc_18007CC8A
0x18007cc80  call    ClatMgrCheckPolicy
0x18007cc85  mov     r14b, al
0x18007cc88  jmp     short loc_18007CCBE
0x18007cc8a  xorps   xmm0, xmm0
0x18007cc8d  lea     rcx, [rbp+57h+var_50]
0x18007cc91  xor     eax, eax
0x18007cc93  movups  [rbp+57h+var_50], xmm0
0x18007cc97  mov     [rbp+57h+var_40], eax
0x18007cc9a  call    cs:__imp_IPxlatPolicyMgrReadConfiguration
0x18007cca1  nop     dword ptr [rax+rax+00h]
0x18007cca6  cmp     dword ptr [rbp+57h+var_50], r12d
0x18007ccaa  setnz   r14b
0x18007ccae  call    Feature_CLAT_Preview2_AutoEnable__private_IsEnabledDeviceUsageNoInline
0x18007ccb3  test    eax, eax
0x18007ccb5  jz      short loc_18007CCBE
0x18007ccb7  cmp     [rbp+57h+var_40], r12d
0x18007ccbb  setnz   bl
0x18007ccbe  call    Feature_CLAT_Preview2_AutoEnable__private_IsEnabledDeviceUsageNoInline
0x18007ccc3  test    eax, eax
0x18007ccc5  jz      short loc_18007CCF0
0x18007ccc7  cmp     [rdi+108h], r12b
0x18007ccce  jz      short loc_18007CCEA
0x18007ccd0  test    bl, bl
0x18007ccd2  jnz     short loc_18007CCEA
0x18007ccd4  lea     rdx, aAutoenableDisa; "AutoEnable disabled. Disabling CLAT on "...
0x18007ccdb  mov     ecx, 4000000h
0x18007cce0  call    EventWrite0
0x18007cce5  call    ClatMgrFlushInterfaces
0x18007ccea  mov     [rdi+108h], bl
0x18007ccf0  test    r14b, r14b
0x18007ccf3  jz      loc_18007CE25
0x18007ccf9  test    bl, bl
0x18007ccfb  jz      loc_18007CE25
0x18007cd01  mov     [rsp+0E0h+var_80], r12b
0x18007cd06  lea     rax, [rbp+57h+var_70]
0x18007cd0a  mov     [rsp+0E0h+var_88], rax
0x18007cd0f  lea     r9, [rbp+57h+var_68]
0x18007cd13  mov     [rsp+0E0h+var_90], 20h ; ' '
0x18007cd1b  lea     rax, [rbp+57h+var_60]
0x18007cd1f  mov     [rsp+0E0h+var_98], rax
0x18007cd24  lea     rdx, NPI_MS_IPV6_MODULEID
0x18007cd2b  mov     [rsp+0E0h+var_A0], r12d
0x18007cd30  lea     rax, [rbp+57h+var_58]
0x18007cd34  mov     [rsp+0E0h+var_A8], r12
0x18007cd39  mov     r8d, 7
0x18007cd3f  mov     [rsp+0E0h+var_B0], 0F0h
0x18007cd47  mov     [rsp+0E0h+var_B8], rax
0x18007cd4c  mov     [rsp+0E0h+var_C0], 8
0x18007cd54  lea     ecx, [r8-6]
0x18007cd58  call    cs:__imp_NsiAllocateAndGetTable
0x18007cd5f  nop     dword ptr [rax+rax+00h]
0x18007cd64  test    eax, eax
0x18007cd66  jz      short loc_18007CD81
0x18007cd68  lea     rdx, aNsiallocateand_1; "NsiAllocateAndGetTable failed: Status=%"...
0x18007cd6f  mov     r8d, eax
0x18007cd72  mov     ecx, 4000000h
0x18007cd77  call    EventWrite0
0x18007cd7c  jmp     loc_18007CE60
0x18007cd81  mov     edi, r12d
0x18007cd84  cmp     [rbp+57h+var_70], r12d
0x18007cd88  jbe     loc_18007CE25
0x18007cd8e  mov     rax, [rbp+57h+var_60]
0x18007cd92  mov     ecx, edi
0x18007cd94  shl     rcx, 5
0x18007cd98  mov     r14d, edi
0x18007cd9b  mov     eax, [rcx+rax+4]
0x18007cd9f  cmp     eax, 18h
0x18007cda2  jz      short loc_18007CE1A
0x18007cda4  cmp     eax, 0EDh
0x18007cda9  jz      short loc_18007CE1A
0x18007cdab  add     eax, 0FFFFFF0Dh
0x18007cdb0  cmp     eax, 1
0x18007cdb3  jbe     short loc_18007CE1A
0x18007cdb5  mov     rcx, [rbp+57h+var_68]
0x18007cdb9  mov     rcx, [rcx+r14*8]
0x18007cdbd  call    ClatMgrFindInterface
0x18007cdc2  mov     rbx, rax
0x18007cdc5  test    rax, rax
0x18007cdc8  jnz     short loc_18007CDE3
0x18007cdca  call    ClatMgrAddInterface
0x18007cdcf  test    eax, eax
0x18007cdd1  jnz     short loc_18007CE35
0x18007cdd3  mov     rcx, [rbp+57h+var_68]
0x18007cdd7  mov     rcx, [rcx+r14*8]
0x18007cddb  call    ClatMgrFindInterface
0x18007cde0  mov     rbx, rax
0x18007cde3  mov     [rbx+18h], r12b
0x18007cde7  cmp     byte ptr cs:word_1800CBFC9, r12b
0x18007cdee  jz      short loc_18007CDF8
0x18007cdf0  mov     rcx, rbx
0x18007cdf3  call    ClatMgrCheckTriggerPref64Ra
0x18007cdf8  cmp     byte ptr cs:word_1800CBFC9+1, r12b
0x18007cdff  jz      short loc_18007CE09
0x18007ce01  mov     rcx, rbx
0x18007ce04  call    ClatMgrCheckTriggerDhcp108
0x18007ce09  cmp     cs:byte_1800CBFCB, r12b
0x18007ce10  jz      short loc_18007CE1A
0x18007ce12  mov     rcx, rbx
0x18007ce15  call    ClatMgrCheckTriggerNoIpv4
0x18007ce1a  inc     edi
0x18007ce1c  cmp     edi, [rbp+57h+var_70]
0x18007ce1f  jb      loc_18007CD8E
0x18007ce25  mov     rbx, cs:qword_1800CBFD0
0x18007ce2c  lea     rdi, qword_1800CBFD0
0x18007ce33  jmp     short loc_18007CE5B
0x18007ce35  lea     rdx, aClatmgraddinte; "ClatMgrAddInterface failed: Status=%d"
0x18007ce3c  jmp     loc_18007CD6F
0x18007ce41  mov     rax, rbx
0x18007ce44  mov     rbx, [rbx]
0x18007ce47  cmp     [rax+18h], r12b
0x18007ce4b  jz      short loc_18007CE57
0x18007ce4d  mov     rcx, rax
0x18007ce50  call    ClatMgrRemoveInterface
0x18007ce55  jmp     short loc_18007CE5B
0x18007ce57  mov     byte ptr [rax+18h], 1
0x18007ce5b  cmp     rbx, rdi
0x18007ce5e  jnz     short loc_18007CE41
0x18007ce60  mov     rcx, [rbp+57h+var_68]
0x18007ce64  test    rcx, rcx
0x18007ce67  jz      short loc_18007CE80
0x18007ce69  mov     r9, [rbp+57h+var_60]
0x18007ce6d  xor     r8d, r8d
0x18007ce70  mov     rdx, [rbp+57h+var_58]
0x18007ce74  call    cs:__imp_NsiFreeTable
0x18007ce7b  nop     dword ptr [rax+rax+00h]
0x18007ce80  mov     rcx, r15; lpCriticalSection
0x18007ce83  call    cs:__imp_LeaveCriticalSection
0x18007ce8a  nop     dword ptr [rax+rax+00h]
0x18007ce8f  mov     rcx, [rbp+57h+var_38]
0x18007ce93  xor     rcx, rsp; StackCookie
0x18007ce96  call    __security_check_cookie
0x18007ce9b  add     rsp, 0B8h
0x18007cea2  pop     r15
0x18007cea4  pop     r14
0x18007cea6  pop     r12
0x18007cea8  pop     rdi
0x18007cea9  pop     rbx
0x18007ceaa  pop     rbp
0x18007ceab  retn
```
