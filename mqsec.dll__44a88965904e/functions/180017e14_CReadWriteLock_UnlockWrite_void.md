# CReadWriteLock::UnlockWrite(void)

- ea: `0x180017e14`
- end: `0x180017ede`
- name: `?UnlockWrite@CReadWriteLock@@QEAAXXZ`
- size: `202`
- prototype: `void __fastcall(CReadWriteLock *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ce4c`

## callees

- `0x18000c3c4`
- `0x180017a60`
- `0x180017b24`
- `0x180017e14`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x180017ea9`
- `KERNEL32!ReleaseSemaphore` at `0x180017ea9`
- `KERNEL32!SetEvent` at `0x180017ecd`
- `KERNEL32!SetEvent` at `0x180017ecd`

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
0x180017e14  mov     [rsp+arg_0], rbx
0x180017e19  push    rdi
0x180017e1a  sub     rsp, 20h
0x180017e1e  mov     rbx, rcx
0x180017e21  mov     rcx, cs:WPP_GLOBAL_Control
0x180017e28  lea     rax, WPP_GLOBAL_Control
0x180017e2f  cmp     rcx, rax
0x180017e32  jz      short loc_180017E52
0x180017e34  test    byte ptr [rcx+1Ch], 4
0x180017e38  jz      short loc_180017E52
0x180017e3a  mov     rcx, [rcx+10h]
0x180017e3e  lea     r8, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids
0x180017e45  mov     edx, 0Dh
0x180017e4a  mov     r9, rbx
0x180017e4d  call    WPP_SF_q
0x180017e52  mov     r8d, 400h
0x180017e58  mov     edx, [rbx+4]
0x180017e5b  cmp     edx, r8d
0x180017e5e  jnz     short loc_180017E6E
0x180017e60  xor     ecx, ecx
0x180017e62  mov     eax, r8d
0x180017e65  lock cmpxchg [rbx+4], ecx
0x180017e6a  jnz     short loc_180017E58
0x180017e6c  jmp     short loc_180017ED3
0x180017e6e  test    edx, 3FF000h
0x180017e74  jz      short loc_180017EB1
0x180017e76  mov     edi, edx
0x180017e78  mov     ecx, edx
0x180017e7a  shr     edi, 0Ch
0x180017e7d  and     edi, 3FFh
0x180017e83  imul    eax, edi, 0FFFh
0x180017e89  sub     ecx, eax
0x180017e8b  mov     eax, edx
0x180017e8d  sub     ecx, r8d
0x180017e90  lock cmpxchg [rbx+4], ecx
0x180017e95  cmp     edx, eax
0x180017e97  jnz     short loc_180017E58
0x180017e99  mov     rcx, rbx; this
0x180017e9c  call    ?GetReadWaiterSemaphore@CReadWriteLock@@AEAAPEAXXZ; CReadWriteLock::GetReadWaiterSemaphore(void)
0x180017ea1  mov     rcx, rax; hSemaphore
0x180017ea4  xor     r8d, r8d; lpPreviousCount
0x180017ea7  mov     edx, edi; lReleaseCount
0x180017ea9  call    cs:__imp_ReleaseSemaphore
0x180017eaf  jmp     short loc_180017ED3
0x180017eb1  lea     ecx, [rdx-400000h]
0x180017eb7  mov     eax, edx
0x180017eb9  lock cmpxchg [rbx+4], ecx
0x180017ebe  cmp     edx, eax
0x180017ec0  jnz     short loc_180017E58
0x180017ec2  mov     rcx, rbx; this
0x180017ec5  call    ?GetWriteWaiterEvent@CReadWriteLock@@AEAAPEAXXZ; CReadWriteLock::GetWriteWaiterEvent(void)
0x180017eca  mov     rcx, rax; hEvent
0x180017ecd  call    cs:__imp_SetEvent
0x180017ed3  mov     rbx, [rsp+28h+arg_0]
0x180017ed8  add     rsp, 20h
0x180017edc  pop     rdi
0x180017edd  retn
```
