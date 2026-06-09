# SaveEapUserCredentials

- ea: `0x180068e40`
- end: `0x180069251`
- name: `SaveEapUserCredentials`
- size: `1041`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180068b08`

## callees

- `0x180005010`
- `0x180007d00`
- `0x18001e0c0`
- `0x180067eac`
- `0x1800681a8`
- `0x18006871c`
- `0x180068830`
- `0x1800689bc`
- `0x180068e40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180069005`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18006905b`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180069005`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18006905b`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180068e99`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180068ec5`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180068e99`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180068ec5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800690b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069192`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800691c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800690b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180069192`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800691c2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180069181`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180069181`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800690fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006910c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800690fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006910c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180069146`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180069146`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800690a8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800690a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068f96`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068fdb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180069029`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180069073`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068f96`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180068fdb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180069029`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180069073`

## pseudocode

```c
__int64 __fastcall SaveEapUserCredentials(
        int a1,
        const char *a2,
        const char *a3,
        const CHAR *a4,
        int cbMultiByte,
        HANDLE hSourceHandle,
        __int64 a7)
{
  _QWORD *v7; // rsi
  unsigned int HasWlanSvcMembership; // edi
  struct _EAPTLS_CONTROL_BLOCK *v12; // rcx
  __int64 v13; // rdx
  struct _EAPTLS_CONTROL_BLOCK *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx
  char *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  char *v20; // rax
  __int64 v21; // rdx
  WCHAR *lpWideCharStr; // rax
  int v23; // eax
  DWORD LastError; // eax
  struct _EAPTLS_CONTROL_BLOCK *v25; // rcx
  __int64 v26; // rdx
  HANDLE CurrentProcess; // rbx
  HANDLE v28; // rax
  HANDLE Thread; // rax
  CWorkerThreadState *v30; // rcx
  int v32; // [rsp+70h] [rbp+8h] BYREF
  HANDLE TargetHandle; // [rsp+80h] [rbp+18h] BYREF

  v32 = a1;
  v7 = 0;
  if ( !a3 || !a4 || !cbMultiByte )
  {
    HasWlanSvcMembership = 87;
    goto LABEL_54;
  }
  HasWlanSvcMembership = 0;
  if ( !a2 || !*a2 )
  {
    if ( strchr(a3, 64) )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_13;
      v13 = 58;
      goto LABEL_12;
    }
    if ( !strchr(a3, 92) )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, a3);
      goto LABEL_54;
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v13 = 59;
LABEL_12:
      WPP_SF_s(*((_QWORD *)v12 + 2), v13, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, a3);
    }
  }
LABEL_13:
  if ( !(unsigned int)SavedCredsFeatureEnabledForUsernamePassword() )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_54;
    v15 = 61;
    goto LABEL_16;
  }
  LOBYTE(v32) = 0;
  HasWlanSvcMembership = CallerHasWlanSvcMembership((bool *)&v32);
  if ( HasWlanSvcMembership )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v15 = 62;
