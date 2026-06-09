# TB_OnDestroy

- ea: `0x180029d2c`
- end: `0x180029ed1`
- name: `TB_OnDestroy`
- size: `421`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18002aab0`

## callees

- `0x1800263a8`
- `0x180029d2c`
- `0x18002fd4c`
- `0x180085890`
- `0x18008698c`
- `0x1800876c0`

## import_xrefs

- `GDI32!DeleteObject` at `0x180029dc1`
- `GDI32!DeleteObject` at `0x180029e40`
- `GDI32!DeleteObject` at `0x180029dc1`
- `GDI32!DeleteObject` at `0x180029e40`
- `KERNEL32!LocalFree` at `0x180029e0a`
- `KERNEL32!LocalFree` at `0x180029e25`
- `KERNEL32!LocalFree` at `0x180029e75`
- `KERNEL32!LocalFree` at `0x180029e87`
- `KERNEL32!LocalFree` at `0x180029ea1`
- `KERNEL32!LocalFree` at `0x180029eaa`
- `KERNEL32!LocalFree` at `0x180029e0a`
- `KERNEL32!LocalFree` at `0x180029e25`
- `KERNEL32!LocalFree` at `0x180029e75`
- `KERNEL32!LocalFree` at `0x180029e87`
- `KERNEL32!LocalFree` at `0x180029ea1`
- `KERNEL32!LocalFree` at `0x180029eaa`
- `KERNEL32!LocalSize` at `0x180029dfa`
- `KERNEL32!LocalSize` at `0x180029dfa`
- `USER32!IsWindow` at `0x180029d8b`
- `USER32!IsWindow` at `0x180029d8b`
- `USER32!DestroyWindow` at `0x180029d99`
- `USER32!DestroyWindow` at `0x180029d99`
- `USER32!SetWindowLongPtrW` at `0x180029eb8`
- `USER32!SetWindowLongPtrW` at `0x180029eb8`

## pseudocode

```c
__int64 __fastcall TB_OnDestroy(char *hMem)
{
  HWND v1; // r12
  int i; // edi
  _QWORD *v4; // rcx
  void *v5; // rcx
  HLOCAL *v6; // rsi
  unsigned __int64 v7; // r14
  HLOCAL v8; // r15
  int v9; // ebp
  HLOCAL v10; // rdi
  void *v11; // rcx
  struct _IMAGELIST *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx

  v1 = *(HWND *)hMem;
  for ( i = 0; i < *((_DWORD *)hMem + 50); ++i )
  {
    v4 = (_QWORD *)(*((_QWORD *)hMem + 10) + 8 * (5LL * i + 3));
    if ( *v4 != -1 && *v4 >= 0x10000u )
      Str_Set(v4, 0);
  }
  if ( (*((_DWORD *)hMem + 4) & 0x100) != 0 && IsWindow(*((HWND *)hMem + 13)) )
  {
    DestroyWindow(*((HWND *)hMem + 13));
    *((_QWORD *)hMem + 13) = 0;
  }
  if ( *((_QWORD *)hMem + 30) )
    DestroyDragProxy();
  v5 = (void *)*((_QWORD *)hMem + 9);
  if ( v5 )
    DeleteObject(v5);
  ReleaseMonoDC(hMem);
  if ( *((int *)hMem + 40) > 0 )
  {
    v6 = (HLOCAL *)*((_QWORD *)hMem + 19);
    v7 = 0;
    v8 = 0;
    v9 = 0;
    do
    {
      v10 = *v6;
      if ( (unsigned __int64)*v6 >= v7 || v10 <= v8 )
      {
        v8 = *v6;
        v7 = (unsigned __int64)v10 + 2 * (LocalSize(*v6) >> 1);
        LocalFree(*v6);
      }
      ++v6;
      ++v9;
    }
    while ( v9 < *((_DWORD *)hMem + 40) );
    LocalFree(*((HLOCAL *)hMem + 19));
  }
  v11 = (void *)*((_QWORD *)hMem + 16);
  if ( v11 && (hMem[316] & 4) != 0 )
    DeleteObject(v11);
  if ( *((_QWORD *)hMem + 18) )
  {
    v12 = 0;
    if ( *((int *)hMem + 70) > 0 )
      v12 = (struct _IMAGELIST *)**((_QWORD **)hMem + 34);
    ImageList_Destroy(v12);
  }
  v13 = (void *)*((_QWORD *)hMem + 18);
  if ( v13 )
    LocalFree(v13);
  v14 = (void *)*((_QWORD *)hMem + 34);
  if ( v14 )
    LocalFree(v14);
  Str_Set(hMem + 112, 0);
  v15 = (void *)*((_QWORD *)hMem + 10);
  if ( v15 )
    LocalFree(v15);
  LocalFree(hMem);
  SetWindowLongPtrW(v1, 0, 0);
  return TerminateDitherBrush();
}

