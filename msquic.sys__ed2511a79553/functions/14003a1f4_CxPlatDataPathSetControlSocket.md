# CxPlatDataPathSetControlSocket

- ea: `0x14003a1f4`
- end: `0x14003a2fa`
- name: `CxPlatDataPathSetControlSocket`
- size: `262`
- prototype: `__int64 __fastcall(int, int, int, int, PLARGE_INTEGER, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14003b850`

## callees

- `0x14003a1f4`
- `0x14003c980`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14003a2cc`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003a2cc`
- `ntoskrnl!KeResetEvent` at `0x14003a250`
- `ntoskrnl!KeResetEvent` at `0x14003a250`
- `ntoskrnl!IoReuseIrp` at `0x14003a223`
- `ntoskrnl!IoReuseIrp` at `0x14003a223`

## pseudocode

```c
__int64 __fastcall CxPlatDataPathSetControlSocket(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        PLARGE_INTEGER a5,
        __int64 a6)
{
  __int64 v6; // rbx
  __int64 v11; // rax
  __int64 result; // rax
  __int64 v13; // [rsp+80h] [rbp+8h] BYREF

  v6 = a1 + 128;
  IoReuseIrp((PIRP)(a1 + 128), 0);
  v11 = *(_QWORD *)(a1 + 312);
  *(_QWORD *)(v11 - 16) = &CxPlatDataPathIoCompletion;
  *(_QWORD *)(v11 - 8) = a1 + 96;
  *(_BYTE *)(v11 - 69) = -32;
  KeResetEvent((PRKEVENT)(a1 + 96));
  v13 = 0;
  result = (***(__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD, _QWORD, PLARGE_INTEGER, __int64, _QWORD, _QWORD, __int64 *, __int64))(a1 + 88))(
             *(_QWORD *)(a1 + 88),
             a2,
             a3,
             a4,
             a5,
             a6,
             0,
             0,
             &v13,
             v6);
  if ( (_DWORD)result == 259 )
  {
    KeWaitForSingleObject((PVOID)(a1 + 96), Executive, 0, 0, 0);
    return *(unsigned int *)(a1 + 176);
  }
  return result;
}

```

## disassembly

```asm
0x14003a1f4  mov     [rsp+arg_8], rbx
0x14003a1f9  mov     [rsp+arg_10], rbp
0x14003a1fe  mov     [rsp+arg_18], rsi
0x14003a203  push    rdi
0x14003a204  push    r14
0x14003a206  push    r15
0x14003a208  sub     rsp, 60h
0x14003a20c  lea     rbx, [rcx+80h]
0x14003a213  mov     ebp, edx
0x14003a215  mov     r14, rcx
0x14003a218  xor     edx, edx; Iostatus
0x14003a21a  mov     rcx, rbx; Irp
0x14003a21d  mov     edi, r9d
0x14003a220  mov     esi, r8d
0x14003a223  call    cs:__imp_IoReuseIrp
0x14003a22a  nop     dword ptr [rax+rax+00h]
0x14003a22f  mov     rax, [r14+138h]
0x14003a236  lea     rcx, CxPlatDataPathIoCompletion
0x14003a23d  lea     r15, [r14+60h]
0x14003a241  mov     [rax-10h], rcx
0x14003a245  mov     rcx, r15; Event
0x14003a248  mov     [rax-8], r15
0x14003a24c  mov     byte ptr [rax-45h], 0E0h
0x14003a250  call    cs:__imp_KeResetEvent
0x14003a257  nop     dword ptr [rax+rax+00h]
0x14003a25c  and     [rsp+78h+arg_0], 0
0x14003a265  lea     rdx, [rsp+78h+arg_0]
0x14003a26d  mov     rcx, [r14+58h]
0x14003a271  mov     r9d, edi
0x14003a274  mov     [rsp+78h+var_30], rbx
0x14003a279  mov     r8d, esi
0x14003a27c  mov     [rsp+78h+var_38], rdx
0x14003a281  and     [rsp+78h+var_40], 0
0x14003a287  mov     rdx, [rsp+78h+arg_28]
0x14003a28f  mov     rax, [rcx]
0x14003a292  and     [rsp+78h+var_48], 0
0x14003a298  mov     [rsp+78h+var_50], rdx
0x14003a29d  mov     rdx, [rsp+78h+arg_20]
0x14003a2a5  mov     rax, [rax]
0x14003a2a8  mov     [rsp+78h+Timeout], rdx; Timeout
0x14003a2ad  mov     edx, ebp
0x14003a2af  call    _guard_dispatch_icall
0x14003a2b4  cmp     eax, 103h
0x14003a2b9  jnz     short loc_14003A2DF
0x14003a2bb  and     [rsp+78h+Timeout], 0
0x14003a2c1  xor     r9d, r9d; Alertable
0x14003a2c4  xor     r8d, r8d; WaitMode
0x14003a2c7  xor     edx, edx; WaitReason
0x14003a2c9  mov     rcx, r15; Object
0x14003a2cc  call    cs:__imp_KeWaitForSingleObject
0x14003a2d3  nop     dword ptr [rax+rax+00h]
0x14003a2d8  mov     eax, [r14+0B0h]
0x14003a2df  lea     r11, [rsp+78h+var_18]
0x14003a2e4  mov     rbx, [r11+28h]
0x14003a2e8  mov     rbp, [r11+30h]
0x14003a2ec  mov     rsi, [r11+38h]
0x14003a2f0  mov     rsp, r11
0x14003a2f3  pop     r15
0x14003a2f5  pop     r14
0x14003a2f7  pop     rdi
0x14003a2f8  retn
```
