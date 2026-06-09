# GeCommand

- ea: `0x1800168f8`
- end: `0x180016a6c`
- name: `GeCommand`
- size: `372`
- prototype: `_BOOL8 __fastcall(__int64, unsigned __int16, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180016d50`

## callees

- `0x180011be0`
- `0x180011cec`
- `0x1800166d4`
- `0x180016838`
- `0x1800168f8`
- `0x180016a74`
- `0x180016b98`
- `0x180016c34`
- `0x180017094`
- `0x180017e50`
- `0x180018184`
- `0x180018558`

## import_xrefs

- `USER32!SendMessageW` at `0x180016a00`
- `USER32!SendMessageW` at `0x180016a00`
- `USER32!EnableWindow` at `0x180016a2d`
- `USER32!EnableWindow` at `0x180016a2d`
- `rtutils!TracePrintfExA` at `0x180016931`
- `rtutils!TracePrintfExA` at `0x180016931`

## string_xrefs

- `0x18001691e`: `GeCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
_BOOL8 __fastcall GeCommand(__int64 a1, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  unsigned int v10; // ebx
  int v11; // eax
  __int64 v13; // rdx
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  BOOL v18; // edx

  v6 = a3;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "GeCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
  if ( v6 > 0x46B )
  {
    v14 = v6 - 1132;
    if ( v14 )
    {
      v15 = v14 - 4;
      if ( !v15 )
      {
        GeDialingRules(a1);
        return 1;
      }
      v16 = v15 - 291;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( !v17 )
        {
          if ( (unsigned int)SendMessageW(*(HWND *)(a1 + 200), 0xF0u, 0, 0) )
          {
            GeFillLbDialAnotherFirst(a1, 0);
            v18 = 1;
          }
          else
          {
            GeClearLbDialAnotherFirst(*(HWND *)(a1 + 208));
            v18 = 0;
          }
          EnableWindow(*(HWND *)(a1 + 208), v18);
          return 1;
        }
        if ( v17 == 1 && a2 == 1 )
        {
          GeDialAnotherFirstSelChange(a1);
          return 1;
        }
      }
      else if ( a2 == 512 )
      {
        GeValidateHostName(a1);
        return 1;
      }
      return 0;
    }
    v13 = 1;
LABEL_33:
    GeMoveDevice(a1, v13);
    return 1;
  }
  if ( v6 == 1131 )
  {
    v13 = 0;
    goto LABEL_33;
  }
  v7 = v6 - 1119;
  if ( !v7 )
  {
    GeUpdatePhoneNumberFields(a1, 1);
    return 1;
  }
  v8 = v7 - 2;
  if ( !v8 )
  {
    v11 = CuDialingRulesCbHandler(a1 + 1184);
    return v11 != 0;
  }
  v9 = v8 - 5;
  if ( !v9 )
  {
    v11 = CuCountryCodeLbHandler(a1 + 1184, a2);
    return v11 != 0;
  }
  v10 = v9 - 3;
  if ( !v10 )
  {
    GeAlternates(a1);
    return 1;
  }
  if ( v10 != 1 )
    return 0;
  GeConfigure(a1);
  return 1;
}

```

## disassembly

