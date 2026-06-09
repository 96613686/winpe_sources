# ProvOpenAlgorithmProvider

- ea: `0x14000a690`
- end: `0x14000a816`
- name: `ProvOpenAlgorithmProvider`
- size: `390`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140001244`
- `0x140001280`
- `0x140001fd4`
- `0x140003cf6`
- `0x14000a690`

## import_xrefs

- `cng!BCryptCloseAlgorithmProvider` at `0x14000a7af`
- `cng!BCryptCloseAlgorithmProvider` at `0x14000a7f7`
- `cng!BCryptCloseAlgorithmProvider` at `0x14000a7af`
- `cng!BCryptCloseAlgorithmProvider` at `0x14000a7f7`
- `cng!BCryptOpenAlgorithmProvider` at `0x14000a6ee`
- `cng!BCryptOpenAlgorithmProvider` at `0x14000a6ee`
- `cng!BCryptGetProperty` at `0x14000a786`
- `cng!BCryptGetProperty` at `0x14000a786`

## pseudocode

```c
__int64 __fastcall ProvOpenAlgorithmProvider(_QWORD *a1, const wchar_t *a2, ULONG a3)
{
  NTSTATUS Property; // edi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  signed __int32 v9; // eax
  bool v10; // zf
  void *v11; // rcx
  UCHAR pbOutput[8]; // [rsp+30h] [rbp-18h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+38h] [rbp-10h] BYREF
  ULONG pcbResult; // [rsp+68h] [rbp+20h] BYREF

  phAlgorithm = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  if ( wcscmp_0(a2, L"AES") )
    return (unsigned int)-1073741637;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, a2, L"Microsoft Primitive Provider", a3);
  if ( Property >= 0 )
  {
    v7 = (_DWORD *)ProvAlloc(0x18u);
    v8 = v7;
    if ( !v7 )
    {
      Property = -1073741801;
      goto LABEL_15;
    }
    *v7 = 1816224072;
    v9 = _InterlockedExchangeAdd(&g_ulUnique, 1u);
    *((_BYTE *)v8 + 12) = 0;
    v10 = g_cbSoftwareKeyObjectSize == 0;
    v8[1] = v9 + 1;
    v8[2] = 1;
    *((_QWORD *)v8 + 2) = phAlgorithm;
    phAlgorithm = 0;
    if ( v10 )
    {
      Property = BCryptGetProperty(*((BCRYPT_HANDLE *)v8 + 2), L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
      if ( Property < 0 )
      {
LABEL_10:
        v11 = (void *)*((_QWORD *)v8 + 2);
        if ( v11 )
        {
          BCryptCloseAlgorithmProvider(v11, 0);
          *((_QWORD *)v8 + 2) = 0;
        }
        ProvFree(v8);
        goto LABEL_15;
      }
      if ( pcbResult != 4 )
      {
        Property = -1073741595;
        goto LABEL_10;
      }
      g_cbSoftwareKeyObjectSize = *(_DWORD *)pbOutput;
      g_cbMyKeyObjectSize = *(_DWORD *)pbOutput + 112;
    }
    *a1 = GetHandleFromPointer(v8);
  }
LABEL_15:
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x14000a690  mov     rax, rsp
0x14000a693  mov     [rax+8], rbx
0x14000a697  mov     [rax+10h], rsi
0x14000a69b  push    rdi
0x14000a69c  sub     rsp, 40h
0x14000a6a0  mov     rbx, rdx
0x14000a6a3  mov     qword ptr [rax-10h], 0
0x14000a6ab  mov     rsi, rcx
0x14000a6ae  mov     dword ptr [rax-18h], 0
0x14000a6b5  mov     rcx, rbx; Str1
0x14000a6b8  mov     dword ptr [rax+20h], 0
0x14000a6bf  lea     rdx, aAes; "AES"
0x14000a6c6  mov     edi, r8d
0x14000a6c9  call    wcscmp_0
0x14000a6ce  test    eax, eax
0x14000a6d0  jz      short loc_14000A6DC
0x14000a6d2  mov     edi, 0C00000BBh
0x14000a6d7  jmp     loc_14000A803
0x14000a6dc  mov     r9d, edi; dwFlags
0x14000a6df  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x14000a6e6  mov     rdx, rbx; pszAlgId
0x14000a6e9  lea     rcx, [rsp+48h+phAlgorithm]; phAlgorithm
0x14000a6ee  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14000a6f5  nop     dword ptr [rax+rax+00h]
0x14000a6fa  mov     edi, eax
0x14000a6fc  test    eax, eax
0x14000a6fe  js      loc_14000A7EB
0x14000a704  mov     ecx, 18h; Size
0x14000a709  call    ProvAlloc
0x14000a70e  mov     rbx, rax
0x14000a711  test    rax, rax
0x14000a714  jnz     short loc_14000A720
0x14000a716  mov     edi, 0C0000017h
0x14000a71b  jmp     loc_14000A7EB
0x14000a720  mov     ecx, 1
0x14000a725  mov     dword ptr [rax], 6C416148h
0x14000a72b  mov     eax, ecx
0x14000a72d  lock xadd cs:g_ulUnique, eax
0x14000a735  add     eax, ecx
0x14000a737  mov     byte ptr [rbx+0Ch], 0
0x14000a73b  cmp     cs:g_cbSoftwareKeyObjectSize, 0
0x14000a742  mov     [rbx+4], eax
0x14000a745  mov     [rbx+8], ecx
0x14000a748  mov     rax, [rsp+48h+phAlgorithm]
0x14000a74d  mov     [rbx+10h], rax
0x14000a751  mov     [rsp+48h+phAlgorithm], 0
0x14000a75a  jnz     loc_14000A7E0
0x14000a760  lea     rax, [rsp+48h+arg_18]
0x14000a765  mov     [rsp+48h+dwFlags], 0; dwFlags
0x14000a76d  lea     r9d, [rcx+3]; cbOutput
0x14000a771  mov     [rsp+48h+pcbResult], rax; pcbResult
0x14000a776  mov     rcx, [rbx+10h]; hObject
0x14000a77a  lea     r8, [rsp+48h+pbOutput]; pbOutput
0x14000a77f  lea     rdx, aObjectlength; "ObjectLength"
0x14000a786  call    cs:__imp_BCryptGetProperty
0x14000a78d  nop     dword ptr [rax+rax+00h]
0x14000a792  mov     edi, eax
0x14000a794  test    eax, eax
0x14000a796  js      short loc_14000A7A4
0x14000a798  cmp     [rsp+48h+arg_18], 4
0x14000a79d  jz      short loc_14000A7CD
0x14000a79f  mov     edi, 0C00000E5h
0x14000a7a4  mov     rcx, [rbx+10h]; hAlgorithm
0x14000a7a8  test    rcx, rcx
0x14000a7ab  jz      short loc_14000A7C3
0x14000a7ad  xor     edx, edx; dwFlags
0x14000a7af  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000a7b6  nop     dword ptr [rax+rax+00h]
0x14000a7bb  mov     qword ptr [rbx+10h], 0
0x14000a7c3  mov     rcx, rbx
0x14000a7c6  call    ProvFree
0x14000a7cb  jmp     short loc_14000A7EB
0x14000a7cd  mov     eax, dword ptr [rsp+48h+pbOutput]
0x14000a7d1  mov     cs:g_cbSoftwareKeyObjectSize, eax
0x14000a7d7  add     eax, 70h ; 'p'
0x14000a7da  mov     cs:g_cbMyKeyObjectSize, eax
0x14000a7e0  mov     rcx, rbx
0x14000a7e3  call    GetHandleFromPointer
0x14000a7e8  mov     [rsi], rax
0x14000a7eb  mov     rcx, [rsp+48h+phAlgorithm]; hAlgorithm
0x14000a7f0  test    rcx, rcx
0x14000a7f3  jz      short loc_14000A803
0x14000a7f5  xor     edx, edx; dwFlags
0x14000a7f7  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000a7fe  nop     dword ptr [rax+rax+00h]
0x14000a803  mov     rbx, [rsp+48h+arg_0]
0x14000a808  mov     eax, edi
0x14000a80a  mov     rsi, [rsp+48h+arg_8]
0x14000a80f  add     rsp, 40h
0x14000a813  pop     rdi
0x14000a814  retn
```
