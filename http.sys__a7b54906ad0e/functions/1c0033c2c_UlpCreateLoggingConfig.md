# UlpCreateLoggingConfig

- ea: `0x1c0033c2c`
- end: `0x1c0033ec7`
- name: `UlpCreateLoggingConfig`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1c00325a8`

## callees

- `0x1c001b900`
- `0x1c0033c2c`
- `0x1c00344c0`
- `0x1c0092d6c`
- `0x1c011f454`
- `0x1c011f548`

## import_xrefs

- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1c0033d90`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1c0033d90`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0033c94`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0033d54`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0033c94`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c0033d54`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0033d77`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0033da6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0033d77`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0033da6`

## pseudocode

```c
__int64 __fastcall UlpCreateLoggingConfig(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v4; // eax
  char v5; // r12
  __int64 v7; // r15
  void *v8; // r14
  int v9; // r13d
  _OWORD *PoolWithTagPriority; // rsi
  unsigned int v11; // ebx
  __int64 v12; // rax
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // r8
  ULONG v16; // ecx
  int v17; // eax
  _DWORD *v18; // rax
  _DWORD *v19; // rbx
  int v21; // ecx
  int v22; // eax
  ULONG v23; // [rsp+30h] [rbp-28h] BYREF
  __int64 v24; // [rsp+38h] [rbp-20h] BYREF
  void *v25; // [rsp+40h] [rbp-18h]
  __int64 v29; // [rsp+B8h] [rbp+60h] BYREF

  v4 = *(_DWORD *)(a4 + 4);
  v5 = 0;
  v24 = 0;
  v25 = 0;
  v7 = 0;
  LODWORD(v29) = 0;
  v8 = 0;
  v9 = 0;
  PoolWithTagPriority = 0;
  if ( (v4 & 0x10) != 0 )
  {
    v5 = 1;
  }
  else
  {
    if ( *(_QWORD *)(a4 + 96) )
    {
      PoolWithTagPriority = ExAllocatePoolWithTagPriority((POOL_TYPE)512, 0x48u, 0x53436C55u, LowPoolPriority);
      if ( !PoolWithTagPriority )
        return (unsigned int)-1073741670;
      v12 = *(_QWORD *)(a4 + 96);
      *PoolWithTagPriority = *(_OWORD *)v12;
      PoolWithTagPriority[1] = *(_OWORD *)(v12 + 16);
      PoolWithTagPriority[2] = *(_OWORD *)(v12 + 32);
      PoolWithTagPriority[3] = *(_OWORD *)(v12 + 48);
      *((_QWORD *)PoolWithTagPriority + 8) = *(_QWORD *)(v12 + 64);
    }
    v13 = *(_QWORD *)(a4 + 88);
    if ( v13 )
    {
      v14 = UlpCaptureSecurityDescriptor(v13, 0, &v24, &v23);
      v7 = v24;
      v11 = v14;
      if ( v14 < 0 )
        goto LABEL_15;
    }
  }
  if ( !*(_DWORD *)(a4 + 56) )
  {
    v16 = *(unsigned __int16 *)(a4 + 8);
    if ( (_WORD)v16 )
    {
      v17 = UlpCaptureSoftwareDirective(*(PCWCH *)(a4 + 16), v16, (__int64)&v29);
      v8 = v25;
      v11 = v17;
      if ( v17 >= 0 )
      {
        v9 = v29;
        goto LABEL_13;
      }
LABEL_15:
      if ( PoolWithTagPriority )
        ExFreePoolWithTag(PoolWithTagPriority, 0);
      if ( v7 )
      {
        LOBYTE(v15) = 1;
        SeReleaseSecurityDescriptor(v7, 0, v15);
      }
      if ( v8 )
        ExFreePoolWithTag(v8, 0);
      return v11;
    }
  }
LABEL_13:
  v18 = ExAllocatePoolWithTagPriority((POOL_TYPE)512, 0xD0u, 0x464C6C55u, LowPoolPriority);
  v19 = v18;
  if ( !v18 )
  {
    v11 = -1073741670;
    goto LABEL_15;
  }
  memset(v18, 0, 0xD0u);
  *v19 = 1179413589;
  v21 = *(_DWORD *)(a4 + 56);
  v19[20] = v21;
  v19[21] = *(_DWORD *)(a4 + 76);
  v19[22] = *(_DWORD *)(a4 + 80);
  v19[23] = *(_DWORD *)(a4 + 60);
  v19[24] = *(_DWORD *)(a2 + 128);
  *((_QWORD *)v19 + 2) = v8;
  v19[6] = v9;
  *((_QWORD *)v19 + 15) = v7;
  *((_BYTE *)v19 + 128) = v5;
  if ( (*(_DWORD *)a2 & 1) != 0 )
    *((_BYTE *)v19 + 144) = 1;
  *((_QWORD *)v19 + 17) = PoolWithTagPriority;
  *((_QWORD *)v19 + 22) = 0;
  *((_QWORD *)v19 + 23) = 0;
  *((_QWORD *)v19 + 24) = a3;
  v19[25] = 15;
  v19[26] = 1;
  if ( (unsigned int)(v21 - 1) <= 1 )
    v19[38] |= 0x10u;
  v22 = *(_DWORD *)(a4 + 4);
  if ( (v22 & 1) != 0 )
  {
    v19[38] |= 0x200u;
    v22 = *(_DWORD *)(a4 + 4);
  }
  if ( (v22 & 2) != 0 && v21 != 3 )
    v19[38] |= 0x400u;
  *((_QWORD *)v19 + 25) = a1;
  UlpInsertLogEntry(v19);
  *(_QWORD *)(a2 + 120) = v19;
  if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x400) != 0 )
    WPP_SF_qS(47, WPP_07d3f8078d093d4b6da456c67947dc87_Traceguids, v19, *(_QWORD *)(a4 + 40));
  return 0;
}

```

