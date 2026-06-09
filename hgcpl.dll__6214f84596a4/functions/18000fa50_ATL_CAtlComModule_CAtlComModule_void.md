# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000fa50`
- end: `0x18000fac0`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019000`

## callees

- `0x18000fa50`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000faa4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000faa4`

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
0x18000fa50  mov     [rsp+arg_0], rbx
0x18000fa55  mov     [rsp+arg_8], rsi
0x18000fa5a  push    rdi
0x18000fa5b  sub     rsp, 20h
0x18000fa5f  cmp     dword ptr [rcx], 0
0x18000fa62  mov     rbx, rcx
0x18000fa65  jz      short loc_18000FAB0
0x18000fa67  mov     rdi, [rcx+10h]
0x18000fa6b  cmp     rdi, [rcx+18h]
0x18000fa6f  jnb     short loc_18000FAA0
0x18000fa71  mov     rsi, [rdi]
0x18000fa74  test    rsi, rsi
0x18000fa77  jz      short loc_18000FA96
0x18000fa79  mov     rcx, [rsi+20h]
0x18000fa7d  test    rcx, rcx
0x18000fa80  jz      short loc_18000FA8E
0x18000fa82  mov     rax, [rcx]
0x18000fa85  mov     rax, [rax+10h]
0x18000fa89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa8e  mov     qword ptr [rsi+20h], 0
0x18000fa96  add     rdi, 8
0x18000fa9a  cmp     rdi, [rbx+18h]
0x18000fa9e  jb      short loc_18000FA71
0x18000faa0  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000faa4  call    cs:__imp_DeleteCriticalSection
0x18000faaa  mov     dword ptr [rbx], 0
0x18000fab0  mov     rbx, [rsp+28h+arg_0]
0x18000fab5  mov     rsi, [rsp+28h+arg_8]
0x18000faba  add     rsp, 20h
0x18000fabe  pop     rdi
0x18000fabf  retn
```
