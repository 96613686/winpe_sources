# CReadWriteLock::LockRead(void)

- ea: `0x180017be8`
- end: `0x180017caf`
- name: `?LockRead@CReadWriteLock@@QEAAXXZ`
- size: `199`
- prototype: `void __fastcall(CReadWriteLock *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d890`
- `0x18000d940`

## callees

- `0x18000c3c4`
- `0x180017a60`
- `0x180017be8`

## import_xrefs

- `KERNEL32!Sleep` at `0x180017c59`
- `KERNEL32!Sleep` at `0x180017c59`
- `KERNEL32!WaitForSingleObject` at `0x180017c99`
- `KERNEL32!WaitForSingleObject` at `0x180017c99`

## pseudocode

```c
void __fastcall CReadWriteLock::LockRead(CReadWriteLock *this)
{
  unsigned int v2; // esi
  unsigned __int32 v3; // ebx
  unsigned int v4; // eax
  void *WaiterSemaphore; // r8

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids, this);
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
0x180017be8  mov     [rsp+arg_0], rbx
0x180017bed  mov     [rsp+arg_8], rsi
0x180017bf2  push    rdi
0x180017bf3  sub     rsp, 20h
0x180017bf7  mov     rdi, rcx
0x180017bfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c01  lea     rax, WPP_GLOBAL_Control
0x180017c08  cmp     rcx, rax
0x180017c0b  jz      short loc_180017C2B
0x180017c0d  test    byte ptr [rcx+1Ch], 4
0x180017c11  jz      short loc_180017C2B
0x180017c13  mov     rcx, [rcx+10h]
0x180017c17  lea     r8, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids
0x180017c1e  mov     edx, 0Ah
0x180017c23  mov     r9, rdi
0x180017c26  call    WPP_SF_q
0x180017c2b  xor     esi, esi
0x180017c2d  mov     ebx, [rdi+4]
0x180017c30  mov     eax, ebx
0x180017c32  cmp     ebx, 3FFh
0x180017c38  jnb     short loc_180017C48
0x180017c3a  lea     ecx, [rbx+1]
0x180017c3d  lock cmpxchg [rdi+4], ecx
0x180017c42  cmp     ebx, eax
0x180017c44  jnz     short loc_180017C2D
0x180017c46  jmp     short loc_180017C9F
0x180017c48  and     eax, 3FFh
0x180017c4d  cmp     eax, 3FFh
0x180017c52  jnz     short loc_180017C61
0x180017c54  mov     ecx, 3E8h; dwMilliseconds
0x180017c59  call    cs:__imp_Sleep
0x180017c5f  jmp     short loc_180017C2D
0x180017c61  mov     eax, ebx
0x180017c63  and     eax, 3FF000h
0x180017c68  cmp     eax, 3FF000h
0x180017c6d  jz      short loc_180017C54
0x180017c6f  mov     eax, esi
0x180017c71  inc     esi
0x180017c73  cmp     eax, [rdi]
0x180017c75  jb      short loc_180017C2D
0x180017c77  mov     rcx, rdi; this
0x180017c7a  call    ?GetReadWaiterSemaphore@CReadWriteLock@@AEAAPEAXXZ; CReadWriteLock::GetReadWaiterSemaphore(void)
0x180017c7f  mov     r8, rax
0x180017c82  lea     ecx, [rbx+1000h]
0x180017c88  mov     eax, ebx
0x180017c8a  lock cmpxchg [rdi+4], ecx
0x180017c8f  cmp     ebx, eax
0x180017c91  jnz     short loc_180017C2D
0x180017c93  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180017c96  mov     rcx, r8; hHandle
0x180017c99  call    cs:__imp_WaitForSingleObject
0x180017c9f  mov     rbx, [rsp+28h+arg_0]
0x180017ca4  mov     rsi, [rsp+28h+arg_8]
0x180017ca9  add     rsp, 20h
0x180017cad  pop     rdi
0x180017cae  retn
```
