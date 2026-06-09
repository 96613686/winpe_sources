# CDownloadHistoryManager::ReleaseDownloadHistoryData(__MIDL___MIDL_itf_dlm_0000_0000_0017 *)

- ea: `0x1803b0e38`
- end: `0x1803b0f76`
- name: `?ReleaseDownloadHistoryData@CDownloadHistoryManager@@SAXPEAU__MIDL___MIDL_itf_dlm_0000_0000_0017@@@Z`
- size: `318`
- prototype: `void __fastcall(struct __MIDL___MIDL_itf_dlm_0000_0000_0017 *)`
- caller_count: `18`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x1803b0240`
- `0x1803b0380`
- `0x1803b2528`
- `0x1803b4150`
- `0x1803b552c`
- `0x1803b6334`
- `0x1803b6ffc`
- `0x1803b70fc`
- `0x1803b7808`
- `0x1803b7ef8`
- `0x1803b8328`
- `0x1803b88d8`
- `0x1803b8a5c`
- `0x1803b92ac`
- `0x1803bc0c4`
- `0x1803bd790`
- `0x1803bed58`
- `0x1803c55c8`

## import_xrefs

- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0e48`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0e5b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0e6e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0e81`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0e94`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0ea7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0eba`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0ecd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0ee0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0ef3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0f06`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0f19`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0f2c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0f3f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0f52`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0e48`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0e5b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0e6e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0e81`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0e94`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0ea7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0eba`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0ecd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0ee0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0ef3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0f06`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0f19`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0f2c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0f3f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0f52`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803b0f6a`

## pseudocode

```c
void __fastcall CDownloadHistoryManager::ReleaseDownloadHistoryData(LPVOID *a1)
{
  CoTaskMemFree(a1[43]);
  CoTaskMemFree(a1[44]);
  CoTaskMemFree(a1[45]);
  CoTaskMemFree(a1[46]);
  CoTaskMemFree(a1[47]);
  CoTaskMemFree(a1[48]);
  CoTaskMemFree(a1[49]);
  CoTaskMemFree(a1[50]);
  CoTaskMemFree(a1[51]);
  CoTaskMemFree(a1[52]);
  CoTaskMemFree(a1[56]);
  CoTaskMemFree(a1[53]);
  CoTaskMemFree(a1[57]);
  CoTaskMemFree(a1[58]);
  CoTaskMemFree(a1[54]);
  CoTaskMemFree(a1[55]);
}

```

## disassembly

```asm
0x1803b0e38  push    rbx
0x1803b0e3a  sub     rsp, 20h
0x1803b0e3e  mov     rbx, rcx
0x1803b0e41  mov     rcx, [rcx+158h]; pv
0x1803b0e48  call    cs:__imp_CoTaskMemFree
0x1803b0e4f  nop     dword ptr [rax+rax+00h]
0x1803b0e54  mov     rcx, [rbx+160h]; pv
0x1803b0e5b  call    cs:__imp_CoTaskMemFree
0x1803b0e62  nop     dword ptr [rax+rax+00h]
0x1803b0e67  mov     rcx, [rbx+168h]; pv
0x1803b0e6e  call    cs:__imp_CoTaskMemFree
0x1803b0e75  nop     dword ptr [rax+rax+00h]
0x1803b0e7a  mov     rcx, [rbx+170h]; pv
0x1803b0e81  call    cs:__imp_CoTaskMemFree
0x1803b0e88  nop     dword ptr [rax+rax+00h]
0x1803b0e8d  mov     rcx, [rbx+178h]; pv
0x1803b0e94  call    cs:__imp_CoTaskMemFree
0x1803b0e9b  nop     dword ptr [rax+rax+00h]
0x1803b0ea0  mov     rcx, [rbx+180h]; pv
0x1803b0ea7  call    cs:__imp_CoTaskMemFree
0x1803b0eae  nop     dword ptr [rax+rax+00h]
0x1803b0eb3  mov     rcx, [rbx+188h]; pv
0x1803b0eba  call    cs:__imp_CoTaskMemFree
0x1803b0ec1  nop     dword ptr [rax+rax+00h]
0x1803b0ec6  mov     rcx, [rbx+190h]; pv
0x1803b0ecd  call    cs:__imp_CoTaskMemFree
0x1803b0ed4  nop     dword ptr [rax+rax+00h]
0x1803b0ed9  mov     rcx, [rbx+198h]; pv
0x1803b0ee0  call    cs:__imp_CoTaskMemFree
0x1803b0ee7  nop     dword ptr [rax+rax+00h]
0x1803b0eec  mov     rcx, [rbx+1A0h]; pv
0x1803b0ef3  call    cs:__imp_CoTaskMemFree
0x1803b0efa  nop     dword ptr [rax+rax+00h]
0x1803b0eff  mov     rcx, [rbx+1C0h]; pv
0x1803b0f06  call    cs:__imp_CoTaskMemFree
0x1803b0f0d  nop     dword ptr [rax+rax+00h]
0x1803b0f12  mov     rcx, [rbx+1A8h]; pv
0x1803b0f19  call    cs:__imp_CoTaskMemFree
0x1803b0f20  nop     dword ptr [rax+rax+00h]
0x1803b0f25  mov     rcx, [rbx+1C8h]; pv
0x1803b0f2c  call    cs:__imp_CoTaskMemFree
0x1803b0f33  nop     dword ptr [rax+rax+00h]
0x1803b0f38  mov     rcx, [rbx+1D0h]; pv
0x1803b0f3f  call    cs:__imp_CoTaskMemFree
0x1803b0f46  nop     dword ptr [rax+rax+00h]
0x1803b0f4b  mov     rcx, [rbx+1B0h]; pv
0x1803b0f52  call    cs:__imp_CoTaskMemFree
0x1803b0f59  nop     dword ptr [rax+rax+00h]
0x1803b0f5e  mov     rcx, [rbx+1B8h]
0x1803b0f65  add     rsp, 20h
0x1803b0f69  pop     rbx
0x1803b0f6a  jmp     cs:__imp_CoTaskMemFree
```
