# StatusTaskDialogCallback(HWND__ *,uint,unsigned __int64,__int64,__int64)

- ea: `0x14001c970`
- end: `0x14001c9c1`
- name: `?StatusTaskDialogCallback@@YAJPEAUHWND__@@I_K_J2@Z`
- size: `81`
- prototype: `__int64 __fastcall(HWND hWnd, int, __int64, __int64, HANDLE *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x14001c970`

## import_xrefs

- `USER32!SendMessageW` at `0x14001c9b3`
- `USER32!SendMessageW` at `0x14001c9b3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001c98c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001c98c`

## pseudocode

```c
__int64 __fastcall StatusTaskDialogCallback(HWND hWnd, int a2, __int64 a3, __int64 a4, HANDLE *a5)
{
  HWND v5; // rbx
  LPARAM v6; // r9
  UINT v7; // edx
  WPARAM v8; // r8

  v5 = hWnd;
  if ( !a2 )
  {
    v6 = 50;
    v7 = 1131;
    v8 = 1;
    goto LABEL_6;
  }
  if ( a2 == 4 && !WaitForSingleObject(*a5, 0) )
  {
    v6 = 0;
    v7 = 16;
    v8 = 0;
    hWnd = v5;
LABEL_6:
    SendMessageW(hWnd, v7, v8, v6);
  }
  return 0;
}

```

## disassembly

```asm
0x14001c970  push    rbx
0x14001c972  sub     rsp, 20h
0x14001c976  mov     rbx, rcx
0x14001c979  test    edx, edx
0x14001c97b  jz      short loc_14001C9A4
0x14001c97d  cmp     edx, 4
0x14001c980  jnz     short loc_14001C9B9
0x14001c982  mov     rcx, [rsp+28h+arg_20]
0x14001c987  xor     edx, edx; dwMilliseconds
0x14001c989  mov     rcx, [rcx]; hHandle
0x14001c98c  call    cs:__imp_WaitForSingleObject
0x14001c992  test    eax, eax
0x14001c994  jnz     short loc_14001C9B9
0x14001c996  xor     r9d, r9d
0x14001c999  lea     edx, [rax+10h]
0x14001c99c  xor     r8d, r8d
0x14001c99f  mov     rcx, rbx; hWnd
0x14001c9a2  jmp     short loc_14001C9B3
0x14001c9a4  mov     r9d, 32h ; '2'; lParam
0x14001c9aa  mov     edx, 46Bh; Msg
0x14001c9af  lea     r8d, [r9-31h]; wParam
0x14001c9b3  call    cs:__imp_SendMessageW
0x14001c9b9  xor     eax, eax
0x14001c9bb  add     rsp, 20h
0x14001c9bf  pop     rbx
0x14001c9c0  retn
```
