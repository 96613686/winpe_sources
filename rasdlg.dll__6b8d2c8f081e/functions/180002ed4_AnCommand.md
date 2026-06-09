# AnCommand

- ea: `0x180002ed4`
- end: `0x1800030ba`
- name: `AnCommand`
- size: `486`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800030c0`

## callees

- `0x180002ed4`
- `0x1800031e8`
- `0x180003854`
- `0x180003910`
- `0x1800039ac`
- `0x180003c2c`
- `0x1800041b8`
- `0x18003b57c`
- `0x18003b7ac`
- `0x180048580`

## import_xrefs

- `RASAPI32!DestroyPhoneNode` at `0x180002fff`
- `RASAPI32!DestroyPhoneNode` at `0x18000303c`
- `RASAPI32!DestroyPhoneNode` at `0x180002fff`
- `RASAPI32!DestroyPhoneNode` at `0x18000303c`
- `RASAPI32!CreatePhoneNode` at `0x18000300a`
- `RASAPI32!CreatePhoneNode` at `0x18000300a`
- `USER32!EndDialog` at `0x18000309f`
- `USER32!EndDialog` at `0x18000309f`
- `rtutils!TracePrintfExA` at `0x180002f13`
- `rtutils!TracePrintfExA` at `0x180003086`
- `rtutils!TracePrintfExA` at `0x180002f13`
- `rtutils!TracePrintfExA` at `0x180003086`

## string_xrefs

- `0x180002efe`: `AnCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall AnCommand(__int64 a1, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  int v5; // ebx
  DWORD v6; // ecx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  __int64 v15; // rdx
  __int64 v16; // rbx
  __int64 v17; // rdx
  __int64 *SelectedParamPtr; // rbx
  __int64 v19; // rsi
  __int64 PhoneNode; // rbx
  INT_PTR v21; // rdx

  v5 = a3;
  v6 = g_dwTraceId;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "AnCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
    v6 = g_dwTraceId;
  }
  v7 = v5 - 1;
  if ( !v7 )
  {
    v21 = (int)AnSave(a1);
LABEL_32:
    EndDialog(*(HWND *)(a1 + 8), v21);
    return 1;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    if ( v6 != -1 )
      TracePrintfExA(v6, 0xCu, "Cancel pressed");
    v21 = 0;
    goto LABEL_32;
  }
  v9 = v8 - 1009;
  if ( !v9 )
  {
    AnUpdateCheckboxes(a1);
    return 1;
  }
  v10 = v9 - 2;
  if ( !v10 )
  {
    PhoneNode = CreatePhoneNode();
    if ( !PhoneNode )
      return 1;
    if ( !(unsigned int)EditPhoneNumberDlg(*(HWND *)(a1 + 8)) )
    {
      DestroyPhoneNode(PhoneNode);
      return 1;
    }
    AnListFromLv(a1);
    DtlAddNodeLast(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 168LL), PhoneNode);
    goto LABEL_26;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    SelectedParamPtr = (__int64 *)ListView_GetSelectedParamPtr(*(HWND *)(a1 + 16));
    if ( !SelectedParamPtr )
      return 1;
    AnListFromLv(a1);
    v19 = SelectedParamPtr[1];
    if ( !v19 )
      v19 = *SelectedParamPtr;
    DtlRemoveNode(*(_QWORD *)(*(_QWORD *)(a1 + 136) + 168LL), SelectedParamPtr);
    DestroyPhoneNode(SelectedParamPtr);
    v17 = v19;
    goto LABEL_26;
  }
  v12 = v11 - 1;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      if ( v13 != 1 )
        return 0;
      v15 = 1;
      goto LABEL_13;
    }
    v16 = ListView_GetSelectedParamPtr(*(HWND *)(a1 + 16));
    if ( !v16 || !(unsigned int)EditPhoneNumberDlg(*(HWND *)(a1 + 8)) )
      return 1;
    AnListFromLv(a1);
    v17 = v16;
LABEL_26:
    AnFillLv(a1, v17);
    return 1;
  }
  v15 = 0;
LABEL_13:
  AnMoveNumber(a1, v15);
  return 1;
}

