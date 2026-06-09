# HsmFltPostCLEANUP

- ea: `0x14006bfa0`
- end: `0x14006c053`
- name: `HsmFltPostCLEANUP`
- size: `179`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140001590`
- `0x140007360`
- `0x14001e2a0`
- `0x14005c9e0`
- `0x14006bfa0`

## import_xrefs

- `FLTMGR!FltDeleteContext` at `0x14006bfee`
- `FLTMGR!FltDeleteContext` at `0x14006bfee`
- `FLTMGR!FltReleaseContext` at `0x14006bffd`
- `FLTMGR!FltReleaseContext` at `0x14006bffd`

## pseudocode

```c
__int64 __fastcall HsmFltPostCLEANUP(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  __int64 v4; // rsi
  __int64 v7; // r9
  __int64 v8; // r8

  v4 = a3[2];
  LOBYTE(a4) = 1;
  HsmpTracePostCallbackEnter(a1, a3, 0, a4);
  if ( v4
    && (unsigned __int8)((__int64 (__fastcall *)(__int64, _QWORD, __int64, _QWORD))qword_140029758)(
                          2,
                          *(_QWORD *)(v4 + 8),
                          a1,
                          0) )
  {
    HsmpCldNotifyPostOperation(2, a1, (*(_BYTE *)(a1 + 32) & 0xC) != 0 ? 4 : 0, 0, 0);
  }
  FltDeleteContext(a3);
  FltReleaseContext(a3);
  LOBYTE(v7) = 1;
  HsmpTracePostCallbackExit(0, a1, v8, v7);
  return 0;
}

```

## disassembly

```asm
0x14006bfa0  mov     [rsp+arg_0], rbx
0x14006bfa5  mov     [rsp+arg_8], rsi
0x14006bfaa  push    rdi
0x14006bfab  sub     rsp, 30h
0x14006bfaf  mov     rsi, [r8+10h]
0x14006bfb3  mov     rbx, r8
0x14006bfb6  mov     rdx, rbx
0x14006bfb9  mov     r9b, 1
0x14006bfbc  xor     r8d, r8d
0x14006bfbf  mov     rdi, rcx
0x14006bfc2  call    HsmpTracePostCallbackEnter
0x14006bfc7  test    rsi, rsi
0x14006bfca  jz      short loc_14006BFEB
0x14006bfcc  mov     rax, cs:qword_140029758
0x14006bfd3  xor     r9d, r9d
0x14006bfd6  mov     rdx, [rsi+8]
0x14006bfda  mov     r8, rdi
0x14006bfdd  mov     ecx, 2
0x14006bfe2  call    _guard_dispatch_icall
0x14006bfe7  test    al, al
0x14006bfe9  jnz     short loc_14006C029
0x14006bfeb  mov     rcx, rbx; Context
0x14006bfee  call    cs:__imp_FltDeleteContext
0x14006bff5  nop     dword ptr [rax+rax+00h]
0x14006bffa  mov     rcx, rbx; Context
0x14006bffd  call    cs:__imp_FltReleaseContext
0x14006c004  nop     dword ptr [rax+rax+00h]
0x14006c009  mov     r9b, 1
0x14006c00c  mov     rdx, rdi
0x14006c00f  xor     ecx, ecx
0x14006c011  call    HsmpTracePostCallbackExit
0x14006c016  mov     rbx, [rsp+38h+arg_0]
0x14006c01b  xor     eax, eax
0x14006c01d  mov     rsi, [rsp+38h+arg_8]
0x14006c022  add     rsp, 30h
0x14006c026  pop     rdi
0x14006c027  retn
0x14006c029  movzx   eax, byte ptr [rdi+20h]
0x14006c02d  mov     rdx, rdi
0x14006c030  and     al, 0Ch
0x14006c032  mov     [rsp+38h+var_18], 0
0x14006c03b  neg     al
0x14006c03d  mov     ecx, 2
0x14006c042  sbb     r8d, r8d
0x14006c045  xor     r9d, r9d
0x14006c048  and     r8d, 4
0x14006c04c  call    HsmpCldNotifyPostOperation
0x14006c051  jmp     short loc_14006BFEB
```
