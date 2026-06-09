# CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::CopyOrFillEntry(void * *,void * *,CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::CStrings *,void *,uchar)

- ea: `0x180005f30`
- end: `0x180006075`
- name: `?CopyOrFillEntry@?$CDescriptor@VCInfoLevelStringEnum_SHARE_INFO@@@@AEAAEPEAPEAX0PEAVCStrings@1@PEAXE@Z`
- size: `325`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800016b0`

## callees

- `0x180002000`
- `0x180005f30`
- `0x180009456`
- `0x180009462`

## pseudocode

```c
char __fastcall CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::CopyOrFillEntry(
        __int64 a1,
        void **a2,
        void **a3,
        const void **a4,
        void *Src)
{
  const void **v5; // rsi
  char *v6; // rbp
  char *v8; // r12
  unsigned int v11; // eax
  size_t v12; // r8
  const void *v13; // rdx
  int v14; // eax
  char *v15; // rcx
  size_t v16; // rbx
  int v17; // eax
  char *v18; // rdx
  size_t v19; // rbx
  __int64 v20; // rcx
  char result; // al

  v5 = (const void **)(a1 + 32);
  v6 = (char *)*a2;
  v8 = (char *)*a3;
  if ( !Src )
    v5 = a4;
  if ( !a4 )
    CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::ExtractStrings(a1, v5, Src);
  v11 = 0;
  if ( *(_DWORD *)(a1 + 20) != -1 )
    v11 = *(unsigned __int16 *)v5 + 2;
  if ( *(_DWORD *)(a1 + 24) != -1 )
    v11 += *((unsigned __int16 *)v5 + 8) + 2;
  v12 = *(unsigned int *)(a1 + 68);
  if ( &v6[v12] > &v8[-v11] )
    return 0;
  if ( Src )
  {
    memcpy_0(v6, Src, v12);
  }
  else
  {
    v13 = *(const void **)(a1 + 8);
    if ( v13 )
      memcpy_0(v6, v13, v12);
    else
      memset_0(v6, 0, v12);
  }
  v14 = *(_DWORD *)(a1 + 20);
  if ( v14 != -1 )
  {
    v15 = &v6[v14];
    if ( v15 )
    {
      v8 = &v8[-*(unsigned __int16 *)v5 - 2];
      *(_QWORD *)v15 = v8;
      v16 = *(unsigned __int16 *)v5;
      memcpy_0(v8, v5[1], v16);
      *(_WORD *)&v8[2 * (v16 >> 1)] = 0;
    }
  }
  v17 = *(_DWORD *)(a1 + 24);
  if ( v17 != -1 )
  {
    v18 = &v6[v17];
    if ( v18 )
    {
      v8 += -2LL - *((unsigned __int16 *)v5 + 8);
      *(_QWORD *)v18 = v8;
      v19 = *((unsigned __int16 *)v5 + 8);
      memcpy_0(v8, v5[3], v19);
      *(_WORD *)&v8[2 * (v19 >> 1)] = 0;
    }
  }
  v20 = *(unsigned int *)(a1 + 68);
  result = 1;
  *a3 = v8;
  *a2 = &v6[v20];
  return result;
}

