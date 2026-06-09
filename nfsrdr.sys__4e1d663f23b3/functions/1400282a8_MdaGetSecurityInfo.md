# MdaGetSecurityInfo

- ea: `0x1400282a8`
- end: `0x140028405`
- name: `MdaGetSecurityInfo`
- size: `349`
- prototype: `__int64 __fastcall(__int64, struct _UNICODE_STRING *, PSID *, __int64, HANDLE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140025be0`

## callees

- `0x1400159cc`
- `0x1400282a8`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x140028346`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140028346`
- `ntoskrnl!ZwQueryInformationToken` at `0x140028374`
- `ntoskrnl!ZwQueryInformationToken` at `0x140028374`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14002838f`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14002838f`
- `ntoskrnl!ZwClose` at `0x1400283b9`
- `ntoskrnl!ZwClose` at `0x1400283b9`

## pseudocode

```c
__int64 __fastcall MdaGetSecurityInfo(__int64 a1, struct _UNICODE_STRING *a2, PSID *a3, __int64 a4, HANDLE *a5)
{
  void *v8; // rcx
  NTSTATUS v9; // ebx
  HANDLE TokenHandle; // [rsp+60h] [rbp+8h] BYREF
  ULONG ReturnLength; // [rsp+78h] [rbp+20h] BYREF

  TokenHandle = 0;
  ReturnLength = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
  if ( !a1 )
    return 3221225506LL;
  v8 = *(void **)a1;
  if ( !*(_QWORD *)a1 )
  {
    v8 = *(void **)(a1 + 16);
    if ( !v8 )
      return 3221225506LL;
  }
  v9 = ObOpenObjectByPointer(v8, 0x200u, 0, 0x10u, 0, 0, &TokenHandle);
  if ( v9 >= 0 )
  {
    v9 = ZwQueryInformationToken(TokenHandle, TokenUser, a3, 0x58u, &ReturnLength);
    if ( v9 >= 0 )
      v9 = RtlConvertSidToUnicodeString(a2, *a3, 1u);
    if ( a5 )
      *a5 = TokenHandle;
    else
      ZwClose(TokenHandle);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400282a8  mov     rax, rsp
0x1400282ab  mov     [rax+10h], rbx
0x1400282af  mov     [rax+20h], r9d
0x1400282b3  push    rsi
0x1400282b4  push    rdi
0x1400282b5  push    r14
0x1400282b7  sub     rsp, 40h
0x1400282bb  mov     rdi, r8
0x1400282be  mov     qword ptr [rax+8], 0
0x1400282c6  mov     rsi, rdx
0x1400282c9  mov     dword ptr [rax+20h], 0
0x1400282d0  mov     rbx, rcx
0x1400282d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400282da  lea     r14, WPP_GLOBAL_Control
0x1400282e1  cmp     rcx, r14
0x1400282e4  jz      short loc_140028302
0x1400282e6  mov     eax, [rcx+2Ch]
0x1400282e9  test    al, 8
0x1400282eb  jz      short loc_140028302
0x1400282ed  mov     rcx, [rcx+18h]
0x1400282f1  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x1400282f8  mov     edx, 3Eh ; '>'
0x1400282fd  call    WPP_SF_
0x140028302  test    rbx, rbx
0x140028305  jz      loc_1400283F1
0x14002830b  mov     rcx, [rbx]
0x14002830e  test    rcx, rcx
0x140028311  jnz     short loc_140028320
0x140028313  mov     rcx, [rbx+10h]; Object
0x140028317  test    rcx, rcx
0x14002831a  jz      loc_1400283F1
0x140028320  lea     rax, [rsp+58h+TokenHandle]
0x140028325  mov     r9d, 10h; DesiredAccess
0x14002832b  mov     [rsp+58h+Handle], rax; Handle
0x140028330  xor     r8d, r8d; PassedAccessState
0x140028333  mov     [rsp+58h+AccessMode], 0; AccessMode
0x140028338  mov     edx, 200h; HandleAttributes
0x14002833d  mov     [rsp+58h+ObjectType], 0; ObjectType
0x140028346  call    cs:__imp_ObOpenObjectByPointer
0x14002834d  nop     dword ptr [rax+rax+00h]
0x140028352  mov     ebx, eax
0x140028354  test    eax, eax
0x140028356  js      short loc_1400283C5
0x140028358  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x14002835d  lea     rax, [rsp+58h+ReturnLength]
0x140028362  mov     r9d, 58h ; 'X'; TokenInformationLength
0x140028368  mov     [rsp+58h+ObjectType], rax; ReturnLength
0x14002836d  mov     r8, rdi; TokenInformation
0x140028370  lea     edx, [r9-57h]; TokenInformationClass
0x140028374  call    cs:__imp_ZwQueryInformationToken
0x14002837b  nop     dword ptr [rax+rax+00h]
0x140028380  mov     ebx, eax
0x140028382  test    eax, eax
0x140028384  js      short loc_14002839D
0x140028386  mov     rdx, [rdi]; Sid
0x140028389  mov     r8b, 1; AllocateDestinationString
0x14002838c  mov     rcx, rsi; UnicodeString
0x14002838f  call    cs:__imp_RtlConvertSidToUnicodeString
0x140028396  nop     dword ptr [rax+rax+00h]
0x14002839b  mov     ebx, eax
0x14002839d  mov     rcx, [rsp+58h+arg_20]
0x1400283a5  test    rcx, rcx
0x1400283a8  jz      short loc_1400283B4
0x1400283aa  mov     rax, [rsp+58h+TokenHandle]
0x1400283af  mov     [rcx], rax
0x1400283b2  jmp     short loc_1400283C5
0x1400283b4  mov     rcx, [rsp+58h+TokenHandle]; Handle
0x1400283b9  call    cs:__imp_ZwClose
0x1400283c0  nop     dword ptr [rax+rax+00h]
0x1400283c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400283cc  cmp     rcx, r14
0x1400283cf  jz      short loc_1400283ED
0x1400283d1  mov     eax, [rcx+2Ch]
0x1400283d4  test    al, 8
0x1400283d6  jz      short loc_1400283ED
0x1400283d8  mov     rcx, [rcx+18h]
0x1400283dc  lea     r8, WPP_ecfd99f4757a3b03b4f64e68aa326964_Traceguids
0x1400283e3  mov     edx, 44h ; 'D'
0x1400283e8  call    WPP_SF_
0x1400283ed  mov     eax, ebx
0x1400283ef  jmp     short loc_1400283F6
0x1400283f1  mov     eax, 0C0000022h
0x1400283f6  mov     rbx, [rsp+58h+arg_8]
0x1400283fb  add     rsp, 40h
0x1400283ff  pop     r14
0x140028401  pop     rdi
0x140028402  pop     rsi
0x140028403  retn
```
