# PlaiGetCurrentUserSid(ushort * *)

- ea: `0x18004c3c8`
- end: `0x18004c894`
- name: `?PlaiGetCurrentUserSid@@YAJPEAPEAG@Z`
- size: `1228`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800fbc48`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x18002b3a0`
- `0x18004c3c8`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c42d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c4f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c5e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c68b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c42d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c4f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c5e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c68b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c861`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004c861`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004c4e8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004c4e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004c4d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004c4d9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004c41f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004c41f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004c408`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004c408`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004c5d7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004c5d7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004c679`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004c679`

## string_xrefs

- `0x18004c739`: `PlaiGetCurrentUserSid`
- `0x18004c81e`: `PlaiGetCurrentUserSid`

## pseudocode

```c
__int64 __fastcall PlaiGetCurrentUserSid(LPWSTR *StringSid)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rax
  int *v7; // rcx
  int *v8; // r9
  HANDLE CurrentProcess; // rax
  DWORD v10; // eax
  int v11; // eax
  __int64 v12; // rax
  PSID *v13; // rdi
  DWORD v14; // eax
  int v15; // eax
  __int64 v16; // rax
  DWORD v17; // eax
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  int ReturnLength; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+78h] [rbp-88h] BYREF
  DWORD TokenInformationLength; // [rsp+80h] [rbp-80h] BYREF
  void *TokenHandle; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v27[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v28[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v29[64]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v30[64]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 v31[64]; // [rsp+290h] [rbp+190h] BYREF

  TokenInformationLength = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    goto LABEL_18;
  LastError = GetLastError();
  v4 = PlaiHResultFromWin32(LastError);
  v5 = v4;
  if ( v4 >= 0 )
    goto LABEL_18;
  if ( v4 == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      v10 = GetLastError();
      v11 = PlaiHResultFromWin32(v10);
      v5 = v11;
      if ( v11 < 0 )
      {
        v24 = 0;
        v23 = v11;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_48;
        }
        PlaiWhoAmI(v28, 0x4000000000000800uLL);
        v12 = -1;
        do
          ++v12;
        while ( v28[v12] );
        goto LABEL_46;
      }
    }
LABEL_18:
    v13 = 0;
    TokenInformationLength = 84;
    while ( 1 )
    {
      if ( v13 )
        PlaiFree(v13, 1);
      v13 = (PSID *)PlaiAlloc(TokenInformationLength, 1, 0, qword_180147320, ReturnLength);
      if ( !v13 )
        break;
      if ( GetTokenInformation(TokenHandle, TokenUser, v13, TokenInformationLength, &TokenInformationLength) )
        goto LABEL_31;
      v14 = GetLastError();
      v15 = PlaiHResultFromWin32(v14);
      v5 = v15;
      if ( v15 != -2147024774 )
      {
        if ( v15 >= 0 )
        {
LABEL_31:
          if ( ConvertSidToStringSidW(*v13, StringSid) )
          {
            v5 = 0;
          }
          else
          {
            v17 = GetLastError();
            v18 = PlaiHResultFromWin32(v17);
            v5 = v18;
            if ( v18 < 0 )
            {
              v24 = 0;
              v23 = v18;
              if ( (_DWORD)xmmword_180169738 )
              {
                if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                {
                  PlaiWhoAmI(v30, 0x4000000000000800uLL);
                  v19 = -1;
                  do
                    ++v19;
                  while ( v30[v19] );
LABEL_39:
                  EventingWriteEvent(
                    &g_Eventing,
                    PLA_EVENT_ERROR,
                    5,
                    &v23,
                    4,
                    qword_180147320,
                    1,
                    &v24,
                    4,
                    "PlaiGetCurrentUserSid",
                    22);
                }
              }
            }
          }
        }
        else
        {
          v24 = 0;
          v23 = v15;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v29, 0x4000000000000800uLL);
            v16 = -1;
            do
              ++v16;
            while ( v29[v16] );
            goto LABEL_39;
          }
        }
        PlaiFree(v13, 1);
        goto LABEL_48;
      }
    }
    v5 = -2147024882;
    v23 = -2147024882;
    v24 = 0;
    if ( !(_DWORD)xmmword_180169738
      || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
      || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
    {
      goto LABEL_48;
    }
    PlaiWhoAmI(v31, 0x4000000000000800uLL);
    v20 = -1;
    do
      ++v20;
    while ( v31[v20] );
LABEL_46:
    v8 = &v23;
    v7 = &v24;
LABEL_47:
    EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, v8, 4, qword_180147320, 1, v7, 4, "PlaiGetCurrentUserSid", 22);
    goto LABEL_48;
  }
  v23 = 0;
  v24 = v4;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v27, 0x4000000000000800uLL);
    v6 = -1;
    do
      ++v6;
    while ( v27[v6] );
    v7 = &v23;
    v8 = &v24;
    goto LABEL_47;
  }
LABEL_48:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x18004c3c8  mov     [rsp-8+arg_8], rbx
0x18004c3cd  mov     [rsp-8+arg_10], rsi
0x18004c3d2  push    rbp
0x18004c3d3  push    rdi
0x18004c3d4  push    r12
0x18004c3d6  push    r14
0x18004c3d8  push    r15
0x18004c3da  lea     rbp, [rsp-220h]
0x18004c3e2  sub     rsp, 320h
0x18004c3e9  mov     rax, cs:__security_cookie
0x18004c3f0  xor     rax, rsp
0x18004c3f3  mov     [rbp+240h+var_30], rax
0x18004c3fa  xor     r12d, r12d
0x18004c3fd  mov     r15, rcx
0x18004c400  mov     [rbp+240h+TokenInformationLength], r12d
0x18004c404  mov     [rbp+240h+TokenHandle], r12
0x18004c408  call    cs:__imp_GetCurrentThread
0x18004c40e  lea     edi, [r12+8]
0x18004c413  xor     r8d, r8d; OpenAsSelf
0x18004c416  mov     rcx, rax; ThreadHandle
0x18004c419  lea     r9, [rbp+240h+TokenHandle]; TokenHandle
0x18004c41d  mov     edx, edi; DesiredAccess
0x18004c41f  call    cs:__imp_OpenThreadToken
0x18004c425  test    eax, eax
0x18004c427  jnz     loc_18004C580
0x18004c42d  call    cs:__imp_GetLastError
0x18004c433  mov     ecx, eax; unsigned int
0x18004c435  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18004c43a  mov     ebx, eax
0x18004c43c  test    eax, eax
0x18004c43e  jns     loc_18004C580
0x18004c444  cmp     eax, 800703F0h
0x18004c449  jz      loc_18004C4D9
0x18004c44f  cmp     dword ptr cs:xmmword_180169738, r12d
0x18004c456  mov     [rsp+340h+var_2D0], r12d
0x18004c45b  mov     [rsp+340h+var_2C8], eax
0x18004c45f  jz      loc_18004C858
0x18004c465  mov     rdx, 4000000000000800h; unsigned __int64
0x18004c46f  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004c476  jz      loc_18004C858
0x18004c47c  mov     rax, cs:qword_180169748
0x18004c483  and     rax, rdx
0x18004c486  cmp     cs:qword_180169748, rax
0x18004c48d  jnz     loc_18004C858
0x18004c493  lea     rcx, [rbp+240h+var_2B0]; unsigned __int16 *
0x18004c497  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004c49c  lea     rcx, [rbp+240h+var_2B0]
0x18004c4a0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004c4a4  inc     rax
0x18004c4a7  cmp     [rcx+rax*2], r12w
0x18004c4ac  jnz     short loc_18004C4A4
0x18004c4ae  lea     ecx, [rax+rax]
0x18004c4b1  mov     esi, 1
0x18004c4b6  add     rcx, 2
0x18004c4ba  lea     rax, [rbp+240h+var_2B0]
0x18004c4be  mov     [rsp+340h+var_2E0], rcx
0x18004c4c3  lea     r14, qword_180147320
0x18004c4ca  lea     rcx, [rsp+340h+var_2D0]
0x18004c4cf  lea     r9, [rsp+340h+var_2C8]
0x18004c4d4  jmp     loc_18004C809
0x18004c4d9  call    cs:__imp_GetCurrentProcess
0x18004c4df  lea     r8, [rbp+240h+TokenHandle]; TokenHandle
0x18004c4e3  mov     edx, edi; DesiredAccess
0x18004c4e5  mov     rcx, rax; ProcessHandle
0x18004c4e8  call    cs:__imp_OpenProcessToken
0x18004c4ee  test    eax, eax
0x18004c4f0  jnz     loc_18004C580
0x18004c4f6  call    cs:__imp_GetLastError
0x18004c4fc  mov     ecx, eax; unsigned int
0x18004c4fe  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18004c503  mov     ebx, eax
0x18004c505  test    eax, eax
0x18004c507  jns     short loc_18004C580
0x18004c509  cmp     dword ptr cs:xmmword_180169738, r12d
0x18004c510  mov     [rsp+340h+var_2C8], r12d
0x18004c515  mov     [rsp+340h+var_2D0], eax
0x18004c519  jz      loc_18004C858
0x18004c51f  mov     rdx, 4000000000000800h; unsigned __int64
0x18004c529  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004c530  jz      loc_18004C858
0x18004c536  mov     rax, cs:qword_180169748
0x18004c53d  and     rax, rdx
0x18004c540  cmp     cs:qword_180169748, rax
0x18004c547  jnz     loc_18004C858
0x18004c54d  lea     rcx, [rbp+240h+var_230]; unsigned __int16 *
0x18004c551  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004c556  lea     rcx, [rbp+240h+var_230]
0x18004c55a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004c55e  inc     rax
0x18004c561  cmp     [rcx+rax*2], r12w
0x18004c566  jnz     short loc_18004C55E
0x18004c568  lea     ecx, [rax+rax]
0x18004c56b  mov     esi, 1
0x18004c570  lea     rax, [rbp+240h+var_230]
0x18004c574  lea     r14, qword_180147320
0x18004c57b  jmp     loc_18004C7F6
0x18004c580  mov     rdi, r12
0x18004c583  mov     [rbp+240h+TokenInformationLength], 54h ; 'T'
0x18004c58a  mov     esi, 1
0x18004c58f  lea     r14, qword_180147320
0x18004c596  test    rdi, rdi
0x18004c599  jz      short loc_18004C5A5
0x18004c59b  mov     edx, esi; int
0x18004c59d  mov     rcx, rdi; lpMem
0x18004c5a0  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x18004c5a5  mov     ecx, [rbp+240h+TokenInformationLength]; dwBytes
0x18004c5a8  mov     r9, r14; char *
0x18004c5ab  xor     r8d, r8d; int
0x18004c5ae  mov     edx, esi; int
0x18004c5b0  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x18004c5b5  mov     rdi, rax
0x18004c5b8  test    rax, rax
0x18004c5bb  jz      loc_18004C782
0x18004c5c1  mov     r9d, [rbp+240h+TokenInformationLength]; TokenInformationLength
0x18004c5c5  lea     rax, [rbp+240h+TokenInformationLength]
0x18004c5c9  mov     rcx, [rbp+240h+TokenHandle]; TokenHandle
0x18004c5cd  mov     r8, rdi; TokenInformation
0x18004c5d0  mov     edx, esi; TokenInformationClass
0x18004c5d2  mov     [rsp+340h+ReturnLength], rax; ReturnLength
0x18004c5d7  call    cs:__imp_GetTokenInformation
0x18004c5dd  test    eax, eax
0x18004c5df  jnz     loc_18004C673
0x18004c5e5  call    cs:__imp_GetLastError
0x18004c5eb  mov     ecx, eax; unsigned int
0x18004c5ed  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18004c5f2  mov     ebx, eax
0x18004c5f4  cmp     eax, 8007007Ah
0x18004c5f9  jz      short loc_18004C596
0x18004c5fb  test    eax, eax
0x18004c5fd  jns     short loc_18004C673
0x18004c5ff  cmp     dword ptr cs:xmmword_180169738, r12d
0x18004c606  mov     [rsp+340h+var_2C8], r12d
0x18004c60b  mov     [rsp+340h+var_2D0], eax
0x18004c60f  jz      loc_18004C773
0x18004c615  mov     rdx, 4000000000000800h; unsigned __int64
0x18004c61f  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004c626  jz      loc_18004C773
0x18004c62c  mov     rax, cs:qword_180169748
0x18004c633  and     rax, rdx
0x18004c636  cmp     cs:qword_180169748, rax
0x18004c63d  jnz     loc_18004C773
0x18004c643  lea     rcx, [rbp+240h+var_1B0]; unsigned __int16 *
0x18004c64a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004c64f  lea     rcx, [rbp+240h+var_1B0]
0x18004c656  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004c65a  inc     rax
0x18004c65d  cmp     [rcx+rax*2], r12w
0x18004c662  jnz     short loc_18004C65A
0x18004c664  lea     ecx, [rax+rax]
0x18004c667  lea     rax, [rbp+240h+var_1B0]
0x18004c66e  jmp     loc_18004C711
0x18004c673  mov     rcx, [rdi]; Sid
0x18004c676  mov     rdx, r15; StringSid
0x18004c679  call    cs:__imp_ConvertSidToStringSidW
0x18004c67f  test    eax, eax
0x18004c681  jz      short loc_18004C68B
0x18004c683  mov     ebx, r12d
0x18004c686  jmp     loc_18004C773
0x18004c68b  call    cs:__imp_GetLastError
0x18004c691  mov     ecx, eax; unsigned int
0x18004c693  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18004c698  mov     ebx, eax
0x18004c69a  test    eax, eax
0x18004c69c  jns     loc_18004C773
0x18004c6a2  cmp     dword ptr cs:xmmword_180169738, r12d
0x18004c6a9  mov     [rsp+340h+var_2C8], r12d
0x18004c6ae  mov     [rsp+340h+var_2D0], eax
0x18004c6b2  jz      loc_18004C773
0x18004c6b8  mov     rdx, 4000000000000800h; unsigned __int64
0x18004c6c2  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004c6c9  jz      loc_18004C773
0x18004c6cf  mov     rax, cs:qword_180169748
0x18004c6d6  and     rax, rdx
0x18004c6d9  cmp     cs:qword_180169748, rax
0x18004c6e0  jnz     loc_18004C773
0x18004c6e6  lea     rcx, [rbp+240h+var_130]; unsigned __int16 *
0x18004c6ed  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004c6f2  lea     rcx, [rbp+240h+var_130]
0x18004c6f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004c6fd  inc     rax
0x18004c700  cmp     [rcx+rax*2], r12w
0x18004c705  jnz     short loc_18004C6FD
0x18004c707  lea     ecx, [rax+rax]
0x18004c70a  lea     rax, [rbp+240h+var_130]
0x18004c711  add     rcx, 2
0x18004c715  lea     r9, [rsp+340h+var_2D0]
0x18004c71a  mov     [rsp+340h+var_2E0], rcx
0x18004c71f  lea     rdx, PLA_EVENT_ERROR
0x18004c726  mov     [rsp+340h+var_2E8], rax
0x18004c72b  lea     rcx, [rsp+340h+var_2C8]
0x18004c730  mov     [rsp+340h+var_2F0], 16h
0x18004c739  lea     rax, aPlaigetcurrent; "PlaiGetCurrentUserSid"
0x18004c740  mov     [rsp+340h+var_2F8], rax
0x18004c745  mov     eax, 4
0x18004c74a  mov     [rsp+340h+var_300], rax
0x18004c74f  mov     [rsp+340h+var_308], rcx
0x18004c754  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004c75b  mov     [rsp+340h+var_310], rsi
0x18004c760  mov     [rsp+340h+var_318], r14
0x18004c765  lea     r8d, [rax+1]
0x18004c769  mov     [rsp+340h+ReturnLength], rax
0x18004c76e  call    EventingWriteEvent
0x18004c773  mov     edx, esi; int
0x18004c775  mov     rcx, rdi; lpMem
0x18004c778  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x18004c77d  jmp     loc_18004C858
0x18004c782  cmp     dword ptr cs:xmmword_180169738, r12d
0x18004c789  mov     ebx, 8007000Eh
0x18004c78e  mov     [rsp+340h+var_2D0], ebx
0x18004c792  mov     [rsp+340h+var_2C8], r12d
0x18004c797  jz      loc_18004C858
0x18004c79d  mov     rdx, 4000000000000800h; unsigned __int64
0x18004c7a7  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004c7ae  jz      loc_18004C858
0x18004c7b4  mov     rax, cs:qword_180169748
0x18004c7bb  and     rax, rdx
0x18004c7be  cmp     cs:qword_180169748, rax
0x18004c7c5  jnz     loc_18004C858
0x18004c7cb  lea     rcx, [rbp+240h+var_B0]; unsigned __int16 *
0x18004c7d2  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004c7d7  lea     rcx, [rbp+240h+var_B0]
0x18004c7de  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004c7e2  inc     rax
0x18004c7e5  cmp     [rcx+rax*2], r12w
0x18004c7ea  jnz     short loc_18004C7E2
0x18004c7ec  lea     ecx, [rax+rax]
0x18004c7ef  lea     rax, [rbp+240h+var_B0]
0x18004c7f6  add     rcx, 2
0x18004c7fa  lea     r9, [rsp+340h+var_2D0]
0x18004c7ff  mov     [rsp+340h+var_2E0], rcx
0x18004c804  lea     rcx, [rsp+340h+var_2C8]
0x18004c809  mov     [rsp+340h+var_2E8], rax
0x18004c80e  lea     rdx, PLA_EVENT_ERROR
0x18004c815  mov     [rsp+340h+var_2F0], 16h
0x18004c81e  lea     rax, aPlaigetcurrent; "PlaiGetCurrentUserSid"
0x18004c825  mov     [rsp+340h+var_2F8], rax
0x18004c82a  mov     eax, 4
0x18004c82f  mov     [rsp+340h+var_300], rax
0x18004c834  mov     [rsp+340h+var_308], rcx
0x18004c839  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18004c840  mov     [rsp+340h+var_310], rsi
0x18004c845  mov     [rsp+340h+var_318], r14
0x18004c84a  lea     r8d, [rax+1]
0x18004c84e  mov     [rsp+340h+ReturnLength], rax
0x18004c853  call    EventingWriteEvent
0x18004c858  mov     rcx, [rbp+240h+TokenHandle]; hObject
0x18004c85c  test    rcx, rcx
0x18004c85f  jz      short loc_18004C867
0x18004c861  call    cs:__imp_CloseHandle
0x18004c867  mov     eax, ebx
0x18004c869  mov     rcx, [rbp+240h+var_30]
0x18004c870  xor     rcx, rsp; StackCookie
0x18004c873  call    __security_check_cookie
0x18004c878  lea     r11, [rsp+340h+var_20]
0x18004c880  mov     rbx, [r11+38h]
0x18004c884  mov     rsi, [r11+40h]
0x18004c888  mov     rsp, r11
0x18004c88b  pop     r15
0x18004c88d  pop     r14
0x18004c88f  pop     r12
0x18004c891  pop     rdi
0x18004c892  pop     rbp
0x18004c893  retn
```
