# CReadWriteLock::UnlockWrite(void)

- ea: `0x14001cbcc`
- end: `0x14001cc96`
- name: `?UnlockWrite@CReadWriteLock@@QEAAXXZ`
- size: `202`
- prototype: `void __fastcall(CReadWriteLock *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140003d28`

## callees

- `0x14000a5bc`
- `0x14001c818`
- `0x14001c8dc`
- `0x14001cbcc`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x14001cc61`
- `KERNEL32!ReleaseSemaphore` at `0x14001cc61`
- `KERNEL32!SetEvent` at `0x14001cc85`
- `KERNEL32!SetEvent` at `0x14001cc85`

## pseudocode

```c
void __fastcall CReadWriteLock::UnlockWrite(CReadWriteLock *this)
{
  unsigned __int32 v2; // edx
  LONG v3; // edi
  void *WaiterSemaphore; // rax
  void *v5; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids, this);
  do
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v2 = *((_DWORD *)this + 1);
        if ( v2 != 1024 )
          break;
        if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 1, 0, 1024) == 1024 )
          return;
      }
      if ( (v2 & 0x3FF000) == 0 )
        break;
      v3 = (v2 >> 12) & 0x3FF;
      if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v2 - 4095 * v3 - 1024, v2) )
      {
        WaiterSemaphore = CReadWriteLock::GetReadWaiterSemaphore(this);
        ReleaseSemaphore(WaiterSemaphore, v3, 0);
        return;
      }
    }
  }
  while ( v2 != _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v2 - 0x400000, v2) );
  v5 = CReadWriteLock::GetWriteWaiterEvent(this);
  SetEvent(v5);
}

```

## disassembly

```asm
0x14001cbcc  mov     [rsp+arg_0], rbx
0x14001cbd1  push    rdi
0x14001cbd2  sub     rsp, 20h
0x14001cbd6  mov     rbx, rcx
0x14001cbd9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cbe0  lea     rax, WPP_GLOBAL_Control
0x14001cbe7  cmp     rcx, rax
0x14001cbea  jz      short loc_14001CC0A
0x14001cbec  test    byte ptr [rcx+1Ch], 4
0x14001cbf0  jz      short loc_14001CC0A
0x14001cbf2  mov     rcx, [rcx+10h]
0x14001cbf6  lea     r8, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids
0x14001cbfd  mov     edx, 0Dh
0x14001cc02  mov     r9, rbx
0x14001cc05  call    WPP_SF_q
0x14001cc0a  mov     r8d, 400h
0x14001cc10  mov     edx, [rbx+4]
0x14001cc13  cmp     edx, r8d
0x14001cc16  jnz     short loc_14001CC26
0x14001cc18  xor     ecx, ecx
0x14001cc1a  mov     eax, r8d
0x14001cc1d  lock cmpxchg [rbx+4], ecx
0x14001cc22  jnz     short loc_14001CC10
0x14001cc24  jmp     short loc_14001CC8B
0x14001cc26  test    edx, 3FF000h
0x14001cc2c  jz      short loc_14001CC69
0x14001cc2e  mov     edi, edx
0x14001cc30  mov     ecx, edx
0x14001cc32  shr     edi, 0Ch
0x14001cc35  and     edi, 3FFh
0x14001cc3b  imul    eax, edi, 0FFFh
0x14001cc41  sub     ecx, eax
0x14001cc43  mov     eax, edx
0x14001cc45  sub     ecx, r8d
0x14001cc48  lock cmpxchg [rbx+4], ecx
0x14001cc4d  cmp     edx, eax
0x14001cc4f  jnz     short loc_14001CC10
0x14001cc51  mov     rcx, rbx; this
0x14001cc54  call    ?GetReadWaiterSemaphore@CReadWriteLock@@AEAAPEAXXZ; CReadWriteLock::GetReadWaiterSemaphore(void)
0x14001cc59  mov     rcx, rax; hSemaphore
0x14001cc5c  xor     r8d, r8d; lpPreviousCount
0x14001cc5f  mov     edx, edi; lReleaseCount
0x14001cc61  call    cs:__imp_ReleaseSemaphore
0x14001cc67  jmp     short loc_14001CC8B
0x14001cc69  lea     ecx, [rdx-400000h]
0x14001cc6f  mov     eax, edx
0x14001cc71  lock cmpxchg [rbx+4], ecx
0x14001cc76  cmp     edx, eax
0x14001cc78  jnz     short loc_14001CC10
0x14001cc7a  mov     rcx, rbx; this
0x14001cc7d  call    ?GetWriteWaiterEvent@CReadWriteLock@@AEAAPEAXXZ; CReadWriteLock::GetWriteWaiterEvent(void)
0x14001cc82  mov     rcx, rax; hEvent
0x14001cc85  call    cs:__imp_SetEvent
0x14001cc8b  mov     rbx, [rsp+28h+arg_0]
0x14001cc90  add     rsp, 20h
0x14001cc94  pop     rdi
0x14001cc95  retn
```
