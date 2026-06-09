# CTSGraphics::RegionAlloc(tagTS_GFX_RECT *,uint,void * *)

- ea: `0x18006d7f0`
- end: `0x18006da60`
- name: `?RegionAlloc@CTSGraphics@@UEAAJPEAUtagTS_GFX_RECT@@IPEAPEAX@Z`
- size: `624`
- prototype: `__int64 __fastcall(CTSGraphics *__hidden this, struct tagTS_GFX_RECT *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18006d550`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x18006d7f0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18006d924`
- `KERNEL32!GetLastError` at `0x18006d9aa`
- `KERNEL32!GetLastError` at `0x18006d9d2`
- `KERNEL32!GetLastError` at `0x18006d924`
- `KERNEL32!GetLastError` at `0x18006d9aa`
- `KERNEL32!GetLastError` at `0x18006d9d2`
- `GDI32!CreateRectRgn` at `0x18006d825`
- `GDI32!CreateRectRgn` at `0x18006d897`
- `GDI32!CreateRectRgn` at `0x18006d825`
- `GDI32!CreateRectRgn` at `0x18006d897`
- `GDI32!SetRectRgn` at `0x18006d8c9`
- `GDI32!SetRectRgn` at `0x18006d8c9`
- `GDI32!CombineRgn` at `0x18006d96d`
- `GDI32!CombineRgn` at `0x18006d96d`
- `GDI32!DeleteObject` at `0x18006da0a`
- `GDI32!DeleteObject` at `0x18006da18`
- `GDI32!DeleteObject` at `0x18006da0a`
- `GDI32!DeleteObject` at `0x18006da18`

## pseudocode

```c
__int64 __fastcall CTSGraphics::RegionAlloc(CTSGraphics *this, struct tagTS_GFX_RECT *a2, unsigned int a3, HRGN *a4)
{
  int v7; // r9d
  int v8; // r8d
  int v9; // edx
  int v10; // ecx
  HRGN RectRgn; // rdi
  HRGN v12; // rbp
  int v13; // ebx
  unsigned int i; // r14d
  DWORD v16; // ebx
  unsigned int v17; // eax
  DWORD LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v20; // rdx
  unsigned int v21; // eax

  if ( a4 && (a2 || !a3) )
  {
    if ( a3 )
    {
      v7 = *((_DWORD *)a2 + 3);
      v8 = *((_DWORD *)a2 + 2);
      v9 = *((_DWORD *)a2 + 1);
      v10 = *(_DWORD *)a2;
    }
    else
    {
      v7 = 0;
      v8 = 0;
      v9 = 0;
      v10 = 0;
    }
    RectRgn = CreateRectRgn(v10, v9, v8, v7);
    if ( RectRgn )
    {
      v12 = 0;
      if ( a3 > 1 )
      {
        v12 = CreateRectRgn(0, 0, 0, 0);
        for ( i = 1; ; ++i )
        {
          if ( i >= a3 )
            goto LABEL_7;
          if ( !SetRectRgn(
                  v12,
                  *((_DWORD *)a2 + 4 * i),
                  *((_DWORD *)a2 + 4 * i + 1),
                  *((_DWORD *)a2 + 4 * i + 2),
                  *((_DWORD *)a2 + 4 * i + 3)) )
            break;
          if ( !CombineRgn(RectRgn, RectRgn, v12, 2) )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              LastError = GetLastError();
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              v20 = 87;
              goto LABEL_37;
            }
LABEL_20:
            v13 = -2147467259;
            goto LABEL_8;
          }
        }
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 86;
LABEL_37:
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v20,
            WPP_858788a8f1cd3b98711f16bb2674a6fa_Traceguids,
            CurrentThreadActivityIdPrefix,
            LastError);
        }
        goto LABEL_20;
      }
LABEL_7:
      *a4 = RectRgn;
      v13 = 0;
