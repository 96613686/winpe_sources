# SspLogNTLMClientBlockedWorker

- ea: `0x1800513c4`
- end: `0x1800517cc`
- name: `SspLogNTLMClientBlockedWorker`
- size: `1032`
- prototype: `__int64 __fastcall(int, int, int, int, PLUID LogonId, __int64, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800268dc`
- `0x180051358`

## callees

- `0x18000cba0`
- `0x18002e3e8`
- `0x18002fb50`
- `0x180050d80`
- `0x180051104`
- `0x1800513c4`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051716`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051716`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005156e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005156e`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18005158a`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x18005158a`
- `ntdll!EtwEventEnabled` at `0x18005146d`
- `ntdll!EtwEventEnabled` at `0x18005146d`
- `ntdll!EtwEventWrite` at `0x180051708`
- `ntdll!EtwEventWrite` at `0x180051708`
- `SspiCli!LsaGetLogonSessionData` at `0x1800515db`
- `SspiCli!LsaGetLogonSessionData` at `0x1800515db`
- `SspiCli!LsaFreeReturnBuffer` at `0x180051737`
- `SspiCli!LsaFreeReturnBuffer` at `0x180051737`

## pseudocode

```c
int __fastcall SspLogNTLMClientBlockedWorker(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        DWORD a4,
        PLUID LogonId,
        __int64 a6,
        int a7)
{
  unsigned __int16 *v10; // r14
  int result; // eax
  __int64 v12; // rsi
  __int64 v13; // rdi
  __int64 v14; // rbx
  HANDLE v15; // rax
  void *v16; // r15
  PWSTR v17; // rdx
  const wchar_t *v18; // r8
  int Length; // r8d
  int v20; // ecx
  int v21; // eax
  __int64 v22; // rax
  DWORD dwProcessId; // [rsp+20h] [rbp-E0h] BYREF
  DWORD dwSize; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v25; // [rsp+30h] [rbp-D0h] BYREF
  PSECURITY_LOGON_SESSION_DATA ppLogonSessionData; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v27; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v28; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v29; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v30; // [rsp+70h] [rbp-90h] BYREF
  struct ASN1objectidentifier_s *v31; // [rsp+80h] [rbp-80h]
  const wchar_t *v32; // [rsp+90h] [rbp-70h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  const wchar_t *v34; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  const wchar_t *v36; // [rsp+B0h] [rbp-50h]
  __int64 v37; // [rsp+B8h] [rbp-48h]
  DWORD *p_dwProcessId; // [rsp+C0h] [rbp-40h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  WCHAR *v40; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  PLUID v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  PWSTR Buffer; // [rsp+F0h] [rbp-10h]
  __int64 v45; // [rsp+F8h] [rbp-8h]
  PWSTR v46; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+108h] [rbp+8h]
  unsigned __int16 *v48; // [rsp+110h] [rbp+10h]
  __int64 v49; // [rsp+118h] [rbp+18h]
  WCHAR ExeName[264]; // [rsp+120h] [rbp+20h] BYREF

  dwProcessId = a4;
  v10 = 0;
  dwSize = 261;
  v30 = 0;
  v31 = 0;
  v25 = 0;
  v27 = 0;
  ppLogonSessionData = 0;
  v28 = 0;
  v29 = 0;
  if ( a7 )
    MsvPingWlBalloon(LogonId);
  result = SspInitEtwLogHandle();
  if ( result >= 0 )
  {
    result = EtwEventEnabled(MsvEtwLogHandle, a6);
    if ( !(_BYTE)result )
      return result;
    result = NtLmDuplicateUnicodeString(&v29, a2);
    if ( result >= 0 )
    {
      result = NtLmDuplicateUnicodeString(&v28, a3);
      if ( result >= 0 )
      {
        result = NtLmDuplicateUnicodeString(&v27, a1);
        if ( result >= 0 )
        {
          v12 = *((_QWORD *)&v27 + 1);
          if ( *((_QWORD *)&v27 + 1) && (_WORD)v27 )
          {
            v32 = (const wchar_t *)*((_QWORD *)&v27 + 1);
            v33 = (unsigned int)(unsigned __int16)v27 + 2;
          }
          else
          {
            v32 = L"(NULL)";
            v33 = 14;
          }
          v13 = *((_QWORD *)&v29 + 1);
          if ( *((_QWORD *)&v29 + 1) && (_WORD)v29 )
          {
            v34 = (const wchar_t *)*((_QWORD *)&v29 + 1);
            v35 = (unsigned int)(unsigned __int16)v29 + 2;
          }
          else
          {
            v34 = L"(NULL)";
            v35 = 14;
          }
          v14 = *((_QWORD *)&v28 + 1);
          if ( *((_QWORD *)&v28 + 1) && (_WORD)v28 )
          {
            v36 = (const wchar_t *)*((_QWORD *)&v28 + 1);
            v37 = (unsigned int)(unsigned __int16)v28 + 2;
          }
          else
          {
            v36 = L"(NULL)";
            v37 = 14;
          }
          p_dwProcessId = &dwProcessId;
          v39 = 4;
          v15 = OpenProcess(0x1000u, 0, dwProcessId);
          v16 = v15;
          if ( v15 && QueryFullProcessImageNameW(v15, 0, ExeName, &dwSize) && dwSize )
          {
            v40 = ExeName;
            v41 = 2 * dwSize + 2;
          }
          else
          {
            v41 = 4;
            v40 = L"-";
          }
          v42 = LogonId;
          v43 = 8;
          if ( LsaGetLogonSessionData(LogonId, &ppLogonSessionData) >= 0 && ppLogonSessionData )
          {
            if ( ppLogonSessionData != (PSECURITY_LOGON_SESSION_DATA)-16LL
              && (v17 = ppLogonSessionData->UserName.Buffer) != 0
              && (Length = ppLogonSessionData->UserName.Length, (_WORD)Length) )
            {
              Buffer = ppLogonSessionData->UserName.Buffer;
              v45 = (unsigned int)(Length + 2);
              v18 = L"(NULL)";
            }
            else
            {
              v18 = L"(NULL)";
              v45 = 14;
              Buffer = L"(NULL)";
            }
            if ( ppLogonSessionData != (PSECURITY_LOGON_SESSION_DATA)-32LL )
            {
              v17 = ppLogonSessionData->LogonDomain.Buffer;
              if ( v17 )
              {
                v20 = ppLogonSessionData->LogonDomain.Length;
                if ( (_WORD)v20 )
                {
                  v46 = ppLogonSessionData->LogonDomain.Buffer;
                  v47 = (unsigned int)(v20 + 2);
LABEL_39:
                  if ( ((unsigned __int8 (__fastcall *)(__int128 *, PWSTR, const wchar_t *))LsaFunctions->GetCallInfo)(
                         &v30,
                         v17,
                         v18)
                    && (v21 = SspOIDToString(v31, &v25), v10 = v25, v21) )
                  {
                    v22 = -1;
                    do
                      ++v22;
                    while ( v25[v22] );
                    v48 = v25;
                    v49 = (unsigned int)(2 * v22 + 2);
                  }
                  else
                  {
                    v49 = 14;
                    v48 = L"(NULL)";
                  }
                  result = EtwEventWrite(MsvEtwLogHandle, a6, 9);
                  if ( v16 )
                    result = CloseHandle(v16);
                  goto LABEL_48;
                }
              }
            }
            v46 = L"(NULL)";
          }
          else
          {
            v45 = 14;
            Buffer = L"(NULL)";
            v46 = L"(NULL)";
          }
          v47 = 14;
          goto LABEL_39;
        }
      }
    }
  }
  v12 = *((_QWORD *)&v27 + 1);
  v14 = *((_QWORD *)&v28 + 1);
  v13 = *((_QWORD *)&v29 + 1);
