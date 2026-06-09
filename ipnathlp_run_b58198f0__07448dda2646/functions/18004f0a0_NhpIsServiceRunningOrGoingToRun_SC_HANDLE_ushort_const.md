# NhpIsServiceRunningOrGoingToRun(SC_HANDLE__ *,ushort const *)

- ea: `0x18004f0a0`
- end: `0x18004f28a`
- name: `?NhpIsServiceRunningOrGoingToRun@@YAHPEAUSC_HANDLE__@@PEBG@Z`
- size: `490`
- prototype: `__int64 __fastcall(SC_HANDLE hSCManager, LPCWSTR lpServiceName)`
- caller_count: `4`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180023af0`
- `0x180026500`
- `0x180040940`
- `0x180075f14`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x18003a66c`
- `0x18004f0a0`
- `0x180051f30`
- `0x1800768c0`
- `0x180077978`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f1c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f1c6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004f19d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004f19d`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004f128`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004f128`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18004f172`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18004f172`

## pseudocode

```c
_BOOL8 __fastcall NhpIsServiceRunningOrGoingToRun(SC_HANDLE hSCManager, LPCWSTR lpServiceName)
{
  BOOL v4; // esi
  unsigned int v5; // r15d
  SC_HANDLE v6; // rax
  __int64 v7; // r9
  SC_HANDLE v8; // rbp
  unsigned int started; // eax
  PVOID *v10; // rcx
  DWORD LastError; // eax
  unsigned int v13; // [rsp+30h] [rbp-48h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-40h] BYREF

  if ( lpServiceName && hSCManager )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, lpServiceName);
    }
    v4 = 0;
    v5 = 0;
    v13 = 0;
    v6 = OpenServiceW(hSCManager, lpServiceName, 5u);
    v8 = v6;
    if ( v6 )
    {
      memset(&ServiceStatus, 0, sizeof(ServiceStatus));
      started = NhpQueryServiceStartType(v6, &v13);
      v5 = v13;
      if ( started || v13 != 2 )
      {
        if ( QueryServiceStatus(v8, &ServiceStatus) )
          v4 = ((ServiceStatus.dwCurrentState - 2) & 0xFFFFFFFD) == 0;
      }
      else
      {
        v4 = 1;
      }
      CloseServiceHandle(v8);
    }
    else
    {
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v4;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_19:
        if ( v10 != &WPP_GLOBAL_Control && (*((_DWORD *)v10 + 7) & 0x200) != 0 && *((_BYTE *)v10 + 25) >= 6u )
        {
          LOBYTE(v7) = v4;
          WPP_SF_cd(v10[2], 60, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v7, v5);
        }
        return v4;
      }
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, LastError);
    }
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x18004f0a0  mov     [rsp+arg_10], rbp
0x18004f0a5  mov     [rsp+arg_18], rsi
0x18004f0aa  push    rdi
0x18004f0ab  push    r14
0x18004f0ad  push    r15
0x18004f0af  sub     rsp, 60h
0x18004f0b3  mov     rax, cs:__security_cookie
0x18004f0ba  xor     rax, rsp
0x18004f0bd  mov     [rsp+78h+var_20], rax
0x18004f0c2  mov     rbp, rdx
0x18004f0c5  mov     r14, rcx
0x18004f0c8  test    rdx, rdx
0x18004f0cb  jz      loc_18004F22D
0x18004f0d1  test    rcx, rcx
0x18004f0d4  jz      loc_18004F22D
0x18004f0da  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f0e1  lea     rdi, WPP_GLOBAL_Control
0x18004f0e8  cmp     rcx, rdi
0x18004f0eb  jz      short loc_18004F114
0x18004f0ed  test    dword ptr [rcx+1Ch], 200h
0x18004f0f4  jz      short loc_18004F114
0x18004f0f6  cmp     byte ptr [rcx+19h], 6
0x18004f0fa  jb      short loc_18004F114
0x18004f0fc  mov     rcx, [rcx+10h]
0x18004f100  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18004f107  mov     edx, 3Ah ; ':'
0x18004f10c  mov     r9, rbp
0x18004f10f  call    WPP_SF_S
0x18004f114  xor     esi, esi
0x18004f116  xor     r15d, r15d
0x18004f119  mov     rdx, rbp; lpServiceName
0x18004f11c  mov     [rsp+78h+var_48], r15d
0x18004f121  mov     rcx, r14; hSCManager
0x18004f124  lea     r8d, [rsi+5]; dwDesiredAccess
0x18004f128  call    cs:__imp_OpenServiceW
0x18004f12f  nop     dword ptr [rax+rax+00h]
0x18004f134  mov     rbp, rax
0x18004f137  test    rax, rax
0x18004f13a  jz      short loc_18004F1AB
0x18004f13c  xorps   xmm0, xmm0
0x18004f13f  lea     rdx, [rsp+78h+var_48]; unsigned int *
0x18004f144  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18004f149  mov     rcx, rax; hService
0x18004f14c  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18004f151  call    ?NhpQueryServiceStartType@@YAKPEAUSC_HANDLE__@@PEAK@Z; NhpQueryServiceStartType(SC_HANDLE__ *,ulong *)
0x18004f156  mov     r15d, [rsp+78h+var_48]
0x18004f15b  test    eax, eax
0x18004f15d  jnz     short loc_18004F16A
0x18004f15f  cmp     r15d, 2
0x18004f163  jnz     short loc_18004F16A
0x18004f165  lea     esi, [rax+1]
0x18004f168  jmp     short loc_18004F19A
0x18004f16a  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18004f16f  mov     rcx, rbp; hService
0x18004f172  call    cs:__imp_QueryServiceStatus
0x18004f179  nop     dword ptr [rax+rax+00h]
0x18004f17e  test    eax, eax
0x18004f180  jz      short loc_18004F19A
0x18004f182  mov     eax, [rsp+78h+ServiceStatus.dwCurrentState]
0x18004f186  add     eax, 0FFFFFFFEh
0x18004f189  test    eax, 0FFFFFFFDh
0x18004f18e  mov     eax, esi
0x18004f190  mov     esi, 1
0x18004f195  cmovz   eax, esi
0x18004f198  mov     esi, eax
0x18004f19a  mov     rcx, rbp; hSCObject
0x18004f19d  call    cs:__imp_CloseServiceHandle
0x18004f1a4  nop     dword ptr [rax+rax+00h]
0x18004f1a9  jmp     short loc_18004F1F1
0x18004f1ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f1b2  cmp     rcx, rdi
0x18004f1b5  jz      short loc_18004F229
0x18004f1b7  test    dword ptr [rcx+1Ch], 200h
0x18004f1be  jz      short loc_18004F1F8
0x18004f1c0  cmp     byte ptr [rcx+19h], 2
0x18004f1c4  jb      short loc_18004F1F8
0x18004f1c6  call    cs:__imp_GetLastError
0x18004f1cd  nop     dword ptr [rax+rax+00h]
0x18004f1d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f1d9  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18004f1e0  mov     edx, 3Bh ; ';'
0x18004f1e5  mov     r9d, eax
0x18004f1e8  mov     rcx, [rcx+10h]
0x18004f1ec  call    WPP_SF_d
0x18004f1f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f1f8  cmp     rcx, rdi
0x18004f1fb  jz      short loc_18004F229
0x18004f1fd  test    dword ptr [rcx+1Ch], 200h
0x18004f204  jz      short loc_18004F229
0x18004f206  cmp     byte ptr [rcx+19h], 6
0x18004f20a  jb      short loc_18004F229
0x18004f20c  mov     rcx, [rcx+10h]
0x18004f210  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18004f217  mov     r9b, sil
0x18004f21a  mov     [rsp+78h+var_58], r15d
0x18004f21f  mov     edx, 3Ch ; '<'
0x18004f224  call    WPP_SF_cd
0x18004f229  mov     eax, esi
0x18004f22b  jmp     short loc_18004F266
0x18004f22d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f234  lea     rdi, WPP_GLOBAL_Control
0x18004f23b  cmp     rcx, rdi
0x18004f23e  jz      short loc_18004F264
0x18004f240  test    dword ptr [rcx+1Ch], 200h
0x18004f247  jz      short loc_18004F264
0x18004f249  cmp     byte ptr [rcx+19h], 2
0x18004f24d  jb      short loc_18004F264
0x18004f24f  mov     rcx, [rcx+10h]
0x18004f253  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18004f25a  mov     edx, 39h ; '9'
0x18004f25f  call    WPP_SF_
0x18004f264  xor     eax, eax
0x18004f266  mov     rcx, [rsp+78h+var_20]
0x18004f26b  xor     rcx, rsp; StackCookie
0x18004f26e  call    __security_check_cookie
0x18004f273  lea     r11, [rsp+78h+var_18]
0x18004f278  mov     rbp, [r11+30h]
0x18004f27c  mov     rsi, [r11+38h]
0x18004f280  mov     rsp, r11
0x18004f283  pop     r15
0x18004f285  pop     r14
0x18004f287  pop     rdi
0x18004f288  retn
```
