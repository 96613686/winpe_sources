# ClasspZoneCommandProcessAsyncFailureEvent

- ea: `0x14003c3a4`
- end: `0x14003c483`
- name: `ClasspZoneCommandProcessAsyncFailureEvent`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140032f1c`

## callees

- `0x140016ae0`
- `0x14003c3a4`
- `0x14003d5e0`
- `0x14003e430`

## pseudocode

```c
_DWORD *__fastcall ClasspZoneCommandProcessAsyncFailureEvent(int a1, __int64 a2, char a3)
{
  __int64 v3; // rbx
  _DWORD *result; // rax
  int v7; // edx
  int v8; // ecx
  __int64 v9; // [rsp+50h] [rbp+7h] BYREF
  __int64 v10; // [rsp+58h] [rbp+Fh] BYREF
  __int64 v11; // [rsp+60h] [rbp+17h] BYREF
  __int64 v12; // [rsp+68h] [rbp+1Fh] BYREF
  __int128 *v13; // [rsp+70h] [rbp+27h] BYREF
  __int128 v14; // [rsp+78h] [rbp+2Fh] BYREF

  v3 = *(_QWORD *)(a2 + 64);
  v13 = &v14;
  result = 0;
  v12 = 0;
  v11 = 0;
  v10 = 0;
  v9 = 0;
  v14 = 0;
  if ( v3 )
  {
    result = ClasspGetDeviceIdData(v3, &v13, &v12, &v11, &v10, &v9);
    if ( (BYTE5(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 1) != 0 )
      return (_DWORD *)McTemplateK0jqssssq_EtwWriteTransfer(
                         v8,
                         v7,
                         a1,
                         (_DWORD)v13,
                         *(_DWORD *)(v3 + 588),
                         v12,
                         v11,
                         v10,
                         v9,
                         a3);
  }
  return result;
}

```

## disassembly

```asm
0x14003c3a4  mov     [rsp-8+arg_10], rbx
0x14003c3a9  push    rbp
0x14003c3aa  push    rsi
0x14003c3ab  push    rdi
0x14003c3ac  lea     rbp, [rsp-47h]
0x14003c3b1  sub     rsp, 90h
0x14003c3b8  mov     rax, cs:__security_cookie
0x14003c3bf  xor     rax, rsp
0x14003c3c2  mov     [rbp+57h+var_18], rax
0x14003c3c6  mov     rbx, [rdx+40h]
0x14003c3ca  lea     rax, [rbp+57h+var_28]
0x14003c3ce  mov     [rbp+57h+var_30], rax
0x14003c3d2  xorps   xmm0, xmm0
0x14003c3d5  xor     eax, eax
0x14003c3d7  mov     edi, r8d
0x14003c3da  mov     [rbp+57h+var_38], rax
0x14003c3de  mov     rsi, rcx
0x14003c3e1  mov     [rbp+57h+var_40], rax
0x14003c3e5  mov     [rbp+57h+var_48], rax
0x14003c3e9  mov     [rbp+57h+var_50], rax
0x14003c3ed  movups  [rbp+57h+var_28], xmm0
0x14003c3f1  test    rbx, rbx
0x14003c3f4  jz      short loc_14003C463
0x14003c3f6  lea     rax, [rbp+57h+var_50]
0x14003c3fa  mov     rcx, rbx
0x14003c3fd  mov     [rsp+0A0h+var_78], rax
0x14003c402  lea     r9, [rbp+57h+var_40]
0x14003c406  lea     rax, [rbp+57h+var_48]
0x14003c40a  lea     r8, [rbp+57h+var_38]
0x14003c40e  mov     [rsp+0A0h+var_80], rax
0x14003c413  lea     rdx, [rbp+57h+var_30]
0x14003c417  call    ClasspGetDeviceIdData
0x14003c41c  test    byte ptr cs:WPP_MAIN_CB.Queue+3Dh, 1
0x14003c423  jz      short loc_14003C463
0x14003c425  mov     rax, [rbp+57h+var_50]
0x14003c429  mov     r8, rsi
0x14003c42c  mov     r9, [rbp+57h+var_30]
0x14003c430  mov     [rsp+0A0h+var_58], edi
0x14003c434  mov     [rsp+0A0h+var_60], rax
0x14003c439  mov     rax, [rbp+57h+var_48]
0x14003c43d  mov     [rsp+0A0h+var_68], rax
0x14003c442  mov     rax, [rbp+57h+var_40]
0x14003c446  mov     [rsp+0A0h+var_70], rax
0x14003c44b  mov     rax, [rbp+57h+var_38]
0x14003c44f  mov     [rsp+0A0h+var_78], rax
0x14003c454  mov     eax, [rbx+24Ch]
0x14003c45a  mov     dword ptr [rsp+0A0h+var_80], eax
0x14003c45e  call    McTemplateK0jqssssq_EtwWriteTransfer
0x14003c463  mov     rcx, [rbp+57h+var_18]
0x14003c467  xor     rcx, rsp; StackCookie
0x14003c46a  call    __security_check_cookie
0x14003c46f  mov     rbx, [rsp+0A0h+arg_10]
0x14003c477  add     rsp, 90h
0x14003c47e  pop     rdi
0x14003c47f  pop     rsi
0x14003c480  pop     rbp
0x14003c481  retn
```
