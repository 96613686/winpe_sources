# RpCommand

- ea: `0x18002135c`
- end: `0x1800213fd`
- name: `RpCommand`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180021410`

## callees

- `0x18002135c`
- `0x180021660`
- `0x18002ae50`
- `0x18002b5d0`

## import_xrefs

- `USER32!SetWindowTextW` at `0x1800213e7`
- `USER32!SetWindowTextW` at `0x1800213e7`
- `rtutils!TracePrintfExA` at `0x180021394`
- `rtutils!TracePrintfExA` at `0x180021394`

## string_xrefs

- `0x18002137f`: `RpCommand(n=%d,i=%d,c=$%x)`

## pseudocode

```c
__int64 __fastcall RpCommand(__int64 a1, unsigned __int16 a2, unsigned __int16 a3, int a4)
{
  const WCHAR *PszFromList; // rax

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "RpCommand(n=%d,i=%d,c=$%x)", a2, a3, a4);
  if ( a3 != 1359 )
    return 0;
  RpPhoneNumberToStash(a1);
  if ( (unsigned int)PhoneNumberDlg(*(HWND *)(a1 + 72)) )
  {
    PszFromList = (const WCHAR *)FirstPszFromList(*(_QWORD *)(a1 + 464));
    SetWindowTextW(*(HWND *)(a1 + 168), PszFromList);
  }
  return 1;
}

```

## disassembly

```asm
0x18002135c  mov     [rsp+arg_0], rbx
0x180021361  push    rdi
0x180021362  sub     rsp, 30h
0x180021366  mov     rbx, rcx
0x180021369  movzx   edi, r8w
0x18002136d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180021373  mov     r10, r9
0x180021376  cmp     ecx, 0FFFFFFFFh
0x180021379  jz      short loc_18002139A
0x18002137b  movzx   r9d, dx
0x18002137f  lea     r8, aRpcommandNDIDC; "RpCommand(n=%d,i=%d,c=$%x)"
0x180021386  mov     [rsp+38h+var_10], r10
0x18002138b  mov     edx, 0Ch; dwFlags
0x180021390  mov     [rsp+38h+var_18], edi
0x180021394  call    cs:__imp_TracePrintfExA
0x18002139a  mov     eax, 54Fh
0x18002139f  cmp     di, ax
0x1800213a2  jz      short loc_1800213A8
0x1800213a4  xor     eax, eax
0x1800213a6  jmp     short loc_1800213F2
0x1800213a8  mov     rcx, rbx
0x1800213ab  call    RpPhoneNumberToStash
0x1800213b0  mov     rdx, [rbx]
0x1800213b3  lea     r9, [rbx+1D8h]
0x1800213ba  mov     r8, [rbx+1D0h]
0x1800213c1  mov     rcx, [rbx+48h]; hWnd
0x1800213c5  mov     edx, [rdx+1Ch]
0x1800213c8  call    PhoneNumberDlg
0x1800213cd  test    eax, eax
0x1800213cf  jz      short loc_1800213ED
0x1800213d1  mov     rcx, [rbx+1D0h]
0x1800213d8  call    FirstPszFromList
0x1800213dd  mov     rcx, [rbx+0A8h]; hWnd
0x1800213e4  mov     rdx, rax; lpString
0x1800213e7  call    cs:__imp_SetWindowTextW
0x1800213ed  mov     eax, 1
0x1800213f2  mov     rbx, [rsp+38h+arg_0]
0x1800213f7  add     rsp, 30h
0x1800213fb  pop     rdi
0x1800213fc  retn
```
