# _dispatchImpl::setErrorInfo(ushort const *)

- ea: `0x10075f4f`
- end: `0x10075fe3`
- name: `?setErrorInfo@_dispatchImpl@@KGXPBG@Z`
- size: `148`
- prototype: `void __userpurge(const wchar_t *szDescription@<ecx>)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10075c61`
- `0x10075d1d`
- `0x10075e0e`
- `0x10075fe9`

## callees

- `0x10040bb4`
- `0x10067b20`
- `0x100750e3`
- `0x10075f4f`

## import_xrefs

- `combase!SetErrorInfo` at `0x10075fc8`
- `combase!SetErrorInfo` at `0x10075fc8`
- `combase!CreateErrorInfo` at `0x10075f6b`
- `combase!CreateErrorInfo` at `0x10075f6b`

## pseudocode

```c
void __thiscall _dispatchImpl::setErrorInfo(const wchar_t *szDescription)
{
  ICreateErrorInfo *p; // esi
  HRESULT (__stdcall *SetSource)(ICreateErrorInfo *, wchar_t *); // edi
  wchar_t *Source; // eax
  _reference<IErrorInfo> errinfo; // [esp+4h] [ebp-8h] BYREF
  _reference<ICreateErrorInfo> cerrinfo; // [esp+8h] [ebp-4h] BYREF

  cerrinfo._p = 0;
  errinfo._p = 0;
  if ( CreateErrorInfo(&cerrinfo._p) >= 0
    && ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), ICreateErrorInfo *, GUID *, _reference<IErrorInfo> *))cerrinfo._p->QueryInterface)(
         cerrinfo._p->QueryInterface,
         cerrinfo._p,
         &IID_IErrorInfo,
         &errinfo) >= 0 )
  {
    p = cerrinfo._p;
    SetSource = cerrinfo._p->SetSource;
    Source = _dispatchImpl::GetSource();
    ((void (__thiscall *)(HRESULT (__stdcall *)(ICreateErrorInfo *, wchar_t *), ICreateErrorInfo *, wchar_t *))SetSource)(
      SetSource,
      p,
      Source);
    ((void (__thiscall *)(HRESULT (__stdcall *)(ICreateErrorInfo *, wchar_t *), ICreateErrorInfo *, const wchar_t *))cerrinfo._p->SetDescription)(
      cerrinfo._p->SetDescription,
      cerrinfo._p,
      szDescription);
    SetErrorInfo(0, errinfo._p);
  }
  release(&errinfo._p);
  release(&cerrinfo._p);
}

```

## disassembly

```asm
0x10075f4f  mov     edi, edi
0x10075f51  push    ebp
0x10075f52  mov     ebp, esp
0x10075f54  push    szDescription
0x10075f55  push    szDescription
0x10075f56  push    ebx
0x10075f57  lea     eax, [ebp+cerrinfo]
0x10075f5a  mov     [ebp+cerrinfo._p], 0
0x10075f61  push    eax; pperrinfo
0x10075f62  mov     ebx, szDescription
0x10075f64  mov     [ebp+errinfo._p], 0
0x10075f6b  call    ds:__imp__CreateErrorInfo@4; CreateErrorInfo(x)
0x10075f71  test    eax, eax
0x10075f73  js      short loc_10075FD0
0x10075f75  mov     szDescription, [ebp+cerrinfo._p]
0x10075f78  push    esi
0x10075f79  mov     eax, [szDescription]
0x10075f7b  mov     esi, [eax]
0x10075f7d  lea     eax, [ebp+errinfo]
0x10075f80  push    eax
0x10075f81  push    offset _IID_IErrorInfo
0x10075f86  push    szDescription
0x10075f87  mov     szDescription, esi; this
0x10075f89  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10075f8f  call    esi
0x10075f91  test    eax, eax
0x10075f93  js      short loc_10075FCF
0x10075f95  mov     esi, [ebp+cerrinfo._p]
0x10075f98  push    edi
0x10075f99  mov     eax, [esi]
0x10075f9b  mov     edi, [eax+10h]
0x10075f9e  call    ?GetSource@_dispatchImpl@@KGPAGXZ; _dispatchImpl::GetSource(void)
0x10075fa3  push    eax
0x10075fa4  push    esi
0x10075fa5  mov     szDescription, edi; this
0x10075fa7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10075fad  call    edi
0x10075faf  mov     eax, [ebp+cerrinfo._p]
0x10075fb2  push    ebx
0x10075fb3  push    eax
0x10075fb4  mov     szDescription, [eax]
0x10075fb6  mov     esi, [szDescription+14h]
0x10075fb9  mov     szDescription, esi; this
0x10075fbb  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10075fc1  call    esi
0x10075fc3  push    [ebp+errinfo._p]; perrinfo
0x10075fc6  push    0; dwReserved
0x10075fc8  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10075fce  pop     edi
0x10075fcf  pop     esi
0x10075fd0  lea     szDescription, [ebp+errinfo]; ppref
0x10075fd3  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10075fd8  lea     szDescription, [ebp+cerrinfo]; ppref
0x10075fdb  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10075fe0  pop     ebx
0x10075fe1  leave
0x10075fe2  retn
```
