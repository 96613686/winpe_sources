# CASFReader::GetScript(ushort,ushort *,ushort *,ushort *,ushort *,unsigned __int64 *)

- ea: `0x18000a3d0`
- end: `0x18000a421`
- name: `?GetScript@CASFReader@@EEAAJGPEAG000PEA_K@Z`
- size: `81`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, unsigned __int16, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a3d0`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::GetScript(
        CASFReader *this,
        unsigned __int16 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        unsigned __int64 *a7)
{
  __int64 v7; // rcx

  v7 = *((_QWORD *)this + 29);
  if ( v7 )
    return (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int64 *))(*(_QWORD *)v7 + 96LL))(
             v7,
             a2,
             a3,
             a4,
             a5,
             a6,
             a7);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18000a3d0  sub     rsp, 48h
0x18000a3d4  mov     rcx, [rcx+0E8h]
0x18000a3db  movzx   r10d, dx
0x18000a3df  test    rcx, rcx
0x18000a3e2  jnz     short loc_18000A3EB
0x18000a3e4  mov     eax, 80004005h
0x18000a3e9  jmp     short loc_18000A41C
0x18000a3eb  mov     rdx, [rsp+48h+arg_30]
0x18000a3f3  mov     rax, [rcx]
0x18000a3f6  mov     [rsp+48h+var_18], rdx
0x18000a3fb  mov     rdx, [rsp+48h+arg_28]
0x18000a400  mov     [rsp+48h+var_20], rdx
0x18000a405  mov     rdx, [rsp+48h+arg_20]
0x18000a40a  mov     rax, [rax+60h]
0x18000a40e  mov     [rsp+48h+var_28], rdx
0x18000a413  movzx   edx, r10w
0x18000a417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a41c  add     rsp, 48h
0x18000a420  retn
```
