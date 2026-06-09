# ParseForDrive(ushort const *,ushort *,unsigned __int64)

- ea: `0x1400083c8`
- end: `0x1400084c6`
- name: `?ParseForDrive@@YAHPEBGPEAG_K@Z`
- size: `254`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140009d34`

## callees

- `0x1400029a0`
- `0x140005fa0`
- `0x1400083c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x140008455`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x140008484`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x140008455`
- `api-ms-win-crt-private-l1-1-0!_o_toupper` at `0x140008484`
- `SHLWAPI!PathStripToRootW` at `0x140008410`
- `SHLWAPI!PathStripToRootW` at `0x140008410`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x140008401`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x140008401`

## pseudocode

```c
__int64 __fastcall ParseForDrive(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  BOOL v4; // eax
  WCHAR *v5; // r8
  __int64 result; // rax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  *a2 = 0;
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) || (v4 = PathStripToRootW(Buffer), v5 = Buffer, !v4) )
    v5 = (WCHAR *)L"C:\\";
  StringCchCopyW(a2, 4u, v5);
  while ( *a1 )
  {
    if ( ((*a1 - 45) & 0xFFFD) == 0 )
    {
      if ( *++a1 )
      {
        if ( toupper(*a1) == 68 )
        {
          do
            ++a1;
          while ( *a1 == 32 );
          if ( *a1 )
          {
            *a2 = toupper(*a1);
            result = 1;
            *(_DWORD *)(a2 + 1) = 6029370;
            a2[3] = 0;
            return result;
          }
        }
      }
    }
    ++a1;
  }
  return 0;
}

```

## disassembly

```asm
0x1400083c8  mov     [rsp+arg_10], rbx
0x1400083cd  mov     [rsp+arg_18], rsi
0x1400083d2  push    rdi
0x1400083d3  sub     rsp, 240h
0x1400083da  mov     rax, cs:__security_cookie
0x1400083e1  xor     rax, rsp
0x1400083e4  mov     [rsp+248h+var_18], rax
0x1400083ec  mov     rdi, rdx
0x1400083ef  mov     rbx, rcx
0x1400083f2  xor     esi, esi
0x1400083f4  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x1400083f9  mov     [rdx], si
0x1400083fc  mov     edx, 104h; uSize
0x140008401  call    cs:__imp_GetWindowsDirectoryW
0x140008407  test    eax, eax
0x140008409  jz      short loc_14000841F
0x14000840b  lea     rcx, [rsp+248h+Buffer]; pszPath
0x140008410  call    cs:__imp_PathStripToRootW
0x140008416  lea     r8, [rsp+248h+Buffer]
0x14000841b  test    eax, eax
0x14000841d  jnz     short loc_140008426
0x14000841f  lea     r8, aC; "C:\\"
0x140008426  mov     edx, 4; unsigned __int64
0x14000842b  mov     rcx, rdi; unsigned __int16 *
0x14000842e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140008433  movzx   eax, word ptr [rbx]
0x140008436  test    ax, ax
0x140008439  jz      short loc_14000849F
0x14000843b  sub     ax, 2Dh ; '-'
0x14000843f  mov     ecx, 0FFFDh
0x140008444  test    cx, ax
0x140008447  jnz     short loc_14000847C
0x140008449  add     rbx, 2
0x14000844d  cmp     [rbx], si
0x140008450  jz      short loc_14000847C
0x140008452  movzx   ecx, word ptr [rbx]; C
0x140008455  call    cs:__imp_toupper
0x14000845b  cmp     eax, 44h ; 'D'
0x14000845e  jnz     short loc_14000847C
0x140008460  jmp     short loc_140008468
0x140008462  cmp     ax, 20h ; ' '
0x140008466  jnz     short loc_140008474
0x140008468  add     rbx, 2
0x14000846c  movzx   eax, word ptr [rbx]
0x14000846f  test    ax, ax
0x140008472  jnz     short loc_140008462
0x140008474  movzx   eax, word ptr [rbx]
0x140008477  test    ax, ax
0x14000847a  jnz     short loc_140008482
0x14000847c  add     rbx, 2
0x140008480  jmp     short loc_140008433
0x140008482  mov     ecx, eax; C
0x140008484  call    cs:__imp_toupper
0x14000848a  mov     [rdi], ax
0x14000848d  mov     eax, 1
0x140008492  mov     dword ptr [rdi+2], 5C003Ah
0x140008499  mov     [rdi+6], si
0x14000849d  jmp     short loc_1400084A1
0x14000849f  xor     eax, eax
0x1400084a1  mov     rcx, [rsp+248h+var_18]
0x1400084a9  xor     rcx, rsp; StackCookie
0x1400084ac  call    __security_check_cookie
0x1400084b1  lea     r11, [rsp+248h+var_8]
0x1400084b9  mov     rbx, [r11+20h]
0x1400084bd  mov     rsi, [r11+28h]
0x1400084c1  mov     rsp, r11
0x1400084c4  pop     rdi
0x1400084c5  retn
```
