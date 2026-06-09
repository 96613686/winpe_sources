# DevAuthParseCert

- ea: `0x180002ef4`
- end: `0x1800030ab`
- name: `DevAuthParseCert`
- size: `439`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800020e4`

## callees

- `0x180002ef4`
- `0x1800030b4`
- `0x1800031a0`
- `0x18000325c`
- `0x180003904`
- `0x1800067e0`
- `0x1800068a0`

## pseudocode

```c
__int64 __fastcall DevAuthParseCert(__int64 a1, unsigned int a2, _QWORD *a3, _DWORD *a4, _DWORD *a5)
{
  unsigned int v5; // ebp
  bool v6; // zf
  _DWORD *v8; // r15
  unsigned int v11; // edi
  __int128 v12; // xmm0
  __int64 v13; // rdx
  int v14; // eax
  size_t v15; // rsi
  int v16; // edi
  _DWORD *v17; // rbx
  _BYTE v20[32]; // [rsp+30h] [rbp-148h] BYREF
  char v21; // [rsp+50h] [rbp-128h] BYREF
  char v22[16]; // [rsp+60h] [rbp-118h] BYREF
  char v23[48]; // [rsp+70h] [rbp-108h] BYREF
  size_t Size; // [rsp+A0h] [rbp-D8h]
  void *Buf1; // [rsp+A8h] [rbp-D0h]
  __int128 v26; // [rsp+D0h] [rbp-A8h]
  __int128 v27[4]; // [rsp+E0h] [rbp-98h] BYREF

  v5 = 0;
  v6 = dword_18000C640 == 1;
  v8 = a4;
  *a5 = -1;
  if ( v6 )
  {
LABEL_6:
    if ( (unsigned int)MinAsn1ParseCertificate(a1, a2, v20) == a2 && (unsigned int)VerifyAlgorithm(v22) )
    {
      v15 = (unsigned int)Size;
      v16 = 0;
      while ( 1 )
      {
        v17 = (_DWORD *)&g_ValidCAs + 10 * v16;
        if ( (_DWORD)v15 == *v17 && !memcmp(Buf1, *((const void **)&g_ValidCAs + 5 * v16 + 1), v15) )
          break;
        if ( (unsigned int)++v16 >= 5 )
          return v5;
      }
      if ( v17
        && VerifySignature((int)&v21, (__int64)v23, (__int64)(v17 + 4))
        && (unsigned int)ParsePublicKey((__int64)v27, a3, v8) )
      {
        v5 = 1;
        *a5 = v17[8];
      }
    }
  }
  else
  {
    v11 = 0;
    while ( (unsigned int)MinAsn1ParseCertificate(
                            *(&g_CA_Certs + 2 * (int)v11),
                            (unsigned int)dword_180009008[4 * v11],
                            v20) == dword_180009008[4 * v11] )
    {
      v12 = v26;
      v13 = 5LL * (int)v11;
      v14 = dword_18000900C[4 * v11++];
      dword_18000C860[2 * v13] = v14;
      *(__int128 *)((char *)&g_ValidCAs + 8 * v13) = v12;
      *(__int128 *)((char *)&xmmword_18000C850 + 8 * v13) = v27[0];
      if ( v11 >= 5 )
      {
        v8 = a4;
        dword_18000C640 = 1;
        goto LABEL_6;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180002ef4  push    rbx
0x180002ef6  push    rbp
0x180002ef7  push    rsi
0x180002ef8  push    rdi
0x180002ef9  push    r12
0x180002efb  push    r13
0x180002efd  push    r14
0x180002eff  push    r15
0x180002f01  sub     rsp, 138h
0x180002f08  mov     rax, cs:__security_cookie
0x180002f0f  xor     rax, rsp
0x180002f12  mov     [rsp+178h+var_58], rax
0x180002f1a  mov     r14, [rsp+178h+arg_20]
0x180002f22  xor     ebp, ebp
0x180002f24  cmp     cs:dword_18000C640, 1
0x180002f2b  mov     r12, rcx
0x180002f2e  mov     r15, r9
0x180002f31  mov     [rsp+178h+var_158], r9
0x180002f36  mov     r13, r8
0x180002f39  lea     rcx, cs:180000000h
0x180002f40  mov     dword ptr [r14], 0FFFFFFFFh
0x180002f47  mov     esi, edx
0x180002f49  jz      loc_180002FD1
0x180002f4f  xor     edi, edi
0x180002f51  movsxd  r15, edi
0x180002f54  lea     r8, [rsp+178h+var_148]
0x180002f59  mov     rbx, r15
0x180002f5c  add     rbx, rbx
0x180002f5f  mov     edx, ds:rva dword_180009008[rcx+rbx*8]
0x180002f66  mov     rcx, ds:rva g_CA_Certs[rcx+rbx*8]
0x180002f6e  call    MinAsn1ParseCertificate
0x180002f73  lea     rcx, cs:180000000h
0x180002f7a  cmp     eax, ds:rva dword_180009008[rcx+rbx*8]
0x180002f81  jnz     loc_180003084
0x180002f87  movaps  xmm0, [rsp+178h+var_A8]
0x180002f8f  lea     rdx, [r15+r15*4]
0x180002f93  mov     eax, ds:rva dword_18000900C[rcx+rbx*8]
0x180002f9a  inc     edi
0x180002f9c  mov     rva dword_18000C860[rcx+rdx*8], eax
0x180002fa3  movdqu  rva g_ValidCAs[rcx+rdx*8], xmm0
0x180002fac  movaps  xmm0, [rsp+178h+var_98]
0x180002fb4  movdqu  rva xmmword_18000C850[rcx+rdx*8], xmm0
0x180002fbd  cmp     edi, 5
0x180002fc0  jb      short loc_180002F51
0x180002fc2  mov     r15, [rsp+178h+var_158]
0x180002fc7  mov     cs:dword_18000C640, 1
0x180002fd1  lea     r8, [rsp+178h+var_148]
0x180002fd6  mov     edx, esi
0x180002fd8  mov     rcx, r12
0x180002fdb  call    MinAsn1ParseCertificate
0x180002fe0  cmp     eax, esi
0x180002fe2  jnz     loc_180003084
0x180002fe8  lea     rcx, [rsp+178h+var_118]
0x180002fed  call    _VerifyAlgorithm
0x180002ff2  test    eax, eax
0x180002ff4  jz      loc_180003084
0x180002ffa  mov     esi, dword ptr [rsp+178h+Size]
0x180003001  lea     r12, cs:180000000h
0x180003008  xor     edi, edi
0x18000300a  movsxd  rax, edi
0x18000300d  lea     rbx, rva g_ValidCAs[r12]
0x180003015  lea     rdx, [rax+rax*4]
0x180003019  lea     rbx, [rbx+rdx*8]
0x18000301d  cmp     esi, [rbx]
0x18000301f  jnz     short loc_18000303D
0x180003021  mov     rdx, qword ptr (rva g_ValidCAs+8)[r12+rdx*8]; Buf2
0x180003029  mov     r8, rsi; Size
0x18000302c  mov     rcx, [rsp+178h+Buf1]; Buf1
0x180003034  call    memcmp
0x180003039  test    eax, eax
0x18000303b  jz      short loc_180003046
0x18000303d  inc     edi
0x18000303f  cmp     edi, 5
0x180003042  jb      short loc_18000300A
0x180003044  jmp     short loc_180003084
0x180003046  test    rbx, rbx
0x180003049  jz      short loc_180003084
0x18000304b  lea     r8, [rbx+10h]
0x18000304f  lea     rdx, [rsp+178h+var_108]
0x180003054  lea     rcx, [rsp+178h+var_128]
0x180003059  call    _VerifySignature
0x18000305e  test    eax, eax
0x180003060  jz      short loc_180003084
0x180003062  mov     r8, r15
0x180003065  lea     rcx, [rsp+178h+var_98]
0x18000306d  mov     rdx, r13
0x180003070  call    _ParsePublicKey
0x180003075  test    eax, eax
0x180003077  jz      short loc_180003084
0x180003079  mov     eax, [rbx+20h]
0x18000307c  mov     ebp, 1
0x180003081  mov     [r14], eax
0x180003084  mov     eax, ebp
0x180003086  mov     rcx, [rsp+178h+var_58]
0x18000308e  xor     rcx, rsp; StackCookie
0x180003091  call    __security_check_cookie
0x180003096  add     rsp, 138h
0x18000309d  pop     r15
0x18000309f  pop     r14
0x1800030a1  pop     r13
0x1800030a3  pop     r12
0x1800030a5  pop     rdi
0x1800030a6  pop     rsi
0x1800030a7  pop     rbp
0x1800030a8  pop     rbx
0x1800030a9  retn
```