LABEL_8:
      if ( v12 )
        DeleteObject(v12);
      if ( v13 < 0 )
        DeleteObject(RectRgn);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = GetLastError();
        v17 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_858788a8f1cd3b98711f16bb2674a6fa_Traceguids, v17, v16);
      }
      return (unsigned int)-2147467259;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, WPP_858788a8f1cd3b98711f16bb2674a6fa_Traceguids, v21);
    }
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18006d7f0  push    rbx
0x18006d7f2  push    rbp
0x18006d7f3  push    rsi
0x18006d7f4  push    rdi
0x18006d7f5  push    r14
0x18006d7f7  push    r15
0x18006d7f9  sub     rsp, 38h
0x18006d7fd  mov     r15, r9
0x18006d800  mov     esi, r8d
0x18006d803  mov     rbx, rdx
0x18006d806  test    r9, r9
0x18006d809  jz      short loc_18006D86F
0x18006d80b  test    rdx, rdx
0x18006d80e  jz      loc_18006D8F8
0x18006d814  test    esi, esi
0x18006d816  jz      short loc_18006D863
0x18006d818  mov     r9d, [rdx+0Ch]; y2
0x18006d81c  mov     r8d, [rdx+8]; x2
0x18006d820  mov     edx, [rdx+4]; y1
0x18006d823  mov     ecx, [rbx]; x1
0x18006d825  call    cs:__imp_CreateRectRgn
0x18006d82b  mov     rdi, rax
0x18006d82e  test    rax, rax
0x18006d831  jz      loc_18006D905
0x18006d837  xor     ebp, ebp
0x18006d839  cmp     esi, 1
0x18006d83c  ja      short loc_18006D88D
0x18006d83e  mov     [r15], rdi
0x18006d841  xor     ebx, ebx
0x18006d843  test    rbp, rbp
0x18006d846  jnz     loc_18006DA07
0x18006d84c  test    ebx, ebx
0x18006d84e  js      loc_18006DA15
0x18006d854  mov     eax, ebx
0x18006d856  add     rsp, 38h
0x18006d85a  pop     r15
0x18006d85c  pop     r14
0x18006d85e  pop     rdi
0x18006d85f  pop     rsi
0x18006d860  pop     rbp
0x18006d861  pop     rbx
0x18006d862  retn
0x18006d863  xor     r9d, r9d
0x18006d866  xor     r8d, r8d
0x18006d869  xor     edx, edx
0x18006d86b  xor     ecx, ecx
0x18006d86d  jmp     short loc_18006D825
0x18006d86f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d876  lea     rax, WPP_GLOBAL_Control
0x18006d87d  cmp     rcx, rax
0x18006d880  jnz     loc_18006DA23
0x18006d886  mov     ebx, 80070057h
0x18006d88b  jmp     short loc_18006D854
0x18006d88d  xor     r9d, r9d; y2
0x18006d890  xor     r8d, r8d; x2
0x18006d893  xor     edx, edx; y1
0x18006d895  xor     ecx, ecx; x1
0x18006d897  call    cs:__imp_CreateRectRgn
0x18006d89d  mov     rbp, rax
0x18006d8a0  mov     r14d, 1
0x18006d8a6  cmp     r14d, esi
0x18006d8a9  jnb     short loc_18006D83E
0x18006d8ab  mov     edx, r14d
0x18006d8ae  add     rdx, rdx
0x18006d8b1  mov     ecx, [rbx+rdx*8+0Ch]
0x18006d8b5  mov     r9d, [rbx+rdx*8+8]; right
0x18006d8ba  mov     r8d, [rbx+rdx*8+4]; top
0x18006d8bf  mov     edx, [rbx+rdx*8]; left
0x18006d8c2  mov     [rsp+68h+bottom], ecx; bottom
0x18006d8c6  mov     rcx, rbp; hrgn
0x18006d8c9  call    cs:__imp_SetRectRgn
0x18006d8cf  test    eax, eax
0x18006d8d1  jnz     loc_18006D95E
0x18006d8d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d8de  lea     rax, WPP_GLOBAL_Control
0x18006d8e5  cmp     rcx, rax
0x18006d8e8  jnz     loc_18006D9BE
0x18006d8ee  mov     ebx, 80004005h
0x18006d8f3  jmp     loc_18006D843
0x18006d8f8  test    esi, esi
0x18006d8fa  jnz     loc_18006D86F
0x18006d900  jmp     loc_18006D814
0x18006d905  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d90c  lea     rax, WPP_GLOBAL_Control
0x18006d913  cmp     rcx, rax
0x18006d916  jz      short loc_18006D954
0x18006d918  test    byte ptr [rcx+1Ch], 1
0x18006d91c  jz      short loc_18006D954
0x18006d91e  cmp     byte ptr [rcx+19h], 2
0x18006d922  jb      short loc_18006D954
0x18006d924  call    cs:__imp_GetLastError
0x18006d92a  mov     ebx, eax
0x18006d92c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006d931  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d938  lea     r8, WPP_858788a8f1cd3b98711f16bb2674a6fa_Traceguids
0x18006d93f  mov     edx, 54h ; 'T'
0x18006d944  mov     [rsp+68h+bottom], ebx
0x18006d948  mov     r9d, eax
0x18006d94b  mov     rcx, [rcx+10h]
0x18006d94f  call    WPP_SF_Dd
0x18006d954  mov     ebx, 80004005h
0x18006d959  jmp     loc_18006D854
0x18006d95e  mov     r9d, 2; iMode
0x18006d964  mov     r8, rbp; hrgnSrc2
0x18006d967  mov     rdx, rdi; hrgnSrc1
0x18006d96a  mov     rcx, rdi; hrgnDst
0x18006d96d  call    cs:__imp_CombineRgn
0x18006d973  test    eax, eax
0x18006d975  jz      short loc_18006D97F
0x18006d977  inc     r14d
0x18006d97a  jmp     loc_18006D8A6
0x18006d97f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d986  lea     rax, WPP_GLOBAL_Control
0x18006d98d  cmp     rcx, rax
0x18006d990  jz      loc_18006D8EE
0x18006d996  test    byte ptr [rcx+1Ch], 1
0x18006d99a  jz      loc_18006D8EE
0x18006d9a0  cmp     byte ptr [rcx+19h], 2
0x18006d9a4  jb      loc_18006D8EE
0x18006d9aa  call    cs:__imp_GetLastError
0x18006d9b0  mov     ebx, eax
0x18006d9b2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006d9b7  mov     edx, 57h ; 'W'
0x18006d9bc  jmp     short loc_18006D9E4
0x18006d9be  test    byte ptr [rcx+1Ch], 1
0x18006d9c2  jz      loc_18006D8EE
0x18006d9c8  cmp     byte ptr [rcx+19h], 2
0x18006d9cc  jb      loc_18006D8EE
0x18006d9d2  call    cs:__imp_GetLastError
0x18006d9d8  mov     ebx, eax
0x18006d9da  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006d9df  mov     edx, 56h ; 'V'
0x18006d9e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18006d9eb  lea     r8, WPP_858788a8f1cd3b98711f16bb2674a6fa_Traceguids
0x18006d9f2  mov     r9d, eax
0x18006d9f5  mov     [rsp+68h+bottom], ebx
0x18006d9f9  mov     rcx, [rcx+10h]
0x18006d9fd  call    WPP_SF_Dd
0x18006da02  jmp     loc_18006D8EE
0x18006da07  mov     rcx, rbp; ho
0x18006da0a  call    cs:__imp_DeleteObject
0x18006da10  jmp     loc_18006D84C
0x18006da15  mov     rcx, rdi; ho
0x18006da18  call    cs:__imp_DeleteObject
0x18006da1e  jmp     loc_18006D854
0x18006da23  test    byte ptr [rcx+1Ch], 1
0x18006da27  jz      loc_18006D886
0x18006da2d  cmp     byte ptr [rcx+19h], 2
0x18006da31  jb      loc_18006D886
0x18006da37  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18006da3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006da43  lea     r8, WPP_858788a8f1cd3b98711f16bb2674a6fa_Traceguids
0x18006da4a  mov     edx, 53h ; 'S'
0x18006da4f  mov     r9d, eax
0x18006da52  mov     rcx, [rcx+10h]
0x18006da56  call    WPP_SF_d
0x18006da5b  jmp     loc_18006D886
```
