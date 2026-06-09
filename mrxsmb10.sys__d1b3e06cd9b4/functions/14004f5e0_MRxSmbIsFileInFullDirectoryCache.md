# MRxSmbIsFileInFullDirectoryCache

- ea: `0x14004f5e0`
- end: `0x14004f819`
- name: `MRxSmbIsFileInFullDirectoryCache`
- size: `569`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140036d40`
- `0x140048b30`

## callees

- `0x14000e46c`
- `0x140043d74`
- `0x14004f5e0`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14004f714`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004f714`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004f6df`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004f6df`
- `rdbss!RxNameCacheExpireEntry` at `0x14004f808`
- `rdbss!RxNameCacheExpireEntry` at `0x14004f808`
- `rdbss!RxNameCacheActivateEntry` at `0x14004f7ec`
- `rdbss!RxNameCacheActivateEntry` at `0x14004f7ec`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004f6f9`
- `rdbss!RxNameCacheFetchEntryEx` at `0x14004f6f9`
- `rdbss!RxNameCacheCheckEntry` at `0x14004f76d`
- `rdbss!RxNameCacheCheckEntry` at `0x14004f76d`

## pseudocode

```c
char __fastcall MRxSmbIsFileInFullDirectoryCache(__int64 a1, _BYTE *a2, __int64 a3)
{
  __int64 v3; // rax
  char v4; // bp
  unsigned __int16 *v7; // rbx
  __int64 v8; // rax
  unsigned __int16 v9; // r9
  __int64 v10; // rsi
  unsigned __int16 v11; // ax
  unsigned int v12; // r8d
  __int64 v13; // r9
  __int64 v14; // r10
  __int64 v15; // rcx
  struct _NAME_CACHE_CONTROL_ *v16; // rsi
  struct _NAME_CACHE *Entry; // rax
  struct _NAME_CACHE *v18; // rdi
  char IsFileInPartialDirectoryCache; // al
  __int128 v21; // [rsp+30h] [rbp-38h] BYREF
  __int128 v22; // [rsp+40h] [rbp-28h] BYREF
  char v23; // [rsp+70h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a1 + 56);
  v4 = 0;
  v21 = 0;
  v7 = (unsigned __int16 *)(v3 + 360);
  v22 = 0;
  if ( *(_BYTE *)(a1 + 32) )
    v8 = *(_QWORD *)(v3 + 120);
  else
    v8 = *(_QWORD *)(a1 + 648);
  v9 = *v7;
  v10 = *(_QWORD *)(v8 + 40);
  v11 = 0;
  *a2 = 0;
  while ( 1 )
  {
    if ( v11 >= (unsigned __int16)(v9 >> 1) )
    {
      WORD1(v21) = v9;
      LOWORD(v21) = v9;
      goto LABEL_8;
    }
    if ( *(_WORD *)(*((_QWORD *)v7 + 1) + 2LL * v11) == 58 )
      break;
    ++v11;
  }
  WORD1(v21) = 2 * v11;
  LOWORD(v21) = 2 * v11;
LABEL_8:
  *((_QWORD *)&v21 + 1) = *((_QWORD *)v7 + 1);
  v12 = *v7 >> 1;
  v13 = *((_QWORD *)v7 + 1);
  v14 = v13;
  if ( v12 )
  {
    v15 = 0;
    do
    {
      if ( *(_WORD *)(v13 + 2 * v15) == 92 )
        v14 = v13 + 2 * v15;
      v15 = (unsigned int)(v15 + 1);
    }
    while ( (unsigned int)v15 < v12 );
  }
  LOWORD(v22) = 2 * ((v14 - v13) >> 1);
  WORD1(v22) = v22;
  *((_QWORD *)&v22 + 1) = *((_QWORD *)v7 + 1);
  if ( !(_WORD)v22 )
    return 0;
  v16 = (struct _NAME_CACHE_CONTROL_ *)(v10 + 1024);
  ExAcquireFastMutex(&MRxSmbFileInfoCacheLock);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(v16, &v22, 0, 0);
  v18 = Entry;
  if ( Entry )
  {
    if ( RxNameCacheCheckEntry(Entry, Entry->ExpireTime.LowPart) )
    {
      RxNameCacheExpireEntry(v16, v18);
    }
    else
    {
      v23 = 1;
      IsFileInPartialDirectoryCache = MRxSmbIsFileInPartialDirectoryCache(v18, &v21, &v23, a3);
      *a2 = IsFileInPartialDirectoryCache;
      if ( IsFileInPartialDirectoryCache
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_ZZ(
          WPP_GLOBAL_Control->AttachedDevice,
          25,
          (unsigned int)WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids,
          (_DWORD)v7,
          (__int64)&v22);
      }
      RxNameCacheActivateEntry(v16, v18, 0, 0);
      v4 = v23;
    }
  }
  ExReleaseFastMutex(&MRxSmbFileInfoCacheLock);
  return v4;
}

```

