# MREXTSELECTCLIPRGN::bPlay(void *,tagHANDLETABLE *,uint)

- ea: `0x180059d30`
- end: `0x180059dd4`
- name: `?bPlay@MREXTSELECTCLIPRGN@@QEAAHPEAXPEAUtagHANDLETABLE@@I@Z`
- size: `164`
- prototype: `__int64 __fastcall(MREXTSELECTCLIPRGN *__hidden this, HDC hdc, struct tagHANDLETABLE *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180016350`

## callees

- `0x18002e040`
- `0x180059d30`
- `0x180059de0`

## import_xrefs

- `GDI32!ExtSelectClipRgn` at `0x180059d96`
- `GDI32!ExtSelectClipRgn` at `0x180059d96`
- `GDI32!DeleteObject` at `0x180059dc2`
- `GDI32!DeleteObject` at `0x180059dc2`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!ExtCreateRegion` at `0x180059d78`
- `ext-ms-win-rtcore-gdi-rgn-l1-1-0!ExtCreateRegion` at `0x180059d78`

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
0x180059d30  push    rbx
0x180059d32  push    rbp
0x180059d33  push    rsi
0x180059d34  push    rdi
0x180059d35  sub     rsp, 28h
0x180059d39  mov     rbp, rdx
0x180059d3c  mov     rdi, rcx
0x180059d3f  mov     rcx, [r8]
0x180059d42  mov     edx, 460000h
0x180059d47  mov     rbx, r8
0x180059d4a  call    pvClientObjGet
0x180059d4f  mov     rsi, rax
0x180059d52  test    rax, rax
0x180059d55  jz      short loc_180059DD0
0x180059d57  mov     rdx, rbx; struct tagHANDLETABLE *
0x180059d5a  mov     rcx, rdi; this
0x180059d5d  call    ?bCheckRecord@MREXTSELECTCLIPRGN@@QEAAHPEAUtagHANDLETABLE@@@Z; MREXTSELECTCLIPRGN::bCheckRecord(tagHANDLETABLE *)
0x180059d62  test    eax, eax
0x180059d64  jz      short loc_180059DD0
0x180059d66  mov     edx, [rdi+8]; nCount
0x180059d69  test    edx, edx
0x180059d6b  jz      short loc_180059DBB
0x180059d6d  lea     r8, [rdi+10h]; lpData
0x180059d71  lea     rcx, [rsi+2C0h]; lpx
0x180059d78  call    cs:__imp_ExtCreateRegion
0x180059d7f  nop     dword ptr [rax+rax+00h]
0x180059d84  mov     rbx, rax
0x180059d87  test    rax, rax
0x180059d8a  jz      short loc_180059DD0
0x180059d8c  mov     r8d, [rdi+0Ch]; mode
0x180059d90  mov     rdx, rbx; hrgn
0x180059d93  mov     rcx, rbp; hdc
0x180059d96  call    cs:__imp_ExtSelectClipRgn
0x180059d9d  nop     dword ptr [rax+rax+00h]
0x180059da2  xor     edi, edi
0x180059da4  test    eax, eax
0x180059da6  setnz   dil
0x180059daa  test    rbx, rbx
0x180059dad  jnz     short loc_180059DBF
0x180059daf  mov     eax, edi
0x180059db1  add     rsp, 28h
0x180059db5  pop     rdi
0x180059db6  pop     rsi
0x180059db7  pop     rbp
0x180059db8  pop     rbx
0x180059db9  retn
0x180059dbb  xor     ebx, ebx
0x180059dbd  jmp     short loc_180059D8C
0x180059dbf  mov     rcx, rbx; ho
0x180059dc2  call    cs:__imp_DeleteObject
0x180059dc9  nop     dword ptr [rax+rax+00h]
0x180059dce  jmp     short loc_180059DAF
0x180059dd0  xor     eax, eax
0x180059dd2  jmp     short loc_180059DB1
```
