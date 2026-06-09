# NlpChangePwdCredByLogonId

- ea: `0x18000c000`
- end: `0x18000c5c5`
- name: `NlpChangePwdCredByLogonId`
- size: `1477`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, __int64)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000b600`
- `0x18000d1b0`
- `0x1800193e0`
- `0x18003fdec`

## callees

- `0x18000c000`
- `0x18000c630`
- `0x18000ceb0`
- `0x18001fefc`
- `0x18002fb50`
- `0x18003509c`
- `0x180040a0c`
- `0x18004417c`
- `0x1800555f8`
- `0x18006d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c59a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c59a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000c52d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000c52d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c5ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c5ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c594`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c594`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000c056`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000c056`
- `ntdll!RtlReleaseResource` at `0x18000c20a`
- `ntdll!RtlReleaseResource` at `0x18000c28e`
- `ntdll!RtlReleaseResource` at `0x18000c2c8`
- `ntdll!RtlReleaseResource` at `0x18000c5ba`
- `ntdll!RtlReleaseResource` at `0x18000c20a`
- `ntdll!RtlReleaseResource` at `0x18000c28e`
- `ntdll!RtlReleaseResource` at `0x18000c2c8`
- `ntdll!RtlReleaseResource` at `0x18000c5ba`
- `ntdll!RtlInitString` at `0x18000c0ee`
- `ntdll!RtlInitString` at `0x18000c0ee`
- `ntdll!RtlInitUnicodeString` at `0x18000c542`
- `ntdll!RtlInitUnicodeString` at `0x18000c542`
- `LSASRV!LsaISetLogonInfo` at `0x18000c3aa`
- `LSASRV!LsaISetLogonInfo` at `0x18000c3aa`
- `LSASRV!LsaICryptProtectData` at `0x18000c581`
- `LSASRV!LsaICryptProtectData` at `0x18000c581`

## pseudocode

