# CThreadInputMgr::OnAccFocusEvent(HWND__ *,long,long)

- ea: `0x180027f40`
- end: `0x1800283fc`
- name: `?OnAccFocusEvent@CThreadInputMgr@@QEAAXPEAUHWND__@@JJ@Z`
- size: `1212`
- prototype: `void __fastcall(CThreadInputMgr *__hidden this, HWND hWnd, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800279d0`

## callees

- `0x18000e638`
- `0x180018640`
- `0x180024abc`
- `0x180027f40`
- `0x180033870`
- `0x18010a010`

## import_xrefs

- `ntdll!RtlUnhandledExceptionFilter` at `0x180107677`
- `ntdll!RtlUnhandledExceptionFilter` at `0x180107677`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800282d7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800282d7`
- `USER32!SetRect` at `0x18002827e`
- `USER32!SetRect` at `0x18002827e`
- `USER32!GetPropW` at `0x180028001`
- `USER32!GetPropW` at `0x180028001`
- `USER32!SetRectEmpty` at `0x180027fc1`
- `USER32!SetRectEmpty` at `0x180027fc1`
- `USER32!GetWindowThreadProcessId` at `0x180027fe9`
- `USER32!GetWindowThreadProcessId` at `0x180027fe9`
- `OLEAUT32!__imp_VariantClear` at `0x1800282a1`
- `OLEAUT32!__imp_VariantClear` at `0x1800282a1`

## string_xrefs

- `0x1800282b5`: `Oleacc.dll`
- `0x1800282d0`: `AccessibleObjectFromEvent`

## pseudocode

```c
void __fastcall CThreadInputMgr::OnAccFocusEvent(CThreadInputMgr *this, HWND hWnd, unsigned int a3, unsigned int a4)
{
  _BYTE *v6; // rsi
  char v7; // r13
  _QWORD *v8; // r12
  _BYTE *v9; // r14
  int v10; // edi
  HINSTANCE ProcAddress; // rax
  HMODULE v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // ecx
  __int64 v16; // rax
  int yTop; // [rsp+44h] [rbp-114h] BYREF
  int v18; // [rsp+48h] [rbp-110h] BYREF
  int xLeft; // [rsp+4Ch] [rbp-10Ch] BYREF
  int v20; // [rsp+50h] [rbp-108h] BYREF
  __int64 *v21; // [rsp+58h] [rbp-100h] BYREF
  VARIANTARG pvarg; // [rsp+60h] [rbp-F8h] BYREF
  _QWORD *v23; // [rsp+80h] [rbp-D8h]
  _BYTE *v24; // [rsp+88h] [rbp-D0h]
  __int128 v25; // [rsp+90h] [rbp-C8h] BYREF
  __int64 v26; // [rsp+A0h] [rbp-B8h]
  char *v27; // [rsp+B0h] [rbp-A8h]
  VARIANTARG v28; // [rsp+C0h] [rbp-98h] BYREF
  VARIANTARG v29; // [rsp+E0h] [rbp-78h] BYREF
  VARIANTARG v30; // [rsp+100h] [rbp-58h] BYREF

  v6 = (char *)this + 3053;
  v27 = (char *)this + 3053;
  if ( *((_BYTE *)this + 3053)
    && !*((_BYTE *)this + 3055)
    && ((v9 = (char *)this + 3064, v8 = (_QWORD *)((char *)this + 3032), *((_BYTE *)this + 3064))
     || *((_QWORD *)this + 372) == *v8) )
  {
    v7 = 1;
  }
  else
  {
    v7 = 0;
    v8 = (_QWORD *)((char *)this + 3032);
    v9 = (char *)this + 3064;
  }
  v24 = v9;
  v23 = v8;
  *v8 = 0;
  *((_QWORD *)this + 380) = 0;
  *v6 = 0;
  *((_BYTE *)this + 3054) = 0;
  SetRectEmpty((LPRECT)((char *)this + 3096));
  if ( !*v9 || !*((_BYTE *)this + 3071) )
  {
    if ( hWnd )
    {
      v10 = *(_DWORD *)(*((_QWORD *)this + 26) + 104LL);
      if ( GetWindowThreadProcessId(hWnd, 0) == v10
        && !GetPropW(hWnd, L"MSCTFMSAAIgnore")
        && ((int)(a3 + 0x80000000) < 0 || a3 == -4) )
      {
        ATL::CComPtr<ITipProxy>::CComPtr<ITipProxy>(&v21);
        memset(&pvarg, 0, sizeof(pvarg));
        v25 = 0;
        v26 = 0;
        ProcAddress = (HINSTANCE)qword_180141318;
        v12 = g_hOleacc;
        if ( !qword_180141318 || !g_hOleacc )
        {
          if ( g_hOleacc
            || (ProcAddress = LoadSystemLibrary(L"Oleacc.dll"), v12 = ProcAddress, (g_hOleacc = ProcAddress) != 0) )
          {
            ProcAddress = (HINSTANCE)GetProcAddress(v12, "AccessibleObjectFromEvent");
            qword_180141318 = (__int64)ProcAddress;
          }
          else
          {
            qword_180141318 = 0;
          }
        }
        if ( !ProcAddress
          || ((unsigned int (__fastcall *)(HWND, _QWORD, _QWORD, __int64 **, VARIANTARG *))ProcAddress)(
               hWnd,
               a3,
               a4,
               &v21,
               &pvarg)
          || !v21 )
        {
          goto LABEL_38;
        }
        v13 = *v21;
        v28 = pvarg;
        if ( !(*(unsigned int (__fastcall **)(__int64 *, VARIANTARG *, __int128 *))(v13 + 104))(v21, &v28, &v25)
          && (_WORD)v25 == 3
          && (DWORD2(v25) == 42 || *v9 && DWORD2(v25) == 46 || *((_BYTE *)this + 3066) && DWORD2(v25) == 15) )
        {
          *v8 = hWnd;
          *((_DWORD *)this + 760) = a3;
          *((_DWORD *)this + 761) = a4;
          *v6 = 1;
          v14 = *v21;
          v29 = pvarg;
          if ( !(*(unsigned int (__fastcall **)(__int64 *, VARIANTARG *, __int128 *))(v14 + 112))(v21, &v29, &v25)
            && (_WORD)v25 == 3 )
          {
            v15 = DWORD2(v25);
            *((_BYTE *)this + 3055) = (BYTE8(v25) & 0x40) != 0;
            *((_BYTE *)this + 3054) = (v15 & 0x20000000) != 0;
          }
          xLeft = 0;
          yTop = 0;
          v20 = 0;
          v18 = 0;
          v16 = *v21;
          v30 = pvarg;
          if ( (*(int (__fastcall **)(__int64 *, int *, int *, int *, int *, VARIANTARG *))(v16 + 176))(
                 v21,
                 &xLeft,
                 &yTop,
                 &v20,
                 &v18,
                 &v30) >= 0 )
            SetRect((LPRECT)((char *)this + 3096), xLeft, yTop, xLeft + v20, yTop + v18);
        }
        if ( pvarg.vt != 11 )
        {
          if ( pvarg.vt != 13 )
          {
            switch ( pvarg.vt )
            {
              case 0u:
              case 1u:
              case 2u:
              case 3u:
              case 4u:
              case 5u:
              case 6u:
              case 7u:
              case 0x10u:
              case 0x11u:
              case 0x12u:
              case 0x13u:
              case 0x14u:
              case 0x15u:
              case 0x16u:
              case 0x17u:
                goto LABEL_19;
              default:
                VariantClear(&pvarg);
                pvarg.vt = 0;
                break;
            }
            goto LABEL_38;
          }
          if ( pvarg.llVal )
            (*(void (__fastcall **)(LONGLONG))(*pvarg.pllVal + 16))(pvarg.llVal);
        }
LABEL_19:
        pvarg.vt = 0;
LABEL_38:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
      }
    }
  }
  if ( v7 || *v6 && !*((_BYTE *)this + 3055) && (*v9 || *((_QWORD *)this + 372) == *v8) )
    CThreadInputMgr::_OnDocumentFocusChanged(this);
}

