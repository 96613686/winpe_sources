# SpInitUserModeContext

- ea: `0x180005d30`
- end: `0x180006708`
- name: `SpInitUserModeContext`
- size: `2520`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180005260`

## callees

- `0x180004e60`
- `0x180005d30`
- `0x180006710`
- `0x180006c90`
- `0x180007700`
- `0x18002ee3c`
- `0x18002ee7c`
- `0x18002f014`
- `0x18002fb50`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800064c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006521`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006531`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800064c7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006521`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006531`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000626b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000626b`
- `ntdll!RtlReleaseResource` at `0x18000640a`
- `ntdll!RtlReleaseResource` at `0x18000640a`
- `bcrypt!BCryptFinishHash` at `0x180005eba`
- `bcrypt!BCryptFinishHash` at `0x180005f85`
- `bcrypt!BCryptFinishHash` at `0x180006051`
- `bcrypt!BCryptFinishHash` at `0x180006119`
- `bcrypt!BCryptFinishHash` at `0x180005eba`
- `bcrypt!BCryptFinishHash` at `0x180005f85`
- `bcrypt!BCryptFinishHash` at `0x180006051`
- `bcrypt!BCryptFinishHash` at `0x180006119`
- `bcrypt!BCryptDestroyHash` at `0x180005eca`
- `bcrypt!BCryptDestroyHash` at `0x180005f95`
- `bcrypt!BCryptDestroyHash` at `0x180006061`
- `bcrypt!BCryptDestroyHash` at `0x180006129`
- `bcrypt!BCryptDestroyHash` at `0x1800065e8`
- `bcrypt!BCryptDestroyHash` at `0x180006627`
- `bcrypt!BCryptDestroyHash` at `0x18000665a`
- `bcrypt!BCryptDestroyHash` at `0x18000668d`
- `bcrypt!BCryptDestroyHash` at `0x180005eca`
- `bcrypt!BCryptDestroyHash` at `0x180005f95`
- `bcrypt!BCryptDestroyHash` at `0x180006061`
- `bcrypt!BCryptDestroyHash` at `0x180006129`
- `bcrypt!BCryptDestroyHash` at `0x1800065e8`
- `bcrypt!BCryptDestroyHash` at `0x180006627`
- `bcrypt!BCryptDestroyHash` at `0x18000665a`
- `bcrypt!BCryptDestroyHash` at `0x18000668d`
- `bcrypt!BCryptHashData` at `0x180005e7d`
- `bcrypt!BCryptHashData` at `0x180005e9d`
- `bcrypt!BCryptHashData` at `0x180005f48`
- `bcrypt!BCryptHashData` at `0x180005f68`
- `bcrypt!BCryptHashData` at `0x180006014`
- `bcrypt!BCryptHashData` at `0x180006034`
- `bcrypt!BCryptHashData` at `0x1800060dc`
- `bcrypt!BCryptHashData` at `0x1800060fc`
- `bcrypt!BCryptHashData` at `0x180005e7d`
- `bcrypt!BCryptHashData` at `0x180005e9d`
- `bcrypt!BCryptHashData` at `0x180005f48`
- `bcrypt!BCryptHashData` at `0x180005f68`
- `bcrypt!BCryptHashData` at `0x180006014`
- `bcrypt!BCryptHashData` at `0x180006034`
- `bcrypt!BCryptHashData` at `0x1800060dc`
- `bcrypt!BCryptHashData` at `0x1800060fc`
- `bcrypt!BCryptCreateHash` at `0x180005e60`
- `bcrypt!BCryptCreateHash` at `0x180005f2b`
- `bcrypt!BCryptCreateHash` at `0x180005ff4`
- `bcrypt!BCryptCreateHash` at `0x1800060bc`
- `bcrypt!BCryptCreateHash` at `0x180005e60`
- `bcrypt!BCryptCreateHash` at `0x180005f2b`
- `bcrypt!BCryptCreateHash` at `0x180005ff4`
- `bcrypt!BCryptCreateHash` at `0x1800060bc`
- `SspiCli!FreeContextBuffer` at `0x18000642a`
- `SspiCli!FreeContextBuffer` at `0x18000642a`

## pseudocode

