# CThreadInputMgr::_GetFocusedControlBounds(void)

- ea: `0x180091598`
- end: `0x180091870`
- name: `?_GetFocusedControlBounds@CThreadInputMgr@@AEAA?AUtagRECT@@XZ`
- size: `728`
- prototype: `struct tagRECT *__fastcall(CThreadInputMgr *__hidden this, LPPOINT lpPoints)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000ccac`

## callees

- `0x1800071e0`
- `0x18000c450`
- `0x180015320`
- `0x180018640`
- `0x180024abc`
- `0x180057444`
- `0x180060344`
- `0x180067814`
- `0x180091598`
- `0x1800a18d4`
- `0x18010a010`

## import_xrefs

- `USER32!IntersectRect` at `0x180091829`
- `USER32!IntersectRect` at `0x180091829`
- `USER32!MapWindowPoints` at `0x180091689`
- `USER32!MapWindowPoints` at `0x180091852`
- `USER32!MapWindowPoints` at `0x180091689`
- `USER32!MapWindowPoints` at `0x180091852`
- `USER32!GetClientRect` at `0x18009166d`
- `USER32!GetClientRect` at `0x18009166d`
- `USER32!SetRect` at `0x1800917a3`
- `USER32!SetRect` at `0x1800917a3`
- `USER32!IsRectEmpty` at `0x1800915d2`
- `USER32!IsRectEmpty` at `0x180091654`
- `USER32!IsRectEmpty` at `0x1800916ae`
- `USER32!IsRectEmpty` at `0x1800917d7`
- `USER32!IsRectEmpty` at `0x180091816`
- `USER32!IsRectEmpty` at `0x1800915d2`
- `USER32!IsRectEmpty` at `0x180091654`
- `USER32!IsRectEmpty` at `0x1800916ae`
- `USER32!IsRectEmpty` at `0x1800917d7`
- `USER32!IsRectEmpty` at `0x180091816`

## pseudocode

```c
struct tagRECT *__fastcall CThreadInputMgr::_GetFocusedControlBounds(CThreadInputMgr *this, LPPOINT lpPoints)
{
  __int64 v4; // rcx
  _OWORD *v5; // rbx
  struct IInputContextPrivate *TopInputContext; // rax
  struct IInputContextPrivate *v7; // r15
  int (__fastcall *v8)(struct IInputContextPrivate *, __int64 *); // rbx
  HWND v9; // rcx
  const RECT *v10; // rbx
  struct IAccessibleVtbl *lpVtbl; // rax
  LONG y; // ecx
  LONG v13; // eax
  HWND v14; // rcx
  int v16; // [rsp+40h] [rbp-78h] BYREF
  int xLeft; // [rsp+44h] [rbp-74h] BYREF
  IAccessible *ppacc[2]; // [rsp+48h] [rbp-70h] BYREF
  VARIANT pvarg; // [rsp+58h] [rbp-60h] BYREF
  VARIANT v20; // [rsp+70h] [rbp-48h] BYREF
  __int64 v21; // [rsp+D0h] [rbp+18h] BYREF
  int yTop; // [rsp+D8h] [rbp+20h] BYREF

  *(_OWORD *)&lpPoints->x = 0;
  if ( CThreadInputMgr::_IsTsfFocusInEdit(this) )
  {
    v5 = (_OWORD *)(v4 + 3080);
    if ( IsRectEmpty((const RECT *)(v4 + 3080)) )
    {
      TopInputContext = CThreadInputMgr::GetTopInputContext(this);
      v7 = TopInputContext;
      if ( TopInputContext )
      {
        v21 = 0;
        v8 = *(int (__fastcall **)(struct IInputContextPrivate *, __int64 *))(*(_QWORD *)TopInputContext + 72LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
        if ( v8(v7, &v21) >= 0 )
          (*(void (__fastcall **)(__int64, LPPOINT))(*(_QWORD *)v21 + 40LL))(v21, lpPoints);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
      }
    }
    else
    {
      *(_OWORD *)&lpPoints->x = *v5;
    }
  }
  if ( IsRectEmpty((const RECT *)lpPoints) )
  {
    v9 = (HWND)*((_QWORD *)this + 372);
    if ( v9 )
    {
      if ( GetClientRect(v9, (LPRECT)lpPoints) )
        MapWindowPoints(*((HWND *)this + 372), 0, lpPoints, 2u);
    }
  }
  if ( CThreadInputMgr::_IsAccFocusInEdit(this) )
  {
    v10 = (const RECT *)((char *)this + 3096);
    ppacc[1] = (IAccessible *)((char *)this + 3096);
    if ( IsRectEmpty((const RECT *)((char *)this + 3096)) )
    {
      ATL::CComPtr<ITipProxy>::CComPtr<ITipProxy>(ppacc);
      memset(&pvarg, 0, sizeof(pvarg));
      if ( !AccessibleObjectFromEvent(
              *((HWND *)this + 379),
              *((_DWORD *)this + 760),
              *((_DWORD *)this + 761),
              ppacc,
              &pvarg)
        && ppacc[0] )
      {
        xLeft = 0;
        yTop = 0;
        v16 = 0;
        LODWORD(v21) = 0;
        lpVtbl = ppacc[0]->lpVtbl;
        v20 = pvarg;
        if ( ((int (__fastcall *)(IAccessible *, int *, int *, int *, __int64 *, VARIANT *))lpVtbl->accLocation)(
               ppacc[0],
               &xLeft,
               &yTop,
               &v16,
               &v21,
               &v20) >= 0 )
          SetRect((LPRECT)((char *)this + 3096), xLeft, yTop, xLeft + v16, yTop + v21);
        QuickVariantClear(&pvarg);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(ppacc);
    }
    if ( !IsRectEmpty(v10) )
    {
      if ( *((_BYTE *)this + 3064) )
      {
        if ( *((_QWORD *)this + 379) == *((_QWORD *)this + 372) )
        {
          y = lpPoints[1].y;
          v13 = *((_DWORD *)this + 777);
          if ( v13 < y && v13 > lpPoints->y )
            *((_DWORD *)this + 777) = y;
        }
      }
      if ( IsRectEmpty((const RECT *)lpPoints) || !IntersectRect((LPRECT)lpPoints, (const RECT *)lpPoints, v10) )
      {
        *(RECT *)&lpPoints->x = *v10;
        v14 = (HWND)*((_QWORD *)this + 379);
        if ( v14 )
          MapWindowPoints(v14, 0, lpPoints, 2u);
      }
      *v10 = 0;
    }
  }
  return (struct tagRECT *)lpPoints;
}

```

