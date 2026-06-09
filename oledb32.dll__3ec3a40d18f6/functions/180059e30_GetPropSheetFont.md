# GetPropSheetFont

- ea: `0x180059e30`
- end: `0x180059fd5`
- name: `GetPropSheetFont`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180059fdc`

## callees

- `0x1800112b0`
- `0x18003bdac`
- `0x180059e30`
- `0x18007e6ca`
- `0x18007e700`

## import_xrefs

- `KERNEL32!MulDiv` at `0x180059f69`
- `KERNEL32!MulDiv` at `0x180059f69`
- `KERNEL32!LockResource` at `0x180059ed3`
- `KERNEL32!LockResource` at `0x180059ed3`
- `KERNEL32!FreeLibrary` at `0x180059fa4`
- `KERNEL32!FreeLibrary` at `0x180059fa4`
- `KERNEL32!LoadResource` at `0x180059ec1`
- `KERNEL32!LoadResource` at `0x180059ec1`
- `KERNEL32!FindResourceW` at `0x180059eac`
- `KERNEL32!FindResourceW` at `0x180059eac`
- `USER32!ReleaseDC` at `0x180059f7a`
- `USER32!ReleaseDC` at `0x180059f7a`
- `USER32!GetDC` at `0x180059f42`
- `USER32!GetDC` at `0x180059f42`
- `GDI32!GetDeviceCaps` at `0x180059f58`
- `GDI32!GetDeviceCaps` at `0x180059f58`
- `GDI32!CreateFontIndirectW` at `0x180059faf`
- `GDI32!CreateFontIndirectW` at `0x180059faf`

## pseudocode

```c
HFONT GetPropSheetFont()
{
  HMODULE LibraryW; // rax
  HMODULE v1; // rsi
  HRSRC ResourceW; // rax
  HGLOBAL Resource; // rax
  _DWORD *v4; // rax
  __int64 v5; // rbx
  unsigned int v6; // r14d
  __int64 v7; // rdi
  unsigned __int16 *v8; // rbx
  HDC DC; // rax
  HDC v13; // rbp
  int DeviceCaps; // eax
  LOGFONTW lf; // [rsp+20h] [rbp-A8h] BYREF

  memset_0(&lf, 0, sizeof(lf));
  lf.lfHeight = 8;
  lf.lfWeight = 400;
  lf.lfCharSet = 1;
  StringCchCopyW(lf.lfFaceName, 0x20u, L"MS Shell Dlg");
  LibraryW = IsolationAwareLoadLibraryW();
  v1 = LibraryW;
  if ( LibraryW )
  {
    ResourceW = FindResourceW(LibraryW, (LPCWSTR)0x3EE, (LPCWSTR)5);
    if ( ResourceW )
    {
      Resource = LoadResource(v1, ResourceW);
      if ( Resource )
      {
        v4 = LockResource(Resource);
        if ( v4 )
        {
          v5 = 18;
          v6 = *v4 & 0xFFFF0000;
          if ( v6 == -65536 )
            v5 = 26;
          v7 = 1;
          v8 = (unsigned __int16 *)((char *)v4 + v5);
          if ( *v8 == 0xFFFF )
          {
            v8 += 2;
          }
          else
          {
            while ( *v8++ )
              ;
          }
          if ( *v8 == 0xFFFF )
          {
            v8 += 2;
          }
          else
          {
            while ( *v8++ )
              ;
          }
          while ( *v8++ )
            ;
          DC = GetDC(0);
          v13 = DC;
          if ( DC )
          {
            DeviceCaps = GetDeviceCaps(DC, 90);
            lf.lfHeight = -MulDiv(*v8, DeviceCaps, 72);
            ReleaseDC(0, v13);
          }
          if ( v6 == -65536 )
            v7 = 3;
          StringCchCopyW(lf.lfFaceName, 0x20u, &v8[v7]);
        }
      }
    }
    FreeLibrary(v1);
  }
  return CreateFontIndirectW(&lf);
}

