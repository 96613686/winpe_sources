# DetachDetours(std::vector<DXGI_DETOUR_CALL_ID,std::allocator<DXGI_DETOUR_CALL_ID>> const &)

- ea: `0x18001f108`
- end: `0x18001f29d`
- name: `?DetachDetours@@YAJAEBV?$vector@W4DXGI_DETOUR_CALL_ID@@V?$allocator@W4DXGI_DETOUR_CALL_ID@@@std@@@std@@@Z`
- size: `405`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001f060`
- `0x18001fefc`

## callees

- `0x18000c6b0`
- `0x18001f108`
- `0x180074998`
- `0x180078800`
- `0x1800788c0`
- `0x180078ed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f12b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f16b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f12b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f16b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f269`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f159`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f159`

## string_xrefs

- `0x18001f286`: `DetourTransactionCommit failed unexpectedly`
- `0x18001f184`: `DetourUpdateThread failed unexpectedly`

## pseudocode

```c
__int64 __fastcall DetachDetours(__int64 a1)
{
  __int64 result; // rax
  signed int LastError; // eax
  CModule *v4; // rcx
  signed int v5; // ebx
  const char *v6; // r8
  HANDLE CurrentThread; // rax
  signed int v8; // eax
  _BYTE *v9; // rbx
  int v10; // esi
  _BYTE *v11; // rbp
  unsigned int v12; // edi
  int v13; // eax
  unsigned __int64 v14; // rcx
  HDC (__fastcall *v15)(HWND); // r8
  void **v16; // rdx
  const char *v17; // rcx
  const char *v18; // rcx
  signed int v19; // eax

  result = (unsigned int)g_cDetourCallsActive;
  if ( !g_cDetourCallsActive )
    return result;
  if ( (unsigned int)DetourTransactionBegin() )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
    {
      v6 = "DetourTransactionBegin failed unexpectedly";
      goto LABEL_7;
    }
    return (unsigned int)v5;
  }
  CurrentThread = GetCurrentThread();
  if ( (unsigned int)DetourUpdateThread(CurrentThread) )
  {
    v8 = GetLastError();
    v5 = v8;
    if ( v8 > 0 )
      v5 = (unsigned __int16)v8 | 0x80070000;
    if ( v5 < 0 )
    {
      v6 = "DetourUpdateThread failed unexpectedly";
      goto LABEL_7;
    }
    return (unsigned int)v5;
  }
  v9 = *(_BYTE **)a1;
  v10 = 0;
  v11 = *(_BYTE **)(a1 + 8);
  while ( v9 != v11 )
  {
    v12 = (unsigned __int8)*v9;
    v13 = dword_180108A7C;
    if ( !_bittest(&v13, v12) )
      goto LABEL_25;
    v14 = (unsigned __int8)*v9;
    if ( *v9 )
    {
      v14 = (unsigned int)(v14 - 1);
      if ( (_DWORD)v14 )
      {
        if ( (_DWORD)v14 != 1 )
        {
          v10 = -2147024809;
          CModule::RecordJournalImpl((CModule *)v14, -2147024809, "Invalid detour call ID");
          goto LABEL_25;
        }
        v15 = (HDC (__fastcall *)(HWND))My_QueryDisplayConfig;
        v16 = (void **)&Real_QueryDisplayConfig;
      }
      else
      {
        DetachHelper((const char *)v14, &Real_EnumDisplaySettingsA, My_EnumDisplaySettingsA);
        DetachHelper(v17, &Real_EnumDisplaySettingsW, My_EnumDisplaySettingsW);
        DetachHelper(v18, &Real_EnumDisplaySettingsExA, My_EnumDisplaySettingsExA);
        v15 = (HDC (__fastcall *)(HWND))My_EnumDisplaySettingsExW;
        v16 = (void **)&Real_EnumDisplaySettingsExW;
      }
    }
    else
    {
      v15 = My_GetDC;
      v16 = &Real_GetDC;
    }
    DetachHelper((const char *)v14, v16, v15);
    if ( v10 >= 0 )
      dword_180108A7C &= -2 << v12;
LABEL_25:
    ++v9;
  }
  if ( !(unsigned int)DetourTransactionCommit() )
    return (unsigned int)v10;
  v19 = GetLastError();
  v5 = v19;
  if ( v19 > 0 )
    v5 = (unsigned __int16)v19 | 0x80070000;
  if ( v5 < 0 )
  {
    v6 = "DetourTransactionCommit failed unexpectedly";
LABEL_7:
    CModule::RecordJournalImpl(v4, v5, v6);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001f108  push    rbx
0x18001f10a  push    rbp
0x18001f10b  push    rsi
0x18001f10c  push    rdi
0x18001f10d  sub     rsp, 28h
0x18001f111  mov     eax, cs:?g_cDetourCallsActive@@3JC; long volatile g_cDetourCallsActive
0x18001f117  mov     rdi, rcx
0x18001f11a  test    eax, eax
0x18001f11c  jz      loc_18001F294
0x18001f122  call    DetourTransactionBegin
0x18001f127  test    eax, eax
0x18001f129  jz      short loc_18001F159
0x18001f12b  call    cs:__imp_GetLastError
0x18001f131  mov     ebx, eax
0x18001f133  test    eax, eax
0x18001f135  jle     short loc_18001F140
0x18001f137  movzx   ebx, ax
0x18001f13a  or      ebx, 80070000h
0x18001f140  test    ebx, ebx
0x18001f142  jns     short loc_18001F152
0x18001f144  lea     r8, aDetourtransact_1; "DetourTransactionBegin failed unexpecte"...
0x18001f14b  mov     edx, ebx; unsigned int
0x18001f14d  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18001f152  mov     eax, ebx
0x18001f154  jmp     loc_18001F294
0x18001f159  call    cs:__imp_GetCurrentThread
0x18001f15f  mov     rcx, rax; hThread
0x18001f162  call    DetourUpdateThread
0x18001f167  test    eax, eax
0x18001f169  jz      short loc_18001F18D
0x18001f16b  call    cs:__imp_GetLastError
0x18001f171  mov     ebx, eax
0x18001f173  test    eax, eax
0x18001f175  jle     short loc_18001F180
0x18001f177  movzx   ebx, ax
0x18001f17a  or      ebx, 80070000h
0x18001f180  test    ebx, ebx
0x18001f182  jns     short loc_18001F152
0x18001f184  lea     r8, aDetourupdateth_0; "DetourUpdateThread failed unexpectedly"
0x18001f18b  jmp     short loc_18001F14B
0x18001f18d  mov     rbx, [rdi]
0x18001f190  xor     esi, esi
0x18001f192  mov     rbp, [rdi+8]
0x18001f196  jmp     loc_18001F257
0x18001f19b  movzx   edi, byte ptr [rbx]
0x18001f19e  mov     eax, cs:dword_180108A7C
0x18001f1a4  bt      eax, edi
0x18001f1a7  jnb     loc_18001F254
0x18001f1ad  mov     ecx, edi; char *
0x18001f1af  test    edi, edi
0x18001f1b1  jz      short loc_18001F22E
0x18001f1b3  sub     ecx, 1; char *
0x18001f1b6  jz      short loc_18001F1E5
0x18001f1b8  cmp     ecx, 1
0x18001f1bb  jz      short loc_18001F1D5
0x18001f1bd  lea     r8, aInvalidDetourC; "Invalid detour call ID"
0x18001f1c4  mov     edx, 80070057h; unsigned int
0x18001f1c9  mov     esi, 80070057h
0x18001f1ce  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18001f1d3  jmp     short loc_18001F254
0x18001f1d5  lea     r8, ?My_QueryDisplayConfig@@YAJIPEAIPEAUDISPLAYCONFIG_PATH_INFO@@0PEAUDISPLAYCONFIG_MODE_INFO@@PEAW4DISPLAYCONFIG_TOPOLOGY_ID@@@Z; My_QueryDisplayConfig(uint,uint *,DISPLAYCONFIG_PATH_INFO *,uint *,DISPLAYCONFIG_MODE_INFO *,DISPLAYCONFIG_TOPOLOGY_ID *)
0x18001f1dc  lea     rdx, ?Real_QueryDisplayConfig@@3P6AJIPEAIPEAUDISPLAYCONFIG_PATH_INFO@@0PEAUDISPLAYCONFIG_MODE_INFO@@PEAW4DISPLAYCONFIG_TOPOLOGY_ID@@@ZEA; long (*Real_QueryDisplayConfig)(uint,uint *,DISPLAYCONFIG_PATH_INFO *,uint *,DISPLAYCONFIG_MODE_INFO *,DISPLAYCONFIG_TOPOLOGY_ID *)
0x18001f1e3  jmp     short loc_18001F23C
0x18001f1e5  lea     r8, ?My_EnumDisplaySettingsA@@YAHPEBDKPEAU_devicemodeA@@@Z; void *
0x18001f1ec  lea     rdx, ?Real_EnumDisplaySettingsA@@3P6AHPEBDKPEAU_devicemodeA@@@ZEA; void **
0x18001f1f3  call    ?DetachHelper@@YAXPEBDPEAPEAXPEAX@Z; DetachHelper(char const *,void * *,void *)
0x18001f1f8  lea     r8, ?My_EnumDisplaySettingsW@@YAHPEBGKPEAU_devicemodeW@@@Z; void *
0x18001f1ff  lea     rdx, ?Real_EnumDisplaySettingsW@@3P6AHPEBGKPEAU_devicemodeW@@@ZEA; void **
0x18001f206  call    ?DetachHelper@@YAXPEBDPEAPEAXPEAX@Z; DetachHelper(char const *,void * *,void *)
0x18001f20b  lea     r8, ?My_EnumDisplaySettingsExA@@YAHPEBDKPEAU_devicemodeA@@K@Z; void *
0x18001f212  lea     rdx, ?Real_EnumDisplaySettingsExA@@3P6AHPEBDKPEAU_devicemodeA@@K@ZEA; void **
0x18001f219  call    ?DetachHelper@@YAXPEBDPEAPEAXPEAX@Z; DetachHelper(char const *,void * *,void *)
0x18001f21e  lea     r8, ?My_EnumDisplaySettingsExW@@YAHPEBGKPEAU_devicemodeW@@K@Z; My_EnumDisplaySettingsExW(ushort const *,ulong,_devicemodeW *,ulong)
0x18001f225  lea     rdx, ?Real_EnumDisplaySettingsExW@@3P6AHPEBGKPEAU_devicemodeW@@K@ZEA; int (*Real_EnumDisplaySettingsExW)(ushort const *,ulong,_devicemodeW *,ulong)
0x18001f22c  jmp     short loc_18001F23C
0x18001f22e  lea     r8, ?My_GetDC@@YAPEAUHDC__@@PEAUHWND__@@@Z; void *
0x18001f235  lea     rdx, ?Real_GetDC@@3P6APEAUHDC__@@PEAUHWND__@@@ZEA; void **
0x18001f23c  call    ?DetachHelper@@YAXPEBDPEAPEAXPEAX@Z; DetachHelper(char const *,void * *,void *)
0x18001f241  test    esi, esi
0x18001f243  js      short loc_18001F254
0x18001f245  mov     ecx, edi
0x18001f247  mov     eax, 0FFFFFFFEh
0x18001f24c  shl     eax, cl
0x18001f24e  and     cs:dword_180108A7C, eax
0x18001f254  inc     rbx
0x18001f257  cmp     rbx, rbp
0x18001f25a  jnz     loc_18001F19B
0x18001f260  call    DetourTransactionCommit
0x18001f265  test    eax, eax
0x18001f267  jz      short loc_18001F292
0x18001f269  call    cs:__imp_GetLastError
0x18001f26f  mov     ebx, eax
0x18001f271  test    eax, eax
0x18001f273  jle     short loc_18001F27E
0x18001f275  movzx   ebx, ax
0x18001f278  or      ebx, 80070000h
0x18001f27e  test    ebx, ebx
0x18001f280  jns     loc_18001F152
0x18001f286  lea     r8, aDetourtransact_0; "DetourTransactionCommit failed unexpect"...
0x18001f28d  jmp     loc_18001F14B
0x18001f292  mov     eax, esi
0x18001f294  add     rsp, 28h
0x18001f298  pop     rdi
0x18001f299  pop     rsi
0x18001f29a  pop     rbp
0x18001f29b  pop     rbx
0x18001f29c  retn
```
