# ListView_ExtendedStyleChange

- ea: `0x1800529fc`
- end: `0x180052bb1`
- name: `ListView_ExtendedStyleChange`
- size: `437`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18005a094`
- `0x18005c0a0`

## callees

- `0x180034cd0`
- `0x180035020`
- `0x1800529fc`
- `0x180053d94`
- `0x180058694`
- `0x18005a314`
- `0x180079ae0`
- `0x180085890`

## import_xrefs

- `GDI32!DeleteObject` at `0x180052b6f`
- `GDI32!DeleteObject` at `0x180052b6f`
- `USER32!SendMessageW` at `0x180052a5b`
- `USER32!SendMessageW` at `0x180052a5b`
- `USER32!InvalidateRect` at `0x180052a3e`
- `USER32!InvalidateRect` at `0x180052aad`
- `USER32!InvalidateRect` at `0x180052ac3`
- `USER32!InvalidateRect` at `0x180052b9e`
- `USER32!InvalidateRect` at `0x180052a3e`
- `USER32!InvalidateRect` at `0x180052aad`
- `USER32!InvalidateRect` at `0x180052ac3`
- `USER32!InvalidateRect` at `0x180052b9e`
- `USER32!SetWindowRgn` at `0x180052b90`
- `USER32!SetWindowRgn` at `0x180052b90`

## pseudocode

```c
__int64 __fastcall ListView_ExtendedStyleChange(__int64 a1, int a2, int a3)
{
  unsigned int v4; // ebp
  char v7; // al
  HWND v8; // rcx
  unsigned int v9; // eax
  int v10; // edx
  unsigned int v11; // esi
  struct _IMAGELIST *v12; // rax
  HWND v13; // rcx
  int i; // edi
  __int64 v15; // rsi
  char *v16; // rcx

  v4 = *(_DWORD *)(a1 + 76);
  if ( *(__int64 *)(a1 + 40) < 3 )
  {
    v7 = *(_DWORD *)(a1 + 16) & 3;
    *(_QWORD *)(a1 + 40) = 3;
    if ( v7 == 1 )
    {
      ListView_RUpdateScrollBars();
      InvalidateRect(*(HWND *)a1, 0, 1);
    }
  }
  v8 = *(HWND *)(a1 + 208);
  if ( v8 )
    SendMessageW(v8, 0x41Cu, 0, 0);
  if ( a3 )
    a2 = a3 & a2 | *(_DWORD *)(a1 + 76) & ~a3;
  v9 = a2 & 0xFFFFDDFF;
  v10 = *(_DWORD *)(a1 + 16) & 3;
  if ( !v10 )
    v9 = a2;
  v11 = v9 & 0xFFFFFDFF;
  if ( (*(_DWORD *)(a1 + 16) & 0x1000) == 0 )
    v11 = v9;
  *(_DWORD *)(a1 + 76) = v11;
  if ( (((unsigned __int8)v4 ^ (unsigned __int8)v11) & 1) != 0 && v10 == 1 )
    InvalidateRect(*(HWND *)a1, 0, 1);
  if ( (((unsigned __int16)v4 ^ (unsigned __int16)v11) & 0x18C2) != 0 )
    InvalidateRect(*(HWND *)a1, 0, 1);
  if ( (((unsigned __int8)v4 ^ (unsigned __int8)v11) & 4) != 0 )
  {
    if ( (v11 & 4) != 0 )
    {
      ListView_InitCheckBoxes(a1, 1);
    }
    else
    {
      v12 = (struct _IMAGELIST *)ListView_OnSetImageList(a1, 0, 2);
      if ( v12 )
        ImageList_Destroy(v12);
    }
  }
  if ( (((unsigned __int16)v4 ^ (unsigned __int16)v11) & 0x100) != 0 )
  {
    v13 = *(HWND *)a1;
    if ( (v11 & 0x100) != 0 )
      InitializeFlatSB(v13);
    else
      UninitializeFlatSB(v13);
  }
  if ( (((unsigned __int16)v4 ^ (unsigned __int16)v11) & 0x200) != 0 )
  {
    if ( g_fSlowMachine == -1 )
      g_fSlowMachine = 0;
    if ( (v11 & 0x200) != 0 )
    {
      ListView_RecalcRegion(a1, 1);
    }
    else
    {
      for ( i = 0; i < *(_DWORD *)(a1 + 512); *(_QWORD *)(v15 + 40) = 0 )
      {
        v15 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 8LL) + 8LL * i);
        v16 = *(char **)(v15 + 40);
        if ( (unsigned __int64)(v16 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          DeleteObject(v16);
        ++i;
      }
      SetWindowRgn(*(HWND *)a1, 0, 1);
    }
    InvalidateRect(*(HWND *)a1, 0, 1);
  }
  return v4;
}

