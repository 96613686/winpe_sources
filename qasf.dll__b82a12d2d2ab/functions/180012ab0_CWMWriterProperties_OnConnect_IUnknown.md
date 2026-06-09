# CWMWriterProperties::OnConnect(IUnknown *)

- ea: `0x180012ab0`
- end: `0x180012b81`
- name: `?OnConnect@CWMWriterProperties@@EEAAJPEAUIUnknown@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(CWMWriterProperties *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x180001460`
- `0x180012ab0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CWMWriterProperties::OnConnect(CWMWriterProperties *this, struct IUnknown *a2)
{
  __int64 result; // rax
  void (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v6; // [rsp+30h] [rbp-18h] BYREF

  result = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
             a2,
             &IID_IConfigAsfWriter2,
             (char *)this + 96);
  if ( (int)result >= 0 )
  {
    result = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
               a2,
               &IID_IBaseFilter,
               (char *)this + 104);
    if ( (int)result >= 0 )
    {
      v5 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 13);
      v6 = 0;
      (**v5)(v5, &IID_IServiceProvider, &v6);
      (*(void (__fastcall **)(__int64, GUID *, GUID *, char *))(*(_QWORD *)v6 + 24LL))(
        v6,
        &IID_IWMWriterAdvanced2,
        &IID_IWMWriterAdvanced2,
        (char *)this + 112);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180012ab0  mov     [rsp+arg_10], rbx
0x180012ab5  mov     [rsp+arg_18], rsi
0x180012aba  push    rdi
0x180012abb  sub     rsp, 40h
0x180012abf  mov     rax, cs:__security_cookie
0x180012ac6  xor     rax, rsp
0x180012ac9  mov     [rsp+48h+var_10], rax
0x180012ace  mov     rax, [rdx]
0x180012ad1  lea     r8, [rcx+60h]
0x180012ad5  mov     rbx, rdx
0x180012ad8  mov     rdi, rcx
0x180012adb  lea     rdx, IID_IConfigAsfWriter2
0x180012ae2  mov     rcx, rbx
0x180012ae5  mov     rax, [rax]
0x180012ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012aed  test    eax, eax
0x180012aef  js      short loc_180012B64
0x180012af1  mov     rax, [rbx]
0x180012af4  lea     r8, [rdi+68h]
0x180012af8  lea     rdx, IID_IBaseFilter
0x180012aff  mov     rcx, rbx
0x180012b02  mov     rax, [rax]
0x180012b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b0a  test    eax, eax
0x180012b0c  js      short loc_180012B64
0x180012b0e  mov     rcx, [rdi+68h]
0x180012b12  lea     r8, [rsp+48h+var_18]
0x180012b17  mov     [rsp+48h+var_18], 0
0x180012b20  lea     rdx, IID_IServiceProvider
0x180012b27  mov     rax, [rcx]
0x180012b2a  mov     rax, [rax]
0x180012b2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b32  mov     rcx, [rsp+48h+var_18]
0x180012b37  lea     rdx, IID_IWMWriterAdvanced2
0x180012b3e  lea     r9, [rdi+70h]
0x180012b42  mov     r8, rdx
0x180012b45  mov     rax, [rcx]
0x180012b48  mov     rax, [rax+18h]
0x180012b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b51  mov     rcx, [rsp+48h+var_18]
0x180012b56  mov     rax, [rcx]
0x180012b59  mov     rax, [rax+10h]
0x180012b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b62  xor     eax, eax
0x180012b64  mov     rcx, [rsp+48h+var_10]
0x180012b69  xor     rcx, rsp; StackCookie
0x180012b6c  call    __security_check_cookie
0x180012b71  mov     rbx, [rsp+48h+arg_10]
0x180012b76  mov     rsi, [rsp+48h+arg_18]
0x180012b7b  add     rsp, 40h
0x180012b7f  pop     rdi
0x180012b80  retn
```