```c
__int64 __fastcall NlpChangePwdCredByLogonId(unsigned int *a1, __int64 a2, int a3, int a4, _DWORD *a5)
{
  unsigned int v7; // r15d
  struct _RTL_BALANCED_NODE *v8; // rbx
  int active; // eax
  struct _RTL_BALANCED_NODE **v10; // rsi
  int v11; // edx
  int v12; // ebx
  int v13; // r8d
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rcx
  __int128 *v19; // r14
  __int128 *v20; // rbx
  int v21; // eax
  __int64 v22; // rdx
  _BYTE *v23; // rax
  __int64 v25; // rdx
  int v26; // r12d
  __int128 *v27; // rax
  __int64 v28; // rcx
  __int128 v29; // xmm0
  __int64 v30; // [rsp+60h] [rbp-61h]
  unsigned int v31; // [rsp+68h] [rbp-59h]
  int v32; // [rsp+6Ch] [rbp-55h] BYREF
  HANDLE Token; // [rsp+70h] [rbp-51h] BYREF
  int v34; // [rsp+78h] [rbp-49h] BYREF
  int v35; // [rsp+7Ch] [rbp-45h] BYREF
  __int128 v36; // [rsp+80h] [rbp-41h] BYREF
  __int64 v37; // [rsp+90h] [rbp-31h]
  HLOCAL hMem[2]; // [rsp+98h] [rbp-29h] BYREF
  struct _STRING DestinationString; // [rsp+A8h] [rbp-19h] BYREF
  struct _UNICODE_STRING v40; // [rsp+B8h] [rbp-9h] BYREF
  __int64 v41; // [rsp+C8h] [rbp+7h] BYREF

  v37 = a2;
  LODWORD(Token) = a4;
  LODWORD(v41) = a3;
  *a5 = 0;
  v7 = 0;
  v30 = 0;
  RtlAcquireResourceExclusive(&NlpActiveLogonLock, 1u);
  v8 = NlpActiveLogonTable;
  while ( v8 )
  {
    active = NlpActiveLogonCompare(a1, v8);
    if ( active < 0 )
    {
      v8 = v8->Children[0];
    }
    else
    {
      if ( active <= 0 )
        break;
      v8 = v8->Children[1];
    }
  }
  v10 = &v8[-1].Children[1];
  if ( !v8 )
    v10 = 0;
  if ( !v10 )
    goto LABEL_27;
  v32 = 0;
  *a5 = 1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
    WPP_SF_DDZZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      (unsigned int)WPP_392ea864dd3e33f07e463c681f7a5069_Traceguids,
      a1[1],
      *a1,
      a2,
      a2 + 16);
  v35 = 0;
  v34 = 0;
  DestinationString = 0;
  v36 = 0;
  RtlInitString(&DestinationString, "Primary");
  v12 = ((__int64 (__fastcall *)(char *, _QWORD, int *, _QWORD, struct _STRING *, int *, __int128 *))qword_180088228)(
          (char *)v10 + 44,
          (unsigned int)MspAuthenticationPackageId,
          &v35,
          0,
          &DestinationString,
          &v34,
          &v36);
  if ( v12 >= 0 )
  {
    v30 = 0;
    v14 = *((_QWORD *)&v36 + 1);
    ((void (__fastcall *)(_QWORD, _QWORD))qword_180088378)(*((_QWORD *)&v36 + 1), (unsigned __int16)v36);
    if ( v14 )
    {
      v15 = *(_QWORD *)(v14 + 24);
      if ( v15 )
        *(_QWORD *)(v14 + 24) = v14 + v15;
      v16 = *(_QWORD *)(v14 + 8);
      if ( v16 )
        *(_QWORD *)(v14 + 8) = v14 + v16;
      v7 = (unsigned __int16)v36;
      v17 = v14;
      v30 = v14;
    }
    else
    {
      v17 = 0;
    }
    v18 = *(_QWORD *)(a2 + 32);
    v19 = (__int128 *)(a2 + 32);
    v20 = (__int128 *)(v17 + 32);
    v31 = 0;
    if ( *(_QWORD *)(v17 + 32) == v18 )
    {
      v21 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64, int *, _QWORD, _QWORD))(*(_QWORD *)v18 + 88LL))(
              v18,
              v20,
              a2 + 32,
              &v32,
              0,
              0);
      v31 = v21;
      if ( v21 < 0 )
      {
        v7 = v21;
        goto LABEL_27;
      }
      v17 = v30;
    }
    if ( v32 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
      {
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_392ea864dd3e33f07e463c681f7a5069_Traceguids, a1[1], *a1);
        v17 = v30;
      }
      v7 = v31;
      v30 = v17;
      goto LABEL_27;
    }
    if ( (_DWORD)v41 )
    {
      v41 = 0;
      LsaISetLogonInfo(a1, 0, 0, 0, 0, 0, 0, 0, &v41, &v41, &v41);
    }
    v26 = NlpDeletePrimaryCredential((char *)v10 + 44);
    if ( v26 < 0 )
    {
      v25 = 352;
      do
      {
        *(_BYTE *)v20 = 0;
        v20 = (__int128 *)((char *)v20 + 1);
        --v25;
      }
      while ( v25 );
      ((void (__fastcall *)(__int64))LsaFunctions->FreeLsaHeap)(v30);
      RtlReleaseResource(&NlpActiveLogonLock);
      return (unsigned int)v26;
    }
    v27 = v19;
    v28 = 2;
    do
    {
      v20 += 8;
      v29 = *v27;
      v27 += 8;
      *(v20 - 8) = v29;
      *(v20 - 7) = *(v27 - 7);
      *(v20 - 6) = *(v27 - 6);
      *(v20 - 5) = *(v27 - 5);
      *(v20 - 4) = *(v27 - 4);
      *(v20 - 3) = *(v27 - 3);
      *(v20 - 2) = *(v27 - 2);
      *(v20 - 1) = *(v27 - 1);
      --v28;
    }
    while ( v28 );
    *v20 = *v27;
    v20[1] = v27[1];
    v20[2] = v27[2];
    v20[3] = v27[3];
    v20[4] = v27[4];
    v20[5] = v27[5];
    v7 = NlpAddPrimaryCredential((char *)v10 + 44, v30, v7);
    ((void (__fastcall *)(__int64))LsaFunctions->FreeLsaHeap)(v30);
    v30 = 0;
    if ( (v7 & 0x80000000) == 0 )
    {
      NlpChangeCachePassword(0, (struct _UNICODE_STRING *)(v10 + 11), (struct _UNICODE_STRING *)(v10 + 9), v19);
      if ( (_DWORD)Token )
      {
        v41 = 0;
        Token = 0;
        *(_OWORD *)hMem = 0;
        v40 = 0;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0 )
        {
          WPP_SF_DDZZ(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            30,
            (unsigned int)WPP_392ea864dd3e33f07e463c681f7a5069_Traceguids,
            a1[1],
            *a1,
            v37,
            v37 + 16);
        }
        if ( ((int (__fastcall *)(unsigned int *, HANDLE *))LsaFunctions->OpenTokenByLogonId)(a1, &Token) >= 0 )
        {
          if ( SetThreadToken(0, Token) )
          {
            RtlInitUnicodeString(&v40, L"MSV_PWD_CHANGE_DPAPI");
            if ( (unsigned __int8)LsaICryptProtectData(&v41, 8, &v40, 0, 0, 0, 0, 8, &hMem[1], hMem) )
            {
              if ( hMem[1] )
                LocalFree(hMem[1]);
            }
          }
          RevertToSelf();
        }
        if ( Token )
        {
          CloseHandle(Token);
          RtlReleaseResource(&NlpActiveLogonLock);
          return v7;
        }
      }
    }
LABEL_27:
    RtlReleaseResource(&NlpActiveLogonLock);
    if ( v30 )
    {
      v22 = 352;
      v23 = (_BYTE *)(v30 + 32);
      do
      {
        *v23++ = 0;
        --v22;
      }
      while ( v22 );
      ((void (*)(void))LsaFunctions->FreeLsaHeap)();
    }
    return v7;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sdsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      v13,
      (unsigned int)"NlpGetPrimaryCredential",
      187,
      (__int64)"GetCredentialsFailure",
      v12);
  RtlReleaseResource(&NlpActiveLogonLock);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000c000  mov     [rsp-8+arg_10], rbx
0x18000c005  push    rbp
0x18000c006  push    rsi
0x18000c007  push    rdi
0x18000c008  push    r12
0x18000c00a  push    r13
0x18000c00c  push    r14
0x18000c00e  push    r15
0x18000c010  lea     rbp, [rsp-1Fh]
0x18000c015  sub     rsp, 0E0h
0x18000c01c  mov     rax, cs:__security_cookie
0x18000c023  xor     rax, rsp
0x18000c026  mov     [rbp+4Fh+var_40], rax
0x18000c02a  mov     r14, [rbp+4Fh+arg_20]
0x18000c02e  xor     r13d, r13d
0x18000c031  mov     r12, rdx
0x18000c034  mov     [rbp+4Fh+var_80], rdx
0x18000c038  mov     rdi, rcx
0x18000c03b  mov     dword ptr [rbp+4Fh+Token], r9d
0x18000c03f  mov     dl, 1; Wait
0x18000c041  mov     dword ptr [rbp+4Fh+var_48], r8d
0x18000c045  lea     rcx, NlpActiveLogonLock; Resource
0x18000c04c  mov     [r14], r13d
0x18000c04f  mov     r15d, r13d
0x18000c052  mov     [rbp+4Fh+var_B0], r13
0x18000c056  call    cs:__imp_RtlAcquireResourceExclusive
0x18000c05c  mov     rbx, cs:NlpActiveLogonTable
0x18000c063  test    rbx, rbx
0x18000c066  jz      short loc_18000C08E
0x18000c068  nop     dword ptr [rax+rax+00000000h]
0x18000c070  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x18000c073  mov     rcx, rdi; void *
0x18000c076  call    ?NlpActiveLogonCompare@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; NlpActiveLogonCompare(void *,_RTL_BALANCED_NODE *)
0x18000c07b  test    eax, eax
0x18000c07d  js      loc_18000C269
0x18000c083  jle     short loc_18000C08E
0x18000c085  mov     rbx, [rbx+8]
0x18000c089  test    rbx, rbx
0x18000c08c  jnz     short loc_18000C070
0x18000c08e  test    rbx, rbx
0x18000c091  lea     rsi, [rbx-10h]
0x18000c095  cmovz   rsi, r13
0x18000c099  test    rsi, rsi
0x18000c09c  jz      loc_18000C203
0x18000c0a2  mov     [rbp+4Fh+var_A4], r13d
0x18000c0a6  mov     dword ptr [r14], 1
0x18000c0ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0b4  lea     r14, WPP_GLOBAL_Control
0x18000c0bb  cmp     rcx, r14
0x18000c0be  jz      short loc_18000C0CD
0x18000c0c0  test    dword ptr [rcx+1Ch], 1000h
0x18000c0c7  jnz     loc_18000C2D6
0x18000c0cd  xorps   xmm0, xmm0
0x18000c0d0  mov     [rbp+4Fh+var_94], r13d
0x18000c0d4  xorps   xmm1, xmm1
0x18000c0d7  mov     [rbp+4Fh+var_98], r13d
0x18000c0db  lea     rdx, SourceString; "Primary"
0x18000c0e2  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x18000c0e6  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x18000c0ea  movups  [rbp+4Fh+var_90], xmm1
0x18000c0ee  call    cs:__imp_RtlInitString
0x18000c0f4  mov     edx, cs:MspAuthenticationPackageId
0x18000c0fa  lea     rax, [rbp+4Fh+var_90]
0x18000c0fe  mov     [rsp+110h+var_E0], rax
0x18000c103  lea     r8, [rbp+4Fh+var_94]
0x18000c107  lea     rax, [rbp+4Fh+var_98]
0x18000c10b  xor     r9d, r9d
0x18000c10e  mov     [rsp+110h+var_E8], rax
0x18000c113  lea     rcx, [rsi+2Ch]
0x18000c117  lea     rax, [rbp+4Fh+DestinationString]
0x18000c11b  mov     [rsp+110h+var_F0], rax
0x18000c120  mov     rax, cs:qword_180088228
0x18000c127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c12c  mov     ebx, eax
0x18000c12e  test    eax, eax
0x18000c130  js      loc_18000C271
0x18000c136  movzx   edx, word ptr [rbp+4Fh+var_90]
0x18000c13a  xor     ebx, ebx
0x18000c13c  mov     rax, cs:qword_180088378
0x18000c143  mov     [rbp+4Fh+var_B0], rbx
0x18000c147  mov     rbx, qword ptr [rbp+4Fh+var_90+8]
0x18000c14b  mov     rcx, rbx
0x18000c14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c153  test    rbx, rbx
0x18000c156  jz      loc_18000C298
0x18000c15c  mov     rax, [rbx+18h]
0x18000c160  test    rax, rax
0x18000c163  jz      short loc_18000C16C
0x18000c165  add     rax, rbx
0x18000c168  mov     [rbx+18h], rax
0x18000c16c  mov     rax, [rbx+8]
0x18000c170  test    rax, rax
0x18000c173  jz      short loc_18000C17C
0x18000c175  add     rax, rbx
0x18000c178  mov     [rbx+8], rax
0x18000c17c  movzx   r15d, word ptr [rbp+4Fh+var_90]
0x18000c181  mov     rax, rbx
0x18000c184  mov     [rbp+4Fh+var_B0], rbx
0x18000c188  mov     rcx, [r12+20h]
0x18000c18d  lea     r14, [r12+20h]
0x18000c192  xor     edx, edx
0x18000c194  lea     rbx, [rax+20h]
0x18000c198  mov     [rbp+4Fh+var_A8], edx
0x18000c19b  cmp     [rbx], rcx
0x18000c19e  jnz     short loc_18000C1D1
0x18000c1a0  mov     rax, [rcx]
0x18000c1a3  lea     r9, [rbp+4Fh+var_A4]
0x18000c1a7  mov     [rsp+110h+var_E8], rdx
0x18000c1ac  mov     r8, r14
0x18000c1af  mov     [rsp+110h+var_F0], rdx
0x18000c1b4  mov     rdx, rbx
0x18000c1b7  mov     rax, [rax+58h]
0x18000c1bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1c0  mov     [rbp+4Fh+var_A8], eax
0x18000c1c3  test    eax, eax
0x18000c1c5  js      loc_18000C336
0x18000c1cb  mov     rax, [rbp+4Fh+var_B0]
0x18000c1cf  xor     edx, edx
0x18000c1d1  cmp     [rbp+4Fh+var_A4], r13d
0x18000c1d5  jz      loc_18000C366
0x18000c1db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c1e2  lea     rdx, WPP_GLOBAL_Control
0x18000c1e9  cmp     rcx, rdx
0x18000c1ec  jz      short loc_18000C1FB
0x18000c1ee  test    dword ptr [rcx+1Ch], 1000h
0x18000c1f5  jnz     loc_18000C33E
0x18000c1fb  mov     r15d, [rbp+4Fh+var_A8]
0x18000c1ff  mov     [rbp+4Fh+var_B0], rax
0x18000c203  lea     rcx, NlpActiveLogonLock; Resource
0x18000c20a  call    cs:__imp_RtlReleaseResource
0x18000c210  mov     rcx, [rbp+4Fh+var_B0]
0x18000c214  test    rcx, rcx
0x18000c217  jz      short loc_18000C23F
0x18000c219  mov     edx, 160h
0x18000c21e  lea     rax, [rcx+20h]
0x18000c222  mov     [rax], r13b
0x18000c225  lea     rax, [rax+1]
0x18000c229  sub     rdx, 1
0x18000c22d  jnz     short loc_18000C222
0x18000c22f  mov     rax, cs:LsaFunctions
0x18000c236  mov     rax, [rax+30h]
0x18000c23a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c23f  mov     eax, r15d
0x18000c242  mov     rcx, [rbp+4Fh+var_40]
0x18000c246  xor     rcx, rsp; StackCookie
0x18000c249  call    __security_check_cookie
0x18000c24e  mov     rbx, [rsp+110h+arg_10]
0x18000c256  add     rsp, 0E0h
0x18000c25d  pop     r15
0x18000c25f  pop     r14
0x18000c261  pop     r13
0x18000c263  pop     r12
0x18000c265  pop     rdi
0x18000c266  pop     rsi
0x18000c267  pop     rbp
0x18000c268  retn
0x18000c269  mov     rbx, [rbx]
0x18000c26c  jmp     loc_18000C089
0x18000c271  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c278  cmp     rcx, r14
0x18000c27b  jz      short loc_18000C287
0x18000c27d  test    byte ptr [rcx+1Ch], 1
0x18000c281  jnz     loc_18000C309
0x18000c287  lea     rcx, NlpActiveLogonLock; Resource
0x18000c28e  call    cs:__imp_RtlReleaseResource
0x18000c294  mov     eax, ebx
0x18000c296  jmp     short loc_18000C242
0x18000c298  mov     rax, r13
0x18000c29b  jmp     loc_18000C188
0x18000c2a0  mov     [rbx], r13b
0x18000c2a3  lea     rbx, [rbx+1]
0x18000c2a7  sub     rdx, 1
0x18000c2ab  jnz     short loc_18000C2A0
0x18000c2ad  mov     rax, cs:LsaFunctions
0x18000c2b4  mov     rcx, [rbp+4Fh+var_B0]
0x18000c2b8  mov     rax, [rax+30h]
0x18000c2bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2c1  lea     rcx, NlpActiveLogonLock; Resource
0x18000c2c8  call    cs:__imp_RtlReleaseResource
0x18000c2ce  mov     eax, r12d
0x18000c2d1  jmp     loc_18000C242
0x18000c2d6  mov     r9d, [rdi+4]
0x18000c2da  lea     rax, [r12+10h]
0x18000c2df  mov     rcx, [rcx+10h]
0x18000c2e3  lea     r8, WPP_392ea864dd3e33f07e463c681f7a5069_Traceguids
0x18000c2ea  mov     [rsp+110h+var_E0], rax
0x18000c2ef  mov     edx, 1Ch
0x18000c2f4  mov     eax, [rdi]
0x18000c2f6  mov     [rsp+110h+var_E8], r12
0x18000c2fb  mov     dword ptr [rsp+110h+var_F0], eax
0x18000c2ff  call    WPP_SF_DDZZ
0x18000c304  jmp     loc_18000C0CD
0x18000c309  mov     rcx, [rcx+10h]
0x18000c30d  lea     rax, aGetcredentials; "GetCredentialsFailure"
0x18000c314  mov     dword ptr [rsp+110h+var_E0], ebx
0x18000c318  lea     r9, aNlpgetprimaryc; "NlpGetPrimaryCredential"
0x18000c31f  mov     [rsp+110h+var_E8], rax
0x18000c324  mov     dword ptr [rsp+110h+var_F0], 9BBh
0x18000c32c  call    WPP_SF_sdsD
0x18000c331  jmp     loc_18000C287
0x18000c336  mov     r15d, eax
0x18000c339  jmp     loc_18000C203
0x18000c33e  mov     eax, [rdi]
0x18000c340  lea     r8, WPP_392ea864dd3e33f07e463c681f7a5069_Traceguids
0x18000c347  mov     r9d, [rdi+4]
0x18000c34b  mov     edx, 1Dh
0x18000c350  mov     rcx, [rcx+10h]
0x18000c354  mov     dword ptr [rsp+110h+var_F0], eax
0x18000c358  call    WPP_SF_dd
0x18000c35d  mov     rax, [rbp+4Fh+var_B0]
0x18000c361  jmp     loc_18000C1FB
0x18000c366  cmp     dword ptr [rbp+4Fh+var_48], r13d
0x18000c36a  jz      short loc_18000C3B0
0x18000c36c  lea     rax, [rbp+4Fh+var_48]
0x18000c370  mov     [rbp+4Fh+var_48], r13
0x18000c374  mov     [rsp+110h+var_C0], rax
0x18000c379  xor     r9d, r9d
0x18000c37c  lea     rax, [rbp+4Fh+var_48]
0x18000c380  xor     r8d, r8d
0x18000c383  mov     [rsp+110h+var_C8], rax
0x18000c388  mov     rcx, rdi
0x18000c38b  lea     rax, [rbp+4Fh+var_48]
0x18000c38f  mov     [rsp+110h+var_D0], rax
0x18000c394  mov     [rsp+110h+var_D8], rdx
0x18000c399  mov     [rsp+110h+var_E0], rdx
0x18000c39e  mov     [rsp+110h+var_E8], rdx
0x18000c3a3  mov     [rsp+110h+var_F0], rdx
0x18000c3a8  xor     edx, edx
0x18000c3aa  call    cs:__imp_LsaISetLogonInfo
0x18000c3b0  lea     rcx, [rsi+2Ch]
0x18000c3b4  call    NlpDeletePrimaryCredential
0x18000c3b9  mov     r12d, eax
0x18000c3bc  test    eax, eax
0x18000c3be  jns     short loc_18000C3CA
0x18000c3c0  mov     edx, 160h
0x18000c3c5  jmp     loc_18000C2A0
0x18000c3ca  mov     rax, r14
0x18000c3cd  mov     ecx, 2
0x18000c3d2  lea     rbx, [rbx+80h]
0x18000c3d9  movups  xmm0, xmmword ptr [rax]
0x18000c3dc  lea     rax, [rax+80h]
0x18000c3e3  movups  xmmword ptr [rbx-80h], xmm0
0x18000c3e7  movups  xmm1, xmmword ptr [rax-70h]
0x18000c3eb  movups  xmmword ptr [rbx-70h], xmm1
0x18000c3ef  movups  xmm0, xmmword ptr [rax-60h]
0x18000c3f3  movups  xmmword ptr [rbx-60h], xmm0
0x18000c3f7  movups  xmm1, xmmword ptr [rax-50h]
0x18000c3fb  movups  xmmword ptr [rbx-50h], xmm1
0x18000c3ff  movups  xmm0, xmmword ptr [rax-40h]
0x18000c403  movups  xmmword ptr [rbx-40h], xmm0
0x18000c407  movups  xmm1, xmmword ptr [rax-30h]
0x18000c40b  movups  xmmword ptr [rbx-30h], xmm1
0x18000c40f  movups  xmm0, xmmword ptr [rax-20h]
0x18000c413  movups  xmmword ptr [rbx-20h], xmm0
0x18000c417  movups  xmm1, xmmword ptr [rax-10h]
0x18000c41b  movups  xmmword ptr [rbx-10h], xmm1
0x18000c41f  sub     rcx, 1
0x18000c423  jnz     short loc_18000C3D2
0x18000c425  movups  xmm0, xmmword ptr [rax]
0x18000c428  mov     rdx, [rbp+4Fh+var_B0]
0x18000c42c  lea     rcx, [rsi+2Ch]
0x18000c430  mov     r8d, r15d
0x18000c433  movups  xmmword ptr [rbx], xmm0
0x18000c436  movups  xmm1, xmmword ptr [rax+10h]
0x18000c43a  movups  xmmword ptr [rbx+10h], xmm1
0x18000c43e  movups  xmm0, xmmword ptr [rax+20h]
0x18000c442  movups  xmmword ptr [rbx+20h], xmm0
0x18000c446  movups  xmm1, xmmword ptr [rax+30h]
0x18000c44a  movups  xmmword ptr [rbx+30h], xmm1
0x18000c44e  movups  xmm0, xmmword ptr [rax+40h]
0x18000c452  movups  xmmword ptr [rbx+40h], xmm0
0x18000c456  movups  xmm1, xmmword ptr [rax+50h]
0x18000c45a  movups  xmmword ptr [rbx+50h], xmm1
0x18000c45e  call    NlpAddPrimaryCredential
0x18000c463  mov     rcx, [rbp+4Fh+var_B0]
0x18000c467  mov     r15d, eax
0x18000c46a  mov     rax, cs:LsaFunctions
0x18000c471  mov     rax, [rax+30h]
0x18000c475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c47a  xor     r12d, r12d
0x18000c47d  mov     [rbp+4Fh+var_B0], r12
0x18000c481  test    r15d, r15d
0x18000c484  js      loc_18000C203
0x18000c48a  lea     r8, [rsi+48h]
0x18000c48e  mov     r9, r14
0x18000c491  lea     rdx, [rsi+58h]
0x18000c495  xor     ecx, ecx
0x18000c497  call    NlpChangeCachePassword
0x18000c49c  cmp     dword ptr [rbp+4Fh+Token], r12d
0x18000c4a0  jz      loc_18000C203
0x18000c4a6  xorps   xmm0, xmm0
0x18000c4a9  mov     [rbp+4Fh+var_48], r12
0x18000c4ad  xorps   xmm1, xmm1
0x18000c4b0  mov     [rbp+4Fh+Token], r12
0x18000c4b4  movups  xmmword ptr [rbp+4Fh+hMem], xmm0
0x18000c4b8  movups  xmmword ptr [rbp+4Fh+var_58.Length], xmm1
0x18000c4bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4c3  lea     rdx, WPP_GLOBAL_Control
0x18000c4ca  cmp     rcx, rdx
0x18000c4cd  jz      short loc_18000C509
  ... truncated ...
```
