# sub_1801D0BAC

- ea: `0x1801d0bac`
- end: `0x1801d0d32`
- name: `sub_1801D0BAC`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1801d08f0`

## callees

- `0x1801adc90`
- `0x1801ae380`
- `0x1801ce3c8`
- `0x1801d0bac`
- `0x1801d1de8`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1801d0c7b`
- `KERNEL32!ReadFile` at `0x1801d0c7b`

## pseudocode

```c
__int64 __fastcall sub_1801D0BAC(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // eax
  __int64 v7; // rdi
  unsigned int v8; // r14d
  __int64 v10; // kr00_8
  __int64 v11; // rbx
  __int64 v12; // rsi
  __int64 v13; // r13
  __int64 v14; // rcx
  unsigned __int8 *v15; // rdx
  unsigned __int8 *v16; // rcx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-1058h] BYREF
  _BYTE Buffer[4096]; // [rsp+40h] [rbp-1048h] BYREF

  v6 = sub_1801CE3C8();
  v7 = 0;
  v8 = v6;
  if ( !*(_DWORD *)(a1 + 16) )
    return a2;
  v10 = *(_QWORD *)a1 - *(_QWORD *)(a1 + 8);
  v11 = (__int64)(int)v6 >> 6;
  v12 = v10 / 2;
  v13 = sub_1801D1DE8(v6, *(_QWORD *)(qword_1805FB920[v11] + 72LL * (v6 & 0x3F) + 48), 0, a3);
  v14 = qword_1805FB920[v11];
  if ( v13 != *(_QWORD *)(v14 + 72LL * (v8 & 0x3F) + 48) )
    return -1;
  NumberOfBytesRead = 0;
  if ( !ReadFile(*(HANDLE *)(v14 + 72LL * (v8 & 0x3F) + 40), Buffer, 0x1000u, &NumberOfBytesRead, 0)
    || sub_1801D1DE8(v8, a2, 0, a3) < 0
    || v12 > NumberOfBytesRead )
  {
    return -1;
  }
  v15 = &Buffer[NumberOfBytesRead];
  v16 = Buffer;
  if ( v12 )
  {
    do
    {
      if ( v16 >= v15 )
        break;
      if ( *v16 == 13 )
      {
        if ( v16 < v15 - 1 && v16[1] == 10 )
          ++v16;
      }
      else
      {
        v16 += *((char *)qword_1805C5300 + *v16);
      }
      ++v7;
      ++v16;
    }
    while ( v7 != v12 );
  }
  return v16 - Buffer + v13;
}

```

## disassembly

