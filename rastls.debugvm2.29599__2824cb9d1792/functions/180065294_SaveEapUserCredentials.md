# SaveEapUserCredentials

- ea: `0x180065294`
- end: `0x180065644`
- name: `SaveEapUserCredentials`
- size: `944`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180064f60`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18001c680`
- `0x180064404`
- `0x1800646bc`
- `0x180064bb0`
- `0x180064cb4`
- `0x180064e18`
- `0x180065294`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180065441`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18006548b`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180065441`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18006548b`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x1800652ed`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180065313`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x1800652ed`
- `api-ms-win-crt-private-l1-1-0!strchr` at `0x180065313`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800654d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800655bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800654d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800655bc`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180065587`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180065587`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180065515`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006551e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180065515`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006551e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180065552`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180065552`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800654cc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800654cc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800653de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006541d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006545f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006549d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800653de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006541d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006545f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18006549d`

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
0x180065294  mov     [rsp+arg_8], rbx
0x180065299  mov     [rsp+arg_0], ecx
0x18006529d  push    rbp
0x18006529e  push    rsi
0x18006529f  push    rdi
0x1800652a0  push    r13
0x1800652a2  push    r15
0x1800652a4  sub     rsp, 40h
0x1800652a8  xor     esi, esi
0x1800652aa  lea     r13, WPP_GLOBAL_Control
0x1800652b1  mov     r15, r9
0x1800652b4  mov     rbx, r8
0x1800652b7  mov     rbp, rdx
0x1800652ba  test    r8, r8
0x1800652bd  jz      loc_180065600
0x1800652c3  test    r9, r9
0x1800652c6  jz      loc_180065600
0x1800652cc  cmp     [rsp+68h+cbMultiByte], esi
0x1800652d3  jz      loc_180065600
0x1800652d9  xor     edi, edi
0x1800652db  test    rdx, rdx
0x1800652de  jz      short loc_1800652E5
0x1800652e0  cmp     [rdx], sil
0x1800652e3  jnz     short loc_180065346
0x1800652e5  mov     edx, 40h ; '@'; Val
0x1800652ea  mov     rcx, rbx; Str
0x1800652ed  call    cs:__imp_strchr
0x1800652f3  test    rax, rax
0x1800652f6  jz      short loc_18006530B
0x1800652f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800652ff  cmp     rcx, r13
0x180065302  jz      short loc_180065346
0x180065304  mov     edx, 3Ah ; ':'
0x180065309  jmp     short loc_180065333
0x18006530b  mov     edx, 5Ch ; '\'; Val
0x180065310  mov     rcx, rbx; Str
0x180065313  call    cs:__imp_strchr
0x180065319  test    rax, rax
0x18006531c  jz      loc_1800655DA
0x180065322  mov     rcx, cs:WPP_GLOBAL_Control
0x180065329  cmp     rcx, r13
0x18006532c  jz      short loc_180065346
0x18006532e  mov     edx, 3Bh ; ';'
0x180065333  mov     rcx, [rcx+10h]
0x180065337  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18006533e  mov     r9, rbx
0x180065341  call    WPP_SF_s
0x180065346  call    ?SavedCredsFeatureEnabledForUsernamePassword@@YAHXZ; SavedCredsFeatureEnabledForUsernamePassword(void)
0x18006534b  test    eax, eax
0x18006534d  jnz     short loc_180065377
0x18006534f  mov     rcx, cs:WPP_GLOBAL_Control
0x180065356  cmp     rcx, r13
0x180065359  jz      loc_180065605
0x18006535f  lea     edx, [rax+3Dh]
0x180065362  mov     rcx, [rcx+10h]
0x180065366  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x18006536d  call    WPP_SF_
0x180065372  jmp     loc_180065605
0x180065377  lea     rcx, [rsp+68h+arg_0]; bool *
0x18006537c  mov     byte ptr [rsp+68h+arg_0], sil
0x180065381  call    ?CallerHasWlanSvcMembership@@YAKPEA_N@Z; CallerHasWlanSvcMembership(bool *)
0x180065386  mov     edi, eax
0x180065388  test    eax, eax
0x18006538a  jz      short loc_1800653A3
0x18006538c  mov     rcx, cs:WPP_GLOBAL_Control
0x180065393  cmp     rcx, r13
0x180065396  jz      loc_180065605
0x18006539c  mov     edx, 3Eh ; '>'
0x1800653a1  jmp     short loc_180065362
0x1800653a3  cmp     byte ptr [rsp+68h+arg_0], sil
0x1800653a8  jnz     short loc_1800653C1
0x1800653aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800653b1  cmp     rcx, r13
0x1800653b4  jz      loc_180065605
0x1800653ba  mov     edx, 3Fh ; '?'
0x1800653bf  jmp     short loc_180065362
0x1800653c1  mov     rcx, [rsp+68h+arg_30]
0x1800653c9  call    CheckIfWirelessInterface
0x1800653ce  test    eax, eax
0x1800653d0  jz      loc_180065605
0x1800653d6  mov     edx, 28h ; '('; uBytes
0x1800653db  lea     ecx, [rdx+18h]; uFlags
0x1800653de  call    cs:__imp_LocalAlloc
0x1800653e4  mov     rsi, rax
0x1800653e7  test    rax, rax
0x1800653ea  jnz     short loc_1800653F6
0x1800653ec  mov     edi, 8
0x1800653f1  jmp     loc_180065605
0x1800653f6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800653fa  mov     [rsi+20h], rax
0x1800653fe  test    rbp, rbp
0x180065401  jz      short loc_18006544B
0x180065403  cmp     byte ptr [rbp+0], 0
0x180065407  jz      short loc_18006544B
0x180065409  mov     rdx, rax
0x18006540c  inc     rdx
0x18006540f  cmp     byte ptr [rdx+rbp], 0
0x180065413  jnz     short loc_18006540C
0x180065415  inc     rdx; uBytes
0x180065418  mov     ecx, 40h ; '@'; uFlags
0x18006541d  call    cs:__imp_LocalAlloc
0x180065423  mov     [rsi], rax
0x180065426  test    rax, rax
0x180065429  jz      short loc_1800653EC
0x18006542b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18006542f  inc     rdx
0x180065432  cmp     byte ptr [rdx+rbp], 0
0x180065436  jnz     short loc_18006542F
0x180065438  inc     rdx; SizeInBytes
0x18006543b  mov     r8, rbp; Source
0x18006543e  mov     rcx, rax; Destination
0x180065441  call    cs:__imp_strcpy_s
0x180065447  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006544b  mov     rdx, rax
0x18006544e  inc     rdx
0x180065451  cmp     byte ptr [rbx+rdx], 0
0x180065455  jnz     short loc_18006544E
0x180065457  inc     rdx; uBytes
0x18006545a  mov     ecx, 40h ; '@'; uFlags
0x18006545f  call    cs:__imp_LocalAlloc
0x180065465  mov     [rsi+8], rax
0x180065469  test    rax, rax
0x18006546c  jz      loc_1800653EC
0x180065472  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180065476  mov     rdx, rbp
0x180065479  inc     rdx
0x18006547c  cmp     byte ptr [rbx+rdx], 0
0x180065480  jnz     short loc_180065479
0x180065482  inc     rdx; SizeInBytes
0x180065485  mov     r8, rbx; Source
0x180065488  mov     rcx, rax; Destination
0x18006548b  call    cs:__imp_strcpy_s
0x180065491  mov     ebx, 40h ; '@'
0x180065496  mov     edx, 202h; uBytes
0x18006549b  mov     ecx, ebx; uFlags
0x18006549d  call    cs:__imp_LocalAlloc
0x1800654a3  mov     [rsi+10h], rax
0x1800654a7  test    rax, rax
0x1800654aa  jz      loc_1800653EC
0x1800654b0  mov     r9d, [rsp+68h+cbMultiByte]; cbMultiByte
0x1800654b8  mov     r8, r15; lpMultiByteStr
0x1800654bb  mov     [rsp+68h+cchWideChar], 101h; cchWideChar
0x1800654c3  xor     edx, edx; dwFlags
0x1800654c5  xor     ecx, ecx; CodePage
0x1800654c7  mov     [rsp+68h+lpWideCharStr], rax; lpWideCharStr
0x1800654cc  call    cs:__imp_MultiByteToWideChar
0x1800654d2  test    eax, eax
0x1800654d4  jnz     short loc_180065508
0x1800654d6  call    cs:__imp_GetLastError
0x1800654dc  mov     edi, eax
0x1800654de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800654e5  cmp     rcx, r13
0x1800654e8  jz      loc_180065605
0x1800654ee  mov     edx, ebx
0x1800654f0  mov     rcx, [rcx+10h]
0x1800654f4  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x1800654fb  mov     r9d, eax
0x1800654fe  call    WPP_SF_d
0x180065503  jmp     loc_180065605
0x180065508  add     eax, eax
0x18006550a  mov     [rsi+18h], eax
0x18006550d  mov     [rsp+68h+TargetHandle], rbp
0x180065515  call    cs:__imp_GetCurrentProcess
0x18006551b  mov     rbx, rax
0x18006551e  call    cs:__imp_GetCurrentProcess
0x180065524  mov     rdx, [rsp+68h+hSourceHandle]; hSourceHandle
0x18006552c  lea     r9, [rsp+68h+TargetHandle]; lpTargetHandle
0x180065534  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18006553c  mov     rcx, rax; hSourceProcessHandle
0x18006553f  mov     [rsp+68h+cchWideChar], 1; bInheritHandle
0x180065547  mov     r8, rbx; hTargetProcessHandle
0x18006554a  mov     dword ptr [rsp+68h+lpWideCharStr], 0; dwDesiredAccess
0x180065552  call    cs:__imp_DuplicateHandle
0x180065558  test    eax, eax
0x18006555a  jz      short loc_1800655BC
0x18006555c  mov     rax, [rsp+68h+TargetHandle]
0x180065564  lea     r8, ?SaveCredsThread@@YAKPEAX@Z; lpStartAddress
0x18006556b  mov     qword ptr [rsp+68h+cchWideChar], 0; lpThreadId
0x180065574  mov     r9, rsi; lpParameter
0x180065577  xor     edx, edx; dwStackSize
0x180065579  mov     [rsi+20h], rax
0x18006557d  xor     ecx, ecx; lpThreadAttributes
0x18006557f  mov     dword ptr [rsp+68h+lpWideCharStr], 0; dwCreationFlags
0x180065587  call    cs:__imp_CreateThread
0x18006558d  test    rax, rax
0x180065590  jnz     short loc_1800655B0
0x180065592  call    cs:__imp_GetLastError
0x180065598  mov     edi, eax
0x18006559a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800655a1  cmp     rcx, r13
0x1800655a4  jz      short loc_180065605
0x1800655a6  mov     edx, 42h ; 'B'
0x1800655ab  jmp     loc_1800654F0
0x1800655b0  xor     esi, esi
0x1800655b2  mov     rdx, rax; void *
0x1800655b5  call    ?SetThreadHandle@CWorkerThreadState@@QEAAXPEAX@Z; CWorkerThreadState::SetThreadHandle(void *)
0x1800655ba  jmp     short loc_180065605
0x1800655bc  call    cs:__imp_GetLastError
0x1800655c2  mov     edi, eax
0x1800655c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800655cb  cmp     rcx, r13
0x1800655ce  jz      short loc_180065605
0x1800655d0  mov     edx, 41h ; 'A'
0x1800655d5  jmp     loc_1800654F0
0x1800655da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800655e1  cmp     rcx, r13
0x1800655e4  jz      short loc_180065605
0x1800655e6  mov     rcx, [rcx+10h]
0x1800655ea  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x1800655f1  mov     edx, 3Ch ; '<'
0x1800655f6  mov     r9, rbx
0x1800655f9  call    WPP_SF_s
0x1800655fe  jmp     short loc_180065605
0x180065600  mov     edi, 57h ; 'W'
0x180065605  mov     rcx, rsi; hMem
0x180065608  call    ?FreeEapCredStructure@@YAXPEAU_EapCredThreadArgs@@@Z; FreeEapCredStructure(_EapCredThreadArgs *)
0x18006560d  mov     rcx, cs:WPP_GLOBAL_Control
0x180065614  cmp     rcx, r13
0x180065617  jz      short loc_180065631
0x180065619  mov     rcx, [rcx+10h]
0x18006561d  lea     r8, WPP_2161b76e39b5354c88ebe7c7297da229_Traceguids
0x180065624  mov     edx, 43h ; 'C'
0x180065629  mov     r9d, edi
0x18006562c  call    WPP_SF_d
0x180065631  mov     rbx, [rsp+68h+arg_8]
0x180065636  mov     eax, edi
0x180065638  add     rsp, 40h
0x18006563c  pop     r15
0x18006563e  pop     r13
0x180065640  pop     rdi
0x180065641  pop     rsi
0x180065642  pop     rbp
0x180065643  retn
```
