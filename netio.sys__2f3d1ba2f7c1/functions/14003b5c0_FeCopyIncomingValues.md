# FeCopyIncomingValues

- ea: `0x14003b5c0`
- end: `0x14003b99b`
- name: `FeCopyIncomingValues`
- size: `987`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003b2d4`

## callees

- `0x140009520`
- `0x140009e00`
- `0x14000afa0`
- `0x14003b5c0`
- `0x14003b9a4`
- `0x14003bb48`
- `0x14003bba4`
- `0x14004efd4`
- `0x140078100`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x14003b89a`
- `ntoskrnl!RtlLengthSid` at `0x14003b89a`

## string_xrefs

- `0x14003b64b`: `FeCopyIncomingValues`
- `0x14003b671`: `FeCopyIncomingValues`
- `0x14003b963`: `FeCopyIncomingValues`

## pseudocode

```c
__int64 __fastcall FeCopyIncomingValues(unsigned __int16 *a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rbx
  __int64 BytesNeededForComplexValues; // rsi
  __int64 v7; // rbx
  __int64 v8; // r8
  _WORD *v10; // r13
  _WORD *v11; // r12
  unsigned int v12; // eax
  char *v13; // rbp
  __int64 v14; // r8
  __int64 v15; // r14
  __int64 v16; // rcx
  __int64 v17; // rax
  char v18; // r9
  unsigned __int64 v19; // rdx
  const void **v20; // rdx
  unsigned __int64 v21; // rbx
  __int64 v22; // rcx
  char *v23; // rbx
  size_t v24; // rdi
  _OWORD *v25; // rcx
  _WORD *v26; // rdx
  __int64 v27; // rbx
  size_t v28; // rbx
  _WORD *v29; // [rsp+30h] [rbp-48h] BYREF
  __int64 v30; // [rsp+80h] [rbp+8h] BYREF
  _QWORD *v31; // [rsp+90h] [rbp+18h]
  volatile signed __int32 *v32; // [rsp+98h] [rbp+20h] BYREF

  v31 = a3;
  v3 = *((unsigned int *)a1 + 1);
  v30 = 0;
  v32 = 0;
  v29 = 0;
  BytesNeededForComplexValues = GetBytesNeededForComplexValues(a1, &v30);
  if ( BytesNeededForComplexValues
    || (v7 = 8 * v3, (BytesNeededForComplexValues = WfpSizeTAdd(v30, (v7 * 2 + 23) & 0xFFFFFFFFFFFFFFF8uLL, &v32)) != 0)
    || (BytesNeededForComplexValues = WfpPoolAllocNonPaged(v32, 1986618694, &v29)) != 0 )
  {
LABEL_4:
    WfpReportError(BytesNeededForComplexValues, "FeCopyIncomingValues");
    return BytesNeededForComplexValues;
  }
  v10 = v29;
  *v29 = *a1;
  v11 = v10 + 8;
  *((_DWORD *)v10 + 1) = *((_DWORD *)a1 + 1);
  *((_QWORD *)v10 + 1) = v10 + 8;
  memmove(v10 + 8, *((const void **)a1 + 1), 16LL * *((unsigned int *)a1 + 1));
  if ( (unsigned __int8)LayerHasFqbn(*a1) && !a2 )
  {
    BytesNeededForComplexValues = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"FeCopyIncomingValues",
        13);
    }
    goto LABEL_4;
  }
  v12 = 0;
  v13 = (char *)(((unsigned __int64)&v10[v7 + 11] + 1) & 0xFFFFFFFFFFFFFFF8uLL);
  while ( 1 )
  {
    LODWORD(v30) = v12;
    if ( v12 >= *((_DWORD *)a1 + 1) )
    {
      *v31 = v10;
      return BytesNeededForComplexValues;
    }
    v14 = *((_QWORD *)a1 + 1);
    v15 = 2LL * v12;
    switch ( *(_DWORD *)(v14 + 16LL * v12) )
    {
      case 4:
      case 8:
      case 0xA:
        v19 = (unsigned __int64)(v13 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        v13 = (char *)(v19 + 8);
        *(_QWORD *)v19 = **(_QWORD **)(v14 + 16LL * v12 + 8);
        goto LABEL_25;
      case 0xB:
        v25 = (_OWORD *)((unsigned __int64)(v13 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
        v13 = (char *)(v25 + 1);
        *v25 = *(_OWORD *)*(_QWORD *)(v14 + 16LL * v12 + 8);
        *(_QWORD *)&v11[8 * v12 + 4] = v25;
        goto LABEL_26;
      case 0xC:
        v20 = *(const void ***)(v14 + 16LL * v12 + 8);
        v21 = (unsigned __int64)(v13 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        memmove((void *)(v21 + 16), v20[1], *(unsigned int *)v20);
        *(_QWORD *)(v21 + 8) = v21 + 16;
        *(_DWORD *)v21 = **(_DWORD **)(*((_QWORD *)a1 + 1) + 8 * v15 + 8);
        *(_QWORD *)&v11[4 * v15 + 4] = v21;
        v13 = (char *)(v21
                     + 16
                     + ((**(unsigned int **)(*((_QWORD *)a1 + 1) + 8 * v15 + 8) + 7LL) & 0xFFFFFFFFFFFFFFF8uLL));
        goto LABEL_26;
      case 0xD:
        v23 = (char *)((unsigned __int64)(v13 + 7) & 0xFFFFFFFFFFFFFFF8uLL);
        v24 = RtlLengthSid(*(PSID *)(v14 + 16LL * v12 + 8));
        memmove(v23, *(const void **)(*((_QWORD *)a1 + 1) + 8 * v15 + 8), v24);
        *(_QWORD *)&v11[4 * v15 + 4] = v23;
        v13 = &v23[v24];
        goto LABEL_26;
    }
    v16 = (unsigned int)(*(_DWORD *)(v14 + 16LL * v12) - 16);
    if ( *(_DWORD *)(v14 + 16LL * v12) == 16 )
      break;
    if ( *(_DWORD *)(v14 + 16LL * v12) == 17 )
    {
      v26 = *(_WORD **)(v14 + 16LL * v12 + 8);
      v27 = -1;
      do
        ++v27;
      while ( v26[v27] );
      v28 = 2 * v27 + 2;
      memmove(v13, v26, v28);
      *(_QWORD *)&v11[4 * v15 + 4] = v13;
      v13 += v28;
    }
    else if ( *(_DWORD *)(v14 + 16LL * v12) == 18 )
    {
      v22 = *(_QWORD *)(v14 + 16LL * v12 + 8);
      v19 = (unsigned __int64)(v13 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      *(_DWORD *)v19 = *(_DWORD *)v22;
      v13 = (char *)(v19 + 6);
      *(_WORD *)(v19 + 4) = *(_WORD *)(v22 + 4);
LABEL_25:
      *(_QWORD *)&v11[4 * v15 + 4] = v19;
    }
LABEL_26:
    v12 = v30 + 1;
  }
  v17 = *(_QWORD *)(*(_QWORD *)(v14 + 16LL * v12 + 8) + 8LL);
  if ( *(_DWORD *)(v17 - 224) == 1399155777 )
  {
    v32 = (volatile signed __int32 *)(v17 - 192);
    v18 = *(_BYTE *)(v17 - 192 + 5);
    do
    {
      v16 = *(unsigned int *)v32;
      if ( (v16 & 2) != 0 || (v16 & 1) == 0 && (v18 || (unsigned int)v16 < 4) )
      {
        v8 = 3221226021LL;
        goto LABEL_7;
      }
    }
    while ( (_DWORD)v16 != _InterlockedCompareExchange(v32, v16 + 4, v16) );
    v19 = (unsigned __int64)(v13 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
    v13 = (char *)(v19 + 16);
    *(_DWORD *)v19 = **(_DWORD **)(*((_QWORD *)a1 + 1) + 8 * v15 + 8);
    *(_QWORD *)(v19 + 8) = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 8 * v15 + 8) + 8LL);
    goto LABEL_25;
  }
  v8 = -1073741811;
LABEL_7:
  BytesNeededForComplexValues = WfpReportSysErrorAsNtStatus(v16, "FeCopyIncomingValues", v8, 1);
  if ( BytesNeededForComplexValues )
    goto LABEL_4;
  return BytesNeededForComplexValues;
}

```

