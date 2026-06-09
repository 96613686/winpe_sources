# SspMapContext

- ea: `0x18000b960`
- end: `0x18000bff3`
- name: `SspMapContext`
- size: `1683`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014dc0`
- `0x180025ff0`

## callees

- `0x18000b960`
- `0x18000c630`
- `0x18002ee3c`
- `0x18002ee7c`
- `0x18002f014`
- `0x18002fb50`
- `0x18002fb90`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bc5b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000bc5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf6a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000be34`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000be34`
- `ntdll!NtOpenThreadToken` at `0x18000bcba`
- `ntdll!NtOpenThreadToken` at `0x18000bcba`
- `ntdll!NtClose` at `0x18000bf9a`
- `ntdll!NtClose` at `0x18000bf9a`
- `ntdll!RtlReleaseResource` at `0x18000baa4`
- `ntdll!RtlReleaseResource` at `0x18000baa4`
- `ntdll!RtlAcquireResourceShared` at `0x18000b9fb`
- `ntdll!RtlAcquireResourceShared` at `0x18000b9fb`
- `ntdll!NtSetInformationThread` at `0x18000bcf0`
- `ntdll!NtSetInformationThread` at `0x18000bd37`
- `ntdll!NtSetInformationThread` at `0x18000bcf0`
- `ntdll!NtSetInformationThread` at `0x18000bd37`
- `SspiCli!GetUserNameExW` at `0x18000bd12`
- `SspiCli!GetUserNameExW` at `0x18000bd12`

## pseudocode

```c
__int64 __fastcall SspMapContext(__int64 *a1, _OWORD *a2, int a3, _QWORD *a4, _QWORD *a5, int a6, __int64 a7)
{
  __int64 v7; // r15
  __int64 v8; // rsi
  char v9; // r12
  const void **v10; // rdi
  char *v11; // rsi
  struct _RTL_BALANCED_NODE *v12; // rbx
  int active; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int v16; // ecx
  unsigned int v17; // edx
  NTSTATUS v18; // ebx
  __int64 result; // rax
  unsigned int v20; // esi
  _DWORD *v21; // rax
  _DWORD *v22; // rdi
  _OWORD *v23; // rax
  size_t v24; // r8
  int v25; // ecx
  __int64 v26; // rcx
  unsigned int v27; // r14d
  unsigned int v28; // eax
  _QWORD *v29; // rax
  void *v30; // rcx
  __int64 v31; // rax
  NTSTATUS v32; // eax
  __int64 v33; // rcx
  int v34; // ecx
  __int64 v35; // rbx
  unsigned __int64 v36; // rax
  size_t v37; // r8
  int v38; // ecx
  __int64 v39; // rbx
  DWORD LastError; // eax
  unsigned int v41; // eax
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  int v45; // [rsp+44h] [rbp-BCh]
  _OWORD *v46; // [rsp+48h] [rbp-B8h]
  _QWORD *v47; // [rsp+50h] [rbp-B0h]
  _OWORD TokenInformation[3]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v49; // [rsp+88h] [rbp-78h]
  WCHAR Src[1032]; // [rsp+90h] [rbp-70h] BYREF

  v7 = *a1;
  v46 = a2;
  v47 = a4;
  v45 = a3;
  v49 = 0;
  LODWORD(Size) = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( !v7 )
  {
    v18 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 136, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids, 0);
    return (unsigned int)v18;
  }
  if ( !*(_DWORD *)(v7 + 272) )
  {
    v8 = *(_QWORD *)(v7 + 88);
    v9 = 0;
    v10 = 0;
    if ( v8 )
    {
      v11 = (char *)(v8 + 24);
      if ( !v11 )
        goto LABEL_12;
    }
    else
    {
      if ( (a3 & 0x4000) == 0 )
        goto LABEL_12;
      if ( *(_WORD *)(v7 + 136) )
        goto LABEL_12;
      if ( *(_QWORD *)(v7 + 144) )
        goto LABEL_12;
      if ( *(_WORD *)(v7 + 120) )
        goto LABEL_12;
      if ( *(_QWORD *)(v7 + 128) )
        goto LABEL_12;
      v30 = *(void **)(v7 + 80);
      if ( !v30 )
        goto LABEL_12;
      ReturnLength = 56;
      if ( !GetTokenInformation(v30, TokenStatistics, TokenInformation, 0x38u, &ReturnLength) )
        goto LABEL_12;
      v11 = (char *)TokenInformation + 8;
    }
    RtlAcquireResourceShared(&NlpActiveLogonLock, 1u);
    v12 = NlpActiveLogonTable;
    v9 = 1;
    while ( v12 )
    {
      active = NlpActiveLogonCompare(v11, v12);
      if ( active < 0 )
      {
        v12 = v12->Children[0];
      }
      else
      {
        if ( active <= 0 )
          break;
        v12 = v12->Children[1];
      }
    }
    v10 = (const void **)&v12[-1].Children[1];
    if ( !v12 )
      v10 = 0;
LABEL_12:
    Src[0] = 0;
    if ( v10 )
    {
      v14 = *((unsigned __int16 *)v10 + 36);
      if ( (_WORD)v14 )
      {
        v33 = *((unsigned __int16 *)v10 + 44);
        if ( (_WORD)v33 )
        {
          if ( (unsigned __int64)(v14 + v33 + 4) <= 0x808 )
          {
            memcpy_0(Src, v10[12], *((unsigned __int16 *)v10 + 44));
            v34 = *((unsigned __int16 *)v10 + 44) >> 1;
            Src[v34] = 92;
            v35 = (unsigned int)(v34 + 1);
            LODWORD(Size) = v34 + 1;
            memcpy_0(&Src[v35], v10[10], *((unsigned __int16 *)v10 + 36));
            v36 = (unsigned int)v35 + (*((unsigned __int16 *)v10 + 36) >> 1);
LABEL_66:
            if ( 2 * v36 >= 0x808 )
              _report_rangecheckfailure();
            Src[v36] = 0;
            goto LABEL_14;
          }
          v18 = -1073741823;
          goto LABEL_18;
        }
      }
    }
    else
    {
      if ( *(_WORD *)(v7 + 120) )
      {
        if ( *(_WORD *)(v7 + 136) )
        {
          v37 = *(unsigned __int16 *)(v7 + 120);
          if ( *(unsigned __int16 *)(v7 + 136) + v37 + 4 <= 0x808 )
          {
            memcpy_0(Src, *(const void **)(v7 + 128), v37);
            v38 = *(unsigned __int16 *)(v7 + 120) >> 1;
            Src[v38] = 92;
            v39 = (unsigned int)(v38 + 1);
            LODWORD(Size) = v38 + 1;
            memcpy_0(&Src[v39], *(const void **)(v7 + 144), *(unsigned __int16 *)(v7 + 136));
            v36 = (unsigned int)v39 + (*(unsigned __int16 *)(v7 + 136) >> 1);
            goto LABEL_66;
          }
          v18 = -1073741823;
LABEL_18:
          if ( v9 )
            RtlReleaseResource(&NlpActiveLogonLock);
          return (unsigned int)v18;
        }
      }
      else
      {
        v31 = *(unsigned __int16 *)(v7 + 136);
        if ( (_WORD)v31 )
        {
          if ( (unsigned __int64)(v31 + 2) <= 0x808 )
          {
            memcpy_0(&Src[(unsigned int)Size], *(const void **)(v7 + 144), *(unsigned __int16 *)(v7 + 136));
            v36 = (unsigned __int64)*(unsigned __int16 *)(v7 + 136) >> 1;
            goto LABEL_66;
          }
          v18 = -1073741823;
          goto LABEL_18;
        }
      }
      if ( *(_QWORD *)(v7 + 80) )
      {
        TokenHandle = 0;
        v32 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
        v18 = v32;
        if ( v32 < 0 )
        {
          if ( v32 != -1073741700 )
            goto LABEL_18;
          TokenHandle = 0;
        }
        v18 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, (PVOID)(v7 + 80), 8u);
        if ( v18 >= 0 )
        {
          LODWORD(Size) = 1028;
          if ( !GetUserNameExW(NameSamCompatible, Src, (PULONG)&Size) )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              LastError = GetLastError();
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                137,
                WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids,
                LastError);
            }
            Src[0] = 0;
          }
        }
        NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
        if ( TokenHandle )
          NtClose(TokenHandle);
        if ( v18 < 0 )
          goto LABEL_18;
      }
    }
