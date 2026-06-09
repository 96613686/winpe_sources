# CDownloadHistoryManager::ReleaseDownloadHistoryData(__MIDL___MIDL_itf_dlm_0000_0000_0017 *)

- ea: `0x180380628`
- end: `0x180380707`
- name: `?ReleaseDownloadHistoryData@CDownloadHistoryManager@@SAXPEAU__MIDL___MIDL_itf_dlm_0000_0000_0017@@@Z`
- size: `223`
- prototype: `void __fastcall(struct __MIDL___MIDL_itf_dlm_0000_0000_0017 *)`
- caller_count: `18`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18037fb30`
- `0x18037fc5c`
- `0x180381c20`
- `0x180383650`
- `0x18038495c`
- `0x1803856e0`
- `0x1803862e4`
- `0x1803863dc`
- `0x180386a78`
- `0x18038712c`
- `0x180387540`
- `0x180387ab8`
- `0x180387c30`
- `0x180388408`
- `0x18038aed0`
- `0x18038c420`
- `0x18038d944`
- `0x180393e44`

## import_xrefs

- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180380638`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180380645`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180380652`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18038065f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18038066c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180380679`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180380686`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180380693`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803806a0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803806ad`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803806ba`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803806c7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803806d4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803806e1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803806ee`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180380638`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180380645`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180380652`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18038065f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18038066c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180380679`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180380686`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180380693`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803806a0`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803806ad`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803806ba`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803806c7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803806d4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803806e1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1803806ee`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180380700`

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
0x180380628  push    rbx
0x18038062a  sub     rsp, 20h
0x18038062e  mov     rbx, rcx
0x180380631  mov     rcx, [rcx+158h]; pv
0x180380638  call    cs:__imp_CoTaskMemFree
0x18038063e  mov     rcx, [rbx+160h]; pv
0x180380645  call    cs:__imp_CoTaskMemFree
0x18038064b  mov     rcx, [rbx+168h]; pv
0x180380652  call    cs:__imp_CoTaskMemFree
0x180380658  mov     rcx, [rbx+170h]; pv
0x18038065f  call    cs:__imp_CoTaskMemFree
0x180380665  mov     rcx, [rbx+178h]; pv
0x18038066c  call    cs:__imp_CoTaskMemFree
0x180380672  mov     rcx, [rbx+180h]; pv
0x180380679  call    cs:__imp_CoTaskMemFree
0x18038067f  mov     rcx, [rbx+188h]; pv
0x180380686  call    cs:__imp_CoTaskMemFree
0x18038068c  mov     rcx, [rbx+190h]; pv
0x180380693  call    cs:__imp_CoTaskMemFree
0x180380699  mov     rcx, [rbx+198h]; pv
0x1803806a0  call    cs:__imp_CoTaskMemFree
0x1803806a6  mov     rcx, [rbx+1A0h]; pv
0x1803806ad  call    cs:__imp_CoTaskMemFree
0x1803806b3  mov     rcx, [rbx+1C0h]; pv
0x1803806ba  call    cs:__imp_CoTaskMemFree
0x1803806c0  mov     rcx, [rbx+1A8h]; pv
0x1803806c7  call    cs:__imp_CoTaskMemFree
0x1803806cd  mov     rcx, [rbx+1C8h]; pv
0x1803806d4  call    cs:__imp_CoTaskMemFree
0x1803806da  mov     rcx, [rbx+1D0h]; pv
0x1803806e1  call    cs:__imp_CoTaskMemFree
0x1803806e7  mov     rcx, [rbx+1B0h]; pv
0x1803806ee  call    cs:__imp_CoTaskMemFree
0x1803806f4  mov     rcx, [rbx+1B8h]
0x1803806fb  add     rsp, 20h
0x1803806ff  pop     rbx
0x180380700  jmp     cs:__imp_CoTaskMemFree
```
