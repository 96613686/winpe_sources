# Recycler::FinalizeConcurrent(void)

- ea: `0x180258a90`
- end: `0x180258b90`
- name: `?FinalizeConcurrent@Recycler@@AEAAXXZ`
- size: `256`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1802592c4`

## callees

- `0x180258618`
- `0x180258a90`

## import_xrefs

- `KERNEL32!SetThreadPriority` at `0x180258aea`
- `KERNEL32!SetThreadPriority` at `0x180258aea`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180258b0e`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x180258b0e`
- `KERNEL32!SetEvent` at `0x180258ad5`
- `KERNEL32!SetEvent` at `0x180258ad5`
- `KERNEL32!CloseHandle` at `0x180258b26`
- `KERNEL32!CloseHandle` at `0x180258b44`
- `KERNEL32!CloseHandle` at `0x180258b67`
- `KERNEL32!CloseHandle` at `0x180258b26`
- `KERNEL32!CloseHandle` at `0x180258b44`
- `KERNEL32!CloseHandle` at `0x180258b67`

## pseudocode

```c
void __fastcall Recycler::FinalizeConcurrent(HANDLE *this)
{
  bool v2; // al
  HANDLE v3; // rax
  HANDLE v4; // rcx
  HANDLE v5; // rcx
  HANDLE v6; // rcx
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  v2 = Recycler::AbortConcurrent((Recycler *)this);
  *(_DWORD *)this = 4;
  if ( v2 && this[1619] )
  {
    v3 = this[1618];
    Handles[1] = this[1619];
    v4 = this[1617];
    Handles[0] = v3;
    SetEvent(v4);
    SetThreadPriority(this[1619], 0);
    WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
  }
  v5 = this[2018];
  if ( v5 )
  {
    CloseHandle(v5);
    this[2018] = 0;
  }
  CloseHandle(this[1618]);
  v6 = this[1617];
  this[1618] = 0;
  if ( v6 )
  {
    CloseHandle(v6);
    this[1617] = 0;
  }
  this[1619] = 0;
}

```

## disassembly

```asm
0x180258a90  mov     [rsp+arg_0], rcx
0x180258a95  push    rbx
0x180258a96  sub     rsp, 40h
0x180258a9a  mov     rbx, [rsp+48h+arg_0]
0x180258a9f  mov     rcx, rbx; this
0x180258aa2  call    ?AbortConcurrent@Recycler@@AEAA_N_N@Z; Recycler::AbortConcurrent(bool)
0x180258aa7  mov     dword ptr [rbx], 4
0x180258aad  test    al, al
0x180258aaf  jz      short loc_180258B1A
0x180258ab1  mov     rcx, [rbx+3298h]
0x180258ab8  test    rcx, rcx
0x180258abb  jz      short loc_180258B1A
0x180258abd  mov     rax, [rbx+3290h]
0x180258ac4  mov     [rsp+48h+var_10], rcx
0x180258ac9  mov     rcx, [rbx+3288h]; hEvent
0x180258ad0  mov     [rsp+48h+Handles], rax
0x180258ad5  call    cs:__imp_SetEvent
0x180258adc  nop     dword ptr [rax+rax+00h]
0x180258ae1  mov     rcx, [rbx+3298h]; hThread
0x180258ae8  xor     edx, edx; nPriority
0x180258aea  call    cs:__imp_SetThreadPriority
0x180258af1  nop     dword ptr [rax+rax+00h]
0x180258af6  xor     r8d, r8d; bWaitAll
0x180258af9  mov     [rsp+48h+bAlertable], 0; bAlertable
0x180258b01  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180258b05  lea     rdx, [rsp+48h+Handles]; lpHandles
0x180258b0a  lea     ecx, [r8+2]; nCount
0x180258b0e  call    cs:__imp_WaitForMultipleObjectsEx
0x180258b15  nop     dword ptr [rax+rax+00h]
0x180258b1a  mov     rcx, [rbx+3F10h]; hObject
0x180258b21  test    rcx, rcx
0x180258b24  jz      short loc_180258B3D
0x180258b26  call    cs:__imp_CloseHandle
0x180258b2d  nop     dword ptr [rax+rax+00h]
0x180258b32  mov     qword ptr [rbx+3F10h], 0
0x180258b3d  mov     rcx, [rbx+3290h]; hObject
0x180258b44  call    cs:__imp_CloseHandle
0x180258b4b  nop     dword ptr [rax+rax+00h]
0x180258b50  mov     rcx, [rbx+3288h]; hObject
0x180258b57  mov     qword ptr [rbx+3290h], 0
0x180258b62  test    rcx, rcx
0x180258b65  jz      short loc_180258B7E
0x180258b67  call    cs:__imp_CloseHandle
0x180258b6e  nop     dword ptr [rax+rax+00h]
0x180258b73  mov     qword ptr [rbx+3288h], 0
0x180258b7e  mov     qword ptr [rbx+3298h], 0
0x180258b89  add     rsp, 40h
0x180258b8d  pop     rbx
0x180258b8e  retn
```
