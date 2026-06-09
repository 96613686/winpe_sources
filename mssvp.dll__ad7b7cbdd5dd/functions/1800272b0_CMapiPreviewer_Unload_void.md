# CMapiPreviewer::Unload(void)

- ea: `0x1800272b0`
- end: `0x1800273eb`
- name: `?Unload@CMapiPreviewer@@UEAAJXZ`
- size: `315`
- prototype: `__int64 __fastcall(CMapiPreviewer *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800031c0`
- `0x18000557c`
- `0x18001d404`
- `0x180022fb4`
- `0x1800272b0`
- `0x18003d010`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x1800272fc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180027350`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x1800272fc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180027350`
- `GDI32!DeleteObject` at `0x18002736f`
- `GDI32!DeleteObject` at `0x18002738e`
- `GDI32!DeleteObject` at `0x18002736f`
- `GDI32!DeleteObject` at `0x18002738e`

## pseudocode

```c
__int64 __fastcall CMapiPreviewer::Unload(CMapiPreviewer *this)
{
  __int64 v2; // rcx
  unsigned int Error; // eax
  unsigned int v4; // esi
  __int64 i; // rbp
  __int64 v6; // rdi
  HWND v7; // rcx
  __int64 v8; // rdi
  void *v9; // rcx
  void *v10; // rcx

  ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 200);
  v2 = *((_QWORD *)this + 11);
  if ( v2 )
  {
    Error = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 48LL))(v2);
  }
  else
  {
    v4 = 0;
    if ( !*((_QWORD *)this + 20) )
      goto LABEL_8;
    CMapiPreviewer::DeactivateTooltip((CMapiPreviewer *)((char *)this - 16));
    if ( DestroyWindow(*((HWND *)this + 20)) )
    {
      ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 1184);
      ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 1192);
      *((_QWORD *)this + 20) = 0;
      goto LABEL_8;
    }
    Error = ResultFromLastError();
  }
  v4 = Error;
LABEL_8:
  for ( i = 0; (unsigned int)i < *((_DWORD *)this + 294); i = (unsigned int)(i + 1) )
  {
    v6 = 56 * (i + 5);
    v7 = *(HWND *)((char *)this + v6);
    if ( v7 )
    {
      DestroyWindow(v7);
      *(_QWORD *)((char *)this + v6) = 0;
    }
    v8 = 56LL * (unsigned int)i;
    v9 = *(void **)((char *)this + v8 + 288);
    if ( v9 )
    {
      DeleteObject(v9);
      *(_QWORD *)((char *)this + v8 + 288) = 0;
    }
    v10 = *(void **)((char *)this + v8 + 304);
    if ( v10 )
    {
      DeleteObject(v10);
      *(_QWORD *)((char *)this + v8 + 304) = 0;
    }
    ATL::CSimpleStringT<wchar_t,0>::SetString((char *)this + v8 + 296, &lParam, 0);
  }
  *((_QWORD *)this + 147) = 0;
  ATL::CComPtrBase<IPreviewHandlerFrame>::Release((char *)this + 240);
  return v4;
}

```

## disassembly

```asm
0x1800272b0  push    rbx
0x1800272b2  push    rbp
0x1800272b3  push    rsi
0x1800272b4  push    rdi
0x1800272b5  push    r14
0x1800272b7  sub     rsp, 20h
0x1800272bb  mov     rbx, rcx
0x1800272be  add     rcx, 0C8h
0x1800272c5  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x1800272ca  mov     rcx, [rbx+58h]
0x1800272ce  test    rcx, rcx
0x1800272d1  jz      short loc_1800272E1
0x1800272d3  mov     rax, [rcx]
0x1800272d6  mov     rax, [rax+30h]
0x1800272da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272df  jmp     short loc_18002732C
0x1800272e1  xor     esi, esi
0x1800272e3  cmp     [rbx+0A0h], rsi
0x1800272ea  jz      short loc_18002732E
0x1800272ec  lea     rcx, [rbx-10h]; this
0x1800272f0  call    ?DeactivateTooltip@CMapiPreviewer@@AEAAXXZ; CMapiPreviewer::DeactivateTooltip(void)
0x1800272f5  mov     rcx, [rbx+0A0h]; hWnd
0x1800272fc  call    cs:__imp_DestroyWindow
0x180027302  test    eax, eax
0x180027304  jz      short loc_180027327
0x180027306  lea     rcx, [rbx+4A0h]
0x18002730d  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x180027312  lea     rcx, [rbx+4A8h]
0x180027319  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x18002731e  mov     [rbx+0A0h], rsi
0x180027325  jmp     short loc_18002732E
0x180027327  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002732c  mov     esi, eax
0x18002732e  xor     ebp, ebp
0x180027330  cmp     [rbx+498h], ebp
0x180027336  jbe     loc_1800273C7
0x18002733c  lea     rax, [rbp+5]
0x180027340  mov     r14d, ebp
0x180027343  imul    rdi, rax, 38h ; '8'
0x180027347  mov     rcx, [rdi+rbx]; hWnd
0x18002734b  test    rcx, rcx
0x18002734e  jz      short loc_18002735E
0x180027350  call    cs:__imp_DestroyWindow
0x180027356  mov     qword ptr [rdi+rbx], 0
0x18002735e  imul    rdi, r14, 38h ; '8'
0x180027362  mov     rcx, [rdi+rbx+120h]; ho
0x18002736a  test    rcx, rcx
0x18002736d  jz      short loc_180027381
0x18002736f  call    cs:__imp_DeleteObject
0x180027375  mov     qword ptr [rdi+rbx+120h], 0
0x180027381  mov     rcx, [rdi+rbx+130h]; ho
0x180027389  test    rcx, rcx
0x18002738c  jz      short loc_1800273A0
0x18002738e  call    cs:__imp_DeleteObject
0x180027394  mov     qword ptr [rdi+rbx+130h], 0
0x1800273a0  lea     rcx, [rbx+128h]
0x1800273a7  xor     r8d, r8d
0x1800273aa  add     rcx, rdi
0x1800273ad  lea     rdx, lParam
0x1800273b4  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x1800273b9  inc     ebp
0x1800273bb  cmp     ebp, [rbx+498h]
0x1800273c1  jb      loc_18002733C
0x1800273c7  lea     rcx, [rbx+0F0h]
0x1800273ce  mov     qword ptr [rbx+498h], 0
0x1800273d9  call    ?Release@?$CComPtrBase@UIPreviewHandlerFrame@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IPreviewHandlerFrame>::Release(void)
0x1800273de  mov     eax, esi
0x1800273e0  add     rsp, 20h
0x1800273e4  pop     r14
0x1800273e6  pop     rdi
0x1800273e7  pop     rsi
0x1800273e8  pop     rbp
0x1800273e9  pop     rbx
0x1800273ea  retn
```
