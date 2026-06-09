# NfsRdrpGetUidGidFromPasswdGroup

- ea: `0x140029104`
- end: `0x140029288`
- name: `NfsRdrpGetUidGidFromPasswdGroup`
- size: `388`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140025be0`
- `0x140029b24`

## callees

- `0x1400159fc`
- `0x140029104`
- `0x140029290`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002926c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002926c`
- `ntoskrnl!ExAllocatePool2` at `0x140029175`
- `ntoskrnl!ExAllocatePool2` at `0x140029175`
- `ksecdd!SecLookupAccountSid` at `0x1400291d0`
- `ksecdd!SecLookupAccountSid` at `0x1400291d0`

## pseudocode

```c
__int64 __fastcall NfsRdrpGetUidGidFromPasswdGroup(__int64 a1, __int64 a2, void **a3, __int64 a4)
{
  struct _UNICODE_STRING *p_DomainBuffer; // r8
  struct _UNICODE_STRING *p_NameBuffer; // rdx
  WCHAR *v9; // rdi
  WCHAR *Pool2; // rax
  NTSTATUS UidGidFromPasswdGroupByUserName; // ebx
  void *v12; // rcx
  ULONG DomainSize; // [rsp+30h] [rbp-38h] BYREF
  ULONG NameSize; // [rsp+34h] [rbp-34h] BYREF
  struct _UNICODE_STRING NameBuffer; // [rsp+38h] [rbp-30h] BYREF
  struct _UNICODE_STRING DomainBuffer; // [rsp+48h] [rbp-20h] BYREF
  enum _SID_NAME_USE NameUse; // [rsp+A8h] [rbp+40h] BYREF

  NameSize = 0;
  DomainSize = 0;
  NameUse = 0;
  NameBuffer = 0;
  DomainBuffer = 0;
  if ( a2
    && (p_DomainBuffer = *(struct _UNICODE_STRING **)(a2 + 32)) != 0
    && (p_NameBuffer = *(struct _UNICODE_STRING **)(a2 + 16)) != 0
    && p_DomainBuffer->Length
    && p_NameBuffer->Length )
  {
    v9 = 0;
  }
  else
  {
    Pool2 = (WCHAR *)ExAllocatePool2(258, 1058, 844260942);
    v9 = Pool2;
    if ( !Pool2 )
      return (unsigned int)-1073741670;
    v12 = *a3;
    DomainBuffer.Buffer = Pool2;
    *(_DWORD *)&DomainBuffer.Length = 35782656;
    NameBuffer.Buffer = Pool2 + 273;
    *(_DWORD *)&NameBuffer.Length = 0x2000000;
    UidGidFromPasswdGroupByUserName = SecLookupAccountSid(
                                        v12,
                                        &NameSize,
                                        &NameBuffer,
                                        &DomainSize,
                                        &DomainBuffer,
                                        &NameUse);
    if ( UidGidFromPasswdGroupByUserName < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          19,
          WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
          (unsigned int)UidGidFromPasswdGroupByUserName);
      goto LABEL_19;
    }
    p_NameBuffer = &NameBuffer;
    p_DomainBuffer = &DomainBuffer;
  }
  UidGidFromPasswdGroupByUserName = NfsRdrpGetUidGidFromPasswdGroupByUserName(a1, p_NameBuffer, p_DomainBuffer, a4);
  if ( UidGidFromPasswdGroupByUserName < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      20,
      WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids,
      (unsigned int)UidGidFromPasswdGroupByUserName);
  }
  if ( v9 )
LABEL_19:
    ExFreePoolWithTag(v9, 0);
  return (unsigned int)UidGidFromPasswdGroupByUserName;
}

```

## disassembly

