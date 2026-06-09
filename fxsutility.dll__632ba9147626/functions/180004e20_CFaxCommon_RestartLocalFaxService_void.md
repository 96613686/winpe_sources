# CFaxCommon::RestartLocalFaxService(void)

- ea: `0x180004e20`
- end: `0x180004fb4`
- name: `?RestartLocalFaxService@CFaxCommon@@UEAAJXZ`
- size: `404`
- prototype: `signed int __fastcall(CFaxCommon *this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180004e20`
- `0x1800055a0`
- `0x18000568c`
- `0x180005838`
- `0x180005b6c`
- `0x180005eac`
- `0x180005ed4`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180004f90`
- `KERNEL32!SetLastError` at `0x180004f90`
- `KERNEL32!GetLastError` at `0x180004e47`
- `KERNEL32!GetLastError` at `0x180004f3e`
- `KERNEL32!GetLastError` at `0x180004f96`
- `KERNEL32!GetLastError` at `0x180004e47`
- `KERNEL32!GetLastError` at `0x180004f3e`
- `KERNEL32!GetLastError` at `0x180004f96`
- `ADVAPI32!StartServiceW` at `0x180004f1c`
- `ADVAPI32!StartServiceW` at `0x180004f1c`

## pseudocode

```c
signed int __fastcall CFaxCommon::RestartLocalFaxService(CFaxCommon *this)
{
  _QWORD *v1; // rcx
  DWORD v2; // ebx
  DWORD LastError; // eax
  signed int result; // eax
  unsigned int v5; // [rsp+20h] [rbp-38h]
  LPCWSTR ServiceArgVectors; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v7; // [rsp+68h] [rbp+10h] BYREF
  SC_HANDLE hService; // [rsp+70h] [rbp+18h] BYREF
  SC_HANDLE hSCObject; // [rsp+78h] [rbp+20h] BYREF

  if ( !(unsigned int)StopService(this, L"Fax", 1, 60000) )
    GetLastError();
  ServiceArgVectors = L"/DelaySuicide";
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_db036311db36307996a98c23702218b2_Traceguids);
    v1 = WPP_GLOBAL_Control;
  }
  hSCObject = 0;
  hService = 0;
  v7 = 0;
  if ( v1 != &WPP_GLOBAL_Control && (*((_BYTE *)v1 + 28) & 2) != 0 && *((_BYTE *)v1 + 25) >= 5u )
    WPP_SF_(v1[2], 81, &WPP_db036311db36307996a98c23702218b2_Traceguids);
  v2 = FaxOpenService(0, L"Fax", &hSCObject, &hService, v5, 0x14u, &v7);
  if ( !v2 )
  {
    if ( v7 != 4 )
    {
      if ( StartServiceW(hService, 1u, &ServiceArgVectors) )
      {
        v2 = WaitForServiceStopOrStart(hService, 0, 0x927C0u);
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v2 + 82,
          &WPP_db036311db36307996a98c23702218b2_Traceguids,
          LastError);
      }
    }
    FaxCloseService(hSCObject, hService);
    if ( !v2 )
      return 0;
  }
  SetLastError(v2);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180004e20  mov     [rsp+arg_0], rbx
