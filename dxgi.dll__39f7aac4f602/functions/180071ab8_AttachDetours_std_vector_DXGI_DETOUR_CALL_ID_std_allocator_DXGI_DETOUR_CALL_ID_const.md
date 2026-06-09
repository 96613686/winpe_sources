# AttachDetours(std::vector<DXGI_DETOUR_CALL_ID,std::allocator<DXGI_DETOUR_CALL_ID>> const &)

- ea: `0x180071ab8`
- end: `0x180071cde`
- name: `?AttachDetours@@YAJAEBV?$vector@W4DXGI_DETOUR_CALL_ID@@V?$allocator@W4DXGI_DETOUR_CALL_ID@@@std@@@std@@@Z`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180071a24`

## callees

- `0x18000c6b0`
- `0x180071ab8`
- `0x1800734e8`
- `0x180078690`
- `0x180078800`
- `0x1800788c0`
- `0x180078ed0`
- `0x180078f90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071ae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071b1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071c81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071cac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071ae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071b1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071c81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180071cac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180071b09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180071b09`

## string_xrefs

- `0x180071b38`: `DetourUpdateThread failed`
- `0x180071baf`: `QueryDisplayConfig`
- `0x180071cc5`: `DetourTransactionCommit failed unexpectedly`

## pseudocode

```c
__int64 __fastcall AttachDetours(__int64 a1)
{
  signed int LastError; // eax
  CModule *v4; // rcx
  signed int v5; // ebx
  const char *v6; // r8
  HANDLE CurrentThread; // rax
  signed int v8; // eax
  _BYTE *v9; // rdi
  _BYTE *v10; // rbp
  unsigned __int64 v11; // rcx
  int v12; // esi
  HDC (__fastcall *v13)(HWND); // r9
  void **v14; // r8
  const char *v15; // rdx
  const char *v16; // rcx
  const char *v17; // rcx
  signed int v18; // eax
  signed int v19; // eax

  if ( (unsigned int)DetourIsHelperProcess() )
    return 2147942405LL;
  if ( (unsigned int)DetourTransactionBegin() )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 < 0 )
    {
      v6 = "DetourTransactionBegin failed";
      goto LABEL_42;
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
      v6 = "DetourUpdateThread failed";
      goto LABEL_42;
    }
    return (unsigned int)v5;
  }
  v9 = *(_BYTE **)a1;
  v5 = 0;
  v10 = *(_BYTE **)(a1 + 8);
  if ( *(_BYTE **)a1 == v10 )
    goto LABEL_37;
  do
  {
    v11 = (unsigned __int8)*v9;
    v12 = 1 << v11;
    if ( ((1 << v11) & dword_180108A7C) != 0 )
      goto LABEL_30;
    if ( !*v9 )
    {
      if ( v5 < 0 )
        goto LABEL_30;
      v13 = My_GetDC;
      v14 = &Real_GetDC;
      v15 = "GetDC";
      goto LABEL_28;
    }
    v11 = (unsigned int)(v11 - 1);
    if ( !(_DWORD)v11 )
    {
      if ( v5 < 0 )
        goto LABEL_30;
      v5 = AttachHelper((const char *)v11, "EnumDisplaySettingsA", &Real_EnumDisplaySettingsA, My_EnumDisplaySettingsA);
      if ( v5 < 0 )
        goto LABEL_30;
      v5 = AttachHelper(v16, "EnumDisplaySettingsW", &Real_EnumDisplaySettingsW, My_EnumDisplaySettingsW);
      if ( v5 < 0 )
        goto LABEL_30;
      v5 = AttachHelper(v17, "EnumDisplaySettingsExA", &Real_EnumDisplaySettingsExA, My_EnumDisplaySettingsExA);
      if ( v5 < 0 )
        goto LABEL_30;
      v13 = (HDC (__fastcall *)(HWND))My_EnumDisplaySettingsExW;
      v14 = (void **)&Real_EnumDisplaySettingsExW;
      v15 = "EnumDisplaySettingsExW";
      goto LABEL_28;
    }
    if ( (_DWORD)v11 != 1 )
    {
      v5 = -2147024809;
      CModule::RecordJournalImpl((CModule *)v11, -2147024809, "Invalid detour call ID");
      goto LABEL_30;
    }
    if ( v5 >= 0 )
    {
      v13 = (HDC (__fastcall *)(HWND))My_QueryDisplayConfig;
      v14 = (void **)&Real_QueryDisplayConfig;
      v15 = "QueryDisplayConfig";
LABEL_28:
      v5 = AttachHelper((const char *)v11, v15, v14, v13);
      if ( v5 >= 0 )
        dword_180108A7C |= v12;
    }
LABEL_30:
    ++v9;
  }
  while ( v9 != v10 );
  if ( v5 < 0 )
  {
    if ( (unsigned int)DetourTransactionAbort() )
    {
      v18 = GetLastError();
      v5 = v18;
      if ( v18 > 0 )
        v5 = (unsigned __int16)v18 | 0x80070000;
      if ( v5 < 0 )
      {
        v6 = "DetourTransactionAbort failed unexpectedly";
        goto LABEL_42;
      }
    }
    return (unsigned int)v5;
  }
