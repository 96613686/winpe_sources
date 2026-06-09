# TpCallInitialize

- ea: `0x140002a60`
- end: `0x140002b44`
- name: `TpCallInitialize`
- size: `228`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140005c90`
- `0x140014884`

## callees

- `0x14000110c`
- `0x140002a60`
- `0x140007040`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x140002ad3`
- `ntoskrnl!KeInitializeSpinLock` at `0x140002ad3`

## pseudocode

```c
__int64 __fastcall TpCallInitialize(KSPIN_LOCK *a1, __int64 a2, __int64 a3, char a4)
{
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x69u,
      (__int64)WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
  }
  memset(a1, 0, 0x358u);
  a1[1] = (KSPIN_LOCK)a1;
  *a1 = (KSPIN_LOCK)a1;
  *((_DWORD *)a1 + 4) = 1749380944;
  *((_DWORD *)a1 + 20) = 3;
  KeInitializeSpinLock(a1 + 7);
  *((_BYTE *)a1 + 76) = a4;
  a1[102] = (KSPIN_LOCK)(a1 + 101);
  a1[101] = (KSPIN_LOCK)(a1 + 101);
  a1[13] = 0;
  *((_DWORD *)a1 + 32) = 1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x6Au,
      (__int64)WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140002a60  mov     [rsp+arg_0], rbx
0x140002a65  mov     [rsp+arg_8], rsi
0x140002a6a  push    rdi
0x140002a6b  sub     rsp, 20h
0x140002a6f  mov     dil, r9b
0x140002a72  mov     rbx, rcx
0x140002a75  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a7c  lea     rsi, WPP_GLOBAL_Control
0x140002a83  cmp     rcx, rsi
0x140002a86  jz      short loc_140002AAA
0x140002a88  mov     eax, [rcx+2Ch]
0x140002a8b  test    al, 2
0x140002a8d  jz      short loc_140002AAA
0x140002a8f  cmp     byte ptr [rcx+29h], 3
0x140002a93  jb      short loc_140002AAA
0x140002a95  mov     rcx, [rcx+18h]
0x140002a99  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x140002aa0  mov     edx, 69h ; 'i'
0x140002aa5  call    WPP_SF_
0x140002aaa  xor     edx, edx; Val
0x140002aac  mov     r8d, 358h; Size
0x140002ab2  mov     rcx, rbx; void *
0x140002ab5  call    memset
0x140002aba  lea     rcx, [rbx+38h]; SpinLock
0x140002abe  mov     [rbx+8], rbx
0x140002ac2  mov     [rbx], rbx
0x140002ac5  mov     dword ptr [rbx+10h], 68456F50h
0x140002acc  mov     dword ptr [rbx+50h], 3
0x140002ad3  call    cs:__imp_KeInitializeSpinLock
0x140002ada  nop     dword ptr [rax+rax+00h]
0x140002adf  lea     rax, [rbx+328h]
0x140002ae6  mov     [rbx+4Ch], dil
0x140002aea  mov     [rax+8], rax
0x140002aee  mov     [rax], rax
0x140002af1  mov     qword ptr [rbx+68h], 0
0x140002af9  mov     dword ptr [rbx+80h], 1
0x140002b03  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b0a  cmp     rcx, rsi
0x140002b0d  jz      short loc_140002B31
0x140002b0f  mov     eax, [rcx+2Ch]
0x140002b12  test    al, 2
0x140002b14  jz      short loc_140002B31
0x140002b16  cmp     byte ptr [rcx+29h], 3
0x140002b1a  jb      short loc_140002B31
0x140002b1c  mov     rcx, [rcx+18h]
0x140002b20  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x140002b27  mov     edx, 6Ah ; 'j'
0x140002b2c  call    WPP_SF_
0x140002b31  mov     rbx, [rsp+28h+arg_0]
0x140002b36  xor     eax, eax
0x140002b38  mov     rsi, [rsp+28h+arg_8]
0x140002b3d  add     rsp, 20h
0x140002b41  pop     rdi
0x140002b42  retn
```
