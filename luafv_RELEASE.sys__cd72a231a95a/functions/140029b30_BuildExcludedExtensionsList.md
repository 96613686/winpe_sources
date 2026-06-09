# BuildExcludedExtensionsList

- ea: `0x140029b30`
- end: `0x14002a040`
- name: `BuildExcludedExtensionsList`
- size: `1296`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140029784`

## callees

- `0x140005d00`
- `0x140006000`
- `0x14001b650`
- `0x1400280d4`
- `0x1400289f8`
- `0x140028f98`
- `0x140029b30`
- `0x14002a048`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x140029b8d`
- `ntoskrnl!ZwQueryValueKey` at `0x140029fac`
- `ntoskrnl!ZwQueryValueKey` at `0x140029b8d`
- `ntoskrnl!ZwQueryValueKey` at `0x140029fac`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140029e40`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140029f22`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140029e40`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140029f22`

## pseudocode

```c
__int64 __fastcall BuildExcludedExtensionsList(HANDLE KeyHandle)
{
  NTSTATUS v2; // eax
  PWSTR Buffer; // r12
  __int64 v4; // r8
  wchar_t *v5; // rdx
  int v6; // esi
  unsigned int v7; // ebx
  ULONG v8; // edi
  __int64 result; // rax
  char *Pool; // rax
  __int64 v11; // r14
  wchar_t *v12; // r8
  _WORD *i; // rax
  __int64 v14; // rcx
  size_t v15; // r8
  __int64 v16; // r15
  unsigned int v17; // ecx
  char v18; // r10
  unsigned int v19; // r8d
  unsigned int v20; // edx
  unsigned int v21; // r9d
  unsigned __int64 v22; // rsi
  unsigned __int64 v23; // rdx
  char v24; // r12
  unsigned int v25; // esi
  unsigned int v26; // ecx
  unsigned int v27; // r13d
  unsigned int v28; // esi
  ULONG v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // esi
  unsigned int v32; // eax
  unsigned int v33; // eax
  NTSTATUS ValueKey; // eax
  int v35; // eax
  bool v36; // sf
  int v37; // [rsp+30h] [rbp-49h] BYREF
  UNICODE_STRING String1; // [rsp+38h] [rbp-41h] BYREF
  UNICODE_STRING String2; // [rsp+48h] [rbp-31h] BYREF
  __int128 v40; // [rsp+58h] [rbp-21h] BYREF
  UNICODE_STRING v41; // [rsp+68h] [rbp-11h] BYREF
  UNICODE_STRING v42; // [rsp+78h] [rbp-1h] BYREF
  ULONG ResultLength; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned int v45; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v46; // [rsp+F8h] [rbp+7Fh] BYREF

  String2 = 0;
  ResultLength = 0;
  v40 = 0;
  while ( 1 )
  {
    v2 = ZwQueryValueKey(
           KeyHandle,
           &ExcludedExtensionsAddValueName,
           KeyValuePartialInformation,
           QueryBuffer,
           QueryBufferLength,
           &ResultLength);
    if ( v2 != -2147483643 && v2 != -1073741789 )
      break;
    if ( (int)GrowQueryBuffer(ResultLength) < 0 )
      goto LABEL_5;
  }
  if ( v2 || *((_DWORD *)QueryBuffer + 1) != 7 )
  {
LABEL_5:
    Buffer = String2.Buffer;
    goto LABEL_6;
  }
  Buffer = (PWSTR)((char *)QueryBuffer + 12);
  String2.Length = *((_WORD *)QueryBuffer + 4);
  String2.MaximumLength = String2.Length;
  String2.Buffer = (PWSTR)((char *)QueryBuffer + 12);
LABEL_6:
  v4 = (unsigned __int16)DefaultExcludedExtensions >> 1;
  if ( !((unsigned __int16)DefaultExcludedExtensions >> 1) )
    goto LABEL_9;
  v5 = off_14002B030;
  if ( (_DWORD)v4 == 1 )
  {
    if ( !*off_14002B030 )
    {
LABEL_9:
      v6 = 0;
      v7 = 0;
      v8 = 0;
      goto LABEL_10;
    }
  }
  else if ( (_DWORD)v4 == 2 )
  {
    if ( !*off_14002B030 && !off_14002B030[1] )
      goto LABEL_9;
    return 3221225485LL;
  }
  if ( (unsigned int)v4 < 3
    || !*off_14002B030
    || off_14002B030[(unsigned int)(v4 - 2)]
    || off_14002B030[(unsigned int)(v4 - 1)] )
  {
    return 3221225485LL;
  }
  v12 = &off_14002B030[v4];
  v8 = 0;
  v7 = 0;
  v6 = 0;
  do
  {
    for ( i = v5 + 1; *i; ++i )
      ;
    v14 = i - v5;
    if ( (unsigned int)v14 > 4 )
    {
      ++v7;
      v6 += v14;
    }
    else
    {
      ++v8;
    }
    v5 = i + 1;
  }
  while ( i[1] );
  if ( i + 2 != v12 )
    return 3221225485LL;
LABEL_10:
  ResultLength = v8;
  v45 = v7;
  LODWORD(v46) = v6;
  if ( Buffer )
  {
    result = CheckExtensionsList(&String2.Length, &ResultLength, &v45, &v46);
    if ( (int)result < 0 )
      return result;
    v8 += ResultLength;
    v7 += v45;
    v6 += v46;
  }
  Pool = LuafvAllocatePool(1, 2 * (v6 + 4 * (v8 + 2 * v7)), 14);
  v11 = (__int64)Pool;
  if ( !Pool )
    return 3221225626LL;
  v15 = 8LL * v8;
  v16 = (__int64)&Pool[v15];
  *(_QWORD *)&String1.Length = &Pool[16 * v7 + v15];
  memset(Pool, 0, v15);
  v37 = 0;
  LODWORD(v46) = 0;
  AddExtensionsList(
    (unsigned int)&DefaultExcludedExtensions,
    v11,
    (unsigned int)&v37,
    v16,
    (__int64)&v46,
    (__int64)&String1);
  if ( Buffer )
    AddExtensionsList((unsigned int)&String2, v11, (unsigned int)&v37, v16, (__int64)&v46, (__int64)&String1);
  v17 = v8;
  do
  {
    v18 = 1;
    if ( v17 > 1 )
    {
      v19 = 1;
      v20 = 1;
      v21 = 1;
      do
      {
        v22 = *(_QWORD *)(v11 + 8LL * (v21 - 1));
        v23 = *(_QWORD *)(v11 + 8LL * v20);
        if ( v22 > v23 )
        {
          v18 = 0;
          *(_QWORD *)(v11 + 8LL * (v21 - 1)) = v23;
          *(_QWORD *)(v11 + 8LL * v21) = v22;
        }
        v20 = ++v19;
        v21 = v19;
      }
      while ( v19 < v17 );
    }
    --v17;
  }
  while ( !v18 );
  do
  {
    if ( v7 <= 1 )
      break;
    v24 = 1;
    v25 = 1;
    v26 = 1;
    v27 = 1;
    do
    {
      String1 = 0;
      v46 = 16LL * (v27 - 1);
      String2 = 0;
      String1 = *(UNICODE_STRING *)(v46 + v16);
      String2 = *(UNICODE_STRING *)(v16 + 16LL * v26);
      if ( RtlCompareUnicodeString(&String1, &String2, 0) > 0 )
      {
        *(UNICODE_STRING *)(v46 + v16) = String2;
        v24 = 0;
        *(UNICODE_STRING *)(v16 + 16LL * v27) = String1;
      }
      v26 = ++v25;
      v27 = v25;
    }
    while ( v25 < v7 );
  }
  while ( !v24 );
  v28 = 1;
  while ( v28 < v8 )
  {
    if ( *(_QWORD *)(v11 + 8LL * (v28 - 1)) == *(_QWORD *)(v11 + 8LL * v28) )
    {
      v29 = v8--;
      v30 = v29 - v28 - 1;
      if ( v30 )
        memmove((void *)(v11 + 8LL * v28), (const void *)(v11 + 8LL * (v28 + 1)), 8LL * v30);
    }
    else
    {
      ++v28;
    }
  }
  v31 = 1;
  while ( v31 < v7 )
  {
    v42 = 0;
    v41 = 0;
    v42 = *(UNICODE_STRING *)(v16 + 16LL * (v31 - 1));
    v41 = *(UNICODE_STRING *)(v16 + 16LL * v31);
    if ( RtlCompareUnicodeString(&v42, &v41, 0) )
    {
      ++v31;
    }
    else
    {
      v32 = v7--;
      v33 = v32 - v31 - 1;
      if ( v33 )
        memmove((void *)(v16 + 16LL * v31), (const void *)(v16 + 16LL * (v31 + 1)), 16LL * v33);
    }
  }
  HIDWORD(qword_14000ECB0) = v7;
  LODWORD(v46) = 0;
  qword_14000ECA8 = v16;
  qword_14000ECA0 = v11;
  LODWORD(qword_14000ECB0) = v8;
  while ( 1 )
  {
    ValueKey = ZwQueryValueKey(
                 KeyHandle,
                 &ExcludedExtensionsRemoveValueName,
                 KeyValuePartialInformation,
                 QueryBuffer,
                 QueryBufferLength,
                 (PULONG)&v46);
    if ( ValueKey != -2147483643 && ValueKey != -1073741789 )
      break;
    v35 = GrowQueryBuffer(v46);
    if ( v35 < 0 )
    {
      v36 = v35 < 0;
      goto LABEL_68;
    }
  }
  v36 = ValueKey < 0;
  if ( ValueKey )
  {
LABEL_68:
    if ( v36 )
      return 0;
    goto LABEL_69;
  }
  if ( *((_DWORD *)QueryBuffer + 1) != 7 )
    return 0;
  LOWORD(v40) = *((_WORD *)QueryBuffer + 4);
  WORD1(v40) = v40;
  *((_QWORD *)&v40 + 1) = (char *)QueryBuffer + 12;
LABEL_69:
  result = CheckExtensionsList((unsigned __int16 *)&v40, &ResultLength, &v45, &v46);
  if ( (int)result < 0 )
    return result;
  if ( ResultLength || v45 )
    RemoveExtensionsList((__int64)&v40);
  return 0;
}

```

