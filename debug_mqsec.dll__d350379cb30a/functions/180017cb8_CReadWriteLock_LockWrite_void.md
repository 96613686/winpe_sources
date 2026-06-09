# CReadWriteLock::LockWrite(void)

- ea: `0x180017cb8`
- end: `0x180017d6f`
- name: `?LockWrite@CReadWriteLock@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(CReadWriteLock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e1a0`

## callees

- `0x18000c3c4`
- `0x180017b24`
- `0x180017cb8`

## import_xrefs

- `KERNEL32!Sleep` at `0x180017d27`
- `KERNEL32!Sleep` at `0x180017d27`
- `KERNEL32!WaitForSingleObject` at `0x180017d59`
- `KERNEL32!WaitForSingleObject` at `0x180017d59`

## pseudocode

```c
void __fastcall CReadWriteLock::LockWrite(CReadWriteLock *this)
{
  unsigned int v2; // esi
  signed __int32 v3; // edi
  unsigned int v4; // eax
  void *v5; // r8

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids, this);
  v2 = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v3 = *((_DWORD *)this + 1);
        if ( v3 )
          break;
        if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 1, 1024, 0) )
          return;
      }
      if ( (v3 & 0xFFC00000) != 0xFFC00000 )
        break;
      Sleep(0x3E8u);
    }
    v4 = v2++;
    if ( v4 >= *(_DWORD *)this )
    {
      v5 = CReadWriteLock::GetWriteWaiterEvent(this);
      if ( v3 == _InterlockedCompareExchange((volatile signed __int32 *)this + 1, v3 + 0x400000, v3) )
        break;
    }
  }
  WaitForSingleObject(v5, 0xFFFFFFFF);
}

```

## disassembly

```asm
0x180017cb8  mov     [rsp+arg_0], rbx
0x180017cbd  mov     [rsp+arg_8], rsi
0x180017cc2  push    rdi
0x180017cc3  sub     rsp, 20h
0x180017cc7  mov     rbx, rcx
0x180017cca  mov     rcx, cs:WPP_GLOBAL_Control
0x180017cd1  lea     rax, WPP_GLOBAL_Control
0x180017cd8  cmp     rcx, rax
0x180017cdb  jz      short loc_180017CFB
0x180017cdd  test    byte ptr [rcx+1Ch], 4
0x180017ce1  jz      short loc_180017CFB
0x180017ce3  mov     rcx, [rcx+10h]
0x180017ce7  lea     r8, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids
0x180017cee  mov     edx, 0Bh
0x180017cf3  mov     r9, rbx
0x180017cf6  call    WPP_SF_q
0x180017cfb  xor     esi, esi
0x180017cfd  mov     edi, [rbx+4]
0x180017d00  test    edi, edi
0x180017d02  jnz     short loc_180017D14
0x180017d04  mov     ecx, 400h
0x180017d09  xor     eax, eax
0x180017d0b  lock cmpxchg [rbx+4], ecx
0x180017d10  jnz     short loc_180017CFD
0x180017d12  jmp     short loc_180017D5F
0x180017d14  mov     eax, edi
0x180017d16  and     eax, 0FFC00000h
0x180017d1b  cmp     eax, 0FFC00000h
0x180017d20  jnz     short loc_180017D2F
0x180017d22  mov     ecx, 3E8h; dwMilliseconds
0x180017d27  call    cs:__imp_Sleep
0x180017d2d  jmp     short loc_180017CFD
0x180017d2f  mov     eax, esi
0x180017d31  inc     esi
0x180017d33  cmp     eax, [rbx]
0x180017d35  jb      short loc_180017CFD
0x180017d37  mov     rcx, rbx; this
0x180017d3a  call    ?GetWriteWaiterEvent@CReadWriteLock@@AEAAPEAXXZ; CReadWriteLock::GetWriteWaiterEvent(void)
0x180017d3f  mov     r8, rax
0x180017d42  lea     ecx, [rdi+400000h]
0x180017d48  mov     eax, edi
0x180017d4a  lock cmpxchg [rbx+4], ecx
0x180017d4f  cmp     edi, eax
0x180017d51  jnz     short loc_180017CFD
0x180017d53  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180017d56  mov     rcx, r8; hHandle
0x180017d59  call    cs:__imp_WaitForSingleObject
0x180017d5f  mov     rbx, [rsp+28h+arg_0]
0x180017d64  mov     rsi, [rsp+28h+arg_8]
0x180017d69  add     rsp, 20h
0x180017d6d  pop     rdi
0x180017d6e  retn
```
