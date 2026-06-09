# ClasspWritePowerFailureEvent

- ea: `0x1400181ec`
- end: `0x140018337`
- name: `ClasspWritePowerFailureEvent`
- size: `331`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140018180`
- `0x140018f70`
- `0x140029040`

## callees

- `0x140016ae0`
- `0x140016f70`
- `0x1400181ec`
- `0x14003d06c`
- `0x14003e430`

## pseudocode

```c
__int128 *__fastcall ClasspWritePowerFailureEvent(int a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int128 *result; // rax
  bool v5; // zf
  __int64 v7; // rdi
  unsigned int v8; // r14d
  unsigned __int8 v9; // si
  int v10; // edx
  int v11; // ecx
  __int64 v12; // [rsp+90h] [rbp-9h] BYREF
  __int64 v13; // [rsp+98h] [rbp-1h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v15; // [rsp+A8h] [rbp+Fh] BYREF
  __int128 *v16; // [rsp+B0h] [rbp+17h] BYREF
  __int128 v17; // [rsp+B8h] [rbp+1Fh] BYREF

  v3 = *(_QWORD *)(a2 + 64);
  result = &v17;
  v16 = &v17;
  v15 = 0;
  v17 = 0;
  v5 = (*(_BYTE *)(v3 + 104) & 1) == 0;
  v14 = 0;
  v13 = 0;
  v12 = 0;
  if ( !v5 )
  {
    v7 = *(_QWORD *)(a3 + 184);
    v8 = *(_DWORD *)(a3 + 48);
    v9 = *(_BYTE *)(v7 + 1);
    result = (__int128 *)ClasspIsErrorStatusNoisy(v8, 0, 2, v9);
    if ( !(_BYTE)result )
    {
      result = (__int128 *)ClasspGetDeviceIdData(v3, &v16, &v15, &v14, &v13, &v12);
      if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x10) != 0 )
        return (__int128 *)McTemplateK0jqssssduqqqqqq_EtwWriteTransfer(
                             v11,
                             v10,
                             a1,
                             (_DWORD)v16,
                             *(_DWORD *)(v3 + 588),
                             v15,
                             v14,
                             v13,
                             v12,
                             v8,
                             v9,
                             *(_DWORD *)(v7 + 8),
                             *(_DWORD *)(v7 + 16),
                             *(_DWORD *)(v7 + 24),
                             *(_DWORD *)(v7 + 32),
                             *(_DWORD *)(v3 + 536),
                             *(_DWORD *)(v3 + 1008));
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400181ec  mov     [rsp-8+arg_10], rbx
0x1400181f1  push    rbp
0x1400181f2  push    rsi
0x1400181f3  push    rdi
0x1400181f4  push    r14
0x1400181f6  push    r15
0x1400181f8  lea     rbp, [rsp-37h]
0x1400181fd  sub     rsp, 0D0h
0x140018204  mov     rax, cs:__security_cookie
0x14001820b  xor     rax, rsp
0x14001820e  mov     [rbp+57h+var_28], rax
0x140018212  mov     rbx, [rdx+40h]
0x140018216  lea     rax, [rbp+57h+var_38]
0x14001821a  xor     r10d, r10d
0x14001821d  mov     [rbp+57h+var_40], rax
0x140018221  xorps   xmm0, xmm0
0x140018224  mov     [rbp+57h+var_48], r10
0x140018228  movups  [rbp+57h+var_38], xmm0
0x14001822c  test    byte ptr [rbx+68h], 1
0x140018230  mov     r15, rcx
0x140018233  mov     [rbp+57h+var_50], r10
0x140018237  mov     [rbp+57h+var_58], r10
0x14001823b  mov     [rbp+57h+var_60], r10
0x14001823f  jz      loc_140018313
0x140018245  mov     rdi, [r8+0B8h]
0x14001824c  xor     edx, edx
0x14001824e  mov     r14d, [r8+30h]
0x140018252  lea     r8d, [r10+2]
0x140018256  mov     ecx, r14d
0x140018259  movzx   esi, byte ptr [rdi+1]
0x14001825d  mov     r9d, esi
0x140018260  call    ClasspIsErrorStatusNoisy
0x140018265  test    al, al
0x140018267  jnz     loc_140018313
0x14001826d  lea     rax, [rbp+57h+var_60]
0x140018271  mov     rcx, rbx
0x140018274  mov     [rsp+0F0h+var_C8], rax
0x140018279  lea     r9, [rbp+57h+var_50]
0x14001827d  lea     rax, [rbp+57h+var_58]
0x140018281  lea     r8, [rbp+57h+var_48]
0x140018285  mov     [rsp+0F0h+var_D0], rax
0x14001828a  lea     rdx, [rbp+57h+var_40]
0x14001828e  call    ClasspGetDeviceIdData
0x140018293  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ch, 10h
0x14001829a  jz      short loc_140018313
0x14001829c  mov     eax, [rbx+3F0h]
0x1400182a2  mov     r8, r15
0x1400182a5  mov     r9, [rbp+57h+var_40]
0x1400182a9  mov     [rsp+0F0h+var_70], eax
0x1400182b0  mov     eax, [rbx+218h]
0x1400182b6  mov     [rsp+0F0h+var_78], eax
0x1400182ba  mov     eax, [rdi+20h]
0x1400182bd  mov     [rsp+0F0h+var_80], eax
0x1400182c1  mov     eax, [rdi+18h]
0x1400182c4  mov     [rsp+0F0h+var_88], eax
0x1400182c8  mov     eax, [rdi+10h]
0x1400182cb  mov     [rsp+0F0h+var_90], eax
0x1400182cf  mov     eax, [rdi+8]
0x1400182d2  mov     [rsp+0F0h+var_98], eax
0x1400182d6  mov     rax, [rbp+57h+var_60]
0x1400182da  mov     [rsp+0F0h+var_A0], sil
0x1400182df  mov     [rsp+0F0h+var_A8], r14d
0x1400182e4  mov     [rsp+0F0h+var_B0], rax
0x1400182e9  mov     rax, [rbp+57h+var_58]
0x1400182ed  mov     [rsp+0F0h+var_B8], rax
0x1400182f2  mov     rax, [rbp+57h+var_50]
0x1400182f6  mov     [rsp+0F0h+var_C0], rax
0x1400182fb  mov     rax, [rbp+57h+var_48]
0x1400182ff  mov     [rsp+0F0h+var_C8], rax
0x140018304  mov     eax, [rbx+24Ch]
0x14001830a  mov     dword ptr [rsp+0F0h+var_D0], eax
0x14001830e  call    McTemplateK0jqssssduqqqqqq_EtwWriteTransfer
0x140018313  mov     rcx, [rbp+57h+var_28]
0x140018317  xor     rcx, rsp; StackCookie
0x14001831a  call    __security_check_cookie
0x14001831f  mov     rbx, [rsp+0F0h+arg_10]
0x140018327  add     rsp, 0D0h
0x14001832e  pop     r15
0x140018330  pop     r14
0x140018332  pop     rdi
0x140018333  pop     rsi
0x140018334  pop     rbp
0x140018335  retn
```