```

## disassembly

```asm
0x1800529fc  push    rbx
0x1800529fe  push    rbp
0x1800529ff  push    rsi
0x180052a00  push    rdi
0x180052a01  push    r14
0x180052a03  sub     rsp, 20h
0x180052a07  cmp     qword ptr [rcx+28h], 3
0x180052a0c  mov     esi, r8d
0x180052a0f  mov     ebp, [rcx+4Ch]
0x180052a12  mov     edi, edx
0x180052a14  mov     rbx, rcx
0x180052a17  mov     r14d, 1
0x180052a1d  jge     short loc_180052A44
0x180052a1f  mov     eax, [rcx+10h]
0x180052a22  and     al, 3
0x180052a24  mov     qword ptr [rcx+28h], 3
0x180052a2c  cmp     al, r14b
0x180052a2f  jnz     short loc_180052A44
0x180052a31  call    ListView_RUpdateScrollBars
0x180052a36  mov     rcx, [rbx]; hWnd
0x180052a39  mov     r8d, r14d; bErase
0x180052a3c  xor     edx, edx; lpRect
0x180052a3e  call    cs:__imp_InvalidateRect
0x180052a44  mov     rcx, [rbx+0D0h]; hWnd
0x180052a4b  test    rcx, rcx
0x180052a4e  jz      short loc_180052A61
0x180052a50  xor     r9d, r9d; lParam
0x180052a53  xor     r8d, r8d; wParam
0x180052a56  mov     edx, 41Ch; Msg
0x180052a5b  call    cs:__imp_SendMessageW
0x180052a61  test    esi, esi
0x180052a63  jz      short loc_180052A74
0x180052a65  mov     eax, edi
0x180052a67  mov     ecx, esi
0x180052a69  not     ecx
0x180052a6b  and     eax, esi
0x180052a6d  and     ecx, [rbx+4Ch]
0x180052a70  mov     edi, ecx
0x180052a72  or      edi, eax
0x180052a74  mov     edx, [rbx+10h]
0x180052a77  mov     eax, edi
0x180052a79  and     eax, 0FFFFDDFFh
0x180052a7e  and     edx, 3
0x180052a81  cmovz   eax, edi
0x180052a84  mov     esi, eax
0x180052a86  btr     esi, 9
0x180052a8a  test    dword ptr [rbx+10h], 1000h
0x180052a91  cmovz   esi, eax
0x180052a94  mov     edi, esi
0x180052a96  mov     [rbx+4Ch], esi
0x180052a99  xor     edi, ebp
0x180052a9b  test    r14b, dil
0x180052a9e  jz      short loc_180052AB3
0x180052aa0  cmp     edx, r14d
0x180052aa3  jnz     short loc_180052AB3
0x180052aa5  mov     rcx, [rbx]; hWnd
0x180052aa8  mov     r8d, r14d; bErase
0x180052aab  xor     edx, edx; lpRect
0x180052aad  call    cs:__imp_InvalidateRect
0x180052ab3  test    edi, 18C2h
0x180052ab9  jz      short loc_180052AC9
0x180052abb  mov     rcx, [rbx]; hWnd
0x180052abe  mov     r8d, r14d; bErase
0x180052ac1  xor     edx, edx; lpRect
0x180052ac3  call    cs:__imp_InvalidateRect
0x180052ac9  test    dil, 4
0x180052acd  jz      short loc_180052AFA
0x180052acf  mov     rcx, rbx
0x180052ad2  test    sil, 4
0x180052ad6  jz      short loc_180052AE2
0x180052ad8  mov     edx, r14d
0x180052adb  call    ListView_InitCheckBoxes
0x180052ae0  jmp     short loc_180052AFA
0x180052ae2  xor     edx, edx
0x180052ae4  lea     r8d, [rdx+2]
0x180052ae8  call    ListView_OnSetImageList
0x180052aed  test    rax, rax
0x180052af0  jz      short loc_180052AFA
0x180052af2  mov     rcx, rax; himl
0x180052af5  call    ImageList_Destroy
0x180052afa  bt      edi, 8
0x180052afe  jnb     short loc_180052B15
0x180052b00  bt      esi, 8
0x180052b04  mov     rcx, [rbx]; HWND
0x180052b07  jnb     short loc_180052B10
0x180052b09  call    InitializeFlatSB
0x180052b0e  jmp     short loc_180052B15
0x180052b10  call    UninitializeFlatSB
0x180052b15  bt      edi, 9
0x180052b19  jnb     loc_180052BA4
0x180052b1f  cmp     cs:g_fSlowMachine, 0FFFFFFFFh
0x180052b26  jnz     short loc_180052B32
0x180052b28  mov     cs:g_fSlowMachine, 0
0x180052b32  bt      esi, 9
0x180052b36  jnb     short loc_180052B48
0x180052b38  mov     r8d, r14d
0x180052b3b  mov     edx, r14d
0x180052b3e  mov     rcx, rbx; int
0x180052b41  call    ListView_RecalcRegion
0x180052b46  jmp     short loc_180052B96
0x180052b48  xor     edi, edi
0x180052b4a  cmp     [rbx+200h], edi
0x180052b50  jle     short loc_180052B88
0x180052b52  mov     rax, [rbx+40h]
0x180052b56  movsxd  rdx, edi
0x180052b59  mov     rcx, [rax+8]
0x180052b5d  mov     rsi, [rcx+rdx*8]
0x180052b61  mov     rcx, [rsi+28h]; ho
0x180052b65  lea     rax, [rcx-1]
0x180052b69  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180052b6d  ja      short loc_180052B75
0x180052b6f  call    cs:__imp_DeleteObject
0x180052b75  add     edi, r14d
0x180052b78  mov     qword ptr [rsi+28h], 0
0x180052b80  cmp     edi, [rbx+200h]
0x180052b86  jl      short loc_180052B52
0x180052b88  mov     rcx, [rbx]; hWnd
0x180052b8b  mov     r8d, r14d; bRedraw
0x180052b8e  xor     edx, edx; hRgn
0x180052b90  call    cs:__imp_SetWindowRgn
0x180052b96  mov     rcx, [rbx]; hWnd
0x180052b99  mov     r8d, r14d; bErase
0x180052b9c  xor     edx, edx; lpRect
0x180052b9e  call    cs:__imp_InvalidateRect
0x180052ba4  mov     eax, ebp
0x180052ba6  add     rsp, 20h
0x180052baa  pop     r14
0x180052bac  pop     rdi
0x180052bad  pop     rsi
0x180052bae  pop     rbp
0x180052baf  pop     rbx
0x180052bb0  retn
```
