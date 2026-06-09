# Entropy::AddThreadCycleTime(void)

- ea: `0x1801b0aec`
- end: `0x1801b0b5f`
- name: `?AddThreadCycleTime@Entropy@@QEAAXXZ`
- size: `115`
- prototype: `void __fastcall(Entropy *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180165c20`
- `0x180180948`
- `0x1801951e8`

## callees

- `0x1801ac8e0`
- `0x1801b0aec`

## import_xrefs

- `KERNEL32!QueryThreadCycleTime` at `0x1801b0b12`
- `KERNEL32!QueryThreadCycleTime` at `0x1801b0b12`
- `KERNEL32!GetCurrentThread` at `0x1801b0afe`
- `KERNEL32!GetCurrentThread` at `0x1801b0afe`

## pseudocode

```c
void __fastcall Entropy::AddThreadCycleTime(Entropy *this)
{
  HANDLE CurrentThread; // rax
  unsigned __int64 v2; // rdx
  char v3; // r8
  unsigned __int64 CycleTime[3]; // [rsp+20h] [rbp-18h] BYREF

  CycleTime[0] = 0;
  CurrentThread = GetCurrentThread();
  QueryThreadCycleTime(CurrentThread, CycleTime);
  v2 = 0;
  *(_DWORD *)this = *((_DWORD *)this + 1);
  do
  {
    v3 = *((_BYTE *)CycleTime + v2);
    if ( v3 )
    {
      *((_BYTE *)this + *((_QWORD *)this + 1) + 4) ^= v3;
      *((_QWORD *)this + 1) = ((unsigned __int8)*((_QWORD *)this + 1) + 1) & 3;
    }
    ++v2;
  }
  while ( v2 < 4 );
  Entropy::AddCurrentTime(this);
}

```

## disassembly

```asm
0x1801b0aec  mov     [rsp+arg_0], rcx
0x1801b0af1  sub     rsp, 38h
0x1801b0af5  mov     [rsp+38h+CycleTime], 0
0x1801b0afe  call    cs:__imp_GetCurrentThread
0x1801b0b05  nop     dword ptr [rax+rax+00h]
0x1801b0b0a  mov     rcx, rax; ThreadHandle
0x1801b0b0d  lea     rdx, [rsp+38h+CycleTime]; CycleTime
0x1801b0b12  call    cs:__imp_QueryThreadCycleTime
0x1801b0b19  nop     dword ptr [rax+rax+00h]
0x1801b0b1e  mov     rcx, [rsp+38h+arg_0]; this
0x1801b0b23  xor     edx, edx
0x1801b0b25  mov     eax, [rcx+4]
0x1801b0b28  mov     [rcx], eax
0x1801b0b2a  mov     r8b, byte ptr [rsp+rdx+38h+CycleTime]
0x1801b0b2f  test    r8b, r8b
0x1801b0b32  jz      short loc_1801B0B4B
0x1801b0b34  mov     rax, [rcx+8]
0x1801b0b38  xor     [rax+rcx+4], r8b
0x1801b0b3d  mov     rax, [rcx+8]
0x1801b0b41  inc     rax
0x1801b0b44  and     eax, 3
0x1801b0b47  mov     [rcx+8], rax
0x1801b0b4b  inc     rdx
0x1801b0b4e  cmp     rdx, 4
0x1801b0b52  jb      short loc_1801B0B2A
0x1801b0b54  call    ?AddCurrentTime@Entropy@@AEAAXXZ; Entropy::AddCurrentTime(void)
0x1801b0b59  add     rsp, 38h
0x1801b0b5d  retn
```
