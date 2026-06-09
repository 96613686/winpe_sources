# CBody::ShowContextMenu(ulong,tagPOINT *,IUnknown *,IDispatch *)

- ea: `0x18007e940`
- end: `0x18007eb11`
- name: `?ShowContextMenu@CBody@@UEAAJKPEAUtagPOINT@@PEAUIUnknown@@PEAUIDispatch@@@Z`
- size: `465`
- prototype: `__int64 __fastcall(CBody *__hidden this, unsigned int, struct tagPOINT *, struct IUnknown *, struct IDispatch *)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002098`
- `0x180063b7c`
- `0x180076f64`
- `0x180079180`
- `0x18007b974`
- `0x18007d0c0`
- `0x18007e940`
- `0x18007f1b4`
- `0x18007fed8`
- `0x1800cd010`

## import_xrefs

- `USER32!RemoveMenu` at `0x18007e9ea`
- `USER32!RemoveMenu` at `0x18007e9fb`
- `USER32!RemoveMenu` at `0x18007e9ea`
- `USER32!RemoveMenu` at `0x18007e9fb`
- `USER32!DestroyMenu` at `0x18007eadb`
- `USER32!DestroyMenu` at `0x18007eadb`
- `USER32!EnableMenuItem` at `0x18007ea12`
- `USER32!EnableMenuItem` at `0x18007ea12`
- `USER32!TrackPopupMenu` at `0x18007ea90`
- `USER32!TrackPopupMenu` at `0x18007ea90`
- `USER32!GetParent` at `0x18007ea65`
- `USER32!GetParent` at `0x18007ea65`

## pseudocode

```c
__int64 __fastcall CBody::ShowContextMenu(
        CBody *this,
        __int64 a2,
        struct tagPOINT *a3,
        struct IUnknown *a4,
        struct IDispatch *a5)
{
  struct IDispatch *v5; // r14
  CBody *v6; // rbp
  __int64 v8; // rcx
  int v10; // ebx
  __int64 result; // rax
  int v12; // eax
  HMENU PopupMenu; // rax
  unsigned __int16 **v14; // rdx
  HMENU v15; // rdi
  int v16; // eax
  HWND hWnd; // rax
  BOOL v18; // eax
  int v19; // ebx
  __int64 v20; // [rsp+80h] [rbp+8h] BYREF

  v5 = a5;
  v6 = (CBody *)((char *)this - 176);
  v20 = 0;
  v8 = *((_QWORD *)this + 20);
  v10 = a2;
  if ( v8 )
  {
    result = (*(__int64 (__fastcall **)(__int64, __int64, struct tagPOINT *, struct IUnknown *, struct IDispatch *))(*(_QWORD *)v8 + 24LL))(
               v8,
               a2,
               a3,
               a4,
               a5);
    if ( (_DWORD)result != -2146691327 )
      return result;
  }
  CBody::SuspendBlocking(v6);
  v12 = *((_DWORD *)this + 24);
  *((_DWORD *)this + 108) = v10;
  PopupMenu = LoadPopupMenu(2 - (unsigned int)((v12 & 4) != 0));
  v15 = PopupMenu;
  if ( PopupMenu )
  {
    if ( (*((_BYTE *)this + 96) & 4) != 0 )
    {
      if ( !v10 && !(unsigned int)CBody::GetSelectedAnchor(v6, v14) )
        v10 = 5;
      goto LABEL_12;
    }
    if ( v10 == 5 )
    {
      CBody::AppendAnchorItems(v6, PopupMenu, v5);
    }
    else
    {
      RemoveMenu(PopupMenu, 0xDFu, 0);
      RemoveMenu(v15, 0xE0u, 0);
      if ( v10 == 1 )
      {
LABEL_12:
        *((_DWORD *)this + 24) &= ~0x80u;
        v16 = 0;
        if ( v10 == 1 )
          v16 = 128;
        *((_DWORD *)this + 24) |= v16;
        CBody::UpdateContextMenu(v6, v15, ((v10 - 1) & 0xFFFFFFFB) == 0, v5);
        hWnd = GetParent(*((HWND *)this - 9));
        v18 = TrackPopupMenu(v15, 0x102u, a3->x, a3->y, 0, hWnd, 0);
        *((_QWORD *)this + 53) = v5;
        v19 = v18;
        if ( v5 )
          ((void (__fastcall *)(struct IDispatch *))v5->lpVtbl->AddRef)(v5);
        if ( v19 )
          CBody::OnWMCommand(v6, 0, v19, 0);
        goto LABEL_18;
      }
    }
    EnableMenuItem(v15, 0x79u, 1u);
    goto LABEL_12;
  }
LABEL_18:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 424);
  if ( v15 )
    DestroyMenu(v15);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v20);
  CBody::ResumeBlocking(v6, 0);
  result = 0;
  *((_DWORD *)this + 108) = 0;
  return result;
}

```

