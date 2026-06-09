# LogonCredGenerateSignature

- ea: `0x180029818`
- end: `0x180029ad6`
- name: `LogonCredGenerateSignature`
- size: `702`
- prototype: `__int64 __fastcall(__int64, UCHAR *, ULONG, unsigned __int8 *, unsigned int **, DWORD *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800278c4`
- `0x180036dc0`

## callees

- `0x180002310`
- `0x180003080`
- `0x1800032b4`
- `0x180007f10`
- `0x18000b638`
- `0x18001c9c0`
- `0x18001d810`
- `0x18002955c`
- `0x180029818`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800298ea`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002993a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800298ea`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18002993a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800298d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029a82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029aa4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029a82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029aa4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029905`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029905`
- `bcrypt!BCryptGenRandom` at `0x18002996f`
- `bcrypt!BCryptGenRandom` at `0x18002996f`
- `ntdll!RtlNtStatusToDosError` at `0x18002999e`
- `ntdll!RtlNtStatusToDosError` at `0x18002999e`

## string_xrefs

- `0x180029987`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`
- `0x180029a58`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\session.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LogonCredGenerateSignature(
        __int64 a1,
        UCHAR *a2,
        ULONG a3,
        unsigned __int8 *a4,
        unsigned int **a5,
        DWORD *a6)
{
  DWORD LastError; // ebx
  DWORD v9; // r14d
  __int64 v10; // rsi
  unsigned int *v11; // rdi
  unsigned int IterationCount; // eax
  PSID v13; // rcx
  DWORD LengthSid; // eax
  PSID v15; // rdx
  NTSTATUS v16; // eax
  NTSTATUS v17; // ebx
  DWORD v18; // eax
  __int64 v19; // r9
  __int64 v20; // rcx
  unsigned int *v21; // rax
  PSID pSid; // [rsp+60h] [rbp-A8h] BYREF
  ULONG cbInput; // [rsp+68h] [rbp-A0h]
  struct _LUID v25; // [rsp+70h] [rbp-98h] BYREF
  PUCHAR pbInput; // [rsp+78h] [rbp-90h]
  UCHAR pbSecret[64]; // [rsp+80h] [rbp-88h] BYREF

  cbInput = a3;
  pbInput = a2;
  v25 = 0;
  pSid = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 40, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids);
  if ( !(unsigned int)GetTokenAuthenticationId(a1, &v25) )
    return GetLastError();
  if ( !(unsigned int)GetTokenUserSid(a1, &pSid) )
  {
    LastError = GetLastError();
    goto LABEL_21;
  }
  v9 = GetLengthSid(pSid) + 112;
  v10 = v9;
  v11 = (unsigned int *)LocalAlloc(0x40u, v9);
  if ( !v11 )
  {
    LastError = 8;
    goto LABEL_21;
  }
  IterationCount = GetIterationCount(0x800Eu);
  v13 = pSid;
  *v11 = 2;
  v11[5] = IterationCount;
  LengthSid = GetLengthSid(v13);
  v15 = pSid;
  v11[10] = LengthSid;
  v11[11] = 64;
  memcpy_0(v11 + 12, v15, LengthSid);
  v16 = BCryptGenRandom(0, (PUCHAR)v11 + 24, 0x10u, 2u);
  v17 = v16;
  if ( v16 < 0 )
  {
    DebugTraceError(
      (unsigned int)v16,
      "ntStatus",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp",
      2530);
    LastError = RtlNtStatusToDosError(v17);
LABEL_17:
    v21 = v11;
    if ( v9 )
    {
      do
      {
        *(_BYTE *)v21 = 0;
        v21 = (unsigned int *)((char *)v21 + 1);
        --v10;
      }
      while ( v10 );
    }
    LocalFree(v11);
    goto LABEL_21;
  }
  v18 = LogonCredGenerateSignatureKey(&v25, 3, a4, (struct _CRED_SIGNATURE *)v11, 0x800Eu, pbSecret, 0x40u);
  LastError = v18;
  if ( v18 )
  {
    v19 = 2550;
    v20 = v18;
LABEL_16:
    DebugTraceError(v20, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\session.cpp", v19);
    goto LABEL_17;
  }
  if ( !(unsigned int)ReusableHMAC(
                        0,
                        0,
                        0x800Eu,
                        pbSecret,
                        0x40u,
                        pbInput,
                        cbInput,
                        0,
                        0,
                        (PUCHAR)v11 + v11[10] + 48,
                        0x40u) )
  {
    LastError = 13;
    v19 = 2565;
    v20 = 13;
    goto LABEL_16;
  }
  *a5 = v11;
  *a6 = v9;
LABEL_21:
  if ( pSid )
    LocalFree(pSid);
  return LastError;
}

```

## disassembly

