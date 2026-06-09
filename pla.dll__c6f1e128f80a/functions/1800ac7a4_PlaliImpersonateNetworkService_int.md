# PlaliImpersonateNetworkService(int *)

- ea: `0x1800ac7a4`
- end: `0x1800ac9b3`
- name: `?PlaliImpersonateNetworkService@@YAJPEAH@Z`
- size: `527`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18012fdec`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x1800ac7a4`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac931`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac931`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac90e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac90e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800ac8f3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800ac8f3`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x1800ac7f8`
- `api-ms-win-security-logon-l1-1-1!LogonUserW` at `0x1800ac7f8`

## string_xrefs

- `0x1800ac8a8`: `PlaliImpersonateNetworkService`
- `0x1800ac7f1`: `NetworkService`

## pseudocode

```c
__int64 __fastcall PlaliImpersonateNetworkService(int *a1)
{
  DWORD LastError; // eax
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rax
  DWORD v7; // eax
  int v8; // eax
  __int64 v9; // rax
  int v10; // [rsp+70h] [rbp-90h] BYREF
  int v11; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hToken; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v13[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v14[64]; // [rsp+110h] [rbp+10h] BYREF

  hToken = 0;
  if ( !LogonUserW(L"NetworkService", L"NT AUTHORITY", (LPCWSTR)&szPassword, 5u, 0, &hToken) )
  {
    LastError = GetLastError();
    v3 = PlaiHResultFromWin32(LastError);
    v4 = v3;
    if ( v3 < 0 )
    {
      v10 = 0;
      v11 = v3;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v13, 0x4000000000000800uLL);
        v5 = -1;
        do
          ++v5;
        while ( v13[v5] );
        EventingWriteEvent(
          &g_Eventing,
          PLA_EVENT_ERROR,
          5,
          &v11,
          4,
          qword_180147320,
          1,
          &v10,
          4,
          "PlaliImpersonateNetworkService",
          31,
          v13,
          (unsigned int)(2 * v5) + 2LL);
      }
      goto LABEL_13;
    }
  }
  if ( ImpersonateLoggedOnUser(hToken) )
  {
    v4 = 0;
LABEL_12:
    *a1 = 1;
    goto LABEL_13;
  }
  v7 = GetLastError();
  v8 = PlaiHResultFromWin32(v7);
  v4 = v8;
  if ( v8 >= 0 )
    goto LABEL_12;
  v11 = 0;
  v10 = v8;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v14, 0x4000000000000800uLL);
    v9 = -1;
    do
      ++v9;
    while ( v14[v9] );
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v10,
      4,
      qword_180147320,
      1,
      &v11,
      4,
      "PlaliImpersonateNetworkService",
      31,
      v14,
      (unsigned int)(2 * v9) + 2LL);
  }
LABEL_13:
  if ( hToken )
    CloseHandle(hToken);
  return v4;
}

```

## disassembly

