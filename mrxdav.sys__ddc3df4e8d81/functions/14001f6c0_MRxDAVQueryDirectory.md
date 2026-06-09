# MRxDAVQueryDirectory

- ea: `0x14001f6c0`
- end: `0x14001fa64`
- name: `MRxDAVQueryDirectory`
- size: `932`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `15`
- tags: ``

## callees

- `0x14000163c`
- `0x140001680`
- `0x1400017e4`
- `0x1400027ac`
- `0x140003698`
- `0x140006900`
- `0x140006c00`
- `0x14001f6c0`
- `0x14001fc00`
- `0x1400252f8`
- `0x140025758`
- `0x14002593c`
- `0x140025a08`
- `0x140025aa0`
- `0x1400269d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f70e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f74a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fa2a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f70e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001f74a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fa2a`
- `ntoskrnl!ExAllocatePool2` at `0x14001f7fe`
- `ntoskrnl!ExAllocatePool2` at `0x14001f7fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fa05`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001fa05`

## string_xrefs

- `0x14001f960`: `MRxDAVQueryDirectory`

## pseudocode

```c
__int64 __fastcall MRxDAVQueryDirectory(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // r14
  __int64 v4; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v6; // rbx
  HANDLE v7; // rax
  unsigned __int16 v8; // cx
  unsigned __int16 v9; // ax
  int v10; // edi
  void *Pool2; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  void *v14; // rbx
  unsigned __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rbx
  HANDLE v19; // rax
  PVOID P[2]; // [rsp+30h] [rbp-29h] BYREF
  _QWORD v22[14]; // [rsp+40h] [rbp-19h] BYREF
  int v23; // [rsp+C0h] [rbp+67h] BYREF

  v1 = *(_QWORD *)(a1 + 56);
  v2 = *(_QWORD *)(a1 + 64);
  *(_OWORD *)P = 0;
  v23 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v4, 10, WPP_609949de13fe38daba556366630c430b_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v7 = PsGetCurrentThreadId();
      WPP_SF_qq(v6, 11, WPP_609949de13fe38daba556366630c430b_Traceguids, v7, a1);
    }
  }
  P[1] = 0;
  v8 = *(_WORD *)(v1 + 360);
  if ( v8 <= 0x208u )
  {
    v9 = *(_WORD *)(v2 + 80);
    if ( v9 <= 0x208u )
    {
      WORD1(P[0]) = v8 + v9 + 2;
      LOWORD(P[0]) = WORD1(P[0]);
      if ( WORD1(P[0]) > 0x208u )
      {
        v10 = -1073741562;
        LODWORD(P[0]) = 0;
        goto LABEL_39;
      }
      if ( *(_BYTE *)(a1 + 518) )
      {
        v10 = -1073741822;
        LODWORD(P[0]) = 0;
        goto LABEL_39;
      }
      if ( *(_DWORD *)(a1 + 448) == 37 || *(_DWORD *)(a1 + 448) == 38 )
      {
        v10 = -1073741637;
        goto LABEL_39;
      }
      Pool2 = (void *)ExAllocatePool2(258, 520, 1683052100);
      P[1] = Pool2;
      if ( !Pool2 )
      {
        v10 = -1073741670;
        goto LABEL_37;
      }
      memset(Pool2, 0, 0x208u);
      memmove(P[1], *(const void **)(v1 + 368), *(unsigned __int16 *)(v1 + 360));
      *((_WORD *)P[1] + ((unsigned __int64)*(unsigned __int16 *)(v1 + 360) >> 1)) = 92;
      memmove(
        (char *)P[1] + 2 * ((unsigned __int64)*(unsigned __int16 *)(v1 + 360) >> 1) + 2,
        *(const void **)(v2 + 88),
        *(unsigned __int16 *)(v2 + 80));
      if ( !*(_BYTE *)(a1 + 520) )
      {
        memset(v22, 0, 0x40u);
        if ( v2 )
          v2 = *(_QWORD *)(v2 + 56);
        if ( *(_DWORD *)(v2 + 12) )
        {
          *(_QWORD *)(v2 + 8) = 0;
          v10 = -2147483642;
          goto LABEL_37;
        }
        if ( MRxDAVIsFileNotFoundCachedWithName((__int64)P, *(_QWORD *)(v1 + 120)) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
          {
            WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 3), 12, WPP_609949de13fe38daba556366630c430b_Traceguids, P);
          }
          v10 = -1073741772;
          goto LABEL_37;
        }
        if ( (unsigned __int8)MRxDAVIsFileInfoCacheFound(a1, v22, &v23, P) )
        {
          v14 = *(void **)(a1 + 456);
          memset(v14, 0, *(unsigned int *)(a1 + 472));
          v10 = MRxDAVQueryDirectoryFromCache(a1, (__int64)v14, (__int64)v22, &v22[5]);
          if ( v10 >= 0 )
          {
            *(_DWORD *)(v2 + 8) = 1;
            *(_DWORD *)(v2 + 12) = 1;
          }
          goto LABEL_37;
        }
      }
      v10 = UMRxAsyncEngOuterWrapper(
              a1,
              v12,
              v13,
              0xBu,
              MRxDAVQueryDirectoryContinuation,
              (__int64)"MRxDAVQueryDirectory");
      v15 = (unsigned int)(v10 + 1073741809);
      if ( (unsigned int)v15 <= 0x2B )
      {
        v16 = 0x82000000001LL;
        if ( _bittest64(&v16, v15) )
        {
          if ( (int)MRxDAVQueryDirectoryFake(a1, (const UNICODE_STRING *)P) < 0 )
          {
            MRxDAVCacheFileNotFoundWithName(P, *(_QWORD *)(*(_QWORD *)(a1 + 56) + 120LL));
            v17 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 120LL);
            MRxDAVInvalidateBasicFileInfoCacheWithName(P, v17);
            MRxDAVInvalidateStandardFileInfoCacheWithName(P, v17);
          }
          else
          {
            v10 = 0;
          }
        }
      }
      goto LABEL_37;
    }
  }
  v10 = -1073741562;
  LODWORD(P[0]) = 0;