```

## disassembly

```asm
0x180059e30  push    rbx
0x180059e32  push    rbp
0x180059e33  push    rsi
0x180059e34  push    rdi
0x180059e35  push    r14
0x180059e37  push    r15
0x180059e39  sub     rsp, 98h
0x180059e40  mov     rax, cs:__security_cookie
0x180059e47  xor     rax, rsp
0x180059e4a  mov     [rsp+0C8h+var_48], rax
0x180059e52  xor     edx, edx; Val
0x180059e54  lea     rcx, [rsp+0C8h+lf]; void *
0x180059e59  lea     r8d, [rdx+5Ch]; Size
0x180059e5d  call    memset_0
0x180059e62  lea     r8, aMsShellDlg; "MS Shell Dlg"
0x180059e69  mov     [rsp+0C8h+lf.lfHeight], 8
0x180059e71  mov     edx, 20h ; ' '; unsigned __int64
0x180059e76  mov     [rsp+0C8h+lf.lfWeight], 190h
0x180059e7e  lea     rcx, [rsp+0C8h+lf.lfFaceName]; unsigned __int16 *
0x180059e83  mov     [rsp+0C8h+lf.lfCharSet], 1
0x180059e88  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180059e8d  call    IsolationAwareLoadLibraryW
0x180059e92  mov     rsi, rax
0x180059e95  test    rax, rax
0x180059e98  jz      loc_180059FAA
0x180059e9e  mov     edx, 3EEh; lpName
0x180059ea3  mov     r8d, 5; lpType
0x180059ea9  mov     rcx, rax; hModule
0x180059eac  call    cs:__imp_FindResourceW
0x180059eb2  test    rax, rax
0x180059eb5  jz      loc_180059FA1
0x180059ebb  mov     rdx, rax; hResInfo
0x180059ebe  mov     rcx, rsi; hModule
0x180059ec1  call    cs:__imp_LoadResource
0x180059ec7  test    rax, rax
0x180059eca  jz      loc_180059FA1
0x180059ed0  mov     rcx, rax; hResData
0x180059ed3  call    cs:__imp_LockResource
0x180059ed9  test    rax, rax
0x180059edc  jz      loc_180059FA1
0x180059ee2  mov     r14d, [rax]
0x180059ee5  mov     ebx, 12h
0x180059eea  and     r14d, 0FFFF0000h
0x180059ef1  mov     ecx, 0FFFFh
0x180059ef6  cmp     r14d, 0FFFF0000h
0x180059efd  lea     edx, [rbx+8]
0x180059f00  cmovz   ebx, edx
0x180059f03  lea     edi, [rdx-18h]
0x180059f06  add     rbx, rax
0x180059f09  cmp     [rbx], cx
0x180059f0c  jnz     short loc_180059F14
0x180059f0e  add     rbx, 4
0x180059f12  jmp     short loc_180059F1F
0x180059f14  movzx   eax, word ptr [rbx]
0x180059f17  add     rbx, rdi
0x180059f1a  test    ax, ax
0x180059f1d  jnz     short loc_180059F14
0x180059f1f  cmp     [rbx], cx
0x180059f22  jnz     short loc_180059F2A
0x180059f24  add     rbx, 4
0x180059f28  jmp     short loc_180059F35
0x180059f2a  movzx   eax, word ptr [rbx]
0x180059f2d  add     rbx, rdi
0x180059f30  test    ax, ax
0x180059f33  jnz     short loc_180059F2A
0x180059f35  movzx   eax, word ptr [rbx]
0x180059f38  add     rbx, rdi
0x180059f3b  test    ax, ax
0x180059f3e  jnz     short loc_180059F35
0x180059f40  xor     ecx, ecx; hWnd
0x180059f42  call    cs:__imp_GetDC
0x180059f48  mov     rbp, rax
0x180059f4b  test    rax, rax
0x180059f4e  jz      short loc_180059F80
0x180059f50  mov     edx, 5Ah ; 'Z'; index
0x180059f55  mov     rcx, rax; hdc
0x180059f58  call    cs:__imp_GetDeviceCaps
0x180059f5e  movzx   ecx, word ptr [rbx]; nNumber
0x180059f61  mov     r8d, 48h ; 'H'; nDenominator
0x180059f67  mov     edx, eax; nNumerator
0x180059f69  call    cs:__imp_MulDiv
0x180059f6f  mov     rdx, rbp; hDC
0x180059f72  xor     ecx, ecx; hWnd
0x180059f74  neg     eax
0x180059f76  mov     [rsp+0C8h+lf.lfHeight], eax
0x180059f7a  call    cs:__imp_ReleaseDC
0x180059f80  mov     eax, 6
0x180059f85  lea     rcx, [rsp+0C8h+lf.lfFaceName]; unsigned __int16 *
0x180059f8a  cmp     r14d, 0FFFF0000h
0x180059f91  cmovz   rdi, rax
0x180059f95  lea     edx, [rax+1Ah]; unsigned __int64
0x180059f98  lea     r8, [rbx+rdi]; unsigned __int16 *
0x180059f9c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180059fa1  mov     rcx, rsi; hLibModule
0x180059fa4  call    cs:__imp_FreeLibrary
0x180059faa  lea     rcx, [rsp+0C8h+lf]; lplf
0x180059faf  call    cs:__imp_CreateFontIndirectW
0x180059fb5  mov     rcx, [rsp+0C8h+var_48]
0x180059fbd  xor     rcx, rsp; StackCookie
0x180059fc0  call    __security_check_cookie
0x180059fc5  add     rsp, 98h
0x180059fcc  pop     r15
0x180059fce  pop     r14
0x180059fd0  pop     rdi
0x180059fd1  pop     rsi
0x180059fd2  pop     rbp
0x180059fd3  pop     rbx
0x180059fd4  retn
```
