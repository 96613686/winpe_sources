# DwGetConfigInfoForDeviceClass

- ea: `0x180010b48`
- end: `0x180010bfd`
- name: `DwGetConfigInfoForDeviceClass`
- size: `181`
- prototype: `__int64 __fastcall(DWORD dwDeviceID, LPCSTR lpszDeviceClass)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180010c04`

## callees

- `0x180010b48`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010b68`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010bbb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010b68`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180010bbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010bae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010be3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010bae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010be3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b76`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetDevConfigA` at `0x180010b8d`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetDevConfigA` at `0x180010bd4`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetDevConfigA` at `0x180010b8d`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetDevConfigA` at `0x180010bd4`

## pseudocode

```c
__int64 __fastcall DwGetConfigInfoForDeviceClass(DWORD dwDeviceID, LPCSTR lpszDeviceClass, struct varstring_tag **a3)
{
  struct varstring_tag *v6; // rax
  struct varstring_tag *v7; // rbx
  DWORD LastError; // eax
  LONG DevConfigA; // eax
  DWORD v10; // edi
  unsigned int dwNeededSize; // esi
  struct varstring_tag *v12; // rax

  v6 = (struct varstring_tag *)LocalAlloc(0x40u, 0x7D0u);
  v7 = v6;
  if ( !v6 )
    goto LABEL_2;
  v6->dwTotalSize = 2000;
  DevConfigA = lineGetDevConfigA(dwDeviceID, v6, lpszDeviceClass);
  v10 = DevConfigA;
  if ( DevConfigA && DevConfigA != -2147483571 )
    goto LABEL_10;
  dwNeededSize = v7->dwNeededSize;
  if ( dwNeededSize <= 0x7D0 )
    goto LABEL_9;
  LocalFree(v7);
  v12 = (struct varstring_tag *)LocalAlloc(0x40u, dwNeededSize);
  v7 = v12;
  if ( v12 )
  {
    v12->dwTotalSize = dwNeededSize;
    LastError = lineGetDevConfigA(dwDeviceID, v12, lpszDeviceClass);
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
  }
  v10 = LastError;
LABEL_9:
  if ( v10 )
  {
LABEL_10:
    LocalFree(v7);
    v7 = 0;
  }
  *a3 = v7;
  return v10;
}

```

## disassembly

```asm
0x180010b48  push    rbx
0x180010b4a  push    rbp
0x180010b4b  push    rsi
0x180010b4c  push    rdi
0x180010b4d  push    r14
0x180010b4f  push    r15
0x180010b51  sub     rsp, 28h
0x180010b55  mov     rbp, rdx
0x180010b58  mov     r14d, ecx
0x180010b5b  mov     edx, 7D0h; uBytes
0x180010b60  mov     ecx, 40h ; '@'; uFlags
0x180010b65  mov     r15, r8
0x180010b68  call    cs:__imp_LocalAlloc
0x180010b6e  mov     rbx, rax
0x180010b71  test    rax, rax
0x180010b74  jnz     short loc_180010B7E
0x180010b76  call    cs:__imp_GetLastError
0x180010b7c  jmp     short loc_180010BDA
0x180010b7e  mov     r8, rbp; lpszDeviceClass
0x180010b81  mov     dword ptr [rax], 7D0h
0x180010b87  mov     rdx, rbx; lpDeviceConfig
0x180010b8a  mov     ecx, r14d; dwDeviceID
0x180010b8d  call    cs:__imp_lineGetDevConfigA
0x180010b93  mov     edi, eax
0x180010b95  test    eax, eax
0x180010b97  jz      short loc_180010BA0
0x180010b99  cmp     eax, 8000004Dh
0x180010b9e  jnz     short loc_180010BE0
0x180010ba0  mov     esi, [rbx+4]
0x180010ba3  cmp     esi, 7D0h
0x180010ba9  jbe     short loc_180010BDC
0x180010bab  mov     rcx, rbx; hMem
0x180010bae  call    cs:__imp_LocalFree
0x180010bb4  mov     edx, esi; uBytes
0x180010bb6  mov     ecx, 40h ; '@'; uFlags
0x180010bbb  call    cs:__imp_LocalAlloc
0x180010bc1  mov     rbx, rax
0x180010bc4  test    rax, rax
0x180010bc7  jz      short loc_180010B76
0x180010bc9  mov     r8, rbp; lpszDeviceClass
0x180010bcc  mov     [rax], esi
0x180010bce  mov     rdx, rax; lpDeviceConfig
0x180010bd1  mov     ecx, r14d; dwDeviceID
0x180010bd4  call    cs:__imp_lineGetDevConfigA
0x180010bda  mov     edi, eax
0x180010bdc  test    edi, edi
0x180010bde  jz      short loc_180010BEB
0x180010be0  mov     rcx, rbx; hMem
0x180010be3  call    cs:__imp_LocalFree
0x180010be9  xor     ebx, ebx
0x180010beb  mov     [r15], rbx
0x180010bee  mov     eax, edi
0x180010bf0  add     rsp, 28h
0x180010bf4  pop     r15
0x180010bf6  pop     r14
0x180010bf8  pop     rdi
0x180010bf9  pop     rsi
0x180010bfa  pop     rbp
0x180010bfb  pop     rbx
0x180010bfc  retn
```
