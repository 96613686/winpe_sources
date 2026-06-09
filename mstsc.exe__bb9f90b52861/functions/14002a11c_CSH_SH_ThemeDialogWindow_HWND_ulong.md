# CSH::SH_ThemeDialogWindow(HWND__ *,ulong)

- ea: `0x14002a11c`
- end: `0x14002a2c7`
- name: `?SH_ThemeDialogWindow@CSH@@QEAAJPEAUHWND__@@K@Z`
- size: `427`
- prototype: `__int64 __fastcall(CSH *__hidden this, HWND, unsigned int)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140045184`
- `0x140046230`
- `0x140046c20`
- `0x140047d84`
- `0x1400487b8`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14002a11c`
- `0x140114010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x14002a15b`
- `KERNEL32!LoadLibraryW` at `0x14002a15b`
- `KERNEL32!GetProcAddress` at `0x14002a17b`
- `KERNEL32!GetProcAddress` at `0x14002a17b`
- `KERNEL32!GetLastError` at `0x14002a22b`
- `KERNEL32!GetLastError` at `0x14002a22b`

## string_xrefs

- `0x14002a154`: `uxtheme.dll`

## pseudocode

```c
__int64 __fastcall CSH::SH_ThemeDialogWindow(CSH *this, HWND a2)
{
  int v4; // esi
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  unsigned int v7; // eax
  __int64 v8; // rdx
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 (__fastcall *v11)(HWND, __int64); // rax
  unsigned int v12; // eax

  v4 = -2147467263;
  if ( *((_DWORD *)this + 674) )
    return (unsigned int)v4;
  if ( !*((_QWORD *)this + 336) )
  {
    LibraryW = LoadLibraryW(L"uxtheme.dll");
    *((_QWORD *)this + 336) = LibraryW;
    if ( !LibraryW )
    {
      *((_DWORD *)this + 674) = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          67,
          WPP_b7ae6d635a30399768ffbc73af776916_Traceguids,
          CurrentThreadActivityIdPrefix,
          LastError);
      }
      goto LABEL_18;
    }
    ProcAddress = GetProcAddress(LibraryW, "EnableThemeDialogTexture");
    *((_QWORD *)this + 338) = ProcAddress;
    if ( ProcAddress )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 66;
        goto LABEL_13;
      }
    }
    else
    {
      *((_DWORD *)this + 674) = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 65;
LABEL_13:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids, v7);
      }
    }
  }
