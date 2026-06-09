# LsaDbpDsForestBuildTrustEntryForAttrBlock(_UNICODE_STRING *,_ATTRBLOCKSIMPLE *,_LSAPDS_FOREST_TRUST_BLOB * *)

- ea: `0x18002c504`
- end: `0x18002c7a1`
- name: `?LsaDbpDsForestBuildTrustEntryForAttrBlock@@YAJPEAU_UNICODE_STRING@@PEAU_ATTRBLOCKSIMPLE@@PEAPEAU_LSAPDS_FOREST_TRUST_BLOB@@@Z`
- size: `669`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, struct _ATTRBLOCKSIMPLE *, struct _LSAPDS_FOREST_TRUST_BLOB **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002cb54`

## callees

- `0x180001fb8`
- `0x18000fd40`
- `0x18002c504`
- `0x18003ad30`

## import_xrefs

- `LSASRV!LsapAllocateLsaHeap` at `0x18002c52d`
- `LSASRV!LsapAllocateLsaHeap` at `0x18002c610`
- `LSASRV!LsapAllocateLsaHeap` at `0x18002c673`
- `LSASRV!LsapAllocateLsaHeap` at `0x18002c6f3`
- `LSASRV!LsapAllocateLsaHeap` at `0x18002c52d`
- `LSASRV!LsapAllocateLsaHeap` at `0x18002c610`
- `LSASRV!LsapAllocateLsaHeap` at `0x18002c673`
- `LSASRV!LsapAllocateLsaHeap` at `0x18002c6f3`
- `LSASRV!LsapFreeLsaHeap` at `0x18002c742`
- `LSASRV!LsapFreeLsaHeap` at `0x18002c74c`
- `LSASRV!LsapFreeLsaHeap` at `0x18002c756`
- `LSASRV!LsapFreeLsaHeap` at `0x18002c75f`
- `LSASRV!LsapFreeLsaHeap` at `0x18002c742`
- `LSASRV!LsapFreeLsaHeap` at `0x18002c74c`
- `LSASRV!LsapFreeLsaHeap` at `0x18002c756`
- `LSASRV!LsapFreeLsaHeap` at `0x18002c75f`
- `ntdll!RtlLengthSid` at `0x18002c6eb`
- `ntdll!RtlLengthSid` at `0x18002c70c`
- `ntdll!RtlLengthSid` at `0x18002c6eb`
- `ntdll!RtlLengthSid` at `0x18002c70c`
- `ntdll!RtlEqualUnicodeString` at `0x18002c773`
- `ntdll!RtlEqualUnicodeString` at `0x18002c773`

## pseudocode

```c
__int64 __fastcall LsaDbpDsForestBuildTrustEntryForAttrBlock(
        struct _UNICODE_STRING *a1,
        struct _ATTRBLOCKSIMPLE *a2,
        struct _LSAPDS_FOREST_TRUST_BLOB **a3)
{
  void *LsaHeap; // rax
  void *v6; // rbx
  int v8; // edi
  unsigned __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r12
  __int64 v12; // rcx
  __int128 v13; // xmm0
  __int64 v14; // rcx
  __int64 v15; // rax
  void *v16; // rcx
  unsigned __int16 v17; // ax
  unsigned __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rax
  void *v22; // rcx
  unsigned __int16 v23; // ax
  __int64 v24; // rsi
  ULONG v25; // eax
  __int64 v26; // rax
  ULONG v27; // eax
  __int128 v28; // xmm0
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // r8

