# _dispatchImpl::setErrorInfo(ushort const *)

- ea: `0x10075f1f`
- end: `0x10075fb3`
- name: `?setErrorInfo@_dispatchImpl@@KGXPBG@Z`
- size: `148`
- prototype: `void __userpurge(const wchar_t *szDescription@<ecx>)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10075c31`
- `0x10075ced`
- `0x10075dde`
- `0x10075fb9`

## callees

- `0x10040c44`
- `0x10067bc0`
- `0x100750b1`
- `0x10075f1f`

## import_xrefs

- `combase!SetErrorInfo` at `0x10075f98`
- `combase!SetErrorInfo` at `0x10075f98`
- `combase!CreateErrorInfo` at `0x10075f3b`
- `combase!CreateErrorInfo` at `0x10075f3b`

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
0x10075f1f  mov     edi, edi
0x10075f21  push    ebp
0x10075f22  mov     ebp, esp
0x10075f24  push    szDescription
0x10075f25  push    szDescription
0x10075f26  push    ebx
0x10075f27  lea     eax, [ebp+cerrinfo]
0x10075f2a  mov     [ebp+cerrinfo._p], 0
0x10075f31  push    eax; pperrinfo
0x10075f32  mov     ebx, szDescription
0x10075f34  mov     [ebp+errinfo._p], 0
0x10075f3b  call    ds:__imp__CreateErrorInfo@4; CreateErrorInfo(x)
0x10075f41  test    eax, eax
0x10075f43  js      short loc_10075FA0
0x10075f45  mov     szDescription, [ebp+cerrinfo._p]
0x10075f48  push    esi
0x10075f49  mov     eax, [szDescription]
0x10075f4b  mov     esi, [eax]
0x10075f4d  lea     eax, [ebp+errinfo]
0x10075f50  push    eax
0x10075f51  push    offset _IID_IErrorInfo
0x10075f56  push    szDescription
0x10075f57  mov     szDescription, esi; this
0x10075f59  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10075f5f  call    esi
0x10075f61  test    eax, eax
0x10075f63  js      short loc_10075F9F
0x10075f65  mov     esi, [ebp+cerrinfo._p]
0x10075f68  push    edi
0x10075f69  mov     eax, [esi]
0x10075f6b  mov     edi, [eax+10h]
0x10075f6e  call    ?GetSource@_dispatchImpl@@KGPAGXZ; _dispatchImpl::GetSource(void)
0x10075f73  push    eax
0x10075f74  push    esi
0x10075f75  mov     szDescription, edi; this
0x10075f77  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10075f7d  call    edi
0x10075f7f  mov     eax, [ebp+cerrinfo._p]
0x10075f82  push    ebx
0x10075f83  push    eax
0x10075f84  mov     szDescription, [eax]
0x10075f86  mov     esi, [szDescription+14h]
0x10075f89  mov     szDescription, esi; this
0x10075f8b  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10075f91  call    esi
0x10075f93  push    [ebp+errinfo._p]; perrinfo
0x10075f96  push    0; dwReserved
0x10075f98  call    ds:__imp__SetErrorInfo@8; SetErrorInfo(x,x)
0x10075f9e  pop     edi
0x10075f9f  pop     esi
0x10075fa0  lea     szDescription, [ebp+errinfo]; ppref
0x10075fa3  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10075fa8  lea     szDescription, [ebp+cerrinfo]; ppref
0x10075fab  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10075fb0  pop     ebx
0x10075fb1  leave
0x10075fb2  retn
```
