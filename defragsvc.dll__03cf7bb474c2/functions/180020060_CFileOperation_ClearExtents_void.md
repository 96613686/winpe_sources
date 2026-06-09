# CFileOperation::ClearExtents(void)

- ea: `0x180020060`
- end: `0x1800205a9`
- name: `?ClearExtents@CFileOperation@@UEAAJXZ`
- size: `1353`
- prototype: `__int64 __fastcall(CFileOperation *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x180020060`
- `0x180038c3c`
- `0x180046494`
- `0x18004a92c`

## import_xrefs

- `ntdll!RtlClearBits` at `0x1800202b0`
- `ntdll!RtlClearBits` at `0x180020334`
- `ntdll!RtlClearBits` at `0x1800202b0`
- `ntdll!RtlClearBits` at `0x180020334`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x1800200d1`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x1800200d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002035e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002036f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002037f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800203e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800203f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020409`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002035e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002036f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002037f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800203e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800203f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180020409`

## pseudocode

```c
__int64 __fastcall CFileOperation::ClearExtents(CFileOperation *this)
{
  int ThreadContextRetail; // eax
  CSxGlobalTracer *v3; // rcx
  unsigned int v4; // esi
  int v5; // ecx
  int v6; // eax
  __int16 i; // cx
  __int64 v8; // rdx
  unsigned int v9; // r13d
  unsigned int v10; // r9d
  __int64 v11; // rsi
  __int64 *v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned int v15; // r15d
  __int64 v16; // rbx
  int v17; // eax
  unsigned int v18; // edx
  ULONG v19; // r9d
  __int64 v20; // r15
  __int64 v21; // r12
  __int64 *v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r15
  __int64 v25; // rdi
  bool v26; // zf
  __int64 v27; // rdi
  int v28; // ecx
  unsigned int v29; // ebx
  __int64 v31; // rdx
  __int16 v32; // ax
  int v33; // [rsp+20h] [rbp-40h] BYREF
  __int64 v34; // [rsp+24h] [rbp-3Ch]
  __int16 v35; // [rsp+2Ch] [rbp-34h]
  const char *v36; // [rsp+30h] [rbp-30h]
  __int128 v37; // [rsp+38h] [rbp-28h] BYREF
  __int64 v38; // [rsp+48h] [rbp-18h]
  int v39; // [rsp+50h] [rbp-10h]
  ULONG StartingIndex; // [rsp+A0h] [rbp+40h]
  __int64 v41; // [rsp+B0h] [rbp+50h]

  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_7d91fd3008b83281181ea730215a620a_Traceguids);
  }
  v33 = 0;
  v34 = 579;
  v35 = 1;
  v36 = "CFileOperation::ClearExtents";
  v37 = 0;
  v38 = 0;
  v39 = 0;
  ThreadContextRetail = SxTracerGetThreadContextRetail((char *)&v37 + 8);
  if ( ThreadContextRetail >= 0 )
  {
    *(_QWORD *)&v37 = *(_QWORD *)(*((_QWORD *)&v37 + 1) + 32LL);
    *(_QWORD *)(*((_QWORD *)&v37 + 1) + 32LL) = &v33;
LABEL_6:
    v3 = WPP_GLOBAL_Control;
    goto LABEL_7;
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids,
      (unsigned int)ThreadContextRetail);
    goto LABEL_6;
  }
LABEL_7:
  if ( v35 )
  {
    if ( v35 == 1 )
    {
      if ( v3 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v3 + 7) & 0x20000000) == 0 )
        goto LABEL_11;
      v31 = 12;
    }
    else
    {
      if ( v3 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v3 + 7) & 0x20000) == 0 )
        goto LABEL_11;
      v31 = 13;
    }
  }
  else
  {
    if ( v3 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v3 + 7) & 0x8000000) == 0 )
      goto LABEL_11;
    v31 = 11;
  }
  WPP_SF_s(*((_QWORD *)v3 + 2), v31, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids, v36);
