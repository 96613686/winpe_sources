# NcaEvCollStrongAuthIsUserUsingSmartcard(void *)

- ea: `0x1800131ac`
- end: `0x1800134b5`
- name: `?NcaEvCollStrongAuthIsUserUsingSmartcard@@YAHPEAX@Z`
- size: `777`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012fe0`
- `0x1800134c0`

## callees

- `0x180004f04`
- `0x180004f34`
- `0x1800131ac`
- `0x180016ee4`
- `0x180018fd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001323d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001336b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001340d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001323d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001336b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001340d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800133fb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800133fb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001322d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800132f0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001322d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800132f0`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001335b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001335b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013446`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180013446`

## pseudocode

```c
__int64 __fastcall NcaEvCollStrongAuthIsUserUsingSmartcard(HANDLE TokenHandle)
{
  int v1; // r14d
  DWORD LastError; // eax
  DWORD v4; // ebx
  PVOID *v5; // r10
  __int64 v6; // rdx
  __int64 v7; // r9
  PVOID *v8; // rcx
  BOOL v9; // edi
  HANDLE Token; // [rsp+30h] [rbp-10h] BYREF
  HANDLE hExistingToken; // [rsp+38h] [rbp-8h] BYREF
  int TokenInformation; // [rsp+88h] [rbp+48h] BYREF
  DWORD ReturnLength; // [rsp+90h] [rbp+50h] BYREF
  unsigned int v15; // [rsp+98h] [rbp+58h] BYREF

  v1 = 0;
  v15 = 0;
  TokenInformation = 0;
  hExistingToken = 0;
  ReturnLength = 0;
  Token = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_b3aa15e3641333918320d88489d2b829_Traceguids);
  if ( !GetTokenInformation(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength) )
  {
    LastError = GetLastError();
    v4 = LastError;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 29;
LABEL_8:
      v7 = LastError;
LABEL_9:
      WPP_SF_d(v5[2], v6, &WPP_b3aa15e3641333918320d88489d2b829_Traceguids, v7);
LABEL_41:
      v5 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_42;
    }
    goto LABEL_42;
  }
  if ( TokenInformation == 1 )
  {
    v4 = 0;
    v5 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 30;
      v7 = 0;
      goto LABEL_9;
    }
    goto LABEL_42;
  }
  if ( TokenInformation != 3 )
    goto LABEL_30;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_b3aa15e3641333918320d88489d2b829_Traceguids);
  if ( GetTokenInformation(TokenHandle, TokenLinkedToken, &hExistingToken, 8u, &ReturnLength) )
  {
    if ( hExistingToken )
    {
      if ( !DuplicateTokenEx(hExistingToken, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &Token) )
      {
        LastError = GetLastError();
        v4 = LastError;
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 33;
          goto LABEL_8;
        }
        goto LABEL_42;
      }
      TokenHandle = Token;
      Token = 0;
      v1 = 1;
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      {
LABEL_34:
        v9 = 0;
        if ( !TokenHandle || (v9 = SetThreadToken(0, TokenHandle)) )
        {
          v4 = 0;
          LoopbackAuthAndImpersonate(v8, &v15);
          if ( v9 )
            RevertToSelf();
          goto LABEL_41;
        }
        LastError = GetLastError();
        v4 = LastError;
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = (unsigned int)(v9 + 36);
          goto LABEL_8;
        }
        goto LABEL_42;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_31:
        if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
          WPP_SF_(v8[2], 35, &WPP_b3aa15e3641333918320d88489d2b829_Traceguids);
        goto LABEL_34;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_b3aa15e3641333918320d88489d2b829_Traceguids);
    }
LABEL_30:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_31;
  }
  LastError = GetLastError();
  v4 = LastError;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v6 = 32;
    goto LABEL_8;
  }
LABEL_42:
  if ( hExistingToken )
  {
    NcaCloseHandle(hExistingToken);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v1 )
  {
    NcaCloseHandle(TokenHandle);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
    WPP_SF_d(v5[2], 37, &WPP_b3aa15e3641333918320d88489d2b829_Traceguids, v4);
  return v15;
}

