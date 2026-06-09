# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18001b2d8`
- end: `0x18001b348`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180022e50`

## callees

- `0x18001b2d8`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b32c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b32c`

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
0x18001b2d8  mov     [rsp+arg_0], rbx
0x18001b2dd  mov     [rsp+arg_8], rsi
0x18001b2e2  push    rdi
0x18001b2e3  sub     rsp, 20h
0x18001b2e7  cmp     dword ptr [rcx], 0
0x18001b2ea  mov     rbx, rcx
0x18001b2ed  jz      short loc_18001B338
0x18001b2ef  mov     rdi, [rcx+10h]
0x18001b2f3  cmp     rdi, [rcx+18h]
0x18001b2f7  jnb     short loc_18001B328
0x18001b2f9  mov     rsi, [rdi]
0x18001b2fc  test    rsi, rsi
0x18001b2ff  jz      short loc_18001B31E
0x18001b301  mov     rcx, [rsi+20h]
0x18001b305  test    rcx, rcx
0x18001b308  jz      short loc_18001B316
0x18001b30a  mov     rax, [rcx]
0x18001b30d  mov     rax, [rax+10h]
0x18001b311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b316  mov     qword ptr [rsi+20h], 0
0x18001b31e  add     rdi, 8
0x18001b322  cmp     rdi, [rbx+18h]
0x18001b326  jb      short loc_18001B2F9
0x18001b328  lea     rcx, [rbx+20h]; lpCriticalSection
0x18001b32c  call    cs:__imp_DeleteCriticalSection
0x18001b332  mov     dword ptr [rbx], 0
0x18001b338  mov     rbx, [rsp+28h+arg_0]
0x18001b33d  mov     rsi, [rsp+28h+arg_8]
0x18001b342  add     rsp, 20h
0x18001b346  pop     rdi
0x18001b347  retn
```
