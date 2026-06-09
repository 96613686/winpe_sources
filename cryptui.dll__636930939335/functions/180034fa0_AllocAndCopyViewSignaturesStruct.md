# AllocAndCopyViewSignaturesStruct

- ea: `0x180034fa0`
- end: `0x1800350fe`
- name: `AllocAndCopyViewSignaturesStruct`
- size: `350`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180037680`

## callees

- `0x180001f66`
- `0x18000590c`
- `0x180034fa0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034fb8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003503e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003505f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180034fb8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003503e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003505f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800350d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800350e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800350ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800350d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800350e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800350ea`
- `CRYPT32!CertDuplicateStore` at `0x1800350ab`
- `CRYPT32!CertDuplicateStore` at `0x1800350ab`
- `CRYPT32!CryptMsgDuplicate` at `0x18003508b`
- `CRYPT32!CryptMsgDuplicate` at `0x18003508b`

## pseudocode

```c
_QWORD *__fastcall AllocAndCopyViewSignaturesStruct(__int64 a1)
{
  __int64 v1; // rbx
  _OWORD *v3; // rax
  _QWORD *v4; // rdi
  const unsigned __int16 *v5; // rcx
  unsigned __int16 *v6; // rax
  HLOCAL v7; // rax
  HLOCAL v8; // rax
  __int64 v9; // rbp
  void *v10; // rcx
  void *v11; // rcx

  v1 = 0;
  v3 = LocalAlloc(0x40u, 0x78u);
  v4 = v3;
  if ( !v3 )
    return (_QWORD *)v1;
  *v3 = *(_OWORD *)a1;
  v3[1] = *(_OWORD *)(a1 + 16);
  v3[2] = *(_OWORD *)(a1 + 32);
  v3[3] = *(_OWORD *)(a1 + 48);
  v3[4] = *(_OWORD *)(a1 + 64);
  v3[5] = *(_OWORD *)(a1 + 80);
  v3[6] = *(_OWORD *)(a1 + 96);
  *((_QWORD *)v3 + 14) = *(_QWORD *)(a1 + 112);
  *((_QWORD *)v3 + 7) = 0;
  *((_QWORD *)v3 + 8) = -1;
  *((_QWORD *)v3 + 12) = 0;
  v5 = *(const unsigned __int16 **)(a1 + 56);
  if ( !v5 || (v6 = AllocAndCopyWStr(v5), (v4[7] = v6) != 0) )
  {
    v7 = LocalAlloc(0x40u, 8LL * *(unsigned int *)(a1 + 88));
    v4[12] = v7;
    if ( v7 )
    {
      if ( *(_WORD *)(a1 + 32) != 1 )
      {
        if ( *(_WORD *)(a1 + 32) == 2 )
          v4[5] = CryptMsgDuplicate(*(HCRYPTMSG *)(a1 + 40));
        goto LABEL_10;
      }
      v8 = LocalAlloc(0x40u, *(unsigned int *)(a1 + 40));
      v4[6] = v8;
      if ( v8 )
      {
        memcpy_0(v8, *(const void **)(a1 + 48), *(unsigned int *)(a1 + 40));
LABEL_10:
        v9 = 0;
        *((_DWORD *)v4 + 26) = 0;
        for ( v4[14] = 0; (unsigned int)v9 < *(_DWORD *)(a1 + 88); v9 = (unsigned int)(v9 + 1) )
          *(_QWORD *)(v4[12] + 8 * v9) = CertDuplicateStore(*(HCERTSTORE *)(*(_QWORD *)(a1 + 96) + 8 * v9));
        return v4;
      }
    }
  }
  v10 = (void *)v4[7];
  if ( v10 )
    LocalFree(v10);
  v11 = (void *)v4[12];
  if ( v11 )
    LocalFree(v11);
  LocalFree(v4);
  return (_QWORD *)v1;
}

