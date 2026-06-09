# LoadLibraryFromSystemDir(ushort const *,ulong)

- ea: `0x1800156a0`
- end: `0x180015779`
- name: `?LoadLibraryFromSystemDir@@YAPEAUHINSTANCE__@@PEBGK@Z`
- size: `217`
- prototype: `HINSTANCE __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180021164`

## callees

- `0x1800080ec`
- `0x1800156a0`
- `0x180030e6e`
- `0x180030ea0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001574c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001574c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156ec`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800156e0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800156e0`

## pseudocode

```c
HINSTANCE __fastcall LoadLibraryFromSystemDir(const unsigned __int16 *a1)
{
  __int64 v2; // rbx
  UINT SystemDirectoryW; // eax
  signed int LastError; // eax
  bool v5; // sf
  signed int v6; // eax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  v2 = 0;
  memset_0(Buffer, 0, 0x20Au);
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x105u);
  if ( SystemDirectoryW )
  {
    if ( Buffer[SystemDirectoryW - 1] != 92 )
    {
      if ( SystemDirectoryW + 2 > 0x105 )
        return (HINSTANCE)v2;
      Buffer[SystemDirectoryW] = 92;
      Buffer[SystemDirectoryW + 1] = 0;
    }
    v6 = StringCchCatW(Buffer, 0x105u, a1);
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_9;
    v6 = (unsigned __int16)LastError | 0x80070000;
  }
  v5 = v6 < 0;
LABEL_9:
  if ( !v5 )
    return LoadLibraryExW(Buffer, 0, 2u);
  return (HINSTANCE)v2;
}

```

## disassembly

```asm
0x1800156a0  mov     [rsp+arg_8], rbx
0x1800156a5  push    rdi
0x1800156a6  sub     rsp, 240h
0x1800156ad  mov     rax, cs:__security_cookie
0x1800156b4  xor     rax, rsp
0x1800156b7  mov     [rsp+248h+var_18], rax
0x1800156bf  mov     rdi, rcx
0x1800156c2  xor     edx, edx; Val
0x1800156c4  lea     rcx, [rsp+248h+Buffer]; void *
0x1800156c9  mov     r8d, 20Ah; Size
0x1800156cf  xor     ebx, ebx
0x1800156d1  call    memset_0
0x1800156d6  mov     edx, 105h; uSize
0x1800156db  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x1800156e0  call    cs:__imp_GetSystemDirectoryW
0x1800156e6  mov     edx, eax
0x1800156e8  test    eax, eax
0x1800156ea  jnz     short loc_180015700
0x1800156ec  call    cs:__imp_GetLastError
0x1800156f2  test    eax, eax
0x1800156f4  jle     short loc_18001573F
0x1800156f6  movzx   eax, ax
0x1800156f9  or      eax, 80070000h
0x1800156fe  jmp     short loc_18001573D
0x180015700  lea     eax, [rdx-1]
0x180015703  mov     r8d, 5Ch ; '\'
0x180015709  cmp     [rsp+rax*2+248h+Buffer], r8w
0x18001570f  jz      short loc_18001572B
0x180015711  lea     eax, [rdx+2]
0x180015714  cmp     eax, 105h
0x180015719  ja      short loc_180015755
0x18001571b  lea     ecx, [rdx+1]
0x18001571e  mov     [rsp+rdx*2+248h+Buffer], r8w
0x180015724  xor     eax, eax
0x180015726  mov     [rsp+rcx*2+248h+Buffer], ax
0x18001572b  mov     r8, rdi; unsigned __int16 *
0x18001572e  lea     rcx, [rsp+248h+Buffer]; unsigned __int16 *
0x180015733  mov     edx, 105h; unsigned __int64
0x180015738  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001573d  test    eax, eax
0x18001573f  js      short loc_180015755
0x180015741  xor     edx, edx; hFile
0x180015743  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x180015748  lea     r8d, [rdx+2]; dwFlags
0x18001574c  call    cs:__imp_LoadLibraryExW
0x180015752  mov     rbx, rax
0x180015755  mov     rax, rbx
0x180015758  mov     rcx, [rsp+248h+var_18]
0x180015760  xor     rcx, rsp; StackCookie
0x180015763  call    __security_check_cookie
0x180015768  mov     rbx, [rsp+248h+arg_8]
0x180015770  add     rsp, 240h
0x180015777  pop     rdi
0x180015778  retn
```
