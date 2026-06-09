# ATL::CAtlComModule::~CAtlComModule(void)

- ea: `0x180026890`
- end: `0x180026900`
- name: `??1CAtlComModule@ATL@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180033770`

## callees

- `0x180026890`
- `0x180034010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800268e4`
- `KERNEL32!DeleteCriticalSection` at `0x1800268e4`

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
0x180026890  mov     [rsp+arg_0], rbx
0x180026895  mov     [rsp+arg_8], rsi
0x18002689a  push    rdi
0x18002689b  sub     rsp, 20h
0x18002689f  cmp     dword ptr [rcx], 0
0x1800268a2  mov     rbx, rcx
0x1800268a5  jz      short loc_1800268F0
0x1800268a7  mov     rdi, [rcx+10h]
0x1800268ab  cmp     rdi, [rcx+18h]
0x1800268af  jnb     short loc_1800268E0
0x1800268b1  mov     rsi, [rdi]
0x1800268b4  test    rsi, rsi
0x1800268b7  jz      short loc_1800268D6
0x1800268b9  mov     rcx, [rsi+20h]
0x1800268bd  test    rcx, rcx
0x1800268c0  jz      short loc_1800268CE
0x1800268c2  mov     rax, [rcx]
0x1800268c5  mov     rax, [rax+10h]
0x1800268c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268ce  mov     qword ptr [rsi+20h], 0
0x1800268d6  add     rdi, 8
0x1800268da  cmp     rdi, [rbx+18h]
0x1800268de  jb      short loc_1800268B1
0x1800268e0  lea     rcx, [rbx+20h]; lpCriticalSection
0x1800268e4  call    cs:__imp_DeleteCriticalSection
0x1800268ea  mov     dword ptr [rbx], 0
0x1800268f0  mov     rbx, [rsp+28h+arg_0]
0x1800268f5  mov     rsi, [rsp+28h+arg_8]
0x1800268fa  add     rsp, 20h
0x1800268fe  pop     rdi
0x1800268ff  retn
```
