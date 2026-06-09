# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000a190`
- end: `0x18000a200`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011d10`

## callees

- `0x18000a190`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a1e4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a1e4`

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
0x18000a190  mov     [rsp+arg_0], rbx
0x18000a195  mov     [rsp+arg_8], rsi
0x18000a19a  push    rdi
0x18000a19b  sub     rsp, 20h
0x18000a19f  cmp     dword ptr [rcx], 0
0x18000a1a2  mov     rbx, rcx
0x18000a1a5  jz      short loc_18000A1F0
0x18000a1a7  mov     rdi, [rcx+10h]
0x18000a1ab  cmp     rdi, [rcx+18h]
0x18000a1af  jnb     short loc_18000A1E0
0x18000a1b1  mov     rsi, [rdi]
0x18000a1b4  test    rsi, rsi
0x18000a1b7  jz      short loc_18000A1D6
0x18000a1b9  mov     rcx, [rsi+20h]
0x18000a1bd  test    rcx, rcx
0x18000a1c0  jz      short loc_18000A1CE
0x18000a1c2  mov     rax, [rcx]
0x18000a1c5  mov     rax, [rax+10h]
0x18000a1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1ce  mov     qword ptr [rsi+20h], 0
0x18000a1d6  add     rdi, 8
0x18000a1da  cmp     rdi, [rbx+18h]
0x18000a1de  jb      short loc_18000A1B1
0x18000a1e0  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000a1e4  call    cs:__imp_DeleteCriticalSection
0x18000a1ea  mov     dword ptr [rbx], 0
0x18000a1f0  mov     rbx, [rsp+28h+arg_0]
0x18000a1f5  mov     rsi, [rsp+28h+arg_8]
0x18000a1fa  add     rsp, 20h
0x18000a1fe  pop     rdi
0x18000a1ff  retn
```
