# FIsIgnorableCMEvent(_RASEVENT const *)

- ea: `0x1800206c4`
- end: `0x180020781`
- name: `?FIsIgnorableCMEvent@@YAHPEBU_RASEVENT@@@Z`
- size: `189`
- prototype: `__int64 __fastcall(const struct _RASEVENT *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180020790`

## callees

- `0x180001710`
- `0x180019200`
- `0x1800206c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180020759`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180020759`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180020743`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180020743`

## pseudocode

```c
_BOOL8 __fastcall FIsIgnorableCMEvent(const wchar_t *a1)
{
  wchar_t Filename[264]; // [rsp+50h] [rbp-228h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_d31d59df70993a9dd4981e83321196c3_Traceguids);
  _wsplitpath_s(a1 + 409, 0, 0, 0, 0, Filename, 0x104u, 0, 0);
  return (unsigned int)_o__wcsnicmp(L"_CM", Filename, 3) == 0;
}

```

## disassembly

```asm
0x1800206c4  push    rbx
0x1800206c6  sub     rsp, 270h
0x1800206cd  mov     rax, cs:__security_cookie
0x1800206d4  xor     rax, rsp
0x1800206d7  mov     [rsp+278h+var_18], rax
0x1800206df  mov     rbx, rcx
0x1800206e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800206e9  lea     rax, WPP_GLOBAL_Control
0x1800206f0  cmp     rcx, rax
0x1800206f3  jz      short loc_180020710
0x1800206f5  test    byte ptr [rcx+1Ch], 8
0x1800206f9  jz      short loc_180020710
0x1800206fb  mov     rcx, [rcx+10h]
0x1800206ff  lea     r8, WPP_d31d59df70993a9dd4981e83321196c3_Traceguids
0x180020706  mov     edx, 0Ah
0x18002070b  call    WPP_SF_
0x180020710  lea     rcx, [rbx+332h]; FullPath
0x180020717  xor     r9d, r9d; Dir
0x18002071a  xor     ebx, ebx
0x18002071c  lea     rax, [rsp+278h+var_228]
0x180020721  mov     [rsp+278h+ExtCount], rbx; ExtCount
0x180020726  xor     r8d, r8d; DriveCount
0x180020729  mov     [rsp+278h+Ext], rbx; Ext
0x18002072e  xor     edx, edx; Drive
0x180020730  mov     [rsp+278h+FilenameCount], 104h; FilenameCount
0x180020739  mov     [rsp+278h+Filename], rax; Filename
0x18002073e  mov     [rsp+278h+DirCount], rbx; DirCount
0x180020743  call    cs:__imp__wsplitpath_s
0x180020749  lea     r8d, [rbx+3]
0x18002074d  lea     rdx, [rsp+278h+var_228]
0x180020752  lea     rcx, aCm; "_CM"
0x180020759  call    cs:__imp__o__wcsnicmp
0x18002075f  test    eax, eax
0x180020761  mov     ecx, ebx
0x180020763  setz    cl
0x180020766  mov     eax, ecx
0x180020768  mov     rcx, [rsp+278h+var_18]
0x180020770  xor     rcx, rsp; StackCookie
0x180020773  call    __security_check_cookie
0x180020778  add     rsp, 270h
0x18002077f  pop     rbx
0x180020780  retn
```