LABEL_37:
  if ( (unsigned int)DetourTransactionCommit() )
  {
    v19 = GetLastError();
    v5 = v19;
    if ( v19 > 0 )
      v5 = (unsigned __int16)v19 | 0x80070000;
    if ( v5 < 0 )
    {
      v6 = "DetourTransactionCommit failed unexpectedly";
LABEL_42:
      CModule::RecordJournalImpl(v4, v5, v6);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180071ab8  push    rbx
0x180071aba  push    rbp
0x180071abb  push    rsi
0x180071abc  push    rdi
0x180071abd  sub     rsp, 28h
0x180071ac1  mov     rsi, rcx
0x180071ac4  call    DetourIsHelperProcess
0x180071ac9  test    eax, eax
0x180071acb  jz      short loc_180071AD7
0x180071acd  mov     eax, 80070005h
0x180071ad2  jmp     loc_180071CD5
0x180071ad7  call    DetourTransactionBegin
0x180071adc  test    eax, eax
0x180071ade  jz      short loc_180071B09
0x180071ae0  call    cs:__imp_GetLastError
0x180071ae6  mov     ebx, eax
0x180071ae8  test    eax, eax
0x180071aea  jle     short loc_180071AF5
0x180071aec  movzx   ebx, ax
0x180071aef  or      ebx, 80070000h
0x180071af5  test    ebx, ebx
0x180071af7  jns     loc_180071CD3
0x180071afd  lea     r8, aDetourtransact_2; "DetourTransactionBegin failed"
0x180071b04  jmp     loc_180071CCC
0x180071b09  call    cs:__imp_GetCurrentThread
0x180071b0f  mov     rcx, rax; hThread
0x180071b12  call    DetourUpdateThread
0x180071b17  test    eax, eax
0x180071b19  jz      short loc_180071B44
0x180071b1b  call    cs:__imp_GetLastError
0x180071b21  mov     ebx, eax
0x180071b23  test    eax, eax
0x180071b25  jle     short loc_180071B30
0x180071b27  movzx   ebx, ax
0x180071b2a  or      ebx, 80070000h
0x180071b30  test    ebx, ebx
0x180071b32  jns     loc_180071CD3
0x180071b38  lea     r8, aDetourupdateth; "DetourUpdateThread failed"
0x180071b3f  jmp     loc_180071CCC
0x180071b44  mov     rdi, [rsi]
0x180071b47  xor     ebx, ebx
0x180071b49  mov     rbp, [rsi+8]
0x180071b4d  cmp     rdi, rbp
0x180071b50  jz      loc_180071CA3
0x180071b56  movzx   ecx, byte ptr [rdi]; char *
0x180071b59  mov     esi, 1
0x180071b5e  shl     esi, cl
0x180071b60  test    cs:dword_180108A7C, esi
0x180071b66  jnz     loc_180071C68
0x180071b6c  test    ecx, ecx
0x180071b6e  jz      loc_180071C3E
0x180071b74  sub     ecx, 1; char *
0x180071b77  jz      short loc_180071BBB
0x180071b79  cmp     ecx, 1
0x180071b7c  jz      short loc_180071B99
0x180071b7e  lea     r8, aInvalidDetourC; "Invalid detour call ID"
0x180071b85  mov     edx, 80070057h; unsigned int
0x180071b8a  mov     ebx, 80070057h
0x180071b8f  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180071b94  jmp     loc_180071C68
0x180071b99  test    ebx, ebx
0x180071b9b  js      loc_180071C68
0x180071ba1  lea     r9, ?My_QueryDisplayConfig@@YAJIPEAIPEAUDISPLAYCONFIG_PATH_INFO@@0PEAUDISPLAYCONFIG_MODE_INFO@@PEAW4DISPLAYCONFIG_TOPOLOGY_ID@@@Z; My_QueryDisplayConfig(uint,uint *,DISPLAYCONFIG_PATH_INFO *,uint *,DISPLAYCONFIG_MODE_INFO *,DISPLAYCONFIG_TOPOLOGY_ID *)
0x180071ba8  lea     r8, ?Real_QueryDisplayConfig@@3P6AJIPEAIPEAUDISPLAYCONFIG_PATH_INFO@@0PEAUDISPLAYCONFIG_MODE_INFO@@PEAW4DISPLAYCONFIG_TOPOLOGY_ID@@@ZEA; long (*Real_QueryDisplayConfig)(uint,uint *,DISPLAYCONFIG_PATH_INFO *,uint *,DISPLAYCONFIG_MODE_INFO *,DISPLAYCONFIG_TOPOLOGY_ID *)
0x180071baf  lea     rdx, aQuerydisplayco_0; "QueryDisplayConfig"
0x180071bb6  jmp     loc_180071C57
0x180071bbb  test    ebx, ebx
0x180071bbd  js      loc_180071C68
0x180071bc3  lea     r9, ?My_EnumDisplaySettingsA@@YAHPEBDKPEAU_devicemodeA@@@Z; void *
0x180071bca  lea     r8, ?Real_EnumDisplaySettingsA@@3P6AHPEBDKPEAU_devicemodeA@@@ZEA; void **
0x180071bd1  lea     rdx, aEnumdisplayset_2; "EnumDisplaySettingsA"
0x180071bd8  call    ?AttachHelper@@YAJPEBD0PEAPEAXPEAX@Z; AttachHelper(char const *,char const *,void * *,void *)
0x180071bdd  mov     ebx, eax
0x180071bdf  test    eax, eax
0x180071be1  js      loc_180071C68
0x180071be7  lea     r9, ?My_EnumDisplaySettingsW@@YAHPEBGKPEAU_devicemodeW@@@Z; void *
0x180071bee  lea     r8, ?Real_EnumDisplaySettingsW@@3P6AHPEBGKPEAU_devicemodeW@@@ZEA; void **
0x180071bf5  lea     rdx, aEnumdisplayset_1; "EnumDisplaySettingsW"
0x180071bfc  call    ?AttachHelper@@YAJPEBD0PEAPEAXPEAX@Z; AttachHelper(char const *,char const *,void * *,void *)
0x180071c01  mov     ebx, eax
0x180071c03  test    eax, eax
0x180071c05  js      short loc_180071C68
0x180071c07  lea     r9, ?My_EnumDisplaySettingsExA@@YAHPEBDKPEAU_devicemodeA@@K@Z; void *
0x180071c0e  lea     r8, ?Real_EnumDisplaySettingsExA@@3P6AHPEBDKPEAU_devicemodeA@@K@ZEA; void **
0x180071c15  lea     rdx, aEnumdisplayset_0; "EnumDisplaySettingsExA"
0x180071c1c  call    ?AttachHelper@@YAJPEBD0PEAPEAXPEAX@Z; AttachHelper(char const *,char const *,void * *,void *)
0x180071c21  mov     ebx, eax
0x180071c23  test    eax, eax
0x180071c25  js      short loc_180071C68
0x180071c27  lea     r9, ?My_EnumDisplaySettingsExW@@YAHPEBGKPEAU_devicemodeW@@K@Z; My_EnumDisplaySettingsExW(ushort const *,ulong,_devicemodeW *,ulong)
0x180071c2e  lea     r8, ?Real_EnumDisplaySettingsExW@@3P6AHPEBGKPEAU_devicemodeW@@K@ZEA; int (*Real_EnumDisplaySettingsExW)(ushort const *,ulong,_devicemodeW *,ulong)
0x180071c35  lea     rdx, aEnumdisplayset_3; "EnumDisplaySettingsExW"
0x180071c3c  jmp     short loc_180071C57
0x180071c3e  test    ebx, ebx
0x180071c40  js      short loc_180071C68
0x180071c42  lea     r9, ?My_GetDC@@YAPEAUHDC__@@PEAUHWND__@@@Z; void *
0x180071c49  lea     r8, ?Real_GetDC@@3P6APEAUHDC__@@PEAUHWND__@@@ZEA; void **
0x180071c50  lea     rdx, aGetdc_0; "GetDC"
0x180071c57  call    ?AttachHelper@@YAJPEBD0PEAPEAXPEAX@Z; AttachHelper(char const *,char const *,void * *,void *)
0x180071c5c  mov     ebx, eax
0x180071c5e  test    eax, eax
0x180071c60  js      short loc_180071C68
0x180071c62  or      cs:dword_180108A7C, esi
0x180071c68  inc     rdi
0x180071c6b  cmp     rdi, rbp
0x180071c6e  jnz     loc_180071B56
0x180071c74  test    ebx, ebx
0x180071c76  jns     short loc_180071CA3
0x180071c78  call    DetourTransactionAbort
0x180071c7d  test    eax, eax
0x180071c7f  jz      short loc_180071CD3
0x180071c81  call    cs:__imp_GetLastError
0x180071c87  mov     ebx, eax
0x180071c89  test    eax, eax
0x180071c8b  jle     short loc_180071C96
0x180071c8d  movzx   ebx, ax
0x180071c90  or      ebx, 80070000h
0x180071c96  test    ebx, ebx
0x180071c98  jns     short loc_180071CD3
0x180071c9a  lea     r8, aDetourtransact; "DetourTransactionAbort failed unexpecte"...
0x180071ca1  jmp     short loc_180071CCC
0x180071ca3  call    DetourTransactionCommit
0x180071ca8  test    eax, eax
0x180071caa  jz      short loc_180071CD3
0x180071cac  call    cs:__imp_GetLastError
0x180071cb2  mov     ebx, eax
0x180071cb4  test    eax, eax
0x180071cb6  jle     short loc_180071CC1
0x180071cb8  movzx   ebx, ax
0x180071cbb  or      ebx, 80070000h
0x180071cc1  test    ebx, ebx
0x180071cc3  jns     short loc_180071CD3
0x180071cc5  lea     r8, aDetourtransact_0; "DetourTransactionCommit failed unexpect"...
0x180071ccc  mov     edx, ebx; unsigned int
0x180071cce  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180071cd3  mov     eax, ebx
0x180071cd5  add     rsp, 28h
0x180071cd9  pop     rdi
0x180071cda  pop     rsi
0x180071cdb  pop     rbp
0x180071cdc  pop     rbx
0x180071cdd  retn
```
