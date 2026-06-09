# SslExpandTrafficKeys

- ea: `0x18000c270`
- end: `0x18000c5a9`
- name: `SslExpandTrafficKeys`
- size: `825`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x18000a770`
- `0x18000c270`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180020010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000c343`
- `ntdll!RtlAllocateHeap` at `0x18000c37c`
- `ntdll!RtlAllocateHeap` at `0x18000c343`
- `ntdll!RtlAllocateHeap` at `0x18000c37c`

## string_xrefs

- `0x18000c499`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000c4e5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000c545`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x18000c591`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslExpandTrafficKeys(
        _DWORD *a1,
        _DWORD *a2,
        _DWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        __int64 a6,
        int a7)
{
  _DWORD *v8; // r14
  _DWORD *v9; // rbp
  _DWORD *v10; // rbx
  _OWORD *v11; // rdi
  _OWORD *v12; // rax
  NCRYPT_KEY_HANDLE *v13; // rdx
  NCryptKeyName **v14; // r8
  PVOID *v15; // r9
  _OWORD *v16; // rsi
  _OWORD *Heap; // rax
  _OWORD *v18; // rcx
  _OWORD *v19; // r9
  unsigned int v20; // ebp
  __int64 v22; // r9
  __int64 v23; // rcx

  v8 = a3;
  v9 = a2;
  v10 = a1;
  if ( !a1 || *a1 < 0x1B0u || a1[1] != 1145324609 || a1[3] )
    v10 = 0;
  if ( !a2 || *a2 < 0x20u || a2[1] != 1145324610 )
    v9 = 0;
  if ( !a3 || *a3 < 0x20u || a3[1] != 1145324611 )
    v8 = 0;
  if ( !v10 || !v9 || !v8 )
  {
    v20 = -2146893786;
    v22 = 3941;
    v23 = 2148073510LL;
    goto LABEL_51;
  }
  if ( !a4 && !a5 )
  {
    v20 = -2146893785;
    v22 = 3948;
    v23 = 2148073511LL;
LABEL_51:
    DebugTraceError(v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v22);
    return NormalizeNteStatus(v20, v13, v14, v15, (DWORD)a5);
  }
  if ( *((_WORD *)v10 + 16) < 4u )
  {
    v20 = -2146893783;
    v22 = 3959;
    v23 = 2148073513LL;
    goto LABEL_51;
  }
  v11 = 0;
  if ( !a4 )
  {
LABEL_22:
    v16 = 0;
    if ( a5 )
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
      v16 = Heap;
      if ( !Heap )
      {
        v20 = -2146893810;
        DebugTraceError(2148073486LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", 3985);
LABEL_35:
        if ( v11 )
          MSCryptFree(v11);
        if ( v16 )
          MSCryptFree(v16);
        return NormalizeNteStatus(v20, v13, v14, v15, (DWORD)a5);
      }
      *Heap = 0;
      Heap[1] = 0;
    }
    v18 = v16 + 1;
    v19 = v11 + 1;
    if ( !v16 )
      v18 = 0;
    if ( !v11 )
      v19 = 0;
    v20 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _OWORD *, _OWORD *, __int64, int))v10 + 38))(
            *((_QWORD *)v10 + 53),
            *((_QWORD *)v9 + 2),
            *((_QWORD *)v8 + 2),
            v19,
            v18,
            a6,
            a7);
    if ( (v20 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (_DWORD)v13,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          (unsigned int)"Status",
          v20,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
          165);
    }
    else
    {
      if ( v11 )
      {
        *(_DWORD *)v11 = 32;
        *(_QWORD *)((char *)v11 + 4) = 1145324610;
        *((_DWORD *)v11 + 3) = 1;
        *((_QWORD *)v11 + 3) = v10;
        *a4 = v11;
        v11 = 0;
        _InterlockedIncrement(v10 + 4);
      }
      if ( v16 )
      {
        *(_DWORD *)v16 = 32;
        *(_QWORD *)((char *)v16 + 4) = 1145324610;
        *((_DWORD *)v16 + 3) = 1;
        *((_QWORD *)v16 + 3) = v10;
        *a5 = v16;
        v16 = 0;
        _InterlockedIncrement(v10 + 4);
      }
      v20 = 0;
    }
    goto LABEL_35;
  }
  v12 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20u);
  v11 = v12;
  if ( v12 )
  {
    *v12 = 0;
    v12[1] = 0;
    goto LABEL_22;
  }
  v20 = -2146893810;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v13,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
      (unsigned int)"Status",
      14,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
      133);
  return NormalizeNteStatus(v20, v13, v14, v15, (DWORD)a5);
}

