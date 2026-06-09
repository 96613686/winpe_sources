# CreateTempDir(char *,ulong)

- ea: `0x1400096b4`
- end: `0x140009730`
- name: `?CreateTempDir@@YAJPEADK@Z`
- size: `124`
- prototype: `__int64 __fastcall(char *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140004738`
- `0x140004aa0`

## callees

- `0x1400096b4`
- `0x14000a798`
- `0x1400109c0`

## import_xrefs

- `KERNEL32!GetTempPath2A` at `0x1400096df`
- `KERNEL32!GetTempPath2A` at `0x1400096df`
- `KERNEL32!GetLastError` at `0x1400096fe`
- `KERNEL32!GetLastError` at `0x1400096fe`

## pseudocode

```c
signed int __fastcall CreateTempDir(char *a1)
{
  signed int result; // eax
  CHAR TemplateDirectory[272]; // [rsp+20h] [rbp-128h] BYREF

  *a1 = 0;
  if ( (unsigned int)GetTempPath2A(260, TemplateDirectory) )
    return MakeUniqueTempDirectory(TemplateDirectory, a1);
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1400096b4  push    rbx
0x1400096b6  sub     rsp, 140h
0x1400096bd  mov     rax, cs:__security_cookie
0x1400096c4  xor     rax, rsp
0x1400096c7  mov     [rsp+148h+var_18], rax
0x1400096cf  mov     rbx, rcx
0x1400096d2  mov     byte ptr [rcx], 0
0x1400096d5  mov     ecx, 104h
0x1400096da  lea     rdx, [rsp+148h+TemplateDirectory]
0x1400096df  call    cs:__imp_GetTempPath2A
0x1400096e6  nop     dword ptr [rax+rax+00h]
0x1400096eb  test    eax, eax
0x1400096ed  jz      short loc_1400096FE
0x1400096ef  mov     rdx, rbx; char *
0x1400096f2  lea     rcx, [rsp+148h+TemplateDirectory]; lpTemplateDirectory
0x1400096f7  call    ?MakeUniqueTempDirectory@@YAJPEBDPEADK@Z; MakeUniqueTempDirectory(char const *,char *,ulong)
0x1400096fc  jmp     short loc_140009716
0x1400096fe  call    cs:__imp_GetLastError
0x140009705  nop     dword ptr [rax+rax+00h]
0x14000970a  test    eax, eax
0x14000970c  jle     short loc_140009716
0x14000970e  movzx   eax, ax
0x140009711  or      eax, 80070000h
0x140009716  mov     rcx, [rsp+148h+var_18]
0x14000971e  xor     rcx, rsp; StackCookie
0x140009721  call    __security_check_cookie
0x140009726  add     rsp, 140h
0x14000972d  pop     rbx
0x14000972e  retn
```
