# NtLmCreateUserModeContext(unsigned __int64,void *,_SecBuffer *,_NTLM_CLIENT_CONTEXT * *)

- ea: `0x18004b8e4`
- end: `0x18004bca7`
- name: `?NtLmCreateUserModeContext@@YAJ_KPEAXPEAU_SecBuffer@@PEAPEAU_NTLM_CLIENT_CONTEXT@@@Z`
- size: `963`
- prototype: `int(unsigned __int64, void *, struct _SecBuffer *, struct _NTLM_CLIENT_CONTEXT **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18004c320`

## callees

- `0x180004e60`
- `0x180006c90`
- `0x180007700`
- `0x18001a1ec`
- `0x18002ee7c`
- `0x18003509c`
- `0x18004b8e4`
- `0x18006bd74`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18004bc3f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18004bc3f`
- `ntdll!RtlReleaseResource` at `0x18004bc7e`
- `ntdll!RtlReleaseResource` at `0x18004bc7e`
- `bcrypt!BCryptImportKey` at `0x18004bac6`
- `bcrypt!BCryptImportKey` at `0x18004bb3c`
- `bcrypt!BCryptImportKey` at `0x18004bac6`
- `bcrypt!BCryptImportKey` at `0x18004bb3c`

## pseudocode

```c
__int64 __fastcall NtLmCreateUserModeContext(
        __int64 a1,
        void *a2,
        struct _SecBuffer *a3,
        struct _NTLM_CLIENT_CONTEXT **a4)
{
  __int64 cbBuffer; // r9
  char *pvBuffer; // rdi
  __int64 v9; // rax
  __int64 v10; // rbx
  NTSTATUS TokenDacl; // esi
  _DWORD *v12; // r14
  void *v13; // rax
  BCRYPT_ALG_HANDLE MsRc4AlgorithmProvider; // rbp
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned __int32 v21; // ecx
  unsigned int v22; // eax
  __int64 v23; // rdi
  struct _RTL_RESOURCE *v24; // rbp
  struct _LIST_ENTRY near **v25; // rcx
  struct _LIST_ENTRY near *v26; // rax

