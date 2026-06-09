# MREXTSELECTCLIPRGN::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x180054a10`
- end: `0x180054aa1`
- name: `?bPlay@MREXTSELECTCLIPRGN@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `145`
- prototype: `__int64 __fastcall(MREXTSELECTCLIPRGN *__hidden this, HDC hdc, struct tagHANDLETABLE *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800305e0`

## callees

- `0x180024fb8`
- `0x180054a10`
- `0x180054ab0`

## import_xrefs

- `GDI32!ExtSelectClipRgn` at `0x180054a70`
- `GDI32!ExtSelectClipRgn` at `0x180054a70`
- `GDI32!DeleteObject` at `0x180054a95`
- `GDI32!DeleteObject` at `0x180054a95`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!ExtCreateRegion` at `0x180054a58`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!ExtCreateRegion` at `0x180054a58`

## pseudocode

```c
_BOOL8 __fastcall MREXTSELECTCLIPRGN::bPlay(MREXTSELECTCLIPRGN *this, HDC hdc, struct tagHANDLETABLE *a3)
{
  __int64 v6; // rsi
  DWORD v7; // edx
  HRGN Region; // rbx
  BOOL v9; // edi

  v6 = pvClientObjGet(a3->objectHandle[0], 4587520);
  if ( !v6 || !MREXTSELECTCLIPRGN::bCheckRecord(this, a3) )
    return 0;
  v7 = *((_DWORD *)this + 2);
  if ( !v7 )
  {
    Region = 0;
    goto LABEL_5;
  }
  Region = ExtCreateRegion((const XFORM *)(v6 + 704), v7, (const RGNDATA *)((char *)this + 16));
  if ( !Region )
    return 0;
LABEL_5:
  v9 = ExtSelectClipRgn(hdc, Region, *((_DWORD *)this + 3)) != 0;
  if ( Region )
    DeleteObject(Region);
  return v9;
}

```

## disassembly

```asm
0x180054a10  push    rbx
0x180054a12  push    rbp
0x180054a13  push    rsi
0x180054a14  push    rdi
0x180054a15  sub     rsp, 28h
0x180054a19  mov     rbp, rdx
0x180054a1c  mov     rdi, rcx
0x180054a1f  mov     rcx, [r8]
0x180054a22  mov     edx, 460000h
0x180054a27  mov     rbx, r8
0x180054a2a  call    pvClientObjGet
0x180054a2f  mov     rsi, rax
0x180054a32  test    rax, rax
0x180054a35  jz      short loc_180054A9D
0x180054a37  mov     rdx, rbx; struct tagHANDLETABLE *
0x180054a3a  mov     rcx, rdi; this
0x180054a3d  call    ?bCheckRecord@MREXTSELECTCLIPRGN@@QEAAHPEAUtagHANDLETABLE@@@Z; MREXTSELECTCLIPRGN::bCheckRecord(tagHANDLETABLE *)
0x180054a42  test    eax, eax
0x180054a44  jz      short loc_180054A9D
0x180054a46  mov     edx, [rdi+8]; nCount
0x180054a49  test    edx, edx
0x180054a4b  jz      short loc_180054A8E
0x180054a4d  lea     r8, [rdi+10h]; lpData
0x180054a51  lea     rcx, [rsi+2C0h]; lpx
0x180054a58  call    cs:__imp_ExtCreateRegion
0x180054a5e  mov     rbx, rax
0x180054a61  test    rax, rax
0x180054a64  jz      short loc_180054A9D
0x180054a66  mov     r8d, [rdi+0Ch]; mode
0x180054a6a  mov     rdx, rbx; hrgn
0x180054a6d  mov     rcx, rbp; hdc
0x180054a70  call    cs:__imp_ExtSelectClipRgn
0x180054a76  xor     edi, edi
0x180054a78  test    eax, eax
0x180054a7a  setnz   dil
0x180054a7e  test    rbx, rbx
0x180054a81  jnz     short loc_180054A92
0x180054a83  mov     eax, edi
0x180054a85  add     rsp, 28h
0x180054a89  pop     rdi
0x180054a8a  pop     rsi
0x180054a8b  pop     rbp
0x180054a8c  pop     rbx
0x180054a8d  retn
0x180054a8e  xor     ebx, ebx
0x180054a90  jmp     short loc_180054A66
0x180054a92  mov     rcx, rbx; ho
0x180054a95  call    cs:__imp_DeleteObject
0x180054a9b  jmp     short loc_180054A83
0x180054a9d  xor     eax, eax
0x180054a9f  jmp     short loc_180054A85
```
