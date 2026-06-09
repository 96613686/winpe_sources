# CRdrFileTransfer::CreateTempPath(void)

- ea: `0x140046bd0`
- end: `0x140046d55`
- name: `?CreateTempPath@CRdrFileTransfer@@IEAAJXZ`
- size: `389`
- prototype: `__int64 __fastcall(CRdrFileTransfer *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140046608`
- `0x140046784`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005750`
- `0x14000a640`
- `0x140046bd0`
- `0x140046d5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046c5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046c5d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140046cc8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140046cc8`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140046c53`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140046c53`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140046cd7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140046cd7`

## pseudocode

```c
__int64 __fastcall CRdrFileTransfer::CreateTempPath(const WCHAR *this)
{
  int v1; // ebx
  unsigned int v2; // eax
  unsigned __int16 *v3; // rsi
  signed int LastError; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  CRdrFileTransfer *v6; // rcx
  unsigned __int64 v7; // r8
  unsigned int v8; // eax
  int v10; // [rsp+28h] [rbp-10h]

  if ( *((_DWORD *)this + 12) )
  {
    v3 = (unsigned __int16 *)(this + 286);
    if ( !GetTempFileNameW(this + 26, L"_TS", 0, (LPWSTR)this + 286) )
      goto LABEL_7;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v3);
    }
    if ( DeleteFileW(v3) && CreateDirectoryW(v3, 0) )
    {
      v1 = CRdrFileTransfer::DoubleNullTerminateString(v6, v3, v7);
      if ( v1 >= 0 )
      {
        return 0;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v8 = RdpWppGetCurrentThreadActivityIdPrefix();
        v10 = v1;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          (unsigned int)WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids,
          v8,
          (__int64)"DoubleNullTerminateString failed!",
          v10);
      }
    }
    else
    {
LABEL_7:
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v1 = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v2 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids, v2);
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140046bd0  mov     [rsp+arg_0], rbx
0x140046bd5  mov     [rsp+arg_8], rsi
0x140046bda  push    rdi
0x140046bdb  sub     rsp, 30h
0x140046bdf  cmp     dword ptr [rcx+30h], 0
0x140046be3  jnz     short loc_140046C3B
0x140046be5  mov     ebx, 1
0x140046bea  mov     rax, cs:WPP_GLOBAL_Control
0x140046bf1  lea     rdi, WPP_GLOBAL_Control
0x140046bf8  cmp     rax, rdi
0x140046bfb  jz      loc_140046D43
0x140046c01  test    [rax+1Ch], bl
0x140046c04  jz      loc_140046D43
0x140046c0a  cmp     byte ptr [rax+19h], 5
0x140046c0e  jb      loc_140046D43
0x140046c14  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140046c19  mov     rcx, cs:WPP_GLOBAL_Control
0x140046c20  lea     edx, [rbx+18h]
0x140046c23  mov     r9d, eax
0x140046c26  lea     r8, WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids
0x140046c2d  mov     rcx, [rcx+10h]
0x140046c31  call    WPP_SF_d
0x140046c36  jmp     loc_140046D43
0x140046c3b  lea     rsi, [rcx+23Ch]
0x140046c42  xor     r8d, r8d; uUnique
0x140046c45  mov     r9, rsi; lpTempFileName
0x140046c48  lea     rdx, PrefixString; "_TS"
0x140046c4f  add     rcx, 34h ; '4'; lpPathName
0x140046c53  call    cs:__imp_GetTempFileNameW
0x140046c59  test    eax, eax
0x140046c5b  jnz     short loc_140046C7B
0x140046c5d  call    cs:__imp_GetLastError
0x140046c63  mov     ebx, eax
0x140046c65  test    eax, eax
0x140046c67  jle     loc_140046D43
0x140046c6d  movzx   ebx, ax
0x140046c70  or      ebx, 80070000h
0x140046c76  jmp     loc_140046D43
0x140046c7b  mov     rax, cs:WPP_GLOBAL_Control
0x140046c82  lea     rdi, WPP_GLOBAL_Control
0x140046c89  cmp     rax, rdi
0x140046c8c  jz      short loc_140046CC5
0x140046c8e  mov     ebx, 1
0x140046c93  test    [rax+1Ch], bl
0x140046c96  jz      short loc_140046CC5
0x140046c98  cmp     byte ptr [rax+19h], 5
0x140046c9c  jb      short loc_140046CC5
0x140046c9e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140046ca3  mov     rcx, cs:WPP_GLOBAL_Control
0x140046caa  lea     edx, [rbx+19h]
0x140046cad  mov     r9d, eax
0x140046cb0  mov     [rsp+38h+var_18], rsi
0x140046cb5  lea     r8, WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids
0x140046cbc  mov     rcx, [rcx+10h]
0x140046cc0  call    WPP_SF_DS
0x140046cc5  mov     rcx, rsi; lpFileName
0x140046cc8  call    cs:__imp_DeleteFileW
0x140046cce  test    eax, eax
0x140046cd0  jz      short loc_140046C5D
0x140046cd2  xor     edx, edx; lpSecurityAttributes
0x140046cd4  mov     rcx, rsi; lpPathName
0x140046cd7  call    cs:__imp_CreateDirectoryW
0x140046cdd  test    eax, eax
0x140046cdf  jz      loc_140046C5D
0x140046ce5  mov     rdx, rsi; unsigned __int16 *
0x140046ce8  call    ?DoubleNullTerminateString@CRdrFileTransfer@@IEAAJPEAG_K@Z; CRdrFileTransfer::DoubleNullTerminateString(ushort *,unsigned __int64)
0x140046ced  mov     ebx, eax
0x140046cef  test    eax, eax
0x140046cf1  jns     short loc_140046D41
0x140046cf3  mov     rax, cs:WPP_GLOBAL_Control
0x140046cfa  cmp     rax, rdi
0x140046cfd  jz      short loc_140046D43
0x140046cff  test    byte ptr [rax+1Ch], 8
0x140046d03  jz      short loc_140046D43
0x140046d05  cmp     byte ptr [rax+19h], 2
0x140046d09  jb      short loc_140046D43
0x140046d0b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140046d10  lea     rcx, aDoublenullterm; "DoubleNullTerminateString failed!"
0x140046d17  mov     [rsp+38h+var_10], ebx
0x140046d1b  mov     [rsp+38h+var_18], rcx
0x140046d20  lea     r8, WPP_aff8ace9ce173a6be6d945882be5b339_Traceguids
0x140046d27  mov     rcx, cs:WPP_GLOBAL_Control
0x140046d2e  mov     edx, 1Bh
0x140046d33  mov     r9d, eax
0x140046d36  mov     rcx, [rcx+10h]
0x140046d3a  call    WPP_SF_DsD
0x140046d3f  jmp     short loc_140046D43
0x140046d41  xor     ebx, ebx
0x140046d43  mov     rsi, [rsp+38h+arg_8]
0x140046d48  mov     eax, ebx
0x140046d4a  mov     rbx, [rsp+38h+arg_0]
0x140046d4f  add     rsp, 30h
0x140046d53  pop     rdi
0x140046d54  retn
```
