# I_ReaderListClearReader

- ea: `0x18000c8f0`
- end: `0x18000cb94`
- name: `I_ReaderListClearReader`
- size: `676`
- prototype: `__int64 __fastcall(__int64, unsigned __int16 *, _DWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180004900`
- `0x1800062e0`

## callees

- `0x180004600`
- `0x18000c8f0`
- `0x18000cce0`
- `0x180016a66`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000caaa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cac2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cada`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000caf2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ca92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000caaa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cac2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cada`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000caf2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cb0a`
- `CRYPT32!CertCloseStore` at `0x18000ca63`
- `CRYPT32!CertCloseStore` at `0x18000ca77`
- `CRYPT32!CertCloseStore` at `0x18000ca63`
- `CRYPT32!CertCloseStore` at `0x18000ca77`
- `ncrypt!NCryptFreeObject` at `0x18000cb30`
- `ncrypt!NCryptFreeObject` at `0x18000cb30`
- `ADVAPI32!CryptReleaseContext` at `0x18000cb1e`
- `ADVAPI32!CryptReleaseContext` at `0x18000cb1e`

## pseudocode

```c
__int64 __fastcall I_ReaderListClearReader(__int64 a1, unsigned __int16 *a2, _DWORD *a3)
{
  STRSAFE_LPSTR v6; // rcx
  __int64 *v7; // r14
  unsigned __int16 *v8; // rax
  int v9; // edx
  unsigned int v10; // r15d
  __int64 v12; // rcx
  int i; // r12d
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // r8
  void *v17; // r8
  void *v18; // r8
  void *v19; // r8
  void *v20; // r8
  void *v21; // r8
  HCRYPTPROV v22; // rcx
  NCRYPT_HANDLE v23; // rcx
  __int64 v24; // rbp
  int v25; // esi
  int v26; // edi
  __int64 v27; // rbx

  WppTraceIndent(a1, 0);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( a3 )
    *a3 = 0;
  v7 = *(__int64 **)(a1 + 112);
  if ( v7 )
  {
    while ( 1 )
    {
      v8 = a2;
      do
      {
        v6 = (STRSAFE_LPSTR)*(unsigned __int16 *)((char *)v8 + *v7 - (_QWORD)a2);
        v9 = *v8 - (_DWORD)v6;
        if ( v9 )
          break;
        ++v8;
      }
      while ( (_DWORD)v6 );
      if ( !v9 )
        break;
      v7 = (__int64 *)v7[30];
      if ( !v7 )
        goto LABEL_13;
    }
    v12 = v7[29];
    v10 = 0;
    for ( i = 0; v12; ++i )
    {
      v7[29] = *(_QWORD *)(v12 + 104);
      I_FreeCredListItem((LPVOID *)v12);
      v12 = v7[29];
    }
    v14 = (void *)v7[21];
    if ( v14 )
      CertCloseStore(v14, 0);
    v15 = (void *)v7[22];
    if ( v15 )
    {
      CertCloseStore(v15, 0);
      ++i;
    }
    v16 = (void *)v7[13];
    if ( v16 )
      HeapFree(hHeap, 0, v16);
    v17 = (void *)v7[14];
    if ( v17 )
      HeapFree(hHeap, 0, v17);
    v18 = (void *)v7[2];
    if ( v18 )
      HeapFree(hHeap, 0, v18);
    v19 = (void *)v7[10];
    if ( v19 )
      HeapFree(hHeap, 0, v19);
    v20 = (void *)v7[11];
    if ( v20 )
      HeapFree(hHeap, 0, v20);
    v21 = (void *)v7[12];
    if ( v21 )
      HeapFree(hHeap, 0, v21);
    v22 = v7[16];
    if ( v22 )
      CryptReleaseContext(v22, 0);
    v23 = v7[17];
    if ( v23 )
      NCryptFreeObject(v23);
    v24 = *v7;
    v25 = *((_DWORD *)v7 + 2);
    v26 = *((_DWORD *)v7 + 3);
    v27 = v7[30];
    memset_0(v7 + 2, 0, 0xE0u);
    *v7 = v24;
    *((_DWORD *)v7 + 2) = v25;
    *((_DWORD *)v7 + 3) = v26;
    v7[30] = v27;
    if ( a3 )
      *a3 = i != 0;
  }
  else
  {
LABEL_13:
    v10 = 1168;
  }
  WppTraceIndent(v6, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      191,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x18000c8f0  sub     rsp, 58h
0x18000c8f4  mov     [rsp+58h+arg_0], rbx
0x18000c8f9  mov     rbx, rdx
0x18000c8fc  mov     [rsp+58h+var_18], r13
0x18000c901  xor     edx, edx
0x18000c903  mov     [rsp+58h+var_20], r14
0x18000c908  mov     r13, r8
0x18000c90b  mov     r14, rcx
0x18000c90e  call    WppTraceIndent
0x18000c913  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c91a  lea     rax, WPP_GLOBAL_Control
0x18000c921  cmp     rcx, rax
0x18000c924  jz      short loc_18000C94E
0x18000c926  test    byte ptr [rcx+1Ch], 2
0x18000c92a  jz      short loc_18000C94E
0x18000c92c  cmp     byte ptr [rcx+19h], 5
0x18000c930  jb      short loc_18000C94E
0x18000c932  mov     r9, cs:WPP_pszIndent
0x18000c939  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000c940  mov     rcx, [rcx+10h]
0x18000c944  mov     edx, 0BEh
0x18000c949  call    WPP_SF_s
0x18000c94e  test    r13, r13
0x18000c951  jz      short loc_18000C95B
0x18000c953  mov     dword ptr [r13+0], 0
0x18000c95b  mov     r14, [r14+70h]
0x18000c95f  mov     [rsp+58h+var_10], r12
0x18000c964  mov     [rsp+58h+var_28], r15
0x18000c969  test    r14, r14
0x18000c96c  jz      short loc_18000C9A4
0x18000c96e  xchg    ax, ax
0x18000c970  mov     r8, [r14]
0x18000c973  mov     rax, rbx
0x18000c976  sub     r8, rbx
0x18000c979  nop     dword ptr [rax+00000000h]
0x18000c980  movzx   edx, word ptr [rax]
0x18000c983  movzx   ecx, word ptr [rax+r8]
0x18000c988  sub     edx, ecx
0x18000c98a  jnz     short loc_18000C994
0x18000c98c  add     rax, 2
0x18000c990  test    ecx, ecx
0x18000c992  jnz     short loc_18000C980
0x18000c994  test    edx, edx
0x18000c996  jz      short loc_18000CA15
0x18000c998  mov     r14, [r14+0F0h]
0x18000c99f  test    r14, r14
0x18000c9a2  jnz     short loc_18000C970
0x18000c9a4  mov     r15d, 490h
0x18000c9aa  mov     edx, 1
0x18000c9af  call    WppTraceIndent
0x18000c9b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c9bb  lea     rax, WPP_GLOBAL_Control
0x18000c9c2  mov     r14, [rsp+58h+var_20]
0x18000c9c7  mov     r13, [rsp+58h+var_18]
0x18000c9cc  mov     r12, [rsp+58h+var_10]
0x18000c9d1  mov     rbx, [rsp+58h+arg_0]
0x18000c9d6  cmp     rcx, rax
0x18000c9d9  jz      short loc_18000CA08
0x18000c9db  test    byte ptr [rcx+1Ch], 2
0x18000c9df  jz      short loc_18000CA08
0x18000c9e1  cmp     byte ptr [rcx+19h], 5
0x18000c9e5  jb      short loc_18000CA08
0x18000c9e7  mov     r9, cs:WPP_pszIndent
0x18000c9ee  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18000c9f5  mov     rcx, [rcx+10h]
0x18000c9f9  mov     edx, 0BFh
0x18000c9fe  mov     [rsp+58h+var_38], r15d
0x18000ca03  call    WPP_SF_sD
0x18000ca08  mov     eax, r15d
0x18000ca0b  mov     r15, [rsp+58h+var_28]
0x18000ca10  add     rsp, 58h
0x18000ca14  retn
0x18000ca15  mov     rcx, [r14+0E8h]; lpMem
0x18000ca1c  xor     r15d, r15d
0x18000ca1f  mov     [rsp+58h+arg_8], rbp
0x18000ca24  xor     r12d, r12d
0x18000ca27  mov     [rsp+58h+arg_10], rsi
0x18000ca2c  mov     [rsp+58h+var_8], rdi
0x18000ca31  test    rcx, rcx
0x18000ca34  jz      short loc_18000CA55
0x18000ca36  mov     rax, [rcx+68h]
0x18000ca3a  mov     [r14+0E8h], rax
0x18000ca41  call    I_FreeCredListItem
0x18000ca46  mov     rcx, [r14+0E8h]
0x18000ca4d  inc     r12d
0x18000ca50  test    rcx, rcx
0x18000ca53  jnz     short loc_18000CA36
0x18000ca55  mov     rcx, [r14+0A8h]; hCertStore
0x18000ca5c  test    rcx, rcx
0x18000ca5f  jz      short loc_18000CA69
0x18000ca61  xor     edx, edx; dwFlags
0x18000ca63  call    cs:__imp_CertCloseStore
0x18000ca69  mov     rcx, [r14+0B0h]; hCertStore
0x18000ca70  test    rcx, rcx
0x18000ca73  jz      short loc_18000CA80
0x18000ca75  xor     edx, edx; dwFlags
0x18000ca77  call    cs:__imp_CertCloseStore
0x18000ca7d  inc     r12d
0x18000ca80  mov     r8, [r14+68h]; lpMem
0x18000ca84  test    r8, r8
0x18000ca87  jz      short loc_18000CA98
0x18000ca89  mov     rcx, cs:hHeap; hHeap
0x18000ca90  xor     edx, edx; dwFlags
0x18000ca92  call    cs:__imp_HeapFree
0x18000ca98  mov     r8, [r14+70h]; lpMem
0x18000ca9c  test    r8, r8
0x18000ca9f  jz      short loc_18000CAB0
0x18000caa1  mov     rcx, cs:hHeap; hHeap
0x18000caa8  xor     edx, edx; dwFlags
0x18000caaa  call    cs:__imp_HeapFree
0x18000cab0  mov     r8, [r14+10h]; lpMem
0x18000cab4  test    r8, r8
0x18000cab7  jz      short loc_18000CAC8
0x18000cab9  mov     rcx, cs:hHeap; hHeap
0x18000cac0  xor     edx, edx; dwFlags
0x18000cac2  call    cs:__imp_HeapFree
0x18000cac8  mov     r8, [r14+50h]; lpMem
0x18000cacc  test    r8, r8
0x18000cacf  jz      short loc_18000CAE0
0x18000cad1  mov     rcx, cs:hHeap; hHeap
0x18000cad8  xor     edx, edx; dwFlags
0x18000cada  call    cs:__imp_HeapFree
0x18000cae0  mov     r8, [r14+58h]; lpMem
0x18000cae4  test    r8, r8
0x18000cae7  jz      short loc_18000CAF8
0x18000cae9  mov     rcx, cs:hHeap; hHeap
0x18000caf0  xor     edx, edx; dwFlags
0x18000caf2  call    cs:__imp_HeapFree
0x18000caf8  mov     r8, [r14+60h]; lpMem
0x18000cafc  test    r8, r8
0x18000caff  jz      short loc_18000CB10
0x18000cb01  mov     rcx, cs:hHeap; hHeap
0x18000cb08  xor     edx, edx; dwFlags
0x18000cb0a  call    cs:__imp_HeapFree
0x18000cb10  mov     rcx, [r14+80h]; hProv
0x18000cb17  test    rcx, rcx
0x18000cb1a  jz      short loc_18000CB24
0x18000cb1c  xor     edx, edx; dwFlags
0x18000cb1e  call    cs:__imp_CryptReleaseContext
0x18000cb24  mov     rcx, [r14+88h]; hObject
0x18000cb2b  test    rcx, rcx
0x18000cb2e  jz      short loc_18000CB36
0x18000cb30  call    cs:__imp_NCryptFreeObject
0x18000cb36  mov     rbp, [r14]
0x18000cb39  lea     rcx, [r14+10h]; void *
0x18000cb3d  mov     esi, [r14+8]
0x18000cb41  xor     edx, edx; Val
0x18000cb43  mov     edi, [r14+0Ch]
0x18000cb47  mov     r8d, 0E0h; Size
0x18000cb4d  mov     rbx, [r14+0F0h]
0x18000cb54  call    memset_0
0x18000cb59  mov     [r14], rbp
0x18000cb5c  mov     rbp, [rsp+58h+arg_8]
0x18000cb61  mov     [r14+8], esi
0x18000cb65  mov     rsi, [rsp+58h+arg_10]
0x18000cb6a  mov     [r14+0Ch], edi
0x18000cb6e  mov     rdi, [rsp+58h+var_8]
0x18000cb73  mov     [r14+0F0h], rbx
0x18000cb7a  test    r13, r13
0x18000cb7d  jz      loc_18000C9AA
0x18000cb83  xor     eax, eax
0x18000cb85  test    r12d, r12d
0x18000cb88  setnz   al
0x18000cb8b  mov     [r13+0], eax
0x18000cb8f  jmp     loc_18000C9AA
```
