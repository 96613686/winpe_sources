# sqlite3ErrStr

- ea: `0x140056018`
- end: `0x14005606c`
- name: `sqlite3ErrStr`
- size: `84`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140060050`
- `0x140066370`
- `0x14006c1ac`
- `0x140074448`
- `0x14007b618`
- `0x14008a290`
- `0x14008a340`
- `0x14008a480`
- `0x14008c390`
- `0x14009c15c`

## callees

- `0x140056018`

## string_xrefs

- `0x14005604f`: `abort due to ROLLBACK`

## pseudocode

```c
const char *__fastcall sqlite3ErrStr(int a1)
{
  const char *v1; // rdx

  switch ( a1 )
  {
    case 100:
      return "another row available";
    case 101:
      return "no more rows available";
    case 516:
      return "abort due to ROLLBACK";
  }
  v1 = "unknown error";
  if ( (unsigned __int8)a1 < 0x1Du && off_1400AA190[(unsigned __int8)a1] )
    return off_1400AA190[(unsigned __int8)a1];
  return v1;
}

```

## disassembly

```asm
0x140056018  mov     edx, ecx
0x14005601a  sub     edx, 64h ; 'd'
0x14005601d  jz      short loc_140056061
0x14005601f  sub     edx, 1
0x140056022  jz      short loc_140056058
0x140056024  cmp     edx, 19Fh
0x14005602a  jz      short loc_14005604F
0x14005602c  movzx   eax, cl
0x14005602f  lea     rdx, aUnknownError; "unknown error"
0x140056036  cmp     eax, 1Dh
0x140056039  jnb     short loc_140056068
0x14005603b  lea     rcx, off_1400AA190; "not an error"
0x140056042  cmp     qword ptr [rcx+rax*8], 0
0x140056047  jz      short loc_140056068
0x140056049  mov     rdx, [rcx+rax*8]
0x14005604d  jmp     short loc_140056068
0x14005604f  lea     rdx, aAbortDueToRoll; "abort due to ROLLBACK"
0x140056056  jmp     short loc_140056068
0x140056058  lea     rdx, aNoMoreRowsAvai; "no more rows available"
0x14005605f  jmp     short loc_140056068
0x140056061  lea     rdx, aAnotherRowAvai; "another row available"
0x140056068  mov     rax, rdx
0x14005606b  retn
```
