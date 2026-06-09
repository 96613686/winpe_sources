# RasSrvCleanupService

- ea: `0x18002df80`
- end: `0x18002e064`
- name: `RasSrvCleanupService`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x18002ecd8`

## callees

- `0x18002df80`
- `0x18002e6bc`
- `0x18002f01c`
- `0x18002f240`
- `0x1800345d8`
- `0x180034694`
- `0x180034c0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e03c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e03c`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18002e032`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18002e032`

## string_xrefs

- `0x18002df9d`: `remoteaccess`

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
  result = DialupOpenNamedService(aRemoteaccess_0, (__int64 *)&lpMem);
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
0x18002df80  mov     [rsp+arg_8], rbx
0x18002df85  push    rdi
0x18002df86  sub     rsp, 60h
0x18002df8a  mov     [rsp+68h+lpMem], 0
0x18002df93  call    RasSrvUiInit
0x18002df98  lea     rdx, [rsp+68h+lpMem]
0x18002df9d  lea     rcx, aRemoteaccess_0; "remoteaccess"
0x18002dfa4  call    DialupOpenNamedService
0x18002dfa9  test    eax, eax
0x18002dfab  jnz     loc_18002E059
0x18002dfb1  mov     rdi, [rsp+68h+lpMem]
0x18002dfb6  mov     rcx, rdi; lpMem
0x18002dfb9  call    RasSrvStopService
0x18002dfbe  mov     ebx, eax
0x18002dfc0  test    eax, eax
0x18002dfc2  jnz     loc_18002E048
0x18002dfc8  lea     rdx, [rsp+68h+lpMem]
0x18002dfcd  mov     dword ptr [rsp+68h+lpMem], eax
0x18002dfd1  lea     ecx, [rax+1]
0x18002dfd4  call    RassrvICConfigAccess
0x18002dfd9  test    rdi, rdi
0x18002dfdc  jnz     short loc_18002DFE3
0x18002dfde  lea     ebx, [rdi+57h]
0x18002dfe1  jmp     short loc_18002E048
0x18002dfe3  mov     rcx, [rdi+8]; hService
0x18002dfe7  or      edx, 0FFFFFFFFh; dwServiceType
0x18002dfea  mov     [rsp+68h+lpDisplayName], 0; lpDisplayName
0x18002dff3  mov     r9d, edx; dwErrorControl
0x18002dff6  mov     [rsp+68h+lpPassword], 0; lpPassword
0x18002dfff  mov     r8d, 4; dwStartType
0x18002e005  mov     [rsp+68h+lpServiceStartName], 0; lpServiceStartName
0x18002e00e  mov     [rsp+68h+lpDependencies], 0; lpDependencies
0x18002e017  mov     [rsp+68h+lpdwTagId], 0; lpdwTagId
0x18002e020  mov     [rsp+68h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x18002e029  mov     [rsp+68h+lpBinaryPathName], 0; lpBinaryPathName
0x18002e032  call    cs:__imp_ChangeServiceConfigW
0x18002e038  test    eax, eax
0x18002e03a  jnz     short loc_18002E046
0x18002e03c  call    cs:__imp_GetLastError
0x18002e042  mov     ebx, eax
0x18002e044  jmp     short loc_18002E048
0x18002e046  xor     ebx, ebx
0x18002e048  xor     ecx, ecx
0x18002e04a  call    FwRASGlobalPortOpenings
0x18002e04f  mov     rcx, rdi; lpMem
0x18002e052  call    SvcClose
0x18002e057  mov     eax, ebx
0x18002e059  mov     rbx, [rsp+68h+arg_8]
0x18002e05e  add     rsp, 60h
0x18002e062  pop     rdi
0x18002e063  retn
```
