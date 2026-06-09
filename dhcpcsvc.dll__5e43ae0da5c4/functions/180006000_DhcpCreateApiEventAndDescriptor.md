# DhcpCreateApiEventAndDescriptor

- ea: `0x180006000`
- end: `0x180006171`
- name: `DhcpCreateApiEventAndDescriptor`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008c50`

## callees

- `0x180003280`
- `0x1800048c0`
- `0x180005162`
- `0x180006000`
- `0x18000fdc4`
- `0x180011060`
- `0x180012a00`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetLastError` at `0x18000611c`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetLastError` at `0x18000611c`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCurrentProcessId` at `0x1800060dc`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCurrentProcessId` at `0x1800060dc`
- `api-ms-win-downlevel-kernel32-l1-1-0!CreateEventA` at `0x18000610e`
- `api-ms-win-downlevel-kernel32-l1-1-0!CreateEventA` at `0x18000610e`

## pseudocode

```c
__int64 __fastcall DhcpCreateApiEventAndDescriptor(_QWORD *a1, signed __int32 *a2)
{
  __int64 v4; // rcx
  unsigned int ApiEventSecurityDescriptor; // ebx
  void *v6; // rax
  signed __int32 v7; // ebp
  DWORD CurrentProcessId; // eax
  HANDLE v9; // rax
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+30h] [rbp-158h] BYREF
  char pszDest[272]; // [rsp+50h] [rbp-138h] BYREF

  memset_0(pszDest, 0, 0x104u);
  *(_QWORD *)&EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = 0;
  *(_QWORD *)&EventAttributes.bInheritHandle = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_qq(v4, 83, WPP_e15037783097355a5233924022d92169_Traceguids, a1, a2);
  if ( a1 )
    *a1 = 0;
  if ( a2 )
    *a2 = 0;
  if ( !a1 || !a2 )
  {
    ApiEventSecurityDescriptor = 87;
    goto LABEL_16;
  }
  v6 = (void *)qword_18001E230;
  EventAttributes.lpSecurityDescriptor = 0;
  if ( !qword_18001E230 )
  {
    ApiEventSecurityDescriptor = CreateApiEventSecurityDescriptor(v4);
    if ( ApiEventSecurityDescriptor )
      goto LABEL_16;
    v6 = (void *)qword_18001E230;
  }
  EventAttributes.lpSecurityDescriptor = v6;
  v7 = _InterlockedIncrement(&dword_18001E1F0);
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfA(pszDest, 0x104u, "Global\\DhcpPid%16xUniqueId%16x", CurrentProcessId, v7);
  v9 = CreateEventA(&EventAttributes, 0, 0, pszDest);
  *a1 = v9;
  if ( v9 )
  {
    ApiEventSecurityDescriptor = 0;
    *a2 = v7;
  }
  else
  {
    ApiEventSecurityDescriptor = GetLastError();
  }
LABEL_16:
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 84, WPP_e15037783097355a5233924022d92169_Traceguids, ApiEventSecurityDescriptor);
  return ApiEventSecurityDescriptor;
}

```

## disassembly

```asm
0x180006000  mov     [rsp+arg_10], rbx
0x180006005  push    rbp
0x180006006  push    rsi
0x180006007  push    rdi
0x180006008  sub     rsp, 170h
0x18000600f  mov     rax, cs:__security_cookie
0x180006016  xor     rax, rsp
0x180006019  mov     [rsp+188h+var_28], rax
0x180006021  mov     rdi, rdx
0x180006024  mov     rsi, rcx
0x180006027  xor     edx, edx; Val
0x180006029  lea     rcx, [rsp+188h+pszDest]; void *
0x18000602e  mov     r8d, 104h; Size
0x180006034  call    memset_0
0x180006039  mov     qword ptr [rsp+188h+EventAttributes.nLength], 18h
0x180006042  mov     [rsp+188h+EventAttributes.lpSecurityDescriptor], 0
0x18000604b  mov     qword ptr [rsp+188h+EventAttributes.bInheritHandle], 0
0x180006054  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000605b  jz      short loc_180006076
0x18000605d  mov     edx, 53h ; 'S'
0x180006062  mov     [rsp+188h+var_168], rdi
0x180006067  mov     r9, rsi
0x18000606a  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180006071  call    WPP_SF_qq
0x180006076  test    rsi, rsi
0x180006079  jz      short loc_180006082
0x18000607b  mov     qword ptr [rsi], 0
0x180006082  test    rdi, rdi
0x180006085  jz      short loc_18000608D
0x180006087  mov     dword ptr [rdi], 0
0x18000608d  test    rsi, rsi
0x180006090  jnz     short loc_18000609C
0x180006092  mov     ebx, 57h ; 'W'
0x180006097  jmp     loc_18000612A
0x18000609c  test    rdi, rdi
0x18000609f  jz      short loc_180006092
0x1800060a1  mov     rax, cs:qword_18001E230
0x1800060a8  mov     [rsp+188h+EventAttributes.lpSecurityDescriptor], 0
0x1800060b1  test    rax, rax
0x1800060b4  jnz     short loc_1800060C8
0x1800060b6  call    CreateApiEventSecurityDescriptor
0x1800060bb  mov     ebx, eax
0x1800060bd  test    eax, eax
0x1800060bf  jnz     short loc_18000612A
0x1800060c1  mov     rax, cs:qword_18001E230
0x1800060c8  mov     [rsp+188h+EventAttributes.lpSecurityDescriptor], rax
0x1800060cd  mov     ebp, 1
0x1800060d2  lock xadd cs:dword_18001E1F0, ebp
0x1800060da  inc     ebp
0x1800060dc  call    cs:__imp_GetCurrentProcessId
0x1800060e2  lea     r8, aGlobalDhcppid1; "Global\\DhcpPid%16xUniqueId%16x"
0x1800060e9  mov     dword ptr [rsp+188h+var_168], ebp
0x1800060ed  mov     r9d, eax
0x1800060f0  lea     rcx, [rsp+188h+pszDest]; pszDest
0x1800060f5  mov     edx, 104h; cchDest
0x1800060fa  call    StringCchPrintfA
0x1800060ff  lea     r9, [rsp+188h+pszDest]; lpName
0x180006104  xor     r8d, r8d; bInitialState
0x180006107  xor     edx, edx; bManualReset
0x180006109  lea     rcx, [rsp+188h+EventAttributes]; lpEventAttributes
0x18000610e  call    cs:__imp_CreateEventA
0x180006114  mov     [rsi], rax
0x180006117  test    rax, rax
0x18000611a  jnz     short loc_180006126
0x18000611c  call    cs:__imp_GetLastError
0x180006122  mov     ebx, eax
0x180006124  jmp     short loc_18000612A
0x180006126  xor     ebx, ebx
0x180006128  mov     [rdi], ebp
0x18000612a  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180006131  jz      short loc_18000614C
0x180006133  mov     edx, 54h ; 'T'
0x180006138  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000613f  mov     ecx, 404h
0x180006144  mov     r9d, ebx
0x180006147  call    WPP_SF_d
0x18000614c  mov     eax, ebx
0x18000614e  mov     rcx, [rsp+188h+var_28]
0x180006156  xor     rcx, rsp; StackCookie
0x180006159  call    __security_check_cookie
0x18000615e  mov     rbx, [rsp+188h+arg_10]
0x180006166  add     rsp, 170h
0x18000616d  pop     rdi
0x18000616e  pop     rsi
0x18000616f  pop     rbp
0x180006170  retn
```
