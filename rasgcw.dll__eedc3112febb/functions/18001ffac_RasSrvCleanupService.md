# RasSrvCleanupService

- ea: `0x18001ffac`
- end: `0x180020090`
- name: `RasSrvCleanupService`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800209bc`

## callees

- `0x18001ffac`
- `0x180020240`
- `0x180020b80`
- `0x180020e0c`
- `0x1800263f8`
- `0x1800264b4`
- `0x180026a24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020068`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18002005e`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18002005e`

## string_xrefs

- `0x18001ffc9`: `remoteaccess`

## pseudocode

```c
__int64 RasSrvCleanupService()
{
  __int64 result; // rax
  SC_HANDLE *v1; // rdi
  DWORD LastError; // ebx
  LPVOID lpMem; // [rsp+70h] [rbp+8h] BYREF

  lpMem = 0;
  RasSrvUiInit();
  result = DialupOpenNamedService(aRemoteaccess, (__int64 *)&lpMem);
  if ( !(_DWORD)result )
  {
    v1 = (SC_HANDLE *)lpMem;
    LastError = RasSrvStopService(lpMem);
    if ( !LastError )
    {
      LODWORD(lpMem) = 0;
      RassrvICConfigAccess(1, (BYTE *)&lpMem);
      if ( v1 )
      {
        if ( ChangeServiceConfigW(v1[1], 0xFFFFFFFF, 4u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
          LastError = 0;
        else
          LastError = GetLastError();
      }
      else
      {
        LastError = 87;
      }
    }
    FwRASGlobalPortOpenings(0);
    SvcClose(v1);
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x18001ffac  mov     [rsp+arg_8], rbx
0x18001ffb1  push    rdi
0x18001ffb2  sub     rsp, 60h
0x18001ffb6  mov     [rsp+68h+lpMem], 0
0x18001ffbf  call    RasSrvUiInit
0x18001ffc4  lea     rdx, [rsp+68h+lpMem]
0x18001ffc9  lea     rcx, aRemoteaccess; "remoteaccess"
0x18001ffd0  call    DialupOpenNamedService
0x18001ffd5  test    eax, eax
0x18001ffd7  jnz     loc_180020085
0x18001ffdd  mov     rdi, [rsp+68h+lpMem]
0x18001ffe2  mov     rcx, rdi; lpMem
0x18001ffe5  call    RasSrvStopService
0x18001ffea  mov     ebx, eax
0x18001ffec  test    eax, eax
0x18001ffee  jnz     loc_180020074
0x18001fff4  lea     rdx, [rsp+68h+lpMem]
0x18001fff9  mov     dword ptr [rsp+68h+lpMem], eax
0x18001fffd  lea     ecx, [rax+1]
0x180020000  call    RassrvICConfigAccess
0x180020005  test    rdi, rdi
0x180020008  jnz     short loc_18002000F
0x18002000a  lea     ebx, [rdi+57h]
0x18002000d  jmp     short loc_180020074
0x18002000f  mov     rcx, [rdi+8]; hService
0x180020013  or      edx, 0FFFFFFFFh; dwServiceType
0x180020016  mov     [rsp+68h+lpDisplayName], 0; lpDisplayName
0x18002001f  mov     r9d, edx; dwErrorControl
0x180020022  mov     [rsp+68h+lpPassword], 0; lpPassword
0x18002002b  mov     r8d, 4; dwStartType
0x180020031  mov     [rsp+68h+lpServiceStartName], 0; lpServiceStartName
0x18002003a  mov     [rsp+68h+lpDependencies], 0; lpDependencies
0x180020043  mov     [rsp+68h+lpdwTagId], 0; lpdwTagId
0x18002004c  mov     [rsp+68h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x180020055  mov     [rsp+68h+lpBinaryPathName], 0; lpBinaryPathName
0x18002005e  call    cs:__imp_ChangeServiceConfigW
0x180020064  test    eax, eax
0x180020066  jnz     short loc_180020072
0x180020068  call    cs:__imp_GetLastError
0x18002006e  mov     ebx, eax
0x180020070  jmp     short loc_180020074
0x180020072  xor     ebx, ebx
0x180020074  xor     ecx, ecx
0x180020076  call    FwRASGlobalPortOpenings
0x18002007b  mov     rcx, rdi; lpMem
0x18002007e  call    SvcClose
0x180020083  mov     eax, ebx
0x180020085  mov     rbx, [rsp+68h+arg_8]
0x18002008a  add     rsp, 60h
0x18002008e  pop     rdi
0x18002008f  retn
```
