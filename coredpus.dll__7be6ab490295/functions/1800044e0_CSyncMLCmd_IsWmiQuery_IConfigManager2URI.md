# CSyncMLCmd::IsWmiQuery(IConfigManager2URI *)

- ea: `0x1800044e0`
- end: `0x180004576`
- name: `?IsWmiQuery@CSyncMLCmd@@KAHPEAUIConfigManager2URI@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(struct IConfigManager2URI *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bf60`
- `0x18000cfb0`
- `0x180011a68`

## callees

- `0x1800044e0`
- `0x180030010`

## import_xrefs

- `DMCmnUtils!InvStrCmpIW` at `0x18000454c`
- `DMCmnUtils!InvStrCmpIW` at `0x18000454c`

## pseudocode

```c
_BOOL8 __fastcall CSyncMLCmd::IsWmiQuery(struct IConfigManager2URI *a1)
{
  __int64 v1; // rax
  bool v3; // sf
  _BOOL8 result; // rax
  unsigned int v5; // [rsp+30h] [rbp+8h] BYREF
  const unsigned __int16 *v6; // [rsp+38h] [rbp+10h] BYREF

  v1 = *(_QWORD *)a1;
  v5 = 0;
  v6 = 0;
  v3 = (*(int (__fastcall **)(struct IConfigManager2URI *, unsigned int *))(v1 + 136))(a1, &v5) < 0;
  result = 0;
  if ( !v3 && v5 >= 2 )
    return (*(int (__fastcall **)(struct IConfigManager2URI *, __int64, const unsigned __int16 **))(*(_QWORD *)a1 + 88LL))(
             a1,
             1,
             &v6) >= 0
        && (!v6 || !InvStrCmpIW(v6, L"cimv2"));
  return result;
}

```

## disassembly

```asm
0x1800044e0  mov     [rsp+arg_10], rbx
0x1800044e5  mov     [rsp+arg_18], rsi
0x1800044ea  push    rdi
0x1800044eb  sub     rsp, 20h
0x1800044ef  mov     rax, [rcx]
0x1800044f2  lea     rdx, [rsp+28h+arg_0]
0x1800044f7  xor     esi, esi
0x1800044f9  mov     rdi, rcx
0x1800044fc  mov     [rsp+28h+arg_0], esi
0x180004500  mov     [rsp+28h+arg_8], rsi
0x180004505  mov     rax, [rax+88h]
0x18000450c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004511  test    eax, eax
0x180004513  mov     eax, esi
0x180004515  js      short loc_180004565
0x180004517  cmp     [rsp+28h+arg_0], 2
0x18000451c  jb      short loc_180004565
0x18000451e  mov     rax, [rdi]
0x180004521  lea     r8, [rsp+28h+arg_8]
0x180004526  mov     edx, 1
0x18000452b  mov     rcx, rdi
0x18000452e  mov     rax, [rax+58h]
0x180004532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004537  test    eax, eax
0x180004539  js      short loc_180004563
0x18000453b  mov     rcx, [rsp+28h+arg_8]
0x180004540  test    rcx, rcx
0x180004543  jz      short loc_18000455C
0x180004545  lea     rdx, aCimv2; "cimv2"
0x18000454c  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x180004553  nop     dword ptr [rax+rax+00h]
0x180004558  test    eax, eax
0x18000455a  jnz     short loc_180004563
0x18000455c  mov     eax, 1
0x180004561  jmp     short loc_180004565
0x180004563  mov     eax, esi
0x180004565  mov     rbx, [rsp+28h+arg_10]
0x18000456a  mov     rsi, [rsp+28h+arg_18]
0x18000456f  add     rsp, 20h
0x180004573  pop     rdi
0x180004574  retn
```
