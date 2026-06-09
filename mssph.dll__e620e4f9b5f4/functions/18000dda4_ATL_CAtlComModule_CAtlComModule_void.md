# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18000dda4`
- end: `0x18000de14`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180026ea0`

## callees

- `0x18000dda4`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ddf8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ddf8`

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
0x18000dda4  mov     [rsp+arg_0], rbx
0x18000dda9  mov     [rsp+arg_8], rsi
0x18000ddae  push    rdi
0x18000ddaf  sub     rsp, 20h
0x18000ddb3  cmp     dword ptr [rcx], 0
0x18000ddb6  mov     rbx, rcx
0x18000ddb9  jz      short loc_18000DE04
0x18000ddbb  mov     rdi, [rcx+10h]
0x18000ddbf  cmp     rdi, [rcx+18h]
0x18000ddc3  jnb     short loc_18000DDF4
0x18000ddc5  mov     rsi, [rdi]
0x18000ddc8  test    rsi, rsi
0x18000ddcb  jz      short loc_18000DDEA
0x18000ddcd  mov     rcx, [rsi+20h]
0x18000ddd1  test    rcx, rcx
0x18000ddd4  jz      short loc_18000DDE2
0x18000ddd6  mov     rax, [rcx]
0x18000ddd9  mov     rax, [rax+10h]
0x18000dddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dde2  mov     qword ptr [rsi+20h], 0
0x18000ddea  add     rdi, 8
0x18000ddee  cmp     rdi, [rbx+18h]
0x18000ddf2  jb      short loc_18000DDC5
0x18000ddf4  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000ddf8  call    cs:__imp_DeleteCriticalSection
0x18000ddfe  mov     dword ptr [rbx], 0
0x18000de04  mov     rbx, [rsp+28h+arg_0]
0x18000de09  mov     rsi, [rsp+28h+arg_8]
0x18000de0e  add     rsp, 20h
0x18000de12  pop     rdi
0x18000de13  retn
```
