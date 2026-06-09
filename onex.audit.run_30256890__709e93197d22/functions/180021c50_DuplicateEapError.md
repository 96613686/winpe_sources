# DuplicateEapError

- ea: `0x180021c50`
- end: `0x180021e6a`
- name: `DuplicateEapError`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180018d60`

## callees

- `0x180005440`
- `0x180010ae0`
- `0x1800214f0`
- `0x180021c50`

## import_xrefs

- `MobileNetworking!AllocateAndCopyPointerData` at `0x180021d1b`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x180021d63`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x180021d1b`
- `MobileNetworking!AllocateAndCopyPointerData` at `0x180021d63`
- `MobileNetworking!AllocateMemory` at `0x180021cc5`
- `MobileNetworking!AllocateMemory` at `0x180021cc5`
- `MobileNetworking!FreeMemory` at `0x180021da9`
- `MobileNetworking!FreeMemory` at `0x180021dbc`
- `MobileNetworking!FreeMemory` at `0x180021dcf`
- `MobileNetworking!FreeMemory` at `0x180021da9`
- `MobileNetworking!FreeMemory` at `0x180021dbc`
- `MobileNetworking!FreeMemory` at `0x180021dcf`

## pseudocode

```c
__int64 __fastcall DuplicateEapError(__int64 a1, _QWORD *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rax
  _QWORD v14[2]; // [rsp+20h] [rbp-10h] BYREF
  __int64 v15; // [rsp+80h] [rbp+50h] BYREF
  __int64 v16; // [rsp+88h] [rbp+58h] BYREF

  v15 = 0;
  v16 = 0;
  v14[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 67, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids);
  v4 = AllocateMemory(88, &v15, "DuplicateEapError", 1114);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_22;
    v7 = 68;
    goto LABEL_21;
  }
  v8 = *(_QWORD *)(a1 + 72);
  v9 = -1;
  if ( v8 )
  {
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)(v8 + 2 * v10) );
    v4 = AllocateAndCopyPointerData(&v16, v8, (unsigned int)(2 * v10 + 2));
    v5 = v4;
    if ( v4 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_22;
      v7 = 69;
      goto LABEL_21;
    }
  }
  v11 = *(_QWORD *)(a1 + 80);
  if ( !v11 )
    goto LABEL_23;
  do
    ++v9;
  while ( *(_WORD *)(v11 + 2 * v9) );
  v4 = AllocateAndCopyPointerData(v14, v11, (unsigned int)(2 * v9 + 2));
  v5 = v4;
  if ( !v4 )
  {
LABEL_23:
    v12 = v15;
    *(_OWORD *)v15 = *(_OWORD *)a1;
    *(_OWORD *)(v12 + 16) = *(_OWORD *)(a1 + 16);
    *(_OWORD *)(v12 + 32) = *(_OWORD *)(a1 + 32);
    *(_OWORD *)(v12 + 48) = *(_OWORD *)(a1 + 48);
    *(_OWORD *)(v12 + 64) = *(_OWORD *)(a1 + 64);
    *(_QWORD *)(v12 + 80) = *(_QWORD *)(a1 + 80);
    *(_QWORD *)(v15 + 72) = v16;
    *(_QWORD *)(v15 + 80) = v14[0];
    *a2 = v15;
    goto LABEL_24;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v7 = 70;
LABEL_21:
    WPP_SF_d(v6[7], v7, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids, v4);
  }
LABEL_22:
  FreeMemory(&v16, "DuplicateEapError", 1142);
  FreeMemory(v14, "DuplicateEapError", 1143);
  FreeMemory(&v15, "DuplicateEapError", 1144);
