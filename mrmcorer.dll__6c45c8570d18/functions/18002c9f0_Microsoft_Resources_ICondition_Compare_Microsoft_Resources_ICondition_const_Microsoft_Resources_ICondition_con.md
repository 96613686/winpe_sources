# Microsoft::Resources::ICondition::Compare(Microsoft::Resources::ICondition const *,Microsoft::Resources::ICondition const *)

- ea: `0x18002c9f0`
- end: `0x18002cfc9`
- name: `?Compare@ICondition@Resources@Microsoft@@SA?AW4_DEFCOMPARISON@@PEBV123@0@Z`
- size: `1497`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180028de0`
- `0x18002bfc0`
- `0x18002c900`
- `0x18004dd50`

## callees

- `0x180016b00`
- `0x18002c9f0`
- `0x18002cfd0`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cdaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cdd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ce39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ce5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd57`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd75`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cd96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cdaf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002cdd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ce39`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002ce5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cd65`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cd83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cda4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cdbd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cdde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ce47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ce6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cd65`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cd83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cda4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cdbd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002cdde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ce47`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002ce6d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002cbfb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002cbfb`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::ICondition::Compare(
        int (__fastcall ***a1)(__int64, unsigned __int64 *),
        int (__fastcall ***a2)(__int64, unsigned __int64 *))
{
  int (__fastcall **v4)(__int64, unsigned __int64 *); // rax
  int (__fastcall *v5)(__int64, unsigned __int64 *); // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  bool v8; // cc
  const WCHAR *v9; // r8
  const WCHAR *v10; // rcx
  int v11; // eax
  unsigned int v12; // ebx
  void *v13; // rdi
  void *v14; // rdi
  __int64 result; // rax
  unsigned int v16; // esi
  void *v17; // rbx
  void *v18; // rbx
  void *v19; // rbx
  void *v20; // rbx
  HANDLE v21; // rax
  HANDLE v22; // rax
  HANDLE v23; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v25; // rax
  void *v26; // rbx
  HANDLE v27; // rax
  HANDLE v28; // rax
  unsigned int v29; // esi
  unsigned __int64 v30; // [rsp+38h] [rbp-19h] BYREF
  unsigned __int64 v31; // [rsp+40h] [rbp-11h] BYREF
  LPVOID *p_lpMem; // [rsp+48h] [rbp-9h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-1h] BYREF
  int v34; // [rsp+58h] [rbp+7h]
  __int64 v35; // [rsp+60h] [rbp+Fh]
  LPVOID *v36; // [rsp+68h] [rbp+17h] BYREF
  LPVOID v37; // [rsp+70h] [rbp+1Fh] BYREF
  int v38; // [rsp+78h] [rbp+27h]
  __int64 v39; // [rsp+80h] [rbp+2Fh]
  char v40; // [rsp+B8h] [rbp+67h] BYREF
  char v41; // [rsp+C0h] [rbp+6Fh] BYREF
  int v42; // [rsp+C8h] [rbp+77h] BYREF
  int v43; // [rsp+D0h] [rbp+7Fh] BYREF

  if ( a1 == a2 )
    return 0;
  if ( (a1 == 0) != (a2 == 0) )
  {
    result = 1;
    if ( !a1 )
      return 0xFFFFFFFFLL;
    return result;
  }
  v30 = 0;
  v36 = &v37;
  v31 = 0;
  p_lpMem = &lpMem;
  v4 = *a1;
  v42 = 0;
  v43 = 0;
  v37 = 0;
  v5 = *v4;
  v38 = 0;
  v39 = 0;
  lpMem = 0;
  v34 = 0;
  v35 = 0;
  v41 = 0;
  v40 = 0;
  if ( v5((__int64)a1, &v30) < 0 || (**a2)((__int64)a2, &v31) < 0 )
  {
    v6 = v30;
    v7 = v31;
    goto LABEL_45;
  }
  v6 = v30;
  v7 = v31;
  if ( v30 != v31 )
  {
LABEL_45:
    v16 = -1;
    if ( v6 > v7 )
      v16 = 1;
    v17 = lpMem;
    if ( (lpMem || !v34) && (v34 || !lpMem) )
    {
      v35 = 0;
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v17);
        lpMem = 0;
        v34 = 0;
      }
    }
    v18 = v37;
    if ( (v37 || !v38) && (v38 || !v37) )
    {
      v39 = 0;
      if ( v37 )
      {
        v25 = GetProcessHeap();
        HeapFree(v25, 0, v18);
      }
    }
    return v16;
  }
  if ( (*a1)[3]((__int64)a1, (unsigned __int64 *)&v42) < 0 || (*a2)[3]((__int64)a2, (unsigned __int64 *)&v43) < 0 )
  {
    v26 = lpMem;
    if ( (lpMem || !v34) && (v34 || !lpMem) )
    {
      v35 = 0;
      if ( lpMem )
      {
        v28 = GetProcessHeap();
        HeapFree(v28, 0, v26);
        lpMem = 0;
        v34 = 0;
      }
    }
    v20 = v37;
    if ( !v37 && v38 )
      return 0x7FFFFFFF;
    if ( !v38 && v37 )
      return 0x7FFFFFFF;
    v39 = 0;
    if ( !v37 )
      return 0x7FFFFFFF;
    goto LABEL_86;
  }
  v8 = v42 <= v43;
  if ( v42 != v43 )
    goto LABEL_92;
  if ( v42 == 12 )
  {
    if ( (*a1)[4]((__int64)a1, &v30) < 0 || (*a2)[4]((__int64)a2, &v31) < 0 )
    {
      DefStringResult_Clear(&lpMem, 1);
      DefStringResult_Clear(&v37, 1);
      return 0x7FFFFFFF;
    }
    v8 = (__int64)v30 <= (__int64)v31;
    if ( v30 != v31 )
    {
LABEL_92:
      v29 = -1;
      if ( !v8 )
        v29 = 1;
      goto LABEL_94;
    }
  }
  if ( (*a1)[6]((__int64)a1, (unsigned __int64 *)&v41) < 0 || (*a2)[6]((__int64)a2, (unsigned __int64 *)&v40) < 0 )
    goto LABEL_88;
  if ( v41 )
  {
    if ( !v40 )
    {
      Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&p_lpMem);
      Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v36);
      return 0xFFFFFFFFLL;
    }
    if ( (*a1)[7]((__int64)a1, (unsigned __int64 *)&v36) >= 0
      && (*a2)[7]((__int64)a2, (unsigned __int64 *)&p_lpMem) >= 0 )
    {
      if ( p_lpMem && (*p_lpMem || !*((_DWORD *)p_lpMem + 2)) && (*((_DWORD *)p_lpMem + 2) || !*p_lpMem) )
        v9 = (const WCHAR *)p_lpMem[2];
      else
        v9 = 0;
      if ( v36 && (*v36 || !*((_DWORD *)v36 + 2)) && (*((_DWORD *)v36 + 2) || !*v36) )
        v10 = (const WCHAR *)v36[2];
      else
        v10 = 0;
      v11 = CompareStringOrdinal(v10, -1, v9, -1, 1) - 2;
      v12 = 0x7FFFFFFF;
      if ( v11 != 0x7FFFFFFF )
      {
        if ( v11 < 0 )
          v12 = -1;
        else
          v12 = v11 > 0;
      }
      v13 = lpMem;
      if ( (lpMem || !v34) && (v34 || !lpMem) )
      {
        v35 = 0;
        if ( lpMem )
        {
          v22 = GetProcessHeap();
          HeapFree(v22, 0, v13);
          lpMem = 0;
          v34 = 0;
        }
      }
      v14 = v37;
      if ( (v37 || !v38) && (v38 || !v37) )
      {
        v39 = 0;
        if ( v37 )
        {
          v23 = GetProcessHeap();
          HeapFree(v23, 0, v14);
        }
      }
      return v12;
    }
    v19 = lpMem;
    if ( (lpMem || !v34) && (v34 || !lpMem) )
    {
      v35 = 0;
      if ( lpMem )
      {
        v21 = GetProcessHeap();
        HeapFree(v21, 0, v19);
        lpMem = 0;
        v34 = 0;
      }
    }
    v20 = v37;
    if ( !v37 && v38 )
      return 0x7FFFFFFF;
    if ( !v38 && v37 )
      return 0x7FFFFFFF;
    v39 = 0;
    if ( !v37 )
      return 0x7FFFFFFF;
