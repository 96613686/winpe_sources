# TSPI_lineGetDevConfig

- ea: `0x180005bc0`
- end: `0x180005ceb`
- name: `TSPI_lineGetDevConfig`
- size: `299`
- prototype: `LONG __stdcall(DWORD dwDeviceID, LPVARSTRING lpDeviceConfig, LPCWSTR lpszDeviceClass)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x18000298c`
- `0x180003af0`
- `0x180004184`
- `0x180005bc0`
- `0x180007df8`
- `0x180008091`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x180005ca4`
- `KERNEL32!WideCharToMultiByte` at `0x180005ca4`
- `KERNEL32!lstrlenW` at `0x180005bd8`
- `KERNEL32!lstrlenW` at `0x180005bd8`

## string_xrefs

- `0x180005beb`: `lineGetDevConfig(%d): deviceID(%x)`

## pseudocode

```c
LONG __stdcall TSPI_lineGetDevConfig(DWORD dwDeviceID, LPVARSTRING lpDeviceConfig, LPCWSTR lpszDeviceClass)
{
  int v6; // eax
  int cbMultiByte; // ebp
  LONG result; // eax
  _DWORD *v9; // rsi
  char *v10; // rdi
  DWORD v11; // ecx
  LONG v12; // ebp
  void *lpInBuffer; // [rsp+88h] [rbp+10h] BYREF

  v6 = lstrlenW(lpszDeviceClass);
  lpInBuffer = 0;
  ++dword_18000E254;
  cbMultiByte = v6 + 1;
  TspLog(8, "lineGetDevConfig(%d): deviceID(%x)", dword_18000E254, dwDeviceID);
  result = PrepareSyncRequest(117637393, dwDeviceID, cbMultiByte + lpDeviceConfig->dwTotalSize + 16, &lpInBuffer);
  if ( !result )
  {
    v9 = lpInBuffer;
    v10 = (char *)lpInBuffer + 16;
    *((_DWORD *)lpInBuffer + 5) = dwDeviceID;
    *((_DWORD *)v10 + 2) = cbMultiByte;
    v11 = lpDeviceConfig->dwTotalSize + 16;
    *((_DWORD *)v10 + 3) = v11;
    *((_DWORD *)v10 + 4) = lpDeviceConfig->dwTotalSize;
    *((_DWORD *)v10 + 6) = 24;
    *((_DWORD *)v10 + 5) = 24;
    *((_QWORD *)v10 + 4) = 0;
    *((_DWORD *)v10 + 7) = 0;
    WideCharToMultiByte(0, 0, lpszDeviceClass, -1, &v10[v11], cbMultiByte, 0, 0);
    v12 = SyncDriverRequest(0x8FFF23C8, v9);
    if ( !v12 )
      memcpy_0(lpDeviceConfig, v10 + 16, *((unsigned int *)v10 + 6));
    FreeRequest(v9);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x180005bc0  push    rbx
0x180005bc2  push    rbp
0x180005bc3  push    rsi
0x180005bc4  push    rdi
0x180005bc5  push    r14
0x180005bc7  push    r15
0x180005bc9  sub     rsp, 48h
0x180005bcd  mov     ebx, ecx
0x180005bcf  mov     r15, r8
0x180005bd2  mov     rcx, r8; lpString
0x180005bd5  mov     r14, rdx
0x180005bd8  call    cs:__imp_lstrlenW
0x180005bdf  nop     dword ptr [rax+rax+00h]
0x180005be4  mov     r8d, cs:dword_18000E254
0x180005beb  lea     rdx, aLinegetdevconf; "lineGetDevConfig(%d): deviceID(%x)"
0x180005bf2  inc     r8d
0x180005bf5  mov     [rsp+78h+lpInBuffer], 0
0x180005c01  mov     r9d, ebx
0x180005c04  mov     cs:dword_18000E254, r8d
0x180005c0b  mov     ecx, 8
0x180005c10  lea     ebp, [rax+1]
0x180005c13  call    TspLog
0x180005c18  mov     r8d, [r14]
0x180005c1b  lea     r9, [rsp+78h+lpInBuffer]
0x180005c23  add     r8d, 10h
0x180005c27  mov     edx, ebx
0x180005c29  add     r8d, ebp
0x180005c2c  mov     ecx, 7030111h
0x180005c31  call    PrepareSyncRequest
0x180005c36  test    eax, eax
0x180005c38  jnz     loc_180005CDD
0x180005c3e  mov     rsi, [rsp+78h+lpInBuffer]
0x180005c46  or      r9d, 0FFFFFFFFh; cchWideChar
0x180005c4a  mov     [rsp+78h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180005c53  mov     r8, r15; lpWideCharStr
0x180005c56  mov     [rsp+78h+lpDefaultChar], 0; lpDefaultChar
0x180005c5f  xor     edx, edx; dwFlags
0x180005c61  mov     [rsp+78h+cbMultiByte], ebp; cbMultiByte
0x180005c65  lea     rdi, [rsi+10h]
0x180005c69  mov     [rdi+4], ebx
0x180005c6c  mov     [rdi+8], ebp
0x180005c6f  mov     ecx, [r14]
0x180005c72  add     ecx, 10h
0x180005c75  mov     [rdi+0Ch], ecx
0x180005c78  mov     eax, [r14]
0x180005c7b  mov     [rdi+10h], eax
0x180005c7e  mov     eax, 18h
0x180005c83  mov     [rdi+18h], eax
0x180005c86  mov     [rdi+14h], eax
0x180005c89  mov     eax, ecx
0x180005c8b  xor     ecx, ecx; CodePage
0x180005c8d  add     rax, rdi
0x180005c90  mov     qword ptr [rdi+20h], 0
0x180005c98  mov     [rsp+78h+lpMultiByteStr], rax; lpMultiByteStr
0x180005c9d  mov     dword ptr [rdi+1Ch], 0
0x180005ca4  call    cs:__imp_WideCharToMultiByte
0x180005cab  nop     dword ptr [rax+rax+00h]
0x180005cb0  mov     rdx, rsi; lpInBuffer
0x180005cb3  mov     ecx, 8FFF23C8h; dwIoControlCode
0x180005cb8  call    SyncDriverRequest
0x180005cbd  mov     ebp, eax
0x180005cbf  test    eax, eax
0x180005cc1  jnz     short loc_180005CD3
0x180005cc3  mov     r8d, [rdi+18h]; Size
0x180005cc7  lea     rdx, [rdi+10h]; Src
0x180005ccb  mov     rcx, r14; void *
0x180005cce  call    memcpy_0
0x180005cd3  mov     rcx, rsi; void *
0x180005cd6  call    FreeRequest
0x180005cdb  mov     eax, ebp
0x180005cdd  add     rsp, 48h
0x180005ce1  pop     r15
0x180005ce3  pop     r14
0x180005ce5  pop     rdi
0x180005ce6  pop     rsi
0x180005ce7  pop     rbp
0x180005ce8  pop     rbx
0x180005ce9  retn
```
