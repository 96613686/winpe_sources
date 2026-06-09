# RasAutoDialSharedConnection

- ea: `0x1800b0590`
- end: `0x1800b064e`
- name: `RasAutoDialSharedConnection`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800b0590`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b05fe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b05fe`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x1800b05c5`
- `api-ms-win-core-synch-l1-1-0!OpenEventA` at `0x1800b05c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b05d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b060c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b05d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b060c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b063b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b063b`
- `rtutils!TracePrintfExA` at `0x1800b05b1`
- `rtutils!TracePrintfExA` at `0x1800b05f3`
- `rtutils!TracePrintfExA` at `0x1800b0632`
- `rtutils!TracePrintfExA` at `0x1800b05b1`
- `rtutils!TracePrintfExA` at `0x1800b05f3`
- `rtutils!TracePrintfExA` at `0x1800b0632`

## string_xrefs

- `0x1800b05e9`: `RasAutoDialSharedConnection: OpenEvent=%d`

## pseudocode

```c
__int64 RasAutoDialSharedConnection()
{
  HANDLE v0; // rax
  void *v1; // rdi
  DWORD v2; // eax
  DWORD v3; // ebx
  DWORD LastError; // eax

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "RasAutoDialSharedConnection");
  v0 = OpenEventA(0x100002u, 0, "RasAutoDialSharedConnectionEvent");
  v1 = v0;
  if ( v0 )
  {
    if ( SetEvent(v0) )
    {
      v3 = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError && g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "RasAutoDialSharedConnection: SetEvent=%d", LastError);
    }
    CloseHandle(v1);
  }
  else
  {
    v2 = GetLastError();
    v3 = v2;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "RasAutoDialSharedConnection: OpenEvent=%d", v2);
  }
  return v3;
}

```

## disassembly

```asm
0x1800b0590  mov     [rsp+arg_0], rbx
0x1800b0595  push    rdi
0x1800b0596  sub     rsp, 20h
0x1800b059a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800b05a0  cmp     ecx, 0FFFFFFFFh
0x1800b05a3  jz      short loc_1800B05B7
0x1800b05a5  lea     r8, aRasautodialsha_3; "RasAutoDialSharedConnection"
0x1800b05ac  mov     edx, 0Ch; dwFlags
0x1800b05b1  call    cs:__imp_TracePrintfExA
0x1800b05b7  lea     r8, aRasautodialsha_0; "RasAutoDialSharedConnectionEvent"
0x1800b05be  xor     edx, edx; bInheritHandle
0x1800b05c0  mov     ecx, 100002h; dwDesiredAccess
0x1800b05c5  call    cs:__imp_OpenEventA
0x1800b05cb  mov     rdi, rax
0x1800b05ce  test    rax, rax
0x1800b05d1  jnz     short loc_1800B05FB
0x1800b05d3  call    cs:__imp_GetLastError
0x1800b05d9  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800b05df  mov     ebx, eax
0x1800b05e1  cmp     ecx, 0FFFFFFFFh
0x1800b05e4  jz      short loc_1800B0641
0x1800b05e6  mov     r9d, eax
0x1800b05e9  lea     r8, aRasautodialsha_2; "RasAutoDialSharedConnection: OpenEvent="...
0x1800b05f0  lea     edx, [rdi+0Ch]; dwFlags
0x1800b05f3  call    cs:__imp_TracePrintfExA
0x1800b05f9  jmp     short loc_1800B0641
0x1800b05fb  mov     rcx, rdi; hEvent
0x1800b05fe  call    cs:__imp_SetEvent
0x1800b0604  test    eax, eax
0x1800b0606  jz      short loc_1800B060C
0x1800b0608  xor     ebx, ebx
0x1800b060a  jmp     short loc_1800B0638
0x1800b060c  call    cs:__imp_GetLastError
0x1800b0612  mov     ebx, eax
0x1800b0614  test    eax, eax
0x1800b0616  jz      short loc_1800B0638
0x1800b0618  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800b061e  cmp     ecx, 0FFFFFFFFh
0x1800b0621  jz      short loc_1800B0638
0x1800b0623  mov     r9d, eax
0x1800b0626  lea     r8, aRasautodialsha_1; "RasAutoDialSharedConnection: SetEvent=%"...
0x1800b062d  mov     edx, 0Ch; dwFlags
0x1800b0632  call    cs:__imp_TracePrintfExA
0x1800b0638  mov     rcx, rdi; hObject
0x1800b063b  call    cs:__imp_CloseHandle
0x1800b0641  mov     eax, ebx
0x1800b0643  mov     rbx, [rsp+28h+arg_0]
0x1800b0648  add     rsp, 20h
0x1800b064c  pop     rdi
0x1800b064d  retn
```
