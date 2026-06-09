# PlaiIsAdminUser(ushort const *,ushort const *,int *)

- ea: `0x18010a344`
- end: `0x18010a85b`
- name: `?PlaiIsAdminUser@@YAJPEBG0PEAH@Z`
- size: `1303`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCWSTR lpszPassword, PBOOL IsMember)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800edc58`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x18001153c`
- `0x180012ef0`
- `0x18002b3a0`
- `0x180046c60`
- `0x18010a344`
- `0x18013aee0`

## import_xrefs

- `msvcrt!wcschr` at `0x18010a555`
- `msvcrt!wcschr` at `0x18010a578`
- `msvcrt!wcschr` at `0x18010a555`
- `msvcrt!wcschr` at `0x18010a578`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010a5c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010a602`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010a69b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010a5c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010a602`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010a69b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010a829`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010a829`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18010a72c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18010a72c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18010a68d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18010a68d`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x18010a5b6`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x18010a5f4`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x18010a5b6`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x18010a5f4`

## pseudocode

```c
__int64 __fastcall PlaiIsAdminUser(const unsigned __int16 *a1, LPCWSTR lpszPassword, PBOOL IsMember)
{
  unsigned __int16 *v6; // rax
  const wchar_t *v7; // rsi
  int IsAdminToken; // ebx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rax
  wchar_t *v12; // rax
  const WCHAR *v13; // rbx
  const WCHAR *v14; // rdi
  wchar_t *v15; // rax
  DWORD v16; // eax
  DWORD v17; // eax
  int v18; // eax
  __int64 v19; // rax
  DWORD LastError; // eax
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  int dwLogonProvider; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hToken[2]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v29[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v30[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v31[64]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v32[64]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 v33[64]; // [rsp+290h] [rbp+190h] BYREF

  hToken[0] = 0;
  v6 = (unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, qword_180147320, dwLogonProvider);
  v7 = v6;
  if ( v6 )
  {
    v10 = StringCchCopyW(v6, 0x400u, a1);
    IsAdminToken = v10;
    if ( v10 >= 0 )
    {
      v12 = wcschr(v7, 0x5Cu);
      if ( v12 )
      {
        *v12 = 0;
        v13 = v12 + 1;
        v14 = v7;
      }
      else
      {
        v15 = wcschr(v7, 0x40u);
        v13 = v7;
        if ( v15 )
        {
          *v15 = 0;
          v14 = v15 + 1;
        }
        else
        {
          v14 = 0;
        }
      }
      if ( LogonUserW(v13, v14, lpszPassword, 4u, 0, hToken)
        || (v16 = GetLastError(), (int)PlaiHResultFromWin32(v16) >= 0)
        || LogonUserW(v13, v14, lpszPassword, 2u, 0, hToken)
        || (v17 = GetLastError(), v18 = PlaiHResultFromWin32(v17), IsAdminToken = v18, v18 >= 0) )
      {
        if ( ImpersonateLoggedOnUser(hToken[0])
          || (LastError = GetLastError(), v21 = PlaiHResultFromWin32(LastError), IsAdminToken = v21, v21 >= 0) )
        {
          IsAdminToken = PlaiIsAdminToken(IsMember);
          RevertToSelf();
          if ( IsAdminToken >= 0 )
            goto LABEL_45;
          v27 = 0;
          v26 = IsAdminToken;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_45;
          }
          PlaiWhoAmI(v33, 0x4000000000000800uLL);
          v23 = -1;
          do
            ++v23;
          while ( v33[v23] );
        }
        else
        {
          v27 = 0;
          v26 = v21;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_45;
          }
          PlaiWhoAmI(v32, 0x4000000000000800uLL);
          v22 = -1;
          do
            ++v22;
          while ( v32[v22] );
        }
      }
      else
      {
        v27 = 0;
        v26 = v18;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_45;
        }
        PlaiWhoAmI(v31, 0x4000000000000800uLL);
        v19 = -1;
        do
          ++v19;
        while ( v31[v19] );
      }
    }
    else
    {
      v27 = 0;
      v26 = v10;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_45;
      }
      PlaiWhoAmI(v30, 0x4000000000000800uLL);
      v11 = -1;
      do
        ++v11;
      while ( v30[v11] );
    }
    EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_ERROR, 5, (__int64)&v26);
