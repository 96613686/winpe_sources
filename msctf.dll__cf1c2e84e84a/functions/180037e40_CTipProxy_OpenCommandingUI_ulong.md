# CTipProxy::OpenCommandingUI(ulong)

- ea: `0x180037e40`
- end: `0x1800381ea`
- name: `?OpenCommandingUI@CTipProxy@@AEAAXK@Z`
- size: `938`
- prototype: `void __fastcall(CTipProxy *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180036fe0`
- `0x180043a20`
- `0x18006b0f8`

## callees

- `0x180018640`
- `0x180024f54`
- `0x180037e40`
- `0x1800389e0`
- `0x180038aa0`
- `0x18003f2f0`
- `0x18003fa4c`
- `0x18009eaea`
- `0x1800c0d0c`
- `0x1800c6464`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038059`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180038059`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800380da`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800380da`
- `USER32!OffsetRect` at `0x18003809b`
- `USER32!OffsetRect` at `0x18003809b`
- `USER32!InflateRect` at `0x180037ff4`
- `USER32!InflateRect` at `0x18003800d`
- `USER32!InflateRect` at `0x180037ff4`
- `USER32!InflateRect` at `0x18003800d`
- `USER32!IntersectRect` at `0x180038026`
- `USER32!IntersectRect` at `0x180038026`
- `USER32!IsRectEmpty` at `0x180038082`
- `USER32!IsRectEmpty` at `0x180038082`
- `USER32!GetKeyboardLayout` at `0x1800380c9`
- `USER32!GetKeyboardLayout` at `0x1800380c9`
- `USER32!GetGUIThreadInfo` at `0x180038066`
- `USER32!GetGUIThreadInfo` at `0x180038066`

## pseudocode

