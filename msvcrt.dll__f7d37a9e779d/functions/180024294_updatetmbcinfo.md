# __updatetmbcinfo

- ea: `0x180024294`
- end: `0x180024348`
- name: `__updatetmbcinfo`
- size: `180`
- prototype: `pthreadmbcinfo __cdecl()`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180001038`
- `0x180024390`
- `0x18002c760`

## callees

- `0x18001d300`
- `0x180024294`
- `0x18003d7e0`
- `0x18003e048`
- `0x18003e6c0`
- `0x18003e8e0`

## pseudocode

```c
pthreadmbcinfo __cdecl _updatetmbcinfo()
{
  __int64 v0; // rax
  __int64 v1; // rdi
  pthreadmbcinfo v2; // rbx

  v0 = getptd();
  v1 = v0;
  if ( ((*(_BYTE *)(v0 + 200) & 2) != 0 || (_globallocalestatus & 1) == 0) && *(_QWORD *)(v0 + 192) )
  {
    v2 = *(pthreadmbcinfo *)(v0 + 184);
  }
  else
  {
    lock(13);
    v2 = *(pthreadmbcinfo *)(v1 + 184);
    if ( v2 != _ptmbcinfo )
    {
      if ( v2
        && _InterlockedExchangeAdd((volatile signed __int32 *)v2, 0xFFFFFFFF) == 1
        && v2 != (pthreadmbcinfo)_initialmbcinfo )
      {
        free(v2);
      }
      *(_QWORD *)(v1 + 184) = _ptmbcinfo;
      v2 = _ptmbcinfo;
      _InterlockedIncrement((volatile signed __int32 *)_ptmbcinfo);
    }
    unlock(13);
  }
  if ( !v2 )
    amsg_exit(32);
  return v2;
}

```

## disassembly

```asm
0x180024294  mov     [rsp+arg_0], rbx
0x180024299  push    rdi
0x18002429a  sub     rsp, 20h
0x18002429e  call    _getptd
0x1800242a3  mov     rdi, rax
0x1800242a6  test    byte ptr [rax+0C8h], 2
0x1800242ad  jnz     short loc_1800242B8
0x1800242af  test    byte ptr cs:__globallocalestatus, 1
0x1800242b6  jnz     short loc_1800242C2
0x1800242b8  cmp     qword ptr [rax+0C0h], 0
0x1800242c0  jnz     short loc_180024326
0x1800242c2  mov     ecx, 0Dh
0x1800242c7  call    _lock
0x1800242cc  nop
0x1800242cd  mov     rbx, [rdi+0B8h]
0x1800242d4  cmp     rbx, cs:__ptmbcinfo
0x1800242db  jz      short loc_18002431A
0x1800242dd  test    rbx, rbx
0x1800242e0  jz      short loc_180024302
0x1800242e2  or      eax, 0FFFFFFFFh
0x1800242e5  lock xadd [rbx], eax
0x1800242e9  cmp     eax, 1
0x1800242ec  jnz     short loc_180024302
0x1800242ee  lea     rax, __initialmbcinfo
0x1800242f5  cmp     rbx, rax
0x1800242f8  jz      short loc_180024302
0x1800242fa  mov     rcx, rbx; Block
0x1800242fd  call    free
0x180024302  mov     rax, cs:__ptmbcinfo
0x180024309  mov     [rdi+0B8h], rax
0x180024310  mov     rbx, cs:__ptmbcinfo
0x180024317  lock inc dword ptr [rbx]
0x18002431a  mov     ecx, 0Dh
0x18002431f  call    _unlock
0x180024324  jmp     short loc_18002432D
0x180024326  mov     rbx, [rax+0B8h]
0x18002432d  test    rbx, rbx
0x180024330  jnz     short loc_18002433A
0x180024332  lea     ecx, [rbx+20h]
0x180024335  call    _amsg_exit
0x18002433a  mov     rax, rbx
0x18002433d  mov     rbx, [rsp+28h+arg_0]
0x180024342  add     rsp, 20h
0x180024346  pop     rdi
0x180024347  retn
0x18007bbc9  push    rbp
0x18007bbcb  sub     rsp, 20h
0x18007bbcf  mov     rbp, rdx
0x18007bbd2  mov     ecx, 0Dh
0x18007bbd7  add     rsp, 20h
0x18007bbdb  pop     rbp
0x18007bbdc  jmp     _unlock
```