## disassembly

```asm
0x1c0033c2c  mov     [rsp-40h+arg_10], r8
0x1c0033c31  mov     [rsp-40h+arg_8], rdx
0x1c0033c36  mov     [rsp-40h+arg_0], rcx
0x1c0033c3b  push    rbp
0x1c0033c3c  push    rbx
0x1c0033c3d  push    rsi
0x1c0033c3e  push    rdi
0x1c0033c3f  push    r12
0x1c0033c41  push    r13
0x1c0033c43  push    r14
0x1c0033c45  push    r15
0x1c0033c47  mov     rbp, rsp
0x1c0033c4a  sub     rsp, 58h
0x1c0033c4e  mov     eax, [r9+4]
0x1c0033c52  xor     r12d, r12d
0x1c0033c55  mov     [rbp+var_20], r12
0x1c0033c59  mov     rdi, r9
0x1c0033c5c  mov     [rbp+var_18], r12
0x1c0033c60  mov     r15d, r12d
0x1c0033c63  mov     dword ptr [rbp+arg_18], r12d
0x1c0033c67  mov     r14d, r12d
0x1c0033c6a  mov     r13d, r12d
0x1c0033c6d  mov     esi, r12d
0x1c0033c70  test    al, 10h
0x1c0033c72  jz      short loc_1C0033C7C
0x1c0033c74  mov     r12b, 1
0x1c0033c77  jmp     loc_1C0033D00
0x1c0033c7c  cmp     [r9+60h], r12
0x1c0033c80  jz      short loc_1C0033CDE
0x1c0033c82  xor     r9d, r9d; Priority
0x1c0033c85  mov     ecx, 200h; PoolType
0x1c0033c8a  mov     r8d, 53436C55h; Tag
0x1c0033c90  lea     edx, [r9+48h]; NumberOfBytes
0x1c0033c94  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c0033c9b  nop     dword ptr [rax+rax+00h]
0x1c0033ca0  mov     rsi, rax
0x1c0033ca3  test    rax, rax
0x1c0033ca6  jnz     short loc_1C0033CB2
0x1c0033ca8  mov     ebx, 0C000009Ah
0x1c0033cad  jmp     loc_1C0033DB2
0x1c0033cb2  mov     rax, [rdi+60h]
0x1c0033cb6  movups  xmm0, xmmword ptr [rax]
0x1c0033cb9  movups  xmmword ptr [rsi], xmm0
0x1c0033cbc  movups  xmm1, xmmword ptr [rax+10h]
0x1c0033cc0  movups  xmmword ptr [rsi+10h], xmm1
0x1c0033cc4  movups  xmm0, xmmword ptr [rax+20h]
0x1c0033cc8  movups  xmmword ptr [rsi+20h], xmm0
0x1c0033ccc  movups  xmm1, xmmword ptr [rax+30h]
0x1c0033cd0  movups  xmmword ptr [rsi+30h], xmm1
0x1c0033cd4  movsd   xmm0, qword ptr [rax+40h]
0x1c0033cd9  movsd   qword ptr [rsi+40h], xmm0
0x1c0033cde  mov     rcx, [rdi+58h]
0x1c0033ce2  test    rcx, rcx
0x1c0033ce5  jz      short loc_1C0033D00
0x1c0033ce7  lea     r9, [rbp+var_28]
0x1c0033ceb  xor     edx, edx
0x1c0033ced  lea     r8, [rbp+var_20]
0x1c0033cf1  call    UlpCaptureSecurityDescriptor
0x1c0033cf6  mov     r15, [rbp+var_20]
0x1c0033cfa  mov     ebx, eax
0x1c0033cfc  test    eax, eax
0x1c0033cfe  js      short loc_1C0033D6D
0x1c0033d00  xor     eax, eax
0x1c0033d02  cmp     [rdi+38h], eax
0x1c0033d05  jnz     short loc_1C0033D41
0x1c0033d07  movzx   ecx, word ptr [rdi+8]
0x1c0033d0b  test    cx, cx
0x1c0033d0e  jz      short loc_1C0033D41
0x1c0033d10  mov     r8d, [rdi+4]
0x1c0033d14  lea     r9, [rbp+var_18]
0x1c0033d18  mov     edx, ecx; BytesInUnicodeString
0x1c0033d1a  shr     r8d, 1
0x1c0033d1d  lea     rcx, [rbp+arg_18]
0x1c0033d21  and     r8b, 1
0x1c0033d25  mov     [rsp+58h+var_38], rcx; __int64
0x1c0033d2a  mov     rcx, [rdi+10h]; UnicodeString
0x1c0033d2e  call    UlpCaptureSoftwareDirective
0x1c0033d33  mov     r14, [rbp+var_18]
0x1c0033d37  mov     ebx, eax
0x1c0033d39  test    eax, eax
0x1c0033d3b  js      short loc_1C0033D6D
0x1c0033d3d  mov     r13d, dword ptr [rbp+arg_18]
0x1c0033d41  xor     r9d, r9d; Priority
0x1c0033d44  mov     edx, 0D0h; NumberOfBytes
0x1c0033d49  mov     ecx, 200h; PoolType
0x1c0033d4e  mov     r8d, 464C6C55h; Tag
0x1c0033d54  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c0033d5b  nop     dword ptr [rax+rax+00h]
0x1c0033d60  mov     rbx, rax
0x1c0033d63  test    rax, rax
0x1c0033d66  jnz     short loc_1C0033DB9
0x1c0033d68  mov     ebx, 0C000009Ah
0x1c0033d6d  test    rsi, rsi
0x1c0033d70  jz      short loc_1C0033D83
0x1c0033d72  xor     edx, edx; Tag
0x1c0033d74  mov     rcx, rsi; P
0x1c0033d77  call    cs:__imp_ExFreePoolWithTag
0x1c0033d7e  nop     dword ptr [rax+rax+00h]
0x1c0033d83  test    r15, r15
0x1c0033d86  jz      short loc_1C0033D9C
0x1c0033d88  mov     r8b, 1
0x1c0033d8b  xor     edx, edx
0x1c0033d8d  mov     rcx, r15
0x1c0033d90  call    cs:__imp_SeReleaseSecurityDescriptor
0x1c0033d97  nop     dword ptr [rax+rax+00h]
0x1c0033d9c  test    r14, r14
0x1c0033d9f  jz      short loc_1C0033DB2
0x1c0033da1  xor     edx, edx; Tag
0x1c0033da3  mov     rcx, r14; P
0x1c0033da6  call    cs:__imp_ExFreePoolWithTag
0x1c0033dad  nop     dword ptr [rax+rax+00h]
0x1c0033db2  mov     eax, ebx
0x1c0033db4  jmp     loc_1C0033EB5
0x1c0033db9  xor     edx, edx; Val
0x1c0033dbb  mov     r8d, 0D0h; Size
0x1c0033dc1  mov     rcx, rbx; void *
0x1c0033dc4  call    memset
0x1c0033dc9  mov     rdx, [rbp+arg_8]
0x1c0033dcd  mov     dword ptr [rbx], 464C6C55h
0x1c0033dd3  mov     ecx, [rdi+38h]
0x1c0033dd6  mov     [rbx+50h], ecx
0x1c0033dd9  mov     eax, [rdi+4Ch]
0x1c0033ddc  mov     [rbx+54h], eax
0x1c0033ddf  mov     eax, [rdi+50h]
0x1c0033de2  mov     [rbx+58h], eax
0x1c0033de5  mov     eax, [rdi+3Ch]
0x1c0033de8  mov     [rbx+5Ch], eax
0x1c0033deb  mov     eax, [rdx+80h]
0x1c0033df1  mov     [rbx+60h], eax
0x1c0033df4  mov     [rbx+10h], r14
0x1c0033df8  mov     [rbx+18h], r13d
0x1c0033dfc  mov     [rbx+78h], r15
0x1c0033e00  mov     [rbx+80h], r12b
0x1c0033e07  mov     eax, [rdx]
0x1c0033e09  mov     edx, 1
0x1c0033e0e  test    dl, al
0x1c0033e10  jz      short loc_1C0033E18
0x1c0033e12  mov     [rbx+90h], dl
0x1c0033e18  xor     eax, eax
0x1c0033e1a  mov     [rbx+88h], rsi
0x1c0033e21  mov     [rbx+0B0h], rax
0x1c0033e28  mov     [rbx+0B8h], rax
0x1c0033e2f  mov     rax, [rbp+arg_10]
0x1c0033e33  mov     [rbx+0C0h], rax
0x1c0033e3a  lea     eax, [rcx-1]
0x1c0033e3d  mov     dword ptr [rbx+64h], 0Fh
0x1c0033e44  mov     [rbx+68h], edx
0x1c0033e47  cmp     eax, edx
0x1c0033e49  ja      short loc_1C0033E52
0x1c0033e4b  or      dword ptr [rbx+98h], 10h
0x1c0033e52  mov     eax, [rdi+4]
0x1c0033e55  test    dl, al
0x1c0033e57  jz      short loc_1C0033E64
0x1c0033e59  bts     dword ptr [rbx+98h], 9
0x1c0033e61  mov     eax, [rdi+4]
0x1c0033e64  mov     esi, 400h
0x1c0033e69  test    al, 2
0x1c0033e6b  jz      short loc_1C0033E78
0x1c0033e6d  cmp     ecx, 3
0x1c0033e70  jz      short loc_1C0033E78
0x1c0033e72  or      [rbx+98h], esi
0x1c0033e78  mov     rax, [rbp+arg_0]
0x1c0033e7c  mov     rcx, rbx
0x1c0033e7f  mov     [rbx+0C8h], rax
0x1c0033e86  call    UlpInsertLogEntry
0x1c0033e8b  mov     rax, [rbp+arg_8]
0x1c0033e8f  mov     [rax+78h], rbx
0x1c0033e93  test    dword ptr cs:WPP_MAIN_CB.Queue+4, esi
0x1c0033e99  jz      short loc_1C0033EB3
0x1c0033e9b  mov     r9, [rdi+28h]
0x1c0033e9f  lea     rdx, WPP_07d3f8078d093d4b6da456c67947dc87_Traceguids
0x1c0033ea6  mov     ecx, 2Fh ; '/'
0x1c0033eab  mov     r8, rbx
0x1c0033eae  call    WPP_SF_qS
0x1c0033eb3  xor     eax, eax
0x1c0033eb5  add     rsp, 58h
0x1c0033eb9  pop     r15
0x1c0033ebb  pop     r14
0x1c0033ebd  pop     r13
0x1c0033ebf  pop     r12
0x1c0033ec1  pop     rdi
0x1c0033ec2  pop     rsi
0x1c0033ec3  pop     rbx
0x1c0033ec4  pop     rbp
0x1c0033ec5  retn
```
