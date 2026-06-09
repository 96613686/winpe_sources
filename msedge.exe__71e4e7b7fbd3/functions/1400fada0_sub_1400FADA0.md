# sub_1400FADA0

- ea: `0x1400fada0`
- end: `0x1400fb079`
- name: `sub_1400FADA0`
- size: `729`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14003abe0`
- `0x140078930`
- `0x140086c50`
- `0x1400ada40`
- `0x1400cd1f0`
- `0x1400d8290`
- `0x1400f1cc8`
- `0x1400fada0`
- `0x1400fb080`
- `0x1400fb0a0`
- `0x1400fb0b4`
- `0x140102f70`
- `0x1401079e0`
- `0x140107aa0`
- `0x14010bdc0`
- `0x14011fa70`
- `0x140152400`
- `0x140153270`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400fae1c`
- `KERNEL32!GetLastError` at `0x1400fafc8`
- `KERNEL32!GetLastError` at `0x1401b93a1`
- `KERNEL32!GetLastError` at `0x1401b93b1`
- `KERNEL32!GetLastError` at `0x1401b93cc`
- `KERNEL32!GetLastError` at `0x1400fae1c`
- `KERNEL32!GetLastError` at `0x1400fafc8`
- `KERNEL32!GetLastError` at `0x1401b939a`
- `KERNEL32!GetLastError` at `0x1401b93cc`
- `KERNEL32!TerminateProcess` at `0x1401b9381`
- `KERNEL32!TerminateProcess` at `0x1401b93da`
- `KERNEL32!TerminateProcess` at `0x1401b9381`
- `KERNEL32!TerminateProcess` at `0x1401b93da`
- `ADVAPI32!CreateProcessAsUserW` at `0x1400faf0c`
- `ADVAPI32!CreateProcessAsUserW` at `0x1400faf0c`
- `ADVAPI32!SetThreadToken` at `0x1400faf52`
- `ADVAPI32!SetThreadToken` at `0x1400faf52`

## pseudocode

