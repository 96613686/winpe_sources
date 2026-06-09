# PeTerm

- ea: `0x18001cabc`
- end: `0x18001ccdc`
- name: `PeTerm`
- size: `544`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `2`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180016d50`
- `0x180017fb0`

## callees

- `0x180011e80`
- `0x1800139b0`
- `0x180015a3c`
- `0x180016838`
- `0x180016898`
- `0x18001c088`
- `0x18001cabc`
- `0x18003b6b8`
- `0x180040e50`
- `0x180040ef8`
- `0x180049614`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001cc90`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001cc90`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001cc87`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001cc87`
- `USER32!RemovePropW` at `0x18001ccd5`
- `USER32!SendMessageW` at `0x18001cb62`
- `USER32!SendMessageW` at `0x18001cbed`
- `USER32!SendMessageW` at `0x18001cb62`
- `USER32!SendMessageW` at `0x18001cbed`
- `USER32!GetParent` at `0x18001ccb6`
- `USER32!GetParent` at `0x18001ccb6`
- `rtutils!TracePrintfExA` at `0x18001cae5`
- `rtutils!TracePrintfExA` at `0x18001ccad`
- `rtutils!TracePrintfExA` at `0x18001cae5`
- `rtutils!TracePrintfExA` at `0x18001ccad`
- `SETUPAPI!SetupDiDestroyClassImageList` at `0x18001cc79`
- `SETUPAPI!SetupDiDestroyClassImageList` at `0x18001cc79`

## pseudocode

```c
HANDLE __fastcall PeTerm(HWND hWnd)
{
  __int64 *v2; // rax
  __int64 *v3; // rbx
  HWND v4; // rcx
  HWND v5; // rcx
  __int64 *v6; // rcx
  __int64 *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  HWND Parent; // rax

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "PeTerm");
  v2 = (__int64 *)AiContext(hWnd);
  v3 = v2;
  if ( v2 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(*v2 + 16) + 12LL) & 0x40000000) != 0 )
    {
      EuFree(*v2);
      *v3 = 0;
    }
    v4 = (HWND)v3[26];
    if ( v4 )
      GeClearLbDialAnotherFirst(v4);
    v5 = (HWND)v3[28];
    if ( v5 )
      GeClearLbVpnDestination(v5);
    v6 = (__int64 *)v3[177];
    if ( v6 )
      DtlDestroyList(v6, (void (__fastcall *)(__int64))DestroyPszNode);
    SendMessageW((HWND)v3[7], 0x1009u, 0, 0);
    if ( *((_DWORD *)v3 + 506) )
    {
      DeannotateLVCheckBoxForAcc(v3[7]);
      *((_DWORD *)v3 + 506) = 0;
    }
    v7 = (__int64 *)v3[73];
    if ( v7 )
      DtlDestroyList(v7, (void (__fastcall *)(__int64))DestroyEapcfgNode);
    if ( *((_DWORD *)v3 + 330) )
      CuFree(v3 + 148);
    if ( *((_DWORD *)v3 + 350) )
      SuFree(v3 + 166);
    v8 = v3[186];
    if ( v8 )
    {
      *(_QWORD *)(v8 + 16) = 0;
      ReleaseObj(v3[186]);
    }
    SendMessageW((HWND)v3[67], 0x1009u, 0, 0);
    if ( *((_DWORD *)v3 + 507) )
    {
      DeannotateLVCheckBoxForAcc(v3[67]);
      *((_DWORD *)v3 + 507) = 0;
    }
    v9 = v3[185];
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      v3[185] = 0;
    }
    v10 = v3[180];
    if ( v10 )
    {
      HrUninitializeAndReleaseINetCfg(*((unsigned int *)v3 + 362), v10, 0);
      v3[180] = 0;
      *((_DWORD *)v3 + 362) = 0;
    }
    v11 = v3[187];
    if ( v11 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      v3[187] = 0;
    }
    SetupDiDestroyClassImageList((PSP_CLASSIMAGELIST_DATA)(v3 + 182));
    if ( *((_DWORD *)v3 + 508) )
      CoUninitialize();
    GlobalFree(v3);
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Context freed");
  }
  Parent = GetParent(hWnd);
  return RemovePropW(Parent, g_contextId);
}