  LsaHeap = (void *)LsapAllocateLsaHeap(112);
  v6 = LsaHeap;
  if ( !LsaHeap )
    return 3221225626LL;
  v8 = 0;
  memset_0(LsaHeap, 0, 0x70u);
  v11 = 0;
  if ( *(_DWORD *)a2 )
  {
    while ( 1 )
    {
      if ( v8 < 0 )
      {
LABEL_29:
        LsapFreeLsaHeap(*((_QWORD *)v6 + 3), v9, v10);
        LsapFreeLsaHeap(*((_QWORD *)v6 + 5), v29, v30);
        LsapFreeLsaHeap(*((_QWORD *)v6 + 12), v31, v32);
        LsapFreeLsaHeap(v6, v33, v34);
        return (unsigned int)v8;
      }
      v12 = *((_QWORD *)a2 + 1);
      if ( *(_DWORD *)(v12 + 24 * v11) == 131088 )
      {
        v24 = *(_QWORD *)(*(_QWORD *)(v12 + 24 * v11 + 16) + 8LL);
        if ( *(_DWORD *)(v24 + 4) )
        {
          v25 = RtlLengthSid((PSID)(v24 + 24));
          v26 = LsapAllocateLsaHeap(v25);
          *((_QWORD *)v6 + 12) = v26;
          if ( v26 )
          {
            v27 = RtlLengthSid((PSID)(v24 + 24));
            memcpy_0(*((void **)v6 + 12), (const void *)(v24 + 24), v27);
          }
          else
          {
            v8 = -1073741670;
          }
        }
        v28 = *(_OWORD *)(v24 + 8);
        *((_BYTE *)v6 + 106) = 1;
        *((_OWORD *)v6 + 5) = v28;
        goto LABEL_27;
      }
      if ( *(_DWORD *)(v12 + 24 * v11) == 589826 )
      {
        *((_OWORD *)v6 + 3) = *(_OWORD *)*(_QWORD *)(*(_QWORD *)(v12 + 24 * v11 + 16) + 8LL);
        goto LABEL_27;
      }
      if ( *(_DWORD *)(v12 + 24 * v11) == 589852 )
      {
        v20 = (unsigned __int16)(**(_WORD **)(v12 + 24 * v11 + 16) + 2);
        *((_WORD *)v6 + 9) = v20;
        v21 = LsapAllocateLsaHeap(v20);
        *((_QWORD *)v6 + 3) = v21;
        v22 = (void *)v21;
        if ( v21 )
        {
          v23 = *((_WORD *)v6 + 9) - 2;
          *((_WORD *)v6 + 8) = v23;
          memcpy_0(v22, *(const void **)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 24 * v11 + 16) + 8LL), v23);
          v18 = **(unsigned int **)(*((_QWORD *)a2 + 1) + 24 * v11 + 16);
          v19 = *((_QWORD *)v6 + 3);
          goto LABEL_20;
        }
      }
      else
      {
        if ( *(_DWORD *)(v12 + 24 * v11) != 589911 )
        {
          if ( *(_DWORD *)(v12 + 24 * v11) == 590295 )
          {
            v13 = *(_OWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 24 * v11 + 16) + 8LL) + 8LL);
            *((_BYTE *)v6 + 107) = 1;
            *((_OWORD *)v6 + 4) = v13;
          }
          else if ( *(_DWORD *)(v12 + 24 * v11) == 590498 )
          {
            *((_BYTE *)v6 + 105) = 1;
          }
          else
          {
            v8 = -1073741811;
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                10,
                WPP_6c9a2cf316993f904ac0f2d2afcb3e00_Traceguids,
                *(unsigned int *)(v12 + 24 * v11));
          }
          goto LABEL_27;
        }
        v14 = (unsigned __int16)(**(_WORD **)(v12 + 24 * v11 + 16) + 2);
        *((_WORD *)v6 + 17) = v14;
        v15 = LsapAllocateLsaHeap(v14);
        *((_QWORD *)v6 + 5) = v15;
        v16 = (void *)v15;
        if ( v15 )
        {
          v17 = *((_WORD *)v6 + 17) - 2;
          *((_WORD *)v6 + 16) = v17;
          memcpy_0(v16, *(const void **)(*(_QWORD *)(*((_QWORD *)a2 + 1) + 24 * v11 + 16) + 8LL), v17);
          v18 = **(unsigned int **)(*((_QWORD *)a2 + 1) + 24 * v11 + 16);
          v19 = *((_QWORD *)v6 + 5);
LABEL_20:
          v9 = v18 >> 1;
          *(_WORD *)(v19 + 2 * v9) = 0;
          goto LABEL_27;
        }
      }
      v8 = -1073741670;
LABEL_27:
      v11 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v11 >= *(_DWORD *)a2 )
      {
        if ( v8 >= 0 )
          break;
        goto LABEL_29;
      }
    }
  }
  if ( RtlEqualUnicodeString(a1, (PCUNICODE_STRING)v6 + 1, 1u) )
    *((_WORD *)v6 + 52) = 1;
  *a3 = (struct _LSAPDS_FOREST_TRUST_BLOB *)v6;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002c504  mov     [rsp+arg_8], rbx
