# ClatMgrProcessUpdate

- ea: `0x18007cafc`
- end: `0x18007cd97`
- name: `ClatMgrProcessUpdate`
- size: `667`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18007caf0`
- `0x18007cda0`
- `0x18007d0b0`

## callees

- `0x18000d7b0`
- `0x180047178`
- `0x1800471a4`
- `0x18004730c`
- `0x18004b630`
- `0x18007be30`
- `0x18007bec0`
- `0x18007c018`
- `0x18007c2b8`
- `0x18007c630`
- `0x18007cafc`
- `0x18007d128`
- `0x18007d170`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cb36`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cb36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cd6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cd6d`
- `NSI!NsiFreeTable` at `0x18007cd5e`
- `NSI!NsiFreeTable` at `0x18007cd5e`
- `NSI!NsiAllocateAndGetTable` at `0x18007cc42`
- `NSI!NsiAllocateAndGetTable` at `0x18007cc42`
- `IPXLATCFG!IPxlatPolicyMgrReadConfiguration` at `0x18007cb83`
- `IPXLATCFG!IPxlatPolicyMgrReadConfiguration` at `0x18007cb83`

## string_xrefs

- `0x18007cb48`: `Service exit event signalled. Skipping processing.`

## pseudocode

```c
void __fastcall ClatMgrProcessUpdate(LPCRITICAL_SECTION lpCriticalSection)
{
  bool v2; // bl
  char v3; // di
  unsigned int Table; // eax
  unsigned int i; // edi
  int v6; // eax
  __int64 v7; // rcx
  __int64 Interface; // rbx
  unsigned int v9; // eax
  __int64 *v10; // rbx
  __int64 *v11; // rax
  unsigned int v12; // [rsp+70h] [rbp-19h] BYREF
  __int64 v13; // [rsp+78h] [rbp-11h] BYREF
  __int64 v14; // [rsp+80h] [rbp-9h] BYREF
  __int64 v15; // [rsp+88h] [rbp-1h] BYREF
  __int128 v16; // [rsp+90h] [rbp+7h] BYREF
  int v17; // [rsp+A0h] [rbp+17h]

  v13 = 0;
  v15 = 0;
  v14 = 0;
  v12 = 0;
  EnterCriticalSection(lpCriticalSection);
  if ( LOBYTE(lpCriticalSection[1].LockSemaphore) )
  {
    EventWrite0(0x4000000, L"Service exit event signalled. Skipping processing.");
    goto LABEL_37;
  }
  v2 = 1;
  if ( (unsigned int)Feature_CLAT_Preview2_GPO__private_IsEnabledDeviceUsageNoInline() )
  {
    v16 = 0;
    v17 = 0;
    IPxlatPolicyMgrReadConfiguration(&v16);
    v3 = (_DWORD)v16 != 0;
    if ( (unsigned int)Feature_CLAT_Preview2_AutoEnable__private_IsEnabledDeviceUsageNoInline() )
      v2 = v17 != 0;
  }
  else
  {
    v3 = ClatMgrCheckPolicy();
  }
  if ( (unsigned int)Feature_CLAT_Preview2_AutoEnable__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( LOBYTE(lpCriticalSection[6].LockCount) && !v2 )
    {
      EventWrite0(0x4000000, L"AutoEnable disabled. Disabling CLAT on all interfaces where it was auto enabled.");
      ClatMgrFlushInterfaces();
    }
    LOBYTE(lpCriticalSection[6].LockCount) = v2;
  }
  if ( v3 && v2 )
  {
    Table = NsiAllocateAndGetTable(1, &NPI_MS_IPV6_MODULEID, 7, &v13, 8, &v15, 240, 0, 0, &v14, 32, &v12, 0);
    if ( Table )
    {
      EventWrite0(0x4000000, L"NsiAllocateAndGetTable failed: Status=%d", Table);
      goto LABEL_37;
    }
    for ( i = 0; i < v12; ++i )
    {
      v6 = *(_DWORD *)(32LL * i + v14 + 4);
      if ( v6 != 24 && v6 != 237 && (unsigned int)(v6 - 243) > 1 )
      {
        Interface = ClatMgrFindInterface(*(_QWORD *)(v13 + 8LL * i));
        if ( !Interface )
        {
          v9 = ClatMgrAddInterface(v7);
          if ( v9 )
          {
            EventWrite0(0x4000000, L"ClatMgrAddInterface failed: Status=%d", v9);
            goto LABEL_37;
          }
          Interface = ClatMgrFindInterface(*(_QWORD *)(v13 + 8LL * i));
        }
        *(_BYTE *)(Interface + 24) = 0;
        if ( (_BYTE)word_1800CBFB9 )
          ClatMgrCheckTriggerPref64Ra(Interface);
        if ( HIBYTE(word_1800CBFB9) )
          ClatMgrCheckTriggerDhcp108(Interface);
        if ( byte_1800CBFBB )
          ClatMgrCheckTriggerNoIpv4(Interface);
      }
    }
  }
  v10 = (__int64 *)qword_1800CBFC0;
  while ( v10 != &qword_1800CBFC0 )
  {
    v11 = v10;
    v10 = (__int64 *)*v10;
    if ( *((_BYTE *)v11 + 24) )
      ClatMgrRemoveInterface(v11);
    else
      *((_BYTE *)v11 + 24) = 1;
  }
LABEL_37:
  if ( v13 )
    NsiFreeTable(v13, v15, 0, v14);
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18007cafc  push    rbp
0x18007cafe  push    rbx
0x18007caff  push    rdi
0x18007cb00  push    r12
0x18007cb02  push    r14
0x18007cb04  push    r15
0x18007cb06  lea     rbp, [rsp-2Fh]
0x18007cb0b  sub     rsp, 0B8h
0x18007cb12  mov     rax, cs:__security_cookie
0x18007cb19  xor     rax, rsp
0x18007cb1c  mov     [rbp+57h+var_38], rax
0x18007cb20  xor     r12d, r12d
0x18007cb23  mov     r14, rcx
0x18007cb26  mov     [rbp+57h+var_68], r12
0x18007cb2a  mov     [rbp+57h+var_58], r12
0x18007cb2e  mov     [rbp+57h+var_60], r12
0x18007cb32  mov     [rbp+57h+var_70], r12d
0x18007cb36  call    cs:__imp_EnterCriticalSection
0x18007cb3d  nop     dword ptr [rax+rax+00h]
0x18007cb42  cmp     [r14+40h], r12b
0x18007cb46  jz      short loc_18007CB5E
0x18007cb48  lea     rdx, aServiceExitEve; "Service exit event signalled. Skipping "...
0x18007cb4f  mov     ecx, 4000000h
0x18007cb54  call    EventWrite0
0x18007cb59  jmp     loc_18007CD4A
0x18007cb5e  mov     bl, 1
0x18007cb60  call    Feature_CLAT_Preview2_GPO__private_IsEnabledDeviceUsageNoInline
0x18007cb65  test    eax, eax
0x18007cb67  jnz     short loc_18007CB73
0x18007cb69  call    ClatMgrCheckPolicy
0x18007cb6e  mov     dil, al
0x18007cb71  jmp     short loc_18007CBA7
0x18007cb73  xorps   xmm0, xmm0
0x18007cb76  lea     rcx, [rbp+57h+var_50]
0x18007cb7a  xor     eax, eax
0x18007cb7c  movups  [rbp+57h+var_50], xmm0
0x18007cb80  mov     [rbp+57h+var_40], eax
0x18007cb83  call    cs:__imp_IPxlatPolicyMgrReadConfiguration
0x18007cb8a  nop     dword ptr [rax+rax+00h]
0x18007cb8f  cmp     dword ptr [rbp+57h+var_50], r12d
0x18007cb93  setnz   dil
0x18007cb97  call    Feature_CLAT_Preview2_AutoEnable__private_IsEnabledDeviceUsageNoInline
0x18007cb9c  test    eax, eax
0x18007cb9e  jz      short loc_18007CBA7
0x18007cba0  cmp     [rbp+57h+var_40], r12d
0x18007cba4  setnz   bl
0x18007cba7  call    Feature_CLAT_Preview2_AutoEnable__private_IsEnabledDeviceUsageNoInline
0x18007cbac  test    eax, eax
0x18007cbae  jz      short loc_18007CBDA
0x18007cbb0  cmp     [r14+0F8h], r12b
0x18007cbb7  jz      short loc_18007CBD3
0x18007cbb9  test    bl, bl
0x18007cbbb  jnz     short loc_18007CBD3
0x18007cbbd  lea     rdx, aAutoenableDisa; "AutoEnable disabled. Disabling CLAT on "...
0x18007cbc4  mov     ecx, 4000000h
0x18007cbc9  call    EventWrite0
0x18007cbce  call    ClatMgrFlushInterfaces
0x18007cbd3  mov     [r14+0F8h], bl
0x18007cbda  test    dil, dil
0x18007cbdd  jz      loc_18007CD0F
0x18007cbe3  test    bl, bl
0x18007cbe5  jz      loc_18007CD0F
0x18007cbeb  mov     [rsp+0E0h+var_80], r12b
0x18007cbf0  lea     rax, [rbp+57h+var_70]
0x18007cbf4  mov     [rsp+0E0h+var_88], rax
0x18007cbf9  lea     r9, [rbp+57h+var_68]
0x18007cbfd  mov     [rsp+0E0h+var_90], 20h ; ' '
0x18007cc05  lea     rax, [rbp+57h+var_60]
0x18007cc09  mov     [rsp+0E0h+var_98], rax
0x18007cc0e  lea     rdx, NPI_MS_IPV6_MODULEID
0x18007cc15  mov     [rsp+0E0h+var_A0], r12d
0x18007cc1a  lea     rax, [rbp+57h+var_58]
0x18007cc1e  mov     [rsp+0E0h+var_A8], r12
0x18007cc23  mov     r8d, 7
0x18007cc29  mov     [rsp+0E0h+var_B0], 0F0h
0x18007cc31  mov     [rsp+0E0h+var_B8], rax
0x18007cc36  mov     [rsp+0E0h+var_C0], 8
0x18007cc3e  lea     ecx, [r8-6]
0x18007cc42  call    cs:__imp_NsiAllocateAndGetTable
0x18007cc49  nop     dword ptr [rax+rax+00h]
0x18007cc4e  test    eax, eax
0x18007cc50  jz      short loc_18007CC6B
0x18007cc52  lea     rdx, aNsiallocateand_1; "NsiAllocateAndGetTable failed: Status=%"...
0x18007cc59  mov     r8d, eax
0x18007cc5c  mov     ecx, 4000000h
0x18007cc61  call    EventWrite0
0x18007cc66  jmp     loc_18007CD4A
0x18007cc6b  mov     edi, r12d
0x18007cc6e  cmp     [rbp+57h+var_70], r12d
0x18007cc72  jbe     loc_18007CD0F
0x18007cc78  mov     rax, [rbp+57h+var_60]
0x18007cc7c  mov     ecx, edi
0x18007cc7e  shl     rcx, 5
0x18007cc82  mov     r15d, edi
0x18007cc85  mov     eax, [rcx+rax+4]
0x18007cc89  cmp     eax, 18h
0x18007cc8c  jz      short loc_18007CD04
0x18007cc8e  cmp     eax, 0EDh
0x18007cc93  jz      short loc_18007CD04
0x18007cc95  add     eax, 0FFFFFF0Dh
0x18007cc9a  cmp     eax, 1
0x18007cc9d  jbe     short loc_18007CD04
0x18007cc9f  mov     rcx, [rbp+57h+var_68]
0x18007cca3  mov     rcx, [rcx+r15*8]
0x18007cca7  call    ClatMgrFindInterface
0x18007ccac  mov     rbx, rax
0x18007ccaf  test    rax, rax
0x18007ccb2  jnz     short loc_18007CCCD
0x18007ccb4  call    ClatMgrAddInterface
0x18007ccb9  test    eax, eax
0x18007ccbb  jnz     short loc_18007CD1F
0x18007ccbd  mov     rcx, [rbp+57h+var_68]
0x18007ccc1  mov     rcx, [rcx+r15*8]
0x18007ccc5  call    ClatMgrFindInterface
0x18007ccca  mov     rbx, rax
0x18007cccd  mov     [rbx+18h], r12b
0x18007ccd1  cmp     byte ptr cs:word_1800CBFB9, r12b
0x18007ccd8  jz      short loc_18007CCE2
0x18007ccda  mov     rcx, rbx
0x18007ccdd  call    ClatMgrCheckTriggerPref64Ra
0x18007cce2  cmp     byte ptr cs:word_1800CBFB9+1, r12b
0x18007cce9  jz      short loc_18007CCF3
0x18007cceb  mov     rcx, rbx
0x18007ccee  call    ClatMgrCheckTriggerDhcp108
0x18007ccf3  cmp     cs:byte_1800CBFBB, r12b
0x18007ccfa  jz      short loc_18007CD04
0x18007ccfc  mov     rcx, rbx
0x18007ccff  call    ClatMgrCheckTriggerNoIpv4
0x18007cd04  inc     edi
0x18007cd06  cmp     edi, [rbp+57h+var_70]
0x18007cd09  jb      loc_18007CC78
0x18007cd0f  mov     rbx, cs:qword_1800CBFC0
0x18007cd16  lea     rdi, qword_1800CBFC0
0x18007cd1d  jmp     short loc_18007CD45
0x18007cd1f  lea     rdx, aClatmgraddinte; "ClatMgrAddInterface failed: Status=%d"
0x18007cd26  jmp     loc_18007CC59
0x18007cd2b  mov     rax, rbx
0x18007cd2e  mov     rbx, [rbx]
0x18007cd31  cmp     [rax+18h], r12b
0x18007cd35  jz      short loc_18007CD41
0x18007cd37  mov     rcx, rax
0x18007cd3a  call    ClatMgrRemoveInterface
0x18007cd3f  jmp     short loc_18007CD45
0x18007cd41  mov     byte ptr [rax+18h], 1
0x18007cd45  cmp     rbx, rdi
0x18007cd48  jnz     short loc_18007CD2B
0x18007cd4a  mov     rcx, [rbp+57h+var_68]
0x18007cd4e  test    rcx, rcx
0x18007cd51  jz      short loc_18007CD6A
0x18007cd53  mov     r9, [rbp+57h+var_60]
0x18007cd57  xor     r8d, r8d
0x18007cd5a  mov     rdx, [rbp+57h+var_58]
0x18007cd5e  call    cs:__imp_NsiFreeTable
0x18007cd65  nop     dword ptr [rax+rax+00h]
0x18007cd6a  mov     rcx, r14; lpCriticalSection
0x18007cd6d  call    cs:__imp_LeaveCriticalSection
0x18007cd74  nop     dword ptr [rax+rax+00h]
0x18007cd79  mov     rcx, [rbp+57h+var_38]
0x18007cd7d  xor     rcx, rsp; StackCookie
0x18007cd80  call    __security_check_cookie
0x18007cd85  add     rsp, 0B8h
0x18007cd8c  pop     r15
0x18007cd8e  pop     r14
0x18007cd90  pop     r12
0x18007cd92  pop     rdi
0x18007cd93  pop     rbx
0x18007cd94  pop     rbp
0x18007cd95  retn
```
