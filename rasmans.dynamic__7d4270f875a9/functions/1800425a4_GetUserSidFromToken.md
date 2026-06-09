# GetUserSidFromToken

- ea: `0x1800425a4`
- end: `0x1800429a8`
- name: `GetUserSidFromToken`
- size: `1028`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014734`
- `0x180016500`
- `0x18004245c`

## callees

- `0x180005bfc`
- `0x180005cf8`
- `0x1800425a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042625`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042625`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180042641`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180042641`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004266e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004266e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180042683`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180042683`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042952`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042952`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042697`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042748`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800427aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800428c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042697`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042748`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800427aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042876`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800428c2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800428b2`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800428b2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180042738`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180042807`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180042738`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180042807`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042796`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042862`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042796`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042862`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042907`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042927`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042907`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042927`

## pseudocode

```c
__int64 __fastcall GetUserSidFromToken(void *a1, HLOCAL *a2)
{
  int v3; // r14d
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  DWORD v6; // ebx
  HANDLE CurrentProcess; // rax
  struct _LIST_ENTRY *v8; // rcx
  __int64 v9; // rdx
  PSID *v10; // rdi
  DWORD v11; // eax
  struct _LIST_ENTRY *v12; // rcx
  __int64 v13; // rdx
  HLOCAL v14; // rax
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+68h] [rbp+38h] BYREF

  TokenHandle = a1;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 657, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, a1);
    a1 = TokenHandle;
  }
  TokenInformationLength = 0;
  if ( a1 != (void *)-1LL )
  {
    v3 = 0;
    if ( a1 )
    {
LABEL_22:
      if ( !GetTokenInformation(a1, TokenUser, 0, 0, &TokenInformationLength) )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError != 122 )
        {
          if ( !LastError )
            goto LABEL_55;
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
          {
            v9 = 660;
            goto LABEL_15;
          }
          goto LABEL_56;
        }
      }
      v10 = (PSID *)LocalAlloc(0, TokenInformationLength);
      if ( !v10 )
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( !LastError )
          goto LABEL_55;
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v9 = 661;
          goto LABEL_15;
        }
        goto LABEL_56;
      }
      if ( GetTokenInformation(TokenHandle, TokenUser, v10, TokenInformationLength, &TokenInformationLength) )
      {
        v14 = LocalAlloc(0, 0x44u);
        *a2 = v14;
        if ( v14 )
        {
          v6 = 0;
          if ( CopySid(0x44u, v14, *v10) )
            goto LABEL_54;
          v11 = GetLastError();
          v6 = v11;
          if ( !v11 )
            goto LABEL_54;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_54;
          }
          v13 = 664;
        }
        else
        {
          v11 = GetLastError();
          v6 = v11;
          if ( !v11 )
            goto LABEL_54;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_54;
          }
          v13 = 663;
        }
      }
      else
      {
        v11 = GetLastError();
        v6 = v11;
        if ( !v11 )
          goto LABEL_54;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_54;
        }
        v13 = 662;
      }
      WPP_SF_d(v12[1].Flink, v13, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v11);
LABEL_54:
      LocalFree(v10);
      goto LABEL_55;
    }
  }
  v3 = 1;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
LABEL_21:
    a1 = TokenHandle;
    goto LABEL_22;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( !LastError )
      {
LABEL_55:
        v8 = WPP_GLOBAL_Control;
        goto LABEL_56;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v9 = 658;
LABEL_15:
        WPP_SF_d(v8[1].Flink, v9, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, LastError);
        goto LABEL_55;
      }
      goto LABEL_56;
    }
    goto LABEL_21;
  }
  if ( !LastError )
    goto LABEL_55;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v9 = 659;
    goto LABEL_15;
  }
LABEL_56:
  if ( *a2 && v6 )
  {
    LocalFree(*a2);
    *a2 = 0;
    v8 = WPP_GLOBAL_Control;
  }
  if ( v3 && TokenHandle )
  {
    CloseHandle(TokenHandle);
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v8[1].Blink) & 0x2000) != 0
    && BYTE1(v8[1].Blink) >= 6u )
  {
    WPP_SF_d(v8[1].Flink, 665, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x1800425a4  mov     [rsp-28h+arg_10], rbx
0x1800425a9  mov     [rsp-28h+arg_18], rsi
0x1800425ae  mov     [rsp-28h+TokenHandle], rcx
0x1800425b3  push    rbp
0x1800425b4  push    rdi
0x1800425b5  push    r12
0x1800425b7  push    r13
0x1800425b9  push    r14
0x1800425bb  mov     rbp, rsp
0x1800425be  sub     rsp, 30h
0x1800425c2  mov     rsi, rdx
0x1800425c5  mov     rax, cs:WPP_GLOBAL_Control
0x1800425cc  lea     r13, WPP_GLOBAL_Control
0x1800425d3  mov     r12d, 2000h
0x1800425d9  cmp     rax, r13
0x1800425dc  jz      short loc_180042606
0x1800425de  test    [rax+1Ch], r12d
0x1800425e2  jz      short loc_180042606
0x1800425e4  cmp     byte ptr [rax+19h], 6
0x1800425e8  jb      short loc_180042606
0x1800425ea  mov     r9, rcx
0x1800425ed  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x1800425f4  mov     rcx, [rax+10h]
0x1800425f8  mov     edx, 291h
0x1800425fd  call    WPP_SF_q
0x180042602  mov     rcx, [rbp+TokenHandle]
0x180042606  mov     [rbp+TokenInformationLength], 0
0x18004260d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180042611  jz      short loc_18004261F
0x180042613  xor     r14d, r14d
0x180042616  test    rcx, rcx
0x180042619  jnz     loc_180042725
0x18004261f  mov     r14d, 1
0x180042625  call    cs:__imp_GetCurrentThread
0x18004262c  nop     dword ptr [rax+rax+00h]
0x180042631  lea     edi, [r14+7]
0x180042635  mov     r8d, r14d; OpenAsSelf
0x180042638  mov     rcx, rax; ThreadHandle
0x18004263b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18004263f  mov     edx, edi; DesiredAccess
0x180042641  call    cs:__imp_OpenThreadToken
0x180042648  nop     dword ptr [rax+rax+00h]
0x18004264d  test    eax, eax
0x18004264f  jnz     loc_180042721
0x180042655  call    cs:__imp_GetLastError
0x18004265c  nop     dword ptr [rax+rax+00h]
0x180042661  mov     ebx, eax
0x180042663  cmp     eax, 3F0h
0x180042668  jnz     loc_1800426EE
0x18004266e  call    cs:__imp_GetCurrentProcess
0x180042675  nop     dword ptr [rax+rax+00h]
0x18004267a  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18004267e  mov     edx, edi; DesiredAccess
0x180042680  mov     rcx, rax; ProcessHandle
0x180042683  call    cs:__imp_OpenProcessToken
0x18004268a  nop     dword ptr [rax+rax+00h]
0x18004268f  test    eax, eax
0x180042691  jnz     loc_180042721
0x180042697  call    cs:__imp_GetLastError
0x18004269e  nop     dword ptr [rax+rax+00h]
0x1800426a3  mov     ebx, eax
0x1800426a5  test    eax, eax
0x1800426a7  jz      loc_180042913
0x1800426ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800426b4  cmp     rcx, r13
0x1800426b7  jz      loc_18004291A
0x1800426bd  test    [rcx+1Ch], r12d
0x1800426c1  jz      loc_18004291A
0x1800426c7  cmp     byte ptr [rcx+19h], 2
0x1800426cb  jb      loc_18004291A
0x1800426d1  mov     edx, 292h
0x1800426d6  mov     rcx, [rcx+10h]
0x1800426da  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x1800426e1  mov     r9d, eax
0x1800426e4  call    WPP_SF_d
0x1800426e9  jmp     loc_180042913
0x1800426ee  test    eax, eax
0x1800426f0  jz      loc_180042913
0x1800426f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800426fd  cmp     rcx, r13
0x180042700  jz      loc_18004291A
0x180042706  test    [rcx+1Ch], r12d
0x18004270a  jz      loc_18004291A
0x180042710  cmp     byte ptr [rcx+19h], 2
0x180042714  jb      loc_18004291A
0x18004271a  mov     edx, 293h
0x18004271f  jmp     short loc_1800426D6
0x180042721  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180042725  xor     r9d, r9d; TokenInformationLength
0x180042728  lea     rax, [rbp+TokenInformationLength]
0x18004272c  xor     r8d, r8d; TokenInformation
0x18004272f  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180042734  lea     edx, [r9+1]; TokenInformationClass
0x180042738  call    cs:__imp_GetTokenInformation
0x18004273f  nop     dword ptr [rax+rax+00h]
0x180042744  test    eax, eax
0x180042746  jnz     short loc_180042791
0x180042748  call    cs:__imp_GetLastError
0x18004274f  nop     dword ptr [rax+rax+00h]
0x180042754  mov     ebx, eax
0x180042756  cmp     eax, 7Ah ; 'z'
0x180042759  jz      short loc_180042791
0x18004275b  test    eax, eax
0x18004275d  jz      loc_180042913
0x180042763  mov     rcx, cs:WPP_GLOBAL_Control
0x18004276a  cmp     rcx, r13
0x18004276d  jz      loc_18004291A
0x180042773  test    [rcx+1Ch], r12d
0x180042777  jz      loc_18004291A
0x18004277d  cmp     byte ptr [rcx+19h], 2
0x180042781  jb      loc_18004291A
0x180042787  mov     edx, 294h
0x18004278c  jmp     loc_1800426D6
0x180042791  mov     edx, [rbp+TokenInformationLength]; uBytes
0x180042794  xor     ecx, ecx; uFlags
0x180042796  call    cs:__imp_LocalAlloc
0x18004279d  nop     dword ptr [rax+rax+00h]
0x1800427a2  mov     rdi, rax
0x1800427a5  test    rax, rax
0x1800427a8  jnz     short loc_1800427EE
0x1800427aa  call    cs:__imp_GetLastError
0x1800427b1  nop     dword ptr [rax+rax+00h]
0x1800427b6  mov     ebx, eax
0x1800427b8  test    eax, eax
0x1800427ba  jz      loc_180042913
0x1800427c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800427c7  cmp     rcx, r13
0x1800427ca  jz      loc_18004291A
0x1800427d0  test    [rcx+1Ch], r12d
0x1800427d4  jz      loc_18004291A
0x1800427da  cmp     byte ptr [rcx+19h], 2
0x1800427de  jb      loc_18004291A
0x1800427e4  mov     edx, 295h
0x1800427e9  jmp     loc_1800426D6
0x1800427ee  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800427f2  lea     rax, [rbp+TokenInformationLength]
0x1800427f6  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800427fa  mov     r8, rdi; TokenInformation
0x1800427fd  mov     edx, 1; TokenInformationClass
0x180042802  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x180042807  call    cs:__imp_GetTokenInformation
0x18004280e  nop     dword ptr [rax+rax+00h]
0x180042813  test    eax, eax
0x180042815  jnz     short loc_18004285B
0x180042817  call    cs:__imp_GetLastError
0x18004281e  nop     dword ptr [rax+rax+00h]
0x180042823  mov     ebx, eax
0x180042825  test    eax, eax
0x180042827  jz      loc_180042904
0x18004282d  mov     rcx, cs:WPP_GLOBAL_Control
0x180042834  cmp     rcx, r13
0x180042837  jz      loc_180042904
0x18004283d  test    [rcx+1Ch], r12d
0x180042841  jz      loc_180042904
0x180042847  cmp     byte ptr [rcx+19h], 2
0x18004284b  jb      loc_180042904
0x180042851  mov     edx, 296h
0x180042856  jmp     loc_1800428F1
0x18004285b  mov     edx, 44h ; 'D'; uBytes
0x180042860  xor     ecx, ecx; uFlags
0x180042862  call    cs:__imp_LocalAlloc
0x180042869  nop     dword ptr [rax+rax+00h]
0x18004286e  mov     [rsi], rax
0x180042871  test    rax, rax
0x180042874  jnz     short loc_1800428A7
0x180042876  call    cs:__imp_GetLastError
0x18004287d  nop     dword ptr [rax+rax+00h]
0x180042882  mov     ebx, eax
0x180042884  test    eax, eax
0x180042886  jz      short loc_180042904
0x180042888  mov     rcx, cs:WPP_GLOBAL_Control
0x18004288f  cmp     rcx, r13
0x180042892  jz      short loc_180042904
0x180042894  test    [rcx+1Ch], r12d
0x180042898  jz      short loc_180042904
0x18004289a  cmp     byte ptr [rcx+19h], 2
0x18004289e  jb      short loc_180042904
0x1800428a0  mov     edx, 297h
0x1800428a5  jmp     short loc_1800428F1
0x1800428a7  mov     r8, [rdi]; pSourceSid
0x1800428aa  xor     ebx, ebx
0x1800428ac  mov     rdx, rax; pDestinationSid
0x1800428af  lea     ecx, [rbx+44h]; nDestinationSidLength
0x1800428b2  call    cs:__imp_CopySid
0x1800428b9  nop     dword ptr [rax+rax+00h]
0x1800428be  test    eax, eax
0x1800428c0  jnz     short loc_180042904
0x1800428c2  call    cs:__imp_GetLastError
0x1800428c9  nop     dword ptr [rax+rax+00h]
0x1800428ce  mov     ebx, eax
0x1800428d0  test    eax, eax
0x1800428d2  jz      short loc_180042904
0x1800428d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800428db  cmp     rcx, r13
0x1800428de  jz      short loc_180042904
0x1800428e0  test    [rcx+1Ch], r12d
0x1800428e4  jz      short loc_180042904
0x1800428e6  cmp     byte ptr [rcx+19h], 2
0x1800428ea  jb      short loc_180042904
0x1800428ec  mov     edx, 298h
0x1800428f1  mov     rcx, [rcx+10h]
0x1800428f5  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x1800428fc  mov     r9d, eax
0x1800428ff  call    WPP_SF_d
0x180042904  mov     rcx, rdi; hMem
0x180042907  call    cs:__imp_LocalFree
0x18004290e  nop     dword ptr [rax+rax+00h]
0x180042913  mov     rcx, cs:WPP_GLOBAL_Control
0x18004291a  cmp     qword ptr [rsi], 0
0x18004291e  jz      short loc_180042941
0x180042920  test    ebx, ebx
0x180042922  jz      short loc_180042941
0x180042924  mov     rcx, [rsi]; hMem
0x180042927  call    cs:__imp_LocalFree
0x18004292e  nop     dword ptr [rax+rax+00h]
0x180042933  mov     qword ptr [rsi], 0
0x18004293a  mov     rcx, cs:WPP_GLOBAL_Control
0x180042941  test    r14d, r14d
0x180042944  jz      short loc_180042965
0x180042946  mov     rax, [rbp+TokenHandle]
0x18004294a  test    rax, rax
0x18004294d  jz      short loc_180042965
0x18004294f  mov     rcx, rax; hObject
0x180042952  call    cs:__imp_CloseHandle
0x180042959  nop     dword ptr [rax+rax+00h]
0x18004295e  mov     rcx, cs:WPP_GLOBAL_Control
0x180042965  cmp     rcx, r13
0x180042968  jz      short loc_18004298E
0x18004296a  test    [rcx+1Ch], r12d
0x18004296e  jz      short loc_18004298E
0x180042970  cmp     byte ptr [rcx+19h], 6
0x180042974  jb      short loc_18004298E
0x180042976  mov     rcx, [rcx+10h]
0x18004297a  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x180042981  mov     edx, 299h
0x180042986  mov     r9d, ebx
0x180042989  call    WPP_SF_d
0x18004298e  mov     rsi, [rsp+30h+arg_18]
0x180042993  mov     eax, ebx
0x180042995  mov     rbx, [rsp+30h+arg_10]
0x18004299a  add     rsp, 30h
0x18004299e  pop     r14
0x1800429a0  pop     r13
0x1800429a2  pop     r12
0x1800429a4  pop     rdi
0x1800429a5  pop     rbp
0x1800429a6  retn
```
