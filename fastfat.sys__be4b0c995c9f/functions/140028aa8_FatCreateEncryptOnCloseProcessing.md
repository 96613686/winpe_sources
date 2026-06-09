# FatCreateEncryptOnCloseProcessing

- ea: `0x140028aa8`
- end: `0x140028cba`
- name: `FatCreateEncryptOnCloseProcessing`
- size: `530`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14002adec`
- `0x14002b790`

## callees

- `0x1400031e8`
- `0x140005288`
- `0x14000c230`
- `0x14000c680`
- `0x140028aa8`
- `0x14002ca48`
- `0x140044e74`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140028c35`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140028c35`
- `ntoskrnl!RtlOemStringToUnicodeString` at `0x140028b9b`
- `ntoskrnl!RtlOemStringToUnicodeString` at `0x140028b9b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140028c49`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140028c49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028c88`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028c88`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140028bf5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140028bf5`

## pseudocode

```c
__int64 __fastcall FatCreateEncryptOnCloseProcessing(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const UNICODE_STRING *a4,
        __int64 a5,
        __int64 a6)
{
  int v6; // r13d
  const UNICODE_STRING *v8; // r15
  int Length; // edx
  unsigned int v10; // esi
  struct _UNICODE_STRING *p_DestinationString; // r8
  __int64 v12; // r8
  __int64 v13; // rdx
  WCHAR *PoolWithTag; // rax
  WCHAR *v15; // rdi
  int v16; // r8d
  int v17; // r9d
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-A8h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-98h] BYREF
  unsigned int v21; // [rsp+50h] [rbp-88h]
  __int64 v22; // [rsp+58h] [rbp-80h]
  __int64 v23; // [rsp+60h] [rbp-78h]
  __int64 v24; // [rsp+68h] [rbp-70h]
  _BYTE v25[32]; // [rsp+70h] [rbp-68h] BYREF

  v6 = a3;
  v23 = a2;
  v24 = a1;
  v22 = a6;
  Destination = 0;
  v8 = a4 + 10;
  Length = a4[10].Length;
  if ( (_WORD)Length )
  {
    if ( !*(_QWORD *)(a5 + 152) && (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 8LL) + 20LL) & 6) != 0 )
    {
      v10 = Length + *(unsigned __int16 *)(a5 + 528) + 2;
      v21 = v10;
      if ( v10 <= 0xFFFF )
      {
        if ( *(_QWORD *)(a5 + 536) )
          goto LABEL_9;
        p_DestinationString = (struct _UNICODE_STRING *)(a5 + 552);
        if ( !*(_WORD *)(a5 + 552) )
        {
          memset(v25, 0, 26);
          *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
          DestinationString.Buffer = (PWSTR)v25;
          *(_DWORD *)&DestinationString.Length = 1703936;
          RtlOemStringToUnicodeString(&DestinationString, (PCOEM_STRING)(a5 + 480), 0);
          v12 = *(_DWORD *)(a5 + 192) >> 13;
          LOBYTE(v12) = (*(_DWORD *)(a5 + 192) & 0x2000) != 0;
          v13 = *(_DWORD *)(a5 + 192) >> 12;
          LOBYTE(v13) = (*(_DWORD *)(a5 + 192) & 0x1000) != 0;
          FatUnicodeRestoreShortNameCase(&DestinationString, v13, v12);
          p_DestinationString = &DestinationString;
        }
        FatSetFullNameInFcb(a1, a5, p_DestinationString);
        if ( *(_QWORD *)(a5 + 536) )
        {
LABEL_9:
          PoolWithTag = (WCHAR *)ExAllocatePoolWithTag((POOL_TYPE)1025, v10, 0x70646546u);
          v15 = PoolWithTag;
          if ( !ExPoolZeroingNativelySupported && PoolWithTag )
            memset(PoolWithTag, 0, v10);
          Destination.Buffer = v15;
          if ( v15 )
          {
            Destination.MaximumLength = v10;
            RtlCopyUnicodeString(&Destination, v8);
            RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)(a5 + 528));
            EfsOpenEncryptOnCloseFileCallback(v6, v23, v16, v17, (__int64)&Destination, v22 + 16);
          }
        }
      }
    }
  }
  if ( Destination.Buffer )
    ExFreePoolWithTag(Destination.Buffer, 0);
  return 0;
}

```

