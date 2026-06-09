# LsapUpdateUserTokenSessionId(void *,ulong)

- ea: `0x1800da62c`
- end: `0x1800daab4`
- name: `?LsapUpdateUserTokenSessionId@@YAJPEAXK@Z`
- size: `1160`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800cef40`

## callees

- `0x180009410`
- `0x180011278`
- `0x1800b86d0`
- `0x1800da62c`
- `0x18014d010`

## import_xrefs

- `ntdll!NtSetInformationToken` at `0x1800da847`
- `ntdll!NtSetInformationToken` at `0x1800da899`
- `ntdll!NtSetInformationToken` at `0x1800da8f2`
- `ntdll!NtSetInformationToken` at `0x1800da942`
- `ntdll!NtSetInformationToken` at `0x1800da99b`
- `ntdll!NtSetInformationToken` at `0x1800da9e8`
- `ntdll!NtSetInformationToken` at `0x1800daa37`
- `ntdll!NtSetInformationToken` at `0x1800da847`
- `ntdll!NtSetInformationToken` at `0x1800da899`
- `ntdll!NtSetInformationToken` at `0x1800da8f2`
- `ntdll!NtSetInformationToken` at `0x1800da942`
- `ntdll!NtSetInformationToken` at `0x1800da99b`
- `ntdll!NtSetInformationToken` at `0x1800da9e8`
- `ntdll!NtSetInformationToken` at `0x1800daa37`
- `ntdll!NtQueryInformationToken` at `0x1800da693`
- `ntdll!NtQueryInformationToken` at `0x1800da6e8`
- `ntdll!NtQueryInformationToken` at `0x1800da693`
- `ntdll!NtQueryInformationToken` at `0x1800da6e8`

## pseudocode

```c
__int64 __fastcall LsapUpdateUserTokenSessionId(HANDLE TokenHandle, int a2)
{
  struct _LSAP_LOGON_SESSION *v2; // rsi
  NTSTATUS v4; // eax
  unsigned int v5; // edi
  LsaHandleCache *v6; // rcx
  __int64 v7; // rdx
  struct _LSAP_LOGON_SESSION *LogonSession; // rax
  struct _LSAP_LOGON_SESSION *v9; // rbx
  __int64 v10; // r9
  void *v11; // r12
  struct _LUID *v12; // rcx
  int v13; // eax
  void *v14; // r15
  void *v15; // r13
  struct _LSAP_LOGON_SESSION *v16; // rax
  NTSTATUS v17; // eax
  char v18; // r12
  LsaHandleCache *v19; // rcx
  __int64 v20; // rdx
  NTSTATUS v21; // eax
  NTSTATUS v22; // eax
  char v24; // [rsp+30h] [rbp-49h]
  int v25; // [rsp+38h] [rbp-41h] BYREF
  int TokenInformation; // [rsp+40h] [rbp-39h] BYREF
  ULONG ReturnLength; // [rsp+44h] [rbp-35h] BYREF
  HANDLE TokenHandlea; // [rsp+48h] [rbp-31h]
  __int128 v29; // [rsp+50h] [rbp-29h] BYREF
  int v30; // [rsp+60h] [rbp-19h] BYREF
  struct _LUID v31[2]; // [rsp+64h] [rbp-15h] BYREF
  __int128 v32; // [rsp+74h] [rbp-5h]
  __int128 v33; // [rsp+84h] [rbp+Bh]
  int v34; // [rsp+94h] [rbp+1Bh]

  v2 = 0;
  v25 = a2;
  TokenInformation = 0;
  ReturnLength = 0;
  v34 = 0;
  v30 = 0;
  *(_OWORD *)&v31[0].LowPart = 0;
  v32 = 0;
  v33 = 0;
  v29 = 0;
  v4 = NtQueryInformationToken(TokenHandle, TokenSessionId, &TokenInformation, 4u, &ReturnLength);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v7 = 45;
LABEL_58:
      v10 = (unsigned int)v4;
      goto LABEL_59;
    }
    return v5;
  }
  v4 = NtQueryInformationToken(TokenHandle, TokenStatistics, &v30, 0x38u, &ReturnLength);
  v5 = v4;
  if ( v4 >= 0 )
  {
    LogonSession = LsapLocateLogonSession((struct _LUID *)&v31[0].HighPart);
    v9 = LogonSession;
    if ( !LogonSession )
    {
      v10 = 3221225567LL;
      v5 = -1073741729;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v5;
      v7 = 47;
      goto LABEL_59;
    }
    v11 = (void *)*((_QWORD *)LogonSession + 36);
    v12 = (struct _LUID *)((char *)LogonSession + 120);
    v13 = *((_DWORD *)LogonSession + 30) | *((_DWORD *)LogonSession + 31);
    TokenHandlea = v11;
    if ( v13 )
    {
      v14 = (void *)*((_QWORD *)v9 + 37);
      v16 = LsapLocateLogonSession(v12);
      v2 = v16;
      if ( !v16 )
      {
        v10 = 3221225567LL;
        v5 = -1073741729;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          return v5;
        }
        v7 = 48;
LABEL_59:
        WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_edf095b3158a35ed0e01973899680e9e_Traceguids, v10);
        return v5;
      }
      v15 = (void *)*((_QWORD *)v16 + 36);
    }
    else
    {
      v14 = 0;
      v15 = 0;
    }
    DWORD2(v29) = v25;
    *(_QWORD *)&v29 = TokenHandle;
    v4 = (*((__int64 (__fastcall **)(__int64, __int128 *, __int64))LsapCallbackInterface + 1))(3735680, &v29, 16);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 49;
        goto LABEL_58;
      }
      return v5;
    }
    v4 = NtSetInformationToken(TokenHandle, TokenSessionId, &v25, 4u);
    v5 = v4;
    if ( v4 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 50;
        goto LABEL_58;
      }
      return v5;
    }
    v24 = 0;
    v17 = NtSetInformationToken(v11, TokenSessionId, &v25, 4u);
    v5 = v17;
    if ( v17 < 0 )
    {
      v18 = 0;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v20 = 51;
LABEL_43:
        WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_edf095b3158a35ed0e01973899680e9e_Traceguids, (unsigned int)v17);
        goto LABEL_44;
      }
      goto LABEL_44;
    }
    v18 = 1;
    if ( v14 )
    {
      v17 = NtSetInformationToken(v14, TokenSessionId, &v25, 4u);
      v5 = v17;
      if ( v17 < 0 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v20 = 52;
          goto LABEL_43;
        }
LABEL_44:
        v21 = NtSetInformationToken(TokenHandle, TokenSessionId, &TokenInformation, 4u);
        if ( v21 < 0
          && WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            54,
            WPP_edf095b3158a35ed0e01973899680e9e_Traceguids,
            (unsigned int)v21);
        }
        if ( v18 )
        {
          v22 = NtSetInformationToken(TokenHandlea, TokenSessionId, &TokenInformation, 4u);
          if ( v22 < 0
            && WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              55,
              WPP_edf095b3158a35ed0e01973899680e9e_Traceguids,
              (unsigned int)v22);
          }
        }
        if ( v24 )
        {
          v4 = NtSetInformationToken(v14, TokenSessionId, &TokenInformation, 4u);
          if ( v4 < 0 )
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v7 = 56;
              goto LABEL_58;
            }
          }
        }
        return v5;
      }
      v24 = 1;
    }
    if ( !v15 || (v17 = NtSetInformationToken(v15, TokenSessionId, &v25, 4u), v5 = v17, v17 >= 0) )
    {
      *((_DWORD *)v9 + 62) = v25;
      if ( v2 )
        *((_DWORD *)v2 + 62) = v25;
      return v5;
    }
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_44;
    v20 = 53;
    goto LABEL_43;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 46;
    goto LABEL_58;
  }
  return v5;
}