```

## disassembly

```asm
0x180027f40  mov     [rsp+arg_18], r9d
0x180027f45  mov     [rsp+arg_10], r8d
0x180027f4a  mov     [rsp+arg_0], rcx
0x180027f4f  push    rbx
0x180027f50  push    rsi
0x180027f51  push    rdi
0x180027f52  push    r12
0x180027f54  push    r13
0x180027f56  push    r14
0x180027f58  push    r15
0x180027f5a  sub     rsp, 120h
0x180027f61  mov     r15, rdx
0x180027f64  mov     rbx, rcx
0x180027f67  lea     rsi, [rcx+0BEDh]
0x180027f6e  mov     [rsp+158h+var_A8], rsi
0x180027f76  cmp     byte ptr [rsi], 0
0x180027f79  jnz     loc_18002836A
0x180027f7f  xor     r13b, r13b
0x180027f82  lea     r12, [rcx+0BD8h]
0x180027f89  lea     r14, [rcx+0BF8h]
0x180027f90  mov     [rsp+158h+var_D0], r14
0x180027f98  mov     [rsp+158h+var_D8], r12
0x180027fa0  mov     [rsp+158h+var_118], r13b
0x180027fa5  xor     eax, eax
0x180027fa7  mov     [r12], rax
0x180027fab  mov     [rcx+0BE0h], rax
0x180027fb2  mov     [rsi], al
0x180027fb4  mov     [rcx+0BEEh], al
0x180027fba  add     rcx, 0C18h; lprc
0x180027fc1  call    cs:__imp_SetRectEmpty
0x180027fc7  cmp     byte ptr [r14], 0
0x180027fcb  jnz     loc_1800283CA
0x180027fd1  test    r15, r15
0x180027fd4  jz      loc_180028342
0x180027fda  mov     rax, [rbx+0D0h]
0x180027fe1  mov     edi, [rax+68h]
0x180027fe4  xor     edx, edx; lpdwProcessId
0x180027fe6  mov     rcx, r15; hWnd
0x180027fe9  call    cs:__imp_GetWindowThreadProcessId
0x180027fef  cmp     eax, edi
0x180027ff1  jnz     loc_180028342
0x180027ff7  lea     rdx, aMsctfmsaaignor; "MSCTFMSAAIgnore"
0x180027ffe  mov     rcx, r15; hWnd
0x180028001  call    cs:__imp_GetPropW
0x180028007  test    rax, rax
0x18002800a  jnz     loc_180028342
0x180028010  mov     ecx, 80000000h
0x180028015  mov     edi, [rsp+158h+arg_10]
0x18002801c  lea     eax, [rdi+rcx]
0x18002801f  test    ecx, eax
0x180028021  jz      loc_18002835F
0x180028027  lea     rcx, [rsp+158h+var_100]
0x18002802c  call    ??0?$CComPtr@UITipProxy@@@ATL@@QEAA@XZ; ATL::CComPtr<ITipProxy>::CComPtr<ITipProxy>(void)
0x180028031  xorps   xmm0, xmm0
0x180028034  xor     eax, eax
0x180028036  movups  xmmword ptr [rsp+158h+pvarg], xmm0
0x18002803b  mov     qword ptr [rsp+158h+pvarg+10h], rax
0x180028040  xorps   xmm1, xmm1
0x180028043  movups  [rsp+158h+var_C8], xmm1
0x18002804b  mov     [rsp+158h+var_B8], rax
0x180028053  mov     rax, cs:qword_180141318
0x18002805a  mov     rcx, cs:?g_hOleacc@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hOleacc
0x180028061  test    rax, rax
0x180028064  jz      loc_1800282B0
0x18002806a  test    rcx, rcx
0x18002806d  jz      loc_1800282B0
0x180028073  test    rax, rax
0x180028076  jz      loc_180028310
0x18002807c  lea     rcx, [rsp+158h+pvarg]
0x180028081  mov     qword ptr [rsp+158h+yBottom], rcx
0x180028086  lea     r9, [rsp+158h+var_100]
0x18002808b  mov     r8d, [rsp+158h+arg_18]
0x180028093  mov     edx, edi
0x180028095  mov     rcx, r15
0x180028098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002809d  test    eax, eax
0x18002809f  jnz     loc_180028310
0x1800280a5  mov     rcx, [rsp+158h+var_100]
0x1800280aa  test    rcx, rcx
0x1800280ad  jz      loc_180028310
0x1800280b3  mov     rax, [rcx]
0x1800280b6  movups  xmm0, xmmword ptr [rsp+158h+pvarg]
0x1800280bb  movaps  [rsp+158h+var_98], xmm0
0x1800280c3  movsd   xmm1, qword ptr [rsp+158h+pvarg+10h]
0x1800280c9  movsd   [rsp+158h+var_88], xmm1
0x1800280d2  lea     r8, [rsp+158h+var_C8]
0x1800280da  lea     rdx, [rsp+158h+var_98]
0x1800280e2  mov     rax, [rax+68h]
0x1800280e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280eb  test    eax, eax
0x1800280ed  jnz     short loc_180028119
0x1800280ef  cmp     word ptr [rsp+158h+var_C8], 3
0x1800280f8  jnz     short loc_180028119
0x1800280fa  mov     eax, dword ptr [rsp+158h+var_C8+8]
0x180028101  cmp     eax, 2Ah ; '*'
0x180028104  jz      short loc_180028155
0x180028106  cmp     byte ptr [r14], 0
0x18002810a  jnz     short loc_180028150
0x18002810c  cmp     byte ptr [rbx+0BFAh], 0
0x180028113  jnz     loc_180028289
0x180028119  movzx   eax, word ptr [rsp+158h+pvarg]
0x18002811e  cmp     eax, 0Bh
0x180028121  jnz     short loc_18002812F
0x180028123  xor     eax, eax; jumptable 000000018002830E cases 0-7,16-23
0x180028125  mov     word ptr [rsp+158h+pvarg], ax
0x18002812a  jmp     loc_180028310
0x18002812f  cmp     eax, 0Dh
0x180028132  jnz     loc_180028297
0x180028138  mov     rcx, qword ptr [rsp+158h+pvarg+8]
0x18002813d  test    rcx, rcx
0x180028140  jz      short loc_180028123; jumptable 000000018002830E cases 0-7,16-23
0x180028142  mov     rax, [rcx]
0x180028145  mov     rax, [rax+10h]
0x180028149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002814e  jmp     short loc_180028123; jumptable 000000018002830E cases 0-7,16-23
0x180028150  cmp     eax, 2Eh ; '.'
0x180028153  jnz     short loc_18002810C
0x180028155  mov     [r12], r15
0x180028159  mov     [rbx+0BE0h], edi
0x18002815f  mov     eax, [rsp+158h+arg_18]
0x180028166  mov     [rbx+0BE4h], eax
0x18002816c  mov     byte ptr [rsi], 1
0x18002816f  mov     rcx, [rsp+158h+var_100]
0x180028174  mov     rax, [rcx]
0x180028177  movups  xmm0, xmmword ptr [rsp+158h+pvarg]
0x18002817c  movaps  [rsp+158h+var_78], xmm0
0x180028184  movsd   xmm1, qword ptr [rsp+158h+pvarg+10h]
0x18002818a  movsd   [rsp+158h+var_68], xmm1
0x180028193  lea     r8, [rsp+158h+var_C8]
0x18002819b  lea     rdx, [rsp+158h+var_78]
0x1800281a3  mov     rax, [rax+70h]
0x1800281a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281ac  test    eax, eax
0x1800281ae  jnz     short loc_1800281DB
0x1800281b0  cmp     word ptr [rsp+158h+var_C8], 3
0x1800281b9  jnz     short loc_1800281DB
0x1800281bb  mov     ecx, dword ptr [rsp+158h+var_C8+8]
0x1800281c2  mov     eax, ecx
0x1800281c4  shr     eax, 6
0x1800281c7  and     al, 1
0x1800281c9  mov     [rbx+0BEFh], al
0x1800281cf  shr     ecx, 1Dh
0x1800281d2  and     cl, 1
0x1800281d5  mov     [rbx+0BEEh], cl
0x1800281db  mov     [rsp+158h+xLeft], 0
0x1800281e3  mov     [rsp+158h+yTop], 0
0x1800281eb  mov     [rsp+158h+var_108], 0
0x1800281f3  mov     [rsp+158h+var_110], 0
0x1800281fb  mov     rcx, [rsp+158h+var_100]
0x180028200  mov     rax, [rcx]
0x180028203  movups  xmm0, xmmword ptr [rsp+158h+pvarg]
0x180028208  movaps  [rsp+158h+var_58], xmm0
0x180028210  movsd   xmm1, qword ptr [rsp+158h+pvarg+10h]
0x180028216  movsd   [rsp+158h+var_48], xmm1
0x18002821f  lea     rdx, [rsp+158h+var_58]
0x180028227  mov     [rsp+158h+var_130], rdx
0x18002822c  lea     rdx, [rsp+158h+var_110]
0x180028231  mov     qword ptr [rsp+158h+yBottom], rdx
0x180028236  lea     r9, [rsp+158h+var_108]
0x18002823b  lea     r8, [rsp+158h+yTop]
0x180028240  lea     rdx, [rsp+158h+xLeft]
0x180028245  mov     rax, [rax+0B0h]
0x18002824c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028251  test    eax, eax
0x180028253  js      loc_180028119
0x180028259  mov     r8d, [rsp+158h+yTop]; yTop
0x18002825e  mov     r10d, [rsp+158h+var_110]
0x180028263  add     r10d, r8d
0x180028266  mov     edx, [rsp+158h+xLeft]; xLeft
0x18002826a  mov     r9d, [rsp+158h+var_108]
0x18002826f  add     r9d, edx; xRight
0x180028272  mov     [rsp+158h+yBottom], r10d; yBottom
0x180028277  lea     rcx, [rbx+0C18h]; lprc
0x18002827e  call    cs:__imp_SetRect
0x180028284  jmp     loc_180028119
0x180028289  cmp     eax, 0Fh
0x18002828c  jnz     loc_180028119
0x180028292  jmp     loc_180028155
0x180028297  cmp     eax, 17h; switch 24 cases
0x18002829a  jbe     short loc_1800282F5
0x18002829c  lea     rcx, [rsp+158h+pvarg]; jumptable 000000018002830E default case, cases 8-15
0x1800282a1  call    cs:__imp_VariantClear
0x1800282a7  xor     eax, eax
0x1800282a9  mov     word ptr [rsp+158h+pvarg], ax
0x1800282ae  jmp     short loc_180028310
0x1800282b0  test    rcx, rcx
0x1800282b3  jnz     short loc_1800282D0
0x1800282b5  lea     rcx, aOleaccDll; "Oleacc.dll"
0x1800282bc  call    ?LoadSystemLibrary@@YAPEAUHINSTANCE__@@PEBG@Z; LoadSystemLibrary(ushort const *)
0x1800282c1  mov     rcx, rax; hModule
0x1800282c4  mov     cs:?g_hOleacc@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hOleacc
0x1800282cb  test    rax, rax
0x1800282ce  jz      short loc_1800282E9
0x1800282d0  lea     rdx, aAccessibleobje; "AccessibleObjectFromEvent"
0x1800282d7  call    cs:__imp_GetProcAddress
0x1800282dd  mov     cs:qword_180141318, rax
0x1800282e4  jmp     loc_180028073
0x1800282e9  mov     cs:qword_180141318, rax
0x1800282f0  jmp     loc_180028073
0x1800282f5  lea     rdx, __ImageBase
0x1800282fc  movzx   eax, ds:(byte_1800283E4 - 180000000h)[rdx+rax]
0x180028304  mov     ecx, ds:(jpt_18002830E - 180000000h)[rdx+rax*4]
0x18002830b  add     rcx, rdx
0x18002830e  jmp     rcx; switch jump
0x180028310  jmp     short loc_180028338
0x180028312  mov     rbx, [rsp+158h+arg_0]
0x18002831a  movzx   r13d, [rsp+158h+var_118]
0x180028320  mov     r12, [rsp+158h+var_D8]
0x180028328  mov     r14, [rsp+158h+var_D0]
0x180028330  mov     rsi, [rsp+158h+var_A8]
0x180028338  lea     rcx, [rsp+158h+var_100]
0x18002833d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180028342  test    r13b, r13b
0x180028345  jnz     short loc_1800283C0
0x180028347  cmp     [rsi], r13b
0x18002834a  jnz     short loc_1800283A4
0x18002834c  add     rsp, 120h
0x180028353  pop     r15
0x180028355  pop     r14
0x180028357  pop     r13
0x180028359  pop     r12
0x18002835b  pop     rdi
0x18002835c  pop     rsi
0x18002835d  pop     rbx
0x18002835e  retn
0x18002835f  cmp     edi, 0FFFFFFFCh
0x180028362  jz      loc_180028027
0x180028368  jmp     short loc_180028342
0x18002836a  cmp     byte ptr [rcx+0BEFh], 0
0x180028371  jnz     loc_180027F7F
0x180028377  lea     r14, [rcx+0BF8h]
0x18002837e  lea     r12, [rcx+0BD8h]
0x180028385  cmp     byte ptr [r14], 0
0x180028389  jnz     short loc_18002839C
0x18002838b  mov     rax, [r12]
0x18002838f  cmp     [rcx+0BA0h], rax
0x180028396  jnz     loc_180027F7F
0x18002839c  mov     r13b, 1
0x18002839f  jmp     loc_180027F90
0x1800283a4  cmp     byte ptr [rbx+0BEFh], 0
0x1800283ab  jnz     short loc_18002834C
0x1800283ad  cmp     byte ptr [r14], 0
0x1800283b1  jnz     short loc_1800283C0
0x1800283b3  mov     rax, [r12]
0x1800283b7  cmp     [rbx+0BA0h], rax
0x1800283be  jnz     short loc_18002834C
0x1800283c0  mov     rcx, rbx; this
0x1800283c3  call    ?_OnDocumentFocusChanged@CThreadInputMgr@@AEAAXXZ; CThreadInputMgr::_OnDocumentFocusChanged(void)
0x1800283c8  jmp     short loc_18002834C
0x1800283ca  cmp     byte ptr [rbx+0BFFh], 0
0x1800283d1  jz      loc_180027FD1
0x1800283d7  jmp     loc_180028342
0x180107660  push    rbp
0x180107662  sub     rsp, 40h
0x180107666  mov     rbp, rdx
0x180107669  mov     [rbp+0A8h], rcx
0x180107670  mov     rcx, [rbp+0A8h]; ExceptionInfo
0x180107677  call    cs:__imp_RtlUnhandledExceptionFilter
0x18010767d  mov     dword ptr [rbp+78h], 1
0x180107684  mov     eax, [rbp+78h]
0x180107687  add     rsp, 40h
0x18010768b  pop     rbp
0x18010768c  retn
```
