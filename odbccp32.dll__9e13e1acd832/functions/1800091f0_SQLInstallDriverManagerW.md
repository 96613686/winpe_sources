# SQLInstallDriverManagerW

- ea: `0x1800091f0`
- end: `0x180009279`
- name: `SQLInstallDriverManagerW`
- size: `137`
- prototype: `BOOL __stdcall(LPWSTR lpszPath, WORD cchPathMax, WORD *pcchPathOut)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000f530`

## callees

- `0x180001740`
- `0x180004bac`
- `0x18000829c`
- `0x1800091f0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180009261`
- `KERNEL32!LeaveCriticalSection` at `0x180009261`
- `KERNEL32!EnterCriticalSection` at `0x18000920f`
- `KERNEL32!EnterCriticalSection` at `0x18000920f`

## pseudocode

```c
BOOL __stdcall SQLInstallDriverManagerW(LPWSTR lpszPath, WORD cchPathMax, WORD *pcchPathOut)
{
  WORD *v6; // r8
  BOOL v7; // ebx
  __int16 v9; // [rsp+30h] [rbp+8h] BYREF

  EnterCriticalSection(&g_csInstaller);
  FreeErrorQueue();
  v9 = 0;
  if ( lpszPath && cchPathMax >= 0x104u )
  {
    v6 = (WORD *)&v9;
    if ( pcchPathOut )
      v6 = pcchPathOut;
    GetTargetDirectory(lpszPath, cchPathMax, v6);
    v7 = 1;
  }
  else
  {
    PostInstError(2);
    v7 = 0;
  }
  LeaveCriticalSection(&g_csInstaller);
  return v7;
}

```

## disassembly

```asm
0x1800091f0  mov     [rsp+arg_8], rbx
0x1800091f5  mov     [rsp+arg_10], rsi
0x1800091fa  push    rdi
0x1800091fb  sub     rsp, 20h
0x1800091ff  mov     rdi, rcx
0x180009202  mov     rsi, r8
0x180009205  lea     rcx, g_csInstaller; lpCriticalSection
0x18000920c  movzx   ebx, dx
0x18000920f  call    cs:__imp_EnterCriticalSection
0x180009215  call    FreeErrorQueue
0x18000921a  xor     eax, eax
0x18000921c  mov     [rsp+28h+arg_0], ax
0x180009221  test    rdi, rdi
0x180009224  jz      short loc_18000924E
0x180009226  mov     eax, 104h
0x18000922b  cmp     bx, ax
0x18000922e  jb      short loc_18000924E
0x180009230  test    rsi, rsi
0x180009233  lea     r8, [rsp+28h+arg_0]
0x180009238  movzx   edx, bx
0x18000923b  mov     rcx, rdi; Buffer
0x18000923e  cmovnz  r8, rsi
0x180009242  call    GetTargetDirectory
0x180009247  mov     ebx, 1
0x18000924c  jmp     short loc_18000925A
0x18000924e  mov     ecx, 2
0x180009253  call    PostInstError
0x180009258  xor     ebx, ebx
0x18000925a  lea     rcx, g_csInstaller; lpCriticalSection
0x180009261  call    cs:__imp_LeaveCriticalSection
0x180009267  mov     rsi, [rsp+28h+arg_10]
0x18000926c  mov     eax, ebx
0x18000926e  mov     rbx, [rsp+28h+arg_8]
0x180009273  add     rsp, 20h
0x180009277  pop     rdi
0x180009278  retn
```