```asm
0x1800ac7a4  push    rbp
0x1800ac7a6  push    rbx
0x1800ac7a7  push    rsi
0x1800ac7a8  push    rdi
0x1800ac7a9  lea     rbp, [rsp-0A8h]
0x1800ac7b1  sub     rsp, 1A8h
0x1800ac7b8  mov     rax, cs:__security_cookie
0x1800ac7bf  xor     rax, rsp
0x1800ac7c2  mov     [rbp+0C0h+var_30], rax
0x1800ac7c9  xor     esi, esi
0x1800ac7cb  lea     rax, [rbp+0C0h+hToken]
0x1800ac7cf  mov     rdi, rcx
0x1800ac7d2  mov     [rsp+1C0h+phToken], rax; phToken
0x1800ac7d7  lea     r8, szPassword; lpszPassword
0x1800ac7de  mov     [rbp+0C0h+hToken], rsi
0x1800ac7e2  lea     rdx, szDomain; "NT AUTHORITY"
0x1800ac7e9  mov     [rsp+1C0h+dwLogonProvider], esi; dwLogonProvider
0x1800ac7ed  lea     r9d, [rsi+5]; dwLogonType
0x1800ac7f1  lea     rcx, szUsername; "NetworkService"
0x1800ac7f8  call    cs:__imp_LogonUserW
0x1800ac7fe  test    eax, eax
0x1800ac800  jnz     loc_1800AC8EF
0x1800ac806  call    cs:__imp_GetLastError
0x1800ac80c  mov     ecx, eax; unsigned int
0x1800ac80e  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800ac813  mov     ebx, eax
0x1800ac815  test    eax, eax
0x1800ac817  jns     loc_1800AC8EF
0x1800ac81d  cmp     dword ptr cs:xmmword_180169738, esi
0x1800ac823  mov     [rsp+1C0h+var_150], esi
0x1800ac827  mov     [rsp+1C0h+var_148], eax
0x1800ac82b  jz      loc_1800AC905
0x1800ac831  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ac83b  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ac842  jz      loc_1800AC905
0x1800ac848  mov     rax, cs:qword_180169748
0x1800ac84f  and     rax, rdx
0x1800ac852  cmp     cs:qword_180169748, rax
0x1800ac859  jnz     loc_1800AC905
0x1800ac85f  lea     rcx, [rbp+0C0h+var_130]; unsigned __int16 *
0x1800ac863  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ac868  lea     rcx, [rbp+0C0h+var_130]
0x1800ac86c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ac870  inc     rax
0x1800ac873  cmp     [rcx+rax*2], si
0x1800ac877  jnz     short loc_1800AC870
0x1800ac879  lea     ecx, [rax+rax]
0x1800ac87c  add     rcx, 2
0x1800ac880  lea     rax, [rbp+0C0h+var_130]
0x1800ac884  mov     [rsp+1C0h+var_160], rcx
0x1800ac889  lea     r9, [rsp+1C0h+var_148]
0x1800ac88e  lea     rcx, [rsp+1C0h+var_150]
0x1800ac893  mov     [rsp+1C0h+var_168], rax
0x1800ac898  lea     rdx, PLA_EVENT_ERROR
0x1800ac89f  mov     [rsp+1C0h+var_170], 1Fh
0x1800ac8a8  lea     rax, aPlaliimpersona; "PlaliImpersonateNetworkService"
0x1800ac8af  mov     [rsp+1C0h+var_178], rax
0x1800ac8b4  mov     eax, 4
0x1800ac8b9  mov     [rsp+1C0h+var_180], rax
0x1800ac8be  mov     [rsp+1C0h+var_188], rcx
0x1800ac8c3  lea     rcx, qword_180147320
0x1800ac8ca  mov     [rsp+1C0h+var_190], 1
0x1800ac8d3  mov     [rsp+1C0h+phToken], rcx
0x1800ac8d8  lea     r8d, [rax+1]
0x1800ac8dc  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800ac8e3  mov     qword ptr [rsp+1C0h+dwLogonProvider], rax
0x1800ac8e8  call    EventingWriteEvent
0x1800ac8ed  jmp     short loc_1800AC905
0x1800ac8ef  mov     rcx, [rbp+0C0h+hToken]; hToken
0x1800ac8f3  call    cs:__imp_ImpersonateLoggedOnUser
0x1800ac8f9  test    eax, eax
0x1800ac8fb  jz      short loc_1800AC931
0x1800ac8fd  mov     ebx, esi
0x1800ac8ff  mov     dword ptr [rdi], 1
0x1800ac905  mov     rcx, [rbp+0C0h+hToken]; hObject
0x1800ac909  test    rcx, rcx
0x1800ac90c  jz      short loc_1800AC914
0x1800ac90e  call    cs:__imp_CloseHandle
0x1800ac914  mov     eax, ebx
0x1800ac916  mov     rcx, [rbp+0C0h+var_30]
0x1800ac91d  xor     rcx, rsp; StackCookie
0x1800ac920  call    __security_check_cookie
0x1800ac925  add     rsp, 1A8h
0x1800ac92c  pop     rdi
0x1800ac92d  pop     rsi
0x1800ac92e  pop     rbx
0x1800ac92f  pop     rbp
0x1800ac930  retn
0x1800ac931  call    cs:__imp_GetLastError
0x1800ac937  mov     ecx, eax; unsigned int
0x1800ac939  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800ac93e  mov     ebx, eax
0x1800ac940  test    eax, eax
0x1800ac942  jns     short loc_1800AC8FF
0x1800ac944  cmp     dword ptr cs:xmmword_180169738, esi
0x1800ac94a  mov     [rsp+1C0h+var_148], esi
0x1800ac94e  mov     [rsp+1C0h+var_150], eax
0x1800ac952  jz      short loc_1800AC905
0x1800ac954  mov     rdx, 4000000000000800h; unsigned __int64
0x1800ac95e  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800ac965  jz      short loc_1800AC905
0x1800ac967  mov     rax, cs:qword_180169748
0x1800ac96e  and     rax, rdx
0x1800ac971  cmp     cs:qword_180169748, rax
0x1800ac978  jnz     short loc_1800AC905
0x1800ac97a  lea     rcx, [rbp+0C0h+var_B0]; unsigned __int16 *
0x1800ac97e  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800ac983  lea     rcx, [rbp+0C0h+var_B0]
0x1800ac987  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ac98b  inc     rax
0x1800ac98e  cmp     [rcx+rax*2], si
0x1800ac992  jnz     short loc_1800AC98B
0x1800ac994  lea     ecx, [rax+rax]
0x1800ac997  add     rcx, 2
0x1800ac99b  lea     rax, [rbp+0C0h+var_B0]
0x1800ac99f  mov     [rsp+1C0h+var_160], rcx
0x1800ac9a4  lea     r9, [rsp+1C0h+var_150]
0x1800ac9a9  lea     rcx, [rsp+1C0h+var_148]
0x1800ac9ae  jmp     loc_1800AC893
```
