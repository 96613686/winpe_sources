# SetServiceStartupType

- ea: `0x180005a28`
- end: `0x180005b65`
- name: `SetServiceStartupType`
- size: `317`
- prototype: `unsigned int __fastcall(LPCWSTR lpMachineName)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180005070`
- `0x180011040`

## callees

- `0x1800055a0`
- `0x18000568c`
- `0x180005a28`
- `0x180005eac`
- `0x180005ed4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005b0e`
- `KERNEL32!GetLastError` at `0x180005b0e`
- `ADVAPI32!ChangeServiceConfigW` at `0x180005b04`
- `ADVAPI32!ChangeServiceConfigW` at `0x180005b04`

## pseudocode

```c
unsigned int __fastcall SetServiceStartupType(LPCWSTR lpMachineName)
{
  unsigned int result; // eax
  unsigned int v3; // ebx
  DWORD LastError; // eax
  unsigned int lpBinaryPathName; // [rsp+20h] [rbp-48h]
  SC_HANDLE hService; // [rsp+78h] [rbp+10h] BYREF
  SC_HANDLE hSCObject; // [rsp+88h] [rbp+20h] BYREF

  hSCObject = 0;
  hService = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  result = FaxOpenService(lpMachineName, L"Fax", &hSCObject, &hService, lpBinaryPathName, 2u, 0);
  v3 = result;
  if ( !result )
  {
    if ( !ChangeServiceConfigW(hService, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
      }
    }
    FaxCloseService(hSCObject, hService);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180005a28  mov     rax, rsp
0x180005a2b  mov     [rax+8], rbx
0x180005a2f  mov     [rax+10h], rdx
0x180005a33  push    rbp
0x180005a34  sub     rsp, 60h
0x180005a38  mov     rbx, rcx
0x180005a3b  mov     qword ptr [rax+20h], 0
0x180005a43  mov     qword ptr [rax+10h], 0
0x180005a4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a52  lea     rbp, WPP_GLOBAL_Control
0x180005a59  cmp     rcx, rbp
0x180005a5c  jz      short loc_180005A7F
0x180005a5e  test    byte ptr [rcx+1Ch], 2
0x180005a62  jz      short loc_180005A7F
0x180005a64  cmp     byte ptr [rcx+19h], 5
0x180005a68  jb      short loc_180005A7F
0x180005a6a  mov     rcx, [rcx+10h]
0x180005a6e  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x180005a75  mov     edx, 4Ah ; 'J'
0x180005a7a  call    WPP_SF_
0x180005a7f  mov     [rsp+68h+lpdwTagId], 0; unsigned int *
0x180005a88  lea     r9, [rsp+68h+hService]; struct SC_HANDLE__ **
0x180005a8d  lea     r8, [rsp+68h+hSCObject]; struct SC_HANDLE__ **
0x180005a95  mov     dword ptr [rsp+68h+lpLoadOrderGroup], 2; unsigned int
0x180005a9d  lea     rdx, ServiceName; "Fax"
0x180005aa4  mov     rcx, rbx; lpMachineName
0x180005aa7  call    ?FaxOpenService@@YAKPEBG0PEAPEAUSC_HANDLE__@@1KKPEAK@Z; FaxOpenService(ushort const *,ushort const *,SC_HANDLE__ * *,SC_HANDLE__ * *,ulong,ulong,ulong *)
0x180005aac  mov     ebx, eax
0x180005aae  test    eax, eax
0x180005ab0  jnz     loc_180005B5A
0x180005ab6  mov     rcx, [rsp+68h+hService]; hService
0x180005abb  lea     r8d, [rax+2]; dwStartType
0x180005abf  mov     [rsp+68h+lpDisplayName], 0; lpDisplayName
0x180005ac8  or      edx, 0FFFFFFFFh; dwServiceType
0x180005acb  mov     [rsp+68h+lpPassword], 0; lpPassword
0x180005ad4  mov     r9d, edx; dwErrorControl
0x180005ad7  mov     [rsp+68h+lpServiceStartName], 0; lpServiceStartName
0x180005ae0  mov     [rsp+68h+lpDependencies], 0; lpDependencies
0x180005ae9  mov     [rsp+68h+lpdwTagId], 0; lpdwTagId
0x180005af2  mov     [rsp+68h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180005afb  mov     [rsp+68h+lpBinaryPathName], 0; lpBinaryPathName
0x180005b04  call    cs:__imp_ChangeServiceConfigW
0x180005b0a  test    eax, eax
0x180005b0c  jnz     short loc_180005B46
0x180005b0e  call    cs:__imp_GetLastError
0x180005b14  mov     ebx, eax
0x180005b16  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b1d  cmp     rcx, rbp
0x180005b20  jz      short loc_180005B46
0x180005b22  test    byte ptr [rcx+1Ch], 2
0x180005b26  jz      short loc_180005B46
0x180005b28  cmp     byte ptr [rcx+19h], 2
0x180005b2c  jb      short loc_180005B46
0x180005b2e  mov     rcx, [rcx+10h]
0x180005b32  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x180005b39  mov     edx, 4Bh ; 'K'
0x180005b3e  mov     r9d, eax
0x180005b41  call    WPP_SF_d
0x180005b46  mov     rdx, [rsp+68h+hService]; SC_HANDLE
0x180005b4b  mov     rcx, [rsp+68h+hSCObject]; hSCObject
0x180005b53  call    ?FaxCloseService@@YAKPEAUSC_HANDLE__@@0@Z; FaxCloseService(SC_HANDLE__ *,SC_HANDLE__ *)
0x180005b58  mov     eax, ebx
0x180005b5a  mov     rbx, [rsp+68h+arg_0]
0x180005b5f  add     rsp, 60h
0x180005b63  pop     rbp
0x180005b64  retn
```
