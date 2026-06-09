# PeProvDlgApply

- ea: `0x18001c960`
- end: `0x18001cab4`
- name: `PeProvDlgApply`
- size: `340`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180017fb0`

## callees

- `0x18001c088`
- `0x18001c960`
- `0x180041c9c`
- `0x180048048`
- `0x180048f0c`

## import_xrefs

- `RASAPI32!UpdatePreferredVPNDestinationInRegistry` at `0x18001ca2d`
- `RASAPI32!UpdatePreferredVPNDestinationInRegistry` at `0x18001ca2d`
- `USER32!SendMessageW` at `0x18001c9cd`
- `USER32!SendMessageW` at `0x18001c9cd`
- `rtutils!TracePrintfExA` at `0x18001c985`
- `rtutils!TracePrintfExA` at `0x18001ca0e`
- `rtutils!TracePrintfExA` at `0x18001ca50`
- `rtutils!TracePrintfExA` at `0x18001c985`
- `rtutils!TracePrintfExA` at `0x18001ca0e`
- `rtutils!TracePrintfExA` at `0x18001ca50`

## string_xrefs

- `0x18001ca44`: `PeProvDlgApply: Update preference failed with %d`

## pseudocode

```c
__int64 __fastcall PeProvDlgApply(HWND a1)
{
  HWND *v2; // rax
  HWND *v3; // rbx
  HWND v4; // rcx
  int v5; // eax
  int v6; // esi
  HWND v7; // rdi
  LRESULT ItemDataPtr; // rax
  int updated; // eax
  __int64 v11; // rdx
  PCNZWCH *v12; // rcx

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "PeProvDlgApply");
  v2 = (HWND *)AiContext(a1);
  v3 = v2;
  if ( !v2 )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "PeProvDlgApply: Could not get page context");
    return 0;
  }
  v4 = v2[28];
  if ( v4 )
  {
    v5 = SendMessageW(v4, 0x147u, 0, 0);
    v6 = v5;
    if ( v5 != *((_DWORD *)v3 + 58) )
    {
      v7 = *v3;
      ItemDataPtr = ComboBox_GetItemDataPtr(v3[28], v5);
      if ( !ItemDataPtr )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "PeProvDlgApply: Could not get current selection data");
        return 0;
      }
      updated = UpdatePreferredVPNDestinationInRegistry(
                  *(_QWORD *)(*((_QWORD *)v7 + 109) + 8LL),
                  *(_QWORD *)(ItemDataPtr + 8),
                  *(unsigned int *)(*((_QWORD *)v7 + 8) + 8LL));
      if ( updated )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "PeProvDlgApply: Update preference failed with %d", updated);
        return 0;
      }
      *((_DWORD *)v3 + 58) = v6;
      v11 = *((_QWORD *)v7 + 109);
      v12 = (PCNZWCH *)*((_QWORD *)v7 + 8);
      *((_DWORD *)v7 + 390) = 1;
      if ( HrasconnFromEntry(*v12, *(PCNZWCH *)(v11 + 8)) )
        MsgDlgUtil(v3[1], 0xF4u, 0, g_hinstDll, 0x169u);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18001c960  push    rbx