LABEL_14:
    v15 = -1;
    do
      ++v15;
    while ( Src[v15] );
    LODWORD(Size) = 2 * v15;
    v16 = 2 * v15 + 170;
    v17 = v16 + *(_DWORD *)(v7 + 184);
    if ( v17 < v16 || (v20 = v17 + *(_DWORD *)(v7 + 344), v20 < v17) )
    {
      v18 = -1073741675;
    }
    else
    {
      if ( NtLmState == 1 )
        v21 = (_DWORD *)((__int64 (__fastcall *)(_QWORD))LsaFunctions->AllocateLsaHeap)(v20);
      else
        v21 = LocalAlloc(0x40u, v20);
      v22 = v21;
      if ( v21 )
      {
        v21[1] = v45;
        v18 = 0;
        v23 = v46;
        v22[2] = 0;
        *(_OWORD *)(v22 + 5) = *v23;
        if ( v20 <= 0xA8 )
        {
          *(_QWORD *)(v22 + 15) = 0;
          v25 = 0;
        }
        else
        {
          v22[15] = 168;
          v24 = (unsigned int)Size;
          v22[16] = Size;
          memcpy_0(v22 + 42, Src, v24);
          v22[16] += 2;
          v25 = v22[16];
        }
        v26 = (unsigned int)(v25 + 168);
        if ( *(_QWORD *)(v7 + 176) )
        {
          v22[17] = v26;
          v41 = *(_DWORD *)(v7 + 184);
          v22[18] = v41;
          v27 = v41 + v26;
          memcpy_0((char *)v22 + v26, *(const void **)(v7 + 176), v41);
        }
        else
        {
          v27 = v26;
        }
        if ( *(_QWORD *)(v7 + 336) )
        {
          v22[35] = v27;
          v28 = *(_DWORD *)(v7 + 344);
          v22[36] = v28;
          memcpy_0((char *)v22 + v27, *(const void **)(v7 + 336), v28);
        }
        v29 = v47;
        *(_QWORD *)(v22 + 3) = 0;
        *(_QWORD *)(a7 + 8) = v22;
        *(_DWORD *)a7 = v20;
        if ( v29 )
          *((_QWORD *)v22 + 6) = *v29;
        else
          *((_QWORD *)v22 + 6) = 0;
        if ( a5 )
          *((_QWORD *)v22 + 5) = *a5;
        else
          *((_QWORD *)v22 + 5) = 0;
        v22[14] = a6;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids);
        v18 = -1073741670;
      }
    }
    goto LABEL_18;
  }
  result = 0;
  *(_OWORD *)a7 = *(_OWORD *)(v7 + 272);
  *(_OWORD *)(v7 + 272) = 0;
  return result;
}

