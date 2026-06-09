# DwmpSetImmersiveIconicNotifyWindow

- ea: `0x18000a240`
- end: `0x18000a2ec`
- name: `DwmpSetImmersiveIconicNotifyWindow`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x18000352c`
- `0x18000a240`
- `0x18000ade0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a271`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a271`
- `USER32!GetWindowThreadProcessId` at `0x18000a26b`
- `USER32!GetWindowThreadProcessId` at `0x18000a26b`
- `USER32!GetShellWindow` at `0x18000a250`
- `USER32!GetShellWindow` at `0x18000a250`

## pseudocode

```c
__int64 __fastcall DwmpSetImmersiveIconicNotifyWindow(__int64 a1)
{
  bool v2; // di
  HWND ShellWindow; // rax
  CApiPortClient *v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  void *v8; // [rsp+28h] [rbp-20h]
  int v9; // [rsp+30h] [rbp-18h] BYREF
  __int64 v10; // [rsp+34h] [rbp-14h]
  DWORD dwProcessId; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  ShellWindow = GetShellWindow();
  if ( ShellWindow )
  {
    dwProcessId = 0;
    GetWindowThreadProcessId(ShellWindow, &dwProcessId);
    v2 = GetCurrentProcessId() == dwProcessId;
  }
  if ( a1 && v2 )
  {
    v9 = 1073741908;
    v10 = a1;
    v5 = CApiPortClient::SendNotification(v4, &v9, 12);
    v6 = v5;
    if ( v5 < 0 )
      MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019640, 2u, v5, 0x2E6u, v8);
  }
  else
  {
    v6 = -2147024809;
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_180019640, 2u, -2147024809, 0x2DFu, v8);
  }
  return v6;
}

```

## disassembly

```asm
0x18000a240  mov     [rsp+arg_8], rbx
0x18000a245  push    rdi
0x18000a246  sub     rsp, 40h
0x18000a24a  mov     rbx, rcx
0x18000a24d  xor     dil, dil
0x18000a250  call    cs:__imp_GetShellWindow
0x18000a256  test    rax, rax
0x18000a259  jz      short loc_18000A27F
0x18000a25b  lea     rdx, [rsp+48h+dwProcessId]; lpdwProcessId
0x18000a260  mov     [rsp+48h+dwProcessId], 0
0x18000a268  mov     rcx, rax; hWnd
0x18000a26b  call    cs:__imp_GetWindowThreadProcessId
0x18000a271  call    cs:__imp_GetCurrentProcessId
0x18000a277  cmp     eax, [rsp+48h+dwProcessId]
0x18000a27b  setz    dil
0x18000a27f  test    rbx, rbx
0x18000a282  jz      short loc_18000A2B9
0x18000a284  test    dil, dil
0x18000a287  jz      short loc_18000A2B9
0x18000a289  mov     r8d, 0Ch; __int16
0x18000a28f  mov     [rsp+48h+var_18], 40000054h
0x18000a297  lea     rdx, [rsp+48h+var_18]; void *
0x18000a29c  mov     [rsp+48h+var_14], rbx
0x18000a2a1  call    ?SendNotification@CApiPortClient@@QEAAJPEAXF@Z; CApiPortClient::SendNotification(void *,short)
0x18000a2a6  mov     ebx, eax
0x18000a2a8  test    eax, eax
0x18000a2aa  jns     short loc_18000A2DF
0x18000a2ac  mov     [rsp+48h+var_28], 2E6h
0x18000a2b4  mov     r9d, eax
0x18000a2b7  jmp     short loc_18000A2C9
0x18000a2b9  mov     ebx, 80070057h
0x18000a2be  mov     [rsp+48h+var_28], 2DFh; unsigned int
0x18000a2c6  mov     r9d, ebx; int
0x18000a2c9  mov     r8d, 2; unsigned int
0x18000a2cf  lea     rdx, qword_180019640; int *
0x18000a2d6  lea     ecx, [r8+2]; unsigned int
0x18000a2da  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18000a2df  mov     eax, ebx
0x18000a2e1  mov     rbx, [rsp+48h+arg_8]
0x18000a2e6  add     rsp, 40h
0x18000a2ea  pop     rdi
0x18000a2eb  retn
```
