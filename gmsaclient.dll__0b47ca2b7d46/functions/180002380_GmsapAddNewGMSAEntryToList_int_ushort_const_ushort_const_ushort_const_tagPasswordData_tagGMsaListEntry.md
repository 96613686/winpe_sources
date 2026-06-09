# GmsapAddNewGMSAEntryToList(int,ushort const *,ushort const *,ushort const *,_tagPasswordData *,_tagGMsaListEntry * *)

- ea: `0x180002380`
- end: `0x1800025aa`
- name: `?GmsapAddNewGMSAEntryToList@@YAJHPEBG00PEAU_tagPasswordData@@PEAPEAU_tagGMsaListEntry@@@Z`
- size: `554`
- prototype: `int(int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _tagPasswordData *, struct _tagGMsaListEntry **)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180003e84`
- `0x1800043f0`

## callees

- `0x180002380`
- `0x180003160`
- `0x180005018`
- `0x180006280`
- `0x1800062b0`
- `0x1800063cc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800023d8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800023d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002487`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002503`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002522`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002487`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800024de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002503`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002522`

## pseudocode

```c
__int64 __fastcall GmsapAddNewGMSAEntryToList(
        int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct _tagPasswordData *a5,
        FILETIME **a6)
{
  FILETIME *v10; // rbx
  int v11; // edi
  int updated; // eax
  void *v13; // rcx
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  void *v17; // rcx
  _QWORD *v19; // rax
  __int64 v20[9]; // [rsp+30h] [rbp-48h] BYREF

  LODWORD(v20[0]) = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x2Cu, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
  v10 = (FILETIME *)LocalAlloc(0x40u, 0x68u);
  if ( !v10 )
  {
    v11 = -1073741801;
    goto LABEL_24;
  }
  v11 = GmsapDuplicateStringStrict(a2);
  if ( v11 < 0 )
    goto LABEL_13;
  v11 = GmsapDuplicateStringStrict(a3);
  if ( v11 < 0 )
    goto LABEL_13;
  v11 = GmsapDuplicateStringStrict(a4);
  if ( v11 < 0 )
    goto LABEL_13;
  updated = GmsapUpdateGMSAEntry(v10, a5, (int *)v20);
  v11 = updated;
  if ( updated < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_SSD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        (unsigned int)&WPP_70b8577d707437755865c965214ce19a_Traceguids,
        (_DWORD)a3,
        (__int64)a2,
        updated,
        v20[0]);
LABEL_13:
    v13 = (void *)v10[2];
    if ( v13 )
    {
      LocalFree(v13);
      v10[2] = 0;
    }
    v14 = (void *)v10[3];
    if ( v14 )
    {
      LocalFree(v14);
      v10[3] = 0;
    }
    v15 = (void *)v10[4];
    if ( v15 )
    {
      LocalFree(v15);
      v10[4] = 0;
    }
    v16 = (void *)v10[8];
    if ( v16 )
    {
      LocalFree(v16);
      v10[8] = 0;
      v10[9] = 0;
    }
    v17 = (void *)v10[10];
    if ( v17 )
    {
      LocalFree(v17);
      v10[10] = 0;
      v10[11] = 0;
    }
    LocalFree(v10);
    goto LABEL_24;
  }
  if ( a1 )
  {
    v19 = hMem;
    if ( *((HLOCAL **)hMem + 1) != &hMem )
      __fastfail(3u);
    *v10 = (FILETIME)hMem;
    v10[1] = (FILETIME)&hMem;
    v19[1] = v10;
    hMem = v10;
  }
  v11 = 0;
  *a6 = v10;
