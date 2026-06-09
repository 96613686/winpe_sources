# LauncherSetPrivilege(void *,ushort const *,int)

- ea: `0x18000810c`
- end: `0x180008305`
- name: `?LauncherSetPrivilege@@YAHPEAXPEBGH@Z`
- size: `505`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPCWSTR lpName, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000830c`

## callees

- `0x180005528`
- `0x18000810c`
- `0x180008ac8`
- `0x180008cf0`
- `0x18000fe10`

## import_xrefs

- `ADVAPI32!LookupPrivilegeValueW` at `0x18000817b`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18000817b`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18000820b`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18000820b`
- `KERNEL32!GetLastError` at `0x180008185`
- `KERNEL32!GetLastError` at `0x180008215`
- `KERNEL32!GetLastError` at `0x180008245`
- `KERNEL32!GetLastError` at `0x180008252`
- `KERNEL32!GetLastError` at `0x1800082a1`
- `KERNEL32!GetLastError` at `0x180008185`
- `KERNEL32!GetLastError` at `0x180008215`
- `KERNEL32!GetLastError` at `0x180008245`
- `KERNEL32!GetLastError` at `0x180008252`
- `KERNEL32!GetLastError` at `0x1800082a1`
- `KERNEL32!SetLastError` at `0x180008289`
- `KERNEL32!SetLastError` at `0x180008289`

## string_xrefs

- `0x1800081bc`: `drivers\wdm\usbpw\launcher\dll\pwboot.cpp`

## pseudocode

```c
__int64 __fastcall LauncherSetPrivilege(HANDLE TokenHandle, LPCWSTR lpName, int a3)
{
  unsigned int v3; // edi
  DWORD v7; // eax
  DWORD v8; // ebx
  DWORD v9; // eax
  DWORD LastError; // eax
  int v11; // r8d
  int v12; // r9d
  const char *v13; // rcx
  PDWORD ReturnLength; // [rsp+28h] [rbp-50h]
  char v16; // [rsp+30h] [rbp-48h]
  _LUID Luid; // [rsp+40h] [rbp-38h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-30h] BYREF

  v3 = 0;
  NewState = 0;
  Luid = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_a14d398675a93d8a8179cf1378ada974_Traceguids);
  if ( LookupPrivilegeValueW(0, lpName, &Luid) )
  {
    NewState.Privileges[0].Luid = Luid;
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Attributes = a3 != 0 ? 2 : 0;
    if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0) )
    {
      if ( GetLastError() == 1300 )
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LODWORD(ReturnLength) = LastError;
          WPP_SF_sdD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            45,
            (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
            (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
            66,
            ReturnLength);
        }
      }
      else
      {
        v8 = 0;
        v3 = 1;
      }
    }
    else
    {
      v9 = GetLastError();
      v8 = v9;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LODWORD(ReturnLength) = v9;
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          44,
          (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
          64,
          ReturnLength);
      }
    }
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        (unsigned int)&WPP_a14d398675a93d8a8179cf1378ada974_Traceguids,
        (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\pwboot.cpp",
        45,
        v7);
  }
  SetLastError(v8);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v16 = GetLastError();
    v13 = "Success";
    if ( !v3 )
      v13 = "Failure";
    WPP_SF_sdsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, v11, v12, 74, (__int64)v13, v16);
  }
  return v3;
}

```

## disassembly

