# CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::DestroyAsyncEvents(void)

- ea: `0x18000153c`
- end: `0x18000159b`
- name: `?DestroyAsyncEvents@?$CADOConnectionPointImpl@VCConnection@@$1?IID_IADOConnectionEvents@@3U_GUID@@B$1?IID_IADOConnectionEventsVt@@3U3@B@@QEAAXXZ`
- size: `95`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001870`
- `0x180074830`

## callees

- `0x18000153c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000154c`
- `KERNEL32!GetCurrentThreadId` at `0x18000154c`
- `USER32!DestroyWindow` at `0x180001561`
- `USER32!DestroyWindow` at `0x180001561`
- `USER32!PostMessageW` at `0x180001579`
- `USER32!PostMessageW` at `0x180001579`

## pseudocode

```c
void __fastcall CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::DestroyAsyncEvents(
        __int64 a1)
{
  DWORD CurrentThreadId; // eax
  HWND v3; // rcx

  if ( *(_QWORD *)(a1 + 32) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v3 = *(HWND *)(a1 + 32);
    if ( *(_DWORD *)(a1 + 24) == CurrentThreadId )
      DestroyWindow(v3);
    else
      PostMessageW(v3, 0x10u, 0, 0);
    *(_DWORD *)(a1 + 24) = 0;
    *(_QWORD *)(a1 + 32) = 0;
  }
}

```

## disassembly

```asm
0x18000153c  push    rbx
0x18000153e  sub     rsp, 20h
0x180001542  cmp     qword ptr [rcx+20h], 0
0x180001547  mov     rbx, rcx
0x18000154a  jz      short loc_180001594
0x18000154c  call    cs:__imp_GetCurrentThreadId
0x180001553  nop     dword ptr [rax+rax+00h]
0x180001558  mov     rcx, [rbx+20h]; hWnd
0x18000155c  cmp     [rbx+18h], eax
0x18000155f  jnz     short loc_18000156F
0x180001561  call    cs:__imp_DestroyWindow
0x180001568  nop     dword ptr [rax+rax+00h]
0x18000156d  jmp     short loc_180001585
0x18000156f  xor     r9d, r9d; lParam
0x180001572  xor     r8d, r8d; wParam
0x180001575  lea     edx, [r9+10h]; Msg
0x180001579  call    cs:__imp_PostMessageW
0x180001580  nop     dword ptr [rax+rax+00h]
0x180001585  mov     dword ptr [rbx+18h], 0
0x18000158c  mov     qword ptr [rbx+20h], 0
0x180001594  add     rsp, 20h
0x180001598  pop     rbx
0x180001599  retn
```
