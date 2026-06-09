# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18002a2fc`
- end: `0x18002a36c`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180033cb0`

## callees

- `0x18002a2fc`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a350`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002a350`

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
0x18002a2fc  mov     [rsp+arg_0], rbx
0x18002a301  mov     [rsp+arg_8], rsi
0x18002a306  push    rdi
0x18002a307  sub     rsp, 20h
0x18002a30b  cmp     dword ptr [rcx], 0
0x18002a30e  mov     rbx, rcx
0x18002a311  jz      short loc_18002A35C
0x18002a313  mov     rdi, [rcx+10h]
0x18002a317  cmp     rdi, [rcx+18h]
0x18002a31b  jnb     short loc_18002A34C
0x18002a31d  mov     rsi, [rdi]
0x18002a320  test    rsi, rsi
0x18002a323  jz      short loc_18002A342
0x18002a325  mov     rcx, [rsi+20h]
0x18002a329  test    rcx, rcx
0x18002a32c  jz      short loc_18002A33A
0x18002a32e  mov     rax, [rcx]
0x18002a331  mov     rax, [rax+10h]
0x18002a335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a33a  mov     qword ptr [rsi+20h], 0
0x18002a342  add     rdi, 8
0x18002a346  cmp     rdi, [rbx+18h]
0x18002a34a  jb      short loc_18002A31D
0x18002a34c  lea     rcx, [rbx+20h]; lpCriticalSection
0x18002a350  call    cs:__imp_DeleteCriticalSection
0x18002a356  mov     dword ptr [rbx], 0
0x18002a35c  mov     rbx, [rsp+28h+arg_0]
0x18002a361  mov     rsi, [rsp+28h+arg_8]
0x18002a366  add     rsp, 20h
0x18002a36a  pop     rdi
0x18002a36b  retn
```
