# _pSpUtilsLogSetPath

- ea: `0x180021288`
- end: `0x180021371`
- name: `_pSpUtilsLogSetPath`
- size: `233`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800202d0`
- `0x180020384`

## callees

- `0x180020878`
- `0x180021200`
- `0x180021288`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800212aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800212f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021332`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800212aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800212f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021332`

## pseudocode

```c
__int64 __fastcall pSpUtilsLogSetPath(STRSAFE_LPCWSTR pszSrc)
{
  unsigned int appended; // ebx

  if ( InstallLogFilePath )
  {
    HeapFree(hHeap, 0, InstallLogFilePath);
    InstallLogFilePath = 0;
  }
  appended = pSetupAppendPath(pszSrc, L"setupapi.ev1", (__int64 *)&InstallLogFilePath);
  if ( !appended )
    goto LABEL_10;
  if ( EventLogFilePath )
  {
    HeapFree(hHeap, 0, EventLogFilePath);
    EventLogFilePath = 0;
  }
  appended = pSetupAppendPath(pszSrc, L"setupapi.ev2", (__int64 *)&EventLogFilePath);
  if ( !appended )
    goto LABEL_10;
  if ( StringLogFilePath )
  {
    HeapFree(hHeap, 0, StringLogFilePath);
    StringLogFilePath = 0;
  }
  appended = pSetupAppendPath(pszSrc, L"setupapi.ev3", (__int64 *)&StringLogFilePath);
  if ( !appended )
LABEL_10:
    pSpUtilsInstallLogUninitialize();
  return appended;
}

```

## disassembly

```asm
0x180021288  mov     [rsp+arg_0], rbx
0x18002128d  push    rdi
0x18002128e  sub     rsp, 20h
0x180021292  mov     r8, cs:InstallLogFilePath; lpMem
0x180021299  mov     rdi, rcx
0x18002129c  test    r8, r8
0x18002129f  jz      short loc_1800212BB
0x1800212a1  mov     rcx, cs:hHeap; hHeap
0x1800212a8  xor     edx, edx; dwFlags
0x1800212aa  call    cs:__imp_HeapFree
0x1800212b0  mov     cs:InstallLogFilePath, 0
0x1800212bb  lea     r8, InstallLogFilePath
0x1800212c2  mov     rcx, rdi; pszSrc
0x1800212c5  lea     rdx, aSetupapiEv1; "setupapi.ev1"
0x1800212cc  call    pSetupAppendPath
0x1800212d1  mov     ebx, eax
0x1800212d3  test    eax, eax
0x1800212d5  jz      loc_18002135F
0x1800212db  mov     r8, cs:EventLogFilePath; lpMem
0x1800212e2  test    r8, r8
0x1800212e5  jz      short loc_180021301
0x1800212e7  mov     rcx, cs:hHeap; hHeap
0x1800212ee  xor     edx, edx; dwFlags
0x1800212f0  call    cs:__imp_HeapFree
0x1800212f6  mov     cs:EventLogFilePath, 0
0x180021301  lea     r8, EventLogFilePath
0x180021308  mov     rcx, rdi; pszSrc
0x18002130b  lea     rdx, aSetupapiEv2; "setupapi.ev2"
0x180021312  call    pSetupAppendPath
0x180021317  mov     ebx, eax
0x180021319  test    eax, eax
0x18002131b  jz      short loc_18002135F
0x18002131d  mov     r8, cs:StringLogFilePath; lpMem
0x180021324  test    r8, r8
0x180021327  jz      short loc_180021343
0x180021329  mov     rcx, cs:hHeap; hHeap
0x180021330  xor     edx, edx; dwFlags
0x180021332  call    cs:__imp_HeapFree
0x180021338  mov     cs:StringLogFilePath, 0
0x180021343  lea     r8, StringLogFilePath
0x18002134a  mov     rcx, rdi; pszSrc
0x18002134d  lea     rdx, aSetupapiEv3; "setupapi.ev3"
0x180021354  call    pSetupAppendPath
0x180021359  mov     ebx, eax
0x18002135b  test    eax, eax
0x18002135d  jnz     short loc_180021364
0x18002135f  call    _pSpUtilsInstallLogUninitialize
0x180021364  mov     eax, ebx
0x180021366  mov     rbx, [rsp+28h+arg_0]
0x18002136b  add     rsp, 20h
0x18002136f  pop     rdi
0x180021370  retn
```
