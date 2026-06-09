# MRxDAVQueryDirectoryFake

- ea: `0x140003698`
- end: `0x1400039aa`
- name: `MRxDAVQueryDirectoryFake`
- size: `786`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14001f6c0`

## callees

- `0x140001680`
- `0x1400017e4`
- `0x140001948`
- `0x140001978`
- `0x140002824`
- `0x140003698`
- `0x140006c00`
- `0x14001fc00`
- `0x140025a08`
- `0x140025aa0`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x140003713`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000379e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003713`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000379e`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000382f`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000382f`

## pseudocode

```c
__int64 __fastcall MRxDAVQueryDirectoryFake(__int64 a1, const UNICODE_STRING *a2)
{
  __int64 v2; // r13
  __int64 v3; // rbx
  __int64 v6; // rbp
  const UNICODE_STRING *v7; // rbp
  __int64 v8; // r14
  __int64 v9; // rbx
  HANDLE CurrentThreadId; // rax
  unsigned int v11; // edi
  int v12; // esi
  __int64 v13; // rbx
  HANDLE v14; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  void *v18; // rsi
  size_t v19; // rbp
  unsigned int v20; // eax
  _QWORD v21[17]; // [rsp+30h] [rbp-88h] BYREF
  int v22; // [rsp+C0h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  v3 = *(_QWORD *)(a1 + 64);
  v22 = 0;
  memset(v21, 0, 0x40u);
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL);
  if ( v6 )
    v7 = *(const UNICODE_STRING **)(v6 + 40);
  else
    v7 = 0;
  v8 = 0;
  if ( v3 )
    v8 = *(_QWORD *)(v3 + 56);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    CurrentThreadId = PsGetCurrentThreadId();
    WPP_SF_qq(v9, 14, WPP_609949de13fe38daba556366630c430b_Traceguids, CurrentThreadId, a1);
  }
  if ( *(_BYTE *)(a1 + 520) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 15, WPP_609949de13fe38daba556366630c430b_Traceguids);
    }
    goto LABEL_13;
  }
  if ( !v7[7].Length || !v7[7].Buffer )
  {
LABEL_13:
    v11 = -1073741823;
    v12 = -1073741823;
    goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
  {
    WPP_SF_ZZ(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      16,
      (unsigned int)WPP_609949de13fe38daba556366630c430b_Traceguids,
      (_DWORD)a2,
      (__int64)&v7[7]);
  }
  if ( a2->Length >= v7[7].Length || !RtlPrefixUnicodeString(a2, v7 + 7, 1u) )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
    {
      goto LABEL_13;
    }
    v17 = 17;
LABEL_29:
    WPP_SF_(v16[3], v17, WPP_609949de13fe38daba556366630c430b_Traceguids);
    goto LABEL_13;
  }
  if ( (unsigned __int8)MRxDAVIsFileNotFoundCachedWithName(&v7[7], *(_QWORD *)(v2 + 120)) )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
    {
      goto LABEL_13;
    }
    v17 = 18;
    goto LABEL_29;
  }
  if ( !(unsigned __int8)MRxDAVIsFileInfoCacheFound(a1, v21, &v22, &v7[7]) )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || !_bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
    {
      goto LABEL_13;
    }
    v17 = 21;
    goto LABEL_29;
  }
  v18 = *(void **)(a1 + 456);
  v19 = *(unsigned int *)(a1 + 472);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 19, WPP_609949de13fe38daba556366630c430b_Traceguids);
  }
  memset(v18, 0, v19);
  v20 = MRxDAVQueryDirectoryFromCache(a1, (__int64)v18, (__int64)v21, &v21[5]);
  v12 = v20;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)WPP_GLOBAL_Control + 11, 0xEu) )
  {
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 3), 20, WPP_609949de13fe38daba556366630c430b_Traceguids, v20);
  }
  if ( v12 >= 0 )
  {
    *(_DWORD *)(v8 + 8) = 1;
    *(_DWORD *)(v8 + 12) = 1;
  }
  v11 = v12;
LABEL_14:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
  {
    v13 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v14 = PsGetCurrentThreadId();
    WPP_SF_qD(v13, 22, WPP_609949de13fe38daba556366630c430b_Traceguids, v14, v12);
  }
  return v11;
}

```

## disassembly

