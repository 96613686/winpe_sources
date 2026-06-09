# ClasspWriteNonScsiSrbErrorResultEvent

- ea: `0x14003bf7c`
- end: `0x14003c0cd`
- name: `ClasspWriteNonScsiSrbErrorResultEvent`
- size: `337`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140005560`
- `0x1400073d4`

## callees

- `0x140016ae0`
- `0x140016f70`
- `0x14003bf7c`
- `0x14003cd58`
- `0x14003e430`

## pseudocode

```c
__int64 __fastcall ClasspWriteNonScsiSrbErrorResultEvent(int a1, __int64 a2, unsigned int a3, __int64 a4, char a5)
{
  __int64 v5; // rdi
  __int64 result; // rax
  __int64 v8; // r15
  char v9; // r14
  unsigned int v10; // ebx
  char v11; // si
  __int64 v12; // r10
  int v13; // r15d
  int v14; // edx
  int v15; // ecx
  __int64 v16; // [rsp+70h] [rbp-11h] BYREF
  __int64 v17; // [rsp+78h] [rbp-9h] BYREF
  __int64 v18; // [rsp+80h] [rbp-1h] BYREF
  __int64 v19; // [rsp+88h] [rbp+7h] BYREF
  __int128 *v20; // [rsp+90h] [rbp+Fh] BYREF
  __int128 v21; // [rsp+98h] [rbp+17h] BYREF

  v5 = *(_QWORD *)(a2 + 64);
  v20 = &v21;
  result = *(unsigned __int8 *)(a4 + 2);
  v19 = 0;
  v18 = 0;
  v17 = 0;
  v8 = 24;
  v16 = 0;
  if ( (_BYTE)result != 40 )
    v8 = 12;
  v9 = a3;
  v21 = 0;
  if ( (_BYTE)result == 40 )
    v10 = *(_DWORD *)(a4 + 20);
  else
    v10 = result;
  if ( v5 )
  {
    v11 = *(_BYTE *)(a4 + 3);
    LOBYTE(a2) = v11;
    result = ClasspIsErrorStatusNoisy(a3, a2, 5, v10);
    if ( !(_BYTE)result )
    {
      v13 = *(_DWORD *)(v8 + v12);
      result = (__int64)ClasspGetDeviceIdData(v5, &v20, &v19, &v18, &v17, &v16);
      if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 4) != 0 )
        return McTemplateK0jqssssduddu_EtwWriteTransfer(
                 v15,
                 v14,
                 a1,
                 (_DWORD)v20,
                 *(_DWORD *)(v5 + 588),
                 v19,
                 v18,
                 v17,
                 v16,
                 v9,
                 v11,
                 v10,
                 v13,
                 a5);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003bf7c  mov     [rsp-8+arg_10], rbx
0x14003bf81  mov     [rsp-8+arg_18], rsi
0x14003bf86  push    rbp
0x14003bf87  push    rdi
0x14003bf88  push    r12
0x14003bf8a  push    r14
0x14003bf8c  push    r15
0x14003bf8e  lea     rbp, [rsp-2Fh]
0x14003bf93  sub     rsp, 0B0h
0x14003bf9a  mov     rax, cs:__security_cookie
0x14003bfa1  xor     rax, rsp
0x14003bfa4  mov     [rbp+4Fh+var_28], rax
0x14003bfa8  mov     rdi, [rdx+40h]
0x14003bfac  lea     rax, [rbp+4Fh+var_38]
0x14003bfb0  xor     r11d, r11d
0x14003bfb3  mov     [rbp+4Fh+var_40], rax
0x14003bfb7  movzx   eax, byte ptr [r9+2]
0x14003bfbc  mov     r12, rcx
0x14003bfbf  cmp     al, 28h ; '('
0x14003bfc1  mov     [rbp+4Fh+var_48], r11
0x14003bfc5  xorps   xmm0, xmm0
0x14003bfc8  mov     [rbp+4Fh+var_50], r11
0x14003bfcc  lea     ecx, [r11+0Ch]
0x14003bfd0  mov     [rbp+4Fh+var_58], r11
0x14003bfd4  lea     r15d, [r11+18h]
0x14003bfd8  mov     [rbp+4Fh+var_60], r11
0x14003bfdc  cmovnz  r15d, ecx
0x14003bfe0  mov     r10, r9
0x14003bfe3  mov     r14d, r8d
0x14003bfe6  movups  [rbp+4Fh+var_38], xmm0
0x14003bfea  jnz     short loc_14003BFF2
0x14003bfec  mov     ebx, [r9+14h]
0x14003bff0  jmp     short loc_14003BFF4
0x14003bff2  mov     ebx, eax
0x14003bff4  test    rdi, rdi
0x14003bff7  jz      loc_14003C0A4
0x14003bffd  mov     sil, [r9+3]
0x14003c001  mov     r8d, 5
0x14003c007  mov     dl, sil
0x14003c00a  mov     r9d, ebx
0x14003c00d  mov     ecx, r14d
0x14003c010  call    ClasspIsErrorStatusNoisy
0x14003c015  test    al, al
0x14003c017  jnz     loc_14003C0A4
0x14003c01d  mov     r15d, [r15+r10]
0x14003c021  lea     rax, [rbp+4Fh+var_60]
0x14003c025  mov     [rsp+0D0h+var_A8], rax
0x14003c02a  lea     r9, [rbp+4Fh+var_50]
0x14003c02e  lea     rax, [rbp+4Fh+var_58]
0x14003c032  mov     rcx, rdi
0x14003c035  lea     r8, [rbp+4Fh+var_48]
0x14003c039  mov     [rsp+0D0h+var_B0], rax
0x14003c03e  lea     rdx, [rbp+4Fh+var_40]
0x14003c042  call    ClasspGetDeviceIdData
0x14003c047  test    byte ptr cs:WPP_MAIN_CB.Queue+3Ch, 4
0x14003c04e  jz      short loc_14003C0A4
0x14003c050  mov     al, [rbp+4Fh+arg_20]
0x14003c053  mov     r8, r12
0x14003c056  mov     r9, [rbp+4Fh+var_40]
0x14003c05a  mov     [rsp+0D0h+var_68], al
0x14003c05e  mov     rax, [rbp+4Fh+var_60]
0x14003c062  mov     [rsp+0D0h+var_70], r15d
0x14003c067  mov     [rsp+0D0h+var_78], ebx
0x14003c06b  mov     [rsp+0D0h+var_80], sil
0x14003c070  mov     [rsp+0D0h+var_88], r14d
0x14003c075  mov     [rsp+0D0h+var_90], rax
0x14003c07a  mov     rax, [rbp+4Fh+var_58]
0x14003c07e  mov     [rsp+0D0h+var_98], rax
0x14003c083  mov     rax, [rbp+4Fh+var_50]
0x14003c087  mov     [rsp+0D0h+var_A0], rax
0x14003c08c  mov     rax, [rbp+4Fh+var_48]
0x14003c090  mov     [rsp+0D0h+var_A8], rax
0x14003c095  mov     eax, [rdi+24Ch]
0x14003c09b  mov     dword ptr [rsp+0D0h+var_B0], eax
0x14003c09f  call    McTemplateK0jqssssduddu_EtwWriteTransfer
0x14003c0a4  mov     rcx, [rbp+4Fh+var_28]
0x14003c0a8  xor     rcx, rsp; StackCookie
0x14003c0ab  call    __security_check_cookie
0x14003c0b0  lea     r11, [rsp+0D0h+var_20]
0x14003c0b8  mov     rbx, [r11+40h]
0x14003c0bc  mov     rsi, [r11+48h]
0x14003c0c0  mov     rsp, r11
0x14003c0c3  pop     r15
0x14003c0c5  pop     r14
0x14003c0c7  pop     r12
0x14003c0c9  pop     rdi
0x14003c0ca  pop     rbp
0x14003c0cb  retn
```
