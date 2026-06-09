# _dispatchImpl::setErrorInfo(ushort const *)

- ea: `0x1800941fc`
- end: `0x1800942be`
- name: `?setErrorInfo@_dispatchImpl@@KAXPEBG@Z`
- size: `194`
- prototype: `void __fastcall(const wchar_t *szDescription)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180094068`
- `0x1800be9d8`
- `0x1800c71f8`
- `0x1800d6b44`

## callees

- `0x180019e20`
- `0x1800941fc`
- `0x18009ce00`
- `0x18018c010`

## import_xrefs

- `combase!SetErrorInfo` at `0x18009428d`
- `combase!SetErrorInfo` at `0x18009428d`
- `combase!CreateErrorInfo` at `0x180094223`
- `combase!CreateErrorInfo` at `0x180094223`

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
0x1800941fc  mov     rax, rsp
0x1800941ff  mov     [rax+8], rbx
0x180094203  mov     [rax+20h], rsi
0x180094207  push    rdi
0x180094208  sub     rsp, 20h
0x18009420c  mov     rsi, szDescription
0x18009420f  mov     qword ptr [rax+10h], 0
0x180094217  lea     szDescription, [rax+10h]; pperrinfo
0x18009421b  mov     qword ptr [rax+18h], 0
0x180094223  call    cs:__imp_CreateErrorInfo
0x18009422a  nop     dword ptr [rax+rax+00h]
0x18009422f  test    eax, eax
0x180094231  js      short loc_180094299
0x180094233  mov     szDescription, [rsp+28h+cerrinfo._p]
0x180094238  lea     r8, [rsp+28h+errinfo]
0x18009423d  lea     rdx, IID_IErrorInfo
0x180094244  mov     rax, [szDescription]
0x180094247  mov     rax, [rax]
0x18009424a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009424f  test    eax, eax
0x180094251  js      short loc_180094299
0x180094253  mov     rdi, [rsp+28h+cerrinfo._p]
0x180094258  mov     rax, [rdi]
0x18009425b  mov     rbx, [rax+20h]
0x18009425f  call    ?GetSource@_dispatchImpl@@KAPEAGXZ; _dispatchImpl::GetSource(void)
0x180094264  mov     rdx, rax
0x180094267  mov     szDescription, rdi
0x18009426a  mov     rax, rbx
0x18009426d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094272  mov     szDescription, [rsp+28h+cerrinfo._p]
0x180094277  mov     rdx, rsi
0x18009427a  mov     rax, [szDescription]
0x18009427d  mov     rax, [rax+28h]
0x180094281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094286  mov     rdx, [rsp+28h+errinfo._p]; perrinfo
0x18009428b  xor     ecx, ecx; dwReserved
0x18009428d  call    cs:__imp_SetErrorInfo
0x180094294  nop     dword ptr [rax+rax+00h]
0x180094299  lea     szDescription, [rsp+28h+errinfo]; ppref
0x18009429e  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800942a3  lea     szDescription, [rsp+28h+cerrinfo]; ppref
0x1800942a8  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800942ad  mov     rbx, [rsp+28h+arg_0]
0x1800942b2  mov     rsi, [rsp+28h+arg_18]
0x1800942b7  add     rsp, 20h
0x1800942bb  pop     rdi
0x1800942bc  retn
```