```asm
0x140029104  push    rbp
0x140029106  push    rbx
0x140029107  push    rsi
0x140029108  push    rdi
0x140029109  push    r14
0x14002910b  push    r15
0x14002910d  mov     rbp, rsp
0x140029110  sub     rsp, 68h
0x140029114  xor     r15d, r15d
0x140029117  xorps   xmm0, xmm0
0x14002911a  mov     [rbp+NameSize], r15d
0x14002911e  xorps   xmm1, xmm1
0x140029121  mov     [rbp+DomainSize], r15d
0x140029125  mov     rsi, r9
0x140029128  mov     [rbp+arg_8], r15d
0x14002912c  mov     rbx, r8
0x14002912f  mov     r14, rcx
0x140029132  movups  xmmword ptr [rbp+NameBuffer.Length], xmm0
0x140029136  movups  xmmword ptr [rbp+var_20.Length], xmm1
0x14002913a  test    rdx, rdx
0x14002913d  jz      short loc_140029165
0x14002913f  mov     r8, [rdx+20h]
0x140029143  test    r8, r8
0x140029146  jz      short loc_140029165
0x140029148  mov     rdx, [rdx+10h]
0x14002914c  test    rdx, rdx
0x14002914f  jz      short loc_140029165
0x140029151  cmp     [r8], r15w
0x140029155  jz      short loc_140029165
0x140029157  cmp     [rdx], r15w
0x14002915b  jz      short loc_140029165
0x14002915d  mov     edi, r15d
0x140029160  jmp     loc_14002921F
0x140029165  mov     edx, 422h
0x14002916a  mov     ecx, 102h
0x14002916f  mov     r8d, 3252664Eh
0x140029175  call    cs:__imp_ExAllocatePool2
0x14002917c  nop     dword ptr [rax+rax+00h]
0x140029181  mov     rdi, rax
0x140029184  test    rax, rax
0x140029187  jnz     short loc_140029193
0x140029189  mov     ebx, 0C000009Ah
0x14002918e  jmp     loc_140029278
0x140029193  mov     rcx, [rbx]; Sid
0x140029196  lea     r9, [rbp+DomainSize]; DomainSize
0x14002919a  mov     [rbp+var_20.Buffer], rax
0x14002919e  lea     r8, [rbp+NameBuffer]; NameBuffer
0x1400291a2  add     rax, 222h
0x1400291a8  mov     dword ptr [rbp+var_20.Length], 2220000h
0x1400291af  mov     [rbp+NameBuffer.Buffer], rax
0x1400291b3  lea     rdx, [rbp+NameSize]; NameSize
0x1400291b7  lea     rax, [rbp+arg_8]
0x1400291bb  mov     dword ptr [rbp+NameBuffer.Length], 2000000h
0x1400291c2  mov     [rsp+68h+NameUse], rax; NameUse
0x1400291c7  lea     rax, [rbp+var_20]
0x1400291cb  mov     [rsp+68h+DomainBuffer], rax; DomainBuffer
0x1400291d0  call    cs:__imp_SecLookupAccountSid
0x1400291d7  nop     dword ptr [rax+rax+00h]
0x1400291dc  mov     ebx, eax
0x1400291de  test    eax, eax
0x1400291e0  jns     short loc_140029217
0x1400291e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400291e9  lea     rax, WPP_GLOBAL_Control
0x1400291f0  cmp     rcx, rax
0x1400291f3  jz      short loc_140029267
0x1400291f5  mov     edx, [rcx+2Ch]
0x1400291f8  test    dl, 1
0x1400291fb  jz      short loc_140029267
0x1400291fd  mov     rcx, [rcx+18h]
0x140029201  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140029208  mov     edx, 13h
0x14002920d  mov     r9d, ebx
0x140029210  call    WPP_SF_d
0x140029215  jmp     short loc_140029267
0x140029217  lea     rdx, [rbp+NameBuffer]
0x14002921b  lea     r8, [rbp+var_20]
0x14002921f  mov     r9, rsi
0x140029222  mov     rcx, r14
0x140029225  call    NfsRdrpGetUidGidFromPasswdGroupByUserName
0x14002922a  mov     ebx, eax
0x14002922c  test    eax, eax
0x14002922e  jns     short loc_140029262
0x140029230  mov     rcx, cs:WPP_GLOBAL_Control
0x140029237  lea     rax, WPP_GLOBAL_Control
0x14002923e  cmp     rcx, rax
0x140029241  jz      short loc_140029262
0x140029243  mov     eax, [rcx+2Ch]
0x140029246  test    al, 1
0x140029248  jz      short loc_140029262
0x14002924a  mov     rcx, [rcx+18h]
0x14002924e  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x140029255  mov     edx, 14h
0x14002925a  mov     r9d, ebx
0x14002925d  call    WPP_SF_d
0x140029262  test    rdi, rdi
0x140029265  jz      short loc_140029278
0x140029267  xor     edx, edx; Tag
0x140029269  mov     rcx, rdi; P
0x14002926c  call    cs:__imp_ExFreePoolWithTag
0x140029273  nop     dword ptr [rax+rax+00h]
0x140029278  mov     eax, ebx
0x14002927a  add     rsp, 68h
0x14002927e  pop     r15
0x140029280  pop     r14
0x140029282  pop     rdi
0x140029283  pop     rsi
0x140029284  pop     rbx
0x140029285  pop     rbp
0x140029286  retn
```