```c
__int64 __fastcall sub_1400FADA0(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  _QWORD *v7; // r15
  __int64 v8; // rsi
  int v9; // r14d
  WCHAR *p_CommandLine; // rdi
  DWORD dwCreationFlags; // r14d
  struct _STARTUPINFOW *lpStartupInfo; // rsi
  WCHAR *v13; // rbp
  void *v14; // rax
  BOOL v15; // esi
  void *v16; // rax
  __int64 v17; // r8
  __int64 v18; // r12
  __int64 v19; // rdx
  char v20; // si
  DWORD LastError; // eax
  _DWORD *v22; // rdi
  WCHAR *v23; // rsi
  __int64 i; // rcx
  int v26; // eax
  __int64 v27; // rax
  const char *v28; // rcx
  const char *v29; // rsi
  size_t v30; // rax
  __int64 v31; // r14
  __int64 v32; // [rsp+0h] [rbp-188h] BYREF
  BOOL bInheritHandles; // [rsp+5Ch] [rbp-12Ch]
  __int64 v34; // [rsp+60h] [rbp-128h]
  LPVOID lpEnvironment; // [rsp+68h] [rbp-120h]
  __int64 v36; // [rsp+70h] [rbp-118h]
  void *Thread; // [rsp+78h] [rbp-110h] BYREF
  __int128 CommandLine; // [rsp+80h] [rbp-108h] BYREF
  __int64 v39; // [rsp+90h] [rbp-F8h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+A0h] [rbp-E8h] BYREF
  const char *v41; // [rsp+C0h] [rbp-C8h]
  __int64 v42; // [rsp+C8h] [rbp-C0h]
  WCHAR *v43; // [rsp+D0h] [rbp-B8h]
  __int64 v44; // [rsp+D8h] [rbp-B0h]
  WCHAR ApplicationName[12]; // [rsp+E0h] [rbp-A8h] BYREF
  __int128 v46; // [rsp+F8h] [rbp-90h]
  __int128 v47; // [rsp+108h] [rbp-80h]
  __int128 v48; // [rsp+118h] [rbp-70h]
  __int64 v49; // [rsp+128h] [rbp-60h]

  v36 = a1;
  (*(void (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)(a1 + 72) + 8LL))(*(_QWORD *)(a1 + 72), a4);
  *(_QWORD *)(a2 + 96) = 0;
  *(_OWORD *)(a2 + 80) = 0;
  *(_OWORD *)(a2 + 64) = 0;
  *(_OWORD *)(a2 + 48) = 0;
  *(_OWORD *)(a2 + 32) = 0;
  *(_OWORD *)(a2 + 16) = 0;
  *(_OWORD *)a2 = 0;
  sub_1400FB080(a2);
  *(_QWORD *)(a2 + 24) = 0;
  *(_DWORD *)(a2 + 32) = GetLastError();
  *(_BYTE *)(a2 + 36) = 0;
  v7 = a4;
  v8 = *a4;
  v9 = (*(_QWORD *)(v8 + 160) != 0) << 19;
  bInheritHandles = *(unsigned __int8 *)(v8 + 24);
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  p_CommandLine = (WCHAR *)&CommandLine;
  v39 = 0;
  CommandLine = 0;
  sub_140102F70(a3, &CommandLine);
  lpEnvironment = (LPVOID)sub_1400FB0B4(v8);
  if ( v39 < 0 )
    p_CommandLine = (WCHAR *)CommandLine;
  dwCreationFlags = v9 | 0x40C;
  lpStartupInfo = (struct _STARTUPINFOW *)(v8 + 56);
  v34 = a3;
  sub_140107AA0(a3, ApplicationName);
  v13 = ApplicationName;
  if ( (ApplicationName[11] & 0x8000u) != 0 )
    v13 = *(WCHAR **)ApplicationName;
  v14 = (void *)sub_1400D8290(v7 + 2);
  v15 = CreateProcessAsUserW(
          v14,
          v13,
          p_CommandLine,
          0,
          0,
          bInheritHandles,
          dwCreationFlags,
          lpEnvironment,
          0,
          lpStartupInfo,
          &ProcessInformation);
  sub_140086C50(ApplicationName);
  if ( !v15 )
  {
    *(_DWORD *)(a2 + 24) = GetLastError();
    wcscpy(ApplicationName, L"\x12");
    *(_DWORD *)&ApplicationName[2] = GetLastError();
    LOBYTE(ApplicationName[4]) = 0;
    v18 = v34;
    goto LABEL_13;
  }
  sub_1400ADA40(a2, &ProcessInformation);
  Thread = *(void **)(a2 + 8);
  v16 = (void *)sub_1400D8290(v7 + 1);
  v18 = v34;
  if ( !SetThreadToken(&Thread, v16) )
  {
    *(_DWORD *)(a2 + 24) = GetLastError();
    TerminateProcess(*(HANDLE *)a2, 0);
    *(_OWORD *)&ApplicationName[4] = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v26 = *(_DWORD *)(a2 + 24);
    wcscpy(ApplicationName, L"\x15");
    *(_DWORD *)&ApplicationName[2] = v26;
    v27 = sub_1400D8290(v7 + 1);
    v28 = "HANDLES_ALL_OK";
    if ( !v27 )
      v28 = "HANDLES_STATE_INVALID_SECOND_PARAM";
    v29 = "HANDLES_STATE_INVALID_FIRST_PARAM";
    if ( !v27 )
      v29 = "HANDLES_STATE_INVALID_PARAMS";
    if ( Thread )
      v29 = v28;
    v30 = strlen(v29);
    v31 = 63;
    if ( v30 < 0x3F )
      v31 = v30;
    v43 = &ApplicationName[4];
    v44 = v31;
    v41 = v29;
    v42 = v31;
    sub_140078930();
    *((_BYTE *)&ApplicationName[4] + v31) = 0;
    goto LABEL_13;
  }
  v19 = *(_QWORD *)(a2 + 8);
  *(_OWORD *)ApplicationName = 0;
  LOBYTE(v17) = 1;
  sub_1400CD1F0(ApplicationName, v19, v17, 0);
  if ( !LOBYTE(ApplicationName[4]) )
    goto LABEL_20;
  v20 = sub_1400FB0A0(ApplicationName);
  if ( LOBYTE(ApplicationName[4]) == 1 )
    sub_14010BDC0(ApplicationName);
  if ( v20 )
    goto LABEL_20;
  *(_DWORD *)ApplicationName = 0;
  LastError = GetLastError();
  while ( 1 )
  {
    *(_DWORD *)&ApplicationName[2] = LastError;
    LOBYTE(ApplicationName[4]) = 0;
LABEL_13:
    v22 = (_DWORD *)(a2 + 28);
    if ( v39 < 0 )
      sub_14003ABE0(CommandLine, 2 * v39);
    v23 = ApplicationName;
    for ( i = 18; i; --i )
    {
      *v22 = *(_DWORD *)v23;
      v23 += 2;
      ++v22;
    }
    (*(void (__fastcall **)(_QWORD, _QWORD *, _QWORD))(**(_QWORD **)(v36 + 72) + 16LL))(
      *(_QWORD *)(v36 + 72),
      v7,
      *(unsigned int *)(a2 + 16));
    sub_1401079E0(v18);
    sub_1400F1CC8(v7);
    if ( _security_cookie == ((unsigned __int64)&v32 ^ v49) )
      break;
LABEL_20:
    *(_DWORD *)(a2 + 24) = 1346;
    TerminateProcess(*(HANDLE *)a2, 0);
    LastError = *(_DWORD *)(a2 + 24);
    wcscpy(ApplicationName, L"\x15");
  }
  return a2;
}

```

