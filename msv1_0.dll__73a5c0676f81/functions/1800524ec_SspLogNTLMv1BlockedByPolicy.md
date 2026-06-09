# SspLogNTLMv1BlockedByPolicy

- ea: `0x1800524ec`
- end: `0x18005293e`
- name: `SspLogNTLMv1BlockedByPolicy`
- size: `1106`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024c00`

## callees

- `0x18000cba0`
- `0x18002e3e8`
- `0x18002fb50`
- `0x180030844`
- `0x180051104`
- `0x1800524ec`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052881`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052881`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800526d6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800526d6`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800526f2`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800526f2`
- `ntdll!EtwEventEnabled` at `0x1800525b0`
- `ntdll!EtwEventEnabled` at `0x1800525b0`
- `ntdll!EtwEventWrite` at `0x180052873`
- `ntdll!EtwEventWrite` at `0x180052873`
- `SspiCli!LsaGetLogonSessionData` at `0x18005274a`
- `SspiCli!LsaGetLogonSessionData` at `0x18005274a`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800528a2`
- `SspiCli!LsaFreeReturnBuffer` at `0x1800528a2`

## pseudocode

```c
int __fastcall SspLogNTLMv1BlockedByPolicy(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int16 *v6; // r14
  int result; // eax
  __int64 *v8; // r12
  __int64 v9; // rsi
  __int64 v10; // rdi
  __int64 v11; // rbx
  HANDLE v12; // rax
  void *v13; // r15
  PWSTR v14; // rdx
  const wchar_t *v15; // r8
  int Length; // r8d
  int v17; // ecx
  int v18; // eax
  __int64 v19; // rax
  DWORD dwSize; // [rsp+20h] [rbp-E0h] BYREF
  DWORD LowPart; // [rsp+24h] [rbp-DCh] BYREF
  unsigned __int16 *v22; // [rsp+28h] [rbp-D8h] BYREF
  PSECURITY_LOGON_SESSION_DATA ppLogonSessionData; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v25; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v26; // [rsp+58h] [rbp-A8h] BYREF
  struct _LUID LogonId[4]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v28; // [rsp+88h] [rbp-78h] BYREF
  struct ASN1objectidentifier_s *v29; // [rsp+98h] [rbp-68h]
  const wchar_t *v30; // [rsp+A0h] [rbp-60h]
  __int64 v31; // [rsp+A8h] [rbp-58h] BYREF
  const wchar_t *v32; // [rsp+B0h] [rbp-50h]
  __int64 v33; // [rsp+B8h] [rbp-48h]
  const wchar_t *v34; // [rsp+C0h] [rbp-40h]
  __int64 v35; // [rsp+C8h] [rbp-38h]
  DWORD *v36; // [rsp+D0h] [rbp-30h]
  __int64 v37; // [rsp+D8h] [rbp-28h]
  WCHAR *v38; // [rsp+E0h] [rbp-20h]
  __int64 v39; // [rsp+E8h] [rbp-18h]
  struct _LUID *v40; // [rsp+F0h] [rbp-10h]
  __int64 v41; // [rsp+F8h] [rbp-8h]
  PWSTR Buffer; // [rsp+100h] [rbp+0h]
  __int64 v43; // [rsp+108h] [rbp+8h]
  PWSTR v44; // [rsp+110h] [rbp+10h]
  __int64 v45; // [rsp+118h] [rbp+18h]
  unsigned __int16 *v46; // [rsp+120h] [rbp+20h]
  __int64 v47; // [rsp+128h] [rbp+28h]
  WCHAR ExeName[264]; // [rsp+130h] [rbp+30h] BYREF

  v30 = 0;
  memset_0(&v31, 0, 0x88u);
  dwSize = 261;
  memset(LogonId, 0, sizeof(LogonId));
  v29 = 0;
  v6 = 0;
  v22 = 0;
  ppLogonSessionData = 0;
  v28 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  result = SspInitEtwLogHandle();
  if ( result < 0 )
    goto LABEL_48;
  v8 = NTLMv1CredBlockedByPolicy;
  if ( !NtLmGlobalBlockNtlmv1SSO )
    v8 = NTLMv1CredAuditedByPolicy;
  result = EtwEventEnabled(MsvEtwLogHandle, v8);
  if ( (_BYTE)result )
  {
    result = NtLmDuplicateUnicodeString(&v26, a2);
    if ( result >= 0 )
    {
      result = NtLmDuplicateUnicodeString(&v25, a3);
      if ( result >= 0 )
      {
        result = NtLmDuplicateUnicodeString(&v24, a1);
        if ( result >= 0 )
        {
          v9 = *((_QWORD *)&v24 + 1);
          if ( *((_QWORD *)&v24 + 1) && (_WORD)v24 )
          {
            v30 = (const wchar_t *)*((_QWORD *)&v24 + 1);
            v31 = (unsigned int)(unsigned __int16)v24 + 2;
          }
          else
          {
            v30 = L"(NULL)";
            v31 = 14;
          }
          v10 = *((_QWORD *)&v26 + 1);
          if ( *((_QWORD *)&v26 + 1) && (_WORD)v26 )
          {
            v32 = (const wchar_t *)*((_QWORD *)&v26 + 1);
            v33 = (unsigned int)(unsigned __int16)v26 + 2;
          }
          else
          {
            v32 = L"(NULL)";
            v33 = 14;
          }
          v11 = *((_QWORD *)&v25 + 1);
          if ( *((_QWORD *)&v25 + 1) && (_WORD)v25 )
          {
            v34 = (const wchar_t *)*((_QWORD *)&v25 + 1);
            v35 = (unsigned int)(unsigned __int16)v25 + 2;
          }
          else
          {
            v34 = L"(NULL)";
            v35 = 14;
          }
          result = ((__int64 (__fastcall *)(struct _LUID *))LsaFunctions->GetClientInfo)(LogonId);
          if ( result >= 0 )
          {
            v36 = &LowPart;
            LowPart = LogonId[1].LowPart;
            v37 = 4;
            v12 = OpenProcess(0x1000u, 0, LogonId[1].LowPart);
            v13 = v12;
            if ( v12 && QueryFullProcessImageNameW(v12, 0, ExeName, &dwSize) && dwSize )
            {
              v38 = ExeName;
              v39 = 2 * dwSize + 2;
            }
            else
            {
              v39 = 4;
              v38 = L"-";
            }
            v41 = 8;
            v40 = LogonId;
            if ( LsaGetLogonSessionData(LogonId, &ppLogonSessionData) >= 0 && ppLogonSessionData )
            {
              if ( ppLogonSessionData != (PSECURITY_LOGON_SESSION_DATA)-16LL
                && (v14 = ppLogonSessionData->UserName.Buffer) != 0
                && (Length = ppLogonSessionData->UserName.Length, (_WORD)Length) )
              {
                Buffer = ppLogonSessionData->UserName.Buffer;
                v43 = (unsigned int)(Length + 2);
                v15 = L"(NULL)";
              }
              else
              {
                v15 = L"(NULL)";
                v43 = 14;
                Buffer = L"(NULL)";
              }
              if ( ppLogonSessionData != (PSECURITY_LOGON_SESSION_DATA)-32LL )
              {
                v14 = ppLogonSessionData->LogonDomain.Buffer;
                if ( v14 )
                {
                  v17 = ppLogonSessionData->LogonDomain.Length;
                  if ( (_WORD)v17 )
                  {
                    v44 = ppLogonSessionData->LogonDomain.Buffer;
                    v45 = (unsigned int)(v17 + 2);
LABEL_40:
                    if ( ((unsigned __int8 (__fastcall *)(__int128 *, PWSTR, const wchar_t *))LsaFunctions->GetCallInfo)(
                           &v28,
                           v14,
                           v15)
                      && (v18 = SspOIDToString(v29, &v22), v6 = v22, v18) )
                    {
                      v19 = -1;
                      do
                        ++v19;
                      while ( v22[v19] );
                      v46 = v22;
                      v47 = (unsigned int)(2 * v19 + 2);
                    }
                    else
                    {
                      v47 = 14;
                      v46 = L"(NULL)";
                    }
                    result = EtwEventWrite(MsvEtwLogHandle, v8, 9);
                    if ( v13 )
                      result = CloseHandle(v13);
                    goto LABEL_49;
                  }
                }
              }
              v44 = L"(NULL)";
            }
            else
            {
              v43 = 14;
              Buffer = L"(NULL)";
              v44 = L"(NULL)";
            }
            v45 = 14;
            goto LABEL_40;
          }
LABEL_49:
          if ( ppLogonSessionData )
            result = LsaFreeReturnBuffer(ppLogonSessionData);
          if ( v6 )
            result = ((__int64 (__fastcall *)(unsigned __int16 *))LsaFunctions->FreePrivateHeap)(v6);
          if ( v9 )
            result = ((__int64 (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(v9);
          if ( v10 )
            result = ((__int64 (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(v10);
          if ( v11 )
            return ((__int64 (__fastcall *)(__int64))LsaFunctions->FreePrivateHeap)(v11);
          return result;
        }
      }
    }
LABEL_48:
    v9 = *((_QWORD *)&v24 + 1);
    v11 = *((_QWORD *)&v25 + 1);
    v10 = *((_QWORD *)&v26 + 1);
    goto LABEL_49;
  }
  return result;
}

```

## disassembly

```asm
0x1800524ec  mov     [rsp-8+arg_18], rbx
0x1800524f1  push    rbp
0x1800524f2  push    rsi
0x1800524f3  push    rdi
0x1800524f4  push    r12
0x1800524f6  push    r13
0x1800524f8  push    r14
0x1800524fa  push    r15
0x1800524fc  lea     rbp, [rsp-250h]
0x180052504  sub     rsp, 350h
0x18005250b  mov     rax, cs:__security_cookie
0x180052512  xor     rax, rsp
0x180052515  mov     [rbp+280h+var_40], rax
0x18005251c  mov     rdi, r8
0x18005251f  mov     rbx, rdx
0x180052522  mov     rsi, rcx
0x180052525  xor     r13d, r13d
0x180052528  xor     edx, edx; Val
0x18005252a  mov     [rbp+280h+var_2E0], r13
0x18005252e  mov     r8d, 88h; Size
0x180052534  lea     rcx, [rbp+280h+var_2D8]; void *
0x180052538  call    memset_0
0x18005253d  xorps   xmm0, xmm0
0x180052540  mov     [rsp+380h+dwSize], 105h
0x180052548  xor     eax, eax
0x18005254a  mov     dword ptr [rsp+380h+LogonId], r13d
0x18005254f  xorps   xmm1, xmm1
0x180052552  mov     [rbp+280h+var_2E8], rax
0x180052556  movups  xmmword ptr [rsp+380h+LogonId+4], xmm0
0x18005255b  mov     r14d, r13d
0x18005255e  mov     [rsp+380h+var_358], r13
0x180052563  movups  xmmword ptr [rsp+380h+LogonId+10h], xmm0
0x180052568  mov     [rsp+380h+ppLogonSessionData], r13
0x18005256d  movups  [rbp+280h+var_2F8], xmm0
0x180052571  movups  [rsp+380h+var_348], xmm0
0x180052576  movups  [rsp+380h+var_338], xmm1
0x18005257b  movups  [rsp+380h+var_328], xmm0
0x180052580  call    SspInitEtwLogHandle
0x180052585  test    eax, eax
0x180052587  js      loc_180052889
0x18005258d  cmp     cs:NtLmGlobalBlockNtlmv1SSO, r13b
0x180052594  lea     rax, NTLMv1CredAuditedByPolicy
0x18005259b  mov     rcx, cs:MsvEtwLogHandle
0x1800525a2  lea     r12, NTLMv1CredBlockedByPolicy
0x1800525a9  cmovz   r12, rax
0x1800525ad  mov     rdx, r12
0x1800525b0  call    cs:__imp_EtwEventEnabled
0x1800525b6  test    al, al
0x1800525b8  jz      loc_180052914
0x1800525be  mov     rdx, rbx
0x1800525c1  lea     rcx, [rsp+380h+var_328]
0x1800525c6  call    NtLmDuplicateUnicodeString
0x1800525cb  test    eax, eax
0x1800525cd  js      loc_180052889
0x1800525d3  mov     rdx, rdi
0x1800525d6  lea     rcx, [rsp+380h+var_338]
0x1800525db  call    NtLmDuplicateUnicodeString
0x1800525e0  test    eax, eax
0x1800525e2  js      loc_180052889
0x1800525e8  mov     rdx, rsi
0x1800525eb  lea     rcx, [rsp+380h+var_348]
0x1800525f0  call    NtLmDuplicateUnicodeString
0x1800525f5  test    eax, eax
0x1800525f7  js      loc_180052889
0x1800525fd  mov     rsi, qword ptr [rsp+380h+var_348+8]
0x180052602  lea     rcx, aNull; "(NULL)"
0x180052609  test    rsi, rsi
0x18005260c  jz      short loc_180052628
0x18005260e  movzx   eax, word ptr [rsp+380h+var_348]
0x180052613  test    ax, ax
0x180052616  jz      short loc_180052628
0x180052618  add     eax, 2
0x18005261b  mov     [rbp+280h+var_2E0], rsi
0x18005261f  mov     dword ptr [rbp+280h+var_2D8], eax
0x180052622  mov     dword ptr [rbp+280h+var_2D8+4], r13d
0x180052626  jmp     short loc_180052634
0x180052628  mov     [rbp+280h+var_2E0], rcx
0x18005262c  mov     [rbp+280h+var_2D8], 0Eh
0x180052634  mov     rdi, qword ptr [rsp+380h+var_328+8]
0x180052639  test    rdi, rdi
0x18005263c  jz      short loc_180052658
0x18005263e  movzx   eax, word ptr [rsp+380h+var_328]
0x180052643  test    ax, ax
0x180052646  jz      short loc_180052658
0x180052648  add     eax, 2
0x18005264b  mov     [rbp+280h+var_2D0], rdi
0x18005264f  mov     dword ptr [rbp+280h+var_2C8], eax
0x180052652  mov     dword ptr [rbp+280h+var_2C8+4], r13d
0x180052656  jmp     short loc_180052664
0x180052658  mov     [rbp+280h+var_2D0], rcx
0x18005265c  mov     [rbp+280h+var_2C8], 0Eh
0x180052664  mov     rbx, qword ptr [rsp+380h+var_338+8]
0x180052669  test    rbx, rbx
0x18005266c  jz      short loc_180052688
0x18005266e  movzx   eax, word ptr [rsp+380h+var_338]
0x180052673  test    ax, ax
0x180052676  jz      short loc_180052688
0x180052678  add     eax, 2
0x18005267b  mov     [rbp+280h+var_2C0], rbx
0x18005267f  mov     dword ptr [rbp+280h+var_2B8], eax
0x180052682  mov     dword ptr [rbp+280h+var_2B8+4], r13d
0x180052686  jmp     short loc_180052694
0x180052688  mov     [rbp+280h+var_2C0], rcx
0x18005268c  mov     [rbp+280h+var_2B8], 0Eh
0x180052694  mov     rax, cs:LsaFunctions
0x18005269b  lea     rcx, [rsp+380h+LogonId]
0x1800526a0  mov     rax, [rax+80h]
0x1800526a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800526ac  test    eax, eax
0x1800526ae  js      loc_180052898
0x1800526b4  mov     r8d, dword ptr [rsp+380h+LogonId+8]; dwProcessId
0x1800526b9  lea     rax, [rsp+380h+var_35C]
0x1800526be  xor     edx, edx; bInheritHandle
0x1800526c0  mov     [rbp+280h+var_2B0], rax
0x1800526c4  mov     ecx, 1000h; dwDesiredAccess
0x1800526c9  mov     [rsp+380h+var_35C], r8d
0x1800526ce  mov     [rbp+280h+var_2A8], 4
0x1800526d6  call    cs:__imp_OpenProcess
0x1800526dc  mov     r15, rax
0x1800526df  test    rax, rax
0x1800526e2  jz      short loc_18005271C
0x1800526e4  lea     r9, [rsp+380h+dwSize]; lpdwSize
0x1800526e9  xor     edx, edx; dwFlags
0x1800526eb  lea     r8, [rbp+280h+ExeName]; lpExeName
0x1800526ef  mov     rcx, rax; hProcess
0x1800526f2  call    cs:__imp_QueryFullProcessImageNameW
0x1800526f8  test    eax, eax
0x1800526fa  jz      short loc_18005271C
0x1800526fc  mov     eax, [rsp+380h+dwSize]
0x180052700  test    eax, eax
0x180052702  jz      short loc_18005271C
0x180052704  lea     rcx, [rbp+280h+ExeName]
0x180052708  mov     dword ptr [rbp+280h+var_298+4], r13d
0x18005270c  lea     eax, ds:2[rax*2]
0x180052713  mov     [rbp+280h+var_2A0], rcx
0x180052717  mov     dword ptr [rbp+280h+var_298], eax
0x18005271a  jmp     short loc_18005272F
0x18005271c  lea     rax, asc_1800745A0; "-"
0x180052723  mov     [rbp+280h+var_298], 4
0x18005272b  mov     [rbp+280h+var_2A0], rax
0x18005272f  lea     rax, [rsp+380h+LogonId]
0x180052734  mov     [rbp+280h+var_288], 8
0x18005273c  lea     rdx, [rsp+380h+ppLogonSessionData]; ppLogonSessionData
0x180052741  mov     [rbp+280h+var_290], rax
0x180052745  lea     rcx, [rsp+380h+LogonId]; LogonId
0x18005274a  call    cs:__imp_LsaGetLogonSessionData
0x180052750  test    eax, eax
0x180052752  js      loc_1800527D9
0x180052758  mov     rcx, [rsp+380h+ppLogonSessionData]
0x18005275d  test    rcx, rcx
0x180052760  jz      short loc_1800527D9
0x180052762  lea     rax, [rcx+10h]
0x180052766  test    rax, rax
0x180052769  jz      short loc_180052796
0x18005276b  mov     rdx, [rcx+18h]
0x18005276f  test    rdx, rdx
0x180052772  jz      short loc_180052796
0x180052774  movzx   r8d, word ptr [rax]
0x180052778  test    r8w, r8w
0x18005277c  jz      short loc_180052796
0x18005277e  lea     eax, [r8+2]
0x180052782  mov     [rbp+280h+var_280], rdx
0x180052786  mov     dword ptr [rbp+280h+var_278], eax
0x180052789  lea     r8, aNull; "(NULL)"
0x180052790  mov     dword ptr [rbp+280h+var_278+4], r13d
0x180052794  jmp     short loc_1800527A9
0x180052796  lea     r8, aNull; "(NULL)"
0x18005279d  mov     [rbp+280h+var_278], 0Eh
0x1800527a5  mov     [rbp+280h+var_280], r8
0x1800527a9  lea     rax, [rcx+20h]
0x1800527ad  test    rax, rax
0x1800527b0  jz      short loc_1800527D3
0x1800527b2  mov     rdx, [rcx+28h]
0x1800527b6  test    rdx, rdx
0x1800527b9  jz      short loc_1800527D3
0x1800527bb  movzx   ecx, word ptr [rax]
0x1800527be  test    cx, cx
0x1800527c1  jz      short loc_1800527D3
0x1800527c3  lea     eax, [rcx+2]
0x1800527c6  mov     [rbp+280h+var_270], rdx
0x1800527ca  mov     dword ptr [rbp+280h+var_268], eax
0x1800527cd  mov     dword ptr [rbp+280h+var_268+4], r13d
0x1800527d1  jmp     short loc_1800527F8
0x1800527d3  mov     [rbp+280h+var_270], r8
0x1800527d7  jmp     short loc_1800527F0
0x1800527d9  lea     rax, aNull; "(NULL)"
0x1800527e0  mov     [rbp+280h+var_278], 0Eh
0x1800527e8  mov     [rbp+280h+var_280], rax
0x1800527ec  mov     [rbp+280h+var_270], rax
0x1800527f0  mov     [rbp+280h+var_268], 0Eh
0x1800527f8  mov     rax, cs:LsaFunctions
0x1800527ff  lea     rcx, [rbp+280h+var_2F8]
0x180052803  mov     rax, [rax+0C0h]
0x18005280a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005280f  test    al, al
0x180052811  jz      short loc_18005284C
0x180052813  mov     rcx, [rbp+280h+var_2E8]; struct ASN1objectidentifier_s *
0x180052817  lea     rdx, [rsp+380h+var_358]; unsigned __int16 **
0x18005281c  call    ?SspOIDToString@@YAHPEAUASN1objectidentifier_s@@PEAPEAG@Z; SspOIDToString(ASN1objectidentifier_s *,ushort * *)
0x180052821  mov     r14, [rsp+380h+var_358]
0x180052826  test    eax, eax
0x180052828  jz      short loc_18005284C
0x18005282a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005282e  inc     rax
0x180052831  cmp     [r14+rax*2], r13w
0x180052836  jnz     short loc_18005282E
0x180052838  lea     eax, ds:2[rax*2]
0x18005283f  mov     [rbp+280h+var_260], r14
0x180052843  mov     dword ptr [rbp+280h+var_258], eax
0x180052846  mov     dword ptr [rbp+280h+var_258+4], r13d
0x18005284a  jmp     short loc_18005285F
0x18005284c  lea     rax, aNull; "(NULL)"
0x180052853  mov     [rbp+280h+var_258], 0Eh
0x18005285b  mov     [rbp+280h+var_260], rax
0x18005285f  mov     rcx, cs:MsvEtwLogHandle
0x180052866  lea     r9, [rbp+280h+var_2E0]
0x18005286a  mov     r8d, 9
0x180052870  mov     rdx, r12
0x180052873  call    cs:__imp_EtwEventWrite
0x180052879  test    r15, r15
0x18005287c  jz      short loc_180052898
0x18005287e  mov     rcx, r15; hObject
0x180052881  call    cs:__imp_CloseHandle
0x180052887  jmp     short loc_180052898
0x180052889  mov     rsi, qword ptr [rsp+380h+var_348+8]
0x18005288e  mov     rbx, qword ptr [rsp+380h+var_338+8]
0x180052893  mov     rdi, qword ptr [rsp+380h+var_328+8]
0x180052898  mov     rcx, [rsp+380h+ppLogonSessionData]; Buffer
0x18005289d  test    rcx, rcx
0x1800528a0  jz      short loc_1800528A8
0x1800528a2  call    cs:__imp_LsaFreeReturnBuffer
0x1800528a8  test    r14, r14
0x1800528ab  jz      short loc_1800528C3
0x1800528ad  mov     rax, cs:LsaFunctions
0x1800528b4  mov     rcx, r14
0x1800528b7  mov     rax, [rax+188h]
0x1800528be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800528c3  test    rsi, rsi
0x1800528c6  jz      short loc_1800528DE
0x1800528c8  mov     rax, cs:LsaFunctions
0x1800528cf  mov     rcx, rsi
0x1800528d2  mov     rax, [rax+188h]
0x1800528d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800528de  test    rdi, rdi
0x1800528e1  jz      short loc_1800528F9
0x1800528e3  mov     rax, cs:LsaFunctions
0x1800528ea  mov     rcx, rdi
0x1800528ed  mov     rax, [rax+188h]
0x1800528f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800528f9  test    rbx, rbx
0x1800528fc  jz      short loc_180052914
0x1800528fe  mov     rax, cs:LsaFunctions
0x180052905  mov     rcx, rbx
0x180052908  mov     rax, [rax+188h]
0x18005290f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052914  mov     rcx, [rbp+280h+var_40]
0x18005291b  xor     rcx, rsp; StackCookie
0x18005291e  call    __security_check_cookie
0x180052923  mov     rbx, [rsp+380h+arg_18]
0x18005292b  add     rsp, 350h
0x180052932  pop     r15
0x180052934  pop     r14
0x180052936  pop     r13
0x180052938  pop     r12
0x18005293a  pop     rdi
0x18005293b  pop     rsi
0x18005293c  pop     rbp
0x18005293d  retn
```
