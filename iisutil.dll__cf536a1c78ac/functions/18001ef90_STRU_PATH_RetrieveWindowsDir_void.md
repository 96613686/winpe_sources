# STRU_PATH::RetrieveWindowsDir(void)

- ea: `0x18001ef90`
- end: `0x18001f014`
- name: `?RetrieveWindowsDir@STRU_PATH@@QEAAJXZ`
- size: `132`
- prototype: `__int64 __fastcall(STRU_PATH *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180011b40`
- `0x180012ca0`
- `0x18001ef90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001efde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001efee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001efde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001efee`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001efb0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001efb0`

## pseudocode

```c
signed int __fastcall STRU_PATH::RetrieveWindowsDir(LPWSTR *this)
{
  signed int result; // eax
  UINT SystemWindowsDirectoryW; // eax

  result = STRA::Resize((STRA *)this, 0x208u);
  if ( result >= 0 )
  {
    SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(this[4], 0x104u);
    if ( SystemWindowsDirectoryW - 1 > 0x103 )
    {
      if ( GetLastError() )
      {
        result = GetLastError();
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
      }
      else
      {
        return -2147467259;
      }
    }
    else
    {
      return !STRU::SetLen((STRU *)this, SystemWindowsDirectoryW) ? 0x8007000E : 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001ef90  push    rbx
0x18001ef92  sub     rsp, 20h
0x18001ef96  mov     edx, 208h; unsigned int
0x18001ef9b  mov     rbx, rcx
0x18001ef9e  call    ?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x18001efa3  test    eax, eax
0x18001efa5  js      short loc_18001F00D
0x18001efa7  mov     rcx, [rbx+20h]; lpBuffer
0x18001efab  mov     edx, 104h; uSize
0x18001efb0  call    cs:__imp_GetSystemWindowsDirectoryW
0x18001efb7  nop     dword ptr [rax+rax+00h]
0x18001efbc  lea     edx, [rax-1]
0x18001efbf  cmp     edx, 103h
0x18001efc5  ja      short loc_18001EFDE
0x18001efc7  mov     edx, eax; unsigned int
0x18001efc9  mov     rcx, rbx; this
0x18001efcc  call    ?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18001efd1  neg     al
0x18001efd3  sbb     eax, eax
0x18001efd5  not     eax
0x18001efd7  and     eax, 8007000Eh
0x18001efdc  jmp     short loc_18001F00D
0x18001efde  call    cs:__imp_GetLastError
0x18001efe5  nop     dword ptr [rax+rax+00h]
0x18001efea  test    eax, eax
0x18001efec  jz      short loc_18001F008
0x18001efee  call    cs:__imp_GetLastError
0x18001eff5  nop     dword ptr [rax+rax+00h]
0x18001effa  test    eax, eax
0x18001effc  jle     short loc_18001F00D
0x18001effe  movzx   eax, ax
0x18001f001  or      eax, 80070000h
0x18001f006  jmp     short loc_18001F00D
0x18001f008  mov     eax, 80004005h
0x18001f00d  add     rsp, 20h
0x18001f011  pop     rbx
0x18001f012  retn
```
