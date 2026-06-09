# I_GetTemplateInfoFromCert

- ea: `0x180001570`
- end: `0x1800019d1`
- name: `I_GetTemplateInfoFromCert`
- size: `1121`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180002aa0`

## callees

- `0x180001570`
- `0x180004600`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000168f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001737`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001845`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800018b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000168f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001737`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180001845`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800018b4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001780`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001797`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800017b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001780`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001797`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800017b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000166f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800016d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000171e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000176c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000166f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800016d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000171e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000176c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001893`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180001710`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180001762`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180001710`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180001762`
- `CRYPT32!CertFindExtension` at `0x18000162b`
- `CRYPT32!CertFindExtension` at `0x1800017dd`
- `CRYPT32!CertFindExtension` at `0x18000162b`
- `CRYPT32!CertFindExtension` at `0x1800017dd`
- `CRYPT32!CryptDecodeObject` at `0x180001665`
- `CRYPT32!CryptDecodeObject` at `0x1800016cf`
- `CRYPT32!CryptDecodeObject` at `0x18000181b`
- `CRYPT32!CryptDecodeObject` at `0x180001889`
- `CRYPT32!CryptDecodeObject` at `0x180001665`
- `CRYPT32!CryptDecodeObject` at `0x1800016cf`
- `CRYPT32!CryptDecodeObject` at `0x18000181b`
- `CRYPT32!CryptDecodeObject` at `0x180001889`

## pseudocode