LABEL_24:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 71, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x180021c50  mov     [rsp-38h+arg_0], rbx
0x180021c55  push    rbp
0x180021c56  push    rsi
0x180021c57  push    rdi
0x180021c58  push    r12
0x180021c5a  push    r13
0x180021c5c  push    r14
0x180021c5e  push    r15
0x180021c60  mov     rbp, rsp
0x180021c63  sub     rsp, 30h
0x180021c67  xor     r15d, r15d
0x180021c6a  mov     r14, rdx
0x180021c6d  mov     [rbp+arg_10], r15
0x180021c71  mov     rsi, rcx
0x180021c74  mov     [rbp+arg_18], r15
0x180021c78  mov     [rbp+var_10], r15
0x180021c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c83  lea     r12, WPP_GLOBAL_Control
0x180021c8a  lea     r13, WPP_8ae8a8867dca3efc60ed89af660f4cc6_Traceguids
0x180021c91  cmp     rcx, r12
0x180021c94  jz      short loc_180021CAF
0x180021c96  test    dword ptr [rcx+44h], 800h
0x180021c9d  jz      short loc_180021CAF
0x180021c9f  mov     rcx, [rcx+38h]
0x180021ca3  lea     edx, [r15+43h]
0x180021ca7  mov     r8, r13
0x180021caa  call    WPP_SF_
0x180021caf  mov     r9d, 45Ah
0x180021cb5  lea     r8, aDuplicateeaper; "DuplicateEapError"
0x180021cbc  lea     rdx, [rbp+arg_10]
0x180021cc0  mov     ecx, 58h ; 'X'
0x180021cc5  call    cs:__imp_AllocateMemory
0x180021ccb  mov     ebx, eax
0x180021ccd  test    eax, eax
0x180021ccf  jz      short loc_180021CF5
0x180021cd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180021cd8  cmp     rcx, r12
0x180021cdb  jz      loc_180021D95
0x180021ce1  test    byte ptr [rcx+44h], 1
0x180021ce5  jz      loc_180021D95
0x180021ceb  mov     edx, 44h ; 'D'
0x180021cf0  jmp     loc_180021D86
0x180021cf5  mov     rdx, [rsi+48h]
0x180021cf9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180021cfd  test    rdx, rdx
0x180021d00  jz      short loc_180021D40
0x180021d02  mov     r8, rdi
0x180021d05  inc     r8
0x180021d08  cmp     [rdx+r8*2], r15w
0x180021d0d  jnz     short loc_180021D05
0x180021d0f  lea     r8d, ds:2[r8*2]
0x180021d17  lea     rcx, [rbp+arg_18]
0x180021d1b  call    cs:__imp_AllocateAndCopyPointerData
0x180021d21  mov     ebx, eax
0x180021d23  test    eax, eax
0x180021d25  jz      short loc_180021D40
0x180021d27  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d2e  cmp     rcx, r12
0x180021d31  jz      short loc_180021D95
0x180021d33  test    byte ptr [rcx+44h], 1
0x180021d37  jz      short loc_180021D95
0x180021d39  mov     edx, 45h ; 'E'
0x180021d3e  jmp     short loc_180021D86
0x180021d40  mov     rdx, [rsi+50h]
0x180021d44  test    rdx, rdx
0x180021d47  jz      loc_180021DD7
0x180021d4d  inc     rdi
0x180021d50  cmp     [rdx+rdi*2], r15w
0x180021d55  jnz     short loc_180021D4D
0x180021d57  lea     r8d, ds:2[rdi*2]
0x180021d5f  lea     rcx, [rbp+var_10]
0x180021d63  call    cs:__imp_AllocateAndCopyPointerData
0x180021d69  mov     ebx, eax
0x180021d6b  test    eax, eax
0x180021d6d  jz      short loc_180021DD7
0x180021d6f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d76  cmp     rcx, r12
0x180021d79  jz      short loc_180021D95
0x180021d7b  test    byte ptr [rcx+44h], 1
0x180021d7f  jz      short loc_180021D95
0x180021d81  mov     edx, 46h ; 'F'
0x180021d86  mov     rcx, [rcx+38h]
0x180021d8a  mov     r9d, eax
0x180021d8d  mov     r8, r13
0x180021d90  call    WPP_SF_d
0x180021d95  lea     rdi, aDuplicateeaper; "DuplicateEapError"
0x180021d9c  mov     r8d, 476h
0x180021da2  mov     rdx, rdi
0x180021da5  lea     rcx, [rbp+arg_18]
0x180021da9  call    cs:__imp_FreeMemory
0x180021daf  mov     r8d, 477h
0x180021db5  lea     rcx, [rbp+var_10]
0x180021db9  mov     rdx, rdi
0x180021dbc  call    cs:__imp_FreeMemory
0x180021dc2  mov     r8d, 478h
0x180021dc8  lea     rcx, [rbp+arg_10]
0x180021dcc  mov     rdx, rdi
0x180021dcf  call    cs:__imp_FreeMemory
0x180021dd5  jmp     short loc_180021E2A
0x180021dd7  movups  xmm0, xmmword ptr [rsi]
0x180021dda  mov     rax, [rbp+arg_10]
0x180021dde  movups  xmmword ptr [rax], xmm0
0x180021de1  movups  xmm1, xmmword ptr [rsi+10h]
0x180021de5  movups  xmmword ptr [rax+10h], xmm1
0x180021de9  movups  xmm0, xmmword ptr [rsi+20h]
0x180021ded  movups  xmmword ptr [rax+20h], xmm0
0x180021df1  movups  xmm1, xmmword ptr [rsi+30h]
0x180021df5  movups  xmmword ptr [rax+30h], xmm1
0x180021df9  movups  xmm0, xmmword ptr [rsi+40h]
0x180021dfd  movups  xmmword ptr [rax+40h], xmm0
0x180021e01  movsd   xmm1, qword ptr [rsi+50h]
0x180021e06  movsd   qword ptr [rax+50h], xmm1
0x180021e0b  mov     rcx, [rbp+arg_10]
0x180021e0f  mov     rax, [rbp+arg_18]
0x180021e13  mov     [rcx+48h], rax
0x180021e17  mov     rax, [rbp+arg_10]
0x180021e1b  mov     rcx, [rbp+var_10]
0x180021e1f  mov     [rax+50h], rcx
0x180021e23  mov     rax, [rbp+arg_10]
0x180021e27  mov     [r14], rax
0x180021e2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e31  cmp     rcx, r12
0x180021e34  jz      short loc_180021E53
0x180021e36  test    dword ptr [rcx+44h], 800h
0x180021e3d  jz      short loc_180021E53
0x180021e3f  mov     rcx, [rcx+38h]
0x180021e43  mov     edx, 47h ; 'G'
0x180021e48  mov     r9d, ebx
0x180021e4b  mov     r8, r13
0x180021e4e  call    WPP_SF_D
0x180021e53  mov     eax, ebx
0x180021e55  mov     rbx, [rsp+30h+arg_0]
0x180021e5a  add     rsp, 30h
0x180021e5e  pop     r15
0x180021e60  pop     r14
0x180021e62  pop     r13
0x180021e64  pop     r12
0x180021e66  pop     rdi
0x180021e67  pop     rsi
0x180021e68  pop     rbp
0x180021e69  retn
```
