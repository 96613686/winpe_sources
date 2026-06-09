# __updatetlocinfo

- ea: `0x18002c214`
- end: `0x18002c292`
- name: `__updatetlocinfo`
- size: `126`
- prototype: `pthreadlocinfo __cdecl()`
- caller_count: `9`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180001038`
- `0x18002b650`
- `0x18002b6a0`
- `0x18002b6f0`
- `0x18002b740`
- `0x18002c760`
- `0x18002d060`
- `0x18002e580`
- `0x180032bb0`

## callees

- `0x18002c214`
- `0x18002cfec`
- `0x18003d7e0`
- `0x18003e048`
- `0x18003e6c0`
- `0x18003e8e0`

## pseudocode

```c
pthreadlocinfo __cdecl _updatetlocinfo()
{
  __int64 v0; // rax
  __int64 v1; // rbx
  struct threadlocaleinfostruct *v2; // rbx

  v0 = getptd();
  if ( (*(_BYTE *)(v0 + 200) & 2) == 0 && (_globallocalestatus & 1) != 0 )
  {
    v1 = v0 + 192;
LABEL_5:
    lock(12);
    v2 = (struct threadlocaleinfostruct *)updatetlocinfoEx_nolock(v1, _ptlocinfo);
    unlock(12);
    goto LABEL_7;
  }
  v1 = v0 + 192;
  if ( !*(_QWORD *)(v0 + 192) )
    goto LABEL_5;
  v2 = *(struct threadlocaleinfostruct **)(getptd() + 192);
LABEL_7:
  if ( !v2 )
    amsg_exit(32);
  return v2;
}

```

## disassembly

```asm
0x18002c214  push    rbx
0x18002c216  sub     rsp, 20h
0x18002c21a  call    _getptd
0x18002c21f  test    byte ptr [rax+0C8h], 2
0x18002c226  jnz     short loc_18002C23A
0x18002c228  test    byte ptr cs:__globallocalestatus, 1
0x18002c22f  jz      short loc_18002C23A
0x18002c231  lea     rbx, [rax+0C0h]
0x18002c238  jmp     short loc_18002C247
0x18002c23a  lea     rbx, [rax+0C0h]
0x18002c241  cmp     qword ptr [rbx], 0
0x18002c245  jnz     short loc_18002C270
0x18002c247  mov     ecx, 0Ch
0x18002c24c  call    _lock
0x18002c251  nop
0x18002c252  mov     rdx, cs:__ptlocinfo
0x18002c259  mov     rcx, rbx
0x18002c25c  call    _updatetlocinfoEx_nolock
0x18002c261  mov     rbx, rax
0x18002c264  mov     ecx, 0Ch
0x18002c269  call    _unlock
0x18002c26e  jmp     short loc_18002C27C
0x18002c270  call    _getptd
0x18002c275  mov     rbx, [rax+0C0h]
0x18002c27c  test    rbx, rbx
0x18002c27f  jnz     short loc_18002C289
0x18002c281  lea     ecx, [rbx+20h]
0x18002c284  call    _amsg_exit
0x18002c289  mov     rax, rbx
0x18002c28c  add     rsp, 20h
0x18002c290  pop     rbx
0x18002c291  retn
0x18007bbe8  push    rbp
0x18007bbea  sub     rsp, 20h
0x18007bbee  mov     rbp, rdx
0x18007bbf1  mov     ecx, 0Ch
0x18007bbf6  add     rsp, 20h
0x18007bbfa  pop     rbp
0x18007bbfb  jmp     _unlock
```
