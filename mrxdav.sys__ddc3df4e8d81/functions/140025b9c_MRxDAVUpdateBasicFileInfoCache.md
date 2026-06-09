# MRxDAVUpdateBasicFileInfoCache

- ea: `0x140025b9c`
- end: `0x140025cfa`
- name: `MRxDAVUpdateBasicFileInfoCache`
- size: `350`
- prototype: `void __fastcall(__int64, int, __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140011eec`
- `0x140022a80`

## callees

- `0x140005ee8`
- `0x140005f88`
- `0x140025b9c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140025be7`
- `ntoskrnl!ExAcquireFastMutex` at `0x140025be7`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025cde`
- `ntoskrnl!ExReleaseFastMutex` at `0x140025cde`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140025c00`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140025c00`
- `rdbss!RxNameCacheActivateEntry` at `0x140025c71`
- `rdbss!RxNameCacheActivateEntry` at `0x140025c71`

## pseudocode

```c
void __fastcall MRxDAVUpdateBasicFileInfoCache(__int64 a1, int a2, __int64 *a3)
{
  __int64 v3; // rdi
  __int64 v5; // rax
  __int64 v6; // rbp
  __int64 v7; // rax
  __int64 v8; // r15
  __int64 Entry; // rax
  int v10; // r8d
  struct _NAME_CACHE *v11; // r14
  __int64 v12; // rbx
  unsigned int v13; // esi
  int v14; // r8d

  v3 = 0;
  if ( a3 && *a3 )
    v3 = *a3;
  v5 = *(_QWORD *)(a1 + 56);
  v6 = v5 + 360;
  if ( *(_BYTE *)(a1 + 32) )
    v7 = *(_QWORD *)(v5 + 120);
  else
    v7 = *(_QWORD *)(a1 + 648);
  v8 = *(_QWORD *)(v7 + 40);
  ExAcquireFastMutex(&MRxDAVFileInfoCacheLock);
  Entry = RxNameCacheFetchEntryEx(v8 + 16, v6, 0, 0);
  v11 = (struct _NAME_CACHE *)Entry;
  if ( Entry )
  {
    v12 = *(_QWORD *)(Entry + 40);
    if ( v3 )
      *(_QWORD *)(v12 + 16) = v3;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
    {
      WPP_SF_DZ(*((_QWORD *)WPP_GLOBAL_Control + 3), 19, v10, *(_DWORD *)(v12 + 32), v6);
    }
    *(_DWORD *)(v12 + 32) = a2;
    v13 = a2 & 0xFFFFFF7F;
    if ( v13 )
      *(_DWORD *)(v12 + 32) = v13;
    RxNameCacheActivateEntry((PNAME_CACHE_CONTROL)(v8 + 16), v11, 0, 0);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
        WPP_SF_DZ(*((_QWORD *)WPP_GLOBAL_Control + 3), 20, v14, *(_DWORD *)(v12 + 32), v6);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xDu) )
      {
        WPP_SF_ddZ(*((_QWORD *)WPP_GLOBAL_Control + 3), 21, v14, *(_DWORD *)v12, *(_DWORD *)(v12 + 8), v6);
      }
    }
  }
  ExReleaseFastMutex(&MRxDAVFileInfoCacheLock);
}

