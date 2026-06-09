# STRU_PATH::RetrieveSystemDir(void)

- ea: `0x18001ee70`
- end: `0x18001eef4`
- name: `?RetrieveSystemDir@STRU_PATH@@QEAAJXZ`
- size: `132`
- prototype: `__int64 __fastcall(STRU_PATH *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180011b40`
- `0x180012ca0`
- `0x18001ee70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eebe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eebe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001eece`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001ee90`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001ee90`

## pseudocode

```c
signed int __fastcall STRU_PATH::RetrieveSystemDir(LPWSTR *this)
{
  signed int result; // eax
  UINT SystemDirectoryW; // eax

  result = STRA::Resize((STRA *)this, 0x208u);
  if ( result >= 0 )
  {
    SystemDirectoryW = GetSystemDirectoryW(this[4], 0x104u);
    if ( SystemDirectoryW - 1 > 0x103 )
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
      return !STRU::SetLen((STRU *)this, SystemDirectoryW) ? 0x8007000E : 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001ee70  push    rbx
0x18001ee72  sub     rsp, 20h
0x18001ee76  mov     edx, 208h; unsigned int
0x18001ee7b  mov     rbx, rcx
0x18001ee7e  call    ?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x18001ee83  test    eax, eax
0x18001ee85  js      short loc_18001EEED
0x18001ee87  mov     rcx, [rbx+20h]; lpBuffer
0x18001ee8b  mov     edx, 104h; uSize
0x18001ee90  call    cs:__imp_GetSystemDirectoryW
0x18001ee97  nop     dword ptr [rax+rax+00h]
0x18001ee9c  lea     edx, [rax-1]
0x18001ee9f  cmp     edx, 103h
0x18001eea5  ja      short loc_18001EEBE
0x18001eea7  mov     edx, eax; unsigned int
0x18001eea9  mov     rcx, rbx; this
0x18001eeac  call    ?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18001eeb1  neg     al
0x18001eeb3  sbb     eax, eax
0x18001eeb5  not     eax
0x18001eeb7  and     eax, 8007000Eh
0x18001eebc  jmp     short loc_18001EEED
0x18001eebe  call    cs:__imp_GetLastError
0x18001eec5  nop     dword ptr [rax+rax+00h]
0x18001eeca  test    eax, eax
0x18001eecc  jz      short loc_18001EEE8
0x18001eece  call    cs:__imp_GetLastError
0x18001eed5  nop     dword ptr [rax+rax+00h]
0x18001eeda  test    eax, eax
0x18001eedc  jle     short loc_18001EEED
0x18001eede  movzx   eax, ax
0x18001eee1  or      eax, 80070000h
0x18001eee6  jmp     short loc_18001EEED
0x18001eee8  mov     eax, 80004005h
0x18001eeed  add     rsp, 20h
0x18001eef1  pop     rbx
0x18001eef2  retn
```
