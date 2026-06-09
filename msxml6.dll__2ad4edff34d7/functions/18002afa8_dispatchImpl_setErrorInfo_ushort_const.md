# _dispatchImpl::setErrorInfo(ushort const *)

- ea: `0x18002afa8`
- end: `0x18002b05d`
- name: `?setErrorInfo@_dispatchImpl@@KAXPEBG@Z`
- size: `181`
- prototype: `void __fastcall(const wchar_t *szDescription)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002b09c`
- `0x1800bd174`
- `0x1800c5938`
- `0x1800d4ea4`

## callees

- `0x18000d7d0`
- `0x18002afa8`
- `0x18009c5d4`
- `0x180188010`

## import_xrefs

- `combase!SetErrorInfo` at `0x18002b033`
- `combase!SetErrorInfo` at `0x18002b033`
- `combase!CreateErrorInfo` at `0x18002afcf`
- `combase!CreateErrorInfo` at `0x18002afcf`

## pseudocode

```c
void __fastcall _dispatchImpl::setErrorInfo(wchar_t *szDescription)
{
  ICreateErrorInfo *p; // rdi
  HRESULT (__fastcall *SetSource)(ICreateErrorInfo *, wchar_t *); // rbx
  wchar_t *Source; // rax
  _reference<ICreateErrorInfo> cerrinfo; // [rsp+38h] [rbp+10h] BYREF
  _reference<IErrorInfo> errinfo; // [rsp+40h] [rbp+18h] BYREF

  cerrinfo._p = 0;
  errinfo._p = 0;
  if ( CreateErrorInfo(&cerrinfo._p) >= 0
    && cerrinfo._p->QueryInterface(cerrinfo._p, &IID_IErrorInfo, (void **)&errinfo) >= 0 )
  {
    p = cerrinfo._p;
    SetSource = cerrinfo._p->SetSource;
    Source = _dispatchImpl::GetSource();
    SetSource(p, Source);
    cerrinfo._p->SetDescription(cerrinfo._p, szDescription);
    SetErrorInfo(0, errinfo._p);
  }
  release(&errinfo._p);
  release(&cerrinfo._p);
}

```

## disassembly

```asm
0x18002afa8  mov     rax, rsp
0x18002afab  mov     [rax+8], rbx
0x18002afaf  mov     [rax+20h], rsi
0x18002afb3  push    rdi
0x18002afb4  sub     rsp, 20h
0x18002afb8  mov     rsi, szDescription
0x18002afbb  mov     qword ptr [rax+10h], 0
0x18002afc3  lea     szDescription, [rax+10h]; pperrinfo
0x18002afc7  mov     qword ptr [rax+18h], 0
0x18002afcf  call    cs:__imp_CreateErrorInfo
0x18002afd5  test    eax, eax
0x18002afd7  js      short loc_18002B039
0x18002afd9  mov     szDescription, [rsp+28h+cerrinfo._p]
0x18002afde  lea     r8, [rsp+28h+errinfo]
0x18002afe3  lea     rdx, IID_IErrorInfo
0x18002afea  mov     rax, [szDescription]
0x18002afed  mov     rax, [rax]
0x18002aff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aff5  test    eax, eax
0x18002aff7  js      short loc_18002B039
0x18002aff9  mov     rdi, [rsp+28h+cerrinfo._p]
0x18002affe  mov     rax, [rdi]
0x18002b001  mov     rbx, [rax+20h]
0x18002b005  call    ?GetSource@_dispatchImpl@@KAPEAGXZ; _dispatchImpl::GetSource(void)
0x18002b00a  mov     rdx, rax
0x18002b00d  mov     szDescription, rdi
0x18002b010  mov     rax, rbx
0x18002b013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b018  mov     szDescription, [rsp+28h+cerrinfo._p]
0x18002b01d  mov     rdx, rsi
0x18002b020  mov     rax, [szDescription]
0x18002b023  mov     rax, [rax+28h]
0x18002b027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b02c  mov     rdx, [rsp+28h+errinfo._p]; perrinfo
0x18002b031  xor     ecx, ecx; dwReserved
0x18002b033  call    cs:__imp_SetErrorInfo
0x18002b039  lea     szDescription, [rsp+28h+errinfo]; ppref
0x18002b03e  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18002b043  lea     szDescription, [rsp+28h+cerrinfo]; ppref
0x18002b048  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x18002b04d  mov     rbx, [rsp+28h+arg_0]
0x18002b052  mov     rsi, [rsp+28h+arg_18]
0x18002b057  add     rsp, 20h
0x18002b05b  pop     rdi
0x18002b05c  retn
```
