# CWMWriter::JoinFilterGraph(IFilterGraph *,ushort const *)

- ea: `0x180010490`
- end: `0x1800105d8`
- name: `?JoinFilterGraph@CWMWriter@@UEAAJPEAUIFilterGraph@@PEBG@Z`
- size: `328`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, struct IFilterGraph *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180001460`
- `0x180004f90`
- `0x18000f414`
- `0x180010490`
- `0x18001f010`

## pseudocode

```c
int __fastcall CWMWriter::JoinFilterGraph(CWMWriter *this, struct IFilterGraph *a2, const unsigned __int16 *a3)
{
  int result; // eax
  HRESULT WMWriter; // ebx
  struct IFilterGraphVtbl *lpVtbl; // rax
  int v8; // ebx
  __int64 v9; // [rsp+30h] [rbp-38h] BYREF
  __int64 v10; // [rsp+38h] [rbp-30h] BYREF

  result = CBaseFilter::JoinFilterGraph(this, a2, a3);
  WMWriter = result;
  if ( result >= 0 )
  {
    if ( a2 )
    {
      if ( !*((_DWORD *)this + 92) )
      {
        lpVtbl = a2->lpVtbl;
        v9 = 0;
        if ( ((__int64 (__fastcall *)(struct IFilterGraph *, GUID *, __int64 *))lpVtbl->QueryInterface)(
               a2,
               &IID_IObjectWithSite,
               &v9) >= 0 )
        {
          v10 = 0;
          v8 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v9 + 32LL))(
                 v9,
                 &IID_IServiceProvider,
                 &v10);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
          if ( v8 >= 0 )
          {
            (*(void (__fastcall **)(__int64, GUID *, GUID *, char *))(*(_QWORD *)v10 + 24LL))(
              v10,
              &IID_IWMReader,
              &IID_IUnknown,
              (char *)this + 360);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          }
        }
        *((_DWORD *)this + 92) = 1;
      }
      WMWriter = 0;
      if ( !*((_QWORD *)this + 36) )
      {
        WMWriter = CWMWriter::CreateWMWriter((CWMWriter *)((char *)this - 24));
        if ( WMWriter >= 0 )
          WMWriter = (*(__int64 (__fastcall **)(char *, char *))(*((_QWORD *)this + 16) + 40LL))(
                       (char *)this + 128,
                       (char *)this + 340);
      }
      if ( WMWriter < 0 )
        CBaseFilter::JoinFilterGraph(this, 0, 0);
    }
    return WMWriter;
  }
  return result;
}

```

## disassembly

```asm
0x180010490  push    rbx
0x180010492  push    rsi
0x180010493  push    rdi
0x180010494  sub     rsp, 50h
0x180010498  mov     rax, cs:__security_cookie
0x18001049f  xor     rax, rsp
0x1800104a2  mov     [rsp+68h+var_28], rax
0x1800104a7  mov     rsi, rdx
0x1800104aa  mov     rdi, rcx
0x1800104ad  call    ?JoinFilterGraph@CBaseFilter@@UEAAJPEAUIFilterGraph@@PEBG@Z; CBaseFilter::JoinFilterGraph(IFilterGraph *,ushort const *)
0x1800104b2  mov     ebx, eax
0x1800104b4  test    eax, eax
0x1800104b6  js      loc_1800105C3
0x1800104bc  test    rsi, rsi
0x1800104bf  jz      loc_1800105C1
0x1800104c5  cmp     dword ptr [rdi+170h], 0
0x1800104cc  jnz     loc_18001057A
0x1800104d2  mov     rax, [rsi]
0x1800104d5  lea     r8, [rsp+68h+var_38]
0x1800104da  lea     rdx, IID_IObjectWithSite
0x1800104e1  mov     [rsp+68h+var_38], 0
0x1800104ea  mov     rcx, rsi
0x1800104ed  mov     rax, [rax]
0x1800104f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104f5  test    eax, eax
0x1800104f7  js      short loc_180010570
0x1800104f9  mov     rcx, [rsp+68h+var_38]
0x1800104fe  lea     r8, [rsp+68h+var_30]
0x180010503  mov     [rsp+68h+var_30], 0
0x18001050c  lea     rdx, IID_IServiceProvider
0x180010513  mov     rax, [rcx]
0x180010516  mov     rax, [rax+20h]
0x18001051a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001051f  mov     rdx, [rsp+68h+var_38]
0x180010524  mov     ebx, eax
0x180010526  mov     rcx, [rdx]
0x180010529  mov     rax, [rcx+10h]
0x18001052d  mov     rcx, rdx
0x180010530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010535  test    ebx, ebx
0x180010537  js      short loc_180010570
0x180010539  mov     rcx, [rsp+68h+var_30]
0x18001053e  lea     r9, [rdi+168h]
0x180010545  lea     r8, IID_IUnknown
0x18001054c  lea     rdx, IID_IWMReader
0x180010553  mov     rax, [rcx]
0x180010556  mov     rax, [rax+18h]
0x18001055a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001055f  mov     rcx, [rsp+68h+var_30]
0x180010564  mov     rax, [rcx]
0x180010567  mov     rax, [rax+10h]
0x18001056b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010570  mov     dword ptr [rdi+170h], 1
0x18001057a  xor     ebx, ebx
0x18001057c  cmp     [rdi+120h], rbx
0x180010583  jnz     short loc_1800105B0
0x180010585  lea     rcx, [rdi-18h]; this
0x180010589  call    ?CreateWMWriter@CWMWriter@@QEAAJXZ; CWMWriter::CreateWMWriter(void)
0x18001058e  mov     ebx, eax
0x180010590  test    eax, eax
0x180010592  js      short loc_1800105B0
0x180010594  lea     rcx, [rdi+80h]
0x18001059b  mov     rax, [rcx]
0x18001059e  lea     rdx, [rdi+154h]
0x1800105a5  mov     rax, [rax+28h]
0x1800105a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105ae  mov     ebx, eax
0x1800105b0  test    ebx, ebx
0x1800105b2  jns     short loc_1800105C1
0x1800105b4  xor     r8d, r8d; unsigned __int16 *
0x1800105b7  xor     edx, edx; struct IFilterGraph *
0x1800105b9  mov     rcx, rdi; this
0x1800105bc  call    ?JoinFilterGraph@CBaseFilter@@UEAAJPEAUIFilterGraph@@PEBG@Z; CBaseFilter::JoinFilterGraph(IFilterGraph *,ushort const *)
0x1800105c1  mov     eax, ebx
0x1800105c3  mov     rcx, [rsp+68h+var_28]
0x1800105c8  xor     rcx, rsp; StackCookie
0x1800105cb  call    __security_check_cookie
0x1800105d0  add     rsp, 50h
0x1800105d4  pop     rdi
0x1800105d5  pop     rsi
0x1800105d6  pop     rbx
0x1800105d7  retn
```
