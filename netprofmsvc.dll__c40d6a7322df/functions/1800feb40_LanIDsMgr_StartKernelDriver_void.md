# LanIDsMgr::StartKernelDriver(void)

- ea: `0x1800feb40`
- end: `0x1800feccd`
- name: `?StartKernelDriver@LanIDsMgr@@AEAAPEAUSC_HANDLE__@@XZ`
- size: `397`
- prototype: `struct SC_HANDLE__ *__fastcall(LanIDsMgr *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001003c`

## callees

- `0x180010340`
- `0x18003bf00`
- `0x1800feb40`
- `0x1800ff1f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800feb62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800febc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fec16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800feb62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800febc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800fec16`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800febb4`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800febb4`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800fec0c`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800fec0c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800fec57`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800fecb9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800fec57`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800fecb9`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800feb52`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800feb52`

## pseudocode

```c
SC_HANDLE __fastcall LanIDsMgr::StartKernelDriver(LanIDsMgr *this)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rdi
  SC_HANDLE v3; // rbx
  DWORD v4; // eax
  SC_HANDLE v5; // rax
  DWORD LastError; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx

  v1 = OpenSCManagerW(0, 0, 1u);
  v2 = v1;
  if ( v1 )
  {
    v5 = OpenServiceW(v1, LanIDsMgr::s_lldpServiceName, 0x34u);
    v3 = v5;
    if ( !v5 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_a7d930b269293553628841c7763b54c1_Traceguids, LastError);
      goto LABEL_22;
    }
    if ( StartServiceW(v5, 0, 0) )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_22;
      v8 = 54;
    }
    else
    {
      if ( GetLastError() != 1056 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_ds(*((_QWORD *)WPP_GLOBAL_Control + 2), LanIDsMgr::s_lldpServiceAscii);
        CloseServiceHandle(v3);
        v3 = 0;
        goto LABEL_22;
      }
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_22:
        CloseServiceHandle(v2);
        return v3;
      }
      v8 = 53;
    }
    WPP_SF_s(v7[2], v8, &WPP_a7d930b269293553628841c7763b54c1_Traceguids, LanIDsMgr::s_lldpServiceAscii);
    goto LABEL_22;
  }
  v3 = 0;
  v4 = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_a7d930b269293553628841c7763b54c1_Traceguids, v4);
  return v3;
}

```

## disassembly