LABEL_37:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0);
LABEL_39:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v19 = PsGetCurrentThreadId();
    WPP_SF_qD(v18, 13, WPP_609949de13fe38daba556366630c430b_Traceguids, v19, v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14001f6c0  push    rbp
0x14001f6c2  push    rbx
0x14001f6c3  push    rsi
0x14001f6c4  push    rdi
0x14001f6c5  push    r12
0x14001f6c7  push    r14
0x14001f6c9  lea     rbp, [rsp-2Fh]
0x14001f6ce  sub     rsp, 88h
0x14001f6d5  mov     rdi, [rcx+38h]
0x14001f6d9  xorps   xmm0, xmm0
0x14001f6dc  mov     r14, [rcx+40h]
0x14001f6e0  mov     rsi, rcx
0x14001f6e3  movups  xmmword ptr [rbp+57h+P], xmm0
0x14001f6e7  mov     [rbp+57h+arg_0], 0
0x14001f6ee  mov     rbx, cs:WPP_GLOBAL_Control
0x14001f6f5  lea     r12, WPP_GLOBAL_Control
0x14001f6fc  cmp     rbx, r12
0x14001f6ff  jz      short loc_14001F772
0x14001f701  test    dword ptr [rbx+2Ch], 2000h
0x14001f708  jz      short loc_14001F731
0x14001f70a  mov     rbx, [rbx+18h]
0x14001f70e  call    cs:__imp_PsGetCurrentThreadId
0x14001f715  nop     dword ptr [rax+rax+00h]
0x14001f71a  mov     edx, 0Ah
0x14001f71f  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001f726  mov     r9, rax
0x14001f729  mov     rcx, rbx
0x14001f72c  call    WPP_SF_q
0x14001f731  mov     rbx, cs:WPP_GLOBAL_Control
0x14001f738  cmp     rbx, r12
0x14001f73b  jz      short loc_14001F772
0x14001f73d  test    dword ptr [rbx+2Ch], 2000h
0x14001f744  jz      short loc_14001F772
0x14001f746  mov     rbx, [rbx+18h]
0x14001f74a  call    cs:__imp_PsGetCurrentThreadId
0x14001f751  nop     dword ptr [rax+rax+00h]
0x14001f756  mov     edx, 0Bh
0x14001f75b  mov     [rsp+0B0h+var_90], rsi
0x14001f760  mov     r9, rax
0x14001f763  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001f76a  mov     rcx, rbx
0x14001f76d  call    WPP_SF_qq
0x14001f772  mov     [rbp+57h+P+8], 0
0x14001f77a  mov     ebx, 208h
0x14001f77f  movzx   ecx, word ptr [rdi+168h]
0x14001f786  cmp     bx, cx
0x14001f789  jb      loc_14001F9F0
0x14001f78f  movzx   eax, word ptr [r14+50h]
0x14001f794  cmp     bx, ax
0x14001f797  jb      loc_14001F9F0
0x14001f79d  add     ax, 2
0x14001f7a1  add     ax, cx
0x14001f7a4  mov     word ptr [rbp+57h+P+2], ax
0x14001f7a8  mov     word ptr [rbp+57h+P], ax
0x14001f7ac  cmp     ax, bx
0x14001f7af  jbe     short loc_14001F7C0
0x14001f7b1  xor     eax, eax
0x14001f7b3  mov     edi, 0C0000106h
0x14001f7b8  mov     dword ptr [rbp+57h+P], eax
0x14001f7bb  jmp     loc_14001FA11
0x14001f7c0  cmp     byte ptr [rsi+206h], 0
0x14001f7c7  jz      short loc_14001F7D8
0x14001f7c9  xor     eax, eax
0x14001f7cb  mov     edi, 0C0000002h
0x14001f7d0  mov     dword ptr [rbp+57h+P], eax
0x14001f7d3  jmp     loc_14001FA11
0x14001f7d8  mov     ecx, [rsi+1C0h]
0x14001f7de  sub     ecx, 25h ; '%'
0x14001f7e1  jz      loc_14001F9E9
0x14001f7e7  cmp     ecx, 1
0x14001f7ea  jz      loc_14001F9E9
0x14001f7f0  mov     r8d, 64515644h
0x14001f7f6  mov     rdx, rbx
0x14001f7f9  mov     ecx, 102h
0x14001f7fe  call    cs:__imp_ExAllocatePool2
0x14001f805  nop     dword ptr [rax+rax+00h]
0x14001f80a  mov     [rbp+57h+P+8], rax
0x14001f80e  test    rax, rax
0x14001f811  jnz     short loc_14001F81D
0x14001f813  mov     edi, 0C000009Ah
0x14001f818  jmp     loc_14001F9FA
0x14001f81d  mov     r8, rbx; Size
0x14001f820  xor     edx, edx; Val
0x14001f822  mov     rcx, rax; void *
0x14001f825  call    memset
0x14001f82a  movzx   r8d, word ptr [rdi+168h]; Size
0x14001f832  mov     rdx, [rdi+170h]; Src
0x14001f839  mov     rcx, [rbp+57h+P+8]; void *
0x14001f83d  call    memmove
0x14001f842  movzx   ecx, word ptr [rdi+168h]
0x14001f849  mov     rax, [rbp+57h+P+8]
0x14001f84d  shr     rcx, 1
0x14001f850  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x14001f856  movzx   ecx, word ptr [rdi+168h]
0x14001f85d  mov     rax, [rbp+57h+P+8]
0x14001f861  movzx   r8d, word ptr [r14+50h]; Size
0x14001f866  add     rax, 2
0x14001f86a  mov     rdx, [r14+58h]; Src
0x14001f86e  shr     rcx, 1
0x14001f871  lea     rcx, [rax+rcx*2]; void *
0x14001f875  call    memmove
0x14001f87a  cmp     byte ptr [rsi+208h], 0
0x14001f881  jnz     loc_14001F960
0x14001f887  xor     edx, edx; Val
0x14001f889  lea     rcx, [rbp+57h+var_70]; void *
0x14001f88d  lea     r8d, [rdx+40h]; Size
0x14001f891  call    memset
0x14001f896  test    r14, r14
0x14001f899  jz      short loc_14001F89F
0x14001f89b  mov     r14, [r14+38h]
0x14001f89f  cmp     dword ptr [r14+0Ch], 0
0x14001f8a4  jbe     short loc_14001F8B8
0x14001f8a6  mov     qword ptr [r14+8], 0
0x14001f8ae  mov     edi, 80000006h
0x14001f8b3  jmp     loc_14001F9FA
0x14001f8b8  mov     rdx, [rdi+78h]
0x14001f8bc  lea     rcx, [rbp+57h+P]
0x14001f8c0  call    MRxDAVIsFileNotFoundCachedWithName
0x14001f8c5  test    al, al
0x14001f8c7  jz      short loc_14001F901
0x14001f8c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f8d0  cmp     rcx, r12
0x14001f8d3  jz      short loc_14001F8F7
0x14001f8d5  test    dword ptr [rcx+2Ch], 4000h
0x14001f8dc  jz      short loc_14001F8F7
0x14001f8de  mov     rcx, [rcx+18h]
0x14001f8e2  lea     r9, [rbp+57h+P]
0x14001f8e6  mov     edx, 0Ch
0x14001f8eb  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001f8f2  call    WPP_SF_Z
0x14001f8f7  mov     edi, 0C0000034h
0x14001f8fc  jmp     loc_14001F9FA
0x14001f901  lea     r9, [rbp+57h+P]
0x14001f905  mov     rcx, rsi
0x14001f908  lea     r8, [rbp+57h+arg_0]
0x14001f90c  lea     rdx, [rbp+57h+var_70]
0x14001f910  call    MRxDAVIsFileInfoCacheFound
0x14001f915  test    al, al
0x14001f917  jz      short loc_14001F960
0x14001f919  mov     rbx, [rsi+1C8h]
0x14001f920  xor     edx, edx; Val
0x14001f922  mov     r8d, [rsi+1D8h]; Size
0x14001f929  mov     rcx, rbx; void *
0x14001f92c  call    memset
0x14001f931  lea     r9, [rbp+57h+var_48]
0x14001f935  mov     rdx, rbx
0x14001f938  lea     r8, [rbp+57h+var_70]
0x14001f93c  mov     rcx, rsi
0x14001f93f  call    MRxDAVQueryDirectoryFromCache
0x14001f944  mov     edi, eax
0x14001f946  test    eax, eax
0x14001f948  js      loc_14001F9FA
0x14001f94e  mov     eax, 1
0x14001f953  mov     [r14+8], eax
0x14001f957  mov     [r14+0Ch], eax
0x14001f95b  jmp     loc_14001F9FA
0x14001f960  lea     rax, aMrxdavquerydir; "MRxDAVQueryDirectory"
0x14001f967  mov     r9d, 0Bh
0x14001f96d  mov     [rsp+0B0h+var_88], rax
0x14001f972  mov     rcx, rsi
0x14001f975  lea     rax, MRxDAVQueryDirectoryContinuation
0x14001f97c  mov     [rsp+0B0h+var_90], rax
0x14001f981  call    UMRxAsyncEngOuterWrapper
0x14001f986  mov     edi, eax
0x14001f988  add     eax, 3FFFFFF1h
0x14001f98d  cmp     eax, 2Bh ; '+'
0x14001f990  ja      short loc_14001F9FA
0x14001f992  mov     rcx, 82000000001h
0x14001f99c  bt      rcx, rax
0x14001f9a0  jnb     short loc_14001F9FA
0x14001f9a2  lea     rdx, [rbp+57h+P]
0x14001f9a6  mov     rcx, rsi
0x14001f9a9  call    MRxDAVQueryDirectoryFake
0x14001f9ae  test    eax, eax
0x14001f9b0  js      short loc_14001F9B6
0x14001f9b2  xor     edi, edi
0x14001f9b4  jmp     short loc_14001F9FA
0x14001f9b6  mov     rdx, [rsi+38h]
0x14001f9ba  lea     rcx, [rbp+57h+P]
0x14001f9be  mov     rdx, [rdx+78h]
0x14001f9c2  call    MRxDAVCacheFileNotFoundWithName
0x14001f9c7  mov     rax, [rsi+38h]
0x14001f9cb  lea     rcx, [rbp+57h+P]
0x14001f9cf  mov     rbx, [rax+78h]
0x14001f9d3  mov     rdx, rbx
0x14001f9d6  call    MRxDAVInvalidateBasicFileInfoCacheWithName
0x14001f9db  mov     rdx, rbx
0x14001f9de  lea     rcx, [rbp+57h+P]
0x14001f9e2  call    MRxDAVInvalidateStandardFileInfoCacheWithName
0x14001f9e7  jmp     short loc_14001F9FA
0x14001f9e9  mov     edi, 0C00000BBh
0x14001f9ee  jmp     short loc_14001FA11
0x14001f9f0  xor     eax, eax
0x14001f9f2  mov     edi, 0C0000106h
0x14001f9f7  mov     dword ptr [rbp+57h+P], eax
0x14001f9fa  mov     rcx, [rbp+57h+P+8]; P
0x14001f9fe  test    rcx, rcx
0x14001fa01  jz      short loc_14001FA11
0x14001fa03  xor     edx, edx; Tag
0x14001fa05  call    cs:__imp_ExFreePoolWithTag
0x14001fa0c  nop     dword ptr [rax+rax+00h]
0x14001fa11  mov     rbx, cs:WPP_GLOBAL_Control
0x14001fa18  cmp     rbx, r12
0x14001fa1b  jz      short loc_14001FA51
0x14001fa1d  test    dword ptr [rbx+2Ch], 2000h
0x14001fa24  jz      short loc_14001FA51
0x14001fa26  mov     rbx, [rbx+18h]
0x14001fa2a  call    cs:__imp_PsGetCurrentThreadId
0x14001fa31  nop     dword ptr [rax+rax+00h]
0x14001fa36  mov     edx, 0Dh
0x14001fa3b  mov     dword ptr [rsp+0B0h+var_90], edi
0x14001fa3f  mov     r9, rax
0x14001fa42  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14001fa49  mov     rcx, rbx
0x14001fa4c  call    WPP_SF_qD
0x14001fa51  mov     eax, edi
0x14001fa53  add     rsp, 88h
0x14001fa5a  pop     r14
0x14001fa5c  pop     r12
0x14001fa5e  pop     rdi
0x14001fa5f  pop     rsi
0x14001fa60  pop     rbx
0x14001fa61  pop     rbp
0x14001fa62  retn
```