```

## disassembly

```asm
0x180034fa0  push    rbx
0x180034fa2  push    rbp
0x180034fa3  push    rsi
0x180034fa4  push    rdi
0x180034fa5  push    r15
0x180034fa7  sub     rsp, 20h
0x180034fab  xor     ebx, ebx
0x180034fad  mov     rsi, rcx
0x180034fb0  lea     ebp, [rbx+40h]
0x180034fb3  mov     ecx, ebp; uFlags
0x180034fb5  lea     edx, [rbx+78h]; uBytes
0x180034fb8  call    cs:__imp_LocalAlloc
0x180034fbe  mov     rdi, rax
0x180034fc1  test    rax, rax
0x180034fc4  jz      loc_1800350F0
0x180034fca  movups  xmm0, xmmword ptr [rsi]
0x180034fcd  movups  xmmword ptr [rax], xmm0
0x180034fd0  movups  xmm1, xmmword ptr [rsi+10h]
0x180034fd4  movups  xmmword ptr [rax+10h], xmm1
0x180034fd8  movups  xmm0, xmmword ptr [rsi+20h]
0x180034fdc  movups  xmmword ptr [rax+20h], xmm0
0x180034fe0  movups  xmm1, xmmword ptr [rsi+30h]
0x180034fe4  movups  xmmword ptr [rax+30h], xmm1
0x180034fe8  movups  xmm0, xmmword ptr [rsi+40h]
0x180034fec  movups  xmmword ptr [rax+40h], xmm0
0x180034ff0  movups  xmm1, xmmword ptr [rsi+50h]
0x180034ff4  movups  xmmword ptr [rax+50h], xmm1
0x180034ff8  movups  xmm0, xmmword ptr [rsi+60h]
0x180034ffc  movups  xmmword ptr [rax+60h], xmm0
0x180035000  movsd   xmm1, qword ptr [rsi+70h]
0x180035005  movsd   qword ptr [rax+70h], xmm1
0x18003500a  mov     [rax+38h], rbx
0x18003500e  mov     qword ptr [rax+40h], 0FFFFFFFFFFFFFFFFh
0x180035016  mov     [rax+60h], rbx
0x18003501a  mov     rcx, [rsi+38h]; Src
0x18003501e  test    rcx, rcx
0x180035021  jz      short loc_180035035
0x180035023  call    ?AllocAndCopyWStr@@YAPEAGPEBG@Z; AllocAndCopyWStr(ushort const *)
0x180035028  mov     [rdi+38h], rax
0x18003502c  test    rax, rax
0x18003502f  jz      loc_1800350C9
0x180035035  mov     edx, [rsi+58h]
0x180035038  mov     ecx, ebp; uFlags
0x18003503a  shl     rdx, 3; uBytes
0x18003503e  call    cs:__imp_LocalAlloc
0x180035044  mov     [rdi+60h], rax
0x180035048  test    rax, rax
0x18003504b  jz      short loc_1800350C9
0x18003504d  mov     r15d, 1
0x180035053  cmp     [rsi+20h], r15w
0x180035058  jnz     short loc_180035080
0x18003505a  mov     edx, [rsi+28h]; uBytes
0x18003505d  mov     ecx, ebp; uFlags
0x18003505f  call    cs:__imp_LocalAlloc
0x180035065  mov     [rdi+30h], rax
0x180035069  test    rax, rax
0x18003506c  jz      short loc_1800350C9
0x18003506e  mov     r8d, [rsi+28h]; Size
0x180035072  mov     rcx, rax; void *
0x180035075  mov     rdx, [rsi+30h]; Src
0x180035079  call    memcpy_0
0x18003507e  jmp     short loc_180035095
0x180035080  cmp     word ptr [rsi+20h], 2
0x180035085  jnz     short loc_180035095
0x180035087  mov     rcx, [rsi+28h]; hCryptMsg
0x18003508b  call    cs:__imp_CryptMsgDuplicate
0x180035091  mov     [rdi+28h], rax
0x180035095  xor     ebp, ebp
0x180035097  mov     [rdi+68h], ebx
0x18003509a  mov     [rdi+70h], rbx
0x18003509e  cmp     [rsi+58h], ebx
0x1800350a1  jbe     short loc_1800350C4
0x1800350a3  mov     rcx, [rsi+60h]
0x1800350a7  mov     rcx, [rcx+rbp*8]; hCertStore
0x1800350ab  call    cs:__imp_CertDuplicateStore
0x1800350b1  mov     rcx, rax
0x1800350b4  mov     rax, [rdi+60h]
0x1800350b8  mov     [rax+rbp*8], rcx
0x1800350bc  add     ebp, r15d
0x1800350bf  cmp     ebp, [rsi+58h]
0x1800350c2  jb      short loc_1800350A3
0x1800350c4  mov     rbx, rdi
0x1800350c7  jmp     short loc_1800350F0
0x1800350c9  mov     rcx, [rdi+38h]; hMem
0x1800350cd  test    rcx, rcx
0x1800350d0  jz      short loc_1800350D8
0x1800350d2  call    cs:__imp_LocalFree
0x1800350d8  mov     rcx, [rdi+60h]; hMem
0x1800350dc  test    rcx, rcx
0x1800350df  jz      short loc_1800350E7
0x1800350e1  call    cs:__imp_LocalFree
0x1800350e7  mov     rcx, rdi; hMem
0x1800350ea  call    cs:__imp_LocalFree
0x1800350f0  mov     rax, rbx
0x1800350f3  add     rsp, 20h
0x1800350f7  pop     r15
0x1800350f9  pop     rdi
0x1800350fa  pop     rsi
0x1800350fb  pop     rbp
0x1800350fc  pop     rbx
0x1800350fd  retn
```
