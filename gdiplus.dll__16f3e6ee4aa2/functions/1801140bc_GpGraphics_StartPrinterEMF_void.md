# GpGraphics::StartPrinterEMF(void)

- ea: `0x1801140bc`
- end: `0x1801142ef`
- name: `?StartPrinterEMF@GpGraphics@@IEAA?AW4Status@@XZ`
- size: `563`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180070870`
- `0x180071654`

## callees

- `0x1800067bc`
- `0x180025c0c`
- `0x1800e36d0`
- `0x1800fe680`
- `0x1800ff04c`
- `0x1801140bc`
- `0x18011cbb0`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801141e1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801141e1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1801141c4`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1801141c4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1801141ef`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180114284`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1801141ef`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180114284`
- `GDI32!ExtEscape` at `0x180114129`
- `GDI32!ExtEscape` at `0x180114129`

## pseudocode

```c
__int64 __fastcall GpGraphics::StartPrinterEMF(__int64 a1)
{
  __int64 v2; // rcx
  __int64 result; // rax
  _OWORD *v4; // rax
  unsigned int v5; // edi
  CHAR *v6; // rcx
  __int64 v7; // rdx
  __int128 v8; // xmm1
  HGLOBAL v9; // rax
  __int64 v10; // rax
  LPSTREAM v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  _BYTE v14[8]; // [rsp+40h] [rbp-448h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-440h] BYREF
  CHAR OutData[4]; // [rsp+50h] [rbp-438h] BYREF
  _BYTE v17[1052]; // [rsp+54h] [rbp-434h] BYREF

  ppstm = 0;
  memset_0(v17, 0, 0x418u);
  v2 = *(_QWORD *)(a1 + 136);
  *(_DWORD *)OutData = 1052;
  if ( ExtEscape(*(HDC *)(v2 + 624), 4607, 0, 0, 1052, OutData) <= 0 )
    return 6;
  v4 = (_OWORD *)GpMallocEx(1052, 0);
  *(_QWORD *)(a1 + 72) = v4;
  if ( !v4 )
    return 3;
  v5 = 8;
  v6 = OutData;
  v7 = 8;
  do
  {
    *v4 = *(_OWORD *)v6;
    v4[1] = *((_OWORD *)v6 + 1);
    v4[2] = *((_OWORD *)v6 + 2);
    v4[3] = *((_OWORD *)v6 + 3);
    v4[4] = *((_OWORD *)v6 + 4);
    v4[5] = *((_OWORD *)v6 + 5);
    v4[6] = *((_OWORD *)v6 + 6);
    v8 = *((_OWORD *)v6 + 7);
    v6 += 128;
    v4[7] = v8;
    v4 += 8;
    --v7;
  }
  while ( v7 );
  *v4 = *(_OWORD *)v6;
  *(_OWORD *)((char *)v4 + 12) = *(_OWORD *)(v6 + 12);
  v9 = GlobalAlloc(2u, 1u);
  *(_QWORD *)(a1 + 80) = v9;
  if ( !v9 )
    return 3;
  if ( CreateStreamOnHGlobal(v9, 0, &ppstm) )
  {
    GlobalFree(*(HGLOBAL *)(a1 + 80));
    result = 7;
    *(_QWORD *)(a1 + 80) = 0;
  }
  else
  {
    FPUStateSaver::FPUStateSaver((FPUStateSaver *)v14, 1);
    v10 = GpMallocEx(256, 0);
    if ( v10 )
      v10 = GpMetafile::GpMetafile(v10, ppstm, *(_QWORD *)(*(_QWORD *)(a1 + 136) + 624LL), 4, 0, 7);
    v11 = ppstm;
    *(_QWORD *)(a1 + 88) = v10;
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v11 + 16LL))(v11);
    v12 = *(_QWORD *)(a1 + 88);
    if ( v12 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 128LL))(v12);
      *(_QWORD *)(a1 + 96) = v13;
      if ( v13 )
      {
        v5 = 0;
        *(_QWORD *)(a1 + 56) = *(_QWORD *)(v13 + 56);
      }
    }
    else
    {
      GlobalFree(*(HGLOBAL *)(a1 + 80));
      *(_QWORD *)(a1 + 80) = 0;
      v5 = 3;
    }
    FPUStateSaver::~FPUStateSaver((FPUStateSaver *)v14);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1801140bc  mov     [rsp+arg_8], rbx
0x1801140c1  push    rdi
0x1801140c2  sub     rsp, 480h
0x1801140c9  mov     rax, cs:__security_cookie
0x1801140d0  xor     rax, rsp
0x1801140d3  mov     [rsp+488h+var_18], rax
0x1801140db  mov     rbx, rcx
0x1801140de  mov     [rsp+488h+ppstm], 0
0x1801140e7  lea     rcx, [rsp+488h+var_434]; void *
0x1801140ec  xor     edx, edx; Val
0x1801140ee  mov     r8d, 418h; Size
0x1801140f4  call    memset_0
0x1801140f9  mov     rcx, [rbx+88h]
0x180114100  lea     rax, [rsp+488h+OutData]
0x180114105  mov     edi, 41Ch
0x18011410a  mov     [rsp+488h+lpOutData], rax; lpOutData
0x18011410f  mov     dword ptr [rsp+488h+OutData], edi
0x180114113  xor     r9d, r9d; lpInData
0x180114116  xor     r8d, r8d; cjInput
0x180114119  mov     [rsp+488h+cjOutput], edi; cjOutput
0x18011411d  mov     rcx, [rcx+270h]; hdc
0x180114124  mov     edx, 11FFh; iEscape
0x180114129  call    cs:__imp_ExtEscape
0x18011412f  test    eax, eax
0x180114131  jg      short loc_18011413D
0x180114133  mov     eax, 6
0x180114138  jmp     loc_1801142CE
0x18011413d  xor     edx, edx
0x18011413f  mov     rcx, rdi
0x180114142  call    GpMallocEx
0x180114147  mov     [rbx+48h], rax
0x18011414b  test    rax, rax
0x18011414e  jz      loc_1801142C9
0x180114154  mov     edi, 8
0x180114159  lea     rcx, [rsp+488h+OutData]
0x18011415e  mov     edx, edi
0x180114160  lea     r8d, [rdi+78h]
0x180114164  movups  xmm0, xmmword ptr [rcx]
0x180114167  movups  xmmword ptr [rax], xmm0
0x18011416a  movups  xmm1, xmmword ptr [rcx+10h]
0x18011416e  movups  xmmword ptr [rax+10h], xmm1
0x180114172  movups  xmm0, xmmword ptr [rcx+20h]
0x180114176  movups  xmmword ptr [rax+20h], xmm0
0x18011417a  movups  xmm1, xmmword ptr [rcx+30h]
0x18011417e  movups  xmmword ptr [rax+30h], xmm1
0x180114182  movups  xmm0, xmmword ptr [rcx+40h]
0x180114186  movups  xmmword ptr [rax+40h], xmm0
0x18011418a  movups  xmm1, xmmword ptr [rcx+50h]
0x18011418e  movups  xmmword ptr [rax+50h], xmm1
0x180114192  movups  xmm0, xmmword ptr [rcx+60h]
0x180114196  movups  xmmword ptr [rax+60h], xmm0
0x18011419a  movups  xmm1, xmmword ptr [rcx+70h]
0x18011419e  add     rcx, r8
0x1801141a1  movups  xmmword ptr [rax+70h], xmm1
0x1801141a5  add     rax, r8
0x1801141a8  sub     rdx, 1
0x1801141ac  jnz     short loc_180114164
0x1801141ae  movups  xmm0, xmmword ptr [rcx]
0x1801141b1  mov     edx, 1; dwBytes
0x1801141b6  movups  xmmword ptr [rax], xmm0
0x1801141b9  movups  xmm1, xmmword ptr [rcx+0Ch]
0x1801141bd  lea     ecx, [rdx+1]; uFlags
0x1801141c0  movups  xmmword ptr [rax+0Ch], xmm1
0x1801141c4  call    cs:__imp_GlobalAlloc
0x1801141ca  mov     [rbx+50h], rax
0x1801141ce  test    rax, rax
0x1801141d1  jz      loc_1801142C9
0x1801141d7  lea     r8, [rsp+488h+ppstm]; ppstm
0x1801141dc  xor     edx, edx; fDeleteOnRelease
0x1801141de  mov     rcx, rax; hGlobal
0x1801141e1  call    cs:__imp_CreateStreamOnHGlobal
0x1801141e7  test    eax, eax
0x1801141e9  jz      short loc_180114207
0x1801141eb  mov     rcx, [rbx+50h]; hMem
0x1801141ef  call    cs:__imp_GlobalFree
0x1801141f5  mov     eax, 7
0x1801141fa  mov     qword ptr [rbx+50h], 0
0x180114202  jmp     loc_1801142CE
0x180114207  mov     edx, 1; int
0x18011420c  lea     rcx, [rsp+488h+var_448]; this
0x180114211  call    ??0FPUStateSaver@@QEAA@H@Z; FPUStateSaver::FPUStateSaver(int)
0x180114216  xor     edx, edx
0x180114218  mov     ecx, 100h
0x18011421d  call    GpMallocEx
0x180114222  test    rax, rax
0x180114225  jz      short loc_180114262
0x180114227  mov     r8, [rbx+88h]
0x18011422e  mov     r9d, 4
0x180114234  mov     rdx, [rsp+488h+ppstm]
0x180114239  mov     rcx, rax
0x18011423c  mov     [rsp+488h+var_450], 0
0x180114245  mov     dword ptr [rsp+488h+lpOutData], 7
0x18011424d  mov     r8, [r8+270h]
0x180114254  mov     qword ptr [rsp+488h+cjOutput], 0
0x18011425d  call    ??0GpMetafile@@QEAA@PEAUIStream@@PEAUHDC__@@W4EmfType@@PEBVRectF@@W4MetafileFrameUnit@@PEBGPEAV0@@Z; GpMetafile::GpMetafile(IStream *,HDC__ *,EmfType,RectF const *,MetafileFrameUnit,ushort const *,GpMetafile *)
0x180114262  mov     rcx, [rsp+488h+ppstm]
0x180114267  mov     [rbx+58h], rax
0x18011426b  mov     rax, [rcx]
0x18011426e  mov     rax, [rax+10h]
0x180114272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114277  mov     rcx, [rbx+58h]
0x18011427b  test    rcx, rcx
0x18011427e  jnz     short loc_180114299
0x180114280  mov     rcx, [rbx+50h]; hMem
0x180114284  call    cs:__imp_GlobalFree
0x18011428a  mov     qword ptr [rbx+50h], 0
0x180114292  mov     edi, 3
0x180114297  jmp     short loc_1801142BB
0x180114299  mov     rax, [rcx]
0x18011429c  mov     rax, [rax+80h]
0x1801142a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801142a8  mov     [rbx+60h], rax
0x1801142ac  test    rax, rax
0x1801142af  jz      short loc_1801142BB
0x1801142b1  mov     rax, [rax+38h]
0x1801142b5  xor     edi, edi
0x1801142b7  mov     [rbx+38h], rax
0x1801142bb  lea     rcx, [rsp+488h+var_448]; this
0x1801142c0  call    ??1FPUStateSaver@@QEAA@XZ; FPUStateSaver::~FPUStateSaver(void)
0x1801142c5  mov     eax, edi
0x1801142c7  jmp     short loc_1801142CE
0x1801142c9  mov     eax, 3
0x1801142ce  mov     rcx, [rsp+488h+var_18]
0x1801142d6  xor     rcx, rsp; StackCookie
0x1801142d9  call    __security_check_cookie
0x1801142de  mov     rbx, [rsp+488h+arg_8]
0x1801142e6  add     rsp, 480h
0x1801142ed  pop     rdi
0x1801142ee  retn
```
