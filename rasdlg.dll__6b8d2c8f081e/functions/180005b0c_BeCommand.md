# BeCommand

- ea: `0x180005b0c`
- end: `0x180005c6a`
- name: `BeCommand`
- size: `350`
- prototype: `__int64 __fastcall(HWND hDlg, unsigned __int16, unsigned __int16, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005c70`

## callees

- `0x180005b0c`
- `0x18003b57c`
- `0x18003b5bc`
- `0x18003b784`
- `0x18003b82c`

## import_xrefs

- `USER32!IsDlgButtonChecked` at `0x180005ba4`
- `USER32!IsDlgButtonChecked` at `0x180005ba4`
- `USER32!EndDialog` at `0x180005c52`
- `USER32!EndDialog` at `0x180005c52`
- `USER32!GetWindowLongPtrW` at `0x180005bba`
- `USER32!GetWindowLongPtrW` at `0x180005bba`
- `rtutils!TracePrintfExA` at `0x180005b50`
- `rtutils!TracePrintfExA` at `0x180005b96`
- `rtutils!TracePrintfExA` at `0x180005b50`
- `rtutils!TracePrintfExA` at `0x180005b96`

## string_xrefs

- `0x180005b3e`: `BeCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall BeCommand(HWND hDlg, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  DWORD v6; // ecx
  int v7; // ebx
  const char *v9; // r9
  unsigned int v10; // esi
  LONG_PTR WindowLongPtrW; // rdi
  __int64 v12; // rbp
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 PszNode; // rax

  v6 = g_dwTraceId;
  v7 = a3;
  if ( g_dwTraceId != -1 )
  {
    TracePrintfExA(g_dwTraceId, 0xCu, "BeCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
    v6 = g_dwTraceId;
  }
  if ( (unsigned int)(v7 - 1) >= 2 )
    return 0;
  if ( v6 != -1 )
  {
    v9 = "OK";
    if ( a3 != 1 )
      v9 = "Cancel";
    TracePrintfExA(v6, 0xCu, "%s pressed", v9);
  }
  if ( IsDlgButtonChecked(hDlg, 1030) )
  {
    v10 = 0;
    WindowLongPtrW = GetWindowLongPtrW(hDlg, 16);
    v12 = *(_QWORD *)(WindowLongPtrW + 80);
    if ( *(_DWORD *)(WindowLongPtrW + 88) )
    {
      do
      {
        if ( *(_DWORD *)(v12 + 4) )
        {
          v13 = *(_QWORD *)(WindowLongPtrW + 8);
          if ( *(_QWORD *)(v13 + 424)
            || (v14 = *(_QWORD *)(WindowLongPtrW + 8),
                *(_QWORD *)(v14 + 424) = DtlCreateList(),
                v13 = *(_QWORD *)(WindowLongPtrW + 8),
                *(_QWORD *)(v13 + 424)) )
          {
            v15 = DtlNodeFromIndex(*(_QWORD *)(*(_QWORD *)(v13 + 440) + 32LL), v10);
            if ( v15 )
            {
              PszNode = CreatePszNode(**(_QWORD **)(v15 + 16));
              if ( PszNode )
                DtlAddNodeLast(*(_QWORD *)(*(_QWORD *)(WindowLongPtrW + 8) + 424LL), PszNode);
            }
          }
        }
        ++v10;
        v12 += 96;
      }
      while ( v10 < *(_DWORD *)(WindowLongPtrW + 88) );
    }
  }
  EndDialog(hDlg, a3 == 1);
  return 1;
}

```

## disassembly

