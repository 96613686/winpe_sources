# CDImageDeferredContext::DrawImage(DRAW_IMAGE_PARAMETERS const &,bool *)

- ea: `0x180096f00`
- end: `0x180097502`
- name: `?DrawImage@CDImageDeferredContext@@UEAAJAEBUDRAW_IMAGE_PARAMETERS@@PEA_N@Z`
- size: `1538`
- prototype: `__int64 __fastcall(CDImageDeferredContext *__hidden this, const struct DRAW_IMAGE_PARAMETERS *, bool *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001fd58`
- `0x1800389c0`
- `0x180096f00`
- `0x180097510`
- `0x180098a80`
- `0x1800a3e00`
- `0x18015d2bc`
- `0x180194334`
- `0x1802075a4`
- `0x180228434`
- `0x18025b100`
- `0x18025b124`
- `0x1802cc680`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800973b0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800973b0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180097480`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180097480`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18009739c`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18009739c`

## pseudocode

```c
__int64 __fastcall CDImageDeferredContext::DrawImage(
        CDImageDeferredContext *this,
        const struct DRAW_IMAGE_PARAMETERS *a2,
        bool *a3)
{
  char *v3; // rdi
  bool v4; // zf
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  _QWORD *v9; // r14
  unsigned __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rsi
  __int64 v16; // rcx
  CDImageContext *v17; // rcx
  struct CRenderIntermediate **v18; // r13
  int DrawImageCommandGraph; // eax
  __int64 v20; // r9
  int v21; // r15d
  struct IXmlWriter *v22; // rdx
  _QWORD *v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  _QWORD *v27; // rcx
  _QWORD *v28; // rax
  __int64 v29; // rdx
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  _QWORD *v32; // rax
  __int64 v33; // rax
  _QWORD *v34; // rax
  HRESULT v35; // eax
  ULONGLONG TickCount64; // rax
  bool v37; // [rsp+40h] [rbp-39h] BYREF
  _DWORD v38[3]; // [rsp+44h] [rbp-35h] BYREF
  char v39; // [rsp+50h] [rbp-29h]
  __int64 v40; // [rsp+58h] [rbp-21h] BYREF
  int v41; // [rsp+60h] [rbp-19h]
  char v42; // [rsp+68h] [rbp-11h]
  LPSTREAM ppstm; // [rsp+70h] [rbp-9h] BYREF
  __int64 v44; // [rsp+78h] [rbp-1h]
  bool *v45; // [rsp+80h] [rbp+7h]
  __int64 v46[2]; // [rsp+88h] [rbp+Fh] BYREF

  *a3 = 0;
  v3 = (char *)this + 16;
  v4 = *((_QWORD *)this + 7) == 0;
  v45 = a3;
  *(struct tagRECT *)v46 = g_emptyRectL;
  if ( !v4 )
  {
    v7 = *((_QWORD *)this + 12);
    v8 = *((_QWORD *)this + 13);
    if ( v7 )
      v8 = (v7 << 10) + v8 - 1024;
    if ( v8 > 0x32000 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 16LL))(*((_QWORD *)this + 21));
  }
  v9 = (_QWORD *)((char *)this + 120);
  if ( (_QWORD *)*v9 != v9 )
  {
    v10 = *((_QWORD *)this + 19) - *((_QWORD *)a2 + 10);
    if ( !v10 )
      v10 = *((unsigned int *)this + 40) - (unsigned __int64)*((unsigned int *)a2 + 22);
    if ( v10 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 16LL))(*((_QWORD *)this + 21));
  }
  v11 = *((_QWORD *)v3 + 5);
  v12 = *((_QWORD *)v3 + 11);
  *((_QWORD *)v3 + 3) = v11;
  *((_QWORD *)v3 + 4) = v12;
  if ( v11 && (unsigned __int64)(1024 - v12) >= 0x68 )
  {
    v13 = *((_QWORD *)this + 13);
  }
  else
  {
    v27 = (_QWORD *)*((_QWORD *)this + 8);
    v28 = (_QWORD *)((char *)this + 64);
    if ( v27 == (_QWORD *)((char *)this + 64) )
    {
      v34 = operator new(0x418u, (const struct std::nothrow_t *)&std::nothrow);
      *((_QWORD *)this + 7) = v34;
      v27 = v34;
      if ( !v34 )
        goto LABEL_51;
    }
    else
    {
      if ( (_QWORD *)v27[1] != v28 )
        goto LABEL_46;
      v29 = *v27;
      if ( *(_QWORD **)(*v27 + 8LL) != v27 )
        goto LABEL_46;
      *v28 = v29;
      *(_QWORD *)(v29 + 8) = v28;
      *((_QWORD *)this + 7) = v27;
    }
    v27[130] = 0;
    v30 = (_QWORD *)((char *)this + 80);
    v31 = *((_QWORD *)this + 10);
    if ( *(CDImageDeferredContext **)(v31 + 8) != (CDImageDeferredContext *)((char *)this + 80) )
      goto LABEL_46;
    v32 = (_QWORD *)*((_QWORD *)this + 7);
    v32[1] = v30;
    *v32 = v31;
    *(_QWORD *)(v31 + 8) = v32;
    *v30 = v32;
    v13 = 0;
    ++*((_QWORD *)this + 12);
    *((_QWORD *)this + 13) = 0;
  }
  v14 = *((_QWORD *)this + 7);
  *(_QWORD *)(v14 + v13 + 16) = 96;
  *((_QWORD *)this + 13) += 104LL;
  v15 = v13 + v14 + 24;
  if ( !v15 )
  {
LABEL_51:
    DoStackCapture(-2147024882);
    CArenaAllocator<1024>::SetScope(v3, v3 + 24);
    return 2147942414LL;
  }
  v16 = *((_QWORD *)this + 23);
  *(_QWORD *)(v15 + 24) = 0;
  *(_QWORD *)(v15 + 32) = 0;
  *(_QWORD *)(v15 + 40) = v3;
  *(_QWORD *)(v15 + 56) = v15 + 48;
  *(_QWORD *)(v15 + 48) = v15 + 48;
  *(_DWORD *)(v15 + 72) = 0;
  *(_QWORD *)(v15 + 80) = 0;
  *(_QWORD *)(v15 + 88) = 0;
  *(_QWORD *)(v15 + 64) = v16 + 1;
  v17 = (CDImageContext *)*((_QWORD *)this + 1);
  ++*((_QWORD *)this + 23);
  v38[0] = 0;
  v18 = (struct CRenderIntermediate **)(v15 + 16);
  *((_BYTE *)this + 176) = 1;
  DrawImageCommandGraph = CDImageContext::GetDrawImageCommandGraph(v17, (__int64)v46, v15 + 16, (__int64)v38);
  v20 = *((_QWORD *)this + 1);
  v21 = DrawImageCommandGraph;
  *((_BYTE *)this + 176) = 0;
  *(_QWORD *)&v38[1] = v20;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  ppstm = 0;
  v37 = 0;
  if ( DrawImageCommandGraph < 0 )
    goto LABEL_42;
  if ( !*v18 )
    goto LABEL_24;
  v21 = 0;
  if ( *(_BYTE *)(v20 + 4840) )
  {
    TickCount64 = GetTickCount64();
    v20 = *(_QWORD *)&v38[1];
    v44 = TickCount64;
    if ( !*(_QWORD *)(*(_QWORD *)&v38[1] + 4704LL)
      && (!*(_BYTE *)(*(_QWORD *)&v38[1] + 4841LL) || TickCount64 - qword_1805DBF08 > 0x3E8) )
    {
      v35 = CreateStreamOnHGlobal(0, 1, &ppstm);
      v21 = v35;
      if ( v35 < 0
        || (OutputDebugStringA("\n\nD2D Imaging Render Log:\n"),
            qword_1805DBF08 = v44,
            v35 = (*(__int64 (__fastcall **)(_QWORD, LPSTREAM, _QWORD))(**(_QWORD **)&v38[1] + 32LL))(
                    *(_QWORD *)&v38[1],
                    ppstm,
                    *(unsigned int *)(*(_QWORD *)&v38[1] + 4844LL)),
            v21 = v35,
            v35 < 0) )
      {
LABEL_58:
        DoStackCapture(v35);
        goto LABEL_19;
      }
      v20 = *(_QWORD *)&v38[1];
    }
  }
  v22 = *(struct IXmlWriter **)(v20 + 4704);
  if ( !v22 )
    goto LABEL_19;
  v35 = CRenderGraphLogger::BeginLog(
          (CRenderGraphLogger *)&v40,
          v22,
          L"BatchedRenderGraph",
          (*(_DWORD *)(v20 + 4712) & 8) != 0,
          (*(_DWORD *)(v20 + 4712) & 0x20) != 0,
          (*(_DWORD *)(v20 + 4712) & 0x10) != 0,
          (*(_DWORD *)(v20 + 4712) & 0x40) != 0);
  v21 = v35;
  if ( v35 < 0 )
    goto LABEL_58;
  v39 = 1;
LABEL_19:
  if ( v39 )
    CRenderGraphLogger::LogGraph((CRenderGraphLogger *)&v40, *v18, *(_BYTE *)(*((_QWORD *)this + 1) + 330LL));
  if ( v21 >= 0 )
  {
    if ( (unsigned int)(v38[0] - 1) > 0x1FF
      || (v21 = CDImageDeferredContext::TryAtlasOperation(this, (struct CDImageDeferredContext::COperation *)v15, &v37),
          v21 >= 0) )
    {
LABEL_24:
      if ( *v18 )
      {
LABEL_25:
        (***((void (__fastcall ****)(_QWORD, _QWORD, __int64 *))this + 21))(*((_QWORD *)this + 21), *(_QWORD *)a2, v46);
        if ( !*v18 )
        {
          CDImageDeferredContext::COperation::ReleaseResources(
            (CDImageDeferredContext::COperation *)v15,
            (unsigned __int64 *)this + 26);
          CArenaAllocator<1024>::SetScope(v3, v3 + 24);
          CRenderLogScope::FinishLog((CRenderLogScope *)&v38[1]);
          ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&ppstm);
          ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v40);
          return 0;
        }
        v23 = (_QWORD *)*((_QWORD *)this + 16);
        if ( (_QWORD *)*v23 == v9 )
        {
          *(_QWORD *)(v15 + 8) = v23;
          *(_QWORD *)v15 = v9;
          *v23 = v15;
          *((_QWORD *)this + 16) = v15;
          ++*((_DWORD *)this + 54);
          v24 = *((_QWORD *)this + 21);
          *((_QWORD *)this + 19) = *((_QWORD *)a2 + 10);
          *((_DWORD *)this + 40) = *((_DWORD *)a2 + 22);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
          if ( v39 )
            CRenderGraphLogger::LogAtlasing(
              (CRenderGraphLogger *)&v40,
              v37,
              *((_DWORD *)this + 36),
              *((_DWORD *)this + 37));
          *v45 = 1;
          CRenderLogScope::FinishLog((CRenderLogScope *)&v38[1]);
          ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&ppstm);
          ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v40);
          if ( v3 )
          {
            if ( v21 < 0 )
            {
              CArenaAllocator<1024>::SetScope(v3, v3 + 24);
            }
            else
            {
              v25 = *((_QWORD *)v3 + 5);
              if ( !v25 || v25 == *((_QWORD *)v3 + 9) )
                ++*((_QWORD *)v3 + 12);
              else
                ++*(_QWORD *)(**((_QWORD **)v3 + 8) + 1040LL);
            }
          }
          return 0;
        }
LABEL_46:
        __fastfail(3u);
      }
    }
  }
LABEL_42:
  CDImageDeferredContext::COperation::ReleaseResources(
    (CDImageDeferredContext::COperation *)v15,
    (unsigned __int64 *)this + 26);
  v33 = *((_QWORD *)this + 23);
  if ( (_QWORD *)*v9 == v9 )
    *((_QWORD *)this + 24) = v33;
  else
    *(_QWORD *)(*((_QWORD *)this + 16) + 64LL) = v33;
  if ( v21 >= 0 )
    goto LABEL_25;
  DoStackCapture(v21);
  CRenderLogScope::FinishLog((CRenderLogScope *)&v38[1]);
  ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&ppstm);
  ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(&v40);
  CArenaAllocator<1024>::SetScope(v3, v3 + 24);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180096f00  push    rbp
0x180096f02  push    rbx
0x180096f03  push    rdi
0x180096f04  push    r12
0x180096f06  push    r13
0x180096f08  push    r14
0x180096f0a  push    r15
0x180096f0c  lea     rbp, [rsp-27h]
0x180096f11  sub     rsp, 0A0h
0x180096f18  mov     rax, cs:__security_cookie
0x180096f1f  xor     rax, rsp
0x180096f22  mov     [rbp+57h+var_38], rax
0x180096f26  mov     byte ptr [r8], 0
0x180096f2a  lea     rdi, [rcx+10h]
0x180096f2e  cmp     qword ptr [rdi+28h], 0
0x180096f33  mov     r12, rdx
0x180096f36  movups  xmm0, cs:?g_emptyRectL@@3UtagRECT@@B; tagRECT const g_emptyRectL
0x180096f3d  mov     [rbp+57h+var_50], r8
0x180096f41  mov     rbx, rcx
0x180096f44  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x180096f48  jz      short loc_180096F72
0x180096f4a  mov     rax, [rbx+60h]
0x180096f4e  mov     rcx, [rcx+68h]
0x180096f52  test    rax, rax
0x180096f55  jz      short loc_180096F65
0x180096f57  shl     rax, 0Ah
0x180096f5b  add     rcx, 0FFFFFFFFFFFFFC00h
0x180096f62  add     rcx, rax
0x180096f65  cmp     rcx, 32000h
0x180096f6c  ja      loc_180097468
0x180096f72  lea     r14, [rbx+78h]
0x180096f76  cmp     [r14], r14
0x180096f79  jz      short loc_180096FA0
0x180096f7b  mov     rcx, [rbx+98h]
0x180096f82  sub     rcx, [r12+50h]
0x180096f87  jnz     short loc_180096F97
0x180096f89  mov     ecx, [rbx+0A0h]
0x180096f8f  mov     eax, [r12+58h]
0x180096f94  sub     rcx, rax
0x180096f97  test    rcx, rcx
0x180096f9a  jnz     loc_180097379
0x180096fa0  mov     rax, [rdi+28h]
0x180096fa4  xor     r13d, r13d
0x180096fa7  mov     rcx, [rdi+58h]
0x180096fab  mov     [rsp+0D0h+arg_18], rsi
0x180096fb3  mov     [rdi+18h], rax
0x180096fb7  mov     [rdi+20h], rcx
0x180096fbb  test    rax, rax
0x180096fbe  jz      loc_180097200
0x180096fc4  mov     eax, 400h
0x180096fc9  sub     rax, rcx
0x180096fcc  cmp     rax, 68h ; 'h'
0x180096fd0  jb      loc_180097200
0x180096fd6  mov     rcx, [rbx+68h]
0x180096fda  mov     rax, [rbx+38h]
0x180096fde  mov     qword ptr [rax+rcx+10h], 60h ; '`'
0x180096fe7  lea     rsi, [rax+18h]
0x180096feb  add     qword ptr [rbx+68h], 68h ; 'h'
0x180096ff0  add     rsi, rcx
0x180096ff3  jz      loc_180097359
0x180096ff9  mov     rcx, [rbx+0B8h]
0x180097000  lea     r9, [rsi+18h]
0x180097004  mov     [r9], r13
0x180097007  lea     rax, [rsi+30h]
0x18009700b  mov     [r9+8], r13
0x18009700f  inc     rcx
0x180097012  mov     [r9+10h], rdi
0x180097016  mov     r8, r12
0x180097019  mov     [rax+8], rax
0x18009701d  mov     rdx, rdi
0x180097020  mov     [rax], rax
0x180097023  lea     rax, [rbp+57h+var_8C]
0x180097027  mov     [rsi+48h], r13d
0x18009702b  mov     [rsi+50h], r13
0x18009702f  mov     [rsi+58h], r13
0x180097033  mov     qword ptr [rsp+0D0h+var_A0], rax; __int64
0x180097038  lea     rax, [rbp+57h+var_48]
0x18009703c  mov     [rsi+40h], rcx
0x180097040  mov     rcx, [rbx+8]; this
0x180097044  inc     qword ptr [rbx+0B8h]
0x18009704b  mov     dword ptr [rbp+57h+var_8C], r13d
0x18009704f  lea     r13, [rsi+10h]
0x180097053  mov     qword ptr [rsp+0D0h+var_A8], r13; __int64
0x180097058  mov     qword ptr [rsp+0D0h+var_B0], rax; __int64
0x18009705d  mov     byte ptr [rbx+0B0h], 1
0x180097064  call    ?GetDrawImageCommandGraph@CDImageContext@@QEAAJPEAV?$CArenaAllocator@$0EAA@@@AEBUDRAW_IMAGE_PARAMETERS@@AEAV?$CRendererArenaArray@V?$CRefCountPtr@VBitmapRealization@@@@V?$CDefaultTraits@V?$CRefCountPtr@VBitmapRealization@@@@@@@@PEAUtagRECT@@PEAPEAVCRenderIntermediate@@PEAI@Z; CDImageContext::GetDrawImageCommandGraph(CArenaAllocator<1024> *,DRAW_IMAGE_PARAMETERS const &,CRendererArenaArray<CRefCountPtr<BitmapRealization>,CDefaultTraits<CRefCountPtr<BitmapRealization>>> &,tagRECT *,CRenderIntermediate * *,uint *)
0x180097069  mov     r9, [rbx+8]
0x18009706d  mov     r15d, eax
0x180097070  xor     eax, eax
0x180097072  mov     byte ptr [rbx+0B0h], 0
0x180097079  mov     qword ptr [rbp+57h+var_8C+4], r9
0x18009707d  mov     [rbp+57h+var_80], 0
0x180097081  mov     [rbp+57h+var_78], rax
0x180097085  mov     [rbp+57h+var_70], eax
0x180097088  mov     [rbp+57h+var_68], al
0x18009708b  mov     [rbp+57h+ppstm], rax
0x18009708f  mov     [rbp+57h+var_90], al
0x180097092  test    r15d, r15d
0x180097095  js      loc_1800972A8
0x18009709b  cmp     [r13+0], rax
0x18009709f  jz      short loc_1800970FA
0x1800970a1  mov     r15d, eax
0x1800970a4  cmp     [r9+12E8h], al
0x1800970ab  jnz     loc_180097480
0x1800970b1  mov     rdx, [r9+1260h]; struct IXmlWriter *
0x1800970b8  test    rdx, rdx
0x1800970bb  jnz     loc_180097404
0x1800970c1  cmp     [rbp+57h+var_80], 0
0x1800970c5  jnz     loc_1800974C4
0x1800970cb  test    r15d, r15d
0x1800970ce  js      loc_1800972A8
0x1800970d4  mov     eax, dword ptr [rbp+57h+var_8C]
0x1800970d7  dec     eax
0x1800970d9  cmp     eax, 1FFh
0x1800970de  ja      short loc_1800970FA
0x1800970e0  lea     r8, [rbp+57h+var_90]; bool *
0x1800970e4  mov     rdx, rsi; struct CDImageDeferredContext::COperation *
0x1800970e7  mov     rcx, rbx; this
0x1800970ea  call    ?TryAtlasOperation@CDImageDeferredContext@@AEAAJPEAVCOperation@1@PEA_N@Z; CDImageDeferredContext::TryAtlasOperation(CDImageDeferredContext::COperation *,bool *)
0x1800970ef  mov     r15d, eax
0x1800970f2  test    eax, eax
0x1800970f4  js      loc_1800972A8
0x1800970fa  cmp     qword ptr [r13+0], 0
0x1800970ff  jz      loc_1800972A8
0x180097105  mov     rcx, [rbx+0A8h]
0x18009710c  lea     r8, [rbp+57h+var_48]
0x180097110  mov     rdx, [r12]
0x180097114  mov     rax, [rcx]
0x180097117  mov     rax, [rax]
0x18009711a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009711f  cmp     qword ptr [r13+0], 0
0x180097124  jz      loc_18009726D
0x18009712a  mov     rax, [r14+8]
0x18009712e  cmp     [rax], r14
0x180097131  jnz     loc_18009730A
0x180097137  mov     [rsi+8], rax
0x18009713b  mov     [rsi], r14
0x18009713e  mov     [rax], rsi
0x180097141  mov     [r14+8], rsi
0x180097145  inc     dword ptr [rbx+0D8h]
0x18009714b  movsd   xmm0, qword ptr [r12+50h]
0x180097152  mov     rcx, [rbx+0A8h]
0x180097159  movsd   qword ptr [rbx+98h], xmm0
0x180097161  mov     eax, [r12+58h]
0x180097166  mov     [rbx+0A0h], eax
0x18009716c  mov     rax, [rcx]
0x18009716f  mov     rax, [rax+8]
0x180097173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097178  cmp     [rbp+57h+var_80], 0
0x18009717c  jnz     loc_1800974E2
0x180097182  mov     rax, [rbp+57h+var_50]
0x180097186  lea     rcx, [rbp+57h+var_8C+4]; this
0x18009718a  mov     byte ptr [rax], 1
0x18009718d  call    ?FinishLog@CRenderLogScope@@AEAAJXZ; CRenderLogScope::FinishLog(void)
0x180097192  lea     rcx, [rbp+57h+ppstm]; void *
0x180097196  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x18009719b  lea     rcx, [rbp+57h+var_78]; void *
0x18009719f  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800971a4  test    rdi, rdi
0x1800971a7  jz      short loc_1800971D7
0x1800971a9  test    r15d, r15d
0x1800971ac  js      loc_180097311
0x1800971b2  mov     rax, [rdi+28h]
0x1800971b6  test    rax, rax
0x1800971b9  jz      loc_180097322
0x1800971bf  cmp     rax, [rdi+48h]
0x1800971c3  jz      loc_180097322
0x1800971c9  mov     rax, [rdi+40h]
0x1800971cd  mov     rcx, [rax]
0x1800971d0  inc     qword ptr [rcx+410h]
0x1800971d7  xor     eax, eax
0x1800971d9  mov     rsi, [rsp+0D0h+arg_18]
0x1800971e1  mov     rcx, [rbp+57h+var_38]
0x1800971e5  xor     rcx, rsp; StackCookie
0x1800971e8  call    __security_check_cookie
0x1800971ed  add     rsp, 0A0h
0x1800971f4  pop     r15
0x1800971f6  pop     r14
0x1800971f8  pop     r13
0x1800971fa  pop     r12
0x1800971fc  pop     rdi
0x1800971fd  pop     rbx
0x1800971fe  pop     rbp
0x1800971ff  retn
0x180097200  mov     rcx, [rbx+40h]
0x180097204  lea     rax, [rbx+40h]
0x180097208  cmp     rcx, rax
0x18009720b  jz      loc_180097338
0x180097211  cmp     [rcx+8], rax
0x180097215  jnz     loc_18009730A
0x18009721b  mov     rdx, [rcx]
0x18009721e  cmp     [rdx+8], rcx
0x180097222  jnz     loc_18009730A
0x180097228  mov     [rax], rdx
0x18009722b  mov     [rdx+8], rax
0x18009722f  mov     [rbx+38h], rcx
0x180097233  mov     [rcx+410h], r13
0x18009723a  lea     rcx, [rbx+50h]
0x18009723e  mov     rdx, [rcx]
0x180097241  cmp     [rdx+8], rcx
0x180097245  jnz     loc_18009730A
0x18009724b  mov     rax, [rbx+38h]
0x18009724f  mov     [rax+8], rcx
0x180097253  mov     [rax], rdx
0x180097256  mov     [rdx+8], rax
0x18009725a  mov     [rcx], rax
0x18009725d  mov     rcx, r13
0x180097260  inc     qword ptr [rbx+60h]
0x180097264  mov     [rbx+68h], r13
0x180097268  jmp     loc_180096FDA
0x18009726d  lea     rdx, [rbx+0D0h]; unsigned __int64 *
0x180097274  mov     rcx, rsi; this
0x180097277  call    ?ReleaseResources@COperation@CDImageDeferredContext@@QEAAXPEA_K@Z; CDImageDeferredContext::COperation::ReleaseResources(unsigned __int64 *)
0x18009727c  lea     rdx, [rdi+18h]
0x180097280  mov     rcx, rdi
0x180097283  call    ?SetScope@?$CArenaAllocator@$0EAA@@@AEAAXAEBUSCOPE@1@@Z; CArenaAllocator<1024>::SetScope(CArenaAllocator<1024>::SCOPE const &)
0x180097288  lea     rcx, [rbp+57h+var_8C+4]; this
0x18009728c  call    ?FinishLog@CRenderLogScope@@AEAAJXZ; CRenderLogScope::FinishLog(void)
0x180097291  lea     rcx, [rbp+57h+ppstm]; void *
0x180097295  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x18009729a  lea     rcx, [rbp+57h+var_78]; void *
0x18009729e  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800972a3  jmp     loc_1800971D7
0x1800972a8  lea     rdx, [rbx+0D0h]; unsigned __int64 *
0x1800972af  mov     rcx, rsi; this
0x1800972b2  call    ?ReleaseResources@COperation@CDImageDeferredContext@@QEAAXPEA_K@Z; CDImageDeferredContext::COperation::ReleaseResources(unsigned __int64 *)
0x1800972b7  mov     rax, [rbx+0B8h]
0x1800972be  cmp     [r14], r14
0x1800972c1  jnz     short loc_18009732B
0x1800972c3  mov     [rbx+0C0h], rax
0x1800972ca  test    r15d, r15d
0x1800972cd  jns     loc_180097105
0x1800972d3  mov     ecx, r15d; int
0x1800972d6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800972db  lea     rcx, [rbp+57h+var_8C+4]; this
0x1800972df  call    ?FinishLog@CRenderLogScope@@AEAAJXZ; CRenderLogScope::FinishLog(void)
0x1800972e4  lea     rcx, [rbp+57h+ppstm]; void *
0x1800972e8  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800972ed  lea     rcx, [rbp+57h+var_78]; void *
0x1800972f1  call    ??1?$CComPtr@UIWICBitmap@@@ATL@@QEAA@XZ; ATL::CComPtr<IWICBitmap>::~CComPtr<IWICBitmap>(void)
0x1800972f6  lea     rdx, [rdi+18h]
0x1800972fa  mov     rcx, rdi
0x1800972fd  call    ?SetScope@?$CArenaAllocator@$0EAA@@@AEAAXAEBUSCOPE@1@@Z; CArenaAllocator<1024>::SetScope(CArenaAllocator<1024>::SCOPE const &)
0x180097302  mov     eax, r15d
0x180097305  jmp     loc_1800971D9
0x18009730a  mov     ecx, 3
0x18009730f  int     29h; Win8: RtlFailFast(ecx)
0x180097311  lea     rdx, [rdi+18h]
0x180097315  mov     rcx, rdi
0x180097318  call    ?SetScope@?$CArenaAllocator@$0EAA@@@AEAAXAEBUSCOPE@1@@Z; CArenaAllocator<1024>::SetScope(CArenaAllocator<1024>::SCOPE const &)
0x18009731d  jmp     loc_1800971D7
0x180097322  inc     qword ptr [rdi+60h]
0x180097326  jmp     loc_1800971D7
0x18009732b  mov     rcx, [rbx+80h]
0x180097332  mov     [rcx+40h], rax
0x180097336  jmp     short loc_1800972CA
0x180097338  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009733f  mov     ecx, 418h; unsigned __int64
0x180097344  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180097349  mov     [rbx+38h], rax
0x18009734d  mov     rcx, rax
0x180097350  test    rax, rax
0x180097353  jnz     loc_180097233
0x180097359  mov     ecx, 8007000Eh; int
0x18009735e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180097363  lea     rdx, [rdi+18h]
0x180097367  mov     rcx, rdi
0x18009736a  call    ?SetScope@?$CArenaAllocator@$0EAA@@@AEAAXAEBUSCOPE@1@@Z; CArenaAllocator<1024>::SetScope(CArenaAllocator<1024>::SCOPE const &)
0x18009736f  mov     eax, 8007000Eh
0x180097374  jmp     loc_1800971D9
0x180097379  mov     rcx, [rbx+0A8h]
0x180097380  mov     rax, [rcx]
0x180097383  mov     rax, [rax+10h]
0x180097387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009738c  jmp     loc_180096FA0
0x180097391  lea     r8, [rbp+57h+ppstm]; ppstm
0x180097395  mov     edx, 1; fDeleteOnRelease
0x18009739a  xor     ecx, ecx; hGlobal
0x18009739c  call    cs:__imp_CreateStreamOnHGlobal
0x1800973a2  mov     r15d, eax
0x1800973a5  test    eax, eax
0x1800973a7  js      short loc_1800973EF
0x1800973a9  lea     rcx, OutputString; "\n\nD2D Imaging Render Log:\n"
0x1800973b0  call    cs:__imp_OutputDebugStringA
0x1800973b6  mov     rcx, qword ptr [rbp+57h+var_8C+4]
0x1800973ba  mov     rax, [rbp+57h+var_58]
0x1800973be  mov     rdx, [rbp+57h+ppstm]
0x1800973c2  mov     cs:qword_1805DBF08, rax
0x1800973c9  mov     rax, [rcx]
0x1800973cc  mov     r8d, [rcx+12ECh]
0x1800973d3  mov     rax, [rax+20h]
0x1800973d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800973dc  mov     r15d, eax
0x1800973df  test    eax, eax
0x1800973e1  jns     short loc_1800973FB
0x1800973e3  mov     ecx, eax; int
0x1800973e5  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800973ea  jmp     loc_1800970C1
0x1800973ef  mov     ecx, eax; int
0x1800973f1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
  ... truncated ...
```
