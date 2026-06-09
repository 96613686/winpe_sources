# Smb2ConfirmAbeVisibilityAndFetchNetworkOpenInfoFromCache

- ea: `0x140003840`
- end: `0x140003a6f`
- name: `Smb2ConfirmAbeVisibilityAndFetchNetworkOpenInfoFromCache`
- size: `559`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140024760`

## callees

- `0x140003840`
- `0x1400040a0`
- `0x140004640`
- `0x140055890`
- `0x140055a40`
- `0x140056350`

## import_xrefs

- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400039fb`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400039fb`

## pseudocode

```c
__int64 __fastcall Smb2ConfirmAbeVisibilityAndFetchNetworkOpenInfoFromCache(_QWORD *a1, __int64 a2, char a3, void *a4)
{
  __int64 v4; // r10
  unsigned int v9; // ebx
  __int64 v10; // rdi
  __int64 v11; // r14
  int v12; // r9d
  _BYTE *v13; // rax
  __int64 v14; // r8
  unsigned int v16; // [rsp+90h] [rbp+8h] BYREF

  v4 = a1[7];
  v16 = 0;
  v9 = 0;
  v10 = *(_QWORD *)(v4 + 136);
  v11 = *(_QWORD *)(*(_QWORD *)(v4 + 120) + 40LL);
  do
  {
    if ( !v9 )
    {
      if ( (*(_DWORD *)(v10 + 8) & 2) != 0 )
        goto LABEL_13;
      if ( (int)Smb2FetchFileIdentityFromCacheEx(
                  (__int64)a1,
                  (struct _NAME_CACHE_CONTROL_ *)(v11 + 192),
                  0,
                  (*(_DWORD *)(a2 + 28) & 0x200000) != 0,
                  (struct _LIST_ENTRY *)(v10 + 24)) >= 0 )
      {
        *(_DWORD *)(v10 + 8) |= 2u;
LABEL_13:
        if ( !a3 || *(_BYTE *)(MRxSmbGetConfigurationBlock(a1) + 430) )
        {
LABEL_14:
          v16 = 56;
          v9 = (((int)Smb2FetchFileInfoFromCache(
                        (__int64)a1,
                        (struct _NAME_CACHE_CONTROL_ *)(v11 + 376),
                        1,
                        34,
                        0,
                        a4,
                        &v16) >> 31)
              & 0xFFFFFFFC)
             + 8;
          continue;
        }
        v9 = (((int)Smb2FetchFileAbeStatusFromCache((__int64)a1, (struct _NAME_CACHE_CONTROL_ *)(v11 + 1296)) >> 31)
            & 0xFFFFFFFD)
           + 6;
        continue;
      }
      v9 = 5;
LABEL_7:
      v12 = -262143;
      v16 = 32;
      v13 = (_BYTE *)(v10 + 24);
LABEL_8:
      v14 = *(_DWORD *)(a2 + 28) >> 21;
      LOBYTE(v14) = (*(_DWORD *)(a2 + 28) & 0x200000) != 0;
      if ( (int)Smb2QueryFileInformationFromDirCache((__int64)a1, a2, v14, v12, v13, &v16) < 0 )
        return 3221225494LL;
      if ( v9 != 3 )
      {
        if ( v9 == 4 )
        {
          v9 = 8;
LABEL_22:
          if ( a3 )
          {
            if ( ((v9 - 3) & 0xFFFFFFFD) == 0 )
              Smb2InsertFileAbeStatusCacheEntry(
                a1,
                (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(*(_QWORD *)(a1[7] + 120LL) + 40LL) + 1296LL));
          }
          continue;
        }
        *(_DWORD *)(v10 + 8) |= 2u;
      }
      v9 = 6;
      goto LABEL_22;
    }
    if ( v9 == 6 )
      goto LABEL_14;
    if ( v9 == 3 || v9 - 4 <= 1 )
    {
      if ( v9 == 3 )
        goto LABEL_7;
      v12 = 34;
      v16 = 56;
      v13 = a4;
      goto LABEL_8;
    }
  }
  while ( v9 != 8 );
  return 0;
}

