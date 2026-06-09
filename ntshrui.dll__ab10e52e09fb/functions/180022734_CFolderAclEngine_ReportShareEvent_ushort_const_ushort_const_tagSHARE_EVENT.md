# CFolderAclEngine::_ReportShareEvent(ushort const *,ushort const *,_tagSHARE_EVENT)

- ea: `0x180022734`
- end: `0x1800228a7`
- name: `?_ReportShareEvent@CFolderAclEngine@@IEAAXPEBG0W4_tagSHARE_EVENT@@@Z`
- size: `371`
- prototype: `void __high(const unsigned __int16 *, const unsigned __int16 *, enum _tagSHARE_EVENT)`
- caller_count: `7`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180010a84`
- `0x180012160`
- `0x18005a044`
- `0x18005c1d0`
- `0x18005c398`
- `0x18005c994`
- `0x18005d3c0`

## callees

- `0x180022734`
- `0x180057228`
- `0x18005e108`
- `0x180078010`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x180022874`
- `SHELL32!SHChangeNotify` at `0x180022874`
- `SHELL32!SHGetIDListFromObject` at `0x180022852`
- `SHELL32!SHGetIDListFromObject` at `0x180022852`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800227a7`
- `SHELL32!SHCreateItemFromParsingName` at `0x18002281a`
- `SHELL32!SHCreateItemFromParsingName` at `0x1800227a7`
- `SHELL32!SHCreateItemFromParsingName` at `0x18002281a`
- `SHELL32!__imp_ILFree` at `0x18002287e`
- `SHELL32!__imp_ILFree` at `0x18002287e`

## pseudocode

```c
int __fastcall CFolderAclEngine::_ReportShareEvent(__int64 a1, const WCHAR *a2, const WCHAR *a3, unsigned int a4)
{
  _UNKNOWN **v8; // rax
  unsigned int v9; // eax
  __int64 v10; // r9
  __int64 v11; // r8
  int v12; // ebx
  LONG v13; // ecx
  IUnknown *punk; // [rsp+30h] [rbp-10h] BYREF
  void *ppv; // [rsp+60h] [rbp+20h] BYREF
  int v17; // [rsp+78h] [rbp+38h] BYREF

  v8 = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    LODWORD(v8) = WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, (_DWORD)a3, (_DWORD)a2, (__int64)a3, a4);
  if ( *(_QWORD *)(a1 + 8) )
  {
    ppv = 0;
    LODWORD(v8) = SHCreateItemFromParsingName(a2, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    if ( (int)v8 >= 0 )
    {
      v9 = ItemTypeFromShellItem((struct IShellItem *)ppv);
      v10 = 3;
      if ( v9 == 3 )
      {
        v11 = 0;
      }
      else
      {
        v11 = *(_QWORD *)(a1 + 16);
        v10 = v9;
      }
      (*(void (__fastcall **)(_QWORD, void *, __int64, __int64, unsigned int))(**(_QWORD **)(a1 + 8) + 32LL))(
        *(_QWORD *)(a1 + 8),
        ppv,
        v11,
        v10,
        a4);
      LODWORD(v8) = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  punk = 0;
  if ( a4 <= 1 )
  {
    LODWORD(v8) = SHCreateItemFromParsingName(a3, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)&punk);
    if ( (int)v8 >= 0 )
    {
      v17 = 0x20000000;
      v12 = ((__int64 (__fastcall *)(IUnknown *, __int64, int *))punk->lpVtbl[2].QueryInterface)(punk, 0x20000000, &v17);
      ppv = 0;
      if ( SHGetIDListFromObject(punk, (LPITEMIDLIST *)&ppv) >= 0 )
      {
        v13 = 4096;
        if ( v12 )
          v13 = 0x2000;
        SHChangeNotify(v13, 0, ppv, 0);
        ILFree((LPITEMIDLIST)ppv);
      }
      LODWORD(v8) = ((__int64 (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
    }
  }
  return (int)v8;
}

```

## disassembly

```asm
0x180022734  mov     [rsp-18h+arg_8], rbx
0x180022739  mov     [rsp-18h+arg_10], rsi
0x18002273e  push    rbp
0x18002273f  push    rdi
0x180022740  push    r14
0x180022742  mov     rbp, rsp
0x180022745  sub     rsp, 40h
0x180022749  mov     ebx, r9d
0x18002274c  mov     r14, r8
0x18002274f  mov     rsi, rdx
0x180022752  mov     rdi, rcx
0x180022755  mov     rcx, cs:WPP_GLOBAL_Control
0x18002275c  lea     rax, WPP_GLOBAL_Control
0x180022763  cmp     rcx, rax
0x180022766  jz      short loc_180022788
0x180022768  test    byte ptr [rcx+1Ch], 8
0x18002276c  jz      short loc_180022788
0x18002276e  mov     rcx, [rcx+10h]
0x180022772  mov     edx, 0Ch
0x180022777  mov     [rsp+40h+var_18], ebx
0x18002277b  mov     r9, rsi
0x18002277e  mov     [rsp+40h+var_20], r8
0x180022783  call    WPP_SF_SSd
0x180022788  cmp     qword ptr [rdi+8], 0
0x18002278d  jz      short loc_1800227F9
0x18002278f  lea     r9, [rbp+ppv]; ppv
0x180022793  mov     [rbp+ppv], 0
0x18002279b  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800227a2  xor     edx, edx; pbc
0x1800227a4  mov     rcx, rsi; pszPath
0x1800227a7  call    cs:__imp_SHCreateItemFromParsingName
0x1800227ad  test    eax, eax
0x1800227af  js      short loc_1800227F9
0x1800227b1  mov     rcx, [rbp+ppv]
0x1800227b5  call    ?ItemTypeFromShellItem@@YA?AW4_SHARE_ITEM_TYPE@@PEAUIShellItem@@@Z; ItemTypeFromShellItem(IShellItem *)
0x1800227ba  mov     rcx, [rdi+8]
0x1800227be  mov     r9d, 3
0x1800227c4  mov     rdx, [rbp+ppv]
0x1800227c8  mov     dword ptr [rsp+40h+var_20], ebx
0x1800227cc  mov     r10, [rcx]
0x1800227cf  cmp     eax, r9d
0x1800227d2  jz      short loc_1800227DD
0x1800227d4  mov     r8, [rdi+10h]
0x1800227d8  mov     r9d, eax
0x1800227db  jmp     short loc_1800227E0
0x1800227dd  xor     r8d, r8d
0x1800227e0  mov     rax, [r10+20h]
0x1800227e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227e9  mov     rcx, [rbp+ppv]
0x1800227ed  mov     rax, [rcx]
0x1800227f0  mov     rax, [rax+10h]
0x1800227f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227f9  mov     [rbp+punk], 0
0x180022801  cmp     ebx, 1
0x180022804  ja      loc_180022894
0x18002280a  lea     r9, [rbp+punk]; ppv
0x18002280e  xor     edx, edx; pbc
0x180022810  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180022817  mov     rcx, r14; pszPath
0x18002281a  call    cs:__imp_SHCreateItemFromParsingName
0x180022820  test    eax, eax
0x180022822  js      short loc_180022894
0x180022824  mov     rcx, [rbp+punk]
0x180022828  lea     r8, [rbp+arg_18]
0x18002282c  mov     edx, 20000000h
0x180022831  mov     [rbp+arg_18], edx
0x180022834  mov     rax, [rcx]
0x180022837  mov     rax, [rax+30h]
0x18002283b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022840  mov     rcx, [rbp+punk]; punk
0x180022844  lea     rdx, [rbp+ppv]; ppidl
0x180022848  mov     ebx, eax
0x18002284a  mov     [rbp+ppv], 0
0x180022852  call    cs:__imp_SHGetIDListFromObject
0x180022858  test    eax, eax
0x18002285a  js      short loc_180022884
0x18002285c  mov     r8, [rbp+ppv]; dwItem1
0x180022860  mov     ecx, 1000h
0x180022865  mov     eax, 2000h
0x18002286a  test    ebx, ebx
0x18002286c  cmovnz  ecx, eax; wEventId
0x18002286f  xor     r9d, r9d; dwItem2
0x180022872  xor     edx, edx; uFlags
0x180022874  call    cs:__imp_SHChangeNotify
0x18002287a  mov     rcx, [rbp+ppv]; pidl
0x18002287e  call    cs:__imp_ILFree
0x180022884  mov     rcx, [rbp+punk]
0x180022888  mov     rax, [rcx]
0x18002288b  mov     rax, [rax+10h]
0x18002288f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022894  mov     rbx, [rsp+40h+arg_8]
0x180022899  mov     rsi, [rsp+40h+arg_10]
0x18002289e  add     rsp, 40h
0x1800228a2  pop     r14
0x1800228a4  pop     rdi
0x1800228a5  pop     rbp
0x1800228a6  retn
```
