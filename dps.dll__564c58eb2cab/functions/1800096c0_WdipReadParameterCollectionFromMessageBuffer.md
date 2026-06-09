# WdipReadParameterCollectionFromMessageBuffer

- ea: `0x1800096c0`
- end: `0x1800099b5`
- name: `WdipReadParameterCollectionFromMessageBuffer`
- size: `757`
- prototype: `__int64 __fastcall(__int64, unsigned __int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002510`
- `0x18000b6d8`
- `0x18000c21c`

## callees

- `0x1800013a0`
- `0x180009090`
- `0x1800096c0`
- `0x18000a856`
- `0x180017d7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009873`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000988f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800098ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800098d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009911`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000992d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009948`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009966`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009873`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000988f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800098ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800098d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009911`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000992d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009948`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009966`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009865`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009881`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000989d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800098c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009903`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000991f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000993a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009958`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009865`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009881`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000989d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800098c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009903`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000991f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000993a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009958`

## string_xrefs

- `0x180009712`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x18000998a`: `clientcore\base\diagnosis\pdi\wdi\framework\common\params.cpp`
- `0x18000970b`: `WdipReadParameterCollectionFromMessageBuffer`
- `0x180009983`: `WdipReadParameterCollectionFromMessageBuffer`

## pseudocode

```c
__int64 __fastcall WdipReadParameterCollectionFromMessageBuffer(__int64 a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int8 *v5; // rcx
  unsigned int v7; // edi
  unsigned int v8; // r14d
  bool v9; // zf
  unsigned __int8 *v10; // rcx
  int v11; // r8d
  int v12; // r13d
  SIZE_T v13; // rcx
  size_t v14; // rbx
  _QWORD *v15; // rax
  _QWORD *v16; // r12
  __int64 v17; // rbx
  struct __WDIP_PARAMETER *v18; // rax
  __int64 v19; // rbp
  __int64 v20; // rax
  __int64 v21; // r15
  void **v22; // r13
  void *v23; // rbx
  HANDLE ProcessHeap; // rax
  void *v25; // rbx
  HANDLE v26; // rax
  void *v27; // rbx
  HANDLE v28; // rax
  void *v29; // rbx
  HANDLE v30; // rax
  unsigned int i; // esi
  __int64 v32; // rbp
  void **v33; // r15
  void *v34; // rbx
  HANDLE v35; // rax
  void *v36; // rbx
  HANDLE v37; // rax
  void *v38; // rbx
  HANDLE v39; // rax
  HANDLE v40; // rax
  int v42; // [rsp+70h] [rbp+8h]
  unsigned __int8 *v43; // [rsp+78h] [rbp+10h] BYREF

  v5 = (unsigned __int8 *)(*(unsigned int *)(a2 + 124) + a2 + 40);
  v43 = v5;
  if ( !a1 )
  {
    v7 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipReadParameterCollectionFromMessageBuffer",
      347,
      (int)L"Error = %d",
      87);
    return v7;
  }
  if ( !v5 || (unsigned __int64)v5 < a2 || (unsigned __int64)&v5[-a2] > a3 || a3 + a2 - (_QWORD)v5 < 4 )
  {
    v11 = 354;
    goto LABEL_35;
  }
  v8 = *(_DWORD *)v5;
  v9 = v5 + 4 == 0;
  v10 = v5 + 4;
  v43 = v10;
  if ( v9 || (unsigned __int64)v10 < a2 || (unsigned __int64)&v10[-a2] > a3 || a3 + a2 - (_QWORD)v10 < 4 )
  {
    v11 = 365;
LABEL_35:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipReadParameterCollectionFromMessageBuffer",
      v11,
      (int)L"Error = %d",
      111);
    return (unsigned int)-2147024362;
  }
  v12 = *(_DWORD *)v10;
  v7 = 0;
  v42 = *(_DWORD *)v10;
  v43 = v10 + 4;
  if ( !v8 )
  {
    *(_DWORD *)(a1 + 4) = 0;
    *(_DWORD *)a1 = v12;
    return v7;
  }
  v13 = 8 * v8;
  if ( v8 != (v8 & 0x1FFFFFFF) )
    return (unsigned int)-2147024362;
  v14 = (unsigned int)v13;
  v15 = WdipAlloc(v13);
  v16 = v15;
  if ( v15 )
  {
    memset_0(v15, 0, v14);
    v17 = 0;
    while ( 1 )
    {
      v18 = WdipReadParameterFromMessageBuffer((struct _DPS_MESSAGE *)a2, a3, &v43);
      v16[v17] = v18;
      if ( !v18 )
        break;
      v17 = (unsigned int)(v17 + 1);
      if ( (unsigned int)v17 >= v8 )
      {
        if ( *(_QWORD *)(a1 + 8) )
        {
          v19 = 0;
          if ( *(_DWORD *)(a1 + 4) )
          {
            do
            {
              v20 = *(_QWORD *)(a1 + 8);
              v21 = *(_QWORD *)(v20 + 8 * v19);
              v22 = (void **)(v20 + 8 * v19);
              if ( v21 )
              {
                v23 = *(void **)(v21 + 48);
                ProcessHeap = GetProcessHeap();
                HeapFree(ProcessHeap, 0, v23);
                v25 = *(void **)(v21 + 56);
                *(_QWORD *)(v21 + 48) = 0;
                v26 = GetProcessHeap();
                HeapFree(v26, 0, v25);
                *(_QWORD *)(v21 + 56) = 0;
                v27 = *v22;
                v28 = GetProcessHeap();
                HeapFree(v28, 0, v27);
                *v22 = 0;
              }
              v19 = (unsigned int)(v19 + 1);
            }
            while ( (unsigned int)v19 < *(_DWORD *)(a1 + 4) );
            v12 = v42;
          }
          v29 = *(void **)(a1 + 8);
          v30 = GetProcessHeap();
          HeapFree(v30, 0, v29);
        }
        *(_QWORD *)(a1 + 8) = v16;
        *(_DWORD *)(a1 + 4) = v8;
        *(_DWORD *)a1 = v12;
        return v7;
      }
    }
    for ( i = 0; i < v8; ++i )
    {
      v32 = v16[i];
      v33 = (void **)&v16[i];
      if ( v32 )
      {
        v34 = *(void **)(v32 + 48);
        v35 = GetProcessHeap();
        HeapFree(v35, 0, v34);
        v36 = *(void **)(v32 + 56);
        *(_QWORD *)(v32 + 48) = 0;
        v37 = GetProcessHeap();
        HeapFree(v37, 0, v36);
        *(_QWORD *)(v32 + 56) = 0;
        v38 = *v33;
        v39 = GetProcessHeap();
        HeapFree(v39, 0, v38);
        *v33 = 0;
      }
    }
    v40 = GetProcessHeap();
    HeapFree(v40, 0, v16);
  }
  else
  {
    v7 = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\params.cpp",
      (int)L"WdipReadParameterCollectionFromMessageBuffer",
      386,
      (int)L"Error = %d",
      14);
  }
  return v7;
}

```

