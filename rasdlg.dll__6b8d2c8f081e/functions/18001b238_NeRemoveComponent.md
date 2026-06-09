# NeRemoveComponent

- ea: `0x18001b238`
- end: `0x18001b305`
- name: `NeRemoveComponent`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a9e0`

## callees

- `0x18001b048`
- `0x18001b134`
- `0x18001b238`
- `0x18001b30c`
- `0x18001b388`
- `0x18002797c`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b2f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b2f4`
- `USER32!PostMessageW` at `0x18001b2c6`
- `USER32!PostMessageW` at `0x18001b2c6`
- `rtutils!TracePrintfExA` at `0x18001b265`
- `rtutils!TracePrintfExA` at `0x18001b265`

## string_xrefs

- `0x18001b259`: `NeRemoveComponent`

## pseudocode

```c
void __fastcall NeRemoveComponent(__int64 a1)
{
  __int64 v2; // rax
  int v3; // eax
  int v4; // edi
  __int64 v5; // rcx
  LPVOID pv; // [rsp+30h] [rbp+8h] BYREF

  pv = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "NeRemoveComponent");
  v2 = PComponentFromCurSel(*(HWND *)(a1 + 536));
  if ( v2 && (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v2 + 48LL))(v2, &pv) >= 0 )
  {
    v3 = NeModifySettings(a1, pv, 1);
    v4 = v3;
    if ( v3 >= 0 && v3 != 1 )
    {
      PostMessageW(*(HWND *)(a1 + 8), 0x46Bu, 0, 0);
      NeSaveBindingChanges(a1);
      NeReLoadNetworkComponents(v5, a1, 0);
      if ( v4 == 303136 )
        NeRequestReboot(a1);
    }
    CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x18001b238  mov     [rsp+arg_8], rbx
0x18001b23d  push    rdi
0x18001b23e  sub     rsp, 20h
0x18001b242  mov     rbx, rcx
0x18001b245  mov     [rsp+28h+pv], 0
0x18001b24e  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001b254  cmp     ecx, 0FFFFFFFFh
0x18001b257  jz      short loc_18001B26B
0x18001b259  lea     r8, aNeremovecompon; "NeRemoveComponent"
0x18001b260  mov     edx, 0Ch; dwFlags
0x18001b265  call    cs:__imp_TracePrintfExA
0x18001b26b  mov     rcx, [rbx+218h]; hWnd
0x18001b272  xor     edx, edx
0x18001b274  call    PComponentFromCurSel
0x18001b279  mov     r8, rax
0x18001b27c  test    rax, rax
0x18001b27f  jz      short loc_18001B2FA
0x18001b281  mov     rcx, [rax]
0x18001b284  lea     rdx, [rsp+28h+pv]
0x18001b289  mov     rax, [rcx+30h]
0x18001b28d  mov     rcx, r8
0x18001b290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b295  test    eax, eax
0x18001b297  js      short loc_18001B2FA
0x18001b299  mov     rdx, [rsp+28h+pv]
0x18001b29e  mov     r8d, 1
0x18001b2a4  mov     rcx, rbx
0x18001b2a7  call    NeModifySettings
0x18001b2ac  mov     edi, eax
0x18001b2ae  test    eax, eax
0x18001b2b0  js      short loc_18001B2EF
0x18001b2b2  cmp     eax, 1
0x18001b2b5  jz      short loc_18001B2EF
0x18001b2b7  mov     rcx, [rbx+8]; hWnd
0x18001b2bb  xor     r9d, r9d; lParam
0x18001b2be  xor     r8d, r8d; wParam
0x18001b2c1  mov     edx, 46Bh; Msg
0x18001b2c6  call    cs:__imp_PostMessageW
0x18001b2cc  mov     rcx, rbx
0x18001b2cf  call    NeSaveBindingChanges
0x18001b2d4  xor     r8d, r8d
0x18001b2d7  mov     rdx, rbx
0x18001b2da  call    NeReLoadNetworkComponents
0x18001b2df  cmp     edi, 4A020h
0x18001b2e5  jnz     short loc_18001B2EF
0x18001b2e7  mov     rcx, rbx
0x18001b2ea  call    NeRequestReboot
0x18001b2ef  mov     rcx, [rsp+28h+pv]; pv
0x18001b2f4  call    cs:__imp_CoTaskMemFree
0x18001b2fa  mov     rbx, [rsp+28h+arg_8]
0x18001b2ff  add     rsp, 20h
0x18001b303  pop     rdi
0x18001b304  retn
```
