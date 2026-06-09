# UtilRegSetCurrentTime(HKEY__ *,wchar_t const *,wchar_t const *)

- ea: `0x18003c178`
- end: `0x18003c33b`
- name: `?UtilRegSetCurrentTime@@YAJPEAUHKEY__@@PEB_W1@Z`
- size: `451`
- prototype: `__int64 __fastcall(HKEY hKey, const wchar_t *, const wchar_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e7c0`
- `0x18002c8c8`
- `0x18002f798`
- `0x180034498`
- `0x180035fe4`

## callees

- `0x180009ed8`
- `0x18003c178`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003c2a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003c2a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c2d3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c2d3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c232`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c232`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c1e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c252`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c321`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c1e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c252`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c321`

## pseudocode

```c
__int64 __fastcall UtilRegSetCurrentTime(HKEY hKey, const wchar_t *a2, const wchar_t *a3)
{
  HKEY v5; // rcx
  LSTATUS v7; // ebx
  HKEY v8; // rcx
  unsigned int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  int v12; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-18h] BYREF
  HKEY *p_hKeya; // [rsp+60h] [rbp-10h]
  struct _FILETIME Data; // [rsp+88h] [rbp+18h] BYREF
  HKEY hKeya; // [rsp+98h] [rbp+28h] BYREF

  v5 = 0;
  hKeya = 0;
  SystemTimeAsFileTime = 0;
  Data = 0;
  if ( __PAIR128__((unsigned __int64)hKey, 0) == (unsigned __int64)a2 || !a3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
      v5 = hKeya;
    }
    if ( v5 )
      RegCloseKey(v5);
    return 2147942487LL;
  }
  if ( a2 )
  {
    p_hKeya = &hKeya;
    phkResult = 0;
    v7 = RegCreateKeyExW(hKey, a2, 0, 0, 0, 0x20106u, 0, &phkResult, 0);
    if ( phkResult )
    {
      v8 = *p_hKeya;
      *p_hKeya = phkResult;
      if ( v8 )
        RegCloseKey(v8);
    }
    if ( v7 )
    {
      v9 = -2147467259;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_26;
      v11 = 88;
      goto LABEL_17;
    }
    hKey = hKeya;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  Data = SystemTimeAsFileTime;
  v12 = RegSetValueExW(hKey, a3, 0, 0xBu, (const BYTE *)&Data, 8u);
  if ( !v12 )
  {
    v9 = 0;
    goto LABEL_26;
  }
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80070000;
  v9 = v12;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_26;
  v11 = 89;
LABEL_17:
  WPP_SF_(v10[2], v11, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
LABEL_26:
  if ( hKeya )
    RegCloseKey(hKeya);
  return v9;
}

```

## disassembly

