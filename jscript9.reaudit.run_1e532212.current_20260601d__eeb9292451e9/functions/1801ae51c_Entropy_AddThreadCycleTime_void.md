# Entropy::AddThreadCycleTime(void)

- ea: `0x1801ae51c`
- end: `0x1801ae582`
- name: `?AddThreadCycleTime@Entropy@@QEAAXXZ`
- size: `102`
- prototype: `void __fastcall(Entropy *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180164df0`
- `0x180180094`
- `0x180193314`

## callees

- `0x1801aa33c`
- `0x1801ae51c`

## import_xrefs

- `KERNEL32!QueryThreadCycleTime` at `0x1801ae53c`
- `KERNEL32!QueryThreadCycleTime` at `0x1801ae53c`
- `KERNEL32!GetCurrentThread` at `0x1801ae52e`
- `KERNEL32!GetCurrentThread` at `0x1801ae52e`

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
0x1801ae51c  mov     [rsp+arg_0], rcx
0x1801ae521  sub     rsp, 38h
0x1801ae525  mov     [rsp+38h+CycleTime], 0
0x1801ae52e  call    cs:__imp_GetCurrentThread
0x1801ae534  mov     rcx, rax; ThreadHandle
0x1801ae537  lea     rdx, [rsp+38h+CycleTime]; CycleTime
0x1801ae53c  call    cs:__imp_QueryThreadCycleTime
0x1801ae542  mov     rcx, [rsp+38h+arg_0]; this
0x1801ae547  xor     edx, edx
0x1801ae549  mov     eax, [rcx+4]
0x1801ae54c  mov     [rcx], eax
0x1801ae54e  mov     r8b, byte ptr [rsp+rdx+38h+CycleTime]
0x1801ae553  test    r8b, r8b
0x1801ae556  jz      short loc_1801AE56F
0x1801ae558  mov     rax, [rcx+8]
0x1801ae55c  xor     [rax+rcx+4], r8b
0x1801ae561  mov     rax, [rcx+8]
0x1801ae565  inc     rax
0x1801ae568  and     eax, 3
0x1801ae56b  mov     [rcx+8], rax
0x1801ae56f  inc     rdx
0x1801ae572  cmp     rdx, 4
0x1801ae576  jb      short loc_1801AE54E
0x1801ae578  call    ?AddCurrentTime@Entropy@@AEAAXXZ; Entropy::AddCurrentTime(void)
0x1801ae57d  add     rsp, 38h
0x1801ae581  retn
```