LABEL_11:
  v4 = **((_DWORD **)this + 6);
  v5 = *(_DWORD *)(*((_QWORD *)this + 5) + 28LL);
  if ( !v5 )
  {
    v29 = -2147467259;
    v33 = -2147467259;
    WORD1(v34) = 592;
    goto LABEL_53;
  }
  if ( (v4 & 0xF0000000) != v5 || (v6 = 1, !v4) )
    v6 = 0;
  for ( i = 592; ; i = 619 )
  {
    LOWORD(v34) = i;
    v33 = 0;
    if ( !v4 || !v6 )
    {
      **((_DWORD **)this + 6) = 0;
      *(_QWORD *)(*((_QWORD *)this + 6) + 8LL) = 0;
      v29 = v33;
      goto LABEL_53;
    }
    v8 = *((_QWORD *)this + 5);
    if ( !*(_DWORD *)(v8 + 28) )
    {
      v29 = -2147467259;
      goto LABEL_58;
    }
    v9 = v4 & 0xF0000000;
    if ( (v4 & 0xF0000000) != *(_DWORD *)(v8 + 28)
      || (v10 = (unsigned __int16)v4 != 0 ? (unsigned __int16)v4 - 1 : 0,
          StartingIndex = v10,
          v11 = HIWORD(v4) & 0xFFF,
          v41 = (unsigned int)v11,
          (v12 = *(__int64 **)(*(_QWORD *)(v8 + 8) + 8 * v11)) == 0)
      || v10 >= *(_DWORD *)(v8 + 20) )
    {
      v29 = -2147024809;
LABEL_58:
      v33 = v29;
      WORD1(v34) = 600;
      goto LABEL_53;
    }
    v13 = *(_QWORD *)(v8 + 32) * v10;
    v14 = *v12;
    v33 = 0;
    LOWORD(v34) = 600;
    v4 = *(_DWORD *)(v13 + v14 + 20);
    v15 = *(_DWORD *)(v13 + v14 + 16);
LABEL_22:
    v16 = *((_QWORD *)this + 5);
    v17 = *(_DWORD *)(v16 + 28);
    if ( v15 )
      break;
    if ( !v17 )
    {
      v29 = -2147467259;
      goto LABEL_83;
    }
    if ( v9 != v17 || (v27 = *(_QWORD *)(*(_QWORD *)(v16 + 8) + 8 * v41)) == 0 || StartingIndex >= *(_DWORD *)(v16 + 20) )
    {
      v29 = -2147024809;
LABEL_83:
      v32 = 615;
      goto LABEL_65;
    }
    RtlClearBits((PRTL_BITMAP)(v27 + 16), StartingIndex, 1u);
    if ( *(_DWORD *)(v27 + 32) == *(_DWORD *)(v16 + 20) )
      ++*(_DWORD *)(v16 + 24);
    v26 = (*(_DWORD *)(v27 + 32))-- == 1;
    if ( v26 && *(_DWORD *)(v16 + 24) > 1u )
    {
      CoTaskMemFree(*(LPVOID *)(v27 + 8));
      *(_QWORD *)(v27 + 8) = 0;
      CoTaskMemFree(*(LPVOID *)v27);
      *(_QWORD *)v27 = 0;
      CoTaskMemFree((LPVOID)v27);
      *(_QWORD *)(*(_QWORD *)(v16 + 8) + 8 * v41) = 0;
      --*(_DWORD *)(v16 + 24);
    }
    else if ( (unsigned int)v41 < *(_DWORD *)(v16 + 16) )
    {
      *(_DWORD *)(v16 + 16) = v41;
    }
    v33 = 0;
    LOWORD(v34) = 615;
    v28 = *(_DWORD *)(*((_QWORD *)this + 5) + 28LL);
    if ( !v28 )
    {
      v29 = -2147467259;
      v32 = 619;
      goto LABEL_65;
    }
    if ( (v4 & 0xF0000000) == v28 )
    {
      v6 = 1;
      if ( v4 )
        continue;
    }
    v6 = 0;
  }
  if ( !v17 )
  {
    v29 = -2147467259;
LABEL_64:
    v32 = 607;
LABEL_65:
    v33 = v29;
    WORD1(v34) = v32;
    goto LABEL_53;
  }
  v18 = v15 & 0xF0000000;
  if ( (v15 & 0xF0000000) != v17
    || (v19 = (unsigned __int16)v15 != 0 ? (unsigned __int16)v15 - 1 : 0,
        v20 = HIWORD(v15) & 0xFFF,
        v21 = (unsigned int)v20,
        (v22 = *(__int64 **)(*(_QWORD *)(v16 + 8) + 8 * v20)) == 0)
    || v19 >= *(_DWORD *)(v16 + 20) )
  {
    v29 = -2147024809;
    goto LABEL_64;
  }
  v23 = *(_QWORD *)(v16 + 32);
  v24 = *v22;
  v33 = 0;
  LOWORD(v34) = 607;
  if ( *(_DWORD *)(v16 + 28) )
  {
    if ( v18 != *(_DWORD *)(v16 + 28)
      || (v25 = *(_QWORD *)(*(_QWORD *)(v16 + 8) + 8 * v21)) == 0
      || v19 >= *(_DWORD *)(v16 + 20) )
    {
      v29 = -2147024809;
      goto LABEL_78;
    }
    v15 = *(_DWORD *)(v23 * v19 + v24 + 20);
    RtlClearBits((PRTL_BITMAP)(v25 + 16), v19, 1u);
    if ( *(_DWORD *)(v25 + 32) == *(_DWORD *)(v16 + 20) )
      ++*(_DWORD *)(v16 + 24);
    v26 = (*(_DWORD *)(v25 + 32))-- == 1;
    if ( v26 && *(_DWORD *)(v16 + 24) > 1u )
    {
      CoTaskMemFree(*(LPVOID *)(v25 + 8));
      *(_QWORD *)(v25 + 8) = 0;
      CoTaskMemFree(*(LPVOID *)v25);
      *(_QWORD *)v25 = 0;
      CoTaskMemFree((LPVOID)v25);
      *(_QWORD *)(*(_QWORD *)(v16 + 8) + 8 * v21) = 0;
      --*(_DWORD *)(v16 + 24);
    }
    else if ( (unsigned int)v21 < *(_DWORD *)(v16 + 16) )
    {
      *(_DWORD *)(v16 + 16) = v21;
    }
    v33 = 0;
    LOWORD(v34) = 611;
    goto LABEL_22;
  }
  v29 = -2147467259;
