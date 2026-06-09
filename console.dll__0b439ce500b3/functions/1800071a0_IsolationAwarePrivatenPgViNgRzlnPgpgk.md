# IsolationAwarePrivatenPgViNgRzlnPgpgk

- ea: `0x1800071a0`
- end: `0x180007239`
- name: `IsolationAwarePrivatenPgViNgRzlnPgpgk`
- size: `153`
- prototype: `__int64 __fastcall(ULONG_PTR *lpCookie)`
- caller_count: `10`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800070cc`
- `0x180008748`
- `0x1800088f4`
- `0x1800089e8`
- `0x180008aac`
- `0x180008b74`
- `0x18000bd08`
- `0x18000f23c`
- `0x18000f328`
- `0x180014008`

## callees

- `0x1800071a0`
- `0x180007240`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800071fc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800071ba`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800071ba`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800071ec`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800071ec`

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
  if ( LastError == 120 || LastError == 1 || LastError - 126 <= 1 || (result = 0, v4 == 50) )
  {
    IsolationAwarePrivateT_SqbjaYRiRY = 1;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800071a0  push    rbx
0x1800071a2  sub     rsp, 20h
0x1800071a6  mov     eax, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x1800071ac  mov     rbx, rcx
0x1800071af  test    eax, eax
0x1800071b1  jz      short loc_1800071CC
0x1800071b3  lea     rcx, ?debugString@?4??IsolationAwarePrivatenPgViNgRzlnPgpgk@@9@4QBDB; "IsolationAware function called after Is"...
0x1800071ba  call    cs:__imp_OutputDebugStringA
0x1800071c1  nop     dword ptr [rax+rax+00h]
0x1800071c6  mov     eax, cs:WinbaseIsolationAwarePrivateT_SpYRNahcpNYYRQ
0x1800071cc  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800071d3  jnz     short loc_18000722D
0x1800071d5  test    eax, eax
0x1800071d7  jnz     short loc_1800071E2
0x1800071d9  call    WinbaseIsolationAwarePrivatetRgzlnPgpgk
0x1800071de  test    eax, eax
0x1800071e0  jz      short loc_1800071FC
0x1800071e2  mov     rcx, cs:WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x1800071e9  mov     rdx, rbx; lpCookie
0x1800071ec  call    cs:__imp_ActivateActCtx
0x1800071f3  nop     dword ptr [rax+rax+00h]
0x1800071f8  test    eax, eax
0x1800071fa  jnz     short loc_18000722D
0x1800071fc  call    cs:__imp_GetLastError
0x180007203  nop     dword ptr [rax+rax+00h]
0x180007208  mov     edx, eax
0x18000720a  cmp     eax, 78h ; 'x'
0x18000720d  jz      short loc_180007223
0x18000720f  cmp     eax, 1
0x180007212  jz      short loc_180007223
0x180007214  lea     ecx, [rax-7Eh]
0x180007217  cmp     ecx, 1
0x18000721a  jbe     short loc_180007223
0x18000721c  xor     eax, eax
0x18000721e  cmp     edx, 32h ; '2'
0x180007221  jnz     short loc_180007232
0x180007223  mov     cs:IsolationAwarePrivateT_SqbjaYRiRY, 1
0x18000722d  mov     eax, 1
0x180007232  add     rsp, 20h
0x180007236  pop     rbx
0x180007237  retn
```
