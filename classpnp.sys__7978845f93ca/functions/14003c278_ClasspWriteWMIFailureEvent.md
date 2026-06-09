# ClasspWriteWMIFailureEvent

- ea: `0x14003c278`
- end: `0x14003c39b`
- name: `ClasspWriteWMIFailureEvent`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140005190`

## callees

- `0x140016ae0`
- `0x140016f70`
- `0x14003c278`
- `0x14003ceec`
- `0x14003e430`

## pseudocode

```c
_DWORD *__fastcall ClasspWriteWMIFailureEvent(int a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  unsigned int v4; // r14d
  unsigned int v6; // esi
  _DWORD *result; // rax
  __int64 v9; // rbx
  int v10; // edx
  int v11; // ecx
  __int64 v12; // [rsp+70h] [rbp-9h] BYREF
  __int64 v13; // [rsp+78h] [rbp-1h] BYREF
  __int64 v14; // [rsp+80h] [rbp+7h] BYREF
  __int64 v15; // [rsp+88h] [rbp+Fh] BYREF
  __int128 *v16; // [rsp+90h] [rbp+17h] BYREF
  __int128 v17; // [rsp+98h] [rbp+1Fh] BYREF

  v3 = *(_QWORD *)(a3 + 184);
  v4 = *(_DWORD *)(a3 + 48);
  v16 = &v17;
  v15 = 0;
  v17 = 0;
  v6 = *(unsigned __int8 *)(v3 + 1);
  v14 = 0;
  v13 = 0;
  v12 = 0;
  result = (_DWORD *)ClasspIsErrorStatusNoisy(v4, 0, 7, v6);
  if ( !(_BYTE)result )
  {
    v9 = *(_QWORD *)(a2 + 64);
    result = ClasspGetDeviceIdData(v9, &v16, &v15, &v14, &v13, &v12);
    if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x20) != 0 )
      return (_DWORD *)McTemplateK0jqssssdujp_EtwWriteTransfer(
                         v11,
                         v10,
                         a1,
                         (_DWORD)v16,
                         *(_DWORD *)(v9 + 588),
                         v15,
                         v14,
                         v13,
                         v12,
                         v4,
                         v6,
                         *(_QWORD *)(v3 + 16),
                         *(_QWORD *)(v3 + 8));
  }
  return result;
}

```

## disassembly

```asm
0x14003c278  mov     [rsp-8+arg_18], rbx
0x14003c27d  push    rbp
0x14003c27e  push    rsi
0x14003c27f  push    rdi
0x14003c280  push    r14
0x14003c282  push    r15
0x14003c284  lea     rbp, [rsp-37h]
0x14003c289  sub     rsp, 0B0h
0x14003c290  mov     rax, cs:__security_cookie
0x14003c297  xor     rax, rsp
0x14003c29a  mov     [rbp+57h+var_28], rax
0x14003c29e  mov     rdi, [r8+0B8h]
0x14003c2a5  lea     rax, [rbp+57h+var_38]
0x14003c2a9  mov     r14d, [r8+30h]
0x14003c2ad  xor     r10d, r10d
0x14003c2b0  mov     rbx, rdx
0x14003c2b3  mov     [rbp+57h+var_40], rax
0x14003c2b7  xorps   xmm0, xmm0
0x14003c2ba  mov     [rbp+57h+var_48], r10
0x14003c2be  movups  [rbp+57h+var_38], xmm0
0x14003c2c2  movzx   esi, byte ptr [rdi+1]
0x14003c2c6  lea     r8d, [r10+7]
0x14003c2ca  mov     r15, rcx
0x14003c2cd  mov     [rbp+57h+var_50], r10
0x14003c2d1  mov     r9d, esi
0x14003c2d4  mov     [rbp+57h+var_58], r10
0x14003c2d8  xor     edx, edx
0x14003c2da  mov     [rbp+57h+var_60], r10
0x14003c2de  mov     ecx, r14d
0x14003c2e1  call    ClasspIsErrorStatusNoisy
0x14003c2e6  test    al, al
0x14003c2e8  jnz     loc_14003C377
0x14003c2ee  mov     rbx, [rbx+40h]
0x14003c2f2  lea     rax, [rbp+57h+var_60]
0x14003c2f6  mov     [rsp+0D0h+var_A8], rax
0x14003c2fb  lea     r9, [rbp+57h+var_50]
0x14003c2ff  lea     rax, [rbp+57h+var_58]
0x14003c303  mov     rcx, rbx
0x14003c306  lea     r8, [rbp+57h+var_48]
0x14003c30a  mov     [rsp+0D0h+var_B0], rax
0x14003c30f  lea     rdx, [rbp+57h+var_40]
0x14003c313  call    ClasspGetDeviceIdData
0x14003c318  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ch, 20h
0x14003c31f  jz      short loc_14003C377
0x14003c321  mov     rax, [rdi+8]
0x14003c325  mov     r8, r15
0x14003c328  mov     r9, [rbp+57h+var_40]
0x14003c32c  mov     [rsp+0D0h+var_70], rax
0x14003c331  mov     rax, [rdi+10h]
0x14003c335  mov     [rsp+0D0h+var_78], rax
0x14003c33a  mov     rax, [rbp+57h+var_60]
0x14003c33e  mov     [rsp+0D0h+var_80], sil
0x14003c343  mov     [rsp+0D0h+var_88], r14d
0x14003c348  mov     [rsp+0D0h+var_90], rax
0x14003c34d  mov     rax, [rbp+57h+var_58]
0x14003c351  mov     [rsp+0D0h+var_98], rax
0x14003c356  mov     rax, [rbp+57h+var_50]
0x14003c35a  mov     [rsp+0D0h+var_A0], rax
0x14003c35f  mov     rax, [rbp+57h+var_48]
0x14003c363  mov     [rsp+0D0h+var_A8], rax
0x14003c368  mov     eax, [rbx+24Ch]
0x14003c36e  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14003c372  call    McTemplateK0jqssssdujp_EtwWriteTransfer
0x14003c377  mov     rcx, [rbp+57h+var_28]
0x14003c37b  xor     rcx, rsp; StackCookie
0x14003c37e  call    __security_check_cookie
0x14003c383  mov     rbx, [rsp+0D0h+arg_18]
0x14003c38b  add     rsp, 0B0h
0x14003c392  pop     r15
0x14003c394  pop     r14
0x14003c396  pop     rdi
0x14003c397  pop     rsi
0x14003c398  pop     rbp
0x14003c399  retn
```