## disassembly

```asm
0x140029b30  mov     [rsp-8+KeyHandle], rcx
0x140029b35  push    rbp
0x140029b36  push    rbx
0x140029b37  push    rsi
0x140029b38  push    rdi
0x140029b39  push    r12
0x140029b3b  push    r13
0x140029b3d  push    r14
0x140029b3f  push    r15
0x140029b41  lea     rbp, [rsp-1Fh]
0x140029b46  sub     rsp, 98h
0x140029b4d  xorps   xmm0, xmm0
0x140029b50  xorps   xmm1, xmm1
0x140029b53  xor     ebx, ebx
0x140029b55  mov     r13, rcx
0x140029b58  movups  xmmword ptr [rbp+57h+String2.Length], xmm0
0x140029b5c  mov     [rbp+57h+arg_8], ebx
0x140029b5f  movups  [rbp+57h+var_78], xmm1
0x140029b63  mov     r9, cs:QueryBuffer; KeyValueInformation
0x140029b6a  lea     rax, [rbp+57h+arg_8]
0x140029b6e  mov     [rsp+0D0h+ResultLength], rax; ResultLength
0x140029b73  lea     rdx, ExcludedExtensionsAddValueName; ValueName
0x140029b7a  mov     eax, cs:QueryBufferLength
0x140029b80  mov     r8d, 2; KeyValueInformationClass
0x140029b86  mov     rcx, r13; KeyHandle
0x140029b89  mov     [rsp+0D0h+Length], eax; Length
0x140029b8d  call    cs:__imp_ZwQueryValueKey
0x140029b94  nop     dword ptr [rax+rax+00h]
0x140029b99  cmp     eax, 80000005h
0x140029b9e  jz      short loc_140029BAB
0x140029ba0  cmp     eax, 0C0000023h
0x140029ba5  jnz     loc_140029C51
0x140029bab  mov     ecx, [rbp+57h+arg_8]
0x140029bae  call    GrowQueryBuffer
0x140029bb3  test    eax, eax
0x140029bb5  jns     short loc_140029B63
0x140029bb7  xor     r13d, r13d
0x140029bba  mov     r12, [rbp+57h+String2.Buffer]
0x140029bbe  movzx   r8d, cs:DefaultExcludedExtensions
0x140029bc6  mov     r14d, 1
0x140029bcc  shr     r8d, 1
0x140029bcf  jz      short loc_140029BEB
0x140029bd1  mov     rdx, cs:off_14002B030; "acm"
0x140029bd8  cmp     r8d, r14d
0x140029bdb  jnz     loc_140029C86
0x140029be1  cmp     [rdx], r13w
0x140029be5  jnz     loc_140029C9E
0x140029beb  mov     esi, r13d
0x140029bee  mov     ebx, r13d
0x140029bf1  mov     edi, r13d
0x140029bf4  mov     [rbp+57h+arg_8], edi
0x140029bf7  mov     [rbp+57h+arg_10], ebx
0x140029bfa  mov     dword ptr [rbp+57h+arg_18], esi
0x140029bfd  test    r12, r12
0x140029c00  jz      short loc_140029C28
0x140029c02  lea     r9, [rbp+57h+arg_18]
0x140029c06  lea     r8, [rbp+57h+arg_10]
0x140029c0a  lea     rdx, [rbp+57h+arg_8]
0x140029c0e  lea     rcx, [rbp+57h+String2]
0x140029c12  call    CheckExtensionsList
0x140029c17  test    eax, eax
0x140029c19  js      loc_14002A004
0x140029c1f  add     edi, [rbp+57h+arg_8]
0x140029c22  add     ebx, [rbp+57h+arg_10]
0x140029c25  add     esi, dword ptr [rbp+57h+arg_18]
0x140029c28  lea     eax, [rdi+rbx*2]
0x140029c2b  mov     r8b, 0Eh
0x140029c2e  lea     edx, [rsi+rax*4]
0x140029c31  mov     ecx, r14d
0x140029c34  add     edx, edx
0x140029c36  call    LuafvAllocatePool
0x140029c3b  mov     r14, rax
0x140029c3e  test    rax, rax
0x140029c41  jnz     loc_140029D16
0x140029c47  mov     eax, 0C000009Ah
0x140029c4c  jmp     loc_14002A004
0x140029c51  xor     r13d, r13d
0x140029c54  test    eax, eax
0x140029c56  jnz     loc_140029BBA
0x140029c5c  mov     rcx, cs:QueryBuffer
0x140029c63  cmp     dword ptr [rcx+4], 7
0x140029c67  jnz     loc_140029BBA
0x140029c6d  movzx   eax, word ptr [rcx+8]
0x140029c71  lea     r12, [rcx+0Ch]
0x140029c75  mov     [rbp+57h+String2.Length], ax
0x140029c79  mov     [rbp+57h+String2.MaximumLength], ax
0x140029c7d  mov     [rbp+57h+String2.Buffer], r12
0x140029c81  jmp     loc_140029BBE
0x140029c86  cmp     r8d, 2
0x140029c8a  jnz     short loc_140029C9E
0x140029c8c  cmp     [rdx], r13w
0x140029c90  jnz     short loc_140029D0C
0x140029c92  cmp     [rdx+2], r13w
0x140029c97  jnz     short loc_140029D0C
0x140029c99  jmp     loc_140029BEB
0x140029c9e  cmp     r8d, 3
0x140029ca2  jb      short loc_140029D0C
0x140029ca4  cmp     [rdx], r13w
0x140029ca8  jz      short loc_140029D0C
0x140029caa  lea     eax, [r8-2]
0x140029cae  cmp     [rdx+rax*2], r13w
0x140029cb3  jnz     short loc_140029D0C
0x140029cb5  lea     eax, [r8-1]
0x140029cb9  cmp     [rdx+rax*2], r13w
0x140029cbe  jnz     short loc_140029D0C
0x140029cc0  lea     r8, [rdx+r8*2]
0x140029cc4  mov     edi, r13d
0x140029cc7  mov     ebx, r13d
0x140029cca  mov     esi, r13d
0x140029ccd  lea     rax, [rdx+2]
0x140029cd1  jmp     short loc_140029CD7
0x140029cd3  add     rax, 2
0x140029cd7  cmp     [rax], r13w
0x140029cdb  jnz     short loc_140029CD3
0x140029cdd  mov     rcx, rax
0x140029ce0  sub     rcx, rdx
0x140029ce3  sar     rcx, 1
0x140029ce6  cmp     ecx, 4
0x140029ce9  ja      short loc_140029CF0
0x140029ceb  add     edi, r14d
0x140029cee  jmp     short loc_140029CF5
0x140029cf0  add     ebx, r14d
0x140029cf3  add     esi, ecx
0x140029cf5  lea     rdx, [rax+2]
0x140029cf9  cmp     [rdx], r13w
0x140029cfd  jnz     short loc_140029CCD
0x140029cff  lea     rax, [rdx+2]
0x140029d03  cmp     rax, r8
0x140029d06  jz      loc_140029BF4
0x140029d0c  mov     eax, 0C000000Dh
0x140029d11  jmp     loc_14002A004
0x140029d16  mov     eax, edi
0x140029d18  xor     edx, edx; Val
0x140029d1a  mov     rcx, r14; void *
0x140029d1d  lea     r8, ds:0[rax*8]; Size
0x140029d25  mov     eax, ebx
0x140029d27  shl     rax, 4
0x140029d2b  lea     r15, [r8+r14]
0x140029d2f  add     rax, r15
0x140029d32  mov     qword ptr [rbp+57h+String1.Length], rax
0x140029d36  call    memset
0x140029d3b  lea     rax, [rbp+57h+String1]
0x140029d3f  mov     [rbp+57h+var_A0], r13d
0x140029d43  mov     [rsp+0D0h+ResultLength], rax
0x140029d48  lea     r8, [rbp+57h+var_A0]
0x140029d4c  lea     rax, [rbp+57h+arg_18]
0x140029d50  mov     dword ptr [rbp+57h+arg_18], r13d
0x140029d54  mov     r9, r15
0x140029d57  mov     qword ptr [rsp+0D0h+Length], rax
0x140029d5c  mov     rdx, r14
0x140029d5f  lea     rcx, DefaultExcludedExtensions
0x140029d66  call    AddExtensionsList
0x140029d6b  test    r12, r12
0x140029d6e  jz      short loc_140029D95
0x140029d70  lea     rax, [rbp+57h+String1]
0x140029d74  mov     r9, r15
0x140029d77  mov     [rsp+0D0h+ResultLength], rax
0x140029d7c  lea     r8, [rbp+57h+var_A0]
0x140029d80  lea     rax, [rbp+57h+arg_18]
0x140029d84  mov     rdx, r14
0x140029d87  lea     rcx, [rbp+57h+String2]
0x140029d8b  mov     qword ptr [rsp+0D0h+Length], rax
0x140029d90  call    AddExtensionsList
0x140029d95  mov     ecx, edi
0x140029d97  mov     r11d, 1
0x140029d9d  mov     r10b, r11b
0x140029da0  cmp     ecx, r11d
0x140029da3  jbe     short loc_140029DE6
0x140029da5  mov     r8d, r11d
0x140029da8  mov     edx, r11d
0x140029dab  mov     r9d, r11d
0x140029dae  lea     eax, [r9-1]
0x140029db2  mov     rsi, [r14+rax*8]
0x140029db6  mov     r11d, eax
0x140029db9  mov     eax, edx
0x140029dbb  mov     rdx, [r14+rax*8]
0x140029dbf  cmp     rsi, rdx
0x140029dc2  jbe     short loc_140029DD2
0x140029dc4  mov     eax, r9d
0x140029dc7  mov     r10b, r13b
0x140029dca  mov     [r14+r11*8], rdx
0x140029dce  mov     [r14+rax*8], rsi
0x140029dd2  mov     r11d, 1
0x140029dd8  add     r8d, r11d
0x140029ddb  mov     edx, r8d
0x140029dde  mov     r9d, r8d
0x140029de1  cmp     r8d, ecx
0x140029de4  jb      short loc_140029DAE
0x140029de6  dec     ecx
0x140029de8  test    r10b, r10b
0x140029deb  jz      short loc_140029D9D
0x140029ded  cmp     ebx, r11d
0x140029df0  jbe     loc_140029E93
0x140029df6  mov     r12b, r11b
0x140029df9  mov     esi, r11d
0x140029dfc  mov     ecx, r11d
0x140029dff  mov     r13d, r11d
0x140029e02  xorps   xmm0, xmm0
0x140029e05  lea     eax, [r13-1]
0x140029e09  shl     rax, 4
0x140029e0d  lea     rdx, [rbp+57h+String2]; String2
0x140029e11  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x140029e15  mov     [rbp+57h+arg_18], rax
0x140029e19  xor     r8d, r8d; CaseInSensitive
0x140029e1c  xorps   xmm1, xmm1
0x140029e1f  movups  xmmword ptr [rbp+57h+String2.Length], xmm1
0x140029e23  movups  xmm0, xmmword ptr [rax+r15]
0x140029e28  mov     eax, ecx
0x140029e2a  lea     rcx, [rbp+57h+String1]; String1
0x140029e2e  add     rax, rax
0x140029e31  movdqu  xmmword ptr [rbp+57h+String1.Length], xmm0
0x140029e36  movups  xmm0, xmmword ptr [r15+rax*8]
0x140029e3b  movdqu  xmmword ptr [rbp+57h+String2.Length], xmm0
0x140029e40  call    cs:__imp_RtlCompareUnicodeString
0x140029e47  nop     dword ptr [rax+rax+00h]
0x140029e4c  test    eax, eax
0x140029e4e  jle     short loc_140029E71
0x140029e50  movups  xmm0, xmmword ptr [rbp+57h+String2.Length]
0x140029e54  mov     rax, [rbp+57h+arg_18]
0x140029e58  movdqu  xmmword ptr [rax+r15], xmm0
0x140029e5e  mov     eax, r13d
0x140029e61  movups  xmm0, xmmword ptr [rbp+57h+String1.Length]
0x140029e65  add     rax, rax
0x140029e68  xor     r12b, r12b
0x140029e6b  movdqu  xmmword ptr [r15+rax*8], xmm0
0x140029e71  mov     r11d, 1
0x140029e77  add     esi, r11d
0x140029e7a  mov     ecx, esi
0x140029e7c  mov     r13d, esi
0x140029e7f  cmp     esi, ebx
0x140029e81  jb      loc_140029E02
0x140029e87  xor     r13d, r13d
0x140029e8a  test    r12b, r12b
0x140029e8d  jz      loc_140029DED
0x140029e93  mov     esi, r11d
0x140029e96  cmp     edi, r11d
0x140029e99  jbe     short loc_140029EDD
0x140029e9b  mov     eax, esi
0x140029e9d  lea     ecx, [rsi-1]
0x140029ea0  lea     r9, [r14+rax*8]
0x140029ea4  mov     rax, [r9]
0x140029ea7  cmp     [r14+rcx*8], rax
0x140029eab  jnz     short loc_140029ED6
0x140029ead  mov     eax, edi
0x140029eaf  dec     edi
0x140029eb1  sub     eax, esi
0x140029eb3  sub     eax, 1
0x140029eb6  jz      short loc_140029ED9
0x140029eb8  mov     r8d, eax
0x140029ebb  mov     rcx, r9; void *
0x140029ebe  lea     eax, [rsi+1]
0x140029ec1  shl     r8, 3; Size
0x140029ec5  lea     rdx, [r14+rax*8]; Src
0x140029ec9  call    memmove
0x140029ece  mov     r11d, 1
0x140029ed4  jmp     short loc_140029ED9
0x140029ed6  add     esi, r11d
0x140029ed9  cmp     esi, edi
0x140029edb  jb      short loc_140029E9B
0x140029edd  mov     esi, r11d
0x140029ee0  cmp     ebx, r11d
0x140029ee3  jbe     short loc_140029F5E
0x140029ee5  xorps   xmm0, xmm0
0x140029ee8  mov     r12d, esi
0x140029eeb  movups  xmmword ptr [rbp+57h+var_58.Length], xmm0
0x140029eef  shl     r12, 4
0x140029ef3  lea     ecx, [rsi-1]
0x140029ef6  xorps   xmm1, xmm1
0x140029ef9  lea     rdx, [rbp+57h+var_68]; String2
0x140029efd  movups  xmmword ptr [rbp+57h+var_68.Length], xmm1
0x140029f01  add     rcx, rcx
0x140029f04  add     r12, r15
0x140029f07  xor     r8d, r8d; CaseInSensitive
0x140029f0a  movups  xmm0, xmmword ptr [r15+rcx*8]
0x140029f0f  lea     rcx, [rbp+57h+var_58]; String1
0x140029f13  movdqu  xmmword ptr [rbp+57h+var_58.Length], xmm0
0x140029f18  movups  xmm0, xmmword ptr [r12]
0x140029f1d  movdqu  xmmword ptr [rbp+57h+var_68.Length], xmm0
0x140029f22  call    cs:__imp_RtlCompareUnicodeString
0x140029f29  nop     dword ptr [rax+rax+00h]
0x140029f2e  test    eax, eax
0x140029f30  jnz     short loc_140029F58
0x140029f32  mov     eax, ebx
0x140029f34  dec     ebx
0x140029f36  sub     eax, esi
0x140029f38  sub     eax, 1
0x140029f3b  jz      short loc_140029F5A
0x140029f3d  mov     r8d, eax
0x140029f40  lea     edx, [rsi+1]
0x140029f43  shl     rdx, 4
0x140029f47  mov     rcx, r12; void *
0x140029f4a  add     rdx, r15; Src
0x140029f4d  shl     r8, 4; Size
0x140029f51  call    memmove
0x140029f56  jmp     short loc_140029F5A
0x140029f58  inc     esi
0x140029f5a  cmp     esi, ebx
0x140029f5c  jb      short loc_140029EE5
0x140029f5e  mov     dword ptr cs:qword_14000ECB0+4, ebx
0x140029f64  xor     ebx, ebx
  ... truncated ...
```