```

## disassembly

```asm
0x18000c270  push    rbx
0x18000c272  push    rbp
0x18000c273  push    r13
0x18000c275  push    r14
0x18000c277  push    r15
0x18000c279  sub     rsp, 40h
0x18000c27d  xor     r13d, r13d
0x18000c280  mov     r15, r9
0x18000c283  mov     r14, r8
0x18000c286  mov     rbp, rdx
0x18000c289  mov     rbx, rcx
0x18000c28c  test    rcx, rcx
0x18000c28f  jz      short loc_18000C2A8
0x18000c291  cmp     dword ptr [rcx], 1B0h
0x18000c297  jb      short loc_18000C2A8
0x18000c299  cmp     dword ptr [rcx+4], 44444441h
0x18000c2a0  jnz     short loc_18000C2A8
0x18000c2a2  cmp     [rcx+0Ch], r13d
0x18000c2a6  jz      short loc_18000C2AB
0x18000c2a8  mov     rbx, r13
0x18000c2ab  test    rdx, rdx
0x18000c2ae  jz      short loc_18000C2BE
0x18000c2b0  cmp     dword ptr [rdx], 20h ; ' '
0x18000c2b3  jb      short loc_18000C2BE
0x18000c2b5  cmp     dword ptr [rdx+4], 44444442h
0x18000c2bc  jz      short loc_18000C2C1
0x18000c2be  mov     rbp, r13
0x18000c2c1  test    r8, r8
0x18000c2c4  jz      short loc_18000C2D6
0x18000c2c6  cmp     dword ptr [r8], 20h ; ' '
0x18000c2ca  jb      short loc_18000C2D6
0x18000c2cc  cmp     dword ptr [r8+4], 44444443h
0x18000c2d4  jz      short loc_18000C2D9
0x18000c2d6  mov     r14, r13
0x18000c2d9  mov     [rsp+68h+arg_0], rsi
0x18000c2de  mov     [rsp+68h+arg_8], rdi
0x18000c2e3  mov     [rsp+68h+arg_10], r12
0x18000c2eb  test    rbx, rbx
0x18000c2ee  jz      loc_18000C581
0x18000c2f4  test    rbp, rbp
0x18000c2f7  jz      loc_18000C581
0x18000c2fd  test    r14, r14
0x18000c300  jz      loc_18000C581
0x18000c306  mov     r12, [rsp+68h+arg_20]
0x18000c30e  test    r15, r15
0x18000c311  jz      loc_18000C512
0x18000c317  mov     eax, 4
0x18000c31c  cmp     ax, [rbx+20h]
0x18000c320  ja      loc_18000C52D
0x18000c326  mov     rdi, r13
0x18000c329  test    r15, r15
0x18000c32c  jz      short loc_18000C35F
0x18000c32e  mov     rcx, gs:60h
0x18000c337  xor     edx, edx; Flags
0x18000c339  mov     r8d, 20h ; ' '; Size
0x18000c33f  mov     rcx, [rcx+30h]; HeapHandle
0x18000c343  call    cs:__imp_RtlAllocateHeap
0x18000c349  mov     rdi, rax
0x18000c34c  test    rax, rax
0x18000c34f  jz      loc_18000C4BF
0x18000c355  xorps   xmm0, xmm0
0x18000c358  movups  xmmword ptr [rax], xmm0
0x18000c35b  movups  xmmword ptr [rax+10h], xmm0
0x18000c35f  mov     rsi, r13
0x18000c362  test    r12, r12
0x18000c365  jz      short loc_18000C398
0x18000c367  mov     rcx, gs:60h
0x18000c370  xor     edx, edx; Flags
0x18000c372  mov     r8d, 20h ; ' '; Size
0x18000c378  mov     rcx, [rcx+30h]; HeapHandle
0x18000c37c  call    cs:__imp_RtlAllocateHeap
0x18000c382  mov     rsi, rax
0x18000c385  test    rax, rax
0x18000c388  jz      loc_18000C53F
0x18000c38e  xorps   xmm0, xmm0
0x18000c391  movups  xmmword ptr [rax], xmm0
0x18000c394  movups  xmmword ptr [rax+10h], xmm0
0x18000c398  test    rsi, rsi
0x18000c39b  lea     rcx, [rsi+10h]
0x18000c39f  lea     r9, [rdi+10h]
0x18000c3a3  cmovz   rcx, r13
0x18000c3a7  test    rdi, rdi
0x18000c3aa  jnz     short loc_18000C3AF
0x18000c3ac  mov     r9, r13
0x18000c3af  mov     eax, [rsp+68h+arg_30]
0x18000c3b6  mov     r8, [r14+10h]
0x18000c3ba  mov     rdx, [rbp+10h]
0x18000c3be  mov     [rsp+68h+var_38], eax
0x18000c3c2  mov     rax, [rsp+68h+arg_28]
0x18000c3ca  mov     [rsp+68h+var_40], rax
0x18000c3cf  mov     rax, [rbx+130h]
0x18000c3d6  mov     [rsp+68h+var_48], rcx
0x18000c3db  mov     rcx, [rbx+1A8h]
0x18000c3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3e7  mov     ebp, eax
0x18000c3e9  test    eax, eax
0x18000c3eb  js      loc_18000C47C
0x18000c3f1  test    rdi, rdi
0x18000c3f4  jz      short loc_18000C419
0x18000c3f6  mov     dword ptr [rdi], 20h ; ' '
0x18000c3fc  mov     qword ptr [rdi+4], 44444442h
0x18000c404  mov     dword ptr [rdi+0Ch], 1
0x18000c40b  mov     [rdi+18h], rbx
0x18000c40f  mov     [r15], rdi
0x18000c412  mov     rdi, r13
0x18000c415  lock inc dword ptr [rbx+10h]
0x18000c419  test    rsi, rsi
0x18000c41c  jz      short loc_18000C442
0x18000c41e  mov     dword ptr [rsi], 20h ; ' '
0x18000c424  mov     qword ptr [rsi+4], 44444442h
0x18000c42c  mov     dword ptr [rsi+0Ch], 1
0x18000c433  mov     [rsi+18h], rbx
0x18000c437  mov     [r12], rsi
0x18000c43b  mov     rsi, r13
0x18000c43e  lock inc dword ptr [rbx+10h]
0x18000c442  mov     ebp, r13d
0x18000c445  test    rdi, rdi
0x18000c448  jnz     loc_18000C567
0x18000c44e  test    rsi, rsi
0x18000c451  jnz     loc_18000C574
0x18000c457  mov     ecx, ebp
0x18000c459  mov     r12, [rsp+68h+arg_10]
0x18000c461  mov     rdi, [rsp+68h+arg_8]
0x18000c466  mov     rsi, [rsp+68h+arg_0]
0x18000c46b  add     rsp, 40h
0x18000c46f  pop     r15
0x18000c471  pop     r14
0x18000c473  pop     r13
0x18000c475  pop     rbp
0x18000c476  pop     rbx
0x18000c477  jmp     NormalizeNteStatus
0x18000c47c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c483  lea     rax, WPP_GLOBAL_Control
0x18000c48a  cmp     rcx, rax
0x18000c48d  jz      short loc_18000C445
0x18000c48f  test    byte ptr [rcx+1Ch], 1
0x18000c493  jz      short loc_18000C445
0x18000c495  mov     rcx, [rcx+10h]
0x18000c499  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c4a0  mov     [rsp+68h+var_38], 0FA5h
0x18000c4a8  lea     r9, aStatus; "Status"
0x18000c4af  mov     [rsp+68h+var_40], r8
0x18000c4b4  mov     dword ptr [rsp+68h+var_48], ebp
0x18000c4b8  call    WPP_SF_sDsd
0x18000c4bd  jmp     short loc_18000C445
0x18000c4bf  mov     ebp, 8009000Eh
0x18000c4c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4cb  lea     rax, WPP_GLOBAL_Control
0x18000c4d2  cmp     rcx, rax
0x18000c4d5  jz      short loc_18000C457
0x18000c4d7  test    byte ptr [rcx+1Ch], 1
0x18000c4db  jz      loc_18000C457
0x18000c4e1  mov     rcx, [rcx+10h]
0x18000c4e5  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c4ec  mov     [rsp+68h+var_38], 0F85h
0x18000c4f4  lea     r9, aStatus; "Status"
0x18000c4fb  mov     [rsp+68h+var_40], r8
0x18000c500  mov     dword ptr [rsp+68h+var_48], 8009000Eh
0x18000c508  call    WPP_SF_sDsd
0x18000c50d  jmp     loc_18000C457
0x18000c512  test    r12, r12
0x18000c515  jnz     loc_18000C317
0x18000c51b  mov     ebp, 80090027h
0x18000c520  mov     r9d, 0F6Ch
0x18000c526  mov     ecx, 80090027h
0x18000c52b  jmp     short loc_18000C591
0x18000c52d  mov     ebp, 80090029h
0x18000c532  mov     r9d, 0F77h
0x18000c538  mov     ecx, 80090029h
0x18000c53d  jmp     short loc_18000C591
0x18000c53f  mov     r9d, 0F91h
0x18000c545  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c54c  lea     rdx, aStatus; "Status"
0x18000c553  mov     ecx, 8009000Eh
0x18000c558  mov     ebp, 8009000Eh
0x18000c55d  call    DebugTraceError
0x18000c562  jmp     loc_18000C445
0x18000c567  mov     rcx, rdi
0x18000c56a  call    MSCryptFree
0x18000c56f  jmp     loc_18000C44E
0x18000c574  mov     rcx, rsi
0x18000c577  call    MSCryptFree
0x18000c57c  jmp     loc_18000C457
0x18000c581  mov     ebp, 80090026h
0x18000c586  mov     r9d, 0F65h
0x18000c58c  mov     ecx, 80090026h
0x18000c591  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c598  lea     rdx, aStatus; "Status"
0x18000c59f  call    DebugTraceError
0x18000c5a4  jmp     loc_18000C457
```