LABEL_48:
  if ( ppLogonSessionData )
    result = LsaFreeReturnBuffer(ppLogonSessionData);
  if ( v10 )
    result = ((__int64 (__fastcall *)(unsigned __int16 *))LsaFunctions->FreePrivateHeap)(v10);
  if ( v12 )
    result = ((__int64 (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(v12);
  if ( v13 )
    result = ((__int64 (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(v13);
  if ( v14 )
    return ((__int64 (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(v14);
  return result;
}

```

## disassembly

```asm
0x1800513c4  push    rbp
0x1800513c6  push    rbx
0x1800513c7  push    rsi
0x1800513c8  push    rdi
0x1800513c9  push    r12
0x1800513cb  push    r13
0x1800513cd  push    r14
0x1800513cf  push    r15
0x1800513d1  lea     rbp, [rsp-248h]
0x1800513d9  sub     rsp, 348h
0x1800513e0  mov     rax, cs:__security_cookie
0x1800513e7  xor     rax, rsp
0x1800513ea  mov     [rbp+280h+var_50], rax
0x1800513f1  mov     r12, [rbp+280h+LogonId]
0x1800513f8  xor     r15d, r15d
0x1800513fb  mov     r13, [rbp+280h+arg_28]
0x180051402  xorps   xmm0, xmm0
0x180051405  xor     eax, eax
0x180051407  mov     [rsp+380h+dwProcessId], r9d
0x18005140c  xorps   xmm1, xmm1
0x18005140f  mov     rdi, r8
0x180051412  mov     rbx, rdx
0x180051415  mov     rsi, rcx
0x180051418  mov     r14d, r15d
0x18005141b  mov     [rsp+380h+dwSize], 105h
0x180051423  movups  [rsp+380h+var_310], xmm0
0x180051428  mov     [rbp+280h+var_300], rax
0x18005142c  mov     [rsp+380h+var_350], r15
0x180051431  movups  [rsp+380h+var_340], xmm0
0x180051436  mov     [rsp+380h+ppLogonSessionData], r15
0x18005143b  movups  [rsp+380h+var_330], xmm1
0x180051440  movups  [rsp+380h+var_320], xmm0
0x180051445  cmp     [rbp+280h+arg_30], r15d
0x18005144c  jz      short loc_180051456
0x18005144e  mov     rcx, r12; struct _LUID *
0x180051451  call    ?MsvPingWlBalloon@@YAEPEAU_LUID@@@Z; MsvPingWlBalloon(_LUID *)
0x180051456  call    SspInitEtwLogHandle
0x18005145b  test    eax, eax
0x18005145d  js      loc_18005171E
0x180051463  mov     rcx, cs:MsvEtwLogHandle
0x18005146a  mov     rdx, r13
0x18005146d  call    cs:__imp_EtwEventEnabled
0x180051473  test    al, al
0x180051475  jz      loc_1800517A9
0x18005147b  mov     rdx, rbx
0x18005147e  lea     rcx, [rsp+380h+var_320]
0x180051483  call    NtLmDuplicateUnicodeString
0x180051488  test    eax, eax
0x18005148a  js      loc_18005171E
0x180051490  mov     rdx, rdi
0x180051493  lea     rcx, [rsp+380h+var_330]
0x180051498  call    NtLmDuplicateUnicodeString
0x18005149d  test    eax, eax
0x18005149f  js      loc_18005171E
0x1800514a5  mov     rdx, rsi
0x1800514a8  lea     rcx, [rsp+380h+var_340]
0x1800514ad  call    NtLmDuplicateUnicodeString
0x1800514b2  test    eax, eax
0x1800514b4  js      loc_18005171E
0x1800514ba  mov     rsi, qword ptr [rsp+380h+var_340+8]
0x1800514bf  lea     rcx, aNull; "(NULL)"
0x1800514c6  test    rsi, rsi
0x1800514c9  jz      short loc_1800514E5
0x1800514cb  movzx   eax, word ptr [rsp+380h+var_340]
0x1800514d0  test    ax, ax
0x1800514d3  jz      short loc_1800514E5
0x1800514d5  add     eax, 2
0x1800514d8  mov     [rbp+280h+var_2F0], rsi
0x1800514dc  mov     dword ptr [rbp+280h+var_2E8], eax
0x1800514df  mov     dword ptr [rbp+280h+var_2E8+4], r15d
0x1800514e3  jmp     short loc_1800514F1
0x1800514e5  mov     [rbp+280h+var_2F0], rcx
0x1800514e9  mov     [rbp+280h+var_2E8], 0Eh
0x1800514f1  mov     rdi, qword ptr [rsp+380h+var_320+8]
0x1800514f6  test    rdi, rdi
0x1800514f9  jz      short loc_180051515
0x1800514fb  movzx   eax, word ptr [rsp+380h+var_320]
0x180051500  test    ax, ax
0x180051503  jz      short loc_180051515
0x180051505  add     eax, 2
0x180051508  mov     [rbp+280h+var_2E0], rdi
0x18005150c  mov     dword ptr [rbp+280h+var_2D8], eax
0x18005150f  mov     dword ptr [rbp+280h+var_2D8+4], r15d
0x180051513  jmp     short loc_180051521
0x180051515  mov     [rbp+280h+var_2E0], rcx
0x180051519  mov     [rbp+280h+var_2D8], 0Eh
0x180051521  mov     rbx, qword ptr [rsp+380h+var_330+8]
0x180051526  test    rbx, rbx
0x180051529  jz      short loc_180051545
0x18005152b  movzx   eax, word ptr [rsp+380h+var_330]
0x180051530  test    ax, ax
0x180051533  jz      short loc_180051545
0x180051535  add     eax, 2
0x180051538  mov     [rbp+280h+var_2D0], rbx
0x18005153c  mov     dword ptr [rbp+280h+var_2C8], eax
0x18005153f  mov     dword ptr [rbp+280h+var_2C8+4], r15d
0x180051543  jmp     short loc_180051551
0x180051545  mov     [rbp+280h+var_2D0], rcx
0x180051549  mov     [rbp+280h+var_2C8], 0Eh
0x180051551  mov     r8d, [rsp+380h+dwProcessId]; dwProcessId
0x180051556  lea     rax, [rsp+380h+dwProcessId]
0x18005155b  xor     edx, edx; bInheritHandle
0x18005155d  mov     [rbp+280h+var_2C0], rax
0x180051561  mov     ecx, 1000h; dwDesiredAccess
0x180051566  mov     [rbp+280h+var_2B8], 4
0x18005156e  call    cs:__imp_OpenProcess
0x180051574  mov     r15, rax
0x180051577  test    rax, rax
0x18005157a  jz      short loc_1800515B4
0x18005157c  lea     r9, [rsp+380h+dwSize]; lpdwSize
0x180051581  xor     edx, edx; dwFlags
0x180051583  lea     r8, [rbp+280h+ExeName]; lpExeName
0x180051587  mov     rcx, rax; hProcess
0x18005158a  call    cs:__imp_QueryFullProcessImageNameW
0x180051590  test    eax, eax
0x180051592  jz      short loc_1800515B4
0x180051594  mov     eax, [rsp+380h+dwSize]
0x180051598  test    eax, eax
0x18005159a  jz      short loc_1800515B4
0x18005159c  lea     rcx, [rbp+280h+ExeName]
0x1800515a0  mov     dword ptr [rbp+280h+var_2A8+4], r14d
0x1800515a4  lea     eax, ds:2[rax*2]
0x1800515ab  mov     [rbp+280h+var_2B0], rcx
0x1800515af  mov     dword ptr [rbp+280h+var_2A8], eax
0x1800515b2  jmp     short loc_1800515C7
0x1800515b4  lea     rax, asc_1800745A0; "-"
0x1800515bb  mov     [rbp+280h+var_2A8], 4
0x1800515c3  mov     [rbp+280h+var_2B0], rax
0x1800515c7  lea     rdx, [rsp+380h+ppLogonSessionData]; ppLogonSessionData
0x1800515cc  mov     [rbp+280h+var_2A0], r12
0x1800515d0  mov     rcx, r12; LogonId
0x1800515d3  mov     [rbp+280h+var_298], 8
0x1800515db  call    cs:__imp_LsaGetLogonSessionData
0x1800515e1  xor     r12d, r12d
0x1800515e4  test    eax, eax
0x1800515e6  js      loc_18005166D
0x1800515ec  mov     rcx, [rsp+380h+ppLogonSessionData]
0x1800515f1  test    rcx, rcx
0x1800515f4  jz      short loc_18005166D
0x1800515f6  lea     rax, [rcx+10h]
0x1800515fa  test    rax, rax
0x1800515fd  jz      short loc_18005162A
0x1800515ff  mov     rdx, [rcx+18h]
0x180051603  test    rdx, rdx
0x180051606  jz      short loc_18005162A
0x180051608  movzx   r8d, word ptr [rax]
0x18005160c  test    r8w, r8w
0x180051610  jz      short loc_18005162A
0x180051612  lea     eax, [r8+2]
0x180051616  mov     [rbp+280h+var_290], rdx
0x18005161a  mov     dword ptr [rbp+280h+var_288], eax
0x18005161d  lea     r8, aNull; "(NULL)"
0x180051624  mov     dword ptr [rbp+280h+var_288+4], r12d
0x180051628  jmp     short loc_18005163D
0x18005162a  lea     r8, aNull; "(NULL)"
0x180051631  mov     [rbp+280h+var_288], 0Eh
0x180051639  mov     [rbp+280h+var_290], r8
0x18005163d  lea     rax, [rcx+20h]
0x180051641  test    rax, rax
0x180051644  jz      short loc_180051667
0x180051646  mov     rdx, [rcx+28h]
0x18005164a  test    rdx, rdx
0x18005164d  jz      short loc_180051667
0x18005164f  movzx   ecx, word ptr [rax]
0x180051652  test    cx, cx
0x180051655  jz      short loc_180051667
0x180051657  lea     eax, [rcx+2]
0x18005165a  mov     [rbp+280h+var_280], rdx
0x18005165e  mov     dword ptr [rbp+280h+var_278], eax
0x180051661  mov     dword ptr [rbp+280h+var_278+4], r12d
0x180051665  jmp     short loc_18005168C
0x180051667  mov     [rbp+280h+var_280], r8
0x18005166b  jmp     short loc_180051684
0x18005166d  lea     rax, aNull; "(NULL)"
0x180051674  mov     [rbp+280h+var_288], 0Eh
0x18005167c  mov     [rbp+280h+var_290], rax
0x180051680  mov     [rbp+280h+var_280], rax
0x180051684  mov     [rbp+280h+var_278], 0Eh
0x18005168c  mov     rax, cs:LsaFunctions
0x180051693  lea     rcx, [rsp+380h+var_310]
0x180051698  mov     rax, [rax+0C0h]
0x18005169f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516a4  test    al, al
0x1800516a6  jz      short loc_1800516E1
0x1800516a8  mov     rcx, [rbp+280h+var_300]; struct ASN1objectidentifier_s *
0x1800516ac  lea     rdx, [rsp+380h+var_350]; unsigned __int16 **
0x1800516b1  call    ?SspOIDToString@@YAHPEAUASN1objectidentifier_s@@PEAPEAG@Z; SspOIDToString(ASN1objectidentifier_s *,ushort * *)
0x1800516b6  mov     r14, [rsp+380h+var_350]
0x1800516bb  test    eax, eax
0x1800516bd  jz      short loc_1800516E1
0x1800516bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800516c3  inc     rax
0x1800516c6  cmp     [r14+rax*2], r12w
0x1800516cb  jnz     short loc_1800516C3
0x1800516cd  lea     eax, ds:2[rax*2]
0x1800516d4  mov     [rbp+280h+var_270], r14
0x1800516d8  mov     dword ptr [rbp+280h+var_268], eax
0x1800516db  mov     dword ptr [rbp+280h+var_268+4], r12d
0x1800516df  jmp     short loc_1800516F4
0x1800516e1  lea     rax, aNull; "(NULL)"
0x1800516e8  mov     [rbp+280h+var_268], 0Eh
0x1800516f0  mov     [rbp+280h+var_270], rax
0x1800516f4  mov     rcx, cs:MsvEtwLogHandle
0x1800516fb  lea     r9, [rbp+280h+var_2F0]
0x1800516ff  mov     r8d, 9
0x180051705  mov     rdx, r13
0x180051708  call    cs:__imp_EtwEventWrite
0x18005170e  test    r15, r15
0x180051711  jz      short loc_18005172D
0x180051713  mov     rcx, r15; hObject
0x180051716  call    cs:__imp_CloseHandle
0x18005171c  jmp     short loc_18005172D
0x18005171e  mov     rsi, qword ptr [rsp+380h+var_340+8]
0x180051723  mov     rbx, qword ptr [rsp+380h+var_330+8]
0x180051728  mov     rdi, qword ptr [rsp+380h+var_320+8]
0x18005172d  mov     rcx, [rsp+380h+ppLogonSessionData]; Buffer
0x180051732  test    rcx, rcx
0x180051735  jz      short loc_18005173D
0x180051737  call    cs:__imp_LsaFreeReturnBuffer
0x18005173d  test    r14, r14
0x180051740  jz      short loc_180051758
0x180051742  mov     rax, cs:LsaFunctions
0x180051749  mov     rcx, r14
0x18005174c  mov     rax, [rax+188h]
0x180051753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051758  test    rsi, rsi
0x18005175b  jz      short loc_180051773
0x18005175d  mov     rax, cs:LsaFunctions
0x180051764  mov     rcx, rsi
0x180051767  mov     rax, [rax+188h]
0x18005176e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051773  test    rdi, rdi
0x180051776  jz      short loc_18005178E
0x180051778  mov     rax, cs:LsaFunctions
0x18005177f  mov     rcx, rdi
0x180051782  mov     rax, [rax+188h]
0x180051789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005178e  test    rbx, rbx
0x180051791  jz      short loc_1800517A9
0x180051793  mov     rax, cs:LsaFunctions
0x18005179a  mov     rcx, rbx
0x18005179d  mov     rax, [rax+188h]
0x1800517a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800517a9  mov     rcx, [rbp+280h+var_50]
0x1800517b0  xor     rcx, rsp; StackCookie
0x1800517b3  call    __security_check_cookie
0x1800517b8  add     rsp, 348h
0x1800517bf  pop     r15
0x1800517c1  pop     r14
0x1800517c3  pop     r13
0x1800517c5  pop     r12
0x1800517c7  pop     rdi
0x1800517c8  pop     rsi
0x1800517c9  pop     rbx
0x1800517ca  pop     rbp
0x1800517cb  retn
```
