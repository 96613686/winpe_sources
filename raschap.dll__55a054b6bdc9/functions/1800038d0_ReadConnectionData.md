# ReadConnectionData

- ea: `0x1800038d0`
- end: `0x180003aca`
- name: `ReadConnectionData`
- size: `506`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003200`
- `0x180016cb0`
- `0x180016ee0`
- `0x180017870`
- `0x18001cbe4`

## callees

- `0x1800014c0`
- `0x1800038d0`
- `0x180003bd0`
- `0x180004df0`
- `0x180006a20`
- `0x1800147cc`
- `0x180025efc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003957`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003957`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000390e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000397c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000390e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000397c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003aab`
- `SspiCli!FreeContextBuffer` at `0x1800039c5`
- `SspiCli!FreeContextBuffer` at `0x1800039c5`
- `SspiCli!QuerySecurityPackageInfoW` at `0x1800039af`
- `SspiCli!QuerySecurityPackageInfoW` at `0x1800039af`
- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_GetConfigForceNotDomainJoined` at `0x180003937`
- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_GetConfigForceNotDomainJoined` at `0x180003937`

## pseudocode

```c
__int64 __fastcall ReadConnectionData(char a1, const void *a2, unsigned int a3, _QWORD *a4)
{
  SIZE_T v5; // rbx
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  DWORD v10; // esi
  int v11; // edi
  size_t v13; // rsi
  _DWORD *v14; // rax
  unsigned int fCapabilities; // edi
  DWORD LastError; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  PSecPkgInfoW ppPackageInfo; // [rsp+20h] [rbp-48h] BYREF

  v5 = a3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
  if ( (unsigned int)v5 < 8 || !a2 )
  {
    v8 = LocalAlloc(0x40u, 8u);
    v9 = v8;
    if ( v8 )
    {
      v10 = 0;
      *v8 = 1;
      v11 = 0;
      if ( (unsigned __int8)IsRasChapExt_GetConfigIgnoreIASLogonPresent() )
      {
        if ( !(unsigned int)RasChapExt_GetConfigForceNotDomainJoined() )
          v11 = isMachineJoinedToDomain();
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
      }
      if ( a1 < 0 && ((a1 & 0x20) != 0 || v11) && (unsigned int)IsLogonCredAllowed() )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids);
        v9[1] = 2;
      }
      goto LABEL_9;
    }
    LastError = GetLastError();
    v10 = LastError;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_10;
    v18 = 11;
LABEL_27:
    WPP_SF_d(v17[2], v18, &WPP_6ebde121e3c33d342fae613342d287d2_Traceguids, LastError);
    goto LABEL_10;
  }
  v13 = v5;
  v14 = LocalAlloc(0x40u, v5);
  v9 = v14;
  if ( !v14 )
  {
    LastError = GetLastError();
    v10 = LastError;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_10;
    v18 = 14;
    goto LABEL_27;
  }
  memcpy_0(v14, a2, v13);
  v10 = 0;
  ppPackageInfo = 0;
  if ( !QuerySecurityPackageInfoW((LPWSTR)L"NTLM", &ppPackageInfo) )
  {
    if ( ppPackageInfo )
    {
      fCapabilities = ppPackageInfo->fCapabilities;
      FreeContextBuffer(ppPackageInfo);
      if ( (fCapabilities & 0x1000000) != 0 )
        v9[1] &= ~2u;
    }
  }
LABEL_9:
  *a4 = v9;
LABEL_10:
  LocalFree(0);
  return v10;
}

