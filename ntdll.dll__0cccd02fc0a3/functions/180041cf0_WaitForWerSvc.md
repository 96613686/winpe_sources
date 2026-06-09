# WaitForWerSvc

- ea: `0x180041cf0`
- end: `0x180041d99`
- name: `WaitForWerSvc`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800418e4`

## callees

- `0x180041cf0`
- `0x18015e350`
- `0x18015e4b0`
- `0x18015ead0`

## string_xrefs

- `0x180041cfd`: `\KernelObjects\SystemErrorPortReady`

## pseudocode

```c
__int64 __fastcall WaitForWerSvc(int a1)
{
  __int64 v1; // rbx
  __int64 result; // rax
  char v3; // dl
  LARGE_INTEGER *v4; // r8
  unsigned int v5; // ebx
  _QWORD v6[2]; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v7[4]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v8; // [rsp+50h] [rbp-10h]
  HANDLE Handle; // [rsp+78h] [rbp+18h] BYREF
  __int64 v10; // [rsp+80h] [rbp+20h] BYREF

  v1 = a1;
  v6[1] = L"\\KernelObjects\\SystemErrorPortReady";
  v6[0] = 4718662;
  v7[3] = 0;
  Handle = 0;
  v10 = 0;
  v7[1] = 0;
  v7[2] = v6;
  v7[0] = 48;
  v8 = 0;
  result = NtOpenEvent(&Handle, 1048577, v7);
  if ( (int)result >= 0 )
  {
    if ( (_DWORD)v1 == -1 )
    {
      v3 = 1;
    }
    else
    {
      v3 = 0;
      v10 = -10000 * v1;
    }
    v4 = (LARGE_INTEGER *)&v10;
    if ( v3 )
      v4 = 0;
    v5 = NtWaitForSingleObject(Handle, 0, v4);
    NtClose(Handle);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180041cf0  mov     [rsp-8+arg_0], rbx
0x180041cf5  push    rbp
0x180041cf6  mov     rbp, rsp
0x180041cf9  sub     rsp, 60h
0x180041cfd  lea     rax, aKernelobjectsS; "\\KernelObjects\\SystemErrorPortReady"
0x180041d04  movsxd  rbx, ecx
0x180041d07  mov     [rbp+var_38], rax
0x180041d0b  lea     r8, [rbp+var_30]
0x180041d0f  xor     eax, eax
0x180041d11  mov     [rbp+var_40], 480046h
0x180041d19  mov     [rbp+var_18], rax
0x180041d1d  lea     rcx, [rbp+Handle]
0x180041d21  mov     [rbp+Handle], rax
0x180041d25  xorps   xmm0, xmm0
0x180041d28  mov     [rbp+arg_10], rax
0x180041d2c  mov     edx, 100001h
0x180041d31  mov     [rbp+var_28], rax
0x180041d35  lea     rax, [rbp+var_40]
0x180041d39  mov     [rbp+var_20], rax
0x180041d3d  mov     [rbp+var_30], 30h ; '0'
0x180041d45  movdqu  [rbp+var_10], xmm0
0x180041d4a  call    NtOpenEvent
0x180041d4f  test    eax, eax
0x180041d51  js      short loc_180041D8D
0x180041d53  cmp     ebx, 0FFFFFFFFh
0x180041d56  jnz     short loc_180041D5C
0x180041d58  mov     dl, 1
0x180041d5a  jmp     short loc_180041D69
0x180041d5c  xor     dl, dl
0x180041d5e  imul    rcx, rbx, 0FFFFFFFFFFFFD8F0h
0x180041d65  mov     [rbp+arg_10], rcx
0x180041d69  mov     rcx, [rbp+Handle]; Handle
0x180041d6d  lea     r8, [rbp+arg_10]
0x180041d71  xor     eax, eax
0x180041d73  test    dl, dl
0x180041d75  cmovnz  r8, rax; Timeout
0x180041d79  xor     edx, edx; Alertable
0x180041d7b  call    NtWaitForSingleObject
0x180041d80  mov     rcx, [rbp+Handle]; Handle
0x180041d84  mov     ebx, eax
0x180041d86  call    NtClose
0x180041d8b  mov     eax, ebx
0x180041d8d  mov     rbx, [rsp+60h+arg_0]
0x180041d92  add     rsp, 60h
0x180041d96  pop     rbp
0x180041d97  retn
```