LABEL_45:
    PlaiFree(v7, 1);
    goto LABEL_46;
  }
  IsAdminToken = -2147024882;
  v27 = -2147024882;
  v26 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v29, 0x4000000000000800uLL);
    v9 = -1;
    do
      ++v9;
    while ( v29[v9] );
    EventingWriteEvent((__int64)&g_Eventing, (__int64)PLA_EVENT_ERROR, 5, (__int64)&v27);
  }
LABEL_46:
  if ( hToken[0] )
    CloseHandle(hToken[0]);
  return (unsigned int)IsAdminToken;
}

```

## disassembly

```asm
0x18010a344  mov     [rsp-8+arg_18], rbx
0x18010a349  push    rbp
0x18010a34a  push    rsi
0x18010a34b  push    rdi
0x18010a34c  push    r12
0x18010a34e  push    r13
0x18010a350  push    r14
0x18010a352  push    r15
0x18010a354  lea     rbp, [rsp-220h]
0x18010a35c  sub     rsp, 320h
0x18010a363  mov     rax, cs:__security_cookie
0x18010a36a  xor     rax, rsp
0x18010a36d  mov     [rbp+250h+var_40], rax
0x18010a374  xor     r13d, r13d
0x18010a377  lea     rdi, qword_180147320
0x18010a37e  mov     r12, r8
0x18010a381  mov     [rbp+250h+hToken], r13
0x18010a385  mov     r15, rdx
0x18010a388  mov     rbx, rcx
0x18010a38b  mov     r9, rdi; char *
0x18010a38e  xor     r8d, r8d; int
0x18010a391  lea     edx, [r13+1]; int
0x18010a395  mov     ecx, 800h; dwBytes
0x18010a39a  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x18010a39f  mov     rsi, rax
0x18010a3a2  test    rax, rax
0x18010a3a5  jnz     loc_18010A482
0x18010a3ab  cmp     dword ptr cs:xmmword_180169738, r13d
0x18010a3b2  mov     ebx, 8007000Eh
0x18010a3b7  mov     [rsp+350h+var_2D8], ebx
0x18010a3bb  mov     [rsp+350h+var_2E0], r13d
0x18010a3c0  jz      loc_18010A820
0x18010a3c6  mov     rdx, 4000000000000800h; unsigned __int64
0x18010a3d0  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010a3d7  jz      loc_18010A820
0x18010a3dd  mov     rax, cs:qword_180169748
0x18010a3e4  and     rax, rdx
0x18010a3e7  cmp     cs:qword_180169748, rax
0x18010a3ee  jnz     loc_18010A820
0x18010a3f4  lea     rcx, [rbp+250h+var_2C0]; unsigned __int16 *
0x18010a3f8  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010a3fd  lea     rcx, [rbp+250h+var_2C0]
0x18010a401  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010a405  inc     rax
0x18010a408  cmp     [rcx+rax*2], r13w
0x18010a40d  jnz     short loc_18010A405
0x18010a40f  lea     ecx, [rax+rax]
0x18010a412  mov     r14d, 4
0x18010a418  add     rcx, 2
0x18010a41c  lea     rax, [rbp+250h+var_2C0]
0x18010a420  mov     [rsp+350h+var_2F0], rcx
0x18010a425  lea     r9, [rsp+350h+var_2D8]
0x18010a42a  mov     [rsp+350h+var_2F8], rax
0x18010a42f  lea     rdx, PLA_EVENT_ERROR
0x18010a436  mov     [rsp+350h+var_300], 10h
0x18010a43f  lea     rax, aPlaiisadminuse; "PlaiIsAdminUser"
0x18010a446  mov     [rsp+350h+var_308], rax
0x18010a44b  lea     r8d, [r14+1]
0x18010a44f  mov     [rsp+350h+var_310], r14
0x18010a454  lea     rax, [rsp+350h+var_2E0]
0x18010a459  mov     [rsp+350h+var_318], rax
0x18010a45e  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18010a465  mov     [rsp+350h+var_320], 1
0x18010a46e  mov     [rsp+350h+phToken], rdi
0x18010a473  mov     qword ptr [rsp+350h+dwLogonProvider], r14
0x18010a478  call    EventingWriteEvent
0x18010a47d  jmp     loc_18010A820
0x18010a482  mov     r8, rbx; unsigned __int16 *
0x18010a485  mov     edx, 400h; unsigned __int64
0x18010a48a  mov     rcx, rsi; unsigned __int16 *
0x18010a48d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18010a492  mov     ebx, eax
0x18010a494  test    eax, eax
0x18010a496  jns     loc_18010A54D
0x18010a49c  cmp     dword ptr cs:xmmword_180169738, r13d
0x18010a4a3  mov     [rsp+350h+var_2D8], r13d
0x18010a4a8  mov     [rsp+350h+var_2E0], eax
0x18010a4ac  jz      loc_18010A813
0x18010a4b2  mov     rdx, 4000000000000800h; unsigned __int64
0x18010a4bc  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010a4c3  jz      loc_18010A813
0x18010a4c9  mov     rax, cs:qword_180169748
0x18010a4d0  and     rax, rdx
0x18010a4d3  cmp     cs:qword_180169748, rax
0x18010a4da  jnz     loc_18010A813
0x18010a4e0  lea     rcx, [rbp+250h+var_240]; unsigned __int16 *
0x18010a4e4  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010a4e9  lea     rcx, [rbp+250h+var_240]
0x18010a4ed  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010a4f1  inc     rax
0x18010a4f4  cmp     [rcx+rax*2], r13w
0x18010a4f9  jnz     short loc_18010A4F1
0x18010a4fb  lea     ecx, [rax+rax]
0x18010a4fe  mov     r14d, 4
0x18010a504  lea     rax, [rbp+250h+var_240]
0x18010a508  add     rcx, 2
0x18010a50c  mov     [rsp+350h+var_2F0], rcx
0x18010a511  mov     [rsp+350h+var_2F8], rax
0x18010a516  lea     rax, aPlaiisadminuse; "PlaiIsAdminUser"
0x18010a51d  mov     [rsp+350h+var_300], 10h
0x18010a526  mov     [rsp+350h+var_308], rax
0x18010a52b  lea     rax, [rsp+350h+var_2D8]
0x18010a530  mov     [rsp+350h+var_310], r14
0x18010a535  mov     [rsp+350h+var_318], rax
0x18010a53a  mov     [rsp+350h+var_320], 1
0x18010a543  mov     [rsp+350h+phToken], rdi
0x18010a548  jmp     loc_18010A7F0
0x18010a54d  mov     edx, 5Ch ; '\'; Ch
0x18010a552  mov     rcx, rsi; Str
0x18010a555  call    cs:__imp_wcschr
0x18010a55b  mov     rbx, rax
0x18010a55e  test    rax, rax
0x18010a561  jz      short loc_18010A570
0x18010a563  mov     [rax], r13w
0x18010a567  add     rbx, 2
0x18010a56b  mov     rdi, rsi
0x18010a56e  jmp     short loc_18010A596
0x18010a570  mov     edx, 40h ; '@'; Ch
0x18010a575  mov     rcx, rsi; Str
0x18010a578  call    cs:__imp_wcschr
0x18010a57e  mov     rdi, rax
0x18010a581  mov     rbx, rsi
0x18010a584  test    rax, rax
0x18010a587  jz      short loc_18010A593
0x18010a589  mov     [rax], r13w
0x18010a58d  add     rdi, 2
0x18010a591  jmp     short loc_18010A596
0x18010a593  mov     rdi, r13
0x18010a596  lea     rax, [rbp+250h+hToken]
0x18010a59a  mov     r14d, 4
0x18010a5a0  mov     [rsp+350h+phToken], rax; phToken
0x18010a5a5  mov     r9d, r14d; dwLogonType
0x18010a5a8  mov     r8, r15; lpszPassword
0x18010a5ab  mov     [rsp+350h+dwLogonProvider], r13d; dwLogonProvider
0x18010a5b0  mov     rdx, rdi; lpszDomain
0x18010a5b3  mov     rcx, rbx; lpszUsername
0x18010a5b6  call    cs:__imp_LogonUserW
0x18010a5bc  test    eax, eax
0x18010a5be  jnz     loc_18010A689
0x18010a5c4  call    cs:__imp_GetLastError
0x18010a5ca  mov     ecx, eax; unsigned int
0x18010a5cc  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18010a5d1  test    eax, eax
0x18010a5d3  jns     loc_18010A689
0x18010a5d9  lea     rax, [rbp+250h+hToken]
0x18010a5dd  mov     r8, r15; lpszPassword
0x18010a5e0  mov     [rsp+350h+phToken], rax; phToken
0x18010a5e5  lea     r9d, [r14-2]; dwLogonType
0x18010a5e9  mov     rdx, rdi; lpszDomain
0x18010a5ec  mov     [rsp+350h+dwLogonProvider], r13d; dwLogonProvider
0x18010a5f1  mov     rcx, rbx; lpszUsername
0x18010a5f4  call    cs:__imp_LogonUserW
0x18010a5fa  test    eax, eax
0x18010a5fc  jnz     loc_18010A689
0x18010a602  call    cs:__imp_GetLastError
0x18010a608  mov     ecx, eax; unsigned int
0x18010a60a  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18010a60f  mov     ebx, eax
0x18010a611  test    eax, eax
0x18010a613  jns     short loc_18010A689
0x18010a615  cmp     dword ptr cs:xmmword_180169738, r13d
0x18010a61c  mov     [rsp+350h+var_2D8], r13d
0x18010a621  mov     [rsp+350h+var_2E0], eax
0x18010a625  jz      loc_18010A813
0x18010a62b  mov     rdx, 4000000000000800h; unsigned __int64
0x18010a635  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010a63c  jz      loc_18010A813
0x18010a642  mov     rax, cs:qword_180169748
0x18010a649  and     rax, rdx
0x18010a64c  cmp     cs:qword_180169748, rax
0x18010a653  jnz     loc_18010A813
0x18010a659  lea     rcx, [rbp+250h+var_1C0]; unsigned __int16 *
0x18010a660  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010a665  lea     rcx, [rbp+250h+var_1C0]
0x18010a66c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010a670  inc     rax
0x18010a673  cmp     [rcx+rax*2], r13w
0x18010a678  jnz     short loc_18010A670
0x18010a67a  lea     ecx, [rax+rax]
0x18010a67d  lea     rax, [rbp+250h+var_1C0]
0x18010a684  jmp     loc_18010A7A9
0x18010a689  mov     rcx, [rbp+250h+hToken]; hToken
0x18010a68d  call    cs:__imp_ImpersonateLoggedOnUser
0x18010a693  test    eax, eax
0x18010a695  jnz     loc_18010A722
0x18010a69b  call    cs:__imp_GetLastError
0x18010a6a1  mov     ecx, eax; unsigned int
0x18010a6a3  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18010a6a8  mov     ebx, eax
0x18010a6aa  test    eax, eax
0x18010a6ac  jns     short loc_18010A722
0x18010a6ae  cmp     dword ptr cs:xmmword_180169738, r13d
0x18010a6b5  mov     [rsp+350h+var_2D8], r13d
0x18010a6ba  mov     [rsp+350h+var_2E0], eax
0x18010a6be  jz      loc_18010A813
0x18010a6c4  mov     rdx, 4000000000000800h; unsigned __int64
0x18010a6ce  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010a6d5  jz      loc_18010A813
0x18010a6db  mov     rax, cs:qword_180169748
0x18010a6e2  and     rax, rdx
0x18010a6e5  cmp     cs:qword_180169748, rax
0x18010a6ec  jnz     loc_18010A813
0x18010a6f2  lea     rcx, [rbp+250h+var_140]; unsigned __int16 *
0x18010a6f9  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010a6fe  lea     rcx, [rbp+250h+var_140]
0x18010a705  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010a709  inc     rax
0x18010a70c  cmp     [rcx+rax*2], r13w
0x18010a711  jnz     short loc_18010A709
0x18010a713  lea     ecx, [rax+rax]
0x18010a716  lea     rax, [rbp+250h+var_140]
0x18010a71d  jmp     loc_18010A7A9
0x18010a722  mov     rcx, r12; IsMember
0x18010a725  call    ?PlaiIsAdminToken@@YAJPEAH@Z; PlaiIsAdminToken(int *)
0x18010a72a  mov     ebx, eax
0x18010a72c  call    cs:__imp_RevertToSelf
0x18010a732  test    ebx, ebx
0x18010a734  jns     loc_18010A813
0x18010a73a  cmp     dword ptr cs:xmmword_180169738, r13d
0x18010a741  mov     [rsp+350h+var_2D8], r13d
0x18010a746  mov     [rsp+350h+var_2E0], ebx
0x18010a74a  jz      loc_18010A813
0x18010a750  mov     rdx, 4000000000000800h; unsigned __int64
0x18010a75a  test    qword ptr cs:xmmword_180169738+8, rdx
0x18010a761  jz      loc_18010A813
0x18010a767  mov     rax, cs:qword_180169748
0x18010a76e  and     rax, rdx
0x18010a771  cmp     cs:qword_180169748, rax
0x18010a778  jnz     loc_18010A813
0x18010a77e  lea     rcx, [rbp+250h+var_C0]; unsigned __int16 *
0x18010a785  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18010a78a  lea     rcx, [rbp+250h+var_C0]
0x18010a791  or      rax, 0FFFFFFFFFFFFFFFFh
0x18010a795  inc     rax
0x18010a798  cmp     [rcx+rax*2], r13w
0x18010a79d  jnz     short loc_18010A795
0x18010a79f  lea     ecx, [rax+rax]
0x18010a7a2  lea     rax, [rbp+250h+var_C0]
0x18010a7a9  add     rcx, 2
0x18010a7ad  mov     [rsp+350h+var_2F0], rcx
0x18010a7b2  mov     [rsp+350h+var_2F8], rax
0x18010a7b7  lea     rax, aPlaiisadminuse; "PlaiIsAdminUser"
0x18010a7be  mov     [rsp+350h+var_300], 10h
0x18010a7c7  mov     [rsp+350h+var_308], rax
0x18010a7cc  lea     rax, [rsp+350h+var_2D8]
0x18010a7d1  mov     [rsp+350h+var_310], r14
0x18010a7d6  mov     [rsp+350h+var_318], rax
0x18010a7db  lea     rax, qword_180147320
0x18010a7e2  mov     [rsp+350h+var_320], 1
0x18010a7eb  mov     [rsp+350h+phToken], rax
0x18010a7f0  lea     r9, [rsp+350h+var_2E0]
0x18010a7f5  mov     qword ptr [rsp+350h+dwLogonProvider], r14
0x18010a7fa  mov     r8d, 5
0x18010a800  lea     rdx, PLA_EVENT_ERROR
0x18010a807  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18010a80e  call    EventingWriteEvent
0x18010a813  mov     edx, 1; int
0x18010a818  mov     rcx, rsi; lpMem
0x18010a81b  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x18010a820  mov     rcx, [rbp+250h+hToken]; hObject
0x18010a824  test    rcx, rcx
0x18010a827  jz      short loc_18010A82F
0x18010a829  call    cs:__imp_CloseHandle
0x18010a82f  mov     eax, ebx
0x18010a831  mov     rcx, [rbp+250h+var_40]
0x18010a838  xor     rcx, rsp; StackCookie
0x18010a83b  call    __security_check_cookie
0x18010a840  mov     rbx, [rsp+350h+arg_18]
0x18010a848  add     rsp, 320h
0x18010a84f  pop     r15
0x18010a851  pop     r14
0x18010a853  pop     r13
0x18010a855  pop     r12
0x18010a857  pop     rdi
0x18010a858  pop     rsi
0x18010a859  pop     rbp
0x18010a85a  retn
```