LABEL_16:
      WPP_SF_(*((_QWORD *)v14 + 2), v15, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids);
      goto LABEL_54;
    }
    goto LABEL_54;
  }
  if ( (_BYTE)v32 )
  {
    if ( !(unsigned int)CheckIfWirelessInterface(a7) )
      goto LABEL_54;
    v7 = LocalAlloc(0x40u, 0x28u);
    if ( !v7 )
      goto LABEL_25;
    v7[4] = -1;
    if ( a2 && *a2 )
    {
      v16 = -1;
      do
        ++v16;
      while ( a2[v16] );
      v17 = (char *)LocalAlloc(0x40u, v16 + 1);
      *v7 = v17;
      if ( !v17 )
        goto LABEL_25;
      v18 = -1;
      do
        ++v18;
      while ( a2[v18] );
      strcpy_s(v17, v18 + 1, a2);
    }
    v19 = -1;
    do
      ++v19;
    while ( a3[v19] );
    v20 = (char *)LocalAlloc(0x40u, v19 + 1);
    v7[1] = v20;
    if ( v20 )
    {
      v21 = -1;
      do
        ++v21;
      while ( a3[v21] );
      strcpy_s(v20, v21 + 1, a3);
      lpWideCharStr = (WCHAR *)LocalAlloc(0x40u, 0x202u);
      v7[2] = lpWideCharStr;
      if ( lpWideCharStr )
      {
        v23 = MultiByteToWideChar(0, 0, a4, cbMultiByte, lpWideCharStr, 257);
        if ( v23 )
        {
          *((_DWORD *)v7 + 6) = 2 * v23;
          TargetHandle = (HANDLE)-1LL;
          CurrentProcess = GetCurrentProcess();
          v28 = GetCurrentProcess();
          if ( DuplicateHandle(v28, hSourceHandle, CurrentProcess, &TargetHandle, 0, 1, 2u) )
          {
            v7[4] = TargetHandle;
            Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)SaveCredsThread, v7, 0, 0);
            if ( Thread )
            {
              v7 = 0;
              CWorkerThreadState::SetThreadHandle(v30, Thread);
              goto LABEL_54;
            }
            LastError = GetLastError();
            HasWlanSvcMembership = LastError;
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              goto LABEL_54;
            v26 = 66;
          }
          else
          {
            LastError = GetLastError();
            HasWlanSvcMembership = LastError;
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              goto LABEL_54;
            v26 = 65;
          }
        }
        else
        {
          LastError = GetLastError();
          HasWlanSvcMembership = LastError;
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_54;
          v26 = 64;
        }
        WPP_SF_d(*((_QWORD *)v25 + 2), v26, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids, LastError);
        goto LABEL_54;
      }
    }
LABEL_25:
    HasWlanSvcMembership = 8;
    goto LABEL_54;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v15 = 63;
    goto LABEL_16;
  }
LABEL_54:
  FreeEapCredStructure(v7);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      67,
      WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids,
      HasWlanSvcMembership);
  return HasWlanSvcMembership;
}

