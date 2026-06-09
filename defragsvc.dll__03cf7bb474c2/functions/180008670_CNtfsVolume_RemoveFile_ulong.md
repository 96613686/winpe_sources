# CNtfsVolume::RemoveFile(ulong)

- ea: `0x180008670`
- end: `0x18000897a`
- name: `?RemoveFile@CNtfsVolume@@UEAAJK@Z`
- size: `778`
- prototype: `__int64 __fastcall(CNtfsVolume *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006400`
- `0x180006bf8`
- `0x180008670`
- `0x180046494`
- `0x18004a92c`

## import_xrefs

- `ntdll!RtlClearBits` at `0x1800087f1`
- `ntdll!RtlClearBits` at `0x1800087f1`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x1800086c1`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x1800086c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008874`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008881`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000888d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008874`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008881`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000888d`

## string_xrefs

- `0x1800086a2`: `CNtfsVolume::RemoveFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNtfsVolume::RemoveFile(CNtfsVolume *this, unsigned int a2)
{
  int ThreadContextRetail; // eax
  CSxGlobalTracer *v5; // rcx
  __int16 v6; // ax
  __int64 v7; // rdx
  unsigned int v8; // edi
  ULONG v9; // r14d
  __int64 v10; // rbx
  __int64 v11; // rsi
  _QWORD *v12; // rax
  __int64 v13; // rcx
  bool v14; // zf
  unsigned int *v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // rdi
  int v18; // ebx
  int v20; // eax
  __int16 v21; // cx
  __int64 v22; // rdx
  int v23; // [rsp+20h] [rbp-48h] BYREF
  __int64 v24; // [rsp+24h] [rbp-44h]
  __int16 v25; // [rsp+2Ch] [rbp-3Ch]
  const char *v26; // [rsp+30h] [rbp-38h]
  __int128 v27; // [rsp+38h] [rbp-30h] BYREF
  __int64 v28; // [rsp+48h] [rbp-20h]
  int v29; // [rsp+50h] [rbp-18h]

  v23 = 0;
  v24 = 717;
  v25 = 1;
  v26 = "CNtfsVolume::RemoveFile";
  v27 = 0;
  v28 = 0;
  v29 = 0;
  ThreadContextRetail = SxTracerGetThreadContextRetail((char *)&v27 + 8);
  if ( ThreadContextRetail >= 0 )
  {
    *(_QWORD *)&v27 = *(_QWORD *)(*((_QWORD *)&v27 + 1) + 32LL);
    *(_QWORD *)(*((_QWORD *)&v27 + 1) + 32LL) = &v23;
LABEL_3:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_4;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids,
      (unsigned int)ThreadContextRetail);
    goto LABEL_3;
  }
LABEL_4:
  if ( v25 )
  {
    if ( v25 == 1 )
    {
      if ( v5 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v5 + 7) & 0x20000000) == 0 )
        goto LABEL_8;
      v22 = 12;
LABEL_40:
      WPP_SF_s(*((_QWORD *)v5 + 2), v22, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids, v26);
      goto LABEL_8;
    }
    if ( v5 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x20000) != 0 )
    {
      v22 = 13;
      goto LABEL_40;
    }
  }
  else if ( v5 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x8000000) != 0 )
  {
    v22 = 11;
    goto LABEL_40;
  }
LABEL_8:
  v6 = 721;
  if ( !a2 )
  {
    v18 = -2147024809;
    v23 = -2147024809;
    goto LABEL_27;
  }
  v23 = 0;
  LOWORD(v24) = 721;
  v7 = *((_QWORD *)this + 59);
  if ( !*(_DWORD *)(v7 + 28) )
  {
    v20 = -2147467259;
    v23 = -2147467259;
    goto LABEL_29;
  }
  v8 = a2 & 0xF0000000;
  if ( (a2 & 0xF0000000) != *(_DWORD *)(v7 + 28)
    || (v9 = (unsigned __int16)a2 != 0 ? (unsigned __int16)a2 - 1 : 0,
        v10 = HIWORD(a2) & 0xFFF,
        v11 = (unsigned int)v10,
        (v12 = *(_QWORD **)(*(_QWORD *)(v7 + 8) + 8 * v10)) == 0)
    || v9 >= *(_DWORD *)(v7 + 20) )
  {
    v20 = -2147024809;
    v23 = -2147024809;
LABEL_29:
    v21 = 723;
LABEL_30:
    WORD1(v24) = v21;
    v18 = v20;
    goto LABEL_25;
  }
  v13 = *(_QWORD *)(v7 + 32) * v9;
  v14 = v13 + *v12 == 0;
  v15 = (unsigned int *)(v13 + *v12);
  v23 = 0;
  LOWORD(v24) = 723;
  if ( !v14 && *v15 )
  {
    v18 = CVolume::_FreeExtents(this, v15);
    v23 = v18;
    v6 = 727;
    if ( v18 >= 0 )
    {
      LOWORD(v24) = 727;
      goto LABEL_15;
    }
LABEL_27:
    WORD1(v24) = v6;
    goto LABEL_25;
  }
LABEL_15:
  v16 = *((_QWORD *)this + 59);
  if ( !*(_DWORD *)(v16 + 28) )
  {
    v20 = -2147467259;
    v23 = -2147467259;
    goto LABEL_34;
  }
  if ( v8 != *(_DWORD *)(v16 + 28)
    || (v17 = *(_QWORD *)(*(_QWORD *)(v16 + 8) + 8 * v11)) == 0
    || v9 >= *(_DWORD *)(v16 + 20) )
  {
    v20 = -2147024809;
    v23 = -2147024809;
LABEL_34:
    v21 = 731;
    goto LABEL_30;
  }
  RtlClearBits((PRTL_BITMAP)(v17 + 16), v9, 1u);
  if ( *(_DWORD *)(v17 + 32) == *(_DWORD *)(v16 + 20) )
    ++*(_DWORD *)(v16 + 24);
  v14 = (*(_DWORD *)(v17 + 32))-- == 1;
  if ( v14 && *(_DWORD *)(v16 + 24) > 1u )
  {
    CoTaskMemFree(*(LPVOID *)(v17 + 8));
    *(_QWORD *)(v17 + 8) = 0;
    CoTaskMemFree(*(LPVOID *)v17);
    *(_QWORD *)v17 = 0;
    CoTaskMemFree((LPVOID)v17);
    *(_QWORD *)(*(_QWORD *)(v16 + 8) + 8 * v11) = 0;
    --*(_DWORD *)(v16 + 24);
  }
  else if ( (unsigned int)v11 < *(_DWORD *)(v16 + 16) )
  {
    *(_DWORD *)(v16 + 16) = v11;
  }
  LOWORD(v24) = 731;
  v23 = 0;
  v18 = 0;
LABEL_25:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v23);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x180008670  push    rbp
0x180008672  push    rbx
0x180008673  push    rsi
0x180008674  push    rdi
0x180008675  push    r12
0x180008677  push    r13
0x180008679  push    r14
0x18000867b  push    r15
0x18000867d  mov     rbp, rsp
0x180008680  sub     rsp, 68h
0x180008684  mov     ebx, edx
0x180008686  mov     r15, rcx
0x180008689  xor     r12d, r12d
0x18000868c  mov     [rbp+var_48], r12d
0x180008690  mov     [rbp+var_44], 2CDh
0x180008698  lea     r13d, [r12+1]
0x18000869d  mov     [rbp+var_3C], r13w
0x1800086a2  lea     rax, aCntfsvolumeRem; "CNtfsVolume::RemoveFile"
0x1800086a9  mov     [rbp+var_38], rax
0x1800086ad  xorps   xmm0, xmm0
0x1800086b0  movdqu  [rbp+var_30], xmm0
0x1800086b5  mov     [rbp+var_20], r12
0x1800086b9  mov     [rbp+var_18], r12d
0x1800086bd  lea     rcx, [rbp+var_30+8]
0x1800086c1  call    cs:__imp_SxTracerGetThreadContextRetail
0x1800086c7  lea     rsi, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x1800086ce  lea     rdi, WPP_GLOBAL_Control
0x1800086d5  test    eax, eax
0x1800086d7  js      loc_180008908
0x1800086dd  mov     rcx, qword ptr [rbp+var_30+8]
0x1800086e1  mov     rax, [rcx+20h]
0x1800086e5  mov     qword ptr [rbp+var_30], rax
0x1800086e9  lea     rax, [rbp+var_48]
0x1800086ed  mov     [rcx+20h], rax
0x1800086f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086f8  movzx   eax, [rbp+var_3C]
0x1800086fc  test    ax, ax
0x1800086ff  jz      loc_18000893B
0x180008705  cmp     ax, r13w
0x180008709  jnz     loc_1800088D8
0x18000870f  cmp     rcx, rdi
0x180008712  jz      short loc_180008721
0x180008714  test    dword ptr [rcx+1Ch], 20000000h
0x18000871b  jnz     loc_180008958
0x180008721  mov     eax, 2D1h
0x180008726  test    ebx, ebx
0x180008728  jz      loc_18000883A
0x18000872e  mov     [rbp+var_48], r12d
0x180008732  mov     word ptr [rbp+var_44], ax
0x180008736  mov     rdx, [r15+1D8h]
0x18000873d  cmp     [rdx+1Ch], r12d
0x180008741  jbe     loc_18000895F
0x180008747  mov     edi, ebx
0x180008749  and     edi, 0F0000000h
0x18000874f  cmp     edi, [rdx+1Ch]
0x180008752  jnz     loc_180008853
0x180008758  movzx   eax, bx
0x18000875b  lea     ecx, [rax-1]
0x18000875e  neg     eax
0x180008760  sbb     r14d, r14d
0x180008763  and     r14d, ecx
0x180008766  shr     ebx, 10h
0x180008769  and     ebx, 0FFFh
0x18000876f  mov     esi, ebx
0x180008771  mov     rax, [rdx+8]
0x180008775  mov     rax, [rax+rbx*8]
0x180008779  test    rax, rax
0x18000877c  jz      loc_180008853
0x180008782  cmp     r14d, [rdx+14h]
0x180008786  jnb     loc_180008853
0x18000878c  mov     ecx, r14d
0x18000878f  imul    rcx, [rdx+20h]
0x180008794  mov     rdx, [rax]
0x180008797  add     rdx, rcx; unsigned int *
0x18000879a  mov     [rbp+var_48], r12d
0x18000879e  mov     ecx, 2D3h
0x1800087a3  mov     word ptr [rbp+var_44], cx
0x1800087a7  jz      short loc_1800087B2
0x1800087a9  cmp     [rdx], r12d
0x1800087ac  jnz     loc_1800088B5
0x1800087b2  mov     rbx, [r15+1D8h]
0x1800087b9  cmp     [rbx+1Ch], r12d
0x1800087bd  jbe     loc_18000896C
0x1800087c3  cmp     edi, [rbx+1Ch]
0x1800087c6  jnz     loc_1800088A4
0x1800087cc  mov     rax, [rbx+8]
0x1800087d0  mov     rdi, [rax+rsi*8]
0x1800087d4  test    rdi, rdi
0x1800087d7  jz      loc_1800088A4
0x1800087dd  cmp     r14d, [rbx+14h]
0x1800087e1  jnb     loc_1800088A4
0x1800087e7  lea     rcx, [rdi+10h]; BitMapHeader
0x1800087eb  mov     r8d, r13d; NumberToClear
0x1800087ee  mov     edx, r14d; StartingIndex
0x1800087f1  call    cs:__imp_RtlClearBits
0x1800087f7  mov     eax, [rbx+14h]
0x1800087fa  cmp     [rdi+20h], eax
0x1800087fd  jz      short loc_180008848
0x1800087ff  or      r14d, 0FFFFFFFFh
0x180008803  add     [rdi+20h], r14d
0x180008807  jz      short loc_18000886A
0x180008809  cmp     esi, [rbx+10h]
0x18000880c  jb      short loc_18000884E
0x18000880e  mov     ecx, 2DBh
0x180008813  mov     word ptr [rbp+var_44], cx
0x180008817  mov     [rbp+var_48], r12d
0x18000881b  mov     ebx, r12d
0x18000881e  lea     rcx, [rbp+var_48]; this
0x180008822  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180008827  mov     eax, ebx
0x180008829  add     rsp, 68h
0x18000882d  pop     r15
0x18000882f  pop     r14
0x180008831  pop     r13
0x180008833  pop     r12
0x180008835  pop     rdi
0x180008836  pop     rsi
0x180008837  pop     rbx
0x180008838  pop     rbp
0x180008839  retn
0x18000883a  mov     ebx, 80070057h
0x18000883f  mov     [rbp+var_48], ebx
0x180008842  mov     word ptr [rbp+var_44+2], ax
0x180008846  jmp     short loc_18000881E
0x180008848  add     [rbx+18h], r13d
0x18000884c  jmp     short loc_1800087FF
0x18000884e  mov     [rbx+10h], esi
0x180008851  jmp     short loc_18000880E
0x180008853  mov     ebx, 80070057h
0x180008858  mov     eax, ebx
0x18000885a  mov     [rbp+var_48], ebx
0x18000885d  mov     ecx, 2D3h
0x180008862  mov     word ptr [rbp+var_44+2], cx
0x180008866  mov     ebx, eax
0x180008868  jmp     short loc_18000881E
0x18000886a  cmp     [rbx+18h], r13d
0x18000886e  jbe     short loc_180008809
0x180008870  mov     rcx, [rdi+8]; pv
0x180008874  call    cs:__imp_CoTaskMemFree
0x18000887a  mov     [rdi+8], r12
0x18000887e  mov     rcx, [rdi]; pv
0x180008881  call    cs:__imp_CoTaskMemFree
0x180008887  mov     [rdi], r12
0x18000888a  mov     rcx, rdi; pv
0x18000888d  call    cs:__imp_CoTaskMemFree
0x180008893  mov     rax, [rbx+8]
0x180008897  mov     [rax+rsi*8], r12
0x18000889b  add     [rbx+18h], r14d
0x18000889f  jmp     loc_18000880E
0x1800088a4  mov     ebx, 80070057h
0x1800088a9  mov     eax, ebx
0x1800088ab  mov     [rbp+var_48], ebx
0x1800088ae  mov     ecx, 2DBh
0x1800088b3  jmp     short loc_180008862
0x1800088b5  mov     rcx, r15; this
0x1800088b8  call    ?_FreeExtents@CVolume@@IEAAJPEAK@Z; CVolume::_FreeExtents(ulong *)
0x1800088bd  mov     ebx, eax
0x1800088bf  mov     [rbp+var_48], eax
0x1800088c2  test    eax, eax
0x1800088c4  mov     eax, 2D7h
0x1800088c9  js      loc_180008842
0x1800088cf  mov     word ptr [rbp+var_44], ax
0x1800088d3  jmp     loc_1800087B2
0x1800088d8  cmp     rcx, rdi
0x1800088db  jz      loc_180008721
0x1800088e1  test    dword ptr [rcx+1Ch], 20000h
0x1800088e8  jz      loc_180008721
0x1800088ee  mov     edx, 0Dh
0x1800088f3  mov     r9, [rbp+var_38]
0x1800088f7  mov     r8, rsi
0x1800088fa  mov     rcx, [rcx+10h]
0x1800088fe  call    WPP_SF_s
0x180008903  jmp     loc_180008721
0x180008908  mov     rcx, cs:WPP_GLOBAL_Control
0x18000890f  cmp     rcx, rdi
0x180008912  jz      loc_1800086F8
0x180008918  test    [rcx+1Ch], r13b
0x18000891c  jz      loc_1800086F8
0x180008922  mov     edx, 0Ah
0x180008927  mov     r9d, eax
0x18000892a  mov     r8, rsi
0x18000892d  mov     rcx, [rcx+10h]
0x180008931  call    WPP_SF_d
0x180008936  jmp     loc_1800086F1
0x18000893b  cmp     rcx, rdi
0x18000893e  jz      loc_180008721
0x180008944  test    dword ptr [rcx+1Ch], 8000000h
0x18000894b  jz      loc_180008721
0x180008951  mov     edx, 0Bh
0x180008956  jmp     short loc_1800088F3
0x180008958  mov     edx, 0Ch
0x18000895d  jmp     short loc_1800088F3
0x18000895f  mov     eax, 80004005h
0x180008964  mov     [rbp+var_48], eax
0x180008967  jmp     loc_18000885D
0x18000896c  mov     eax, 80004005h
0x180008971  mov     [rbp+var_48], eax
0x180008974  jmp     loc_1800088AE
```
