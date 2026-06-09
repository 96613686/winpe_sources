# LPA::CoreLpa::~CoreLpa(void)

- ea: `0x1800727c0`
- end: `0x18007285c`
- name: `??1CoreLpa@LPA@@UEAA@XZ`
- size: `156`
- prototype: `void __fastcall(LPA::CoreLpa *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180072a40`

## callees

- `0x180065598`
- `0x1800709e4`
- `0x1800727c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800727f2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800727f2`

## pseudocode

```c
void __fastcall LPA::CoreLpa::~CoreLpa(LPA::CoreLpa *this)
{
  std::_Ref_count_base *v2; // rcx
  std::_Ref_count_base *v3; // rcx
  std::_Ref_count_base *v4; // rcx
  std::_Ref_count_base *v5; // rcx
  std::_Ref_count_base *v6; // rcx
  std::_Ref_count_base *v7; // rcx

  *(_QWORD *)this = &LPA::CoreLpa::`vftable';
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 208);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>((char *)this + 192);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 14);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 12);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 10);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  v5 = (std::_Ref_count_base *)*((_QWORD *)this + 8);
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  v6 = (std::_Ref_count_base *)*((_QWORD *)this + 6);
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  v7 = (std::_Ref_count_base *)*((_QWORD *)this + 4);
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
  *(_QWORD *)this = &RefCountingHelpers::RefCountedClass::`vftable';
}

```

## disassembly

```asm
0x1800727c0  push    rbx
0x1800727c2  sub     rsp, 20h
0x1800727c6  lea     rax, ??_7CoreLpa@LPA@@6B@; const LPA::CoreLpa::`vftable'
0x1800727cd  mov     rbx, rcx
0x1800727d0  mov     [rcx], rax
0x1800727d3  add     rcx, 0D0h
0x1800727da  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800727df  lea     rcx, [rbx+0C0h]
0x1800727e6  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800727eb  lea     rcx, [rbx+80h]; lpCriticalSection
0x1800727f2  call    cs:__imp_DeleteCriticalSection
0x1800727f8  mov     rcx, [rbx+70h]; this
0x1800727fc  test    rcx, rcx
0x1800727ff  jz      short loc_180072806
0x180072801  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180072806  mov     rcx, [rbx+60h]; this
0x18007280a  test    rcx, rcx
0x18007280d  jz      short loc_180072814
0x18007280f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180072814  mov     rcx, [rbx+50h]; this
0x180072818  test    rcx, rcx
0x18007281b  jz      short loc_180072822
0x18007281d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180072822  mov     rcx, [rbx+40h]; this
0x180072826  test    rcx, rcx
0x180072829  jz      short loc_180072830
0x18007282b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180072830  mov     rcx, [rbx+30h]; this
0x180072834  test    rcx, rcx
0x180072837  jz      short loc_18007283E
0x180072839  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007283e  mov     rcx, [rbx+20h]; this
0x180072842  test    rcx, rcx
0x180072845  jz      short loc_18007284C
0x180072847  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007284c  lea     rax, ??_7RefCountedClass@RefCountingHelpers@@6B@; const RefCountingHelpers::RefCountedClass::`vftable'
0x180072853  mov     [rbx], rax
0x180072856  add     rsp, 20h
0x18007285a  pop     rbx
0x18007285b  retn
```
