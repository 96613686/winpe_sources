# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18002958c`
- end: `0x1800295fc`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002ad90`

## callees

- `0x18002958c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800295e0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800295e0`

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
0x18002958c  mov     [rsp+arg_0], rbx
0x180029591  mov     [rsp+arg_8], rsi
0x180029596  push    rdi
0x180029597  sub     rsp, 20h
0x18002959b  cmp     dword ptr [rcx], 0
0x18002959e  mov     rbx, rcx
0x1800295a1  jz      short loc_1800295EC
0x1800295a3  mov     rdi, [rcx+10h]
0x1800295a7  cmp     rdi, [rcx+18h]
0x1800295ab  jnb     short loc_1800295DC
0x1800295ad  mov     rsi, [rdi]
0x1800295b0  test    rsi, rsi
0x1800295b3  jz      short loc_1800295D2
0x1800295b5  mov     rcx, [rsi+20h]
0x1800295b9  test    rcx, rcx
0x1800295bc  jz      short loc_1800295CA
0x1800295be  mov     rax, [rcx]
0x1800295c1  mov     rax, [rax+10h]
0x1800295c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295ca  mov     qword ptr [rsi+20h], 0
0x1800295d2  add     rdi, 8
0x1800295d6  cmp     rdi, [rbx+18h]
0x1800295da  jb      short loc_1800295AD
0x1800295dc  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800295e0  call    cs:__imp_DeleteCriticalSection
0x1800295e6  mov     dword ptr [rbx], 0
0x1800295ec  mov     rbx, [rsp+28h+arg_0]
0x1800295f1  mov     rsi, [rsp+28h+arg_8]
0x1800295f6  add     rsp, 20h
0x1800295fa  pop     rdi
0x1800295fb  retn
```