LABEL_78:
  v33 = v29;
  WORD1(v34) = 611;
LABEL_53:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v33);
  return v29;
}

```

## disassembly

```asm
0x180020060  mov     [rsp-38h+arg_18], rbx
0x180020065  push    rbp
0x180020066  push    rsi
0x180020067  push    rdi
0x180020068  push    r12
0x18002006a  push    r13
0x18002006c  push    r14
0x18002006e  push    r15
0x180020070  mov     rbp, rsp
0x180020073  sub     rsp, 60h
0x180020077  mov     r14, rcx
0x18002007a  lea     rbx, WPP_GLOBAL_Control
0x180020081  mov     r12d, 20000000h
0x180020087  mov     rcx, cs:WPP_GLOBAL_Control
0x18002008e  cmp     rcx, rbx
0x180020091  jz      short loc_18002009D
0x180020093  test    [rcx+1Ch], r12d
0x180020097  jnz     loc_1800204BB
0x18002009d  xor     edi, edi
0x18002009f  mov     [rbp+var_40], edi
0x1800200a2  mov     [rbp+var_3C], 243h
0x1800200aa  lea     r15d, [rdi+1]
0x1800200ae  mov     [rbp+var_34], r15w
0x1800200b3  lea     rax, aCfileoperation_19; "CFileOperation::ClearExtents"
0x1800200ba  mov     [rbp+var_30], rax
0x1800200be  xorps   xmm0, xmm0
0x1800200c1  movdqu  [rbp+var_28], xmm0
0x1800200c6  mov     [rbp+var_18], rdi
0x1800200ca  mov     [rbp+var_10], edi
0x1800200cd  lea     rcx, [rbp+var_28+8]
0x1800200d1  call    cs:__imp_SxTracerGetThreadContextRetail
0x1800200d7  lea     rsi, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x1800200de  test    eax, eax
0x1800200e0  js      loc_1800204D5
0x1800200e6  mov     rcx, qword ptr [rbp+var_28+8]
0x1800200ea  mov     rax, [rcx+20h]
0x1800200ee  mov     qword ptr [rbp+var_28], rax
0x1800200f2  lea     rax, [rbp+var_40]
0x1800200f6  mov     [rcx+20h], rax
0x1800200fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180020101  movzx   eax, [rbp+var_34]
0x180020105  test    ax, ax
0x180020108  jz      loc_180020508
0x18002010e  cmp     ax, r15w
0x180020112  jnz     loc_180020475
0x180020118  cmp     rcx, rbx
0x18002011b  jz      short loc_180020127
0x18002011d  test    [rcx+1Ch], r12d
0x180020121  jnz     loc_180020528
0x180020127  mov     rax, [r14+30h]
0x18002012b  mov     esi, [rax]
0x18002012d  mov     rax, [r14+28h]
0x180020131  mov     [rbp+StartingIndex], edi
0x180020134  mov     ecx, [rax+1Ch]
0x180020137  test    ecx, ecx
0x180020139  jz      loc_180020532
0x18002013f  mov     eax, esi
0x180020141  mov     r8d, 0F0000000h
0x180020147  and     eax, r8d
0x18002014a  cmp     eax, ecx
0x18002014c  jnz     loc_180020548
0x180020152  test    esi, esi
0x180020154  mov     eax, r15d
0x180020157  jz      loc_180020548
0x18002015d  mov     ecx, 250h
0x180020162  mov     r10d, 263h
0x180020168  lea     r11d, [r10-0Bh]
0x18002016c  mov     word ptr [rbp+var_3C], cx
0x180020170  mov     [rbp+var_40], edi
0x180020173  test    esi, esi
0x180020175  jz      loc_180020421
0x18002017b  test    eax, eax
0x18002017d  jz      loc_180020421
0x180020183  mov     rdx, [r14+28h]
0x180020187  cmp     [rdx+1Ch], edi
0x18002018a  jbe     loc_18002059E
0x180020190  mov     r13d, esi
0x180020193  and     r13d, r8d
0x180020196  cmp     r13d, [rdx+1Ch]
0x18002019a  jnz     loc_180020466
0x1800201a0  movzx   eax, si
0x1800201a3  lea     ecx, [rax-1]
0x1800201a6  neg     eax
0x1800201a8  sbb     r9d, r9d
0x1800201ab  and     r9d, ecx
0x1800201ae  mov     [rbp+StartingIndex], r9d
0x1800201b2  shr     esi, 10h
0x1800201b5  and     esi, 0FFFh
0x1800201bb  mov     r12d, esi
0x1800201be  mov     [rbp+arg_10], r12
0x1800201c2  mov     rax, [rdx+8]
0x1800201c6  mov     rax, [rax+rsi*8]
0x1800201ca  test    rax, rax
0x1800201cd  jz      loc_180020466
0x1800201d3  cmp     r9d, [rdx+14h]
0x1800201d7  jnb     loc_180020466
0x1800201dd  mov     ecx, r9d
0x1800201e0  imul    rcx, [rdx+20h]
0x1800201e5  mov     rax, [rax]
0x1800201e8  mov     [rbp+var_40], edi
0x1800201eb  mov     word ptr [rbp+var_3C], r11w
0x1800201f0  mov     esi, [rcx+rax+14h]
0x1800201f4  mov     r15d, [rcx+rax+10h]
0x1800201f9  mov     rbx, [r14+28h]
0x1800201fd  mov     eax, [rbx+1Ch]
0x180020200  test    r15d, r15d
0x180020203  jz      loc_1800202F0
0x180020209  test    eax, eax
0x18002020b  jz      loc_18002056F
0x180020211  mov     edx, r15d
0x180020214  and     edx, r8d
0x180020217  cmp     edx, eax
0x180020219  jnz     loc_1800204A5
0x18002021f  movzx   eax, r15w
0x180020223  lea     ecx, [rax-1]
0x180020226  neg     eax
0x180020228  sbb     r9d, r9d
0x18002022b  and     r9d, ecx
0x18002022e  shr     r15d, 10h
0x180020232  and     r15d, 0FFFh
0x180020239  mov     r12d, r15d
0x18002023c  mov     rax, [rbx+8]
0x180020240  mov     rcx, [rax+r15*8]
0x180020244  test    rcx, rcx
0x180020247  jz      loc_1800204A5
0x18002024d  cmp     r9d, [rbx+14h]
0x180020251  jnb     loc_1800204A5
0x180020257  mov     r8, [rbx+20h]
0x18002025b  mov     r15, [rcx]
0x18002025e  mov     [rbp+var_40], edi
0x180020261  mov     eax, 25Fh
0x180020266  mov     word ptr [rbp+var_3C], ax
0x18002026a  cmp     [rbx+1Ch], edi
0x18002026d  jbe     loc_18002055D
0x180020273  cmp     edx, [rbx+1Ch]
0x180020276  jnz     loc_180020556
0x18002027c  mov     rax, [rbx+8]
0x180020280  mov     rdi, [rax+r12*8]
0x180020284  test    rdi, rdi
0x180020287  jz      loc_180020556
0x18002028d  cmp     r9d, [rbx+14h]
0x180020291  jnb     loc_180020556
0x180020297  mov     eax, r9d
0x18002029a  imul    rax, r8
0x18002029e  mov     r15d, [rax+r15+14h]
0x1800202a3  lea     rcx, [rdi+10h]; BitMapHeader
0x1800202a7  mov     r8d, 1; NumberToClear
0x1800202ad  mov     edx, r9d; StartingIndex
0x1800202b0  call    cs:__imp_RtlClearBits
0x1800202b6  mov     eax, [rbx+14h]
0x1800202b9  cmp     [rdi+20h], eax
0x1800202bc  jnz     short loc_1800202C1
0x1800202be  inc     dword ptr [rbx+18h]
0x1800202c1  add     dword ptr [rdi+20h], 0FFFFFFFFh
0x1800202c5  jz      loc_1800203DA
0x1800202cb  cmp     r12d, [rbx+10h]
0x1800202cf  jnb     short loc_1800202D5
0x1800202d1  mov     [rbx+10h], r12d
0x1800202d5  xor     edi, edi
0x1800202d7  mov     [rbp+var_40], edi
0x1800202da  mov     r10d, 263h
0x1800202e0  mov     word ptr [rbp+var_3C], r10w
0x1800202e5  mov     r8d, 0F0000000h
0x1800202eb  jmp     loc_1800201F9
0x1800202f0  test    eax, eax
0x1800202f2  jz      loc_18002058F
0x1800202f8  cmp     r13d, eax
0x1800202fb  jnz     loc_180020588
0x180020301  mov     rax, [rbx+8]
0x180020305  mov     r12, [rbp+arg_10]
0x180020309  mov     rdi, [rax+r12*8]
0x18002030d  test    rdi, rdi
0x180020310  jz      loc_180020588
0x180020316  mov     r9d, [rbp+StartingIndex]
0x18002031a  cmp     r9d, [rbx+14h]
0x18002031e  jnb     loc_180020588
0x180020324  lea     rcx, [rdi+10h]; BitMapHeader
0x180020328  mov     r15d, 1
0x18002032e  mov     r8d, r15d; NumberToClear
0x180020331  mov     edx, r9d; StartingIndex
0x180020334  call    cs:__imp_RtlClearBits
0x18002033a  mov     eax, [rbx+14h]
0x18002033d  cmp     [rdi+20h], eax
0x180020340  jnz     short loc_180020346
0x180020342  add     [rbx+18h], r15d
0x180020346  add     dword ptr [rdi+20h], 0FFFFFFFFh
0x18002034a  jnz     loc_180020455
0x180020350  cmp     [rbx+18h], r15d
0x180020354  jbe     loc_180020455
0x18002035a  mov     rcx, [rdi+8]; pv
0x18002035e  call    cs:__imp_CoTaskMemFree
0x180020364  mov     qword ptr [rdi+8], 0
0x18002036c  mov     rcx, [rdi]; pv
0x18002036f  call    cs:__imp_CoTaskMemFree
0x180020375  mov     qword ptr [rdi], 0
0x18002037c  mov     rcx, rdi; pv
0x18002037f  call    cs:__imp_CoTaskMemFree
0x180020385  mov     rax, [rbx+8]
0x180020389  xor     edi, edi
0x18002038b  mov     [rax+r12*8], rdi
0x18002038f  dec     dword ptr [rbx+18h]
0x180020392  mov     [rbp+var_40], edi
0x180020395  mov     r10d, 267h
0x18002039b  mov     word ptr [rbp+var_3C], r10w
0x1800203a0  mov     rax, [r14+28h]
0x1800203a4  mov     [rbp+StartingIndex], edi
0x1800203a7  mov     ecx, [rax+1Ch]
0x1800203aa  test    ecx, ecx
0x1800203ac  jz      loc_180020579
0x1800203b2  mov     eax, esi
0x1800203b4  mov     r8d, 0F0000000h
0x1800203ba  and     eax, r8d
0x1800203bd  cmp     eax, ecx
0x1800203bf  jnz     loc_18002054F
0x1800203c5  test    esi, esi
0x1800203c7  mov     eax, r15d
0x1800203ca  jz      loc_18002054F
0x1800203d0  mov     ecx, 26Bh
0x1800203d5  jmp     loc_180020162
0x1800203da  cmp     dword ptr [rbx+18h], 1
0x1800203de  jbe     loc_1800202CB
0x1800203e4  mov     rcx, [rdi+8]; pv
0x1800203e8  call    cs:__imp_CoTaskMemFree
0x1800203ee  mov     qword ptr [rdi+8], 0
0x1800203f6  mov     rcx, [rdi]; pv
0x1800203f9  call    cs:__imp_CoTaskMemFree
0x1800203ff  mov     qword ptr [rdi], 0
0x180020406  mov     rcx, rdi; pv
0x180020409  call    cs:__imp_CoTaskMemFree
0x18002040f  mov     rax, [rbx+8]
0x180020413  xor     edi, edi
0x180020415  mov     [rax+r12*8], rdi
0x180020419  dec     dword ptr [rbx+18h]
0x18002041c  jmp     loc_1800202D7
0x180020421  mov     rax, [r14+30h]
0x180020425  mov     [rax], edi
0x180020427  mov     rax, [r14+30h]
0x18002042b  mov     [rax+8], rdi
0x18002042f  mov     ebx, [rbp+var_40]
0x180020432  lea     rcx, [rbp+var_40]; this
0x180020436  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002043b  mov     eax, ebx
0x18002043d  mov     rbx, [rsp+60h+arg_18]
0x180020445  add     rsp, 60h
0x180020449  pop     r15
0x18002044b  pop     r14
0x18002044d  pop     r13
0x18002044f  pop     r12
0x180020451  pop     rdi
0x180020452  pop     rsi
0x180020453  pop     rbp
0x180020454  retn
0x180020455  cmp     r12d, [rbx+10h]
0x180020459  jnb     short loc_18002045F
0x18002045b  mov     [rbx+10h], r12d
0x18002045f  xor     edi, edi
0x180020461  jmp     loc_180020392
0x180020466  mov     ebx, 80070057h
0x18002046b  mov     [rbp+var_40], ebx
0x18002046e  mov     word ptr [rbp+var_3C+2], r11w
0x180020473  jmp     short loc_180020432
0x180020475  cmp     rcx, rbx
0x180020478  jz      loc_180020127
0x18002047e  test    dword ptr [rcx+1Ch], 20000h
0x180020485  jz      loc_180020127
0x18002048b  mov     edx, 0Dh
0x180020490  mov     r9, [rbp+var_30]
0x180020494  mov     r8, rsi
0x180020497  mov     rcx, [rcx+10h]
0x18002049b  call    WPP_SF_s
0x1800204a0  jmp     loc_180020127
0x1800204a5  mov     ebx, 80070057h
0x1800204aa  mov     eax, 25Fh
0x1800204af  mov     [rbp+var_40], ebx
0x1800204b2  mov     word ptr [rbp+var_3C+2], ax
0x1800204b6  jmp     loc_180020432
0x1800204bb  mov     edx, 15h
0x1800204c0  lea     r8, WPP_7d91fd3008b83281181ea730215a620a_Traceguids
0x1800204c7  mov     rcx, [rcx+10h]
0x1800204cb  call    WPP_SF_
0x1800204d0  jmp     loc_18002009D
0x1800204d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800204dc  cmp     rcx, rbx
0x1800204df  jz      loc_180020101
0x1800204e5  test    [rcx+1Ch], r15b
0x1800204e9  jz      loc_180020101
0x1800204ef  mov     edx, 0Ah
0x1800204f4  mov     r9d, eax
0x1800204f7  mov     r8, rsi
0x1800204fa  mov     rcx, [rcx+10h]
0x1800204fe  call    WPP_SF_d
0x180020503  jmp     loc_1800200FA
0x180020508  cmp     rcx, rbx
0x18002050b  jz      loc_180020127
0x180020511  test    dword ptr [rcx+1Ch], 8000000h
0x180020518  jz      loc_180020127
0x18002051e  mov     edx, 0Bh
0x180020523  jmp     loc_180020490
0x180020528  mov     edx, 0Ch
0x18002052d  jmp     loc_180020490
  ... truncated ...
```