```

## disassembly

```asm
0x180005f30  push    rbx
0x180005f32  push    rbp
0x180005f33  push    rsi
0x180005f34  push    rdi
0x180005f35  push    r12
0x180005f37  push    r14
0x180005f39  push    r15
0x180005f3b  sub     rsp, 20h
0x180005f3f  mov     rbx, [rsp+58h+Src]
0x180005f47  lea     rsi, [rcx+20h]
0x180005f4b  mov     rbp, [rdx]
0x180005f4e  mov     r14, r8
0x180005f51  mov     r12, [r8]
0x180005f54  mov     r15, rdx
0x180005f57  mov     rdi, rcx
0x180005f5a  test    rbx, rbx
0x180005f5d  jnz     short loc_180005F62
0x180005f5f  mov     rsi, r9
0x180005f62  test    r9, r9
0x180005f65  jnz     short loc_180005F72
0x180005f67  mov     r8, rbx
0x180005f6a  mov     rdx, rsi
0x180005f6d  call    ?ExtractStrings@?$CDescriptor@VCInfoLevelStringEnum_SHARE_INFO@@@@QEAAXPEAVCStrings@1@PEAX@Z; CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::ExtractStrings(CDescriptor<CInfoLevelStringEnum_SHARE_INFO>::CStrings *,void *)
0x180005f72  xor     eax, eax
0x180005f74  cmp     dword ptr [rdi+14h], 0FFFFFFFFh
0x180005f78  jz      short loc_180005F80
0x180005f7a  movzx   eax, word ptr [rsi]
0x180005f7d  add     eax, 2
0x180005f80  cmp     dword ptr [rdi+18h], 0FFFFFFFFh
0x180005f84  jz      short loc_180005F8F
0x180005f86  movzx   ecx, word ptr [rsi+10h]
0x180005f8a  add     eax, 2
0x180005f8d  add     eax, ecx
0x180005f8f  mov     r8d, [rdi+44h]; Size
0x180005f93  mov     r9, r12
0x180005f96  mov     ecx, eax
0x180005f98  sub     r9, rcx
0x180005f9b  lea     rax, [r8+rbp]
0x180005f9f  cmp     rax, r9
0x180005fa2  ja      loc_180006064
0x180005fa8  mov     rcx, rbp; void *
0x180005fab  test    rbx, rbx
0x180005fae  jz      short loc_180005FBA
0x180005fb0  mov     rdx, rbx; Src
0x180005fb3  call    memcpy_0
0x180005fb8  jmp     short loc_180005FCF
0x180005fba  mov     rdx, [rdi+8]; Val
0x180005fbe  test    rdx, rdx
0x180005fc1  jz      short loc_180005FCA
0x180005fc3  call    memcpy_0
0x180005fc8  jmp     short loc_180005FCF
0x180005fca  call    memset_0
0x180005fcf  mov     eax, [rdi+14h]
0x180005fd2  cmp     eax, 0FFFFFFFFh
0x180005fd5  jz      short loc_180006007
0x180005fd7  mov     ecx, eax
0x180005fd9  add     rcx, rbp
0x180005fdc  jz      short loc_180006007
0x180005fde  movzx   eax, word ptr [rsi]
0x180005fe1  sub     r12, rax
0x180005fe4  add     r12, 0FFFFFFFFFFFFFFFEh
0x180005fe8  mov     [rcx], r12
0x180005feb  mov     rcx, r12; void *
0x180005fee  movzx   ebx, word ptr [rsi]
0x180005ff1  mov     rdx, [rsi+8]; Src
0x180005ff5  mov     r8d, ebx; Size
0x180005ff8  call    memcpy_0
0x180005ffd  shr     rbx, 1
0x180006000  xor     eax, eax
0x180006002  mov     [r12+rbx*2], ax
0x180006007  mov     eax, [rdi+18h]
0x18000600a  cmp     eax, 0FFFFFFFFh
0x18000600d  jz      short loc_180006047
0x18000600f  mov     edx, eax
0x180006011  add     rdx, rbp
0x180006014  jz      short loc_180006047
0x180006016  movzx   eax, word ptr [rsi+10h]
0x18000601a  mov     rcx, 0FFFFFFFFFFFFFFFEh
0x180006021  sub     rcx, rax
0x180006024  add     r12, rcx
0x180006027  mov     [rdx], r12
0x18000602a  mov     rcx, r12; void *
0x18000602d  movzx   ebx, word ptr [rsi+10h]
0x180006031  mov     rdx, [rsi+18h]; Src
0x180006035  mov     r8d, ebx; Size
0x180006038  call    memcpy_0
0x18000603d  shr     rbx, 1
0x180006040  xor     ecx, ecx
0x180006042  mov     [r12+rbx*2], cx
0x180006047  mov     ecx, [rdi+44h]
0x18000604a  mov     al, 1
0x18000604c  add     rcx, rbp
0x18000604f  mov     [r14], r12
0x180006052  mov     [r15], rcx
0x180006055  add     rsp, 20h
0x180006059  pop     r15
0x18000605b  pop     r14
0x18000605d  pop     r12
0x18000605f  pop     rdi
0x180006060  pop     rsi
0x180006061  pop     rbp
0x180006062  pop     rbx
0x180006063  retn
0x180006064  xor     al, al
0x180006066  add     rsp, 20h
0x18000606a  pop     r15
0x18000606c  pop     r14
0x18000606e  pop     r12
0x180006070  pop     rdi
0x180006071  pop     rsi
0x180006072  pop     rbp
0x180006073  pop     rbx
0x180006074  retn
```
