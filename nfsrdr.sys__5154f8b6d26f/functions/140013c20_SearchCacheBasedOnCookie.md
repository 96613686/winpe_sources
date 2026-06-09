# SearchCacheBasedOnCookie

- ea: `0x140013c20`
- end: `0x140013db1`
- name: `SearchCacheBasedOnCookie`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140018804`

## callees

- `0x140013c20`
- `0x1400159cc`
- `0x1400159fc`

## pseudocode

```c
__int64 __fastcall SearchCacheBasedOnCookie(__int64 a1, __int64 a2)
{
  __int64 **v4; // rax
  unsigned int v5; // ebx
  __int64 *v6; // rdx
  int v7; // r8d
  unsigned __int64 v8; // rcx
  __int16 v9; // ax
  __int64 v10; // r10
  int v11; // r9d
  unsigned __int16 v12; // r9
  unsigned __int64 v13; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids);
  if ( !a1 || !a2 )
  {
    v5 = -1073741811;
    goto LABEL_24;
  }
  v4 = *(__int64 ***)(a1 + 8);
  v5 = -1073741275;
  v6 = *v4;
  *(_QWORD *)(a2 + 24) = *v4;
  if ( v6 )
  {
    *(_WORD *)(a2 + 16) = 0;
    while ( 1 )
    {
      v7 = *((_DWORD *)v6 + 6);
      v8 = (unsigned __int64)(v6 + 5);
      v9 = 0;
      if ( v7 <= 0 )
      {
        LOWORD(v11) = 0;
      }
      else
      {
        v10 = *(_QWORD *)(a2 + 80);
        do
        {
          LOWORD(v11) = v9;
          if ( v10 == *(_QWORD *)(v8 + 8) )
            break;
          v11 = (unsigned __int16)(v9 + 1);
          *(_WORD *)(a2 + 16) = v11;
          v7 = *((_DWORD *)v6 + 6);
          ++v9;
          v8 = (*(_DWORD *)(v8 + 16) + 184 + v8 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
        }
        while ( v11 < v7 );
      }
      if ( (unsigned __int16)v11 < v7 && *(_QWORD *)(a2 + 80) == *(_QWORD *)(v8 + 8) )
        break;
      *(_WORD *)(a2 + 16) = 0;
      v6 = (__int64 *)*v6;
      if ( v6 == **(__int64 ***)(a1 + 8) )
        goto LABEL_24;
    }
    v12 = v11 + 1;
    *(_WORD *)(a2 + 16) = v12;
    if ( v12 < *((int *)v6 + 6) )
    {
      v13 = (*(_DWORD *)(v8 + 16) + 184 + v8 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      goto LABEL_22;
    }
    if ( v6 != *(__int64 **)(a1 + 8) )
    {
      v6 = (__int64 *)*v6;
      *(_WORD *)(a2 + 16) = 0;
      v13 = (unsigned __int64)(v6 + 5);
LABEL_22:
      *(_QWORD *)(a2 + 24) = v6;
      v5 = 0;
      *(_DWORD *)(a2 + 20) = *(_DWORD *)a1;
      *(_QWORD *)(a2 + 32) = v13;
    }
  }
LABEL_24:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids);
  return v5;
}

