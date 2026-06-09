# DevicesPage::AddDevicesToCombo(Array<Device> const &)

- ea: `0x18000c65c`
- end: `0x18000c765`
- name: `?AddDevicesToCombo@DevicesPage@@AEAAJAEBV?$Array@UDevice@@@@@Z`
- size: `265`
- prototype: `__int64 __fastcall(__int64, struct _DSA **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e244`

## callees

- `0x180001334`
- `0x18000134c`
- `0x18000c5d0`
- `0x18000c65c`
- `0x180018040`

## import_xrefs

- `USER32!SendMessageW` at `0x18000c6f7`
- `USER32!SendMessageW` at `0x18000c713`
- `USER32!SendMessageW` at `0x18000c733`
- `USER32!SendMessageW` at `0x18000c6f7`
- `USER32!SendMessageW` at `0x18000c713`
- `USER32!SendMessageW` at `0x18000c733`

## pseudocode

```c
__int64 __fastcall DevicesPage::AddDevicesToCombo(__int64 a1, struct _DSA **a2)
{
  int i; // esi
  int v5; // ecx
  void *v6; // rbx
  unsigned int v7; // edi
  _DWORD *v8; // rax
  struct _DSA *v9; // rcx
  HWND *v10; // rdi
  int v11; // eax
  WPARAM v12; // rbp

  Combo<Device>::Clear(*(_QWORD *)(a1 + 88));
  for ( i = 0; ; ++i )
  {
    v5 = *a2 ? *(_DWORD *)*a2 : 0;
    v6 = 0;
    v7 = 0;
    if ( i >= v5 )
      break;
    v8 = operator new(0x630u);
    v6 = v8;
    if ( !v8 )
    {
      v7 = -2147024882;
      v6 = 0;
      break;
    }
    *v8 = 0;
    *((_WORD *)v8 + 2) = 0;
    *((_WORD *)v8 + 262) = 0;
    *((_WORD *)v8 + 522) = 0;
    *((_WORD *)v8 + 782) = 0;
    v9 = *a2;
    if ( !*a2 )
      goto LABEL_14;
    if ( i >= *(_DWORD *)v9 )
    {
      v7 = -2147024809;
      break;
    }
    if ( !DSA_GetItem(v9, i, v8) )
      goto LABEL_14;
    v10 = *(HWND **)(a1 + 88);
    v11 = SendMessageW(*v10, 0x143u, 0, (LPARAM)v6 + 524);
    if ( v11 == -1 )
      goto LABEL_14;
    v12 = v11;
    if ( (unsigned int)SendMessageW(*v10, 0x151u, v11, (LPARAM)v6) == -1 )
    {
      SendMessageW(*v10, 0x144u, v12, 0);
LABEL_14:
      v7 = -2147467259;
      break;
    }
  }
  operator delete(v6);
  return v7;
}

```

## disassembly

```asm
0x18000c65c  push    rbx
0x18000c65e  push    rbp
0x18000c65f  push    rsi
0x18000c660  push    rdi
0x18000c661  push    r14
0x18000c663  push    r15
0x18000c665  sub     rsp, 28h
0x18000c669  mov     r15, rcx
0x18000c66c  mov     r14, rdx
0x18000c66f  mov     rcx, [rcx+58h]
0x18000c673  call    ?Clear@?$Combo@UDevice@@@@QEAAXXZ; Combo<Device>::Clear(void)
0x18000c678  xor     esi, esi
0x18000c67a  mov     rax, [r14]
0x18000c67d  test    rax, rax
0x18000c680  jz      short loc_18000C686
0x18000c682  mov     ecx, [rax]
0x18000c684  jmp     short loc_18000C688
0x18000c686  xor     ecx, ecx
0x18000c688  xor     ebx, ebx
0x18000c68a  xor     edi, edi
0x18000c68c  cmp     esi, ecx
0x18000c68e  jge     loc_18000C74E
0x18000c694  mov     ecx, 630h; Size
0x18000c699  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c69e  mov     rbx, rax
0x18000c6a1  test    rax, rax
0x18000c6a4  jz      loc_18000C747
0x18000c6aa  mov     [rax], edi
0x18000c6ac  xor     eax, eax
0x18000c6ae  mov     [rbx+4], ax
0x18000c6b2  mov     [rbx+20Ch], ax
0x18000c6b9  mov     [rbx+414h], ax
0x18000c6c0  mov     [rbx+61Ch], ax
0x18000c6c7  mov     rcx, [r14]; hdsa
0x18000c6ca  test    rcx, rcx
0x18000c6cd  jz      short loc_18000C739
0x18000c6cf  cmp     esi, [rcx]
0x18000c6d1  jge     short loc_18000C740
0x18000c6d3  mov     r8, rbx; pitem
0x18000c6d6  mov     edx, esi; i
0x18000c6d8  call    DSA_GetItem
0x18000c6dd  test    eax, eax
0x18000c6df  jz      short loc_18000C739
0x18000c6e1  mov     rdi, [r15+58h]
0x18000c6e5  lea     r9, [rbx+20Ch]; lParam
0x18000c6ec  xor     r8d, r8d; wParam
0x18000c6ef  mov     edx, 143h; Msg
0x18000c6f4  mov     rcx, [rdi]; hWnd
0x18000c6f7  call    cs:__imp_SendMessageW
0x18000c6fd  cmp     eax, 0FFFFFFFFh
0x18000c700  jz      short loc_18000C739
0x18000c702  mov     rcx, [rdi]; hWnd
0x18000c705  mov     r9, rbx; lParam
0x18000c708  movsxd  rbp, eax
0x18000c70b  mov     edx, 151h; Msg
0x18000c710  mov     r8, rbp; wParam
0x18000c713  call    cs:__imp_SendMessageW
0x18000c719  cmp     eax, 0FFFFFFFFh
0x18000c71c  jz      short loc_18000C725
0x18000c71e  inc     esi
0x18000c720  jmp     loc_18000C67A
0x18000c725  mov     rcx, [rdi]; hWnd
0x18000c728  xor     r9d, r9d; lParam
0x18000c72b  mov     r8, rbp; wParam
0x18000c72e  mov     edx, 144h; Msg
0x18000c733  call    cs:__imp_SendMessageW
0x18000c739  mov     edi, 80004005h
0x18000c73e  jmp     short loc_18000C74E
0x18000c740  mov     edi, 80070057h
0x18000c745  jmp     short loc_18000C74E
0x18000c747  mov     edi, 8007000Eh
0x18000c74c  xor     ebx, ebx
0x18000c74e  mov     rcx, rbx; Block
0x18000c751  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c756  mov     eax, edi
0x18000c758  add     rsp, 28h
0x18000c75c  pop     r15
0x18000c75e  pop     r14
0x18000c760  pop     rdi
0x18000c761  pop     rsi
0x18000c762  pop     rbp
0x18000c763  pop     rbx
0x18000c764  retn
```
