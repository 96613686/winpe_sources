# Dhcpv4EnableDhcpEx

- ea: `0x18000c110`
- end: `0x18000c2bc`
- name: `Dhcpv4EnableDhcpEx`
- size: `428`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1800021a0`
- `0x180002620`
- `0x180002760`
- `0x180006790`
- `0x18000c110`
- `0x18000f4ec`
- `0x1800127f0`
- `0x180012850`
- `0x180012a00`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c1f1`
- `RPCRT4!NdrClientCall3` at `0x18000c1f1`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c1af`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c20d`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c22b`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c1af`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c20d`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000c22b`

## pseudocode

```c
__int64 __fastcall Dhcpv4EnableDhcpEx(PCWSTR SourceString)
{
  unsigned int IsEnabled; // ebx
  LPWSTR CommandLineW; // rax
  int v4; // ecx
  LPWSTR v5; // rax
  int v6; // ecx
  __int64 v8; // [rsp+60h] [rbp+18h] BYREF

  v8 = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_S(1028, 15, WPP_e15037783097355a5233924022d92169_Traceguids, SourceString);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    IsEnabled = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 16, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
  }
  else if ( SourceString )
  {
    IsEnabled = DhcpIsEnabled(SourceString);
    if ( !IsEnabled )
    {
      IsEnabled = DhcpAdapterNameToIfId(SourceString, &v8);
      if ( !IsEnabled )
      {
        if ( (xmmword_18001E1E0 & 0x10) != 0 )
        {
          CommandLineW = GetCommandLineW();
          WPP_SF_SS(
            v4,
            IsEnabled + 17,
            (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids,
            (_DWORD)SourceString,
            (__int64)CommandLineW);
        }
        IsEnabled = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 3u, 0).Pointer;
        if ( (xmmword_18001E1E0 & 0x10) != 0 )
        {
          v5 = GetCommandLineW();
          WPP_SF_DSS(
            v6,
            18,
            (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids,
            IsEnabled,
            (__int64)SourceString,
            (__int64)v5);
        }
        if ( !IsEnabled )
          IsEnabled = DhcpEnableDhcp(SourceString, 1);
      }
    }
  }
  else
  {
    IsEnabled = 87;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 19, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, (_DWORD)SourceString, IsEnabled);
  return IsEnabled;
}

```

## disassembly