```

## disassembly

```asm
0x140025b9c  push    rbx
0x140025b9e  push    rbp
0x140025b9f  push    rsi
0x140025ba0  push    rdi
0x140025ba1  push    r12
0x140025ba3  push    r14
0x140025ba5  push    r15
0x140025ba7  sub     rsp, 30h
0x140025bab  xor     edi, edi
0x140025bad  mov     esi, edx
0x140025baf  test    r8, r8
0x140025bb2  jz      short loc_140025BBE
0x140025bb4  mov     rax, [r8]
0x140025bb7  test    rax, rax
0x140025bba  cmovnz  rdi, rax
0x140025bbe  cmp     byte ptr [rcx+20h], 0
0x140025bc2  mov     rax, [rcx+38h]
0x140025bc6  lea     rbp, [rax+168h]
0x140025bcd  jnz     short loc_140025BD8
0x140025bcf  mov     rax, [rcx+288h]
0x140025bd6  jmp     short loc_140025BDC
0x140025bd8  mov     rax, [rax+78h]
0x140025bdc  mov     r15, [rax+28h]
0x140025be0  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x140025be7  call    cs:__imp_ExAcquireFastMutex
0x140025bee  nop     dword ptr [rax+rax+00h]
0x140025bf3  xor     r9d, r9d
0x140025bf6  lea     rcx, [r15+10h]
0x140025bfa  xor     r8d, r8d
0x140025bfd  mov     rdx, rbp
0x140025c00  call    cs:__imp_RxNameCacheFetchEntryEx
0x140025c07  nop     dword ptr [rax+rax+00h]
0x140025c0c  mov     r14, rax
0x140025c0f  test    rax, rax
0x140025c12  jz      loc_140025CD7
0x140025c18  mov     rbx, [rax+28h]
0x140025c1c  test    rdi, rdi
0x140025c1f  jz      short loc_140025C25
0x140025c21  mov     [rbx+10h], rdi
0x140025c25  mov     rcx, cs:WPP_GLOBAL_Control
0x140025c2c  lea     r12, WPP_GLOBAL_Control
0x140025c33  cmp     rcx, r12
0x140025c36  jz      short loc_140025C56
0x140025c38  bt      dword ptr [rcx+2Ch], 0Dh
0x140025c3d  jnb     short loc_140025C56
0x140025c3f  mov     r9d, [rbx+20h]
0x140025c43  mov     edx, 13h
0x140025c48  mov     rcx, [rcx+18h]
0x140025c4c  mov     [rsp+68h+var_48], rbp
0x140025c51  call    WPP_SF_DZ
0x140025c56  mov     [rbx+20h], esi
0x140025c59  and     esi, 0FFFFFF7Fh
0x140025c5f  jz      short loc_140025C64
0x140025c61  mov     [rbx+20h], esi
0x140025c64  xor     r9d, r9d; MRxContext
0x140025c67  lea     rcx, [r15+10h]; NameCacheCtl
0x140025c6b  xor     r8d, r8d; LifeTime
0x140025c6e  mov     rdx, r14; NameCache
0x140025c71  call    cs:__imp_RxNameCacheActivateEntry
0x140025c78  nop     dword ptr [rax+rax+00h]
0x140025c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140025c84  cmp     rcx, r12
0x140025c87  jz      short loc_140025CD7
0x140025c89  bt      dword ptr [rcx+2Ch], 0Dh
0x140025c8e  jnb     short loc_140025CA7
0x140025c90  mov     r9d, [rbx+20h]
0x140025c94  mov     edx, 14h
0x140025c99  mov     rcx, [rcx+18h]
0x140025c9d  mov     [rsp+68h+var_48], rbp
0x140025ca2  call    WPP_SF_DZ
0x140025ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x140025cae  cmp     rcx, r12
0x140025cb1  jz      short loc_140025CD7
0x140025cb3  bt      dword ptr [rcx+2Ch], 0Dh
0x140025cb8  jnb     short loc_140025CD7
0x140025cba  mov     eax, [rbx+8]
0x140025cbd  mov     edx, 15h
0x140025cc2  mov     r9d, [rbx]
0x140025cc5  mov     rcx, [rcx+18h]
0x140025cc9  mov     [rsp+68h+var_40], rbp
0x140025cce  mov     dword ptr [rsp+68h+var_48], eax
0x140025cd2  call    WPP_SF_ddZ
0x140025cd7  lea     rcx, MRxDAVFileInfoCacheLock; FastMutex
0x140025cde  call    cs:__imp_ExReleaseFastMutex
0x140025ce5  nop     dword ptr [rax+rax+00h]
0x140025cea  add     rsp, 30h
0x140025cee  pop     r15
0x140025cf0  pop     r14
0x140025cf2  pop     r12
0x140025cf4  pop     rdi
0x140025cf5  pop     rsi
0x140025cf6  pop     rbp
0x140025cf7  pop     rbx
0x140025cf8  retn
```