```asm
0x180029818  push    rbx
0x18002981a  push    rsi
0x18002981b  push    rdi
0x18002981c  push    r12
0x18002981e  push    r13
0x180029820  push    r14
0x180029822  push    r15
0x180029824  sub     rsp, 0D0h
0x18002982b  mov     rax, cs:__security_cookie
0x180029832  xor     rax, rsp
0x180029835  mov     [rsp+108h+var_48], rax
0x18002983d  mov     r15, [rsp+108h+arg_20]
0x180029845  mov     r13, r9
0x180029848  mov     r12, [rsp+108h+arg_28]
0x180029850  mov     rbx, rcx
0x180029853  mov     [rsp+108h+var_A0], r8d
0x180029858  mov     [rsp+108h+var_90], rdx
0x18002985d  mov     qword ptr [rsp+108h+var_98.LowPart], 0
0x180029866  mov     [rsp+108h+pSid], 0
0x18002986f  mov     rcx, cs:WPP_GLOBAL_Control
0x180029876  lea     rax, WPP_GLOBAL_Control
0x18002987d  cmp     rcx, rax
0x180029880  jz      short loc_18002989D
0x180029882  test    byte ptr [rcx+1Ch], 4
0x180029886  jz      short loc_18002989D
0x180029888  mov     rcx, [rcx+10h]
0x18002988c  lea     r8, WPP_e3a7258610da3aa1df17bc00612a8d45_Traceguids
0x180029893  mov     edx, 28h ; '('
0x180029898  call    WPP_SF_
0x18002989d  lea     rdx, [rsp+108h+var_98]
0x1800298a2  mov     rcx, rbx
0x1800298a5  call    GetTokenAuthenticationId
0x1800298aa  test    eax, eax
0x1800298ac  jnz     short loc_1800298C1
0x1800298ae  call    cs:__imp_GetLastError
0x1800298b5  nop     dword ptr [rax+rax+00h]
0x1800298ba  mov     ebx, eax
0x1800298bc  jmp     loc_180029AB0
0x1800298c1  lea     rdx, [rsp+108h+pSid]
0x1800298c6  mov     rcx, rbx
0x1800298c9  call    GetTokenUserSid
0x1800298ce  test    eax, eax
0x1800298d0  jnz     short loc_1800298E5
0x1800298d2  call    cs:__imp_GetLastError
0x1800298d9  nop     dword ptr [rax+rax+00h]
0x1800298de  mov     ebx, eax
0x1800298e0  jmp     loc_180029A97
0x1800298e5  mov     rcx, [rsp+108h+pSid]; pSid
0x1800298ea  call    cs:__imp_GetLengthSid
0x1800298f1  nop     dword ptr [rax+rax+00h]
0x1800298f6  mov     ecx, 40h ; '@'; uFlags
0x1800298fb  lea     r14d, [rax+70h]
0x1800298ff  mov     edx, r14d; uBytes
0x180029902  mov     esi, r14d
0x180029905  call    cs:__imp_LocalAlloc
0x18002990c  nop     dword ptr [rax+rax+00h]
0x180029911  mov     rdi, rax
0x180029914  test    rax, rax
0x180029917  jnz     short loc_180029921
0x180029919  lea     ebx, [rax+8]
0x18002991c  jmp     loc_180029A97
0x180029921  mov     ecx, 800Eh; unsigned int
0x180029926  call    ?GetIterationCount@@YAKI@Z; GetIterationCount(uint)
0x18002992b  mov     rcx, [rsp+108h+pSid]; pSid
0x180029930  mov     ebx, 2
0x180029935  mov     [rdi], ebx
0x180029937  mov     [rdi+14h], eax
0x18002993a  call    cs:__imp_GetLengthSid
0x180029941  nop     dword ptr [rax+rax+00h]
0x180029946  mov     rdx, [rsp+108h+pSid]; Src
0x18002994b  lea     rcx, [rdi+30h]; void *
0x18002994f  mov     r8d, eax; Size
0x180029952  mov     [rdi+28h], r8d
0x180029956  mov     dword ptr [rdi+2Ch], 40h ; '@'
0x18002995d  call    memcpy_0
0x180029962  lea     rdx, [rdi+18h]; pbBuffer
0x180029966  mov     r9d, ebx; dwFlags
0x180029969  xor     ecx, ecx; hAlgorithm
0x18002996b  lea     r8d, [rbx+0Eh]; cbBuffer
0x18002996f  call    cs:__imp_BCryptGenRandom
0x180029976  nop     dword ptr [rax+rax+00h]
0x18002997b  mov     ebx, eax
0x18002997d  test    eax, eax
0x18002997f  jns     short loc_1800299B1
0x180029981  mov     r9d, 9E2h
0x180029987  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18002998e  lea     rdx, aNtstatus; "ntStatus"
0x180029995  mov     ecx, eax
0x180029997  call    DebugTraceError
0x18002999c  mov     ecx, ebx; Status
0x18002999e  call    cs:__imp_RtlNtStatusToDosError
0x1800299a5  nop     dword ptr [rax+rax+00h]
0x1800299aa  mov     ebx, eax
0x1800299ac  jmp     loc_180029A6B
0x1800299b1  lea     rax, [rsp+108h+pbSecret]
0x1800299b9  mov     [rsp+108h+cbInput], 40h ; '@'; unsigned int
0x1800299c1  mov     [rsp+108h+pbInput], rax; unsigned __int8 *
0x1800299c6  lea     rcx, [rsp+108h+var_98]; struct _LUID *
0x1800299cb  mov     r9, rdi; struct _CRED_SIGNATURE *
0x1800299ce  mov     [rsp+108h+var_E8], 800Eh; unsigned int
0x1800299d6  mov     r8, r13; unsigned __int8 *
0x1800299d9  mov     edx, 3; unsigned int
0x1800299de  call    ?LogonCredGenerateSignatureKey@@YAKPEAU_LUID@@KPEAEPEAU_CRED_SIGNATURE@@I1K@Z; LogonCredGenerateSignatureKey(_LUID *,ulong,uchar *,_CRED_SIGNATURE *,uint,uchar *,ulong)
0x1800299e3  mov     ebx, eax
0x1800299e5  test    eax, eax
0x1800299e7  jz      short loc_1800299F3
0x1800299e9  mov     r9d, 9F6h
0x1800299ef  mov     ecx, eax
0x1800299f1  jmp     short loc_180029A58
0x1800299f3  mov     ecx, [rdi+28h]
0x1800299f6  lea     r9, [rsp+108h+pbSecret]; pbSecret
0x1800299fe  mov     eax, [rsp+108h+var_A0]
0x180029a02  add     rcx, 30h ; '0'
0x180029a06  mov     edx, 40h ; '@'
0x180029a0b  add     rcx, rdi
0x180029a0e  mov     [rsp+108h+var_B8], edx; unsigned int
0x180029a12  mov     r8d, 800Eh; unsigned int
0x180029a18  mov     [rsp+108h+pbOutput], rcx; pbOutput
0x180029a1d  xor     ecx, ecx; hAlgorithm
0x180029a1f  mov     [rsp+108h+cbHashObject], 0; cbHashObject
0x180029a27  mov     [rsp+108h+pbHashObject], 0; pbHashObject
0x180029a30  mov     [rsp+108h+cbInput], eax; cbInput
0x180029a34  mov     rax, [rsp+108h+var_90]
0x180029a39  mov     [rsp+108h+pbInput], rax; pbInput
0x180029a3e  mov     [rsp+108h+var_E8], edx; ULONG
0x180029a42  xor     edx, edx; hHash
0x180029a44  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x180029a49  test    eax, eax
0x180029a4b  jnz     short loc_180029A90
0x180029a4d  lea     ebx, [rax+0Dh]
0x180029a50  mov     r9d, 0A05h
0x180029a56  mov     ecx, ebx
0x180029a58  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180029a5f  lea     rdx, aDwlasterror; "dwLastError"
0x180029a66  call    DebugTraceError
0x180029a6b  mov     rax, rdi
0x180029a6e  test    r14d, r14d
0x180029a71  jz      short loc_180029A7F
0x180029a73  mov     byte ptr [rax], 0
0x180029a76  inc     rax
0x180029a79  sub     rsi, 1
0x180029a7d  jnz     short loc_180029A73
0x180029a7f  mov     rcx, rdi; hMem
0x180029a82  call    cs:__imp_LocalFree
0x180029a89  nop     dword ptr [rax+rax+00h]
0x180029a8e  jmp     short loc_180029A97
0x180029a90  mov     [r15], rdi
0x180029a93  mov     [r12], r14d
0x180029a97  cmp     [rsp+108h+pSid], 0
0x180029a9d  jz      short loc_180029AB0
0x180029a9f  mov     rcx, [rsp+108h+pSid]; hMem
0x180029aa4  call    cs:__imp_LocalFree
0x180029aab  nop     dword ptr [rax+rax+00h]
0x180029ab0  mov     eax, ebx
0x180029ab2  mov     rcx, [rsp+108h+var_48]
0x180029aba  xor     rcx, rsp; StackCookie
0x180029abd  call    __security_check_cookie
0x180029ac2  add     rsp, 0D0h
0x180029ac9  pop     r15
0x180029acb  pop     r14
0x180029acd  pop     r13
0x180029acf  pop     r12
0x180029ad1  pop     rdi
0x180029ad2  pop     rsi
0x180029ad3  pop     rbx
0x180029ad4  retn
```
