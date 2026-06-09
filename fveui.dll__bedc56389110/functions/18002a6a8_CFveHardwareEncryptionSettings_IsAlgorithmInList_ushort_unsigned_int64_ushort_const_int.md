# CFveHardwareEncryptionSettings::IsAlgorithmInList(ushort *,unsigned __int64,ushort const *,int *)

- ea: `0x18002a6a8`
- end: `0x18002a809`
- name: `?IsAlgorithmInList@CFveHardwareEncryptionSettings@@CAJPEAG_KPEBGPEAH@Z`
- size: `353`
- prototype: `__int64 __fastcall(unsigned __int16 *Source1, unsigned __int64, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a330`

## callees

- `0x18000b9bc`
- `0x180010ff0`
- `0x18002a6a8`
- `0x18002b678`

## import_xrefs

- `KERNEL32!RtlCompareMemory` at `0x18002a7ad`
- `KERNEL32!RtlCompareMemory` at `0x18002a7ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFveHardwareEncryptionSettings::IsAlgorithmInList(
        unsigned __int16 *Source1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        int *a4)
{
  unsigned __int16 *v6; // rdi
  unsigned int v7; // ebx
  unsigned __int64 v8; // rdx
  unsigned __int16 *v9; // rbp
  int v10; // r13d
  unsigned __int16 *v11; // rsi
  unsigned __int64 v12; // r14
  int v13; // eax
  unsigned __int64 v15; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int64 v16; // [rsp+68h] [rbp+10h] BYREF
  int *v17; // [rsp+78h] [rbp+20h]

  v17 = a4;
  v16 = 0;
  v15 = 0;
  v6 = Source1;
  *a4 = 0;
  v7 = 0;
  if ( !Source1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a3 )
    return v7;
  v7 = StringCchLengthW(a3, 0x100u, &v16);
  if ( (v7 & 0x80000000) != 0 )
    return v7;
  v7 = ULongLongMult(a2, v8, &v15);
  if ( (v7 & 0x80000000) != 0 )
    return v7;
  v9 = (unsigned __int16 *)((char *)v6 + v15);
  if ( (unsigned __int16 *)((char *)v6 + v15) < v6 )
    return (unsigned int)-2147024362;
  v10 = 1;
  v11 = v6;
  if ( v9 != &v6[a2] )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v7 = 0;
  while ( 1 )
  {
    if ( v6 > v9 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( v11 > v9 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( *v11 != 59 && *v11 && v11 != v9 )
      goto LABEL_27;
    if ( v6 > v11 )
      break;
    v7 = 0;
    v12 = (unsigned __int64)((char *)v11 - (char *)v6) >> 1;
    if ( &v6[v12] != v11 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( v12 == v16 && RtlCompareMemory(v6, a3, (char *)v11 - (char *)v6) == (char *)v11 - (char *)v6 )
    {
      *v17 = 1;
      return v7;
    }
    v6 = v11 + 1;
    v13 = 0;
    if ( *v11 == 59 )
      v13 = v10;
    v10 = v13;
LABEL_27:
    if ( !v10 )
      return v7;
    ++v11;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs();
  return (unsigned int)-2147024362;
}

```

## disassembly