0x180004e25  push    r14
0x180004e27  sub     rsp, 50h
0x180004e2b  mov     r9d, 0EA60h
0x180004e31  lea     rdx, ServiceName; "Fax"
0x180004e38  mov     r8d, 1
0x180004e3e  call    StopService
0x180004e43  test    eax, eax
0x180004e45  jnz     short loc_180004E4D
0x180004e47  call    cs:__imp_GetLastError
0x180004e4d  lea     rax, aDelaysuicide; "/DelaySuicide"
0x180004e54  mov     [rsp+58h+ServiceArgVectors], rax
0x180004e59  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e60  lea     r14, WPP_GLOBAL_Control
0x180004e67  cmp     rcx, r14
0x180004e6a  jz      short loc_180004E94
0x180004e6c  test    byte ptr [rcx+1Ch], 2
0x180004e70  jz      short loc_180004E94
0x180004e72  cmp     byte ptr [rcx+19h], 5
0x180004e76  jb      short loc_180004E94
0x180004e78  mov     rcx, [rcx+10h]
0x180004e7c  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x180004e83  mov     edx, 1Fh
0x180004e88  call    WPP_SF_
0x180004e8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e94  mov     [rsp+58h+hSCObject], 0
0x180004e9d  mov     [rsp+58h+hService], 0
0x180004ea6  mov     [rsp+58h+arg_8], 0
0x180004eae  cmp     rcx, r14
0x180004eb1  jz      short loc_180004ED4
0x180004eb3  test    byte ptr [rcx+1Ch], 2
0x180004eb7  jz      short loc_180004ED4
0x180004eb9  cmp     byte ptr [rcx+19h], 5
0x180004ebd  jb      short loc_180004ED4
0x180004ebf  mov     rcx, [rcx+10h]
0x180004ec3  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x180004eca  mov     edx, 51h ; 'Q'
0x180004ecf  call    WPP_SF_
0x180004ed4  lea     rax, [rsp+58h+arg_8]
0x180004ed9  xor     ecx, ecx; lpMachineName
0x180004edb  mov     [rsp+58h+var_28], rax; unsigned int *
0x180004ee0  lea     r9, [rsp+58h+hService]; struct SC_HANDLE__ **
0x180004ee5  lea     r8, [rsp+58h+hSCObject]; struct SC_HANDLE__ **
0x180004eea  mov     [rsp+58h+var_30], 14h; unsigned int
0x180004ef2  lea     rdx, ServiceName; "Fax"
0x180004ef9  call    ?FaxOpenService@@YAKPEBG0PEAPEAUSC_HANDLE__@@1KKPEAK@Z; FaxOpenService(ushort const *,ushort const *,SC_HANDLE__ * *,SC_HANDLE__ * *,ulong,ulong,ulong *)
0x180004efe  mov     ebx, eax
0x180004f00  test    eax, eax
0x180004f02  jnz     loc_180004F8E
0x180004f08  cmp     [rsp+58h+arg_8], 4
0x180004f0d  jz      short loc_180004F77
0x180004f0f  mov     rcx, [rsp+58h+hService]; hService
0x180004f14  lea     r8, [rsp+58h+ServiceArgVectors]; lpServiceArgVectors
0x180004f19  lea     edx, [rax+1]; dwNumServiceArgs
0x180004f1c  call    cs:__imp_StartServiceW
0x180004f22  test    eax, eax
0x180004f24  jnz     short loc_180004F63
0x180004f26  mov     rax, cs:WPP_GLOBAL_Control
0x180004f2d  cmp     rax, r14
0x180004f30  jz      short loc_180004F77
0x180004f32  test    byte ptr [rax+1Ch], 2
0x180004f36  jz      short loc_180004F77
0x180004f38  cmp     byte ptr [rax+19h], 2
0x180004f3c  jb      short loc_180004F77
0x180004f3e  call    cs:__imp_GetLastError
0x180004f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f4b  lea     edx, [rbx+52h]
0x180004f4e  mov     r9d, eax
0x180004f51  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x180004f58  mov     rcx, [rcx+10h]
0x180004f5c  call    WPP_SF_d
0x180004f61  jmp     short loc_180004F77
0x180004f63  mov     rcx, [rsp+58h+hService]; hService
0x180004f68  xor     edx, edx; int
0x180004f6a  mov     r8d, 927C0h; unsigned int
0x180004f70  call    ?WaitForServiceStopOrStart@@YAKPEAUSC_HANDLE__@@HK@Z; WaitForServiceStopOrStart(SC_HANDLE__ *,int,ulong)
0x180004f75  mov     ebx, eax
0x180004f77  mov     rdx, [rsp+58h+hService]; SC_HANDLE
0x180004f7c  mov     rcx, [rsp+58h+hSCObject]; hSCObject
0x180004f81  call    ?FaxCloseService@@YAKPEAUSC_HANDLE__@@0@Z; FaxCloseService(SC_HANDLE__ *,SC_HANDLE__ *)
0x180004f86  test    ebx, ebx
0x180004f88  jnz     short loc_180004F8E
0x180004f8a  xor     eax, eax
0x180004f8c  jmp     short loc_180004FA8
0x180004f8e  mov     ecx, ebx; dwErrCode
0x180004f90  call    cs:__imp_SetLastError
0x180004f96  call    cs:__imp_GetLastError
0x180004f9c  test    eax, eax
0x180004f9e  jle     short loc_180004FA8
0x180004fa0  movzx   eax, ax
0x180004fa3  or      eax, 80070000h
0x180004fa8  mov     rbx, [rsp+58h+arg_0]
0x180004fad  add     rsp, 50h
0x180004fb1  pop     r14
0x180004fb3  retn
```
