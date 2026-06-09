# CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::CopyOrFillEntry(void * *,void * *,CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::CStrings *,void *,uchar)

- ea: `0x180006750`
- end: `0x180006834`
- name: `?CopyOrFillEntry@?$CDescriptor@VCInfoLevelStringEnum_WKSTA_INFO@@@@AEAAEPEAPEAX0PEAVCStrings@1@PEAXE@Z`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180001020`

## callees

- `0x1800064f0`
- `0x180006750`
- `0x18000683c`
- `0x180008330`
- `0x180009456`
- `0x180009462`

## pseudocode

```c
char __fastcall CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::CopyOrFillEntry(
        __int64 a1,
        void **a2,
        __int64 *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v5; // rbp
  __int64 v6; // r14
  __int64 v7; // rdi
  char *v9; // rsi
  __int64 v12; // r15
  char v13; // di
  const void *v14; // rdx
  __int64 i; // rbp
  __int64 v17; // [rsp+70h] [rbp+8h] BYREF

  v5 = a5;
  v6 = a1 + 32;
  v7 = *a3;
  v9 = (char *)*a2;
  v17 = *a3;
  if ( !a5 )
    v6 = a4;
  if ( !a4 )
    CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::ExtractStrings(a1, v6, a5);
  v12 = *(unsigned int *)(a1 + 84);
  if ( (unsigned __int64)&v9[v12] > v7
                                  - (unsigned __int64)(unsigned int)CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::GetVariableSizeFromStrings(
                                                                      a1,
                                                                      v6) )
    return 0;
  v13 = 1;
  if ( v5 )
  {
    v14 = (const void *)v5;
LABEL_9:
    memcpy_0(v9, v14, (unsigned int)v12);
    goto LABEL_11;
  }
  v14 = *(const void **)(a1 + 8);
  if ( v14 )
    goto LABEL_9;
  memset_0(v9, 0, (unsigned int)v12);
LABEL_11:
  for ( i = 0; i != 3; ++i )
    CopyString(v9, &v17, *(unsigned int *)(a1 + 4 * i + 20), v6 + 16 * i);
  *a2 = &v9[*(unsigned int *)(a1 + 84)];
  *a3 = v17;
  return v13;
}

```

## disassembly

```asm
0x180006750  push    rbx
0x180006752  push    rbp
0x180006753  push    rsi
0x180006754  push    rdi
0x180006755  push    r12
0x180006757  push    r13
0x180006759  push    r14
0x18000675b  push    r15
0x18000675d  sub     rsp, 28h
0x180006761  mov     rbp, [rsp+68h+arg_20]
0x180006769  lea     r14, [rcx+20h]
0x18000676d  mov     rdi, [r8]
0x180006770  mov     r12, r8
0x180006773  mov     rsi, [rdx]
0x180006776  mov     r13, rdx
0x180006779  mov     [rsp+68h+arg_0], rdi
0x18000677e  mov     rbx, rcx
0x180006781  test    rbp, rbp
0x180006784  jnz     short loc_180006789
0x180006786  mov     r14, r9
0x180006789  test    r9, r9
0x18000678c  jnz     short loc_180006799
0x18000678e  mov     r8, rbp
0x180006791  mov     rdx, r14
0x180006794  call    ?ExtractStrings@?$CDescriptor@VCInfoLevelStringEnum_WKSTA_INFO@@@@QEAAXPEAVCStrings@1@PEAX@Z; CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::ExtractStrings(CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::CStrings *,void *)
0x180006799  mov     r15d, [rbx+54h]
0x18000679d  mov     rdx, r14
0x1800067a0  mov     rcx, rbx
0x1800067a3  call    ?GetVariableSizeFromStrings@?$CDescriptor@VCInfoLevelStringEnum_WKSTA_INFO@@@@QEAAKPEAVCStrings@1@@Z; CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::GetVariableSizeFromStrings(CDescriptor<CInfoLevelStringEnum_WKSTA_INFO>::CStrings *)
0x1800067a8  mov     r11d, eax
0x1800067ab  lea     rax, [r15+rsi]
0x1800067af  sub     rdi, r11
0x1800067b2  cmp     rax, rdi
0x1800067b5  ja      short loc_18000681D
0x1800067b7  mov     edi, 1
0x1800067bc  mov     r8d, r15d; Size
0x1800067bf  mov     rcx, rsi; void *
0x1800067c2  test    rbp, rbp
0x1800067c5  jz      short loc_1800067CC
0x1800067c7  mov     rdx, rbp
0x1800067ca  jmp     short loc_1800067D5
0x1800067cc  mov     rdx, [rbx+8]; Val
0x1800067d0  test    rdx, rdx
0x1800067d3  jz      short loc_1800067DC
0x1800067d5  call    memcpy_0
0x1800067da  jmp     short loc_1800067E1
0x1800067dc  call    memset_0
0x1800067e1  xor     ebp, ebp
0x1800067e3  mov     r8d, [rbx+rbp*4+14h]
0x1800067e8  lea     rdx, [rsp+68h+arg_0]
0x1800067ed  mov     r9, rbp
0x1800067f0  mov     rcx, rsi
0x1800067f3  shl     r9, 4
0x1800067f7  add     r9, r14
0x1800067fa  call    CopyString
0x1800067ff  add     rbp, rdi
0x180006802  cmp     rbp, 3
0x180006806  jnz     short loc_1800067E3
0x180006808  mov     eax, [rbx+54h]
0x18000680b  add     rax, rsi
0x18000680e  mov     [r13+0], rax
0x180006812  mov     rax, [rsp+68h+arg_0]
0x180006817  mov     [r12], rax
0x18000681b  jmp     short loc_180006820
0x18000681d  xor     dil, dil
0x180006820  mov     al, dil
0x180006823  add     rsp, 28h
0x180006827  pop     r15
0x180006829  pop     r14
0x18000682b  pop     r13
0x18000682d  pop     r12
0x18000682f  pop     rdi
0x180006830  pop     rsi
0x180006831  pop     rbp
0x180006832  pop     rbx
0x180006833  retn
```
