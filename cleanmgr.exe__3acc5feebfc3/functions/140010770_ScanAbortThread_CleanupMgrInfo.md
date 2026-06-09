# ScanAbortThread(CleanupMgrInfo *)

- ea: `0x140010770`
- end: `0x14001080e`
- name: `?ScanAbortThread@@YAKPEAVCleanupMgrInfo@@@Z`
- size: `158`
- prototype: `__int64 __fastcall(LPARAM Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000ffb0`
- `0x140010770`

## import_xrefs

- `USER32!ShowWindow` at `0x1400107b9`
- `USER32!ShowWindow` at `0x1400107b9`
- `USER32!CreateDialogParamW` at `0x140010793`
- `USER32!CreateDialogParamW` at `0x140010793`
- `USER32!DestroyWindow` at `0x1400107f5`
- `USER32!DestroyWindow` at `0x1400107f5`
- `USER32!SetForegroundWindow` at `0x1400107c6`
- `USER32!SetForegroundWindow` at `0x1400107c6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400107d3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400107d3`

## pseudocode

```c
__int64 __fastcall ScanAbortThread(LPARAM Parameter)
{
  HWND DialogParamW; // rax
  HWND v3; // rcx

  DialogParamW = CreateDialogParamW(g_hInstance, (LPCWSTR)0x66, 0, (DLGPROC)ScanAbortDlgProc, Parameter);
  *(_QWORD *)(Parameter + 1664) = DialogParamW;
  if ( DialogParamW )
  {
    if ( (*(_DWORD *)(Parameter + 1632) & 0x1220) == 0 )
    {
      ShowWindow(DialogParamW, 5);
      SetForegroundWindow(*(HWND *)(Parameter + 1664));
    }
    SetEvent(*(HANDLE *)(Parameter + 1672));
    while ( 1 )
    {
      v3 = *(HWND *)(Parameter + 1664);
      if ( *(_DWORD *)(Parameter + 1768) )
        break;
      MessagePump(v3);
    }
    if ( v3 )
    {
      DestroyWindow(v3);
      *(_QWORD *)(Parameter + 1664) = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140010770  push    rbx
0x140010772  sub     rsp, 30h
0x140010776  xor     r8d, r8d; hWndParent
0x140010779  mov     [rsp+38h+dwInitParam], rcx; dwInitParam
0x14001077e  mov     rbx, rcx
0x140010781  lea     r9, ?ScanAbortDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x140010788  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x14001078f  lea     edx, [r8+66h]; lpTemplateName
0x140010793  call    cs:__imp_CreateDialogParamW
0x140010799  mov     [rbx+680h], rax
0x1400107a0  test    rax, rax
0x1400107a3  jz      short loc_140010806
0x1400107a5  test    dword ptr [rbx+660h], 1220h
0x1400107af  jnz     short loc_1400107CC
0x1400107b1  mov     edx, 5; nCmdShow
0x1400107b6  mov     rcx, rax; hWnd
0x1400107b9  call    cs:__imp_ShowWindow
0x1400107bf  mov     rcx, [rbx+680h]; hWnd
0x1400107c6  call    cs:__imp_SetForegroundWindow
0x1400107cc  mov     rcx, [rbx+688h]; hEvent
0x1400107d3  call    cs:__imp_SetEvent
0x1400107d9  jmp     short loc_1400107E0
0x1400107db  call    ?MessagePump@@YAHPEAUHWND__@@@Z; MessagePump(HWND__ *)
0x1400107e0  cmp     dword ptr [rbx+6E8h], 0
0x1400107e7  mov     rcx, [rbx+680h]; hDlg
0x1400107ee  jz      short loc_1400107DB
0x1400107f0  test    rcx, rcx
0x1400107f3  jz      short loc_140010806
0x1400107f5  call    cs:__imp_DestroyWindow
0x1400107fb  mov     qword ptr [rbx+680h], 0
0x140010806  xor     eax, eax
0x140010808  add     rsp, 30h
0x14001080c  pop     rbx
0x14001080d  retn
```
