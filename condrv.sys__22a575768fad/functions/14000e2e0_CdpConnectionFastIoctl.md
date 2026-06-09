# CdpConnectionFastIoctl

- ea: `0x14000e2e0`
- end: `0x14000e39a`
- name: `CdpConnectionFastIoctl`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400081a0`
- `0x14000e2e0`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x14000e2f0`
- `ntoskrnl!ExGetPreviousMode` at `0x14000e2f0`
- `ntoskrnl!ProbeForWrite` at `0x14000e371`
- `ntoskrnl!ProbeForWrite` at `0x14000e371`

## pseudocode

```c
char __fastcall CdpConnectionFastIoctl(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, int a5, int a6, __int64 a7)
{
  KPROCESSOR_MODE PreviousMode; // di
  __int64 v11; // rax
  int v12; // eax

  PreviousMode = ExGetPreviousMode();
  *(_QWORD *)(a7 + 8) = 0;
  if ( a6 != 5242915 )
    return 0;
  if ( a5 == 8 )
  {
    if ( PreviousMode == 1 )
      ProbeForWrite(a4, 8u, 4u);
    v11 = *(_QWORD *)(a1 + 24);
    if ( PreviousMode )
      RtlWriteULong64ToUser(a4, *(_QWORD *)(v11 + 184));
    else
      *a4 = *(_QWORD *)(v11 + 184);
    v12 = 0;
  }
  else
  {
    v12 = -1073741306;
  }
  *(_DWORD *)a7 = v12;
  return 1;
}

```

## disassembly

```asm
0x14000e2e0  push    rbx
0x14000e2e2  push    rsi
0x14000e2e3  push    rdi
0x14000e2e4  push    r14
0x14000e2e6  sub     rsp, 38h
0x14000e2ea  mov     r14, r9
0x14000e2ed  mov     rsi, rcx
0x14000e2f0  call    cs:__imp_ExGetPreviousMode
0x14000e2f7  nop     dword ptr [rax+rax+00h]
0x14000e2fc  movzx   edi, al
0x14000e2ff  mov     rbx, [rsp+58h+arg_30]
0x14000e307  mov     qword ptr [rbx+8], 0
0x14000e30f  cmp     [rsp+58h+arg_28], 500023h
0x14000e31a  jz      short loc_14000E329
0x14000e31c  xor     al, al
0x14000e31e  add     rsp, 38h
0x14000e322  pop     r14
0x14000e324  pop     rdi
0x14000e325  pop     rsi
0x14000e326  pop     rbx
0x14000e327  retn
0x14000e329  mov     byte ptr [rsp+58h+arg_28], dil
0x14000e331  cmp     [rsp+58h+arg_20], 8
0x14000e339  jnz     short loc_14000E393
0x14000e33b  cmp     dil, 1
0x14000e33f  jz      short loc_14000E363
0x14000e341  mov     rax, [rsi+18h]
0x14000e345  mov     rcx, [rax+0B8h]
0x14000e34c  test    dil, dil
0x14000e34f  jz      short loc_14000E35E
0x14000e351  mov     rdx, rcx
0x14000e354  mov     rcx, r14
0x14000e357  call    RtlWriteULong64ToUser
0x14000e35c  jmp     short loc_14000E37F
0x14000e35e  mov     [r14], rcx
0x14000e361  jmp     short loc_14000E37F
0x14000e363  mov     edx, 8; Length
0x14000e368  mov     r8d, 4; Alignment
0x14000e36e  mov     rcx, r14; Address
0x14000e371  call    cs:__imp_ProbeForWrite
0x14000e378  nop     dword ptr [rax+rax+00h]
0x14000e37d  jmp     short loc_14000E341
0x14000e37f  jmp     short loc_14000E38B
0x14000e381  mov     rbx, [rsp+58h+arg_30]
0x14000e389  jmp     short loc_14000E38D
0x14000e38b  xor     eax, eax
0x14000e38d  mov     [rbx], eax
0x14000e38f  mov     al, 1
0x14000e391  jmp     short loc_14000E31E
0x14000e393  mov     eax, 0C0000206h
0x14000e398  jmp     short loc_14000E38D
0x14000e7a0  push    rbp
0x14000e7a2  sub     rsp, 20h
0x14000e7a6  mov     rbp, rdx
0x14000e7a9  xor     eax, eax
0x14000e7ab  cmp     [rbp+88h], al
0x14000e7b1  setnz   al
0x14000e7b4  mov     [rbp+20h], eax
0x14000e7b7  mov     eax, [rbp+20h]
0x14000e7ba  add     rsp, 20h
0x14000e7be  pop     rbp
0x14000e7bf  retn
```
