# AeComputeFileHash

- ea: `0x180063f60`
- end: `0x1800640ae`
- name: `AeComputeFileHash`
- size: `334`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015768`
- `0x180049694`
- `0x18005d170`
- `0x1800795e0`

## callees

- `0x180063f60`
- `0x1800640b4`
- `0x180065d9c`
- `0x180065e7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063fb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063fb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064059`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064059`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180063faa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180063faa`

## string_xrefs

- `0x180063fe6`: `AeComputeFileHash`
- `0x18006403a`: `AeComputeFileHash`
- `0x18006407e`: `AeComputeFileHash`

## pseudocode

```c
__int64 __fastcall AeComputeFileHash(const WCHAR *a1, __int64 a2, int a3)
{
  char *FileW; // rax
  int v6; // r8d
  char *v7; // rsi
  int LastError; // ebx
  int v9; // r8d
  int v10; // r8d

  if ( a1 && a2 )
  {
    FileW = (char *)CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v7 = FileW;
    if ( FileW == (char *)-1LL )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sdS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          v9,
          (unsigned int)"AeComputeFileHash",
          LastError,
          (__int64)a1);
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = AeComputeFileHashFromHandle(FileW, a2, v6);
      if ( LastError >= 0 )
      {
        LastError = 0;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, v10, (unsigned int)"AeComputeFileHash", LastError);
      }
      CloseHandle(v7);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, a3, (unsigned int)"AeComputeFileHash", 211);
    return (unsigned int)-2147024809;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180063f60  mov     rax, rsp
0x180063f63  mov     [rax+8], rbx
0x180063f67  mov     [rax+10h], rsi
0x180063f6b  push    rdi
0x180063f6c  sub     rsp, 40h
0x180063f70  mov     rbx, rdx
0x180063f73  mov     rdi, rcx
0x180063f76  test    rcx, rcx
0x180063f79  jz      loc_180064061
0x180063f7f  test    rdx, rdx
0x180063f82  jz      loc_180064061
0x180063f88  mov     qword ptr [rax-18h], 0
0x180063f90  xor     r9d, r9d; lpSecurityAttributes
0x180063f93  mov     dword ptr [rax-20h], 80h
0x180063f9a  mov     edx, 80000000h; dwDesiredAccess
0x180063f9f  mov     dword ptr [rax-28h], 3
0x180063fa6  lea     r8d, [r9+1]; dwShareMode
0x180063faa  call    cs:__imp_CreateFileW
0x180063fb0  mov     rsi, rax
0x180063fb3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180063fb7  jnz     short loc_18006400C
0x180063fb9  call    cs:__imp_GetLastError
0x180063fbf  mov     ebx, eax
0x180063fc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180063fc8  lea     rax, WPP_GLOBAL_Control
0x180063fcf  cmp     rcx, rax
0x180063fd2  jz      short loc_180063FF6
0x180063fd4  test    byte ptr [rcx+1Ch], 1
0x180063fd8  jz      short loc_180063FF6
0x180063fda  mov     rcx, [rcx+10h]
0x180063fde  lea     edx, [rsi+16h]
0x180063fe1  mov     [rsp+48h+var_20], rdi
0x180063fe6  lea     r9, aAecomputefileh_0; "AeComputeFileHash"
0x180063fed  mov     [rsp+48h+var_28], ebx
0x180063ff1  call    WPP_SF_sdS
0x180063ff6  test    ebx, ebx
0x180063ff8  jle     loc_18006409C
0x180063ffe  movzx   ebx, bx
0x180064001  or      ebx, 80070000h
0x180064007  jmp     loc_18006409C
0x18006400c  mov     rdx, rbx
0x18006400f  mov     rcx, rsi; hFile
0x180064012  call    AeComputeFileHashFromHandle
0x180064017  mov     ebx, eax
0x180064019  test    eax, eax
0x18006401b  jns     short loc_180064054
0x18006401d  mov     rcx, cs:WPP_GLOBAL_Control
0x180064024  lea     rax, WPP_GLOBAL_Control
0x18006402b  cmp     rcx, rax
0x18006402e  jz      short loc_180064056
0x180064030  test    byte ptr [rcx+1Ch], 1
0x180064034  jz      short loc_180064056
0x180064036  mov     rcx, [rcx+10h]
0x18006403a  lea     r9, aAecomputefileh_0; "AeComputeFileHash"
0x180064041  movzx   eax, bx
0x180064044  mov     edx, 16h
0x180064049  mov     [rsp+48h+var_28], eax
0x18006404d  call    WPP_SF_sd
0x180064052  jmp     short loc_180064056
0x180064054  xor     ebx, ebx
0x180064056  mov     rcx, rsi; hObject
0x180064059  call    cs:__imp_CloseHandle
0x18006405f  jmp     short loc_18006409C
0x180064061  mov     rcx, cs:WPP_GLOBAL_Control
0x180064068  lea     rax, WPP_GLOBAL_Control
0x18006406f  cmp     rcx, rax
0x180064072  jz      short loc_180064097
0x180064074  test    byte ptr [rcx+1Ch], 1
0x180064078  jz      short loc_180064097
0x18006407a  mov     rcx, [rcx+10h]
0x18006407e  lea     r9, aAecomputefileh_0; "AeComputeFileHash"
0x180064085  mov     edx, 14h
0x18006408a  mov     [rsp+48h+var_28], 1D3h
0x180064092  call    WPP_SF_sd
0x180064097  mov     ebx, 80070057h
0x18006409c  mov     rsi, [rsp+48h+arg_8]
0x1800640a1  mov     eax, ebx
0x1800640a3  mov     rbx, [rsp+48h+arg_0]
0x1800640a8  add     rsp, 40h
0x1800640ac  pop     rdi
0x1800640ad  retn
```
