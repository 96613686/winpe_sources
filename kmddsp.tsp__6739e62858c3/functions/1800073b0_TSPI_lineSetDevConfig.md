# TSPI_lineSetDevConfig

- ea: `0x1800073b0`
- end: `0x1800074b1`
- name: `TSPI_lineSetDevConfig`
- size: `257`
- prototype: `LONG __stdcall(DWORD dwDeviceID, const LPVOID lpDeviceConfig, DWORD dwSize, LPCWSTR lpszDeviceClass)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000298c`
- `0x180003af0`
- `0x180004184`
- `0x1800073b0`
- `0x180007df8`
- `0x180008091`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x18000747c`
- `KERNEL32!WideCharToMultiByte` at `0x18000747c`
- `KERNEL32!lstrlenW` at `0x1800073ce`
- `KERNEL32!lstrlenW` at `0x1800073ce`

## string_xrefs

- `0x1800073e1`: `lineSetDevConfig(%d): deviceID(%x)`

## pseudocode

```c
LONG __stdcall TSPI_lineSetDevConfig(
        DWORD dwDeviceID,
        const LPVOID lpDeviceConfig,
        DWORD dwSize,
        LPCWSTR lpszDeviceClass)
{
  int v8; // eax
  int cbMultiByte; // ebp
  LONG result; // eax
  _DWORD *v11; // rdi
  CHAR *v12; // rbx
  char *v13; // rcx
  void *lpInBuffer; // [rsp+40h] [rbp-48h] BYREF

  v8 = lstrlenW(lpszDeviceClass);
  lpInBuffer = 0;
  ++dword_18000E2A8;
  cbMultiByte = v8 + 1;
  TspLog(8, "lineSetDevConfig(%d): deviceID(%x)", dword_18000E2A8, dwDeviceID);
  result = PrepareSyncRequest(117637408, dwDeviceID, cbMultiByte + dwSize + 24, &lpInBuffer);
  if ( !result )
  {
    v11 = lpInBuffer;
    v12 = (char *)lpInBuffer + 16;
    v13 = (char *)lpInBuffer + 36;
    *((_DWORD *)lpInBuffer + 5) = dwDeviceID;
    *((_DWORD *)v12 + 2) = cbMultiByte;
    *((_DWORD *)v12 + 3) = dwSize + 23;
    *((_DWORD *)v12 + 4) = dwSize;
    memcpy_0(v13, lpDeviceConfig, dwSize);
    WideCharToMultiByte(0, 0, lpszDeviceClass, -1, &v12[*((unsigned int *)v12 + 3)], cbMultiByte, 0, 0);
    LODWORD(v12) = SyncDriverRequest(0x8FFF23CC, v11);
    FreeRequest(v11);
    return (int)v12;
  }
  return result;
}

```

## disassembly

```asm
0x1800073b0  push    rbx
0x1800073b2  push    rbp
0x1800073b3  push    rsi
0x1800073b4  push    rdi
0x1800073b5  push    r12
0x1800073b7  push    r14
0x1800073b9  push    r15
0x1800073bb  sub     rsp, 50h
0x1800073bf  mov     r14d, ecx
0x1800073c2  mov     esi, r8d
0x1800073c5  mov     rcx, r9; lpString
0x1800073c8  mov     r15, r9
0x1800073cb  mov     r12, rdx
0x1800073ce  call    cs:__imp_lstrlenW
0x1800073d5  nop     dword ptr [rax+rax+00h]
0x1800073da  mov     r8d, cs:dword_18000E2A8
0x1800073e1  lea     rdx, aLinesetdevconf; "lineSetDevConfig(%d): deviceID(%x)"
0x1800073e8  inc     r8d
0x1800073eb  mov     [rsp+88h+lpInBuffer], 0
0x1800073f4  mov     r9d, r14d
0x1800073f7  mov     cs:dword_18000E2A8, r8d
0x1800073fe  mov     ecx, 8
0x180007403  lea     ebp, [rax+1]
0x180007406  call    TspLog
0x18000740b  lea     r8d, [rsi+18h]
0x18000740f  mov     edx, r14d
0x180007412  add     r8d, ebp
0x180007415  lea     r9, [rsp+88h+lpInBuffer]
0x18000741a  mov     ecx, 7030120h
0x18000741f  call    PrepareSyncRequest
0x180007424  test    eax, eax
0x180007426  jnz     short loc_1800074A1
0x180007428  mov     rdi, [rsp+88h+lpInBuffer]
0x18000742d  lea     eax, [rsi+17h]
0x180007430  mov     r8d, esi; Size
0x180007433  mov     rdx, r12; Src
0x180007436  lea     rbx, [rdi+10h]
0x18000743a  lea     rcx, [rbx+14h]; void *
0x18000743e  mov     [rbx+4], r14d
0x180007442  mov     [rbx+8], ebp
0x180007445  mov     [rbx+0Ch], eax
0x180007448  mov     [rbx+10h], esi
0x18000744b  call    memcpy_0
0x180007450  mov     eax, [rbx+0Ch]
0x180007453  or      r9d, 0FFFFFFFFh; cchWideChar
0x180007457  mov     [rsp+88h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180007460  add     rax, rbx
0x180007463  mov     [rsp+88h+lpDefaultChar], 0; lpDefaultChar
0x18000746c  mov     r8, r15; lpWideCharStr
0x18000746f  mov     [rsp+88h+cbMultiByte], ebp; cbMultiByte
0x180007473  xor     edx, edx; dwFlags
0x180007475  xor     ecx, ecx; CodePage
0x180007477  mov     [rsp+88h+lpMultiByteStr], rax; lpMultiByteStr
0x18000747c  call    cs:__imp_WideCharToMultiByte
0x180007483  nop     dword ptr [rax+rax+00h]
0x180007488  mov     rdx, rdi; lpInBuffer
0x18000748b  mov     ecx, 8FFF23CCh; dwIoControlCode
0x180007490  call    SyncDriverRequest
0x180007495  mov     rcx, rdi; void *
0x180007498  mov     ebx, eax
0x18000749a  call    FreeRequest
0x18000749f  mov     eax, ebx
0x1800074a1  add     rsp, 50h
0x1800074a5  pop     r15
0x1800074a7  pop     r14
0x1800074a9  pop     r12
0x1800074ab  pop     rdi
0x1800074ac  pop     rsi
0x1800074ad  pop     rbp
0x1800074ae  pop     rbx
0x1800074af  retn
```
