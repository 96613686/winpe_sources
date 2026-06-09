# GpGraphics::StartPrinterEMF(void)

- ea: `0x18010269c`
- end: `0x1801028f0`
- name: `?StartPrinterEMF@GpGraphics@@IEAA?AW4Status@@XZ`
- size: `596`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000a9a0`

## callees

- `0x1800105b0`
- `0x180065eb0`
- `0x1800e5044`
- `0x1800e9380`
- `0x1800ea0ec`
- `0x18010269c`
- `0x18010e6e0`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801027d5`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1801027d5`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1801027b2`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1801027b2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1801027e9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18010287d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1801027e9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18010287d`
- `GDI32!ExtEscape` at `0x18010270a`
- `GDI32!ExtEscape` at `0x18010270a`

## pseudocode

```c
__int64 __fastcall GpGraphics::StartPrinterEMF(__int64 a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rcx
  __int64 result; // rax
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rax
  CHAR *v8; // rdx
  __int128 v9; // xmm1
  HGLOBAL v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  LPSTREAM v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  _BYTE v16[8]; // [rsp+40h] [rbp-448h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-440h] BYREF
  CHAR OutData[4]; // [rsp+50h] [rbp-438h] BYREF
  _BYTE v19[1052]; // [rsp+54h] [rbp-434h] BYREF

  v2 = 0;
  ppstm = 0;
  memset_0(v19, 0, 0x418u);
  v3 = *(_QWORD *)(a1 + 136);
  *(_DWORD *)OutData = 1052;
  if ( ExtEscape(*(HDC *)(v3 + 624), 4607, 0, 0, 1052, OutData) <= 0 )
    return 6;
  v5 = GpMallocEx(1052, 0);
  *(_QWORD *)(a1 + 72) = v5;
  v6 = v5;
  if ( !v5 )
    return 3;
  v7 = 8;
  v8 = OutData;
  do
  {
    *(_OWORD *)v6 = *(_OWORD *)v8;
    *(_OWORD *)(v6 + 16) = *((_OWORD *)v8 + 1);
    *(_OWORD *)(v6 + 32) = *((_OWORD *)v8 + 2);
    *(_OWORD *)(v6 + 48) = *((_OWORD *)v8 + 3);
    *(_OWORD *)(v6 + 64) = *((_OWORD *)v8 + 4);
    *(_OWORD *)(v6 + 80) = *((_OWORD *)v8 + 5);
    *(_OWORD *)(v6 + 96) = *((_OWORD *)v8 + 6);
    v6 += 128;
    v9 = *((_OWORD *)v8 + 7);
    v8 += 128;
    *(_OWORD *)(v6 - 16) = v9;
    --v7;
  }
  while ( v7 );
  *(_OWORD *)v6 = *(_OWORD *)v8;
  *(_QWORD *)(v6 + 16) = *((_QWORD *)v8 + 2);
  *(_DWORD *)(v6 + 24) = *((_DWORD *)v8 + 6);
  v10 = GlobalAlloc(2u, 1u);
  *(_QWORD *)(a1 + 80) = v10;
  if ( !v10 )
    return 3;
  if ( CreateStreamOnHGlobal(v10, 0, &ppstm) )
  {
    GlobalFree(*(HGLOBAL *)(a1 + 80));
    result = 7;
    *(_QWORD *)(a1 + 80) = 0;
  }
  else
  {
    FPUStateSaver::FPUStateSaver((FPUStateSaver *)v16, 1);
    v11 = GpMallocEx(256, 0);
    if ( v11 )
      v12 = GpMetafile::GpMetafile(v11, ppstm, *(_QWORD *)(*(_QWORD *)(a1 + 136) + 624LL), 4, 0, 7);
    else
      v12 = 0;
    v13 = ppstm;
    *(_QWORD *)(a1 + 88) = v12;
    (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v13 + 16LL))(v13);
    v14 = *(_QWORD *)(a1 + 88);
    if ( v14 )
    {
      v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 128LL))(v14);
      *(_QWORD *)(a1 + 96) = v15;
      if ( v15 )
        *(_QWORD *)(a1 + 56) = *(_QWORD *)(v15 + 56);
      else
        v2 = 8;
    }
    else
    {
      GlobalFree(*(HGLOBAL *)(a1 + 80));
      *(_QWORD *)(a1 + 80) = 0;
      v2 = 3;
    }
    FPUStateSaver::~FPUStateSaver((FPUStateSaver *)v16);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x18010269c  mov     [rsp+arg_8], rbx