## disassembly

```asm
0x14004f5e0  mov     [rsp+arg_10], rbx
0x14004f5e5  mov     [rsp+arg_18], rbp
0x14004f5ea  push    rsi
0x14004f5eb  push    r14
0x14004f5ed  push    r15
0x14004f5ef  sub     rsp, 50h
0x14004f5f3  mov     rax, [rcx+38h]
0x14004f5f7  xor     bpl, bpl
0x14004f5fa  xorps   xmm0, xmm0
0x14004f5fd  xorps   xmm1, xmm1
0x14004f600  mov     r15, r8
0x14004f603  mov     r14, rdx
0x14004f606  movups  [rsp+68h+var_38], xmm0
0x14004f60b  lea     rbx, [rax+168h]
0x14004f612  movups  [rsp+68h+var_28], xmm1
0x14004f617  cmp     [rcx+20h], bpl
0x14004f61b  jnz     loc_14004F748
0x14004f621  mov     rax, [rcx+288h]
0x14004f628  movzx   r9d, word ptr [rbx]
0x14004f62c  mov     rsi, [rax+28h]
0x14004f630  movzx   r8d, r9w
0x14004f634  xor     eax, eax
0x14004f636  mov     [rdx], bpl
0x14004f639  shr     r8w, 1
0x14004f63d  nop     dword ptr [rax]
0x14004f640  cmp     ax, r8w
0x14004f644  jnb     short loc_14004F65D
0x14004f646  mov     rcx, [rbx+8]
0x14004f64a  movzx   edx, ax
0x14004f64d  cmp     word ptr [rcx+rdx*2], 3Ah ; ':'
0x14004f652  jz      loc_14004F751
0x14004f658  inc     ax
0x14004f65b  jmp     short loc_14004F640
0x14004f65d  mov     word ptr [rsp+68h+var_38+2], r9w
0x14004f663  mov     word ptr [rsp+68h+var_38], r9w
0x14004f669  mov     rax, [rbx+8]
0x14004f66d  mov     qword ptr [rsp+68h+var_38+8], rax
0x14004f672  movzx   r8d, word ptr [rbx]
0x14004f676  shr     r8d, 1
0x14004f679  mov     r9, [rbx+8]
0x14004f67d  mov     r10, r9
0x14004f680  jz      short loc_14004F6A7
0x14004f682  xor     ecx, ecx
0x14004f684  nop     dword ptr [rax+00h]
0x14004f688  nop     dword ptr [rax+rax+00000000h]
0x14004f690  cmp     word ptr [r9+rcx*2], 5Ch ; '\'
0x14004f696  lea     rdx, [r9+rcx*2]
0x14004f69a  jz      loc_14004F740
0x14004f6a0  inc     ecx
0x14004f6a2  cmp     ecx, r8d
0x14004f6a5  jb      short loc_14004F690
0x14004f6a7  sub     r10, r9
0x14004f6aa  sar     r10, 1
0x14004f6ad  add     r10w, r10w
0x14004f6b1  mov     word ptr [rsp+68h+var_28], r10w
0x14004f6b7  mov     word ptr [rsp+68h+var_28+2], r10w
0x14004f6bd  mov     rax, [rbx+8]
0x14004f6c1  mov     qword ptr [rsp+68h+var_28+8], rax
0x14004f6c6  jz      loc_14004F763
0x14004f6cc  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004f6d3  mov     [rsp+68h+arg_8], rdi
0x14004f6d8  add     rsi, 400h
0x14004f6df  call    cs:__imp_ExAcquireFastMutex
0x14004f6e6  nop     dword ptr [rax+rax+00h]
0x14004f6eb  xor     r9d, r9d
0x14004f6ee  lea     rdx, [rsp+68h+var_28]
0x14004f6f3  xor     r8d, r8d
0x14004f6f6  mov     rcx, rsi
0x14004f6f9  call    cs:__imp_RxNameCacheFetchEntryEx
0x14004f700  nop     dword ptr [rax+rax+00h]
0x14004f705  mov     rdi, rax
0x14004f708  test    rax, rax
0x14004f70b  jnz     short loc_14004F767
0x14004f70d  lea     rcx, MRxSmbFileInfoCacheLock; FastMutex
0x14004f714  call    cs:__imp_ExReleaseFastMutex
0x14004f71b  nop     dword ptr [rax+rax+00h]
0x14004f720  mov     rdi, [rsp+68h+arg_8]
0x14004f725  movzx   eax, bpl
0x14004f729  lea     r11, [rsp+68h+var_18]
0x14004f72e  mov     rbx, [r11+30h]
0x14004f732  mov     rbp, [r11+38h]
0x14004f736  mov     rsp, r11
0x14004f739  pop     r15
0x14004f73b  pop     r14
0x14004f73d  pop     rsi
0x14004f73e  retn
0x14004f740  mov     r10, rdx
0x14004f743  jmp     loc_14004F6A0
0x14004f748  mov     rax, [rax+78h]
0x14004f74c  jmp     loc_14004F628
0x14004f751  add     ax, ax
0x14004f754  mov     word ptr [rsp+68h+var_38+2], ax
0x14004f759  mov     word ptr [rsp+68h+var_38], ax
0x14004f75e  jmp     loc_14004F669
0x14004f763  xor     al, al
0x14004f765  jmp     short loc_14004F729
0x14004f767  mov     edx, [rax+20h]; MRxContext
0x14004f76a  mov     rcx, rdi; NameCache
0x14004f76d  call    cs:__imp_RxNameCacheCheckEntry
0x14004f774  nop     dword ptr [rax+rax+00h]
0x14004f779  test    eax, eax
0x14004f77b  jnz     loc_14004F802
0x14004f781  mov     r9, r15
0x14004f784  mov     [rsp+68h+arg_0], 1
0x14004f789  lea     r8, [rsp+68h+arg_0]
0x14004f78e  mov     rcx, rdi
0x14004f791  lea     rdx, [rsp+68h+var_38]
0x14004f796  call    MRxSmbIsFileInPartialDirectoryCache
0x14004f79b  mov     [r14], al
0x14004f79e  test    al, al
0x14004f7a0  jz      short loc_14004F7E0
0x14004f7a2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004f7a9  lea     rax, WPP_GLOBAL_Control
0x14004f7b0  cmp     rcx, rax
0x14004f7b3  jz      short loc_14004F7E0
0x14004f7b5  test    dword ptr [rcx+2Ch], 200h
0x14004f7bc  jz      short loc_14004F7E0
0x14004f7be  mov     rcx, [rcx+18h]
0x14004f7c2  lea     rax, [rsp+68h+var_28]
0x14004f7c7  mov     edx, 19h
0x14004f7cc  mov     [rsp+68h+var_48], rax
0x14004f7d1  mov     r9, rbx
0x14004f7d4  lea     r8, WPP_b212f69114bb35f6b87b4b67978f4184_Traceguids
0x14004f7db  call    WPP_SF_ZZ
0x14004f7e0  xor     r9d, r9d; MRxContext
0x14004f7e3  xor     r8d, r8d; LifeTime
0x14004f7e6  mov     rdx, rdi; NameCache
0x14004f7e9  mov     rcx, rsi; NameCacheCtl
0x14004f7ec  call    cs:__imp_RxNameCacheActivateEntry
0x14004f7f3  nop     dword ptr [rax+rax+00h]
0x14004f7f8  movzx   ebp, [rsp+68h+arg_0]
0x14004f7fd  jmp     loc_14004F70D
0x14004f802  mov     rdx, rdi; NameCache
0x14004f805  mov     rcx, rsi; NameCacheCtl
0x14004f808  call    cs:__imp_RxNameCacheExpireEntry
0x14004f80f  nop     dword ptr [rax+rax+00h]
0x14004f814  jmp     loc_14004F70D
```
