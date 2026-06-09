# ATL::CAtlComModule::Term(void)

- ea: `0x18000ca00`
- end: `0x18000ca70`
- name: `?Term@CAtlComModule@ATL@@QEAAXXZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlComModule *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180049e50`

## callees

- `0x18000ca00`
- `0x18004a010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000ca54`
- `KERNEL32!DeleteCriticalSection` at `0x18000ca54`

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
0x18000ca00  mov     [rsp+arg_0], rbx
0x18000ca05  mov     [rsp+arg_8], rsi
0x18000ca0a  push    rdi
0x18000ca0b  sub     rsp, 20h
0x18000ca0f  cmp     dword ptr [rcx], 0
0x18000ca12  mov     rbx, rcx
0x18000ca15  jz      short loc_18000CA60
0x18000ca17  mov     rdi, [rcx+10h]
0x18000ca1b  cmp     rdi, [rcx+18h]
0x18000ca1f  jnb     short loc_18000CA50
0x18000ca21  mov     rsi, [rdi]
0x18000ca24  test    rsi, rsi
0x18000ca27  jz      short loc_18000CA46
0x18000ca29  mov     rcx, [rsi+20h]
0x18000ca2d  test    rcx, rcx
0x18000ca30  jz      short loc_18000CA3E
0x18000ca32  mov     rax, [rcx]
0x18000ca35  mov     rax, [rax+10h]
0x18000ca39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca3e  mov     qword ptr [rsi+20h], 0
0x18000ca46  add     rdi, 8
0x18000ca4a  cmp     rdi, [rbx+18h]
0x18000ca4e  jb      short loc_18000CA21
0x18000ca50  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000ca54  call    cs:__imp_DeleteCriticalSection
0x18000ca5a  mov     dword ptr [rbx], 0
0x18000ca60  mov     rbx, [rsp+28h+arg_0]
0x18000ca65  mov     rsi, [rsp+28h+arg_8]
0x18000ca6a  add     rsp, 20h
0x18000ca6e  pop     rdi
0x18000ca6f  retn
```
