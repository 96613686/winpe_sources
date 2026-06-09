# NptrigCreateTrigger

- ea: `0x14000a4d0`
- end: `0x14000a5ca`
- name: `NptrigCreateTrigger`
- size: `250`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140009f50`

## callees

- `0x140001c40`
- `0x14000a4d0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a537`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a537`
- `ntoskrnl!ExAllocatePool2` at `0x14000a508`
- `ntoskrnl!ExAllocatePool2` at `0x14000a508`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14000a573`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14000a573`
- `FLTMGR!FltReleasePushLockEx` at `0x14000a5b0`
- `FLTMGR!FltReleasePushLockEx` at `0x14000a5b0`

## pseudocode

```c
__int64 __fastcall NptrigCreateTrigger(_WORD *Src)
{
  __int64 v2; // rbx
  __int64 Pool2; // rax
  __int64 v4; // rsi
  unsigned int v5; // ebx
  PVOID DeviceExtension; // rcx
  PVOID v7; // r8
  __int64 v8; // rcx
  __int64 *v9; // rax

  v2 = -1;
  do
    ++v2;
  while ( Src[v2] );
  Pool2 = ExAllocatePool2(64, (unsigned int)(2 * v2 + 2) + 40LL, 1735684174);
  v4 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 24) = Pool2 + 40;
    memmove((void *)(Pool2 + 40), Src, (unsigned int)(2 * v2 + 2));
    DeviceExtension = WPP_MAIN_CB.DeviceExtension;
    *(_WORD *)(v4 + 16) = 2 * v2;
    *(_WORD *)(v4 + 18) = 2 * v2 + 2;
    *(_DWORD *)(v4 + 32) = 1;
    FltAcquirePushLockExclusiveEx(DeviceExtension, 0);
    v7 = WPP_MAIN_CB.DeviceExtension;
    v8 = *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 1);
    v9 = (__int64 *)((char *)WPP_MAIN_CB.DeviceExtension + 8);
    if ( *(PVOID *)(v8 + 8) != (char *)WPP_MAIN_CB.DeviceExtension + 8 )
      __fastfail(3u);
    *(_QWORD *)v4 = v8;
    v5 = 0;
    *(_QWORD *)(v4 + 8) = v9;
    *(_QWORD *)(v8 + 8) = v4;
    *v9 = v4;
    FltReleasePushLockEx(v7, 0);
  }
  else
  {
    v5 = -1073741670;
    if ( MEMORY[0x18] )
      ExFreePoolWithTag(MEMORY[0x18], 0x6774704Eu);
  }
  return v5;
}

```

## disassembly

```asm
0x14000a4d0  push    rbx
0x14000a4d2  push    rbp
0x14000a4d3  push    rsi
0x14000a4d4  push    rdi
0x14000a4d5  push    r14
0x14000a4d7  sub     rsp, 20h
0x14000a4db  mov     rdi, rcx
0x14000a4de  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x14000a4e5  inc     rbx
0x14000a4e8  cmp     word ptr [rcx+rbx*2], 0
0x14000a4ed  jnz     short loc_14000A4E5
0x14000a4ef  lea     ebp, ds:2[rbx*2]
0x14000a4f6  mov     ecx, 40h ; '@'
0x14000a4fb  lea     rdx, [rbp+28h]
0x14000a4ff  mov     r14d, ebp
0x14000a502  mov     r8d, 6774704Eh
0x14000a508  call    cs:__imp_ExAllocatePool2
0x14000a50f  nop     dword ptr [rax+rax+00h]
0x14000a514  mov     rsi, rax
0x14000a517  test    rax, rax
0x14000a51a  jnz     short loc_14000A545
0x14000a51c  mov     rcx, ds:18h; P
0x14000a524  mov     ebx, 0C000009Ah
0x14000a529  test    rcx, rcx
0x14000a52c  jz      loc_14000A5BC
0x14000a532  mov     edx, 6774704Eh; Tag
0x14000a537  call    cs:__imp_ExFreePoolWithTag
0x14000a53e  nop     dword ptr [rax+rax+00h]
0x14000a543  jmp     short loc_14000A5BC
0x14000a545  lea     rcx, [rax+28h]; void *
0x14000a549  mov     r8, r14; Size
0x14000a54c  mov     rdx, rdi; Src
0x14000a54f  mov     [rax+18h], rcx
0x14000a553  call    memmove
0x14000a558  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14000a55f  add     bx, bx
0x14000a562  xor     edx, edx
0x14000a564  mov     [rsi+10h], bx
0x14000a568  mov     [rsi+12h], bp
0x14000a56c  mov     dword ptr [rsi+20h], 1
0x14000a573  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14000a57a  nop     dword ptr [rax+rax+00h]
0x14000a57f  mov     r8, cs:WPP_MAIN_CB.DeviceExtension
0x14000a586  mov     rcx, [r8+8]
0x14000a58a  lea     rax, [r8+8]
0x14000a58e  cmp     [rcx+8], rax
0x14000a592  jz      short loc_14000A59B
0x14000a594  mov     ecx, 3
0x14000a599  int     29h; Win8: RtlFailFast(ecx)
0x14000a59b  mov     [rsi], rcx
0x14000a59e  xor     ebx, ebx
0x14000a5a0  mov     [rsi+8], rax
0x14000a5a4  xor     edx, edx
0x14000a5a6  mov     [rcx+8], rsi
0x14000a5aa  mov     rcx, r8
0x14000a5ad  mov     [rax], rsi
0x14000a5b0  call    cs:__imp_FltReleasePushLockEx
0x14000a5b7  nop     dword ptr [rax+rax+00h]
0x14000a5bc  mov     eax, ebx
0x14000a5be  add     rsp, 20h
0x14000a5c2  pop     r14
0x14000a5c4  pop     rdi
0x14000a5c5  pop     rsi
0x14000a5c6  pop     rbp
0x14000a5c7  pop     rbx
0x14000a5c8  retn
```
