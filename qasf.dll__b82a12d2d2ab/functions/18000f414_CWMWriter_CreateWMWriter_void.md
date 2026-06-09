# CWMWriter::CreateWMWriter(void)

- ea: `0x18000f414`
- end: `0x18000f58e`
- name: `?CreateWMWriter@CWMWriter@@QEAAJXZ`
- size: `378`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180010490`
- `0x180011580`

## callees

- `0x180001460`
- `0x18000f414`
- `0x180010948`
- `0x180011304`
- `0x18001f010`

## import_xrefs

- `WMVCore!WMCreateWriterFileSink` at `0x18000f4d7`
- `WMVCore!WMCreateWriterFileSink` at `0x18000f4d7`
- `WMVCore!WMCreateWriter` at `0x18000f44c`
- `WMVCore!WMCreateWriter` at `0x18000f44c`

## pseudocode

```c
HRESULT __fastcall CWMWriter::CreateWMWriter(CWMWriter *this)
{
  _QWORD *v2; // rdi
  HRESULT result; // eax
  int v4; // edi
  IWMWriterFileSink *ppSink; // [rsp+20h] [rbp-18h] BYREF

  CWMWriter::ReleaseWMWriter(this);
  v2 = (_QWORD *)((char *)this + 312);
  result = WMCreateWriter(*((IUnknown **)this + 48), (IWMWriter **)this + 39);
  if ( result >= 0 )
  {
    result = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v2)(*v2, &IID_IWMWriterAdvanced, (char *)this + 320);
    if ( result >= 0 )
    {
      result = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v2)(*v2, &IID_IWMHeaderInfo, (char *)this + 336);
      if ( result >= 0 )
      {
        result = (**(__int64 (__fastcall ***)(_QWORD, GUID *, char *))*v2)(
                   *v2,
                   &IID_IWMWriterPreprocess,
                   (char *)this + 352);
        if ( result >= 0 )
        {
          ppSink = 0;
          result = WMCreateWriterFileSink(&ppSink);
          if ( result >= 0 )
          {
            result = ((__int64 (__fastcall *)(IWMWriterFileSink *, GUID *, char *))ppSink->lpVtbl->QueryInterface)(
                       ppSink,
                       &IID_IWMRegisterCallback,
                       (char *)this + 400);
            if ( result >= 0 )
            {
              result = ((__int64 (__fastcall *)(IWMWriterFileSink *, GUID *, char *))ppSink->lpVtbl->QueryInterface)(
                         ppSink,
                         &IID_IWMWriterFileSink3,
                         (char *)this + 328);
              if ( result >= 0 )
              {
                v4 = (*(__int64 (__fastcall **)(_QWORD, IWMWriterFileSink *))(**((_QWORD **)this + 40) + 40LL))(
                       *((_QWORD *)this + 40),
                       ppSink);
                ((void (__fastcall *)(IWMWriterFileSink *))ppSink->lpVtbl->Release)(ppSink);
                if ( v4 >= 0 )
                  return CWMWriter::Open(this);
                else
                  return v4;
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f414  mov     [rsp+arg_8], rbx
0x18000f419  mov     [rsp+arg_10], rsi
0x18000f41e  push    rdi
0x18000f41f  sub     rsp, 30h
0x18000f423  mov     rax, cs:__security_cookie
0x18000f42a  xor     rax, rsp
0x18000f42d  mov     [rsp+38h+var_10], rax
0x18000f432  mov     rbx, rcx
0x18000f435  call    ?ReleaseWMWriter@CWMWriter@@QEAAXXZ; CWMWriter::ReleaseWMWriter(void)
0x18000f43a  nop
0x18000f43b  lea     rdi, [rbx+138h]
0x18000f442  mov     rdx, rdi; ppWriter
0x18000f445  mov     rcx, [rbx+180h]; pUnkCert
0x18000f44c  call    cs:__imp_WMCreateWriter
0x18000f452  test    eax, eax
0x18000f454  js      loc_18000F571
0x18000f45a  mov     rcx, [rdi]
0x18000f45d  lea     rsi, [rbx+140h]
0x18000f464  mov     rax, [rcx]
0x18000f467  mov     r8, rsi
0x18000f46a  lea     rdx, IID_IWMWriterAdvanced
0x18000f471  mov     rax, [rax]
0x18000f474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f479  test    eax, eax
0x18000f47b  js      loc_18000F571
0x18000f481  mov     rcx, [rdi]
0x18000f484  mov     rax, [rcx]
0x18000f487  lea     r8, [rbx+150h]
0x18000f48e  lea     rdx, IID_IWMHeaderInfo
0x18000f495  mov     rax, [rax]
0x18000f498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f49d  test    eax, eax
0x18000f49f  js      loc_18000F571
0x18000f4a5  mov     rcx, [rdi]
0x18000f4a8  mov     rax, [rcx]
0x18000f4ab  lea     r8, [rbx+160h]
0x18000f4b2  lea     rdx, IID_IWMWriterPreprocess
0x18000f4b9  mov     rax, [rax]
0x18000f4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4c1  test    eax, eax
0x18000f4c3  js      loc_18000F571
0x18000f4c9  mov     [rsp+38h+ppSink], 0
0x18000f4d2  lea     rcx, [rsp+38h+ppSink]; ppSink
0x18000f4d7  call    cs:__imp_WMCreateWriterFileSink
0x18000f4dd  test    eax, eax
0x18000f4df  js      loc_18000F571
0x18000f4e5  mov     rcx, [rsp+38h+ppSink]
0x18000f4ea  mov     rax, [rcx]
0x18000f4ed  lea     r8, [rbx+190h]
0x18000f4f4  lea     rdx, IID_IWMRegisterCallback
0x18000f4fb  mov     rax, [rax]
0x18000f4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f503  test    eax, eax
0x18000f505  js      short loc_18000F571
0x18000f507  mov     rcx, [rsp+38h+ppSink]
0x18000f50c  mov     rax, [rcx]
0x18000f50f  lea     r8, [rbx+148h]
0x18000f516  lea     rdx, IID_IWMWriterFileSink3
0x18000f51d  mov     rax, [rax]
0x18000f520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f525  test    eax, eax
0x18000f527  js      short loc_18000F571
0x18000f529  mov     rcx, [rsi]
0x18000f52c  mov     rax, [rcx]
0x18000f52f  mov     rdx, [rsp+38h+ppSink]
0x18000f534  mov     rax, [rax+28h]
0x18000f538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f53d  mov     edi, eax
0x18000f53f  mov     rdx, [rsp+38h+ppSink]
0x18000f544  mov     rcx, [rdx]
0x18000f547  mov     rax, [rcx+10h]
0x18000f54b  mov     rcx, rdx
0x18000f54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f553  test    edi, edi
0x18000f555  jns     short loc_18000F55B
0x18000f557  mov     eax, edi
0x18000f559  jmp     short loc_18000F571
0x18000f55b  mov     rcx, rbx; this
0x18000f55e  call    ?Open@CWMWriter@@QEAAJXZ; CWMWriter::Open(void)
0x18000f563  jmp     short loc_18000F571
0x18000f565  mov     eax, 8007007Eh
0x18000f56a  jmp     short loc_18000F571
0x18000f56c  mov     eax, 8007007Eh
0x18000f571  mov     rcx, [rsp+38h+var_10]
0x18000f576  xor     rcx, rsp; StackCookie
0x18000f579  call    __security_check_cookie
0x18000f57e  mov     rbx, [rsp+38h+arg_8]
0x18000f583  mov     rsi, [rsp+38h+arg_10]
0x18000f588  add     rsp, 30h
0x18000f58c  pop     rdi
0x18000f58d  retn
```
