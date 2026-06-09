# CDRMCTridentDlg::LaunchTrident(HWND__ *)

- ea: `0x18002f1a0`
- end: `0x18002f2c1`
- name: `?LaunchTrident@CDRMCTridentDlg@@QEAAJPEAUHWND__@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(CDRMCTridentDlg *__hidden this, HWND)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18002bcd0`
- `0x18002c0f4`

## callees

- `0x18002f1a0`
- `0x18002fbb8`
- `0x18004f65c`
- `0x18004f778`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f1db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002f1db`
- `ATL!__imp_AtlModuleAddCreateWndData` at `0x18002f1fe`
- `ATL!__imp_AtlModuleAddCreateWndData` at `0x18002f1fe`
- `USER32!DispatchMessageW` at `0x18002f29a`
- `USER32!DispatchMessageW` at `0x18002f29a`
- `USER32!TranslateMessage` at `0x18002f290`
- `USER32!TranslateMessage` at `0x18002f290`
- `USER32!GetMessageW` at `0x18002f2ac`
- `USER32!GetMessageW` at `0x18002f2ac`

## pseudocode

```c
__int64 __fastcall CDRMCTridentDlg::LaunchTrident(CDRMCTridentDlg *this, HWND a2)
{
  AtlThunkData_t *Data; // rax
  __int64 v5; // rdx
  unsigned int v6; // esi
  int (__fastcall ***v7)(_QWORD, GUID *, __int64 *); // rcx
  int v8; // ebx
  MSG Msg; // [rsp+30h] [rbp-38h] BYREF
  __int64 v11; // [rsp+90h] [rbp+28h] BYREF

  Data = (AtlThunkData_t *)*((_QWORD *)this + 5);
  memset(&Msg, 0, sizeof(Msg));
  if ( !Data )
  {
    Data = AtlThunk_AllocateData();
    *((_QWORD *)this + 5) = Data;
    if ( !Data )
    {
      SetLastError(0xEu);
      return (unsigned int)-2147168448;
    }
  }
  AtlThunk_InitData(Data, 0, 0);
  AtlModuleAddCreateWndData(&_Module, (char *)this + 16, this);
  if ( !IsolationAwareCreateDialogParamW(hInstance, v5, a2) )
    return (unsigned int)-2147168448;
  if ( *((_QWORD *)this + 8) )
  {
    v6 = 0;
    while ( GetMessageW(&Msg, 0, 0, 0) )
    {
      v7 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))(*((_QWORD *)this + 8) + 80LL);
      if ( v7 )
      {
        v11 = 0;
        if ( (**v7)(v7, &IID_IOleInPlaceActiveObject, &v11) >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64, MSG *))(*(_QWORD *)v11 + 40LL))(v11, &Msg);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
          if ( !v8 )
            continue;
        }
      }
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v6;
}

```

## disassembly

```asm
0x18002f1a0  push    rbp
0x18002f1a2  push    rbx
0x18002f1a3  push    rsi
0x18002f1a4  push    rdi
0x18002f1a5  mov     rbp, rsp
0x18002f1a8  sub     rsp, 68h
0x18002f1ac  mov     rax, [rcx+28h]
0x18002f1b0  xorps   xmm0, xmm0
0x18002f1b3  mov     rbx, rdx
0x18002f1b6  mov     rdi, rcx
0x18002f1b9  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x18002f1bd  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x18002f1c1  movups  xmmword ptr [rbp+Msg.time], xmm0
0x18002f1c5  test    rax, rax
0x18002f1c8  jnz     short loc_18002F1E3
0x18002f1ca  call    AtlThunk_AllocateData
0x18002f1cf  mov     [rdi+28h], rax
0x18002f1d3  test    rax, rax
0x18002f1d6  jnz     short loc_18002F1E3
0x18002f1d8  lea     ecx, [rax+0Eh]; dwErrCode
0x18002f1db  call    cs:__imp_SetLastError
0x18002f1e1  jmp     short loc_18002F218
0x18002f1e3  xor     r8d, r8d; FirstParameter
0x18002f1e6  xor     edx, edx; Proc
0x18002f1e8  mov     rcx, rax; Thunk
0x18002f1eb  call    AtlThunk_InitData
0x18002f1f0  lea     rdx, [rdi+10h]
0x18002f1f4  mov     r8, rdi
0x18002f1f7  lea     rcx, ?_Module@@3VCComModule@ATL@@A; ATL::CComModule _Module
0x18002f1fe  call    cs:__imp_AtlModuleAddCreateWndData
0x18002f204  mov     rcx, cs:hInstance; hInstance
0x18002f20b  mov     r8, rbx
0x18002f20e  call    IsolationAwareCreateDialogParamW
0x18002f213  test    rax, rax
0x18002f216  jnz     short loc_18002F222
0x18002f218  mov     esi, 8004CF40h
0x18002f21d  jmp     loc_18002F2B6
0x18002f222  cmp     qword ptr [rdi+40h], 0
0x18002f227  jnz     short loc_18002F233
0x18002f229  mov     esi, 8007000Eh
0x18002f22e  jmp     loc_18002F2B6
0x18002f233  xor     esi, esi
0x18002f235  jmp     short loc_18002F2A0
0x18002f237  mov     rax, [rdi+40h]
0x18002f23b  mov     rcx, [rax+50h]
0x18002f23f  test    rcx, rcx
0x18002f242  jz      short loc_18002F28C
0x18002f244  mov     [rbp+arg_0], rsi
0x18002f248  lea     r8, [rbp+arg_0]
0x18002f24c  mov     rax, [rcx]
0x18002f24f  lea     rdx, IID_IOleInPlaceActiveObject
0x18002f256  mov     rax, [rax]
0x18002f259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f25e  test    eax, eax
0x18002f260  js      short loc_18002F28C
0x18002f262  mov     rcx, [rbp+arg_0]
0x18002f266  lea     rdx, [rbp+Msg]
0x18002f26a  mov     rax, [rcx]
0x18002f26d  mov     rax, [rax+28h]
0x18002f271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f276  mov     rcx, [rbp+arg_0]
0x18002f27a  mov     ebx, eax
0x18002f27c  mov     rdx, [rcx]
0x18002f27f  mov     rax, [rdx+10h]
0x18002f283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f288  test    ebx, ebx
0x18002f28a  jz      short loc_18002F2A0
0x18002f28c  lea     rcx, [rbp+Msg]; lpMsg
0x18002f290  call    cs:__imp_TranslateMessage
0x18002f296  lea     rcx, [rbp+Msg]; lpMsg
0x18002f29a  call    cs:__imp_DispatchMessageW
0x18002f2a0  xor     r9d, r9d; wMsgFilterMax
0x18002f2a3  lea     rcx, [rbp+Msg]; lpMsg
0x18002f2a7  xor     r8d, r8d; wMsgFilterMin
0x18002f2aa  xor     edx, edx; hWnd
0x18002f2ac  call    cs:__imp_GetMessageW
0x18002f2b2  test    eax, eax
0x18002f2b4  jnz     short loc_18002F237
0x18002f2b6  mov     eax, esi
0x18002f2b8  add     rsp, 68h
0x18002f2bc  pop     rdi
0x18002f2bd  pop     rsi
0x18002f2be  pop     rbx
0x18002f2bf  pop     rbp
0x18002f2c0  retn
```
