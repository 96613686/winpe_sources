# DgCommand

- ea: `0x18001d03c`
- end: `0x18001d198`
- name: `DgCommand`
- size: `348`
- prototype: `__int64 __fastcall(HWND hWnd, __int64, unsigned __int16, unsigned __int16, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001d1a0`

## callees

- `0x18001d03c`
- `0x18002cd5c`
- `0x180039124`
- `0x180048b6c`
- `0x18004e010`

## import_xrefs

- `USER32!SendMessageW` at `0x18001d0f2`
- `USER32!SendMessageW` at `0x18001d0f2`
- `rtutils!TracePrintfExA` at `0x18001d07b`
- `rtutils!TracePrintfExA` at `0x18001d07b`

## string_xrefs

- `0x18001d06b`: `DgCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall DgCommand(HWND hWnd, __int64 a2, unsigned __int16 a3, unsigned __int16 a4, __int64 a5)
{
  int v6; // edi
  __int64 v7; // rcx
  unsigned int v8; // esi
  int v10; // edi
  int v11; // edi
  __int64 (*v12)(void); // rax
  int v13; // eax
  __int64 v14; // rcx
  int v16; // [rsp+20h] [rbp-48h]

  v6 = a4;
  v7 = g_dwTraceId;
  v8 = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "DgCommand(n=%d,i=%d,c=$%x)", a3, a4, a5);
  v10 = v6 - 1703;
  if ( !v10 )
  {
    if ( !*(_QWORD *)(a2 + 264) )
      GetCoCreateInstanceElevationHandle(hWnd, (struct _GUID *)(a2 + 264), 0);
    v14 = *(_QWORD *)(a2 + 264);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 56LL))(v14);
    return 1;
  }
  v11 = v10 - 2;
  if ( !v11 )
  {
    if ( !*(_QWORD *)(a2 + 184)
      || !*(_QWORD *)(a2 + 216)
      || (v16 = a2, (unsigned int)SHFusionDialogBoxParam(v7, 593, hWnd, ElDlgProc) == -1) )
    {
      ErrorDlgUtil(hWnd, 0x6A6u, 0x27Bu, v16, 0x169u, 0xFAu);
    }
    return 1;
  }
  if ( v11 == 3
    && !*(_QWORD *)(a2 + 264)
    && (int)GetCoCreateInstanceElevationHandle(hWnd, (struct _GUID *)(a2 + 264), 0) < 0 )
  {
    if ( *(_QWORD *)(a2 + 184) )
    {
      v12 = *(__int64 (**)(void))(a2 + 224);
      if ( v12 )
      {
        v13 = v12();
        SendMessageW(*(HWND *)(a2 + 128), 0xF1u, v13, 0);
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x18001d03c  push    rbx
0x18001d03e  push    rbp
0x18001d03f  push    rsi
0x18001d040  push    rdi
0x18001d041  sub     rsp, 48h
0x18001d045  mov     rbp, rcx
0x18001d048  movzx   edi, r9w
0x18001d04c  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001d052  xor     esi, esi
0x18001d054  mov     rbx, rdx
0x18001d057  cmp     ecx, 0FFFFFFFFh
0x18001d05a  jz      short loc_18001D081
0x18001d05c  mov     rax, [rsp+68h+arg_20]
0x18001d064  lea     edx, [rsi+0Ch]; dwFlags
0x18001d067  movzx   r9d, r8w
0x18001d06b  lea     r8, aDgcommandNDIDC; "DgCommand(n=%d,i=%d,c=$%x)"
0x18001d072  mov     qword ptr [rsp+68h+var_40], rax
0x18001d077  mov     [rsp+68h+var_48], edi
0x18001d07b  call    cs:__imp_TracePrintfExA
0x18001d081  sub     edi, 6A7h
0x18001d087  jz      loc_18001D155
0x18001d08d  sub     edi, 2
0x18001d090  jz      short loc_18001D0FD
0x18001d092  cmp     edi, 3
0x18001d095  jnz     loc_18001D18D
0x18001d09b  lea     rdx, [rbx+108h]; void **
0x18001d0a2  cmp     [rdx], rsi
0x18001d0a5  jnz     loc_18001D18D
0x18001d0ab  xor     r8d, r8d
0x18001d0ae  mov     rcx, rbp; hwndOwner
0x18001d0b1  call    GetCoCreateInstanceElevationHandle
0x18001d0b6  test    eax, eax
0x18001d0b8  jns     loc_18001D18D
0x18001d0be  cmp     [rbx+0B8h], rsi
0x18001d0c5  jz      loc_18001D18D
0x18001d0cb  mov     rax, [rbx+0E0h]
0x18001d0d2  test    rax, rax
0x18001d0d5  jz      loc_18001D18D
0x18001d0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0e0  mov     rcx, [rbx+80h]; hWnd
0x18001d0e7  xor     r9d, r9d; lParam
0x18001d0ea  movsxd  r8, eax; wParam
0x18001d0ed  mov     edx, 0F1h; Msg
0x18001d0f2  call    cs:__imp_SendMessageW
0x18001d0f8  jmp     loc_18001D18D
0x18001d0fd  cmp     [rbx+0B8h], rsi
0x18001d104  jz      short loc_18001D12D
0x18001d106  cmp     [rbx+0D8h], rsi
0x18001d10d  jz      short loc_18001D12D
0x18001d10f  lea     r9, ElDlgProc
0x18001d116  mov     qword ptr [rsp+68h+var_48], rbx; int
0x18001d11b  mov     r8, rbp
0x18001d11e  mov     edx, 251h
0x18001d123  call    SHFusionDialogBoxParam
0x18001d128  cmp     eax, 0FFFFFFFFh
0x18001d12b  jnz     short loc_18001D188
0x18001d12d  mov     [rsp+68h+var_38], 0FAh; UINT
0x18001d135  xor     r9d, r9d
0x18001d138  mov     r8d, 27Bh; dwMessageId
0x18001d13e  mov     [rsp+68h+var_40], 169h; UINT
0x18001d146  mov     edx, 6A6h; uID
0x18001d14b  mov     rcx, rbp; hWnd
0x18001d14e  call    ErrorDlgUtil
0x18001d153  jmp     short loc_18001D188
0x18001d155  cmp     [rbx+108h], rsi
0x18001d15c  jnz     short loc_18001D170
0x18001d15e  xor     r8d, r8d
0x18001d161  lea     rdx, [rbx+108h]; void **
0x18001d168  mov     rcx, rbp; hwndOwner
0x18001d16b  call    GetCoCreateInstanceElevationHandle
0x18001d170  mov     rcx, [rbx+108h]
0x18001d177  test    rcx, rcx
0x18001d17a  jz      short loc_18001D188
0x18001d17c  mov     rax, [rcx]
0x18001d17f  mov     rax, [rax+38h]
0x18001d183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d188  mov     esi, 1
0x18001d18d  mov     eax, esi
0x18001d18f  add     rsp, 48h
0x18001d193  pop     rdi
0x18001d194  pop     rsi
0x18001d195  pop     rbp
0x18001d196  pop     rbx
0x18001d197  retn
```
