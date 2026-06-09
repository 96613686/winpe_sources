# ATL::CAtlComModule::Term(void)

- ea: `0x1400076e0`
- end: `0x140007750`
- name: `?Term@CAtlComModule@ATL@@QEAAXXZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400044e4`
- `0x140062eb0`

## callees

- `0x1400076e0`
- `0x140063010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140007734`
- `KERNEL32!DeleteCriticalSection` at `0x140007734`

## pseudocode

```c
void __fastcall ATL::CAtlComModule::Term(ATL::CAtlComModule *this)
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
0x1400076e0  mov     [rsp+arg_0], rbx
0x1400076e5  mov     [rsp+arg_8], rsi
0x1400076ea  push    rdi
0x1400076eb  sub     rsp, 20h
0x1400076ef  cmp     dword ptr [rcx], 0
0x1400076f2  mov     rbx, rcx
0x1400076f5  jz      short loc_140007740
0x1400076f7  mov     rdi, [rcx+10h]
0x1400076fb  cmp     rdi, [rcx+18h]
0x1400076ff  jnb     short loc_140007730
0x140007701  mov     rsi, [rdi]
0x140007704  test    rsi, rsi
0x140007707  jz      short loc_140007726
0x140007709  mov     rcx, [rsi+20h]
0x14000770d  test    rcx, rcx
0x140007710  jz      short loc_14000771E
0x140007712  mov     rax, [rcx]
0x140007715  mov     rax, [rax+10h]
0x140007719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000771e  mov     qword ptr [rsi+20h], 0
0x140007726  add     rdi, 8
0x14000772a  cmp     rdi, [rbx+18h]
0x14000772e  jb      short loc_140007701
0x140007730  lea     rcx, [rbx+20h]; lpCriticalSection
0x140007734  call    cs:__imp_DeleteCriticalSection
0x14000773a  mov     dword ptr [rbx], 0
0x140007740  mov     rbx, [rsp+28h+arg_0]
0x140007745  mov     rsi, [rsp+28h+arg_8]
0x14000774a  add     rsp, 20h
0x14000774e  pop     rdi
0x14000774f  retn
```
