# STRU_PATH::RetrieveTempDir(void)

- ea: `0x18001dda0`
- end: `0x18001de11`
- name: `?RetrieveTempDir@STRU_PATH@@QEAAJXZ`
- size: `113`
- prototype: `__int64 __fastcall(STRU_PATH *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180010910`
- `0x180012430`
- `0x18001dda0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dde8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ddf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dde8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ddf2`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001ddc0`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001ddc0`

## pseudocode

```c
signed int __fastcall STRU_PATH::RetrieveTempDir(LPWSTR *this)
{
  signed int result; // eax
  DWORD TempPathW; // eax

  result = STRA::Resize((STRA *)this, 0x208u);
  if ( result >= 0 )
  {
    TempPathW = GetTempPathW(0x104u, this[4]);
    if ( TempPathW - 1 > 0x103 )
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
      return !STRU::SetLen((STRU *)this, TempPathW) ? 0x8007000E : 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001dda0  push    rbx
0x18001dda2  sub     rsp, 20h
0x18001dda6  mov     edx, 208h; unsigned int
0x18001ddab  mov     rbx, rcx
0x18001ddae  call    ?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x18001ddb3  test    eax, eax
0x18001ddb5  js      short loc_18001DE0B
0x18001ddb7  mov     rdx, [rbx+20h]; lpBuffer
0x18001ddbb  mov     ecx, 104h; nBufferLength
0x18001ddc0  call    cs:__imp_GetTempPathW
0x18001ddc6  lea     edx, [rax-1]
0x18001ddc9  cmp     edx, 103h
0x18001ddcf  ja      short loc_18001DDE8
0x18001ddd1  mov     edx, eax; unsigned int
0x18001ddd3  mov     rcx, rbx; this
0x18001ddd6  call    ?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18001dddb  neg     al
0x18001dddd  sbb     eax, eax
0x18001dddf  not     eax
0x18001dde1  and     eax, 8007000Eh
0x18001dde6  jmp     short loc_18001DE0B
0x18001dde8  call    cs:__imp_GetLastError
0x18001ddee  test    eax, eax
0x18001ddf0  jz      short loc_18001DE06
0x18001ddf2  call    cs:__imp_GetLastError
0x18001ddf8  test    eax, eax
0x18001ddfa  jle     short loc_18001DE0B
0x18001ddfc  movzx   eax, ax
0x18001ddff  or      eax, 80070000h
0x18001de04  jmp     short loc_18001DE0B
0x18001de06  mov     eax, 80004005h
0x18001de0b  add     rsp, 20h
0x18001de0f  pop     rbx
0x18001de10  retn
```
