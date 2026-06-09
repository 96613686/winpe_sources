# CASFReader::GetDownloadProgress(ulong *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180009a50`
- end: `0x180009a7b`
- name: `?GetDownloadProgress@CASFReader@@EEAAJPEAKPEA_K1@Z`
- size: `43`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, unsigned int *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009a50`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::GetDownloadProgress(
        CASFReader *this,
        unsigned int *a2,
        unsigned __int64 *a3,
        unsigned __int64 *a4)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 27);
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64, unsigned int *, unsigned __int64 *, unsigned __int64 *))(*(_QWORD *)v4 + 208LL))(
             v4,
             a2,
             a3,
             a4);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180009a50  sub     rsp, 38h
0x180009a54  mov     rcx, [rcx+0D8h]
0x180009a5b  test    rcx, rcx
0x180009a5e  jnz     short loc_180009A67
0x180009a60  mov     eax, 80004005h
0x180009a65  jmp     short loc_180009A76
0x180009a67  mov     rax, [rcx]
0x180009a6a  mov     rax, [rax+0D0h]
0x180009a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a76  add     rsp, 38h
0x180009a7a  retn
```
