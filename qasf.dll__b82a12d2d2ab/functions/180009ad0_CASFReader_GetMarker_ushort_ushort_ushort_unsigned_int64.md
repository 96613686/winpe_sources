# CASFReader::GetMarker(ushort,ushort *,ushort *,unsigned __int64 *)

- ea: `0x180009ad0`
- end: `0x180009b0a`
- name: `?GetMarker@CASFReader@@EEAAJGPEAG0PEA_K@Z`
- size: `58`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, unsigned __int16, unsigned __int16 *, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009ad0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::GetMarker(
        CASFReader *this,
        unsigned __int16 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int64 *a5)
{
  __int64 v5; // rcx

  v5 = *((_QWORD *)this + 29);
  if ( v5 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, unsigned __int16 *, unsigned __int64 *))(*(_QWORD *)v5 + 64LL))(
             v5,
             a2,
             a3,
             a4,
             a5);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180009ad0  sub     rsp, 38h
0x180009ad4  mov     rcx, [rcx+0E8h]
0x180009adb  movzx   r10d, dx
0x180009adf  test    rcx, rcx
0x180009ae2  jnz     short loc_180009AEB
0x180009ae4  mov     eax, 80004005h
0x180009ae9  jmp     short loc_180009B05
0x180009aeb  mov     rdx, [rsp+38h+arg_20]
0x180009af0  mov     rax, [rcx]
0x180009af3  mov     [rsp+38h+var_18], rdx
0x180009af8  movzx   edx, r10w
0x180009afc  mov     rax, [rax+40h]
0x180009b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b05  add     rsp, 38h
0x180009b09  retn
```
