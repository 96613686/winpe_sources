# SspLogNTLMv1BlockedByCredGuard

- ea: `0x1800520c8`
- end: `0x1800524e3`
- name: `SspLogNTLMv1BlockedByCredGuard`
- size: `1051`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024c00`

## callees

- `0x18000cba0`
- `0x18002e3e8`
- `0x18002fb50`
- `0x180030844`
- `0x180051104`
- `0x1800520c8`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052426`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052426`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005229d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005229d`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800522b9`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800522b9`
- `ntdll!EtwEventEnabled` at `0x180052177`
- `ntdll!EtwEventEnabled` at `0x180052177`
- `ntdll!EtwEventWrite` at `0x180052418`
- `ntdll!EtwEventWrite` at `0x180052418`
- `SspiCli!LsaGetLogonSessionData` at `0x180052311`
- `SspiCli!LsaGetLogonSessionData` at `0x180052311`
- `SspiCli!LsaFreeReturnBuffer` at `0x180052447`
- `SspiCli!LsaFreeReturnBuffer` at `0x180052447`

## pseudocode

```c
int __fastcall SspLogNTLMv1BlockedByCredGuard(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int16 *v6; // r14
  int result; // eax
  __int64 v8; // rsi
  __int64 v9; // rdi
  __int64 v10; // rbx
  HANDLE v11; // rax
  void *v12; // r15
  int Length; // r8d
  int v14; // ecx
  int v15; // eax
  __int64 v16; // rax
  DWORD dwSize; // [rsp+20h] [rbp-E0h] BYREF
  DWORD LowPart; // [rsp+24h] [rbp-DCh] BYREF
  unsigned __int16 *v19; // [rsp+28h] [rbp-D8h] BYREF
  PSECURITY_LOGON_SESSION_DATA ppLogonSessionData; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v21; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v22; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v23; // [rsp+58h] [rbp-A8h] BYREF
  struct _LUID LogonId[4]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v25; // [rsp+88h] [rbp-78h] BYREF
  struct ASN1objectidentifier_s *v26; // [rsp+98h] [rbp-68h]
  const wchar_t *v27; // [rsp+A0h] [rbp-60h]
  __int64 v28; // [rsp+A8h] [rbp-58h] BYREF
  const wchar_t *v29; // [rsp+B0h] [rbp-50h]
  __int64 v30; // [rsp+B8h] [rbp-48h]
  const wchar_t *v31; // [rsp+C0h] [rbp-40h]
  __int64 v32; // [rsp+C8h] [rbp-38h]
  DWORD *v33; // [rsp+D0h] [rbp-30h]
  __int64 v34; // [rsp+D8h] [rbp-28h]
  WCHAR *v35; // [rsp+E0h] [rbp-20h]
  __int64 v36; // [rsp+E8h] [rbp-18h]
  struct _LUID *v37; // [rsp+F0h] [rbp-10h]
  __int64 v38; // [rsp+F8h] [rbp-8h]
  PWSTR Buffer; // [rsp+100h] [rbp+0h]
  __int64 v40; // [rsp+108h] [rbp+8h]
  PWSTR v41; // [rsp+110h] [rbp+10h]
  __int64 v42; // [rsp+118h] [rbp+18h]
  unsigned __int16 *v43; // [rsp+120h] [rbp+20h]
  __int64 v44; // [rsp+128h] [rbp+28h]
  WCHAR ExeName[264]; // [rsp+130h] [rbp+30h] BYREF

  v27 = 0;
  memset_0(&v28, 0, 0x88u);
  dwSize = 261;
  memset(LogonId, 0, sizeof(LogonId));
  v26 = 0;
  v6 = 0;
  v19 = 0;
  ppLogonSessionData = 0;
  v25 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  result = SspInitEtwLogHandle();
  if ( result < 0 )
    goto LABEL_45;
  result = EtwEventEnabled(MsvEtwLogHandle, NTLMv1BlockedByCredGuard);
  if ( !(_BYTE)result )
    return result;
  result = NtLmDuplicateUnicodeString(&v23, a2);
  if ( result < 0
    || (result = NtLmDuplicateUnicodeString(&v22, a3), result < 0)
    || (result = NtLmDuplicateUnicodeString(&v21, a1), result < 0) )
  {
LABEL_45:
    v8 = *((_QWORD *)&v21 + 1);
    v10 = *((_QWORD *)&v22 + 1);
    v9 = *((_QWORD *)&v23 + 1);
  }
  else
  {
    v8 = *((_QWORD *)&v21 + 1);
    if ( *((_QWORD *)&v21 + 1) && (_WORD)v21 )
    {
      v27 = (const wchar_t *)*((_QWORD *)&v21 + 1);
      v28 = (unsigned int)(unsigned __int16)v21 + 2;
    }
    else
    {
      v27 = L"(NULL)";
      v28 = 14;
    }
    v9 = *((_QWORD *)&v23 + 1);
    if ( *((_QWORD *)&v23 + 1) && (_WORD)v23 )
    {
      v29 = (const wchar_t *)*((_QWORD *)&v23 + 1);
      v30 = (unsigned int)(unsigned __int16)v23 + 2;
    }
    else
    {
      v29 = L"(NULL)";
      v30 = 14;
    }
    v10 = *((_QWORD *)&v22 + 1);
    if ( *((_QWORD *)&v22 + 1) && (_WORD)v22 )
    {
      v31 = (const wchar_t *)*((_QWORD *)&v22 + 1);
      v32 = (unsigned int)(unsigned __int16)v22 + 2;
    }
    else
    {
      v31 = L"(NULL)";
      v32 = 14;
    }
    result = ((__int64 (__fastcall *)(struct _LUID *))LsaFunctions->GetClientInfo)(LogonId);
    if ( result >= 0 )
    {
      v33 = &LowPart;
      LowPart = LogonId[1].LowPart;
      v34 = 4;
      v11 = OpenProcess(0x1000u, 0, LogonId[1].LowPart);
      v12 = v11;
      if ( v11 && QueryFullProcessImageNameW(v11, 0, ExeName, &dwSize) && dwSize )
      {
        v35 = ExeName;
        v36 = 2 * dwSize + 2;
      }
      else
      {
        v36 = 4;
        v35 = L"-";
      }
      v38 = 8;
      v37 = LogonId;
      if ( LsaGetLogonSessionData(LogonId, &ppLogonSessionData) >= 0 && ppLogonSessionData )
      {
        if ( ppLogonSessionData != (PSECURITY_LOGON_SESSION_DATA)-16LL
          && ppLogonSessionData->UserName.Buffer
          && (Length = ppLogonSessionData->UserName.Length, (_WORD)Length) )
        {
          Buffer = ppLogonSessionData->UserName.Buffer;
          v40 = (unsigned int)(Length + 2);
        }
        else
        {
          Buffer = L"(NULL)";
          v40 = 14;
        }
        if ( ppLogonSessionData != (PSECURITY_LOGON_SESSION_DATA)-32LL )
        {
          if ( ppLogonSessionData->LogonDomain.Buffer )
          {
            v14 = ppLogonSessionData->LogonDomain.Length;
            if ( (_WORD)v14 )
            {
              v41 = ppLogonSessionData->LogonDomain.Buffer;
              v42 = (unsigned int)(v14 + 2);
LABEL_37:
              if ( ((unsigned __int8 (__fastcall *)(__int128 *))LsaFunctions->GetCallInfo)(&v25)
                && (v15 = SspOIDToString(v26, &v19), v6 = v19, v15) )
              {
                v16 = -1;
                do
                  ++v16;
                while ( v19[v16] );
                v43 = v19;
                v44 = (unsigned int)(2 * v16 + 2);
              }
              else
              {
                v43 = L"(NULL)";
                v44 = 14;
              }
              result = EtwEventWrite(MsvEtwLogHandle, NTLMv1BlockedByCredGuard, 9);
              if ( v12 )
                result = CloseHandle(v12);
              goto LABEL_46;
            }
          }
        }
      }
      else
      {
        Buffer = L"(NULL)";
        v40 = 14;
      }
      v42 = 14;
      v41 = L"(NULL)";
      goto LABEL_37;
    }
  }
LABEL_46:
  if ( ppLogonSessionData )
    result = LsaFreeReturnBuffer(ppLogonSessionData);
  if ( v6 )
    result = ((__int64 (__fastcall *)(unsigned __int16 *))LsaFunctions->FreePrivateHeap)(v6);
  if ( v8 )
    result = ((__int64 (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(v8);
  if ( v9 )
    result = ((__int64 (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(v9);
  if ( v10 )
    return ((__int64 (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(v10);
  return result;
}

```

