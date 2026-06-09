# SvcRunning(ushort *)

- ea: `0x18001bb90`
- end: `0x18001bc99`
- name: `?SvcRunning@@YAHPEAG@Z`
- size: `265`
- prototype: `bool __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180016c1c`

## callees

- `0x1800025f0`
- `0x18001bb90`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001bbd3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18001bbd3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001bc58`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001bc66`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001bc58`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18001bc66`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001bbf3`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18001bbf3`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18001bc3e`
- `api-ms-win-service-management-l2-1-0!QueryServiceStatusEx` at `0x18001bc3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc48`

## pseudocode

```c
bool __fastcall SvcRunning(unsigned __int16 *a1)
{
  SC_HANDLE v1; // rax
  SC_HANDLE v2; // rsi
  DWORD LastError; // ebx
  SC_HANDLE v4; // rdi
  bool result; // al
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-48h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-40h] BYREF
  __int128 v8; // [rsp+48h] [rbp-30h]
  int v9; // [rsp+58h] [rbp-20h]

  pcbBytesNeeded = 0;
  v9 = 0;
  *(_OWORD *)Buffer = 0;
  v8 = 0;
  v1 = OpenSCManagerW(0, 0, 0x80000000);
  v2 = v1;
  if ( !v1 )
  {
    v4 = 0;
    goto LABEL_5;
  }
  LastError = 0;
  v4 = OpenServiceW(v1, L"Netman", 0x20004u);
  if ( !v4 )
  {
LABEL_5:
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_10;
  }
  v9 = 0;
  *(_OWORD *)Buffer = 0;
  v8 = 0;
  if ( !QueryServiceStatusEx(v4, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
    LastError = GetLastError();
  if ( v4 )
    CloseServiceHandle(v4);
LABEL_10:
  if ( v2 )
    CloseServiceHandle(v2);
  result = 0;
  if ( !LastError )
    return *(_DWORD *)&Buffer[4] == 4;
  return result;
}

```

## disassembly

```asm
0x18001bb90  mov     [rsp+arg_0], rbx
0x18001bb95  mov     [rsp+arg_8], rsi
0x18001bb9a  push    rdi
0x18001bb9b  sub     rsp, 70h
0x18001bb9f  mov     rax, cs:__security_cookie
0x18001bba6  xor     rax, rsp
0x18001bba9  mov     [rsp+78h+var_18], rax
0x18001bbae  xorps   xmm0, xmm0
0x18001bbb1  mov     [rsp+78h+var_48], 0
0x18001bbb9  xor     eax, eax
0x18001bbbb  xor     edx, edx; lpDatabaseName
0x18001bbbd  xor     ecx, ecx; lpMachineName
0x18001bbbf  mov     [rsp+78h+var_20], eax
0x18001bbc3  mov     r8d, 80000000h; dwDesiredAccess
0x18001bbc9  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x18001bbce  movups  [rsp+78h+var_30], xmm0
0x18001bbd3  call    cs:__imp_OpenSCManagerW
0x18001bbd9  mov     rsi, rax
0x18001bbdc  test    rax, rax
0x18001bbdf  jz      short loc_18001BC03
0x18001bbe1  mov     r8d, 20004h; dwDesiredAccess
0x18001bbe7  lea     rdx, aNetman; "Netman"
0x18001bbee  mov     rcx, rax; hSCManager
0x18001bbf1  xor     ebx, ebx
0x18001bbf3  call    cs:__imp_OpenServiceW
0x18001bbf9  mov     rdi, rax
0x18001bbfc  test    rax, rax
0x18001bbff  jnz     short loc_18001BC11
0x18001bc01  jmp     short loc_18001BC05
0x18001bc03  xor     edi, edi
0x18001bc05  call    cs:__imp_GetLastError
0x18001bc0b  mov     ebx, eax
0x18001bc0d  test    eax, eax
0x18001bc0f  jnz     short loc_18001BC5E
0x18001bc11  xor     eax, eax
0x18001bc13  lea     r8, [rsp+78h+Buffer]; lpBuffer
0x18001bc18  xorps   xmm0, xmm0
0x18001bc1b  mov     [rsp+78h+var_20], eax
0x18001bc1f  lea     rax, [rsp+78h+var_48]
0x18001bc24  mov     r9d, 24h ; '$'; cbBufSize
0x18001bc2a  xor     edx, edx; InfoLevel
0x18001bc2c  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18001bc31  mov     rcx, rdi; hService
0x18001bc34  movups  xmmword ptr [rsp+78h+Buffer], xmm0
0x18001bc39  movups  [rsp+78h+var_30], xmm0
0x18001bc3e  call    cs:__imp_QueryServiceStatusEx
0x18001bc44  test    eax, eax
0x18001bc46  jnz     short loc_18001BC50
0x18001bc48  call    cs:__imp_GetLastError
0x18001bc4e  mov     ebx, eax
0x18001bc50  test    rdi, rdi
0x18001bc53  jz      short loc_18001BC5E
0x18001bc55  mov     rcx, rdi; hSCObject
0x18001bc58  call    cs:__imp_CloseServiceHandle
0x18001bc5e  test    rsi, rsi
0x18001bc61  jz      short loc_18001BC6C
0x18001bc63  mov     rcx, rsi; hSCObject
0x18001bc66  call    cs:__imp_CloseServiceHandle
0x18001bc6c  xor     eax, eax
0x18001bc6e  test    ebx, ebx
0x18001bc70  jnz     short loc_18001BC7A
0x18001bc72  cmp     dword ptr [rsp+78h+Buffer+4], 4
0x18001bc77  setz    al
0x18001bc7a  mov     rcx, [rsp+78h+var_18]
0x18001bc7f  xor     rcx, rsp; StackCookie
0x18001bc82  call    __security_check_cookie
0x18001bc87  lea     r11, [rsp+78h+var_8]
0x18001bc8c  mov     rbx, [r11+10h]
0x18001bc90  mov     rsi, [r11+18h]
0x18001bc94  mov     rsp, r11
0x18001bc97  pop     rdi
0x18001bc98  retn
```
