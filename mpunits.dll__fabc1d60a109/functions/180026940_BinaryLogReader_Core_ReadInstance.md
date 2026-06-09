# BinaryLogReader_Core_ReadInstance

- ea: `0x180026940`
- end: `0x180026bc8`
- name: `BinaryLogReader_Core_ReadInstance`
- size: `648`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180007000`
- `0x180025fb0`
- `0x18002add0`

## callees

- `0x180007920`
- `0x180026940`
- `0x180026d90`
- `0x180026e78`
- `0x180029be8`
- `0x180043dac`
- `0x180044842`
- `0x180045010`

## import_xrefs

- `msvcrt!malloc` at `0x180026a29`
- `msvcrt!malloc` at `0x180026a29`
- `msvcrt!calloc` at `0x1800269c6`
- `msvcrt!calloc` at `0x1800269e3`
- `msvcrt!calloc` at `0x1800269c6`
- `msvcrt!calloc` at `0x1800269e3`

## pseudocode

```c
__int64 __fastcall BinaryLogReader_Core_ReadInstance(__int64 a1, _QWORD *a2, _BYTE *a3)
{
  _BYTE *v6; // rax
  _BYTE *v7; // rdi
  void *v8; // rax
  void *v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // edi
  __int64 result; // rax
  unsigned int v13; // ecx
  __int64 v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // rax
  __int64 v18; // [rsp+70h] [rbp-69h] BYREF
  _QWORD v19[22]; // [rsp+80h] [rbp-59h] BYREF
  char v20; // [rsp+140h] [rbp+67h] BYREF
  int v21; // [rsp+148h] [rbp+6Fh] BYREF
  LPVOID lpTlsValue; // [rsp+150h] [rbp+77h] BYREF
  __int64 v23; // [rsp+158h] [rbp+7Fh] BYREF

  v20 = 0;
  v18 = 0;
  v21 = 0;
  memset_0(v19, 0, 0x78u);
  *a2 = 0;
  v19[1] = ClassObjectNeeded;
  *a3 = 0;
  v19[10] = ClassObjectNeededOnId;
  v19[12] = ClassObjectAndId;
  lpTlsValue = 0;
  v19[0] = a1;
  v19[9] = a1;
  v19[11] = a1;
  if ( !*(_QWORD *)(a1 + 32) )
  {
    v6 = calloc(1u, 0x30u);
    *(_QWORD *)(a1 + 32) = v6;
    v7 = v6;
    if ( !v6 )
      return 27;
    v8 = calloc(0x64u, 8u);
    *(_QWORD *)v7 = v8;
    if ( !v8 )
      return 27;
    v7[16] = 1;
    *((_QWORD *)v7 + 3) = ClassCacheHash;
    *((_QWORD *)v7 + 4) = ClassCacheEqual;
    *((_QWORD *)v7 + 5) = ClassCacheRelease;
    *((_QWORD *)v7 + 1) = 100;
  }
  if ( *(_QWORD *)(a1 + 80) )
    goto LABEL_13;
  v9 = malloc(0x30u);
  *(_QWORD *)(a1 + 80) = v9;
  if ( !v9 || (unsigned int)HashMap_Init(v9, 100, ClassCacheHash, NameCacheEqual, NameCacheRelease) )
    return 27;
  v10 = *(_QWORD *)(a1 + 72);
  if ( v10 && *(_DWORD *)(v10 + 8) )
  {
    v11 = 0;
    while ( !(unsigned int)NameCache_Update(*(_QWORD *)(a1 + 80), *(_QWORD *)(*(_QWORD *)v10 + 8LL * v11)) )
    {
      v10 = *(_QWORD *)(a1 + 72);
      if ( ++v11 >= *(_DWORD *)(v10 + 8) )
        goto LABEL_13;
    }
    return 27;
  }
LABEL_13:
  while ( 1 )
  {
    result = GetNextBlock(a1, &v20, &v21);
    v13 = result;
    if ( (_DWORD)result )
      break;
    if ( v20 )
    {
      if ( v21 )
      {
        v13 = DeserializeInstance(a1, (unsigned int)&v21, (unsigned int)&v18, (unsigned int)v19, (__int64)&lpTlsValue);
        if ( !v13 )
        {
          ++*(_QWORD *)(a1 + 16);
          v17 = v18;
          *a3 = 1;
          *a2 = v17;
        }
      }
      return v13;
    }
    if ( !v21 )
      return v13;
    v14 = 0;
    v23 = 0;
    if ( *(_QWORD *)(a1 + 40) == 0xFFEEDDCCFFEEDDCCuLL )
    {
      v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD *, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, int *, __int64 *, LPVOID *))(*(_QWORD *)(a1 + 48) + 48LL))(
              a1 + 40,
              0,
              0,
              v19,
              *(_QWORD *)(a1 + 56),
              *(_DWORD *)(a1 + 64),
              0,
              0,
              0,
              &v21,
              &v23,
              &lpTlsValue);
      v14 = v23;
      v16 = v15;
    }
    else
    {
      lpTlsValue = 0;
      v16 = 4;
    }
    if ( v14 )
    {
      if ( *(_QWORD *)(v14 + 16) == 0xFFEEDDCCFFEEDDCCuLL )
        (**(void (***)(void))(v14 + 24))();
    }
    if ( v16 )
    {
      ReportErrorDetails(lpTlsValue);
      return v16;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180026940  push    rbp
0x180026942  push    rbx
0x180026943  push    rsi
0x180026944  push    rdi
0x180026945  push    r12
0x180026947  push    r14
0x180026949  push    r15
0x18002694b  lea     rbp, [rsp-27h]
0x180026950  sub     rsp, 100h
0x180026957  xor     r15d, r15d
0x18002695a  mov     rsi, r8
0x18002695d  mov     r14, rdx
0x180026960  mov     [rbp+57h+arg_0], r15b
0x180026964  mov     rbx, rcx
0x180026967  mov     [rbp+57h+var_C0], r15
0x18002696b  xor     edx, edx; Val
0x18002696d  mov     [rbp+57h+arg_8], r15d
0x180026971  lea     r8d, [r15+78h]; Size
0x180026975  lea     rcx, [rbp+57h+var_B0]; void *
0x180026979  call    memset_0
0x18002697e  lea     rax, ClassObjectNeeded
0x180026985  mov     [r14], r15
0x180026988  mov     [rbp+57h+var_A8], rax
0x18002698c  lea     r12d, [r15+64h]
0x180026990  lea     rax, ClassObjectNeededOnId
0x180026997  mov     [rsi], r15b
0x18002699a  mov     [rbp+57h+var_60], rax
0x18002699e  lea     rax, ClassObjectAndId
0x1800269a5  mov     [rbp+57h+var_50], rax
0x1800269a9  mov     [rbp+57h+lpTlsValue], r15
0x1800269ad  mov     [rbp+57h+var_B0], rbx
0x1800269b1  mov     [rbp+57h+var_68], rbx
0x1800269b5  mov     [rbp+57h+var_58], rbx
0x1800269b9  cmp     [rbx+20h], r15
0x1800269bd  jnz     short loc_180026A1E
0x1800269bf  lea     edx, [r15+30h]; Size
0x1800269c3  lea     ecx, [rdx-2Fh]; Count
0x1800269c6  call    cs:__imp_calloc
0x1800269cc  mov     [rbx+20h], rax
0x1800269d0  mov     rdi, rax
0x1800269d3  test    rax, rax
0x1800269d6  jz      loc_180026B41
0x1800269dc  lea     edx, [r15+8]; Size
0x1800269e0  mov     ecx, r12d; Count
0x1800269e3  call    cs:__imp_calloc
0x1800269e9  mov     [rdi], rax
0x1800269ec  test    rax, rax
0x1800269ef  jz      loc_180026B41
0x1800269f5  lea     rax, ClassCacheHash
0x1800269fc  mov     byte ptr [rdi+10h], 1
0x180026a00  mov     [rdi+18h], rax
0x180026a04  lea     rax, ClassCacheEqual
0x180026a0b  mov     [rdi+20h], rax
0x180026a0f  lea     rax, ClassCacheRelease
0x180026a16  mov     [rdi+28h], rax
0x180026a1a  mov     [rdi+8], r12
0x180026a1e  cmp     [rbx+50h], r15
0x180026a22  jnz     short loc_180026AA0
0x180026a24  mov     ecx, 30h ; '0'; Size
0x180026a29  call    cs:__imp_malloc
0x180026a2f  mov     [rbx+50h], rax
0x180026a33  test    rax, rax
0x180026a36  jz      loc_180026B41
0x180026a3c  lea     rcx, NameCacheRelease
0x180026a43  mov     rdx, r12
0x180026a46  mov     [rsp+130h+var_110], rcx
0x180026a4b  lea     r9, NameCacheEqual
0x180026a52  mov     rcx, rax
0x180026a55  lea     r8, ClassCacheHash
0x180026a5c  call    HashMap_Init
0x180026a61  test    eax, eax
0x180026a63  jnz     loc_180026B41
0x180026a69  mov     rcx, [rbx+48h]
0x180026a6d  test    rcx, rcx
0x180026a70  jz      short loc_180026AA0
0x180026a72  cmp     [rcx+8], r15d
0x180026a76  jbe     short loc_180026AA0
0x180026a78  mov     edi, r15d
0x180026a7b  mov     rdx, [rcx]
0x180026a7e  mov     rcx, [rbx+50h]
0x180026a82  mov     eax, edi
0x180026a84  mov     rdx, [rdx+rax*8]
0x180026a88  call    NameCache_Update
0x180026a8d  test    eax, eax
0x180026a8f  jnz     loc_180026B41
0x180026a95  mov     rcx, [rbx+48h]
0x180026a99  inc     edi
0x180026a9b  cmp     edi, [rcx+8]
0x180026a9e  jb      short loc_180026A7B
0x180026aa0  mov     r12, 0FFEEDDCCFFEEDDCCh
0x180026aaa  lea     r8, [rbp+57h+arg_8]
0x180026aae  mov     rcx, rbx
0x180026ab1  lea     rdx, [rbp+57h+arg_0]
0x180026ab5  call    GetNextBlock
0x180026aba  mov     ecx, eax
0x180026abc  test    eax, eax
0x180026abe  jnz     loc_180026BB6
0x180026ac4  cmp     [rbp+57h+arg_0], r15b
0x180026ac8  jnz     loc_180026B7D
0x180026ace  cmp     [rbp+57h+arg_8], r15d
0x180026ad2  jbe     loc_180026BB4
0x180026ad8  mov     rcx, r15
0x180026adb  mov     [rbp+57h+arg_18], rcx
0x180026adf  cmp     [rbx+28h], r12
0x180026ae3  jnz     short loc_180026B48
0x180026ae5  mov     edx, [rbx+40h]
0x180026ae8  lea     rcx, [rbp+57h+lpTlsValue]
0x180026aec  mov     rax, [rbx+30h]
0x180026af0  lea     r9, [rbp+57h+var_B0]
0x180026af4  mov     [rsp+130h+var_D8], rcx
0x180026af9  xor     r8d, r8d
0x180026afc  lea     rcx, [rbp+57h+arg_18]
0x180026b00  mov     [rsp+130h+var_E0], rcx
0x180026b05  lea     rcx, [rbp+57h+arg_8]
0x180026b09  mov     rax, [rax+30h]
0x180026b0d  mov     [rsp+130h+var_E8], rcx
0x180026b12  lea     rcx, [rbx+28h]
0x180026b16  mov     [rsp+130h+var_F0], r15
0x180026b1b  mov     [rsp+130h+var_F8], r15
0x180026b20  mov     [rsp+130h+var_100], r15
0x180026b25  mov     [rsp+130h+var_108], edx
0x180026b29  mov     rdx, [rbx+38h]
0x180026b2d  mov     [rsp+130h+var_110], rdx
0x180026b32  xor     edx, edx
0x180026b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b39  mov     rcx, [rbp+57h+arg_18]
0x180026b3d  mov     edi, eax
0x180026b3f  jmp     short loc_180026B51
0x180026b41  mov     eax, 1Bh
0x180026b46  jmp     short loc_180026BB6
0x180026b48  mov     [rbp+57h+lpTlsValue], r15
0x180026b4c  mov     edi, 4
0x180026b51  test    rcx, rcx
0x180026b54  jz      short loc_180026B68
0x180026b56  cmp     [rcx+10h], r12
0x180026b5a  jnz     short loc_180026B68
0x180026b5c  mov     rax, [rcx+18h]
0x180026b60  mov     rax, [rax]
0x180026b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b68  test    edi, edi
0x180026b6a  jz      loc_180026AAA
0x180026b70  mov     rcx, [rbp+57h+lpTlsValue]; lpTlsValue
0x180026b74  call    ReportErrorDetails
0x180026b79  mov     eax, edi
0x180026b7b  jmp     short loc_180026BB6
0x180026b7d  cmp     [rbp+57h+arg_8], r15d
0x180026b81  jbe     short loc_180026BB4
0x180026b83  lea     rax, [rbp+57h+lpTlsValue]
0x180026b87  mov     rcx, rbx
0x180026b8a  lea     r9, [rbp+57h+var_B0]
0x180026b8e  mov     [rsp+130h+var_110], rax
0x180026b93  lea     r8, [rbp+57h+var_C0]
0x180026b97  lea     rdx, [rbp+57h+arg_8]
0x180026b9b  call    DeserializeInstance
0x180026ba0  mov     ecx, eax
0x180026ba2  test    eax, eax
0x180026ba4  jnz     short loc_180026BB4
0x180026ba6  inc     qword ptr [rbx+10h]
0x180026baa  mov     rax, [rbp+57h+var_C0]
0x180026bae  mov     byte ptr [rsi], 1
0x180026bb1  mov     [r14], rax
0x180026bb4  mov     eax, ecx
0x180026bb6  add     rsp, 100h
0x180026bbd  pop     r15
0x180026bbf  pop     r14
0x180026bc1  pop     r12
0x180026bc3  pop     rdi
0x180026bc4  pop     rsi
0x180026bc5  pop     rbx
0x180026bc6  pop     rbp
0x180026bc7  retn
```