## disassembly

```asm
0x1800520c8  mov     [rsp-8+arg_18], rbx
0x1800520cd  push    rbp
0x1800520ce  push    rsi
0x1800520cf  push    rdi
0x1800520d0  push    r12
0x1800520d2  push    r13
0x1800520d4  push    r14
0x1800520d6  push    r15
0x1800520d8  lea     rbp, [rsp-250h]
0x1800520e0  sub     rsp, 350h
0x1800520e7  mov     rax, cs:__security_cookie
0x1800520ee  xor     rax, rsp
0x1800520f1  mov     [rbp+280h+var_40], rax
0x1800520f8  mov     rdi, r8
0x1800520fb  mov     rbx, rdx
0x1800520fe  mov     rsi, rcx
0x180052101  xor     r12d, r12d
0x180052104  xor     edx, edx; Val
0x180052106  mov     [rbp+280h+var_2E0], r12
0x18005210a  mov     r8d, 88h; Size
0x180052110  lea     rcx, [rbp+280h+var_2D8]; void *
0x180052114  call    memset_0
0x180052119  xorps   xmm0, xmm0
0x18005211c  mov     [rsp+380h+dwSize], 105h
0x180052124  xor     eax, eax
0x180052126  mov     dword ptr [rsp+380h+LogonId], r12d
0x18005212b  xorps   xmm1, xmm1
0x18005212e  mov     [rbp+280h+var_2E8], rax
0x180052132  movups  xmmword ptr [rsp+380h+LogonId+4], xmm0
0x180052137  mov     r14d, r12d
0x18005213a  mov     [rsp+380h+var_358], r12
0x18005213f  movups  xmmword ptr [rsp+380h+LogonId+10h], xmm0
0x180052144  mov     [rsp+380h+ppLogonSessionData], r12
0x180052149  movups  [rbp+280h+var_2F8], xmm0
0x18005214d  movups  [rsp+380h+var_348], xmm0
0x180052152  movups  [rsp+380h+var_338], xmm1
0x180052157  movups  [rsp+380h+var_328], xmm0
0x18005215c  call    SspInitEtwLogHandle
0x180052161  test    eax, eax
0x180052163  js      loc_18005242E
0x180052169  mov     rcx, cs:MsvEtwLogHandle
0x180052170  lea     rdx, NTLMv1BlockedByCredGuard
0x180052177  call    cs:__imp_EtwEventEnabled
0x18005217d  test    al, al
0x18005217f  jz      loc_1800524B9
0x180052185  mov     rdx, rbx
0x180052188  lea     rcx, [rsp+380h+var_328]
0x18005218d  call    NtLmDuplicateUnicodeString
0x180052192  test    eax, eax
0x180052194  js      loc_18005242E
0x18005219a  mov     rdx, rdi
0x18005219d  lea     rcx, [rsp+380h+var_338]
0x1800521a2  call    NtLmDuplicateUnicodeString
0x1800521a7  test    eax, eax
0x1800521a9  js      loc_18005242E
0x1800521af  mov     rdx, rsi
0x1800521b2  lea     rcx, [rsp+380h+var_348]
0x1800521b7  call    NtLmDuplicateUnicodeString
0x1800521bc  test    eax, eax
0x1800521be  js      loc_18005242E
0x1800521c4  mov     rsi, qword ptr [rsp+380h+var_348+8]
0x1800521c9  lea     r13, aNull; "(NULL)"
0x1800521d0  test    rsi, rsi
0x1800521d3  jz      short loc_1800521EF
0x1800521d5  movzx   eax, word ptr [rsp+380h+var_348]
0x1800521da  test    ax, ax
0x1800521dd  jz      short loc_1800521EF
0x1800521df  add     eax, 2
0x1800521e2  mov     [rbp+280h+var_2E0], rsi
0x1800521e6  mov     dword ptr [rbp+280h+var_2D8], eax
0x1800521e9  mov     dword ptr [rbp+280h+var_2D8+4], r12d
0x1800521ed  jmp     short loc_1800521FB
0x1800521ef  mov     [rbp+280h+var_2E0], r13
0x1800521f3  mov     [rbp+280h+var_2D8], 0Eh
0x1800521fb  mov     rdi, qword ptr [rsp+380h+var_328+8]
0x180052200  test    rdi, rdi
0x180052203  jz      short loc_18005221F
0x180052205  movzx   eax, word ptr [rsp+380h+var_328]
0x18005220a  test    ax, ax
0x18005220d  jz      short loc_18005221F
0x18005220f  add     eax, 2
0x180052212  mov     [rbp+280h+var_2D0], rdi
0x180052216  mov     dword ptr [rbp+280h+var_2C8], eax
0x180052219  mov     dword ptr [rbp+280h+var_2C8+4], r12d
0x18005221d  jmp     short loc_18005222B
0x18005221f  mov     [rbp+280h+var_2D0], r13
0x180052223  mov     [rbp+280h+var_2C8], 0Eh
0x18005222b  mov     rbx, qword ptr [rsp+380h+var_338+8]
0x180052230  test    rbx, rbx
0x180052233  jz      short loc_18005224F
0x180052235  movzx   eax, word ptr [rsp+380h+var_338]
0x18005223a  test    ax, ax
0x18005223d  jz      short loc_18005224F
0x18005223f  add     eax, 2
0x180052242  mov     [rbp+280h+var_2C0], rbx
0x180052246  mov     dword ptr [rbp+280h+var_2B8], eax
0x180052249  mov     dword ptr [rbp+280h+var_2B8+4], r12d
0x18005224d  jmp     short loc_18005225B
0x18005224f  mov     [rbp+280h+var_2C0], r13
0x180052253  mov     [rbp+280h+var_2B8], 0Eh
0x18005225b  mov     rax, cs:LsaFunctions
0x180052262  lea     rcx, [rsp+380h+LogonId]
0x180052267  mov     rax, [rax+80h]
0x18005226e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052273  test    eax, eax
0x180052275  js      loc_18005243D
0x18005227b  mov     r8d, dword ptr [rsp+380h+LogonId+8]; dwProcessId
0x180052280  lea     rax, [rsp+380h+var_35C]
0x180052285  xor     edx, edx; bInheritHandle
0x180052287  mov     [rbp+280h+var_2B0], rax
0x18005228b  mov     ecx, 1000h; dwDesiredAccess
0x180052290  mov     [rsp+380h+var_35C], r8d
0x180052295  mov     [rbp+280h+var_2A8], 4
0x18005229d  call    cs:__imp_OpenProcess
0x1800522a3  mov     r15, rax
0x1800522a6  test    rax, rax
0x1800522a9  jz      short loc_1800522E3
0x1800522ab  lea     r9, [rsp+380h+dwSize]; lpdwSize
0x1800522b0  xor     edx, edx; dwFlags
0x1800522b2  lea     r8, [rbp+280h+ExeName]; lpExeName
0x1800522b6  mov     rcx, rax; hProcess
0x1800522b9  call    cs:__imp_QueryFullProcessImageNameW
0x1800522bf  test    eax, eax
0x1800522c1  jz      short loc_1800522E3
0x1800522c3  mov     eax, [rsp+380h+dwSize]
0x1800522c7  test    eax, eax
0x1800522c9  jz      short loc_1800522E3
0x1800522cb  lea     rcx, [rbp+280h+ExeName]
0x1800522cf  mov     dword ptr [rbp+280h+var_298+4], r12d
0x1800522d3  lea     eax, ds:2[rax*2]
0x1800522da  mov     [rbp+280h+var_2A0], rcx
0x1800522de  mov     dword ptr [rbp+280h+var_298], eax
0x1800522e1  jmp     short loc_1800522F6
0x1800522e3  lea     rax, asc_1800745A0; "-"
0x1800522ea  mov     [rbp+280h+var_298], 4
0x1800522f2  mov     [rbp+280h+var_2A0], rax
0x1800522f6  lea     rax, [rsp+380h+LogonId]
0x1800522fb  mov     [rbp+280h+var_288], 8
0x180052303  lea     rdx, [rsp+380h+ppLogonSessionData]; ppLogonSessionData
0x180052308  mov     [rbp+280h+var_290], rax
0x18005230c  lea     rcx, [rsp+380h+LogonId]; LogonId
0x180052311  call    cs:__imp_LsaGetLogonSessionData
0x180052317  test    eax, eax
0x180052319  js      short loc_180052388
0x18005231b  mov     rcx, [rsp+380h+ppLogonSessionData]
0x180052320  test    rcx, rcx
0x180052323  jz      short loc_180052388
0x180052325  lea     rax, [rcx+10h]
0x180052329  test    rax, rax
0x18005232c  jz      short loc_180052352
0x18005232e  mov     rdx, [rcx+18h]
0x180052332  test    rdx, rdx
0x180052335  jz      short loc_180052352
0x180052337  movzx   r8d, word ptr [rax]
0x18005233b  test    r8w, r8w
0x18005233f  jz      short loc_180052352
0x180052341  lea     eax, [r8+2]
0x180052345  mov     [rbp+280h+var_280], rdx
0x180052349  mov     dword ptr [rbp+280h+var_278], eax
0x18005234c  mov     dword ptr [rbp+280h+var_278+4], r12d
0x180052350  jmp     short loc_18005235E
0x180052352  mov     [rbp+280h+var_280], r13
0x180052356  mov     [rbp+280h+var_278], 0Eh
0x18005235e  lea     rax, [rcx+20h]
0x180052362  test    rax, rax
0x180052365  jz      short loc_180052394
0x180052367  mov     rdx, [rcx+28h]
0x18005236b  test    rdx, rdx
0x18005236e  jz      short loc_180052394
0x180052370  movzx   ecx, word ptr [rax]
0x180052373  test    cx, cx
0x180052376  jz      short loc_180052394
0x180052378  lea     eax, [rcx+2]
0x18005237b  mov     [rbp+280h+var_270], rdx
0x18005237f  mov     dword ptr [rbp+280h+var_268], eax
0x180052382  mov     dword ptr [rbp+280h+var_268+4], r12d
0x180052386  jmp     short loc_1800523A0
0x180052388  mov     [rbp+280h+var_280], r13
0x18005238c  mov     [rbp+280h+var_278], 0Eh
0x180052394  mov     [rbp+280h+var_268], 0Eh
0x18005239c  mov     [rbp+280h+var_270], r13
0x1800523a0  mov     rax, cs:LsaFunctions
0x1800523a7  lea     rcx, [rbp+280h+var_2F8]
0x1800523ab  mov     rax, [rax+0C0h]
0x1800523b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800523b7  test    al, al
0x1800523b9  jz      short loc_1800523F4
0x1800523bb  mov     rcx, [rbp+280h+var_2E8]; struct ASN1objectidentifier_s *
0x1800523bf  lea     rdx, [rsp+380h+var_358]; unsigned __int16 **
0x1800523c4  call    ?SspOIDToString@@YAHPEAUASN1objectidentifier_s@@PEAPEAG@Z; SspOIDToString(ASN1objectidentifier_s *,ushort * *)
0x1800523c9  mov     r14, [rsp+380h+var_358]
0x1800523ce  test    eax, eax
0x1800523d0  jz      short loc_1800523F4
0x1800523d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800523d6  inc     rax
0x1800523d9  cmp     [r14+rax*2], r12w
0x1800523de  jnz     short loc_1800523D6
0x1800523e0  lea     eax, ds:2[rax*2]
0x1800523e7  mov     [rbp+280h+var_260], r14
0x1800523eb  mov     dword ptr [rbp+280h+var_258], eax
0x1800523ee  mov     dword ptr [rbp+280h+var_258+4], r12d
0x1800523f2  jmp     short loc_180052400
0x1800523f4  mov     [rbp+280h+var_260], r13
0x1800523f8  mov     [rbp+280h+var_258], 0Eh
0x180052400  mov     rcx, cs:MsvEtwLogHandle
0x180052407  lea     r9, [rbp+280h+var_2E0]
0x18005240b  mov     r8d, 9
0x180052411  lea     rdx, NTLMv1BlockedByCredGuard
0x180052418  call    cs:__imp_EtwEventWrite
0x18005241e  test    r15, r15
0x180052421  jz      short loc_18005243D
0x180052423  mov     rcx, r15; hObject
0x180052426  call    cs:__imp_CloseHandle
0x18005242c  jmp     short loc_18005243D
0x18005242e  mov     rsi, qword ptr [rsp+380h+var_348+8]
0x180052433  mov     rbx, qword ptr [rsp+380h+var_338+8]
0x180052438  mov     rdi, qword ptr [rsp+380h+var_328+8]
0x18005243d  mov     rcx, [rsp+380h+ppLogonSessionData]; Buffer
0x180052442  test    rcx, rcx
0x180052445  jz      short loc_18005244D
0x180052447  call    cs:__imp_LsaFreeReturnBuffer
0x18005244d  test    r14, r14
0x180052450  jz      short loc_180052468
0x180052452  mov     rax, cs:LsaFunctions
0x180052459  mov     rcx, r14
0x18005245c  mov     rax, [rax+188h]
0x180052463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052468  test    rsi, rsi
0x18005246b  jz      short loc_180052483
0x18005246d  mov     rax, cs:LsaFunctions
0x180052474  mov     rcx, rsi
0x180052477  mov     rax, [rax+188h]
0x18005247e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052483  test    rdi, rdi
0x180052486  jz      short loc_18005249E
0x180052488  mov     rax, cs:LsaFunctions
0x18005248f  mov     rcx, rdi
0x180052492  mov     rax, [rax+188h]
0x180052499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005249e  test    rbx, rbx
0x1800524a1  jz      short loc_1800524B9
0x1800524a3  mov     rax, cs:LsaFunctions
0x1800524aa  mov     rcx, rbx
0x1800524ad  mov     rax, [rax+188h]
0x1800524b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800524b9  mov     rcx, [rbp+280h+var_40]
0x1800524c0  xor     rcx, rsp; StackCookie
0x1800524c3  call    __security_check_cookie
0x1800524c8  mov     rbx, [rsp+380h+arg_18]
0x1800524d0  add     rsp, 350h
0x1800524d7  pop     r15
0x1800524d9  pop     r14
0x1800524db  pop     r13
0x1800524dd  pop     r12
0x1800524df  pop     rdi
0x1800524e0  pop     rsi
0x1800524e1  pop     rbp
0x1800524e2  retn
```
