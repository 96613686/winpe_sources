# CReadWriteLock::LockRead(void)

- ea: `0x14001c9a0`
- end: `0x14001ca67`
- name: `?LockRead@CReadWriteLock@@QEAAXXZ`
- size: `199`
- prototype: `void __fastcall(CReadWriteLock *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140004324`
- `0x1400043c0`
- `0x140004488`
- `0x140005f98`
- `0x1400060b0`
- `0x140006624`
- `0x140009550`

## callees

- `0x14000a5bc`
- `0x14001c818`
- `0x14001c9a0`

## import_xrefs

- `KERNEL32!Sleep` at `0x14001ca11`
- `KERNEL32!Sleep` at `0x14001ca11`
- `KERNEL32!WaitForSingleObject` at `0x14001ca51`
- `KERNEL32!WaitForSingleObject` at `0x14001ca51`

## pseudocode

```c
void __fastcall CReadWriteLock::LockRead(CReadWriteLock *this)
{
  unsigned int v2; // esi
  unsigned __int32 v3; // ebx
  unsigned int v4; // eax
  void *WaiterSemaphore; // r8

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids, this);
  v2 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v3 = *((_DWORD *)this + 1);
        if ( v3 >= 0x3FF )
          break;
        if ( v3 == _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v3 + 1, v3) )
          return;
      }
      if ( (*((_DWORD *)this + 1) & 0x3FF) != 0x3FF && (v3 & 0x3FF000) != 0x3FF000 )
        break;
      Sleep(0x3E8u);
    }
    v4 = v2++;
    if ( v4 >= *(_DWORD *)this )
    {
      WaiterSemaphore = CReadWriteLock::GetReadWaiterSemaphore(this);
      if ( v3 == _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v3 + 4096, v3) )
        break;
    }
  }
  WaitForSingleObject(WaiterSemaphore, 0xFFFFFFFF);
}

```

## disassembly

```asm
0x14001c9a0  mov     [rsp+arg_0], rbx
0x14001c9a5  mov     [rsp+arg_8], rsi
0x14001c9aa  push    rdi
0x14001c9ab  sub     rsp, 20h
0x14001c9af  mov     rdi, rcx
0x14001c9b2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c9b9  lea     rax, WPP_GLOBAL_Control
0x14001c9c0  cmp     rcx, rax
0x14001c9c3  jz      short loc_14001C9E3
0x14001c9c5  test    byte ptr [rcx+1Ch], 4
0x14001c9c9  jz      short loc_14001C9E3
0x14001c9cb  mov     rcx, [rcx+10h]
0x14001c9cf  lea     r8, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids
0x14001c9d6  mov     edx, 0Ah
0x14001c9db  mov     r9, rdi
0x14001c9de  call    WPP_SF_q
0x14001c9e3  xor     esi, esi
0x14001c9e5  mov     ebx, [rdi+4]
0x14001c9e8  mov     eax, ebx
0x14001c9ea  cmp     ebx, 3FFh
0x14001c9f0  jnb     short loc_14001CA00
0x14001c9f2  lea     ecx, [rbx+1]
0x14001c9f5  lock cmpxchg [rdi+4], ecx
0x14001c9fa  cmp     ebx, eax
0x14001c9fc  jnz     short loc_14001C9E5
0x14001c9fe  jmp     short loc_14001CA57
0x14001ca00  and     eax, 3FFh
0x14001ca05  cmp     eax, 3FFh
0x14001ca0a  jnz     short loc_14001CA19
0x14001ca0c  mov     ecx, 3E8h; dwMilliseconds
0x14001ca11  call    cs:__imp_Sleep
0x14001ca17  jmp     short loc_14001C9E5
0x14001ca19  mov     eax, ebx
0x14001ca1b  and     eax, 3FF000h
0x14001ca20  cmp     eax, 3FF000h
0x14001ca25  jz      short loc_14001CA0C
0x14001ca27  mov     eax, esi
0x14001ca29  inc     esi
0x14001ca2b  cmp     eax, [rdi]
0x14001ca2d  jb      short loc_14001C9E5
0x14001ca2f  mov     rcx, rdi; this
0x14001ca32  call    ?GetReadWaiterSemaphore@CReadWriteLock@@AEAAPEAXXZ; CReadWriteLock::GetReadWaiterSemaphore(void)
0x14001ca37  mov     r8, rax
0x14001ca3a  lea     ecx, [rbx+1000h]
0x14001ca40  mov     eax, ebx
0x14001ca42  lock cmpxchg [rdi+4], ecx
0x14001ca47  cmp     ebx, eax
0x14001ca49  jnz     short loc_14001C9E5
0x14001ca4b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14001ca4e  mov     rcx, r8; hHandle
0x14001ca51  call    cs:__imp_WaitForSingleObject
0x14001ca57  mov     rbx, [rsp+28h+arg_0]
0x14001ca5c  mov     rsi, [rsp+28h+arg_8]
0x14001ca61  add     rsp, 20h
0x14001ca65  pop     rdi
0x14001ca66  retn
```
