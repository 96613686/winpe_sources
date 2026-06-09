# L2tpSendDatagram

- ea: `0x14001c1b0`
- end: `0x14001c383`
- name: `L2tpSendDatagram`
- size: `467`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1400175f0`
- `0x140017d90`
- `0x140017fa0`

## callees

- `0x140001e1c`
- `0x140003df0`
- `0x140003ec8`
- `0x1400047f0`
- `0x14001c1b0`
- `0x1400208f0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001c287`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c287`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c21a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c21a`

## pseudocode

```c
__int64 __fastcall L2tpSendDatagram(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5)
{
  __int64 v8; // r14
  KIRQL v9; // al
  bool v10; // zf
  __int64 v11; // rcx
  __int16 v12; // si
  __int64 v13; // rax
  char v14; // si
  __int64 v15; // r15
  int v17; // edi
  struct _DEVICE_OBJECT *AttachedDevice; // rsi
  int StringFromSockAddr; // eax
  int v20; // edx
  int v21; // r8d
  __int64 v22; // rdi
  struct _DEVICE_OBJECT *v23; // rbp
  __int64 v24; // rax
  int v25; // edx
  int v26; // r8d
  char v27; // [rsp+40h] [rbp-B8h]
  _OWORD v29[4]; // [rsp+60h] [rbp-98h] BYREF
  char v30; // [rsp+A0h] [rbp-58h]

  memset(v29, 0, sizeof(v29));
  v30 = 0;
  v8 = 0;
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 32));
  v10 = *(_BYTE *)(a1 + 112) == 0;
  v11 = *(_QWORD *)(a1 + 24);
  v12 = *(_WORD *)(a1 + 50);
  *(_BYTE *)(a1 + 40) = v9;
  v13 = 312;
  if ( v10 )
    v13 = 272;
  v14 = __ROR2__(v12, 8);
  v27 = v14;
  v15 = *(_QWORD *)(v11 + v13);
  if ( (*(_DWORD *)(a1 + 120) & 0x4000) != 0 )
  {
    v8 = a1 + 80;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v17 = *(_DWORD *)(a1 + 108);
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      StringFromSockAddr = GetStringFromSockAddr(a1 + 80, v29);
      WPP_SF_sd((_DWORD)AttachedDevice, v20, v21, StringFromSockAddr, v17);
    }
    v14 = v27;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 32), *(_BYTE *)(a1 + 40));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v22 = *(_QWORD *)(v15 + 384);
    v23 = WPP_GLOBAL_Control->AttachedDevice;
    v24 = GetStringFromSockAddr(a1 + 48, v29);
    WPP_SF_qsdqq((_DWORD)v23, v25, v26, a1, v24, v14, v15, v22);
  }
  return WskSendDatagram(v15, a1 + 48, v8, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x14001c1b0  mov     r11, rsp
0x14001c1b3  mov     [r11+20h], rbx
0x14001c1b7  push    rbp
0x14001c1b8  push    rsi
0x14001c1b9  push    rdi
0x14001c1ba  push    r12
0x14001c1bc  push    r13
0x14001c1be  push    r14
0x14001c1c0  push    r15
0x14001c1c2  sub     rsp, 0C0h
0x14001c1c9  mov     rax, cs:__security_cookie
0x14001c1d0  xor     rax, rsp
0x14001c1d3  mov     [rsp+0F8h+var_48], rax
0x14001c1db  mov     rax, [rsp+0F8h+arg_20]
0x14001c1e3  xorps   xmm0, xmm0
0x14001c1e6  movups  [rsp+0F8h+var_98], xmm0
0x14001c1eb  mov     [rsp+0F8h+var_B0], rax
0x14001c1f0  xor     eax, eax
0x14001c1f2  movups  [rsp+0F8h+var_88], xmm0
0x14001c1f7  mov     rbx, rcx
0x14001c1fa  mov     [r11-58h], al
0x14001c1fe  add     rcx, 20h ; ' '; SpinLock
0x14001c202  mov     [rsp+0F8h+var_A8], r8
0x14001c207  mov     r12d, r9d
0x14001c20a  mov     r13, rdx
0x14001c20d  xor     r14d, r14d
0x14001c210  movups  xmmword ptr [r11-78h], xmm0
0x14001c215  movups  xmmword ptr [r11-68h], xmm0
0x14001c21a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001c221  nop     dword ptr [rax+rax+00h]
0x14001c226  cmp     [rbx+70h], r14b
0x14001c22a  mov     edx, 110h
0x14001c22f  mov     rcx, [rbx+18h]
0x14001c233  movzx   esi, word ptr [rbx+32h]
0x14001c237  mov     [rbx+28h], al
0x14001c23a  mov     eax, 138h
0x14001c23f  cmovz   eax, edx
0x14001c242  ror     si, 8
0x14001c246  test    dword ptr [rbx+78h], 4000h
0x14001c24d  mov     word ptr [rsp+0F8h+var_B8], si
0x14001c252  mov     r15, [rcx+rax]
0x14001c256  lea     rcx, WPP_GLOBAL_Control
0x14001c25d  jz      short loc_14001C27F
0x14001c25f  lea     r14, [rbx+50h]
0x14001c263  mov     rsi, cs:WPP_GLOBAL_Control
0x14001c26a  cmp     rsi, rcx
0x14001c26d  jz      short loc_14001C27A
0x14001c26f  mov     eax, [rsi+2Ch]
0x14001c272  test    al, 10h
0x14001c274  jnz     loc_14001C308
0x14001c27a  movzx   esi, word ptr [rsp+0F8h+var_B8]
0x14001c27f  movzx   edx, byte ptr [rbx+28h]; NewIrql
0x14001c283  lea     rcx, [rbx+20h]; SpinLock
0x14001c287  call    cs:__imp_KeReleaseSpinLock
0x14001c28e  nop     dword ptr [rax+rax+00h]
0x14001c293  mov     rbp, cs:WPP_GLOBAL_Control
0x14001c29a  lea     rax, WPP_GLOBAL_Control
0x14001c2a1  cmp     rbp, rax
0x14001c2a4  jz      short loc_14001C2B1
0x14001c2a6  mov     eax, [rbp+2Ch]
0x14001c2a9  test    al, 10h
0x14001c2ab  jnz     loc_14001C33A
0x14001c2b1  mov     rax, [rsp+0F8h+var_B0]
0x14001c2b6  lea     rdx, [rbx+30h]
0x14001c2ba  mov     [rsp+0F8h+var_C8], rax
0x14001c2bf  mov     r9, r13
0x14001c2c2  mov     rax, [rsp+0F8h+var_A8]
0x14001c2c7  mov     r8, r14
0x14001c2ca  mov     [rsp+0F8h+var_D0], r12d
0x14001c2cf  mov     rcx, r15
0x14001c2d2  mov     [rsp+0F8h+var_D8], rax
0x14001c2d7  call    WskSendDatagram
0x14001c2dc  mov     rcx, [rsp+0F8h+var_48]
0x14001c2e4  xor     rcx, rsp; StackCookie
0x14001c2e7  call    __security_check_cookie
0x14001c2ec  mov     rbx, [rsp+0F8h+arg_18]
0x14001c2f4  add     rsp, 0C0h
0x14001c2fb  pop     r15
0x14001c2fd  pop     r14
0x14001c2ff  pop     r13
0x14001c301  pop     r12
0x14001c303  pop     rdi
0x14001c304  pop     rsi
0x14001c305  pop     rbp
0x14001c306  retn
0x14001c308  cmp     byte ptr [rsi+29h], 1
0x14001c30c  jb      loc_14001C27A
0x14001c312  mov     edi, [rbx+6Ch]
0x14001c315  lea     rdx, [rsp+0F8h+var_98]
0x14001c31a  mov     rsi, [rsi+18h]
0x14001c31e  mov     rcx, r14
0x14001c321  call    GetStringFromSockAddr
0x14001c326  mov     r9, rax
0x14001c329  mov     dword ptr [rsp+0F8h+var_D8], edi
0x14001c32d  mov     rcx, rsi
0x14001c330  call    WPP_SF_sd
0x14001c335  jmp     loc_14001C27A
0x14001c33a  cmp     byte ptr [rbp+29h], 1
0x14001c33e  jb      loc_14001C2B1
0x14001c344  mov     rdi, [r15+180h]
0x14001c34b  lea     rcx, [rbx+30h]
0x14001c34f  mov     rbp, [rbp+18h]
0x14001c353  lea     rdx, [rsp+0F8h+var_98]
0x14001c358  movzx   esi, si
0x14001c35b  call    GetStringFromSockAddr
0x14001c360  mov     [rsp+0F8h+var_C0], rdi
0x14001c365  mov     r9, rbx
0x14001c368  mov     [rsp+0F8h+var_C8], r15
0x14001c36d  mov     rcx, rbp
0x14001c370  mov     [rsp+0F8h+var_D0], esi
0x14001c374  mov     [rsp+0F8h+var_D8], rax
0x14001c379  call    WPP_SF_qsdqq
0x14001c37e  jmp     loc_14001C2B1
```
