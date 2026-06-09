# LsarEasMarkUserControlled

- ea: `0x1800faef0`
- end: `0x1800fb3b6`
- name: `LsarEasMarkUserControlled`
- size: `1222`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000c300`
- `0x180011278`
- `0x180014954`
- `0x180016f70`
- `0x1800f9af0`
- `0x1800fa3d8`
- `0x1800faef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800faf72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fb01e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800faf72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fb01e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fb354`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fb376`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fb354`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800fb376`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fb38b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fb38b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fb188`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fb188`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800fb256`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800fb256`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800faf62`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800faf62`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800fb00e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800fb00e`

## pseudocode

```c
__int64 __fastcall LsarEasMarkUserControlled(__int64 a1, __int64 a2, int a3, int a4, int a5)
{
  WCHAR *v7; // r15
  const WCHAR *v8; // rdi
  signed int LastError; // eax
  void *v10; // rdx
  int v11; // ebx
  LsaHandleCache *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  signed int v15; // eax
  __int64 v16; // rax
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rbx
  unsigned __int16 *v19; // rax
  LSTATUS v20; // eax
  PSID Sid; // [rsp+50h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-20h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-18h] BYREF
  DWORD dwDisposition; // [rsp+B8h] [rbp+38h] BYREF

  dwDisposition = 0;
  Sid = 0;
  SecurityDescriptor = 0;
  v7 = 0;
  hKey = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  if ( *(_WORD *)(a2 + 2) < 2u
    || (v8 = *(const WCHAR **)(a2 + 8), v8[((unsigned __int64)*(unsigned __int16 *)(a2 + 2) - 2) >> 1]) )
  {
    v11 = -1073741811;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return (unsigned int)v11;
    v13 = 38;
    v14 = 3221225485LL;
    goto LABEL_65;
  }
  if ( !ConvertStringSidToSidW(v8, &Sid) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0xC0070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_66;
    v13 = 39;
    goto LABEL_9;
  }
  v11 = _CheckEasAccess(Sid, a3);
  if ( v11 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_66;
    v13 = 40;
    goto LABEL_9;
  }
  if ( a3 )
  {
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:(A;;GR;;;AU)(A;;GA;;;BA)(A;;GA;;;SY)",
            1u,
            &SecurityDescriptor,
            0) )
    {
      v15 = GetLastError();
      v11 = v15;
      if ( v15 > 0 )
        v11 = (unsigned __int16)v15 | 0xC0070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_66;
      v13 = 41;
      goto LABEL_9;
    }
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    v16 = -1;
    SecurityAttributes.nLength = 24;
    do
      ++v16;
    while ( v8[v16] );
    if ( (int)v16 + 63 < (unsigned int)v16 )
    {
      v11 = -1073741675;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_66;
      v13 = 42;
      goto LABEL_27;
    }
    v17 = 2LL * (unsigned int)(v16 + 63);
    if ( v17 > 0xFFFFFFFF )
    {
      v11 = -1073741675;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_66;
      v13 = 43;
LABEL_27:
      v14 = 3221225621LL;
      goto LABEL_65;
    }
    v18 = (unsigned int)v17;
    v19 = (unsigned __int16 *)LsapAllocate((unsigned int)v17);
    v7 = v19;
    if ( !v19 )
    {
      v11 = -1073741801;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_66;
      v13 = 44;
      v14 = 3221225495LL;
      goto LABEL_65;
    }
    v11 = RtlStringCchPrintfW(
            v19,
            v18 >> 1,
            L"%ws%ws",
            L"SYSTEM\\CurrentControlSet\\Control\\EAS\\Policies\\ControlledUsers\\",
            v8);
    if ( v11 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_66;
      v13 = 45;
      goto LABEL_9;
    }
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 1u, &hKey);
    if ( (unsigned int)(v11 - 2) <= 1 )
    {
      v11 = _ResetLocalUserPasswordData(Sid, 1, a4, a5);
      if ( v11 < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_66;
        }
        v13 = 46;
        goto LABEL_9;
      }
      v20 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0, 0, 0xF003Fu, &SecurityAttributes, &hKey, &dwDisposition);
      v11 = v20;
      if ( v20 )
      {
        if ( v20 > 0 )
          v11 = (unsigned __int16)v20 | 0xC0070000;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_66;
        }
        v13 = 47;
LABEL_9:
        v14 = (unsigned int)v11;