## disassembly

```asm
0x1400fada0  push    r15
0x1400fada2  push    r14
0x1400fada4  push    r13
0x1400fada6  push    r12
0x1400fada8  push    rsi
0x1400fada9  push    rdi
0x1400fadaa  push    rbp
0x1400fadab  push    rbx
0x1400fadac  sub     rsp, 148h
0x1400fadb3  movaps  [rsp+188h+var_58], xmm6
0x1400fadbb  mov     rsi, r9
0x1400fadbe  mov     rbp, r8
0x1400fadc1  mov     rbx, rdx
0x1400fadc4  mov     rax, cs:__security_cookie
0x1400fadcb  xor     rax, rsp
0x1400fadce  mov     [rsp+188h+var_60], rax
0x1400fadd6  mov     [rsp+188h+var_118], rcx
0x1400faddb  mov     rcx, [rcx+48h]
0x1400faddf  mov     rax, [rcx]
0x1400fade2  mov     rax, [rax+8]
0x1400fade6  mov     rdx, r9
0x1400fade9  call    cs:__guard_dispatch_icall_fptr
0x1400fadef  xor     r13d, r13d
0x1400fadf2  mov     [rbx+60h], r13
0x1400fadf6  xorps   xmm6, xmm6
0x1400fadf9  movups  xmmword ptr [rbx+50h], xmm6
0x1400fadfd  movups  xmmword ptr [rbx+40h], xmm6
0x1400fae01  movups  xmmword ptr [rbx+30h], xmm6
0x1400fae05  movups  xmmword ptr [rbx+20h], xmm6
0x1400fae09  movups  xmmword ptr [rbx+10h], xmm6
0x1400fae0d  movups  xmmword ptr [rbx], xmm6
0x1400fae10  mov     rcx, rbx
0x1400fae13  call    sub_1400FB080
0x1400fae18  mov     [rbx+18h], r13
0x1400fae1c  call    cs:__imp_GetLastError
0x1400fae22  mov     [rbx+20h], eax
0x1400fae25  mov     byte ptr [rbx+24h], 0
0x1400fae29  mov     r15, rsi
0x1400fae2c  mov     rsi, [rsi]
0x1400fae2f  xor     r14d, r14d
0x1400fae32  cmp     [rsi+0A0h], r13
0x1400fae39  setnz   r14b
0x1400fae3d  shl     r14d, 13h
0x1400fae41  movzx   eax, byte ptr [rsi+18h]
0x1400fae45  mov     [rsp+188h+var_12C], eax
0x1400fae49  mov     qword ptr [rsp+188h+ProcessInformation.dwProcessId], r13
0x1400fae51  movaps  xmmword ptr [rsp+188h+ProcessInformation.hProcess], xmm6
0x1400fae59  lea     rdi, [rsp+188h+CommandLine]
0x1400fae61  mov     [rdi+10h], r13
0x1400fae65  movaps  xmmword ptr [rdi], xmm6
0x1400fae68  mov     rcx, rbp
0x1400fae6b  mov     rdx, rdi
0x1400fae6e  call    sub_140102F70
0x1400fae73  mov     rcx, rsi
0x1400fae76  call    sub_1400FB0B4
0x1400fae7b  mov     [rsp+188h+var_120], rax
0x1400fae80  cmp     byte ptr [rdi+17h], 0
0x1400fae84  jns     short loc_1400FAE8E
0x1400fae86  mov     rdi, qword ptr [rsp+188h+CommandLine]
0x1400fae8e  or      r14d, 40Ch
0x1400fae95  add     rsi, 38h ; '8'
0x1400fae99  lea     r12, [rsp+188h+ApplicationName]
0x1400faea1  mov     [rsp+188h+var_128], rbp
0x1400faea6  mov     rcx, rbp
0x1400faea9  mov     rdx, r12
0x1400faeac  call    sub_140107AA0
0x1400faeb1  cmp     byte ptr [r12+17h], 0
0x1400faeb7  mov     rbp, r12
0x1400faeba  jns     short loc_1400FAEC4
0x1400faebc  mov     rbp, qword ptr [rsp+188h+ApplicationName]
0x1400faec4  lea     rcx, [r15+10h]
0x1400faec8  call    sub_1400D8290
0x1400faecd  lea     rcx, [rsp+188h+ProcessInformation]
0x1400faed5  mov     [rsp+188h+lpProcessInformation], rcx; lpProcessInformation
0x1400faeda  mov     [rsp+188h+lpStartupInfo], rsi; lpStartupInfo
0x1400faedf  mov     [rsp+188h+lpCurrentDirectory], r13; lpCurrentDirectory
0x1400faee4  mov     rcx, [rsp+188h+var_120]
0x1400faee9  mov     [rsp+188h+lpEnvironment], rcx; lpEnvironment
0x1400faeee  mov     [rsp+188h+dwCreationFlags], r14d; dwCreationFlags
0x1400faef3  mov     ecx, [rsp+188h+var_12C]
0x1400faef7  mov     [rsp+188h+bInheritHandles], ecx; bInheritHandles
0x1400faefb  mov     [rsp+188h+lpThreadAttributes], r13; lpThreadAttributes
0x1400faf00  mov     rcx, rax; hToken
0x1400faf03  mov     rdx, rbp; lpApplicationName
0x1400faf06  mov     r8, rdi; lpCommandLine
0x1400faf09  xor     r9d, r9d; lpProcessAttributes
0x1400faf0c  call    cs:CreateProcessAsUserW
0x1400faf12  mov     esi, eax
0x1400faf14  mov     rcx, r12
0x1400faf17  call    sub_140086C50
0x1400faf1c  test    esi, esi
0x1400faf1e  jz      loc_1401B939A
0x1400faf24  lea     rsi, [r15+8]
0x1400faf28  lea     rdx, [rsp+188h+ProcessInformation]
0x1400faf30  mov     rcx, rbx
0x1400faf33  call    sub_1400ADA40
0x1400faf38  mov     rax, [rbx+8]
0x1400faf3c  lea     rdi, [rsp+188h+Thread]
0x1400faf41  mov     [rdi], rax
0x1400faf44  mov     rcx, rsi
0x1400faf47  call    sub_1400D8290
0x1400faf4c  mov     rcx, rdi; Thread
0x1400faf4f  mov     rdx, rax; Token
0x1400faf52  call    cs:SetThreadToken
0x1400faf58  test    eax, eax
0x1400faf5a  mov     r12, [rsp+188h+var_128]
0x1400faf5f  jz      loc_1401B93CC
0x1400faf65  mov     rdx, [rbx+8]
0x1400faf69  xorps   xmm0, xmm0
0x1400faf6c  lea     rsi, [rsp+188h+ApplicationName]
0x1400faf74  movaps  xmmword ptr [rsi], xmm0
0x1400faf77  mov     rcx, rsi
0x1400faf7a  mov     r8b, 1
0x1400faf7d  xor     r9d, r9d
0x1400faf80  call    sub_1400CD1F0
0x1400faf85  cmp     byte ptr [rsi+8], 0
0x1400faf89  jz      loc_1401B9375
0x1400faf8f  lea     rdi, [rsp+188h+ApplicationName]
0x1400faf97  mov     rcx, rdi
0x1400faf9a  call    sub_1400FB0A0
0x1400faf9f  mov     esi, eax
0x1400fafa1  cmp     byte ptr [rdi+8], 1
0x1400fafa5  jnz     short loc_1400FAFB4
0x1400fafa7  lea     rcx, [rsp+188h+ApplicationName]
0x1400fafaf  call    sub_14010BDC0
0x1400fafb4  test    sil, sil
0x1400fafb7  jnz     loc_1401B9375
0x1400fafbd  mov     dword ptr [rsp+188h+ApplicationName], 0
0x1400fafc8  call    cs:__imp_GetLastError
0x1400fafce  mov     dword ptr [rsp+188h+ApplicationName+4], eax
0x1400fafd5  mov     [rsp+188h+var_A0], 0
0x1400fafdd  lea     rdi, [rbx+1Ch]
0x1400fafe1  cmp     [rsp+188h+var_F1], 0
0x1400fafe9  jns     short loc_1400FB003
0x1400fafeb  mov     rcx, qword ptr [rsp+188h+CommandLine]
0x1400faff3  mov     rdx, [rsp+90h]
0x1400faffb  add     rdx, rdx
0x1400faffe  call    sub_14003ABE0
0x1400fb003  lea     rsi, [rsp+188h+ApplicationName]
0x1400fb00b  mov     ecx, 12h
0x1400fb010  rep movsd
0x1400fb012  mov     rax, [rsp+188h+var_118]
0x1400fb017  mov     rcx, [rax+48h]
0x1400fb01b  mov     r8d, [rbx+10h]
0x1400fb01f  mov     rax, [rcx]
0x1400fb022  mov     rax, [rax+10h]
0x1400fb026  mov     rdx, r15
0x1400fb029  call    cs:__guard_dispatch_icall_fptr
0x1400fb02f  mov     rcx, r12
0x1400fb032  call    sub_1401079E0
0x1400fb037  mov     rcx, r15
0x1400fb03a  call    sub_1400F1CC8
0x1400fb03f  mov     rax, [rsp+188h+var_60]
0x1400fb047  xor     rax, rsp
0x1400fb04a  mov     rcx, cs:__security_cookie
0x1400fb051  cmp     rcx, rax
0x1400fb054  jnz     loc_1401B9365
0x1400fb05a  mov     rax, rbx
0x1400fb05d  movaps  xmm6, [rsp+188h+var_58]
0x1400fb065  add     rsp, 148h
0x1400fb06c  pop     rbx
0x1400fb06d  pop     rbp
0x1400fb06e  pop     rdi
0x1400fb06f  pop     rsi
0x1400fb070  pop     r12
0x1400fb072  pop     r13
0x1400fb074  pop     r14
0x1400fb076  pop     r15
0x1400fb078  retn
0x1401b9365  mov     rcx, [rsp+188h+var_60]
0x1401b936d  xor     rcx, rsp; StackCookie
0x1401b9370  call    __security_check_cookie
0x1401b9375  mov     dword ptr [rbx+18h], 542h
0x1401b937c  mov     rcx, [rbx]; hProcess
0x1401b937f  xor     edx, edx; uExitCode
0x1401b9381  call    cs:TerminateProcess
0x1401b9387  mov     eax, [rbx+18h]
0x1401b938a  mov     dword ptr [rsp+188h+ApplicationName], 15h
0x1401b9395  jmp     loc_1400FAFCE
0x1401b939a  mov     rsi, cs:__imp_GetLastError
0x1401b93a1  call    rsi ; __imp_GetLastError
0x1401b93a3  mov     [rbx+18h], eax
0x1401b93a6  mov     dword ptr [rsp+188h+ApplicationName], 12h
0x1401b93b1  call    rsi ; __imp_GetLastError
0x1401b93b3  mov     dword ptr [rsp+188h+ApplicationName+4], eax
0x1401b93ba  mov     [rsp+188h+var_A0], 0
0x1401b93c2  mov     r12, [rsp+188h+var_128]
0x1401b93c7  jmp     loc_1400FAFDD
0x1401b93cc  call    cs:__imp_GetLastError
0x1401b93d2  mov     [rbx+18h], eax
0x1401b93d5  mov     rcx, [rbx]; hProcess
0x1401b93d8  xor     edx, edx; uExitCode
0x1401b93da  call    cs:TerminateProcess
0x1401b93e0  lea     rdi, [rsp+188h+var_A0]
0x1401b93e8  xorps   xmm0, xmm0
0x1401b93eb  movups  xmmword ptr [rdi], xmm0
0x1401b93ee  movups  xmmword ptr [rdi+10h], xmm0
0x1401b93f2  movups  xmmword ptr [rdi+20h], xmm0
0x1401b93f6  movups  xmmword ptr [rdi+30h], xmm0
0x1401b93fa  mov     eax, [rbx+18h]
0x1401b93fd  mov     dword ptr [rdi-8], 15h
0x1401b9404  mov     [rdi-4], eax
0x1401b9407  mov     rcx, rsi
0x1401b940a  call    sub_1400D8290
0x1401b940f  test    rax, rax
0x1401b9412  lea     rax, aHandlesStateIn; "HANDLES_STATE_INVALID_SECOND_PARAM"
0x1401b9419  lea     rcx, aHandlesAllOk; "HANDLES_ALL_OK"
0x1401b9420  cmovz   rcx, rax
0x1401b9424  lea     rax, aHandlesStateIn_0; "HANDLES_STATE_INVALID_PARAMS"
0x1401b942b  lea     rsi, aHandlesStateIn_1; "HANDLES_STATE_INVALID_FIRST_PARAM"
0x1401b9432  cmovz   rsi, rax
0x1401b9436  cmp     [rsp+188h+Thread], 0
0x1401b943c  cmovnz  rsi, rcx
0x1401b9440  mov     rcx, rsi; Str
0x1401b9443  call    strlen
0x1401b9448  cmp     rax, 3Fh ; '?'
0x1401b944c  mov     r14d, 3Fh ; '?'
0x1401b9452  cmovb   r14, rax
0x1401b9456  lea     rcx, [rsp+188h+var_B8]
0x1401b945e  mov     [rcx], rdi
0x1401b9461  mov     [rcx+8], r14
0x1401b9465  lea     rdx, [rsp+188h+var_C8]
0x1401b946d  mov     [rdx], rsi
0x1401b9470  mov     [rdx+8], r14
0x1401b9474  call    sub_140078930
0x1401b9479  mov     [rsp+r14+188h+var_A0], 0
0x1401b9482  jmp     loc_1400FAFDD
```
