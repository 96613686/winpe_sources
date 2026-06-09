# SdbpCheckMatchingRegistryValue

- ea: `0x140823b68`
- end: `0x140823f27`
- name: `SdbpCheckMatchingRegistryValue`
- size: `959`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x14082398c`
- `0x14082420c`

## callees

- `0x140403380`
- `0x140544600`
- `0x1406ce144`
- `0x1406ce1cc`
- `0x1406dd6c0`
- `0x1406f6f80`
- `0x1406f7250`
- `0x140823b68`
- `0x1408be914`
- `0x1408bf658`
- `0x1408c14bc`
- `0x1408c1900`
- `0x1408c2f88`

## string_xrefs

- `0x140823d79`: `Unknown registry value data type`
- `0x140823c0f`: `SdbpCheckMatchingRegistryValue`
- `0x140823cd1`: `SdbpCheckMatchingRegistryValue`
- `0x140823d18`: `SdbpCheckMatchingRegistryValue`
- `0x140823c43`: `dbRegistryDefaultName`
- `0x140823d0b`: `Failed to read value`

## pseudocode

```c
__int64 __fastcall SdbpCheckMatchingRegistryValue(
        __int64 a1,
        void *a2,
        __int64 a3,
        void *a4,
        __int64 a5,
        __int64 a6,
        void *Src,
        size_t Size,
        _DWORD *a9)
{
  unsigned int v9; // esi
  __int64 v11; // rcx
  ULONG v13; // [rsp+30h] [rbp-51h]
  PCWSTR SourceString; // [rsp+38h] [rbp-49h]
  void *Buf1[2]; // [rsp+40h] [rbp-41h]
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp-31h]
  wchar_t *Str1[2]; // [rsp+60h] [rbp-21h]
  __int128 v18; // [rsp+70h] [rbp-11h]

  SourceString = 0;
  v13 = 0;
  v9 = 0;
  DestinationString = 0;
  *(_OWORD *)Str1 = 0;
  v18 = 0;
  *(_OWORD *)Buf1 = 0;
  SdbpUmaInit_PCWSTR(a2);
  SdbpUmaInit_PCWSTR(a4);
  SdbpUmaInit_PCVOID(Src, Size);
  if ( *((_QWORD *)&v18 + 1) || !Buf1[0] && Buf1[1] )
  {
    AslLogCallPrintf(1, (unsigned int)"SdbpCheckMatchingRegistryValue", 1205, (unsigned int)"Out of memory");
  }
  else
  {
    *a9 = 1;
    v9 = 1;
  }
  if ( SourceString )
    AslFree(v11, SourceString);
  if ( Buf1[0] && Buf1[0] != Buf1[1] )
    AslFree(v11, Buf1[0]);
  return v9;
}

