# _pSpUtilsLogSetPath

- ea: `0x1800084ac`
- end: `0x180008595`
- name: `_pSpUtilsLogSetPath`
- size: `233`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800076d4`
- `0x1800077d0`

## callees

- `0x1800079f0`
- `0x180008424`
- `0x1800084ac`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800084ce`
- `KERNEL32!HeapFree` at `0x180008514`
- `KERNEL32!HeapFree` at `0x180008556`
- `KERNEL32!HeapFree` at `0x1800084ce`
- `KERNEL32!HeapFree` at `0x180008514`
- `KERNEL32!HeapFree` at `0x180008556`

## pseudocode

```c
__int64 __fastcall pSpUtilsLogSetPath(STRSAFE_LPCWSTR pszSrc)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  unsigned int appended; // ebx
  __int64 v5; // r8

  if ( InstallLogFilePath )
  {
    HeapFree(hHeap, 0, InstallLogFilePath);
    InstallLogFilePath = 0;
  }
  appended = pSetupAppendPath(pszSrc, L"setupapi.ev1", &InstallLogFilePath);
  if ( !appended )
    goto LABEL_10;
  if ( EventLogFilePath )
  {
    HeapFree(hHeap, 0, EventLogFilePath);
    EventLogFilePath = 0;
  }
  appended = pSetupAppendPath(pszSrc, L"setupapi.ev2", &EventLogFilePath);
  if ( !appended )
    goto LABEL_10;
  if ( StringLogFilePath )
  {
    HeapFree(hHeap, 0, StringLogFilePath);
    StringLogFilePath = 0;
  }
  appended = pSetupAppendPath(pszSrc, L"setupapi.ev3", &StringLogFilePath);
  if ( !appended )
LABEL_10:
    pSpUtilsInstallLogUninitialize(v3, v2, v5);
  return appended;
}

```

## disassembly

```asm
0x1800084ac  mov     [rsp+arg_0], rbx
0x1800084b1  push    rdi
0x1800084b2  sub     rsp, 20h
0x1800084b6  mov     r8, cs:InstallLogFilePath; lpMem
0x1800084bd  mov     rdi, rcx
0x1800084c0  test    r8, r8
0x1800084c3  jz      short loc_1800084DF
0x1800084c5  mov     rcx, cs:hHeap; hHeap
0x1800084cc  xor     edx, edx; dwFlags
0x1800084ce  call    cs:__imp_HeapFree
0x1800084d4  mov     cs:InstallLogFilePath, 0
0x1800084df  lea     r8, InstallLogFilePath
0x1800084e6  mov     rcx, rdi; pszSrc
0x1800084e9  lea     rdx, aSetupapiEv1; "setupapi.ev1"
0x1800084f0  call    pSetupAppendPath
0x1800084f5  mov     ebx, eax
0x1800084f7  test    eax, eax
0x1800084f9  jz      loc_180008583
0x1800084ff  mov     r8, cs:EventLogFilePath; lpMem
0x180008506  test    r8, r8
0x180008509  jz      short loc_180008525
0x18000850b  mov     rcx, cs:hHeap; hHeap
0x180008512  xor     edx, edx; dwFlags
0x180008514  call    cs:__imp_HeapFree
0x18000851a  mov     cs:EventLogFilePath, 0
0x180008525  lea     r8, EventLogFilePath
0x18000852c  mov     rcx, rdi; pszSrc
0x18000852f  lea     rdx, aSetupapiEv2; "setupapi.ev2"
0x180008536  call    pSetupAppendPath
0x18000853b  mov     ebx, eax
0x18000853d  test    eax, eax
0x18000853f  jz      short loc_180008583
0x180008541  mov     r8, cs:StringLogFilePath; lpMem
0x180008548  test    r8, r8
0x18000854b  jz      short loc_180008567
0x18000854d  mov     rcx, cs:hHeap; hHeap
0x180008554  xor     edx, edx; dwFlags
0x180008556  call    cs:__imp_HeapFree
0x18000855c  mov     cs:StringLogFilePath, 0
0x180008567  lea     r8, StringLogFilePath
0x18000856e  mov     rcx, rdi; pszSrc
0x180008571  lea     rdx, aSetupapiEv3; "setupapi.ev3"
0x180008578  call    pSetupAppendPath
0x18000857d  mov     ebx, eax
0x18000857f  test    eax, eax
0x180008581  jnz     short loc_180008588
0x180008583  call    _pSpUtilsInstallLogUninitialize
0x180008588  mov     eax, ebx
0x18000858a  mov     rbx, [rsp+28h+arg_0]
0x18000858f  add     rsp, 20h
0x180008593  pop     rdi
0x180008594  retn
```
