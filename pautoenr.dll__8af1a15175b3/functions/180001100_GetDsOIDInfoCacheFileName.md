# _GetDsOIDInfoCacheFileName

- ea: `0x180001100`
- end: `0x1800015c6`
- name: `_GetDsOIDInfoCacheFileName`
- size: `1222`
- prototype: `WCHAR *__fastcall(int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180001010`
- `0x1800050b0`

## callees

- `0x180001100`
- `0x180004e70`
- `0x180004fb0`
- `0x180005200`
- `0x1800052c0`
- `0x1800052f8`
- `0x1800077e4`
- `0x180007828`
- `0x180007994`
- `0x180007ce6`
- `0x180007d20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001507`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001220`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001507`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001211`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001233`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800012f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001465`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001478`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001211`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001233`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800012f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001465`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001478`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800012a5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800012a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000119b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000119b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000122b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000122b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000136e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000136e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800013c3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800014cd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800013c3`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800014cd`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180001575`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180001575`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180001591`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180001591`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800014fd`
- `api-ms-win-security-base-l1-1-0!GetFileSecurityW` at `0x1800014fd`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800015aa`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x1800015aa`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180001146`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180001146`

## pseudocode

```c
WCHAR *__fastcall GetDsOIDInfoCacheFileName(int a1)
{
  WCHAR *v2; // rdi
  signed int BasicProfileFolderPath; // eax
  size_t v4; // rdx
  HRESULT v5; // ebx
  size_t v6; // rbx
  size_t v7; // rsi
  WCHAR *v8; // rax
  __int64 v9; // r15
  size_t v10; // rcx
  WCHAR *v11; // rax
  int v12; // r13d
  size_t v13; // rdx
  DWORD LastError; // ebx
  WCHAR *v16; // rcx
  int v17; // edx
  DWORD FileAttributesW; // eax
  size_t v19; // rcx
  WCHAR *v20; // rax
  size_t v21; // rax
  WCHAR *v22; // rcx
  PSID v23; // rbx
  ACL *v24; // r14
  void *v25; // rsi
  const wchar_t *v26; // rcx
  WCHAR *v27; // r9
  __int64 v28; // rax
  size_t v29; // r8
  size_t v30; // rsi
  const wchar_t *v31; // rcx
  WCHAR *i; // rax
  void *AnyPackageSid; // r12
  __int64 v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  DWORD nLengthNeeded; // [rsp+60h] [rbp-A0h] BYREF
  size_t pcchLength; // [rsp+68h] [rbp-98h] BYREF
  int v39; // [rsp+70h] [rbp-90h]
  PSID pSid; // [rsp+78h] [rbp-88h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+80h] [rbp-80h] BYREF
  wchar_t psz[264]; // [rsp+90h] [rbp-70h] BYREF

  pcchLength = 0;
  v2 = 0;
  BasicProfileFolderPath = GetBasicProfileFolderPath(4, 0, psz, 260);
  if ( BasicProfileFolderPath >= 0 )
  {
    v5 = StringLengthWorkerW(psz, v4, &pcchLength);
    if ( v5 < 0 )
      goto LABEL_11;
    v6 = pcchLength;
    v7 = pcchLength + 40;
    v8 = (WCHAR *)LocalAlloc(0, 2 * (pcchLength + 40));
    v2 = v8;
    if ( v8 )
    {
      memcpy_0(v8, psz, 2 * v6 + 2);
      v9 = 2147483646;
      if ( v7 - 1 > 0x7FFFFFFE )
      {
        v5 = -2147024809;
      }
      else
      {
        v10 = v7;
        v11 = v2;
        do
        {
          if ( !*v11 )
            break;
          ++v11;
          --v10;
        }
        while ( v10 );
        v12 = -2147024809;
        v5 = -2147024809;
        if ( v10 )
        {
          v5 = 0;
          v13 = v7 - v10;
        }
        else
        {
          v13 = 0;
        }
        if ( v10 )
        {
          v26 = L"\\Microsoft\\Crypto\\OIDInfo";
          v27 = &v2[v13];
          v28 = 2147483646;
          v29 = v7 - v13;
          if ( v7 != v13 )
          {
            do
            {
              if ( !v28 )
                break;
              if ( !*v26 )
                break;
              *v27++ = *v26++;
              --v28;
              --v29;
            }
            while ( v29 );
          }
          v16 = v27 - 1;
          v5 = -2147024774;
          if ( v29 )
            v16 = v27;
          v17 = -2147024774;
          if ( v29 )
            v17 = 0;
          *v16 = 0;
          if ( !v29 )
          {
            v5 = v17;
            goto LABEL_11;
          }
          if ( a1 )
          {
            if ( !(unsigned int)I_RecursiveCreateDirectory(v2) )
              goto LABEL_12;
            AnyPackageSid = _CreateAnyPackageSid();
            if ( AnyPackageSid )
            {
              nLengthNeeded = 0;
              CryptSetFileSidDaclAce(v2, (__int64)AnyPackageSid, (__int64)&nLengthNeeded);
              FreeSid(AnyPackageSid);
            }
          }
          else
          {
            FileAttributesW = GetFileAttributesW(v2);
            if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
            {
              SetLastError(2u);
              goto LABEL_12;
            }
          }
          v19 = v7;
          v20 = v2;
          do
          {
            if ( !*v20 )
              break;
            ++v20;
            --v19;
          }
          while ( v19 );
          if ( v19 )
          {
            v12 = 0;
            v21 = v7 - v19;
          }
          else
          {
            v21 = 0;
          }
          if ( !v19 )
          {
            v5 = v12;
            goto LABEL_11;
          }
          v30 = v7 - v21;
          v31 = L"\\DsOIDInfo.dat";
          for ( i = &v2[v21]; v30; --v30 )
          {
            if ( !v9 )
              break;
            if ( !*v31 )
              break;
            *i++ = *v31++;
            --v9;
          }
          v22 = i - 1;
          if ( v30 )
          {
            v22 = i;
            v5 = 0;
          }
          *v22 = 0;
          if ( v30 )
          {
            if ( a1 )
            {
              pSid = 0;
              *(_DWORD *)pIdentifierAuthority.Value = 0;
              *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
              if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &pSid) )
              {
                v23 = pSid;
              }
              else
              {
                v23 = 0;
                pSid = 0;
              }
              if ( v23 )
              {
                pcchLength = 0;
                v24 = 0;
                v39 = 0;
                nLengthNeeded = 1024;
                v25 = (void *)PkiAlloc(0x400u);
                if ( v25 )
                {
                  while ( !GetFileSecurityW(v2, 4u, v25, nLengthNeeded, &nLengthNeeded) )
                  {
                    if ( GetLastError() != 122 )
                      goto LABEL_37;
                    v35 = PkiRealloc(v25, nLengthNeeded);
                    if ( !v35 )
                      goto LABEL_37;
                    v25 = (void *)v35;
                  }
                  v36 = CryptSetSidDaclAce(v25, v34, 16);
                  v24 = (ACL *)pcchLength;
                  if ( v36
                    && pcchLength
                    && InitializeSecurityDescriptor(v25, 1u)
                    && SetSecurityDescriptorDacl(v25, 1, v24, 0) )
                  {
                    SetFileSecurityW(v2, 4u, v25);
                  }
                }
LABEL_37:
                PkiFree(v25);
                PkiFree(v24);
                FreeSid(v23);
              }
            }
            return v2;
          }
        }
      }
LABEL_11:
      SetLastError(v5);
      if ( v2 )
      {
LABEL_12:
        LastError = GetLastError();
        LocalFree(v2);
        SetLastError(LastError);
        return 0;
      }
      return v2;
    }
    SetLastError(0x8007000E);
    return v2;
  }
  SetLastError(BasicProfileFolderPath);
  return 0;
}

