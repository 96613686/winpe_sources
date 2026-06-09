# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180031b90`
- end: `0x180031c00`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180037500`

## callees

- `0x180031b90`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031be4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180031be4`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::~CAtlComModule(ATL::CAtlComModule *this)
{
  __int64 *i; // rdi
  __int64 v3; // rsi
  __int64 v4; // rcx

  if ( *(_DWORD *)this )
  {
    for ( i = (__int64 *)*((_QWORD *)this + 2); (unsigned __int64)i < *((_QWORD *)this + 3); ++i )
    {
      v3 = *i;
      if ( *i )
      {
        v4 = *(_QWORD *)(v3 + 32);
        if ( v4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        *(_QWORD *)(v3 + 32) = 0;
      }
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *(_DWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180031b90  mov     [rsp+arg_0], rbx
0x180031b95  mov     [rsp+arg_8], rsi
0x180031b9a  push    rdi
0x180031b9b  sub     rsp, 20h
0x180031b9f  cmp     dword ptr [rcx], 0
0x180031ba2  mov     rbx, rcx
0x180031ba5  jz      short loc_180031BF0
0x180031ba7  mov     rdi, [rcx+10h]
0x180031bab  cmp     rdi, [rcx+18h]
0x180031baf  jnb     short loc_180031BE0
0x180031bb1  mov     rsi, [rdi]
0x180031bb4  test    rsi, rsi
0x180031bb7  jz      short loc_180031BD6
0x180031bb9  mov     rcx, [rsi+20h]
0x180031bbd  test    rcx, rcx
0x180031bc0  jz      short loc_180031BCE
0x180031bc2  mov     rax, [rcx]
0x180031bc5  mov     rax, [rax+10h]
0x180031bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031bce  mov     qword ptr [rsi+20h], 0
0x180031bd6  add     rdi, 8
0x180031bda  cmp     rdi, [rbx+18h]
0x180031bde  jb      short loc_180031BB1
0x180031be0  lea     rcx, [rbx+20h]; lpCriticalSection
0x180031be4  call    cs:__imp_DeleteCriticalSection
0x180031bea  mov     dword ptr [rbx], 0
0x180031bf0  mov     rbx, [rsp+28h+arg_0]
0x180031bf5  mov     rsi, [rsp+28h+arg_8]
0x180031bfa  add     rsp, 20h
0x180031bfe  pop     rdi
0x180031bff  retn
```