0x18001c962  push    rbp
0x18001c963  push    rsi
0x18001c964  push    rdi
0x18001c965  sub     rsp, 38h
0x18001c969  mov     rbx, rcx
0x18001c96c  or      ebp, 0FFFFFFFFh
0x18001c96f  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001c975  cmp     ecx, ebp
0x18001c977  jz      short loc_18001C98B
0x18001c979  lea     r8, aPeprovdlgapply_0; "PeProvDlgApply"
0x18001c980  mov     edx, 0Ch; dwFlags
0x18001c985  call    cs:__imp_TracePrintfExA
0x18001c98b  mov     rcx, rbx
0x18001c98e  call    AiContext
0x18001c993  mov     rbx, rax
0x18001c996  test    rax, rax
0x18001c999  jnz     short loc_18001C9B2
0x18001c99b  mov     ecx, cs:g_dwTraceId
0x18001c9a1  cmp     ecx, ebp
0x18001c9a3  jz      loc_18001CA56
0x18001c9a9  lea     r8, aPeprovdlgapply; "PeProvDlgApply: Could not get page cont"...
0x18001c9b0  jmp     short loc_18001CA09
0x18001c9b2  mov     rcx, [rax+0E0h]; hWnd
0x18001c9b9  test    rcx, rcx
0x18001c9bc  jz      loc_18001CAA6
0x18001c9c2  xor     r9d, r9d; lParam
0x18001c9c5  xor     r8d, r8d; wParam
0x18001c9c8  mov     edx, 147h; Msg
0x18001c9cd  call    cs:__imp_SendMessageW
0x18001c9d3  mov     rsi, rax
0x18001c9d6  cmp     eax, [rbx+0E8h]
0x18001c9dc  jz      loc_18001CAA6
0x18001c9e2  mov     rcx, [rbx+0E0h]
0x18001c9e9  mov     edx, esi
0x18001c9eb  mov     rdi, [rbx]
0x18001c9ee  call    ComboBox_GetItemDataPtr
0x18001c9f3  test    rax, rax
0x18001c9f6  jnz     short loc_18001CA16
0x18001c9f8  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001c9fe  cmp     ecx, ebp
0x18001ca00  jz      short loc_18001CA56
0x18001ca02  lea     r8, aPeprovdlgapply_2; "PeProvDlgApply: Could not get current s"...
0x18001ca09  mov     edx, 0Ch; dwFlags
0x18001ca0e  call    cs:__imp_TracePrintfExA
0x18001ca14  jmp     short loc_18001CA56
0x18001ca16  mov     r8, [rdi+40h]
0x18001ca1a  mov     rcx, [rdi+368h]
0x18001ca21  mov     rdx, [rax+8]
0x18001ca25  mov     r8d, [r8+8]
0x18001ca29  mov     rcx, [rcx+8]
0x18001ca2d  call    cs:__imp_UpdatePreferredVPNDestinationInRegistry
0x18001ca33  test    eax, eax
0x18001ca35  jz      short loc_18001CA5A
0x18001ca37  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001ca3d  cmp     ecx, ebp
0x18001ca3f  jz      short loc_18001CA56
0x18001ca41  mov     r9d, eax
0x18001ca44  lea     r8, aPeprovdlgapply_1; "PeProvDlgApply: Update preference faile"...
0x18001ca4b  mov     edx, 0Ch; dwFlags
0x18001ca50  call    cs:__imp_TracePrintfExA
0x18001ca56  xor     eax, eax
0x18001ca58  jmp     short loc_18001CAAB
0x18001ca5a  mov     [rbx+0E8h], esi
0x18001ca60  mov     rdx, [rdi+368h]
0x18001ca67  mov     rcx, [rdi+40h]
0x18001ca6b  mov     dword ptr [rdi+618h], 1
0x18001ca75  mov     rdx, [rdx+8]; PCNZWCH
0x18001ca79  mov     rcx, [rcx]; lpString2
0x18001ca7c  call    HrasconnFromEntry
0x18001ca81  test    rax, rax
0x18001ca84  jz      short loc_18001CAA6
0x18001ca86  mov     r9, cs:g_hinstDll; hInstance
0x18001ca8d  xor     r8d, r8d; Arguments
0x18001ca90  mov     rcx, [rbx+8]; hWnd
0x18001ca94  mov     edx, 0F4h; uID
0x18001ca99  mov     [rsp+58h+var_38], 169h; UINT
0x18001caa1  call    MsgDlgUtil
0x18001caa6  mov     eax, 1
0x18001caab  add     rsp, 38h
0x18001caaf  pop     rdi
0x18001cab0  pop     rsi
0x18001cab1  pop     rbp
0x18001cab2  pop     rbx
0x18001cab3  retn
```