```asm
0x18000810c  mov     [rsp+arg_10], rbx
0x180008111  mov     [rsp+arg_18], rbp
0x180008116  push    rsi
0x180008117  push    rdi
0x180008118  push    r15
0x18000811a  sub     rsp, 60h
0x18000811e  mov     rax, cs:__security_cookie
0x180008125  xor     rax, rsp
0x180008128  mov     [rsp+78h+var_20], rax
0x18000812d  xor     edi, edi
0x18000812f  xorps   xmm0, xmm0
0x180008132  movups  xmmword ptr [rsp+78h+NewState.PrivilegeCount], xmm0
0x180008137  mov     qword ptr [rsp+78h+Luid.LowPart], rdi
0x18000813c  mov     esi, r8d
0x18000813f  mov     rbx, rdx
0x180008142  mov     rbp, rcx
0x180008145  mov     rcx, cs:WPP_GLOBAL_Control
0x18000814c  lea     r15, WPP_GLOBAL_Control
0x180008153  cmp     rcx, r15
0x180008156  jz      short loc_180008171
0x180008158  test    byte ptr [rcx+1Ch], 8
0x18000815c  jz      short loc_180008171
0x18000815e  mov     rcx, [rcx+10h]
0x180008162  lea     edx, [rdi+2Ah]
0x180008165  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x18000816c  call    WPP_SF_
0x180008171  lea     r8, [rsp+78h+Luid]; lpLuid
0x180008176  mov     rdx, rbx; lpName
0x180008179  xor     ecx, ecx; lpSystemName
0x18000817b  call    cs:__imp_LookupPrivilegeValueW
0x180008181  test    eax, eax
0x180008183  jnz     short loc_1800081D4
0x180008185  call    cs:__imp_GetLastError
0x18000818b  mov     ebx, eax
0x18000818d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008194  cmp     rcx, r15
0x180008197  jz      loc_180008287
0x18000819d  test    byte ptr [rcx+1Ch], 1
0x1800081a1  jz      loc_180008287
0x1800081a7  mov     dword ptr [rsp+78h+ReturnLength], eax
0x1800081ab  mov     edx, 2Bh ; '+'
0x1800081b0  mov     dword ptr [rsp+78h+PreviousState], 22Dh
0x1800081b8  mov     rcx, [rcx+10h]
0x1800081bc  lea     r9, aDriversWdmUsbp_5; "drivers\\wdm\\usbpw\\launcher\\dll\\pwb"...
0x1800081c3  lea     r8, WPP_a14d398675a93d8a8179cf1378ada974_Traceguids
0x1800081ca  call    WPP_SF_sdD
0x1800081cf  jmp     loc_180008287
0x1800081d4  mov     rax, qword ptr [rsp+78h+Luid.LowPart]
0x1800081d9  lea     r8, [rsp+78h+NewState]; NewState
0x1800081de  mov     qword ptr [rsp+78h+NewState.Privileges.Luid.LowPart], rax
0x1800081e3  neg     esi
0x1800081e5  mov     [rsp+78h+ReturnLength], rdi; ReturnLength
0x1800081ea  mov     r9d, 10h; BufferLength
0x1800081f0  sbb     eax, eax
0x1800081f2  mov     [rsp+78h+NewState.PrivilegeCount], 1
0x1800081fa  and     eax, 2
0x1800081fd  mov     [rsp+78h+PreviousState], rdi; PreviousState
0x180008202  xor     edx, edx; DisableAllPrivileges
0x180008204  mov     [rsp+78h+NewState.Privileges.Attributes], eax
0x180008208  mov     rcx, rbp; TokenHandle
0x18000820b  call    cs:__imp_AdjustTokenPrivileges
0x180008211  test    eax, eax
0x180008213  jnz     short loc_180008245
0x180008215  call    cs:__imp_GetLastError
0x18000821b  mov     ebx, eax
0x18000821d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008224  cmp     rcx, r15
0x180008227  jz      short loc_180008287
0x180008229  test    byte ptr [rcx+1Ch], 1
0x18000822d  jz      short loc_180008287
0x18000822f  mov     dword ptr [rsp+78h+ReturnLength], eax
0x180008233  mov     edx, 2Ch ; ','
0x180008238  mov     dword ptr [rsp+78h+PreviousState], 240h
0x180008240  jmp     loc_1800081B8
0x180008245  call    cs:__imp_GetLastError
0x18000824b  cmp     eax, 514h
0x180008250  jnz     short loc_180008282
0x180008252  call    cs:__imp_GetLastError
0x180008258  mov     ebx, eax
0x18000825a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008261  cmp     rcx, r15
0x180008264  jz      short loc_180008287
0x180008266  test    byte ptr [rcx+1Ch], 1
0x18000826a  jz      short loc_180008287
0x18000826c  mov     dword ptr [rsp+78h+ReturnLength], eax
0x180008270  mov     edx, 2Dh ; '-'
0x180008275  mov     dword ptr [rsp+78h+PreviousState], 242h
0x18000827d  jmp     loc_1800081B8
0x180008282  xor     ebx, ebx
0x180008284  lea     edi, [rbx+1]
0x180008287  mov     ecx, ebx; dwErrCode
0x180008289  call    cs:__imp_SetLastError
0x18000828f  mov     rax, cs:WPP_GLOBAL_Control
0x180008296  cmp     rax, r15
0x180008299  jz      short loc_1800082E1
0x18000829b  test    byte ptr [rax+1Ch], 4
0x18000829f  jz      short loc_1800082E1
0x1800082a1  call    cs:__imp_GetLastError
0x1800082a7  lea     rdx, aFailure; "Failure"
0x1800082ae  mov     dword ptr [rsp+78h+var_48], eax
0x1800082b2  test    edi, edi
0x1800082b4  lea     rcx, aSuccess; "Success"
0x1800082bb  cmovz   rcx, rdx
0x1800082bf  mov     edx, 2Eh ; '.'
0x1800082c4  mov     [rsp+78h+ReturnLength], rcx
0x1800082c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082d0  mov     dword ptr [rsp+78h+PreviousState], 24Ah
0x1800082d8  mov     rcx, [rcx+10h]
0x1800082dc  call    WPP_SF_sdsd
0x1800082e1  mov     eax, edi
0x1800082e3  mov     rcx, [rsp+78h+var_20]
0x1800082e8  xor     rcx, rsp; StackCookie
0x1800082eb  call    __security_check_cookie
0x1800082f0  lea     r11, [rsp+78h+var_18]
0x1800082f5  mov     rbx, [r11+30h]
0x1800082f9  mov     rbp, [r11+38h]
0x1800082fd  mov     rsp, r11
0x180008300  pop     r15
0x180008302  pop     rdi
0x180008303  pop     rsi
0x180008304  retn
```
