# Accommodation::FindProcess(ushort const *,void * *,int)

- ea: `0x1401b9d38`
- end: `0x1401b9ed5`
- name: `?FindProcess@Accommodation@@SAKPEBGPEAPEAXH@Z`
- size: `413`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, void **, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1401b9edc`

## callees

- `0x1401040e0`
- `0x1401b9d38`
- `0x1401d3480`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401b9e83`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1401b9e83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1401b9db8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1401b9db8`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1401b9dd0`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1401b9df9`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1401b9dd0`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1401b9df9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b9e90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1401b9e90`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1401b9e26`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1401b9e26`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x1401b9e50`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcessModules` at `0x1401b9e50`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x1401b9d92`
- `api-ms-win-core-psapi-l1-1-0!K32EnumProcesses` at `0x1401b9d92`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x1401b9e6f`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleBaseNameW` at `0x1401b9e6f`

## pseudocode

```c
__int64 __fastcall Accommodation::FindProcess(const unsigned __int16 *a1, void **a2)
{
  DWORD CurrentProcessId; // eax
  DWORD v5; // r15d
  DWORD v6; // esi
  __int64 i; // rbx
  DWORD v8; // ecx
  DWORD v9; // r8d
  HANDLE v10; // rax
  void *v11; // rdi
  DWORD cbNeeded; // [rsp+20h] [rbp-E0h] BYREF
  DWORD pSessionId; // [rsp+24h] [rbp-DCh] BYREF
  DWORD v15; // [rsp+28h] [rbp-D8h] BYREF
  DWORD v16; // [rsp+2Ch] [rbp-D4h] BYREF
  HMODULE hModule; // [rsp+30h] [rbp-D0h] BYREF
  DWORD idProcess[2048]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR BaseName[264]; // [rsp+2040h] [rbp+1F40h] BYREF

  *a2 = 0;
  cbNeeded = 0;
  if ( !K32EnumProcesses(idProcess, 0x2000u, &cbNeeded) )
    return 0;
  cbNeeded >>= 2;
  if ( cbNeeded > 0x800 )
    cbNeeded = 2048;
  CurrentProcessId = GetCurrentProcessId();
  pSessionId = 0;
  v5 = CurrentProcessId;
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    return 0;
  v6 = 0;
  for ( i = 0; (unsigned int)i < cbNeeded; i = (unsigned int)(i + 1) )
  {
    v8 = idProcess[i];
    v15 = 0;
    if ( ProcessIdToSessionId(v8, &v15) )
    {
      if ( v15 == pSessionId )
      {
        v9 = idProcess[i];
        if ( v5 != v9 )
        {
          v10 = OpenProcess(0x410u, 0, v9);
          v11 = v10;
          if ( v10 )
          {
            hModule = 0;
            v16 = 0;
            if ( K32EnumProcessModules(v10, &hModule, 8u, &v16)
              && K32GetModuleBaseNameW(v11, hModule, BaseName, 0x104u)
              && !(unsigned int)_o__wcsicmp(BaseName, a1) )
            {
              v6 = idProcess[i];
              *a2 = v11;
              return v6;
            }
            CloseHandle(v11);
          }
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1401b9d38  mov     [rsp-8+arg_10], rbx
0x1401b9d3d  push    rbp
0x1401b9d3e  push    rsi
0x1401b9d3f  push    rdi
0x1401b9d40  push    r12
0x1401b9d42  push    r13
0x1401b9d44  push    r14
0x1401b9d46  push    r15
0x1401b9d48  lea     rbp, [rsp-2160h]
0x1401b9d50  mov     eax, 2260h
0x1401b9d55  call    _alloca_probe
0x1401b9d5a  sub     rsp, rax
0x1401b9d5d  mov     rax, cs:__security_cookie
0x1401b9d64  xor     rax, rsp
0x1401b9d67  mov     [rbp+2190h+var_40], rax
0x1401b9d6e  mov     r12, rdx
0x1401b9d71  mov     qword ptr [rdx], 0
0x1401b9d78  mov     r13, rcx
0x1401b9d7b  mov     [rsp+2290h+cbNeeded], 0
0x1401b9d83  mov     edx, 2000h; cb
0x1401b9d88  lea     rcx, [rsp+2290h+idProcess]; lpidProcess
0x1401b9d8d  lea     r8, [rsp+2290h+cbNeeded]; lpcbNeeded
0x1401b9d92  call    cs:__imp_K32EnumProcesses
0x1401b9d98  test    eax, eax
0x1401b9d9a  jz      loc_1401B9EA9
0x1401b9da0  mov     eax, [rsp+2290h+cbNeeded]
0x1401b9da4  mov     ecx, 800h
0x1401b9da9  shr     eax, 2
0x1401b9dac  mov     [rsp+2290h+cbNeeded], eax
0x1401b9db0  cmp     eax, ecx
0x1401b9db2  jbe     short loc_1401B9DB8
0x1401b9db4  mov     [rsp+2290h+cbNeeded], ecx
0x1401b9db8  call    cs:__imp_GetCurrentProcessId
0x1401b9dbe  lea     rdx, [rsp+2290h+pSessionId]; pSessionId
0x1401b9dc3  mov     [rsp+2290h+pSessionId], 0
0x1401b9dcb  mov     ecx, eax; dwProcessId
0x1401b9dcd  mov     r15d, eax
0x1401b9dd0  call    cs:__imp_ProcessIdToSessionId
0x1401b9dd6  test    eax, eax
0x1401b9dd8  jz      loc_1401B9EA9
0x1401b9dde  xor     esi, esi
0x1401b9de0  xor     ebx, ebx
0x1401b9de2  cmp     ebx, [rsp+2290h+cbNeeded]
0x1401b9de6  jnb     loc_1401B9EA5
0x1401b9dec  mov     ecx, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x1401b9df0  lea     rdx, [rsp+2290h+var_2268]; pSessionId
0x1401b9df5  mov     [rsp+2290h+var_2268], esi
0x1401b9df9  call    cs:__imp_ProcessIdToSessionId
0x1401b9dff  test    eax, eax
0x1401b9e01  jz      loc_1401B9E96
0x1401b9e07  mov     eax, [rsp+2290h+pSessionId]
0x1401b9e0b  cmp     [rsp+2290h+var_2268], eax
0x1401b9e0f  jnz     loc_1401B9E96
0x1401b9e15  mov     r8d, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x1401b9e1a  cmp     r15d, r8d
0x1401b9e1d  jz      short loc_1401B9E96
0x1401b9e1f  xor     edx, edx; bInheritHandle
0x1401b9e21  mov     ecx, 410h; dwDesiredAccess
0x1401b9e26  call    cs:__imp_OpenProcess
0x1401b9e2c  mov     rdi, rax
0x1401b9e2f  test    rax, rax
0x1401b9e32  jz      short loc_1401B9E96
0x1401b9e34  lea     r9, [rsp+2290h+var_2264]; lpcbNeeded
0x1401b9e39  mov     [rsp+2290h+hModule], rsi
0x1401b9e3e  mov     r8d, 8; cb
0x1401b9e44  mov     [rsp+2290h+var_2264], esi
0x1401b9e48  lea     rdx, [rsp+2290h+hModule]; lphModule
0x1401b9e4d  mov     rcx, rax; hProcess
0x1401b9e50  call    cs:__imp_K32EnumProcessModules
0x1401b9e56  test    eax, eax
0x1401b9e58  jz      short loc_1401B9E8D
0x1401b9e5a  mov     rdx, [rsp+2290h+hModule]; hModule
0x1401b9e5f  lea     r8, [rbp+2190h+BaseName]; lpBaseName
0x1401b9e66  mov     r9d, 104h; nSize
0x1401b9e6c  mov     rcx, rdi; hProcess
0x1401b9e6f  call    cs:__imp_K32GetModuleBaseNameW
0x1401b9e75  test    eax, eax
0x1401b9e77  jz      short loc_1401B9E8D
0x1401b9e79  mov     rdx, r13
0x1401b9e7c  lea     rcx, [rbp+2190h+BaseName]
0x1401b9e83  call    cs:__imp__o__wcsicmp
0x1401b9e89  test    eax, eax
0x1401b9e8b  jz      short loc_1401B9E9D
0x1401b9e8d  mov     rcx, rdi; hObject
0x1401b9e90  call    cs:__imp_CloseHandle
0x1401b9e96  inc     ebx
0x1401b9e98  jmp     loc_1401B9DE2
0x1401b9e9d  mov     esi, [rsp+rbx*4+2290h+idProcess]
0x1401b9ea1  mov     [r12], rdi
0x1401b9ea5  mov     eax, esi
0x1401b9ea7  jmp     short loc_1401B9EAB
0x1401b9ea9  xor     eax, eax
0x1401b9eab  mov     rcx, [rbp+2190h+var_40]
0x1401b9eb2  xor     rcx, rsp; StackCookie
0x1401b9eb5  call    __security_check_cookie
0x1401b9eba  mov     rbx, [rsp+2290h+arg_10]
0x1401b9ec2  add     rsp, 2260h
0x1401b9ec9  pop     r15
0x1401b9ecb  pop     r14
0x1401b9ecd  pop     r13
0x1401b9ecf  pop     r12
0x1401b9ed1  pop     rdi
0x1401b9ed2  pop     rsi
0x1401b9ed3  pop     rbp
0x1401b9ed4  retn
```