```

## disassembly

```asm
0x18000b960  push    rbp
0x18000b962  push    rbx
0x18000b963  push    rsi
0x18000b964  push    rdi
0x18000b965  push    r12
0x18000b967  push    r13
0x18000b969  push    r14
0x18000b96b  push    r15
0x18000b96d  lea     rbp, [rsp-7B8h]
0x18000b975  sub     rsp, 8B8h
0x18000b97c  mov     rax, cs:__security_cookie
0x18000b983  xor     rax, rsp
0x18000b986  mov     [rbp+7F0h+var_50], rax
0x18000b98d  mov     r15, [rcx]
0x18000b990  xorps   xmm0, xmm0
0x18000b993  mov     r13, [rbp+7F0h+arg_30]
0x18000b99a  mov     eax, r8d
0x18000b99d  mov     [rsp+8F0h+var_8A8], rdx
0x18000b9a2  xor     edx, edx
0x18000b9a4  mov     [rsp+8F0h+var_8A0], r9
0x18000b9a9  mov     [rsp+8F0h+var_8AC], eax
0x18000b9ad  mov     [rbp+7F0h+var_868], rdx
0x18000b9b1  mov     dword ptr [rsp+8F0h+Size], edx
0x18000b9b5  movups  [rsp+8F0h+TokenInformation], xmm0
0x18000b9ba  movups  [rsp+8F0h+var_888], xmm0
0x18000b9bf  movups  [rsp+8F0h+var_878], xmm0
0x18000b9c4  test    r15, r15
0x18000b9c7  jz      loc_18000BE45
0x18000b9cd  cmp     [r15+110h], edx
0x18000b9d4  jnz     loc_18000BD58
0x18000b9da  mov     rsi, [r15+58h]
0x18000b9de  xor     r12b, r12b
0x18000b9e1  xor     edi, edi
0x18000b9e3  test    rsi, rsi
0x18000b9e6  jz      loc_18000BBEF
0x18000b9ec  add     rsi, 18h
0x18000b9f0  jz      short loc_18000BA3B
0x18000b9f2  mov     dl, 1; Wait
0x18000b9f4  lea     rcx, NlpActiveLogonLock; Resource
0x18000b9fb  call    cs:__imp_RtlAcquireResourceShared
0x18000ba01  mov     rbx, cs:NlpActiveLogonTable
0x18000ba08  mov     r12b, 1
0x18000ba0b  test    rbx, rbx
0x18000ba0e  jz      short loc_18000BA2E
0x18000ba10  mov     rdx, rbx; struct _RTL_BALANCED_NODE *
0x18000ba13  mov     rcx, rsi; void *
0x18000ba16  call    ?NlpActiveLogonCompare@@YAJPEAXPEAU_RTL_BALANCED_NODE@@@Z; NlpActiveLogonCompare(void *,_RTL_BALANCED_NODE *)
0x18000ba1b  test    eax, eax
0x18000ba1d  js      loc_18000BACF
0x18000ba23  jle     short loc_18000BA2E
0x18000ba25  mov     rbx, [rbx+8]
0x18000ba29  test    rbx, rbx
0x18000ba2c  jnz     short loc_18000BA10
0x18000ba2e  xor     eax, eax
0x18000ba30  lea     rdi, [rbx-10h]
0x18000ba34  test    rbx, rbx
0x18000ba37  cmovz   rdi, rax
0x18000ba3b  xor     eax, eax
0x18000ba3d  lea     r14, WPP_GLOBAL_Control
0x18000ba44  mov     [rbp+7F0h+Src], ax
0x18000ba48  test    rdi, rdi
0x18000ba4b  jz      loc_18000BC73
0x18000ba51  movzx   eax, word ptr [rdi+48h]
0x18000ba55  test    ax, ax
0x18000ba58  jnz     loc_18000BDAE
0x18000ba5e  lea     rcx, [rbp+7F0h+Src]
0x18000ba62  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000ba69  nop     dword ptr [rax+00000000h]
0x18000ba70  inc     rax
0x18000ba73  cmp     word ptr [rcx+rax*2], 0
0x18000ba78  jnz     short loc_18000BA70
0x18000ba7a  add     eax, eax
0x18000ba7c  mov     dword ptr [rsp+8F0h+Size], eax
0x18000ba80  mov     edx, [r15+0B8h]
0x18000ba87  lea     ecx, [rax+0AAh]
0x18000ba8d  add     edx, ecx
0x18000ba8f  cmp     edx, ecx
0x18000ba91  jnb     short loc_18000BAD7
0x18000ba93  mov     ebx, 0C0000095h
0x18000ba98  test    r12b, r12b
0x18000ba9b  jz      short loc_18000BAAA
0x18000ba9d  lea     rcx, NlpActiveLogonLock; Resource
0x18000baa4  call    cs:__imp_RtlReleaseResource
0x18000baaa  mov     eax, ebx
0x18000baac  mov     rcx, [rbp+7F0h+var_50]
0x18000bab3  xor     rcx, rsp; StackCookie
0x18000bab6  call    __security_check_cookie
0x18000babb  add     rsp, 8B8h
0x18000bac2  pop     r15
0x18000bac4  pop     r14
0x18000bac6  pop     r13
0x18000bac8  pop     r12
0x18000baca  pop     rdi
0x18000bacb  pop     rsi
0x18000bacc  pop     rbx
0x18000bacd  pop     rbp
0x18000bace  retn
0x18000bacf  mov     rbx, [rbx]
0x18000bad2  jmp     loc_18000BA29
0x18000bad7  mov     esi, [r15+158h]
0x18000bade  add     esi, edx
0x18000bae0  cmp     esi, edx
0x18000bae2  jb      short loc_18000BA93
0x18000bae4  cmp     cs:NtLmState, 1
0x18000baeb  jnz     loc_18000BE2D
0x18000baf1  mov     rax, cs:LsaFunctions
0x18000baf8  mov     ecx, esi
0x18000bafa  mov     rax, [rax+28h]
0x18000bafe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb03  mov     rdi, rax
0x18000bb06  test    rax, rax
0x18000bb09  jz      loc_18000BD89
0x18000bb0f  mov     eax, [rsp+8F0h+var_8AC]
0x18000bb13  xor     edx, edx
0x18000bb15  mov     [rdi+4], eax
0x18000bb18  mov     ebx, edx
0x18000bb1a  mov     rax, [rsp+8F0h+var_8A8]
0x18000bb1f  mov     [rdi+8], edx
0x18000bb22  movups  xmm0, xmmword ptr [rax]
0x18000bb25  movups  xmmword ptr [rdi+14h], xmm0
0x18000bb29  cmp     esi, 0A8h
0x18000bb2f  jbe     loc_18000BDA3
0x18000bb35  mov     dword ptr [rdi+3Ch], 0A8h
0x18000bb3c  lea     rcx, [rdi+0A8h]; void *
0x18000bb43  mov     eax, dword ptr [rsp+8F0h+Size]
0x18000bb47  lea     rdx, [rbp+7F0h+Src]; Src
0x18000bb4b  mov     r8d, eax; Size
0x18000bb4e  mov     [rdi+40h], eax
0x18000bb51  call    memcpy_0
0x18000bb56  add     dword ptr [rdi+40h], 2
0x18000bb5a  mov     ecx, [rdi+40h]
0x18000bb5d  xor     edx, edx
0x18000bb5f  add     ecx, 0A8h
0x18000bb65  cmp     [r15+0B0h], rbx
0x18000bb6c  jnz     loc_18000BFC9
0x18000bb72  mov     r14d, ecx
0x18000bb75  cmp     [r15+150h], rbx
0x18000bb7c  jz      short loc_18000BBA9
0x18000bb7e  mov     [rdi+8Ch], r14d
0x18000bb85  mov     eax, [r15+158h]
0x18000bb8c  mov     [rdi+90h], eax
0x18000bb92  mov     r8d, eax; Size
0x18000bb95  mov     rdx, [r15+150h]; Src
0x18000bb9c  mov     ecx, r14d
0x18000bb9f  add     rcx, rdi; void *
0x18000bba2  call    memcpy_0
0x18000bba7  xor     edx, edx
0x18000bba9  mov     rax, [rsp+8F0h+var_8A0]
0x18000bbae  mov     [rdi+0Ch], rbx
0x18000bbb2  mov     [r13+8], rdi
0x18000bbb6  mov     [r13+0], esi
0x18000bbba  test    rax, rax
0x18000bbbd  jz      loc_18000BD77
0x18000bbc3  mov     rax, [rax]
0x18000bbc6  mov     [rdi+30h], rax
0x18000bbca  mov     rax, [rbp+7F0h+arg_20]
0x18000bbd1  test    rax, rax
0x18000bbd4  jz      loc_18000BD80
0x18000bbda  mov     rax, [rax]
0x18000bbdd  mov     [rdi+28h], rax
0x18000bbe1  mov     eax, [rbp+7F0h+arg_28]
0x18000bbe7  mov     [rdi+38h], eax
0x18000bbea  jmp     loc_18000BA98
0x18000bbef  bt      eax, 0Eh
0x18000bbf3  jnb     loc_18000BA3B
0x18000bbf9  cmp     [r15+88h], dx
0x18000bc01  jnz     loc_18000BA3B
0x18000bc07  cmp     [r15+90h], rdx
0x18000bc0e  jnz     loc_18000BA3B
0x18000bc14  cmp     [r15+78h], dx
0x18000bc19  jnz     loc_18000BA3B
0x18000bc1f  cmp     [r15+80h], rdx
0x18000bc26  jnz     loc_18000BA3B
0x18000bc2c  mov     rcx, [r15+50h]; TokenHandle
0x18000bc30  test    rcx, rcx
0x18000bc33  jz      loc_18000BA3B
0x18000bc39  lea     rax, [rsp+8F0h+var_8B0]
0x18000bc3e  mov     [rsp+8F0h+var_8B0], 38h ; '8'
0x18000bc46  mov     r9d, 38h ; '8'; TokenInformationLength
0x18000bc4c  mov     [rsp+8F0h+ReturnLength], rax; ReturnLength
0x18000bc51  lea     r8, [rsp+8F0h+TokenInformation]; TokenInformation
0x18000bc56  mov     edx, 0Ah; TokenInformationClass
0x18000bc5b  call    cs:__imp_GetTokenInformation
0x18000bc61  test    eax, eax
0x18000bc63  jz      loc_18000BA3B
0x18000bc69  lea     rsi, [rsp+8F0h+TokenInformation+8]
0x18000bc6e  jmp     loc_18000B9F2
0x18000bc73  movzx   eax, word ptr [r15+78h]
0x18000bc78  test    ax, ax
0x18000bc7b  jnz     loc_18000BE92
0x18000bc81  movzx   eax, word ptr [r15+88h]
0x18000bc89  test    ax, ax
0x18000bc8c  jnz     loc_18000BF17
0x18000bc92  cmp     qword ptr [r15+50h], 0
0x18000bc97  jz      loc_18000BA5E
0x18000bc9d  lea     r9, [rsp+8F0h+TokenHandle]; TokenHandle
0x18000bca2  mov     [rsp+8F0h+TokenHandle], 0
0x18000bcab  mov     r8b, 1; OpenAsSelf
0x18000bcae  mov     edx, 0Ch; DesiredAccess
0x18000bcb3  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000bcba  call    cs:__imp_NtOpenThreadToken
0x18000bcc0  mov     ebx, eax
0x18000bcc2  test    eax, eax
0x18000bcc4  jns     short loc_18000BCDA
0x18000bcc6  cmp     eax, 0C000007Ch
0x18000bccb  jnz     loc_18000BA98
0x18000bcd1  mov     [rsp+8F0h+TokenHandle], 0
0x18000bcda  mov     r9d, 8; ThreadInformationLength
0x18000bce0  lea     r8, [r15+50h]; ThreadInformation
0x18000bce4  mov     edx, 5; ThreadInformationClass
0x18000bce9  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000bcf0  call    cs:__imp_NtSetInformationThread
0x18000bcf6  mov     ebx, eax
0x18000bcf8  test    eax, eax
0x18000bcfa  js      short loc_18000BD20
0x18000bcfc  lea     r8, [rsp+8F0h+Size]; nSize
0x18000bd01  mov     dword ptr [rsp+8F0h+Size], 404h
0x18000bd09  lea     rdx, [rbp+7F0h+Src]; lpNameBuffer
0x18000bd0d  mov     ecx, 2; NameFormat
0x18000bd12  call    cs:__imp_GetUserNameExW
0x18000bd18  test    al, al
0x18000bd1a  jz      loc_18000BF58
0x18000bd20  mov     r9d, 8; ThreadInformationLength
0x18000bd26  lea     r8, [rsp+8F0h+TokenHandle]; ThreadInformation
0x18000bd2b  mov     edx, 5; ThreadInformationClass
0x18000bd30  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18000bd37  call    cs:__imp_NtSetInformationThread
0x18000bd3d  mov     rcx, [rsp+8F0h+TokenHandle]; Handle
0x18000bd42  test    rcx, rcx
0x18000bd45  jnz     loc_18000BF9A
0x18000bd4b  test    ebx, ebx
0x18000bd4d  jns     loc_18000BA5E
0x18000bd53  jmp     loc_18000BA98
0x18000bd58  movups  xmm0, xmmword ptr [r15+110h]
0x18000bd60  xor     eax, eax
0x18000bd62  xorps   xmm1, xmm1
0x18000bd65  movups  xmmword ptr [r13+0], xmm0
0x18000bd6a  movups  xmmword ptr [r15+110h], xmm1
0x18000bd72  jmp     loc_18000BAAC
0x18000bd77  mov     [rdi+30h], rdx
0x18000bd7b  jmp     loc_18000BBCA
0x18000bd80  mov     [rdi+28h], rdx
0x18000bd84  jmp     loc_18000BBE1
0x18000bd89  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd90  cmp     rcx, r14
0x18000bd93  jnz     loc_18000BFA5
0x18000bd99  mov     ebx, 0C000009Ah
0x18000bd9e  jmp     loc_18000BA98
0x18000bda3  mov     [rdi+3Ch], rdx
0x18000bda7  mov     ecx, edx
0x18000bda9  jmp     loc_18000BB5F
0x18000bdae  movzx   ecx, word ptr [rdi+58h]
0x18000bdb2  test    cx, cx
0x18000bdb5  jz      loc_18000BA5E
0x18000bdbb  mov     r8d, ecx; Size
0x18000bdbe  add     rcx, 4
0x18000bdc2  add     rcx, rax
0x18000bdc5  cmp     rcx, 808h
0x18000bdcc  ja      loc_18000BE88
0x18000bdd2  mov     rdx, [rdi+60h]; Src
0x18000bdd6  lea     rcx, [rbp+7F0h+Src]; void *
0x18000bdda  call    memcpy_0
0x18000bddf  movzx   ecx, word ptr [rdi+58h]
0x18000bde3  mov     eax, 5Ch ; '\'
0x18000bde8  shr     ecx, 1
0x18000bdea  mov     [rbp+rcx*2+7F0h+Src], ax
0x18000bdef  lea     ebx, [rcx+1]
0x18000bdf2  mov     dword ptr [rsp+8F0h+Size], ebx
0x18000bdf6  lea     rcx, [rbp+7F0h+Src]
0x18000bdfa  movzx   r8d, word ptr [rdi+48h]; Size
0x18000bdff  lea     rcx, [rcx+rbx*2]; void *
0x18000be03  mov     rdx, [rdi+50h]; Src
0x18000be07  call    memcpy_0
0x18000be0c  movzx   eax, word ptr [rdi+48h]
0x18000be10  shr     eax, 1
0x18000be12  add     eax, ebx
0x18000be14  lea     rcx, [rax+rax]
0x18000be18  cmp     rcx, 808h
0x18000be1f  jnb     short loc_18000BE3F
0x18000be21  xor     eax, eax
0x18000be23  mov     [rbp+rcx+7F0h+Src], ax
0x18000be28  jmp     loc_18000BA5E
0x18000be2d  mov     edx, esi; uBytes
0x18000be2f  mov     ecx, 40h ; '@'; uFlags
0x18000be34  call    cs:__imp_LocalAlloc
0x18000be3a  jmp     loc_18000BB03
0x18000be3f  call    __report_rangecheckfailure
0x18000be45  mov     ebx, 0C0000008h
0x18000be4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000be51  lea     r14, WPP_GLOBAL_Control
0x18000be58  cmp     rcx, r14
0x18000be5b  jz      loc_18000BAAA
0x18000be61  test    byte ptr [rcx+1Ch], 1
0x18000be65  jz      loc_18000BAAA
0x18000be6b  mov     rcx, [rcx+10h]
0x18000be6f  lea     r8, WPP_bef59485246b39b2d7f4bbcea231d5a6_Traceguids
0x18000be76  mov     edx, 88h
0x18000be7b  xor     r9d, r9d
0x18000be7e  call    WPP_SF_q
0x18000be83  jmp     loc_18000BAAA
  ... truncated ...
```