```c
void __fastcall CTipProxy::OpenCommandingUI(struct IUnknown **this, unsigned int a2)
{
  struct IUnknown *v4; // r15
  struct IUnknownVtbl *lpVtbl; // rcx
  struct IUnknown *v6; // rcx
  __int64 v7; // rdi
  unsigned int UIContextSettingsFlags; // eax
  struct IUnknown *v9; // r8
  int v10; // eax
  char v11; // si
  DWORD CurrentThreadId; // eax
  unsigned __int16 KeyboardLayout; // r12
  CTsfCommandList *v14; // rax
  CTsfCommandList *v15; // r13
  struct IUnknown *DefaultUIManager; // rax
  _QWORD *v17; // rsi
  struct IUnknown *v18; // rcx
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v22; // [rsp+54h] [rbp-ACh]
  __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v24; // [rsp+60h] [rbp-A0h] BYREF
  struct tagGUITHREADINFO pgui; // [rsp+70h] [rbp-90h] BYREF
  int dy[4]; // [rsp+C0h] [rbp-40h] BYREF
  RECT rcCaret; // [rsp+D0h] [rbp-30h] BYREF
  RECT rcSrc2; // [rsp+E0h] [rbp-20h] BYREF
  struct tagRECT rc; // [rsp+F0h] [rbp-10h] BYREF
  struct tagRECT rcDst; // [rsp+100h] [rbp+0h] BYREF

  CTipProxy::CloseUI((CTipProxy *)this, 1);
  if ( CTipProxy::IsCommandingUIApplicable((CTipProxy *)this) )
  {
    v4 = this[23];
    v19 = 0;
    v24 = 0;
    lpVtbl = v4[14].lpVtbl;
    v23 = 0;
    if ( (*((int (__fastcall **)(struct IUnknownVtbl *, _QWORD, __int64, __int64, __int128 *, int *))lpVtbl->QueryInterface
          + 5))(
           lpVtbl,
           a2,
           0xFFFFFFFFLL,
           1,
           &v24,
           &v19) < 0 )
      goto LABEL_37;
    if ( v19 != 1 )
      goto LABEL_37;
    v6 = this[23];
    if ( v4 != v6 )
      goto LABEL_37;
    v7 = v24;
    v23 = v24;
    UIContextSettingsFlags = CTipProxy::CContextPtr::GetUIContextSettingsFlags(v6, a2, v24);
    v9 = this[23];
    v22 = UIContextSettingsFlags;
    if ( v4 != v9 )
      goto LABEL_37;
    v21 = 0;
    rcCaret = 0;
    v20 = 0;
    *(_OWORD *)dy = 0;
    if ( (*((int (__fastcall **)(struct IUnknownVtbl *, __int64 *))v9[14].lpVtbl->QueryInterface + 9))(
           v9[14].lpVtbl,
           &v20) < 0
      || (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 40LL))(v20, dy) < 0
      || (v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, RECT *, int *))(*(_QWORD *)v20 + 32LL))(
                  v20,
                  a2,
                  v7,
                  &rcCaret,
                  &v21),
          v11 = 1,
          v10 < 0) )
    {
      v11 = 0;
    }
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    if ( !v11 )
      goto LABEL_37;
    if ( v4 != this[23] )
    {
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      return;
    }
    rc = *(struct tagRECT *)dy;
    InflateRect(&rc, 1, 1);
    rcSrc2 = rcCaret;
    InflateRect(&rcSrc2, 1, 1);
    rcDst = 0;
    if ( !IntersectRect(&rcDst, &rc, &rcSrc2) )
    {
      if ( ((_BYTE)this[24] & 0x10) == 0
        || (pgui.cbSize = 72,
            memset_0(&pgui.flags, 0, 0x44u),
            CurrentThreadId = GetCurrentThreadId(),
            !GetGUIThreadInfo(CurrentThreadId, &pgui))
        || !pgui.hwndCaret
        || IsRectEmpty(&pgui.rcCaret)
        || (OffsetRect(&pgui.rcCaret, dy[0], dy[1]), pgui.rcCaret.right > dy[2])
        || pgui.rcCaret.bottom > dy[3] )
      {
LABEL_37:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
        return;
      }
      rcCaret = pgui.rcCaret;
    }
    KeyboardLayout = (unsigned __int16)GetKeyboardLayout(0);
    v14 = (CTsfCommandList *)LocalAlloc(0x40u, 0x38u);
    if ( v14 )
    {
      v15 = CTsfCommandList::CTsfCommandList(
              v14,
              (struct ITsfUIObjectOwner *)((unsigned __int64)(this + 14) & -(__int64)(this != 0)),
              KeyboardLayout & 0x3FF);
      if ( v15 )
      {
        DefaultUIManager = (struct IUnknown *)CTipProxy::GetDefaultUIManager((CTipProxy *)this);
        v17 = this + 41;
        if ( this[41] != DefaultUIManager )
          ATL::AtlComPtrAssign(this + 41, DefaultUIManager);
        v18 = this[43];
        if ( v18 )
          ((void (__fastcall *)(struct IUnknown *))v18->lpVtbl->Release)(v18);
        this[43] = (struct IUnknown *)((char *)v15 + 8);
        if ( *v17 )
        {
          if ( v4 == this[23]
            && (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD, RECT *, int *, CTsfCommandList *))(*(_QWORD *)*v17 + 32LL))(
                 *v17,
                 KeyboardLayout,
                 v22,
                 &rcCaret,
                 dy,
                 v15) >= 0 )
          {
            *((_BYTE *)this + 376) = 1;
          }
          else
          {
            CTipProxy::CloseCommandingUI((CTipProxy *)this);
          }
        }
        else if ( v15 != (CTsfCommandList *)-8LL )
        {
          ATL::AtlComPtrAssign(this + 43, 0);
        }
      }
    }
    goto LABEL_37;
  }
}

```

## disassembly

