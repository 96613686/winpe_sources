# NOTIFICATION_MAP_PATH::SetPhysicalPath(ushort const *,ulong)

- ea: `0x180022790`
- end: `0x1800227d2`
- name: `?SetPhysicalPath@NOTIFICATION_MAP_PATH@@UEAAJPEBGK@Z`
- size: `66`
- prototype: `__int64 __fastcall(NOTIFICATION_MAP_PATH *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180022790`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800227bb`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800227bb`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800227ad`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800227ad`

## pseudocode

```c
int __fastcall NOTIFICATION_MAP_PATH::SetPhysicalPath(
        NOTIFICATION_MAP_PATH *this,
        const unsigned __int16 *a2,
        unsigned int a3)
{
  int result; // eax

  if ( !a2 )
    return -2147024809;
  result = STRU::Copy((NOTIFICATION_MAP_PATH *)((char *)this + 32), a2, a3);
  if ( result >= 0 )
  {
    *((_QWORD *)this + 3) = STRU::QueryStr((NOTIFICATION_MAP_PATH *)((char *)this + 32));
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180022790  mov     [rsp+arg_0], rbx
0x180022795  push    rdi
0x180022796  sub     rsp, 20h
0x18002279a  mov     rbx, rcx
0x18002279d  test    rdx, rdx
0x1800227a0  jnz     short loc_1800227A9
0x1800227a2  mov     eax, 80070057h
0x1800227a7  jmp     short loc_1800227C7
0x1800227a9  add     rcx, 20h ; ' '
0x1800227ad  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800227b3  test    eax, eax
0x1800227b5  js      short loc_1800227C7
0x1800227b7  lea     rcx, [rbx+20h]
0x1800227bb  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800227c1  mov     [rbx+18h], rax
0x1800227c5  xor     eax, eax
0x1800227c7  mov     rbx, [rsp+28h+arg_0]
0x1800227cc  add     rsp, 20h
0x1800227d0  pop     rdi
0x1800227d1  retn
```
