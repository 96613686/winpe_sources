# HsmFltPostCLEANUP

- ea: `0x14006be80`
- end: `0x14006bf33`
- name: `HsmFltPostCLEANUP`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140001590`
- `0x140007360`
- `0x14001e220`
- `0x14005c8c0`
- `0x14006be80`

## import_xrefs

- `FLTMGR!FltDeleteContext` at `0x14006bece`
- `FLTMGR!FltDeleteContext` at `0x14006bece`
- `FLTMGR!FltReleaseContext` at `0x14006bedd`
- `FLTMGR!FltReleaseContext` at `0x14006bedd`

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
    HsmpCldNotifyPostOperation(2u, (struct _FLT_CALLBACK_DATA *)a1, (*(_BYTE *)(a1 + 32) & 0xC) != 0 ? 4 : 0, 0, 0);
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
0x14006be80  mov     [rsp+arg_0], rbx
0x14006be85  mov     [rsp+arg_8], rsi
0x14006be8a  push    rdi
0x14006be8b  sub     rsp, 30h
0x14006be8f  mov     rsi, [r8+10h]
0x14006be93  mov     rbx, r8
0x14006be96  mov     rdx, rbx
0x14006be99  mov     r9b, 1
0x14006be9c  xor     r8d, r8d
0x14006be9f  mov     rdi, rcx
0x14006bea2  call    HsmpTracePostCallbackEnter
0x14006bea7  test    rsi, rsi
0x14006beaa  jz      short loc_14006BECB
0x14006beac  mov     rax, cs:qword_140029758
0x14006beb3  xor     r9d, r9d
0x14006beb6  mov     rdx, [rsi+8]
0x14006beba  mov     r8, rdi
0x14006bebd  mov     ecx, 2
0x14006bec2  call    _guard_dispatch_icall
0x14006bec7  test    al, al
0x14006bec9  jnz     short loc_14006BF09
0x14006becb  mov     rcx, rbx; Context
0x14006bece  call    cs:__imp_FltDeleteContext
0x14006bed5  nop     dword ptr [rax+rax+00h]
0x14006beda  mov     rcx, rbx; Context
0x14006bedd  call    cs:__imp_FltReleaseContext
0x14006bee4  nop     dword ptr [rax+rax+00h]
0x14006bee9  mov     r9b, 1
0x14006beec  mov     rdx, rdi
0x14006beef  xor     ecx, ecx
0x14006bef1  call    HsmpTracePostCallbackExit
0x14006bef6  mov     rbx, [rsp+38h+arg_0]
0x14006befb  xor     eax, eax
0x14006befd  mov     rsi, [rsp+38h+arg_8]
0x14006bf02  add     rsp, 30h
0x14006bf06  pop     rdi
0x14006bf07  retn
0x14006bf09  movzx   eax, byte ptr [rdi+20h]
0x14006bf0d  mov     rdx, rdi
0x14006bf10  and     al, 0Ch
0x14006bf12  mov     [rsp+38h+var_18], 0
0x14006bf1b  neg     al
0x14006bf1d  mov     ecx, 2
0x14006bf22  sbb     r8d, r8d
0x14006bf25  xor     r9d, r9d
0x14006bf28  and     r8d, 4
0x14006bf2c  call    HsmpCldNotifyPostOperation
0x14006bf31  jmp     short loc_14006BECB
```
