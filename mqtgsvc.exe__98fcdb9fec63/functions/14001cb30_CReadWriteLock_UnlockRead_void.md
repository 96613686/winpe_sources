# CReadWriteLock::UnlockRead(void)

- ea: `0x14001cb30`
- end: `0x14001cbc3`
- name: `?UnlockRead@CReadWriteLock@@QEAAXXZ`
- size: `147`
- prototype: `void __fastcall(CReadWriteLock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003d08`

## callees

- `0x14000a5bc`
- `0x14001c8dc`
- `0x14001cb30`

## import_xrefs

- `KERNEL32!SetEvent` at `0x14001cbbc`

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
0x14001cb30  push    rbx
0x14001cb32  sub     rsp, 20h
0x14001cb36  mov     rbx, rcx
0x14001cb39  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cb40  lea     rax, WPP_GLOBAL_Control
0x14001cb47  cmp     rcx, rax
0x14001cb4a  jz      short loc_14001CB6A
0x14001cb4c  test    byte ptr [rcx+1Ch], 4
0x14001cb50  jz      short loc_14001CB6A
0x14001cb52  mov     rcx, [rcx+10h]
0x14001cb56  lea     r8, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids
0x14001cb5d  mov     edx, 0Ch
0x14001cb62  mov     r9, rbx
0x14001cb65  call    WPP_SF_q
0x14001cb6a  mov     edx, [rbx+4]
0x14001cb6d  cmp     edx, 1
0x14001cb70  jnz     short loc_14001CB83
0x14001cb72  xor     ecx, ecx
0x14001cb74  mov     eax, edx
0x14001cb76  lock cmpxchg [rbx+4], ecx
0x14001cb7b  jnz     short loc_14001CB6A
0x14001cb7d  add     rsp, 20h
0x14001cb81  pop     rbx
0x14001cb82  retn
0x14001cb83  mov     eax, edx
0x14001cb85  and     eax, 3FFh
0x14001cb8a  cmp     eax, 1
0x14001cb8d  mov     eax, edx
0x14001cb8f  jbe     short loc_14001CB9D
0x14001cb91  lea     ecx, [rdx-1]
0x14001cb94  lock cmpxchg [rbx+4], ecx
0x14001cb99  cmp     edx, eax
0x14001cb9b  jmp     short loc_14001CB7B
0x14001cb9d  lea     ecx, [rdx-3FFC01h]
0x14001cba3  lock cmpxchg [rbx+4], ecx
0x14001cba8  cmp     edx, eax
0x14001cbaa  jnz     short loc_14001CB6A
0x14001cbac  mov     rcx, rbx; this
0x14001cbaf  call    ?GetWriteWaiterEvent@CReadWriteLock@@AEAAPEAXXZ; CReadWriteLock::GetWriteWaiterEvent(void)
0x14001cbb4  mov     rcx, rax
0x14001cbb7  add     rsp, 20h
0x14001cbbb  pop     rbx
0x14001cbbc  jmp     cs:__imp_SetEvent
```
