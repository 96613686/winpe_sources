# PortGetIOHandle

- ea: `0x180013b60`
- end: `0x180013bee`
- name: `PortGetIOHandle`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000d92c`
- `0x180012340`
- `0x180013b60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013bdb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013bdb`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013bd1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180013bd1`
- `api-ms-win-core-comm-l1-1-0!PurgeComm` at `0x180013ba2`
- `api-ms-win-core-comm-l1-1-0!PurgeComm` at `0x180013ba2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180013b90`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180013b90`

## string_xrefs

- `0x180013b7f`: `PortGetIOHandle: Purging Comm %s`
- `0x180013bb9`: `PortGetIOHandle: %s. port not open. State = %d`

## pseudocode

```c
__int64 __fastcall PortGetIOHandle(__int64 a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rax
  unsigned int v7; // ebx

  GetMutex(a1, a2, a3, a4);
  if ( *(_DWORD *)(a1 + 56) == 3 )
  {
    RasTapiTrace("PortGetIOHandle: Purging Comm %s");
    Sleep(0xAu);
    PurgeComm(*(HANDLE *)(a1 + 888), 0xEu);
    v6 = *(_QWORD *)(a1 + 888);
    v7 = 0;
    *a2 = v6;
  }
  else
  {
    RasTapiTrace("PortGetIOHandle: %s. port not open. State = %d");
    v7 = 618;
  }
  if ( !ReleaseMutex(RasTapiMutex) )
    GetLastError();
  return v7;
}

```

## disassembly

```asm
0x180013b60  mov     [rsp+arg_0], rbx
0x180013b65  push    rdi
0x180013b66  sub     rsp, 20h
0x180013b6a  mov     rdi, rdx
0x180013b6d  mov     rbx, rcx
0x180013b70  call    GetMutex
0x180013b75  cmp     dword ptr [rbx+38h], 3
0x180013b79  lea     rdx, [rbx+18h]
0x180013b7d  jnz     short loc_180013BB6
0x180013b7f  lea     rcx, aPortgetiohandl_0; "PortGetIOHandle: Purging Comm %s"
0x180013b86  call    RasTapiTrace
0x180013b8b  mov     ecx, 0Ah; dwMilliseconds
0x180013b90  call    cs:__imp_Sleep
0x180013b96  mov     rcx, [rbx+378h]; hFile
0x180013b9d  mov     edx, 0Eh; dwFlags
0x180013ba2  call    cs:__imp_PurgeComm
0x180013ba8  mov     rax, [rbx+378h]
0x180013baf  xor     ebx, ebx
0x180013bb1  mov     [rdi], rax
0x180013bb4  jmp     short loc_180013BCA
0x180013bb6  mov     r8, rdx
0x180013bb9  lea     rcx, aPortgetiohandl_1; "PortGetIOHandle: %s. port not open. Sta"...
0x180013bc0  call    RasTapiTrace
0x180013bc5  mov     ebx, 26Ah
0x180013bca  mov     rcx, cs:RasTapiMutex; hMutex
0x180013bd1  call    cs:__imp_ReleaseMutex
0x180013bd7  test    eax, eax
0x180013bd9  jnz     short loc_180013BE1
0x180013bdb  call    cs:__imp_GetLastError
0x180013be1  mov     eax, ebx
0x180013be3  mov     rbx, [rsp+28h+arg_0]
0x180013be8  add     rsp, 20h
0x180013bec  pop     rdi
0x180013bed  retn
```
