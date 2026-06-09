# WaitForWerSvc

- ea: `0x18004f020`
- end: `0x18004f0c9`
- name: `WaitForWerSvc`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004ec14`

## callees

- `0x18004f020`
- `0x18015eb60`
- `0x18015ecc0`
- `0x18015f2e0`

## string_xrefs

- `0x18004f02d`: `\KernelObjects\SystemErrorPortReady`

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
0x18004f020  mov     [rsp-8+arg_0], rbx
0x18004f025  push    rbp
0x18004f026  mov     rbp, rsp
0x18004f029  sub     rsp, 60h
0x18004f02d  lea     rax, aKernelobjectsS; "\\KernelObjects\\SystemErrorPortReady"
0x18004f034  movsxd  rbx, ecx
0x18004f037  mov     [rbp+var_38], rax
0x18004f03b  lea     r8, [rbp+var_30]
0x18004f03f  xor     eax, eax
0x18004f041  mov     [rbp+var_40], 480046h
0x18004f049  mov     [rbp+var_18], rax
0x18004f04d  lea     rcx, [rbp+Handle]
0x18004f051  mov     [rbp+Handle], rax
0x18004f055  xorps   xmm0, xmm0
0x18004f058  mov     [rbp+arg_10], rax
0x18004f05c  mov     edx, 100001h
0x18004f061  mov     [rbp+var_28], rax
0x18004f065  lea     rax, [rbp+var_40]
0x18004f069  mov     [rbp+var_20], rax
0x18004f06d  mov     [rbp+var_30], 30h ; '0'
0x18004f075  movdqu  [rbp+var_10], xmm0
0x18004f07a  call    NtOpenEvent
0x18004f07f  test    eax, eax
0x18004f081  js      short loc_18004F0BD
0x18004f083  cmp     ebx, 0FFFFFFFFh
0x18004f086  jnz     short loc_18004F08C
0x18004f088  mov     dl, 1
0x18004f08a  jmp     short loc_18004F099
0x18004f08c  xor     dl, dl
0x18004f08e  imul    rcx, rbx, 0FFFFFFFFFFFFD8F0h
0x18004f095  mov     [rbp+arg_10], rcx
0x18004f099  mov     rcx, [rbp+Handle]; Handle
0x18004f09d  lea     r8, [rbp+arg_10]
0x18004f0a1  xor     eax, eax
0x18004f0a3  test    dl, dl
0x18004f0a5  cmovnz  r8, rax; Timeout
0x18004f0a9  xor     edx, edx; Alertable
0x18004f0ab  call    NtWaitForSingleObject
0x18004f0b0  mov     rcx, [rbp+Handle]; Handle
0x18004f0b4  mov     ebx, eax
0x18004f0b6  call    NtClose
0x18004f0bb  mov     eax, ebx
0x18004f0bd  mov     rbx, [rsp+60h+arg_0]
0x18004f0c2  add     rsp, 60h
0x18004f0c6  pop     rbp
0x18004f0c7  retn
```
