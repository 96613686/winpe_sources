# _RegRtlOpenProtectedKeyTransacted

- ea: `0x180003f50`
- end: `0x1800045a4`
- name: `_RegRtlOpenProtectedKeyTransacted`
- size: `1620`
- prototype: `__int64 __fastcall(__int64, __int64, int, unsigned int, __int64)`
- caller_count: `11`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001304`
- `0x1800026b0`
- `0x180002a80`
- `0x180003500`
- `0x1800037f0`
- `0x180003e40`
- `0x180003ed0`
- `0x1800051c8`
- `0x180005434`
- `0x18007c2e4`
- `0x18007c368`

## callees

- `0x180001490`
- `0x180003f50`
- `0x1800045b0`
- `0x18003bc80`
- `0x18007c5b8`
- `0x18007c8c8`
- `0x18007c8e8`
- `0x18007c9c0`

## import_xrefs

- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x180004224`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x180004224`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180004250`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180004250`
- `ntdll!NtClose` at `0x180004583`
- `ntdll!NtClose` at `0x18000458e`
- `ntdll!NtClose` at `0x180004599`
- `ntdll!NtClose` at `0x180004583`
- `ntdll!NtClose` at `0x18000458e`
- `ntdll!NtClose` at `0x180004599`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800043a0`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180004424`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x1800043a0`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180004424`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800044b1`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800044b1`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000437d`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180004407`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000448c`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000437d`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180004407`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000448c`
- `ntdll!RtlSubAuthoritySid` at `0x18000429a`
- `ntdll!RtlSubAuthoritySid` at `0x1800042b3`
- `ntdll!RtlSubAuthoritySid` at `0x1800042f4`
- `ntdll!RtlSubAuthoritySid` at `0x18000429a`
- `ntdll!RtlSubAuthoritySid` at `0x1800042b3`
- `ntdll!RtlSubAuthoritySid` at `0x1800042f4`
- `ntdll!RtlInitializeSid` at `0x180004280`
- `ntdll!RtlInitializeSid` at `0x1800042da`
- `ntdll!RtlInitializeSid` at `0x180004280`
- `ntdll!RtlInitializeSid` at `0x1800042da`
- `ntdll!RtlFreeHeap` at `0x1800041de`
- `ntdll!RtlFreeHeap` at `0x18000455b`
- `ntdll!RtlFreeHeap` at `0x180004578`
- `ntdll!RtlFreeHeap` at `0x1800041de`
- `ntdll!RtlFreeHeap` at `0x18000455b`
- `ntdll!RtlFreeHeap` at `0x180004578`
- `ntdll!RtlAllocateHeap` at `0x1800041fb`
- `ntdll!RtlAllocateHeap` at `0x1800041fb`
- `ntdll!NtSetSecurityObject` at `0x1800043c5`
- `ntdll!NtSetSecurityObject` at `0x18000445f`
- `ntdll!NtSetSecurityObject` at `0x1800044cd`
- `ntdll!NtSetSecurityObject` at `0x18000453a`
- `ntdll!NtSetSecurityObject` at `0x1800043c5`
- `ntdll!NtSetSecurityObject` at `0x18000445f`
- `ntdll!NtSetSecurityObject` at `0x1800044cd`
- `ntdll!NtSetSecurityObject` at `0x18000453a`

## pseudocode

```c
__int64 __fastcall RegRtlOpenProtectedKeyTransacted(__int64 a1, __int64 a2, int a3, unsigned int a4, __int64 a5)
{
  PVOID Heap; // rbx
  NTSTATUS KeyTransacted; // edi
  __int64 v12; // rdx
  int KeySecurity; // edi
  PSECURITY_DESCRIPTOR v14; // rsi
  unsigned __int8 OwnerDefaulted; // [rsp+50h] [rbp-F8h] BYREF
  char v16; // [rsp+51h] [rbp-F7h]
  unsigned __int8 DaclDefaulted; // [rsp+52h] [rbp-F6h] BYREF
  unsigned __int8 DaclPresent[5]; // [rsp+53h] [rbp-F5h] BYREF
  int v19; // [rsp+58h] [rbp-F0h] BYREF
  int v20; // [rsp+5Ch] [rbp-ECh]
  __int64 v21; // [rsp+60h] [rbp-E8h]
  SIZE_T Size; // [rsp+68h] [rbp-E0h] BYREF
  HANDLE v23; // [rsp+70h] [rbp-D8h]
  PSID Owner; // [rsp+78h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+80h] [rbp-C8h]
  int v26; // [rsp+88h] [rbp-C0h]
  PACL Dacl; // [rsp+90h] [rbp-B8h] BYREF
  HANDLE v28; // [rsp+98h] [rbp-B0h]
  __int64 v29; // [rsp+A0h] [rbp-A8h]
  PSECURITY_DESCRIPTOR P; // [rsp+A8h] [rbp-A0h]
  _OWORD SecurityDescriptor[2]; // [rsp+B0h] [rbp-98h] BYREF
  __int64 v32; // [rsp+D0h] [rbp-78h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+D8h] [rbp-70h] BYREF
  _BYTE v34[12]; // [rsp+E0h] [rbp-68h] BYREF
  _BYTE Sid[20]; // [rsp+ECh] [rbp-5Ch] BYREF

  v29 = a5;
  Handle = 0;
  v28 = 0;
  v23 = 0;
  v26 = 0;
  Heap = 0;
  LODWORD(Size) = 0;
  Owner = 0;
  OwnerDefaulted = 0;
  Dacl = 0;
  DaclPresent[0] = 0;
  DaclDefaulted = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v32 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  P = 0;
  KeyTransacted = RegRtlOpenKeyTransacted(a1, a2);
  if ( KeyTransacted != -1073741790 )
    goto LABEL_2;
  if ( a2 )
  {
    if ( (a4 & 0xFEFDFFE6) != 0 )
    {
      if ( (a4 & 0xFEFDFFF9) == 0 )
      {
        v12 = 1;
        v19 = 18;
LABEL_19:
        v21 = RegRtlEnableThreadPrivileges(&v19, v12);
        KeyTransacted = RegRtlCreateKeyTransacted(a1, a2, a3 | 4u, a4, 0);
        RegRtlRestoreThreadPrivileges(v21);
        if ( KeyTransacted != -1073741790 && KeyTransacted != -1073741727 )
          goto LABEL_2;
        goto LABEL_21;
      }
      if ( (a4 & 0xFEFCFFE0) != 0 )
        goto LABEL_21;
      v12 = 2;
      v20 = 18;
    }
    else
    {
      v12 = 1;
    }
    v19 = 17;
    goto LABEL_19;
  }
LABEL_21:
  KeyTransacted = RegRtlOpenKeyTransacted(a1, a2);
  if ( KeyTransacted != -1073741790 )
  {
LABEL_53:
    if ( KeyTransacted >= 0 )
    {
      KeyTransacted = RegRtlUnlockKey(v23);
      if ( KeyTransacted >= 0 )
      {
        KeyTransacted = RegRtlOpenKeyTransacted(a1, a2);
        v14 = P;
        if ( P )
        {
          NtSetSecurityObject(v23, 4u, P);
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
        }
      }
    }
    goto LABEL_2;
  }
  v16 = 0;
  if ( (int)RegRtlOpenKeyTransacted(a1, a2) >= 0 )
  {
    Heap = 0;
    LODWORD(Size) = 0;
    while ( 1 )
    {
      KeySecurity = RegRtlGetKeySecurity(v28, 5, Heap, &Size);
      if ( KeySecurity != -1073741789 )
        break;
      if ( Heap )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)Size);
      if ( !Heap )
      {
        KeySecurity = -1073741801;
        break;
      }
    }
    if ( Heap )
    {
      if ( KeySecurity < 0 || RtlGetOwnerSecurityDescriptor(Heap, &Owner, &OwnerDefaulted) < 0 )
        Owner = 0;
      if ( KeySecurity < 0 || RtlGetDaclSecurityDescriptor(Heap, DaclPresent, &Dacl, &DaclDefaulted) < 0 )
        Dacl = 0;
      else
        v16 = 1;
    }
  }
  KeyTransacted = RtlInitializeSid(Sid, &IdentifierAuthority, 2u);
  if ( KeyTransacted >= 0 )
  {
    *RtlSubAuthoritySid(Sid, 0) = 32;
    *RtlSubAuthoritySid(Sid, 1u) = 544;
    if ( !Owner )
    {
      KeyTransacted = RtlInitializeSid(v34, &IdentifierAuthority, 1u);
      if ( KeyTransacted < 0 )
        goto LABEL_2;
      *RtlSubAuthoritySid(v34, 0) = 18;
      Owner = v34;
      OwnerDefaulted = 0;
    }
    v19 = 9;
    v20 = 18;
    v21 = RegRtlEnableThreadPrivileges(&v19, 2);
    KeyTransacted = RegRtlOpenKeyTransacted(a1, a2);
    RegRtlRestoreThreadPrivileges(v21);
    if ( KeyTransacted >= 0 )
    {
      KeyTransacted = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
      if ( KeyTransacted >= 0 )
      {
        KeyTransacted = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, Sid, 0);
        if ( KeyTransacted >= 0 )
        {
          KeyTransacted = NtSetSecurityObject(Handle, 1u, SecurityDescriptor);
          if ( KeyTransacted >= 0 )
          {
            KeyTransacted = RegRtlOpenKeyTransacted(a1, a2);
            if ( RtlCreateSecurityDescriptor(SecurityDescriptor, 1u) >= 0
              && RtlSetOwnerSecurityDescriptor(SecurityDescriptor, Owner, OwnerDefaulted) >= 0 )
            {
              v19 = 18;
              v21 = RegRtlEnableThreadPrivileges(&v19, 1);
              NtSetSecurityObject(Handle, 1u, SecurityDescriptor);
              RegRtlRestoreThreadPrivileges(v21);
            }
            if ( v23
              && v16
              && RtlCreateSecurityDescriptor(SecurityDescriptor, 1u) >= 0
              && RtlSetDaclSecurityDescriptor(SecurityDescriptor, DaclPresent[0], Dacl, DaclDefaulted) >= 0 )
            {
              NtSetSecurityObject(v23, 4u, SecurityDescriptor);
            }
            goto LABEL_53;
          }
        }
      }
    }
  }