LABEL_18:
  v11 = (__int64 (__fastcall *)(HWND, __int64))*((_QWORD *)this + 338);
  if ( v11 )
  {
    v4 = v11(a2, 6);
    if ( v4 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids, v12, v4);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14002a11c  push    rbx
0x14002a11e  push    rbp
0x14002a11f  push    rsi
0x14002a120  push    rdi
0x14002a121  push    r15
0x14002a123  sub     rsp, 30h
0x14002a127  cmp     dword ptr [rcx+0A88h], 0
0x14002a12e  mov     rbp, rdx
0x14002a131  mov     rdi, rcx
0x14002a134  mov     esi, 80004001h
0x14002a139  jnz     loc_14002A2BA
0x14002a13f  cmp     qword ptr [rcx+0A80h], 0
0x14002a147  lea     r15, WPP_GLOBAL_Control
0x14002a14e  jnz     loc_14002A25B
0x14002a154  lea     rcx, aUxthemeDll; "uxtheme.dll"
0x14002a15b  call    cs:__imp_LoadLibraryW
0x14002a161  mov     [rdi+0A80h], rax
0x14002a168  test    rax, rax
0x14002a16b  jz      loc_14002A209
0x14002a171  lea     rdx, aEnablethemedia; "EnableThemeDialogTexture"
0x14002a178  mov     rcx, rax; hModule
0x14002a17b  call    cs:__imp_GetProcAddress
0x14002a181  mov     [rdi+0A90h], rax
0x14002a188  test    rax, rax
0x14002a18b  jnz     short loc_14002A1C7
0x14002a18d  mov     dword ptr [rdi+0A88h], 1
0x14002a197  mov     rax, cs:WPP_GLOBAL_Control
0x14002a19e  cmp     rax, r15
0x14002a1a1  jz      loc_14002A25B
0x14002a1a7  test    byte ptr [rax+1Ch], 1
0x14002a1ab  jz      loc_14002A25B
0x14002a1b1  cmp     byte ptr [rax+19h], 2
0x14002a1b5  jb      loc_14002A25B
0x14002a1bb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002a1c0  mov     edx, 41h ; 'A'
0x14002a1c5  jmp     short loc_14002A1ED
0x14002a1c7  mov     rax, cs:WPP_GLOBAL_Control
0x14002a1ce  cmp     rax, r15
0x14002a1d1  jz      loc_14002A25B
0x14002a1d7  test    byte ptr [rax+1Ch], 1
0x14002a1db  jz      short loc_14002A25B
0x14002a1dd  cmp     byte ptr [rax+19h], 4
0x14002a1e1  jb      short loc_14002A25B
0x14002a1e3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002a1e8  mov     edx, 42h ; 'B'
0x14002a1ed  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a1f4  lea     r8, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids
0x14002a1fb  mov     r9d, eax
0x14002a1fe  mov     rcx, [rcx+10h]
0x14002a202  call    WPP_SF_d
0x14002a207  jmp     short loc_14002A25B
0x14002a209  mov     dword ptr [rdi+0A88h], 1
0x14002a213  mov     rax, cs:WPP_GLOBAL_Control
0x14002a21a  cmp     rax, r15
0x14002a21d  jz      short loc_14002A25B
0x14002a21f  test    byte ptr [rax+1Ch], 1
0x14002a223  jz      short loc_14002A25B
0x14002a225  cmp     byte ptr [rax+19h], 2
0x14002a229  jb      short loc_14002A25B
0x14002a22b  call    cs:__imp_GetLastError
0x14002a231  mov     ebx, eax
0x14002a233  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002a238  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a23f  lea     r8, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids
0x14002a246  mov     edx, 43h ; 'C'
0x14002a24b  mov     [rsp+58h+var_38], ebx
0x14002a24f  mov     r9d, eax
0x14002a252  mov     rcx, [rcx+10h]
0x14002a256  call    WPP_SF_Dd
0x14002a25b  mov     rax, [rdi+0A90h]
0x14002a262  test    rax, rax
0x14002a265  jz      short loc_14002A2BA
0x14002a267  mov     edx, 6
0x14002a26c  mov     rcx, rbp
0x14002a26f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002a274  mov     esi, eax
0x14002a276  test    eax, eax
0x14002a278  jns     short loc_14002A2BA
0x14002a27a  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a281  cmp     rcx, r15
0x14002a284  jz      short loc_14002A2BA
0x14002a286  test    byte ptr [rcx+1Ch], 1
0x14002a28a  jz      short loc_14002A2BA
0x14002a28c  cmp     byte ptr [rcx+19h], 2
0x14002a290  jb      short loc_14002A2BA
0x14002a292  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002a297  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a29e  lea     r8, WPP_b7ae6d635a30399768ffbc73af776916_Traceguids
0x14002a2a5  mov     edx, 44h ; 'D'
0x14002a2aa  mov     [rsp+58h+var_38], esi
0x14002a2ae  mov     r9d, eax
0x14002a2b1  mov     rcx, [rcx+10h]
0x14002a2b5  call    WPP_SF_Dd
0x14002a2ba  mov     eax, esi
0x14002a2bc  add     rsp, 30h
0x14002a2c0  pop     r15
0x14002a2c2  pop     rdi
0x14002a2c3  pop     rsi
0x14002a2c4  pop     rbp
0x14002a2c5  pop     rbx
0x14002a2c6  retn
```
