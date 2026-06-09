# STRU_PATH::RetrieveSystemDir(void)

- ea: `0x18001dd20`
- end: `0x18001dd91`
- name: `?RetrieveSystemDir@STRU_PATH@@QEAAJXZ`
- size: `113`
- prototype: `__int64 __fastcall(STRU_PATH *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180010910`
- `0x180012430`
- `0x18001dd20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd72`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001dd40`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18001dd40`

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
0x18001dd20  push    rbx
0x18001dd22  sub     rsp, 20h
0x18001dd26  mov     edx, 208h; unsigned int
0x18001dd2b  mov     rbx, rcx
0x18001dd2e  call    ?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x18001dd33  test    eax, eax
0x18001dd35  js      short loc_18001DD8B
0x18001dd37  mov     rcx, [rbx+20h]; lpBuffer
0x18001dd3b  mov     edx, 104h; uSize
0x18001dd40  call    cs:__imp_GetSystemDirectoryW
0x18001dd46  lea     edx, [rax-1]
0x18001dd49  cmp     edx, 103h
0x18001dd4f  ja      short loc_18001DD68
0x18001dd51  mov     edx, eax; unsigned int
0x18001dd53  mov     rcx, rbx; this
0x18001dd56  call    ?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18001dd5b  neg     al
0x18001dd5d  sbb     eax, eax
0x18001dd5f  not     eax
0x18001dd61  and     eax, 8007000Eh
0x18001dd66  jmp     short loc_18001DD8B
0x18001dd68  call    cs:__imp_GetLastError
0x18001dd6e  test    eax, eax
0x18001dd70  jz      short loc_18001DD86
0x18001dd72  call    cs:__imp_GetLastError
0x18001dd78  test    eax, eax
0x18001dd7a  jle     short loc_18001DD8B
0x18001dd7c  movzx   eax, ax
0x18001dd7f  or      eax, 80070000h
0x18001dd84  jmp     short loc_18001DD8B
0x18001dd86  mov     eax, 80004005h
0x18001dd8b  add     rsp, 20h
0x18001dd8f  pop     rbx
0x18001dd90  retn
```