0x18002c509  mov     [rsp+arg_10], rsi
0x18002c50e  mov     [rsp+String1], rcx
0x18002c513  push    rdi
0x18002c514  push    r12
0x18002c516  push    r13
0x18002c518  push    r14
0x18002c51a  push    r15
0x18002c51c  sub     rsp, 20h
0x18002c520  mov     esi, 70h ; 'p'
0x18002c525  mov     r13, r8
0x18002c528  mov     ecx, esi
0x18002c52a  mov     r14, rdx
0x18002c52d  call    cs:__imp_LsapAllocateLsaHeap
0x18002c533  mov     rbx, rax
0x18002c536  test    rax, rax
0x18002c539  jnz     short loc_18002C545
0x18002c53b  mov     eax, 0C000009Ah
0x18002c540  jmp     loc_18002C789
0x18002c545  mov     r8, rsi; Size
0x18002c548  xor     edx, edx; Val
0x18002c54a  mov     rcx, rbx; void *
0x18002c54d  xor     edi, edi
0x18002c54f  call    memset_0
0x18002c554  xor     r12d, r12d
0x18002c557  cmp     [r14], edi
0x18002c55a  jbe     loc_18002C767
0x18002c560  test    edi, edi
0x18002c562  js      loc_18002C73E
0x18002c568  mov     rcx, [r14+8]
0x18002c56c  lea     rsi, [r12+r12*2]
0x18002c570  mov     r9d, [rcx+rsi*8]
0x18002c574  mov     eax, r9d
0x18002c577  sub     eax, 20010h
0x18002c57c  jz      loc_18002C6D5
0x18002c582  sub     eax, 6FFF2h
0x18002c587  jz      loc_18002C6C2
0x18002c58d  sub     eax, 1Ah
0x18002c590  jz      loc_18002C660
0x18002c596  sub     eax, 3Bh ; ';'
0x18002c599  jz      short loc_18002C5FD
0x18002c59b  sub     eax, 180h
0x18002c5a0  jz      short loc_18002C5E2
0x18002c5a2  cmp     eax, 0CBh
0x18002c5a7  jz      short loc_18002C5D9
0x18002c5a9  mov     edi, 0C000000Dh
0x18002c5ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c5b5  test    byte ptr [rcx+1Ch], 8
0x18002c5b9  jz      loc_18002C72E
0x18002c5bf  mov     rcx, [rcx+10h]
0x18002c5c3  lea     r8, WPP_6c9a2cf316993f904ac0f2d2afcb3e00_Traceguids
0x18002c5ca  mov     edx, 0Ah
0x18002c5cf  call    WPP_SF_d
0x18002c5d4  jmp     loc_18002C72E
0x18002c5d9  mov     byte ptr [rbx+69h], 1
0x18002c5dd  jmp     loc_18002C72E
0x18002c5e2  mov     rax, [rcx+rsi*8+10h]
0x18002c5e7  mov     rcx, [rax+8]
0x18002c5eb  movups  xmm0, xmmword ptr [rcx+8]
0x18002c5ef  mov     byte ptr [rbx+6Bh], 1
0x18002c5f3  movdqu  xmmword ptr [rbx+40h], xmm0
0x18002c5f8  jmp     loc_18002C72E
0x18002c5fd  mov     rax, [rcx+rsi*8+10h]
0x18002c602  movzx   ecx, word ptr [rax]
0x18002c605  add     cx, 2
0x18002c609  movzx   ecx, cx
0x18002c60c  mov     [rbx+22h], cx
0x18002c610  call    cs:__imp_LsapAllocateLsaHeap
0x18002c616  mov     [rbx+28h], rax
0x18002c61a  mov     rcx, rax; void *
0x18002c61d  test    rax, rax
0x18002c620  jnz     short loc_18002C62C
0x18002c622  mov     edi, 0C000009Ah
0x18002c627  jmp     loc_18002C72E
0x18002c62c  movzx   eax, word ptr [rbx+22h]
0x18002c630  sub     ax, 2
0x18002c634  movzx   r8d, ax; Size
0x18002c638  mov     [rbx+20h], r8w
0x18002c63d  mov     rax, [r14+8]
0x18002c641  mov     rdx, [rax+rsi*8+10h]
0x18002c646  mov     rdx, [rdx+8]; Src
0x18002c64a  call    memcpy_0
0x18002c64f  mov     rax, [r14+8]
0x18002c653  mov     rcx, [rax+rsi*8+10h]
0x18002c658  mov     edx, [rcx]
0x18002c65a  mov     rcx, [rbx+28h]
0x18002c65e  jmp     short loc_18002C6B7
0x18002c660  mov     rax, [rcx+rsi*8+10h]
0x18002c665  movzx   ecx, word ptr [rax]
0x18002c668  add     cx, 2
0x18002c66c  movzx   ecx, cx
0x18002c66f  mov     [rbx+12h], cx
0x18002c673  call    cs:__imp_LsapAllocateLsaHeap
0x18002c679  mov     [rbx+18h], rax
0x18002c67d  mov     rcx, rax; void *
0x18002c680  test    rax, rax
0x18002c683  jz      short loc_18002C622
0x18002c685  movzx   eax, word ptr [rbx+12h]
0x18002c689  sub     ax, 2
0x18002c68d  movzx   r8d, ax; Size
0x18002c691  mov     [rbx+10h], r8w
0x18002c696  mov     rax, [r14+8]
0x18002c69a  mov     rdx, [rax+rsi*8+10h]
0x18002c69f  mov     rdx, [rdx+8]; Src
0x18002c6a3  call    memcpy_0
0x18002c6a8  mov     rax, [r14+8]
0x18002c6ac  mov     rcx, [rax+rsi*8+10h]
0x18002c6b1  mov     edx, [rcx]
0x18002c6b3  mov     rcx, [rbx+18h]
0x18002c6b7  shr     rdx, 1
0x18002c6ba  xor     eax, eax
0x18002c6bc  mov     [rcx+rdx*2], ax
0x18002c6c0  jmp     short loc_18002C72E
0x18002c6c2  mov     rax, [rcx+rsi*8+10h]
0x18002c6c7  mov     rcx, [rax+8]
0x18002c6cb  movups  xmm0, xmmword ptr [rcx]
0x18002c6ce  movdqu  xmmword ptr [rbx+30h], xmm0
0x18002c6d3  jmp     short loc_18002C72E
0x18002c6d5  mov     rax, [rcx+rsi*8+10h]
0x18002c6da  mov     rsi, [rax+8]
0x18002c6de  cmp     dword ptr [rsi+4], 0
0x18002c6e2  jbe     short loc_18002C721
0x18002c6e4  lea     r15, [rsi+18h]
0x18002c6e8  mov     rcx, r15; Sid
0x18002c6eb  call    cs:__imp_RtlLengthSid
0x18002c6f1  mov     ecx, eax
0x18002c6f3  call    cs:__imp_LsapAllocateLsaHeap
0x18002c6f9  mov     [rbx+60h], rax
0x18002c6fd  test    rax, rax
0x18002c700  jnz     short loc_18002C709
0x18002c702  mov     edi, 0C000009Ah
0x18002c707  jmp     short loc_18002C721
0x18002c709  mov     rcx, r15; Sid
0x18002c70c  call    cs:__imp_RtlLengthSid
0x18002c712  mov     rcx, [rbx+60h]; void *
0x18002c716  mov     rdx, r15; Src
0x18002c719  mov     r8d, eax; Size
0x18002c71c  call    memcpy_0
0x18002c721  movups  xmm0, xmmword ptr [rsi+8]
0x18002c725  mov     byte ptr [rbx+6Ah], 1
0x18002c729  movdqu  xmmword ptr [rbx+50h], xmm0
0x18002c72e  inc     r12d
0x18002c731  cmp     r12d, [r14]
0x18002c734  jb      loc_18002C560
0x18002c73a  test    edi, edi
0x18002c73c  jns     short loc_18002C767
0x18002c73e  mov     rcx, [rbx+18h]
0x18002c742  call    cs:__imp_LsapFreeLsaHeap
0x18002c748  mov     rcx, [rbx+28h]
0x18002c74c  call    cs:__imp_LsapFreeLsaHeap
0x18002c752  mov     rcx, [rbx+60h]
0x18002c756  call    cs:__imp_LsapFreeLsaHeap
0x18002c75c  mov     rcx, rbx
0x18002c75f  call    cs:__imp_LsapFreeLsaHeap
0x18002c765  jmp     short loc_18002C787
0x18002c767  mov     rcx, [rsp+48h+String1]; String1
0x18002c76c  lea     rdx, [rbx+10h]; String2
0x18002c770  mov     r8b, 1; CaseInsensitive
0x18002c773  call    cs:__imp_RtlEqualUnicodeString
0x18002c779  test    al, al
0x18002c77b  jz      short loc_18002C783
0x18002c77d  mov     word ptr [rbx+68h], 1
0x18002c783  mov     [r13+0], rbx
0x18002c787  mov     eax, edi
0x18002c789  mov     rbx, [rsp+48h+arg_8]
0x18002c78e  mov     rsi, [rsp+48h+arg_10]
0x18002c793  add     rsp, 20h
0x18002c797  pop     r15
0x18002c799  pop     r14
0x18002c79b  pop     r13
0x18002c79d  pop     r12
0x18002c79f  pop     rdi
0x18002c7a0  retn
```
