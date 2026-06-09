# fcicb_Close

- ea: `0x18002a790`
- end: `0x18002a801`
- name: `fcicb_Close`
- size: `113`
- prototype: `int __cdecl(INT_PTR hf, int *err, void *pv)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002b110`
- `0x18002b1f0`

## callees

- `0x18002a790`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a7bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a7bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a7c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a7c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a7e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a7e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a7e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a7e9`

## pseudocode

```c
__int64 __fastcall fcicb_Close(INT_PTR hf, DWORD *err, void *pv)
{
  unsigned int v3; // edi
  void *v6; // rcx

  v3 = 0;
  if ( (*(_BYTE *)hf & 1) != 0 )
  {
    if ( (*(_BYTE *)hf & 2) != 0 )
    {
      v6 = *(void **)(hf + 8);
LABEL_9:
      CoTaskMemFree(v6);
    }
  }
  else
  {
    if ( !CloseHandle(*(HANDLE *)(hf + 32)) )
    {
      *err = GetLastError();
      v3 = -1;
    }
    if ( (*(_BYTE *)hf & 4) != 0 && *(_DWORD *)(hf + 24) )
    {
      v6 = *(void **)(hf + 8);
      goto LABEL_9;
    }
  }
  CoTaskMemFree((LPVOID)hf);
  return v3;
}

```

## disassembly

```asm
0x18002a790  mov     [rsp+arg_0], rbx
0x18002a795  mov     [rsp+arg_8], rsi
0x18002a79a  push    rdi
0x18002a79b  sub     rsp, 20h
0x18002a79f  xor     edi, edi
0x18002a7a1  mov     rsi, rdx
0x18002a7a4  test    byte ptr [rcx], 1
0x18002a7a7  mov     rbx, rcx
0x18002a7aa  jz      short loc_18002A7B7
0x18002a7ac  test    byte ptr [rcx], 2
0x18002a7af  jz      short loc_18002A7E6
0x18002a7b1  mov     rcx, [rcx+8]
0x18002a7b5  jmp     short loc_18002A7E0
0x18002a7b7  mov     rcx, [rcx+20h]; hObject
0x18002a7bb  call    cs:__imp_CloseHandle
0x18002a7c1  cmp     eax, 1
0x18002a7c4  jz      short loc_18002A7D1
0x18002a7c6  call    cs:__imp_GetLastError
0x18002a7cc  mov     [rsi], eax
0x18002a7ce  or      edi, 0FFFFFFFFh
0x18002a7d1  test    byte ptr [rbx], 4
0x18002a7d4  jz      short loc_18002A7E6
0x18002a7d6  cmp     dword ptr [rbx+18h], 0
0x18002a7da  jz      short loc_18002A7E6
0x18002a7dc  mov     rcx, [rbx+8]; pv
0x18002a7e0  call    cs:__imp_CoTaskMemFree
0x18002a7e6  mov     rcx, rbx; pv
0x18002a7e9  call    cs:__imp_CoTaskMemFree
0x18002a7ef  mov     rbx, [rsp+28h+arg_0]
0x18002a7f4  mov     eax, edi
0x18002a7f6  mov     rsi, [rsp+28h+arg_8]
0x18002a7fb  add     rsp, 20h
0x18002a7ff  pop     rdi
0x18002a800  retn
```
