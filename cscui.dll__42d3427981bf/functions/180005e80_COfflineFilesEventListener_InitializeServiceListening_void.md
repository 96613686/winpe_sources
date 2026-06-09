# COfflineFilesEventListener::_InitializeServiceListening(void)

- ea: `0x180005e80`
- end: `0x180005f4f`
- name: `?_InitializeServiceListening@COfflineFilesEventListener@@IEAAJXZ`
- size: `207`
- prototype: `__int64 __fastcall(COfflineFilesEventListener *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180005cf0`

## callees

- `0x180005e80`
- `0x180008394`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ef2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005eaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005ef2`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180005ee0`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180005ee0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005f23`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005f37`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005f23`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180005f37`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180005e9c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180005e9c`

## string_xrefs

- `0x180005e8d`: `ServicesActive`
- `0x180005ed6`: `CscService`

## pseudocode

```c
signed int __fastcall COfflineFilesEventListener::_InitializeServiceListening(COfflineFilesEventListener *this)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // rdi
  signed int result; // eax
  SC_HANDLE v5; // rax
  signed int LastError; // eax
  signed int v7; // ebx
  SC_HANDLE v8; // rcx

  v2 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v3 = v2;
  if ( v2 )
  {
    v5 = OpenServiceW(v2, L"CscService", 4u);
    *((_QWORD *)this + 20) = v5;
    if ( v5 )
    {
      v7 = COfflineFilesEventListener::_RegisterServiceNotifyCallback(this);
      if ( v7 < 0 )
      {
        v8 = (SC_HANDLE)*((_QWORD *)this + 20);
        if ( v8 )
        {
          CloseServiceHandle(v8);
          *((_QWORD *)this + 20) = 0;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseServiceHandle(v3);
    return v7;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180005e80  mov     [rsp+arg_8], rsi
0x180005e85  push    rdi
0x180005e86  sub     rsp, 20h
0x180005e8a  mov     rsi, rcx
0x180005e8d  lea     rdx, DatabaseName; "ServicesActive"
0x180005e94  xor     ecx, ecx; lpMachineName
0x180005e96  mov     r8d, 1; dwDesiredAccess
0x180005e9c  call    cs:__imp_OpenSCManagerW
0x180005ea2  mov     rdi, rax
0x180005ea5  test    rax, rax
0x180005ea8  jnz     short loc_180005ECB
0x180005eaa  call    cs:__imp_GetLastError
0x180005eb0  test    eax, eax
0x180005eb2  jle     loc_180005F44
0x180005eb8  movzx   eax, ax
0x180005ebb  or      eax, 80070000h
0x180005ec0  mov     rsi, [rsp+28h+arg_8]
0x180005ec5  add     rsp, 20h
0x180005ec9  pop     rdi
0x180005eca  retn
0x180005ecb  mov     r8d, 4; dwDesiredAccess
0x180005ed1  mov     [rsp+28h+arg_0], rbx
0x180005ed6  lea     rdx, ServiceName; "CscService"
0x180005edd  mov     rcx, rdi; hSCManager
0x180005ee0  call    cs:__imp_OpenServiceW
0x180005ee6  mov     [rsi+0A0h], rax
0x180005eed  test    rax, rax
0x180005ef0  jnz     short loc_180005F09
0x180005ef2  call    cs:__imp_GetLastError
0x180005ef8  mov     ebx, eax
0x180005efa  test    eax, eax
0x180005efc  jle     short loc_180005F34
0x180005efe  movzx   ebx, ax
0x180005f01  or      ebx, 80070000h
0x180005f07  jmp     short loc_180005F34
0x180005f09  mov     rcx, rsi; this
0x180005f0c  call    ?_RegisterServiceNotifyCallback@COfflineFilesEventListener@@IEAAJXZ; COfflineFilesEventListener::_RegisterServiceNotifyCallback(void)
0x180005f11  mov     ebx, eax
0x180005f13  test    eax, eax
0x180005f15  jns     short loc_180005F34
0x180005f17  mov     rcx, [rsi+0A0h]; hSCObject
0x180005f1e  test    rcx, rcx
0x180005f21  jz      short loc_180005F34
0x180005f23  call    cs:__imp_CloseServiceHandle
0x180005f29  mov     qword ptr [rsi+0A0h], 0
0x180005f34  mov     rcx, rdi; hSCObject
0x180005f37  call    cs:__imp_CloseServiceHandle
0x180005f3d  mov     eax, ebx
0x180005f3f  mov     rbx, [rsp+28h+arg_0]
0x180005f44  mov     rsi, [rsp+28h+arg_8]
0x180005f49  add     rsp, 20h
0x180005f4d  pop     rdi
0x180005f4e  retn
```
