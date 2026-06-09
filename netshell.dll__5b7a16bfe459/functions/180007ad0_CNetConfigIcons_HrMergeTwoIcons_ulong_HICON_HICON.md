# CNetConfigIcons::HrMergeTwoIcons(ulong,HICON__ * *,HICON__ *)

- ea: `0x180007ad0`
- end: `0x180007c22`
- name: `?HrMergeTwoIcons@CNetConfigIcons@@AEAAJKPEAPEAUHICON__@@PEAU2@@Z`
- size: `338`
- prototype: `int(CNetConfigIcons *__hidden this, unsigned int, HICON *, HICON)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180043cc0`

## callees

- `0x180007ad0`
- `0x18000a6d8`
- `0x180019a24`
- `0x1800608f8`
- `0x180060a00`
- `0x180060a68`
- `0x180060ad4`

## import_xrefs

- `USER32!DestroyIcon` at `0x180007bdd`
- `USER32!DestroyIcon` at `0x180007bdd`
- `USER32!CopyIcon` at `0x180007bfd`
- `USER32!CopyIcon` at `0x180007bfd`

## pseudocode

```c
__int64 __fastcall CNetConfigIcons::HrMergeTwoIcons(CNetConfigIcons *this, unsigned int a2, HICON *a3, HICON a4)
{
  __int64 *v4; // r10
  char *v5; // rsi
  __int64 *v9; // rax
  __int64 *v10; // r11
  char v11; // dl
  __int64 *v12; // rcx
  struct _IMAGELIST *v13; // rbx
  int v14; // esi
  int v15; // eax
  _BYTE v17[12]; // [rsp+30h] [rbp-48h] BYREF
  int v18; // [rsp+3Ch] [rbp-3Ch]
  unsigned int v19; // [rsp+88h] [rbp+10h] BYREF

  v19 = a2;
  v4 = (__int64 *)*((_QWORD *)this + 7);
  v5 = (char *)this + 56;
  v18 = 0;
  v9 = v4;
  v10 = (__int64 *)v4[1];
  if ( !*((_BYTE *)v10 + 25) )
  {
    do
    {
      if ( *((_DWORD *)v10 + 8) >= a2 )
      {
        v11 = 0;
        v9 = v10;
      }
      else
      {
        v11 = 1;
      }
      v12 = v10 + 2;
      if ( !v11 )
        v12 = v10;
      v10 = (__int64 *)*v12;
    }
    while ( !*(_BYTE *)(*v12 + 25) );
  }
  if ( !*((_BYTE *)v9 + 25) && a2 >= *((_DWORD *)v9 + 8) && v9 != v4 )
  {
    v13 = (struct _IMAGELIST *)v9[5];
    goto LABEL_14;
  }
  v13 = ImageList_Create(a2, a2, 0x21u, 2, 0);
  if ( v13 )
  {
    *(_QWORD *)(*(_QWORD *)std::map<unsigned long,_IMAGELIST *>::_Try_emplace<unsigned long const &,>(v5, v17, &v19)
              + 40LL) = v13;
LABEL_14:
    if ( *a3 )
    {
      if ( a4 )
      {
        if ( ImageList_Remove(v13, -1) )
        {
          v14 = ImageList_ReplaceIcon(v13, -1, *a3);
          if ( v14 != -1 )
          {
            v15 = ImageList_ReplaceIcon(v13, -1, a4);
            if ( v15 != -1 )
            {
              if ( ImageList_SetOverlayImage(v13, v15, 1) )
              {
                DestroyIcon(*a3);
                *a3 = ImageList_GetIcon(v13, v14, 0x100u);
                return 0;
              }
            }
          }
        }
        return 2147500037LL;
      }
    }
    else
    {
      *a3 = CopyIcon(a4);
    }
    return 1;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180007ad0  mov     [rsp+arg_8], edx
0x180007ad4  push    rbx
0x180007ad5  push    rbp
0x180007ad6  push    rsi
0x180007ad7  push    rdi
0x180007ad8  sub     rsp, 58h
0x180007adc  mov     r10, [rcx+38h]
0x180007ae0  lea     rsi, [rcx+38h]
0x180007ae4  xor     eax, eax
0x180007ae6  mov     rbp, r9
0x180007ae9  mov     [rsp+78h+var_3C], eax
0x180007aed  mov     rdi, r8
0x180007af0  mov     ebx, edx
0x180007af2  mov     rax, r10
0x180007af5  mov     r11, [r10+8]
0x180007af9  cmp     byte ptr [r11+19h], 0
0x180007afe  jnz     short loc_180007B23
0x180007b00  cmp     [r11+20h], ebx
0x180007b04  jnb     short loc_180007B0A
0x180007b06  mov     dl, 1
0x180007b08  jmp     short loc_180007B0F
0x180007b0a  xor     dl, dl
0x180007b0c  mov     rax, r11
0x180007b0f  test    dl, dl
0x180007b11  lea     rcx, [r11+10h]
0x180007b15  cmovz   rcx, r11
0x180007b19  mov     r11, [rcx]
0x180007b1c  cmp     byte ptr [r11+19h], 0
0x180007b21  jz      short loc_180007B00
0x180007b23  cmp     byte ptr [rax+19h], 0
0x180007b27  jnz     short loc_180007B39
0x180007b29  cmp     ebx, [rax+20h]
0x180007b2c  jb      short loc_180007B39
0x180007b2e  cmp     rax, r10
0x180007b31  jz      short loc_180007B39
0x180007b33  mov     rbx, [rax+28h]
0x180007b37  jmp     short loc_180007B7E
0x180007b39  mov     r9d, 2; cInitial
0x180007b3f  mov     [rsp+78h+cGrow], 0; cGrow
0x180007b47  mov     r8d, 21h ; '!'; flags
0x180007b4d  mov     edx, ebx; cy
0x180007b4f  mov     ecx, ebx; cx
0x180007b51  call    ImageList_Create
0x180007b56  mov     rbx, rax
0x180007b59  test    rax, rax
0x180007b5c  jz      loc_180007C14
0x180007b62  lea     r8, [rsp+78h+arg_8]
0x180007b6a  mov     rcx, rsi
0x180007b6d  lea     rdx, [rsp+78h+var_48]
0x180007b72  call    ??$_Try_emplace@AEBK$$V@?$map@KPEAU_IMAGELIST@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAU_IMAGELIST@@@std@@@3@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKPEAU_IMAGELIST@@@std@@PEAX@std@@_N@1@AEBK@Z; std::map<ulong,_IMAGELIST *>::_Try_emplace<ulong const &,>(ulong const &)
0x180007b77  mov     rcx, [rax]
0x180007b7a  mov     [rcx+28h], rbx
0x180007b7e  cmp     qword ptr [rdi], 0
0x180007b82  jz      short loc_180007BFA
0x180007b84  test    rbp, rbp
0x180007b87  jz      short loc_180007C06
0x180007b89  mov     edx, 0FFFFFFFFh; i
0x180007b8e  mov     rcx, rbx; himl
0x180007b91  call    ImageList_Remove
0x180007b96  test    eax, eax
0x180007b98  jz      short loc_180007C14
0x180007b9a  mov     r8, [rdi]; hicon
0x180007b9d  mov     edx, 0FFFFFFFFh; i
0x180007ba2  mov     rcx, rbx; himl
0x180007ba5  call    ImageList_ReplaceIcon
0x180007baa  mov     esi, eax
0x180007bac  cmp     eax, 0FFFFFFFFh
0x180007baf  jz      short loc_180007C14
0x180007bb1  mov     r8, rbp; hicon
0x180007bb4  mov     edx, 0FFFFFFFFh; i
0x180007bb9  mov     rcx, rbx; himl
0x180007bbc  call    ImageList_ReplaceIcon
0x180007bc1  cmp     eax, 0FFFFFFFFh
0x180007bc4  jz      short loc_180007C14
0x180007bc6  mov     r8d, 1; iOverlay
0x180007bcc  mov     edx, eax; iImage
0x180007bce  mov     rcx, rbx; himl
0x180007bd1  call    ImageList_SetOverlayImage
0x180007bd6  test    eax, eax
0x180007bd8  jz      short loc_180007C14
0x180007bda  mov     rcx, [rdi]; hIcon
0x180007bdd  call    cs:__imp_DestroyIcon
0x180007be3  mov     r8d, 100h; flags
0x180007be9  mov     edx, esi; i
0x180007beb  mov     rcx, rbx; himl
0x180007bee  call    ImageList_GetIcon
0x180007bf3  mov     [rdi], rax
0x180007bf6  xor     eax, eax
0x180007bf8  jmp     short loc_180007C19
0x180007bfa  mov     rcx, rbp; hIcon
0x180007bfd  call    cs:__imp_CopyIcon
0x180007c03  mov     [rdi], rax
0x180007c06  mov     eax, 1
0x180007c0b  add     rsp, 58h
0x180007c0f  pop     rdi
0x180007c10  pop     rsi
0x180007c11  pop     rbp
0x180007c12  pop     rbx
0x180007c13  retn
0x180007c14  mov     eax, 80004005h
0x180007c19  add     rsp, 58h
0x180007c1d  pop     rdi
0x180007c1e  pop     rsi
0x180007c1f  pop     rbp
0x180007c20  pop     rbx
0x180007c21  retn
```
