# GeUpdatePhoneNumberFields

- ea: `0x180018184`
- end: `0x180018301`
- name: `GeUpdatePhoneNumberFields`
- size: `381`
- prototype: `LRESULT __fastcall(__int64, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800168f8`
- `0x180016d50`

## callees

- `0x180017678`
- `0x180018104`
- `0x180018184`
- `0x180018308`
- `0x18002a81c`
- `0x18004658c`
- `0x180048518`

## import_xrefs

- `USER32!SendMessageW` at `0x1800181ca`
- `USER32!SendMessageW` at `0x180018269`
- `USER32!SendMessageW` at `0x1800181ca`
- `USER32!SendMessageW` at `0x180018269`
- `rtutils!TracePrintfExA` at `0x1800181a9`
- `rtutils!TracePrintfExA` at `0x1800181a9`

## string_xrefs

- `0x18001819d`: `GeUpdatePhoneNumberFields`

## pseudocode

```c
LRESULT __fastcall GeUpdatePhoneNumberFields(__int64 a1, int a2)
{
  int v4; // esi
  LRESULT result; // rax
  LRESULT v6; // rdi
  __int64 v7; // rdx
  __int64 v8; // rcx
  LRESULT v9; // rdx
  unsigned int v10; // ebp
  _BOOL8 v11; // r8
  LRESULT v12; // rdx
  LRESULT v13; // rdi
  __int64 v14; // rdx
  int v15; // eax

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "GeUpdatePhoneNumberFields");
  if ( *(_DWORD *)(*(_QWORD *)a1 + 324LL) )
    v4 = SendMessageW(*(HWND *)(a1 + 88), 0xF0u, 0, 0);
  else
    v4 = 1;
  if ( *(int *)(a1 + 1176) >= 0 )
  {
    result = ListView_GetParamPtr(*(HWND *)(a1 + 56));
    v6 = result;
    if ( !result )
      return result;
    if ( v4 )
    {
      if ( a2 )
      {
        GeGetPhoneFields(a1, result);
        v7 = v6;
        v8 = *(_QWORD *)(*(_QWORD *)a1 + 328LL);
LABEL_14:
        CopyLinkPhoneNumberInfo(v8, v7);
        goto LABEL_17;
      }
      v9 = *(_QWORD *)(*(_QWORD *)a1 + 328LL);
    }
    else
    {
      if ( a2 )
      {
        GeGetPhoneFields(a1, *(_QWORD *)(*(_QWORD *)a1 + 328LL));
        v8 = v6;
        v7 = *(_QWORD *)(*(_QWORD *)a1 + 328LL);
        goto LABEL_14;
      }
      v9 = result;
    }
    GeGetPhoneFields(a1, v9);
  }
LABEL_17:
  result = SendMessageW(*(HWND *)(a1 + 56), 0x100Cu, 0xFFFFFFFFFFFFFFFFuLL, 2);
  v10 = result;
  *(_DWORD *)(a1 + 1176) = result;
  if ( (int)result < 0 )
    return result;
  if ( v4 )
  {
    *(_QWORD *)(a1 + 1168) = *(_QWORD *)(*(_QWORD *)a1 + 328LL);
    GeUpdatePhoneNumberTitle(a1, 0);
    v11 = 0;
    v12 = *(_QWORD *)(*(_QWORD *)a1 + 328LL);
    return GeSetPhoneFields(a1, v12, v11);
  }
  result = ListView_GetParamPtr(*(HWND *)(a1 + 56));
  v13 = result;
  if ( result )
  {
    v14 = *(_QWORD *)(result + 16);
    if ( v14 )
    {
      *(_QWORD *)(a1 + 1168) = result;
      GeUpdatePhoneNumberTitle(a1, *(_QWORD *)(v14 + 16));
      v15 = ListView_GetCheck(*(_QWORD *)(a1 + 56), v10);
      v12 = v13;
      v11 = v15 == 0;
      return GeSetPhoneFields(a1, v12, v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180018184  push    rbx
0x180018186  push    rbp
0x180018187  push    rsi
0x180018188  push    rdi
0x180018189  sub     rsp, 28h
0x18001818d  mov     rbx, rcx
0x180018190  mov     ebp, edx
0x180018192  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180018198  cmp     ecx, 0FFFFFFFFh
0x18001819b  jz      short loc_1800181AF
0x18001819d  lea     r8, aGeupdatephonen_0; "GeUpdatePhoneNumberFields"
0x1800181a4  mov     edx, 0Ch; dwFlags
0x1800181a9  call    cs:__imp_TracePrintfExA
0x1800181af  mov     rax, [rbx]
0x1800181b2  cmp     dword ptr [rax+144h], 0
0x1800181b9  jz      short loc_1800181D5
0x1800181bb  mov     rcx, [rbx+58h]; hWnd
0x1800181bf  xor     r9d, r9d; lParam
0x1800181c2  xor     r8d, r8d; wParam
0x1800181c5  mov     edx, 0F0h; Msg
0x1800181ca  call    cs:__imp_SendMessageW
0x1800181d0  mov     rsi, rax
0x1800181d3  jmp     short loc_1800181DA
0x1800181d5  mov     esi, 1
0x1800181da  mov     edx, [rbx+498h]
0x1800181e0  test    edx, edx
0x1800181e2  js      short loc_180018256
0x1800181e4  mov     rcx, [rbx+38h]; hWnd
0x1800181e8  call    ListView_GetParamPtr
0x1800181ed  mov     rdi, rax
0x1800181f0  test    rax, rax
0x1800181f3  jz      loc_1800182F8
0x1800181f9  mov     rcx, rbx
0x1800181fc  test    esi, esi
0x1800181fe  jz      short loc_180018227
0x180018200  test    ebp, ebp
0x180018202  jz      short loc_18001821B
0x180018204  mov     rdx, rax
0x180018207  call    GeGetPhoneFields
0x18001820c  mov     rcx, [rbx]
0x18001820f  mov     rdx, rdi
0x180018212  mov     rcx, [rcx+148h]
0x180018219  jmp     short loc_180018247
0x18001821b  mov     rdx, [rbx]
0x18001821e  mov     rdx, [rdx+148h]
0x180018225  jmp     short loc_180018251
0x180018227  test    ebp, ebp
0x180018229  jz      short loc_18001824E
0x18001822b  mov     rdx, [rbx]
0x18001822e  mov     rdx, [rdx+148h]
0x180018235  call    GeGetPhoneFields
0x18001823a  mov     rdx, [rbx]
0x18001823d  mov     rcx, rdi
0x180018240  mov     rdx, [rdx+148h]
0x180018247  call    CopyLinkPhoneNumberInfo
0x18001824c  jmp     short loc_180018256
0x18001824e  mov     rdx, rdi
0x180018251  call    GeGetPhoneFields
0x180018256  mov     rcx, [rbx+38h]; hWnd
0x18001825a  mov     r9d, 2; lParam
0x180018260  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x180018264  mov     edx, 100Ch; Msg
0x180018269  call    cs:__imp_SendMessageW
0x18001826f  mov     rbp, rax
0x180018272  mov     [rbx+498h], ebp
0x180018278  test    eax, eax
0x18001827a  js      short loc_1800182F8
0x18001827c  test    esi, esi
0x18001827e  jz      short loc_1800182AA
0x180018280  mov     rax, [rbx]
0x180018283  xor     edx, edx
0x180018285  mov     rcx, [rax+148h]
0x18001828c  mov     [rbx+490h], rcx
0x180018293  mov     rcx, rbx
0x180018296  call    GeUpdatePhoneNumberTitle
0x18001829b  mov     rdx, [rbx]
0x18001829e  xor     r8d, r8d
0x1800182a1  mov     rdx, [rdx+148h]
0x1800182a8  jmp     short loc_1800182F0
0x1800182aa  mov     rcx, [rbx+38h]; hWnd
0x1800182ae  mov     edx, ebp
0x1800182b0  call    ListView_GetParamPtr
0x1800182b5  mov     rdi, rax
0x1800182b8  test    rax, rax
0x1800182bb  jz      short loc_1800182F8
0x1800182bd  mov     rdx, [rax+10h]
0x1800182c1  test    rdx, rdx
0x1800182c4  jz      short loc_1800182F8
0x1800182c6  mov     [rbx+490h], rax
0x1800182cd  mov     rcx, rbx
0x1800182d0  mov     rdx, [rdx+10h]
0x1800182d4  call    GeUpdatePhoneNumberTitle
0x1800182d9  mov     rcx, [rbx+38h]
0x1800182dd  mov     edx, ebp
0x1800182df  call    ListView_GetCheck
0x1800182e4  xor     r8d, r8d
0x1800182e7  mov     rdx, rdi
0x1800182ea  test    eax, eax
0x1800182ec  setz    r8b
0x1800182f0  mov     rcx, rbx
0x1800182f3  call    GeSetPhoneFields
0x1800182f8  add     rsp, 28h
0x1800182fc  pop     rdi
0x1800182fd  pop     rsi
0x1800182fe  pop     rbp
0x1800182ff  pop     rbx
0x180018300  retn
```
