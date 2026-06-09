# IsolationAwarePrivatenPgViNgRzlnPgpgk

- ea: `0x1800029e0`
- end: `0x180002a66`
- name: `IsolationAwarePrivatenPgViNgRzlnPgpgk`
- size: `134`
- prototype: `__int64 __fastcall(ULONG_PTR *lpCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180002918`
- `0x180002a80`
- `0x18000a900`

## callees

- `0x1800029e0`
- `0x180002b70`

## import_xrefs

- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180002a26`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180002a26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002a30`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029fa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800029fa`

## pseudocode

```c
__int64 __fastcall IsolationAwarePrivatenPgViNgRzlnPgpgk(ULONG_PTR *lpCookie)
{
  int v1; // eax
  DWORD LastError; // eax
  DWORD v4; // edx
  __int64 result; // rax

  v1 = WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ;
  if ( WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ )
  {
    OutputDebugStringA("IsolationAware function called after IsolationAwareCleanup\n");
    v1 = WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ;
  }
  if ( IsolationAwarePrivateT_SqbjaYRiRY
    || (v1 || (unsigned int)WinbaseIsolationAwarePrivatetRgzlnPgpgk())
    && ActivateActCtx(WinbaseIsolationAwarePrivateT_UnPgpgk, lpCookie) )
  {
    return 1;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError - 126 <= 1 || LastError == 120 || LastError == 1 || (result = 0, v4 == 50) )
  {
    IsolationAwarePrivateT_SqbjaYRiRY = 1;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800029e0  push    rbx
0x1800029e2  sub     rsp, 20h
0x1800029e6  mov     eax, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x1800029ec  mov     rbx, rcx
0x1800029ef  test    eax, eax
0x1800029f1  jz      short loc_180002A06
0x1800029f3  lea     rcx, ?debugString@?4??IsolationAwarePrivatenPgViNgRzlnPgpgk@@9@4QBDB; "IsolationAware function called after Is"...
0x1800029fa  call    cs:__imp_OutputDebugStringA
0x180002a00  mov     eax, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x180002a06  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180002a0d  jnz     short loc_180002A5B
0x180002a0f  test    eax, eax
0x180002a11  jnz     short loc_180002A1C
0x180002a13  call    WinbaseIsolationAwarePrivatetRgzlnPgpgk
0x180002a18  test    eax, eax
0x180002a1a  jz      short loc_180002A30
0x180002a1c  mov     rcx, cs:WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x180002a23  mov     rdx, rbx; lpCookie
0x180002a26  call    cs:__imp_ActivateActCtx
0x180002a2c  test    eax, eax
0x180002a2e  jnz     short loc_180002A5B
0x180002a30  call    cs:__imp_GetLastError
0x180002a36  mov     edx, eax
0x180002a38  lea     ecx, [rax-7Eh]
0x180002a3b  cmp     ecx, 1
0x180002a3e  jbe     short loc_180002A51
0x180002a40  cmp     eax, 78h ; 'x'
0x180002a43  jz      short loc_180002A51
0x180002a45  cmp     eax, 1
0x180002a48  jz      short loc_180002A51
0x180002a4a  xor     eax, eax
0x180002a4c  cmp     edx, 32h ; '2'
0x180002a4f  jnz     short loc_180002A60
0x180002a51  mov     cs:IsolationAwarePrivateT_SqbjaYRiRY, 1
0x180002a5b  mov     eax, 1
0x180002a60  add     rsp, 20h
0x180002a64  pop     rbx
0x180002a65  retn
```