```

## disassembly

```asm
0x1800131ac  push    rbp
0x1800131ae  push    rbx
0x1800131af  push    rsi
0x1800131b0  push    rdi
0x1800131b1  push    r12
0x1800131b3  push    r13
0x1800131b5  push    r14
0x1800131b7  mov     rbp, rsp
0x1800131ba  sub     rsp, 40h
0x1800131be  xor     r14d, r14d
0x1800131c1  mov     [rbp+arg_18], 0
0x1800131c8  mov     [rbp+TokenInformation], r14d
0x1800131cc  mov     rsi, rcx
0x1800131cf  mov     [rbp+hExistingToken], r14
0x1800131d3  mov     [rbp+arg_10], 0
0x1800131da  mov     [rbp+Token], 0
0x1800131e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131e9  lea     r12, WPP_GLOBAL_Control
0x1800131f0  lea     r13, WPP_b3aa15e3641333918320d88489d2b829_Traceguids
0x1800131f7  cmp     rcx, r12
0x1800131fa  jz      short loc_180013212
0x1800131fc  test    byte ptr [rcx+1Ch], 8
0x180013200  jz      short loc_180013212
0x180013202  mov     rcx, [rcx+10h]
0x180013206  lea     edx, [r14+1Ch]
0x18001320a  mov     r8, r13
0x18001320d  call    WPP_SF_
0x180013212  mov     ebx, 4
0x180013217  lea     rax, [rbp+arg_10]
0x18001321b  mov     r9d, ebx; TokenInformationLength
0x18001321e  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180013223  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180013227  mov     rcx, rsi; TokenHandle
0x18001322a  lea     edx, [rbx+0Eh]; TokenInformationClass
0x18001322d  call    cs:__imp_GetTokenInformation
0x180013234  nop     dword ptr [rax+rax+00h]
0x180013239  test    eax, eax
0x18001323b  jnz     short loc_18001327F
0x18001323d  call    cs:__imp_GetLastError
0x180013244  nop     dword ptr [rax+rax+00h]
0x180013249  mov     ebx, eax
0x18001324b  mov     r10, cs:WPP_GLOBAL_Control
0x180013252  cmp     r10, r12
0x180013255  jz      loc_180013459
0x18001325b  test    byte ptr [r10+1Ch], 1
0x180013260  jz      loc_180013459
0x180013266  mov     edx, 1Dh
0x18001326b  mov     r9d, eax
0x18001326e  mov     rcx, [r10+10h]
0x180013272  mov     r8, r13
0x180013275  call    WPP_SF_d
0x18001327a  jmp     loc_180013452
0x18001327f  cmp     [rbp+TokenInformation], 1
0x180013283  jnz     short loc_1800132AA
0x180013285  xor     ebx, ebx
0x180013287  mov     r10, cs:WPP_GLOBAL_Control
0x18001328e  cmp     r10, r12
0x180013291  jz      loc_180013459
0x180013297  test    byte ptr [r10+1Ch], 1
0x18001329c  jz      loc_180013459
0x1800132a2  lea     edx, [rbx+1Eh]
0x1800132a5  xor     r9d, r9d
0x1800132a8  jmp     short loc_18001326E
0x1800132aa  cmp     [rbp+TokenInformation], 3
0x1800132ae  jnz     loc_1800133CD
0x1800132b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132bb  cmp     rcx, r12
0x1800132be  jz      short loc_1800132D6
0x1800132c0  test    [rcx+1Ch], bl
0x1800132c3  jz      short loc_1800132D6
0x1800132c5  mov     rcx, [rcx+10h]
0x1800132c9  mov     edx, 1Fh
0x1800132ce  mov     r8, r13
0x1800132d1  call    WPP_SF_
0x1800132d6  mov     r9d, 8; TokenInformationLength
0x1800132dc  lea     rax, [rbp+arg_10]
0x1800132e0  lea     r8, [rbp+hExistingToken]; TokenInformation
0x1800132e4  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x1800132e9  mov     rcx, rsi; TokenHandle
0x1800132ec  lea     edx, [r9+0Bh]; TokenInformationClass
0x1800132f0  call    cs:__imp_GetTokenInformation
0x1800132f7  nop     dword ptr [rax+rax+00h]
0x1800132fc  test    eax, eax
0x1800132fe  jnz     short loc_180013333
0x180013300  call    cs:__imp_GetLastError
0x180013307  nop     dword ptr [rax+rax+00h]
0x18001330c  mov     ebx, eax
0x18001330e  mov     r10, cs:WPP_GLOBAL_Control
0x180013315  cmp     r10, r12
0x180013318  jz      loc_180013459
0x18001331e  test    byte ptr [r10+1Ch], 1
0x180013323  jz      loc_180013459
0x180013329  mov     edx, 20h ; ' '
0x18001332e  jmp     loc_18001326B
0x180013333  mov     rcx, [rbp+hExistingToken]; hExistingToken
0x180013337  test    rcx, rcx
0x18001333a  jz      loc_1800133CD
0x180013340  mov     r9d, 2; ImpersonationLevel
0x180013346  lea     rax, [rbp+Token]
0x18001334a  mov     [rsp+40h+phNewToken], rax; phNewToken
0x18001334f  xor     r8d, r8d; lpTokenAttributes
0x180013352  mov     dword ptr [rsp+40h+ReturnLength], r9d; TokenType
0x180013357  lea     edx, [r9+0Ah]; dwDesiredAccess
0x18001335b  call    cs:__imp_DuplicateTokenEx
0x180013362  nop     dword ptr [rax+rax+00h]
0x180013367  test    eax, eax
0x180013369  jnz     short loc_18001339E
0x18001336b  call    cs:__imp_GetLastError
0x180013372  nop     dword ptr [rax+rax+00h]
0x180013377  mov     ebx, eax
0x180013379  mov     r10, cs:WPP_GLOBAL_Control
0x180013380  cmp     r10, r12
0x180013383  jz      loc_180013459
0x180013389  test    byte ptr [r10+1Ch], 1
0x18001338e  jz      loc_180013459
0x180013394  mov     edx, 21h ; '!'
0x180013399  jmp     loc_18001326B
0x18001339e  mov     rsi, [rbp+Token]
0x1800133a2  mov     [rbp+Token], r14
0x1800133a6  mov     r14d, 1
0x1800133ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800133b3  cmp     rcx, r12
0x1800133b6  jz      short loc_1800133EF
0x1800133b8  test    [rcx+1Ch], bl
0x1800133bb  jz      short loc_1800133D4
0x1800133bd  mov     rcx, [rcx+10h]
0x1800133c1  lea     edx, [r14+21h]
0x1800133c5  mov     r8, r13
0x1800133c8  call    WPP_SF_
0x1800133cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800133d4  cmp     rcx, r12
0x1800133d7  jz      short loc_1800133EF
0x1800133d9  test    [rcx+1Ch], bl
0x1800133dc  jz      short loc_1800133EF
0x1800133de  mov     rcx, [rcx+10h]
0x1800133e2  mov     edx, 23h ; '#'
0x1800133e7  mov     r8, r13
0x1800133ea  call    WPP_SF_
0x1800133ef  xor     edi, edi
0x1800133f1  test    rsi, rsi
0x1800133f4  jz      short loc_180013436
0x1800133f6  mov     rdx, rsi; Token
0x1800133f9  xor     ecx, ecx; Thread
0x1800133fb  call    cs:__imp_SetThreadToken
0x180013402  nop     dword ptr [rax+rax+00h]
0x180013407  mov     edi, eax
0x180013409  test    eax, eax
0x18001340b  jnz     short loc_180013436
0x18001340d  call    cs:__imp_GetLastError
0x180013414  nop     dword ptr [rax+rax+00h]
0x180013419  mov     ebx, eax
0x18001341b  mov     r10, cs:WPP_GLOBAL_Control
0x180013422  cmp     r10, r12
0x180013425  jz      short loc_180013459
0x180013427  test    byte ptr [r10+1Ch], 1
0x18001342c  jz      short loc_180013459
0x18001342e  lea     edx, [rdi+24h]
0x180013431  jmp     loc_18001326B
0x180013436  xor     ebx, ebx
0x180013438  lea     rdx, [rbp+arg_18]
0x18001343c  call    LoopbackAuthAndImpersonate
0x180013441  cmp     edi, 1
0x180013444  jnz     short loc_180013452
0x180013446  call    cs:__imp_RevertToSelf
0x18001344d  nop     dword ptr [rax+rax+00h]
0x180013452  mov     r10, cs:WPP_GLOBAL_Control
0x180013459  mov     rcx, [rbp+hExistingToken]
0x18001345d  test    rcx, rcx
0x180013460  jz      short loc_18001346E
0x180013462  call    NcaCloseHandle
0x180013467  mov     r10, cs:WPP_GLOBAL_Control
0x18001346e  test    r14d, r14d
0x180013471  jz      short loc_180013482
0x180013473  mov     rcx, rsi
0x180013476  call    NcaCloseHandle
0x18001347b  mov     r10, cs:WPP_GLOBAL_Control
0x180013482  cmp     r10, r12
0x180013485  jz      short loc_1800134A2
0x180013487  test    byte ptr [r10+1Ch], 8
0x18001348c  jz      short loc_1800134A2
0x18001348e  mov     rcx, [r10+10h]
0x180013492  mov     edx, 25h ; '%'
0x180013497  mov     r9d, ebx
0x18001349a  mov     r8, r13
0x18001349d  call    WPP_SF_d
0x1800134a2  mov     eax, [rbp+arg_18]
0x1800134a5  add     rsp, 40h
0x1800134a9  pop     r14
0x1800134ab  pop     r13
0x1800134ad  pop     r12
0x1800134af  pop     rdi
0x1800134b0  pop     rsi
0x1800134b1  pop     rbx
0x1800134b2  pop     rbp
0x1800134b3  retn
```
