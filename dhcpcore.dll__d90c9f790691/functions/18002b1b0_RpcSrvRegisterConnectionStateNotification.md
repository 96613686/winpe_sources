# RpcSrvRegisterConnectionStateNotification

- ea: `0x18002b1b0`
- end: `0x18002b3d4`
- name: `RpcSrvRegisterConnectionStateNotification`
- size: `548`
- prototype: `__int64 __fastcall(_WORD *, unsigned int, STRSAFE_LPWSTR *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180001c48`
- `0x1800020d0`
- `0x1800021c0`
- `0x18001b91c`
- `0x18001cef0`
- `0x18002b1b0`
- `0x18002b3dc`
- `0x18002e8d0`
- `0x18003fe5c`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d9e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b34e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b34e`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18002b300`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18002b300`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b340`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b340`
- `RPCRT4!UuidCreate` at `0x18002b289`
- `RPCRT4!UuidCreate` at `0x18002b289`
- `RPCRT4!UuidToStringW` at `0x18002b2c7`
- `RPCRT4!UuidToStringW` at `0x18002b2c7`
- `RPCRT4!RpcStringFreeW` at `0x18002b3a0`
- `RPCRT4!RpcStringFreeW` at `0x18002b3a0`

## pseudocode

```c
__int64 __fastcall RpcSrvRegisterConnectionStateNotification(_WORD *a1, unsigned int a2, STRSAFE_LPWSTR *a3)
{
  int v7; // r14d
  CRpcWatchDog *v8; // rcx
  unsigned int LastError; // ebx
  int v10; // r8d
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rax
  size_t v14; // rbx
  wchar_t *v15; // rax
  HANDLE v16; // r15
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-60h] BYREF
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+28h] [rbp-58h] BYREF
  UUID v19[2]; // [rsp+40h] [rbp-40h] BYREF
  UUID Uuid; // [rsp+60h] [rbp-20h] BYREF

  *(_QWORD *)&EventAttributes.nLength = 24;
  StringUuid = 0;
  EventAttributes.lpSecurityDescriptor = qword_1800536A0;
  *(_QWORD *)&EventAttributes.bInheritHandle = 0;
  Uuid = 0;
  memset(v19, 0, sizeof(v19));
  if ( g_fVelocityApistubStyleUpdate )
    return RpcSrvRegisterConnectionStateNotification_New(a1, a2, a3);
  v7 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 178, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids);
  LastError = RpcValidateRequests(a1);
  if ( LastError )
    goto LABEL_25;
  *(_QWORD *)&v19[0].Data1 = RpcSrvRegisterConnectionStateNotification;
  CRpcWatchDog::AddEntry(v8, (struct _WatchDogEntry *)v19, v10);
  v7 = 1;
  if ( (a2 & 0xF) == 0 || !a3 )
  {
    LastError = 87;
    goto LABEL_25;
  }
  v11 = UuidCreate(&Uuid);
  if ( v11 )
  {
    if ( (xmmword_1800616A0 & 2) == 0 )
    {
LABEL_12:
      LastError = 1627;
      goto LABEL_25;
    }
    v12 = 179;
LABEL_11:
    WPP_SF_d(1025, v12, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v11);
    goto LABEL_12;
  }
  v11 = UuidToStringW(&Uuid, &StringUuid);
  if ( v11 )
  {
    if ( (xmmword_1800616A0 & 2) == 0 )
      goto LABEL_12;
    v12 = 180;
    goto LABEL_11;
  }
  v13 = -1;
  do
    ++v13;
  while ( StringUuid[v13] );
  v14 = v13 + 8;
  v15 = (wchar_t *)LocalAlloc(0x40u, 2 * (v13 + 8));
  *a3 = v15;
  if ( !v15 )
  {
    LastError = 8;
    goto LABEL_25;
  }
  StringCchCopyW(v15, v14, L"Global\\");
  StringCchCatW(*a3, v14, StringUuid);
  v16 = CreateEventW(&EventAttributes, 0, 0, *a3);
  if ( !v16 && (LastError = GetLastError()) != 0 || (LastError = RegisterConnectionStateNotification(a2, v16, *a3)) != 0 )
  {
LABEL_25:
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 181, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, LastError);
  }
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  if ( v7 )
    CRpcWatchDog::RemoveEntry(v8, (struct _WatchDogEntry *)v19);
  return LastError;
}

