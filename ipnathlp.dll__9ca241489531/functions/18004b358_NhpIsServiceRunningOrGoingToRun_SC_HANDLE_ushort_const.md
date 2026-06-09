# NhpIsServiceRunningOrGoingToRun(SC_HANDLE__ *,ushort const *)

- ea: `0x18004b358`
- end: `0x18004b529`
- name: `?NhpIsServiceRunningOrGoingToRun@@YAHPEAUSC_HANDLE__@@PEBG@Z`
- size: `465`
- prototype: `__int64 __fastcall(SC_HANDLE hSCManager, LPCWSTR lpServiceName)`
- caller_count: `4`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180024024`
- `0x180030ac8`
- `0x18003d5f8`
- `0x180070598`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x180037cf4`
- `0x18004b358`
- `0x18004e0c0`
- `0x180070ecc`
- `0x180071ea4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b46c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b46c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004b449`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18004b449`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004b3e0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18004b3e0`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18004b424`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18004b424`

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
0x18004b358  mov     [rsp+arg_10], rbp
0x18004b35d  mov     [rsp+arg_18], rsi
0x18004b362  push    rdi
0x18004b363  push    r14
0x18004b365  push    r15
0x18004b367  sub     rsp, 60h
0x18004b36b  mov     rax, cs:__security_cookie
0x18004b372  xor     rax, rsp
0x18004b375  mov     [rsp+78h+var_20], rax
0x18004b37a  mov     rbp, rdx
0x18004b37d  mov     r14, rcx
0x18004b380  test    rdx, rdx
0x18004b383  jz      loc_18004B4CD
0x18004b389  test    rcx, rcx
0x18004b38c  jz      loc_18004B4CD
0x18004b392  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b399  lea     rdi, WPP_GLOBAL_Control
0x18004b3a0  cmp     rcx, rdi
0x18004b3a3  jz      short loc_18004B3CC
0x18004b3a5  test    dword ptr [rcx+1Ch], 200h
0x18004b3ac  jz      short loc_18004B3CC
0x18004b3ae  cmp     byte ptr [rcx+19h], 6
0x18004b3b2  jb      short loc_18004B3CC
0x18004b3b4  mov     rcx, [rcx+10h]
0x18004b3b8  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18004b3bf  mov     edx, 3Ah ; ':'
0x18004b3c4  mov     r9, rbp
0x18004b3c7  call    WPP_SF_S
0x18004b3cc  xor     esi, esi
0x18004b3ce  xor     r15d, r15d
0x18004b3d1  mov     rdx, rbp; lpServiceName
0x18004b3d4  mov     [rsp+78h+var_48], r15d
0x18004b3d9  mov     rcx, r14; hSCManager
0x18004b3dc  lea     r8d, [rsi+5]; dwDesiredAccess
0x18004b3e0  call    cs:__imp_OpenServiceW
0x18004b3e6  mov     rbp, rax
0x18004b3e9  test    rax, rax
0x18004b3ec  jz      short loc_18004B451
0x18004b3ee  xorps   xmm0, xmm0
0x18004b3f1  lea     rdx, [rsp+78h+var_48]; unsigned int *
0x18004b3f6  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x18004b3fb  mov     rcx, rax; hService
0x18004b3fe  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18004b403  call    ?NhpQueryServiceStartType@@YAKPEAUSC_HANDLE__@@PEAK@Z; NhpQueryServiceStartType(SC_HANDLE__ *,ulong *)
0x18004b408  mov     r15d, [rsp+78h+var_48]
0x18004b40d  test    eax, eax
0x18004b40f  jnz     short loc_18004B41C
0x18004b411  cmp     r15d, 2
0x18004b415  jnz     short loc_18004B41C
0x18004b417  lea     esi, [rax+1]
0x18004b41a  jmp     short loc_18004B446
0x18004b41c  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x18004b421  mov     rcx, rbp; hService
0x18004b424  call    cs:__imp_QueryServiceStatus
0x18004b42a  test    eax, eax
0x18004b42c  jz      short loc_18004B446
0x18004b42e  mov     eax, [rsp+78h+ServiceStatus.dwCurrentState]
0x18004b432  add     eax, 0FFFFFFFEh
0x18004b435  test    eax, 0FFFFFFFDh
0x18004b43a  mov     eax, esi
0x18004b43c  mov     esi, 1
0x18004b441  cmovz   eax, esi
0x18004b444  mov     esi, eax
0x18004b446  mov     rcx, rbp; hSCObject
0x18004b449  call    cs:__imp_CloseServiceHandle
0x18004b44f  jmp     short loc_18004B491
0x18004b451  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b458  cmp     rcx, rdi
0x18004b45b  jz      short loc_18004B4C9
0x18004b45d  test    dword ptr [rcx+1Ch], 200h
0x18004b464  jz      short loc_18004B498
0x18004b466  cmp     byte ptr [rcx+19h], 2
0x18004b46a  jb      short loc_18004B498
0x18004b46c  call    cs:__imp_GetLastError
0x18004b472  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b479  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18004b480  mov     edx, 3Bh ; ';'
0x18004b485  mov     r9d, eax
0x18004b488  mov     rcx, [rcx+10h]
0x18004b48c  call    WPP_SF_d
0x18004b491  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b498  cmp     rcx, rdi
0x18004b49b  jz      short loc_18004B4C9
0x18004b49d  test    dword ptr [rcx+1Ch], 200h
0x18004b4a4  jz      short loc_18004B4C9
0x18004b4a6  cmp     byte ptr [rcx+19h], 6
0x18004b4aa  jb      short loc_18004B4C9
0x18004b4ac  mov     rcx, [rcx+10h]
0x18004b4b0  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18004b4b7  mov     r9b, sil
0x18004b4ba  mov     [rsp+78h+var_58], r15d
0x18004b4bf  mov     edx, 3Ch ; '<'
0x18004b4c4  call    WPP_SF_cd
0x18004b4c9  mov     eax, esi
0x18004b4cb  jmp     short loc_18004B506
0x18004b4cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b4d4  lea     rdi, WPP_GLOBAL_Control
0x18004b4db  cmp     rcx, rdi
0x18004b4de  jz      short loc_18004B504
0x18004b4e0  test    dword ptr [rcx+1Ch], 200h
0x18004b4e7  jz      short loc_18004B504
0x18004b4e9  cmp     byte ptr [rcx+19h], 2
0x18004b4ed  jb      short loc_18004B504
0x18004b4ef  mov     rcx, [rcx+10h]
0x18004b4f3  lea     r8, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18004b4fa  mov     edx, 39h ; '9'
0x18004b4ff  call    WPP_SF_
0x18004b504  xor     eax, eax
0x18004b506  mov     rcx, [rsp+78h+var_20]
0x18004b50b  xor     rcx, rsp; StackCookie
0x18004b50e  call    __security_check_cookie
0x18004b513  lea     r11, [rsp+78h+var_18]
0x18004b518  mov     rbp, [r11+30h]
0x18004b51c  mov     rsi, [r11+38h]
0x18004b520  mov     rsp, r11
0x18004b523  pop     r15
0x18004b525  pop     r14
0x18004b527  pop     rdi
0x18004b528  retn
```