LABEL_65:
        WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_545c8b7f486339e055cd0f4d1a7ce3f2_Traceguids, v14);
        goto LABEL_66;
      }
    }
    else if ( v11 )
    {
      if ( v11 > 0 )
        v11 = (unsigned __int16)v11 | 0xC0070000;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_66;
      v13 = 48;
      goto LABEL_9;
    }
  }
  else
  {
    v11 = _ResetLocalUserPasswordData(Sid, 0, a4, a5);
    if ( v11 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_66;
      v13 = 49;
      goto LABEL_9;
    }
  }
  v11 = 0;
LABEL_66:
  if ( Sid )
    LocalFree(Sid);
  if ( v7 )
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v7, v10);
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800faef0  mov     [rsp-28h+arg_0], rbx
0x1800faef5  mov     [rsp-28h+arg_10], rsi
0x1800faefa  push    rbp
0x1800faefb  push    rdi
0x1800faefc  push    r12
0x1800faefe  push    r14
0x1800faf00  push    r15
0x1800faf02  mov     rbp, rsp
0x1800faf05  sub     rsp, 80h
0x1800faf0c  xor     r12d, r12d
0x1800faf0f  xor     eax, eax
0x1800faf11  xorps   xmm0, xmm0
0x1800faf14  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], rax
0x1800faf18  mov     r14d, r9d
0x1800faf1b  mov     [rbp+dwDisposition], r12d
0x1800faf1f  mov     esi, r8d
0x1800faf22  mov     [rbp+Sid], r12
0x1800faf26  lea     ecx, [rax+2]
0x1800faf29  mov     [rbp+SecurityDescriptor], r12
0x1800faf2d  mov     r15d, r12d
0x1800faf30  mov     [rbp+hKey], r12
0x1800faf34  movups  xmmword ptr [rbp+SecurityAttributes.nLength], xmm0
0x1800faf38  cmp     [rdx+2], cx
0x1800faf3c  jb      loc_1800FB312
0x1800faf42  movzx   eax, word ptr [rdx+2]
0x1800faf46  mov     rdi, [rdx+8]
0x1800faf4a  sub     rax, rcx
0x1800faf4d  shr     rax, 1
0x1800faf50  cmp     [rdi+rax*2], r12w
0x1800faf55  jnz     loc_1800FB312
0x1800faf5b  lea     rdx, [rbp+Sid]; Sid
0x1800faf5f  mov     rcx, rdi; StringSid
0x1800faf62  call    cs:__imp_ConvertStringSidToSidW
0x1800faf69  nop     dword ptr [rax+rax+00h]
0x1800faf6e  test    eax, eax
0x1800faf70  jnz     short loc_1800FAFBB
0x1800faf72  call    cs:__imp_GetLastError
0x1800faf79  nop     dword ptr [rax+rax+00h]
0x1800faf7e  mov     ebx, eax
0x1800faf80  test    eax, eax
0x1800faf82  jle     short loc_1800FAF8D
0x1800faf84  movzx   ebx, ax
0x1800faf87  or      ebx, 0C0070000h
0x1800faf8d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800faf94  lea     rax, WPP_GLOBAL_Control
0x1800faf9b  cmp     rcx, rax
0x1800faf9e  jz      loc_1800FB34B
0x1800fafa4  test    byte ptr [rcx+1Ch], 1
0x1800fafa8  jz      loc_1800FB34B
0x1800fafae  mov     edx, 27h ; '''
0x1800fafb3  mov     r9d, ebx
0x1800fafb6  jmp     loc_1800FB33B
0x1800fafbb  mov     rcx, [rbp+Sid]; SidToCheck
0x1800fafbf  mov     edx, esi; int
0x1800fafc1  call    ?_CheckEasAccess@@YAJPEAXH@Z; _CheckEasAccess(void *,int)
0x1800fafc6  mov     ebx, eax
0x1800fafc8  test    eax, eax
0x1800fafca  jns     short loc_1800FAFF4
0x1800fafcc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fafd3  lea     rax, WPP_GLOBAL_Control
0x1800fafda  cmp     rcx, rax
0x1800fafdd  jz      loc_1800FB34B
0x1800fafe3  test    byte ptr [rcx+1Ch], 1
0x1800fafe7  jz      loc_1800FB34B
0x1800fafed  mov     edx, 28h ; '('
0x1800faff2  jmp     short loc_1800FAFB3
0x1800faff4  test    esi, esi
0x1800faff6  jz      loc_1800FB2D2
0x1800faffc  xor     r9d, r9d; SecurityDescriptorSize
0x1800fafff  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800fb003  lea     rcx, StringSecurityDescriptor; "D:(A;;GR;;;AU)(A;;GA;;;BA)(A;;GA;;;SY)"
0x1800fb00a  lea     edx, [r9+1]; StringSDRevision
0x1800fb00e  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800fb015  nop     dword ptr [rax+rax+00h]
0x1800fb01a  test    eax, eax
0x1800fb01c  jnz     short loc_1800FB064
0x1800fb01e  call    cs:__imp_GetLastError
0x1800fb025  nop     dword ptr [rax+rax+00h]
0x1800fb02a  mov     ebx, eax
0x1800fb02c  test    eax, eax
0x1800fb02e  jle     short loc_1800FB039
0x1800fb030  movzx   ebx, ax
0x1800fb033  or      ebx, 0C0070000h
0x1800fb039  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fb040  lea     rax, WPP_GLOBAL_Control
0x1800fb047  cmp     rcx, rax
0x1800fb04a  jz      loc_1800FB34B
0x1800fb050  test    byte ptr [rcx+1Ch], 1
0x1800fb054  jz      loc_1800FB34B
0x1800fb05a  mov     edx, 29h ; ')'
0x1800fb05f  jmp     loc_1800FAFB3
0x1800fb064  mov     rax, [rbp+SecurityDescriptor]
0x1800fb068  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rax
0x1800fb06c  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800fb070  mov     [rbp+SecurityAttributes.nLength], 18h
0x1800fb077  inc     rax
0x1800fb07a  cmp     [rdi+rax*2], r12w
0x1800fb07f  jnz     short loc_1800FB077
0x1800fb081  lea     ecx, [rax+3Fh]
0x1800fb084  cmp     ecx, eax
0x1800fb086  jnb     short loc_1800FB0BE
0x1800fb088  mov     ebx, 0C0000095h
0x1800fb08d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fb094  lea     rax, WPP_GLOBAL_Control
0x1800fb09b  cmp     rcx, rax
0x1800fb09e  jz      loc_1800FB34B
0x1800fb0a4  test    byte ptr [rcx+1Ch], 1
0x1800fb0a8  jz      loc_1800FB34B
0x1800fb0ae  mov     edx, 2Ah ; '*'
0x1800fb0b3  mov     r9d, 0C0000095h
0x1800fb0b9  jmp     loc_1800FB33B
0x1800fb0be  mov     eax, ecx
0x1800fb0c0  mov     ecx, 0FFFFFFFFh
0x1800fb0c5  add     rax, rax
0x1800fb0c8  cmp     rax, rcx
0x1800fb0cb  ja      loc_1800FB2A2
0x1800fb0d1  mov     ecx, eax
0x1800fb0d3  mov     ebx, eax
0x1800fb0d5  call    LsapAllocate
0x1800fb0da  mov     r15, rax
0x1800fb0dd  test    rax, rax
0x1800fb0e0  jnz     short loc_1800FB117
0x1800fb0e2  mov     ebx, 0C0000017h
0x1800fb0e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fb0ee  lea     rax, WPP_GLOBAL_Control
0x1800fb0f5  cmp     rcx, rax
0x1800fb0f8  jz      loc_1800FB34B
0x1800fb0fe  test    byte ptr [rcx+1Ch], 1
0x1800fb102  jz      loc_1800FB34B
0x1800fb108  lea     edx, [r15+2Ch]
0x1800fb10c  mov     r9d, 0C0000017h
0x1800fb112  jmp     loc_1800FB33B
0x1800fb117  shr     rbx, 1
0x1800fb11a  lea     r9, aSystemCurrentc_3; "SYSTEM\\CurrentControlSet\\Control\\EAS"...
0x1800fb121  mov     rdx, rbx; unsigned __int64
0x1800fb124  mov     [rsp+80h+phkResult], rdi
0x1800fb129  lea     r8, aWsWs; "%ws%ws"
0x1800fb130  mov     rcx, r15; unsigned __int16 *
0x1800fb133  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800fb138  mov     ebx, eax
0x1800fb13a  test    eax, eax
0x1800fb13c  jns     short loc_1800FB169
0x1800fb13e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fb145  lea     rax, WPP_GLOBAL_Control
0x1800fb14c  cmp     rcx, rax
0x1800fb14f  jz      loc_1800FB34B
0x1800fb155  test    byte ptr [rcx+1Ch], 1
0x1800fb159  jz      loc_1800FB34B
0x1800fb15f  mov     edx, 2Dh ; '-'
0x1800fb164  jmp     loc_1800FAFB3
0x1800fb169  lea     rax, [rbp+hKey]
0x1800fb16d  mov     rdi, 0FFFFFFFF80000002h
0x1800fb174  mov     rcx, rdi; hKey
0x1800fb177  mov     [rsp+80h+phkResult], rax; phkResult
0x1800fb17c  mov     r9d, 1; samDesired
0x1800fb182  xor     r8d, r8d; ulOptions
0x1800fb185  mov     rdx, r15; lpSubKey
0x1800fb188  call    cs:__imp_RegOpenKeyExW
0x1800fb18f  nop     dword ptr [rax+rax+00h]
0x1800fb194  mov     ebx, eax
0x1800fb196  add     eax, 0FFFFFFFEh
0x1800fb199  cmp     eax, 1
0x1800fb19c  jbe     short loc_1800FB1DC
0x1800fb19e  test    ebx, ebx
0x1800fb1a0  jz      loc_1800FB30D
0x1800fb1a6  jle     short loc_1800FB1B1
0x1800fb1a8  movzx   ebx, bx
0x1800fb1ab  or      ebx, 0C0070000h
0x1800fb1b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fb1b8  lea     rax, WPP_GLOBAL_Control
0x1800fb1bf  cmp     rcx, rax
0x1800fb1c2  jz      loc_1800FB34B
0x1800fb1c8  test    byte ptr [rcx+1Ch], 1
0x1800fb1cc  jz      loc_1800FB34B
0x1800fb1d2  mov     edx, 30h ; '0'
0x1800fb1d7  jmp     loc_1800FAFB3
0x1800fb1dc  mov     r9d, [rbp+arg_20]; int
0x1800fb1e0  mov     r8d, r14d; int
0x1800fb1e3  mov     rcx, [rbp+Sid]; void *
0x1800fb1e7  mov     edx, 1; int
0x1800fb1ec  call    ?_ResetLocalUserPasswordData@@YAJPEAXHHH@Z; _ResetLocalUserPasswordData(void *,int,int,int)
0x1800fb1f1  mov     ebx, eax
0x1800fb1f3  test    eax, eax
0x1800fb1f5  jns     short loc_1800FB222
0x1800fb1f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fb1fe  lea     rax, WPP_GLOBAL_Control
0x1800fb205  cmp     rcx, rax
0x1800fb208  jz      loc_1800FB34B
0x1800fb20e  test    byte ptr [rcx+1Ch], 1
0x1800fb212  jz      loc_1800FB34B
0x1800fb218  mov     edx, 2Eh ; '.'
0x1800fb21d  jmp     loc_1800FAFB3
0x1800fb222  lea     rax, [rbp+dwDisposition]
0x1800fb226  xor     r9d, r9d; lpClass
0x1800fb229  mov     [rsp+80h+lpdwDisposition], rax; lpdwDisposition
0x1800fb22e  xor     r8d, r8d; Reserved
0x1800fb231  lea     rax, [rbp+hKey]
0x1800fb235  mov     rdx, r15; lpSubKey
0x1800fb238  mov     [rsp+80h+var_48], rax; phkResult
0x1800fb23d  mov     rcx, rdi; hKey
0x1800fb240  lea     rax, [rbp+SecurityAttributes]
0x1800fb244  mov     [rsp+80h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800fb249  mov     [rsp+80h+samDesired], 0F003Fh; samDesired
0x1800fb251  mov     dword ptr [rsp+80h+phkResult], r12d; dwOptions
0x1800fb256  call    cs:__imp_RegCreateKeyExW
0x1800fb25d  nop     dword ptr [rax+rax+00h]
0x1800fb262  mov     ebx, eax
0x1800fb264  test    eax, eax
0x1800fb266  jz      loc_1800FB30D
0x1800fb26c  jle     short loc_1800FB277
0x1800fb26e  movzx   ebx, ax
0x1800fb271  or      ebx, 0C0070000h
0x1800fb277  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fb27e  lea     rax, WPP_GLOBAL_Control
0x1800fb285  cmp     rcx, rax
0x1800fb288  jz      loc_1800FB34B
0x1800fb28e  test    byte ptr [rcx+1Ch], 1
0x1800fb292  jz      loc_1800FB34B
0x1800fb298  mov     edx, 2Fh ; '/'
0x1800fb29d  jmp     loc_1800FAFB3
0x1800fb2a2  mov     ebx, 0C0000095h
0x1800fb2a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fb2ae  lea     rax, WPP_GLOBAL_Control
0x1800fb2b5  cmp     rcx, rax
0x1800fb2b8  jz      loc_1800FB34B
0x1800fb2be  test    byte ptr [rcx+1Ch], 1
0x1800fb2c2  jz      loc_1800FB34B
0x1800fb2c8  mov     edx, 2Bh ; '+'
0x1800fb2cd  jmp     loc_1800FB0B3
0x1800fb2d2  mov     r9d, [rbp+arg_20]; int
0x1800fb2d6  mov     r8d, r14d; int
0x1800fb2d9  mov     rcx, [rbp+Sid]; void *
0x1800fb2dd  xor     edx, edx; int
0x1800fb2df  call    ?_ResetLocalUserPasswordData@@YAJPEAXHHH@Z; _ResetLocalUserPasswordData(void *,int,int,int)
0x1800fb2e4  mov     ebx, eax
0x1800fb2e6  test    eax, eax
0x1800fb2e8  jns     short loc_1800FB30D
0x1800fb2ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fb2f1  lea     rax, WPP_GLOBAL_Control
0x1800fb2f8  cmp     rcx, rax
0x1800fb2fb  jz      short loc_1800FB34B
0x1800fb2fd  test    byte ptr [rcx+1Ch], 1
0x1800fb301  jz      short loc_1800FB34B
0x1800fb303  mov     edx, 31h ; '1'
0x1800fb308  jmp     loc_1800FAFB3
0x1800fb30d  mov     ebx, r12d
0x1800fb310  jmp     short loc_1800FB34B
0x1800fb312  mov     ebx, 0C000000Dh
0x1800fb317  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fb31e  lea     rax, WPP_GLOBAL_Control
0x1800fb325  cmp     rcx, rax
0x1800fb328  jz      short loc_1800FB397
0x1800fb32a  test    byte ptr [rcx+1Ch], 1
0x1800fb32e  jz      short loc_1800FB397
0x1800fb330  mov     edx, 26h ; '&'
0x1800fb335  mov     r9d, 0C000000Dh
0x1800fb33b  mov     rcx, [rcx+10h]
0x1800fb33f  lea     r8, WPP_545c8b7f486339e055cd0f4d1a7ce3f2_Traceguids
0x1800fb346  call    WPP_SF_d
0x1800fb34b  mov     rcx, [rbp+Sid]; hMem
0x1800fb34f  test    rcx, rcx
0x1800fb352  jz      short loc_1800FB360
0x1800fb354  call    cs:__imp_LocalFree
0x1800fb35b  nop     dword ptr [rax+rax+00h]
0x1800fb360  test    r15, r15
0x1800fb363  jz      short loc_1800FB36D
0x1800fb365  mov     rcx, r15; struct _RTL_BALANCED_NODE *
0x1800fb368  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800fb36d  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800fb371  test    rcx, rcx
0x1800fb374  jz      short loc_1800FB382
0x1800fb376  call    cs:__imp_LocalFree
0x1800fb37d  nop     dword ptr [rax+rax+00h]
0x1800fb382  mov     rcx, [rbp+hKey]; hKey
0x1800fb386  test    rcx, rcx
0x1800fb389  jz      short loc_1800FB397
0x1800fb38b  call    cs:__imp_RegCloseKey
0x1800fb392  nop     dword ptr [rax+rax+00h]
0x1800fb397  lea     r11, [rsp+80h+var_s0]
0x1800fb39f  mov     eax, ebx
0x1800fb3a1  mov     rbx, [r11+30h]
0x1800fb3a5  mov     rsi, [r11+40h]
0x1800fb3a9  mov     rsp, r11
0x1800fb3ac  pop     r15
0x1800fb3ae  pop     r14
0x1800fb3b0  pop     r12
0x1800fb3b2  pop     rdi
0x1800fb3b3  pop     rbp
0x1800fb3b4  retn
```
