# extmatch(ushort const *,ushort const *)

- ea: `0x180009790`
- end: `0x180009823`
- name: `?extmatch@@YAHPEBG0@Z`
- size: `147`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800032a8`
- `0x1800091a0`
- `0x180011cf4`
- `0x1800130f4`
- `0x1800186b0`
- `0x180019280`
- `0x18001b03c`
- `0x1801ac7d0`
- `0x1801adb90`
- `0x1801ae840`

## callees

- `0x180009790`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800097f7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800097f7`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800097e9`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800097e9`

## pseudocode

```c
_BOOL8 __fastcall extmatch(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  wchar_t Ext[264]; // [rsp+50h] [rbp-228h] BYREF

  if ( !a1 )
    return 0;
  _wsplitpath_s(a1, 0, 0, 0, 0, 0, 0, Ext, 0x101u);
  return (unsigned int)_o__wcsicmp(Ext, a2) == 0;
}

```

## disassembly

```asm
0x180009790  push    rbx
0x180009792  sub     rsp, 270h
0x180009799  mov     rax, cs:__security_cookie
0x1800097a0  xor     rax, rsp
0x1800097a3  mov     [rsp+278h+var_18], rax
0x1800097ab  mov     rbx, rdx
0x1800097ae  test    rcx, rcx
0x1800097b1  jz      short loc_18000981F
0x1800097b3  mov     [rsp+278h+ExtCount], 101h; ExtCount
0x1800097bc  lea     rax, [rsp+278h+var_228]
0x1800097c1  mov     [rsp+278h+Ext], rax; Ext
0x1800097c6  xor     r9d, r9d; Dir
0x1800097c9  mov     [rsp+278h+FilenameCount], 0; FilenameCount
0x1800097d2  xor     r8d, r8d; DriveCount
0x1800097d5  mov     [rsp+278h+Filename], 0; Filename
0x1800097de  xor     edx, edx; Drive
0x1800097e0  mov     [rsp+278h+DirCount], 0; DirCount
0x1800097e9  call    cs:__imp__wsplitpath_s
0x1800097ef  mov     rdx, rbx
0x1800097f2  lea     rcx, [rsp+278h+var_228]
0x1800097f7  call    cs:__imp__o__wcsicmp
0x1800097fd  xor     ecx, ecx
0x1800097ff  test    eax, eax
0x180009801  setz    cl
0x180009804  mov     eax, ecx
0x180009806  mov     rcx, [rsp+278h+var_18]
0x18000980e  xor     rcx, rsp; StackCookie
0x180009811  call    __security_check_cookie
0x180009816  add     rsp, 270h
0x18000981d  pop     rbx
0x18000981e  retn
0x18000981f  xor     eax, eax
0x180009821  jmp     short loc_180009806
```
