# GpGraphics::StartPrinterEMF(void)

- ea: `0x18011be8c`
- end: `0x18011c0de`
- name: `?StartPrinterEMF@GpGraphics@@IEAA?AW4Status@@XZ`
- size: `594`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180040530`
- `0x180040ea8`

## callees

- `0x180017b68`
- `0x180063cd8`
- `0x1800eacb0`
- `0x180105d40`
- `0x18010673c`
- `0x18011be8c`
- `0x180124cfc`
- `0x180172010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18011bfbd`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18011bfbd`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18011bf9a`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18011bf9a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18011bfd1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18011c06c`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18011bfd1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18011c06c`
- `GDI32!ExtEscape` at `0x18011bef9`
- `GDI32!ExtEscape` at `0x18011bef9`

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
0x18011be8c  mov     [rsp+arg_8], rbx
0x18011be91  push    rdi
0x18011be92  sub     rsp, 480h
0x18011be99  mov     rax, cs:__security_cookie
0x18011bea0  xor     rax, rsp
0x18011bea3  mov     [rsp+488h+var_18], rax
0x18011beab  mov     rbx, rcx
0x18011beae  mov     [rsp+488h+ppstm], 0
0x18011beb7  lea     rcx, [rsp+488h+var_434]; void *
0x18011bebc  xor     edx, edx; Val
0x18011bebe  mov     r8d, 418h; Size
0x18011bec4  call    memset_0
0x18011bec9  mov     rcx, [rbx+88h]
0x18011bed0  lea     rax, [rsp+488h+OutData]
0x18011bed5  mov     edi, 41Ch
0x18011beda  mov     [rsp+488h+lpOutData], rax; lpOutData
0x18011bedf  mov     dword ptr [rsp+488h+OutData], edi
0x18011bee3  xor     r9d, r9d; lpInData
0x18011bee6  xor     r8d, r8d; cjInput
0x18011bee9  mov     [rsp+488h+cjOutput], edi; cjOutput
0x18011beed  mov     rcx, [rcx+270h]; hdc
0x18011bef4  mov     edx, 11FFh; iEscape
0x18011bef9  call    cs:__imp_ExtEscape
0x18011bf00  nop     dword ptr [rax+rax+00h]
0x18011bf05  test    eax, eax
0x18011bf07  jg      short loc_18011BF13
0x18011bf09  mov     eax, 6
0x18011bf0e  jmp     loc_18011C0BC
0x18011bf13  xor     edx, edx
0x18011bf15  mov     rcx, rdi
0x18011bf18  call    GpMallocEx
0x18011bf1d  mov     [rbx+48h], rax
0x18011bf21  test    rax, rax
0x18011bf24  jz      loc_18011C0B7
0x18011bf2a  mov     edi, 8
0x18011bf2f  lea     rcx, [rsp+488h+OutData]
0x18011bf34  mov     edx, edi
0x18011bf36  lea     r8d, [rdi+78h]
0x18011bf3a  movups  xmm0, xmmword ptr [rcx]
0x18011bf3d  movups  xmmword ptr [rax], xmm0
0x18011bf40  movups  xmm1, xmmword ptr [rcx+10h]
0x18011bf44  movups  xmmword ptr [rax+10h], xmm1
0x18011bf48  movups  xmm0, xmmword ptr [rcx+20h]
0x18011bf4c  movups  xmmword ptr [rax+20h], xmm0
0x18011bf50  movups  xmm1, xmmword ptr [rcx+30h]
0x18011bf54  movups  xmmword ptr [rax+30h], xmm1
0x18011bf58  movups  xmm0, xmmword ptr [rcx+40h]
0x18011bf5c  movups  xmmword ptr [rax+40h], xmm0
0x18011bf60  movups  xmm1, xmmword ptr [rcx+50h]
0x18011bf64  movups  xmmword ptr [rax+50h], xmm1
0x18011bf68  movups  xmm0, xmmword ptr [rcx+60h]
0x18011bf6c  movups  xmmword ptr [rax+60h], xmm0
0x18011bf70  movups  xmm1, xmmword ptr [rcx+70h]
0x18011bf74  add     rcx, r8
0x18011bf77  movups  xmmword ptr [rax+70h], xmm1
0x18011bf7b  add     rax, r8
0x18011bf7e  sub     rdx, 1
0x18011bf82  jnz     short loc_18011BF3A
0x18011bf84  movups  xmm0, xmmword ptr [rcx]
0x18011bf87  mov     edx, 1; dwBytes
0x18011bf8c  movups  xmmword ptr [rax], xmm0
0x18011bf8f  movups  xmm1, xmmword ptr [rcx+0Ch]
0x18011bf93  lea     ecx, [rdx+1]; uFlags
0x18011bf96  movups  xmmword ptr [rax+0Ch], xmm1
0x18011bf9a  call    cs:__imp_GlobalAlloc
0x18011bfa1  nop     dword ptr [rax+rax+00h]
0x18011bfa6  mov     [rbx+50h], rax
0x18011bfaa  test    rax, rax
0x18011bfad  jz      loc_18011C0B7
0x18011bfb3  lea     r8, [rsp+488h+ppstm]; ppstm
0x18011bfb8  xor     edx, edx; fDeleteOnRelease
0x18011bfba  mov     rcx, rax; hGlobal
0x18011bfbd  call    cs:__imp_CreateStreamOnHGlobal
0x18011bfc4  nop     dword ptr [rax+rax+00h]
0x18011bfc9  test    eax, eax
0x18011bfcb  jz      short loc_18011BFEF
0x18011bfcd  mov     rcx, [rbx+50h]; hMem
0x18011bfd1  call    cs:__imp_GlobalFree
0x18011bfd8  nop     dword ptr [rax+rax+00h]
0x18011bfdd  mov     eax, 7
0x18011bfe2  mov     qword ptr [rbx+50h], 0
0x18011bfea  jmp     loc_18011C0BC
0x18011bfef  mov     edx, 1; int
0x18011bff4  lea     rcx, [rsp+488h+var_448]; this
0x18011bff9  call    ??0FPUStateSaver@@QEAA@H@Z; FPUStateSaver::FPUStateSaver(int)
0x18011bffe  xor     edx, edx
0x18011c000  mov     ecx, 100h
0x18011c005  call    GpMallocEx
0x18011c00a  test    rax, rax
0x18011c00d  jz      short loc_18011C04A
0x18011c00f  mov     r8, [rbx+88h]
0x18011c016  mov     r9d, 4
0x18011c01c  mov     rdx, [rsp+488h+ppstm]
0x18011c021  mov     rcx, rax
0x18011c024  mov     [rsp+488h+var_450], 0
0x18011c02d  mov     dword ptr [rsp+488h+lpOutData], 7
0x18011c035  mov     r8, [r8+270h]
0x18011c03c  mov     qword ptr [rsp+488h+cjOutput], 0
0x18011c045  call    ??0GpMetafile@@QEAA@PEAUIStream@@PEAUHDC__@@W4EmfType@@PEBVRectF@@W4MetafileFrameUnit@@PEBGPEAV0@@Z; GpMetafile::GpMetafile(IStream *,HDC__ *,EmfType,RectF const *,MetafileFrameUnit,ushort const *,GpMetafile *)
0x18011c04a  mov     rcx, [rsp+488h+ppstm]
0x18011c04f  mov     [rbx+58h], rax
0x18011c053  mov     rax, [rcx]
0x18011c056  mov     rax, [rax+10h]
0x18011c05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c05f  mov     rcx, [rbx+58h]
0x18011c063  test    rcx, rcx
0x18011c066  jnz     short loc_18011C087
0x18011c068  mov     rcx, [rbx+50h]; hMem
0x18011c06c  call    cs:__imp_GlobalFree
0x18011c073  nop     dword ptr [rax+rax+00h]
0x18011c078  mov     qword ptr [rbx+50h], 0
0x18011c080  mov     edi, 3
0x18011c085  jmp     short loc_18011C0A9
0x18011c087  mov     rax, [rcx]
0x18011c08a  mov     rax, [rax+80h]
0x18011c091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c096  mov     [rbx+60h], rax
0x18011c09a  test    rax, rax
0x18011c09d  jz      short loc_18011C0A9
0x18011c09f  mov     rax, [rax+38h]
0x18011c0a3  xor     edi, edi
0x18011c0a5  mov     [rbx+38h], rax
0x18011c0a9  lea     rcx, [rsp+488h+var_448]; this
0x18011c0ae  call    ??1FPUStateSaver@@QEAA@XZ; FPUStateSaver::~FPUStateSaver(void)
0x18011c0b3  mov     eax, edi
0x18011c0b5  jmp     short loc_18011C0BC
0x18011c0b7  mov     eax, 3
0x18011c0bc  mov     rcx, [rsp+488h+var_18]
0x18011c0c4  xor     rcx, rsp; StackCookie
0x18011c0c7  call    __security_check_cookie
0x18011c0cc  mov     rbx, [rsp+488h+arg_8]
0x18011c0d4  add     rsp, 480h
0x18011c0db  pop     rdi
0x18011c0dc  retn
```