```asm
0x1800feb40  mov     [rsp+arg_0], rbx
0x1800feb45  push    rdi
0x1800feb46  sub     rsp, 30h
0x1800feb4a  xor     edx, edx; lpDatabaseName
0x1800feb4c  xor     ecx, ecx; lpMachineName
0x1800feb4e  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800feb52  call    cs:__imp_OpenSCManagerW
0x1800feb58  mov     rdi, rax
0x1800feb5b  test    rax, rax
0x1800feb5e  jnz     short loc_1800FEBA4
0x1800feb60  xor     ebx, ebx
0x1800feb62  call    cs:__imp_GetLastError
0x1800feb68  mov     rcx, cs:WPP_GLOBAL_Control
0x1800feb6f  lea     rdx, WPP_GLOBAL_Control
0x1800feb76  cmp     rcx, rdx
0x1800feb79  jz      loc_1800FECBF
0x1800feb7f  test    byte ptr [rcx+1Ch], 1
0x1800feb83  jz      loc_1800FECBF
0x1800feb89  mov     rcx, [rcx+10h]
0x1800feb8d  lea     edx, [rdi+32h]
0x1800feb90  mov     r9d, eax
0x1800feb93  lea     r8, WPP_a7d930b269293553628841c7763b54c1_Traceguids
0x1800feb9a  call    WPP_SF_d
0x1800feb9f  jmp     loc_1800FECBF
0x1800feba4  mov     rdx, cs:?s_lldpServiceName@LanIDsMgr@@0V?$basic_zstring_view@_W@wil@@B; lpServiceName
0x1800febab  mov     r8d, 34h ; '4'; dwDesiredAccess
0x1800febb1  mov     rcx, rdi; hSCManager
0x1800febb4  call    cs:__imp_OpenServiceW
0x1800febba  mov     rbx, rax
0x1800febbd  test    rax, rax
0x1800febc0  jnz     short loc_1800FEC04
0x1800febc2  call    cs:__imp_GetLastError
0x1800febc8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800febcf  lea     rdx, WPP_GLOBAL_Control
0x1800febd6  cmp     rcx, rdx
0x1800febd9  jz      loc_1800FECB6
0x1800febdf  test    byte ptr [rcx+1Ch], 1
0x1800febe3  jz      loc_1800FECB6
0x1800febe9  mov     rcx, [rcx+10h]
0x1800febed  lea     edx, [rbx+33h]
0x1800febf0  mov     r9d, eax
0x1800febf3  lea     r8, WPP_a7d930b269293553628841c7763b54c1_Traceguids
0x1800febfa  call    WPP_SF_d
0x1800febff  jmp     loc_1800FECB6
0x1800fec04  xor     r8d, r8d; lpServiceArgVectors
0x1800fec07  xor     edx, edx; dwNumServiceArgs
0x1800fec09  mov     rcx, rbx; hService
0x1800fec0c  call    cs:__imp_StartServiceW
0x1800fec12  test    eax, eax
0x1800fec14  jnz     short loc_1800FEC81
0x1800fec16  call    cs:__imp_GetLastError
0x1800fec1c  mov     r9d, eax
0x1800fec1f  cmp     eax, 420h
0x1800fec24  jz      short loc_1800FEC61
0x1800fec26  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fec2d  lea     rdx, WPP_GLOBAL_Control
0x1800fec34  cmp     rcx, rdx
0x1800fec37  jz      short loc_1800FEC54
0x1800fec39  test    byte ptr [rcx+1Ch], 1
0x1800fec3d  jz      short loc_1800FEC54
0x1800fec3f  mov     rax, cs:?s_lldpServiceAscii@LanIDsMgr@@0V?$basic_zstring_view@D@wil@@B; wil::basic_zstring_view<char> const LanIDsMgr::s_lldpServiceAscii
0x1800fec46  mov     rcx, [rcx+10h]; LoggerHandle
0x1800fec4a  mov     [rsp+38h+var_18], rax; __int64
0x1800fec4f  call    WPP_SF_ds
0x1800fec54  mov     rcx, rbx; hSCObject
0x1800fec57  call    cs:__imp_CloseServiceHandle
0x1800fec5d  xor     ebx, ebx
0x1800fec5f  jmp     short loc_1800FECB6
0x1800fec61  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fec68  lea     rdx, WPP_GLOBAL_Control
0x1800fec6f  cmp     rcx, rdx
0x1800fec72  jz      short loc_1800FECB6
0x1800fec74  test    byte ptr [rcx+1Ch], 2
0x1800fec78  jz      short loc_1800FECB6
0x1800fec7a  mov     edx, 35h ; '5'
0x1800fec7f  jmp     short loc_1800FEC9F
0x1800fec81  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fec88  lea     rdx, WPP_GLOBAL_Control
0x1800fec8f  cmp     rcx, rdx
0x1800fec92  jz      short loc_1800FECB6
0x1800fec94  test    byte ptr [rcx+1Ch], 4
0x1800fec98  jz      short loc_1800FECB6
0x1800fec9a  mov     edx, 36h ; '6'
0x1800fec9f  mov     r9, cs:?s_lldpServiceAscii@LanIDsMgr@@0V?$basic_zstring_view@D@wil@@B; wil::basic_zstring_view<char> const LanIDsMgr::s_lldpServiceAscii
0x1800feca6  lea     r8, WPP_a7d930b269293553628841c7763b54c1_Traceguids
0x1800fecad  mov     rcx, [rcx+10h]
0x1800fecb1  call    WPP_SF_s
0x1800fecb6  mov     rcx, rdi; hSCObject
0x1800fecb9  call    cs:__imp_CloseServiceHandle
0x1800fecbf  mov     rax, rbx
0x1800fecc2  mov     rbx, [rsp+38h+arg_0]
0x1800fecc7  add     rsp, 30h
0x1800feccb  pop     rdi
0x1800feccc  retn
```