```asm
0x1801d0bac  mov     [rsp+arg_0], rbx
0x1801d0bb1  push    rbp
0x1801d0bb2  push    rsi
0x1801d0bb3  push    rdi
0x1801d0bb4  push    r12
0x1801d0bb6  push    r13
0x1801d0bb8  push    r14
0x1801d0bba  push    r15
0x1801d0bbc  mov     eax, 1050h
0x1801d0bc1  call    __alloca_probe
0x1801d0bc6  sub     rsp, rax
0x1801d0bc9  mov     rax, cs:__security_cookie
0x1801d0bd0  xor     rax, rsp
0x1801d0bd3  mov     [rsp+1088h+var_48], rax
0x1801d0bdb  mov     r15, r8
0x1801d0bde  mov     rbp, rdx
0x1801d0be1  mov     rbx, rcx
0x1801d0be4  call    sub_1801CE3C8
0x1801d0be9  xor     edi, edi
0x1801d0beb  movsxd  r14, eax
0x1801d0bee  cmp     [rbx+10h], edi
0x1801d0bf1  jnz     short loc_1801D0BFB
0x1801d0bf3  mov     rax, rbp
0x1801d0bf6  jmp     loc_1801D0D07
0x1801d0bfb  mov     rax, [rbx]
0x1801d0bfe  mov     rcx, r14
0x1801d0c01  sub     rax, [rbx+8]
0x1801d0c05  and     ecx, 3Fh
0x1801d0c08  cqo
0x1801d0c0a  mov     rbx, r14
0x1801d0c0d  sub     rax, rdx
0x1801d0c10  sar     rbx, 6
0x1801d0c14  sar     rax, 1
0x1801d0c17  mov     r9, r15
0x1801d0c1a  lea     r12, [rcx+rcx*8]
0x1801d0c1e  mov     rsi, rax
0x1801d0c21  lea     rax, cs:180000000h
0x1801d0c28  xor     r8d, r8d
0x1801d0c2b  mov     rdx, rva qword_1805FB920[rax+rbx*8]
0x1801d0c33  mov     ecx, r14d
0x1801d0c36  mov     rdx, [rdx+r12*8+30h]
0x1801d0c3b  call    sub_1801D1DE8
0x1801d0c40  mov     r13, rax
0x1801d0c43  lea     rax, cs:180000000h
0x1801d0c4a  mov     rcx, rva qword_1805FB920[rax+rbx*8]
0x1801d0c52  cmp     r13, [rcx+r12*8+30h]
0x1801d0c57  jnz     loc_1801D0D03
0x1801d0c5d  mov     [rsp+1088h+NumberOfBytesRead], edi
0x1801d0c61  lea     r9, [rsp+1088h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1801d0c66  mov     rcx, [rcx+r12*8+28h]; hFile
0x1801d0c6b  lea     rdx, [rsp+1088h+Buffer]; lpBuffer
0x1801d0c70  mov     r8d, 1000h; nNumberOfBytesToRead
0x1801d0c76  mov     [rsp+1088h+lpOverlapped], rdi; lpOverlapped
0x1801d0c7b  call    cs:ReadFile
0x1801d0c81  test    eax, eax
0x1801d0c83  jz      short loc_1801D0D03
0x1801d0c85  mov     r9, r15
0x1801d0c88  xor     r8d, r8d
0x1801d0c8b  mov     rdx, rbp
0x1801d0c8e  mov     ecx, r14d
0x1801d0c91  call    sub_1801D1DE8
0x1801d0c96  test    rax, rax
0x1801d0c99  js      short loc_1801D0D03
0x1801d0c9b  mov     eax, [rsp+1088h+NumberOfBytesRead]
0x1801d0c9f  cmp     rsi, rax
0x1801d0ca2  jg      short loc_1801D0D03
0x1801d0ca4  lea     rdx, [rsp+1088h+Buffer]
0x1801d0ca9  add     rdx, rax
0x1801d0cac  lea     rcx, [rsp+1088h+Buffer]
0x1801d0cb1  test    rsi, rsi
0x1801d0cb4  jz      short loc_1801D0CF5
0x1801d0cb6  lea     r8, cs:180000000h
0x1801d0cbd  cmp     rcx, rdx
0x1801d0cc0  jnb     short loc_1801D0CF5
0x1801d0cc2  cmp     byte ptr [rcx], 0Dh
0x1801d0cc5  jnz     short loc_1801D0CDB
0x1801d0cc7  lea     rax, [rdx-1]
0x1801d0ccb  cmp     rcx, rax
0x1801d0cce  jnb     short loc_1801D0CEA
0x1801d0cd0  cmp     byte ptr [rcx+1], 0Ah
0x1801d0cd4  jnz     short loc_1801D0CEA
0x1801d0cd6  inc     rcx
0x1801d0cd9  jmp     short loc_1801D0CEA
0x1801d0cdb  movzx   eax, byte ptr [rcx]
0x1801d0cde  movsx   rax, byte ptr [rax+r8+5C5300h]
0x1801d0ce7  add     rcx, rax
0x1801d0cea  inc     rdi
0x1801d0ced  inc     rcx
0x1801d0cf0  cmp     rdi, rsi
0x1801d0cf3  jnz     short loc_1801D0CBD
0x1801d0cf5  lea     rax, [rsp+1088h+Buffer]
0x1801d0cfa  sub     rcx, rax
0x1801d0cfd  lea     rax, [rcx+r13]
0x1801d0d01  jmp     short loc_1801D0D07
0x1801d0d03  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801d0d07  mov     rcx, [rsp+1088h+var_48]
0x1801d0d0f  xor     rcx, rsp; StackCookie
0x1801d0d12  call    __security_check_cookie
0x1801d0d17  mov     rbx, [rsp+1088h+arg_0]
0x1801d0d1f  add     rsp, 1050h
0x1801d0d26  pop     r15
0x1801d0d28  pop     r14
0x1801d0d2a  pop     r13
0x1801d0d2c  pop     r12
0x1801d0d2e  pop     rdi
0x1801d0d2f  pop     rsi
0x1801d0d30  pop     rbp
0x1801d0d31  retn
```