```asm
0x180037e40  mov     [rsp-8+arg_10], rbx
0x180037e45  push    rbp
0x180037e46  push    rsi
0x180037e47  push    rdi
0x180037e48  push    r12
0x180037e4a  push    r13
0x180037e4c  push    r14
0x180037e4e  push    r15
0x180037e50  lea     rbp, [rsp-20h]
0x180037e55  sub     rsp, 120h
0x180037e5c  mov     rax, cs:__security_cookie
0x180037e63  xor     rax, rsp
0x180037e66  mov     [rbp+50h+var_40], rax
0x180037e6a  mov     esi, edx
0x180037e6c  mov     r12d, 1
0x180037e72  mov     dl, r12b; bool
0x180037e75  mov     rbx, rcx
0x180037e78  call    ?CloseUI@CTipProxy@@AEAAX_N@Z; CTipProxy::CloseUI(bool)
0x180037e7d  mov     rcx, rbx; this
0x180037e80  call    ?IsCommandingUIApplicable@CTipProxy@@AEBA_NXZ; CTipProxy::IsCommandingUIApplicable(void)
0x180037e85  xor     r14d, r14d
0x180037e88  test    al, al
0x180037e8a  jz      loc_1800381C3
0x180037e90  mov     r15, [rbx+0B8h]
0x180037e97  lea     rdx, [rsp+150h+var_110]
0x180037e9c  mov     [rsp+150h+var_128], rdx
0x180037ea1  xorps   xmm0, xmm0
0x180037ea4  mov     [rsp+150h+var_110], r14d
0x180037ea9  lea     rdx, [rsp+150h+var_F0]
0x180037eae  movups  [rsp+150h+var_F0], xmm0
0x180037eb3  mov     rcx, [r15+70h]
0x180037eb7  mov     r9d, r12d
0x180037eba  mov     [rsp+150h+var_130], rdx
0x180037ebf  or      r8d, 0FFFFFFFFh
0x180037ec3  mov     edx, esi
0x180037ec5  mov     [rsp+150h+var_F8], r14
0x180037eca  mov     rax, [rcx]
0x180037ecd  mov     rax, [rax+28h]
0x180037ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037ed6  test    eax, eax
0x180037ed8  js      loc_1800381B9
0x180037ede  cmp     [rsp+150h+var_110], r12d
0x180037ee3  jnz     loc_1800381B9
0x180037ee9  mov     rcx, [rbx+0B8h]
0x180037ef0  cmp     r15, rcx
0x180037ef3  jnz     loc_1800381B9
0x180037ef9  mov     rdi, qword ptr [rsp+150h+var_F0]
0x180037efe  mov     edx, esi
0x180037f00  mov     r8, rdi
0x180037f03  mov     [rsp+150h+var_F8], rdi
0x180037f08  call    ?GetUIContextSettingsFlags@CContextPtr@CTipProxy@@QEAA?AW4TsfUIContextSettingsFlags@@KPEAUITfRange@@@Z; CTipProxy::CContextPtr::GetUIContextSettingsFlags(ulong,ITfRange *)
0x180037f0d  mov     r8, [rbx+0B8h]
0x180037f14  mov     [rsp+150h+var_FC], eax
0x180037f18  cmp     r15, r8
0x180037f1b  jnz     loc_1800381B9
0x180037f21  xorps   xmm0, xmm0
0x180037f24  mov     [rsp+150h+var_100], r14d
0x180037f29  movups  [rbp+50h+var_80], xmm0
0x180037f2d  mov     [rsp+150h+var_108], r14
0x180037f32  lea     rdx, [rsp+150h+var_108]
0x180037f37  xorps   xmm1, xmm1
0x180037f3a  movups  xmmword ptr [rbp+50h+dy], xmm1
0x180037f3e  mov     r8, [r8+70h]
0x180037f42  mov     rcx, [r8]
0x180037f45  mov     rax, [rcx+48h]
0x180037f49  mov     rcx, r8
0x180037f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f51  test    eax, eax
0x180037f53  js      short loc_180037F99
0x180037f55  mov     rcx, [rsp+150h+var_108]
0x180037f5a  lea     rdx, [rbp+50h+dy]
0x180037f5e  mov     rax, [rcx]
0x180037f61  mov     rax, [rax+28h]
0x180037f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f6a  test    eax, eax
0x180037f6c  js      short loc_180037F99
0x180037f6e  mov     rcx, [rsp+150h+var_108]
0x180037f73  lea     rdx, [rsp+150h+var_100]
0x180037f78  mov     [rsp+150h+var_130], rdx
0x180037f7d  lea     r9, [rbp+50h+var_80]
0x180037f81  mov     r8, rdi
0x180037f84  mov     edx, esi
0x180037f86  mov     rax, [rcx]
0x180037f89  mov     rax, [rax+20h]
0x180037f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f92  mov     sil, r12b
0x180037f95  test    eax, eax
0x180037f97  jns     short loc_180037F9C
0x180037f99  mov     sil, r14b
0x180037f9c  mov     rcx, [rsp+150h+var_108]
0x180037fa1  test    rcx, rcx
0x180037fa4  jz      short loc_180037FB2
0x180037fa6  mov     rax, [rcx]
0x180037fa9  mov     rax, [rax+10h]
0x180037fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037fb2  test    sil, sil
0x180037fb5  jz      loc_1800381B9
0x180037fbb  cmp     r15, [rbx+0B8h]
0x180037fc2  jz      short loc_180037FE1
0x180037fc4  test    rdi, rdi
0x180037fc7  jz      loc_1800381C3
0x180037fcd  mov     rax, [rdi]
0x180037fd0  mov     rcx, rdi
0x180037fd3  mov     rax, [rax+10h]
0x180037fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037fdc  jmp     loc_1800381C3
0x180037fe1  movaps  xmm0, xmmword ptr [rbp+50h+dy]
0x180037fe5  lea     rcx, [rbp+50h+rc]; lprc
0x180037fe9  mov     r8d, r12d; dy
0x180037fec  movdqa  xmmword ptr [rbp+50h+rc.left], xmm0
0x180037ff1  mov     edx, r12d; dx
0x180037ff4  call    cs:__imp_InflateRect
0x180037ffa  movaps  xmm0, [rbp+50h+var_80]
0x180037ffe  lea     rcx, [rbp+50h+rcSrc2]; lprc
0x180038002  mov     r8d, r12d; dy
0x180038005  movdqa  xmmword ptr [rbp+50h+rcSrc2.left], xmm0
0x18003800a  mov     edx, r12d; dx
0x18003800d  call    cs:__imp_InflateRect
0x180038013  xorps   xmm0, xmm0
0x180038016  lea     r8, [rbp+50h+rcSrc2]; lprcSrc2
0x18003801a  lea     rdx, [rbp+50h+rc]; lprcSrc1
0x18003801e  lea     rcx, [rbp+50h+rcDst]; lprcDst
0x180038022  movups  xmmword ptr [rbp+50h+rcDst.left], xmm0
0x180038026  call    cs:__imp_IntersectRect
0x18003802c  test    eax, eax
0x18003802e  jnz     loc_1800380C7
0x180038034  test    byte ptr [rbx+0C0h], 10h
0x18003803b  jz      loc_1800381B9
0x180038041  xor     edx, edx; Val
0x180038043  mov     [rsp+150h+pgui.cbSize], 48h ; 'H'
0x18003804b  lea     r8d, [rax+44h]; Size
0x18003804f  lea     rcx, [rsp+150h+pgui.flags]; void *
0x180038054  call    memset_0
0x180038059  call    cs:__imp_GetCurrentThreadId
0x18003805f  mov     ecx, eax; idThread
0x180038061  lea     rdx, [rsp+150h+pgui]; pgui
0x180038066  call    cs:__imp_GetGUIThreadInfo
0x18003806c  test    eax, eax
0x18003806e  jz      loc_1800381B9
0x180038074  cmp     [rbp+50h+pgui.hwndCaret], r14
0x180038078  jz      loc_1800381B9
0x18003807e  lea     rcx, [rbp+50h+pgui.rcCaret]; lprc
0x180038082  call    cs:__imp_IsRectEmpty
0x180038088  test    eax, eax
0x18003808a  jnz     loc_1800381B9
0x180038090  mov     r8d, [rbp+50h+dy+4]; dy
0x180038094  lea     rcx, [rbp+50h+pgui.rcCaret]; lprc
0x180038098  mov     edx, [rbp+50h+dy]; dx
0x18003809b  call    cs:__imp_OffsetRect
0x1800380a1  mov     edx, [rbp+50h+pgui.rcCaret.right]
0x1800380a4  cmp     edx, [rbp+50h+dy+8]
0x1800380a7  jg      loc_1800381B9
0x1800380ad  mov     ecx, [rbp+50h+pgui.rcCaret.bottom]
0x1800380b0  cmp     ecx, [rbp+50h+dy+0Ch]
0x1800380b3  jg      loc_1800381B9
0x1800380b9  mov     rax, qword ptr [rbp+50h+pgui.rcCaret.left]
0x1800380bd  mov     qword ptr [rbp+50h+var_80], rax
0x1800380c1  mov     dword ptr [rbp+50h+var_80+8], edx
0x1800380c4  mov     dword ptr [rbp+50h+var_80+0Ch], ecx
0x1800380c7  xor     ecx, ecx; idThread
0x1800380c9  call    cs:__imp_GetKeyboardLayout
0x1800380cf  mov     edx, 38h ; '8'; uBytes
0x1800380d4  mov     r12, rax
0x1800380d7  lea     ecx, [rdx+8]; uFlags
0x1800380da  call    cs:__imp_LocalAlloc
0x1800380e0  test    rax, rax
0x1800380e3  jz      loc_1800381B9
0x1800380e9  movzx   r8d, r12w
0x1800380ed  lea     r9, [rbx+70h]
0x1800380f1  mov     ecx, 3FFh
0x1800380f6  and     r8w, cx; unsigned __int16
0x1800380fa  mov     rcx, rbx
0x1800380fd  neg     rcx
0x180038100  mov     rcx, rax; this
0x180038103  sbb     rdx, rdx
0x180038106  and     rdx, r9; struct ITsfUIObjectOwner *
0x180038109  call    ??0CTsfCommandList@@QEAA@PEAUITsfUIObjectOwner@@G@Z; CTsfCommandList::CTsfCommandList(ITsfUIObjectOwner *,ushort)
0x18003810e  mov     r13, rax
0x180038111  test    rax, rax
0x180038114  jz      loc_1800381B9
0x18003811a  mov     rcx, rbx; this
0x18003811d  call    ?GetDefaultUIManager@CTipProxy@@AEAAPEAUIUIManager@@XZ; CTipProxy::GetDefaultUIManager(void)
0x180038122  lea     rsi, [rbx+148h]
0x180038129  cmp     [rsi], rax
0x18003812c  jz      short loc_180038139
0x18003812e  mov     rdx, rax; struct IUnknown *
0x180038131  mov     rcx, rsi; struct IUnknown **
0x180038134  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180038139  lea     rdi, [rbx+158h]
0x180038140  mov     rcx, [rdi]
0x180038143  lea     r14, [r13+8]
0x180038147  test    rcx, rcx
0x18003814a  jz      short loc_180038158
0x18003814c  mov     rax, [rcx]
0x18003814f  mov     rax, [rax+10h]
0x180038153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038158  mov     [rdi], r14
0x18003815b  mov     rcx, [rsi]
0x18003815e  test    rcx, rcx
0x180038161  jz      short loc_1800381AA
0x180038163  cmp     r15, [rbx+0B8h]
0x18003816a  jnz     short loc_1800381A0
0x18003816c  mov     rax, [rcx]
0x18003816f  lea     rdx, [rbp+50h+dy]
0x180038173  mov     r8d, [rsp+150h+var_FC]
0x180038178  lea     r9, [rbp+50h+var_80]
0x18003817c  mov     [rsp+150h+var_128], r13
0x180038181  mov     [rsp+150h+var_130], rdx
0x180038186  movzx   edx, r12w
0x18003818a  mov     rax, [rax+20h]
0x18003818e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038193  test    eax, eax
0x180038195  js      short loc_1800381A0
0x180038197  mov     byte ptr [rbx+178h], 1
0x18003819e  jmp     short loc_1800381B9
0x1800381a0  mov     rcx, rbx; this
0x1800381a3  call    ?CloseCommandingUI@CTipProxy@@AEAAXXZ; CTipProxy::CloseCommandingUI(void)
0x1800381a8  jmp     short loc_1800381B9
0x1800381aa  test    r14, r14
0x1800381ad  jz      short loc_1800381B9
0x1800381af  xor     edx, edx; struct IUnknown *
0x1800381b1  mov     rcx, rdi; struct IUnknown **
0x1800381b4  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1800381b9  lea     rcx, [rsp+150h+var_F8]
0x1800381be  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800381c3  mov     rcx, [rbp+50h+var_40]
0x1800381c7  xor     rcx, rsp; StackCookie
0x1800381ca  call    __security_check_cookie
0x1800381cf  mov     rbx, [rsp+150h+arg_10]
0x1800381d7  add     rsp, 120h
0x1800381de  pop     r15
0x1800381e0  pop     r14
0x1800381e2  pop     r13
0x1800381e4  pop     r12
0x1800381e6  pop     rdi
0x1800381e7  pop     rsi
0x1800381e8  pop     rbp
0x1800381e9  retn
```
