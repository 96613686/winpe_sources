# CUtils::GetComputerNameW(ushort *,ulong *)

- ea: `0x18007ef08`
- end: `0x18007efcb`
- name: `?GetComputerNameW@CUtils@@SAJPEAGPEAK@Z`
- size: `195`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003d93c`

## callees

- `0x1800074c0`
- `0x18001aa50`
- `0x18007ef08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ef39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ef39`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18007ef2f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x18007ef2f`

## string_xrefs

- `0x18007ef90`: `StringCchCopy failed: 0x%x in %s`
- `0x18007ef97`: `CUtils::GetComputerNameW`
- `0x18007ef58`: `GetComputerName failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUtils::GetComputerNameW(unsigned __int16 *a1, unsigned int *a2)
{
  signed int LastError; // eax
  unsigned int v3; // ebx

  if ( dword_1800DA46C < 0 )
  {
    nSize = 16;
    if ( GetComputerNameW(&Buffer, &nSize) )
    {
      ++nSize;
      dword_1800DA46C = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      dword_1800DA46C = v3;
      if ( (v3 & 0x80000000) != 0 )
      {
        _DbgPrintMessage(8, "GetComputerName failed: 0x%x in %s", v3, "CUtils::GetComputerNameW");
        goto LABEL_10;
      }
    }
  }
  v3 = StringCchCopyW(&word_1800DDA48, (unsigned int)dword_1800DDA68, &Buffer);
  if ( (v3 & 0x80000000) == 0 )
  {
    LODWORD(dword_1800DDA68) = nSize;
    return v3;
  }
  _DbgPrintMessage(8, "StringCchCopy failed: 0x%x in %s", v3, "CUtils::GetComputerNameW");
LABEL_10:
  LODWORD(dword_1800DDA68) = 0;
  return v3;
}

```

## disassembly

```asm
0x18007ef08  push    rbx
0x18007ef0a  sub     rsp, 20h
0x18007ef0e  cmp     cs:dword_1800DA46C, 0
0x18007ef15  jge     short loc_18007EF71
0x18007ef17  lea     rdx, nSize; nSize
0x18007ef1e  mov     cs:nSize, 10h
0x18007ef28  lea     rcx, Buffer; lpBuffer
0x18007ef2f  call    cs:__imp_GetComputerNameW
0x18007ef35  test    eax, eax
0x18007ef37  jnz     short loc_18007EF61
0x18007ef39  call    cs:__imp_GetLastError
0x18007ef3f  mov     ebx, eax
0x18007ef41  test    eax, eax
0x18007ef43  jle     short loc_18007EF4E
0x18007ef45  movzx   ebx, ax
0x18007ef48  or      ebx, 80070000h
0x18007ef4e  mov     cs:dword_1800DA46C, ebx
0x18007ef54  test    ebx, ebx
0x18007ef56  jns     short loc_18007EF71
0x18007ef58  lea     rdx, aGetcomputernam; "GetComputerName failed: 0x%x in %s"
0x18007ef5f  jmp     short loc_18007EF97
0x18007ef61  inc     cs:nSize
0x18007ef67  mov     cs:dword_1800DA46C, 0
0x18007ef71  mov     edx, cs:dword_1800DDA68; unsigned __int64
0x18007ef77  lea     r8, Buffer; unsigned __int16 *
0x18007ef7e  lea     rcx, word_1800DDA48; unsigned __int16 *
0x18007ef85  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007ef8a  mov     ebx, eax
0x18007ef8c  test    eax, eax
0x18007ef8e  jns     short loc_18007EFB7
0x18007ef90  lea     rdx, aStringcchcopyF; "StringCchCopy failed: 0x%x in %s"
0x18007ef97  lea     r9, aCutilsGetcompu; "CUtils::GetComputerNameW"
0x18007ef9e  mov     r8d, ebx
0x18007efa1  mov     ecx, 8; int
0x18007efa6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007efab  mov     cs:dword_1800DDA68, 0
0x18007efb5  jmp     short loc_18007EFC3
0x18007efb7  mov     eax, cs:nSize
0x18007efbd  mov     cs:dword_1800DDA68, eax
0x18007efc3  mov     eax, ebx
0x18007efc5  add     rsp, 20h
0x18007efc9  pop     rbx
0x18007efca  retn
```