```asm
0x18000c110  mov     rax, rsp
0x18000c113  mov     [rax+20h], rbx
0x18000c117  mov     [rax+8], rcx
0x18000c11b  push    rdi
0x18000c11c  sub     rsp, 40h
0x18000c120  mov     rdi, rcx
0x18000c123  mov     qword ptr [rax+18h], 0
0x18000c12b  mov     dword ptr [rax+10h], 0
0x18000c132  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c139  jz      short loc_18000C154
0x18000c13b  mov     edx, 0Fh
0x18000c140  mov     ecx, 404h
0x18000c145  mov     r9, rdi
0x18000c148  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c14f  call    WPP_SF_S
0x18000c154  call    DhcpIsFSEGuestSystem
0x18000c159  test    eax, eax
0x18000c15b  jnz     loc_18000C262
0x18000c161  test    rdi, rdi
0x18000c164  jnz     short loc_18000C16E
0x18000c166  lea     ebx, [rax+57h]
0x18000c169  jmp     loc_18000C289
0x18000c16e  lea     rdx, [rsp+48h+arg_8]
0x18000c173  mov     rcx, rdi; SourceString
0x18000c176  call    DhcpIsEnabled
0x18000c17b  mov     ebx, eax
0x18000c17d  test    eax, eax
0x18000c17f  jnz     loc_18000C289
0x18000c185  cmp     dword ptr [rsp+48h+arg_8], eax
0x18000c189  jnz     loc_18000C289
0x18000c18f  lea     rdx, [rsp+48h+arg_10]
0x18000c194  mov     rcx, rdi
0x18000c197  call    DhcpAdapterNameToIfId
0x18000c19c  mov     ebx, eax
0x18000c19e  test    eax, eax
0x18000c1a0  jnz     loc_18000C289
0x18000c1a6  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c1ad  jz      short loc_18000C1CD
0x18000c1af  call    cs:__imp_GetCommandLineW
0x18000c1b5  lea     edx, [rbx+11h]
0x18000c1b8  mov     [rsp+48h+var_28], rax
0x18000c1bd  mov     r9, rdi
0x18000c1c0  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c1c7  call    WPP_SF_SS
0x18000c1cc  nop
0x18000c1cd  mov     [rsp+48h+arg_8], 0
0x18000c1d6  lea     rax, [rsp+48h+arg_10]
0x18000c1db  mov     [rsp+48h+var_28], rax
0x18000c1e0  xor     r9d, r9d
0x18000c1e3  xor     r8d, r8d; pReturnValue
0x18000c1e6  lea     edx, [r9+3]; nProcNum
0x18000c1ea  lea     rcx, pProxyInfo; pProxyInfo
0x18000c1f1  call    cs:__imp_NdrClientCall3
0x18000c1f7  mov     rbx, rax
0x18000c1fa  mov     [rsp+48h+arg_8], rax
0x18000c1ff  mov     [rsp+48h+var_18], eax
0x18000c203  jmp     short loc_18000C222
0x18000c205  mov     edi, eax
0x18000c207  mov     ebx, eax
0x18000c209  mov     [rsp+48h+var_18], eax
0x18000c20d  call    cs:__imp_GetCommandLineW
0x18000c213  mov     rdx, rax
0x18000c216  mov     ecx, ebx
0x18000c218  call    TraceRpcException
0x18000c21d  mov     rdi, [rsp+48h+arg_0]
0x18000c222  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c229  jz      short loc_18000C24F
0x18000c22b  call    cs:__imp_GetCommandLineW
0x18000c231  mov     edx, 12h
0x18000c236  mov     [rsp+48h+var_20], rax
0x18000c23b  mov     [rsp+48h+var_28], rdi
0x18000c240  mov     r9d, ebx
0x18000c243  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c24a  call    WPP_SF_DSS
0x18000c24f  test    ebx, ebx
0x18000c251  jnz     short loc_18000C289
0x18000c253  lea     edx, [rbx+1]
0x18000c256  mov     rcx, rdi
0x18000c259  call    DhcpEnableDhcp
0x18000c25e  mov     ebx, eax
0x18000c260  jmp     short loc_18000C289
0x18000c262  mov     r9d, 32h ; '2'
0x18000c268  mov     ebx, r9d
0x18000c26b  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000c272  jz      short loc_18000C289
0x18000c274  lea     edx, [r9-22h]
0x18000c278  mov     ecx, 401h
0x18000c27d  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c284  call    WPP_SF_d
0x18000c289  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000c290  jz      short loc_18000C2AF
0x18000c292  mov     edx, 13h
0x18000c297  mov     ecx, 404h
0x18000c29c  mov     dword ptr [rsp+48h+var_28], ebx
0x18000c2a0  mov     r9, rdi
0x18000c2a3  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000c2aa  call    WPP_SF_SD
0x18000c2af  mov     eax, ebx
0x18000c2b1  mov     rbx, [rsp+48h+arg_18]
0x18000c2b6  add     rsp, 40h
0x18000c2ba  pop     rdi
0x18000c2bb  retn
0x180010c20  push    rbp
0x180010c22  sub     rsp, 30h
0x180010c26  mov     rbp, rdx
0x180010c29  mov     rcx, [rcx]
0x180010c2c  mov     ecx, [rcx]; ExceptionCode
0x180010c2e  call    cs:__imp_I_RpcExceptionFilter
0x180010c34  nop
0x180010c35  add     rsp, 30h
0x180010c39  pop     rbp
0x180010c3a  retn
```
