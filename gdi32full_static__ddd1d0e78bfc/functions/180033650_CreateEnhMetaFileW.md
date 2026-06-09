# CreateEnhMetaFileW

- ea: `0x180033650`
- end: `0x180033721`
- name: `CreateEnhMetaFileW`
- size: `209`
- prototype: `HDC __stdcall(HDC hdc, LPCWSTR lpFilename, const RECT *lprc, LPCWSTR lpDesc)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180034440`
- `0x180035440`

## callees

- `0x18002ca14`
- `0x18002cfe8`
- `0x18002fda0`
- `0x180031940`
- `0x180033650`
- `0x180033728`
- `0x180089ba4`

## import_xrefs

- `GDI32!GdiSetLastError` at `0x1800336ff`
- `GDI32!GdiSetLastError` at `0x1800336ff`
- `win32u!NtGdiSetBoundsRect` at `0x1800336ce`
- `win32u!NtGdiSetBoundsRect` at `0x1800336ce`
- `win32u!NtGdiCreateMetafileDC` at `0x180033664`
- `win32u!NtGdiCreateMetafileDC` at `0x180033664`

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
0x180033650  push    rbx
0x180033652  push    rbp
0x180033653  push    rsi
0x180033654  push    rdi
0x180033655  push    r14
0x180033657  sub     rsp, 20h
0x18003365b  mov     rbx, r9
0x18003365e  mov     rsi, r8
0x180033661  mov     r14, rdx
0x180033664  call    cs:__imp_NtGdiCreateMetafileDC
0x18003366b  nop     dword ptr [rax+rax+00h]
0x180033670  mov     rdi, rax
0x180033673  test    rax, rax
0x180033676  jz      short loc_1800336EC
0x180033678  mov     edx, 2
0x18003367d  mov     rcx, rax
0x180033680  call    pldcCreate
0x180033685  mov     rbp, rax
0x180033688  test    rax, rax
0x18003368b  jz      short loc_1800336EC
0x18003368d  xor     r9d, r9d; this
0x180033690  mov     r8, rbx; unsigned __int16 *
0x180033693  mov     rdx, r14; lpFileName
0x180033696  mov     rcx, rdi; void *
0x180033699  call    ?pmdcAllocMDC@@YAPEAVMDC@@PEAXPEBG10@Z; pmdcAllocMDC(void *,ushort const *,ushort const *,void *)
0x18003369e  mov     rbx, rax
0x1800336a1  test    rax, rax
0x1800336a4  jz      short loc_1800336E4
0x1800336a6  mov     [rbp+10h], rax
0x1800336aa  test    rsi, rsi
0x1800336ad  jz      short loc_1800336C3
0x1800336af  mov     rcx, rsi; this
0x1800336b2  call    ?bEmpty@ERECTL@@QEAAHXZ; ERECTL::bEmpty(void)
0x1800336b7  test    eax, eax
0x1800336b9  jnz     short loc_1800336FA
0x1800336bb  movups  xmm0, xmmword ptr [rsi]
0x1800336be  movdqu  xmmword ptr [rbx+3Ch], xmm0
0x1800336c3  xor     edx, edx
0x1800336c5  mov     r8d, 8005h
0x1800336cb  mov     rcx, rdi
0x1800336ce  call    cs:__imp_NtGdiSetBoundsRect
0x1800336d5  nop     dword ptr [rax+rax+00h]
0x1800336da  mov     rcx, rdi
0x1800336dd  call    GdiTrackHCreate
0x1800336e2  jmp     short loc_1800336EE
0x1800336e4  mov     rcx, rdi; HDC
0x1800336e7  call    InternalDeleteDC
0x1800336ec  xor     eax, eax
0x1800336ee  add     rsp, 20h
0x1800336f2  pop     r14
0x1800336f4  pop     rdi
0x1800336f5  pop     rsi
0x1800336f6  pop     rbp
0x1800336f7  pop     rbx
0x1800336f8  retn
0x1800336fa  mov     ecx, 57h ; 'W'
0x1800336ff  call    cs:__imp_GdiSetLastError
0x180033706  nop     dword ptr [rax+rax+00h]
0x18003370b  or      dword ptr [rbx+20h], 2
0x18003370f  mov     rcx, rbx; this
0x180033712  call    ?vFreeMDC@@YAXPEAVMDC@@@Z; vFreeMDC(MDC *)
0x180033717  mov     qword ptr [rbp+10h], 0
0x18003371f  jmp     short loc_1800336E4
```
