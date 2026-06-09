# NOTIFICATION_MAP_PATH::SetPhysicalPath(ushort const *,ulong)

- ea: `0x180024420`
- end: `0x18002446f`
- name: `?SetPhysicalPath@NOTIFICATION_MAP_PATH@@UEAAJPEBGK@Z`
- size: `79`
- prototype: `__int64 __fastcall(NOTIFICATION_MAP_PATH *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180024420`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180024451`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180024451`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002443d`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002443d`

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
0x180024420  mov     [rsp+arg_0], rbx
0x180024425  push    rdi
0x180024426  sub     rsp, 20h
0x18002442a  mov     rbx, rcx
0x18002442d  test    rdx, rdx
0x180024430  jnz     short loc_180024439
0x180024432  mov     eax, 80070057h
0x180024437  jmp     short loc_180024463
0x180024439  add     rcx, 20h ; ' '
0x18002443d  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180024444  nop     dword ptr [rax+rax+00h]
0x180024449  test    eax, eax
0x18002444b  js      short loc_180024463
0x18002444d  lea     rcx, [rbx+20h]
0x180024451  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180024458  nop     dword ptr [rax+rax+00h]
0x18002445d  mov     [rbx+18h], rax
0x180024461  xor     eax, eax
0x180024463  mov     rbx, [rsp+28h+arg_0]
0x180024468  add     rsp, 20h
0x18002446c  pop     rdi
0x18002446d  retn
```
