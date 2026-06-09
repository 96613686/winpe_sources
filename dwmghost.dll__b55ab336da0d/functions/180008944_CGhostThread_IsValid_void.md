# CGhostThread::IsValid(void)

- ea: `0x180008944`
- end: `0x18000896a`
- name: `?IsValid@CGhostThread@@QEAAHXZ`
- size: `38`
- prototype: `__int64 __fastcall(CGhostThread *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007d0c`

## callees

- `0x1800087f0`
- `0x180008944`

## pseudocode

```c
__int64 __fastcall CGhostThread::IsValid(CGhostThread *this)
{
  unsigned int v1; // ebx
  int State; // eax

  v1 = 0;
  State = CGhostThread::GetState((__int64)this);
  if ( State == 1 || State == 2 )
    return 1;
  return v1;
}

```

## disassembly

```asm
0x180008944  push    rbx
0x180008946  sub     rsp, 20h
0x18000894a  xor     ebx, ebx
0x18000894c  call    ?GetState@CGhostThread@@AEAA?AW4tagGHOSTTHREADSTATE@@XZ; CGhostThread::GetState(void)
0x180008951  mov     ecx, eax
0x180008953  sub     ecx, 1
0x180008956  jz      short loc_18000895D
0x180008958  cmp     ecx, 1
0x18000895b  jnz     short loc_180008962
0x18000895d  mov     ebx, 1
0x180008962  mov     eax, ebx
0x180008964  add     rsp, 20h
0x180008968  pop     rbx
0x180008969  retn
```