```

## disassembly

```asm
0x180068e40  mov     [rsp+arg_8], rbx
0x180068e45  mov     [rsp+arg_0], ecx
0x180068e49  push    rbp
0x180068e4a  push    rsi
0x180068e4b  push    rdi
0x180068e4c  push    r13
0x180068e4e  push    r15
0x180068e50  sub     rsp, 40h
0x180068e54  xor     esi, esi
0x180068e56  lea     r13, WPP_GLOBAL_Control
0x180068e5d  mov     r15, r9
0x180068e60  mov     rbx, r8
0x180068e63  mov     rbp, rdx
0x180068e66  test    r8, r8
0x180068e69  jz      loc_18006920C
0x180068e6f  test    r9, r9
0x180068e72  jz      loc_18006920C
0x180068e78  cmp     [rsp+68h+cbMultiByte], esi
0x180068e7f  jz      loc_18006920C
0x180068e85  xor     edi, edi
0x180068e87  test    rdx, rdx
0x180068e8a  jz      short loc_180068E91
0x180068e8c  cmp     [rdx], sil
0x180068e8f  jnz     short loc_180068EFE
0x180068e91  mov     edx, 40h ; '@'; Val
0x180068e96  mov     rcx, rbx; Str
0x180068e99  call    cs:__imp_strchr
0x180068ea0  nop     dword ptr [rax+rax+00h]
0x180068ea5  test    rax, rax
0x180068ea8  jz      short loc_180068EBD
0x180068eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180068eb1  cmp     rcx, r13
0x180068eb4  jz      short loc_180068EFE
0x180068eb6  mov     edx, 3Ah ; ':'
0x180068ebb  jmp     short loc_180068EEB
0x180068ebd  mov     edx, 5Ch ; '\'; Val
0x180068ec2  mov     rcx, rbx; Str
0x180068ec5  call    cs:__imp_strchr
0x180068ecc  nop     dword ptr [rax+rax+00h]
0x180068ed1  test    rax, rax
0x180068ed4  jz      loc_1800691E6
0x180068eda  mov     rcx, cs:WPP_GLOBAL_Control
0x180068ee1  cmp     rcx, r13
0x180068ee4  jz      short loc_180068EFE
0x180068ee6  mov     edx, 3Bh ; ';'
0x180068eeb  mov     rcx, [rcx+10h]
0x180068eef  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180068ef6  mov     r9, rbx
0x180068ef9  call    WPP_SF_s
0x180068efe  call    ?SavedCredsFeatureEnabledForUsernamePassword@@YAHXZ; SavedCredsFeatureEnabledForUsernamePassword(void)
0x180068f03  test    eax, eax
0x180068f05  jnz     short loc_180068F2F
0x180068f07  mov     rcx, cs:WPP_GLOBAL_Control
0x180068f0e  cmp     rcx, r13
0x180068f11  jz      loc_180069211
0x180068f17  lea     edx, [rax+3Dh]
0x180068f1a  mov     rcx, [rcx+10h]
0x180068f1e  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180068f25  call    WPP_SF_
0x180068f2a  jmp     loc_180069211
0x180068f2f  lea     rcx, [rsp+68h+arg_0]; bool *
0x180068f34  mov     byte ptr [rsp+68h+arg_0], sil
0x180068f39  call    ?CallerHasWlanSvcMembership@@YAKPEA_N@Z; CallerHasWlanSvcMembership(bool *)
0x180068f3e  mov     edi, eax
0x180068f40  test    eax, eax
0x180068f42  jz      short loc_180068F5B
0x180068f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180068f4b  cmp     rcx, r13
0x180068f4e  jz      loc_180069211
0x180068f54  mov     edx, 3Eh ; '>'
0x180068f59  jmp     short loc_180068F1A
0x180068f5b  cmp     byte ptr [rsp+68h+arg_0], sil
0x180068f60  jnz     short loc_180068F79
0x180068f62  mov     rcx, cs:WPP_GLOBAL_Control
0x180068f69  cmp     rcx, r13
0x180068f6c  jz      loc_180069211
0x180068f72  mov     edx, 3Fh ; '?'
0x180068f77  jmp     short loc_180068F1A
0x180068f79  mov     rcx, [rsp+68h+arg_30]
0x180068f81  call    CheckIfWirelessInterface
0x180068f86  test    eax, eax
0x180068f88  jz      loc_180069211
0x180068f8e  mov     edx, 28h ; '('; uBytes
0x180068f93  lea     ecx, [rdx+18h]; uFlags
0x180068f96  call    cs:__imp_LocalAlloc
0x180068f9d  nop     dword ptr [rax+rax+00h]
0x180068fa2  mov     rsi, rax
0x180068fa5  test    rax, rax
0x180068fa8  jnz     short loc_180068FB4
0x180068faa  mov     edi, 8
0x180068faf  jmp     loc_180069211
0x180068fb4  or      rax, 0FFFFFFFFFFFFFFFFh
0x180068fb8  mov     [rsi+20h], rax
0x180068fbc  test    rbp, rbp
0x180068fbf  jz      short loc_180069015
0x180068fc1  cmp     byte ptr [rbp+0], 0
0x180068fc5  jz      short loc_180069015
0x180068fc7  mov     rdx, rax
0x180068fca  inc     rdx
0x180068fcd  cmp     byte ptr [rdx+rbp], 0
0x180068fd1  jnz     short loc_180068FCA
0x180068fd3  inc     rdx; uBytes
0x180068fd6  mov     ecx, 40h ; '@'; uFlags
0x180068fdb  call    cs:__imp_LocalAlloc
0x180068fe2  nop     dword ptr [rax+rax+00h]
0x180068fe7  mov     [rsi], rax
0x180068fea  test    rax, rax
0x180068fed  jz      short loc_180068FAA
0x180068fef  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180068ff3  inc     rdx
0x180068ff6  cmp     byte ptr [rdx+rbp], 0
0x180068ffa  jnz     short loc_180068FF3
0x180068ffc  inc     rdx; SizeInBytes
0x180068fff  mov     r8, rbp; Source
0x180069002  mov     rcx, rax; Destination
0x180069005  call    cs:__imp_strcpy_s
0x18006900c  nop     dword ptr [rax+rax+00h]
0x180069011  or      rax, 0FFFFFFFFFFFFFFFFh
0x180069015  mov     rdx, rax
0x180069018  inc     rdx
0x18006901b  cmp     byte ptr [rbx+rdx], 0
0x18006901f  jnz     short loc_180069018
0x180069021  inc     rdx; uBytes
0x180069024  mov     ecx, 40h ; '@'; uFlags
0x180069029  call    cs:__imp_LocalAlloc
0x180069030  nop     dword ptr [rax+rax+00h]
0x180069035  mov     [rsi+8], rax
0x180069039  test    rax, rax
0x18006903c  jz      loc_180068FAA
0x180069042  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180069046  mov     rdx, rbp
0x180069049  inc     rdx
0x18006904c  cmp     byte ptr [rbx+rdx], 0
0x180069050  jnz     short loc_180069049
0x180069052  inc     rdx; SizeInBytes
0x180069055  mov     r8, rbx; Source
0x180069058  mov     rcx, rax; Destination
0x18006905b  call    cs:__imp_strcpy_s
0x180069062  nop     dword ptr [rax+rax+00h]
0x180069067  mov     ebx, 40h ; '@'
0x18006906c  mov     edx, 202h; uBytes
0x180069071  mov     ecx, ebx; uFlags
0x180069073  call    cs:__imp_LocalAlloc
0x18006907a  nop     dword ptr [rax+rax+00h]
0x18006907f  mov     [rsi+10h], rax
0x180069083  test    rax, rax
0x180069086  jz      loc_180068FAA
0x18006908c  mov     r9d, [rsp+68h+cbMultiByte]; cbMultiByte
0x180069094  mov     r8, r15; lpMultiByteStr
0x180069097  mov     [rsp+68h+cchWideChar], 101h; cchWideChar
0x18006909f  xor     edx, edx; dwFlags
0x1800690a1  xor     ecx, ecx; CodePage
0x1800690a3  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x1800690a8  call    cs:__imp_MultiByteToWideChar
0x1800690af  nop     dword ptr [rax+rax+00h]
0x1800690b4  test    eax, eax
0x1800690b6  jnz     short loc_1800690F0
0x1800690b8  call    cs:__imp_GetLastError
0x1800690bf  nop     dword ptr [rax+rax+00h]
0x1800690c4  mov     edi, eax
0x1800690c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800690cd  cmp     rcx, r13
0x1800690d0  jz      loc_180069211
0x1800690d6  mov     edx, ebx
0x1800690d8  mov     rcx, [rcx+10h]
0x1800690dc  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x1800690e3  mov     r9d, eax
0x1800690e6  call    WPP_SF_d
0x1800690eb  jmp     loc_180069211
0x1800690f0  add     eax, eax
0x1800690f2  mov     [rsi+18h], eax
0x1800690f5  mov     [rsp+68h+TargetHandle], rbp
0x1800690fd  call    cs:__imp_GetCurrentProcess
0x180069104  nop     dword ptr [rax+rax+00h]
0x180069109  mov     rbx, rax
0x18006910c  call    cs:__imp_GetCurrentProcess
0x180069113  nop     dword ptr [rax+rax+00h]
0x180069118  mov     rdx, [rsp+68h+hSourceHandle]; hSourceHandle
0x180069120  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x180069128  mov     [rsp+68h+dwOptions], 2; dwOptions
0x180069130  mov     rcx, rax; hSourceProcessHandle
0x180069133  mov     [rsp+68h+cchWideChar], 1; bInheritHandle
0x18006913b  mov     r8, rbx; hTargetProcessHandle
0x18006913e  mov     dword ptr [rsp+68h+lpWideCharStr], 0; dwDesiredAccess
0x180069146  call    cs:__imp_DuplicateHandle
0x18006914d  nop     dword ptr [rax+rax+00h]
0x180069152  test    eax, eax
0x180069154  jz      short loc_1800691C2
0x180069156  mov     rax, [rsp+68h+TargetHandle]
0x18006915e  lea     r8, ?SaveCredsThread@@YAKPEAX@Z; lpStartAddress
0x180069165  mov     qword ptr [rsp+68h+cchWideChar], 0; lpThreadId
0x18006916e  mov     r9, rsi; lpParameter
0x180069171  xor     edx, edx; dwStackSize
0x180069173  mov     [rsi+20h], rax
0x180069177  xor     ecx, ecx; lpThreadAttributes
0x180069179  mov     dword ptr [rsp+68h+lpWideCharStr], 0; dwCreationFlags
0x180069181  call    cs:__imp_CreateThread
0x180069188  nop     dword ptr [rax+rax+00h]
0x18006918d  test    rax, rax
0x180069190  jnz     short loc_1800691B6
0x180069192  call    cs:__imp_GetLastError
0x180069199  nop     dword ptr [rax+rax+00h]
0x18006919e  mov     edi, eax
0x1800691a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800691a7  cmp     rcx, r13
0x1800691aa  jz      short loc_180069211
0x1800691ac  mov     edx, 42h ; 'B'
0x1800691b1  jmp     loc_1800690D8
0x1800691b6  xor     esi, esi
0x1800691b8  mov     rdx, rax; void *
0x1800691bb  call    ?SetThreadHandle@CWorkerThreadState@@QEAAXPEAX@Z; CWorkerThreadState::SetThreadHandle(void *)
0x1800691c0  jmp     short loc_180069211
0x1800691c2  call    cs:__imp_GetLastError
0x1800691c9  nop     dword ptr [rax+rax+00h]
0x1800691ce  mov     edi, eax
0x1800691d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800691d7  cmp     rcx, r13
0x1800691da  jz      short loc_180069211
0x1800691dc  mov     edx, 41h ; 'A'
0x1800691e1  jmp     loc_1800690D8
0x1800691e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800691ed  cmp     rcx, r13
0x1800691f0  jz      short loc_180069211
0x1800691f2  mov     rcx, [rcx+10h]
0x1800691f6  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x1800691fd  mov     edx, 3Ch ; '<'
0x180069202  mov     r9, rbx
0x180069205  call    WPP_SF_s
0x18006920a  jmp     short loc_180069211
0x18006920c  mov     edi, 57h ; 'W'
0x180069211  mov     rcx, rsi; hMem
0x180069214  call    ?FreeEapCredStructure@@YAXPEAU_EapCredThreadArgs@@@Z; FreeEapCredStructure(_EapCredThreadArgs *)
0x180069219  mov     rcx, cs:WPP_GLOBAL_Control
0x180069220  cmp     rcx, r13
0x180069223  jz      short loc_18006923D
0x180069225  mov     rcx, [rcx+10h]
0x180069229  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180069230  mov     edx, 43h ; 'C'
0x180069235  mov     r9d, edi
0x180069238  call    WPP_SF_d
0x18006923d  mov     rbx, [rsp+68h+arg_8]
0x180069242  mov     eax, edi
0x180069244  add     rsp, 40h
0x180069248  pop     r15
0x18006924a  pop     r13
0x18006924c  pop     rdi
0x18006924d  pop     rsi
0x18006924e  pop     rbp
0x18006924f  retn
```