  cbBuffer = a3->cbBuffer;
  if ( (unsigned int)cbBuffer >= 0xA8 )
  {
    pvBuffer = (char *)a3->pvBuffer;
    v9 = NtLmAllocate(0x118u);
    v10 = v9;
    if ( !v9 )
      return (unsigned int)-1073741670;
    v12 = (_DWORD *)(v9 + 124);
    *(_DWORD *)(v9 + 48) = *((_DWORD *)pvBuffer + 1);
    *(_DWORD *)(v9 + 120) = *((_DWORD *)pvBuffer + 3);
    *(_DWORD *)(v9 + 124) = *((_DWORD *)pvBuffer + 4);
    *(_OWORD *)(v9 + 148) = *(_OWORD *)(pvBuffer + 20);
    *(_DWORD *)(v9 + 164) = *((_DWORD *)pvBuffer + 9);
    *(_QWORD *)(v9 + 176) = *((_QWORD *)pvBuffer + 5);
    *(_QWORD *)(v9 + 184) = *((_QWORD *)pvBuffer + 6);
    *(_DWORD *)(v9 + 192) = *((_DWORD *)pvBuffer + 14);
    if ( *((_DWORD *)pvBuffer + 15) )
    {
      v13 = (void *)NtLmAllocate(*((unsigned int *)pvBuffer + 16));
      *(_QWORD *)(v10 + 128) = v13;
      if ( !v13 )
      {
        TokenDacl = -1073741670;
        goto LABEL_44;
      }
      memcpy_0(v13, &pvBuffer[*((unsigned int *)pvBuffer + 15)], *((unsigned int *)pvBuffer + 16));
    }
    else
    {
      *(_QWORD *)(v9 + 128) = 0;
    }
    *(_OWORD *)(v10 + 196) = *(_OWORD *)(pvBuffer + 76);
    *(_OWORD *)(v10 + 212) = *(_OWORD *)(pvBuffer + 92);
    *(_OWORD *)(v10 + 228) = *(_OWORD *)(pvBuffer + 108);
    *(_OWORD *)(v10 + 244) = *(_OWORD *)(pvBuffer + 124);
    if ( (*((_DWORD *)pvBuffer + 37) || (MsRc4AlgorithmProvider = 0, *((_DWORD *)pvBuffer + 39)))
      && (MsRc4AlgorithmProvider = GetMsRc4AlgorithmProvider()) == 0 )
    {
      TokenDacl = -1073741816;
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_44;
      v16 = 110;
      v17 = 3221225480LL;
    }
    else
    {
      v18 = *((unsigned int *)pvBuffer + 37);
      TokenDacl = 0;
      if ( (_DWORD)v18
        && (TokenDacl = BCryptImportKey(
                          MsRc4AlgorithmProvider,
                          0,
                          L"OpaqueKeyBlob",
                          (BCRYPT_KEY_HANDLE *)(v10 + 104),
                          0,
                          0,
                          (PUCHAR)&pvBuffer[v18],
                          *((_DWORD *)pvBuffer + 38),
                          0),
            TokenDacl < 0) )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_44;
        v16 = 111;
      }
      else
      {
        v19 = *((unsigned int *)pvBuffer + 39);
        if ( !(_DWORD)v19
          || (TokenDacl = BCryptImportKey(
                            MsRc4AlgorithmProvider,
                            0,
                            L"OpaqueKeyBlob",
                            (BCRYPT_KEY_HANDLE *)(v10 + 112),
                            0,
                            0,
                            (PUCHAR)&pvBuffer[v19],
                            *((_DWORD *)pvBuffer + 40),
                            0),
              TokenDacl >= 0) )
        {
          *(_QWORD *)(v10 + 56) = a2;
          if ( *(_DWORD *)(v10 + 120) == -1 )
            *(_DWORD *)(v10 + 120) = 0;
          if ( *v12 == -1 )
            *v12 = 0;
          if ( (*(_DWORD *)(v10 + 48) & 0x80000) != 0 )
          {
            v20 = v10 + 112;
          }
          else
          {
            v12 = (_DWORD *)(v10 + 120);
            v20 = v10 + 104;
          }
          *(_QWORD *)(v10 + 88) = v10 + 104;
          *(_QWORD *)(v10 + 96) = v20;
          *(_QWORD *)(v10 + 72) = v10 + 120;
          *(_QWORD *)(v10 + 80) = v12;
          *(_DWORD *)(v10 + 168) = 2;
          if ( !a2 || (TokenDacl = SspCreateTokenDacl(a2), TokenDacl >= 0) )
          {
            do
            {
              v21 = _InterlockedIncrement((volatile signed __int32 *)&ExportedContext);
              *(_QWORD *)(v10 + 40) = (int)v21;
            }
            while ( (v21 & 7) == 0 );
            v22 = (v21 >> 4) + HIWORD(v21) + HIBYTE(v21) + v21 + (v21 >> 8);
            v23 = (unsigned __int8)(v22 + (v22 >> 4));
            v24 = (struct _RTL_RESOURCE *)&(&NtLmUserContextLock)[12
                                                                * ((unsigned int)v23 & (NtLmUserContextLockCount - 1))];
            RtlAcquireResourceExclusive(v24, 1u);
            v25 = &(&NtLmUserContextList)[2 * (unsigned int)v23];
            v26 = *v25;
            if ( (struct _LIST_ENTRY near **)(*v25)->Blink != v25 )
              __fastfail(3u);
            ++*((_DWORD *)&NtLmUserContextCount + v23);
            *(_QWORD *)(v10 + 8) = v25;
            *(_QWORD *)v10 = v26;
            v26->Blink = (struct _LIST_ENTRY *)v10;
            *v25 = (struct _LIST_ENTRY near *)v10;
            RtlReleaseResource(v24);
            *a4 = (struct _NTLM_CLIENT_CONTEXT *)v10;
            return (unsigned int)TokenDacl;
          }
          goto LABEL_44;
        }
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_44:
          FreeUserContext((struct _NTLM_CLIENT_CONTEXT *)v10);
          return (unsigned int)TokenDacl;
        }
        v16 = 112;
      }
      v17 = (unsigned int)TokenDacl;
    }
    WPP_SF_d(v15[2], v16, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, v17);
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, cbBuffer, 168);
  return 3221225485LL;
}