LABEL_2:
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( v28 )
    NtClose(v28);
  if ( v23 )
    NtClose(v23);
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)KeyTransacted;
}

```

## disassembly

```asm
0x180003f50  mov     r11, rsp
0x180003f53  push    rbx
0x180003f54  push    rsi
0x180003f55  push    rdi
0x180003f56  push    r12
0x180003f58  push    r13
0x180003f5a  push    r14
0x180003f5c  push    r15
0x180003f5e  sub     rsp, 110h
0x180003f65  mov     rax, cs:__security_cookie
0x180003f6c  xor     rax, rsp
0x180003f6f  mov     [rsp+148h+var_48], rax
0x180003f77  mov     r14d, r9d
0x180003f7a  mov     r13d, r8d
0x180003f7d  mov     rsi, rdx
0x180003f80  mov     r15, rcx
0x180003f83  mov     rax, [rsp+148h+arg_20]
0x180003f8b  mov     [rsp+148h+var_A8], rax
0x180003f93  mov     r12, [rsp+148h+arg_28]
0x180003f9b  xor     edx, edx
0x180003f9d  mov     [r11-0C8h], rdx
0x180003fa4  mov     [r11-0B0h], rdx
0x180003fab  mov     [rsp+148h+var_D8], rdx
0x180003fb0  mov     [rsp+148h+var_C0], edx
0x180003fb7  mov     ebx, edx
0x180003fb9  mov     dword ptr [rsp+148h+Size], edx
0x180003fbd  mov     [rsp+148h+Owner], rdx
0x180003fc2  mov     [rsp+148h+OwnerDefaulted], dl
0x180003fc6  mov     [r11-0B8h], rdx
0x180003fcd  mov     [rsp+148h+DaclPresent], dl
0x180003fd1  mov     [rsp+148h+DaclDefaulted], dl
0x180003fd5  xorps   xmm0, xmm0
0x180003fd8  xor     ecx, ecx
0x180003fda  movups  [rsp+148h+SecurityDescriptor], xmm0
0x180003fe2  movups  [rsp+148h+var_88], xmm0
0x180003fea  mov     [r11-78h], rcx
0x180003fee  mov     [r11-70h], ecx
0x180003ff2  mov     word ptr [r11-6Ch], 500h
0x180003ff9  mov     [r11-0A0h], rdx
0x180004000  mov     [rsp+148h+var_120], r12
0x180004005  mov     [rsp+148h+var_128], rax
0x18000400a  mov     rdx, rsi
0x18000400d  mov     rcx, r15
0x180004010  call    _RegRtlOpenKeyTransacted
0x180004015  mov     edi, eax
0x180004017  cmp     eax, 0C0000022h
0x18000401c  jz      short loc_18000407C
0x18000401e  test    rbx, rbx
0x180004021  jnz     loc_180004566
0x180004027  mov     rcx, [rsp+148h+var_B0]; Handle
0x18000402f  test    rcx, rcx
0x180004032  jnz     loc_180004583
0x180004038  mov     rcx, [rsp+148h+var_D8]; Handle
0x18000403d  test    rcx, rcx
0x180004040  jnz     loc_18000458E
0x180004046  mov     rcx, [rsp+148h+Handle]; Handle
0x18000404e  test    rcx, rcx
0x180004051  jnz     loc_180004599
0x180004057  mov     eax, edi
0x180004059  mov     rcx, [rsp+148h+var_48]
0x180004061  xor     rcx, rsp; StackCookie
0x180004064  call    __security_check_cookie
0x180004069  add     rsp, 110h
0x180004070  pop     r15
0x180004072  pop     r14
0x180004074  pop     r13
0x180004076  pop     r12
0x180004078  pop     rdi
0x180004079  pop     rsi
0x18000407a  pop     rbx
0x18000407b  retn
0x18000407c  test    rsi, rsi
0x18000407f  jz      loc_18000413B
0x180004085  test    r14d, 0FEFDFFE6h
0x18000408c  jnz     short loc_180004095
0x18000408e  mov     edx, 1
0x180004093  jmp     short loc_1800040C7
0x180004095  test    r14d, 0FEFDFFF9h
0x18000409c  jnz     short loc_1800040AD
0x18000409e  mov     edx, 1
0x1800040a3  mov     [rsp+148h+var_F0], 12h
0x1800040ab  jmp     short loc_1800040CF
0x1800040ad  test    r14d, 0FEFCFFE0h
0x1800040b4  jnz     loc_18000413B
0x1800040ba  mov     edx, 2
0x1800040bf  mov     [rsp+148h+var_EC], 12h
0x1800040c7  mov     [rsp+148h+var_F0], 11h
0x1800040cf  lea     rcx, [rsp+148h+var_F0]
0x1800040d4  call    _RegRtlEnableThreadPrivileges
0x1800040d9  mov     [rsp+148h+var_E8], rax
0x1800040de  mov     r8d, r13d
0x1800040e1  or      r8d, 4
0x1800040e5  mov     [rsp+148h+var_108], r12
0x1800040ea  lea     rax, [rsp+148h+var_C0]
0x1800040f2  mov     [rsp+148h+var_110], rax
0x1800040f7  mov     rcx, [rsp+148h+var_A8]
0x1800040ff  mov     [rsp+148h+var_118], rcx
0x180004104  mov     [rsp+148h+var_128], 0
0x18000410d  mov     r9d, r14d
0x180004110  mov     rdx, rsi
0x180004113  mov     rcx, r15
0x180004116  call    _RegRtlCreateKeyTransacted
0x18000411b  mov     edi, eax
0x18000411d  mov     rcx, [rsp+148h+var_E8]
0x180004122  call    _RegRtlRestoreThreadPrivileges
0x180004127  cmp     edi, 0C0000022h
0x18000412d  jz      short loc_18000413B
0x18000412f  cmp     edi, 0C0000061h
0x180004135  jnz     loc_18000401E
0x18000413b  mov     [rsp+148h+var_120], r12
0x180004140  lea     rax, [rsp+148h+var_D8]
0x180004145  mov     [rsp+148h+var_128], rax
0x18000414a  mov     r9d, 60000h
0x180004150  xor     r8d, r8d
0x180004153  mov     rdx, rsi
0x180004156  mov     rcx, r15
0x180004159  call    _RegRtlOpenKeyTransacted
0x18000415e  mov     edi, eax
0x180004160  cmp     eax, 0C0000022h
0x180004165  jnz     loc_1800044D3
0x18000416b  mov     [rsp+148h+var_F7], 0
0x180004170  mov     [rsp+148h+var_120], r12
0x180004175  lea     rax, [rsp+148h+var_B0]
0x18000417d  mov     [rsp+148h+var_128], rax
0x180004182  mov     r9d, 20000h
0x180004188  xor     r8d, r8d
0x18000418b  mov     rdx, rsi
0x18000418e  mov     rcx, r15
0x180004191  call    _RegRtlOpenKeyTransacted
0x180004196  test    eax, eax
0x180004198  js      loc_18000426D
0x18000419e  xor     ebx, ebx
0x1800041a0  mov     dword ptr [rsp+148h+Size], ebx
0x1800041a4  lea     r9, [rsp+148h+Size]
0x1800041a9  mov     r8, rbx
0x1800041ac  mov     edx, 5
0x1800041b1  mov     rcx, [rsp+148h+var_B0]
0x1800041b9  call    _RegRtlGetKeySecurity
0x1800041be  mov     edi, eax
0x1800041c0  cmp     eax, 0C0000023h
0x1800041c5  jnz     short loc_18000420E
0x1800041c7  test    rbx, rbx
0x1800041ca  jz      short loc_1800041E4
0x1800041cc  mov     rcx, gs:60h
0x1800041d5  mov     r8, rbx; P
0x1800041d8  xor     edx, edx; Flags
0x1800041da  mov     rcx, [rcx+30h]; HeapHandle
0x1800041de  call    cs:__imp_RtlFreeHeap
0x1800041e4  mov     r8d, dword ptr [rsp+148h+Size]; Size
0x1800041e9  mov     rcx, gs:60h
0x1800041f2  mov     edx, 8; Flags
0x1800041f7  mov     rcx, [rcx+30h]; HeapHandle
0x1800041fb  call    cs:__imp_RtlAllocateHeap
0x180004201  mov     rbx, rax
0x180004204  test    rax, rax
0x180004207  jnz     short loc_1800041A4
0x180004209  mov     edi, 0C0000017h
0x18000420e  test    rbx, rbx
0x180004211  jz      short loc_18000426D
0x180004213  test    edi, edi
0x180004215  js      short loc_18000422E
0x180004217  lea     r8, [rsp+148h+OwnerDefaulted]; OwnerDefaulted
0x18000421c  lea     rdx, [rsp+148h+Owner]; Owner
0x180004221  mov     rcx, rbx; SecurityDescriptor
0x180004224  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x18000422a  test    eax, eax
0x18000422c  jns     short loc_180004237
0x18000422e  mov     [rsp+148h+Owner], 0
0x180004237  test    edi, edi
0x180004239  js      short loc_180004261
0x18000423b  lea     r9, [rsp+148h+DaclDefaulted]; DaclDefaulted
0x180004240  lea     r8, [rsp+148h+Dacl]; Dacl
0x180004248  lea     rdx, [rsp+148h+DaclPresent]; DaclPresent
0x18000424d  mov     rcx, rbx; SecurityDescriptor
0x180004250  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x180004256  test    eax, eax
0x180004258  js      short loc_180004261
0x18000425a  mov     [rsp+148h+var_F7], 1
0x18000425f  jmp     short loc_18000426D
0x180004261  mov     [rsp+148h+Dacl], 0
0x18000426d  mov     r8b, 2; SubAuthorityCount
0x180004270  lea     rdx, [rsp+148h+IdentifierAuthority]; IdentifierAuthority
0x180004278  lea     rcx, [rsp+148h+Sid]; Sid
0x180004280  call    cs:__imp_RtlInitializeSid
0x180004286  mov     edi, eax
0x180004288  test    eax, eax
0x18000428a  js      loc_18000401E
0x180004290  xor     edx, edx; SubAuthority
0x180004292  lea     rcx, [rsp+148h+Sid]; Sid
0x18000429a  call    cs:__imp_RtlSubAuthoritySid
0x1800042a0  mov     dword ptr [rax], 20h ; ' '
0x1800042a6  mov     edx, 1; SubAuthority
0x1800042ab  lea     rcx, [rsp+148h+Sid]; Sid
0x1800042b3  call    cs:__imp_RtlSubAuthoritySid
0x1800042b9  mov     dword ptr [rax], 220h
0x1800042bf  cmp     [rsp+148h+Owner], 0
0x1800042c5  jnz     short loc_180004312
0x1800042c7  mov     r8b, 1; SubAuthorityCount
0x1800042ca  lea     rdx, [rsp+148h+IdentifierAuthority]; IdentifierAuthority
0x1800042d2  lea     rcx, [rsp+148h+var_68]; Sid
0x1800042da  call    cs:__imp_RtlInitializeSid
0x1800042e0  mov     edi, eax
0x1800042e2  test    eax, eax
0x1800042e4  js      loc_18000401E
0x1800042ea  xor     edx, edx; SubAuthority
0x1800042ec  lea     rcx, [rsp+148h+var_68]; Sid
0x1800042f4  call    cs:__imp_RtlSubAuthoritySid
0x1800042fa  mov     dword ptr [rax], 12h
0x180004300  lea     rax, [rsp+148h+var_68]
0x180004308  mov     [rsp+148h+Owner], rax
0x18000430d  mov     [rsp+148h+OwnerDefaulted], 0
0x180004312  mov     [rsp+148h+var_F0], 9
0x18000431a  mov     [rsp+148h+var_EC], 12h
0x180004322  mov     edx, 2
0x180004327  lea     rcx, [rsp+148h+var_F0]
0x18000432c  call    _RegRtlEnableThreadPrivileges
0x180004331  mov     [rsp+148h+var_E8], rax
0x180004336  mov     [rsp+148h+var_120], r12
0x18000433b  lea     rax, [rsp+148h+Handle]
0x180004343  mov     [rsp+148h+var_128], rax
0x180004348  mov     r9d, 80000h
0x18000434e  xor     r8d, r8d
0x180004351  mov     rdx, rsi
0x180004354  mov     rcx, r15
0x180004357  call    _RegRtlOpenKeyTransacted
0x18000435c  mov     edi, eax
0x18000435e  mov     rcx, [rsp+148h+var_E8]
0x180004363  call    _RegRtlRestoreThreadPrivileges
0x180004368  test    edi, edi
0x18000436a  js      loc_18000401E
0x180004370  mov     edx, 1; Revision
0x180004375  lea     rcx, [rsp+148h+SecurityDescriptor]; SecurityDescriptor
0x18000437d  call    cs:__imp_RtlCreateSecurityDescriptor
0x180004383  mov     edi, eax
0x180004385  test    eax, eax
0x180004387  js      loc_18000401E
0x18000438d  xor     r8d, r8d; OwnerDefaulted
0x180004390  lea     rdx, [rsp+148h+Sid]; Owner
0x180004398  lea     rcx, [rsp+148h+SecurityDescriptor]; SecurityDescriptor
0x1800043a0  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1800043a6  mov     edi, eax
0x1800043a8  test    eax, eax
0x1800043aa  js      loc_18000401E
0x1800043b0  lea     r8, [rsp+148h+SecurityDescriptor]; SecurityDescriptor
0x1800043b8  mov     edx, 1; SecurityInformation
0x1800043bd  mov     rcx, [rsp+148h+Handle]; Handle
0x1800043c5  call    cs:__imp_NtSetSecurityObject
0x1800043cb  mov     edi, eax
0x1800043cd  test    eax, eax
0x1800043cf  js      loc_18000401E
0x1800043d5  mov     [rsp+148h+var_120], r12
0x1800043da  lea     rax, [rsp+148h+var_D8]
0x1800043df  mov     [rsp+148h+var_128], rax
0x1800043e4  mov     r9d, 60000h
0x1800043ea  xor     r8d, r8d
0x1800043ed  mov     rdx, rsi
0x1800043f0  mov     rcx, r15
0x1800043f3  call    _RegRtlOpenKeyTransacted
0x1800043f8  mov     edi, eax
0x1800043fa  mov     edx, 1; Revision
0x1800043ff  lea     rcx, [rsp+148h+SecurityDescriptor]; SecurityDescriptor
0x180004407  call    cs:__imp_RtlCreateSecurityDescriptor
0x18000440d  test    eax, eax
0x18000440f  js      short loc_180004470
0x180004411  movzx   r8d, [rsp+148h+OwnerDefaulted]; OwnerDefaulted
0x180004417  mov     rdx, [rsp+148h+Owner]; Owner
0x18000441c  lea     rcx, [rsp+148h+SecurityDescriptor]; SecurityDescriptor
0x180004424  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x18000442a  test    eax, eax
0x18000442c  js      short loc_180004470
0x18000442e  mov     [rsp+148h+var_F0], 12h
0x180004436  mov     edx, 1
0x18000443b  lea     rcx, [rsp+148h+var_F0]
0x180004440  call    _RegRtlEnableThreadPrivileges
0x180004445  mov     [rsp+148h+var_E8], rax
0x18000444a  lea     r8, [rsp+148h+SecurityDescriptor]; SecurityDescriptor
0x180004452  mov     edx, 1; SecurityInformation
0x180004457  mov     rcx, [rsp+148h+Handle]; Handle
0x18000445f  call    cs:__imp_NtSetSecurityObject
0x180004465  nop
0x180004466  mov     rcx, [rsp+148h+var_E8]
0x18000446b  call    _RegRtlRestoreThreadPrivileges
0x180004470  cmp     [rsp+148h+var_D8], 0
0x180004476  jz      short loc_1800044D3
0x180004478  cmp     [rsp+148h+var_F7], 0
0x18000447d  jz      short loc_1800044D3
0x18000447f  mov     edx, 1; Revision
0x180004484  lea     rcx, [rsp+148h+SecurityDescriptor]; SecurityDescriptor
0x18000448c  call    cs:__imp_RtlCreateSecurityDescriptor
0x180004492  test    eax, eax
0x180004494  js      short loc_1800044D3
0x180004496  movzx   r9d, [rsp+148h+DaclDefaulted]; DaclDefaulted
0x18000449c  mov     r8, [rsp+148h+Dacl]; Dacl
0x1800044a4  movzx   edx, [rsp+148h+DaclPresent]; DaclPresent
0x1800044a9  lea     rcx, [rsp+148h+SecurityDescriptor]; SecurityDescriptor
0x1800044b1  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1800044b7  test    eax, eax
0x1800044b9  js      short loc_1800044D3
0x1800044bb  lea     r8, [rsp+148h+SecurityDescriptor]; SecurityDescriptor
0x1800044c3  mov     edx, 4; SecurityInformation
  ... truncated ...
```