LABEL_24:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x2Eu, &WPP_70b8577d707437755865c965214ce19a_Traceguids, v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180002380  push    rbx
0x180002382  push    rbp
0x180002383  push    rsi
0x180002384  push    rdi
0x180002385  push    r13
0x180002387  push    r14
0x180002389  push    r15
0x18000238b  sub     rsp, 40h
0x18000238f  mov     r15, r9
0x180002392  mov     dword ptr [rsp+78h+var_48], 0
0x18000239a  mov     rbp, r8
0x18000239d  mov     r14, rdx
0x1800023a0  mov     esi, ecx
0x1800023a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023a9  lea     r13, WPP_GLOBAL_Control
0x1800023b0  cmp     rcx, r13
0x1800023b3  jz      short loc_1800023D0
0x1800023b5  test    byte ptr [rcx+1Ch], 8
0x1800023b9  jz      short loc_1800023D0
0x1800023bb  mov     rcx, [rcx+10h]
0x1800023bf  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x1800023c6  mov     edx, 2Ch ; ','
0x1800023cb  call    WPP_SF_
0x1800023d0  mov     edx, 68h ; 'h'; uBytes
0x1800023d5  lea     ecx, [rdx-28h]; uFlags
0x1800023d8  call    cs:__imp_LocalAlloc
0x1800023df  nop     dword ptr [rax+rax+00h]
0x1800023e4  mov     rbx, rax
0x1800023e7  test    rax, rax
0x1800023ea  jnz     short loc_1800023F6
0x1800023ec  mov     edi, 0C0000017h
0x1800023f1  jmp     loc_18000252E
0x1800023f6  lea     rdx, [rax+10h]
0x1800023fa  mov     rcx, r14; SourceString
0x1800023fd  call    GmsapDuplicateStringStrict
0x180002402  mov     edi, eax
0x180002404  test    eax, eax
0x180002406  js      short loc_18000247E
0x180002408  lea     rdx, [rbx+18h]
0x18000240c  mov     rcx, rbp; SourceString
0x18000240f  call    GmsapDuplicateStringStrict
0x180002414  mov     edi, eax
0x180002416  test    eax, eax
0x180002418  js      short loc_18000247E
0x18000241a  lea     rdx, [rbx+20h]
0x18000241e  mov     rcx, r15; SourceString
0x180002421  call    GmsapDuplicateStringStrict
0x180002426  mov     edi, eax
0x180002428  test    eax, eax
0x18000242a  js      short loc_18000247E
0x18000242c  mov     rdx, [rsp+78h+arg_20]; struct _tagPasswordData *
0x180002434  lea     r8, [rsp+78h+var_48]; int *
0x180002439  mov     rcx, rbx; struct _tagGMsaListEntry *
0x18000243c  call    ?GmsapUpdateGMSAEntry@@YAJPEAU_tagGMsaListEntry@@PEAU_tagPasswordData@@PEAH@Z; GmsapUpdateGMSAEntry(_tagGMsaListEntry *,_tagPasswordData *,int *)
0x180002441  mov     edi, eax
0x180002443  test    eax, eax
0x180002445  jns     loc_18000256A
0x18000244b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002452  cmp     rcx, r13
0x180002455  jz      short loc_18000247E
0x180002457  test    byte ptr [rcx+1Ch], 4
0x18000245b  jz      short loc_18000247E
0x18000245d  mov     rcx, [rcx+10h]
0x180002461  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180002468  mov     [rsp+78h+var_50], eax
0x18000246c  mov     edx, 2Dh ; '-'
0x180002471  mov     r9, rbp
0x180002474  mov     [rsp+78h+var_58], r14
0x180002479  call    WPP_SF_SSD
0x18000247e  mov     rcx, [rbx+10h]; hMem
0x180002482  test    rcx, rcx
0x180002485  jz      short loc_18000249B
0x180002487  call    cs:__imp_LocalFree
0x18000248e  nop     dword ptr [rax+rax+00h]
0x180002493  mov     qword ptr [rbx+10h], 0
0x18000249b  mov     rcx, [rbx+18h]; hMem
0x18000249f  test    rcx, rcx
0x1800024a2  jz      short loc_1800024B8
0x1800024a4  call    cs:__imp_LocalFree
0x1800024ab  nop     dword ptr [rax+rax+00h]
0x1800024b0  mov     qword ptr [rbx+18h], 0
0x1800024b8  mov     rcx, [rbx+20h]; hMem
0x1800024bc  test    rcx, rcx
0x1800024bf  jz      short loc_1800024D5
0x1800024c1  call    cs:__imp_LocalFree
0x1800024c8  nop     dword ptr [rax+rax+00h]
0x1800024cd  mov     qword ptr [rbx+20h], 0
0x1800024d5  mov     rcx, [rbx+40h]; hMem
0x1800024d9  test    rcx, rcx
0x1800024dc  jz      short loc_1800024FA
0x1800024de  call    cs:__imp_LocalFree
0x1800024e5  nop     dword ptr [rax+rax+00h]
0x1800024ea  mov     qword ptr [rbx+40h], 0
0x1800024f2  mov     qword ptr [rbx+48h], 0
0x1800024fa  mov     rcx, [rbx+50h]; hMem
0x1800024fe  test    rcx, rcx
0x180002501  jz      short loc_18000251F
0x180002503  call    cs:__imp_LocalFree
0x18000250a  nop     dword ptr [rax+rax+00h]
0x18000250f  mov     qword ptr [rbx+50h], 0
0x180002517  mov     qword ptr [rbx+58h], 0
0x18000251f  mov     rcx, rbx; hMem
0x180002522  call    cs:__imp_LocalFree
0x180002529  nop     dword ptr [rax+rax+00h]
0x18000252e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002535  cmp     rcx, r13
0x180002538  jz      short loc_180002558
0x18000253a  test    byte ptr [rcx+1Ch], 8
0x18000253e  jz      short loc_180002558
0x180002540  mov     rcx, [rcx+10h]
0x180002544  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x18000254b  mov     edx, 2Eh ; '.'
0x180002550  mov     r9d, edi
0x180002553  call    WPP_SF_D
0x180002558  mov     eax, edi
0x18000255a  add     rsp, 40h
0x18000255e  pop     r15
0x180002560  pop     r14
0x180002562  pop     r13
0x180002564  pop     rdi
0x180002565  pop     rsi
0x180002566  pop     rbp
0x180002567  pop     rbx
0x180002568  retn
0x18000256a  test    esi, esi
0x18000256c  jz      short loc_18000259B
0x18000256e  mov     rax, cs:hMem
0x180002575  lea     rcx, hMem
0x18000257c  cmp     [rax+8], rcx
0x180002580  jz      short loc_180002589
0x180002582  mov     ecx, 3
0x180002587  int     29h; Win8: RtlFailFast(ecx)
0x180002589  mov     [rbx], rax
0x18000258c  mov     [rbx+8], rcx
0x180002590  mov     [rax+8], rbx
0x180002594  mov     cs:hMem, rbx
0x18000259b  mov     rax, [rsp+78h+arg_28]
0x1800025a3  xor     edi, edi
0x1800025a5  mov     [rax], rbx
0x1800025a8  jmp     short loc_18000252E
```
