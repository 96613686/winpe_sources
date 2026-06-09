# CCSCShellServiceObject::_NotifyShell(ushort const *,long,uint)

- ea: `0x1800220b4`
- end: `0x180022108`
- name: `?_NotifyShell@CCSCShellServiceObject@@AEAAXPEBGJI@Z`
- size: `84`
- prototype: `void(CCSCShellServiceObject *__hidden this, const unsigned __int16 *, int, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180021a50`
- `0x180022000`
- `0x180022110`

## callees

- `0x1800220b4`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x1800220e9`
- `SHELL32!SHChangeNotify` at `0x1800220e9`
- `SHELL32!__imp_ILFree` at `0x1800220f2`
- `SHELL32!__imp_ILFree` at `0x1800220f2`
- `SHELL32!__imp_SHSimpleIDListFromPath` at `0x1800220d1`
- `SHELL32!__imp_SHSimpleIDListFromPath` at `0x1800220d1`

## pseudocode

```c
void __fastcall CCSCShellServiceObject::_NotifyShell(
        CCSCShellServiceObject *this,
        const unsigned __int16 *a2,
        LONG a3,
        UINT a4)
{
  LPITEMIDLIST v6; // rax
  ITEMIDLIST *v7; // rbx

  if ( a2 )
  {
    v6 = SHSimpleIDListFromPath(a2);
    v7 = v6;
    if ( v6 )
    {
      SHChangeNotify(a3, a4, v6, 0);
      ILFree(v7);
    }
  }
}

```

## disassembly

```asm
0x1800220b4  test    rdx, rdx
0x1800220b7  jz      short locret_180022107
0x1800220b9  mov     [rsp+arg_0], rbx
0x1800220be  mov     [rsp+arg_8], rsi
0x1800220c3  push    rdi
0x1800220c4  sub     rsp, 20h
0x1800220c8  mov     rcx, rdx; pszPath
0x1800220cb  mov     edi, r9d
0x1800220ce  mov     esi, r8d
0x1800220d1  call    cs:__imp_SHSimpleIDListFromPath
0x1800220d7  mov     rbx, rax
0x1800220da  test    rax, rax
0x1800220dd  jz      short loc_1800220F8
0x1800220df  xor     r9d, r9d; dwItem2
0x1800220e2  mov     r8, rax; dwItem1
0x1800220e5  mov     edx, edi; uFlags
0x1800220e7  mov     ecx, esi; wEventId
0x1800220e9  call    cs:__imp_SHChangeNotify
0x1800220ef  mov     rcx, rbx; pidl
0x1800220f2  call    cs:__imp_ILFree
0x1800220f8  mov     rbx, [rsp+28h+arg_0]
0x1800220fd  mov     rsi, [rsp+28h+arg_8]
0x180022102  add     rsp, 20h
0x180022106  pop     rdi
0x180022107  retn
```
