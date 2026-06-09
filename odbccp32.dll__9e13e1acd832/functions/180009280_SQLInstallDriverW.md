# SQLInstallDriverW

- ea: `0x180009280`
- end: `0x1800093a3`
- name: `SQLInstallDriverW`
- size: `291`
- prototype: `BOOL __stdcall(LPCWSTR lpszInfFile, LPCWSTR lpszDriver, LPWSTR lpszPath, WORD cchPathMax, WORD *pcchPathOut)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f2b0`

## callees

- `0x180001740`
- `0x180004bac`
- `0x180009050`
- `0x180009280`
- `0x180014ae0`

## import_xrefs

- `USER32!MessageBoxW` at `0x180009318`
- `USER32!MessageBoxW` at `0x180009318`
- `USER32!LoadStringW` at `0x1800092da`
- `USER32!LoadStringW` at `0x1800092fb`
- `USER32!LoadStringW` at `0x1800092da`
- `USER32!LoadStringW` at `0x1800092fb`
- `KERNEL32!LeaveCriticalSection` at `0x18000937d`
- `KERNEL32!LeaveCriticalSection` at `0x18000937d`
- `KERNEL32!EnterCriticalSection` at `0x180009329`
- `KERNEL32!EnterCriticalSection` at `0x180009329`

## pseudocode

```c
BOOL __stdcall SQLInstallDriverW(
        LPCWSTR lpszInfFile,
        LPCWSTR lpszDriver,
        LPWSTR lpszPath,
        WORD cchPathMax,
        WORD *pcchPathOut)
{
  BOOL v9; // ebx
  WCHAR Caption[128]; // [rsp+40h] [rbp-398h] BYREF
  WCHAR Buffer[304]; // [rsp+140h] [rbp-298h] BYREF

  if ( lpszInfFile && *lpszInfFile )
  {
    if ( LoadStringW(g_hResDLL, 0x532u, Buffer, 301) )
    {
      if ( LoadStringW(g_hResDLL, 0x522u, Caption, 128) )
        MessageBoxW(0, Buffer, Caption, 0x10u);
    }
    return 0;
  }
  else
  {
    EnterCriticalSection(&g_csInstaller);
    FreeErrorQueue();
    if ( lpszPath && cchPathMax >= 0x104u )
    {
      v9 = SQLInstallDriverCover((wchar_t *)lpszDriver, 0, lpszPath, cchPathMax, (__int16 *)pcchPathOut, 2, 0);
    }
    else
    {
      PostInstError(8);
      v9 = 0;
    }
    LeaveCriticalSection(&g_csInstaller);
    return v9;
  }
}

```

## disassembly

```asm
0x180009280  push    rbx
0x180009282  push    rbp
0x180009283  push    rsi
0x180009284  push    rdi
0x180009285  push    r14
0x180009287  sub     rsp, 3B0h
0x18000928e  mov     rax, cs:__security_cookie
0x180009295  xor     rax, rsp
0x180009298  mov     [rsp+3D8h+var_38], rax
0x1800092a0  mov     rbp, [rsp+3D8h+pcchPathOut]
0x1800092a8  xor     r14d, r14d
0x1800092ab  movzx   edi, r9w
0x1800092af  mov     rbx, r8
0x1800092b2  mov     rsi, rdx
0x1800092b5  test    rcx, rcx
0x1800092b8  jz      short loc_180009322
0x1800092ba  cmp     [rcx], r14w
0x1800092be  jz      short loc_180009322
0x1800092c0  mov     rcx, cs:g_hResDLL; hInstance
0x1800092c7  lea     r8, [rsp+3D8h+Buffer]; lpBuffer
0x1800092cf  mov     r9d, 12Dh; cchBufferMax
0x1800092d5  mov     edx, 532h; uID
0x1800092da  call    cs:__imp_LoadStringW
0x1800092e0  test    eax, eax
0x1800092e2  jz      short loc_18000931E
0x1800092e4  mov     rcx, cs:g_hResDLL; hInstance
0x1800092eb  lea     r8, [rsp+3D8h+Caption]; lpBuffer
0x1800092f0  mov     r9d, 80h; cchBufferMax
0x1800092f6  mov     edx, 522h; uID
0x1800092fb  call    cs:__imp_LoadStringW
0x180009301  test    eax, eax
0x180009303  jz      short loc_18000931E
0x180009305  lea     r9d, [r14+10h]; uType
0x180009309  xor     ecx, ecx; hWnd
0x18000930b  lea     r8, [rsp+3D8h+Caption]; lpCaption
0x180009310  lea     rdx, [rsp+3D8h+Buffer]; lpText
0x180009318  call    cs:__imp_MessageBoxW
0x18000931e  xor     eax, eax
0x180009320  jmp     short loc_180009385
0x180009322  lea     rcx, g_csInstaller; lpCriticalSection
0x180009329  call    cs:__imp_EnterCriticalSection
0x18000932f  call    FreeErrorQueue
0x180009334  test    rbx, rbx
0x180009337  jz      short loc_180009369
0x180009339  mov     eax, 104h
0x18000933e  cmp     di, ax
0x180009341  jb      short loc_180009369
0x180009343  mov     [rsp+3D8h+var_3A8], r14; __int64
0x180009348  movzx   r9d, di
0x18000934c  mov     [rsp+3D8h+var_3B0], 2; __int16
0x180009353  mov     r8, rbx
0x180009356  xor     edx, edx; wchar_t *
0x180009358  mov     [rsp+3D8h+var_3B8], rbp; __int64
0x18000935d  mov     rcx, rsi; String1
0x180009360  call    SQLInstallDriverCover
0x180009365  mov     ebx, eax
0x180009367  jmp     short loc_180009376
0x180009369  mov     ecx, 8
0x18000936e  call    PostInstError
0x180009373  mov     ebx, r14d
0x180009376  lea     rcx, g_csInstaller; lpCriticalSection
0x18000937d  call    cs:__imp_LeaveCriticalSection
0x180009383  mov     eax, ebx
0x180009385  mov     rcx, [rsp+3D8h+var_38]
0x18000938d  xor     rcx, rsp; StackCookie
0x180009390  call    __security_check_cookie
0x180009395  add     rsp, 3B0h
0x18000939c  pop     r14
0x18000939e  pop     rdi
0x18000939f  pop     rsi
0x1800093a0  pop     rbp
0x1800093a1  pop     rbx
0x1800093a2  retn
```
