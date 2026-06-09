# Cic_HICON_UserSize(HICON__ * *)

- ea: `0x18005d5cc`
- end: `0x18005d76a`
- name: `?Cic_HICON_UserSize@@YAKPEAPEAUHICON__@@@Z`
- size: `414`
- prototype: `unsigned int __fastcall(HICON *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180089de0`

## callees

- `0x18005d5cc`

## import_xrefs

- `USER32!GetIconInfo` at `0x18005d604`
- `USER32!GetIconInfo` at `0x18005d604`
- `USER32!DestroyIcon` at `0x18005d6f1`
- `USER32!DestroyIcon` at `0x18005d6f1`
- `GDI32!DeleteObject` at `0x18005d69e`
- `GDI32!DeleteObject` at `0x18005d6ad`
- `GDI32!DeleteObject` at `0x18005d69e`
- `GDI32!DeleteObject` at `0x18005d6ad`
- `GDI32!GetObjectW` at `0x18005d6cf`
- `GDI32!GetObjectW` at `0x18005d709`
- `GDI32!GetObjectW` at `0x18005d6cf`
- `GDI32!GetObjectW` at `0x18005d709`

## pseudocode

```c
__int64 __fastcall Cic_HICON_UserSize(HICON *a1)
{
  HICON v2; // rcx
  HBITMAP hbmMask; // rsi
  unsigned int v4; // ebx
  int v5; // r8d
  int v6; // eax
  unsigned __int64 v7; // rcx
  __int64 v8; // r9
  unsigned int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // r8d
  unsigned int v12; // ebx
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // rcx
  ICONINFO piconinfo; // [rsp+20h] [rbp-60h] BYREF
  __int128 v19; // [rsp+40h] [rbp-40h] BYREF
  __int128 v20; // [rsp+50h] [rbp-30h]
  __int128 pv; // [rsp+60h] [rbp-20h] BYREF
  __int128 v22; // [rsp+70h] [rbp-10h]

  if ( !a1 )
    return 0;
  v2 = *a1;
  if ( !v2 )
    return 8;
  memset(&piconinfo, 0, sizeof(piconinfo));
  if ( !GetIconInfo(v2, &piconinfo) )
    goto LABEL_23;
  hbmMask = piconinfo.hbmMask;
  v4 = 104;
  v19 = 0;
  v20 = 0;
  pv = 0;
  v22 = 0;
  if ( piconinfo.hbmColor )
  {
    if ( !GetObjectW(piconinfo.hbmColor, 32, &v19) )
      goto LABEL_23;
    v15 = DWORD2(v19) * (unsigned __int64)(unsigned __int16)v20;
    if ( v15 > 0xFFFFFFFF )
      goto LABEL_23;
    v16 = HIDWORD(v19) * (unsigned __int64)(unsigned int)v15;
    if ( v16 > 0xFFFFFFFF )
      goto LABEL_23;
    v4 = v16 + 104;
    if ( (int)v16 + 104 < (unsigned int)v16 )
      goto LABEL_23;
  }
  if ( hbmMask )
  {
    if ( !GetObjectW(hbmMask, 32, &pv) )
      goto LABEL_23;
    v14 = DWORD2(pv) * (unsigned __int64)(unsigned __int16)v22;
    if ( v14 > 0xFFFFFFFF )
      goto LABEL_23;
    v17 = HIDWORD(pv) * (unsigned __int64)(unsigned int)v14;
    if ( v17 > 0xFFFFFFFF )
      goto LABEL_23;
    v4 += v17;
    if ( v4 < (unsigned int)v17 )
      goto LABEL_23;
  }
  v5 = -1;
  v6 = -1;
  v7 = v4 + 7LL;
  if ( v7 >= v4 )
    v6 = v4 + 7;
  v8 = 0;
  v9 = v6 & 0xFFFFFFF8;
  if ( v7 >= v4 )
    v8 = v9;
  if ( (_DWORD)v8 )
  {
    if ( v8 + 7 >= (unsigned __int64)(unsigned int)v8 )
      v5 = v8 + 7;
    v10 = 0;
    v11 = v5 & 0xFFFFFFF8;
    if ( v8 + 7 >= (unsigned __int64)(unsigned int)v8 )
      v10 = v11;
    v12 = v10 + 136;
  }
  else
  {
LABEL_23:
    v12 = 8;
    DestroyIcon(*a1);
    *a1 = 0;
  }
  if ( piconinfo.hbmColor )
    DeleteObject(piconinfo.hbmColor);
  if ( piconinfo.hbmMask )
    DeleteObject(piconinfo.hbmMask);
  return v12;
}

```

## disassembly

