# DiagCreatePath(ushort *)

- ea: `0x14006162c`
- end: `0x1400616cb`
- name: `?DiagCreatePath@@YAJPEAG@Z`
- size: `159`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140060900`

## callees

- `0x14006162c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14006167a`
- `KERNEL32!GetLastError` at `0x14006168a`
- `KERNEL32!GetLastError` at `0x14006167a`
- `KERNEL32!GetLastError` at `0x14006168a`
- `KERNEL32!CreateDirectoryW` at `0x14006166a`
- `KERNEL32!CreateDirectoryW` at `0x14006166a`
- `msvcrt!wcschr` at `0x14006164c`
- `msvcrt!wcschr` at `0x14006164c`

## pseudocode

```c
__int64 __fastcall DiagCreatePath(LPCWSTR lpPathName)
{
  WCHAR *v2; // rbx
  wchar_t *v3; // rax
  unsigned int v4; // ecx
  signed int LastError; // eax

  v2 = (WCHAR *)(lpPathName + 3);
  while ( 1 )
  {
    v3 = wcschr(v2 + 1, 0x5Cu);
    v4 = 0;
    v2 = v3;
    if ( !v3 )
      break;
    *v3 = 0;
    if ( CreateDirectoryW(lpPathName, 0) || !GetLastError() )
    {
      *v2 = 92;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      *v2 = 92;
      if ( ((v4 + 0x80000000) & 0x80000000) == 0 && v4 != -2147024713 )
        return v4;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14006162c  push    rbx
0x14006162e  push    rbp
0x14006162f  push    rsi
0x140061630  push    rdi
0x140061631  sub     rsp, 28h
0x140061635  mov     rdi, rcx
0x140061638  lea     rbx, [rcx+6]
0x14006163c  mov     esi, 5Ch ; '\'
0x140061641  mov     ebp, 80000000h
0x140061646  mov     edx, esi; Ch
0x140061648  lea     rcx, [rbx+2]; Str
0x14006164c  call    cs:__imp_wcschr
0x140061653  nop     dword ptr [rax+rax+00h]
0x140061658  xor     ecx, ecx
0x14006165a  mov     rbx, rax
0x14006165d  test    rax, rax
0x140061660  jz      short loc_1400616B7
0x140061662  mov     [rax], cx
0x140061665  xor     edx, edx; lpSecurityAttributes
0x140061667  mov     rcx, rdi; lpPathName
0x14006166a  call    cs:__imp_CreateDirectoryW
0x140061671  nop     dword ptr [rax+rax+00h]
0x140061676  test    eax, eax
0x140061678  jnz     short loc_1400616C3
0x14006167a  call    cs:__imp_GetLastError
0x140061681  nop     dword ptr [rax+rax+00h]
0x140061686  test    eax, eax
0x140061688  jz      short loc_1400616C3
0x14006168a  call    cs:__imp_GetLastError
0x140061691  nop     dword ptr [rax+rax+00h]
0x140061696  mov     ecx, eax
0x140061698  test    eax, eax
0x14006169a  jle     short loc_1400616A5
0x14006169c  movzx   ecx, ax
0x14006169f  or      ecx, 80070000h
0x1400616a5  lea     eax, [rcx+rbp]
0x1400616a8  mov     [rbx], si
0x1400616ab  test    ebp, eax
0x1400616ad  jnz     short loc_140061646
0x1400616af  cmp     ecx, 800700B7h
0x1400616b5  jz      short loc_140061646
0x1400616b7  mov     eax, ecx
0x1400616b9  add     rsp, 28h
0x1400616bd  pop     rdi
0x1400616be  pop     rsi
0x1400616bf  pop     rbp
0x1400616c0  pop     rbx
0x1400616c1  retn
0x1400616c3  mov     [rbx], si
0x1400616c6  jmp     loc_140061646
```
