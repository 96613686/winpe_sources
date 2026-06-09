# CReadWriteLock::UnlockRead(void)

- ea: `0x180017d78`
- end: `0x180017e0b`
- name: `?UnlockRead@CReadWriteLock@@QEAAXXZ`
- size: `147`
- prototype: `void __fastcall(CReadWriteLock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ce2c`

## callees

- `0x18000c3c4`
- `0x180017b24`
- `0x180017d78`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180017e04`

## pseudocode

```c
void __fastcall CReadWriteLock::UnlockRead(CReadWriteLock *this)
{
  signed __int32 v2; // edx
  bool v3; // zf
  void *v4; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids, this);
  do
  {
    while ( 1 )
    {
      v2 = *((_DWORD *)this + 1);
      if ( v2 != 1 )
        break;
      v3 = _InterlockedCompareExchange((volatile signed __int32 *)this + 1, 0, 1) == 1;
LABEL_6:
      if ( v3 )
        return;
    }
    if ( (*((_DWORD *)this + 1) & 0x3FFu) > 1 )
    {
      v3 = v2 == _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v2 - 1, v2);
      goto LABEL_6;
    }
  }
  while ( v2 != _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v2 - 4193281, v2) );
  v4 = CReadWriteLock::GetWriteWaiterEvent(this);
  SetEvent(v4);
}

```

## disassembly

```asm
0x180017d78  push    rbx
0x180017d7a  sub     rsp, 20h
0x180017d7e  mov     rbx, rcx
0x180017d81  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d88  lea     rax, WPP_GLOBAL_Control
0x180017d8f  cmp     rcx, rax
0x180017d92  jz      short loc_180017DB2
0x180017d94  test    byte ptr [rcx+1Ch], 4
0x180017d98  jz      short loc_180017DB2
0x180017d9a  mov     rcx, [rcx+10h]
0x180017d9e  lea     r8, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids
0x180017da5  mov     edx, 0Ch
0x180017daa  mov     r9, rbx
0x180017dad  call    WPP_SF_q
0x180017db2  mov     edx, [rbx+4]
0x180017db5  cmp     edx, 1
0x180017db8  jnz     short loc_180017DCB
0x180017dba  xor     ecx, ecx
0x180017dbc  mov     eax, edx
0x180017dbe  lock cmpxchg [rbx+4], ecx
0x180017dc3  jnz     short loc_180017DB2
0x180017dc5  add     rsp, 20h
0x180017dc9  pop     rbx
0x180017dca  retn
0x180017dcb  mov     eax, edx
0x180017dcd  and     eax, 3FFh
0x180017dd2  cmp     eax, 1
0x180017dd5  mov     eax, edx
0x180017dd7  jbe     short loc_180017DE5
0x180017dd9  lea     ecx, [rdx-1]
0x180017ddc  lock cmpxchg [rbx+4], ecx
0x180017de1  cmp     edx, eax
0x180017de3  jmp     short loc_180017DC3
0x180017de5  lea     ecx, [rdx-3FFC01h]
0x180017deb  lock cmpxchg [rbx+4], ecx
0x180017df0  cmp     edx, eax
0x180017df2  jnz     short loc_180017DB2
0x180017df4  mov     rcx, rbx; this
0x180017df7  call    ?GetWriteWaiterEvent@CReadWriteLock@@AEAAPEAXXZ; CReadWriteLock::GetWriteWaiterEvent(void)
0x180017dfc  mov     rcx, rax
0x180017dff  add     rsp, 20h
0x180017e03  pop     rbx
0x180017e04  jmp     cs:__imp_SetEvent
```
