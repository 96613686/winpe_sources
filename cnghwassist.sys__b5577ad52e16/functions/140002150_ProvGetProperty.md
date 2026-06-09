# ProvGetProperty

- ea: `0x140002150`
- end: `0x14000225b`
- name: `ProvGetProperty`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140002150`
- `0x140003cf6`

## import_xrefs

- `cng!BCryptGetProperty` at `0x140002227`
- `cng!BCryptGetProperty` at `0x140002227`

## string_xrefs

- `0x140002189`: `HardwareThreads`

## pseudocode

```c
NTSTATUS __fastcall ProvGetProperty(
        __int64 a1,
        const wchar_t *a2,
        UCHAR *a3,
        ULONG a4,
        ULONG *pcbResult,
        ULONG dwFlags)
{
  __int64 v6; // rbp
  __int64 v8; // rax
  unsigned int v9; // edi
  UCHAR *v10; // rbx
  int v11; // edx
  int v13; // eax
  void *v14; // rcx
  __int64 v15; // rcx

  v6 = 0;
  v8 = a1 ^ 0x4000000000000000LL;
  v9 = a4;
  v10 = a3;
  v11 = *(_DWORD *)(a1 ^ 0x4000000000000000LL);
  if ( v11 == 1816224072 )
    v6 = a1 ^ 0x4000000000000000LL;
  if ( v6 )
  {
    if ( !wcscmp_0(a2, L"HardwareThreads") )
    {
      *pcbResult = 4;
      if ( !v10 )
        return 0;
      if ( v9 < 4 )
        return -1073741789;
      v13 = g_config[0];
      goto LABEL_10;
    }
    if ( !wcscmp_0(a2, L"ObjectLength") )
    {
      *pcbResult = 4;
      if ( !v10 )
        return 0;
      if ( v9 < 4 )
        return -1073741789;
      v13 = g_cbMyKeyObjectSize;
LABEL_10:
      *(_DWORD *)v10 = v13;
      return 0;
    }
    v14 = *(void **)(v6 + 16);
    a4 = v9;
    a3 = v10;
    return BCryptGetProperty(v14, a2, a3, a4, pcbResult, dwFlags);
  }
  v15 = 0;
  if ( v11 == 2034983240 )
    v15 = v8;
  if ( v15 )
  {
    v14 = *(void **)(v15 + 16);
    return BCryptGetProperty(v14, a2, a3, a4, pcbResult, dwFlags);
  }
  return -1073741816;
}

```

## disassembly

```asm
0x140002150  push    rbx
0x140002152  push    rbp
0x140002153  push    rsi
0x140002154  push    rdi
0x140002155  sub     rsp, 38h
0x140002159  xor     ebp, ebp
0x14000215b  mov     rax, rcx
0x14000215e  mov     rcx, 4000000000000000h
0x140002168  mov     rsi, rdx
0x14000216b  xor     rax, rcx
0x14000216e  mov     edi, r9d
0x140002171  mov     rbx, r8
0x140002174  mov     edx, [rax]
0x140002176  cmp     edx, 6C416148h
0x14000217c  cmovz   rbp, rax
0x140002180  test    rbp, rbp
0x140002183  jz      loc_140002235
0x140002189  lea     rdx, aHardwarethread; "HardwareThreads"
0x140002190  mov     rcx, rsi; Str1
0x140002193  call    wcscmp_0
0x140002198  test    eax, eax
0x14000219a  jnz     short loc_1400021CF
0x14000219c  mov     rax, [rsp+58h+arg_20]
0x1400021a4  mov     dword ptr [rax], 4
0x1400021aa  test    rbx, rbx
0x1400021ad  jnz     short loc_1400021B6
0x1400021af  xor     eax, eax
0x1400021b1  jmp     loc_140002251
0x1400021b6  cmp     edi, 4
0x1400021b9  jnb     short loc_1400021C5
0x1400021bb  mov     eax, 0C0000023h
0x1400021c0  jmp     loc_140002251
0x1400021c5  mov     eax, cs:g_config
0x1400021cb  mov     [rbx], eax
0x1400021cd  jmp     short loc_1400021AF
0x1400021cf  lea     rdx, aObjectlength; "ObjectLength"
0x1400021d6  mov     rcx, rsi; Str1
0x1400021d9  call    wcscmp_0
0x1400021de  test    eax, eax
0x1400021e0  jnz     short loc_140002202
0x1400021e2  mov     rax, [rsp+58h+arg_20]
0x1400021ea  mov     dword ptr [rax], 4
0x1400021f0  test    rbx, rbx
0x1400021f3  jz      short loc_1400021AF
0x1400021f5  cmp     edi, 4
0x1400021f8  jb      short loc_1400021BB
0x1400021fa  mov     eax, cs:g_cbMyKeyObjectSize
0x140002200  jmp     short loc_1400021CB
0x140002202  mov     rcx, [rbp+10h]; hObject
0x140002206  mov     r9d, edi; cbOutput
0x140002209  mov     r8, rbx; pbOutput
0x14000220c  mov     eax, [rsp+58h+arg_28]
0x140002213  mov     rdx, rsi; pszProperty
0x140002216  mov     [rsp+58h+dwFlags], eax; dwFlags
0x14000221a  mov     rax, [rsp+58h+arg_20]
0x140002222  mov     [rsp+58h+pcbResult], rax; pcbResult
0x140002227  call    cs:__imp_BCryptGetProperty
0x14000222e  nop     dword ptr [rax+rax+00h]
0x140002233  jmp     short loc_140002251
0x140002235  xor     ecx, ecx
0x140002237  cmp     edx, 794B6148h
0x14000223d  cmovz   rcx, rax
0x140002241  test    rcx, rcx
0x140002244  jz      short loc_14000224C
0x140002246  mov     rcx, [rcx+10h]
0x14000224a  jmp     short loc_14000220C
0x14000224c  mov     eax, 0C0000008h
0x140002251  add     rsp, 38h
0x140002255  pop     rdi
0x140002256  pop     rsi
0x140002257  pop     rbp
0x140002258  pop     rbx
0x140002259  retn
```
