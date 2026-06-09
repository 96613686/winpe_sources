# RpcSrvRegisterConnectionStateNotification_New

- ea: `0x18002b3dc`
- end: `0x18002b5fa`
- name: `RpcSrvRegisterConnectionStateNotification_New`
- size: `542`
- prototype: `__int64 __fastcall(_WORD *, unsigned int, STRSAFE_LPWSTR *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002b1b0`

## callees

- `0x180001c48`
- `0x1800020d0`
- `0x1800021c0`
- `0x18001b91c`
- `0x18001c0d8`
- `0x18001cef0`
- `0x18002b3dc`
- `0x18002e8d0`
- `0x18003fe5c`
- `0x18004d1a0`
- `0x18004d9e8`
- `0x18004dd28`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18002b4ea`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18002b4ea`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b52d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002b52d`
- `RPCRT4!UuidCreate` at `0x18002b4a7`
- `RPCRT4!UuidCreate` at `0x18002b4a7`
- `RPCRT4!UuidToStringW` at `0x18002b4bd`
- `RPCRT4!UuidToStringW` at `0x18002b4bd`
- `RPCRT4!RpcStringFreeW` at `0x18002b59f`
- `RPCRT4!RpcStringFreeW` at `0x18002b59f`

## pseudocode

```c
__int64 __fastcall RpcSrvRegisterConnectionStateNotification_New(_WORD *a1, unsigned int a2, STRSAFE_LPWSTR *a3)
{
  int v3; // r14d
  CRpcWatchDog *v7; // rcx
  unsigned int v8; // ebx
  int v9; // r8d
  RPC_STATUS v10; // eax
  __int64 v11; // rax
  size_t v12; // rbx
  wchar_t *v13; // rax
  HANDLE v14; // rax
  unsigned int LastErrorOrUnknown; // eax
  __int64 v16; // rdx
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-29h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+38h] [rbp-21h] BYREF
  UUID v20[2]; // [rsp+50h] [rbp-9h] BYREF
  UUID Uuid; // [rsp+70h] [rbp+17h] BYREF

  *(_QWORD *)&EventAttributes.nLength = 24;
  StringUuid = 0;
  *(_QWORD *)&EventAttributes.bInheritHandle = 0;
  EventAttributes.lpSecurityDescriptor = qword_1800536A0;
  Uuid = 0;
  v3 = 0;
  memset(v20, 0, sizeof(v20));
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_d(1028, 174, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, a2);
  v8 = RpcValidateRequests(a1);
  if ( !v8 )
  {
    *(_QWORD *)&v20[0].Data1 = RpcSrvRegisterConnectionStateNotification;
    CRpcWatchDog::AddEntry(v7, (struct _WatchDogEntry *)v20, v9);
    v3 = 1;
    if ( (a2 & 0xF) == 0 || !a3 )
    {
      v8 = 87;
      goto LABEL_22;
    }
    v10 = UuidCreate(&Uuid);
    if ( v10 )
    {
      v8 = 1627;
      if ( (xmmword_1800616A0 & 2) == 0 )
        goto LABEL_22;
      v16 = 175;
    }
    else
    {
      v10 = UuidToStringW(&Uuid, &StringUuid);
      if ( !v10 )
      {
        v11 = -1;
        do
          ++v11;
        while ( StringUuid[v11] );
        v12 = v11 + 8;
        v13 = (wchar_t *)LocalAlloc(0x40u, 2 * (v11 + 8));
        *a3 = v13;
        if ( v13 )
        {
          StringCchCopyW(v13, v12, L"Global\\");
          StringCchCatW(*a3, v12, StringUuid);
          v14 = CreateEventW(&EventAttributes, 0, 0, *a3);
          if ( v14 )
            LastErrorOrUnknown = RegisterConnectionStateNotification(a2, v14, *a3);
          else
            LastErrorOrUnknown = GetLastErrorOrUnknown();
          v8 = LastErrorOrUnknown;
        }
        else
        {
          v8 = 8;
        }
        goto LABEL_22;
      }
      v8 = 1627;
      if ( (xmmword_1800616A0 & 2) == 0 )
        goto LABEL_22;
      v16 = 176;
    }
    WPP_SF_Dd(1025, v16, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, 1627, v10);
  }