## disassembly

```asm
0x1800096c0  mov     [rsp+arg_10], rbx
0x1800096c5  push    rbp
0x1800096c6  push    rsi
0x1800096c7  push    rdi
0x1800096c8  push    r12
0x1800096ca  push    r13
0x1800096cc  push    r14
0x1800096ce  push    r15
0x1800096d0  sub     rsp, 30h
0x1800096d4  mov     eax, [rdx+7Ch]
0x1800096d7  mov     rsi, rcx
0x1800096da  lea     rcx, [rdx+28h]
0x1800096de  mov     r15, r8
0x1800096e1  add     rcx, rax
0x1800096e4  mov     rbp, rdx
0x1800096e7  mov     [rsp+68h+arg_8], rcx
0x1800096ec  test    rsi, rsi
0x1800096ef  jnz     short loc_180009723
0x1800096f1  mov     edi, 80070057h
0x1800096f6  mov     dword ptr [rsp+68h+Args], 57h ; 'W'; Args
0x1800096fe  mov     r8d, 15Bh; int
0x180009704  lea     r9, aErrorD; "Error = %d"
0x18000970b  lea     rdx, aWdipreadparame_2; "WdipReadParameterCollectionFromMessageB"...
0x180009712  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180009719  call    WdipTraceError
0x18000971e  jmp     loc_18000999B
0x180009723  test    rcx, rcx
0x180009726  jz      loc_18000996E
0x18000972c  cmp     rcx, rbp
0x18000972f  jb      loc_18000996E
0x180009735  mov     rax, rcx
0x180009738  sub     rax, rbp
0x18000973b  cmp     rax, r15
0x18000973e  ja      loc_18000996E
0x180009744  mov     rax, rbp
0x180009747  sub     rax, rcx
0x18000974a  add     rax, r15
0x18000974d  cmp     rax, 4
0x180009751  jb      loc_18000996E
0x180009757  mov     r14d, [rcx]
0x18000975a  add     rcx, 4
0x18000975e  mov     [rsp+68h+arg_8], rcx
0x180009763  jz      short loc_180009775
0x180009765  cmp     rcx, rbp
0x180009768  jb      short loc_180009775
0x18000976a  mov     rax, rcx
0x18000976d  sub     rax, rbp
0x180009770  cmp     rax, r15
0x180009773  jbe     short loc_180009780
0x180009775  mov     r8d, 16Dh
0x18000977b  jmp     loc_180009974
0x180009780  mov     rax, rbp
0x180009783  sub     rax, rcx
0x180009786  add     rax, r15
0x180009789  cmp     rax, 4
0x18000978d  jb      short loc_180009775
0x18000978f  mov     r13d, [rcx]
0x180009792  lea     rax, [rcx+4]
0x180009796  xor     edi, edi
0x180009798  mov     [rsp+68h+arg_0], r13d
0x18000979d  mov     [rsp+68h+arg_8], rax
0x1800097a2  test    r14d, r14d
0x1800097a5  jnz     short loc_1800097B2
0x1800097a7  mov     [rsi+4], edi
0x1800097aa  mov     [rsi], r13d
0x1800097ad  jmp     loc_18000999B
0x1800097b2  lea     ecx, ds:0[r14*8]
0x1800097ba  mov     eax, ecx
0x1800097bc  shr     eax, 3
0x1800097bf  cmp     r14d, eax
0x1800097c2  jnz     loc_180009996
0x1800097c8  mov     ebx, ecx
0x1800097ca  call    WdipAlloc
0x1800097cf  mov     r12, rax
0x1800097d2  test    rax, rax
0x1800097d5  jnz     short loc_1800097EF
0x1800097d7  mov     edi, 8007000Eh
0x1800097dc  mov     dword ptr [rsp+68h+Args], 0Eh
0x1800097e4  mov     r8d, 182h
0x1800097ea  jmp     loc_180009704
0x1800097ef  mov     r8, rbx; Size
0x1800097f2  xor     edx, edx; Val
0x1800097f4  mov     rcx, r12; void *
0x1800097f7  call    memset_0
0x1800097fc  xor     ebx, ebx
0x1800097fe  test    r14d, r14d
0x180009801  jz      short loc_180009834
0x180009803  nop     dword ptr [rax+00h]
0x180009807  nop     word ptr [rax+rax+00000000h]
0x180009810  lea     r8, [rsp+68h+arg_8]; unsigned __int8 **
0x180009815  mov     rdx, r15; unsigned __int64
0x180009818  mov     rcx, rbp; struct _DPS_MESSAGE *
0x18000981b  call    ?WdipReadParameterFromMessageBuffer@@YAPEAU__WDIP_PARAMETER@@PEAU_DPS_MESSAGE@@_KPEAPEAE@Z; WdipReadParameterFromMessageBuffer(_DPS_MESSAGE *,unsigned __int64,uchar * *)
0x180009820  mov     [r12+rbx*8], rax
0x180009824  test    rax, rax
0x180009827  jz      loc_1800098E9
0x18000982d  inc     ebx
0x18000982f  cmp     ebx, r14d
0x180009832  jb      short loc_180009810
0x180009834  cmp     [rsi+8], rdi
0x180009838  jz      loc_1800098D9
0x18000983e  xor     ebp, ebp
0x180009840  cmp     [rsi+4], edi
0x180009843  jbe     short loc_1800098C1
0x180009845  nop     word ptr [rax+rax+00000000h]
0x180009850  mov     rax, [rsi+8]
0x180009854  mov     r15, [rax+rbp*8]
0x180009858  lea     r13, [rax+rbp*8]
0x18000985c  test    r15, r15
0x18000985f  jz      short loc_1800098B5
0x180009861  mov     rbx, [r15+30h]
0x180009865  call    cs:__imp_GetProcessHeap
0x18000986b  mov     r8, rbx; lpMem
0x18000986e  xor     edx, edx; dwFlags
0x180009870  mov     rcx, rax; hHeap
0x180009873  call    cs:__imp_HeapFree
0x180009879  mov     rbx, [r15+38h]
0x18000987d  mov     [r15+30h], rdi
0x180009881  call    cs:__imp_GetProcessHeap
0x180009887  mov     r8, rbx; lpMem
0x18000988a  xor     edx, edx; dwFlags
0x18000988c  mov     rcx, rax; hHeap
0x18000988f  call    cs:__imp_HeapFree
0x180009895  mov     [r15+38h], rdi
0x180009899  mov     rbx, [r13+0]
0x18000989d  call    cs:__imp_GetProcessHeap
0x1800098a3  mov     r8, rbx; lpMem
0x1800098a6  xor     edx, edx; dwFlags
0x1800098a8  mov     rcx, rax; hHeap
0x1800098ab  call    cs:__imp_HeapFree
0x1800098b1  mov     [r13+0], rdi
0x1800098b5  inc     ebp
0x1800098b7  cmp     ebp, [rsi+4]
0x1800098ba  jb      short loc_180009850
0x1800098bc  mov     r13d, [rsp+68h+arg_0]
0x1800098c1  mov     rbx, [rsi+8]
0x1800098c5  call    cs:__imp_GetProcessHeap
0x1800098cb  mov     r8, rbx; lpMem
0x1800098ce  xor     edx, edx; dwFlags
0x1800098d0  mov     rcx, rax; hHeap
0x1800098d3  call    cs:__imp_HeapFree
0x1800098d9  mov     [rsi+8], r12
0x1800098dd  mov     [rsi+4], r14d
0x1800098e1  mov     [rsi], r13d
0x1800098e4  jmp     loc_18000999B
0x1800098e9  xor     r13d, r13d
0x1800098ec  mov     esi, r13d
0x1800098ef  nop
0x1800098f0  mov     eax, esi
0x1800098f2  mov     rbp, [r12+rax*8]
0x1800098f6  lea     r15, [r12+rax*8]
0x1800098fa  test    rbp, rbp
0x1800098fd  jz      short loc_180009951
0x1800098ff  mov     rbx, [rbp+30h]
0x180009903  call    cs:__imp_GetProcessHeap
0x180009909  mov     r8, rbx; lpMem
0x18000990c  xor     edx, edx; dwFlags
0x18000990e  mov     rcx, rax; hHeap
0x180009911  call    cs:__imp_HeapFree
0x180009917  mov     rbx, [rbp+38h]
0x18000991b  mov     [rbp+30h], r13
0x18000991f  call    cs:__imp_GetProcessHeap
0x180009925  mov     r8, rbx; lpMem
0x180009928  xor     edx, edx; dwFlags
0x18000992a  mov     rcx, rax; hHeap
0x18000992d  call    cs:__imp_HeapFree
0x180009933  mov     [rbp+38h], r13
0x180009937  mov     rbx, [r15]
0x18000993a  call    cs:__imp_GetProcessHeap
0x180009940  mov     r8, rbx; lpMem
0x180009943  xor     edx, edx; dwFlags
0x180009945  mov     rcx, rax; hHeap
0x180009948  call    cs:__imp_HeapFree
0x18000994e  mov     [r15], r13
0x180009951  inc     esi
0x180009953  cmp     esi, r14d
0x180009956  jb      short loc_1800098F0
0x180009958  call    cs:__imp_GetProcessHeap
0x18000995e  mov     r8, r12; lpMem
0x180009961  xor     edx, edx; dwFlags
0x180009963  mov     rcx, rax; hHeap
0x180009966  call    cs:__imp_HeapFree
0x18000996c  jmp     short loc_18000999B
0x18000996e  mov     r8d, 162h; int
0x180009974  lea     r9, aErrorD; "Error = %d"
0x18000997b  mov     dword ptr [rsp+68h+Args], 6Fh ; 'o'; Args
0x180009983  lea     rdx, aWdipreadparame_2; "WdipReadParameterCollectionFromMessageB"...
0x18000998a  lea     rcx, aClientcoreBase_9; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180009991  call    WdipTraceError
0x180009996  mov     edi, 80070216h
0x18000999b  mov     rbx, [rsp+68h+arg_10]
0x1800099a3  mov     eax, edi
0x1800099a5  add     rsp, 30h
0x1800099a9  pop     r15
0x1800099ab  pop     r14
0x1800099ad  pop     r13
0x1800099af  pop     r12
0x1800099b1  pop     rdi
0x1800099b2  pop     rsi
0x1800099b3  pop     rbp
0x1800099b4  retn
```