```

## disassembly

```asm
0x180029d2c  push    rbx
0x180029d2e  push    rbp
0x180029d2f  push    rsi
0x180029d30  push    rdi
0x180029d31  push    r12
0x180029d33  push    r14
0x180029d35  push    r15
0x180029d37  sub     rsp, 20h
0x180029d3b  mov     r12, [rcx]
0x180029d3e  xor     edi, edi
0x180029d40  mov     rbx, rcx
0x180029d43  cmp     [rcx+0C8h], edi
0x180029d49  jle     short loc_180029D7E
0x180029d4b  movsxd  rax, edi
0x180029d4e  lea     rcx, [rax+rax*4]
0x180029d52  mov     rax, [rbx+50h]
0x180029d56  lea     rcx, [rcx+3]
0x180029d5a  lea     rcx, [rax+rcx*8]
0x180029d5e  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180029d62  jz      short loc_180029D74
0x180029d64  cmp     qword ptr [rcx], 10000h
0x180029d6b  jb      short loc_180029D74
0x180029d6d  xor     edx, edx
0x180029d6f  call    Str_Set
0x180029d74  inc     edi
0x180029d76  cmp     edi, [rbx+0C8h]
0x180029d7c  jl      short loc_180029D4B
0x180029d7e  test    dword ptr [rbx+10h], 100h
0x180029d85  jz      short loc_180029DA7
0x180029d87  mov     rcx, [rbx+68h]; hWnd
0x180029d8b  call    cs:__imp_IsWindow
0x180029d91  test    eax, eax
0x180029d93  jz      short loc_180029DA7
0x180029d95  mov     rcx, [rbx+68h]; hWnd
0x180029d99  call    cs:__imp_DestroyWindow
0x180029d9f  mov     qword ptr [rbx+68h], 0
0x180029da7  mov     rcx, [rbx+0F0h]
0x180029dae  test    rcx, rcx
0x180029db1  jz      short loc_180029DB8
0x180029db3  call    DestroyDragProxy
0x180029db8  mov     rcx, [rbx+48h]; ho
0x180029dbc  test    rcx, rcx
0x180029dbf  jz      short loc_180029DC7
0x180029dc1  call    cs:__imp_DeleteObject
0x180029dc7  mov     rcx, rbx
0x180029dca  call    ReleaseMonoDC
0x180029dcf  cmp     dword ptr [rbx+0A0h], 0
0x180029dd6  jle     short loc_180029E2B
0x180029dd8  mov     rsi, [rbx+98h]
0x180029ddf  xor     r14d, r14d
0x180029de2  xor     r15d, r15d
0x180029de5  xor     ebp, ebp
0x180029de7  mov     rdi, [rsi]
0x180029dea  cmp     rdi, r14
0x180029ded  jnb     short loc_180029DF4
0x180029def  cmp     rdi, r15
0x180029df2  ja      short loc_180029E10
0x180029df4  mov     rcx, rdi; hMem
0x180029df7  mov     r15, rdi
0x180029dfa  call    cs:__imp_LocalSize
0x180029e00  mov     rcx, [rsi]; hMem
0x180029e03  shr     rax, 1
0x180029e06  lea     r14, [rdi+rax*2]
0x180029e0a  call    cs:__imp_LocalFree
0x180029e10  add     rsi, 8
0x180029e14  inc     ebp
0x180029e16  cmp     ebp, [rbx+0A0h]
0x180029e1c  jl      short loc_180029DE7
0x180029e1e  mov     rcx, [rbx+98h]; hMem
0x180029e25  call    cs:__imp_LocalFree
0x180029e2b  mov     rcx, [rbx+80h]; ho
0x180029e32  test    rcx, rcx
0x180029e35  jz      short loc_180029E46
0x180029e37  test    byte ptr [rbx+13Ch], 4
0x180029e3e  jz      short loc_180029E46
0x180029e40  call    cs:__imp_DeleteObject
0x180029e46  cmp     qword ptr [rbx+90h], 0
0x180029e4e  jz      short loc_180029E69
0x180029e50  xor     ecx, ecx
0x180029e52  cmp     [rbx+118h], ecx
0x180029e58  jle     short loc_180029E64
0x180029e5a  mov     rax, [rbx+110h]
0x180029e61  mov     rcx, [rax]; himl
0x180029e64  call    ImageList_Destroy
0x180029e69  mov     rcx, [rbx+90h]; hMem
0x180029e70  test    rcx, rcx
0x180029e73  jz      short loc_180029E7B
0x180029e75  call    cs:__imp_LocalFree
0x180029e7b  mov     rcx, [rbx+110h]; hMem
0x180029e82  test    rcx, rcx
0x180029e85  jz      short loc_180029E8D
0x180029e87  call    cs:__imp_LocalFree
0x180029e8d  lea     rcx, [rbx+70h]
0x180029e91  xor     edx, edx
0x180029e93  call    Str_Set
0x180029e98  mov     rcx, [rbx+50h]; hMem
0x180029e9c  test    rcx, rcx
0x180029e9f  jz      short loc_180029EA7
0x180029ea1  call    cs:__imp_LocalFree
0x180029ea7  mov     rcx, rbx; hMem
0x180029eaa  call    cs:__imp_LocalFree
0x180029eb0  xor     r8d, r8d; dwNewLong
0x180029eb3  xor     edx, edx; nIndex
0x180029eb5  mov     rcx, r12; hWnd
0x180029eb8  call    cs:__imp_SetWindowLongPtrW
0x180029ebe  add     rsp, 20h
0x180029ec2  pop     r15
0x180029ec4  pop     r14
0x180029ec6  pop     r12
0x180029ec8  pop     rdi
0x180029ec9  pop     rsi
0x180029eca  pop     rbp
0x180029ecb  pop     rbx
0x180029ecc  jmp     TerminateDitherBrush
```