```

## disassembly

```asm
0x18002b1b0  push    rbp
0x18002b1b2  push    rbx
0x18002b1b3  push    rsi
0x18002b1b4  push    rdi
0x18002b1b5  push    r12
0x18002b1b7  push    r14
0x18002b1b9  push    r15
0x18002b1bb  mov     rbp, rsp
0x18002b1be  sub     rsp, 80h
0x18002b1c5  mov     rax, cs:__security_cookie
0x18002b1cc  xor     rax, rsp
0x18002b1cf  mov     [rbp+var_10], rax
0x18002b1d3  xor     r12d, r12d
0x18002b1d6  mov     qword ptr [rbp+EventAttributes.nLength], 18h
0x18002b1de  cmp     cs:g_fVelocityApistubStyleUpdate, r12d
0x18002b1e5  lea     rax, qword_1800536A0
0x18002b1ec  xorps   xmm1, xmm1
0x18002b1ef  mov     [rbp+StringUuid], r12
0x18002b1f3  xorps   xmm0, xmm0
0x18002b1f6  mov     [rbp+EventAttributes.lpSecurityDescriptor], rax
0x18002b1fa  mov     rdi, r8
0x18002b1fd  mov     qword ptr [rbp+EventAttributes.bInheritHandle], r12
0x18002b201  mov     esi, edx
0x18002b203  mov     rbx, rcx
0x18002b206  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x18002b20a  movups  [rbp+var_40], xmm1
0x18002b20e  movups  [rbp+var_30], xmm1
0x18002b212  jz      short loc_18002B21E
0x18002b214  call    RpcSrvRegisterConnectionStateNotification_New
0x18002b219  jmp     loc_18002B3B6
0x18002b21e  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002b225  mov     r14d, r12d
0x18002b228  jz      short loc_18002B240
0x18002b22a  mov     edx, 0B2h
0x18002b22f  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002b236  mov     ecx, 404h
0x18002b23b  call    WPP_SF_
0x18002b240  mov     r15d, 1
0x18002b246  mov     rcx, rbx
0x18002b249  mov     edx, r15d
0x18002b24c  call    RpcValidateRequests
0x18002b251  mov     ebx, eax
0x18002b253  test    eax, eax
0x18002b255  jnz     loc_18002B374
0x18002b25b  lea     rax, RpcSrvRegisterConnectionStateNotification
0x18002b262  lea     rdx, [rbp+var_40]; struct _WatchDogEntry *
0x18002b266  mov     qword ptr [rbp+var_40], rax
0x18002b26a  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002b26f  mov     r14d, r15d
0x18002b272  test    sil, 0Fh
0x18002b276  jz      loc_18002B36F
0x18002b27c  test    rdi, rdi
0x18002b27f  jz      loc_18002B36F
0x18002b285  lea     rcx, [rbp+Uuid]; Uuid
0x18002b289  call    cs:__imp_UuidCreate
0x18002b28f  test    eax, eax
0x18002b291  jz      short loc_18002B2BF
0x18002b293  test    byte ptr cs:xmmword_1800616A0, 2
0x18002b29a  jz      short loc_18002B2B5
0x18002b29c  mov     edx, 0B3h
0x18002b2a1  mov     ecx, 401h
0x18002b2a6  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002b2ad  mov     r9d, eax
0x18002b2b0  call    WPP_SF_d
0x18002b2b5  mov     ebx, 65Bh
0x18002b2ba  jmp     loc_18002B374
0x18002b2bf  lea     rdx, [rbp+StringUuid]; StringUuid
0x18002b2c3  lea     rcx, [rbp+Uuid]; Uuid
0x18002b2c7  call    cs:__imp_UuidToStringW
0x18002b2cd  test    eax, eax
0x18002b2cf  jz      short loc_18002B2E1
0x18002b2d1  test    byte ptr cs:xmmword_1800616A0, 2
0x18002b2d8  jz      short loc_18002B2B5
0x18002b2da  mov     edx, 0B4h
0x18002b2df  jmp     short loc_18002B2A1
0x18002b2e1  mov     rcx, [rbp+StringUuid]
0x18002b2e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b2e9  inc     rax
0x18002b2ec  cmp     [rcx+rax*2], r12w
0x18002b2f1  jnz     short loc_18002B2E9
0x18002b2f3  lea     rbx, [rax+8]
0x18002b2f7  mov     ecx, 40h ; '@'; uFlags
0x18002b2fc  lea     rdx, [rbx+rbx]; uBytes
0x18002b300  call    cs:__imp_LocalAlloc
0x18002b306  mov     [rdi], rax
0x18002b309  test    rax, rax
0x18002b30c  jnz     short loc_18002B313
0x18002b30e  lea     ebx, [rax+8]
0x18002b311  jmp     short loc_18002B374
0x18002b313  lea     r8, aGlobal; "Global\\"
0x18002b31a  mov     rdx, rbx; cchDest
0x18002b31d  mov     rcx, rax; pszDest
0x18002b320  call    StringCchCopyW
0x18002b325  mov     r8, [rbp+StringUuid]; pszSrc
0x18002b329  mov     rdx, rbx; cchDest
0x18002b32c  mov     rcx, [rdi]; pszDest
0x18002b32f  call    StringCchCatW
0x18002b334  mov     r9, [rdi]; lpName
0x18002b337  lea     rcx, [rbp+EventAttributes]; lpEventAttributes
0x18002b33b  xor     r8d, r8d; bInitialState
0x18002b33e  xor     edx, edx; bManualReset
0x18002b340  call    cs:__imp_CreateEventW
0x18002b346  mov     r15, rax
0x18002b349  test    rax, rax
0x18002b34c  jnz     short loc_18002B35A
0x18002b34e  call    cs:__imp_GetLastError
0x18002b354  mov     ebx, eax
0x18002b356  test    eax, eax
0x18002b358  jnz     short loc_18002B374
0x18002b35a  mov     r8, [rdi]
0x18002b35d  mov     rdx, r15
0x18002b360  mov     ecx, esi
0x18002b362  call    RegisterConnectionStateNotification
0x18002b367  mov     ebx, eax
0x18002b369  test    eax, eax
0x18002b36b  jz      short loc_18002B396
0x18002b36d  jmp     short loc_18002B374
0x18002b36f  mov     ebx, 57h ; 'W'
0x18002b374  test    byte ptr cs:xmmword_1800616A0, 2
0x18002b37b  jz      short loc_18002B396
0x18002b37d  mov     edx, 0B5h
0x18002b382  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002b389  mov     ecx, 401h
0x18002b38e  mov     r9d, ebx
0x18002b391  call    WPP_SF_D
0x18002b396  cmp     [rbp+StringUuid], r12
0x18002b39a  jz      short loc_18002B3A6
0x18002b39c  lea     rcx, [rbp+StringUuid]; String
0x18002b3a0  call    cs:__imp_RpcStringFreeW
0x18002b3a6  test    r14d, r14d
0x18002b3a9  jz      short loc_18002B3B4
0x18002b3ab  lea     rdx, [rbp+var_40]; struct _WatchDogEntry *
0x18002b3af  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002b3b4  mov     eax, ebx
0x18002b3b6  mov     rcx, [rbp+var_10]
0x18002b3ba  xor     rcx, rsp; StackCookie
0x18002b3bd  call    __security_check_cookie
0x18002b3c2  add     rsp, 80h
0x18002b3c9  pop     r15
0x18002b3cb  pop     r14
0x18002b3cd  pop     r12
0x18002b3cf  pop     rdi
0x18002b3d0  pop     rsi
0x18002b3d1  pop     rbx
0x18002b3d2  pop     rbp
0x18002b3d3  retn
```
