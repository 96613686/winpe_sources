# CHTTPMailTransport::~CHTTPMailTransport(void)

- ea: `0x18009d6ec`
- end: `0x18009d973`
- name: `??1CHTTPMailTransport@@UEAA@XZ`
- size: `647`
- prototype: `void __fastcall(CHTTPMailTransport *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18009d9b0`

## callees

- `0x180002098`
- `0x18009d6ec`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18009d76f`
- `KERNEL32!CloseHandle` at `0x18009d76f`
- `KERNEL32!DeleteCriticalSection` at `0x18009d71d`
- `KERNEL32!DeleteCriticalSection` at `0x18009d71d`
- `USER32!IsWindow` at `0x18009d72e`
- `USER32!IsWindow` at `0x18009d72e`
- `USER32!SendMessageA` at `0x18009d745`
- `USER32!SendMessageA` at `0x18009d745`
- `WININET!InternetCloseHandle` at `0x18009d957`
- `WININET!InternetCloseHandle` at `0x18009d957`

## pseudocode

```c
void __fastcall CHTTPMailTransport::~CHTTPMailTransport(CHTTPMailTransport *this)
{
  HWND v2; // rcx
  __int64 v3; // rcx
  void *v4; // rcx

  *(_QWORD *)this = &CHTTPMailTransport::`vftable'{for `IHTTPMailTransportW'};
  *((_QWORD *)this + 1) = &CHTTPMailTransport::`vftable'{for `IXMLNodeFactory'};
  *((_QWORD *)this + 2) = &CHTTPMailTransport::`vftable'{for `IHTTPMailTransport2'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  v2 = (HWND)*((_QWORD *)this + 12);
  if ( v2 && IsWindow(v2) )
    SendMessageA(*((HWND *)this + 12), 0x10u, 0, 0);
  if ( *((_QWORD *)this + 8) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 8) = 0;
  }
  CloseHandle(*((HANDLE *)this + 13));
  if ( *((_QWORD *)this + 252) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 252) = 0;
  }
  if ( *((_QWORD *)this + 253) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 253) = 0;
  }
  if ( *((_QWORD *)this + 254) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 254) = 0;
  }
  if ( *((_QWORD *)this + 255) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 255) = 0;
  }
  if ( *((_QWORD *)this + 256) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 256) = 0;
  }
  if ( *((_QWORD *)this + 257) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 257) = 0;
  }
  if ( *((_QWORD *)this + 258) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 258) = 0;
  }
  if ( *((_QWORD *)this + 259) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 259) = 0;
  }
  if ( *((_QWORD *)this + 260) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 260) = 0;
  }
  if ( *((_QWORD *)this + 261) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 261) = 0;
  }
  if ( *((_QWORD *)this + 250) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 250) = 0;
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 72);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 80);
  v3 = *((_QWORD *)this + 11);
  if ( v3 )
  {
    *((_QWORD *)this + 11) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 2104);
  v4 = (void *)*((_QWORD *)this + 6);
  if ( v4 )
  {
    InternetCloseHandle(v4);
    *((_QWORD *)this + 6) = 0;
  }
  _InterlockedDecrement(&g_cRef);
}

