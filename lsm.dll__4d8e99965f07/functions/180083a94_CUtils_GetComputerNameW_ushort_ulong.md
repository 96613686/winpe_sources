# CUtils::GetComputerNameW(ushort *,ulong *)

- ea: `0x180083a94`
- end: `0x180083b64`
- name: `?GetComputerNameW@CUtils@@SAJPEAGPEAK@Z`
- size: `208`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180040070`

## callees

- `0x1800077a0`
- `0x180009580`
- `0x180083a94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083acb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083acb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180083abb`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180083abb`

## string_xrefs

- `0x180083b28`: `StringCchCopy failed: 0x%x in %s`
- `0x180083af0`: `GetComputerName failed: 0x%x in %s`
- `0x180083b2f`: `CUtils::GetComputerNameW`

## pseudocode

```c
__int64 __fastcall CUtils::GetComputerNameW(unsigned __int16 *a1, unsigned int *a2)
{
  signed int LastError; // eax
  unsigned int v3; // ebx

  if ( dword_1800DF46C < 0 )
  {
    nSize = 16;
    if ( GetComputerNameW(&Buffer, &nSize) )
    {
      ++nSize;
      dword_1800DF46C = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      dword_1800DF46C = v3;
      if ( (v3 & 0x80000000) != 0 )
      {
        _DbgPrintMessage(8, "GetComputerName failed: 0x%x in %s", v3, "CUtils::GetComputerNameW");
        goto LABEL_10;
      }
    }
  }
  v3 = StringCchCopyW(&word_1800E2A58, (unsigned int)dword_1800E2A78, &Buffer);
  if ( (v3 & 0x80000000) == 0 )
  {
    LODWORD(dword_1800E2A78) = nSize;
    return v3;
  }
  _DbgPrintMessage(8, "StringCchCopy failed: 0x%x in %s", v3, "CUtils::GetComputerNameW");
LABEL_10:
  LODWORD(dword_1800E2A78) = 0;
  return v3;
}

```

## disassembly

```asm
0x180083a94  push    rbx
0x180083a96  sub     rsp, 20h
0x180083a9a  cmp     cs:dword_1800DF46C, 0
0x180083aa1  jge     short loc_180083B09
0x180083aa3  lea     rdx, nSize; nSize
0x180083aaa  mov     cs:nSize, 10h
0x180083ab4  lea     rcx, Buffer; lpBuffer
0x180083abb  call    cs:__imp_GetComputerNameW
0x180083ac2  nop     dword ptr [rax+rax+00h]
0x180083ac7  test    eax, eax
0x180083ac9  jnz     short loc_180083AF9
0x180083acb  call    cs:__imp_GetLastError
0x180083ad2  nop     dword ptr [rax+rax+00h]
0x180083ad7  mov     ebx, eax
0x180083ad9  test    eax, eax
0x180083adb  jle     short loc_180083AE6
0x180083add  movzx   ebx, ax
0x180083ae0  or      ebx, 80070000h
0x180083ae6  mov     cs:dword_1800DF46C, ebx
0x180083aec  test    ebx, ebx
0x180083aee  jns     short loc_180083B09
0x180083af0  lea     rdx, aGetcomputernam; "GetComputerName failed: 0x%x in %s"
0x180083af7  jmp     short loc_180083B2F
0x180083af9  inc     cs:nSize
0x180083aff  mov     cs:dword_1800DF46C, 0
0x180083b09  mov     edx, cs:dword_1800E2A78; unsigned __int64
0x180083b0f  lea     r8, Buffer; unsigned __int16 *
0x180083b16  lea     rcx, word_1800E2A58; unsigned __int16 *
0x180083b1d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180083b22  mov     ebx, eax
0x180083b24  test    eax, eax
0x180083b26  jns     short loc_180083B4F
0x180083b28  lea     rdx, aStringcchcopyF; "StringCchCopy failed: 0x%x in %s"
0x180083b2f  lea     r9, aCutilsGetcompu; "CUtils::GetComputerNameW"
0x180083b36  mov     r8d, ebx
0x180083b39  mov     ecx, 8; int
0x180083b3e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180083b43  mov     cs:dword_1800E2A78, 0
0x180083b4d  jmp     short loc_180083B5B
0x180083b4f  mov     eax, cs:nSize
0x180083b55  mov     cs:dword_1800E2A78, eax
0x180083b5b  mov     eax, ebx
0x180083b5d  add     rsp, 20h
0x180083b61  pop     rbx
0x180083b62  retn
```