## disassembly

```asm
0x180091598  mov     [rsp+arg_8], rdx
0x18009159d  mov     [rsp+arg_0], rcx
0x1800915a2  push    rbx
0x1800915a3  push    rsi
0x1800915a4  push    r14
0x1800915a6  push    r15
0x1800915a8  sub     rsp, 98h
0x1800915af  mov     r14, rdx
0x1800915b2  mov     rsi, rcx
0x1800915b5  xorps   xmm0, xmm0
0x1800915b8  movups  xmmword ptr [rdx], xmm0
0x1800915bb  call    ?_IsTsfFocusInEdit@CThreadInputMgr@@AEBA_NXZ; CThreadInputMgr::_IsTsfFocusInEdit(void)
0x1800915c0  test    al, al
0x1800915c2  jz      loc_180091651
0x1800915c8  lea     rbx, [rcx+0C08h]
0x1800915cf  mov     rcx, rbx; lprc
0x1800915d2  call    cs:__imp_IsRectEmpty
0x1800915d8  test    eax, eax
0x1800915da  jnz     short loc_1800915E6
0x1800915dc  movups  xmm0, xmmword ptr [rbx]
0x1800915df  movdqu  xmmword ptr [r14], xmm0
0x1800915e4  jmp     short loc_180091651
0x1800915e6  mov     rcx, rsi; this
0x1800915e9  call    ?GetTopInputContext@CThreadInputMgr@@QEBAPEAUIInputContextPrivate@@XZ; CThreadInputMgr::GetTopInputContext(void)
0x1800915ee  mov     r15, rax
0x1800915f1  test    rax, rax
0x1800915f4  jz      short loc_180091651
0x1800915f6  mov     [rsp+0B8h+arg_10], 0
0x180091602  mov     rcx, [rax]
0x180091605  mov     rbx, [rcx+48h]
0x180091609  lea     rcx, [rsp+0B8h+arg_10]
0x180091611  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180091616  lea     rdx, [rsp+0B8h+arg_10]
0x18009161e  mov     rcx, r15
0x180091621  mov     rax, rbx
0x180091624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091629  test    eax, eax
0x18009162b  js      short loc_180091644
0x18009162d  mov     rcx, [rsp+0B8h+arg_10]
0x180091635  mov     rax, [rcx]
0x180091638  mov     rdx, r14
0x18009163b  mov     rax, [rax+28h]
0x18009163f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091644  lea     rcx, [rsp+0B8h+arg_10]
0x18009164c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180091651  mov     rcx, r14; lprc
0x180091654  call    cs:__imp_IsRectEmpty
0x18009165a  test    eax, eax
0x18009165c  jz      short loc_18009168F
0x18009165e  mov     rcx, [rsi+0BA0h]; hWnd
0x180091665  test    rcx, rcx
0x180091668  jz      short loc_18009168F
0x18009166a  mov     rdx, r14; lpRect
0x18009166d  call    cs:__imp_GetClientRect
0x180091673  test    eax, eax
0x180091675  jz      short loc_18009168F
0x180091677  mov     r9d, 2; cPoints
0x18009167d  mov     r8, r14; lpPoints
0x180091680  xor     edx, edx; hWndTo
0x180091682  mov     rcx, [rsi+0BA0h]; hWndFrom
0x180091689  call    cs:__imp_MapWindowPoints
0x18009168f  mov     rcx, rsi; this
0x180091692  call    ?_IsAccFocusInEdit@CThreadInputMgr@@AEBA_NXZ; CThreadInputMgr::_IsAccFocusInEdit(void)
0x180091697  test    al, al
0x180091699  jz      loc_18009185F
0x18009169f  lea     rbx, [rsi+0C18h]
0x1800916a6  mov     [rsp+0B8h+var_68], rbx
0x1800916ab  mov     rcx, rbx; lprc
0x1800916ae  call    cs:__imp_IsRectEmpty
0x1800916b4  test    eax, eax
0x1800916b6  jz      loc_1800917D4
0x1800916bc  lea     rcx, [rsp+0B8h+ppacc]
0x1800916c1  call    ??0?$CComPtr@UITipProxy@@@ATL@@QEAA@XZ; ATL::CComPtr<ITipProxy>::CComPtr<ITipProxy>(void)
0x1800916c6  xorps   xmm0, xmm0
0x1800916c9  xor     eax, eax
0x1800916cb  movups  xmmword ptr [rsp+0B8h+pvarg], xmm0
0x1800916d0  mov     qword ptr [rsp+0B8h+pvarg+10h], rax
0x1800916d5  lea     rax, [rsp+0B8h+pvarg]
0x1800916da  mov     [rsp+0B8h+pvarChild], rax; pvarChild
0x1800916df  lea     r9, [rsp+0B8h+ppacc]; ppacc
0x1800916e4  mov     r8d, [rsi+0BE4h]; dwChildId
0x1800916eb  mov     edx, [rsi+0BE0h]; dwId
0x1800916f1  mov     rcx, [rsi+0BD8h]; hwnd
0x1800916f8  call    AccessibleObjectFromEvent
0x1800916fd  test    eax, eax
0x1800916ff  jnz     loc_1800917B3
0x180091705  mov     rcx, [rsp+0B8h+ppacc]
0x18009170a  test    rcx, rcx
0x18009170d  jz      loc_1800917B3
0x180091713  mov     [rsp+0B8h+xLeft], eax
0x180091717  mov     [rsp+0B8h+yTop], eax
0x18009171e  mov     [rsp+0B8h+var_78], eax
0x180091722  mov     dword ptr [rsp+0B8h+arg_10], eax
0x180091729  mov     rax, [rcx]
0x18009172c  movups  xmm1, xmmword ptr [rsp+0B8h+pvarg]
0x180091731  movsd   xmm0, qword ptr [rsp+0B8h+pvarg+10h]
0x180091737  movaps  [rsp+0B8h+var_48], xmm1
0x18009173c  movsd   [rsp+0B8h+var_38], xmm0
0x180091745  lea     rdx, [rsp+0B8h+var_48]
0x18009174a  mov     [rsp+0B8h+var_90], rdx
0x18009174f  lea     rdx, [rsp+0B8h+arg_10]
0x180091757  mov     [rsp+0B8h+pvarChild], rdx
0x18009175c  lea     r9, [rsp+0B8h+var_78]
0x180091761  lea     r8, [rsp+0B8h+yTop]
0x180091769  lea     rdx, [rsp+0B8h+xLeft]
0x18009176e  mov     rax, [rax+0B0h]
0x180091775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009177a  test    eax, eax
0x18009177c  js      short loc_1800917A9
0x18009177e  mov     ecx, dword ptr [rsp+0B8h+arg_10]
0x180091785  mov     r8d, [rsp+0B8h+yTop]; yTop
0x18009178d  add     ecx, r8d
0x180091790  mov     r9d, [rsp+0B8h+var_78]
0x180091795  mov     edx, [rsp+0B8h+xLeft]; xLeft
0x180091799  add     r9d, edx; xRight
0x18009179c  mov     dword ptr [rsp+0B8h+pvarChild], ecx; yBottom
0x1800917a0  mov     rcx, rbx; lprc
0x1800917a3  call    cs:__imp_SetRect
0x1800917a9  lea     rcx, [rsp+0B8h+pvarg]; pvarg
0x1800917ae  call    ?QuickVariantClear@@YAXPEAUtagVARIANT@@@Z; QuickVariantClear(tagVARIANT *)
0x1800917b3  jmp     short loc_1800917CA
0x1800917b5  mov     rsi, [rsp+0B8h+arg_0]
0x1800917bd  mov     r14, [rsp+0B8h+arg_8]
0x1800917c5  mov     rbx, [rsp+0B8h+var_68]
0x1800917ca  lea     rcx, [rsp+0B8h+ppacc]
0x1800917cf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800917d4  mov     rcx, rbx; lprc
0x1800917d7  call    cs:__imp_IsRectEmpty
0x1800917dd  test    eax, eax
0x1800917df  jnz     short loc_18009185F
0x1800917e1  cmp     [rsi+0BF8h], al
0x1800917e7  jz      short loc_180091813
0x1800917e9  mov     rax, [rsi+0BA0h]
0x1800917f0  cmp     [rsi+0BD8h], rax
0x1800917f7  jnz     short loc_180091813
0x1800917f9  mov     ecx, [r14+0Ch]
0x1800917fd  mov     eax, [rsi+0C24h]
0x180091803  cmp     eax, ecx
0x180091805  jge     short loc_180091813
0x180091807  cmp     eax, [r14+4]
0x18009180b  jle     short loc_180091813
0x18009180d  mov     [rsi+0C24h], ecx
0x180091813  mov     rcx, r14; lprc
0x180091816  call    cs:__imp_IsRectEmpty
0x18009181c  test    eax, eax
0x18009181e  jnz     short loc_180091833
0x180091820  mov     r8, rbx; lprcSrc2
0x180091823  mov     rdx, r14; lprcSrc1
0x180091826  mov     rcx, r14; lprcDst
0x180091829  call    cs:__imp_IntersectRect
0x18009182f  test    eax, eax
0x180091831  jnz     short loc_180091858
0x180091833  movups  xmm0, xmmword ptr [rbx]
0x180091836  movdqu  xmmword ptr [r14], xmm0
0x18009183b  mov     rcx, [rsi+0BD8h]; hWndFrom
0x180091842  test    rcx, rcx
0x180091845  jz      short loc_180091858
0x180091847  mov     r9d, 2; cPoints
0x18009184d  mov     r8, r14; lpPoints
0x180091850  xor     edx, edx; hWndTo
0x180091852  call    cs:__imp_MapWindowPoints
0x180091858  xorps   xmm0, xmm0
0x18009185b  movdqu  xmmword ptr [rbx], xmm0
0x18009185f  mov     rax, r14
0x180091862  add     rsp, 98h
0x180091869  pop     r15
0x18009186b  pop     r14
0x18009186d  pop     rsi
0x18009186e  pop     rbx
0x18009186f  retn
0x18010801a  push    rbp
0x18010801c  sub     rsp, 40h
0x180108020  mov     rbp, rdx
0x180108023  xor     edx, edx; bool
0x180108025  call    ?CicExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@_N@Z; CicExceptionFilter(_EXCEPTION_POINTERS *,bool)
0x18010802a  nop
0x18010802b  add     rsp, 40h
0x18010802f  pop     rbp
0x180108030  retn
```