0x1801026a1  push    rdi
0x1801026a2  sub     rsp, 480h
0x1801026a9  mov     rax, cs:__security_cookie
0x1801026b0  xor     rax, rsp
0x1801026b3  mov     [rsp+488h+var_18], rax
0x1801026bb  mov     rdi, rcx
0x1801026be  xor     ebx, ebx
0x1801026c0  lea     rcx, [rsp+488h+var_434]; void *
0x1801026c5  mov     [rsp+488h+ppstm], rbx
0x1801026ca  xor     edx, edx; Val
0x1801026cc  mov     r8d, 418h; Size
0x1801026d2  call    memset_0
0x1801026d7  mov     rcx, [rdi+88h]
0x1801026de  lea     rax, [rsp+488h+OutData]
0x1801026e3  mov     dword ptr [rsp+488h+OutData], 41Ch
0x1801026eb  xor     r9d, r9d; lpInData
0x1801026ee  mov     [rsp+488h+lpOutData], rax; lpOutData
0x1801026f3  xor     r8d, r8d; cjInput
0x1801026f6  mov     edx, 11FFh; iEscape
0x1801026fb  mov     [rsp+488h+cjOutput], 41Ch; cjOutput
0x180102703  mov     rcx, [rcx+270h]; hdc
0x18010270a  call    cs:__imp_ExtEscape
0x180102711  nop     dword ptr [rax+rax+00h]
0x180102716  test    eax, eax
0x180102718  jg      short loc_180102722
0x18010271a  lea     eax, [rbx+6]
0x18010271d  jmp     loc_1801028CE
0x180102722  xor     edx, edx
0x180102724  mov     ecx, 41Ch
0x180102729  call    GpMallocEx
0x18010272e  mov     [rdi+48h], rax
0x180102732  mov     rcx, rax
0x180102735  test    rax, rax
0x180102738  jz      loc_1801028C9
0x18010273e  mov     eax, 8
0x180102743  lea     rdx, [rsp+488h+OutData]
0x180102748  lea     r8d, [rax+78h]
0x18010274c  movups  xmm0, xmmword ptr [rdx]
0x18010274f  movups  xmmword ptr [rcx], xmm0
0x180102752  movups  xmm1, xmmword ptr [rdx+10h]
0x180102756  movups  xmmword ptr [rcx+10h], xmm1
0x18010275a  movups  xmm0, xmmword ptr [rdx+20h]
0x18010275e  movups  xmmword ptr [rcx+20h], xmm0
0x180102762  movups  xmm1, xmmword ptr [rdx+30h]
0x180102766  movups  xmmword ptr [rcx+30h], xmm1
0x18010276a  movups  xmm0, xmmword ptr [rdx+40h]
0x18010276e  movups  xmmword ptr [rcx+40h], xmm0
0x180102772  movups  xmm1, xmmword ptr [rdx+50h]
0x180102776  movups  xmmword ptr [rcx+50h], xmm1
0x18010277a  movups  xmm0, xmmword ptr [rdx+60h]
0x18010277e  movups  xmmword ptr [rcx+60h], xmm0
0x180102782  add     rcx, r8
0x180102785  movups  xmm1, xmmword ptr [rdx+70h]
0x180102789  add     rdx, r8
0x18010278c  movups  xmmword ptr [rcx-10h], xmm1
0x180102790  sub     rax, 1
0x180102794  jnz     short loc_18010274C
0x180102796  movups  xmm0, xmmword ptr [rdx]
0x180102799  movups  xmmword ptr [rcx], xmm0
0x18010279c  mov     rax, [rdx+10h]
0x1801027a0  mov     [rcx+10h], rax
0x1801027a4  mov     eax, [rdx+18h]
0x1801027a7  mov     edx, 1; dwBytes
0x1801027ac  mov     [rcx+18h], eax
0x1801027af  lea     ecx, [rdx+1]; uFlags
0x1801027b2  call    cs:__imp_GlobalAlloc
0x1801027b9  nop     dword ptr [rax+rax+00h]
0x1801027be  mov     [rdi+50h], rax
0x1801027c2  test    rax, rax
0x1801027c5  jz      loc_1801028C9
0x1801027cb  lea     r8, [rsp+488h+ppstm]; ppstm
0x1801027d0  xor     edx, edx; fDeleteOnRelease
0x1801027d2  mov     rcx, rax; hGlobal
0x1801027d5  call    cs:__imp_CreateStreamOnHGlobal
0x1801027dc  nop     dword ptr [rax+rax+00h]
0x1801027e1  test    eax, eax
0x1801027e3  jz      short loc_180102803
0x1801027e5  mov     rcx, [rdi+50h]; hMem
0x1801027e9  call    cs:__imp_GlobalFree
0x1801027f0  nop     dword ptr [rax+rax+00h]
0x1801027f5  mov     eax, 7
0x1801027fa  mov     [rdi+50h], rbx
0x1801027fe  jmp     loc_1801028CE
0x180102803  mov     edx, 1; int
0x180102808  lea     rcx, [rsp+488h+var_448]; this
0x18010280d  call    ??0FPUStateSaver@@QEAA@H@Z; FPUStateSaver::FPUStateSaver(int)
0x180102812  xor     edx, edx
0x180102814  mov     ecx, 100h
0x180102819  call    GpMallocEx
0x18010281e  test    rax, rax
0x180102821  jz      short loc_180102858
0x180102823  mov     r8, [rdi+88h]
0x18010282a  mov     r9d, 4
0x180102830  mov     rdx, [rsp+488h+ppstm]
0x180102835  mov     rcx, rax
0x180102838  mov     [rsp+488h+var_450], rbx
0x18010283d  mov     dword ptr [rsp+488h+lpOutData], 7
0x180102845  mov     r8, [r8+270h]
0x18010284c  mov     qword ptr [rsp+488h+cjOutput], rbx
0x180102851  call    ??0GpMetafile@@QEAA@PEAUIStream@@PEAUHDC__@@W4EmfType@@PEBVRectF@@W4MetafileFrameUnit@@PEBGPEAV0@@Z; GpMetafile::GpMetafile(IStream *,HDC__ *,EmfType,RectF const *,MetafileFrameUnit,ushort const *,GpMetafile *)
0x180102856  jmp     short loc_18010285B
0x180102858  mov     rax, rbx
0x18010285b  mov     rcx, [rsp+488h+ppstm]
0x180102860  mov     [rdi+58h], rax
0x180102864  mov     rax, [rcx]
0x180102867  mov     rax, [rax+10h]
0x18010286b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180102870  mov     rcx, [rdi+58h]
0x180102874  test    rcx, rcx
0x180102877  jnz     short loc_180102894
0x180102879  mov     rcx, [rdi+50h]; hMem
0x18010287d  call    cs:__imp_GlobalFree
0x180102884  nop     dword ptr [rax+rax+00h]
0x180102889  mov     [rdi+50h], rbx
0x18010288d  mov     ebx, 3
0x180102892  jmp     short loc_1801028BB
0x180102894  mov     rax, [rcx]
0x180102897  mov     rax, [rax+80h]
0x18010289e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801028a3  mov     [rdi+60h], rax
0x1801028a7  test    rax, rax
0x1801028aa  jz      short loc_1801028B6
0x1801028ac  mov     rax, [rax+38h]
0x1801028b0  mov     [rdi+38h], rax
0x1801028b4  jmp     short loc_1801028BB
0x1801028b6  mov     ebx, 8
0x1801028bb  lea     rcx, [rsp+488h+var_448]; this
0x1801028c0  call    ??1FPUStateSaver@@QEAA@XZ; FPUStateSaver::~FPUStateSaver(void)
0x1801028c5  mov     eax, ebx
0x1801028c7  jmp     short loc_1801028CE
0x1801028c9  mov     eax, 3
0x1801028ce  mov     rcx, [rsp+488h+var_18]
0x1801028d6  xor     rcx, rsp; StackCookie
0x1801028d9  call    __security_check_cookie
0x1801028de  mov     rbx, [rsp+488h+arg_8]
0x1801028e6  add     rsp, 480h
0x1801028ed  pop     rdi
0x1801028ee  retn
```
