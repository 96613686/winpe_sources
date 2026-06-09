# I_ReaderListPopulateCredsViaContainerEnumeration

- ea: `0x18001fdfc`
- end: `0x180020247`
- name: `I_ReaderListPopulateCredsViaContainerEnumeration`
- size: `1099`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18001e4bc`

## callees

- `0x180004600`
- `0x18000a980`
- `0x18000db90`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`
- `0x18001f090`
- `0x18001fdfc`
- `0x180020250`
- `0x180024380`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800201e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800201e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001feb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001feb6`
- `ntdll!RtlNtStatusToDosError` at `0x18002016b`
- `ntdll!RtlNtStatusToDosError` at `0x18002016b`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001ff97`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18001ff97`
- `ntdll!RtlFreeUnicodeString` at `0x18001ff54`
- `ntdll!RtlFreeUnicodeString` at `0x1800201ac`
- `ntdll!RtlFreeUnicodeString` at `0x18001ff54`
- `ntdll!RtlFreeUnicodeString` at `0x1800201ac`
- `ntdll!RtlInitAnsiString` at `0x18001ff86`
- `ntdll!RtlInitAnsiString` at `0x18001ff86`
- `CRYPT32!CertCloseStore` at `0x180020195`
- `CRYPT32!CertCloseStore` at `0x180020195`
- `CRYPT32!CertOpenStore` at `0x18001fea4`
- `CRYPT32!CertOpenStore` at `0x18001fea4`

## pseudocode

```c
__int64 __fastcall I_ReaderListPopulateCredsViaContainerEnumeration(__int64 a1, __int64 a2, _DWORD *a3)
{
  char *v4; // r14
  wchar_t *p_SourceString; // rbx
  HCERTSTORE v8; // rax
  ULONG ContainerData; // edi
  const char *i; // rsi
  NTSTATUS v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdi
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rsp
  void *v19; // rsp
  wchar_t *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  wchar_t *v24; // rcx
  __int64 v26; // [rsp+0h] [rbp-30h] BYREF
  PCSZ SourceString; // [rsp+30h] [rbp+0h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp+8h] BYREF
  struct _STRING DestinationString; // [rsp+48h] [rbp+18h] BYREF

  SourceString = 0;
  DestinationString = 0;
  v4 = 0;
  p_SourceString = 0;
  UnicodeString = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  *a3 = 0;
  DestinationString = 0;
  UnicodeString = 0;
  v8 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
  *(_QWORD *)(a2 + 168) = v8;
  if ( v8 )
  {
    ContainerData = I_ReaderListBuildContainerList(a2, &SourceString);
    if ( ContainerData )
    {
      WppTraceIndent(0, 2);
      if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[28] & 1) != 0
        && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          95,
          (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent,
          ContainerData);
      }
      v4 = (char *)SourceString;
    }
    else
    {
      if ( *(_DWORD *)(a1 + 16) )
        *(_DWORD *)(a2 + 148) = 1;
      v4 = (char *)SourceString;
      for ( i = SourceString; i && *i; i += v23 + 1 )
      {
        if ( UnicodeString.Buffer )
        {
          RtlFreeUnicodeString(&UnicodeString);
          UnicodeString.Buffer = 0;
        }
        if ( p_SourceString )
        {
          if ( *((_DWORD *)p_SourceString - 2) == 1885431112 )
            ((void (*)(void))g_pfnFree)();
          p_SourceString = 0;
        }
        RtlInitAnsiString(&DestinationString, i);
        v11 = RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u);
        if ( v11 )
        {
          ContainerData = RtlNtStatusToDosError(v11);
          break;
        }
        v13 = -1;
        do
          ++v13;
        while ( UnicodeString.Buffer[v13] );
        v14 = 2 * v13 + 2;
        p_SourceString = 0;
        if ( !v14 )
          goto LABEL_35;
        if ( v14 > g_ulMaxStackAllocSize )
          goto LABEL_35;
        v15 = v14 + g_ulAdditionalProbeSize + 8;
        if ( v15 < v14 || !(unsigned int)VerifyStackAvailable(v15, v12, 0) )
          goto LABEL_35;
        v16 = v14 + 23;
        if ( v14 + 23 <= v14 + 8 )
          v16 = 0xFFFFFFFFFFFFFF0LL;
        v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
        v18 = alloca(v17);
        v19 = alloca(v17);
        p_SourceString = (wchar_t *)&SourceString;
        if ( &v26 == (__int64 *)-48LL
          || (LODWORD(SourceString) = 1801679955, (p_SourceString = (wchar_t *)&UnicodeString) == 0) )
        {
LABEL_35:
          v17 = v14 + 8;
          if ( v14 + 8 >= v14 )
          {
            v20 = (wchar_t *)((__int64 (__fastcall *)(unsigned __int64, __int64, _QWORD))g_pfnAllocate)(v17, v12, 0);
            p_SourceString = v20;
            if ( v20 )
            {
              *(_DWORD *)v20 = 1885431112;
              p_SourceString = v20 + 4;
            }
          }
        }
        if ( !p_SourceString )
        {
          WppTraceIndent(v17, 2);
          ContainerData = 8;
          if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[28] & 1) != 0
            && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              96,
              &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
              WPP_pszIndent);
          }
          break;
        }
        v21 = -1;
        do
          ++v21;
        while ( UnicodeString.Buffer[v21] );
        if ( StringCchCopyW(p_SourceString, v21 + 1, UnicodeString.Buffer) < 0 )
        {
          ContainerData = 122;
          break;
        }
        ContainerData = I_ReaderListReadContainerData(a1, a2, p_SourceString, a3);
        if ( ContainerData == 8 )
        {
          WppTraceIndent(v22, 2);
          if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[28] & 1) != 0
            && (unsigned __int8)WPP_GLOBAL_Control[25] >= 2u )
          {
            WPP_SF_sD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              97,
              (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
              WPP_pszIndent,
              8);
          }
          break;
        }
        ContainerData = 0;
        v23 = -1;
        do
          ++v23;
        while ( i[v23] );
      }
    }
  }
  else
  {
    ContainerData = GetLastError();
  }
  v24 = *(wchar_t **)(a2 + 168);
  if ( v24 && (ContainerData || !*a3) )
  {
    CertCloseStore(v24, 0);
    *(_QWORD *)(a2 + 168) = 0;
  }
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( p_SourceString )
  {
    v24 = p_SourceString - 4;
    if ( *((_DWORD *)p_SourceString - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  if ( v4 )
    HeapFree(hHeap, 0, v4);
  WppTraceIndent(v24, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      98,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      ContainerData);
  }
  return ContainerData;
}

```

## disassembly

```asm
0x18001fdfc  push    rbp
0x18001fdfe  push    rbx
0x18001fdff  push    rsi
0x18001fe00  push    rdi
0x18001fe01  push    r12
0x18001fe03  push    r13
0x18001fe05  push    r14
0x18001fe07  push    r15
0x18001fe09  sub     rsp, 68h
0x18001fe0d  lea     rbp, [rsp+30h]
0x18001fe12  mov     rax, cs:__security_cookie
0x18001fe19  xor     rax, rbp
0x18001fe1c  mov     [rbp+70h+var_48], rax
0x18001fe20  xor     edi, edi
0x18001fe22  mov     r15, rdx
0x18001fe25  xorps   xmm0, xmm0
0x18001fe28  mov     [rbp+70h+SourceString], rdi
0x18001fe2c  xorps   xmm1, xmm1
0x18001fe2f  xor     edx, edx
0x18001fe31  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x18001fe35  mov     r14d, edi
0x18001fe38  mov     ebx, edi
0x18001fe3a  movups  xmmword ptr [rbp+70h+UnicodeString.Length], xmm1
0x18001fe3e  mov     r13, r8
0x18001fe41  mov     r12, rcx
0x18001fe44  call    WppTraceIndent
0x18001fe49  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe50  lea     rsi, WPP_GLOBAL_Control
0x18001fe57  cmp     rcx, rsi
0x18001fe5a  jz      short loc_18001FE82
0x18001fe5c  test    byte ptr [rcx+1Ch], 2
0x18001fe60  jz      short loc_18001FE82
0x18001fe62  cmp     byte ptr [rcx+19h], 5
0x18001fe66  jb      short loc_18001FE82
0x18001fe68  mov     r9, cs:WPP_pszIndent
0x18001fe6f  lea     edx, [rdi+5Eh]
0x18001fe72  mov     rcx, [rcx+10h]
0x18001fe76  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001fe7d  call    WPP_SF_s
0x18001fe82  xor     edx, edx; dwEncodingType
0x18001fe84  mov     [r13+0], edi
0x18001fe88  xorps   xmm0, xmm0
0x18001fe8b  mov     [rsp+0A0h+pvPara], rdi; pvPara
0x18001fe90  xorps   xmm1, xmm1
0x18001fe93  xor     r9d, r9d; dwFlags
0x18001fe96  xor     r8d, r8d; hCryptProv
0x18001fe99  lea     ecx, [rdx+2]; lpszStoreProvider
0x18001fe9c  movups  xmmword ptr [rbp+70h+DestinationString.Length], xmm0
0x18001fea0  movups  xmmword ptr [rbp+70h+UnicodeString.Length], xmm1
0x18001fea4  call    cs:__imp_CertOpenStore
0x18001feaa  mov     [r15+0A8h], rax
0x18001feb1  test    rax, rax
0x18001feb4  jnz     short loc_18001FEC3
0x18001feb6  call    cs:__imp_GetLastError
0x18001febc  mov     edi, eax
0x18001febe  jmp     loc_18002017A
0x18001fec3  lea     rdx, [rbp+70h+SourceString]
0x18001fec7  mov     rcx, r15
0x18001feca  call    I_ReaderListBuildContainerList
0x18001fecf  xor     ecx, ecx
0x18001fed1  mov     edi, eax
0x18001fed3  test    eax, eax
0x18001fed5  jz      short loc_18001FF20
0x18001fed7  lea     edx, [rcx+2]
0x18001feda  call    WppTraceIndent
0x18001fedf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fee6  cmp     rcx, rsi
0x18001fee9  jz      short loc_18001FF17
0x18001feeb  test    byte ptr [rcx+1Ch], 1
0x18001feef  jz      short loc_18001FF17
0x18001fef1  cmp     byte ptr [rcx+19h], 2
0x18001fef5  jb      short loc_18001FF17
0x18001fef7  mov     r9, cs:WPP_pszIndent
0x18001fefe  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001ff05  mov     rcx, [rcx+10h]
0x18001ff09  mov     edx, 5Fh ; '_'
0x18001ff0e  mov     dword ptr [rsp+0A0h+pvPara], edi
0x18001ff12  call    WPP_SF_sD
0x18001ff17  mov     r14, [rbp+70h+SourceString]
0x18001ff1b  jmp     loc_18002017A
0x18001ff20  cmp     [r12+10h], ecx
0x18001ff25  jz      short loc_18001FF32
0x18001ff27  mov     dword ptr [r15+94h], 1
0x18001ff32  mov     r14, [rbp+70h+SourceString]
0x18001ff36  mov     rsi, r14
0x18001ff39  test    rsi, rsi
0x18001ff3c  jz      loc_180020173
0x18001ff42  cmp     [rsi], cl
0x18001ff44  jz      loc_180020173
0x18001ff4a  cmp     [rbp+70h+UnicodeString.Buffer], rcx
0x18001ff4e  jz      short loc_18001FF60
0x18001ff50  lea     rcx, [rbp+70h+UnicodeString]; UnicodeString
0x18001ff54  call    cs:__imp_RtlFreeUnicodeString
0x18001ff5a  xor     ecx, ecx
0x18001ff5c  mov     [rbp+70h+UnicodeString.Buffer], rcx
0x18001ff60  test    rbx, rbx
0x18001ff63  jz      short loc_18001FF7F
0x18001ff65  lea     rcx, [rbx-8]
0x18001ff69  cmp     dword ptr [rcx], 70616548h
0x18001ff6f  jnz     short loc_18001FF7D
0x18001ff71  mov     rax, cs:g_pfnFree
0x18001ff78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff7d  xor     ebx, ebx
0x18001ff7f  mov     rdx, rsi; SourceString
0x18001ff82  lea     rcx, [rbp+70h+DestinationString]; DestinationString
0x18001ff86  call    cs:__imp_RtlInitAnsiString
0x18001ff8c  mov     r8b, 1; AllocateDestinationString
0x18001ff8f  lea     rdx, [rbp+70h+DestinationString]; SourceString
0x18001ff93  lea     rcx, [rbp+70h+UnicodeString]; DestinationString
0x18001ff97  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18001ff9d  xor     r8d, r8d
0x18001ffa0  test    eax, eax
0x18001ffa2  jnz     loc_180020169
0x18001ffa8  mov     rax, [rbp+70h+UnicodeString.Buffer]
0x18001ffac  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001ffb0  inc     rdi
0x18001ffb3  cmp     [rax+rdi*2], r8w
0x18001ffb8  jnz     short loc_18001FFB0
0x18001ffba  lea     rdi, ds:2[rdi*2]
0x18001ffc2  mov     rbx, r8
0x18001ffc5  test    rdi, rdi
0x18001ffc8  jz      short loc_18002002E
0x18001ffca  cmp     rdi, cs:g_ulMaxStackAllocSize
0x18001ffd1  ja      short loc_18002002E
0x18001ffd3  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001ffda  add     rcx, 8
0x18001ffde  add     rcx, rdi
0x18001ffe1  cmp     rcx, rdi
0x18001ffe4  jb      short loc_18002002E
0x18001ffe6  call    VerifyStackAvailable
0x18001ffeb  xor     r8d, r8d
0x18001ffee  test    eax, eax
0x18001fff0  jz      short loc_18002002E
0x18001fff2  lea     rax, [rdi+8]
0x18001fff6  lea     rcx, [rax+0Fh]
0x18001fffa  cmp     rcx, rax
0x18001fffd  ja      short loc_180020009
0x18001ffff  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180020009  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002000d  mov     rax, rcx
0x180020010  call    _alloca_probe
0x180020015  sub     rsp, rcx
0x180020018  lea     rbx, [rsp+0A0h+SourceString]
0x18002001d  test    rbx, rbx
0x180020020  jz      short loc_18002002E
0x180020022  mov     dword ptr [rbx], 6B637453h
0x180020028  add     rbx, 8
0x18002002c  jnz     short loc_180020058
0x18002002e  lea     rcx, [rdi+8]
0x180020032  cmp     rcx, rdi
0x180020035  jb      short loc_180020058
0x180020037  mov     rax, cs:g_pfnAllocate
0x18002003e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020043  xor     r8d, r8d
0x180020046  mov     rbx, rax
0x180020049  test    rax, rax
0x18002004c  jz      short loc_180020058
0x18002004e  mov     dword ptr [rax], 70616548h
0x180020054  add     rbx, 8
0x180020058  test    rbx, rbx
0x18002005b  jz      loc_18002011F
0x180020061  mov     rax, [rbp+70h+UnicodeString.Buffer]
0x180020065  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180020069  inc     rdx
0x18002006c  cmp     [rax+rdx*2], r8w
0x180020071  jnz     short loc_180020069
0x180020073  mov     r8, [rbp+70h+UnicodeString.Buffer]; pszSrc
0x180020077  inc     rdx; cchDest
0x18002007a  mov     rcx, rbx; pszDest
0x18002007d  call    StringCchCopyW
0x180020082  test    eax, eax
0x180020084  js      loc_180020118
0x18002008a  mov     r9, r13
0x18002008d  mov     r8, rbx
0x180020090  mov     rdx, r15
0x180020093  mov     rcx, r12
0x180020096  call    I_ReaderListReadContainerData
0x18002009b  mov     edi, eax
0x18002009d  cmp     eax, 8
0x1800200a0  jz      short loc_1800200BD
0x1800200a2  xor     ecx, ecx
0x1800200a4  mov     edi, ecx
0x1800200a6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800200aa  inc     rax
0x1800200ad  cmp     [rsi+rax], cl
0x1800200b0  jnz     short loc_1800200AA
0x1800200b2  inc     rsi
0x1800200b5  add     rsi, rax
0x1800200b8  jmp     loc_18001FF39
0x1800200bd  mov     edx, 2
0x1800200c2  call    WppTraceIndent
0x1800200c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800200ce  lea     rsi, WPP_GLOBAL_Control
0x1800200d5  cmp     rcx, rsi
0x1800200d8  jz      loc_18002017A
0x1800200de  test    byte ptr [rcx+1Ch], 1
0x1800200e2  jz      loc_18002017A
0x1800200e8  cmp     byte ptr [rcx+19h], 2
0x1800200ec  jb      loc_18002017A
0x1800200f2  mov     r9, cs:WPP_pszIndent
0x1800200f9  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180020100  mov     rcx, [rcx+10h]
0x180020104  mov     edx, 61h ; 'a'
0x180020109  mov     dword ptr [rsp+0A0h+pvPara], 8
0x180020111  call    WPP_SF_sD
0x180020116  jmp     short loc_18002017A
0x180020118  mov     edi, 7Ah ; 'z'
0x18002011d  jmp     short loc_180020173
0x18002011f  mov     edx, 2
0x180020124  call    WppTraceIndent
0x180020129  mov     edi, 8
0x18002012e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020135  lea     rsi, WPP_GLOBAL_Control
0x18002013c  cmp     rcx, rsi
0x18002013f  jz      short loc_18002017A
0x180020141  test    byte ptr [rcx+1Ch], 1
0x180020145  jz      short loc_18002017A
0x180020147  cmp     byte ptr [rcx+19h], 2
0x18002014b  jb      short loc_18002017A
0x18002014d  mov     r9, cs:WPP_pszIndent
0x180020154  lea     edx, [rdi+58h]
0x180020157  mov     rcx, [rcx+10h]
0x18002015b  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180020162  call    WPP_SF_s
0x180020167  jmp     short loc_18002017A
0x180020169  mov     ecx, eax; Status
0x18002016b  call    cs:__imp_RtlNtStatusToDosError
0x180020171  mov     edi, eax
0x180020173  lea     rsi, WPP_GLOBAL_Control
0x18002017a  mov     rcx, [r15+0A8h]; hCertStore
0x180020181  xor     r12d, r12d
0x180020184  test    rcx, rcx
0x180020187  jz      short loc_1800201A2
0x180020189  test    edi, edi
0x18002018b  jnz     short loc_180020193
0x18002018d  cmp     [r13+0], r12d
0x180020191  jnz     short loc_1800201A2
0x180020193  xor     edx, edx; dwFlags
0x180020195  call    cs:__imp_CertCloseStore
0x18002019b  mov     [r15+0A8h], r12
0x1800201a2  cmp     [rbp+70h+UnicodeString.Buffer], r12
0x1800201a6  jz      short loc_1800201B2
0x1800201a8  lea     rcx, [rbp+70h+UnicodeString]; UnicodeString
0x1800201ac  call    cs:__imp_RtlFreeUnicodeString
0x1800201b2  test    rbx, rbx
0x1800201b5  jz      short loc_1800201CF
0x1800201b7  lea     rcx, [rbx-8]
0x1800201bb  cmp     dword ptr [rcx], 70616548h
0x1800201c1  jnz     short loc_1800201CF
0x1800201c3  mov     rax, cs:g_pfnFree
0x1800201ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201cf  test    r14, r14
0x1800201d2  jz      short loc_1800201E6
0x1800201d4  mov     rcx, cs:hHeap; hHeap
0x1800201db  mov     r8, r14; lpMem
0x1800201de  xor     edx, edx; dwFlags
0x1800201e0  call    cs:__imp_HeapFree
0x1800201e6  mov     edx, 1
0x1800201eb  call    WppTraceIndent
0x1800201f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800201f7  cmp     rcx, rsi
0x1800201fa  jz      short loc_180020228
0x1800201fc  test    byte ptr [rcx+1Ch], 2
0x180020200  jz      short loc_180020228
0x180020202  cmp     byte ptr [rcx+19h], 5
0x180020206  jb      short loc_180020228
0x180020208  mov     r9, cs:WPP_pszIndent
0x18002020f  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180020216  mov     rcx, [rcx+10h]
0x18002021a  mov     edx, 62h ; 'b'
0x18002021f  mov     dword ptr [rsp+0A0h+pvPara], edi
0x180020223  call    WPP_SF_sD
0x180020228  mov     eax, edi
0x18002022a  mov     rcx, [rbp+70h+var_48]
0x18002022e  xor     rcx, rbp; StackCookie
0x180020231  call    __security_check_cookie
0x180020236  lea     rsp, [rbp+38h]
0x18002023a  pop     r15
0x18002023c  pop     r14
0x18002023e  pop     r13
0x180020240  pop     r12
0x180020242  pop     rdi
0x180020243  pop     rsi
0x180020244  pop     rbx
0x180020245  pop     rbp
0x180020246  retn
```