```

## disassembly

```asm
0x140003840  push    rbx
0x140003842  push    rbp
0x140003843  push    rsi
0x140003844  push    rdi
0x140003845  push    r12
0x140003847  push    r13
0x140003849  push    r14
0x14000384b  push    r15
0x14000384d  sub     rsp, 48h
0x140003851  mov     r10, [rcx+38h]
0x140003855  xor     r13d, r13d
0x140003858  mov     r12, r9
0x14000385b  mov     [rsp+88h+arg_0], r13d
0x140003863  movzx   ebp, r8b
0x140003867  mov     r15, rdx
0x14000386a  mov     rsi, rcx
0x14000386d  mov     ebx, r13d
0x140003870  mov     rax, [r10+78h]
0x140003874  mov     rdi, [r10+88h]
0x14000387b  mov     r14, [rax+28h]
0x14000387f  cmp     ebx, 7
0x140003882  jz      short loc_1400038FB
0x140003884  test    ebx, ebx
0x140003886  jz      short loc_140003905
0x140003888  cmp     ebx, 6
0x14000388b  jz      loc_140003944
0x140003891  mov     eax, ebx
0x140003893  sub     eax, 2
0x140003896  jz      loc_140003A14
0x14000389c  sub     eax, 1
0x14000389f  jz      short loc_1400038AF
0x1400038a1  sub     eax, 1
0x1400038a4  jz      short loc_1400038AF
0x1400038a6  cmp     eax, 1
0x1400038a9  jnz     loc_14000398C
0x1400038af  cmp     ebx, 3
0x1400038b2  jnz     loc_140003A33
0x1400038b8  mov     r9d, 0FFFC0001h
0x1400038be  mov     [rsp+88h+arg_0], 20h ; ' '
0x1400038c9  lea     rax, [rdi+18h]
0x1400038cd  mov     r8d, [r15+1Ch]
0x1400038d1  lea     rcx, [rsp+88h+arg_0]
0x1400038d9  mov     [rsp+88h+var_60], rcx
0x1400038de  mov     rcx, rsi
0x1400038e1  shr     r8d, 15h
0x1400038e5  and     r8b, 1
0x1400038e9  mov     [rsp+88h+var_68], rax
0x1400038ee  call    Smb2QueryFileInformationFromDirCache
0x1400038f3  test    eax, eax
0x1400038f5  jns     loc_1400039B3
0x1400038fb  mov     eax, 0C0000016h
0x140003900  jmp     loc_140003997
0x140003905  mov     eax, [rdi+8]
0x140003908  test    al, 2
0x14000390a  jnz     short loc_14000393B
0x14000390c  mov     r9d, [r15+1Ch]
0x140003910  lea     rax, [rdi+18h]
0x140003914  shr     r9d, 15h
0x140003918  lea     rdx, [r14+0C0h]
0x14000391f  and     r9b, 1
0x140003923  mov     [rsp+88h+var_68], rax
0x140003928  xor     r8d, r8d
0x14000392b  mov     rcx, rsi
0x14000392e  call    Smb2FetchFileIdentityFromCacheEx
0x140003933  test    eax, eax
0x140003935  js      short loc_1400039A9
0x140003937  or      dword ptr [rdi+8], 2
0x14000393b  test    bpl, bpl
0x14000393e  jnz     loc_1400039FB
0x140003944  lea     rax, [rsp+88h+arg_0]
0x14000394c  mov     [rsp+88h+arg_0], 38h ; '8'
0x140003957  mov     [rsp+88h+var_58], rax
0x14000395c  lea     rdx, [r14+178h]
0x140003963  mov     [rsp+88h+var_60], r12
0x140003968  mov     r9d, 22h ; '"'
0x14000396e  mov     r8d, 1
0x140003974  mov     dword ptr [rsp+88h+var_68], r13d
0x140003979  mov     rcx, rsi
0x14000397c  call    Smb2FetchFileInfoFromCache
0x140003981  mov     ebx, eax
0x140003983  sar     ebx, 1Fh
0x140003986  and     ebx, 0FFFFFFFCh
0x140003989  add     ebx, 8
0x14000398c  cmp     ebx, 8
0x14000398f  jnz     loc_14000387F
0x140003995  xor     eax, eax
0x140003997  add     rsp, 48h
0x14000399b  pop     r15
0x14000399d  pop     r14
0x14000399f  pop     r13
0x1400039a1  pop     r12
0x1400039a3  pop     rdi
0x1400039a4  pop     rsi
0x1400039a5  pop     rbp
0x1400039a6  pop     rbx
0x1400039a7  retn
0x1400039a9  mov     ebx, 5
0x1400039ae  jmp     loc_1400038B8
0x1400039b3  cmp     ebx, 3
0x1400039b6  jz      short loc_1400039CA
0x1400039b8  cmp     ebx, 4
0x1400039bb  jz      loc_140003A5A
0x1400039c1  cmp     ebx, 5
0x1400039c4  jnz     short loc_1400039CF
0x1400039c6  or      dword ptr [rdi+8], 2
0x1400039ca  mov     ebx, 6
0x1400039cf  test    bpl, bpl
0x1400039d2  jz      short loc_14000398C
0x1400039d4  lea     eax, [rbx-3]
0x1400039d7  test    eax, 0FFFFFFFDh
0x1400039dc  jnz     short loc_14000398C
0x1400039de  mov     rax, [rsi+38h]
0x1400039e2  mov     rcx, [rax+78h]
0x1400039e6  mov     rdx, [rcx+28h]
0x1400039ea  mov     rcx, rsi
0x1400039ed  add     rdx, 510h
0x1400039f4  call    Smb2InsertFileAbeStatusCacheEntry
0x1400039f9  jmp     short loc_14000398C
0x1400039fb  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140003a02  nop     dword ptr [rax+rax+00h]
0x140003a07  cmp     [rax+1AEh], r13b
0x140003a0e  jnz     loc_140003944
0x140003a14  lea     rdx, [r14+510h]
0x140003a1b  mov     rcx, rsi
0x140003a1e  call    Smb2FetchFileAbeStatusFromCache
0x140003a23  mov     ebx, eax
0x140003a25  sar     ebx, 1Fh
0x140003a28  and     ebx, 0FFFFFFFDh
0x140003a2b  add     ebx, 6
0x140003a2e  jmp     loc_14000398C
0x140003a33  cmp     ebx, 5
0x140003a36  jz      loc_1400038B8
0x140003a3c  cmp     ebx, 4
0x140003a3f  jnz     short loc_140003A64
0x140003a41  mov     r9d, 22h ; '"'
0x140003a47  mov     [rsp+88h+arg_0], 38h ; '8'
0x140003a52  mov     rax, r12
0x140003a55  jmp     loc_1400038CD
0x140003a5a  mov     ebx, 8
0x140003a5f  jmp     loc_1400039CF
0x140003a64  mov     r9d, r13d
0x140003a67  mov     rax, r13
0x140003a6a  jmp     loc_1400038CD
```