## disassembly

```asm
0x14003b5c0  mov     rax, rsp
0x14003b5c3  mov     [rax+10h], rbx
0x14003b5c7  mov     [rax+18h], r8
0x14003b5cb  push    rbp
0x14003b5cc  push    rsi
0x14003b5cd  push    rdi
0x14003b5ce  push    r12
0x14003b5d0  push    r13
0x14003b5d2  push    r14
0x14003b5d4  push    r15
0x14003b5d6  sub     rsp, 40h
0x14003b5da  mov     ebx, [rcx+4]
0x14003b5dd  xor     r14d, r14d
0x14003b5e0  mov     rdi, rdx
0x14003b5e3  mov     [rax+8], r14
0x14003b5e7  lea     rdx, [rax+8]
0x14003b5eb  mov     [rax+20h], r14
0x14003b5ef  mov     [rax-48h], r14
0x14003b5f3  mov     r15, rcx
0x14003b5f6  call    GetBytesNeededForComplexValues
0x14003b5fb  mov     rsi, rax
0x14003b5fe  test    rax, rax
0x14003b601  jnz     short loc_14003B64B
0x14003b603  mov     rcx, [rsp+78h+arg_0]
0x14003b60b  lea     r8, [rsp+78h+arg_18]
0x14003b613  shl     rbx, 4
0x14003b617  lea     rdx, [rbx+17h]
0x14003b61b  and     rdx, 0FFFFFFFFFFFFFFF8h
0x14003b61f  call    WfpSizeTAdd
0x14003b624  mov     rsi, rax
0x14003b627  test    rax, rax
0x14003b62a  jnz     short loc_14003B64B
0x14003b62c  mov     rcx, [rsp+78h+arg_18]
0x14003b634  lea     r8, [rsp+78h+var_48]
0x14003b639  mov     edx, 76696546h
0x14003b63e  call    WfpPoolAllocNonPaged
0x14003b643  mov     rsi, rax
0x14003b646  test    rax, rax
0x14003b649  jz      short loc_14003B6A1
0x14003b64b  lea     rdx, aFecopyincoming; "FeCopyIncomingValues"
0x14003b652  mov     rcx, rsi
0x14003b655  call    WfpReportError
0x14003b65a  jmp     short loc_14003B685
0x14003b65c  test    r9b, r9b
0x14003b65f  jz      loc_14003B910
0x14003b665  mov     r8d, 0C0000225h
0x14003b66b  mov     r9d, 1
0x14003b671  lea     rdx, aFecopyincoming; "FeCopyIncomingValues"
0x14003b678  call    WfpReportSysErrorAsNtStatus
0x14003b67d  mov     rsi, rax
0x14003b680  test    rax, rax
0x14003b683  jnz     short loc_14003B64B
0x14003b685  mov     rbx, [rsp+78h+arg_8]
0x14003b68d  mov     rax, rsi
0x14003b690  add     rsp, 40h
0x14003b694  pop     r15
0x14003b696  pop     r14
0x14003b698  pop     r13
0x14003b69a  pop     r12
0x14003b69c  pop     rdi
0x14003b69d  pop     rsi
0x14003b69e  pop     rbp
0x14003b69f  retn
0x14003b6a1  movzx   eax, word ptr [r15]
0x14003b6a5  mov     r13, [rsp+78h+var_48]
0x14003b6aa  mov     [r13+0], ax
0x14003b6af  lea     r12, [r13+10h]
0x14003b6b3  mov     eax, [r15+4]
0x14003b6b7  mov     rcx, r12; void *
0x14003b6ba  mov     [r13+4], eax
0x14003b6be  mov     [r13+8], r12
0x14003b6c2  mov     r8d, [r15+4]
0x14003b6c6  mov     rdx, [r15+8]; Src
0x14003b6ca  shl     r8, 4; Size
0x14003b6ce  call    memmove
0x14003b6d3  movzx   ecx, word ptr [r15]
0x14003b6d7  call    LayerHasFqbn
0x14003b6dc  test    al, al
0x14003b6de  jnz     loc_14003B91E
0x14003b6e4  lea     rbp, [r12+7]
0x14003b6e9  mov     eax, r14d
0x14003b6ec  add     rbp, rbx
0x14003b6ef  and     rbp, 0FFFFFFFFFFFFFFF8h
0x14003b6f3  mov     dword ptr [rsp+78h+arg_0], eax
0x14003b6fa  cmp     eax, [r15+4]
0x14003b6fe  jnb     loc_14003B885
0x14003b704  mov     r8, [r15+8]
0x14003b708  mov     r14d, eax
0x14003b70b  add     r14, r14
0x14003b70e  mov     r9d, [r8+r14*8]
0x14003b712  mov     ecx, r9d
0x14003b715  sub     ecx, 4
0x14003b718  jz      loc_14003B8D2
0x14003b71e  sub     ecx, 4
0x14003b721  jz      loc_14003B8D2
0x14003b727  sub     ecx, 2
0x14003b72a  jz      loc_14003B8D2
0x14003b730  sub     ecx, 1
0x14003b733  jz      loc_14003B8EE
0x14003b739  sub     ecx, 1
0x14003b73c  jz      loc_14003B807
0x14003b742  sub     ecx, 1
0x14003b745  jz      loc_14003B895
0x14003b74b  sub     ecx, 3
0x14003b74e  jnz     loc_14003B855
0x14003b754  mov     rax, [r8+r14*8+8]
0x14003b759  mov     rax, [rax+8]
0x14003b75d  cmp     dword ptr [rax-0E0h], 53656C41h
0x14003b767  jnz     loc_14003B98F
0x14003b76d  add     rax, 0FFFFFFFFFFFFFF40h
0x14003b773  mov     [rsp+78h+arg_18], rax
0x14003b77b  mov     rax, [rsp+78h+arg_18]
0x14003b783  mov     [rsp+78h+arg_18], rax
0x14003b78b  mov     rax, [rsp+78h+arg_18]
0x14003b793  mov     r9b, [rax+5]
0x14003b797  mov     rcx, [rsp+78h+arg_18]
0x14003b79f  mov     ecx, [rcx]
0x14003b7a1  test    cl, 2
0x14003b7a4  jnz     loc_14003B665
0x14003b7aa  test    cl, 1
0x14003b7ad  jz      loc_14003B65C
0x14003b7b3  mov     rdx, [rsp+78h+arg_18]
0x14003b7bb  lea     r8d, [rcx+4]
0x14003b7bf  mov     eax, ecx
0x14003b7c1  lock cmpxchg [rdx], r8d
0x14003b7c6  cmp     ecx, eax
0x14003b7c8  jnz     short loc_14003B797
0x14003b7ca  mov     rax, [r15+8]
0x14003b7ce  lea     rdx, [rbp+7]
0x14003b7d2  and     rdx, 0FFFFFFFFFFFFFFF8h
0x14003b7d6  mov     rcx, [rax+r14*8+8]
0x14003b7db  lea     rbp, [rdx+10h]
0x14003b7df  mov     eax, [rcx]
0x14003b7e1  mov     [rdx], eax
0x14003b7e3  mov     rax, [r15+8]
0x14003b7e7  mov     rcx, [rax+r14*8+8]
0x14003b7ec  mov     rax, [rcx+8]
0x14003b7f0  mov     [rdx+8], rax
0x14003b7f4  mov     [r12+r14*8+8], rdx
0x14003b7f9  mov     eax, dword ptr [rsp+78h+arg_0]
0x14003b800  inc     eax
0x14003b802  jmp     loc_14003B6F3
0x14003b807  mov     rdx, [r8+r14*8+8]
0x14003b80c  lea     rbx, [rbp+7]
0x14003b810  and     rbx, 0FFFFFFFFFFFFFFF8h
0x14003b814  mov     r8d, [rdx]; Size
0x14003b817  mov     rdx, [rdx+8]; Src
0x14003b81b  lea     rdi, [rbx+10h]
0x14003b81f  mov     rcx, rdi; void *
0x14003b822  call    memmove
0x14003b827  mov     [rbx+8], rdi
0x14003b82b  mov     rax, [r15+8]
0x14003b82f  mov     rcx, [rax+r14*8+8]
0x14003b834  mov     eax, [rcx]
0x14003b836  mov     [rbx], eax
0x14003b838  mov     [r12+r14*8+8], rbx
0x14003b83d  mov     rax, [r15+8]
0x14003b841  mov     rcx, [rax+r14*8+8]
0x14003b846  mov     ebp, [rcx]
0x14003b848  add     rbp, 7
0x14003b84c  and     rbp, 0FFFFFFFFFFFFFFF8h
0x14003b850  add     rbp, rdi
0x14003b853  jmp     short loc_14003B7F9
0x14003b855  sub     ecx, 1
0x14003b858  jz      loc_14003B97F
0x14003b85e  cmp     ecx, 1
0x14003b861  jnz     short loc_14003B7F9
0x14003b863  mov     rcx, [r8+r14*8+8]
0x14003b868  lea     rdx, [rbp+7]
0x14003b86c  and     rdx, 0FFFFFFFFFFFFFFF8h
0x14003b870  mov     eax, [rcx]
0x14003b872  mov     [rdx], eax
0x14003b874  lea     rbp, [rdx+6]
0x14003b878  movzx   eax, word ptr [rcx+4]
0x14003b87c  mov     [rdx+4], ax
0x14003b880  jmp     loc_14003B7F4
0x14003b885  mov     rax, [rsp+78h+arg_10]
0x14003b88d  mov     [rax], r13
0x14003b890  jmp     loc_14003B685
0x14003b895  mov     rcx, [r8+r14*8+8]; Sid
0x14003b89a  call    cs:__imp_RtlLengthSid
0x14003b8a1  nop     dword ptr [rax+rax+00h]
0x14003b8a6  mov     rdx, [r15+8]
0x14003b8aa  lea     rbx, [rbp+7]
0x14003b8ae  and     rbx, 0FFFFFFFFFFFFFFF8h
0x14003b8b2  mov     r8d, eax; Size
0x14003b8b5  mov     rcx, rbx; void *
0x14003b8b8  mov     edi, eax
0x14003b8ba  mov     rdx, [rdx+r14*8+8]; Src
0x14003b8bf  call    memmove
0x14003b8c4  mov     [r12+r14*8+8], rbx
0x14003b8c9  lea     rbp, [rdi+rbx]
0x14003b8cd  jmp     loc_14003B7F9
0x14003b8d2  mov     rax, [r8+r14*8+8]
0x14003b8d7  lea     rdx, [rbp+7]
0x14003b8db  and     rdx, 0FFFFFFFFFFFFFFF8h
0x14003b8df  mov     rcx, [rax]
0x14003b8e2  lea     rbp, [rdx+8]
0x14003b8e6  mov     [rdx], rcx
0x14003b8e9  jmp     loc_14003B7F4
0x14003b8ee  mov     rax, [r8+r14*8+8]
0x14003b8f3  lea     rcx, [rbp+7]
0x14003b8f7  and     rcx, 0FFFFFFFFFFFFFFF8h
0x14003b8fb  movups  xmm0, xmmword ptr [rax]
0x14003b8fe  lea     rbp, [rcx+10h]
0x14003b902  movdqu  xmmword ptr [rcx], xmm0
0x14003b906  mov     [r12+r14*8+8], rcx
0x14003b90b  jmp     loc_14003B7F9
0x14003b910  cmp     ecx, 4
0x14003b913  jb      loc_14003B665
0x14003b919  jmp     loc_14003B7B3
0x14003b91e  test    rdi, rdi
0x14003b921  jnz     loc_14003B6E4
0x14003b927  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b92e  lea     rax, WPP_GLOBAL_Control
0x14003b935  mov     rsi, 0FFFFFFFFC000000Dh
0x14003b93c  cmp     rcx, rax
0x14003b93f  jz      loc_14003B64B
0x14003b945  cmp     byte ptr [rcx+29h], 2
0x14003b949  jb      loc_14003B64B
0x14003b94f  test    dword ptr [rcx+2Ch], 1000h
0x14003b956  jz      loc_14003B64B
0x14003b95c  mov     rcx, [rcx+18h]
0x14003b960  lea     edx, [rdi+0Ah]
0x14003b963  lea     r9, aFecopyincoming; "FeCopyIncomingValues"
0x14003b96a  mov     [rsp+78h+var_58], esi
0x14003b96e  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14003b975  call    WPP_SF_sd
0x14003b97a  jmp     loc_14003B64B
0x14003b97f  mov     rdx, [r8+r14*8+8]; Src
0x14003b984  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14003b988  xor     eax, eax
0x14003b98a  jmp     loc_14007D0C4
0x14003b98f  mov     r8, 0FFFFFFFFC000000Dh
0x14003b996  jmp     loc_14003B66B
0x14007d0c4  inc     rbx
0x14007d0c7  cmp     [rdx+rbx*2], ax
0x14007d0cb  jnz     short loc_14007D0C4
0x14007d0cd  lea     rbx, ds:2[rbx*2]
0x14007d0d5  mov     rcx, rbp; void *
0x14007d0d8  mov     r8, rbx; Size
0x14007d0db  call    memmove
0x14007d0e0  mov     [r12+r14*8+8], rbp
0x14007d0e5  add     rbp, rbx
0x14007d0e8  jmp     loc_14003B7F9
```