```

## disassembly

```asm
0x180001100  push    rbp
0x180001102  push    rdi
0x180001103  push    r12
0x180001105  push    r14
0x180001107  lea     rbp, [rsp-1B8h]
0x18000110f  sub     rsp, 2B8h
0x180001116  mov     rax, cs:__security_cookie
0x18000111d  xor     rax, rsp
0x180001120  mov     [rbp+1D0h+var_30], rax
0x180001127  mov     r14d, ecx
0x18000112a  lea     r8, [rbp+1D0h+psz]
0x18000112e  xor     r12d, r12d
0x180001131  mov     ecx, 4
0x180001136  mov     r9d, 104h
0x18000113c  mov     [rsp+2D0h+pcchLength], r12
0x180001141  xor     edx, edx
0x180001143  mov     edi, r12d
0x180001146  call    cs:__imp_GetBasicProfileFolderPath
0x18000114c  test    eax, eax
0x18000114e  js      loc_180001463
0x180001154  mov     [rsp+2D0h+arg_0], rbx
0x18000115c  lea     r8, [rsp+2D0h+pcchLength]; pcchLength
0x180001161  mov     [rsp+2D0h+arg_8], rsi
0x180001169  lea     rcx, [rbp+1D0h+psz]; psz
0x18000116d  mov     [rsp+2D0h+arg_10], r13
0x180001175  mov     [rsp+2D0h+var_20], r15
0x18000117d  call    StringLengthWorkerW
0x180001182  mov     ebx, eax
0x180001184  test    eax, eax
0x180001186  js      loc_18000120F
0x18000118c  mov     rbx, [rsp+2D0h+pcchLength]
0x180001191  xor     ecx, ecx; uFlags
0x180001193  lea     rsi, [rbx+28h]
0x180001197  lea     rdx, [rsi+rsi]; uBytes
0x18000119b  call    cs:__imp_LocalAlloc
0x1800011a1  mov     rdi, rax
0x1800011a4  test    rax, rax
0x1800011a7  jz      loc_180001473
0x1800011ad  lea     r8, ds:2[rbx*2]; Size
0x1800011b5  mov     rcx, rax; void *
0x1800011b8  lea     rdx, [rbp+1D0h+psz]; Src
0x1800011bc  call    memcpy_0
0x1800011c1  lea     rax, [rsi-1]
0x1800011c5  mov     r15d, 7FFFFFFEh
0x1800011cb  cmp     rax, r15
0x1800011ce  ja      loc_1800015BC
0x1800011d4  mov     rcx, rsi
0x1800011d7  mov     rax, rdi
0x1800011da  cmp     [rax], r12w
0x1800011de  jz      short loc_1800011EA
0x1800011e0  add     rax, 2
0x1800011e4  sub     rcx, 1
0x1800011e8  jnz     short loc_1800011DA
0x1800011ea  mov     r13d, 80070057h
0x1800011f0  test    rcx, rcx
0x1800011f3  mov     ebx, r13d
0x1800011f6  cmovnz  ebx, r12d
0x1800011fa  jz      loc_180001483
0x180001200  mov     rdx, rsi
0x180001203  sub     rdx, rcx
0x180001206  test    rcx, rcx
0x180001209  jnz     loc_1800013D8
0x18000120f  mov     ecx, ebx; dwErrCode
0x180001211  call    cs:__imp_SetLastError
0x180001217  test    rdi, rdi
0x18000121a  jz      loc_1800013C9
0x180001220  call    cs:__imp_GetLastError
0x180001226  mov     rcx, rdi; hMem
0x180001229  mov     ebx, eax
0x18000122b  call    cs:__imp_LocalFree
0x180001231  mov     ecx, ebx; dwErrCode
0x180001233  call    cs:__imp_SetLastError
0x180001239  mov     rax, r12
0x18000123c  mov     r13, [rsp+2D0h+arg_10]
0x180001244  mov     rsi, [rsp+2D0h+arg_8]
0x18000124c  mov     rbx, [rsp+2D0h+arg_0]
0x180001254  mov     r15, [rsp+2D0h+var_20]
0x18000125c  mov     rcx, [rbp+1D0h+var_30]
0x180001263  xor     rcx, rsp; StackCookie
0x180001266  call    __security_check_cookie
0x18000126b  add     rsp, 2B8h
0x180001272  pop     r14
0x180001274  pop     r12
0x180001276  pop     rdi
0x180001277  pop     rbp
0x180001278  retn
0x180001279  test    r8, r8
0x18000127c  lea     rcx, [r9-2]
0x180001280  mov     ebx, 8007007Ah
0x180001285  cmovnz  rcx, r9
0x180001289  mov     edx, ebx
0x18000128b  cmovnz  edx, r12d
0x18000128f  mov     [rcx], r12w
0x180001293  jz      loc_1800015B5
0x180001299  mov     rcx, rdi; lpFileName
0x18000129c  test    r14d, r14d
0x18000129f  jnz     loc_18000148B
0x1800012a5  call    cs:__imp_GetFileAttributesW
0x1800012ab  cmp     eax, 0FFFFFFFFh
0x1800012ae  jz      short loc_1800012EE
0x1800012b0  test    al, 10h
0x1800012b2  jz      short loc_1800012EE
0x1800012b4  mov     rcx, rsi
0x1800012b7  mov     rax, rdi
0x1800012ba  cmp     word ptr [rax], 0
0x1800012be  jz      short loc_1800012CA
0x1800012c0  add     rax, 2
0x1800012c4  sub     rcx, 1
0x1800012c8  jnz     short loc_1800012BA
0x1800012ca  test    rcx, rcx
0x1800012cd  cmovnz  r13d, r12d
0x1800012d1  jz      loc_1800014DB
0x1800012d7  mov     rax, rsi
0x1800012da  sub     rax, rcx
0x1800012dd  test    rcx, rcx
0x1800012e0  jnz     loc_180001421
0x1800012e6  mov     ebx, r13d
0x1800012e9  jmp     loc_18000120F
0x1800012ee  mov     ecx, 2; dwErrCode
0x1800012f3  call    cs:__imp_SetLastError
0x1800012f9  jmp     loc_180001220
0x1800012fe  test    rsi, rsi
0x180001301  lea     rcx, [rax-2]
0x180001305  cmovnz  rcx, rax
0x180001309  cmovnz  ebx, r12d
0x18000130d  mov     [rcx], r12w
0x180001311  jz      loc_18000120F
0x180001317  test    r14d, r14d
0x18000131a  jz      loc_1800013C9
0x180001320  lea     rax, [rsp+2D0h+var_258]
0x180001325  mov     [rsp+2D0h+var_258], r12
0x18000132a  mov     [rsp+2D0h+pSid], rax; pSid
0x18000132f  lea     rcx, [rbp+1D0h+pIdentifierAuthority]; pIdentifierAuthority
0x180001333  mov     [rsp+2D0h+nSubAuthority7], r12d; nSubAuthority7
0x180001338  mov     r8d, 2; nSubAuthority0
0x18000133e  mov     [rsp+2D0h+nSubAuthority6], r12d; nSubAuthority6
0x180001343  mov     r9d, 1; nSubAuthority1
0x180001349  mov     [rsp+2D0h+nSubAuthority5], r12d; nSubAuthority5
0x18000134e  movzx   edx, r8b; nSubAuthorityCount
0x180001352  mov     [rsp+2D0h+nSubAuthority4], r12d; nSubAuthority4
0x180001357  mov     [rsp+2D0h+nSubAuthority3], r12d; nSubAuthority3
0x18000135c  mov     [rsp+2D0h+nSubAuthority2], r12d; nSubAuthority2
0x180001361  mov     dword ptr [rbp+1D0h+pIdentifierAuthority.Value], 0
0x180001368  mov     word ptr [rbp+1D0h+pIdentifierAuthority.Value+4], 0F00h
0x18000136e  call    cs:__imp_AllocateAndInitializeSid
0x180001374  test    eax, eax
0x180001376  jnz     short loc_1800013D1
0x180001378  mov     rbx, r12
0x18000137b  mov     [rsp+2D0h+var_258], rbx
0x180001380  test    rbx, rbx
0x180001383  jz      short loc_1800013C9
0x180001385  mov     ecx, 400h; uBytes
0x18000138a  mov     [rsp+2D0h+pcchLength], r12
0x18000138f  mov     r14, r12
0x180001392  mov     [rsp+2D0h+var_260], r12d
0x180001397  mov     [rsp+2D0h+nLengthNeeded], 400h
0x18000139f  call    PkiAlloc
0x1800013a4  mov     rsi, rax
0x1800013a7  test    rax, rax
0x1800013aa  jnz     loc_1800014E3
0x1800013b0  mov     rcx, rsi; hMem
0x1800013b3  call    PkiFree
0x1800013b8  mov     rcx, r14; hMem
0x1800013bb  call    PkiFree
0x1800013c0  mov     rcx, rbx; pSid
0x1800013c3  call    cs:__imp_FreeSid
0x1800013c9  mov     rax, rdi
0x1800013cc  jmp     loc_18000123C
0x1800013d1  mov     rbx, [rsp+2D0h+var_258]
0x1800013d6  jmp     short loc_180001380
0x1800013d8  mov     r8, rsi
0x1800013db  lea     rcx, aMicrosoftCrypt; "\\Microsoft\\Crypto\\OIDInfo"
0x1800013e2  lea     r9, [rdi+rdx*2]
0x1800013e6  mov     rax, r15
0x1800013e9  sub     r8, rdx
0x1800013ec  jz      loc_180001279
0x1800013f2  test    rax, rax
0x1800013f5  jz      loc_180001279
0x1800013fb  movzx   edx, word ptr [rcx]
0x1800013fe  test    dx, dx
0x180001401  jz      loc_180001279
0x180001407  mov     [r9], dx
0x18000140b  add     rcx, 2
0x18000140f  add     r9, 2
0x180001413  dec     rax
0x180001416  sub     r8, 1
0x18000141a  jnz     short loc_1800013F2
0x18000141c  jmp     loc_180001279
0x180001421  sub     rsi, rax
0x180001424  lea     rcx, aDsoidinfoDat; "\\DsOIDInfo.dat"
0x18000142b  lea     rax, [rdi+rax*2]
0x18000142f  jz      loc_1800012FE
0x180001435  test    r15, r15
0x180001438  jz      loc_1800012FE
0x18000143e  movzx   edx, word ptr [rcx]
0x180001441  test    dx, dx
0x180001444  jz      loc_1800012FE
0x18000144a  mov     [rax], dx
0x18000144d  add     rcx, 2
0x180001451  add     rax, 2
0x180001455  dec     r15
0x180001458  sub     rsi, 1
0x18000145c  jnz     short loc_180001435
0x18000145e  jmp     loc_1800012FE
0x180001463  mov     ecx, eax; dwErrCode
0x180001465  call    cs:__imp_SetLastError
0x18000146b  mov     rax, r12
0x18000146e  jmp     loc_18000125C
0x180001473  mov     ecx, 8007000Eh; dwErrCode
0x180001478  call    cs:__imp_SetLastError
0x18000147e  jmp     loc_1800013C9
0x180001483  mov     rdx, r12
0x180001486  jmp     loc_180001206
0x18000148b  call    I_RecursiveCreateDirectory
0x180001490  test    eax, eax
0x180001492  jz      loc_180001220
0x180001498  call    ?_CreateAnyPackageSid@@YAPEAXXZ; _CreateAnyPackageSid(void)
0x18000149d  mov     r12, rax
0x1800014a0  test    rax, rax
0x1800014a3  jz      short loc_1800014D3
0x1800014a5  lea     rax, [rsp+2D0h+nLengthNeeded]
0x1800014aa  mov     [rsp+2D0h+nLengthNeeded], 0
0x1800014b2  mov     qword ptr [rsp+2D0h+nSubAuthority3], rax; __int64
0x1800014b7  mov     r8d, 3
0x1800014bd  mov     rcx, rdi; lpFileName
0x1800014c0  mov     qword ptr [rsp+2D0h+nSubAuthority2], r12; __int64
0x1800014c5  call    _CryptSetFileSidDaclAce
0x1800014ca  mov     rcx, r12; pSid
0x1800014cd  call    cs:__imp_FreeSid
0x1800014d3  xor     r12d, r12d
0x1800014d6  jmp     loc_1800012B4
0x1800014db  mov     rax, r12
0x1800014de  jmp     loc_1800012DD
0x1800014e3  mov     r9d, [rsp+2D0h+nLengthNeeded]; nLength
0x1800014e8  lea     rax, [rsp+2D0h+nLengthNeeded]
0x1800014ed  mov     r8, rsi; pSecurityDescriptor
0x1800014f0  mov     qword ptr [rsp+2D0h+nSubAuthority2], rax; lpnLengthNeeded
0x1800014f5  mov     edx, 4; RequestedInformation
0x1800014fa  mov     rcx, rdi; lpFileName
0x1800014fd  call    cs:__imp_GetFileSecurityW
0x180001503  test    eax, eax
0x180001505  jnz     short loc_180001530
0x180001507  call    cs:__imp_GetLastError
0x18000150d  cmp     eax, 7Ah ; 'z'
0x180001510  jnz     loc_1800013B0
0x180001516  mov     edx, [rsp+2D0h+nLengthNeeded]
0x18000151a  mov     rcx, rsi
0x18000151d  call    PkiRealloc
0x180001522  test    rax, rax
0x180001525  jz      loc_1800013B0
0x18000152b  mov     rsi, rax
0x18000152e  jmp     short loc_1800014E3
0x180001530  lea     rax, [rsp+2D0h+pcchLength]
0x180001535  mov     r8d, 10h
0x18000153b  mov     qword ptr [rsp+2D0h+nSubAuthority4], rax
0x180001540  mov     rcx, rsi
0x180001543  lea     rax, [rsp+2D0h+var_260]
0x180001548  mov     qword ptr [rsp+2D0h+nSubAuthority3], rax
0x18000154d  mov     qword ptr [rsp+2D0h+nSubAuthority2], rbx
0x180001552  call    _CryptSetSidDaclAce
0x180001557  mov     r14, [rsp+2D0h+pcchLength]
0x18000155c  test    eax, eax
0x18000155e  jz      loc_1800013B0
0x180001564  test    r14, r14
0x180001567  jz      loc_1800013B0
0x18000156d  mov     edx, 1; dwRevision
0x180001572  mov     rcx, rsi; pSecurityDescriptor
0x180001575  call    cs:__imp_InitializeSecurityDescriptor
0x18000157b  test    eax, eax
0x18000157d  jz      loc_1800013B0
0x180001583  xor     r9d, r9d; bDaclDefaulted
0x180001586  mov     r8, r14; pDacl
0x180001589  mov     edx, 1; bDaclPresent
0x18000158e  mov     rcx, rsi; pSecurityDescriptor
0x180001591  call    cs:__imp_SetSecurityDescriptorDacl
0x180001597  test    eax, eax
0x180001599  jz      loc_1800013B0
0x18000159f  mov     r8, rsi; pSecurityDescriptor
0x1800015a2  mov     edx, 4; SecurityInformation
0x1800015a7  mov     rcx, rdi; lpFileName
0x1800015aa  call    cs:__imp_SetFileSecurityW
0x1800015b0  jmp     loc_1800013B0
0x1800015b5  mov     ebx, edx
0x1800015b7  jmp     loc_18000120F
0x1800015bc  mov     ebx, 80070057h
0x1800015c1  jmp     loc_18000120F
```