```

## disassembly

```asm
0x140823b68  mov     [rsp-8+KeyHandle], rcx
0x140823b6d  push    rbp
0x140823b6e  push    rbx
0x140823b6f  push    rsi
0x140823b70  push    rdi
0x140823b71  push    r12
0x140823b73  push    r13
0x140823b75  push    r14
0x140823b77  push    r15
0x140823b79  lea     rbp, [rsp-7]
0x140823b7e  sub     rsp, 88h
0x140823b85  xorps   xmm0, xmm0
0x140823b88  xor     edi, edi
0x140823b8a  mov     rcx, rdx; Src
0x140823b8d  mov     [rbp+3Fh+SourceString], rdi
0x140823b91  xorps   xmm1, xmm1
0x140823b94  mov     [rbp+3Fh+var_90], edi
0x140823b97  lea     rdx, [rbp+3Fh+Str1]
0x140823b9b  mov     esi, edi
0x140823b9d  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x140823ba1  mov     rbx, r9
0x140823ba4  mov     r15d, r8d
0x140823ba7  movups  xmmword ptr [rbp+3Fh+Str1], xmm0
0x140823bab  movups  [rbp+3Fh+var_50], xmm1
0x140823baf  movups  xmmword ptr [rbp+3Fh+Buf1], xmm0
0x140823bb3  call    SdbpUmaInit_PCWSTR
0x140823bb8  lea     rdx, [rbp+3Fh+var_50]
0x140823bbc  mov     rcx, rbx; Src
0x140823bbf  call    SdbpUmaInit_PCWSTR
0x140823bc4  mov     rdx, [rbp+3Fh+Size]; Size
0x140823bcb  lea     r8, [rbp+3Fh+Buf1]
0x140823bcf  mov     rcx, [rbp+3Fh+Src]; Src
0x140823bd3  call    SdbpUmaInit_PCVOID
0x140823bd8  mov     r12, [rbp+3Fh+Str1]
0x140823bdc  mov     r13, qword ptr [rbp+3Fh+var_50]
0x140823be0  test    r12, r12
0x140823be3  jnz     short loc_140823BEB
0x140823be5  cmp     [rbp+3Fh+Str1+8], rdi
0x140823be9  jnz     short loc_140823C02
0x140823beb  test    r13, r13
0x140823bee  jnz     short loc_140823BF6
0x140823bf0  cmp     qword ptr [rbp+3Fh+var_50+8], rdi
0x140823bf4  jnz     short loc_140823C02
0x140823bf6  cmp     [rbp+3Fh+Buf1], rdi
0x140823bfa  jnz     short loc_140823C25
0x140823bfc  cmp     [rbp+3Fh+Buf1+8], rdi
0x140823c00  jz      short loc_140823C25
0x140823c02  lea     r9, aOutOfMemory_0; "Out of memory"
0x140823c09  mov     r8d, 4B5h
0x140823c0f  lea     rdx, aSdbpcheckmatch_7; "SdbpCheckMatchingRegistryValue"
0x140823c16  mov     ecx, 1
0x140823c1b  call    AslLogCallPrintf
0x140823c20  jmp     loc_140823EC3
0x140823c25  xor     eax, eax
0x140823c27  mov     r14, rdi
0x140823c2a  mov     ebx, 1
0x140823c2f  test    r12, r12
0x140823c32  jz      loc_140823E9C
0x140823c38  cmp     [r12], ax
0x140823c3d  jz      loc_140823E9C
0x140823c43  lea     rdx, aDbregistrydefa; "dbRegistryDefaultName"
0x140823c4a  mov     rcx, r12; Str1
0x140823c4d  call    _wcsicmp
0x140823c52  test    eax, eax
0x140823c54  jnz     short loc_140823C5A
0x140823c56  xor     edx, edx
0x140823c58  jmp     short loc_140823C72
0x140823c5a  mov     rdx, r12
0x140823c5d  lea     rcx, [rbp+3Fh+SourceString]
0x140823c61  call    AslStringDuplicate
0x140823c66  test    eax, eax
0x140823c68  js      loc_140823EC3
0x140823c6e  mov     rdx, [rbp+3Fh+SourceString]; SourceString
0x140823c72  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x140823c76  call    RtlInitUnicodeString
0x140823c7b  mov     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x140823c7f  lea     rax, [rbp+3Fh+var_90]
0x140823c83  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x140823c88  lea     rdx, [rbp+3Fh+DestinationString]; ValueName
0x140823c8c  xor     r9d, r9d; KeyValueInformation
0x140823c8f  mov     [rsp+0C0h+Length], edi; Length
0x140823c93  mov     r8d, ebx; KeyValueInformationClass
0x140823c96  call    ZwQueryValueKey
0x140823c9b  test    eax, eax
0x140823c9d  jns     short loc_140823CB4
0x140823c9f  cmp     eax, 80000005h
0x140823ca4  jz      short loc_140823CB4
0x140823ca6  cmp     eax, 0C0000023h
0x140823cab  jz      short loc_140823CB4
0x140823cad  mov     esi, ebx
0x140823caf  jmp     loc_140823EC3
0x140823cb4  mov     edx, [rbp+3Fh+var_90]
0x140823cb7  call    AslAlloc
0x140823cbc  mov     rdi, rax
0x140823cbf  test    rax, rax
0x140823cc2  jnz     short loc_140823CE4
0x140823cc4  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x140823ccb  mov     r8d, 4E1h
0x140823cd1  lea     rdx, aSdbpcheckmatch_7; "SdbpCheckMatchingRegistryValue"
0x140823cd8  mov     ecx, ebx
0x140823cda  call    AslLogCallPrintf
0x140823cdf  jmp     loc_140823EC3
0x140823ce4  mov     rcx, [rbp+3Fh+KeyHandle]; KeyHandle
0x140823ce8  lea     rax, [rbp+3Fh+var_90]
0x140823cec  mov     [rsp+0C0h+ResultLength], rax; ResultLength
0x140823cf1  lea     rdx, [rbp+3Fh+DestinationString]; ValueName
0x140823cf5  mov     eax, [rbp+3Fh+var_90]
0x140823cf8  mov     r9, rdi; KeyValueInformation
0x140823cfb  mov     r8d, ebx; KeyValueInformationClass
0x140823cfe  mov     [rsp+0C0h+Length], eax; Length
0x140823d02  call    ZwQueryValueKey
0x140823d07  test    eax, eax
0x140823d09  jns     short loc_140823D2B
0x140823d0b  lea     r9, aFailedToReadVa_0; "Failed to read value"
0x140823d12  mov     r8d, 4ECh
0x140823d18  lea     rdx, aSdbpcheckmatch_7; "SdbpCheckMatchingRegistryValue"
0x140823d1f  mov     ecx, ebx
0x140823d21  call    AslLogCallPrintf
0x140823d26  jmp     loc_140823EAC
0x140823d2b  test    r15d, r15d
0x140823d2e  jnz     short loc_140823D40
0x140823d30  mov     rax, [rbp+3Fh+arg_40]
0x140823d37  mov     [rax], ebx
0x140823d39  mov     esi, ebx
0x140823d3b  jmp     loc_140823EAC
0x140823d40  mov     ecx, [rdi+4]
0x140823d43  cmp     ecx, r15d
0x140823d46  jnz     short loc_140823D39
0x140823d48  mov     r15d, [rdi+8]
0x140823d4c  add     r15, rdi
0x140823d4f  sub     ecx, ebx
0x140823d51  jz      loc_140823E49
0x140823d57  sub     ecx, ebx
0x140823d59  jz      loc_140823E49
0x140823d5f  sub     ecx, ebx
0x140823d61  jz      loc_140823E22
0x140823d67  sub     ecx, ebx
0x140823d69  jz      loc_140823E15
0x140823d6f  sub     ecx, 3
0x140823d72  jz      short loc_140823D94
0x140823d74  cmp     ecx, 4
0x140823d77  jz      short loc_140823D88
0x140823d79  lea     r9, aUnknownRegistr; "Unknown registry value data type"
0x140823d80  mov     r8d, 574h
0x140823d86  jmp     short loc_140823D18
0x140823d88  mov     rax, [r15]
0x140823d8b  cmp     [rbp+3Fh+arg_28], rax
0x140823d8f  jmp     loc_140823E1B
0x140823d94  mov     edx, [rdi+0Ch]
0x140823d97  add     rdx, 2
0x140823d9b  call    AslAlloc
0x140823da0  mov     r14, rax
0x140823da3  test    rax, rax
0x140823da6  jnz     short loc_140823DBA
0x140823da8  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x140823daf  mov     r8d, 529h
0x140823db5  jmp     loc_140823D18
0x140823dba  mov     r8d, [rdi+0Ch]; Size
0x140823dbe  mov     rdx, r15; Src
0x140823dc1  mov     rcx, r14; void *
0x140823dc4  call    memmove
0x140823dc9  mov     ecx, [rdi+0Ch]
0x140823dcc  shr     rcx, 1
0x140823dcf  mov     [r14+rcx*2], si
0x140823dd4  mov     rcx, r14
0x140823dd7  mov     eax, [rdi+0Ch]
0x140823dda  and     rax, 0FFFFFFFFFFFFFFFEh
0x140823dde  add     rax, r14
0x140823de1  cmp     r14, rax
0x140823de4  jnb     loc_140823E89
0x140823dea  lea     rax, [rcx+2]
0x140823dee  cmp     [rcx], si
0x140823df1  jnz     short loc_140823E01
0x140823df3  cmp     [rax], si
0x140823df6  jz      loc_140823E89
0x140823dfc  mov     word ptr [rcx], 3Bh ; ';'
0x140823e01  mov     rcx, rax
0x140823e04  mov     eax, [rdi+0Ch]
0x140823e07  and     rax, 0FFFFFFFFFFFFFFFEh
0x140823e0b  add     rax, r14
0x140823e0e  cmp     rcx, rax
0x140823e11  jb      short loc_140823DEA
0x140823e13  jmp     short loc_140823E89
0x140823e15  mov     eax, [r15]
0x140823e18  cmp     [rbp+3Fh+arg_20], eax
0x140823e1b  jz      short loc_140823E9C
0x140823e1d  jmp     loc_140823D39
0x140823e22  mov     eax, [rdi+0Ch]
0x140823e25  cmp     [rbp+3Fh+Size], rax
0x140823e2c  jnz     loc_140823D39
0x140823e32  mov     r8, [rbp+3Fh+Size]; Size
0x140823e39  mov     rdx, r15; Buf2
0x140823e3c  mov     rcx, [rbp+3Fh+Buf1]; Buf1
0x140823e40  call    memcmp
0x140823e45  test    eax, eax
0x140823e47  jmp     short loc_140823E1B
0x140823e49  mov     edx, [rdi+0Ch]
0x140823e4c  add     rdx, 2
0x140823e50  call    AslAlloc
0x140823e55  mov     r14, rax
0x140823e58  test    rax, rax
0x140823e5b  jnz     short loc_140823E6F
0x140823e5d  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x140823e64  mov     r8d, 511h
0x140823e6a  jmp     loc_140823D18
0x140823e6f  mov     r8d, [rdi+0Ch]; Size
0x140823e73  mov     rdx, r15; Src
0x140823e76  mov     rcx, r14; void *
0x140823e79  call    memmove
0x140823e7e  mov     ecx, [rdi+0Ch]
0x140823e81  shr     rcx, 1
0x140823e84  mov     [r14+rcx*2], si
0x140823e89  mov     rdx, r14
0x140823e8c  mov     rcx, r13
0x140823e8f  call    AslStringPatternMatchExW
0x140823e94  test    eax, eax
0x140823e96  jz      loc_140823D39
0x140823e9c  mov     rax, [rbp+3Fh+arg_40]
0x140823ea3  mov     [rax], ebx
0x140823ea5  mov     esi, ebx
0x140823ea7  test    rdi, rdi
0x140823eaa  jz      short loc_140823EB4
0x140823eac  mov     rdx, rdi
0x140823eaf  call    AslFree
0x140823eb4  xor     edi, edi
0x140823eb6  test    r14, r14
0x140823eb9  jz      short loc_140823EC3
0x140823ebb  mov     rdx, r14
0x140823ebe  call    AslFree
0x140823ec3  mov     rdx, [rbp+3Fh+SourceString]
0x140823ec7  test    rdx, rdx
0x140823eca  jz      short loc_140823ED1
0x140823ecc  call    AslFree
0x140823ed1  test    r12, r12
0x140823ed4  jz      short loc_140823EE4
0x140823ed6  cmp     r12, [rbp+3Fh+Str1+8]
0x140823eda  jz      short loc_140823EE4
0x140823edc  mov     rdx, r12
0x140823edf  call    AslFree
0x140823ee4  test    r13, r13
0x140823ee7  jz      short loc_140823EF7
0x140823ee9  cmp     r13, qword ptr [rbp+3Fh+var_50+8]
0x140823eed  jz      short loc_140823EF7
0x140823eef  mov     rdx, r13
0x140823ef2  call    AslFree
0x140823ef7  cmp     [rbp+3Fh+Buf1], rdi
0x140823efb  jz      short loc_140823F10
0x140823efd  mov     rax, [rbp+3Fh+Buf1+8]
0x140823f01  cmp     [rbp+3Fh+Buf1], rax
0x140823f05  jz      short loc_140823F10
0x140823f07  mov     rdx, [rbp+3Fh+Buf1]
0x140823f0b  call    AslFree
0x140823f10  mov     eax, esi
0x140823f12  add     rsp, 88h
0x140823f19  pop     r15
0x140823f1b  pop     r14
0x140823f1d  pop     r13
0x140823f1f  pop     r12
0x140823f21  pop     rdi
0x140823f22  pop     rsi
0x140823f23  pop     rbx
0x140823f24  pop     rbp
0x140823f25  retn
```