```

## disassembly

```asm
0x18001cabc  mov     [rsp+arg_0], rbx
0x18001cac1  mov     [rsp+arg_8], rsi
0x18001cac6  push    rdi
0x18001cac7  sub     rsp, 20h
0x18001cacb  mov     rdi, rcx
0x18001cace  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001cad4  cmp     ecx, 0FFFFFFFFh
0x18001cad7  jz      short loc_18001CAEB
0x18001cad9  lea     r8, aPeterm; "PeTerm"
0x18001cae0  mov     edx, 0Ch; dwFlags
0x18001cae5  call    cs:__imp_TracePrintfExA
0x18001caeb  mov     rcx, rdi
0x18001caee  call    AiContext
0x18001caf3  xor     esi, esi
0x18001caf5  mov     rbx, rax
0x18001caf8  test    rax, rax
0x18001cafb  jz      loc_18001CCB3
0x18001cb01  mov     rcx, [rax]
0x18001cb04  mov     rdx, [rcx+10h]
0x18001cb08  test    dword ptr [rdx+0Ch], 40000000h
0x18001cb0f  jz      short loc_18001CB19
0x18001cb11  call    EuFree
0x18001cb16  mov     [rbx], rsi
0x18001cb19  mov     rcx, [rbx+0D0h]; hWnd
0x18001cb20  test    rcx, rcx
0x18001cb23  jz      short loc_18001CB2A
0x18001cb25  call    GeClearLbDialAnotherFirst
0x18001cb2a  mov     rcx, [rbx+0E0h]; hWnd
0x18001cb31  test    rcx, rcx
0x18001cb34  jz      short loc_18001CB3B
0x18001cb36  call    GeClearLbVpnDestination
0x18001cb3b  mov     rcx, [rbx+588h]; hMem
0x18001cb42  test    rcx, rcx
0x18001cb45  jz      short loc_18001CB53
0x18001cb47  lea     rdx, DestroyPszNode
0x18001cb4e  call    DtlDestroyList
0x18001cb53  mov     rcx, [rbx+38h]; hWnd
0x18001cb57  xor     r9d, r9d; lParam
0x18001cb5a  xor     r8d, r8d; wParam
0x18001cb5d  mov     edx, 1009h; Msg
0x18001cb62  call    cs:__imp_SendMessageW
0x18001cb68  cmp     [rbx+7E8h], esi
0x18001cb6e  jz      short loc_18001CB7F
0x18001cb70  mov     rcx, [rbx+38h]
0x18001cb74  call    DeannotateLVCheckBoxForAcc
0x18001cb79  mov     [rbx+7E8h], esi
0x18001cb7f  mov     rcx, [rbx+248h]; hMem
0x18001cb86  test    rcx, rcx
0x18001cb89  jz      short loc_18001CB97
0x18001cb8b  lea     rdx, DestroyEapcfgNode
0x18001cb92  call    DtlDestroyList
0x18001cb97  cmp     [rbx+528h], esi
0x18001cb9d  jz      short loc_18001CBAB
0x18001cb9f  lea     rcx, [rbx+4A0h]
0x18001cba6  call    CuFree
0x18001cbab  cmp     [rbx+578h], esi
0x18001cbb1  jz      short loc_18001CBBF
0x18001cbb3  lea     rcx, [rbx+530h]
0x18001cbba  call    SuFree
0x18001cbbf  mov     rax, [rbx+5D0h]
0x18001cbc6  test    rax, rax
0x18001cbc9  jz      short loc_18001CBDB
0x18001cbcb  mov     [rax+10h], rsi
0x18001cbcf  mov     rcx, [rbx+5D0h]
0x18001cbd6  call    ReleaseObj
0x18001cbdb  mov     rcx, [rbx+218h]; hWnd
0x18001cbe2  xor     r9d, r9d; lParam
0x18001cbe5  xor     r8d, r8d; wParam
0x18001cbe8  mov     edx, 1009h; Msg
0x18001cbed  call    cs:__imp_SendMessageW
0x18001cbf3  cmp     [rbx+7ECh], esi
0x18001cbf9  jz      short loc_18001CC0D
0x18001cbfb  mov     rcx, [rbx+218h]
0x18001cc02  call    DeannotateLVCheckBoxForAcc
0x18001cc07  mov     [rbx+7ECh], esi
0x18001cc0d  mov     rcx, [rbx+5C8h]
0x18001cc14  test    rcx, rcx
0x18001cc17  jz      short loc_18001CC2C
0x18001cc19  mov     rax, [rcx]
0x18001cc1c  mov     rax, [rax+10h]
0x18001cc20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc25  mov     [rbx+5C8h], rsi
0x18001cc2c  mov     rdx, [rbx+5A0h]
0x18001cc33  test    rdx, rdx
0x18001cc36  jz      short loc_18001CC53
0x18001cc38  mov     ecx, [rbx+5A8h]
0x18001cc3e  xor     r8d, r8d
0x18001cc41  call    HrUninitializeAndReleaseINetCfg
0x18001cc46  mov     [rbx+5A0h], rsi
0x18001cc4d  mov     [rbx+5A8h], esi
0x18001cc53  mov     rcx, [rbx+5D8h]
0x18001cc5a  test    rcx, rcx
0x18001cc5d  jz      short loc_18001CC72
0x18001cc5f  mov     rax, [rcx]
0x18001cc62  mov     rax, [rax+10h]
0x18001cc66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc6b  mov     [rbx+5D8h], rsi
0x18001cc72  lea     rcx, [rbx+5B0h]; ClassImageListData
0x18001cc79  call    cs:__imp_SetupDiDestroyClassImageList
0x18001cc7f  cmp     [rbx+7F0h], esi
0x18001cc85  jz      short loc_18001CC8D
0x18001cc87  call    cs:__imp_CoUninitialize
0x18001cc8d  mov     rcx, rbx; hMem
0x18001cc90  call    cs:__imp_GlobalFree
0x18001cc96  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001cc9c  cmp     ecx, 0FFFFFFFFh
0x18001cc9f  jz      short loc_18001CCB3
0x18001cca1  lea     r8, aContextFreed; "Context freed"
0x18001cca8  mov     edx, 0Ch; dwFlags
0x18001ccad  call    cs:__imp_TracePrintfExA
0x18001ccb3  mov     rcx, rdi; hWnd
0x18001ccb6  call    cs:__imp_GetParent
0x18001ccbc  mov     rdx, cs:g_contextId
0x18001ccc3  mov     rcx, rax
0x18001ccc6  mov     rbx, [rsp+28h+arg_0]
0x18001cccb  mov     rsi, [rsp+28h+arg_8]
0x18001ccd0  add     rsp, 20h
0x18001ccd4  pop     rdi
0x18001ccd5  jmp     cs:__imp_RemovePropW
```