```c
__int64 __fastcall I_GetTemplateInfoFromCert(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  __int64 v6; // rcx
  PCERT_EXTENSION Extension; // rax
  PCERT_EXTENSION v8; // rsi
  DWORD LastError; // edi
  _DWORD *pvStructInfo; // r15
  int v11; // ebx
  DWORD v12; // eax
  _WORD *v13; // r14
  _DWORD *v14; // rsi
  PCERT_EXTENSION v15; // rax
  PCERT_EXTENSION v16; // rbx
  SIZE_T v17; // rbx
  _WORD *v18; // rax
  _WORD *v19; // rcx
  __int64 v20; // rax
  _WORD *v21; // rdx
  _WORD *v22; // rcx
  DWORD pcbStructInfo; // [rsp+70h] [rbp+8h] BYREF

  pcbStructInfo = 0;
  WppTraceIndent(a1, 0);
  v6 = (__int64)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( !a1 || !a2 || !a3 )
  {
    LastError = 87;
    goto LABEL_50;
  }
  *a2 = 0;
  *a3 = 0;
  Extension = CertFindExtension(
                "1.3.6.1.4.1.311.21.7",
                *(_DWORD *)(*(_QWORD *)(a1 + 24) + 192LL),
                *(CERT_EXTENSION **)(*(_QWORD *)(a1 + 24) + 200LL));
  v8 = Extension;
  if ( !Extension )
  {
    v15 = CertFindExtension(
            "1.3.6.1.4.1.311.20.2",
            *(_DWORD *)(*(_QWORD *)(a1 + 24) + 192LL),
            *(CERT_EXTENSION **)(*(_QWORD *)(a1 + 24) + 200LL));
    v16 = v15;
    if ( !v15 )
    {
      LastError = 1168;
      goto LABEL_50;
    }
    if ( !CryptDecodeObject(1u, (LPCSTR)0x18, v15->Value.pbData, v15->Value.cbData, 0, 0, &pcbStructInfo) )
      goto LABEL_31;
    LastError = 8;
    v14 = HeapAlloc(hHeap, 8u, pcbStructInfo);
    if ( !v14 )
      goto LABEL_31;
    pvStructInfo = 0;
    if ( CryptDecodeObject(1u, (LPCSTR)0x18, v16->Value.pbData, v16->Value.cbData, 0, v14, &pcbStructInfo) )
    {
      v17 = (unsigned int)(v14[2] + 2);
      v18 = HeapAlloc(hHeap, 8u, v17);
      v13 = v18;
      if ( v18 )
      {
        if ( v17 )
        {
          if ( v17 > 0x7FFFFFFF )
          {
            *v18 = 0;
            LastError = 87;
            goto LABEL_21;
          }
          v19 = (_WORD *)*((_QWORD *)v14 + 2);
          v20 = 2147483646;
          v21 = v13;
          do
          {
            if ( !v20 )
              break;
            if ( !*v19 )
              break;
            *v21++ = *v19++;
            --v20;
            --v17;
          }
          while ( v17 );
          v22 = v21 - 1;
          if ( v17 )
            v22 = v21;
          *v22 = 0;
          v6 = 2147942522LL;
          if ( v17 )
            v6 = 0;
        }
        else
        {
          v6 = 2147942487LL;
        }
        LastError = (unsigned __int16)v6;
        v11 = 0;
        if ( (_WORD)v6 )
        {
LABEL_21:
          HeapFree(hHeap, 0, v13);
          goto LABEL_22;
        }
LABEL_46:
        *a3 = v11;
        *a2 = v13;
LABEL_22:
        if ( !v14 )
          goto LABEL_24;
      }
    }
    else
    {
      LastError = GetLastError();
    }
    HeapFree(hHeap, 0, v14);
LABEL_24:
    if ( !pvStructInfo )
      goto LABEL_50;
LABEL_25:
    HeapFree(hHeap, 0, pvStructInfo);
    goto LABEL_50;
  }
  if ( !CryptDecodeObject(
          1u,
          "1.3.6.1.4.1.311.21.7",
          Extension->Value.pbData,
          Extension->Value.cbData,
          0,
          0,
          &pcbStructInfo) )
  {
LABEL_31:
    LastError = GetLastError();
    goto LABEL_50;
  }
  LastError = 8;
  pvStructInfo = HeapAlloc(hHeap, 8u, pcbStructInfo);
  if ( pvStructInfo )
  {
    if ( !CryptDecodeObject(
            1u,
            "1.3.6.1.4.1.311.21.7",
            v8->Value.pbData,
            v8->Value.cbData,
            0,
            pvStructInfo,
            &pcbStructInfo) )
      goto LABEL_14;
    if ( !*(_QWORD *)pvStructInfo )
    {
      LastError = 1168;
      goto LABEL_25;
    }
    v11 = pvStructInfo[2];
    v12 = MultiByteToWideChar(0, 0, *(LPCCH *)pvStructInfo, -1, 0, 0);
    pcbStructInfo = v12;
    if ( !v12 )
    {
LABEL_14:
      LastError = GetLastError();
      goto LABEL_25;
    }
    v13 = HeapAlloc(hHeap, 8u, 2LL * v12);
    if ( !v13 )
      goto LABEL_25;
    v14 = 0;
    if ( !MultiByteToWideChar(0, 0, *(LPCCH *)pvStructInfo, -1, v13, pcbStructInfo) )
    {
      LastError = GetLastError();
      goto LABEL_21;
    }
    LastError = 0;
    goto LABEL_46;
  }
  LastError = 1168;
LABEL_50:
  WppTraceIndent(v6, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180001570  mov     rax, rsp
0x180001573  sub     rsp, 68h
0x180001577  mov     [rax+10h], rbx
0x18000157b  mov     rbx, rcx
0x18000157e  mov     [rax+18h], rbp
0x180001582  mov     rbp, r8
0x180001585  mov     [rax-10h], r12
0x180001589  mov     r12, rdx
0x18000158c  mov     [rax-18h], r13
0x180001590  xor     edx, edx
0x180001592  xor     r13d, r13d
0x180001595  mov     [rax+8], r13d
0x180001599  call    WppTraceIndent
0x18000159e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800015a5  lea     rax, WPP_GLOBAL_Control
0x1800015ac  cmp     rcx, rax
0x1800015af  jz      short loc_1800015D9
0x1800015b1  test    byte ptr [rcx+1Ch], 2
0x1800015b5  jz      short loc_1800015D9
0x1800015b7  cmp     byte ptr [rcx+19h], 5
0x1800015bb  jb      short loc_1800015D9
0x1800015bd  mov     r9, cs:WPP_pszIndent
0x1800015c4  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800015cb  mov     rcx, [rcx+10h]
0x1800015cf  mov     edx, 18h
0x1800015d4  call    WPP_SF_s
0x1800015d9  mov     [rsp+68h+arg_18], rsi
0x1800015e1  mov     [rsp+68h+var_8], rdi
0x1800015e6  mov     [rsp+68h+var_20], r14
0x1800015eb  mov     [rsp+68h+var_28], r15
0x1800015f0  test    rbx, rbx
0x1800015f3  jz      loc_18000194E
0x1800015f9  test    r12, r12
0x1800015fc  jz      loc_18000194E
0x180001602  test    rbp, rbp
0x180001605  jz      loc_18000194E
0x18000160b  mov     [r12], r13
0x18000160f  lea     rcx, szStructType; "1.3.6.1.4.1.311.21.7"
0x180001616  mov     [rbp+0], r13d
0x18000161a  mov     rdx, [rbx+18h]
0x18000161e  mov     r8, [rdx+0C8h]; rgExtensions
0x180001625  mov     edx, [rdx+0C0h]; cExtensions
0x18000162b  call    cs:__imp_CertFindExtension
0x180001631  mov     rsi, rax
0x180001634  test    rax, rax
0x180001637  jz      loc_1800017C5
0x18000163d  mov     r9d, [rsi+10h]; cbEncoded
0x180001641  lea     rax, [rsp+68h+arg_0]
0x180001646  mov     r8, [rsi+18h]; pbEncoded
0x18000164a  lea     rdx, szStructType; "1.3.6.1.4.1.311.21.7"
0x180001651  mov     [rsp+68h+pcbStructInfo], rax; pcbStructInfo
0x180001656  mov     ecx, 1; dwCertEncodingType
0x18000165b  mov     [rsp+68h+pvStructInfo], r13; pvStructInfo
0x180001660  mov     [rsp+68h+dwFlags], r13d; dwFlags
0x180001665  call    cs:__imp_CryptDecodeObject
0x18000166b  test    eax, eax
0x18000166d  jnz     short loc_18000167C
0x18000166f  call    cs:__imp_GetLastError
0x180001675  mov     edi, eax
0x180001677  jmp     loc_180001953
0x18000167c  mov     r8d, [rsp+68h+arg_0]; dwBytes
0x180001681  mov     edi, 8
0x180001686  mov     rcx, cs:hHeap; hHeap
0x18000168d  mov     edx, edi; dwFlags
0x18000168f  call    cs:__imp_HeapAlloc
0x180001695  mov     r15, rax
0x180001698  test    rax, rax
0x18000169b  jnz     short loc_1800016A7
0x18000169d  mov     edi, 490h
0x1800016a2  jmp     loc_180001953
0x1800016a7  mov     r9d, [rsi+10h]; cbEncoded
0x1800016ab  lea     rax, [rsp+68h+arg_0]
0x1800016b0  mov     r8, [rsi+18h]; pbEncoded
0x1800016b4  lea     rdx, szStructType; "1.3.6.1.4.1.311.21.7"
0x1800016bb  mov     [rsp+68h+pcbStructInfo], rax; pcbStructInfo
0x1800016c0  mov     ecx, 1; dwCertEncodingType
0x1800016c5  mov     [rsp+68h+pvStructInfo], r15; pvStructInfo
0x1800016ca  mov     [rsp+68h+dwFlags], r13d; dwFlags
0x1800016cf  call    cs:__imp_CryptDecodeObject
0x1800016d5  test    eax, eax
0x1800016d7  jnz     short loc_1800016E6
0x1800016d9  call    cs:__imp_GetLastError
0x1800016df  mov     edi, eax
0x1800016e1  jmp     loc_1800017A6
0x1800016e6  mov     r8, [r15]; lpMultiByteStr
0x1800016e9  test    r8, r8
0x1800016ec  jnz     short loc_1800016F8
0x1800016ee  mov     edi, 490h
0x1800016f3  jmp     loc_1800017A6
0x1800016f8  mov     ebx, [r15+8]
0x1800016fc  xor     edx, edx; dwFlags
0x1800016fe  mov     dword ptr [rsp+68h+pvStructInfo], r13d; cchWideChar
0x180001703  xor     ecx, ecx; CodePage
0x180001705  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x18000170b  mov     qword ptr [rsp+68h+dwFlags], r13; lpWideCharStr
0x180001710  call    cs:__imp_MultiByteToWideChar
0x180001716  mov     [rsp+68h+arg_0], eax
0x18000171a  test    eax, eax
0x18000171c  jnz     short loc_180001728
0x18000171e  call    cs:__imp_GetLastError
0x180001724  mov     edi, eax
0x180001726  jmp     short loc_1800017A6
0x180001728  mov     rcx, cs:hHeap; hHeap
0x18000172f  mov     edx, edi; dwFlags
0x180001731  mov     r8d, eax
0x180001734  add     r8, r8; dwBytes
0x180001737  call    cs:__imp_HeapAlloc
0x18000173d  mov     r14, rax
0x180001740  test    rax, rax
0x180001743  jz      short loc_1800017A6
0x180001745  mov     eax, [rsp+68h+arg_0]
0x180001749  mov     r9d, 0FFFFFFFFh; cbMultiByte
0x18000174f  mov     r8, [r15]; lpMultiByteStr
0x180001752  xor     edx, edx; dwFlags
0x180001754  mov     dword ptr [rsp+68h+pvStructInfo], eax; cchWideChar
0x180001758  xor     ecx, ecx; CodePage
0x18000175a  mov     qword ptr [rsp+68h+dwFlags], r14; lpWideCharStr
0x18000175f  mov     rsi, r13
0x180001762  call    cs:__imp_MultiByteToWideChar
0x180001768  test    eax, eax
0x18000176a  jnz     short loc_1800017BD
0x18000176c  call    cs:__imp_GetLastError
0x180001772  mov     edi, eax
0x180001774  mov     rcx, cs:hHeap; hHeap
0x18000177b  mov     r8, r14; lpMem
0x18000177e  xor     edx, edx; dwFlags
0x180001780  call    cs:__imp_HeapFree
0x180001786  test    rsi, rsi
0x180001789  jz      short loc_18000179D
0x18000178b  mov     rcx, cs:hHeap; hHeap
0x180001792  mov     r8, rsi; lpMem
0x180001795  xor     edx, edx; dwFlags
0x180001797  call    cs:__imp_HeapFree
0x18000179d  test    r15, r15
0x1800017a0  jz      loc_180001953
0x1800017a6  mov     rcx, cs:hHeap; hHeap
0x1800017ad  mov     r8, r15; lpMem
0x1800017b0  xor     edx, edx; dwFlags
0x1800017b2  call    cs:__imp_HeapFree
0x1800017b8  jmp     loc_180001953
0x1800017bd  mov     edi, r13d
0x1800017c0  jmp     loc_18000192A
0x1800017c5  mov     rdx, [rbx+18h]
0x1800017c9  lea     rcx, pszObjId; "1.3.6.1.4.1.311.20.2"
0x1800017d0  mov     r8, [rdx+0C8h]; rgExtensions
0x1800017d7  mov     edx, [rdx+0C0h]; cExtensions
0x1800017dd  call    cs:__imp_CertFindExtension
0x1800017e3  mov     rbx, rax
0x1800017e6  test    rax, rax
0x1800017e9  jnz     short loc_1800017F5
0x1800017eb  mov     edi, 490h
0x1800017f0  jmp     loc_180001953
0x1800017f5  mov     r9d, [rbx+10h]; cbEncoded
0x1800017f9  lea     rax, [rsp+68h+arg_0]
0x1800017fe  mov     r8, [rbx+18h]; pbEncoded
0x180001802  mov     edx, 18h; lpszStructType
0x180001807  mov     [rsp+68h+pcbStructInfo], rax; pcbStructInfo
0x18000180c  mov     ecx, 1; dwCertEncodingType
0x180001811  mov     [rsp+68h+pvStructInfo], r13; pvStructInfo
0x180001816  mov     [rsp+68h+dwFlags], r13d; dwFlags
0x18000181b  call    cs:__imp_CryptDecodeObject
0x180001821  test    eax, eax
0x180001823  jnz     short loc_180001832
0x180001825  call    cs:__imp_GetLastError
0x18000182b  mov     edi, eax
0x18000182d  jmp     loc_180001953
0x180001832  mov     r8d, [rsp+68h+arg_0]; dwBytes
0x180001837  mov     edi, 8
0x18000183c  mov     rcx, cs:hHeap; hHeap
0x180001843  mov     edx, edi; dwFlags
0x180001845  call    cs:__imp_HeapAlloc
0x18000184b  mov     rsi, rax
0x18000184e  test    rax, rax
0x180001851  jnz     short loc_180001860
0x180001853  call    cs:__imp_GetLastError
0x180001859  mov     edi, eax
0x18000185b  jmp     loc_180001953
0x180001860  mov     r9d, [rbx+10h]; cbEncoded
0x180001864  lea     rax, [rsp+68h+arg_0]
0x180001869  mov     r8, [rbx+18h]; pbEncoded
0x18000186d  mov     edx, 18h; lpszStructType
0x180001872  mov     [rsp+68h+pcbStructInfo], rax; pcbStructInfo
0x180001877  mov     ecx, 1; dwCertEncodingType
0x18000187c  mov     [rsp+68h+pvStructInfo], rsi; pvStructInfo
0x180001881  mov     r15, r13
0x180001884  mov     [rsp+68h+dwFlags], r13d; dwFlags
0x180001889  call    cs:__imp_CryptDecodeObject
0x18000188f  test    eax, eax
0x180001891  jnz     short loc_1800018A0
0x180001893  call    cs:__imp_GetLastError
0x180001899  mov     edi, eax
0x18000189b  jmp     loc_18000178B
0x1800018a0  mov     eax, [rsi+8]
0x1800018a3  mov     edx, edi; dwFlags
0x1800018a5  mov     rcx, cs:hHeap; hHeap
0x1800018ac  add     eax, 2
0x1800018af  mov     r8d, eax; dwBytes
0x1800018b2  mov     ebx, eax
0x1800018b4  call    cs:__imp_HeapAlloc
0x1800018ba  mov     r14, rax
0x1800018bd  test    rax, rax
0x1800018c0  jz      loc_18000178B
0x1800018c6  test    rbx, rbx
0x1800018c9  jz      short loc_180001936
0x1800018cb  cmp     rbx, 7FFFFFFFh
0x1800018d2  ja      short loc_180001940
0x1800018d4  mov     rcx, [rsi+10h]
0x1800018d8  mov     eax, 7FFFFFFEh
0x1800018dd  mov     rdx, r14
0x1800018e0  test    rax, rax
0x1800018e3  jz      short loc_180001904
0x1800018e5  movzx   r8d, word ptr [rcx]
0x1800018e9  test    r8w, r8w
0x1800018ed  jz      short loc_180001904
0x1800018ef  mov     [rdx], r8w
0x1800018f3  add     rcx, 2
0x1800018f7  add     rdx, 2
0x1800018fb  dec     rax
0x1800018fe  sub     rbx, 1
0x180001902  jnz     short loc_1800018E0
0x180001904  test    rbx, rbx
0x180001907  lea     rcx, [rdx-2]
0x18000190b  cmovnz  rcx, rdx
0x18000190f  mov     [rcx], r13w
0x180001913  mov     ecx, 8007007Ah
0x180001918  cmovnz  ecx, r13d
0x18000191c  movzx   edi, cx
0x18000191f  mov     ebx, r13d
0x180001922  test    edi, edi
0x180001924  jnz     loc_180001774
0x18000192a  mov     [rbp+0], ebx
0x18000192d  mov     [r12], r14
0x180001931  jmp     loc_180001786
0x180001936  mov     ecx, 80070057h
0x18000193b  test    rbx, rbx
0x18000193e  jz      short loc_18000191C
0x180001940  mov     [rax], r13w
0x180001944  mov     edi, 57h ; 'W'
0x180001949  jmp     loc_180001774
0x18000194e  mov     edi, 57h ; 'W'
0x180001953  mov     edx, 1
0x180001958  call    WppTraceIndent
0x18000195d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001964  lea     rax, WPP_GLOBAL_Control
0x18000196b  mov     r15, [rsp+68h+var_28]
0x180001970  mov     r14, [rsp+68h+var_20]
0x180001975  mov     r13, [rsp+68h+var_18]
0x18000197a  mov     r12, [rsp+68h+var_10]
0x18000197f  mov     rsi, [rsp+68h+arg_18]
0x180001987  mov     rbp, [rsp+68h+arg_10]
0x18000198f  mov     rbx, [rsp+68h+arg_8]
0x180001994  cmp     rcx, rax
0x180001997  jz      short loc_1800019C5
0x180001999  test    byte ptr [rcx+1Ch], 2
0x18000199d  jz      short loc_1800019C5
0x18000199f  cmp     byte ptr [rcx+19h], 5
0x1800019a3  jb      short loc_1800019C5
0x1800019a5  mov     r9, cs:WPP_pszIndent
0x1800019ac  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800019b3  mov     rcx, [rcx+10h]
0x1800019b7  mov     edx, 19h
0x1800019bc  mov     [rsp+68h+dwFlags], edi
0x1800019c0  call    WPP_SF_sD
0x1800019c5  mov     eax, edi
0x1800019c7  mov     rdi, [rsp+68h+var_8]
0x1800019cc  add     rsp, 68h
0x1800019d0  retn
```