```

## disassembly

```asm
0x1800038d0  push    rbx
0x1800038d2  push    rbp
0x1800038d3  push    rsi
0x1800038d4  push    rdi
0x1800038d5  push    r14
0x1800038d7  push    r15
0x1800038d9  sub     rsp, 38h
0x1800038dd  mov     r14, r9
0x1800038e0  mov     ebx, r8d
0x1800038e3  mov     rdi, rdx
0x1800038e6  mov     ebp, ecx
0x1800038e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038ef  lea     r15, WPP_GLOBAL_Control
0x1800038f6  cmp     rcx, r15
0x1800038f9  jnz     loc_180003A85
0x1800038ff  cmp     ebx, 8
0x180003902  jnb     short loc_18000396C
0x180003904  mov     edx, 8; uBytes
0x180003909  mov     ecx, 40h ; '@'; uFlags
0x18000390e  call    cs:__imp_LocalAlloc
0x180003914  mov     rbx, rax
0x180003917  test    rax, rax
0x18000391a  jz      loc_180003A50
0x180003920  xor     esi, esi
0x180003922  mov     dword ptr [rax], 1
0x180003928  mov     edi, esi
0x18000392a  call    IsRasChapExt_GetConfigIgnoreIASLogonPresent
0x18000392f  test    al, al
0x180003931  jz      loc_180003A26
0x180003937  call    cs:__imp_RasChapExt_GetConfigForceNotDomainJoined
0x18000393d  test    eax, eax
0x18000393f  jz      loc_180003A9F
0x180003945  test    bpl, bpl
0x180003948  js      loc_1800039DE
0x18000394e  mov     [r14], rbx
0x180003951  mov     rbx, rsi
0x180003954  mov     rcx, rbx; hMem
0x180003957  call    cs:__imp_LocalFree
0x18000395d  mov     eax, esi
0x18000395f  add     rsp, 38h
0x180003963  pop     r15
0x180003965  pop     r14
0x180003967  pop     rdi
0x180003968  pop     rsi
0x180003969  pop     rbp
0x18000396a  pop     rbx
0x18000396b  retn
0x18000396c  test    rdi, rdi
0x18000396f  jz      short loc_180003904
0x180003971  mov     rdx, rbx; uBytes
0x180003974  mov     ecx, 40h ; '@'; uFlags
0x180003979  mov     rsi, rbx
0x18000397c  call    cs:__imp_LocalAlloc
0x180003982  mov     rbx, rax
0x180003985  test    rax, rax
0x180003988  jz      loc_180003AAB
0x18000398e  mov     r8, rsi; Size
0x180003991  mov     rdx, rdi; Src
0x180003994  mov     rcx, rax; void *
0x180003997  call    memcpy_0
0x18000399c  xor     esi, esi
0x18000399e  lea     rdx, [rsp+68h+ppPackageInfo]; ppPackageInfo
0x1800039a3  lea     rcx, pszPackageName; "NTLM"
0x1800039aa  mov     [rsp+68h+ppPackageInfo], rsi
0x1800039af  call    cs:__imp_QuerySecurityPackageInfoW
0x1800039b5  test    eax, eax
0x1800039b7  jnz     short loc_18000394E
0x1800039b9  mov     rcx, [rsp+68h+ppPackageInfo]; pvContextBuffer
0x1800039be  test    rcx, rcx
0x1800039c1  jz      short loc_18000394E
0x1800039c3  mov     edi, [rcx]
0x1800039c5  call    cs:__imp_FreeContextBuffer
0x1800039cb  bt      edi, 18h
0x1800039cf  jnb     loc_18000394E
0x1800039d5  and     dword ptr [rbx+4], 0FFFFFFFDh
0x1800039d9  jmp     loc_18000394E
0x1800039de  test    bpl, 20h
0x1800039e2  jnz     short loc_1800039EC
0x1800039e4  test    edi, edi
0x1800039e6  jz      loc_18000394E
0x1800039ec  call    IsLogonCredAllowed
0x1800039f1  test    eax, eax
0x1800039f3  jz      loc_18000394E
0x1800039f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a00  cmp     rcx, r15
0x180003a03  jz      short loc_180003A1A
0x180003a05  mov     rcx, [rcx+10h]
0x180003a09  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x180003a10  mov     edx, 0Dh
0x180003a15  call    WPP_SF_
0x180003a1a  mov     dword ptr [rbx+4], 2
0x180003a21  jmp     loc_18000394E
0x180003a26  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a2d  cmp     rcx, r15
0x180003a30  jz      loc_180003945
0x180003a36  mov     rcx, [rcx+10h]
0x180003a3a  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x180003a41  mov     edx, 0Ch
0x180003a46  call    WPP_SF_
0x180003a4b  jmp     loc_180003945
0x180003a50  call    cs:__imp_GetLastError
0x180003a56  mov     esi, eax
0x180003a58  mov     rcx, cs:WPP_GLOBAL_Control
0x180003a5f  cmp     rcx, r15
0x180003a62  jz      loc_180003954
0x180003a68  mov     edx, 0Bh
0x180003a6d  mov     rcx, [rcx+10h]
0x180003a71  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x180003a78  mov     r9d, eax
0x180003a7b  call    WPP_SF_d
0x180003a80  jmp     loc_180003954
0x180003a85  mov     rcx, [rcx+10h]
0x180003a89  lea     r8, WPP_6ebde121e3c33d342fae613342d287d2_Traceguids
0x180003a90  mov     edx, 0Ah
0x180003a95  call    WPP_SF_
0x180003a9a  jmp     loc_1800038FF
0x180003a9f  call    isMachineJoinedToDomain
0x180003aa4  mov     edi, eax
0x180003aa6  jmp     loc_180003945
0x180003aab  call    cs:__imp_GetLastError
0x180003ab1  mov     esi, eax
0x180003ab3  mov     rcx, cs:WPP_GLOBAL_Control
0x180003aba  cmp     rcx, r15
0x180003abd  jz      loc_180003954
0x180003ac3  mov     edx, 0Eh
0x180003ac8  jmp     short loc_180003A6D
```
