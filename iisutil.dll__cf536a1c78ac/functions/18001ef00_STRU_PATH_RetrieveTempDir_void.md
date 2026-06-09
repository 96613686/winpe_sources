# STRU_PATH::RetrieveTempDir(void)

- ea: `0x18001ef00`
- end: `0x18001ef84`
- name: `?RetrieveTempDir@STRU_PATH@@QEAAJXZ`
- size: `132`
- prototype: `__int64 __fastcall(STRU_PATH *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180011b40`
- `0x180012ca0`
- `0x18001ef00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef5e`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001ef20`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18001ef20`

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
0x18001ef00  push    rbx
0x18001ef02  sub     rsp, 20h
0x18001ef06  mov     edx, 208h; unsigned int
0x18001ef0b  mov     rbx, rcx
0x18001ef0e  call    ?Resize@STRA@@QEAAJK@Z; STRA::Resize(ulong)
0x18001ef13  test    eax, eax
0x18001ef15  js      short loc_18001EF7D
0x18001ef17  mov     rdx, [rbx+20h]; lpBuffer
0x18001ef1b  mov     ecx, 104h; nBufferLength
0x18001ef20  call    cs:__imp_GetTempPathW
0x18001ef27  nop     dword ptr [rax+rax+00h]
0x18001ef2c  lea     edx, [rax-1]
0x18001ef2f  cmp     edx, 103h
0x18001ef35  ja      short loc_18001EF4E
0x18001ef37  mov     edx, eax; unsigned int
0x18001ef39  mov     rcx, rbx; this
0x18001ef3c  call    ?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18001ef41  neg     al
0x18001ef43  sbb     eax, eax
0x18001ef45  not     eax
0x18001ef47  and     eax, 8007000Eh
0x18001ef4c  jmp     short loc_18001EF7D
0x18001ef4e  call    cs:__imp_GetLastError
0x18001ef55  nop     dword ptr [rax+rax+00h]
0x18001ef5a  test    eax, eax
0x18001ef5c  jz      short loc_18001EF78
0x18001ef5e  call    cs:__imp_GetLastError
0x18001ef65  nop     dword ptr [rax+rax+00h]
0x18001ef6a  test    eax, eax
0x18001ef6c  jle     short loc_18001EF7D
0x18001ef6e  movzx   eax, ax
0x18001ef71  or      eax, 80070000h
0x18001ef76  jmp     short loc_18001EF7D
0x18001ef78  mov     eax, 80004005h
0x18001ef7d  add     rsp, 20h
0x18001ef81  pop     rbx
0x18001ef82  retn
```
