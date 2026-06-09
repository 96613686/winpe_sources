# CIStreamToIByteStream::HrGetFileName(wchar_t *,uint)

- ea: `0x180100f10`
- end: `0x180100fc7`
- name: `?HrGetFileName@CIStreamToIByteStream@@UEBAJPEA_WI@Z`
- size: `183`
- prototype: `int(CIStreamToIByteStream *__hidden this, wchar_t *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180012bf8`
- `0x18003e690`
- `0x180100f10`
- `0x180146090`
- `0x1801460c0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x180100f94`
- `api-ms-win-crt-string-l1-1-0!wcscpy_s` at `0x180100f94`
- `ole32!CoTaskMemFree` at `0x180100f9f`
- `ole32!CoTaskMemFree` at `0x180100f9f`

## pseudocode

```c
__int64 __fastcall CIStreamToIByteStream::HrGetFileName(CIStreamToIByteStream *this, wchar_t *a2, unsigned int a3)
{
  rsize_t v3; // rsi
  int v6; // edi
  __int64 v7; // rax
  wchar_t *Source[10]; // [rsp+20h] [rbp-78h] BYREF

  v3 = a3;
  if ( a2 )
  {
    if ( a3 )
      *a2 = 0;
    memset(Source, 0, sizeof(Source));
    v7 = Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->((char *)this + 32);
    v6 = (*(__int64 (__fastcall **)(__int64, wchar_t **, _QWORD))(*(_QWORD *)v7 + 96LL))(v7, Source, 0);
    if ( v6 >= 0 && Source[0] )
    {
      wcscpy_s(a2, v3, Source[0]);
      CoTaskMemFree(Source[0]);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180100f10  mov     [rsp+arg_18], rbx
0x180100f15  push    rbp
0x180100f16  push    rsi
0x180100f17  push    rdi
0x180100f18  sub     rsp, 80h
0x180100f1f  mov     rax, cs:__security_cookie
0x180100f26  xor     rax, rsp
0x180100f29  mov     [rsp+98h+var_28], rax
0x180100f2e  mov     esi, r8d
0x180100f31  mov     rbx, rdx
0x180100f34  mov     rdi, rcx
0x180100f37  xor     ebp, ebp
0x180100f39  test    rdx, rdx
0x180100f3c  jnz     short loc_180100F45
0x180100f3e  mov     edi, 80004003h
0x180100f43  jmp     short loc_180100FA5
0x180100f45  test    r8d, r8d
0x180100f48  jz      short loc_180100F4D
0x180100f4a  mov     [rdx], bp
0x180100f4d  xor     edx, edx; Val
0x180100f4f  lea     r8d, [rdx+50h]; Size
0x180100f53  lea     rcx, [rsp+98h+Source]; void *
0x180100f58  call    memset
0x180100f5d  lea     rcx, [rdi+20h]
0x180100f61  call    ??C?$TCntPtr@UICancellationListener@Async@Mso@@@Mso@@QEBAPEAUICancellationListener@Async@1@XZ; Mso::TCntPtr<Mso::Async::ICancellationListener>::operator->(void)
0x180100f66  mov     rcx, rax
0x180100f69  mov     rax, [rax]
0x180100f6c  xor     r8d, r8d
0x180100f6f  lea     rdx, [rsp+98h+Source]
0x180100f74  mov     rax, [rax+60h]
0x180100f78  call    cs:__guard_dispatch_icall_fptr
0x180100f7e  mov     edi, eax
0x180100f80  test    eax, eax
0x180100f82  js      short loc_180100FA5
0x180100f84  mov     r8, [rsp+98h+Source]; Source
0x180100f89  test    r8, r8
0x180100f8c  jz      short loc_180100FA5
0x180100f8e  mov     rdx, rsi; SizeInWords
0x180100f91  mov     rcx, rbx; Destination
0x180100f94  call    cs:__imp_wcscpy_s
0x180100f9a  mov     rcx, [rsp+98h+Source]; pv
0x180100f9f  call    cs:__imp_CoTaskMemFree
0x180100fa5  mov     eax, edi
0x180100fa7  mov     rcx, [rsp+98h+var_28]
0x180100fac  xor     rcx, rsp; StackCookie
0x180100faf  call    __security_check_cookie
0x180100fb4  mov     rbx, [rsp+98h+arg_18]
0x180100fbc  add     rsp, 80h
0x180100fc3  pop     rdi
0x180100fc4  pop     rsi
0x180100fc5  pop     rbp
0x180100fc6  retn
```
