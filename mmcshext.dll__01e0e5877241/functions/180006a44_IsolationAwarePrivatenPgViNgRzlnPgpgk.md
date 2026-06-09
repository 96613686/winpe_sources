# IsolationAwarePrivatenPgViNgRzlnPgpgk

- ea: `0x180006a44`
- end: `0x180006aca`
- name: `IsolationAwarePrivatenPgViNgRzlnPgpgk`
- size: `134`
- prototype: `__int64 __fastcall(ULONG_PTR *lpCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180006984`
- `0x180007918`
- `0x1800079e0`
- `0x180007aac`
- `0x180007b88`
- `0x180009b58`

## callees

- `0x180006a44`
- `0x180006ad0`

## import_xrefs

- `KERNEL32!OutputDebugStringA` at `0x180006a5e`
- `KERNEL32!OutputDebugStringA` at `0x180006a5e`
- `KERNEL32!ActivateActCtx` at `0x180006a8a`
- `KERNEL32!ActivateActCtx` at `0x180006a8a`
- `KERNEL32!GetLastError` at `0x180006a94`
- `KERNEL32!GetLastError` at `0x180006a94`

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
0x180006a44  push    rbx
0x180006a46  sub     rsp, 20h
0x180006a4a  mov     eax, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x180006a50  mov     rbx, rcx
0x180006a53  test    eax, eax
0x180006a55  jz      short loc_180006A6A
0x180006a57  lea     rcx, ?debugString@?4??IsolationAwarePrivatenPgViNgRzlnPgpgk@@9@4QBDB; "IsolationAware function called after Is"...
0x180006a5e  call    cs:__imp_OutputDebugStringA
0x180006a64  mov     eax, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x180006a6a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180006a71  jnz     short loc_180006ABF
0x180006a73  test    eax, eax
0x180006a75  jnz     short loc_180006A80
0x180006a77  call    WinbaseIsolationAwarePrivatetRgzlnPgpgk
0x180006a7c  test    eax, eax
0x180006a7e  jz      short loc_180006A94
0x180006a80  mov     rcx, cs:WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x180006a87  mov     rdx, rbx; lpCookie
0x180006a8a  call    cs:__imp_ActivateActCtx
0x180006a90  test    eax, eax
0x180006a92  jnz     short loc_180006ABF
0x180006a94  call    cs:__imp_GetLastError
0x180006a9a  mov     edx, eax
0x180006a9c  lea     ecx, [rax-7Eh]
0x180006a9f  cmp     ecx, 1
0x180006aa2  jbe     short loc_180006AB5
0x180006aa4  cmp     eax, 78h ; 'x'
0x180006aa7  jz      short loc_180006AB5
0x180006aa9  cmp     eax, 1
0x180006aac  jz      short loc_180006AB5
0x180006aae  xor     eax, eax
0x180006ab0  cmp     edx, 32h ; '2'
0x180006ab3  jnz     short loc_180006AC4
0x180006ab5  mov     cs:IsolationAwarePrivateT_SqbjaYRiRY, 1
0x180006abf  mov     eax, 1
0x180006ac4  add     rsp, 20h
0x180006ac8  pop     rbx
0x180006ac9  retn
```
