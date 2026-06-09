# AutoLibrary::load(void)

- ea: `0x180008c80`
- end: `0x180008ccc`
- name: `?load@AutoLibrary@@AEAAXXZ`
- size: `76`
- prototype: `void __fastcall(AutoLibrary *__hidden this)`
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800083f8`
- `0x180008730`
- `0x180008d2c`
- `0x18001ff80`
- `0x180020180`
- `0x180023020`
- `0x180024320`
- `0x1800256a0`
- `0x1800270a0`

## callees

- `0x1800055a0`
- `0x180007cd0`
- `0x180008c80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008ca6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008ca6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c89`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c89`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AutoLibrary::load(AutoLibrary *this)
{
  bool v2; // zf
  HMODULE Library; // rax
  AutoLibrary *v4; // [rsp+30h] [rbp+8h] BYREF

  AcquireSRWLockExclusive((PSRWLOCK)this);
  v2 = *((_BYTE *)this + 16) == 0;
  v4 = this;
  if ( v2 )
  {
    Library = LoadLibraryExW(*((LPCWSTR *)this + 3), 0, 0x800u);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      (char *)this + 8,
      Library);
    *((_BYTE *)this + 16) = 1;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v4);
}

```

## disassembly

```asm
0x180008c80  push    rbx
0x180008c82  sub     rsp, 20h
0x180008c86  mov     rbx, rcx
0x180008c89  call    cs:__imp_AcquireSRWLockExclusive
0x180008c8f  cmp     byte ptr [rbx+10h], 0
0x180008c93  mov     [rsp+28h+arg_0], rbx
0x180008c98  jnz     short loc_180008CBC
0x180008c9a  mov     rcx, [rbx+18h]; lpLibFileName
0x180008c9e  xor     edx, edx; hFile
0x180008ca0  mov     r8d, 800h; dwFlags
0x180008ca6  call    cs:__imp_LoadLibraryExW
0x180008cac  mov     rdx, rax
0x180008caf  lea     rcx, [rbx+8]
0x180008cb3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x180008cb8  mov     byte ptr [rbx+10h], 1
0x180008cbc  lea     rcx, [rsp+28h+arg_0]
0x180008cc1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008cc6  add     rsp, 20h
0x180008cca  pop     rbx
0x180008ccb  retn
```
