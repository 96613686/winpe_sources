# EdpCredSvcQuerySessionUserTokenBySid(ushort const *,void * *)

- ea: `0x1800857a8`
- end: `0x180085b07`
- name: `?EdpCredSvcQuerySessionUserTokenBySid@@YAJPEBGPEAPEAX@Z`
- size: `863`
- prototype: `int(const unsigned __int16 *, void **)`
- caller_count: `8`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180081bf8`
- `0x1800878ac`
- `0x180096cc0`
- `0x1800a5bdc`
- `0x1800ab620`
- `0x1800acc08`
- `0x1800ba574`
- `0x1800baeb0`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x180084a60`
- `0x1800853a4`
- `0x180085614`
- `0x1800857a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180085aa6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180085aa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180085ab4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180085ab4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085998`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180085981`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180085981`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800858f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085a9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800858f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180085a9b`
- `ntdll!RtlIsMultiSessionSku` at `0x180085832`
- `ntdll!RtlIsMultiSessionSku` at `0x180085832`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserTokenFromSid` at `0x180085ad3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserTokenFromSid` at `0x180085ad3`

## pseudocode

```c
__int64 __fastcall EdpCredSvcQuerySessionUserTokenBySid(const unsigned __int16 *a1, void **a2)
{
  WCHAR *v2; // r14
  _DWORD *v3; // r15
  unsigned int UserTokenFromSid; // ebx
  int v7; // r8d
  int v8; // ecx
  int v9; // ecx
  __int64 i; // r12
  int v11; // eax
  int v12; // eax
  signed int LastError; // eax
  int v14; // ecx
  HANDLE ProcessHeap; // rax
  char bIgnoreCase; // [rsp+20h] [rbp-28h]
  unsigned int v19; // [rsp+98h] [rbp+50h] BYREF
  LPCWCH lpString2; // [rsp+A0h] [rbp+58h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp+60h] BYREF

  v2 = 0;
  v3 = 0;
  lpString2 = 0;
  lpMem = 0;
  v19 = 0;
  if ( a2 )
    *a2 = 0;
  if ( !a1 )
  {
    UserTokenFromSid = -2147024809;
    bIgnoreCase = -51;
    v7 = -2147024809;
LABEL_5:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v7, 38, bIgnoreCase);
    return UserTokenFromSid;
  }
  if ( !a2 )
  {
    UserTokenFromSid = -2147467261;
    bIgnoreCase = -50;
    v7 = -2147467261;
    goto LABEL_5;
  }
  if ( !(unsigned __int8)RtlIsMultiSessionSku() )
  {
    UserTokenFromSid = UMgrQueryUserTokenFromSid(a1, a2);
    if ( UserTokenFromSid == -2147023584 )
    {
      UserTokenFromSid = 1;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 1, 38, 35);
      return UserTokenFromSid;
    }
    goto LABEL_30;
  }
  fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 214);
  UserTokenFromSid = EdpCredSvcQueryActiveSessions((unsigned int **)&lpMem, &v19);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              UserTokenFromSid,
              38,
              214) >= 0 )
  {
    if ( !v19 )
    {
      UserTokenFromSid = 1;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 1, 38, 222);
      goto LABEL_13;
    }
    v3 = lpMem;
    for ( i = 0; (unsigned int)i < v19; i = (unsigned int)(i + 1) )
    {
      if ( v2 )
      {
        LocalFree(v2);
        lpString2 = 0;
      }
      fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 235);
      UserTokenFromSid = EdpCredSvcQuerySessionUserSid(v3[i], (unsigned __int16 **)&lpString2);
      v11 = fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              UserTokenFromSid,
              38,
              235);
      v2 = (WCHAR *)lpString2;
      if ( v11 < 0 )
        goto LABEL_31;
      if ( lpString2 )
      {
        v12 = CompareStringOrdinal(a1, -1, lpString2, -1, 1);
        if ( !v12 )
        {
          LastError = GetLastError();
          UserTokenFromSid = LastError;
          if ( LastError > 0 )
            UserTokenFromSid = (unsigned __int16)LastError | 0x80070000;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, UserTokenFromSid, 38, 252);
          goto LABEL_31;
        }
        if ( v12 == 2 )
          break;
      }
    }
    if ( (unsigned int)i >= v19 )
    {
      UserTokenFromSid = 1;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 1, 38, 15);
      goto LABEL_31;
    }
    fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 22);
    UserTokenFromSid = EdpCredSvcQuerySessionUserToken(v3[(unsigned int)i], a2);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                UserTokenFromSid,
                38,
                22) < 0 )
    {
LABEL_31:
      if ( v2 )
        LocalFree(v2);
      goto LABEL_33;
    }
LABEL_30:
    fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 38, 41);
    fnEfsLogTrace1String1Dword(
      g_hPublisher,
      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
      (unsigned int)&sourceString,
      UserTokenFromSid,
      38,
      41);
    goto LABEL_31;
  }
LABEL_13:
  v3 = lpMem;
LABEL_33:
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
  }
  return UserTokenFromSid;
}

```

