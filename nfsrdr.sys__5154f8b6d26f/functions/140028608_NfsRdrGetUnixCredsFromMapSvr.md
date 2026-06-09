# NfsRdrGetUnixCredsFromMapSvr

- ea: `0x140028608`
- end: `0x140028867`
- name: `NfsRdrGetUnixCredsFromMapSvr`
- size: `607`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140025be0`

## callees

- `0x1400159cc`
- `0x1400159fc`
- `0x140019d7c`
- `0x140020fa8`
- `0x1400219e8`
- `0x140028608`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400287ac`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400287ac`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140028794`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140028794`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028813`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028813`
- `ntoskrnl!ExAllocatePool2` at `0x1400286b9`
- `ntoskrnl!ExAllocatePool2` at `0x1400286b9`
- `ksecdd!SecLookupAccountSid` at `0x140028715`
- `ksecdd!SecLookupAccountSid` at `0x140028715`

## pseudocode

```c
__int64 __fastcall NfsRdrGetUnixCredsFromMapSvr(__int64 a1, __int64 a2, __int64 a3, void **a4, _BYTE *a5)
{
  _BYTE *v5; // r14
  __int64 v6; // rcx
  void *v8; // r8
  int UnixCredsFromSid; // ebx
  WCHAR *Pool2; // rax
  WCHAR *v12; // r15
  void *v14; // rcx
  struct _UNICODE_STRING Destination; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING NameBuffer; // [rsp+40h] [rbp-18h] BYREF
  ULONG DomainSize; // [rsp+A8h] [rbp+50h] BYREF
  __int64 NameUse; // [rsp+B0h] [rbp+58h] BYREF
  ULONG NameSize; // [rsp+B8h] [rbp+60h] BYREF

  NameUse = a3;
  v5 = a5;
  v6 = *(_QWORD *)(a1 + 32);
  LODWORD(NameUse) = 0;
  NameSize = 0;
  DomainSize = 0;
  v8 = *a4;
  NameBuffer = 0;
  *a5 = 0;
  Destination = 0;
  UnixCredsFromSid = MapGetUnixCredsFromSid(v6, a2, v8, (_DWORD *)(a2 + 36));
  if ( UnixCredsFromSid < 0 )
  {
    if ( UnixCredsFromSid == -1073545126 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
      Pool2 = (WCHAR *)ExAllocatePool2(258, 1058, 844260942);
      v12 = Pool2;
      if ( !Pool2 )
        return 3221225626LL;
      v14 = *a4;
      Destination.Buffer = Pool2;
      NameBuffer.Buffer = Pool2 + 273;
      *(_DWORD *)&Destination.Length = 35782656;
      *(_DWORD *)&NameBuffer.Length = 0x2000000;
      UnixCredsFromSid = SecLookupAccountSid(
                           v14,
                           &NameSize,
                           &NameBuffer,
                           &DomainSize,
                           &Destination,
                           (PSID_NAME_USE)&NameUse);
      if ( UnixCredsFromSid >= 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_ZZ(
            WPP_GLOBAL_Control->AttachedDevice,
            71,
            (unsigned int)WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
            (unsigned int)&Destination,
            (__int64)&NameBuffer);
        if ( RtlAppendUnicodeToString(&Destination, L"\\") < 0
          || RtlAppendUnicodeStringToString(&Destination, &NameBuffer) < 0 )
        {
          UnixCredsFromSid = -1073741670;
        }
        else
        {
          UnixCredsFromSid = MapGetUnixCredsFromNTUserName(
                               *(_QWORD *)(a1 + 32),
                               a2,
                               &Destination,
                               (unsigned int *)(a2 + 36));
          if ( UnixCredsFromSid < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
            }
          }
          else
          {
            *v5 = 1;
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
      }
      ExFreePoolWithTag(v12, 0);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
    }
  }
  else
  {
    *v5 = 1;
  }
  return (unsigned int)UnixCredsFromSid;
}

```

## disassembly

```asm
0x140028608  mov     [rsp-40h+arg_10], r8
0x14002860d  mov     [rsp-40h+arg_0], rcx
0x140028612  push    rbp
0x140028613  push    rbx
0x140028614  push    rsi
0x140028615  push    rdi
0x140028616  push    r12
0x140028618  push    r13
0x14002861a  push    r14
0x14002861c  push    r15
0x14002861e  mov     rbp, rsp
0x140028621  sub     rsp, 58h
0x140028625  mov     r14, [rbp+arg_20]
0x140028629  xor     edi, edi
0x14002862b  mov     rcx, [rcx+20h]
0x14002862f  mov     r12, r9
0x140028632  xorps   xmm0, xmm0
0x140028635  mov     dword ptr [rbp+arg_10], edi
0x140028638  xorps   xmm1, xmm1
0x14002863b  mov     [rbp+NameSize], edi
0x14002863e  lea     r9, [rdx+24h]
0x140028642  mov     [rbp+DomainSize], edi
0x140028645  mov     r8, [r12]
0x140028649  mov     r13, rdx
0x14002864c  movups  xmmword ptr [rbp+NameBuffer.Length], xmm0
0x140028650  mov     [r14], dil
0x140028653  movups  xmmword ptr [rbp+Destination.Length], xmm1
0x140028657  call    MapGetUnixCredsFromSid
0x14002865c  mov     ebx, eax
0x14002865e  test    eax, eax
0x140028660  js      short loc_14002866B
0x140028662  mov     byte ptr [r14], 1
0x140028666  jmp     loc_140028853
0x14002866b  cmp     ebx, 0C003005Ah
0x140028671  jnz     loc_140028821
0x140028677  mov     rcx, cs:WPP_GLOBAL_Control
0x14002867e  lea     rdi, WPP_GLOBAL_Control
0x140028685  lea     rsi, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x14002868c  cmp     rcx, rdi
0x14002868f  jz      short loc_1400286A9
0x140028691  mov     eax, [rcx+2Ch]
0x140028694  test    al, 1
0x140028696  jz      short loc_1400286A9
0x140028698  mov     rcx, [rcx+18h]
0x14002869c  mov     edx, 45h ; 'E'
0x1400286a1  mov     r8, rsi
0x1400286a4  call    WPP_SF_
0x1400286a9  mov     edx, 422h
0x1400286ae  mov     ecx, 102h
0x1400286b3  mov     r8d, 3252664Eh
0x1400286b9  call    cs:__imp_ExAllocatePool2
0x1400286c0  nop     dword ptr [rax+rax+00h]
0x1400286c5  mov     r15, rax
0x1400286c8  test    rax, rax
0x1400286cb  jnz     short loc_1400286D7
0x1400286cd  mov     eax, 0C000009Ah
0x1400286d2  jmp     loc_140028855
0x1400286d7  mov     rcx, [r12]; Sid
0x1400286db  lea     r9, [rbp+DomainSize]; DomainSize
0x1400286df  add     rax, 222h
0x1400286e5  mov     [rbp+Destination.Buffer], r15
0x1400286e9  mov     [rbp+NameBuffer.Buffer], rax
0x1400286ed  lea     r8, [rbp+NameBuffer]; NameBuffer
0x1400286f1  lea     rax, [rbp+arg_10]
0x1400286f5  mov     dword ptr [rbp+Destination.Length], 2220000h
0x1400286fc  mov     [rsp+58h+NameUse], rax; NameUse
0x140028701  lea     rdx, [rbp+NameSize]; NameSize
0x140028705  lea     rax, [rbp+Destination]
0x140028709  mov     dword ptr [rbp+NameBuffer.Length], 2000000h
0x140028710  mov     [rsp+58h+DomainBuffer], rax; DomainBuffer
0x140028715  call    cs:__imp_SecLookupAccountSid
0x14002871c  nop     dword ptr [rax+rax+00h]
0x140028721  mov     ebx, eax
0x140028723  test    eax, eax
0x140028725  jns     short loc_140028758
0x140028727  mov     rcx, cs:WPP_GLOBAL_Control
0x14002872e  cmp     rcx, rdi
0x140028731  jz      loc_14002880E
0x140028737  mov     eax, [rcx+2Ch]
0x14002873a  test    al, 1
0x14002873c  jz      loc_14002880E
0x140028742  mov     rcx, [rcx+18h]
0x140028746  mov     edx, 46h ; 'F'
0x14002874b  mov     r8, rsi
0x14002874e  call    WPP_SF_
0x140028753  jmp     loc_14002880E
0x140028758  mov     rcx, cs:WPP_GLOBAL_Control
0x14002875f  cmp     rcx, rdi
0x140028762  jz      short loc_140028789
0x140028764  mov     eax, [rcx+2Ch]
0x140028767  test    al, 4
0x140028769  jz      short loc_140028789
0x14002876b  mov     rcx, [rcx+18h]
0x14002876f  lea     rax, [rbp+NameBuffer]
0x140028773  mov     edx, 47h ; 'G'
0x140028778  mov     [rsp+58h+DomainBuffer], rax
0x14002877d  lea     r9, [rbp+Destination]
0x140028781  mov     r8, rsi
0x140028784  call    WPP_SF_ZZ
0x140028789  lea     rdx, Source; "\\"
0x140028790  lea     rcx, [rbp+Destination]; Destination
0x140028794  call    cs:__imp_RtlAppendUnicodeToString
0x14002879b  nop     dword ptr [rax+rax+00h]
0x1400287a0  test    eax, eax
0x1400287a2  js      short loc_140028809
0x1400287a4  lea     rdx, [rbp+NameBuffer]; Source
0x1400287a8  lea     rcx, [rbp+Destination]; Destination
0x1400287ac  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400287b3  nop     dword ptr [rax+rax+00h]
0x1400287b8  test    eax, eax
0x1400287ba  js      short loc_140028809
0x1400287bc  mov     rcx, [rbp+arg_0]
0x1400287c0  lea     r9, [r13+24h]
0x1400287c4  lea     r8, [rbp+Destination]
0x1400287c8  mov     rdx, r13
0x1400287cb  mov     rcx, [rcx+20h]
0x1400287cf  call    MapGetUnixCredsFromNTUserName
0x1400287d4  mov     ebx, eax
0x1400287d6  test    eax, eax
0x1400287d8  js      short loc_1400287E0
0x1400287da  mov     byte ptr [r14], 1
0x1400287de  jmp     short loc_14002880E
0x1400287e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400287e7  cmp     rcx, rdi
0x1400287ea  jz      short loc_14002880E
0x1400287ec  mov     eax, [rcx+2Ch]
0x1400287ef  test    al, 1
0x1400287f1  jz      short loc_14002880E
0x1400287f3  mov     rcx, [rcx+18h]
0x1400287f7  mov     edx, 48h ; 'H'
0x1400287fc  mov     r9d, ebx
0x1400287ff  mov     r8, rsi
0x140028802  call    WPP_SF_d
0x140028807  jmp     short loc_14002880E
0x140028809  mov     ebx, 0C000009Ah
0x14002880e  xor     edx, edx; Tag
0x140028810  mov     rcx, r15; P
0x140028813  call    cs:__imp_ExFreePoolWithTag
0x14002881a  nop     dword ptr [rax+rax+00h]
0x14002881f  jmp     short loc_140028853
0x140028821  mov     rcx, cs:WPP_GLOBAL_Control
0x140028828  lea     rdi, WPP_GLOBAL_Control
0x14002882f  cmp     rcx, rdi
0x140028832  jz      short loc_140028853
0x140028834  mov     eax, [rcx+2Ch]
0x140028837  test    al, 1
0x140028839  jz      short loc_140028853
0x14002883b  mov     rcx, [rcx+18h]
0x14002883f  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140028846  mov     edx, 49h ; 'I'
0x14002884b  mov     r9d, ebx
0x14002884e  call    WPP_SF_d
0x140028853  mov     eax, ebx
0x140028855  add     rsp, 58h
0x140028859  pop     r15
0x14002885b  pop     r14
0x14002885d  pop     r13
0x14002885f  pop     r12
0x140028861  pop     rdi
0x140028862  pop     rsi
0x140028863  pop     rbx
0x140028864  pop     rbp
0x140028865  retn
```
