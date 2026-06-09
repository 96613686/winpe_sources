# CASFReader::GetPlayMode(WMT_PLAY_MODE *)

- ea: `0x18000a300`
- end: `0x18000a321`
- name: `?GetPlayMode@CASFReader@@EEAAJPEAW4WMT_PLAY_MODE@@@Z`
- size: `33`
- prototype: `__int64 __fastcall(CASFReader *__hidden this, enum WMT_PLAY_MODE *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a300`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::GetPlayMode(CASFReader *this, enum WMT_PLAY_MODE *a2)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 27);
  if ( v2 )
    return (*(__int64 (__fastcall **)(__int64, enum WMT_PLAY_MODE *))(*(_QWORD *)v2 + 192LL))(v2, a2);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18000a300  mov     rcx, [rcx+0D8h]
0x18000a307  test    rcx, rcx
0x18000a30a  jnz     short loc_18000A312
0x18000a30c  mov     eax, 80004005h
0x18000a311  retn
0x18000a312  mov     rax, [rcx]
0x18000a315  mov     rax, [rax+0C0h]
0x18000a31c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
