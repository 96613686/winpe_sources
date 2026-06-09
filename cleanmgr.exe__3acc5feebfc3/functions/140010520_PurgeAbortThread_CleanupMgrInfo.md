# PurgeAbortThread(CleanupMgrInfo *)

- ea: `0x140010520`
- end: `0x1400105b1`
- name: `?PurgeAbortThread@@YAKPEAVCleanupMgrInfo@@@Z`
- size: `145`
- prototype: `__int64 __fastcall(LPARAM Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000ffb0`
- `0x140010520`

## import_xrefs

- `USER32!ShowWindow` at `0x140010569`
- `USER32!ShowWindow` at `0x140010569`
- `USER32!CreateDialogParamW` at `0x140010543`
- `USER32!CreateDialogParamW` at `0x140010543`
- `USER32!DestroyWindow` at `0x140010598`
- `USER32!DestroyWindow` at `0x140010598`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140010576`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140010576`

## pseudocode

```c
__int64 __fastcall PurgeAbortThread(LPARAM Parameter)
{
  HWND DialogParamW; // rax
  HWND v3; // rcx

  DialogParamW = CreateDialogParamW(g_hInstance, (LPCWSTR)0x6A, 0, PurgeAbortDlgProc, Parameter);
  *(_QWORD *)(Parameter + 1696) = DialogParamW;
  if ( DialogParamW )
  {
    if ( (*(_DWORD *)(Parameter + 1632) & 0x1220) == 0 )
      ShowWindow(DialogParamW, 5);
    SetEvent(*(HANDLE *)(Parameter + 1704));
    while ( 1 )
    {
      v3 = *(HWND *)(Parameter + 1696);
      if ( *(_DWORD *)(Parameter + 1772) )
        break;
      MessagePump(v3);
    }
    if ( v3 )
    {
      DestroyWindow(v3);
      *(_QWORD *)(Parameter + 1696) = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140010520  push    rbx
0x140010522  sub     rsp, 30h
0x140010526  xor     r8d, r8d; hWndParent
0x140010529  mov     [rsp+38h+dwInitParam], rcx; dwInitParam
0x14001052e  mov     rbx, rcx
0x140010531  lea     r9, ?PurgeAbortDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x140010538  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x14001053f  lea     edx, [r8+6Ah]; lpTemplateName
0x140010543  call    cs:__imp_CreateDialogParamW
0x140010549  mov     [rbx+6A0h], rax
0x140010550  test    rax, rax
0x140010553  jz      short loc_1400105A9
0x140010555  test    dword ptr [rbx+660h], 1220h
0x14001055f  jnz     short loc_14001056F
0x140010561  mov     edx, 5; nCmdShow
0x140010566  mov     rcx, rax; hWnd
0x140010569  call    cs:__imp_ShowWindow
0x14001056f  mov     rcx, [rbx+6A8h]; hEvent
0x140010576  call    cs:__imp_SetEvent
0x14001057c  jmp     short loc_140010583
0x14001057e  call    ?MessagePump@@YAHPEAUHWND__@@@Z; MessagePump(HWND__ *)
0x140010583  cmp     dword ptr [rbx+6ECh], 0
0x14001058a  mov     rcx, [rbx+6A0h]; hDlg
0x140010591  jz      short loc_14001057E
0x140010593  test    rcx, rcx
0x140010596  jz      short loc_1400105A9
0x140010598  call    cs:__imp_DestroyWindow
0x14001059e  mov     qword ptr [rbx+6A0h], 0
0x1400105a9  xor     eax, eax
0x1400105ab  add     rsp, 30h
0x1400105af  pop     rbx
0x1400105b0  retn
```