```

## disassembly

```asm
0x1800da62c  mov     [rsp-8+arg_10], rbx
0x1800da631  push    rbp
0x1800da632  push    rsi
0x1800da633  push    rdi
0x1800da634  push    r12
0x1800da636  push    r13
0x1800da638  push    r14
0x1800da63a  push    r15
0x1800da63c  lea     rbp, [rsp-27h]
0x1800da641  sub     rsp, 0A0h
0x1800da648  mov     rax, cs:__security_cookie
0x1800da64f  xor     rax, rsp
0x1800da652  mov     [rbp+57h+var_38], rax
0x1800da656  xor     esi, esi
0x1800da658  mov     [rbp+57h+var_98], edx
0x1800da65b  xorps   xmm0, xmm0
0x1800da65e  mov     [rbp+57h+TokenInformation], esi
0x1800da661  xor     eax, eax
0x1800da663  mov     [rbp+57h+var_8C], esi
0x1800da666  mov     [rbp+57h+var_3C], eax
0x1800da669  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800da66d  lea     rax, [rbp+57h+var_8C]
0x1800da671  mov     [rbp+57h+var_70], esi
0x1800da674  lea     r9d, [rsi+4]; TokenInformationLength
0x1800da678  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x1800da67d  lea     edx, [rsi+0Ch]; TokenInformationClass
0x1800da680  mov     r14, rcx
0x1800da683  movups  xmmword ptr [rbp+57h+var_6C.LowPart], xmm0
0x1800da687  movups  [rbp+57h+var_5C], xmm0
0x1800da68b  movups  [rbp+57h+var_4C], xmm0
0x1800da68f  movups  [rbp+57h+var_80], xmm0
0x1800da693  call    cs:__imp_NtQueryInformationToken
0x1800da69a  nop     dword ptr [rax+rax+00h]
0x1800da69f  mov     edi, eax
0x1800da6a1  test    eax, eax
0x1800da6a3  jns     short loc_1800DA6CE
0x1800da6a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da6ac  lea     rbx, WPP_GLOBAL_Control
0x1800da6b3  cmp     rcx, rbx
0x1800da6b6  jz      loc_1800DAA8A
0x1800da6bc  test    byte ptr [rcx+1Ch], 1
0x1800da6c0  jz      loc_1800DAA8A
0x1800da6c6  lea     edx, [rsi+2Dh]
0x1800da6c9  jmp     loc_1800DAA5E
0x1800da6ce  mov     r9d, 38h ; '8'; TokenInformationLength
0x1800da6d4  lea     rax, [rbp+57h+var_8C]
0x1800da6d8  lea     r8, [rbp+57h+var_70]; TokenInformation
0x1800da6dc  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x1800da6e1  mov     rcx, r14; TokenHandle
0x1800da6e4  lea     edx, [r9-2Eh]; TokenInformationClass
0x1800da6e8  call    cs:__imp_NtQueryInformationToken
0x1800da6ef  nop     dword ptr [rax+rax+00h]
0x1800da6f4  mov     edi, eax
0x1800da6f6  test    eax, eax
0x1800da6f8  jns     short loc_1800DA725
0x1800da6fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da701  lea     rbx, WPP_GLOBAL_Control
0x1800da708  cmp     rcx, rbx
0x1800da70b  jz      loc_1800DAA8A
0x1800da711  test    byte ptr [rcx+1Ch], 1
0x1800da715  jz      loc_1800DAA8A
0x1800da71b  mov     edx, 2Eh ; '.'
0x1800da720  jmp     loc_1800DAA5E
0x1800da725  lea     rcx, [rbp+57h+var_6C.HighPart]; struct _LUID *
0x1800da729  call    ?LsapLocateLogonSession@@YAPEAU_LSAP_LOGON_SESSION@@PEAU_LUID@@@Z; LsapLocateLogonSession(_LUID *)
0x1800da72e  mov     rbx, rax
0x1800da731  test    rax, rax
0x1800da734  jnz     short loc_1800DA768
0x1800da736  mov     r9d, 0C000005Fh
0x1800da73c  mov     edi, r9d
0x1800da73f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da746  lea     rbx, WPP_GLOBAL_Control
0x1800da74d  cmp     rcx, rbx
0x1800da750  jz      loc_1800DAA8A
0x1800da756  test    byte ptr [rcx+1Ch], 1
0x1800da75a  jz      loc_1800DAA8A
0x1800da760  lea     edx, [rax+2Fh]
0x1800da763  jmp     loc_1800DAA61
0x1800da768  mov     r12, [rax+120h]
0x1800da76f  lea     rcx, [rax+78h]; struct _LUID *
0x1800da773  mov     eax, [rax+7Ch]
0x1800da776  or      eax, [rcx]
0x1800da778  mov     [rbp+57h+TokenHandle], r12
0x1800da77c  jnz     short loc_1800DA786
0x1800da77e  mov     r15, rsi
0x1800da781  mov     r13, rsi
0x1800da784  jmp     short loc_1800DA7D3
0x1800da786  mov     r15, [rbx+128h]
0x1800da78d  call    ?LsapLocateLogonSession@@YAPEAU_LSAP_LOGON_SESSION@@PEAU_LUID@@@Z; LsapLocateLogonSession(_LUID *)
0x1800da792  mov     rsi, rax
0x1800da795  test    rax, rax
0x1800da798  jnz     short loc_1800DA7CC
0x1800da79a  mov     r9d, 0C000005Fh
0x1800da7a0  mov     edi, r9d
0x1800da7a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da7aa  lea     rbx, WPP_GLOBAL_Control
0x1800da7b1  cmp     rcx, rbx
0x1800da7b4  jz      loc_1800DAA8A
0x1800da7ba  test    byte ptr [rcx+1Ch], 1
0x1800da7be  jz      loc_1800DAA8A
0x1800da7c4  lea     edx, [rax+30h]
0x1800da7c7  jmp     loc_1800DAA61
0x1800da7cc  mov     r13, [rax+120h]
0x1800da7d3  mov     eax, [rbp+57h+var_98]
0x1800da7d6  lea     rdx, [rbp+57h+var_80]
0x1800da7da  mov     dword ptr [rbp+57h+var_80+8], eax
0x1800da7dd  xor     r9d, r9d
0x1800da7e0  mov     rax, cs:?LsapCallbackInterface@@3PEAU_LSA_CALLBACK_FUNCTIONS@@EA; _LSA_CALLBACK_FUNCTIONS * LsapCallbackInterface
0x1800da7e7  mov     ecx, 390080h
0x1800da7ec  mov     qword ptr [rbp+57h+var_80], r14
0x1800da7f0  mov     dword ptr [rsp+0D0h+ReturnLength], 0
0x1800da7f8  lea     r8d, [r9+10h]
0x1800da7fc  mov     rax, [rax+8]
0x1800da800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800da805  mov     edi, eax
0x1800da807  test    eax, eax
0x1800da809  jns     short loc_1800DA836
0x1800da80b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da812  lea     rbx, WPP_GLOBAL_Control
0x1800da819  cmp     rcx, rbx
0x1800da81c  jz      loc_1800DAA8A
0x1800da822  test    byte ptr [rcx+1Ch], 1
0x1800da826  jz      loc_1800DAA8A
0x1800da82c  mov     edx, 31h ; '1'
0x1800da831  jmp     loc_1800DAA5E
0x1800da836  mov     r9d, 4; TokenInformationLength
0x1800da83c  lea     r8, [rbp+57h+var_98]; TokenInformation
0x1800da840  mov     rcx, r14; TokenHandle
0x1800da843  lea     edx, [r9+8]; TokenInformationClass
0x1800da847  call    cs:__imp_NtSetInformationToken
0x1800da84e  nop     dword ptr [rax+rax+00h]
0x1800da853  mov     edi, eax
0x1800da855  test    eax, eax
0x1800da857  jns     short loc_1800DA884
0x1800da859  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da860  lea     rbx, WPP_GLOBAL_Control
0x1800da867  cmp     rcx, rbx
0x1800da86a  jz      loc_1800DAA8A
0x1800da870  test    byte ptr [rcx+1Ch], 1
0x1800da874  jz      loc_1800DAA8A
0x1800da87a  mov     edx, 32h ; '2'
0x1800da87f  jmp     loc_1800DAA5E
0x1800da884  mov     r9d, 4; TokenInformationLength
0x1800da88a  mov     [rbp+57h+var_A0], 0
0x1800da88e  lea     r8, [rbp+57h+var_98]; TokenInformation
0x1800da892  mov     rcx, r12; TokenHandle
0x1800da895  lea     edx, [r9+8]; TokenInformationClass
0x1800da899  call    cs:__imp_NtSetInformationToken
0x1800da8a0  nop     dword ptr [rax+rax+00h]
0x1800da8a5  mov     edi, eax
0x1800da8a7  test    eax, eax
0x1800da8a9  jns     short loc_1800DA8D9
0x1800da8ab  xor     r12b, r12b
0x1800da8ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da8b5  lea     rbx, WPP_GLOBAL_Control
0x1800da8bc  cmp     rcx, rbx
0x1800da8bf  jz      loc_1800DA989
0x1800da8c5  test    byte ptr [rcx+1Ch], 1
0x1800da8c9  jz      loc_1800DA989
0x1800da8cf  mov     edx, 33h ; '3'
0x1800da8d4  jmp     loc_1800DA976
0x1800da8d9  mov     r12b, 1
0x1800da8dc  test    r15, r15
0x1800da8df  jz      short loc_1800DA928
0x1800da8e1  mov     r9d, 4; TokenInformationLength
0x1800da8e7  lea     r8, [rbp+57h+var_98]; TokenInformation
0x1800da8eb  mov     rcx, r15; TokenHandle
0x1800da8ee  lea     edx, [r9+8]; TokenInformationClass
0x1800da8f2  call    cs:__imp_NtSetInformationToken
0x1800da8f9  nop     dword ptr [rax+rax+00h]
0x1800da8fe  mov     edi, eax
0x1800da900  test    eax, eax
0x1800da902  jns     short loc_1800DA924
0x1800da904  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da90b  lea     rbx, WPP_GLOBAL_Control
0x1800da912  cmp     rcx, rbx
0x1800da915  jz      short loc_1800DA989
0x1800da917  test    [rcx+1Ch], r12b
0x1800da91b  jz      short loc_1800DA989
0x1800da91d  mov     edx, 34h ; '4'
0x1800da922  jmp     short loc_1800DA976
0x1800da924  mov     [rbp+57h+var_A0], r12b
0x1800da928  test    r13, r13
0x1800da92b  jz      loc_1800DAA73
0x1800da931  mov     r9d, 4; TokenInformationLength
0x1800da937  lea     r8, [rbp+57h+var_98]; TokenInformation
0x1800da93b  mov     rcx, r13; TokenHandle
0x1800da93e  lea     edx, [r9+8]; TokenInformationClass
0x1800da942  call    cs:__imp_NtSetInformationToken
0x1800da949  nop     dword ptr [rax+rax+00h]
0x1800da94e  mov     edi, eax
0x1800da950  test    eax, eax
0x1800da952  jns     loc_1800DAA73
0x1800da958  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da95f  lea     rbx, WPP_GLOBAL_Control
0x1800da966  cmp     rcx, rbx
0x1800da969  jz      short loc_1800DA989
0x1800da96b  test    [rcx+1Ch], r12b
0x1800da96f  jz      short loc_1800DA989
0x1800da971  mov     edx, 35h ; '5'
0x1800da976  mov     rcx, [rcx+10h]
0x1800da97a  lea     r8, WPP_edf095b3158a35ed0e01973899680e9e_Traceguids
0x1800da981  mov     r9d, eax
0x1800da984  call    WPP_SF_d
0x1800da989  mov     esi, 4
0x1800da98e  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800da992  mov     r9d, esi; TokenInformationLength
0x1800da995  mov     rcx, r14; TokenHandle
0x1800da998  lea     edx, [rsi+8]; TokenInformationClass
0x1800da99b  call    cs:__imp_NtSetInformationToken
0x1800da9a2  nop     dword ptr [rax+rax+00h]
0x1800da9a7  test    eax, eax
0x1800da9a9  jns     short loc_1800DA9D3
0x1800da9ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da9b2  cmp     rcx, rbx
0x1800da9b5  jz      short loc_1800DA9D3
0x1800da9b7  test    byte ptr [rcx+1Ch], 1
0x1800da9bb  jz      short loc_1800DA9D3
0x1800da9bd  mov     rcx, [rcx+10h]
0x1800da9c1  lea     edx, [rsi+32h]
0x1800da9c4  mov     r9d, eax
0x1800da9c7  lea     r8, WPP_edf095b3158a35ed0e01973899680e9e_Traceguids
0x1800da9ce  call    WPP_SF_d
0x1800da9d3  test    r12b, r12b
0x1800da9d6  jz      short loc_1800DAA22
0x1800da9d8  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800da9dc  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800da9e0  mov     r9d, esi; TokenInformationLength
0x1800da9e3  mov     edx, 0Ch; TokenInformationClass
0x1800da9e8  call    cs:__imp_NtSetInformationToken
0x1800da9ef  nop     dword ptr [rax+rax+00h]
0x1800da9f4  test    eax, eax
0x1800da9f6  jns     short loc_1800DAA22
0x1800da9f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800da9ff  cmp     rcx, rbx
0x1800daa02  jz      short loc_1800DAA22
0x1800daa04  test    byte ptr [rcx+1Ch], 1
0x1800daa08  jz      short loc_1800DAA22
0x1800daa0a  mov     rcx, [rcx+10h]
0x1800daa0e  lea     r8, WPP_edf095b3158a35ed0e01973899680e9e_Traceguids
0x1800daa15  mov     edx, 37h ; '7'
0x1800daa1a  mov     r9d, eax
0x1800daa1d  call    WPP_SF_d
0x1800daa22  cmp     [rbp+57h+var_A0], 0
0x1800daa26  jz      short loc_1800DAA8A
0x1800daa28  mov     r9d, esi; TokenInformationLength
0x1800daa2b  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800daa2f  mov     edx, 0Ch; TokenInformationClass
0x1800daa34  mov     rcx, r15; TokenHandle
0x1800daa37  call    cs:__imp_NtSetInformationToken
0x1800daa3e  nop     dword ptr [rax+rax+00h]
0x1800daa43  test    eax, eax
0x1800daa45  jns     short loc_1800DAA8A
0x1800daa47  mov     rcx, cs:WPP_GLOBAL_Control
0x1800daa4e  cmp     rcx, rbx
0x1800daa51  jz      short loc_1800DAA8A
0x1800daa53  test    byte ptr [rcx+1Ch], 1
0x1800daa57  jz      short loc_1800DAA8A
0x1800daa59  mov     edx, 38h ; '8'
0x1800daa5e  mov     r9d, eax
0x1800daa61  mov     rcx, [rcx+10h]
0x1800daa65  lea     r8, WPP_edf095b3158a35ed0e01973899680e9e_Traceguids
0x1800daa6c  call    WPP_SF_d
0x1800daa71  jmp     short loc_1800DAA8A
0x1800daa73  mov     eax, [rbp+57h+var_98]
0x1800daa76  mov     [rbx+0F8h], eax
0x1800daa7c  test    rsi, rsi
0x1800daa7f  jz      short loc_1800DAA8A
0x1800daa81  mov     eax, [rbp+57h+var_98]
0x1800daa84  mov     [rsi+0F8h], eax
0x1800daa8a  mov     eax, edi
0x1800daa8c  mov     rcx, [rbp+57h+var_38]
0x1800daa90  xor     rcx, rsp; StackCookie
0x1800daa93  call    __security_check_cookie
0x1800daa98  mov     rbx, [rsp+0D0h+arg_10]
0x1800daaa0  add     rsp, 0A0h
0x1800daaa7  pop     r15
0x1800daaa9  pop     r14
0x1800daaab  pop     r13
0x1800daaad  pop     r12
0x1800daaaf  pop     rdi
0x1800daab0  pop     rsi
0x1800daab1  pop     rbp
0x1800daab2  retn
```
