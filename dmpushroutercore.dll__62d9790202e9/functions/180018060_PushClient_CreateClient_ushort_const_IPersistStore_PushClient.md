# PushClient::CreateClient(ushort const *,IPersistStore *,PushClient * *)

- ea: `0x180018060`
- end: `0x1800184d6`
- name: `?CreateClient@PushClient@@SAJPEBGPEAVIPersistStore@@PEAPEAV1@@Z`
- size: `1142`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IPersistStore *, struct PushClient **)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001478c`
- `0x180015500`
- `0x180016110`

## callees

- `0x1800039f0`
- `0x1800043a8`
- `0x180006090`
- `0x180013224`
- `0x1800132fc`
- `0x18001517c`
- `0x180017aa8`
- `0x180018060`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800181a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001842c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800181a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001842c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800180cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800183ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800180cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800183ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001816b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001817b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001818b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001819b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001816b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001817b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001818b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001819b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018133`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800181f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018220`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001845e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018133`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800181f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018220`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001845e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800182f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800182f1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180018298`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180018298`
- `DMCmnUtils!CopyString` at `0x18001830a`
- `DMCmnUtils!CopyString` at `0x18001830a`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18001847d`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18001847d`

## pseudocode

```c
__int64 __fastcall PushClient::CreateClient(
        const unsigned __int16 *a1,
        struct IPersistStore *a2,
        struct PushClient **a3)
{
  PushClient *v6; // rax
  PushClient *v7; // rdi
  signed int StringValue; // ebx
  LSTATUS v9; // eax
  bool v10; // cc
  LPCWSTR *v12; // rsi
  __int64 v13; // rcx
  WCHAR *p_Dst; // rax
  __int64 v15; // r14
  _DWORD *v16; // rsi
  signed int DWORD; // eax
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY v20; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v21; // [rsp+48h] [rbp-B8h] BYREF
  PushClient *v22; // [rsp+50h] [rbp-B0h]
  char v23; // [rsp+58h] [rbp-A8h]
  WCHAR Dst; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v25[516]; // [rsp+62h] [rbp-9Eh] BYREF
  __int16 v26; // [rsp+266h] [rbp+166h]