```asm
0x18005d5cc  push    rbp
0x18005d5ce  push    rbx
0x18005d5cf  push    rsi
0x18005d5d0  push    rdi
0x18005d5d1  push    r14
0x18005d5d3  mov     rbp, rsp
0x18005d5d6  sub     rsp, 80h
0x18005d5dd  mov     rdi, rcx
0x18005d5e0  test    rcx, rcx
0x18005d5e3  jz      loc_18005D759
0x18005d5e9  mov     rcx, [rcx]; hIcon
0x18005d5ec  test    rcx, rcx
0x18005d5ef  jz      loc_18005D760
0x18005d5f5  xorps   xmm0, xmm0
0x18005d5f8  lea     rdx, [rbp+piconinfo]; piconinfo
0x18005d5fc  movups  xmmword ptr [rbp+piconinfo.fIcon], xmm0
0x18005d600  movups  xmmword ptr [rbp+piconinfo.hbmMask], xmm0
0x18005d604  call    cs:__imp_GetIconInfo
0x18005d60a  test    eax, eax
0x18005d60c  jz      loc_18005D6E9
0x18005d612  mov     rcx, [rbp+piconinfo.hbmColor]; h
0x18005d616  xorps   xmm0, xmm0
0x18005d619  mov     rsi, [rbp+piconinfo.hbmMask]
0x18005d61d  xorps   xmm1, xmm1
0x18005d620  mov     ebx, 68h ; 'h'
0x18005d625  mov     r14d, 0FFFFFFFFh
0x18005d62b  movups  [rbp+var_40], xmm0
0x18005d62f  movups  [rbp+var_30], xmm0
0x18005d633  movups  [rbp+pv], xmm1
0x18005d637  movups  [rbp+var_10], xmm1
0x18005d63b  test    rcx, rcx
0x18005d63e  jnz     loc_18005D700
0x18005d644  test    rsi, rsi
0x18005d647  jnz     short loc_18005D6C3
0x18005d649  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005d64d  mov     edx, ebx
0x18005d64f  mov     rax, r8
0x18005d652  mov     r10d, 0FFFFFFF8h
0x18005d658  lea     rcx, [rdx+7]
0x18005d65c  cmp     rcx, rdx
0x18005d65f  cmovnb  rax, rcx
0x18005d663  xor     r9d, r9d
0x18005d666  and     eax, r10d
0x18005d669  cmp     rcx, rdx
0x18005d66c  cmovnb  r9d, eax
0x18005d670  test    r9d, r9d
0x18005d673  jz      short loc_18005D6E9
0x18005d675  lea     rax, [r9+7]
0x18005d679  mov     ecx, r9d
0x18005d67c  cmp     rax, rcx
0x18005d67f  cmovnb  r8, rax
0x18005d683  xor     ebx, ebx
0x18005d685  and     r8d, r10d
0x18005d688  cmp     rax, rcx
0x18005d68b  cmovnb  ebx, r8d
0x18005d68f  add     ebx, 88h
0x18005d695  mov     rcx, [rbp+piconinfo.hbmColor]; ho
0x18005d699  test    rcx, rcx
0x18005d69c  jz      short loc_18005D6A4
0x18005d69e  call    cs:__imp_DeleteObject
0x18005d6a4  mov     rcx, [rbp+piconinfo.hbmMask]; ho
0x18005d6a8  test    rcx, rcx
0x18005d6ab  jz      short loc_18005D6B3
0x18005d6ad  call    cs:__imp_DeleteObject
0x18005d6b3  mov     eax, ebx
0x18005d6b5  add     rsp, 80h
0x18005d6bc  pop     r14
0x18005d6be  pop     rdi
0x18005d6bf  pop     rsi
0x18005d6c0  pop     rbx
0x18005d6c1  pop     rbp
0x18005d6c2  retn
0x18005d6c3  lea     r8, [rbp+pv]; pv
0x18005d6c7  mov     edx, 20h ; ' '; c
0x18005d6cc  mov     rcx, rsi; h
0x18005d6cf  call    cs:__imp_GetObjectW
0x18005d6d5  test    eax, eax
0x18005d6d7  jz      short loc_18005D6E9
0x18005d6d9  movzx   ecx, word ptr [rbp+var_10]
0x18005d6dd  mov     eax, dword ptr [rbp+pv+8]
0x18005d6e0  imul    rcx, rax
0x18005d6e4  cmp     rcx, r14
0x18005d6e7  jbe     short loc_18005D740
0x18005d6e9  mov     rcx, [rdi]; hIcon
0x18005d6ec  mov     ebx, 8
0x18005d6f1  call    cs:__imp_DestroyIcon
0x18005d6f7  mov     qword ptr [rdi], 0
0x18005d6fe  jmp     short loc_18005D695
0x18005d700  lea     r8, [rbp+var_40]; pv
0x18005d704  mov     edx, 20h ; ' '; c
0x18005d709  call    cs:__imp_GetObjectW
0x18005d70f  test    eax, eax
0x18005d711  jz      short loc_18005D6E9
0x18005d713  movzx   ecx, word ptr [rbp+var_30]
0x18005d717  mov     eax, dword ptr [rbp+var_40+8]
0x18005d71a  imul    rcx, rax
0x18005d71e  cmp     rcx, r14
0x18005d721  ja      short loc_18005D6E9
0x18005d723  mov     eax, dword ptr [rbp+var_40+0Ch]
0x18005d726  mov     r8d, ecx
0x18005d729  imul    r8, rax
0x18005d72d  cmp     r8, r14
0x18005d730  ja      short loc_18005D6E9
0x18005d732  lea     ebx, [r8+68h]
0x18005d736  cmp     ebx, r8d
0x18005d739  jb      short loc_18005D6E9
0x18005d73b  jmp     loc_18005D644
0x18005d740  mov     eax, dword ptr [rbp+pv+0Ch]
0x18005d743  mov     ecx, ecx
0x18005d745  imul    rcx, rax
0x18005d749  cmp     rcx, r14
0x18005d74c  ja      short loc_18005D6E9
0x18005d74e  add     ebx, ecx
0x18005d750  cmp     ebx, ecx
0x18005d752  jb      short loc_18005D6E9
0x18005d754  jmp     loc_18005D649
0x18005d759  xor     eax, eax
0x18005d75b  jmp     loc_18005D6B5
0x18005d760  mov     eax, 8
0x18005d765  jmp     loc_18005D6B5
```
