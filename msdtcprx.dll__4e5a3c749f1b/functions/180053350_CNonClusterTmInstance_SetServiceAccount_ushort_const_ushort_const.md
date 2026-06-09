# CNonClusterTmInstance::SetServiceAccount(ushort const *,ushort const *)

- ea: `0x180053350`
- end: `0x18005344a`
- name: `?SetServiceAccount@CNonClusterTmInstance@@UEAAJPEBG0@Z`
- size: `250`
- prototype: `int(CNonClusterTmInstance *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task`

## callees

- `0x180053350`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800533e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005340a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005342a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800533e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005340a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005342a`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180053402`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180053422`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180053402`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180053422`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005338b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18005338b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180053369`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180053369`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800533dc`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x1800533dc`

## pseudocode

```c
__int64 __fastcall CNonClusterTmInstance::SetServiceAccount(
        LPCWSTR *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rsi
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rdi
  signed int LastError; // eax
  unsigned int v10; // ebx
  signed int v11; // eax
  signed int v12; // eax

  v5 = OpenSCManagerW(this[4], 0, 1u);
  v6 = v5;
  if ( v5 )
  {
    v7 = OpenServiceW(v5, L"MSDTC", 2u);
    v8 = v7;
    if ( v7 )
    {
      if ( ChangeServiceConfigW(v7, 0xFFFFFFFF, 0xFFFFFFFF, 0xFFFFFFFF, 0, 0, 0, 0, a2, a3, 0) )
      {
        v10 = 0;
      }
      else
      {
        LastError = GetLastError();
        v10 = LastError;
        if ( LastError > 0 )
          v10 = (unsigned __int16)LastError | 0x80070000;
      }
      CloseServiceHandle(v8);
    }
    else
    {
      v11 = GetLastError();
      v10 = v11;
      if ( v11 > 0 )
        v10 = (unsigned __int16)v11 | 0x80070000;
    }
    CloseServiceHandle(v6);
  }
  else
  {
    v12 = GetLastError();
    v10 = v12;
    if ( v12 > 0 )
      return (unsigned __int16)v12 | 0x80070000;
  }
  return v10;
}

```

## disassembly

```asm
0x180053350  push    rbx
0x180053352  push    rbp
0x180053353  push    rsi
0x180053354  push    rdi
0x180053355  sub     rsp, 68h
0x180053359  mov     rcx, [rcx+20h]; lpMachineName
0x18005335d  mov     rbp, rdx
0x180053360  xor     edx, edx; lpDatabaseName
0x180053362  mov     rbx, r8
0x180053365  lea     r8d, [rdx+1]; dwDesiredAccess
0x180053369  call    cs:__imp_OpenSCManagerW
0x18005336f  mov     rsi, rax
0x180053372  test    rax, rax
0x180053375  jz      loc_18005342A
0x18005337b  mov     r8d, 2; dwDesiredAccess
0x180053381  lea     rdx, aMsdtc; "MSDTC"
0x180053388  mov     rcx, rax; hSCManager
0x18005338b  call    cs:__imp_OpenServiceW
0x180053391  mov     rdi, rax
0x180053394  test    rax, rax
0x180053397  jz      short loc_18005340A
0x180053399  mov     [rsp+88h+lpDisplayName], 0; lpDisplayName
0x1800533a2  or      edx, 0FFFFFFFFh; dwServiceType
0x1800533a5  mov     [rsp+88h+lpPassword], rbx; lpPassword
0x1800533aa  mov     r9d, edx; dwErrorControl
0x1800533ad  mov     [rsp+88h+lpServiceStartName], rbp; lpServiceStartName
0x1800533b2  mov     r8d, edx; dwStartType
0x1800533b5  mov     [rsp+88h+lpDependencies], 0; lpDependencies
0x1800533be  mov     rcx, rax; hService
0x1800533c1  mov     [rsp+88h+lpdwTagId], 0; lpdwTagId
0x1800533ca  mov     [rsp+88h+lpLoadOrderGroup], 0; lpLoadOrderGroup
0x1800533d3  mov     [rsp+88h+lpBinaryPathName], 0; lpBinaryPathName
0x1800533dc  call    cs:__imp_ChangeServiceConfigW
0x1800533e2  test    eax, eax
0x1800533e4  jnz     short loc_1800533FD
0x1800533e6  call    cs:__imp_GetLastError
0x1800533ec  mov     ebx, eax
0x1800533ee  test    eax, eax
0x1800533f0  jle     short loc_1800533FF
0x1800533f2  movzx   ebx, ax
0x1800533f5  or      ebx, 80070000h
0x1800533fb  jmp     short loc_1800533FF
0x1800533fd  xor     ebx, ebx
0x1800533ff  mov     rcx, rdi; hSCObject
0x180053402  call    cs:__imp_CloseServiceHandle
0x180053408  jmp     short loc_18005341F
0x18005340a  call    cs:__imp_GetLastError
0x180053410  mov     ebx, eax
0x180053412  test    eax, eax
0x180053414  jle     short loc_18005341F
0x180053416  movzx   ebx, ax
0x180053419  or      ebx, 80070000h
0x18005341f  mov     rcx, rsi; hSCObject
0x180053422  call    cs:__imp_CloseServiceHandle
0x180053428  jmp     short loc_18005343F
0x18005342a  call    cs:__imp_GetLastError
0x180053430  mov     ebx, eax
0x180053432  test    eax, eax
0x180053434  jle     short loc_18005343F
0x180053436  movzx   ebx, ax
0x180053439  or      ebx, 80070000h
0x18005343f  mov     eax, ebx
0x180053441  add     rsp, 68h
0x180053445  pop     rdi
0x180053446  pop     rsi
0x180053447  pop     rbp
0x180053448  pop     rbx
0x180053449  retn
```
