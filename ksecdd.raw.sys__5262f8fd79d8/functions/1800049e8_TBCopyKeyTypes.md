# TBCopyKeyTypes

- ea: `0x1800049e8`
- end: `0x180004a8c`
- name: `TBCopyKeyTypes`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180023750`

## callees

- `0x1800049e8`
- `0x18001f008`
- `0x18001f058`

## pseudocode

```c
__int64 __fastcall TBCopyKeyTypes(int *a1, _QWORD *a2)
{
  int v3; // edx
  unsigned int v5; // edi
  _DWORD *v6; // r10
  _DWORD *v7; // r9
  __int64 v8; // rax
  _DWORD *v10; // [rsp+30h] [rbp+8h] BYREF
  __int64 v11; // [rsp+40h] [rbp+18h] BYREF

  v10 = 0;
  v3 = *a1;
  v11 = 0;
  if ( (unsigned int)TBAllocateBuffer(&v10, (unsigned int)(4 * v3 + 16)) )
  {
    v5 = 0;
    v6 = v10;
    v7 = v10;
    *v10 = *a1;
    *((_QWORD *)v7 + 1) = 0;
    if ( *v7 )
    {
      v8 = 0;
      for ( *((_QWORD *)v6 + 1) = v7 + 4; (unsigned int)v8 < *a1; v8 = (unsigned int)(v8 + 1) )
        *(_DWORD *)(*((_QWORD *)v6 + 1) + 4 * v8) = *(_DWORD *)(*((_QWORD *)a1 + 1) + 4 * v8);
    }
    *a2 = v7;
    v11 = 0;
  }
  else
  {
    v5 = -2146893056;
  }
  TBFreeBuffer(&v11);
  return v5;
}

```

## disassembly

```asm
0x1800049e8  mov     rax, rsp
0x1800049eb  mov     [rax+10h], rbx
0x1800049ef  mov     [rax+20h], rsi
0x1800049f3  push    rdi
0x1800049f4  sub     rsp, 20h
0x1800049f8  mov     rsi, rdx
0x1800049fb  mov     qword ptr [rax+8], 0
0x180004a03  mov     edx, [rcx]
0x180004a05  mov     rbx, rcx
0x180004a08  lea     rcx, [rax+8]
0x180004a0c  mov     qword ptr [rax+18h], 0
0x180004a14  lea     edx, ds:10h[rdx*4]
0x180004a1b  call    TBAllocateBuffer
0x180004a20  test    eax, eax
0x180004a22  jnz     short loc_180004A2B
0x180004a24  mov     edi, 80090300h
0x180004a29  jmp     short loc_180004A6F
0x180004a2b  mov     rcx, [rsp+28h+arg_0]
0x180004a30  xor     edi, edi
0x180004a32  mov     eax, [rbx]
0x180004a34  mov     r10, rcx
0x180004a37  mov     r9, rcx
0x180004a3a  mov     [rcx], eax
0x180004a3c  mov     [rcx+8], rdi
0x180004a40  add     rcx, 10h
0x180004a44  cmp     [r10], edi
0x180004a47  jz      short loc_180004A67
0x180004a49  xor     eax, eax
0x180004a4b  mov     [r10+8], rcx
0x180004a4f  cmp     [rbx], eax
0x180004a51  jbe     short loc_180004A67
0x180004a53  mov     rcx, [rbx+8]
0x180004a57  mov     rdx, [r10+8]
0x180004a5b  mov     ecx, [rcx+rax*4]
0x180004a5e  mov     [rdx+rax*4], ecx
0x180004a61  inc     eax
0x180004a63  cmp     eax, [rbx]
0x180004a65  jb      short loc_180004A53
0x180004a67  mov     [rsi], r9
0x180004a6a  mov     [rsp+28h+arg_10], rdi
0x180004a6f  lea     rcx, [rsp+28h+arg_10]
0x180004a74  call    TBFreeBuffer
0x180004a79  mov     rbx, [rsp+28h+arg_8]
0x180004a7e  mov     eax, edi
0x180004a80  mov     rsi, [rsp+28h+arg_18]
0x180004a85  add     rsp, 20h
0x180004a89  pop     rdi
0x180004a8a  retn
```
