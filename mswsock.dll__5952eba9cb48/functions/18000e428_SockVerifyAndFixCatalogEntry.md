# SockVerifyAndFixCatalogEntry

- ea: `0x18000e428`
- end: `0x18000e6b7`
- name: `SockVerifyAndFixCatalogEntry`
- size: `655`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000d000`

## callees

- `0x18000ca20`
- `0x18000db30`
- `0x18000e428`
- `0x18000f068`
- `0x180038718`
- `0x180038774`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e573`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e5e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e692`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e573`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e5e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e692`
- `ntdll!RtlFreeHeap` at `0x18000e5ae`
- `ntdll!RtlFreeHeap` at `0x18000e5ae`

## pseudocode

```c
char __fastcall SockVerifyAndFixCatalogEntry(__int64 a1, unsigned __int64 i)
{
  _BYTE *v2; // r8
  _BYTE *v3; // rsi
  __int64 v4; // r9
  char v6; // di
  char *v7; // r14
  int v8; // r15d
  int v10; // ebx
  int k; // edx
  __int64 v12; // rcx
  int v13; // edi
  int v14; // ebx
  DWORD v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  int v18; // ebx
  int v19; // edi
  int v20; // esi
  DWORD v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  int j; // edx
  __int64 v26; // rcx
  int v27; // ebx
  int v28; // edi
  DWORD CurrentProcessId; // eax
  __int64 v30; // rcx
  __int64 v31; // r8
  unsigned int v32; // [rsp+80h] [rbp+18h] BYREF
  _BYTE *v33; // [rsp+88h] [rbp+20h] BYREF

  v2 = MswsockProtocolInfoArray;
  v3 = (_BYTE *)i;
  v4 = (unsigned int)MswsockProtocolInfoCount;
  v6 = 0;
  while ( 2 )
  {
    if ( !v2 || v6 )
    {
      v33 = 0;
      v32 = 0;
      SockReleaseRwLockExclusive(a1, i, v2, v4);
      *v3 = 1;
      v10 = SockBuildMswsockProtocolInfoArray(&v33, &v32);
      SockAcquireRwLockExclusive();
      if ( v10 )
        return 0;
      if ( MswsockProtocolInfoArray )
        RtlFreeHeap(SockPrivateHeap, 0, MswsockProtocolInfoArray);
      v2 = v33;
      v4 = v32;
      MswsockProtocolInfoArray = v33;
      MswsockProtocolInfoCount = v32;
    }
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (int)i >= (int)v4 )
        goto LABEL_8;
      v7 = &v2[44 * (int)i];
      v8 = *((_DWORD *)v7 + 3);
      if ( v8 == *(_DWORD *)(a1 + 52) )
        break;
    }
    if ( !v7 )
    {
LABEL_8:
      if ( !v6 )
      {
        v6 = 1;
        continue;
      }
      for ( j = 0; j < (int)v4; ++j )
      {
        v26 = 44LL * j;
        if ( v2[v26]
          && *(_DWORD *)&v2[v26 + 24] == *(_DWORD *)(a1 + 12)
          && *(_DWORD *)&v2[v26 + 16] == *(_DWORD *)(a1 + 4)
          && *(_DWORD *)&v2[v26 + 20] == *(_DWORD *)(a1 + 8) )
        {
          v27 = *(_DWORD *)&v2[v26 + 12];
          v28 = *(_DWORD *)(a1 + 52);
          *(_DWORD *)(a1 + 52) = v27;
          *(_DWORD *)(a1 + 60) = *(_DWORD *)&v2[v26 + 8];
          *(_DWORD *)(a1 + 56) = *(_DWORD *)&v2[v26 + 4];
          *(_OWORD *)(a1 + 104) = *(_OWORD *)&v2[v26 + 28];
          if ( (xmmword_180063D60 & 2) != 0 )
          {
            CurrentProcessId = GetCurrentProcessId();
            WPP_SF_LLL(v30, 11, v31, CurrentProcessId, v28, v27);
          }
          return 1;
        }
      }
      return 0;
    }
    break;
  }
  if ( *v7 )
    return 1;
  if ( (xmmword_180063D60 & 2) != 0 )
  {
    v18 = *((_DWORD *)v7 + 5);
    v19 = *((_DWORD *)v7 + 6);
    v20 = *((_DWORD *)v7 + 4);
    v21 = GetCurrentProcessId();
    WPP_SF_LLLLL(v23, v22, v24, v21, v8, v20, v19, v18);
    v2 = MswsockProtocolInfoArray;
    LODWORD(v4) = MswsockProtocolInfoCount;
  }
  for ( k = 0; k < (int)v4; ++k )
  {
    v12 = 44LL * k;
    if ( v2[v12]
      && *(_DWORD *)&v2[v12 + 24] == *((_DWORD *)v7 + 6)
      && *(_DWORD *)&v2[v12 + 16] == *((_DWORD *)v7 + 4)
      && *(_DWORD *)&v2[v12 + 20] == *((_DWORD *)v7 + 5) )
    {
      v13 = *(_DWORD *)&v2[v12 + 12];
      *(_DWORD *)(a1 + 52) = v13;
      *(_DWORD *)(a1 + 60) = *(_DWORD *)&v2[v12 + 8];
      *(_DWORD *)(a1 + 56) = *(_DWORD *)&v2[v12 + 4];
      *(_OWORD *)(a1 + 104) = *(_OWORD *)&v2[v12 + 28];
      if ( (xmmword_180063D60 & 2) != 0 )
      {
        v14 = *((_DWORD *)v7 + 3);
        v15 = GetCurrentProcessId();
        WPP_SF_LLL(v16, 13, v17, v15, v14, v13);
      }
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000e428  mov     [rsp+arg_0], rbx
0x18000e42d  push    rbp
0x18000e42e  push    rsi
0x18000e42f  push    rdi
0x18000e430  push    r14
0x18000e432  push    r15
0x18000e434  sub     rsp, 40h
0x18000e438  mov     r8, cs:MswsockProtocolInfoArray
0x18000e43f  mov     rsi, rdx
0x18000e442  mov     r9d, cs:MswsockProtocolInfoCount
0x18000e449  mov     rbp, rcx
0x18000e44c  xor     dil, dil
0x18000e44f  test    r8, r8
0x18000e452  jz      short loc_18000E495
0x18000e454  test    dil, dil
0x18000e457  jnz     short loc_18000E495
0x18000e459  xor     edx, edx
0x18000e45b  cmp     edx, r9d
0x18000e45e  jge     short loc_18000E478
0x18000e460  movsxd  rax, edx
0x18000e463  imul    r14, rax, 2Ch ; ','
0x18000e467  add     r14, r8
0x18000e46a  mov     r15d, [r14+0Ch]
0x18000e46e  cmp     r15d, [rbp+34h]
0x18000e472  jz      short loc_18000E486
0x18000e474  inc     edx
0x18000e476  jmp     short loc_18000E45B
0x18000e478  test    dil, dil
0x18000e47b  jnz     loc_18000E628
0x18000e481  mov     dil, 1
0x18000e484  jmp     short loc_18000E44F
0x18000e486  test    r14, r14
0x18000e489  jz      short loc_18000E478
0x18000e48b  cmp     byte ptr [r14], 0
0x18000e48f  jz      short loc_18000E4EC
0x18000e491  mov     al, 1
0x18000e493  jmp     short loc_18000E4DA
0x18000e495  mov     [rsp+68h+arg_18], 0
0x18000e4a1  mov     [rsp+68h+arg_10], 0
0x18000e4ac  call    SockReleaseRwLockExclusive
0x18000e4b1  lea     rdx, [rsp+68h+arg_10]
0x18000e4b9  mov     byte ptr [rsi], 1
0x18000e4bc  lea     rcx, [rsp+68h+arg_18]
0x18000e4c4  call    SockBuildMswsockProtocolInfoArray
0x18000e4c9  mov     ebx, eax
0x18000e4cb  call    SockAcquireRwLockExclusive
0x18000e4d0  test    ebx, ebx
0x18000e4d2  jz      loc_18000E599
0x18000e4d8  xor     al, al
0x18000e4da  mov     rbx, [rsp+68h+arg_0]
0x18000e4df  add     rsp, 40h
0x18000e4e3  pop     r15
0x18000e4e5  pop     r14
0x18000e4e7  pop     rdi
0x18000e4e8  pop     rsi
0x18000e4e9  pop     rbp
0x18000e4ea  retn
0x18000e4ec  test    byte ptr cs:xmmword_180063D60, 2
0x18000e4f3  jnz     loc_18000E5DD
0x18000e4f9  xor     edx, edx
0x18000e4fb  cmp     edx, r9d
0x18000e4fe  jge     short loc_18000E4D8
0x18000e500  movsxd  rax, edx
0x18000e503  imul    rcx, rax, 2Ch ; ','
0x18000e507  cmp     byte ptr [rcx+r8], 0
0x18000e50c  jz      loc_18000E621
0x18000e512  mov     eax, [r14+18h]
0x18000e516  cmp     [rcx+r8+18h], eax
0x18000e51b  jnz     loc_18000E621
0x18000e521  mov     eax, [r14+10h]
0x18000e525  cmp     [rcx+r8+10h], eax
0x18000e52a  jnz     loc_18000E621
0x18000e530  mov     eax, [r14+14h]
0x18000e534  cmp     [rcx+r8+14h], eax
0x18000e539  jnz     loc_18000E621
0x18000e53f  mov     edi, [rcx+r8+0Ch]
0x18000e544  mov     [rbp+34h], edi
0x18000e547  mov     eax, [rcx+r8+8]
0x18000e54c  mov     [rbp+3Ch], eax
0x18000e54f  mov     eax, [rcx+r8+4]
0x18000e554  mov     [rbp+38h], eax
0x18000e557  movups  xmm0, xmmword ptr [rcx+r8+1Ch]
0x18000e55d  movdqu  xmmword ptr [rbp+68h], xmm0
0x18000e562  test    byte ptr cs:xmmword_180063D60, 2
0x18000e569  jz      loc_18000E491
0x18000e56f  mov     ebx, [r14+0Ch]
0x18000e573  call    cs:__imp_GetCurrentProcessId
0x18000e57a  nop     dword ptr [rax+rax+00h]
0x18000e57f  mov     [rsp+68h+var_40], edi
0x18000e583  mov     edx, 0Dh
0x18000e588  mov     [rsp+68h+var_48], ebx
0x18000e58c  mov     r9d, eax
0x18000e58f  call    WPP_SF_LLL
0x18000e594  jmp     loc_18000E491
0x18000e599  mov     r8, cs:MswsockProtocolInfoArray; P
0x18000e5a0  test    r8, r8
0x18000e5a3  jz      short loc_18000E5BA
0x18000e5a5  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18000e5ac  xor     edx, edx; Flags
0x18000e5ae  call    cs:__imp_RtlFreeHeap
0x18000e5b5  nop     dword ptr [rax+rax+00h]
0x18000e5ba  mov     r8, [rsp+68h+arg_18]
0x18000e5c2  mov     r9d, [rsp+68h+arg_10]
0x18000e5ca  mov     cs:MswsockProtocolInfoArray, r8
0x18000e5d1  mov     cs:MswsockProtocolInfoCount, r9d
0x18000e5d8  jmp     loc_18000E459
0x18000e5dd  mov     ebx, [r14+14h]
0x18000e5e1  mov     edi, [r14+18h]
0x18000e5e5  mov     esi, [r14+10h]
0x18000e5e9  call    cs:__imp_GetCurrentProcessId
0x18000e5f0  nop     dword ptr [rax+rax+00h]
0x18000e5f5  mov     [rsp+68h+var_30], ebx
0x18000e5f9  mov     r9d, eax
0x18000e5fc  mov     [rsp+68h+var_38], edi
0x18000e600  mov     [rsp+68h+var_40], esi
0x18000e604  mov     [rsp+68h+var_48], r15d
0x18000e609  call    WPP_SF_LLLLL
0x18000e60e  mov     r8, cs:MswsockProtocolInfoArray
0x18000e615  mov     r9d, cs:MswsockProtocolInfoCount
0x18000e61c  jmp     loc_18000E4F9
0x18000e621  inc     edx
0x18000e623  jmp     loc_18000E4FB
0x18000e628  xor     edx, edx
0x18000e62a  cmp     edx, r9d
0x18000e62d  jge     loc_18000E4D8
0x18000e633  movsxd  rax, edx
0x18000e636  imul    rcx, rax, 2Ch ; ','
0x18000e63a  cmp     byte ptr [rcx+r8], 0
0x18000e63f  jz      short loc_18000E6B0
0x18000e641  mov     eax, [rbp+0Ch]
0x18000e644  cmp     [rcx+r8+18h], eax
0x18000e649  jnz     short loc_18000E6B0
0x18000e64b  mov     eax, [rbp+4]
0x18000e64e  cmp     [rcx+r8+10h], eax
0x18000e653  jnz     short loc_18000E6B0
0x18000e655  mov     eax, [rbp+8]
0x18000e658  cmp     [rcx+r8+14h], eax
0x18000e65d  jnz     short loc_18000E6B0
0x18000e65f  mov     ebx, [rcx+r8+0Ch]
0x18000e664  mov     edi, [rbp+34h]
0x18000e667  mov     [rbp+34h], ebx
0x18000e66a  mov     eax, [rcx+r8+8]
0x18000e66f  mov     [rbp+3Ch], eax
0x18000e672  mov     eax, [rcx+r8+4]
0x18000e677  mov     [rbp+38h], eax
0x18000e67a  movups  xmm0, xmmword ptr [rcx+r8+1Ch]
0x18000e680  movdqu  xmmword ptr [rbp+68h], xmm0
0x18000e685  test    byte ptr cs:xmmword_180063D60, 2
0x18000e68c  jz      loc_18000E491
0x18000e692  call    cs:__imp_GetCurrentProcessId
0x18000e699  nop     dword ptr [rax+rax+00h]
0x18000e69e  mov     [rsp+68h+var_40], ebx
0x18000e6a2  mov     edx, 0Bh
0x18000e6a7  mov     [rsp+68h+var_48], edi
0x18000e6ab  jmp     loc_18000E58C
0x18000e6b0  inc     edx
0x18000e6b2  jmp     loc_18000E62A
```