```asm
0x18002a6a8  mov     rax, rsp
0x18002a6ab  mov     [rax+18h], rbx
0x18002a6af  mov     [rax+20h], r9
0x18002a6b3  push    rbp
0x18002a6b4  push    rsi
0x18002a6b5  push    rdi
0x18002a6b6  push    r12
0x18002a6b8  push    r13
0x18002a6ba  push    r14
0x18002a6bc  push    r15
0x18002a6be  sub     rsp, 20h
0x18002a6c2  xor     r15d, r15d
0x18002a6c5  mov     r12, r8
0x18002a6c8  mov     [rax+10h], r15
0x18002a6cc  mov     r14, rdx
0x18002a6cf  mov     [rax+8], r15
0x18002a6d3  mov     rdi, rcx
0x18002a6d6  mov     [r9], r15d
0x18002a6d9  mov     ebx, r15d
0x18002a6dc  test    rcx, rcx
0x18002a6df  jnz     short loc_18002A6E6
0x18002a6e1  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pszAllowedAlgorithms != NULL")
0x18002a6e6  test    r14, r14
0x18002a6e9  jnz     short loc_18002A6F0
0x18002a6eb  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "cchAllowedAlgorithms != 0")
0x18002a6f0  test    r12, r12
0x18002a6f3  jz      loc_18002A7F2
0x18002a6f9  lea     r8, [rsp+58h+arg_8]; unsigned __int64 *
0x18002a6fe  mov     edx, 100h; unsigned __int64
0x18002a703  mov     rcx, r12; unsigned __int16 *
0x18002a706  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002a70b  mov     ebx, eax
0x18002a70d  test    eax, eax
0x18002a70f  js      loc_18002A7F2
0x18002a715  lea     r8, [rsp+58h+arg_0]; unsigned __int64 *
0x18002a71a  mov     rcx, r14; unsigned __int64
0x18002a71d  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002a722  mov     ebx, eax
0x18002a724  test    eax, eax
0x18002a726  js      loc_18002A7F2
0x18002a72c  mov     rbp, [rsp+58h+arg_0]
0x18002a731  add     rbp, rdi
0x18002a734  cmp     rbp, rdi
0x18002a737  jb      loc_18002A7ED
0x18002a73d  lea     rax, [rdi+r14*2]
0x18002a741  mov     r13d, 1
0x18002a747  mov     rsi, rdi
0x18002a74a  cmp     rbp, rax
0x18002a74d  jz      short loc_18002A754
0x18002a74f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "psEnd == pszAllowedAlgorithms + cchAllowedAlgorithms")
0x18002a754  mov     ebx, r15d
0x18002a757  cmp     rdi, rbp
0x18002a75a  jbe     short loc_18002A761
0x18002a75c  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "psTokenStart <= psEnd")
0x18002a761  cmp     rsi, rbp
0x18002a764  jbe     short loc_18002A76B
0x18002a766  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "psCurrentPos <= psEnd")
0x18002a76b  cmp     word ptr [rsi], 3Bh ; ';'
0x18002a76f  jz      short loc_18002A77C
0x18002a771  cmp     [rsi], r15w
0x18002a775  jz      short loc_18002A77C
0x18002a777  cmp     rsi, rbp
0x18002a77a  jnz     short loc_18002A7CD
0x18002a77c  cmp     rdi, rsi
0x18002a77f  ja      short loc_18002A7E8
0x18002a781  mov     r15, rsi
0x18002a784  xor     ebx, ebx
0x18002a786  sub     r15, rdi
0x18002a789  mov     r14, r15
0x18002a78c  shr     r14, 1
0x18002a78f  lea     rax, [rdi+r14*2]
0x18002a793  cmp     rax, rsi
0x18002a796  jz      short loc_18002A79D
0x18002a798  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "psTokenStart + cchToken == psCurrentPos")
0x18002a79d  cmp     r14, [rsp+58h+arg_8]
0x18002a7a2  jnz     short loc_18002A7B8
0x18002a7a4  mov     r8, r15; Length
0x18002a7a7  mov     rdx, r12; Source2
0x18002a7aa  mov     rcx, rdi; Source1
0x18002a7ad  call    cs:__imp_RtlCompareMemory
0x18002a7b3  cmp     rax, r15
0x18002a7b6  jz      short loc_18002A7DB
0x18002a7b8  xor     r15d, r15d
0x18002a7bb  lea     rdi, [rsi+2]
0x18002a7bf  cmp     word ptr [rsi], 3Bh ; ';'
0x18002a7c3  mov     eax, r15d
0x18002a7c6  cmovz   eax, r13d
0x18002a7ca  mov     r13d, eax
0x18002a7cd  test    r13d, r13d
0x18002a7d0  jz      short loc_18002A7F2
0x18002a7d2  add     rsi, 2
0x18002a7d6  jmp     loc_18002A757
0x18002a7db  mov     rax, [rsp+58h+arg_18]
0x18002a7e0  mov     dword ptr [rax], 1
0x18002a7e6  jmp     short loc_18002A7F2
0x18002a7e8  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "psTokenStart <= psCurrentPos")
0x18002a7ed  mov     ebx, 80070216h
0x18002a7f2  mov     eax, ebx
0x18002a7f4  mov     rbx, [rsp+58h+arg_10]
0x18002a7f9  add     rsp, 20h
0x18002a7fd  pop     r15
0x18002a7ff  pop     r14
0x18002a801  pop     r13
0x18002a803  pop     r12
0x18002a805  pop     rdi
0x18002a806  pop     rsi
0x18002a807  pop     rbp
0x18002a808  retn
```
