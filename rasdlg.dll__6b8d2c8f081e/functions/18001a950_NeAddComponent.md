# NeAddComponent

- ea: `0x18001a950`
- end: `0x18001a9d5`
- name: `NeAddComponent`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a9e0`

## callees

- `0x18001a950`
- `0x18001b048`
- `0x18001b134`
- `0x18001b30c`
- `0x18001b388`

## import_xrefs

- `USER32!PostMessageW` at `0x18001a9a1`
- `USER32!PostMessageW` at `0x18001a9a1`
- `rtutils!TracePrintfExA` at `0x18001a974`
- `rtutils!TracePrintfExA` at `0x18001a974`

## string_xrefs

- `0x18001a968`: `NeAddComponent`

## pseudocode

```c
__int64 __fastcall NeAddComponent(__int64 a1)
{
  __int64 result; // rax
  int v3; // edi
  __int64 v4; // rcx

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "NeAddComponent");
  result = NeModifySettings(a1, 0, 0);
  v3 = result;
  if ( (int)result >= 0 && (_DWORD)result != 1 )
  {
    PostMessageW(*(HWND *)(a1 + 8), 0x46Bu, 0, 0);
    NeSaveBindingChanges(a1);
    result = NeReLoadNetworkComponents(v4, a1, 0);
    if ( v3 == 303136 )
      return NeRequestReboot(a1);
  }
  return result;
}

```

## disassembly

```asm
0x18001a950  mov     [rsp+arg_0], rbx
0x18001a955  push    rdi
0x18001a956  sub     rsp, 20h
0x18001a95a  mov     rbx, rcx
0x18001a95d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001a963  cmp     ecx, 0FFFFFFFFh
0x18001a966  jz      short loc_18001A97A
0x18001a968  lea     r8, aNeaddcomponent; "NeAddComponent"
0x18001a96f  mov     edx, 0Ch; dwFlags
0x18001a974  call    cs:__imp_TracePrintfExA
0x18001a97a  xor     r8d, r8d
0x18001a97d  xor     edx, edx
0x18001a97f  mov     rcx, rbx
0x18001a982  call    NeModifySettings
0x18001a987  mov     edi, eax
0x18001a989  test    eax, eax
0x18001a98b  js      short loc_18001A9CA
0x18001a98d  cmp     eax, 1
0x18001a990  jz      short loc_18001A9CA
0x18001a992  mov     rcx, [rbx+8]; hWnd
0x18001a996  xor     r9d, r9d; lParam
0x18001a999  xor     r8d, r8d; wParam
0x18001a99c  mov     edx, 46Bh; Msg
0x18001a9a1  call    cs:__imp_PostMessageW
0x18001a9a7  mov     rcx, rbx
0x18001a9aa  call    NeSaveBindingChanges
0x18001a9af  xor     r8d, r8d
0x18001a9b2  mov     rdx, rbx
0x18001a9b5  call    NeReLoadNetworkComponents
0x18001a9ba  cmp     edi, 4A020h
0x18001a9c0  jnz     short loc_18001A9CA
0x18001a9c2  mov     rcx, rbx
0x18001a9c5  call    NeRequestReboot
0x18001a9ca  mov     rbx, [rsp+28h+arg_0]
0x18001a9cf  add     rsp, 20h
0x18001a9d3  pop     rdi
0x18001a9d4  retn
```
