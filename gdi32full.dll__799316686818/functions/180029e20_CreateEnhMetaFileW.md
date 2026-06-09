# CreateEnhMetaFileW

- ea: `0x180029e20`
- end: `0x180029ede`
- name: `CreateEnhMetaFileW`
- size: `190`
- prototype: `HDC __stdcall(HDC hdc, LPCWSTR lpFilename, const RECT *lprc, LPCWSTR lpDesc)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18002a9b0`
- `0x18002b5a0`

## callees

- `0x180023aa4`
- `0x180024010`
- `0x180026cf0`
- `0x180028550`
- `0x180029e20`
- `0x180029ee4`
- `0x1800849c0`

## import_xrefs

- `GDI32!GdiSetLastError` at `0x180029ec2`
- `GDI32!GdiSetLastError` at `0x180029ec2`
- `win32u!NtGdiSetBoundsRect` at `0x180029e98`
- `win32u!NtGdiSetBoundsRect` at `0x180029e98`
- `win32u!NtGdiCreateMetafileDC` at `0x180029e34`
- `win32u!NtGdiCreateMetafileDC` at `0x180029e34`

## pseudocode

```c
HDC __stdcall CreateEnhMetaFileW(HDC hdc, LPCWSTR lpFilename, const RECT *lprc, LPCWSTR lpDesc)
{
  __int64 MetafileDC; // rax
  HDC v8; // rdi
  __int64 v9; // rbp
  struct MDC *v10; // rax
  struct MDC *v11; // rbx
  const BITMAPINFOHEADER *v12; // rdx
  DWORD v13; // r8d
  const void *v14; // r9

  MetafileDC = NtGdiCreateMetafileDC(hdc);
  v8 = (HDC)MetafileDC;
  if ( MetafileDC )
  {
    v9 = pldcCreate(MetafileDC, 2);
    if ( v9 )
    {
      v10 = pmdcAllocMDC(v8, lpFilename, lpDesc, 0);
      v11 = v10;
      if ( v10 )
      {
        *(_QWORD *)(v9 + 16) = v10;
        if ( !lprc )
        {
LABEL_7:
          NtGdiSetBoundsRect(v8, 0, 32773);
          return (HDC)GdiTrackHCreate(v8, v12, v13, v14);
        }
        if ( !(unsigned int)ERECTL::bEmpty((ERECTL *)lprc) )
        {
          *(RECT *)((char *)v11 + 60) = *lprc;
          goto LABEL_7;
        }
        GdiSetLastError(87);
        *((_DWORD *)v11 + 8) |= 2u;
        vFreeMDC(v11);
        *(_QWORD *)(v9 + 16) = 0;
      }
      InternalDeleteDC(v8);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180029e20  push    rbx
0x180029e22  push    rbp
0x180029e23  push    rsi
0x180029e24  push    rdi
0x180029e25  push    r14
0x180029e27  sub     rsp, 20h
0x180029e2b  mov     rbx, r9
0x180029e2e  mov     rsi, r8
0x180029e31  mov     r14, rdx
0x180029e34  call    cs:__imp_NtGdiCreateMetafileDC
0x180029e3a  mov     rdi, rax
0x180029e3d  test    rax, rax
0x180029e40  jz      short loc_180029EB0
0x180029e42  mov     edx, 2
0x180029e47  mov     rcx, rax
0x180029e4a  call    pldcCreate
0x180029e4f  mov     rbp, rax
0x180029e52  test    rax, rax
0x180029e55  jz      short loc_180029EB0
0x180029e57  xor     r9d, r9d; this
0x180029e5a  mov     r8, rbx; unsigned __int16 *
0x180029e5d  mov     rdx, r14; lpFileName
0x180029e60  mov     rcx, rdi; void *
0x180029e63  call    ?pmdcAllocMDC@@YAPEAVMDC@@PEAXPEBG10@Z; pmdcAllocMDC(void *,ushort const *,ushort const *,void *)
0x180029e68  mov     rbx, rax
0x180029e6b  test    rax, rax
0x180029e6e  jz      short loc_180029EA8
0x180029e70  mov     [rbp+10h], rax
0x180029e74  test    rsi, rsi
0x180029e77  jz      short loc_180029E8D
0x180029e79  mov     rcx, rsi; this
0x180029e7c  call    ?bEmpty@ERECTL@@QEAAHXZ; ERECTL::bEmpty(void)
0x180029e81  test    eax, eax
0x180029e83  jnz     short loc_180029EBD
0x180029e85  movups  xmm0, xmmword ptr [rsi]
0x180029e88  movdqu  xmmword ptr [rbx+3Ch], xmm0
0x180029e8d  xor     edx, edx
0x180029e8f  mov     r8d, 8005h
0x180029e95  mov     rcx, rdi
0x180029e98  call    cs:__imp_NtGdiSetBoundsRect
0x180029e9e  mov     rcx, rdi
0x180029ea1  call    GdiTrackHCreate
0x180029ea6  jmp     short loc_180029EB2
0x180029ea8  mov     rcx, rdi; HDC
0x180029eab  call    InternalDeleteDC
0x180029eb0  xor     eax, eax
0x180029eb2  add     rsp, 20h
0x180029eb6  pop     r14
0x180029eb8  pop     rdi
0x180029eb9  pop     rsi
0x180029eba  pop     rbp
0x180029ebb  pop     rbx
0x180029ebc  retn
0x180029ebd  mov     ecx, 57h ; 'W'
0x180029ec2  call    cs:__imp_GdiSetLastError
0x180029ec8  or      dword ptr [rbx+20h], 2
0x180029ecc  mov     rcx, rbx; this
0x180029ecf  call    ?vFreeMDC@@YAXPEAVMDC@@@Z; vFreeMDC(MDC *)
0x180029ed4  mov     qword ptr [rbp+10h], 0
0x180029edc  jmp     short loc_180029EA8
```