  hKey = 0;
  phkResult = 0;
  v21 = 0;
  v20 = 0;
  Dst = 0;
  memset_0(v25, 0, 0x206u);
  EnterCriticalSection(&g_csPushRouter);
  *a3 = 0;
  v6 = (PushClient *)operator new(0xF8u, (const struct std::nothrow_t *)&std::nothrow);
  v22 = v6;
  if ( v6 )
    v7 = PushClient::PushClient(v6);
  else
    v7 = 0;
  if ( !v7 )
  {
    StringValue = -2147024882;
    goto LABEL_10;
  }
  v9 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\PushRouter\\Registrations\\ByGenericId",
         0,
         0x20019u,
         &hKey);
  StringValue = v9;
  v10 = v9 <= 0;
  if ( v9
    || (v9 = RegOpenKeyExW(hKey, a1, 0, 0x20019u, &phkResult), StringValue = v9, v10 = v9 <= 0, v9)
    || (v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, c_szAppRegistrationByGenIdStateSep, 0, 0x20019u, &v21),
        StringValue = v9,
        v10 = v9 <= 0,
        v9) )
  {
    if ( !v10 )
      StringValue = (unsigned __int16)v9 | 0x80070000;
    goto LABEL_9;
  }
  StringValue = QueryStringValue(phkResult, 0, L"GenId", (unsigned __int16 **)v7 + 6);
  if ( StringValue < 0 )
  {
LABEL_9:
    (**(void (__fastcall ***)(PushClient *, __int64))v7)(v7, 1);
    goto LABEL_10;
  }
  if ( !*((_QWORD *)v7 + 6) )
    goto LABEL_23;
  v12 = (LPCWSTR *)((char *)v7 + 56);
  StringValue = QueryStringValue(phkResult, 0, L"Path", (unsigned __int16 **)v7 + 7);
  if ( StringValue < 0 )
    goto LABEL_9;
  if ( !*v12 || !ExpandEnvironmentStringsW(*v12, &Dst, 0x104u) )
    goto LABEL_23;
  v26 = 0;
  v13 = 0x7FFFFFFF;
  p_Dst = &Dst;
  do
  {
    if ( !*p_Dst )
      break;
    ++p_Dst;
    --v13;
  }
  while ( v13 );
  StringValue = v13 == 0 ? 0x80070057 : 0;
  v15 = (0x7FFFFFFF - v13) & -(__int64)(v13 != 0);
  if ( !v13 )
    goto LABEL_9;
  LocalFree((HLOCAL)*v12);
  *v12 = 0;
  StringValue = CopyString(&Dst, v15 + 1, (unsigned __int16 **)v7 + 7);
  if ( StringValue < 0 )
    goto LABEL_9;
  StringValue = QueryStringValue(phkResult, 0, L"Params", (unsigned __int16 **)v7 + 8);
  if ( StringValue < 0 )
    goto LABEL_9;
  StringValue = QueryStringValue(phkResult, 0, L"AppId", (unsigned __int16 **)v7 + 9);
  if ( StringValue < 0 )
    goto LABEL_9;
  StringValue = QueryStringValue(phkResult, 0, L"ContentTypes", (unsigned __int16 **)v7 + 10);
  if ( StringValue < 0 )
    goto LABEL_9;
  v16 = (_DWORD *)((char *)v7 + 88);
  StringValue = QueryDWordValue(phkResult, 0, L"MaxMessagesPerQueue", (unsigned __int8 **)v7 + 11);
  if ( StringValue < 0 )
    goto LABEL_9;
  if ( !*v16 )
    *v16 = 10;
  StringValue = QueryDWordValue(v21, a1, L"QueueId", (unsigned __int8 **)v7 + 12);
  if ( StringValue < 0 )
    goto LABEL_9;
  if ( !*((_DWORD *)v7 + 24) )
  {
LABEL_23:
    StringValue = -2147418113;
    goto LABEL_9;
  }
  v22 = (PushClient *)((char *)v7 + 192);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 192));
  v23 = 1;
  if ( *((_DWORD *)v7 + 45) )
  {
    StringValue = -2147023649;
  }
  else
  {
    StringValue = 0;
    if ( !a2 || (StringValue = PersistList::LoadList((PushClient *)((char *)v7 + 152), a2), StringValue >= 0) )
    {
      *((_QWORD *)v7 + 23) = a2;
      *((_DWORD *)v7 + 45) = 1;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 192));
  if ( StringValue < 0 )
    goto LABEL_9;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\PushRouter\\Settings", 0, 0x20019u, &v20) )
  {
    DWORD = OmaDmRegistryGetDWORD(v20, 0, L"MaxClientRelaunches", (unsigned int *)v7 + 61);
    StringValue = 0;
    if ( DWORD != -2147024894 )
      StringValue = DWORD;
    if ( StringValue < 0 )
      goto LABEL_9;
  }
  if ( !*((_DWORD *)v7 + 61) )
    *((_DWORD *)v7 + 61) = 3;
  StringValue = QueryDWordValue(phkResult, 0, L"RunAsSystem", (unsigned __int8 **)((char *)v7 + 100));
  if ( StringValue < 0 )
  {
    *((_DWORD *)v7 + 25) = 0;
    StringValue = 0;
  }
  *a3 = v7;
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v20 )
    RegCloseKey(v20);
  if ( v21 )
    RegCloseKey(v21);
  LeaveCriticalSection(&g_csPushRouter);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x180018060  mov     [rsp-8+arg_18], rbx
