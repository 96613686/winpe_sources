# DrSaveVPNDestinationPreference

- ea: `0x18000d1ac`
- end: `0x18000d28e`
- name: `DrSaveVPNDestinationPreference`
- size: `226`
- prototype: `int __fastcall(__int64 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000cbb0`

## callees

- `0x18000d1ac`
- `0x18003ce6c`
- `0x180048048`

## import_xrefs

- `RASAPI32!UpdatePreferredVPNDestinationInRegistry` at `0x18000d23c`
- `RASAPI32!UpdatePreferredVPNDestinationInRegistry` at `0x18000d23c`
- `USER32!SendMessageW` at `0x18000d1d0`
- `USER32!SendMessageW` at `0x18000d1d0`
- `rtutils!TracePrintfExA` at `0x18000d219`
- `rtutils!TracePrintfExA` at `0x18000d260`
- `rtutils!TracePrintfExA` at `0x18000d219`
- `rtutils!TracePrintfExA` at `0x18000d260`

## string_xrefs

- `0x18000d254`: `DrSaveVPNDestinationPreference: Registry update failed with %d`

## pseudocode

```c
int __fastcall DrSaveVPNDestinationPreference(__int64 **a1)
{
  __int64 v2; // rbp
  LRESULT ItemDataPtr; // rax
  int v4; // edi
  LRESULT v5; // rsi
  int updated; // eax

  v2 = **a1;
  LODWORD(ItemDataPtr) = SendMessageW((HWND)a1[30], 0x147u, 0, 0);
  v4 = ItemDataPtr;
  if ( (_DWORD)ItemDataPtr != -1 && (_DWORD)ItemDataPtr != *((_DWORD *)a1 + 44) )
  {
    ItemDataPtr = ComboBox_GetItemDataPtr((HWND)a1[30], ItemDataPtr);
    v5 = ItemDataPtr;
    if ( ItemDataPtr )
    {
      updated = UpdatePreferredVPNDestinationInRegistry(
                  *(_QWORD *)(*(_QWORD *)(v2 + 440) + 8LL),
                  *(_QWORD *)(*(_QWORD *)(ItemDataPtr + 8) + 16LL),
                  *(unsigned int *)(*(_QWORD *)(v2 + 32) + 8LL));
      if ( updated && g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "DrSaveVPNDestinationPreference: Registry update failed with %d", updated);
      LODWORD(ItemDataPtr) = StringCchCopyWrapW(
                               (wchar_t *)(v2 + 1006),
                               0x81u,
                               *(const wchar_t **)(*(_QWORD *)(v5 + 8) + 16LL));
      *((_DWORD *)a1 + 44) = v4;
    }
    else if ( g_dwTraceId != -1 )
    {
      LODWORD(ItemDataPtr) = TracePrintfExA(
                               g_dwTraceId,
                               0xCu,
                               "DrSaveVPNDestinationPreference: Could not get current selection data");
    }
  }
  return ItemDataPtr;
}

```

## disassembly

```asm
0x18000d1ac  push    rbx
0x18000d1ae  push    rbp
0x18000d1af  push    rsi
0x18000d1b0  push    rdi
0x18000d1b1  sub     rsp, 28h
0x18000d1b5  mov     rax, [rcx]
0x18000d1b8  mov     rbx, rcx
0x18000d1bb  mov     rcx, [rcx+0F0h]; hWnd
0x18000d1c2  xor     r9d, r9d; lParam
0x18000d1c5  xor     r8d, r8d; wParam
0x18000d1c8  mov     edx, 147h; Msg
0x18000d1cd  mov     rbp, [rax]
0x18000d1d0  call    cs:__imp_SendMessageW
0x18000d1d6  mov     rdi, rax
0x18000d1d9  cmp     eax, 0FFFFFFFFh
0x18000d1dc  jz      loc_18000D285
0x18000d1e2  cmp     edi, [rbx+0B0h]
0x18000d1e8  jz      loc_18000D285
0x18000d1ee  mov     rcx, [rbx+0F0h]
0x18000d1f5  mov     edx, edi
0x18000d1f7  call    ComboBox_GetItemDataPtr
0x18000d1fc  mov     rsi, rax
0x18000d1ff  test    rax, rax
0x18000d202  jnz     short loc_18000D221
0x18000d204  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000d20a  cmp     ecx, 0FFFFFFFFh
0x18000d20d  jz      short loc_18000D285
0x18000d20f  lea     r8, aDrsavevpndesti_0; "DrSaveVPNDestinationPreference: Could n"...
0x18000d216  lea     edx, [rax+0Ch]; dwFlags
0x18000d219  call    cs:__imp_TracePrintfExA
0x18000d21f  jmp     short loc_18000D285
0x18000d221  mov     r8, [rbp+20h]
0x18000d225  mov     rdx, [rax+8]
0x18000d229  mov     rcx, [rbp+1B8h]
0x18000d230  mov     r8d, [r8+8]
0x18000d234  mov     rdx, [rdx+10h]
0x18000d238  mov     rcx, [rcx+8]
0x18000d23c  call    cs:__imp_UpdatePreferredVPNDestinationInRegistry
0x18000d242  test    eax, eax
0x18000d244  jz      short loc_18000D266
0x18000d246  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18000d24c  cmp     ecx, 0FFFFFFFFh
0x18000d24f  jz      short loc_18000D266
0x18000d251  mov     r9d, eax
0x18000d254  lea     r8, aDrsavevpndesti; "DrSaveVPNDestinationPreference: Registr"...
0x18000d25b  mov     edx, 0Ch; dwFlags
0x18000d260  call    cs:__imp_TracePrintfExA
0x18000d266  mov     r8, [rsi+8]
0x18000d26a  lea     rcx, [rbp+3EEh]
0x18000d271  mov     edx, 81h
0x18000d276  mov     r8, [r8+10h]
0x18000d27a  call    StringCchCopyWrapW
0x18000d27f  mov     [rbx+0B0h], edi
0x18000d285  add     rsp, 28h
0x18000d289  pop     rdi
0x18000d28a  pop     rsi
0x18000d28b  pop     rbp
0x18000d28c  pop     rbx
0x18000d28d  retn
```