```

## disassembly

```asm
0x140013c20  sub     rsp, 28h
0x140013c24  mov     [rsp+28h+arg_8], rbp
0x140013c29  mov     [rsp+28h+arg_10], rsi
0x140013c2e  mov     rsi, rdx
0x140013c31  mov     [rsp+28h+var_8], rdi
0x140013c36  mov     rdi, rcx
0x140013c39  mov     rcx, cs:WPP_GLOBAL_Control
0x140013c40  lea     rbp, WPP_GLOBAL_Control
0x140013c47  cmp     rcx, rbp
0x140013c4a  jz      short loc_140013C68
0x140013c4c  mov     eax, [rcx+2Ch]
0x140013c4f  test    al, 40h
0x140013c51  jz      short loc_140013C68
0x140013c53  mov     rcx, [rcx+18h]
0x140013c57  lea     r8, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids
0x140013c5e  mov     edx, 0Ah
0x140013c63  call    WPP_SF_
0x140013c68  mov     [rsp+28h+arg_0], rbx
0x140013c6d  test    rdi, rdi
0x140013c70  jz      loc_140013D65
0x140013c76  test    rsi, rsi
0x140013c79  jz      loc_140013D65
0x140013c7f  mov     rax, [rdi+8]
0x140013c83  mov     ebx, 0C0000225h
0x140013c88  mov     rdx, [rax]
0x140013c8b  mov     [rsi+18h], rdx
0x140013c8f  test    rdx, rdx
0x140013c92  jz      loc_140013D6A
0x140013c98  xor     eax, eax
0x140013c9a  mov     [rsi+10h], ax
0x140013c9e  mov     r8d, [rdx+18h]
0x140013ca2  lea     rcx, [rdx+28h]
0x140013ca6  xor     eax, eax
0x140013ca8  test    r8d, r8d
0x140013cab  jle     short loc_140013CEB
0x140013cad  mov     r10, [rsi+50h]
0x140013cb1  movzx   r9d, ax
0x140013cb5  cmp     r10, [rcx+8]
0x140013cb9  jz      short loc_140013CEF
0x140013cbb  inc     ax
0x140013cbe  movzx   r9d, ax
0x140013cc2  mov     [rsi+10h], r9w
0x140013cc7  mov     eax, [rcx+10h]
0x140013cca  add     rcx, 7
0x140013cce  mov     r8d, [rdx+18h]
0x140013cd2  add     eax, 0B8h
0x140013cd7  cdqe
0x140013cd9  add     rcx, rax
0x140013cdc  movzx   eax, r9w
0x140013ce0  and     rcx, 0FFFFFFFFFFFFFFF8h
0x140013ce4  cmp     r9d, r8d
0x140013ce7  jl      short loc_140013CB1
0x140013ce9  jmp     short loc_140013CEF
0x140013ceb  movzx   r9d, ax
0x140013cef  movzx   eax, r9w
0x140013cf3  cmp     eax, r8d
0x140013cf6  jge     short loc_140013D02
0x140013cf8  mov     rax, [rcx+8]
0x140013cfc  cmp     [rsi+50h], rax
0x140013d00  jz      short loc_140013D16
0x140013d02  xor     eax, eax
0x140013d04  mov     [rsi+10h], ax
0x140013d08  mov     rax, [rdi+8]
0x140013d0c  mov     rdx, [rdx]
0x140013d0f  cmp     rdx, [rax]
0x140013d12  jz      short loc_140013D6A
0x140013d14  jmp     short loc_140013C9E
0x140013d16  inc     r9w
0x140013d1a  movzx   eax, r9w
0x140013d1e  mov     [rsi+10h], ax
0x140013d22  cmp     eax, [rdx+18h]
0x140013d25  jl      short loc_140013D3F
0x140013d27  cmp     rdx, [rdi+8]
0x140013d2b  jz      short loc_140013D6A
0x140013d2d  mov     rcx, [rdx]
0x140013d30  xor     eax, eax
0x140013d32  mov     rdx, rcx
0x140013d35  mov     [rsi+10h], ax
0x140013d39  add     rcx, 28h ; '('
0x140013d3d  jmp     short loc_140013D54
0x140013d3f  mov     eax, [rcx+10h]
0x140013d42  add     rcx, 7
0x140013d46  add     eax, 0B8h
0x140013d4b  cdqe
0x140013d4d  add     rcx, rax
0x140013d50  and     rcx, 0FFFFFFFFFFFFFFF8h
0x140013d54  mov     [rsi+18h], rdx
0x140013d58  xor     ebx, ebx
0x140013d5a  mov     eax, [rdi]
0x140013d5c  mov     [rsi+14h], eax
0x140013d5f  mov     [rsi+20h], rcx
0x140013d63  jmp     short loc_140013D6A
0x140013d65  mov     ebx, 0C000000Dh
0x140013d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140013d71  mov     rdi, [rsp+28h+var_8]
0x140013d76  cmp     rcx, rbp
0x140013d79  mov     rbp, [rsp+28h+arg_8]
0x140013d7e  mov     rsi, [rsp+28h+arg_10]
0x140013d83  jz      short loc_140013DA4
0x140013d85  mov     eax, [rcx+2Ch]
0x140013d88  test    al, 40h
0x140013d8a  jz      short loc_140013DA4
0x140013d8c  mov     rcx, [rcx+18h]
0x140013d90  lea     r8, WPP_28507b2526ce3d515390bac3daa00a2b_Traceguids
0x140013d97  mov     edx, 0Bh
0x140013d9c  mov     r9d, ebx
0x140013d9f  call    WPP_SF_d
0x140013da4  mov     eax, ebx
0x140013da6  mov     rbx, [rsp+28h+arg_0]
0x140013dab  add     rsp, 28h
0x140013daf  retn
```
