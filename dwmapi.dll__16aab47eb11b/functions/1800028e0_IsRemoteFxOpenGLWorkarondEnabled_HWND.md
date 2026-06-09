# IsRemoteFxOpenGLWorkarondEnabled(HWND__ *)

- ea: `0x1800028e0`
- end: `0x180002918`
- name: `?IsRemoteFxOpenGLWorkarondEnabled@@YAHPEAUHWND__@@@Z`
- size: `56`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002200`

## callees

- `0x1800028e0`

## import_xrefs

- `USER32!GetPropW` at `0x1800028f0`
- `USER32!GetPropW` at `0x1800028f0`
- `USER32!RemovePropW` at `0x18000290b`
- `USER32!RemovePropW` at `0x18000290b`

## string_xrefs

- `0x1800028e6`: `RemoteFxOpenGL_Window_Present`
- `0x180002901`: `RemoteFxOpenGL_Window_Present`

## pseudocode

```c
__int64 __fastcall IsRemoteFxOpenGLWorkarondEnabled(HWND hWnd)
{
  __int64 result; // rax

  result = (__int64)GetPropW(hWnd, L"RemoteFxOpenGL_Window_Present");
  if ( result )
  {
    RemovePropW(hWnd, L"RemoteFxOpenGL_Window_Present");
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1800028e0  push    rbx
0x1800028e2  sub     rsp, 20h
0x1800028e6  lea     rdx, String; "RemoteFxOpenGL_Window_Present"
0x1800028ed  mov     rbx, rcx
0x1800028f0  call    cs:__imp_GetPropW
0x1800028f6  test    rax, rax
0x1800028f9  jnz     short loc_180002901
0x1800028fb  add     rsp, 20h
0x1800028ff  pop     rbx
0x180002900  retn
0x180002901  lea     rdx, String; "RemoteFxOpenGL_Window_Present"
0x180002908  mov     rcx, rbx; hWnd
0x18000290b  call    cs:__imp_RemovePropW
0x180002911  mov     eax, 1
0x180002916  jmp     short loc_1800028FB
```