```asm
0x18003c178  mov     [rsp-8+arg_0], rbx
0x18003c17d  mov     [rsp-8+arg_10], rdi
0x18003c182  push    rbp
0x18003c183  mov     rbp, rsp
0x18003c186  sub     rsp, 70h
0x18003c18a  mov     rbx, rcx
0x18003c18d  mov     rdi, r8
0x18003c190  xor     ecx, ecx
0x18003c192  mov     [rbp+hKey], rcx
0x18003c196  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18003c19a  mov     [rbp+Data], rcx
0x18003c19e  test    rdx, rdx
0x18003c1a1  jnz     short loc_18003C1A8
0x18003c1a3  test    rbx, rbx
0x18003c1a6  jz      short loc_18003C1AD
0x18003c1a8  test    rdi, rdi
0x18003c1ab  jnz     short loc_18003C1F5
0x18003c1ad  mov     r9, cs:WPP_GLOBAL_Control
0x18003c1b4  lea     rax, WPP_GLOBAL_Control
0x18003c1bb  cmp     r9, rax
0x18003c1be  jz      short loc_18003C1E0
0x18003c1c0  test    byte ptr [r9+1Ch], 1
0x18003c1c5  jz      short loc_18003C1E0
0x18003c1c7  mov     rcx, [r9+10h]
0x18003c1cb  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003c1d2  mov     edx, 57h ; 'W'
0x18003c1d7  call    WPP_SF_
0x18003c1dc  mov     rcx, [rbp+hKey]; hKey
0x18003c1e0  test    rcx, rcx
0x18003c1e3  jz      short loc_18003C1EB
0x18003c1e5  call    cs:__imp_RegCloseKey
0x18003c1eb  mov     eax, 80070057h
0x18003c1f0  jmp     loc_18003C329
0x18003c1f5  test    rdx, rdx
0x18003c1f8  jz      loc_18003C29D
0x18003c1fe  mov     [rsp+70h+lpdwDisposition], rcx; lpdwDisposition
0x18003c203  lea     rax, [rbp+hKey]
0x18003c207  mov     [rbp+var_10], rax
0x18003c20b  xor     r9d, r9d; lpClass
0x18003c20e  lea     rax, [rbp+var_18]
0x18003c212  mov     [rbp+var_18], rcx
0x18003c216  mov     [rsp+70h+phkResult], rax; phkResult
0x18003c21b  xor     r8d, r8d; Reserved
0x18003c21e  mov     [rsp+70h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x18003c223  mov     [rsp+70h+samDesired], 20106h; samDesired
0x18003c22b  mov     [rsp+70h+dwOptions], ecx; dwOptions
0x18003c22f  mov     rcx, rbx; hKey
0x18003c232  call    cs:__imp_RegCreateKeyExW
0x18003c238  mov     r8, [rbp+var_18]
0x18003c23c  mov     ebx, eax
0x18003c23e  test    r8, r8
0x18003c241  jz      short loc_18003C258
0x18003c243  mov     rdx, [rbp+var_10]
0x18003c247  mov     rcx, [rdx]; hKey
0x18003c24a  mov     [rdx], r8
0x18003c24d  test    rcx, rcx
0x18003c250  jz      short loc_18003C258
0x18003c252  call    cs:__imp_RegCloseKey
0x18003c258  test    ebx, ebx
0x18003c25a  jz      short loc_18003C299
0x18003c25c  mov     ebx, 80004005h
0x18003c261  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c268  lea     rax, WPP_GLOBAL_Control
0x18003c26f  cmp     rcx, rax
0x18003c272  jz      loc_18003C318
0x18003c278  test    byte ptr [rcx+1Ch], 1
0x18003c27c  jz      loc_18003C318
0x18003c282  mov     edx, 58h ; 'X'
0x18003c287  mov     rcx, [rcx+10h]
0x18003c28b  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003c292  call    WPP_SF_
0x18003c297  jmp     short loc_18003C318
0x18003c299  mov     rbx, [rbp+hKey]
0x18003c29d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003c2a1  call    cs:__imp_GetSystemTimeAsFileTime
0x18003c2a7  mov     eax, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x18003c2aa  mov     r9d, 0Bh; dwType
0x18003c2b0  mov     dword ptr [rbp+Data+4], eax
0x18003c2b3  xor     r8d, r8d; Reserved
0x18003c2b6  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003c2b9  mov     rdx, rdi; lpValueName
0x18003c2bc  mov     dword ptr [rbp+Data], eax
0x18003c2bf  mov     rcx, rbx; hKey
0x18003c2c2  lea     rax, [rbp+Data]
0x18003c2c6  mov     [rsp+70h+samDesired], 8; cbData
0x18003c2ce  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x18003c2d3  call    cs:__imp_RegSetValueExW
0x18003c2d9  test    eax, eax
0x18003c2db  jz      short loc_18003C316
0x18003c2dd  jle     short loc_18003C2E7
0x18003c2df  movzx   eax, ax
0x18003c2e2  or      eax, 80070000h
0x18003c2e7  mov     ebx, 80004005h
0x18003c2ec  test    eax, eax
0x18003c2ee  cmovns  eax, ebx
0x18003c2f1  mov     ebx, eax
0x18003c2f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c2fa  lea     rax, WPP_GLOBAL_Control
0x18003c301  cmp     rcx, rax
0x18003c304  jz      short loc_18003C318
0x18003c306  test    byte ptr [rcx+1Ch], 1
0x18003c30a  jz      short loc_18003C318
0x18003c30c  mov     edx, 59h ; 'Y'
0x18003c311  jmp     loc_18003C287
0x18003c316  xor     ebx, ebx
0x18003c318  mov     rcx, [rbp+hKey]; hKey
0x18003c31c  test    rcx, rcx
0x18003c31f  jz      short loc_18003C327
0x18003c321  call    cs:__imp_RegCloseKey
0x18003c327  mov     eax, ebx
0x18003c329  lea     r11, [rsp+70h+var_s0]
0x18003c32e  mov     rbx, [r11+10h]
0x18003c332  mov     rdi, [r11+20h]
0x18003c336  mov     rsp, r11
0x18003c339  pop     rbp
0x18003c33a  retn
```
