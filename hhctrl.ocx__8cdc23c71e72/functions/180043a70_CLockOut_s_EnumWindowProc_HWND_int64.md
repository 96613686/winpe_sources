# CLockOut::s_EnumWindowProc(HWND__ *,__int64)

- ea: `0x180043a70`
- end: `0x180043af7`
- name: `?s_EnumWindowProc@CLockOut@@CAHPEAUHWND__@@_J@Z`
- size: `135`
- prototype: `BOOL __stdcall(HWND, LPARAM)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180043a70`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x180043aa4`
- `USER32!GetWindowThreadProcessId` at `0x180043aa4`
- `USER32!IsWindowEnabled` at `0x180043a85`
- `USER32!IsWindowEnabled` at `0x180043a85`
- `USER32!EnableWindow` at `0x180043ad8`
- `USER32!EnableWindow` at `0x180043ad8`

## pseudocode

```c
__int64 __fastcall CLockOut::s_EnumWindowProc(HWND a1, __int64 a2)
{
  unsigned int v4; // edi
  __int64 v5; // rax
  DWORD dwProcessId; // [rsp+38h] [rbp+10h] BYREF

  v4 = 1;
  if ( IsWindowEnabled(a1) )
  {
    dwProcessId = 0;
    GetWindowThreadProcessId(a1, &dwProcessId);
    if ( dwProcessId == *(_DWORD *)(a2 + 2064) )
    {
      v5 = *(int *)(a2 + 2060);
      if ( (int)v5 < 256 )
      {
        *(_QWORD *)(a2 + 8 * v5 + 8) = a1;
        ++*(_DWORD *)(a2 + 2060);
        EnableWindow(a1, 0);
        *(_BYTE *)(a2 + 2056) = 1;
      }
      else
      {
        return 0;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180043a70  mov     [rsp+arg_0], rbx
0x180043a75  mov     [rsp+arg_10], rsi
0x180043a7a  push    rdi
0x180043a7b  sub     rsp, 20h
0x180043a7f  mov     rbx, rdx
0x180043a82  mov     rsi, rcx
0x180043a85  call    cs:__imp_IsWindowEnabled
0x180043a8b  mov     edi, 1
0x180043a90  test    eax, eax
0x180043a92  jz      short loc_180043AE5
0x180043a94  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180043a99  mov     [rsp+28h+dwProcessId], 0
0x180043aa1  mov     rcx, rsi; hWnd
0x180043aa4  call    cs:__imp_GetWindowThreadProcessId
0x180043aaa  mov     eax, [rbx+810h]
0x180043ab0  cmp     [rsp+28h+dwProcessId], eax
0x180043ab4  jnz     short loc_180043AE5
0x180043ab6  movsxd  rax, dword ptr [rbx+80Ch]
0x180043abd  cmp     eax, 100h
0x180043ac2  jl      short loc_180043AC8
0x180043ac4  xor     edi, edi
0x180043ac6  jmp     short loc_180043AE5
0x180043ac8  mov     [rbx+rax*8+8], rsi
0x180043acd  xor     edx, edx; bEnable
0x180043acf  add     [rbx+80Ch], edi
0x180043ad5  mov     rcx, rsi; hWnd
0x180043ad8  call    cs:__imp_EnableWindow
0x180043ade  mov     [rbx+808h], dil
0x180043ae5  mov     rbx, [rsp+28h+arg_0]
0x180043aea  mov     eax, edi
0x180043aec  mov     rsi, [rsp+28h+arg_10]
0x180043af1  add     rsp, 20h
0x180043af5  pop     rdi
0x180043af6  retn
```