```asm
0x180005b0c  push    rbx
0x180005b0e  push    rbp
0x180005b0f  push    rsi
0x180005b10  push    rdi
0x180005b11  push    r13
0x180005b13  push    r14
0x180005b15  push    r15
0x180005b17  sub     rsp, 30h
0x180005b1b  mov     r14, rcx
0x180005b1e  movzx   r15d, r8w
0x180005b22  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180005b28  or      edi, 0FFFFFFFFh
0x180005b2b  mov     rax, r9
0x180005b2e  mov     ebx, r15d
0x180005b31  mov     esi, 0Ch
0x180005b36  cmp     ecx, edi
0x180005b38  jz      short loc_180005B5C
0x180005b3a  movzx   r9d, dx
0x180005b3e  lea     r8, aBecommandNDIDC; "BeCommand(n=%d,i=%d,c=$%x)"
0x180005b45  mov     [rsp+68h+var_40], rax
0x180005b4a  mov     edx, esi; dwFlags
0x180005b4c  mov     [rsp+68h+var_48], ebx
0x180005b50  call    cs:__imp_TracePrintfExA
0x180005b56  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180005b5c  sub     ebx, 1
0x180005b5f  jz      short loc_180005B6D
0x180005b61  cmp     ebx, 1
0x180005b64  jz      short loc_180005B6D
0x180005b66  xor     eax, eax
0x180005b68  jmp     loc_180005C5B
0x180005b6d  mov     r13d, 1
0x180005b73  cmp     ecx, edi
0x180005b75  jz      short loc_180005B9C
0x180005b77  cmp     r15w, r13w
0x180005b7b  lea     rax, aCancel; "Cancel"
0x180005b82  lea     r9, aOk; "OK"
0x180005b89  mov     edx, esi; dwFlags
0x180005b8b  cmovnz  r9, rax
0x180005b8f  lea     r8, aSPressed; "%s pressed"
0x180005b96  call    cs:__imp_TracePrintfExA
0x180005b9c  mov     edx, 406h; nIDButton
0x180005ba1  mov     rcx, r14; hDlg
0x180005ba4  call    cs:__imp_IsDlgButtonChecked
0x180005baa  test    eax, eax
0x180005bac  jz      loc_180005C46
0x180005bb2  mov     edx, 10h; nIndex
0x180005bb7  mov     rcx, r14; hWnd
0x180005bba  call    cs:__imp_GetWindowLongPtrW
0x180005bc0  xor     esi, esi
0x180005bc2  mov     rdi, rax
0x180005bc5  mov     rbp, [rax+50h]
0x180005bc9  cmp     [rax+58h], esi
0x180005bcc  jbe     short loc_180005C46
0x180005bce  cmp     dword ptr [rbp+4], 0
0x180005bd2  jz      short loc_180005C3A
0x180005bd4  mov     rcx, [rdi+8]
0x180005bd8  cmp     qword ptr [rcx+1A8h], 0
0x180005be0  jnz     short loc_180005BFF
0x180005be2  mov     rbx, rcx
0x180005be5  call    DtlCreateList
0x180005bea  mov     [rbx+1A8h], rax
0x180005bf1  mov     rcx, [rdi+8]
0x180005bf5  cmp     qword ptr [rcx+1A8h], 0
0x180005bfd  jz      short loc_180005C3A
0x180005bff  mov     rcx, [rcx+1B8h]
0x180005c06  mov     edx, esi
0x180005c08  mov     rcx, [rcx+20h]
0x180005c0c  call    DtlNodeFromIndex
0x180005c11  test    rax, rax
0x180005c14  jz      short loc_180005C3A
0x180005c16  mov     rcx, [rax+10h]
0x180005c1a  mov     rcx, [rcx]
0x180005c1d  call    CreatePszNode
0x180005c22  test    rax, rax
0x180005c25  jz      short loc_180005C3A
0x180005c27  mov     rcx, [rdi+8]
0x180005c2b  mov     rdx, rax
0x180005c2e  mov     rcx, [rcx+1A8h]
0x180005c35  call    DtlAddNodeLast
0x180005c3a  add     esi, r13d
0x180005c3d  add     rbp, 60h ; '`'
0x180005c41  cmp     esi, [rdi+58h]
0x180005c44  jb      short loc_180005BCE
0x180005c46  xor     edx, edx
0x180005c48  mov     rcx, r14; hDlg
0x180005c4b  cmp     r15w, r13w
0x180005c4f  setz    dl; nResult
0x180005c52  call    cs:__imp_EndDialog
0x180005c58  mov     eax, r13d
0x180005c5b  add     rsp, 30h
0x180005c5f  pop     r15
0x180005c61  pop     r14
0x180005c63  pop     r13
0x180005c65  pop     rdi
0x180005c66  pop     rsi
0x180005c67  pop     rbp
0x180005c68  pop     rbx
0x180005c69  retn
```