```asm
0x1800168f8  push    rbx
0x1800168fa  push    rbp
0x1800168fb  push    rsi
0x1800168fc  push    rdi
0x1800168fd  sub     rsp, 38h
0x180016901  mov     rdi, rcx
0x180016904  movzx   esi, dx
0x180016907  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001690d  mov     rax, r9
0x180016910  movzx   ebx, r8w
0x180016914  cmp     ecx, 0FFFFFFFFh
0x180016917  jz      short loc_180016937
0x180016919  mov     [rsp+58h+var_30], rax
0x18001691e  lea     r8, aGecommandNDIDC; "GeCommand(n=%d,i=%d,c=$%x)"
0x180016925  mov     r9d, esi
0x180016928  mov     [rsp+58h+var_38], ebx
0x18001692c  mov     edx, 0Ch; dwFlags
0x180016931  call    cs:__imp_TracePrintfExA
0x180016937  mov     eax, 46Bh
0x18001693c  mov     ebp, 1
0x180016941  cmp     ebx, eax
0x180016943  ja      short loc_1800169BE
0x180016945  jz      short loc_1800169B7
0x180016947  sub     ebx, 45Fh
0x18001694d  jz      short loc_1800169A8
0x18001694f  sub     ebx, 2
0x180016952  jz      short loc_18001698D
0x180016954  sub     ebx, 5
0x180016957  jz      short loc_18001697C
0x180016959  sub     ebx, 3
0x18001695c  jz      short loc_18001696F
0x18001695e  cmp     ebx, ebp
0x180016960  jnz     short loc_1800169A1
0x180016962  mov     rcx, rdi
0x180016965  call    GeConfigure
0x18001696a  jmp     loc_180016A61
0x18001696f  mov     rcx, rdi
0x180016972  call    GeAlternates
0x180016977  jmp     loc_180016A61
0x18001697c  lea     rcx, [rdi+4A0h]
0x180016983  movzx   edx, si
0x180016986  call    CuCountryCodeLbHandler
0x18001698b  jmp     short loc_180016999
0x18001698d  lea     rcx, [rdi+4A0h]
0x180016994  call    CuDialingRulesCbHandler
0x180016999  test    eax, eax
0x18001699b  jnz     loc_180016A61
0x1800169a1  xor     eax, eax
0x1800169a3  jmp     loc_180016A63
0x1800169a8  mov     edx, ebp
0x1800169aa  mov     rcx, rdi
0x1800169ad  call    GeUpdatePhoneNumberFields
0x1800169b2  jmp     loc_180016A61
0x1800169b7  xor     edx, edx
0x1800169b9  jmp     loc_180016A59
0x1800169be  sub     ebx, 46Ch
0x1800169c4  jz      loc_180016A57
0x1800169ca  sub     ebx, 4
0x1800169cd  jz      short loc_180016A4D
0x1800169cf  sub     ebx, 123h
0x1800169d5  jz      short loc_180016A35
0x1800169d7  sub     ebx, ebp
0x1800169d9  jz      short loc_1800169EE
0x1800169db  cmp     ebx, ebp
0x1800169dd  jnz     short loc_1800169A1
0x1800169df  cmp     si, bp
0x1800169e2  jnz     short loc_1800169A1
0x1800169e4  mov     rcx, rdi
0x1800169e7  call    GeDialAnotherFirstSelChange
0x1800169ec  jmp     short loc_180016A61
0x1800169ee  mov     rcx, [rdi+0C8h]; hWnd
0x1800169f5  xor     r9d, r9d; lParam
0x1800169f8  xor     r8d, r8d; wParam
0x1800169fb  mov     edx, 0F0h; Msg
0x180016a00  call    cs:__imp_SendMessageW
0x180016a06  test    eax, eax
0x180016a08  jz      short loc_180016A18
0x180016a0a  xor     edx, edx
0x180016a0c  mov     rcx, rdi
0x180016a0f  call    GeFillLbDialAnotherFirst
0x180016a14  mov     edx, ebp
0x180016a16  jmp     short loc_180016A26
0x180016a18  mov     rcx, [rdi+0D0h]; hWnd
0x180016a1f  call    GeClearLbDialAnotherFirst
0x180016a24  xor     edx, edx; bEnable
0x180016a26  mov     rcx, [rdi+0D0h]; hWnd
0x180016a2d  call    cs:__imp_EnableWindow
0x180016a33  jmp     short loc_180016A61
0x180016a35  mov     eax, 200h
0x180016a3a  cmp     ax, si
0x180016a3d  jnz     loc_1800169A1
0x180016a43  mov     rcx, rdi
0x180016a46  call    GeValidateHostName
0x180016a4b  jmp     short loc_180016A61
0x180016a4d  mov     rcx, rdi
0x180016a50  call    GeDialingRules
0x180016a55  jmp     short loc_180016A61
0x180016a57  mov     edx, ebp
0x180016a59  mov     rcx, rdi
0x180016a5c  call    GeMoveDevice
0x180016a61  mov     eax, ebp
0x180016a63  add     rsp, 38h
0x180016a67  pop     rdi
0x180016a68  pop     rsi
0x180016a69  pop     rbp
0x180016a6a  pop     rbx
0x180016a6b  retn
```
