# GetEncryptedPasswordsForChangePassword2

- ea: `0x180018a04`
- end: `0x180018b48`
- name: `GetEncryptedPasswordsForChangePassword2`
- size: `324`
- prototype: `__int64 __usercall@<rax>(PCSZ Source@<rcx>, PCSZ@<rdx>, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001b060`
- `0x18001b3ec`

## callees

- `0x180003bd0`
- `0x180006a20`
- `0x180014610`
- `0x180018a04`

## import_xrefs

- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180018a6a`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180018a7b`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180018a6a`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x180018a7b`
- `ntdll!RtlFreeUnicodeString` at `0x180018b03`
- `ntdll!RtlFreeUnicodeString` at `0x180018b0d`
- `ntdll!RtlFreeUnicodeString` at `0x180018b03`
- `ntdll!RtlFreeUnicodeString` at `0x180018b0d`
- `SAMLIB!SamiEncryptPasswords` at `0x180018aae`
- `SAMLIB!SamiEncryptPasswords` at `0x180018aae`

## pseudocode

```c
__int64 __fastcall GetEncryptedPasswordsForChangePassword2(
        PCSZ Source,
        PCSZ a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  unsigned int v11; // edi
  __int64 v12; // rbx
  __int64 v13; // r8
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-10h] BYREF

  Destination = 0;
  UnicodeString = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_b4e6502b7f593fe20362eda088865c91_Traceguids);
  Destination.Buffer = 0;
  UnicodeString.Buffer = 0;
  if ( RtlCreateUnicodeStringFromAsciiz(&Destination, Source) && RtlCreateUnicodeStringFromAsciiz(&UnicodeString, a2) )
    v11 = SamiEncryptPasswords(&Destination, &UnicodeString, a3, a4, a7, a5, a6);
  else
    v11 = 8;
  v12 = -1;
  if ( Destination.Buffer )
  {
    v13 = -1;
    do
      ++v13;
    while ( Destination.Buffer[v13] );
    memset_0(Destination.Buffer, 0, 2 * v13);
  }
  if ( UnicodeString.Buffer )
  {
    do
      ++v12;
    while ( UnicodeString.Buffer[v12] );
    memset_0(UnicodeString.Buffer, 0, 2 * v12);
  }
  RtlFreeUnicodeString(&Destination);
  RtlFreeUnicodeString(&UnicodeString);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_b4e6502b7f593fe20362eda088865c91_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180018a04  push    rbp
0x180018a06  push    rbx
0x180018a07  push    rsi
0x180018a08  push    rdi
0x180018a09  push    r12
0x180018a0b  push    r14
0x180018a0d  push    r15
0x180018a0f  mov     rbp, rsp
0x180018a12  sub     rsp, 60h
0x180018a16  xorps   xmm0, xmm0
0x180018a19  xorps   xmm1, xmm1
0x180018a1c  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x180018a20  mov     rsi, r9
0x180018a23  mov     r14, r8
0x180018a26  movups  xmmword ptr [rbp+UnicodeString.Length], xmm1
0x180018a2a  mov     rdi, rdx
0x180018a2d  mov     rbx, rcx
0x180018a30  mov     rcx, cs:WPP_GLOBAL_Control
0x180018a37  lea     r12, WPP_GLOBAL_Control
0x180018a3e  cmp     rcx, r12
0x180018a41  jz      short loc_180018A58
0x180018a43  mov     rcx, [rcx+10h]
0x180018a47  lea     r8, WPP_b4e6502b7f593fe20362eda088865c91_Traceguids
0x180018a4e  mov     edx, 27h ; '''
0x180018a53  call    WPP_SF_
0x180018a58  xor     r15d, r15d
0x180018a5b  lea     rcx, [rbp+Destination]; Destination
0x180018a5f  mov     rdx, rbx; Source
0x180018a62  mov     [rbp+Destination.Buffer], r15
0x180018a66  mov     [rbp+UnicodeString.Buffer], r15
0x180018a6a  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x180018a70  test    al, al
0x180018a72  jz      short loc_180018AB8
0x180018a74  mov     rdx, rdi; Source
0x180018a77  lea     rcx, [rbp+UnicodeString]; Destination
0x180018a7b  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x180018a81  test    al, al
0x180018a83  jz      short loc_180018AB8
0x180018a85  mov     rax, [rbp+arg_28]
0x180018a89  lea     rdx, [rbp+UnicodeString]
0x180018a8d  mov     [rsp+60h+var_30], rax
0x180018a92  lea     rcx, [rbp+Destination]
0x180018a96  mov     rax, [rbp+arg_20]
0x180018a9a  mov     r9, rsi
0x180018a9d  mov     [rsp+60h+var_38], rax
0x180018aa2  mov     r8, r14
0x180018aa5  mov     rax, [rbp+arg_30]
0x180018aa9  mov     [rsp+60h+var_40], rax
0x180018aae  call    cs:__imp_SamiEncryptPasswords
0x180018ab4  mov     edi, eax
0x180018ab6  jmp     short loc_180018ABD
0x180018ab8  mov     edi, 8
0x180018abd  mov     rcx, [rbp+Destination.Buffer]; void *
0x180018ac1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180018ac5  test    rcx, rcx
0x180018ac8  jz      short loc_180018AE1
0x180018aca  mov     r8, rbx
0x180018acd  inc     r8
0x180018ad0  cmp     [rcx+r8*2], r15w
0x180018ad5  jnz     short loc_180018ACD
0x180018ad7  add     r8, r8; Size
0x180018ada  xor     edx, edx; Val
0x180018adc  call    memset_0
0x180018ae1  mov     rcx, [rbp+UnicodeString.Buffer]; void *
0x180018ae5  test    rcx, rcx
0x180018ae8  jz      short loc_180018AFF
0x180018aea  inc     rbx
0x180018aed  cmp     [rcx+rbx*2], r15w
0x180018af2  jnz     short loc_180018AEA
0x180018af4  lea     r8, [rbx+rbx]; Size
0x180018af8  xor     edx, edx; Val
0x180018afa  call    memset_0
0x180018aff  lea     rcx, [rbp+Destination]; UnicodeString
0x180018b03  call    cs:__imp_RtlFreeUnicodeString
0x180018b09  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x180018b0d  call    cs:__imp_RtlFreeUnicodeString
0x180018b13  mov     rcx, cs:WPP_GLOBAL_Control
0x180018b1a  cmp     rcx, r12
0x180018b1d  jz      short loc_180018B37
0x180018b1f  mov     rcx, [rcx+10h]
0x180018b23  lea     r8, WPP_b4e6502b7f593fe20362eda088865c91_Traceguids
0x180018b2a  mov     edx, 28h ; '('
0x180018b2f  mov     r9d, edi
0x180018b32  call    WPP_SF_d
0x180018b37  mov     eax, edi
0x180018b39  add     rsp, 60h
0x180018b3d  pop     r15
0x180018b3f  pop     r14
0x180018b41  pop     r12
0x180018b43  pop     rdi
0x180018b44  pop     rsi
0x180018b45  pop     rbx
0x180018b46  pop     rbp
0x180018b47  retn
```
