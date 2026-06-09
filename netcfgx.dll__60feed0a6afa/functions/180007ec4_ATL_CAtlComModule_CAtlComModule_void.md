# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180007ec4`
- end: `0x180007f34`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800128a0`

## callees

- `0x180007ec4`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007f18`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007f18`

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
0x180007ec4  mov     [rsp+arg_0], rbx
0x180007ec9  mov     [rsp+arg_8], rsi
0x180007ece  push    rdi
0x180007ecf  sub     rsp, 20h
0x180007ed3  cmp     dword ptr [rcx], 0
0x180007ed6  mov     rbx, rcx
0x180007ed9  jz      short loc_180007F24
0x180007edb  mov     rdi, [rcx+10h]
0x180007edf  cmp     rdi, [rcx+18h]
0x180007ee3  jnb     short loc_180007F14
0x180007ee5  mov     rsi, [rdi]
0x180007ee8  test    rsi, rsi
0x180007eeb  jz      short loc_180007F0A
0x180007eed  mov     rcx, [rsi+20h]
0x180007ef1  test    rcx, rcx
0x180007ef4  jz      short loc_180007F02
0x180007ef6  mov     rax, [rcx]
0x180007ef9  mov     rax, [rax+10h]
0x180007efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f02  mov     qword ptr [rsi+20h], 0
0x180007f0a  add     rdi, 8
0x180007f0e  cmp     rdi, [rbx+18h]
0x180007f12  jb      short loc_180007EE5
0x180007f14  lea     rcx, [rbx+20h]; lpCriticalSection
0x180007f18  call    cs:__imp_DeleteCriticalSection
0x180007f1e  mov     dword ptr [rbx], 0
0x180007f24  mov     rbx, [rsp+28h+arg_0]
0x180007f29  mov     rsi, [rsp+28h+arg_8]
0x180007f2e  add     rsp, 20h
0x180007f32  pop     rdi
0x180007f33  retn
```
