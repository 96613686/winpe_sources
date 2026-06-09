# STRU_PATH::RetrieveWindowsDir(void)

- ea: `0x18001de20`
- end: `0x18001de91`
- name: `?RetrieveWindowsDir@STRU_PATH@@QEAAJXZ`
- size: `113`
- prototype: `__int64 __fastcall(STRU_PATH *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180010910`
- `0x180012430`
- `0x18001de20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001de72`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001de40`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18001de40`

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
0x18001de20  push    rbx
0x18001de22  sub     rsp, 20h
0x18001de26  mov     edx, 208h; unsigned int
0x18001de2b  mov     rbx, rcx
0x18001de2e  call    ?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x18001de33  test    eax, eax
0x18001de35  js      short loc_18001DE8B
0x18001de37  mov     rcx, [rbx+20h]; lpBuffer
0x18001de3b  mov     edx, 104h; uSize
0x18001de40  call    cs:__imp_GetSystemWindowsDirectoryW
0x18001de46  lea     edx, [rax-1]
0x18001de49  cmp     edx, 103h
0x18001de4f  ja      short loc_18001DE68
0x18001de51  mov     edx, eax; unsigned int
0x18001de53  mov     rcx, rbx; this
0x18001de56  call    ?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18001de5b  neg     al
0x18001de5d  sbb     eax, eax
0x18001de5f  not     eax
0x18001de61  and     eax, 8007000Eh
0x18001de66  jmp     short loc_18001DE8B
0x18001de68  call    cs:__imp_GetLastError
0x18001de6e  test    eax, eax
0x18001de70  jz      short loc_18001DE86
0x18001de72  call    cs:__imp_GetLastError
0x18001de78  test    eax, eax
0x18001de7a  jle     short loc_18001DE8B
0x18001de7c  movzx   eax, ax
0x18001de7f  or      eax, 80070000h
0x18001de84  jmp     short loc_18001DE8B
0x18001de86  mov     eax, 80004005h
0x18001de8b  add     rsp, 20h
0x18001de8f  pop     rbx
0x18001de90  retn
```