## disassembly

```asm
0x140028aa8  push    rbx
0x140028aaa  push    rsi
0x140028aab  push    rdi
0x140028aac  push    r12
0x140028aae  push    r13
0x140028ab0  push    r14
0x140028ab2  push    r15
0x140028ab4  sub     rsp, 0A0h
0x140028abb  mov     rax, cs:__security_cookie
0x140028ac2  xor     rax, rsp
0x140028ac5  mov     [rsp+0D8h+var_48], rax
0x140028acd  mov     r13, r8
0x140028ad0  mov     [rsp+0D8h+var_78], rdx
0x140028ad5  mov     r14, rcx
0x140028ad8  mov     [rsp+0D8h+var_70], rcx
0x140028add  mov     rdi, [rsp+0D8h+arg_20]
0x140028ae5  mov     rax, [rsp+0D8h+arg_28]
0x140028aed  mov     [rsp+0D8h+var_80], rax
0x140028af2  xorps   xmm0, xmm0
0x140028af5  movups  xmmword ptr [rsp+0D8h+Destination.Length], xmm0
0x140028afa  lea     r15, [r9+0A0h]
0x140028b01  movzx   edx, word ptr [r15]
0x140028b05  xor     ebx, ebx
0x140028b07  test    dx, dx
0x140028b0a  jz      loc_140028C7A
0x140028b10  cmp     [rdi+98h], rbx
0x140028b17  jnz     loc_140028C7A
0x140028b1d  mov     rax, [r8+8]
0x140028b21  mov     rcx, [rax+8]
0x140028b25  mov     eax, [rcx+14h]
0x140028b28  test    al, 6
0x140028b2a  jz      loc_140028C7A
0x140028b30  lea     r12, [rdi+210h]
0x140028b37  movzx   esi, word ptr [r12]
0x140028b3c  add     esi, 2
0x140028b3f  add     esi, edx
0x140028b41  mov     [rsp+0D8h+var_88], esi
0x140028b45  cmp     esi, 0FFFFh
0x140028b4b  ja      loc_140028C7A
0x140028b51  cmp     [rdi+218h], rbx
0x140028b58  jnz     loc_140028BE5
0x140028b5e  lea     r8, [rdi+228h]
0x140028b65  cmp     [r8], bx
0x140028b69  jnz     short loc_140028BCD
0x140028b6b  movups  xmmword ptr [rsp+0D8h+var_68], xmm0
0x140028b70  movups  xmmword ptr [rsp+0D8h+var_68+0Ah], xmm0
0x140028b75  movups  xmmword ptr [rsp+0D8h+DestinationString.Length], xmm0
0x140028b7a  lea     rax, [rsp+0D8h+var_68]
0x140028b7f  mov     [rsp+0D8h+DestinationString.Buffer], rax
0x140028b84  mov     dword ptr [rsp+0D8h+DestinationString.Length], 1A0000h
0x140028b8c  lea     rdx, [rdi+1E0h]; SourceString
0x140028b93  xor     r8d, r8d; AllocateDestinationString
0x140028b96  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x140028b9b  call    cs:__imp_RtlOemStringToUnicodeString
0x140028ba2  nop     dword ptr [rax+rax+00h]
0x140028ba7  mov     edx, [rdi+0C0h]
0x140028bad  mov     r8d, edx
0x140028bb0  shr     r8d, 0Dh
0x140028bb4  and     r8b, 1
0x140028bb8  shr     edx, 0Ch
0x140028bbb  and     dl, 1
0x140028bbe  lea     rcx, [rsp+0D8h+DestinationString]
0x140028bc3  call    FatUnicodeRestoreShortNameCase
0x140028bc8  lea     r8, [rsp+0D8h+DestinationString]
0x140028bcd  mov     rdx, rdi
0x140028bd0  mov     rcx, r14
0x140028bd3  call    FatSetFullNameInFcb
0x140028bd8  cmp     [rdi+218h], rbx
0x140028bdf  jz      loc_140028C7A
0x140028be5  mov     r14d, esi
0x140028be8  mov     r8d, 70646546h; Tag
0x140028bee  mov     edx, esi; NumberOfBytes
0x140028bf0  mov     ecx, 401h; PoolType
0x140028bf5  call    cs:__imp_ExAllocatePoolWithTag
0x140028bfc  nop     dword ptr [rax+rax+00h]
0x140028c01  mov     rdi, rax
0x140028c04  cmp     cs:ExPoolZeroingNativelySupported, bl
0x140028c0a  jnz     short loc_140028C1E
0x140028c0c  test    rax, rax
0x140028c0f  jz      short loc_140028C1E
0x140028c11  mov     r8d, r14d; Size
0x140028c14  xor     edx, edx; Val
0x140028c16  mov     rcx, rax; void *
0x140028c19  call    memset
0x140028c1e  mov     [rsp+0D8h+Destination.Buffer], rdi
0x140028c23  test    rdi, rdi
0x140028c26  jz      short loc_140028C7A
0x140028c28  mov     [rsp+0D8h+Destination.MaximumLength], si
0x140028c2d  mov     rdx, r15; SourceString
0x140028c30  lea     rcx, [rsp+0D8h+Destination]; DestinationString
0x140028c35  call    cs:__imp_RtlCopyUnicodeString
0x140028c3c  nop     dword ptr [rax+rax+00h]
0x140028c41  mov     rdx, r12; Source
0x140028c44  lea     rcx, [rsp+0D8h+Destination]; Destination
0x140028c49  call    cs:__imp_RtlAppendUnicodeStringToString
0x140028c50  nop     dword ptr [rax+rax+00h]
0x140028c55  mov     rax, [rsp+0D8h+var_80]
0x140028c5a  add     rax, 10h
0x140028c5e  mov     [rsp+0D8h+var_B0], rax
0x140028c63  lea     rax, [rsp+0D8h+Destination]
0x140028c68  mov     [rsp+0D8h+var_B8], rax
0x140028c6d  mov     rdx, [rsp+0D8h+var_78]
0x140028c72  mov     rcx, r13
0x140028c75  call    EfsOpenEncryptOnCloseFileCallback
0x140028c7a  jmp     short $+2
0x140028c7c  mov     rcx, [rsp+0D8h+Destination.Buffer]; P
0x140028c81  test    rcx, rcx
0x140028c84  jz      short loc_140028C94
0x140028c86  xor     edx, edx; Tag
0x140028c88  call    cs:__imp_ExFreePoolWithTag
0x140028c8f  nop     dword ptr [rax+rax+00h]
0x140028c94  xor     eax, eax
0x140028c96  mov     rcx, [rsp+0D8h+var_48]
0x140028c9e  xor     rcx, rsp; StackCookie
0x140028ca1  call    __security_check_cookie
0x140028ca6  add     rsp, 0A0h
0x140028cad  pop     r15
0x140028caf  pop     r14
0x140028cb1  pop     r13
0x140028cb3  pop     r12
0x140028cb5  pop     rdi
0x140028cb6  pop     rsi
0x140028cb7  pop     rbx
0x140028cb8  retn
0x14005bf91  push    rbp
0x14005bf93  sub     rsp, 30h
0x14005bf97  mov     rbp, rdx
0x14005bf9a  mov     rdx, rcx
0x14005bf9d  mov     rcx, [rbp+68h]
0x14005bfa1  call    FatExceptionFilter
0x14005bfa6  nop
0x14005bfa7  add     rsp, 30h
0x14005bfab  pop     rbp
0x14005bfac  retn
```