0x180018065  push    rbp
0x180018066  push    rsi
0x180018067  push    rdi
0x180018068  push    r12
0x18001806a  push    r13
0x18001806c  push    r14
0x18001806e  push    r15
0x180018070  lea     rbp, [rsp-180h]
0x180018078  sub     rsp, 280h
0x18001807f  mov     rax, cs:__security_cookie
0x180018086  xor     rax, rsp
0x180018089  mov     [rbp+1B0h+var_40], rax
0x180018090  mov     r13, r8
0x180018093  mov     r15, rdx
0x180018096  mov     r12, rcx
0x180018099  xor     r14d, r14d
0x18001809c  mov     [rsp+2B0h+hKey], r14
0x1800180a1  mov     [rsp+2B0h+var_280], r14
0x1800180a6  mov     [rsp+2B0h+var_268], r14
0x1800180ab  mov     [rsp+2B0h+var_270], r14
0x1800180b0  mov     [rsp+2B0h+Dst], r14w
0x1800180b6  xor     edx, edx; Val
0x1800180b8  mov     r8d, 206h; Size
0x1800180be  lea     rcx, [rsp+2B0h+var_24E]; void *
0x1800180c3  call    memset_0
0x1800180c8  lea     rcx, ?g_csPushRouter@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800180cf  call    cs:__imp_EnterCriticalSection
0x1800180d5  mov     [r13+0], r14
0x1800180d9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800180e0  mov     ecx, 0F8h; unsigned __int64
0x1800180e5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800180ea  mov     [rsp+2B0h+var_260], rax
0x1800180ef  test    rax, rax
0x1800180f2  jz      short loc_180018101
0x1800180f4  mov     rcx, rax; this
0x1800180f7  call    ??0PushClient@@QEAA@XZ; PushClient::PushClient(void)
0x1800180fc  mov     rdi, rax
0x1800180ff  jmp     short loc_180018104
0x180018101  mov     rdi, r14
0x180018104  test    rdi, rdi
0x180018107  jnz     short loc_180018110
0x180018109  mov     ebx, 8007000Eh
0x18001810e  jmp     short loc_180018161
0x180018110  lea     rax, [rsp+2B0h+hKey]
0x180018115  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18001811a  mov     esi, 20019h
0x18001811f  mov     r9d, esi; samDesired
0x180018122  xor     r8d, r8d; ulOptions
0x180018125  lea     rdx, ?c_szAppRegistrationByGenId@@3QBGB; "Software\\Microsoft\\PushRouter\\Regist"...
0x18001812c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018133  call    cs:__imp_RegOpenKeyExW
0x180018139  mov     ebx, eax
0x18001813b  test    eax, eax
0x18001813d  jz      loc_1800181DA
0x180018143  jle     short loc_18001814E
0x180018145  movzx   ebx, ax
0x180018148  or      ebx, 80070000h
0x18001814e  mov     rax, [rdi]
0x180018151  mov     edx, 1
0x180018156  mov     rcx, rdi
0x180018159  mov     rax, [rax]
0x18001815c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018161  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180018166  test    rcx, rcx
0x180018169  jz      short loc_180018171
0x18001816b  call    cs:__imp_RegCloseKey
0x180018171  mov     rcx, [rsp+2B0h+var_280]; hKey
0x180018176  test    rcx, rcx
0x180018179  jz      short loc_180018181
0x18001817b  call    cs:__imp_RegCloseKey
0x180018181  mov     rcx, [rsp+2B0h+var_270]; hKey
0x180018186  test    rcx, rcx
0x180018189  jz      short loc_180018191
0x18001818b  call    cs:__imp_RegCloseKey
0x180018191  mov     rcx, [rsp+2B0h+var_268]; hKey
0x180018196  test    rcx, rcx
0x180018199  jz      short loc_1800181A1
0x18001819b  call    cs:__imp_RegCloseKey
0x1800181a1  lea     rcx, ?g_csPushRouter@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800181a8  call    cs:__imp_LeaveCriticalSection
0x1800181ae  mov     eax, ebx
0x1800181b0  mov     rcx, [rbp+1B0h+var_40]
0x1800181b7  xor     rcx, rsp; StackCookie
0x1800181ba  call    __security_check_cookie
0x1800181bf  mov     rbx, [rsp+2B0h+arg_18]
0x1800181c7  add     rsp, 280h
0x1800181ce  pop     r15
0x1800181d0  pop     r14
0x1800181d2  pop     r13
0x1800181d4  pop     r12
0x1800181d6  pop     rdi
0x1800181d7  pop     rsi
0x1800181d8  pop     rbp
0x1800181d9  retn
0x1800181da  lea     rax, [rsp+2B0h+var_280]
0x1800181df  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1800181e4  mov     r9d, esi; samDesired
0x1800181e7  xor     r8d, r8d; ulOptions
0x1800181ea  mov     rdx, r12; lpSubKey
0x1800181ed  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800181f2  call    cs:__imp_RegOpenKeyExW
0x1800181f8  mov     ebx, eax
0x1800181fa  test    eax, eax
0x1800181fc  jnz     loc_180018143
0x180018202  lea     rax, [rsp+2B0h+var_268]
0x180018207  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18001820c  mov     r9d, esi; samDesired
0x18001820f  xor     r8d, r8d; ulOptions
0x180018212  mov     rdx, cs:?c_szAppRegistrationByGenIdStateSep@@3QEAGEA; lpSubKey
0x180018219  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018220  call    cs:__imp_RegOpenKeyExW
0x180018226  mov     ebx, eax
0x180018228  test    eax, eax
0x18001822a  jnz     loc_180018143
0x180018230  lea     r9, [rdi+30h]; unsigned __int16 **
0x180018234  lea     r8, aGenid; "GenId"
0x18001823b  xor     edx, edx; unsigned __int16 *
0x18001823d  mov     rcx, [rsp+2B0h+var_280]; HKEY
0x180018242  call    ?QueryStringValue@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; QueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180018247  mov     ebx, eax
0x180018249  test    eax, eax
0x18001824b  js      loc_18001814E
0x180018251  cmp     [rdi+30h], r14
0x180018255  jnz     short loc_180018261
0x180018257  mov     ebx, 8000FFFFh
0x18001825c  jmp     loc_18001814E
0x180018261  lea     rsi, [rdi+38h]
0x180018265  mov     r9, rsi; unsigned __int16 **
0x180018268  lea     r8, aPath; "Path"
0x18001826f  xor     edx, edx; unsigned __int16 *
0x180018271  mov     rcx, [rsp+2B0h+var_280]; HKEY
0x180018276  call    ?QueryStringValue@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; QueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18001827b  mov     ebx, eax
0x18001827d  test    eax, eax
0x18001827f  js      loc_18001814E
0x180018285  mov     rcx, [rsi]; lpSrc
0x180018288  test    rcx, rcx
0x18001828b  jz      short loc_180018257
0x18001828d  mov     r8d, 104h; nSize
0x180018293  lea     rdx, [rsp+2B0h+Dst]; lpDst
0x180018298  call    cs:__imp_ExpandEnvironmentStringsW
0x18001829e  test    eax, eax
0x1800182a0  jz      short loc_180018257
0x1800182a2  mov     [rbp+1B0h+var_4A], r14w
0x1800182aa  mov     edx, 7FFFFFFFh
0x1800182af  mov     ecx, edx
0x1800182b1  lea     rax, [rsp+2B0h+Dst]
0x1800182b6  cmp     [rax], r14w
0x1800182ba  jz      short loc_1800182C6
0x1800182bc  add     rax, 2
0x1800182c0  sub     rcx, 1
0x1800182c4  jnz     short loc_1800182B6
0x1800182c6  mov     rax, rcx
0x1800182c9  neg     rax
0x1800182cc  sbb     ebx, ebx
0x1800182ce  not     ebx
0x1800182d0  and     ebx, 80070057h
0x1800182d6  mov     rax, rcx
0x1800182d9  sub     rdx, rcx
0x1800182dc  neg     rax
0x1800182df  sbb     r14, r14
0x1800182e2  and     r14, rdx
0x1800182e5  test    rcx, rcx
0x1800182e8  jz      loc_18001814E
0x1800182ee  mov     rcx, [rsi]; hMem
0x1800182f1  call    cs:__imp_LocalFree
0x1800182f7  mov     qword ptr [rsi], 0
0x1800182fe  lea     edx, [r14+1]
0x180018302  mov     r8, rsi
0x180018305  lea     rcx, [rsp+2B0h+Dst]
0x18001830a  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180018310  mov     ebx, eax
0x180018312  xor     r14d, r14d
0x180018315  test    eax, eax
0x180018317  js      loc_18001814E
0x18001831d  lea     r9, [rdi+40h]; unsigned __int16 **
0x180018321  lea     r8, aParams; "Params"
0x180018328  xor     edx, edx; unsigned __int16 *
0x18001832a  mov     rcx, [rsp+2B0h+var_280]; HKEY
0x18001832f  call    ?QueryStringValue@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; QueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180018334  mov     ebx, eax
0x180018336  test    eax, eax
0x180018338  js      loc_18001814E
0x18001833e  lea     r9, [rdi+48h]; unsigned __int16 **
0x180018342  lea     r8, aAppid; "AppId"
0x180018349  xor     edx, edx; unsigned __int16 *
0x18001834b  mov     rcx, [rsp+2B0h+var_280]; HKEY
0x180018350  call    ?QueryStringValue@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; QueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180018355  mov     ebx, eax
0x180018357  test    eax, eax
0x180018359  js      loc_18001814E
0x18001835f  lea     r9, [rdi+50h]; unsigned __int16 **
0x180018363  lea     r8, ?c_szContentTypes@@3QBGB; "ContentTypes"
0x18001836a  xor     edx, edx; unsigned __int16 *
0x18001836c  mov     rcx, [rsp+2B0h+var_280]; HKEY
0x180018371  call    ?QueryStringValue@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; QueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x180018376  mov     ebx, eax
0x180018378  test    eax, eax
0x18001837a  js      loc_18001814E
0x180018380  lea     rsi, [rdi+58h]
0x180018384  mov     r9, rsi; unsigned __int8 **
0x180018387  lea     r8, ?c_szMaxMessagesPerQueue@@3QBGB; "MaxMessagesPerQueue"
0x18001838e  xor     edx, edx; unsigned __int16 *
0x180018390  mov     rcx, [rsp+2B0h+var_280]; HKEY
0x180018395  call    ?QueryDWordValue@@YAJPEAUHKEY__@@PEBG1PEAPEAE@Z; QueryDWordValue(HKEY__ *,ushort const *,ushort const *,uchar * *)
0x18001839a  mov     ebx, eax
0x18001839c  test    eax, eax
0x18001839e  js      loc_18001814E
0x1800183a4  cmp     [rsi], r14d
0x1800183a7  jnz     short loc_1800183AF
0x1800183a9  mov     dword ptr [rsi], 0Ah
0x1800183af  lea     r9, [rdi+60h]; unsigned __int8 **
0x1800183b3  lea     r8, ?c_szQueueId@@3QBGB; "QueueId"
0x1800183ba  mov     rdx, r12; unsigned __int16 *
0x1800183bd  mov     rcx, [rsp+2B0h+var_268]; HKEY
0x1800183c2  call    ?QueryDWordValue@@YAJPEAUHKEY__@@PEBG1PEAPEAE@Z; QueryDWordValue(HKEY__ *,ushort const *,ushort const *,uchar * *)
0x1800183c7  mov     ebx, eax
0x1800183c9  test    eax, eax
0x1800183cb  js      loc_18001814E
0x1800183d1  cmp     [rdi+60h], r14d
0x1800183d5  jz      loc_180018257
0x1800183db  lea     rsi, [rdi+98h]
0x1800183e2  lea     r14, [rsi+28h]
0x1800183e6  mov     [rsp+2B0h+var_260], r14
0x1800183eb  mov     rcx, r14; lpCriticalSection
0x1800183ee  call    cs:__imp_EnterCriticalSection
0x1800183f4  mov     [rsp+2B0h+var_258], 1
0x1800183f9  cmp     dword ptr [rsi+1Ch], 0
0x1800183fd  jz      short loc_180018406
0x1800183ff  mov     ebx, 800704DFh
0x180018404  jmp     short loc_180018429
0x180018406  xor     ebx, ebx
0x180018408  test    r15, r15
0x18001840b  jz      short loc_18001841E
0x18001840d  mov     rdx, r15; struct IPersistStore *
0x180018410  mov     rcx, rsi; this
0x180018413  call    ?LoadList@PersistList@@AEAAJPEAVIPersistStore@@@Z; PersistList::LoadList(IPersistStore *)
0x180018418  mov     ebx, eax
0x18001841a  test    eax, eax
0x18001841c  js      short loc_180018429
0x18001841e  mov     [rsi+20h], r15
0x180018422  mov     dword ptr [rsi+1Ch], 1
0x180018429  mov     rcx, r14; lpCriticalSection
0x18001842c  call    cs:__imp_LeaveCriticalSection
0x180018432  xor     r14d, r14d
0x180018435  test    ebx, ebx
0x180018437  js      loc_18001814E
0x18001843d  lea     rax, [rsp+2B0h+var_270]
0x180018442  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180018447  mov     r9d, 20019h; samDesired
0x18001844d  xor     r8d, r8d; ulOptions
0x180018450  lea     rdx, ?c_szPushRouterSettingsKey@@3QBGB; "Software\\Microsoft\\PushRouter\\Settin"...
0x180018457  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001845e  call    cs:__imp_RegOpenKeyExW
0x180018464  test    eax, eax
0x180018466  jnz     short loc_180018496
0x180018468  lea     r9, [rdi+0F4h]
0x18001846f  lea     r8, ?c_szMaxClientRelaunchesValueName@@3QBGB; "MaxClientRelaunches"
0x180018476  xor     edx, edx
0x180018478  mov     rcx, [rsp+2B0h+var_270]
0x18001847d  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180018483  mov     ebx, r14d
0x180018486  cmp     eax, 80070002h
0x18001848b  cmovnz  ebx, eax
0x18001848e  test    ebx, ebx
0x180018490  js      loc_18001814E
0x180018496  cmp     [rdi+0F4h], r14d
0x18001849d  jnz     short loc_1800184A9
0x18001849f  mov     dword ptr [rdi+0F4h], 3
0x1800184a9  lea     r9, [rdi+64h]; unsigned __int8 **
0x1800184ad  lea     r8, aRunassystem; "RunAsSystem"
0x1800184b4  xor     edx, edx; unsigned __int16 *
0x1800184b6  mov     rcx, [rsp+2B0h+var_280]; HKEY
0x1800184bb  call    ?QueryDWordValue@@YAJPEAUHKEY__@@PEBG1PEAPEAE@Z; QueryDWordValue(HKEY__ *,ushort const *,ushort const *,uchar * *)
0x1800184c0  mov     ebx, eax
0x1800184c2  test    eax, eax
0x1800184c4  jns     short loc_1800184CD
0x1800184c6  mov     [rdi+64h], r14d
0x1800184ca  mov     ebx, r14d
0x1800184cd  mov     [r13+0], rdi
0x1800184d1  jmp     loc_180018161
```
