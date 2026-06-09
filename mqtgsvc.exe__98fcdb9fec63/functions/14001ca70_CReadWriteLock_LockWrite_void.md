# CReadWriteLock::LockWrite(void)

- ea: `0x14001ca70`
- end: `0x14001cb27`
- name: `?LockWrite@CReadWriteLock@@QEAAXXZ`
- size: `183`
- prototype: `void __fastcall(CReadWriteLock *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003c5c`
- `0x140003f54`
- `0x14000456c`
- `0x1400060f4`
- `0x1400073d0`
- `0x14000a48c`
- `0x14000c720`

## callees

- `0x14000a5bc`
- `0x14001c8dc`
- `0x14001ca70`

## import_xrefs

- `KERNEL32!Sleep` at `0x14001cadf`
- `KERNEL32!Sleep` at `0x14001cadf`
- `KERNEL32!WaitForSingleObject` at `0x14001cb11`
- `KERNEL32!WaitForSingleObject` at `0x14001cb11`

## pseudocode

```c
void __fastcall CReadWriteLock::LockWrite(CReadWriteLock *this)
{
  unsigned int v2; // esi
  signed __int32 v3; // edi
  unsigned int v4; // eax
  void *v5; // r8

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids, this);
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
0x14001ca70  mov     [rsp+arg_0], rbx
0x14001ca75  mov     [rsp+arg_8], rsi
0x14001ca7a  push    rdi
0x14001ca7b  sub     rsp, 20h
0x14001ca7f  mov     rbx, rcx
0x14001ca82  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ca89  lea     rax, WPP_GLOBAL_Control
0x14001ca90  cmp     rcx, rax
0x14001ca93  jz      short loc_14001CAB3
0x14001ca95  test    byte ptr [rcx+1Ch], 4
0x14001ca99  jz      short loc_14001CAB3
0x14001ca9b  mov     rcx, [rcx+10h]
0x14001ca9f  lea     r8, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids
0x14001caa6  mov     edx, 0Bh
0x14001caab  mov     r9, rbx
0x14001caae  call    WPP_SF_q
0x14001cab3  xor     esi, esi
0x14001cab5  mov     edi, [rbx+4]
0x14001cab8  test    edi, edi
0x14001caba  jnz     short loc_14001CACC
0x14001cabc  mov     ecx, 400h
0x14001cac1  xor     eax, eax
0x14001cac3  lock cmpxchg [rbx+4], ecx
0x14001cac8  jnz     short loc_14001CAB5
0x14001caca  jmp     short loc_14001CB17
0x14001cacc  mov     eax, edi
0x14001cace  and     eax, 0FFC00000h
0x14001cad3  cmp     eax, 0FFC00000h
0x14001cad8  jnz     short loc_14001CAE7
0x14001cada  mov     ecx, 3E8h; dwMilliseconds
0x14001cadf  call    cs:__imp_Sleep
0x14001cae5  jmp     short loc_14001CAB5
0x14001cae7  mov     eax, esi
0x14001cae9  inc     esi
0x14001caeb  cmp     eax, [rbx]
0x14001caed  jb      short loc_14001CAB5
0x14001caef  mov     rcx, rbx; this
0x14001caf2  call    ?GetWriteWaiterEvent@CReadWriteLock@@AEAAPEAXXZ; CReadWriteLock::GetWriteWaiterEvent(void)
0x14001caf7  mov     r8, rax
0x14001cafa  lea     ecx, [rdi+400000h]
0x14001cb00  mov     eax, edi
0x14001cb02  lock cmpxchg [rbx+4], ecx
0x14001cb07  cmp     edi, eax
0x14001cb09  jnz     short loc_14001CAB5
0x14001cb0b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14001cb0e  mov     rcx, r8; hHandle
0x14001cb11  call    cs:__imp_WaitForSingleObject
0x14001cb17  mov     rbx, [rsp+28h+arg_0]
0x14001cb1c  mov     rsi, [rsp+28h+arg_8]
0x14001cb21  add     rsp, 20h
0x14001cb25  pop     rdi
0x14001cb26  retn
```
