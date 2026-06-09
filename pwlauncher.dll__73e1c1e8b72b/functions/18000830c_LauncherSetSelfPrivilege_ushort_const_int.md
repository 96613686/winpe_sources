# LauncherSetSelfPrivilege(ushort const *,int)

- ea: `0x18000830c`
- end: `0x18000847f`
- name: `?LauncherSetSelfPrivilege@@YAHPEBGH@Z`
- size: `371`
- prototype: `__int64 __fastcall(LPCWSTR lpName, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180005c98`

## callees

- `0x180005528`
- `0x18000810c`
- `0x18000830c`
- `0x180008ac8`
- `0x180008cf0`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x180008364`
- `ADVAPI32!OpenProcessToken` at `0x180008364`
- `KERNEL32!CloseHandle` at `0x180008408`
- `KERNEL32!CloseHandle` at `0x180008408`
- `KERNEL32!GetLastError` at `0x18000836e`
- `KERNEL32!GetLastError` at `0x1800083c9`
- `KERNEL32!GetLastError` at `0x180008434`
- `KERNEL32!GetLastError` at `0x18000836e`
- `KERNEL32!GetLastError` at `0x1800083c9`
- `KERNEL32!GetLastError` at `0x180008434`
- `KERNEL32!SetLastError` at `0x18000841c`
- `KERNEL32!SetLastError` at `0x18000841c`
- `KERNEL32!GetCurrentProcess` at `0x18000834e`
- `KERNEL32!GetCurrentProcess` at `0x18000834e`

## string_xrefs

- `0x18000839d`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
__int64 __fastcall LauncherSetSelfPrivilege(LPCWSTR lpName, int a2)
{
  unsigned int v2; // edi
  HANDLE CurrentProcess; // rax
  DWORD v6; // eax
  DWORD v7; // ebx
  DWORD LastError; // eax
  int v9; // r8d
  int v10; // r9d
  const char *v11; // rcx
  char v13; // [rsp+30h] [rbp-38h]
  void *TokenHandle; // [rsp+80h] [rbp+18h] BYREF

  v2 = 0;
  TokenHandle = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20u, &TokenHandle) )
  {
    if ( (unsigned int)LauncherSetPrivilege(TokenHandle, lpName, a2) )
    {
      v7 = 0;
      v2 = 1;
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          49,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          116,
          LastError);
    }
  }
  else
  {
    v6 = GetLastError();
    v7 = v6;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        112,
        v6);
  }
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  SetLastError(v7);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v13 = GetLastError();
    v11 = "Success";
    if ( !v2 )
      v11 = "Failure";
    WPP_SF_sdsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, v9, v10, 129, (__int64)v11, v13);
  }
  return v2;
}

```

## disassembly

```asm
0x18000830c  mov     rax, rsp
0x18000830f  push    rbx
0x180008310  push    rbp
0x180008311  push    rsi
0x180008312  push    rdi
0x180008313  sub     rsp, 48h
0x180008317  xor     edi, edi
0x180008319  mov     ebx, edx
0x18000831b  mov     [rax+18h], rdi
0x18000831f  mov     rsi, rcx
0x180008322  mov     rcx, cs:WPP_GLOBAL_Control
0x180008329  lea     rbp, WPP_GLOBAL_Control
0x180008330  cmp     rcx, rbp
0x180008333  jz      short loc_18000834E
0x180008335  test    byte ptr [rcx+1Ch], 8
0x180008339  jz      short loc_18000834E
0x18000833b  mov     rcx, [rcx+10h]
0x18000833f  lea     edx, [rdi+2Fh]
0x180008342  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x180008349  call    WPP_SF_
0x18000834e  call    cs:__imp_GetCurrentProcess
0x180008354  lea     r8, [rsp+68h+TokenHandle]; TokenHandle
0x18000835c  mov     edx, 20h ; ' '; DesiredAccess
0x180008361  mov     rcx, rax; ProcessHandle
0x180008364  call    cs:__imp_OpenProcessToken
0x18000836a  test    eax, eax
0x18000836c  jnz     short loc_1800083B2
0x18000836e  call    cs:__imp_GetLastError
0x180008374  mov     ebx, eax
0x180008376  mov     rcx, cs:WPP_GLOBAL_Control
0x18000837d  cmp     rcx, rbp
0x180008380  jz      short loc_1800083FB
0x180008382  test    byte ptr [rcx+1Ch], 1
0x180008386  jz      short loc_1800083FB
0x180008388  mov     dword ptr [rsp+68h+var_40], eax
0x18000838c  mov     edx, 30h ; '0'
0x180008391  mov     [rsp+68h+var_48], 270h
0x180008399  mov     rcx, [rcx+10h]
0x18000839d  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x1800083a4  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x1800083ab  call    WPP_SF_sdD
0x1800083b0  jmp     short loc_1800083FB
0x1800083b2  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x1800083ba  mov     r8d, ebx; int
0x1800083bd  mov     rdx, rsi; lpName
0x1800083c0  call    ?LauncherSetPrivilege@@YAHPEAXPEBGH@Z; LauncherSetPrivilege(void *,ushort const *,int)
0x1800083c5  test    eax, eax
0x1800083c7  jnz     short loc_1800083F6
0x1800083c9  call    cs:__imp_GetLastError
0x1800083cf  mov     ebx, eax
0x1800083d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083d8  cmp     rcx, rbp
0x1800083db  jz      short loc_1800083FB
0x1800083dd  test    byte ptr [rcx+1Ch], 1
0x1800083e1  jz      short loc_1800083FB
0x1800083e3  mov     dword ptr [rsp+68h+var_40], eax
0x1800083e7  mov     edx, 31h ; '1'
0x1800083ec  mov     [rsp+68h+var_48], 274h
0x1800083f4  jmp     short loc_180008399
0x1800083f6  xor     ebx, ebx
0x1800083f8  lea     edi, [rbx+1]
0x1800083fb  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x180008403  test    rcx, rcx
0x180008406  jz      short loc_18000841A
0x180008408  call    cs:__imp_CloseHandle
0x18000840e  mov     [rsp+68h+TokenHandle], 0
0x18000841a  mov     ecx, ebx; dwErrCode
0x18000841c  call    cs:__imp_SetLastError
0x180008422  mov     rax, cs:WPP_GLOBAL_Control
0x180008429  cmp     rax, rbp
0x18000842c  jz      short loc_180008474
0x18000842e  test    byte ptr [rax+1Ch], 4
0x180008432  jz      short loc_180008474
0x180008434  call    cs:__imp_GetLastError
0x18000843a  lea     rdx, aFailure; "Failure"
0x180008441  mov     dword ptr [rsp+68h+var_38], eax
0x180008445  test    edi, edi
0x180008447  lea     rcx, aSuccess; "Success"
0x18000844e  cmovz   rcx, rdx
0x180008452  mov     edx, 32h ; '2'
0x180008457  mov     [rsp+68h+var_40], rcx
0x18000845c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008463  mov     [rsp+68h+var_48], 281h
0x18000846b  mov     rcx, [rcx+10h]
0x18000846f  call    WPP_SF_sdsd
0x180008474  mov     eax, edi
0x180008476  add     rsp, 48h
0x18000847a  pop     rdi
0x18000847b  pop     rsi
0x18000847c  pop     rbp
0x18000847d  pop     rbx
0x18000847e  retn
```