## disassembly

```asm
0x18007e940  mov     r11, rsp
0x18007e943  push    rbx
0x18007e944  push    rbp
0x18007e945  push    rsi
0x18007e946  push    rdi
0x18007e947  push    r14
0x18007e949  push    r15
0x18007e94b  sub     rsp, 48h
0x18007e94f  mov     r14, [rsp+78h+arg_20]
0x18007e957  lea     rbp, [rcx-0B0h]
0x18007e95e  mov     rsi, rcx
0x18007e961  mov     qword ptr [r11+8], 0
0x18007e969  mov     rcx, [rbp+150h]
0x18007e970  mov     r15, r8
0x18007e973  mov     ebx, edx
0x18007e975  test    rcx, rcx
0x18007e978  jz      short loc_18007E995
0x18007e97a  mov     rax, [rcx]
0x18007e97d  mov     [r11-58h], r14
0x18007e981  mov     rax, [rax+18h]
0x18007e985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e98a  cmp     eax, 800C1701h
0x18007e98f  jnz     loc_18007EB04
0x18007e995  mov     rcx, rbp; this
0x18007e998  call    ?SuspendBlocking@CBody@@AEAAXXZ; CBody::SuspendBlocking(void)
0x18007e99d  mov     eax, [rsi+60h]
0x18007e9a0  and     al, 4
0x18007e9a2  mov     [rsi+1B0h], ebx
0x18007e9a8  neg     al
0x18007e9aa  sbb     ecx, ecx
0x18007e9ac  add     ecx, 2; unsigned int
0x18007e9af  call    ?LoadPopupMenu@@YAPEAUHMENU__@@I@Z; LoadPopupMenu(uint)
0x18007e9b4  mov     rdi, rax
0x18007e9b7  test    rax, rax
0x18007e9ba  jz      loc_18007EAC7
0x18007e9c0  test    byte ptr [rsi+60h], 4
0x18007e9c4  jnz     short loc_18007EA1A
0x18007e9c6  mov     ecx, 5
0x18007e9cb  cmp     ebx, ecx
0x18007e9cd  jnz     short loc_18007E9DF
0x18007e9cf  mov     r8, r14; struct IDispatch *
0x18007e9d2  mov     rdx, rax; HMENU
0x18007e9d5  mov     rcx, rbp; this
0x18007e9d8  call    ?AppendAnchorItems@CBody@@AEAAJPEAUHMENU__@@PEAUIDispatch@@@Z; CBody::AppendAnchorItems(HMENU__ *,IDispatch *)
0x18007e9dd  jmp     short loc_18007EA06
0x18007e9df  xor     r8d, r8d; uFlags
0x18007e9e2  mov     edx, 0DFh; uPosition
0x18007e9e7  mov     rcx, rdi; hMenu
0x18007e9ea  call    cs:__imp_RemoveMenu
0x18007e9f0  xor     r8d, r8d; uFlags
0x18007e9f3  mov     edx, 0E0h; uPosition
0x18007e9f8  mov     rcx, rdi; hMenu
0x18007e9fb  call    cs:__imp_RemoveMenu
0x18007ea01  cmp     ebx, 1
0x18007ea04  jz      short loc_18007EA2E
0x18007ea06  mov     edx, 79h ; 'y'; uIDEnableItem
0x18007ea0b  mov     rcx, rdi; hMenu
0x18007ea0e  lea     r8d, [rdx-78h]; uEnable
0x18007ea12  call    cs:__imp_EnableMenuItem
0x18007ea18  jmp     short loc_18007EA2E
0x18007ea1a  test    ebx, ebx
0x18007ea1c  jnz     short loc_18007EA2E
0x18007ea1e  mov     rcx, rbp; this
0x18007ea21  call    ?GetSelectedAnchor@CBody@@AEAAJPEAPEAG@Z; CBody::GetSelectedAnchor(ushort * *)
0x18007ea26  test    eax, eax
0x18007ea28  lea     ecx, [rbx+5]
0x18007ea2b  cmovz   ebx, ecx
0x18007ea2e  btr     dword ptr [rsi+60h], 7
0x18007ea33  xor     eax, eax
0x18007ea35  mov     ecx, 80h
0x18007ea3a  cmp     ebx, 1
0x18007ea3d  mov     r9, r14; struct IDispatch *
0x18007ea40  mov     rdx, rdi; HMENU
0x18007ea43  cmovz   eax, ecx
0x18007ea46  or      [rsi+60h], eax
0x18007ea49  lea     eax, [rbx-1]
0x18007ea4c  lea     r8d, [rcx-80h]
0x18007ea50  test    eax, 0FFFFFFFBh
0x18007ea55  mov     rcx, rbp; this
0x18007ea58  setz    r8b; int
0x18007ea5c  call    ?UpdateContextMenu@CBody@@AEAAJPEAUHMENU__@@HPEAUIDispatch@@@Z; CBody::UpdateContextMenu(HMENU__ *,int,IDispatch *)
0x18007ea61  mov     rcx, [rsi-48h]; hWnd
0x18007ea65  call    cs:__imp_GetParent
0x18007ea6b  mov     r9d, [r15+4]; y
0x18007ea6f  mov     edx, 102h; uFlags
0x18007ea74  mov     r8d, [r15]; x
0x18007ea77  mov     rcx, rdi; hMenu
0x18007ea7a  mov     [rsp+78h+prcRect], 0; prcRect
0x18007ea83  mov     [rsp+78h+hWnd], rax; hWnd
0x18007ea88  mov     [rsp+78h+nReserved], 0; nReserved
0x18007ea90  call    cs:__imp_TrackPopupMenu
0x18007ea96  mov     [rsi+1A8h], r14
0x18007ea9d  mov     ebx, eax
0x18007ea9f  test    r14, r14
0x18007eaa2  jz      short loc_18007EAB3
0x18007eaa4  mov     rdx, [r14]
0x18007eaa7  mov     rcx, r14
0x18007eaaa  mov     rax, [rdx+8]
0x18007eaae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eab3  test    ebx, ebx
0x18007eab5  jz      short loc_18007EAC7
0x18007eab7  xor     r9d, r9d; unsigned __int16
0x18007eaba  mov     r8d, ebx; int
0x18007eabd  xor     edx, edx; HWND
0x18007eabf  mov     rcx, rbp; this
0x18007eac2  call    ?OnWMCommand@CBody@@AEAAJPEAUHWND__@@HG@Z; CBody::OnWMCommand(HWND__ *,int,ushort)
0x18007eac7  lea     rcx, [rsi+1A8h]
0x18007eace  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007ead3  test    rdi, rdi
0x18007ead6  jz      short loc_18007EAE1
0x18007ead8  mov     rcx, rdi; hMenu
0x18007eadb  call    cs:__imp_DestroyMenu
0x18007eae1  lea     rcx, [rsp+78h+arg_0]
0x18007eae9  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007eaee  xor     edx, edx; int
0x18007eaf0  mov     rcx, rbp; this
0x18007eaf3  call    ?ResumeBlocking@CBody@@AEAAXH@Z; CBody::ResumeBlocking(int)
0x18007eaf8  xor     eax, eax
0x18007eafa  mov     dword ptr [rsi+1B0h], 0
0x18007eb04  add     rsp, 48h
0x18007eb08  pop     r15
0x18007eb0a  pop     r14
0x18007eb0c  pop     rdi
0x18007eb0d  pop     rsi
0x18007eb0e  pop     rbp
0x18007eb0f  pop     rbx
0x18007eb10  retn
```