```

## disassembly

```asm
0x18004b8e4  push    rbx
0x18004b8e6  push    rbp
0x18004b8e7  push    rsi
0x18004b8e8  push    rdi
0x18004b8e9  push    r12
0x18004b8eb  push    r13
0x18004b8ed  push    r14
0x18004b8ef  push    r15
0x18004b8f1  sub     rsp, 58h
0x18004b8f5  mov     r12, r9
0x18004b8f8  mov     r10d, 0A8h
0x18004b8fe  mov     r9d, [r8]
0x18004b901  mov     r15, rdx
0x18004b904  cmp     r9d, r10d
0x18004b907  jnb     short loc_18004B945
0x18004b909  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b910  lea     rax, WPP_GLOBAL_Control
0x18004b917  cmp     rcx, rax
0x18004b91a  jz      short loc_18004B93B
0x18004b91c  test    byte ptr [rcx+1Ch], 1
0x18004b920  jz      short loc_18004B93B
0x18004b922  mov     rcx, [rcx+10h]
0x18004b926  lea     edx, [r10-3Bh]
0x18004b92a  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x18004b931  mov     dword ptr [rsp+98h+pbKeyObject], r10d
0x18004b936  call    WPP_SF_dd
0x18004b93b  mov     eax, 0C000000Dh
0x18004b940  jmp     loc_18004BC96
0x18004b945  mov     rdi, [r8+8]
0x18004b949  mov     ecx, 118h; uBytes
0x18004b94e  call    NtLmAllocate
0x18004b953  xor     r13d, r13d
0x18004b956  mov     rbx, rax
0x18004b959  test    rax, rax
0x18004b95c  jnz     short loc_18004B968
0x18004b95e  mov     esi, 0C000009Ah
0x18004b963  jmp     loc_18004BC94
0x18004b968  mov     eax, [rdi+4]
0x18004b96b  lea     r14, [rbx+7Ch]
0x18004b96f  mov     [rbx+30h], eax
0x18004b972  mov     eax, [rdi+0Ch]
0x18004b975  mov     [rbx+78h], eax
0x18004b978  mov     eax, [rdi+10h]
0x18004b97b  mov     [r14], eax
0x18004b97e  movups  xmm0, xmmword ptr [rdi+14h]
0x18004b982  movdqu  xmmword ptr [rbx+94h], xmm0
0x18004b98a  mov     eax, [rdi+24h]
0x18004b98d  mov     [rbx+0A4h], eax
0x18004b993  mov     rax, [rdi+28h]
0x18004b997  mov     [rbx+0B0h], rax
0x18004b99e  mov     rax, [rdi+30h]
0x18004b9a2  mov     [rbx+0B8h], rax
0x18004b9a9  mov     eax, [rdi+38h]
0x18004b9ac  mov     [rbx+0C0h], eax
0x18004b9b2  cmp     [rdi+3Ch], r13d
0x18004b9b6  jz      short loc_18004B9EA
0x18004b9b8  mov     ecx, [rdi+40h]; uBytes
0x18004b9bb  call    NtLmAllocate
0x18004b9c0  mov     [rbx+80h], rax
0x18004b9c7  test    rax, rax
0x18004b9ca  jnz     short loc_18004B9D6
0x18004b9cc  mov     esi, 0C000009Ah
0x18004b9d1  jmp     loc_18004BC8C
0x18004b9d6  mov     edx, [rdi+3Ch]
0x18004b9d9  mov     rcx, rax; void *
0x18004b9dc  mov     r8d, [rdi+40h]; Size
0x18004b9e0  add     rdx, rdi; Src
0x18004b9e3  call    memcpy_0
0x18004b9e8  jmp     short loc_18004B9F1
0x18004b9ea  mov     [rbx+80h], r13
0x18004b9f1  movups  xmm0, xmmword ptr [rdi+4Ch]
0x18004b9f5  movdqu  xmmword ptr [rbx+0C4h], xmm0
0x18004b9fd  movups  xmm1, xmmword ptr [rdi+5Ch]
0x18004ba01  movdqu  xmmword ptr [rbx+0D4h], xmm1
0x18004ba09  movups  xmm0, xmmword ptr [rdi+6Ch]
0x18004ba0d  movdqu  xmmword ptr [rbx+0E4h], xmm0
0x18004ba15  movups  xmm1, xmmword ptr [rdi+7Ch]
0x18004ba19  movdqu  xmmword ptr [rbx+0F4h], xmm1
0x18004ba21  cmp     [rdi+94h], r13d
0x18004ba28  ja      short loc_18004BA36
0x18004ba2a  mov     rbp, r13
0x18004ba2d  cmp     [rdi+9Ch], r13d
0x18004ba34  jbe     short loc_18004BA87
0x18004ba36  call    ?GetMsRc4AlgorithmProvider@@YAPEAXXZ; GetMsRc4AlgorithmProvider(void)
0x18004ba3b  mov     rbp, rax
0x18004ba3e  test    rax, rax
0x18004ba41  jnz     short loc_18004BA87
0x18004ba43  mov     esi, 0C0000008h
0x18004ba48  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ba4f  lea     rax, WPP_GLOBAL_Control
0x18004ba56  cmp     rcx, rax
0x18004ba59  jz      loc_18004BC8C
0x18004ba5f  test    byte ptr [rcx+1Ch], 1
0x18004ba63  jz      loc_18004BC8C
0x18004ba69  lea     edx, [rbp+6Eh]
0x18004ba6c  mov     r9d, 0C0000008h
0x18004ba72  mov     rcx, [rcx+10h]
0x18004ba76  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x18004ba7d  call    WPP_SF_d
0x18004ba82  jmp     loc_18004BC8C
0x18004ba87  mov     eax, [rdi+94h]
0x18004ba8d  mov     esi, r13d
0x18004ba90  test    eax, eax
0x18004ba92  jz      short loc_18004BB00
0x18004ba94  lea     rcx, [rdi+rax]
0x18004ba98  mov     [rsp+98h+dwFlags], r13d; dwFlags
0x18004ba9d  mov     eax, [rdi+98h]
0x18004baa3  lea     r9, [rbx+68h]; phKey
0x18004baa7  mov     [rsp+98h+cbInput], eax; cbInput
0x18004baab  lea     r8, pszBlobType; "OpaqueKeyBlob"
0x18004bab2  mov     [rsp+98h+pbInput], rcx; pbInput
0x18004bab7  xor     edx, edx; hImportKey
0x18004bab9  mov     [rsp+98h+cbKeyObject], r13d; cbKeyObject
0x18004babe  mov     rcx, rbp; hAlgorithm
0x18004bac1  mov     [rsp+98h+pbKeyObject], r13; pbKeyObject
0x18004bac6  call    cs:__imp_BCryptImportKey
0x18004bacc  mov     esi, eax
0x18004bace  test    eax, eax
0x18004bad0  jns     short loc_18004BB00
0x18004bad2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bad9  lea     rax, WPP_GLOBAL_Control
0x18004bae0  cmp     rcx, rax
0x18004bae3  jz      loc_18004BC8C
0x18004bae9  test    byte ptr [rcx+1Ch], 1
0x18004baed  jz      loc_18004BC8C
0x18004baf3  mov     edx, 6Fh ; 'o'
0x18004baf8  mov     r9d, esi
0x18004bafb  jmp     loc_18004BA72
0x18004bb00  mov     eax, [rdi+9Ch]
0x18004bb06  test    eax, eax
0x18004bb08  jz      short loc_18004BB70
0x18004bb0a  lea     rcx, [rdi+rax]
0x18004bb0e  mov     [rsp+98h+dwFlags], r13d; dwFlags
0x18004bb13  mov     eax, [rdi+0A0h]
0x18004bb19  lea     r9, [rbx+70h]; phKey
0x18004bb1d  mov     [rsp+98h+cbInput], eax; cbInput
0x18004bb21  lea     r8, pszBlobType; "OpaqueKeyBlob"
0x18004bb28  mov     [rsp+98h+pbInput], rcx; pbInput
0x18004bb2d  xor     edx, edx; hImportKey
0x18004bb2f  mov     [rsp+98h+cbKeyObject], r13d; cbKeyObject
0x18004bb34  mov     rcx, rbp; hAlgorithm
0x18004bb37  mov     [rsp+98h+pbKeyObject], r13; pbKeyObject
0x18004bb3c  call    cs:__imp_BCryptImportKey
0x18004bb42  mov     esi, eax
0x18004bb44  test    eax, eax
0x18004bb46  jns     short loc_18004BB70
0x18004bb48  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bb4f  lea     rax, WPP_GLOBAL_Control
0x18004bb56  cmp     rcx, rax
0x18004bb59  jz      loc_18004BC8C
0x18004bb5f  test    byte ptr [rcx+1Ch], 1
0x18004bb63  jz      loc_18004BC8C
0x18004bb69  mov     edx, 70h ; 'p'
0x18004bb6e  jmp     short loc_18004BAF8
0x18004bb70  or      eax, 0FFFFFFFFh
0x18004bb73  mov     [rbx+38h], r15
0x18004bb77  cmp     [rbx+78h], eax
0x18004bb7a  jnz     short loc_18004BB80
0x18004bb7c  mov     [rbx+78h], r13d
0x18004bb80  cmp     [r14], eax
0x18004bb83  jnz     short loc_18004BB88
0x18004bb85  mov     [r14], r13d
0x18004bb88  test    dword ptr [rbx+30h], 80000h
0x18004bb8f  lea     rcx, [rbx+68h]
0x18004bb93  jz      short loc_18004BB9B
0x18004bb95  lea     rax, [rbx+70h]
0x18004bb99  jmp     short loc_18004BBA2
0x18004bb9b  lea     r14, [rbx+78h]
0x18004bb9f  mov     rax, rcx
0x18004bba2  mov     [rbx+58h], rcx
0x18004bba6  mov     [rbx+60h], rax
0x18004bbaa  lea     rax, [rbx+78h]
0x18004bbae  mov     [rbx+48h], rax
0x18004bbb2  mov     [rbx+50h], r14
0x18004bbb6  mov     dword ptr [rbx+0A8h], 2
0x18004bbc0  test    r15, r15
0x18004bbc3  jz      short loc_18004BBD7
0x18004bbc5  mov     rcx, r15; Handle
0x18004bbc8  call    ?SspCreateTokenDacl@@YAJPEAX@Z; SspCreateTokenDacl(void *)
0x18004bbcd  mov     esi, eax
0x18004bbcf  test    eax, eax
0x18004bbd1  js      loc_18004BC8C
0x18004bbd7  mov     eax, 1
0x18004bbdc  lock xadd cs:?ExportedContext@@3_KA, eax; unsigned __int64 ExportedContext
0x18004bbe4  inc     eax
0x18004bbe6  movsxd  rcx, eax
0x18004bbe9  mov     [rbx+28h], rcx
0x18004bbed  test    cl, 7
0x18004bbf0  jz      short loc_18004BBD7
0x18004bbf2  mov     edx, ecx
0x18004bbf4  lea     r14, __ImageBase
0x18004bbfb  shr     ecx, 18h
0x18004bbfe  lea     rbp, rva ?NtLmUserContextLock@@3PAU_RTL_RESOURCE@@A[r14]; _RTL_RESOURCE near * NtLmUserContextLock ...
0x18004bc05  mov     eax, edx
0x18004bc07  shr     eax, 10h
0x18004bc0a  add     ecx, eax
0x18004bc0c  mov     eax, edx
0x18004bc0e  shr     eax, 8
0x18004bc11  add     eax, edx
0x18004bc13  shr     edx, 4
0x18004bc16  add     eax, ecx
0x18004bc18  add     eax, edx
0x18004bc1a  mov     dl, 1; Wait
0x18004bc1c  mov     ecx, eax
0x18004bc1e  shr     ecx, 4
0x18004bc21  add     ecx, eax
0x18004bc23  movzx   edi, cl
0x18004bc26  mov     ecx, cs:?NtLmUserContextLockCount@@3KA; ulong NtLmUserContextLockCount
0x18004bc2c  dec     ecx
0x18004bc2e  and     rcx, rdi
0x18004bc31  lea     rax, [rcx+rcx*2]
0x18004bc35  shl     rax, 5
0x18004bc39  add     rbp, rax
0x18004bc3c  mov     rcx, rbp; Resource
0x18004bc3f  call    cs:__imp_RtlAcquireResourceExclusive
0x18004bc45  mov     eax, edi
0x18004bc47  lea     rcx, rva ?NtLmUserContextList@@3PAU_LIST_ENTRY@@A[r14]; _LIST_ENTRY near * NtLmUserContextList ...
0x18004bc4e  shl     rax, 4
0x18004bc52  add     rcx, rax
0x18004bc55  mov     rax, [rcx]
0x18004bc58  cmp     [rax+8], rcx
0x18004bc5c  jz      short loc_18004BC65
0x18004bc5e  mov     ecx, 3
0x18004bc63  int     29h; Win8: RtlFailFast(ecx)
0x18004bc65  inc     rva ?NtLmUserContextCount@@3PAKA[r14+rdi*4]; ulong near * NtLmUserContextCount ...
0x18004bc6d  mov     [rbx+8], rcx
0x18004bc71  mov     [rbx], rax
0x18004bc74  mov     [rax+8], rbx
0x18004bc78  mov     [rcx], rbx
0x18004bc7b  mov     rcx, rbp; Resource
0x18004bc7e  call    cs:__imp_RtlReleaseResource
0x18004bc84  mov     [r12], rbx
0x18004bc88  test    esi, esi
0x18004bc8a  jns     short loc_18004BC94
0x18004bc8c  mov     rcx, rbx; struct _NTLM_CLIENT_CONTEXT *
0x18004bc8f  call    ?FreeUserContext@@YAJPEAU_NTLM_CLIENT_CONTEXT@@@Z; FreeUserContext(_NTLM_CLIENT_CONTEXT *)
0x18004bc94  mov     eax, esi
0x18004bc96  add     rsp, 58h
0x18004bc9a  pop     r15
0x18004bc9c  pop     r14
0x18004bc9e  pop     r13
0x18004bca0  pop     r12
0x18004bca2  pop     rdi
0x18004bca3  pop     rsi
0x18004bca4  pop     rbp
0x18004bca5  pop     rbx
0x18004bca6  retn
```
