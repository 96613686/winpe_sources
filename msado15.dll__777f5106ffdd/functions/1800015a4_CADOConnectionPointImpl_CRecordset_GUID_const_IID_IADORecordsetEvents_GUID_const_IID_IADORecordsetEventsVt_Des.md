# CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::DestroyAsyncEvents(void)

- ea: `0x1800015a4`
- end: `0x180001603`
- name: `?DestroyAsyncEvents@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents@@3U_GUID@@B$1?IID_IADORecordsetEventsVt@@3U3@B@@QEAAXXZ`
- size: `95`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001a88`
- `0x180045890`
- `0x180045b48`
- `0x180074950`
- `0x180074a70`
- `0x180074b90`

## callees

- `0x1800015a4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800015b4`
- `KERNEL32!GetCurrentThreadId` at `0x1800015b4`
- `USER32!DestroyWindow` at `0x1800015c9`
- `USER32!DestroyWindow` at `0x1800015c9`
- `USER32!PostMessageW` at `0x1800015f5`
- `USER32!PostMessageW` at `0x1800015f5`

## pseudocode

```c
void __fastcall CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::DestroyAsyncEvents(
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
0x1800015a4  push    rbx
0x1800015a6  sub     rsp, 20h
0x1800015aa  cmp     qword ptr [rcx+20h], 0
0x1800015af  mov     rbx, rcx
0x1800015b2  jz      short loc_1800015E4
0x1800015b4  call    cs:__imp_GetCurrentThreadId
0x1800015bb  nop     dword ptr [rax+rax+00h]
0x1800015c0  mov     rcx, [rbx+20h]; hWnd
0x1800015c4  cmp     [rbx+18h], eax
0x1800015c7  jnz     short loc_1800015EB
0x1800015c9  call    cs:__imp_DestroyWindow
0x1800015d0  nop     dword ptr [rax+rax+00h]
0x1800015d5  mov     dword ptr [rbx+18h], 0
0x1800015dc  mov     qword ptr [rbx+20h], 0
0x1800015e4  add     rsp, 20h
0x1800015e8  pop     rbx
0x1800015e9  retn
0x1800015eb  xor     r9d, r9d; lParam
0x1800015ee  xor     r8d, r8d; wParam
0x1800015f1  lea     edx, [r9+10h]; Msg
0x1800015f5  call    cs:__imp_PostMessageW
0x1800015fc  nop     dword ptr [rax+rax+00h]
0x180001601  jmp     short loc_1800015D5
```
