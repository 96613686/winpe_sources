# ClasspWritePnPFailureEvent

- ea: `0x14003c0d4`
- end: `0x14003c270`
- name: `ClasspWritePnPFailureEvent`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400180f4`

## callees

- `0x140016ae0`
- `0x140016f70`
- `0x14003c0d4`
- `0x14003d258`
- `0x14003e430`

## pseudocode

```c
__int128 *__fastcall ClasspWritePnPFailureEvent(int a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  __int128 *result; // rax
  bool v6; // zf
  __int64 v7; // rbx
  unsigned int v8; // r15d
  unsigned __int8 v9; // di
  char v10; // r14
  int v11; // r9d
  __int64 v12; // [rsp+90h] [rbp-9h] BYREF
  __int64 v13; // [rsp+98h] [rbp-1h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v15; // [rsp+A8h] [rbp+Fh] BYREF
  __int128 *v16; // [rsp+B0h] [rbp+17h] BYREF
  __int128 v17; // [rsp+B8h] [rbp+1Fh] BYREF

  v3 = *(_QWORD *)(a2 + 64);
  result = &v17;
  v16 = &v17;
  v17 = 0;
  v15 = 0;
  v6 = (*(_BYTE *)(v3 + 104) & 1) == 0;
  v14 = 0;
  v13 = 0;
  v12 = 0;
  if ( !v6 )
  {
    v7 = *(_QWORD *)(a3 + 184);
    v8 = *(_DWORD *)(a3 + 48);
    v9 = *(_BYTE *)(v7 + 1);
    result = (__int128 *)ClasspIsErrorStatusNoisy(v8, 0, 1, v9);
    if ( !(_BYTE)result )
    {
      v10 = 0;
      result = (__int128 *)ClasspGetDeviceIdData(v3, &v16, &v15, &v14, &v13, &v12);
      if ( v9 == 7 || v9 == 19 )
      {
        v11 = *(_DWORD *)(v7 + 8);
      }
      else
      {
        LOBYTE(v11) = 0;
        if ( v9 == 22 )
        {
          v11 = *(_DWORD *)(v7 + 16);
          v10 = *(_BYTE *)(v7 + 8);
        }
      }
      if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 8) != 0 )
        return (__int128 *)McTemplateK0jqssssduqtqqqqq_EtwWriteTransfer(
                             *(unsigned __int8 *)(v3 + 105),
                             *(unsigned __int8 *)(v3 + 106),
                             a1,
                             (_DWORD)v16,
                             *(_DWORD *)(v3 + 588),
                             v15,
                             v14,
                             v13,
                             v12,
                             v8,
                             v9,
                             v11,
                             v10,
                             *(_BYTE *)(v3 + 106),
                             *(_BYTE *)(v3 + 105),
                             *(_DWORD *)(v3 + 168),
                             *(_DWORD *)(v3 + 176),
                             *(_DWORD *)(v3 + 172));
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003c0d4  mov     [rsp-8+arg_10], rbx
0x14003c0d9  mov     [rsp-8+arg_18], rsi
0x14003c0de  push    rbp
0x14003c0df  push    rdi
0x14003c0e0  push    r12
0x14003c0e2  push    r14
0x14003c0e4  push    r15
0x14003c0e6  lea     rbp, [rsp-37h]
0x14003c0eb  sub     rsp, 0D0h
0x14003c0f2  mov     rax, cs:__security_cookie
0x14003c0f9  xor     rax, rsp
0x14003c0fc  mov     [rbp+57h+var_28], rax
0x14003c100  mov     rsi, [rdx+40h]
0x14003c104  lea     rax, [rbp+57h+var_38]
0x14003c108  xorps   xmm0, xmm0
0x14003c10b  mov     [rbp+57h+var_40], rax
0x14003c10f  movups  [rbp+57h+var_38], xmm0
0x14003c113  mov     r12, rcx
0x14003c116  mov     [rbp+57h+var_48], 0
0x14003c11e  test    byte ptr [rsi+68h], 1
0x14003c122  mov     [rbp+57h+var_50], 0
0x14003c12a  mov     [rbp+57h+var_58], 0
0x14003c132  mov     [rbp+57h+var_60], 0
0x14003c13a  jz      loc_14003C247
0x14003c140  mov     rbx, [r8+0B8h]
0x14003c147  xor     edx, edx
0x14003c149  mov     r15d, [r8+30h]
0x14003c14d  mov     ecx, r15d
0x14003c150  movzx   edi, byte ptr [rbx+1]
0x14003c154  lea     r8d, [rdx+1]
0x14003c158  mov     r9d, edi
0x14003c15b  call    ClasspIsErrorStatusNoisy
0x14003c160  test    al, al
0x14003c162  jnz     loc_14003C247
0x14003c168  lea     rax, [rbp+57h+var_60]
0x14003c16c  mov     rcx, rsi
0x14003c16f  mov     [rsp+0F0h+var_C8], rax
0x14003c174  lea     r9, [rbp+57h+var_50]
0x14003c178  lea     rax, [rbp+57h+var_58]
0x14003c17c  xor     r14b, r14b
0x14003c17f  lea     r8, [rbp+57h+var_48]
0x14003c183  mov     [rsp+0F0h+var_D0], rax
0x14003c188  lea     rdx, [rbp+57h+var_40]
0x14003c18c  call    ClasspGetDeviceIdData
0x14003c191  cmp     dil, 7
0x14003c195  jz      short loc_14003C1B0
0x14003c197  cmp     dil, 13h
0x14003c19b  jz      short loc_14003C1B0
0x14003c19d  xor     r9d, r9d
0x14003c1a0  cmp     dil, 16h
0x14003c1a4  jnz     short loc_14003C1B4
0x14003c1a6  mov     r9d, [rbx+10h]
0x14003c1aa  mov     r14b, [rbx+8]
0x14003c1ae  jmp     short loc_14003C1B4
0x14003c1b0  mov     r9d, [rbx+8]
0x14003c1b4  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ch, 8
0x14003c1bb  jz      loc_14003C247
0x14003c1c1  mov     eax, [rsi+0ACh]
0x14003c1c7  movzx   ecx, byte ptr [rsi+69h]
0x14003c1cb  movzx   edx, byte ptr [rsi+6Ah]
0x14003c1cf  mov     [rsp+0F0h+var_68], eax
0x14003c1d6  mov     eax, [rsi+0B0h]
0x14003c1dc  mov     [rsp+0F0h+var_70], eax
0x14003c1e3  mov     eax, [rsi+0A8h]
0x14003c1e9  mov     [rsp+0F0h+var_78], eax
0x14003c1ed  mov     rax, [rbp+57h+var_60]
0x14003c1f1  mov     [rsp+0F0h+var_80], ecx
0x14003c1f5  mov     [rsp+0F0h+var_88], edx
0x14003c1f9  movzx   r8d, r14b
0x14003c1fd  mov     [rsp+0F0h+var_90], r8d
0x14003c202  mov     r8, r12
0x14003c205  mov     [rsp+0F0h+var_98], r9d
0x14003c20a  mov     r9, [rbp+57h+var_40]
0x14003c20e  mov     [rsp+0F0h+var_A0], dil
0x14003c213  mov     [rsp+0F0h+var_A8], r15d
0x14003c218  mov     [rsp+0F0h+var_B0], rax
0x14003c21d  mov     rax, [rbp+57h+var_58]
0x14003c221  mov     [rsp+0F0h+var_B8], rax
0x14003c226  mov     rax, [rbp+57h+var_50]
0x14003c22a  mov     [rsp+0F0h+var_C0], rax
0x14003c22f  mov     rax, [rbp+57h+var_48]
0x14003c233  mov     [rsp+0F0h+var_C8], rax
0x14003c238  mov     eax, [rsi+24Ch]
0x14003c23e  mov     dword ptr [rsp+0F0h+var_D0], eax
0x14003c242  call    McTemplateK0jqssssduqtqqqqq_EtwWriteTransfer
0x14003c247  mov     rcx, [rbp+57h+var_28]
0x14003c24b  xor     rcx, rsp; StackCookie
0x14003c24e  call    __security_check_cookie
0x14003c253  lea     r11, [rsp+0F0h+var_20]
0x14003c25b  mov     rbx, [r11+40h]
0x14003c25f  mov     rsi, [r11+48h]
0x14003c263  mov     rsp, r11
0x14003c266  pop     r15
0x14003c268  pop     r14
0x14003c26a  pop     r12
0x14003c26c  pop     rdi
0x14003c26d  pop     rbp
0x14003c26e  retn
```