LABEL_22:
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  if ( v3 )
    CRpcWatchDog::RemoveEntry(v7, (struct _WatchDogEntry *)v20);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 177, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18002b3dc  mov     [rsp-8+arg_18], rbx
0x18002b3e1  push    rbp
0x18002b3e2  push    rsi
0x18002b3e3  push    rdi
0x18002b3e4  push    r14
0x18002b3e6  push    r15
0x18002b3e8  lea     rbp, [rsp-37h]
0x18002b3ed  sub     rsp, 90h
0x18002b3f4  mov     rax, cs:__security_cookie
0x18002b3fb  xor     rax, rsp
0x18002b3fe  mov     [rbp+57h+var_30], rax
0x18002b402  xor     r15d, r15d
0x18002b405  mov     qword ptr [rbp+57h+EventAttributes.nLength], 18h
0x18002b40d  xorps   xmm1, xmm1
0x18002b410  mov     [rbp+57h+StringUuid], r15
0x18002b414  lea     rax, qword_1800536A0
0x18002b41b  mov     qword ptr [rbp+57h+EventAttributes.bInheritHandle], r15
0x18002b41f  xorps   xmm0, xmm0
0x18002b422  mov     [rbp+57h+EventAttributes.lpSecurityDescriptor], rax
0x18002b426  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x18002b42a  mov     r14d, r15d
0x18002b42d  mov     rdi, r8
0x18002b430  movups  [rbp+57h+var_60], xmm1
0x18002b434  mov     esi, edx
0x18002b436  mov     rbx, rcx
0x18002b439  movups  [rbp+57h+var_50], xmm1
0x18002b43d  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002b444  jz      short loc_18002B45F
0x18002b446  mov     edx, 0AEh
0x18002b44b  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002b452  mov     ecx, 404h
0x18002b457  mov     r9d, esi
0x18002b45a  call    WPP_SF_d
0x18002b45f  mov     edx, 1
0x18002b464  mov     rcx, rbx
0x18002b467  call    RpcValidateRequests
0x18002b46c  mov     ebx, eax
0x18002b46e  test    eax, eax
0x18002b470  jnz     loc_18002B595
0x18002b476  lea     rax, RpcSrvRegisterConnectionStateNotification
0x18002b47d  lea     rdx, [rbp+57h+var_60]; struct _WatchDogEntry *
0x18002b481  mov     qword ptr [rbp+57h+var_60], rax
0x18002b485  call    ?AddEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@H@Z; CRpcWatchDog::AddEntry(_WatchDogEntry *,int)
0x18002b48a  lea     r14d, [rbx+1]
0x18002b48e  test    sil, 0Fh
0x18002b492  jnz     short loc_18002B49E
0x18002b494  mov     ebx, 57h ; 'W'
0x18002b499  jmp     loc_18002B595
0x18002b49e  test    rdi, rdi
0x18002b4a1  jz      short loc_18002B494
0x18002b4a3  lea     rcx, [rbp+57h+Uuid]; Uuid
0x18002b4a7  call    cs:__imp_UuidCreate
0x18002b4ad  test    eax, eax
0x18002b4af  jnz     loc_18002B569
0x18002b4b5  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x18002b4b9  lea     rcx, [rbp+57h+Uuid]; Uuid
0x18002b4bd  call    cs:__imp_UuidToStringW
0x18002b4c3  test    eax, eax
0x18002b4c5  jnz     loc_18002B550
0x18002b4cb  mov     rcx, [rbp+57h+StringUuid]
0x18002b4cf  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002b4d3  inc     rax
0x18002b4d6  cmp     [rcx+rax*2], r15w
0x18002b4db  jnz     short loc_18002B4D3
0x18002b4dd  lea     rbx, [rax+8]
0x18002b4e1  mov     ecx, 40h ; '@'; uFlags
0x18002b4e6  lea     rdx, [rbx+rbx]; uBytes
0x18002b4ea  call    cs:__imp_LocalAlloc
0x18002b4f0  mov     [rdi], rax
0x18002b4f3  test    rax, rax
0x18002b4f6  jnz     short loc_18002B500
0x18002b4f8  lea     ebx, [rax+8]
0x18002b4fb  jmp     loc_18002B595
0x18002b500  lea     r8, aGlobal; "Global\\"
0x18002b507  mov     rdx, rbx; cchDest
0x18002b50a  mov     rcx, rax; pszDest
0x18002b50d  call    StringCchCopyW
0x18002b512  mov     r8, [rbp+57h+StringUuid]; pszSrc
0x18002b516  mov     rdx, rbx; cchDest
0x18002b519  mov     rcx, [rdi]; pszDest
0x18002b51c  call    StringCchCatW
0x18002b521  mov     r9, [rdi]; lpName
0x18002b524  lea     rcx, [rbp+57h+EventAttributes]; lpEventAttributes
0x18002b528  xor     r8d, r8d; bInitialState
0x18002b52b  xor     edx, edx; bManualReset
0x18002b52d  call    cs:__imp_CreateEventW
0x18002b533  test    rax, rax
0x18002b536  jnz     short loc_18002B541
0x18002b538  call    GetLastErrorOrUnknown
0x18002b53d  mov     ebx, eax
0x18002b53f  jmp     short loc_18002B595
0x18002b541  mov     r8, [rdi]
0x18002b544  mov     rdx, rax
0x18002b547  mov     ecx, esi
0x18002b549  call    RegisterConnectionStateNotification
0x18002b54e  jmp     short loc_18002B53D
0x18002b550  mov     r9d, 65Bh
0x18002b556  mov     ebx, r9d
0x18002b559  test    byte ptr cs:xmmword_1800616A0, 2
0x18002b560  jz      short loc_18002B595
0x18002b562  mov     edx, 0B0h
0x18002b567  jmp     short loc_18002B580
0x18002b569  mov     r9d, 65Bh
0x18002b56f  mov     ebx, r9d
0x18002b572  test    byte ptr cs:xmmword_1800616A0, 2
0x18002b579  jz      short loc_18002B595
0x18002b57b  mov     edx, 0AFh
0x18002b580  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002b587  mov     [rsp+0B0h+var_90], eax
0x18002b58b  mov     ecx, 401h
0x18002b590  call    WPP_SF_Dd
0x18002b595  cmp     [rbp+57h+StringUuid], r15
0x18002b599  jz      short loc_18002B5A5
0x18002b59b  lea     rcx, [rbp+57h+StringUuid]; String
0x18002b59f  call    cs:__imp_RpcStringFreeW
0x18002b5a5  test    r14d, r14d
0x18002b5a8  jz      short loc_18002B5B3
0x18002b5aa  lea     rdx, [rbp+57h+var_60]; struct _WatchDogEntry *
0x18002b5ae  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x18002b5b3  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002b5ba  jz      short loc_18002B5D5
0x18002b5bc  mov     edx, 0B1h
0x18002b5c1  lea     r8, WPP_8f191193bd893a0df37ce357b02d0085_Traceguids
0x18002b5c8  mov     ecx, 404h
0x18002b5cd  mov     r9d, ebx
0x18002b5d0  call    WPP_SF_D
0x18002b5d5  mov     eax, ebx
0x18002b5d7  mov     rcx, [rbp+57h+var_30]
0x18002b5db  xor     rcx, rsp; StackCookie
0x18002b5de  call    __security_check_cookie
0x18002b5e3  mov     rbx, [rsp+0B0h+arg_18]
0x18002b5eb  add     rsp, 90h
0x18002b5f2  pop     r15
0x18002b5f4  pop     r14
0x18002b5f6  pop     rdi
0x18002b5f7  pop     rsi
0x18002b5f8  pop     rbp
0x18002b5f9  retn
```
