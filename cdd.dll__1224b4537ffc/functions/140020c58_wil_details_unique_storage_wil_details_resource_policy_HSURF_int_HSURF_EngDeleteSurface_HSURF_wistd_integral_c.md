# wil::details::unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>(void)

- ea: `0x140020c58`
- end: `0x140020c8c`
- name: `??1?$unique_storage@U?$resource_policy@PEAUHSURF__@@$$A6AHPEAU1@@Z$1?EngDeleteSurface@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `52`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140004630`
- `0x140027c80`

## callees

- `0x140020c58`
- `0x14002a1b0`

## import_xrefs

- `WIN32K!EngDeleteSurface` at `0x140020c74`

## pseudocode

```c
__int64 __fastcall wil::details::unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&int EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSURF__ *,int (HSURF__ *),&int EngDeleteSurface(HSURF__ *),wistd::integral_constant<unsigned __int64,0>,HSURF__ *,HSURF__ *,0,std::nullptr_t>>(
        __int64 *a1)
{
  __int64 result; // rax
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF
  BOOL (__stdcall *v3)(HSURF); // [rsp+38h] [rbp+10h] BYREF

  result = *a1;
  if ( *a1 )
  {
    v2 = *a1;
    v3 = EngDeleteSurface;
    return wistd::invoke<void (*)(void *),_D3DKMT_DISPLAYMODE * &>(&v3, &v2);
  }
  return result;
}

```

## disassembly

```asm
0x140020c58  sub     rsp, 28h
0x140020c5c  mov     rax, [rcx]
0x140020c5f  test    rax, rax
0x140020c62  jnz     short loc_140020C6A
0x140020c64  add     rsp, 28h
0x140020c68  retn
0x140020c6a  mov     [rsp+28h+arg_0], rax
0x140020c6f  lea     rdx, [rsp+28h+arg_0]
0x140020c74  mov     rax, cs:__imp_EngDeleteSurface
0x140020c7b  lea     rcx, [rsp+28h+arg_8]
0x140020c80  mov     [rsp+28h+arg_8], rax
0x140020c85  call    ??$invoke@P6AXPEAX@ZAEAPEAU_D3DKMT_DISPLAYMODE@@@wistd@@YAX$$QEAP6AXPEAX@ZAEAPEAU_D3DKMT_DISPLAYMODE@@@Z; wistd::invoke<void (*)(void *),_D3DKMT_DISPLAYMODE * &>(void (*&&)(void *),_D3DKMT_DISPLAYMODE * &)
0x140020c8a  jmp     short loc_140020C64
```