```

## disassembly

```asm
0x180002ed4  mov     [rsp+arg_0], rbx
0x180002ed9  mov     [rsp+arg_8], rsi
0x180002ede  push    rdi
0x180002edf  sub     rsp, 30h
0x180002ee3  mov     rdi, rcx
0x180002ee6  movzx   ebx, r8w
0x180002eea  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180002ef0  or      esi, 0FFFFFFFFh
0x180002ef3  mov     rax, r9
0x180002ef6  cmp     ecx, esi
0x180002ef8  jz      short loc_180002F1F
0x180002efa  movzx   r9d, dx
0x180002efe  lea     r8, aAncommandNDIDC; "AnCommand(n=%d,i=%d,c=$%x)"
0x180002f05  mov     [rsp+38h+var_10], rax
0x180002f0a  mov     edx, 0Ch; dwFlags
0x180002f0f  mov     [rsp+38h+var_18], ebx
0x180002f13  call    cs:__imp_TracePrintfExA
0x180002f19  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180002f1f  sub     ebx, 1
0x180002f22  jz      loc_180003090
0x180002f28  sub     ebx, 1
0x180002f2b  jz      loc_180003076
0x180002f31  sub     ebx, 3F1h
0x180002f37  jz      loc_18000306C
0x180002f3d  sub     ebx, 2
0x180002f40  jz      loc_18000300A
0x180002f46  sub     ebx, 1
0x180002f49  jz      short loc_180002FBD
0x180002f4b  sub     ebx, 1
0x180002f4e  jz      short loc_180002FB9
0x180002f50  sub     ebx, 1
0x180002f53  jz      short loc_180002F73
0x180002f55  cmp     ebx, 1
0x180002f58  jz      short loc_180002F61
0x180002f5a  xor     eax, eax
0x180002f5c  jmp     loc_1800030AA
0x180002f61  mov     edx, 1
0x180002f66  mov     rcx, rdi
0x180002f69  call    AnMoveNumber
0x180002f6e  jmp     loc_1800030A5
0x180002f73  mov     rcx, [rdi+10h]; hWnd
0x180002f77  call    ListView_GetSelectedParamPtr
0x180002f7c  mov     rbx, rax
0x180002f7f  test    rax, rax
0x180002f82  jz      loc_1800030A5
0x180002f88  mov     r8, [rdi+90h]
0x180002f8f  mov     r9d, 0F3h
0x180002f95  mov     rcx, [rdi+8]; hWnd
0x180002f99  mov     rdx, rax
0x180002f9c  call    EditPhoneNumberDlg
0x180002fa1  test    eax, eax
0x180002fa3  jz      loc_1800030A5
0x180002fa9  mov     rcx, rdi
0x180002fac  call    AnListFromLv
0x180002fb1  mov     rdx, rbx
0x180002fb4  jmp     loc_180003062
0x180002fb9  xor     edx, edx
0x180002fbb  jmp     short loc_180002F66
0x180002fbd  mov     rcx, [rdi+10h]; hWnd
0x180002fc1  call    ListView_GetSelectedParamPtr
0x180002fc6  mov     rbx, rax
0x180002fc9  test    rax, rax
0x180002fcc  jz      loc_1800030A5
0x180002fd2  mov     rcx, rdi
0x180002fd5  call    AnListFromLv
0x180002fda  mov     rsi, [rbx+8]
0x180002fde  test    rsi, rsi
0x180002fe1  jnz     short loc_180002FE6
0x180002fe3  mov     rsi, [rbx]
0x180002fe6  mov     rcx, [rdi+88h]
0x180002fed  mov     rdx, rbx
0x180002ff0  mov     rcx, [rcx+0A8h]
0x180002ff7  call    DtlRemoveNode
0x180002ffc  mov     rcx, rbx
0x180002fff  call    cs:__imp_DestroyPhoneNode
0x180003005  mov     rdx, rsi
0x180003008  jmp     short loc_180003062
0x18000300a  call    cs:__imp_CreatePhoneNode
0x180003010  mov     rbx, rax
0x180003013  test    rax, rax
0x180003016  jz      loc_1800030A5
0x18000301c  mov     r8, [rdi+90h]
0x180003023  mov     r9d, 0BDh
0x180003029  mov     rcx, [rdi+8]; hWnd
0x18000302d  mov     rdx, rax
0x180003030  call    EditPhoneNumberDlg
0x180003035  test    eax, eax
0x180003037  jnz     short loc_180003044
0x180003039  mov     rcx, rbx
0x18000303c  call    cs:__imp_DestroyPhoneNode
0x180003042  jmp     short loc_1800030A5
0x180003044  mov     rcx, rdi
0x180003047  call    AnListFromLv
0x18000304c  mov     rcx, [rdi+88h]
0x180003053  mov     rdx, rbx
0x180003056  mov     rcx, [rcx+0A8h]
0x18000305d  call    DtlAddNodeLast
0x180003062  mov     rcx, rdi
0x180003065  call    AnFillLv
0x18000306a  jmp     short loc_1800030A5
0x18000306c  mov     rcx, rdi
0x18000306f  call    AnUpdateCheckboxes
0x180003074  jmp     short loc_1800030A5
0x180003076  cmp     ecx, esi
0x180003078  jz      short loc_18000308C
0x18000307a  lea     r8, aCancelPressed; "Cancel pressed"
0x180003081  mov     edx, 0Ch; dwFlags
0x180003086  call    cs:__imp_TracePrintfExA
0x18000308c  xor     edx, edx
0x18000308e  jmp     short loc_18000309B
0x180003090  mov     rcx, rdi
0x180003093  call    AnSave
0x180003098  movsxd  rdx, eax; nResult
0x18000309b  mov     rcx, [rdi+8]; hDlg
0x18000309f  call    cs:__imp_EndDialog
0x1800030a5  mov     eax, 1
0x1800030aa  mov     rbx, [rsp+38h+arg_0]
0x1800030af  mov     rsi, [rsp+38h+arg_8]
0x1800030b4  add     rsp, 30h
0x1800030b8  pop     rdi
0x1800030b9  retn
```