```

## disassembly

```asm
0x18009d6ec  mov     [rsp+arg_0], rbx
0x18009d6f1  push    rdi
0x18009d6f2  sub     rsp, 20h
0x18009d6f6  lea     rax, ??_7CHTTPMailTransport@@6BIHTTPMailTransportW@@@; const CHTTPMailTransport::`vftable'{for `IHTTPMailTransportW'}
0x18009d6fd  mov     rbx, rcx
0x18009d700  mov     [rcx], rax
0x18009d703  lea     rax, ??_7CHTTPMailTransport@@6BIXMLNodeFactory@@@; const CHTTPMailTransport::`vftable'{for `IXMLNodeFactory'}
0x18009d70a  mov     [rcx+8], rax
0x18009d70e  lea     rax, ??_7CHTTPMailTransport@@6BIHTTPMailTransport2@@@; const CHTTPMailTransport::`vftable'{for `IHTTPMailTransport2'}
0x18009d715  mov     [rcx+10h], rax
0x18009d719  sub     rcx, 0FFFFFFFFFFFFFF80h; lpCriticalSection
0x18009d71d  call    cs:__imp_DeleteCriticalSection
0x18009d723  mov     rcx, [rbx+60h]; hWnd
0x18009d727  xor     edi, edi
0x18009d729  test    rcx, rcx
0x18009d72c  jz      short loc_18009D74B
0x18009d72e  call    cs:__imp_IsWindow
0x18009d734  test    eax, eax
0x18009d736  jz      short loc_18009D74B
0x18009d738  mov     rcx, [rbx+60h]; hWnd
0x18009d73c  lea     edx, [rdi+10h]; Msg
0x18009d73f  xor     r9d, r9d; lParam
0x18009d742  xor     r8d, r8d; wParam
0x18009d745  call    cs:__imp_SendMessageA
0x18009d74b  mov     rdx, [rbx+40h]
0x18009d74f  test    rdx, rdx
0x18009d752  jz      short loc_18009D76B
0x18009d754  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18009d75b  mov     rax, [rcx]
0x18009d75e  mov     rax, [rax+28h]
0x18009d762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d767  mov     [rbx+40h], rdi
0x18009d76b  mov     rcx, [rbx+68h]; hObject
0x18009d76f  call    cs:__imp_CloseHandle
0x18009d775  mov     rdx, [rbx+7E0h]
0x18009d77c  test    rdx, rdx
0x18009d77f  jz      short loc_18009D79B
0x18009d781  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18009d788  mov     rax, [rcx]
0x18009d78b  mov     rax, [rax+28h]
0x18009d78f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d794  mov     [rbx+7E0h], rdi
0x18009d79b  mov     rdx, [rbx+7E8h]
0x18009d7a2  test    rdx, rdx
0x18009d7a5  jz      short loc_18009D7C1
0x18009d7a7  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18009d7ae  mov     rax, [rcx]
0x18009d7b1  mov     rax, [rax+28h]
0x18009d7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d7ba  mov     [rbx+7E8h], rdi
0x18009d7c1  mov     rdx, [rbx+7F0h]
0x18009d7c8  test    rdx, rdx
0x18009d7cb  jz      short loc_18009D7E7
0x18009d7cd  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18009d7d4  mov     rax, [rcx]
0x18009d7d7  mov     rax, [rax+28h]
0x18009d7db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d7e0  mov     [rbx+7F0h], rdi
0x18009d7e7  mov     rdx, [rbx+7F8h]
0x18009d7ee  test    rdx, rdx
0x18009d7f1  jz      short loc_18009D80D
0x18009d7f3  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18009d7fa  mov     rax, [rcx]
0x18009d7fd  mov     rax, [rax+28h]
0x18009d801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d806  mov     [rbx+7F8h], rdi
0x18009d80d  mov     rdx, [rbx+800h]
0x18009d814  test    rdx, rdx
0x18009d817  jz      short loc_18009D833
0x18009d819  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18009d820  mov     rax, [rcx]
0x18009d823  mov     rax, [rax+28h]
0x18009d827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d82c  mov     [rbx+800h], rdi
0x18009d833  mov     rdx, [rbx+808h]
0x18009d83a  test    rdx, rdx
0x18009d83d  jz      short loc_18009D859
0x18009d83f  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18009d846  mov     rax, [rcx]
0x18009d849  mov     rax, [rax+28h]
0x18009d84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d852  mov     [rbx+808h], rdi
0x18009d859  mov     rdx, [rbx+810h]
0x18009d860  test    rdx, rdx
0x18009d863  jz      short loc_18009D87F
0x18009d865  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18009d86c  mov     rax, [rcx]
0x18009d86f  mov     rax, [rax+28h]
0x18009d873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d878  mov     [rbx+810h], rdi
0x18009d87f  mov     rdx, [rbx+818h]
0x18009d886  test    rdx, rdx
0x18009d889  jz      short loc_18009D8A5
0x18009d88b  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18009d892  mov     rax, [rcx]
0x18009d895  mov     rax, [rax+28h]
0x18009d899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d89e  mov     [rbx+818h], rdi
0x18009d8a5  mov     rdx, [rbx+820h]
0x18009d8ac  test    rdx, rdx
0x18009d8af  jz      short loc_18009D8CB
0x18009d8b1  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18009d8b8  mov     rax, [rcx]
0x18009d8bb  mov     rax, [rax+28h]
0x18009d8bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d8c4  mov     [rbx+820h], rdi
0x18009d8cb  mov     rdx, [rbx+828h]
0x18009d8d2  test    rdx, rdx
0x18009d8d5  jz      short loc_18009D8F1
0x18009d8d7  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18009d8de  mov     rax, [rcx]
0x18009d8e1  mov     rax, [rax+28h]
0x18009d8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d8ea  mov     [rbx+828h], rdi
0x18009d8f1  mov     rdx, [rbx+7D0h]
0x18009d8f8  test    rdx, rdx
0x18009d8fb  jz      short loc_18009D917
0x18009d8fd  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18009d904  mov     rax, [rcx]
0x18009d907  mov     rax, [rax+28h]
0x18009d90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d910  mov     [rbx+7D0h], rdi
0x18009d917  lea     rcx, [rbx+48h]
0x18009d91b  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18009d920  lea     rcx, [rbx+50h]
0x18009d924  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18009d929  mov     rcx, [rbx+58h]
0x18009d92d  test    rcx, rcx
0x18009d930  jz      short loc_18009D942
0x18009d932  mov     [rbx+58h], rdi
0x18009d936  mov     rax, [rcx]
0x18009d939  mov     rax, [rax+10h]
0x18009d93d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d942  lea     rcx, [rbx+838h]
0x18009d949  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18009d94e  mov     rcx, [rbx+30h]; hInternet
0x18009d952  test    rcx, rcx
0x18009d955  jz      short loc_18009D961
0x18009d957  call    cs:__imp_InternetCloseHandle
0x18009d95d  mov     [rbx+30h], rdi
0x18009d961  lock dec cs:?g_cRef@@3JA; long g_cRef
0x18009d968  mov     rbx, [rsp+28h+arg_0]
0x18009d96d  add     rsp, 20h
0x18009d971  pop     rdi
0x18009d972  retn
```
