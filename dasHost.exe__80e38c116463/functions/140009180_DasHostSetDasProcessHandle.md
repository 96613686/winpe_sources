# DasHostSetDasProcessHandle

- ea: `0x140009180`
- end: `0x140009238`
- name: `DasHostSetDasProcessHandle`
- size: `184`
- prototype: `__int64 __fastcall(__int64, void *, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140008eec`
- `0x140008f88`
- `0x140009180`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400091dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400091dd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400091ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1400091ff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1400091cb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1400091cb`

## pseudocode

```c
__int64 __fastcall DasHostSetDasProcessHandle(__int64 a1, void *a2, int a3)
{
  struct _TP_WAIT *ThreadpoolWait; // rax
  signed int LastError; // eax
  int v6; // edx
  int v7; // r8d
  unsigned int v8; // ebx
  int v10; // [rsp+28h] [rbp-40h]

  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      (int)a2,
      a3,
      14,
      &WPP_6dd9e3daa83c383c742cfcb4a96fedc2_Traceguids);
  ThreadpoolWait = CreateThreadpoolWait((PTP_WAIT_CALLBACK)DasExitWaitCallback, a2, 0);
  g_hDasExitWait = ThreadpoolWait;
  if ( ThreadpoolWait )
  {
    v8 = 0;
    SetThreadpoolWait(ThreadpoolWait, a2, 0);
  }
  else
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v6,
      v7,
      15,
      &WPP_6dd9e3daa83c383c742cfcb4a96fedc2_Traceguids,
      v10,
      v8);
  return v8;
}

```

## disassembly

```asm
0x140009180  push    rbx
0x140009182  push    rbp
0x140009183  push    rsi
0x140009184  push    rdi
0x140009185  sub     rsp, 48h
0x140009189  mov     rdi, rdx
0x14000918c  lea     rsi, WPP_RECORDER_INITIALIZED
0x140009193  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000919a  lea     rbp, WPP_6dd9e3daa83c383c742cfcb4a96fedc2_Traceguids
0x1400091a1  jz      short loc_1400091BE
0x1400091a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400091aa  mov     r9d, 0Eh; int
0x1400091b0  mov     [rsp+68h+MessageGuid], rbp; MessageGuid
0x1400091b5  mov     rcx, [rcx+28h]; int
0x1400091b9  call    WPP_RECORDER_SF_s
0x1400091be  xor     r8d, r8d; pcbe
0x1400091c1  lea     rcx, ?DasExitWaitCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1400091c8  mov     rdx, rdi; pv
0x1400091cb  call    cs:__imp_CreateThreadpoolWait
0x1400091d1  mov     cs:?g_hDasExitWait@@3PEAU_TP_WAIT@@EA, rax; _TP_WAIT * g_hDasExitWait
0x1400091d8  test    rax, rax
0x1400091db  jnz     short loc_1400091F4
0x1400091dd  call    cs:__imp_GetLastError
0x1400091e3  mov     ebx, eax
0x1400091e5  test    eax, eax
0x1400091e7  jle     short loc_140009205
0x1400091e9  movzx   ebx, ax
0x1400091ec  or      ebx, 80070000h
0x1400091f2  jmp     short loc_140009205
0x1400091f4  xor     ebx, ebx
0x1400091f6  xor     r8d, r8d; pftTimeout
0x1400091f9  mov     rdx, rdi; h
0x1400091fc  mov     rcx, rax; pwa
0x1400091ff  call    cs:__imp_SetThreadpoolWait
0x140009205  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000920c  jz      short loc_14000922D
0x14000920e  mov     rcx, cs:WPP_GLOBAL_Control
0x140009215  mov     r9d, 0Fh; int
0x14000921b  mov     dword ptr [rsp+68h+var_38], ebx; char
0x14000921f  mov     [rsp+68h+MessageGuid], rbp; MessageGuid
0x140009224  mov     rcx, [rcx+28h]; int
0x140009228  call    WPP_RECORDER_SF_sd
0x14000922d  mov     eax, ebx
0x14000922f  add     rsp, 48h
0x140009233  pop     rdi
0x140009234  pop     rsi
0x140009235  pop     rbp
0x140009236  pop     rbx
0x140009237  retn
```