LABEL_86:
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v20);
    return 0x7FFFFFFF;
  }
  if ( v40 )
  {
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&p_lpMem);
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v36);
    return 1;
  }
  if ( (*a1)[8]((__int64)a1, &v30) < 0 || (*a2)[8]((__int64)a2, &v31) < 0 )
  {
LABEL_88:
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&p_lpMem);
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v36);
    return 0x7FFFFFFF;
  }
  if ( v30 != v31 )
  {
    v29 = -1;
    if ( v30 > v31 )
      v29 = 1;
LABEL_94:
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&p_lpMem);
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v36);
    return v29;
  }
  Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&p_lpMem);
  Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v36);
  return 0;
}

```

## disassembly

```asm
0x18002c9f0  mov     rax, rsp
0x18002c9f3  push    rbp
0x18002c9f4  push    rbx
0x18002c9f5  push    rdi
0x18002c9f6  lea     rbp, [rax-5Fh]
0x18002c9fa  sub     rsp, 90h
0x18002ca01  mov     rbx, rdx
0x18002ca04  mov     rdi, rcx
0x18002ca07  cmp     rcx, rdx
0x18002ca0a  jz      loc_18002CE52
0x18002ca10  mov     [rax-20h], rsi
0x18002ca14  mov     [rax-28h], r14
0x18002ca18  xor     r14d, r14d
0x18002ca1b  test    rdi, rdi
0x18002ca1e  mov     ecx, r14d
0x18002ca21  mov     eax, r14d
0x18002ca24  setz    cl
0x18002ca27  test    rdx, rdx
0x18002ca2a  setz    al
0x18002ca2d  cmp     ecx, eax
0x18002ca2f  jnz     loc_18002CF3D
0x18002ca35  lea     rax, [rbp+57h+var_38]
0x18002ca39  mov     [rbp+57h+var_70], r14
0x18002ca3d  mov     [rbp+57h+var_40], rax
0x18002ca41  lea     rdx, [rbp+57h+var_70]
0x18002ca45  lea     rax, [rbp+57h+lpMem]
0x18002ca49  mov     [rbp+57h+var_68], r14
0x18002ca4d  mov     [rbp+57h+var_60], rax
0x18002ca51  mov     rcx, rdi
0x18002ca54  mov     rax, [rdi]
0x18002ca57  mov     [rbp+57h+arg_10], r14d
0x18002ca5b  mov     [rbp+57h+arg_18], r14d
0x18002ca5f  mov     [rbp+57h+var_38], r14
0x18002ca63  mov     rax, [rax]
0x18002ca66  mov     [rbp+57h+var_30], r14d
0x18002ca6a  mov     [rbp+57h+var_28], r14
0x18002ca6e  mov     [rbp+57h+lpMem], r14
0x18002ca72  mov     [rbp+57h+var_50], r14d
0x18002ca76  mov     [rbp+57h+var_48], r14
0x18002ca7a  mov     [rbp+57h+arg_8], r14b
0x18002ca7e  mov     [rbp+57h+arg_0], r14b
0x18002ca82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca87  test    eax, eax
0x18002ca89  js      loc_18002CC70
0x18002ca8f  mov     rax, [rbx]
0x18002ca92  lea     rdx, [rbp+57h+var_68]
0x18002ca96  mov     rcx, rbx
0x18002ca99  mov     rax, [rax]
0x18002ca9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002caa1  test    eax, eax
0x18002caa3  js      loc_18002CC70
0x18002caa9  mov     rax, [rbp+57h+var_70]
0x18002caad  mov     rcx, [rbp+57h+var_68]
0x18002cab1  cmp     rax, rcx
0x18002cab4  jnz     loc_18002CC78
0x18002caba  mov     rax, [rdi]
0x18002cabd  lea     rdx, [rbp+57h+arg_10]
0x18002cac1  mov     rcx, rdi
0x18002cac4  mov     rax, [rax+18h]
0x18002cac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cacd  test    eax, eax
0x18002cacf  js      loc_18002CDE9
0x18002cad5  mov     rax, [rbx]
0x18002cad8  lea     rdx, [rbp+57h+arg_18]
0x18002cadc  mov     rcx, rbx
0x18002cadf  mov     rax, [rax+18h]
0x18002cae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cae8  test    eax, eax
0x18002caea  js      loc_18002CDE9
0x18002caf0  mov     eax, [rbp+57h+arg_10]
0x18002caf3  cmp     eax, [rbp+57h+arg_18]
0x18002caf6  jnz     loc_18002CEE7
0x18002cafc  cmp     eax, 0Ch
0x18002caff  jz      loc_18002CE99
0x18002cb05  mov     rax, [rdi]
0x18002cb08  lea     rdx, [rbp+57h+arg_8]
0x18002cb0c  mov     rcx, rdi
0x18002cb0f  mov     rax, [rax+30h]
0x18002cb13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb18  test    eax, eax
0x18002cb1a  js      loc_18002CE7D
0x18002cb20  mov     rax, [rbx]
0x18002cb23  lea     rdx, [rbp+57h+arg_0]
0x18002cb27  mov     rcx, rbx
0x18002cb2a  mov     rax, [rax+30h]
0x18002cb2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb33  test    eax, eax
0x18002cb35  js      loc_18002CE7D
0x18002cb3b  cmp     [rbp+57h+arg_8], r14b
0x18002cb3f  jz      loc_18002CF72
0x18002cb45  cmp     [rbp+57h+arg_0], r14b
0x18002cb49  jz      loc_18002CFAD
0x18002cb4f  mov     rax, [rdi]
0x18002cb52  lea     rdx, [rbp+57h+var_40]
0x18002cb56  mov     rcx, rdi
0x18002cb59  mov     rax, [rax+38h]
0x18002cb5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb62  test    eax, eax
0x18002cb64  js      loc_18002CCD8
0x18002cb6a  mov     rax, [rbx]
0x18002cb6d  lea     rdx, [rbp+57h+var_60]
0x18002cb71  mov     rcx, rbx
0x18002cb74  mov     rax, [rax+38h]
0x18002cb78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb7d  test    eax, eax
0x18002cb7f  js      loc_18002CCD8
0x18002cb85  mov     rax, [rbp+57h+var_60]
0x18002cb89  test    rax, rax
0x18002cb8c  jz      loc_18002CD47
0x18002cb92  mov     rdx, [rax]
0x18002cb95  test    rdx, rdx
0x18002cb98  jnz     short loc_18002CBA4
0x18002cb9a  cmp     [rax+8], r14d
0x18002cb9e  ja      loc_18002CD47
0x18002cba4  cmp     [rax+8], r14d
0x18002cba8  jnz     short loc_18002CBB3
0x18002cbaa  test    rdx, rdx
0x18002cbad  jnz     loc_18002CD47
0x18002cbb3  mov     r8, [rax+10h]; lpString2
0x18002cbb7  mov     rax, [rbp+57h+var_40]
0x18002cbbb  test    rax, rax
0x18002cbbe  jz      loc_18002CD4F
0x18002cbc4  mov     rdx, [rax]
0x18002cbc7  test    rdx, rdx
0x18002cbca  jnz     short loc_18002CBD6
0x18002cbcc  cmp     [rax+8], r14d
0x18002cbd0  ja      loc_18002CD4F
0x18002cbd6  cmp     [rax+8], r14d
0x18002cbda  jnz     short loc_18002CBE5
0x18002cbdc  test    rdx, rdx
0x18002cbdf  jnz     loc_18002CD4F
0x18002cbe5  mov     rcx, [rax+10h]; lpString1
0x18002cbe9  mov     esi, 0FFFFFFFFh
0x18002cbee  mov     dword ptr [rsp+20h], 1; bIgnoreCase
0x18002cbf6  mov     r9d, esi; cchCount2
0x18002cbf9  mov     edx, esi; cchCount1
0x18002cbfb  call    cs:__imp_CompareStringOrdinal
0x18002cc01  add     eax, 0FFFFFFFEh
0x18002cc04  mov     ebx, 7FFFFFFFh
0x18002cc09  cmp     eax, ebx
0x18002cc0b  jz      short loc_18002CC1D
0x18002cc0d  test    eax, eax
0x18002cc0f  js      loc_18002CD40
0x18002cc15  test    eax, eax
0x18002cc17  mov     ebx, r14d
0x18002cc1a  setnle  bl
0x18002cc1d  mov     rdi, [rbp+57h+lpMem]
0x18002cc21  mov     eax, [rbp+57h+var_50]
0x18002cc24  test    rdi, rdi
0x18002cc27  jnz     short loc_18002CC2D
0x18002cc29  test    eax, eax
0x18002cc2b  jnz     short loc_18002CC43
0x18002cc2d  test    eax, eax
0x18002cc2f  jnz     short loc_18002CC36
0x18002cc31  test    rdi, rdi
0x18002cc34  jnz     short loc_18002CC43
0x18002cc36  mov     [rbp+57h+var_48], r14
0x18002cc3a  test    rdi, rdi
0x18002cc3d  jnz     loc_18002CD75
0x18002cc43  mov     rdi, [rbp+57h+var_38]
0x18002cc47  mov     eax, [rbp+57h+var_30]
0x18002cc4a  test    rdi, rdi
0x18002cc4d  jnz     short loc_18002CC53
0x18002cc4f  test    eax, eax
0x18002cc51  jnz     short loc_18002CC69
0x18002cc53  test    eax, eax
0x18002cc55  jnz     short loc_18002CC5C
0x18002cc57  test    rdi, rdi
0x18002cc5a  jnz     short loc_18002CC69
0x18002cc5c  mov     [rbp+57h+var_28], r14
0x18002cc60  test    rdi, rdi
0x18002cc63  jnz     loc_18002CD96
0x18002cc69  mov     eax, ebx
0x18002cc6b  jmp     loc_18002CD25
0x18002cc70  mov     rax, [rbp+57h+var_70]
0x18002cc74  mov     rcx, [rbp+57h+var_68]
0x18002cc78  cmp     rax, rcx
0x18002cc7b  mov     ebx, 1
0x18002cc80  mov     eax, [rbp+57h+var_50]
0x18002cc83  mov     esi, 0FFFFFFFFh
0x18002cc88  cmovg   esi, ebx
0x18002cc8b  mov     rbx, [rbp+57h+lpMem]
0x18002cc8f  test    rbx, rbx
0x18002cc92  jnz     short loc_18002CC98
0x18002cc94  test    eax, eax
0x18002cc96  jnz     short loc_18002CCAE
0x18002cc98  test    eax, eax
0x18002cc9a  jnz     short loc_18002CCA1
0x18002cc9c  test    rbx, rbx
0x18002cc9f  jnz     short loc_18002CCAE
0x18002cca1  mov     [rbp+57h+var_48], r14
0x18002cca5  test    rbx, rbx
0x18002cca8  jnz     loc_18002CDAF
0x18002ccae  mov     rbx, [rbp+57h+var_38]
0x18002ccb2  mov     eax, [rbp+57h+var_30]
0x18002ccb5  test    rbx, rbx
0x18002ccb8  jnz     short loc_18002CCBE
0x18002ccba  test    eax, eax
0x18002ccbc  jnz     short loc_18002CCD4
0x18002ccbe  test    eax, eax
0x18002ccc0  jnz     short loc_18002CCC7
0x18002ccc2  test    rbx, rbx
0x18002ccc5  jnz     short loc_18002CCD4
0x18002ccc7  mov     [rbp+57h+var_28], r14
0x18002cccb  test    rbx, rbx
0x18002ccce  jnz     loc_18002CDD0
0x18002ccd4  mov     eax, esi
0x18002ccd6  jmp     short loc_18002CD25
0x18002ccd8  mov     rbx, [rbp+57h+lpMem]
0x18002ccdc  mov     eax, [rbp+57h+var_50]
0x18002ccdf  test    rbx, rbx
0x18002cce2  jnz     short loc_18002CCE8
0x18002cce4  test    eax, eax
0x18002cce6  jnz     short loc_18002CCFA
0x18002cce8  test    eax, eax
0x18002ccea  jnz     short loc_18002CCF1
0x18002ccec  test    rbx, rbx
0x18002ccef  jnz     short loc_18002CCFA
0x18002ccf1  mov     [rbp+57h+var_48], r14
0x18002ccf5  test    rbx, rbx
0x18002ccf8  jnz     short loc_18002CD57
0x18002ccfa  mov     rbx, [rbp+57h+var_38]
0x18002ccfe  mov     eax, [rbp+57h+var_30]
0x18002cd01  test    rbx, rbx
0x18002cd04  jnz     short loc_18002CD0A
0x18002cd06  test    eax, eax
0x18002cd08  jnz     short loc_18002CD20
0x18002cd0a  test    eax, eax
0x18002cd0c  jnz     short loc_18002CD13
0x18002cd0e  test    rbx, rbx
0x18002cd11  jnz     short loc_18002CD20
0x18002cd13  mov     [rbp+57h+var_28], r14
0x18002cd17  test    rbx, rbx
0x18002cd1a  jnz     loc_18002CE39
0x18002cd20  mov     eax, 7FFFFFFFh
0x18002cd25  mov     rsi, [rsp+88h]
0x18002cd2d  mov     r14, [rsp+0A0h+var_20]
0x18002cd35  add     rsp, 90h
0x18002cd3c  pop     rdi
0x18002cd3d  pop     rbx
0x18002cd3e  pop     rbp
0x18002cd3f  retn
0x18002cd40  mov     ebx, esi
0x18002cd42  jmp     loc_18002CC1D
0x18002cd47  mov     r8, r14
0x18002cd4a  jmp     loc_18002CBB7
0x18002cd4f  mov     rcx, r14
0x18002cd52  jmp     loc_18002CBE9
0x18002cd57  call    cs:__imp_GetProcessHeap
0x18002cd5d  mov     r8, rbx; lpMem
0x18002cd60  xor     edx, edx; dwFlags
0x18002cd62  mov     rcx, rax; hHeap
0x18002cd65  call    cs:__imp_HeapFree
0x18002cd6b  mov     [rbp+57h+lpMem], r14
0x18002cd6f  mov     [rbp+57h+var_50], r14d
0x18002cd73  jmp     short loc_18002CCFA
0x18002cd75  call    cs:__imp_GetProcessHeap
0x18002cd7b  mov     r8, rdi; lpMem
0x18002cd7e  xor     edx, edx; dwFlags
0x18002cd80  mov     rcx, rax; hHeap
0x18002cd83  call    cs:__imp_HeapFree
0x18002cd89  mov     [rbp+57h+lpMem], r14
0x18002cd8d  mov     [rbp+57h+var_50], r14d
0x18002cd91  jmp     loc_18002CC43
0x18002cd96  call    cs:__imp_GetProcessHeap
0x18002cd9c  mov     r8, rdi; lpMem
0x18002cd9f  xor     edx, edx; dwFlags
0x18002cda1  mov     rcx, rax; hHeap
0x18002cda4  call    cs:__imp_HeapFree
0x18002cdaa  jmp     loc_18002CC69
0x18002cdaf  call    cs:__imp_GetProcessHeap
0x18002cdb5  mov     r8, rbx; lpMem
0x18002cdb8  xor     edx, edx; dwFlags
0x18002cdba  mov     rcx, rax; hHeap
0x18002cdbd  call    cs:__imp_HeapFree
0x18002cdc3  mov     [rbp+57h+lpMem], r14
0x18002cdc7  mov     [rbp+57h+var_50], r14d
0x18002cdcb  jmp     loc_18002CCAE
0x18002cdd0  call    cs:__imp_GetProcessHeap
0x18002cdd6  mov     r8, rbx; lpMem
0x18002cdd9  xor     edx, edx; dwFlags
0x18002cddb  mov     rcx, rax; hHeap
0x18002cdde  call    cs:__imp_HeapFree
0x18002cde4  jmp     loc_18002CCD4
0x18002cde9  mov     rbx, [rbp+57h+lpMem]
0x18002cded  mov     eax, [rbp+57h+var_50]
0x18002cdf0  test    rbx, rbx
0x18002cdf3  jnz     short loc_18002CDF9
0x18002cdf5  test    eax, eax
0x18002cdf7  jnz     short loc_18002CE0B
0x18002cdf9  test    eax, eax
0x18002cdfb  jnz     short loc_18002CE02
0x18002cdfd  test    rbx, rbx
0x18002ce00  jnz     short loc_18002CE0B
0x18002ce02  mov     [rbp+57h+var_48], r14
0x18002ce06  test    rbx, rbx
0x18002ce09  jnz     short loc_18002CE5F
0x18002ce0b  mov     rbx, [rbp+57h+var_38]
0x18002ce0f  mov     eax, [rbp+57h+var_30]
0x18002ce12  test    rbx, rbx
  ... truncated ...
```