```c
__int64 __fastcall SpInitUserModeContext(struct _LIST_ENTRY *a1, __int64 a2)
{
  _QWORD *v4; // rcx
  __int64 v5; // rsi
  struct _LIST_ENTRY near **v6; // rax
  struct _LIST_ENTRY near **v7; // rdi
  struct _LIST_ENTRY *v8; // rax
  __int64 v9; // r9
  int v10; // eax
  __int128 v11; // xmm0
  ULONG v12; // r15d
  NTSTATUS v13; // ebx
  unsigned __int8 *v14; // r12
  struct _LIST_ENTRY *v15; // rax
  _DWORD *v16; // rbx
  struct _LIST_ENTRY *v17; // r14
  struct _LIST_ENTRY *v18; // rcx
  void **v19; // r15
  _DWORD *v20; // rax
  unsigned int v21; // ecx
  unsigned int v22; // edx
  unsigned int v23; // eax
  __int64 v24; // rsi
  struct _RTL_RESOURCE *v25; // r14
  struct _LIST_ENTRY near **v26; // rcx
  struct _LIST_ENTRY near *v27; // rax
  SIZE_T v28; // rdx
  struct _LIST_ENTRY *v29; // rax
  SIZE_T v30; // rdx
  struct _LIST_ENTRY *v31; // rax
  void *v33; // rcx
  int TokenDacl; // eax
  __int64 v35; // rdx
  _QWORD *v36; // rcx
  __int64 v37; // rdx
  struct _LIST_ENTRY *v38; // rax
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-30h] BYREF
  UCHAR pbOutput[16]; // [rsp+48h] [rbp-28h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, a1);
    v4 = WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)a2 < 0xA8u )
  {
    v13 = -1073741811;
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
    {
      v35 = 31;
LABEL_100:
      WPP_SF_(v4[2], v35, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids);
      goto LABEL_82;
    }
  }
  else
  {
    v5 = *(_QWORD *)(a2 + 8);
    if ( NtLmState == 1 )
      v6 = (struct _LIST_ENTRY near **)((__int64 (__fastcall *)(__int64))LsaFunctions->AllocatePrivateHeap)(280);
    else
      v6 = (struct _LIST_ENTRY near **)LocalAlloc(0x40u, 0x118u);
    v7 = v6;
    if ( v6 )
    {
      v6[22] = *(struct _LIST_ENTRY near **)(v5 + 40);
      v8 = (struct _LIST_ENTRY *)*(int *)(v5 + 8);
      if ( (_DWORD)v8 )
      {
        v33 = (void *)*(int *)(v5 + 8);
        v7[7] = v8;
        TokenDacl = SspCreateTokenDacl(v33);
        v13 = TokenDacl;
        if ( TokenDacl < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids,
              (unsigned int)TokenDacl);
          goto LABEL_97;
        }
      }
      v7[5] = a1;
      v9 = *(unsigned int *)(v5 + 4);
      *((_DWORD *)v7 + 12) = v9;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, v9);
      v10 = *((_DWORD *)v7 + 12);
      *((_DWORD *)v7 + 42) = 1;
      v11 = *(_OWORD *)(v5 + 20);
      *(_OWORD *)((char *)v7 + 148) = v11;
      if ( (v10 & 0x80000) != 0 )
      {
        if ( (v10 & 0x20000000) != 0 )
        {
          v12 = 16;
        }
        else
        {
          v12 = 5;
          if ( v10 < 0 )
            v12 = 7;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, v12);
        phHash = 0;
        v13 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, &phHash, 0, 0, 0, 0, 0);
        if ( v13 < 0
          || (v13 = BCryptHashData(phHash, (PUCHAR)v7 + 148, v12, 0), v13 < 0)
          || (v13 = BCryptHashData(
                      phHash,
                      (PUCHAR)"session key to client-to-server sealing key magic constant",
                      0x3Bu,
                      0),
              v13 < 0)
          || (v13 = BCryptFinishHash(phHash, pbOutput, 0x10u, 0), v13 < 0)
          || (v13 = BCryptDestroyHash(phHash), v13 < 0) )
        {
          if ( phHash )
            BCryptDestroyHash(phHash);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids);
          goto LABEL_97;
        }
        v14 = (unsigned __int8 *)v7 + 228;
        if ( v7[22] )
          *(_OWORD *)((char *)v7 + 244) = *(_OWORD *)pbOutput;
        else
          *(_OWORD *)v14 = *(_OWORD *)pbOutput;
        phHash = 0;
        v13 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, &phHash, 0, 0, 0, 0, 0);
        if ( v13 < 0
          || (v13 = BCryptHashData(phHash, (PUCHAR)v7 + 148, v12, 0), v13 < 0)
          || (v13 = BCryptHashData(
                      phHash,
                      (PUCHAR)"session key to server-to-client sealing key magic constant",
                      0x3Bu,
                      0),
              v13 < 0)
          || (v13 = BCryptFinishHash(phHash, pbOutput, 0x10u, 0), v13 < 0)
          || (v13 = BCryptDestroyHash(phHash), v13 < 0) )
        {
          if ( phHash )
            BCryptDestroyHash(phHash);
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_97;
          v37 = 37;
          goto LABEL_121;
        }
        if ( v7[22] )
          *(_OWORD *)v14 = *(_OWORD *)pbOutput;
        else
          *(_OWORD *)((char *)v7 + 244) = *(_OWORD *)pbOutput;
        phHash = 0;
        v13 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, &phHash, 0, 0, 0, 0, 0);
        if ( v13 < 0
          || (v13 = BCryptHashData(phHash, (PUCHAR)v7 + 148, 0x10u, 0), v13 < 0)
          || (v13 = BCryptHashData(
                      phHash,
                      (PUCHAR)"session key to client-to-server signing key magic constant",
                      0x3Bu,
                      0),
              v13 < 0)
          || (v13 = BCryptFinishHash(phHash, pbOutput, 0x10u, 0), v13 < 0)
          || (v13 = BCryptDestroyHash(phHash), v13 < 0) )
        {
          if ( phHash )
            BCryptDestroyHash(phHash);
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_97;
          v37 = 38;
          goto LABEL_121;
        }
        if ( v7[22] )
          *(_OWORD *)((char *)v7 + 212) = *(_OWORD *)pbOutput;
        else
          *(_OWORD *)((char *)v7 + 196) = *(_OWORD *)pbOutput;
        phHash = 0;
        v13 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, &phHash, 0, 0, 0, 0, 0);
        if ( v13 < 0
          || (v13 = BCryptHashData(phHash, (PUCHAR)v7 + 148, 0x10u, 0), v13 < 0)
          || (v13 = BCryptHashData(
                      phHash,
                      (PUCHAR)"session key to server-to-client signing key magic constant",
                      0x3Bu,
                      0),
              v13 < 0)
          || (v13 = BCryptFinishHash(phHash, pbOutput, 0x10u, 0), v13 < 0)
          || (v13 = BCryptDestroyHash(phHash), v13 < 0) )
        {
          if ( phHash )
          {
            BCryptDestroyHash(phHash);
            phHash = 0;
          }
          v36 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_97;
          v37 = 39;
LABEL_121:
          WPP_SF_(v36[2], v37, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids);
LABEL_97:
          FreeUserContext((struct _NTLM_CLIENT_CONTEXT *)v7);
          v4 = WPP_GLOBAL_Control;
          goto LABEL_83;
        }
        phHash = 0;
        if ( v7[22] )
          *(_OWORD *)((char *)v7 + 196) = *(_OWORD *)pbOutput;
        else
          *(_OWORD *)((char *)v7 + 212) = *(_OWORD *)pbOutput;
        v15 = (struct _LIST_ENTRY *)((char *)v7 + 124);
        v16 = (_DWORD *)v7 + 31;
        v17 = (struct _LIST_ENTRY *)(v7 + 15);
        v18 = (struct _LIST_ENTRY *)(v7 + 14);
        v19 = (void **)(v7 + 13);
      }
      else
      {
        v14 = (unsigned __int8 *)v7 + 228;
        v19 = (void **)(v7 + 13);
        v17 = (struct _LIST_ENTRY *)(v7 + 15);
        v18 = (struct _LIST_ENTRY *)(v7 + 13);
        *(_OWORD *)((char *)v7 + 228) = v11;
        v15 = (struct _LIST_ENTRY *)(v7 + 15);
        v16 = (_DWORD *)v7 + 31;
        *(_OWORD *)((char *)v7 + 244) = v11;
        *(_OWORD *)((char *)v7 + 196) = v11;
        *(_OWORD *)((char *)v7 + 212) = v11;
      }
      v7[11] = (struct _LIST_ENTRY near *)v19;
      v7[12] = v18;
      v7[9] = v17;
      v7[10] = v15;
      if ( *(_DWORD *)(v5 + 60) )
      {
        v28 = *(unsigned int *)(v5 + 64);
        if ( NtLmState == 1 )
          v29 = (struct _LIST_ENTRY *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocatePrivateHeap)((unsigned int)v28);
        else
          v29 = (struct _LIST_ENTRY *)LocalAlloc(0x40u, v28);
        v7[16] = v29;
        if ( !v29 )
          goto LABEL_124;
        memcpy_0(v29, (const void *)(v5 + *(unsigned int *)(v5 + 60)), *(unsigned int *)(v5 + 64));
        v20 = (_DWORD *)v7 + 31;
      }
      else
      {
        v7[16] = 0;
        v20 = v16;
      }
      if ( *(_DWORD *)(v5 + 68) )
      {
        v38 = (struct _LIST_ENTRY *)NtLmAllocate(*(unsigned int *)(v5 + 72));
        v7[17] = v38;
        if ( !v38 )
          goto LABEL_124;
        *((_DWORD *)v7 + 36) = *(_DWORD *)(v5 + 72);
        memcpy_0(v38, (const void *)(v5 + *(unsigned int *)(v5 + 68)), *(unsigned int *)(v5 + 72));
        v20 = v16;
      }
      if ( !*(_DWORD *)(v5 + 140) )
      {
        v16 = v20;
        goto LABEL_61;
      }
      v30 = *(unsigned int *)(v5 + 144);
      if ( NtLmState == 1 )
        v31 = (struct _LIST_ENTRY *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocatePrivateHeap)((unsigned int)v30);
      else
        v31 = (struct _LIST_ENTRY *)LocalAlloc(0x40u, v30);
      v7[33] = v31;
      if ( v31 )
      {
        *((_DWORD *)v7 + 68) = *(_DWORD *)(v5 + 144);
        memcpy_0(v31, (const void *)(v5 + *(unsigned int *)(v5 + 140)), *(unsigned int *)(v5 + 144));
LABEL_61:
        v21 = *((_DWORD *)v7 + 12);
        LODWORD(v17->Flink) = *(_DWORD *)(v5 + 12);
        *v16 = *(_DWORD *)(v5 + 16);
        v13 = SspRc4Key(v21, v19, v14);
        if ( v13 < 0 )
          goto LABEL_97;
        v13 = SspRc4Key(*((_DWORD *)v7 + 12), (void **)v7 + 14, (unsigned __int8 *)v7 + 244);
        if ( v13 < 0 )
          goto LABEL_97;
        v22 = *((_DWORD *)v7 + 10);
        v7[23] = *(struct _LIST_ENTRY near **)(v5 + 48);
        *((_DWORD *)v7 + 48) = *(_DWORD *)(v5 + 56);
        *((_DWORD *)v7 + 41) = 1954051171;
        v23 = (v22 >> 4) + HIWORD(v22) + HIBYTE(v22) + v22 + (v22 >> 8);
        v24 = (unsigned __int8)(v23 + (v23 >> 4));
        v25 = (struct _RTL_RESOURCE *)&(&NtLmUserContextLock)[12 * ((unsigned int)v24 & (NtLmUserContextLockCount - 1))];
        RtlAcquireResourceExclusive(v25, 1u);
        v26 = &(&NtLmUserContextList)[2 * (unsigned int)v24];
        v27 = *v26;
        if ( (struct _LIST_ENTRY near **)(*v26)->Blink != v26 )
          __fastfail(3u);
        ++*((_DWORD *)&NtLmUserContextCount + v24);
        v7[1] = (struct _LIST_ENTRY near *)v26;
        *v7 = v27;
        v27->Blink = (struct _LIST_ENTRY *)v7;
        *v26 = (struct _LIST_ENTRY near *)v7;
        RtlReleaseResource(v25);
LABEL_82:
        v4 = WPP_GLOBAL_Control;
        goto LABEL_83;
      }
LABEL_124:
      v13 = -1073741670;
      goto LABEL_97;
    }
    v13 = -1073741670;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v35 = 32;
      goto LABEL_100;
    }
  }
LABEL_83:
  if ( *(_QWORD *)(a2 + 8) )
  {
    FreeContextBuffer(*(PVOID *)(a2 + 8));
    *(_QWORD *)(a2 + 8) = 0;
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x100) != 0 )
    WPP_SF_d(v4[2], 40, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, (unsigned int)v13);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180005d30  push    rbp
0x180005d32  push    rbx
0x180005d33  push    r12
0x180005d35  push    r13
0x180005d37  push    r14
0x180005d39  mov     rbp, rsp
0x180005d3c  sub     rsp, 70h
0x180005d40  mov     rax, cs:__security_cookie
0x180005d47  xor     rax, rsp
0x180005d4a  mov     [rbp+var_18], rax
0x180005d4e  mov     r13, rdx
0x180005d51  mov     r14, rcx
0x180005d54  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d5b  lea     r12, WPP_GLOBAL_Control
0x180005d62  cmp     rcx, r12
0x180005d65  jz      short loc_180005D74
0x180005d67  test    dword ptr [rcx+1Ch], 100h
0x180005d6e  jnz     loc_18000653C
0x180005d74  mov     [rsp+70h+arg_10], rsi
0x180005d7c  xor     ebx, ebx
0x180005d7e  cmp     dword ptr [r13+0], 0A8h
0x180005d86  mov     [rsp+70h+var_8], rdi
0x180005d8b  mov     [rsp+70h+var_10], r15
0x180005d90  jb      loc_1800064D2
0x180005d96  cmp     cs:NtLmState, 1
0x180005d9d  mov     rsi, [r13+8]
0x180005da1  jnz     loc_1800064BD
0x180005da7  mov     rax, cs:LsaFunctions
0x180005dae  mov     ecx, 118h
0x180005db3  mov     rax, [rax+180h]
0x180005dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dbf  mov     rdi, rax
0x180005dc2  test    rax, rax
0x180005dc5  jz      loc_18000657A
0x180005dcb  mov     rax, [rsi+28h]
0x180005dcf  mov     [rdi+0B0h], rax
0x180005dd6  movsxd  rax, dword ptr [rsi+8]
0x180005dda  test    eax, eax
0x180005ddc  jnz     loc_1800064A0
0x180005de2  mov     [rdi+28h], r14
0x180005de6  mov     r9d, [rsi+4]
0x180005dea  mov     [rdi+30h], r9d
0x180005dee  mov     rcx, cs:WPP_GLOBAL_Control
0x180005df5  cmp     rcx, r12
0x180005df8  jnz     loc_180006295
0x180005dfe  mov     eax, [rdi+30h]
0x180005e01  mov     dword ptr [rdi+0A8h], 1
0x180005e0b  movups  xmm0, xmmword ptr [rsi+14h]
0x180005e0f  movups  xmmword ptr [rdi+94h], xmm0
0x180005e16  bt      eax, 13h
0x180005e1a  jnb     loc_1800062BC
0x180005e20  bt      eax, 1Dh
0x180005e24  jnb     loc_1800065D2
0x180005e2a  mov     r15d, 10h
0x180005e30  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e37  cmp     rcx, r12
0x180005e3a  jnz     loc_1800062F4
0x180005e40  mov     [rsp+70h+dwFlags], ebx; dwFlags
0x180005e44  lea     rdx, [rbp+phHash]; phHash
0x180005e48  mov     [rsp+70h+cbSecret], ebx; cbSecret
0x180005e4c  xor     r9d, r9d; cbHashObject
0x180005e4f  xor     r8d, r8d; pbHashObject
0x180005e52  mov     [rsp+70h+pbSecret], rbx; pbSecret
0x180005e57  mov     ecx, 21h ; '!'; hAlgorithm
0x180005e5c  mov     [rbp+phHash], rbx
0x180005e60  call    cs:__imp_BCryptCreateHash
0x180005e66  mov     ebx, eax
0x180005e68  test    eax, eax
0x180005e6a  js      short loc_180005ED6
0x180005e6c  mov     rcx, [rbp+phHash]; hHash
0x180005e70  lea     rdx, [rdi+94h]; pbInput
0x180005e77  xor     r9d, r9d; dwFlags
0x180005e7a  mov     r8d, r15d; cbInput
0x180005e7d  call    cs:__imp_BCryptHashData
0x180005e83  mov     ebx, eax
0x180005e85  test    eax, eax
0x180005e87  js      short loc_180005ED6
0x180005e89  mov     rcx, [rbp+phHash]; hHash
0x180005e8d  lea     rdx, pbInput; "session key to client-to-server sealing"...
0x180005e94  xor     r9d, r9d; dwFlags
0x180005e97  mov     r8d, 3Bh ; ';'; cbInput
0x180005e9d  call    cs:__imp_BCryptHashData
0x180005ea3  mov     ebx, eax
0x180005ea5  test    eax, eax
0x180005ea7  js      short loc_180005ED6
0x180005ea9  mov     rcx, [rbp+phHash]; hHash
0x180005ead  lea     rdx, [rbp+pbOutput]; pbOutput
0x180005eb1  xor     r9d, r9d; dwFlags
0x180005eb4  mov     r8d, 10h; cbOutput
0x180005eba  call    cs:__imp_BCryptFinishHash
0x180005ec0  mov     ebx, eax
0x180005ec2  test    eax, eax
0x180005ec4  js      short loc_180005ED6
0x180005ec6  mov     rcx, [rbp+phHash]; hHash
0x180005eca  call    cs:__imp_BCryptDestroyHash
0x180005ed0  mov     ebx, eax
0x180005ed2  test    eax, eax
0x180005ed4  jns     short loc_180005EEB
0x180005ed6  mov     rcx, [rbp+phHash]; hHash
0x180005eda  test    rcx, rcx
0x180005edd  jnz     loc_1800065E8
0x180005ee3  test    ebx, ebx
0x180005ee5  js      loc_1800065F3
0x180005eeb  cmp     qword ptr [rdi+0B0h], 0
0x180005ef3  lea     r12, [rdi+0E4h]
0x180005efa  movups  xmm0, xmmword ptr [rbp+pbOutput]
0x180005efe  jnz     loc_1800063E5
0x180005f04  movups  xmmword ptr [r12], xmm0
0x180005f09  xor     eax, eax
0x180005f0b  lea     rdx, [rbp+phHash]; phHash
0x180005f0f  mov     [rsp+70h+dwFlags], eax; dwFlags
0x180005f13  xor     r9d, r9d; cbHashObject
0x180005f16  mov     [rsp+70h+cbSecret], eax; cbSecret
0x180005f1a  xor     r8d, r8d; pbHashObject
0x180005f1d  mov     ecx, 21h ; '!'; hAlgorithm
0x180005f22  mov     [rsp+70h+pbSecret], rax; pbSecret
0x180005f27  mov     [rbp+phHash], rax
0x180005f2b  call    cs:__imp_BCryptCreateHash
0x180005f31  mov     ebx, eax
0x180005f33  test    eax, eax
0x180005f35  js      short loc_180005FA1
0x180005f37  mov     rcx, [rbp+phHash]; hHash
0x180005f3b  lea     rdx, [rdi+94h]; pbInput
0x180005f42  xor     r9d, r9d; dwFlags
0x180005f45  mov     r8d, r15d; cbInput
0x180005f48  call    cs:__imp_BCryptHashData
0x180005f4e  mov     ebx, eax
0x180005f50  test    eax, eax
0x180005f52  js      short loc_180005FA1
0x180005f54  mov     rcx, [rbp+phHash]; hHash
0x180005f58  lea     rdx, aSessionKeyToSe_0; "session key to server-to-client sealing"...
0x180005f5f  xor     r9d, r9d; dwFlags
0x180005f62  mov     r8d, 3Bh ; ';'; cbInput
0x180005f68  call    cs:__imp_BCryptHashData
0x180005f6e  mov     ebx, eax
0x180005f70  test    eax, eax
0x180005f72  js      short loc_180005FA1
0x180005f74  mov     rcx, [rbp+phHash]; hHash
0x180005f78  lea     rdx, [rbp+pbOutput]; pbOutput
0x180005f7c  xor     r9d, r9d; dwFlags
0x180005f7f  mov     r8d, 10h; cbOutput
0x180005f85  call    cs:__imp_BCryptFinishHash
0x180005f8b  mov     ebx, eax
0x180005f8d  test    eax, eax
0x180005f8f  js      short loc_180005FA1
0x180005f91  mov     rcx, [rbp+phHash]; hHash
0x180005f95  call    cs:__imp_BCryptDestroyHash
0x180005f9b  mov     ebx, eax
0x180005f9d  test    eax, eax
0x180005f9f  jns     short loc_180005FB6
0x180005fa1  mov     rcx, [rbp+phHash]; hHash
0x180005fa5  test    rcx, rcx
0x180005fa8  jnz     loc_180006627
0x180005fae  test    ebx, ebx
0x180005fb0  js      loc_180006632
0x180005fb6  cmp     qword ptr [rdi+0B0h], 0
0x180005fbe  movups  xmm0, xmmword ptr [rbp+pbOutput]
0x180005fc2  jnz     loc_1800063DB
0x180005fc8  movups  xmmword ptr [rdi+0F4h], xmm0
0x180005fcf  xor     r15d, r15d
0x180005fd2  lea     rdx, [rbp+phHash]; phHash
0x180005fd6  mov     [rsp+70h+dwFlags], r15d; dwFlags
0x180005fdb  xor     r9d, r9d; cbHashObject
0x180005fde  mov     [rsp+70h+cbSecret], r15d; cbSecret
0x180005fe3  xor     r8d, r8d; pbHashObject
0x180005fe6  mov     ecx, 21h ; '!'; hAlgorithm
0x180005feb  mov     [rsp+70h+pbSecret], r15; pbSecret
0x180005ff0  mov     [rbp+phHash], r15
0x180005ff4  call    cs:__imp_BCryptCreateHash
0x180005ffa  mov     ebx, eax
0x180005ffc  test    eax, eax
0x180005ffe  js      short loc_18000606D
0x180006000  mov     rcx, [rbp+phHash]; hHash
0x180006004  lea     rdx, [rdi+94h]; pbInput
0x18000600b  xor     r9d, r9d; dwFlags
0x18000600e  mov     r8d, 10h; cbInput
0x180006014  call    cs:__imp_BCryptHashData
0x18000601a  mov     ebx, eax
0x18000601c  test    eax, eax
0x18000601e  js      short loc_18000606D
0x180006020  mov     rcx, [rbp+phHash]; hHash
0x180006024  lea     rdx, aSessionKeyToCl; "session key to client-to-server signing"...
0x18000602b  xor     r9d, r9d; dwFlags
0x18000602e  mov     r8d, 3Bh ; ';'; cbInput
0x180006034  call    cs:__imp_BCryptHashData
0x18000603a  mov     ebx, eax
0x18000603c  test    eax, eax
0x18000603e  js      short loc_18000606D
0x180006040  mov     rcx, [rbp+phHash]; hHash
0x180006044  lea     rdx, [rbp+pbOutput]; pbOutput
0x180006048  xor     r9d, r9d; dwFlags
0x18000604b  mov     r8d, 10h; cbOutput
0x180006051  call    cs:__imp_BCryptFinishHash
0x180006057  mov     ebx, eax
0x180006059  test    eax, eax
0x18000605b  js      short loc_18000606D
0x18000605d  mov     rcx, [rbp+phHash]; hHash
0x180006061  call    cs:__imp_BCryptDestroyHash
0x180006067  mov     ebx, eax
0x180006069  test    eax, eax
0x18000606b  jns     short loc_180006082
0x18000606d  mov     rcx, [rbp+phHash]; hHash
0x180006071  test    rcx, rcx
0x180006074  jnz     loc_18000665A
0x18000607a  test    ebx, ebx
0x18000607c  js      loc_180006665
0x180006082  movups  xmm0, xmmword ptr [rbp+pbOutput]
0x180006086  cmp     [rdi+0B0h], r15
0x18000608d  jnz     loc_180006494
0x180006093  movups  xmmword ptr [rdi+0C4h], xmm0
0x18000609a  mov     [rsp+70h+dwFlags], r15d; dwFlags
0x18000609f  lea     rdx, [rbp+phHash]; phHash
0x1800060a3  mov     [rsp+70h+cbSecret], r15d; cbSecret
0x1800060a8  xor     r9d, r9d; cbHashObject
0x1800060ab  xor     r8d, r8d; pbHashObject
0x1800060ae  mov     [rsp+70h+pbSecret], r15; pbSecret
0x1800060b3  mov     ecx, 21h ; '!'; hAlgorithm
0x1800060b8  mov     [rbp+phHash], r15
0x1800060bc  call    cs:__imp_BCryptCreateHash
0x1800060c2  mov     ebx, eax
0x1800060c4  test    eax, eax
0x1800060c6  js      short loc_18000613B
0x1800060c8  mov     rcx, [rbp+phHash]; hHash
0x1800060cc  lea     rdx, [rdi+94h]; pbInput
0x1800060d3  xor     r9d, r9d; dwFlags
0x1800060d6  mov     r8d, 10h; cbInput
0x1800060dc  call    cs:__imp_BCryptHashData
0x1800060e2  mov     ebx, eax
0x1800060e4  test    eax, eax
0x1800060e6  js      short loc_18000613B
0x1800060e8  mov     rcx, [rbp+phHash]; hHash
0x1800060ec  lea     rdx, aSessionKeyToSe; "session key to server-to-client signing"...
0x1800060f3  xor     r9d, r9d; dwFlags
0x1800060f6  mov     r8d, 3Bh ; ';'; cbInput
0x1800060fc  call    cs:__imp_BCryptHashData
0x180006102  mov     ebx, eax
0x180006104  test    eax, eax
0x180006106  js      short loc_18000613B
0x180006108  mov     rcx, [rbp+phHash]; hHash
0x18000610c  lea     rdx, [rbp+pbOutput]; pbOutput
0x180006110  xor     r9d, r9d; dwFlags
0x180006113  mov     r8d, 10h; cbOutput
0x180006119  call    cs:__imp_BCryptFinishHash
0x18000611f  mov     ebx, eax
0x180006121  test    eax, eax
0x180006123  js      short loc_18000613B
0x180006125  mov     rcx, [rbp+phHash]; hHash
0x180006129  call    cs:__imp_BCryptDestroyHash
0x18000612f  mov     ebx, eax
0x180006131  test    eax, eax
0x180006133  js      short loc_18000613B
0x180006135  mov     [rbp+phHash], r15
0x180006139  jmp     short loc_180006150
0x18000613b  mov     rcx, [rbp+phHash]; hHash
0x18000613f  test    rcx, rcx
0x180006142  jnz     loc_18000668D
0x180006148  test    ebx, ebx
0x18000614a  js      loc_1800064F1
0x180006150  movups  xmm0, xmmword ptr [rbp+pbOutput]
0x180006154  cmp     [rdi+0B0h], r15
0x18000615b  jz      loc_18000636E
0x180006161  movups  xmmword ptr [rdi+0C4h], xmm0
0x180006168  lea     rax, [rdi+7Ch]
0x18000616c  mov     rbx, rax
0x18000616f  lea     r14, [rdi+78h]
0x180006173  lea     rcx, [rdi+70h]
0x180006177  lea     r15, [rdi+68h]
0x18000617b  mov     [rdi+58h], r15
0x18000617f  mov     [rdi+60h], rcx
0x180006183  mov     [rdi+48h], r14
0x180006187  mov     [rdi+50h], rax
0x18000618b  cmp     dword ptr [rsi+3Ch], 0
0x18000618f  jnz     loc_18000631E
0x180006195  mov     qword ptr [rdi+80h], 0
0x1800061a0  mov     rax, rbx
0x1800061a3  cmp     dword ptr [rsi+44h], 0
0x1800061a7  jnz     loc_1800066C0
0x1800061ad  cmp     dword ptr [rsi+8Ch], 0
0x1800061b4  jnz     loc_18000637A
0x1800061ba  mov     rbx, rax
0x1800061bd  mov     eax, [rsi+0Ch]
0x1800061c0  mov     r8, r12; unsigned __int8 *
0x1800061c3  mov     ecx, [rdi+30h]; unsigned int
0x1800061c6  mov     rdx, r15; void **
0x1800061c9  mov     [r14], eax
0x1800061cc  mov     eax, [rsi+10h]
0x1800061cf  mov     [rbx], eax
0x1800061d1  call    ?SspRc4Key@@YAJKPEAPEAXPEAE@Z; SspRc4Key(ulong,void * *,uchar *)
0x1800061d6  mov     ebx, eax
0x1800061d8  test    eax, eax
0x1800061da  js      loc_1800066FC
0x1800061e0  mov     ecx, [rdi+30h]; unsigned int
0x1800061e3  lea     r8, [rdi+0F4h]; unsigned __int8 *
0x1800061ea  lea     rdx, [rdi+70h]; void **
0x1800061ee  call    ?SspRc4Key@@YAJKPEAPEAXPEAE@Z; SspRc4Key(ulong,void * *,uchar *)
0x1800061f3  mov     ebx, eax
0x1800061f5  test    eax, eax
0x1800061f7  js      loc_1800066FC
0x1800061fd  mov     rax, [rsi+30h]
0x180006201  lea     r15, __ImageBase
  ... truncated ...
```
