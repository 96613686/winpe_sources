# sub_18015FFBC

- ea: `0x18015ffbc`
- end: `0x18016012d`
- name: `sub_18015FFBC`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1801602e0`

## callees

- `0x180015a80`
- `0x180019e20`
- `0x180051a34`
- `0x180155c24`
- `0x18015fb7c`
- `0x18015ffbc`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801600d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801600d5`
- `WINHTTP!WinHttpReadData` at `0x180160085`
- `WINHTTP!WinHttpReadData` at `0x180160085`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180160049`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x180160049`

## pseudocode

```c
__int64 __fastcall sub_18015FFBC(__int64 a1)
{
  signed int v2; // ebx
  unsigned int v3; // r14d
  int v4; // eax
  __int64 v5; // rdi
  void *v6; // rcx
  DWORD v7; // eax
  signed int LastError; // eax
  __int64 v10; // [rsp+30h] [rbp-20h] BYREF
  LPVOID lpBuffer; // [rsp+38h] [rbp-18h] BYREF
  __int64 v12; // [rsp+40h] [rbp-10h]
  unsigned int v13; // [rsp+80h] [rbp+30h] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+88h] [rbp+38h] BYREF
  DWORD dwNumberOfBytesAvailable; // [rsp+90h] [rbp+40h] BYREF
  DWORD dwNumberOfBytesToRead; // [rsp+98h] [rbp+48h] BYREF

  v13 = 0;
  lpBuffer = 0;
  v10 = 0;
  v12 = 0;
  v2 = sub_180051A34(&v10);
  if ( v2 < 0 )
    goto LABEL_15;
  v3 = 0;
  if ( (unsigned int)sub_18015FB7C(a1, &v13) )
  {
    v4 = v13;
  }
  else
  {
    v4 = -1;
    v13 = -1;
  }
  v5 = v10;
  if ( v4 )
  {
    while ( 1 )
    {
      v6 = *(void **)(a1 + 176);
      dwNumberOfBytesAvailable = 0;
      dwNumberOfBytesRead = 0;
      dwNumberOfBytesToRead = 0;
      if ( !WinHttpQueryDataAvailable(v6, &dwNumberOfBytesAvailable) )
        break;
      v2 = sub_180155C24(v5, dwNumberOfBytesAvailable, &lpBuffer, &dwNumberOfBytesToRead);
      if ( v2 < 0 )
        goto LABEL_15;
      if ( !WinHttpReadData(*(HINTERNET *)(a1 + 176), lpBuffer, dwNumberOfBytesToRead, &dwNumberOfBytesRead) )
        break;
      v7 = dwNumberOfBytesRead;
      *(_DWORD *)(v5 + 72) += dwNumberOfBytesRead;
      *(_DWORD *)(v5 + 32) += v7;
      if ( dwNumberOfBytesRead )
      {
        v3 += dwNumberOfBytesRead;
        if ( v3 < v13 )
          continue;
      }
      goto LABEL_11;
    }
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_15;
  }
LABEL_11:
  v2 = sub_18018C010(v5, v12, 0);
  if ( v2 < 0 )
  {
LABEL_15:
    sub_180015A80(&v10, 0);
    v5 = v10;
    goto LABEL_16;
  }
  v2 = 0;
LABEL_16:
  sub_180015A80(a1 + 72, v5);
  sub_180015A80(&v10, 0);
  sub_180019E20(&v10);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18015ffbc  push    rbp
0x18015ffbe  push    rbx
0x18015ffbf  push    rsi
0x18015ffc0  push    rdi
0x18015ffc1  push    r14
0x18015ffc3  mov     rbp, rsp
0x18015ffc6  sub     rsp, 50h
0x18015ffca  mov     rsi, rcx
0x18015ffcd  mov     [rbp+arg_0], 0
0x18015ffd4  lea     rcx, [rbp+var_20]
0x18015ffd8  mov     [rbp+lpBuffer], 0
0x18015ffe0  mov     [rbp+var_20], 0
0x18015ffe8  mov     [rbp+var_10], 0
0x18015fff0  call    sub_180051A34
0x18015fff5  mov     ebx, eax
0x18015fff7  test    eax, eax
0x18015fff9  js      loc_1801600F0
0x18015ffff  lea     rdx, [rbp+arg_0]
0x180160003  mov     rcx, rsi
0x180160006  xor     r14d, r14d
0x180160009  call    sub_18015FB7C
0x18016000e  test    eax, eax
0x180160010  jnz     short loc_18016001A
0x180160012  or      eax, 0FFFFFFFFh
0x180160015  mov     [rbp+arg_0], eax
0x180160018  jmp     short loc_18016001D
0x18016001a  mov     eax, [rbp+arg_0]
0x18016001d  mov     rdi, [rbp+var_20]
0x180160021  test    eax, eax
0x180160023  jz      loc_1801600B2
0x180160029  mov     rcx, [rsi+0B0h]; hRequest
0x180160030  lea     rdx, [rbp+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x180160034  mov     [rbp+dwNumberOfBytesAvailable], 0
0x18016003b  mov     [rbp+dwNumberOfBytesRead], 0
0x180160042  mov     [rbp+dwNumberOfBytesToRead], 0
0x180160049  call    cs:WinHttpQueryDataAvailable
0x180160050  nop     dword ptr [rax+rax+00h]
0x180160055  test    eax, eax
0x180160057  jz      short loc_1801600D5
0x180160059  mov     edx, [rbp+dwNumberOfBytesAvailable]
0x18016005c  lea     r9, [rbp+dwNumberOfBytesToRead]
0x180160060  lea     r8, [rbp+lpBuffer]
0x180160064  mov     rcx, rdi
0x180160067  call    sub_180155C24
0x18016006c  mov     ebx, eax
0x18016006e  test    eax, eax
0x180160070  js      short loc_1801600F0
0x180160072  mov     r8d, [rbp+dwNumberOfBytesToRead]; dwNumberOfBytesToRead
0x180160076  lea     r9, [rbp+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x18016007a  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x18016007e  mov     rcx, [rsi+0B0h]; hRequest
0x180160085  call    cs:WinHttpReadData
0x18016008c  nop     dword ptr [rax+rax+00h]
0x180160091  test    eax, eax
0x180160093  jz      short loc_1801600D5
0x180160095  mov     eax, [rbp+dwNumberOfBytesRead]
0x180160098  add     [rdi+48h], eax
0x18016009b  add     [rdi+20h], eax
0x18016009e  mov     eax, [rbp+dwNumberOfBytesRead]
0x1801600a1  test    eax, eax
0x1801600a3  jz      short loc_1801600B2
0x1801600a5  add     r14d, eax
0x1801600a8  cmp     r14d, [rbp+arg_0]
0x1801600ac  jb      loc_180160029
0x1801600b2  mov     rax, [rdi]
0x1801600b5  xor     r9d, r9d
0x1801600b8  mov     rdx, [rbp+var_10]
0x1801600bc  xor     r8d, r8d
0x1801600bf  mov     rcx, rdi
0x1801600c2  mov     rax, [rax+28h]
0x1801600c6  call    sub_18018C010
0x1801600cb  mov     ebx, eax
0x1801600cd  test    eax, eax
0x1801600cf  js      short loc_1801600F0
0x1801600d1  xor     ebx, ebx
0x1801600d3  jmp     short loc_1801600FF
0x1801600d5  call    cs:GetLastError
0x1801600dc  nop     dword ptr [rax+rax+00h]
0x1801600e1  mov     ebx, eax
0x1801600e3  test    eax, eax
0x1801600e5  jle     short loc_1801600F0
0x1801600e7  movzx   ebx, ax
0x1801600ea  or      ebx, 80070000h
0x1801600f0  xor     edx, edx
0x1801600f2  lea     rcx, [rbp+var_20]
0x1801600f6  call    sub_180015A80
0x1801600fb  mov     rdi, [rbp+var_20]
0x1801600ff  lea     rcx, [rsi+48h]
0x180160103  mov     rdx, rdi
0x180160106  call    sub_180015A80
0x18016010b  xor     edx, edx
0x18016010d  lea     rcx, [rbp+var_20]
0x180160111  call    sub_180015A80
0x180160116  lea     rcx, [rbp+var_20]
0x18016011a  call    sub_180019E20
0x18016011f  mov     eax, ebx
0x180160121  add     rsp, 50h
0x180160125  pop     r14
0x180160127  pop     rdi
0x180160128  pop     rsi
0x180160129  pop     rbx
0x18016012a  pop     rbp
0x18016012b  retn
```
