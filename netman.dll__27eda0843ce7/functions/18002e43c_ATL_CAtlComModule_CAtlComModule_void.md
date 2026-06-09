# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x18002e43c`
- end: `0x18002e4ac`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800359e0`

## callees

- `0x18002e43c`
- `0x180036010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002e490`
- `KERNEL32!DeleteCriticalSection` at `0x18002e490`

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
0x18002e43c  mov     [rsp+arg_0], rbx
0x18002e441  mov     [rsp+arg_8], rsi
0x18002e446  push    rdi
0x18002e447  sub     rsp, 20h
0x18002e44b  cmp     dword ptr [rcx], 0
0x18002e44e  mov     rbx, rcx
0x18002e451  jz      short loc_18002E49C
0x18002e453  mov     rdi, [rcx+10h]
0x18002e457  cmp     rdi, [rcx+18h]
0x18002e45b  jnb     short loc_18002E48C
0x18002e45d  mov     rsi, [rdi]
0x18002e460  test    rsi, rsi
0x18002e463  jz      short loc_18002E482
0x18002e465  mov     rcx, [rsi+20h]
0x18002e469  test    rcx, rcx
0x18002e46c  jz      short loc_18002E47A
0x18002e46e  mov     rax, [rcx]
0x18002e471  mov     rax, [rax+10h]
0x18002e475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e47a  mov     qword ptr [rsi+20h], 0
0x18002e482  add     rdi, 8
0x18002e486  cmp     rdi, [rbx+18h]
0x18002e48a  jb      short loc_18002E45D
0x18002e48c  lea     rcx, [rbx+20h]; lpCriticalSection
0x18002e490  call    cs:__imp_DeleteCriticalSection
0x18002e496  mov     dword ptr [rbx], 0
0x18002e49c  mov     rbx, [rsp+28h+arg_0]
0x18002e4a1  mov     rsi, [rsp+28h+arg_8]
0x18002e4a6  add     rsp, 20h
0x18002e4aa  pop     rdi
0x18002e4ab  retn
```
