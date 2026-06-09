# LeDlgProc

- ea: `0x180010a70`
- end: `0x180010b37`
- name: `LeDlgProc`
- size: `199`
- prototype: `__int64 __fastcall(HWND, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800106ec`
- `0x180010a70`
- `0x180010d18`
- `0x18003b6b8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180010b24`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180010b24`
- `GDI32!DeleteObject` at `0x180010afe`
- `GDI32!DeleteObject` at `0x180010b0d`
- `GDI32!DeleteObject` at `0x180010afe`
- `GDI32!DeleteObject` at `0x180010b0d`
- `USER32!GetWindowLongPtrW` at `0x180010a9b`
- `USER32!GetWindowLongPtrW` at `0x180010aca`
- `USER32!GetWindowLongPtrW` at `0x180010a9b`
- `USER32!GetWindowLongPtrW` at `0x180010aca`
- `rtutils!TracePrintfExA` at `0x180010aea`
- `rtutils!TracePrintfExA` at `0x180010aea`

## pseudocode

```c
__int64 __fastcall LeDlgProc(HWND a1, int a2, int a3, int a4)
{
  int v6; // edx
  int v7; // edx
  HWND *WindowLongPtrW; // rax
  __int64 result; // rax
  LONG_PTR v10; // rbx
  void *v11; // rcx
  void *v12; // rcx

  v6 = a2 - 2;
  if ( v6 )
  {
    v7 = v6 - 270;
    if ( !v7 )
    {
      LODWORD(result) = LeInit(a1);
      return (int)result;
    }
    if ( v7 == 1 )
    {
      WindowLongPtrW = (HWND *)GetWindowLongPtrW(a1, 16);
      LODWORD(result) = LeCommand(WindowLongPtrW, HIWORD(a3), a3, a4);
      return (int)result;
    }
  }
  else
  {
    v10 = GetWindowLongPtrW(a1, 16);
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "LeTerm");
    if ( v10 )
    {
      v11 = *(void **)(v10 + 112);
      if ( v11 )
        DeleteObject(v11);
      v12 = *(void **)(v10 + 120);
      if ( v12 )
        DeleteObject(v12);
      DtlDestroyList(*(__int64 **)(v10 + 128), 0);
      GlobalFree((HGLOBAL)v10);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180010a70  mov     [rsp+arg_0], rbx
0x180010a75  push    rdi
0x180010a76  sub     rsp, 20h
0x180010a7a  mov     rbx, r9
0x180010a7d  mov     rdi, r8
0x180010a80  sub     edx, 2
0x180010a83  jz      short loc_180010AC5
0x180010a85  sub     edx, 10Eh
0x180010a8b  jz      short loc_180010AB9
0x180010a8d  cmp     edx, 1
0x180010a90  jnz     loc_180010B2A
0x180010a96  mov     edx, 10h; nIndex
0x180010a9b  call    cs:__imp_GetWindowLongPtrW
0x180010aa1  movzx   r8d, di
0x180010aa5  mov     r9, rbx
0x180010aa8  shr     rdi, 10h
0x180010aac  mov     rcx, rax
0x180010aaf  movzx   edx, di
0x180010ab2  call    LeCommand
0x180010ab7  jmp     short loc_180010AC1
0x180010ab9  mov     rdx, rbx
0x180010abc  call    LeInit
0x180010ac1  cdqe
0x180010ac3  jmp     short loc_180010B2C
0x180010ac5  mov     edx, 10h; nIndex
0x180010aca  call    cs:__imp_GetWindowLongPtrW
0x180010ad0  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180010ad6  mov     rbx, rax
0x180010ad9  cmp     ecx, 0FFFFFFFFh
0x180010adc  jz      short loc_180010AF0
0x180010ade  lea     r8, aLeterm; "LeTerm"
0x180010ae5  mov     edx, 0Ch; dwFlags
0x180010aea  call    cs:__imp_TracePrintfExA
0x180010af0  test    rbx, rbx
0x180010af3  jz      short loc_180010B2A
0x180010af5  mov     rcx, [rbx+70h]; ho
0x180010af9  test    rcx, rcx
0x180010afc  jz      short loc_180010B04
0x180010afe  call    cs:__imp_DeleteObject
0x180010b04  mov     rcx, [rbx+78h]; ho
0x180010b08  test    rcx, rcx
0x180010b0b  jz      short loc_180010B13
0x180010b0d  call    cs:__imp_DeleteObject
0x180010b13  mov     rcx, [rbx+80h]; hMem
0x180010b1a  xor     edx, edx
0x180010b1c  call    DtlDestroyList
0x180010b21  mov     rcx, rbx; hMem
0x180010b24  call    cs:__imp_GlobalFree
0x180010b2a  xor     eax, eax
0x180010b2c  mov     rbx, [rsp+28h+arg_0]
0x180010b31  add     rsp, 20h
0x180010b35  pop     rdi
0x180010b36  retn
```
