# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x1800147cc`
- end: `0x18001483c`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005b6c0`

## callees

- `0x1800147cc`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014820`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014820`

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
0x1800147cc  mov     [rsp+arg_0], rbx
0x1800147d1  mov     [rsp+arg_8], rsi
0x1800147d6  push    rdi
0x1800147d7  sub     rsp, 20h
0x1800147db  cmp     dword ptr [rcx], 0
0x1800147de  mov     rbx, rcx
0x1800147e1  jz      short loc_18001482C
0x1800147e3  mov     rdi, [rcx+10h]
0x1800147e7  cmp     rdi, [rcx+18h]
0x1800147eb  jnb     short loc_18001481C
0x1800147ed  mov     rsi, [rdi]
0x1800147f0  test    rsi, rsi
0x1800147f3  jz      short loc_180014812
0x1800147f5  mov     rcx, [rsi+20h]
0x1800147f9  test    rcx, rcx
0x1800147fc  jz      short loc_18001480A
0x1800147fe  mov     rax, [rcx]
0x180014801  mov     rax, [rax+10h]
0x180014805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001480a  mov     qword ptr [rsi+20h], 0
0x180014812  add     rdi, 8
0x180014816  cmp     rdi, [rbx+18h]
0x18001481a  jb      short loc_1800147ED
0x18001481c  lea     rcx, [rbx+20h]; lpCriticalSection
0x180014820  call    cs:__imp_DeleteCriticalSection
0x180014826  mov     dword ptr [rbx], 0
0x18001482c  mov     rbx, [rsp+28h+arg_0]
0x180014831  mov     rsi, [rsp+28h+arg_8]
0x180014836  add     rsp, 20h
0x18001483a  pop     rdi
0x18001483b  retn
```