## disassembly

```asm
0x1800857a8  mov     [rsp-40h+lpString1], rcx
0x1800857ad  push    rbp
0x1800857ae  push    rbx
0x1800857af  push    rsi
0x1800857b0  push    rdi
0x1800857b1  push    r12
0x1800857b3  push    r13
0x1800857b5  push    r14
0x1800857b7  push    r15
0x1800857b9  mov     rbp, rsp
0x1800857bc  sub     rsp, 48h
0x1800857c0  xor     r14d, r14d
0x1800857c3  xor     r15d, r15d
0x1800857c6  mov     [rbp+lpString2], r14
0x1800857ca  mov     r13, rdx
0x1800857cd  mov     [rbp+lpMem], r15
0x1800857d1  mov     rbx, rcx
0x1800857d4  mov     [rbp+arg_8], r14d
0x1800857d8  test    rdx, rdx
0x1800857db  jz      short loc_1800857E2
0x1800857dd  xor     eax, eax
0x1800857df  mov     [rdx], rax
0x1800857e2  test    rbx, rbx
0x1800857e5  jnz     short loc_180085818
0x1800857e7  mov     ebx, 80070057h
0x1800857ec  mov     dword ptr [rsp+48h+bIgnoreCase], 0ACDh
0x1800857f4  mov     r8d, 80070057h
0x1800857fa  mov     r9d, 26h ; '&'
0x180085800  lea     rdx, EFS_TRACE_ERROR
0x180085807  mov     rcx, cs:g_hPublisher
0x18008580e  call    fnEfsLogTrace1
0x180085813  jmp     loc_180085ABA
0x180085818  test    r13, r13
0x18008581b  jnz     short loc_180085832
0x18008581d  mov     ebx, 80004003h
0x180085822  mov     dword ptr [rsp+48h+bIgnoreCase], 0ACEh
0x18008582a  mov     r8d, 80004003h
0x180085830  jmp     short loc_1800857FA
0x180085832  call    cs:__imp_RtlIsMultiSessionSku
0x180085838  mov     edi, 26h ; '&'
0x18008583d  lea     r12, sourceString
0x180085844  test    al, al
0x180085846  jz      loc_180085ACD
0x18008584c  mov     esi, 0AD6h
0x180085851  lea     rdx, EFS_TRACE_START_EVENT
0x180085858  mov     r9d, edi
0x18008585b  mov     dword ptr [rsp+48h+bIgnoreCase], esi
0x18008585f  mov     r8, r12
0x180085862  call    fnEfsLogTrace1Strings
0x180085867  lea     rdx, [rbp+arg_8]; unsigned int *
0x18008586b  lea     rcx, [rbp+lpMem]; unsigned int **
0x18008586f  call    ?EdpCredSvcQueryActiveSessions@@YAJPEAPEAKPEAK@Z; EdpCredSvcQueryActiveSessions(ulong * *,ulong *)
0x180085874  mov     rcx, cs:g_hPublisher
0x18008587b  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180085882  mov     [rsp+48h+var_18], esi
0x180085886  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18008588d  mov     [rsp+48h+var_20], edi
0x180085891  mov     r9, r12
0x180085894  mov     dword ptr [rsp+48h+bIgnoreCase], eax
0x180085898  mov     ebx, eax
0x18008589a  call    fnEfsLogTrace1String1Dword
0x18008589f  test    eax, eax
0x1800858a1  js      short loc_1800858CF
0x1800858a3  lea     esi, [rdi-25h]
0x1800858a6  cmp     [rbp+arg_8], r14d
0x1800858aa  jnz     short loc_1800858D8
0x1800858ac  mov     rcx, cs:g_hPublisher
0x1800858b3  lea     rdx, EFS_TRACE_STATUS
0x1800858ba  mov     r9d, edi
0x1800858bd  mov     dword ptr [rsp+48h+bIgnoreCase], 0ADEh
0x1800858c5  mov     r8d, esi
0x1800858c8  mov     ebx, esi
0x1800858ca  call    fnEfsLogTrace1
0x1800858cf  mov     r15, [rbp+lpMem]
0x1800858d3  jmp     loc_180085AA1
0x1800858d8  mov     r15, [rbp+lpMem]
0x1800858dc  xor     r12d, r12d
0x1800858df  cmp     r12d, [rbp+arg_8]
0x1800858e3  jnb     loc_1800859D3
0x1800858e9  test    r14, r14
0x1800858ec  jz      short loc_1800858FF
0x1800858ee  mov     rcx, r14; hMem
0x1800858f1  call    cs:__imp_LocalFree
0x1800858f7  mov     [rbp+lpString2], 0
0x1800858ff  mov     r9d, edi
0x180085902  mov     dword ptr [rsp+48h+bIgnoreCase], 0AEBh
0x18008590a  lea     r8, sourceString
0x180085911  lea     rdx, EFS_TRACE_START_EVENT
0x180085918  call    fnEfsLogTrace1Strings
0x18008591d  mov     ecx, [r15+r12*4]; SessionId
0x180085921  lea     rdx, [rbp+lpString2]; unsigned __int16 **
0x180085925  call    ?EdpCredSvcQuerySessionUserSid@@YAJKPEAPEAG@Z; EdpCredSvcQuerySessionUserSid(ulong,ushort * *)
0x18008592a  mov     rcx, cs:g_hPublisher
0x180085931  lea     r9, sourceString
0x180085938  mov     [rsp+48h+var_18], 0AEBh
0x180085940  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180085947  mov     [rsp+48h+var_20], edi
0x18008594b  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180085952  mov     dword ptr [rsp+48h+bIgnoreCase], eax
0x180085956  mov     ebx, eax
0x180085958  call    fnEfsLogTrace1String1Dword
0x18008595d  mov     r14, [rbp+lpString2]
0x180085961  test    eax, eax
0x180085963  js      loc_180085A93
0x180085969  test    r14, r14
0x18008596c  jz      short loc_180085990
0x18008596e  mov     rcx, [rbp+lpString1]; lpString1
0x180085972  or      ebx, 0FFFFFFFFh
0x180085975  mov     r9d, ebx; cchCount2
0x180085978  mov     dword ptr [rsp+48h+bIgnoreCase], esi; bIgnoreCase
0x18008597c  mov     edx, ebx; cchCount1
0x18008597e  mov     r8, r14; lpString2
0x180085981  call    cs:__imp_CompareStringOrdinal
0x180085987  test    eax, eax
0x180085989  jz      short loc_180085998
0x18008598b  cmp     eax, 2
0x18008598e  jz      short loc_1800859D3
0x180085990  add     r12d, esi
0x180085993  jmp     loc_1800858DF
0x180085998  call    cs:__imp_GetLastError
0x18008599e  mov     ebx, eax
0x1800859a0  test    eax, eax
0x1800859a2  jle     short loc_1800859AD
0x1800859a4  movzx   ebx, ax
0x1800859a7  or      ebx, 80070000h
0x1800859ad  mov     dword ptr [rsp+48h+bIgnoreCase], 0AFCh
0x1800859b5  lea     rdx, EFS_TRACE_ERROR
0x1800859bc  mov     r9d, edi
0x1800859bf  mov     r8d, ebx
0x1800859c2  mov     rcx, cs:g_hPublisher
0x1800859c9  call    fnEfsLogTrace1
0x1800859ce  jmp     loc_180085A93
0x1800859d3  mov     r9d, edi
0x1800859d6  mov     ebx, r12d
0x1800859d9  cmp     r12d, [rbp+arg_8]
0x1800859dd  jb      short loc_1800859F5
0x1800859df  mov     ebx, esi
0x1800859e1  mov     dword ptr [rsp+48h+bIgnoreCase], 0B0Fh
0x1800859e9  mov     r8d, esi
0x1800859ec  lea     rdx, EFS_TRACE_STATUS
0x1800859f3  jmp     short loc_1800859C2
0x1800859f5  lea     r12, sourceString
0x1800859fc  mov     esi, 0B16h
0x180085a01  mov     r8, r12
0x180085a04  mov     dword ptr [rsp+48h+bIgnoreCase], esi
0x180085a08  lea     rdx, EFS_TRACE_START_EVENT
0x180085a0f  call    fnEfsLogTrace1Strings
0x180085a14  mov     ecx, [r15+rbx*4]; SessionId
0x180085a18  mov     rdx, r13; void **
0x180085a1b  call    ?EdpCredSvcQuerySessionUserToken@@YAJKPEAPEAX@Z; EdpCredSvcQuerySessionUserToken(ulong,void * *)
0x180085a20  mov     rcx, cs:g_hPublisher
0x180085a27  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180085a2e  mov     [rsp+48h+var_18], esi
0x180085a32  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180085a39  mov     [rsp+48h+var_20], edi
0x180085a3d  mov     r9, r12
0x180085a40  mov     dword ptr [rsp+48h+bIgnoreCase], eax
0x180085a44  mov     ebx, eax
0x180085a46  call    fnEfsLogTrace1String1Dword
0x180085a4b  test    eax, eax
0x180085a4d  js      short loc_180085A93
0x180085a4f  mov     esi, 0B29h
0x180085a54  lea     rdx, EFS_TRACE_START_EVENT
0x180085a5b  mov     r9d, edi
0x180085a5e  mov     dword ptr [rsp+48h+bIgnoreCase], esi
0x180085a62  mov     r8, r12
0x180085a65  call    fnEfsLogTrace1Strings
0x180085a6a  mov     rcx, cs:g_hPublisher
0x180085a71  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180085a78  mov     [rsp+48h+var_18], esi
0x180085a7c  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180085a83  mov     [rsp+48h+var_20], edi
0x180085a87  mov     r9, r12
0x180085a8a  mov     dword ptr [rsp+48h+bIgnoreCase], ebx
0x180085a8e  call    fnEfsLogTrace1String1Dword
0x180085a93  test    r14, r14
0x180085a96  jz      short loc_180085AA1
0x180085a98  mov     rcx, r14; hMem
0x180085a9b  call    cs:__imp_LocalFree
0x180085aa1  test    r15, r15
0x180085aa4  jz      short loc_180085ABA
0x180085aa6  call    cs:__imp_GetProcessHeap
0x180085aac  mov     r8, r15; lpMem
0x180085aaf  xor     edx, edx; dwFlags
0x180085ab1  mov     rcx, rax; hHeap
0x180085ab4  call    cs:__imp_HeapFree
0x180085aba  mov     eax, ebx
0x180085abc  add     rsp, 48h
0x180085ac0  pop     r15
0x180085ac2  pop     r14
0x180085ac4  pop     r13
0x180085ac6  pop     r12
0x180085ac8  pop     rdi
0x180085ac9  pop     rsi
0x180085aca  pop     rbx
0x180085acb  pop     rbp
0x180085acc  retn
0x180085acd  mov     rdx, r13
0x180085ad0  mov     rcx, rbx
0x180085ad3  call    cs:__imp_UMgrQueryUserTokenFromSid
0x180085ad9  mov     ebx, eax
0x180085adb  cmp     eax, 80070520h
0x180085ae0  jnz     loc_180085A4F
0x180085ae6  mov     esi, 1
0x180085aeb  mov     dword ptr [rsp+48h+bIgnoreCase], 0B23h
0x180085af3  mov     ebx, esi
0x180085af5  lea     rdx, EFS_TRACE_STATUS
0x180085afc  mov     r8d, esi
0x180085aff  mov     r9d, edi
0x180085b02  jmp     loc_180085807
```