```asm
0x140003698  mov     rax, rsp
0x14000369b  push    rbx
0x14000369c  push    rbp
0x14000369d  push    rsi
0x14000369e  push    rdi
0x14000369f  push    r12
0x1400036a1  push    r13
0x1400036a3  push    r14
0x1400036a5  push    r15
0x1400036a7  sub     rsp, 78h
0x1400036ab  mov     r13, [rcx+38h]
0x1400036af  xor     r12d, r12d
0x1400036b2  mov     rbx, [rcx+40h]
0x1400036b6  mov     r15, rdx
0x1400036b9  mov     rdi, rcx
0x1400036bc  mov     [rax+8], r12d
0x1400036c0  xor     edx, edx; Val
0x1400036c2  lea     rcx, [rsp+0B8h+var_88]; void *
0x1400036c7  lea     r8d, [r12+40h]; Size
0x1400036cc  call    memset
0x1400036d1  mov     rax, [rdi+48h]
0x1400036d5  mov     rbp, [rax+28h]
0x1400036d9  test    rbp, rbp
0x1400036dc  jnz     short loc_1400036E3
0x1400036de  mov     ebp, r12d
0x1400036e1  jmp     short loc_1400036E7
0x1400036e3  mov     rbp, [rbp+28h]
0x1400036e7  mov     r14, r12
0x1400036ea  test    rbx, rbx
0x1400036ed  jz      short loc_1400036F3
0x1400036ef  mov     r14, [rbx+38h]
0x1400036f3  mov     rbx, cs:WPP_GLOBAL_Control
0x1400036fa  lea     rax, WPP_GLOBAL_Control
0x140003701  cmp     rbx, rax
0x140003704  jz      short loc_140003742
0x140003706  test    dword ptr [rbx+2Ch], 2000h
0x14000370d  jz      short loc_14000373B
0x14000370f  mov     rbx, [rbx+18h]
0x140003713  call    cs:__imp_PsGetCurrentThreadId
0x14000371a  nop     dword ptr [rax+rax+00h]
0x14000371f  mov     edx, 0Eh
0x140003724  mov     [rsp+0B8h+var_98], rdi
0x140003729  mov     r9, rax
0x14000372c  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x140003733  mov     rcx, rbx
0x140003736  call    WPP_SF_qq
0x14000373b  lea     rax, WPP_GLOBAL_Control
0x140003742  cmp     [rdi+208h], r12b
0x140003749  jz      loc_1400037D9
0x14000374f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003756  cmp     rcx, rax
0x140003759  jz      short loc_140003777
0x14000375b  bt      dword ptr [rcx+2Ch], 0Eh
0x140003760  jnb     short loc_140003777
0x140003762  mov     rcx, [rcx+18h]
0x140003766  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14000376d  mov     edx, 0Fh
0x140003772  call    WPP_SF_
0x140003777  lea     r15, WPP_GLOBAL_Control
0x14000377e  mov     edi, 0C0000001h
0x140003783  mov     esi, edi
0x140003785  mov     rbx, cs:WPP_GLOBAL_Control
0x14000378c  cmp     rbx, r15
0x14000378f  jz      short loc_1400037C5
0x140003791  test    dword ptr [rbx+2Ch], 2000h
0x140003798  jz      short loc_1400037C5
0x14000379a  mov     rbx, [rbx+18h]
0x14000379e  call    cs:__imp_PsGetCurrentThreadId
0x1400037a5  nop     dword ptr [rax+rax+00h]
0x1400037aa  mov     edx, 16h
0x1400037af  mov     dword ptr [rsp+0B8h+var_98], esi
0x1400037b3  mov     r9, rax
0x1400037b6  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x1400037bd  mov     rcx, rbx
0x1400037c0  call    WPP_SF_qD
0x1400037c5  mov     eax, edi
0x1400037c7  add     rsp, 78h
0x1400037cb  pop     r15
0x1400037cd  pop     r14
0x1400037cf  pop     r13
0x1400037d1  pop     r12
0x1400037d3  pop     rdi
0x1400037d4  pop     rsi
0x1400037d5  pop     rbp
0x1400037d6  pop     rbx
0x1400037d7  retn
0x1400037d9  lea     rsi, [rbp+70h]
0x1400037dd  cmp     [rsi], r12w
0x1400037e1  jz      short loc_140003777
0x1400037e3  cmp     [rbp+78h], r12
0x1400037e7  jz      short loc_140003777
0x1400037e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400037f0  cmp     rcx, rax
0x1400037f3  jz      short loc_140003819
0x1400037f5  bt      dword ptr [rcx+2Ch], 0Eh
0x1400037fa  jnb     short loc_140003819
0x1400037fc  mov     rcx, [rcx+18h]
0x140003800  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x140003807  mov     edx, 10h
0x14000380c  mov     [rsp+0B8h+var_98], rsi
0x140003811  mov     r9, r15
0x140003814  call    WPP_SF_ZZ
0x140003819  movzx   eax, word ptr [rsi]
0x14000381c  cmp     [r15], ax
0x140003820  jnb     loc_14000397E
0x140003826  mov     r8b, 1; CaseInSensitive
0x140003829  mov     rdx, rsi; String2
0x14000382c  mov     rcx, r15; String1
0x14000382f  call    cs:__imp_RtlPrefixUnicodeString
0x140003836  nop     dword ptr [rax+rax+00h]
0x14000383b  test    al, al
0x14000383d  jz      loc_14000397E
0x140003843  mov     rdx, [r13+78h]
0x140003847  mov     rcx, rsi
0x14000384a  call    MRxDAVIsFileNotFoundCachedWithName
0x14000384f  test    al, al
0x140003851  jz      short loc_14000388F
0x140003853  mov     rcx, cs:WPP_GLOBAL_Control
0x14000385a  lea     r15, WPP_GLOBAL_Control
0x140003861  cmp     rcx, r15
0x140003864  jz      loc_14000377E
0x14000386a  bt      dword ptr [rcx+2Ch], 0Eh
0x14000386f  jnb     loc_14000377E
0x140003875  mov     edx, 12h
0x14000387a  mov     rcx, [rcx+18h]
0x14000387e  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x140003885  call    WPP_SF_
0x14000388a  jmp     loc_14000377E
0x14000388f  mov     r9, rsi
0x140003892  lea     r8, [rsp+0B8h+arg_0]
0x14000389a  lea     rdx, [rsp+0B8h+var_88]
0x14000389f  mov     rcx, rdi
0x1400038a2  call    MRxDAVIsFileInfoCacheFound
0x1400038a7  test    al, al
0x1400038a9  jz      loc_140003952
0x1400038af  mov     rsi, [rdi+1C8h]
0x1400038b6  mov     ebp, [rdi+1D8h]
0x1400038bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400038c3  lea     r15, WPP_GLOBAL_Control
0x1400038ca  cmp     rcx, r15
0x1400038cd  jz      short loc_1400038EB
0x1400038cf  bt      dword ptr [rcx+2Ch], 0Eh
0x1400038d4  jnb     short loc_1400038EB
0x1400038d6  mov     rcx, [rcx+18h]
0x1400038da  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x1400038e1  mov     edx, 13h
0x1400038e6  call    WPP_SF_
0x1400038eb  mov     r8, rbp; Size
0x1400038ee  xor     edx, edx; Val
0x1400038f0  mov     rcx, rsi; void *
0x1400038f3  call    memset
0x1400038f8  lea     r9, [rsp+0B8h+var_60]
0x1400038fd  mov     rdx, rsi
0x140003900  lea     r8, [rsp+0B8h+var_88]
0x140003905  mov     rcx, rdi
0x140003908  call    MRxDAVQueryDirectoryFromCache
0x14000390d  mov     esi, eax
0x14000390f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003916  cmp     rcx, r15
0x140003919  jz      short loc_14000393A
0x14000391b  bt      dword ptr [rcx+2Ch], 0Eh
0x140003920  jnb     short loc_14000393A
0x140003922  mov     rcx, [rcx+18h]
0x140003926  lea     r8, WPP_609949de13fe38daba556366630c430b_Traceguids
0x14000392d  mov     edx, 14h
0x140003932  mov     r9d, eax
0x140003935  call    WPP_SF_L
0x14000393a  test    esi, esi
0x14000393c  js      short loc_14000394B
0x14000393e  mov     eax, 1
0x140003943  mov     [r14+8], eax
0x140003947  mov     [r14+0Ch], eax
0x14000394b  mov     edi, esi
0x14000394d  jmp     loc_140003785
0x140003952  mov     rcx, cs:WPP_GLOBAL_Control
0x140003959  lea     r15, WPP_GLOBAL_Control
0x140003960  cmp     rcx, r15
0x140003963  jz      loc_14000377E
0x140003969  bt      dword ptr [rcx+2Ch], 0Eh
0x14000396e  jnb     loc_14000377E
0x140003974  mov     edx, 15h
0x140003979  jmp     loc_14000387A
0x14000397e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003985  lea     r15, WPP_GLOBAL_Control
0x14000398c  cmp     rcx, r15
0x14000398f  jz      loc_14000377E
0x140003995  bt      dword ptr [rcx+2Ch], 0Eh
0x14000399a  jnb     loc_14000377E
0x1400039a0  mov     edx, 11h
0x1400039a5  jmp     loc_14000387A
```
