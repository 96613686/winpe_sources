# CConnectionFolderExtractIcon::HrInitialize(CPConFoldPidl<ConFoldPidl_v3> const &)

- ea: `0x1800030e0`
- end: `0x18000329b`
- name: `?HrInitialize@CConnectionFolderExtractIcon@@QEAAJAEBV?$CPConFoldPidl@VConFoldPidl_v3@@@@@Z`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000a204`

## callees

- `0x180002df0`
- `0x1800030e0`
- `0x1800032b0`
- `0x180004920`
- `0x18001e1e0`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x18000319d`
- `SHELL32!__imp_ILClone` at `0x18000319d`
- `SHELL32!__imp_SHFree` at `0x180003190`
- `SHELL32!__imp_SHFree` at `0x1800031ef`
- `SHELL32!__imp_SHFree` at `0x1800031ff`
- `SHELL32!__imp_SHFree` at `0x180003212`
- `SHELL32!__imp_SHFree` at `0x180003222`
- `SHELL32!__imp_SHFree` at `0x180003235`
- `SHELL32!__imp_SHFree` at `0x180003248`
- `SHELL32!__imp_SHFree` at `0x18000325b`
- `SHELL32!__imp_SHFree` at `0x18000326e`
- `SHELL32!__imp_SHFree` at `0x180003190`
- `SHELL32!__imp_SHFree` at `0x1800031ef`
- `SHELL32!__imp_SHFree` at `0x1800031ff`
- `SHELL32!__imp_SHFree` at `0x180003212`
- `SHELL32!__imp_SHFree` at `0x180003222`
- `SHELL32!__imp_SHFree` at `0x180003235`
- `SHELL32!__imp_SHFree` at `0x180003248`
- `SHELL32!__imp_SHFree` at `0x18000325b`
- `SHELL32!__imp_SHFree` at `0x18000326e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000314c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000314c`
- `ole32!CoTaskMemFree` at `0x1800031cc`
- `ole32!CoTaskMemFree` at `0x1800031d6`
- `ole32!CoTaskMemFree` at `0x1800031df`
- `ole32!CoTaskMemFree` at `0x1800031cc`
- `ole32!CoTaskMemFree` at `0x1800031d6`
- `ole32!CoTaskMemFree` at `0x1800031df`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CConnectionFolderExtractIcon::HrInitialize(__int64 a1, LPCITEMIDLIST *a2)
{
  unsigned int v4; // edi
  void *v5; // rcx
  LPITEMIDLIST v6; // rax
  LPVOID *v7; // rbx
  int v9; // [rsp+20h] [rbp-C8h] BYREF
  _BYTE v10[64]; // [rsp+28h] [rbp-C0h] BYREF
  void *v11; // [rsp+68h] [rbp-80h]
  void *v12; // [rsp+70h] [rbp-78h]
  void *v13; // [rsp+78h] [rbp-70h]
  void *v14; // [rsp+80h] [rbp-68h]
  void *v15; // [rsp+90h] [rbp-58h]
  int v16; // [rsp+98h] [rbp-50h]
  __int128 v17; // [rsp+A0h] [rbp-48h]
  void *v18; // [rsp+B0h] [rbp-38h]
  LPVOID pv; // [rsp+B8h] [rbp-30h]
  DWORD TickCount; // [rsp+C0h] [rbp-28h]

  v9 = 0;
  v17 = 0;
  v18 = 0;
  v16 = 1;
  v11 = 0;
  v12 = 0;
  v14 = 0;
  v15 = 0;
  v13 = 0;
  CConFoldEntry::clear((CConFoldEntry *)v10);
  pv = 0;
  TickCount = GetTickCount();
  if ( (unsigned int)CConnectionList::HrFindConnectionByGuid(
                       (__int64 **)&g_ccl,
                       (const struct _GUID *)((char *)&(*a2)[9].mkid.cb + 1),
                       (struct ConnListEntry *)&v9) )
  {
    v5 = *(void **)(a1 + 72);
    if ( v5 )
    {
      SHFree(v5);
      *(_QWORD *)(a1 + 72) = 0;
    }
    v6 = ILClone(*a2);
    if ( v6 )
    {
      *(_DWORD *)((char *)&v6[1].mkid.cb + 1) = 3;
      *(_QWORD *)(a1 + 72) = v6;
      v4 = 0;
    }
    else
    {
      v4 = -2147024882;
    }
  }
  else
  {
    v4 = CConFoldEntry::ConvertToPidl(v10, a1 + 72);
  }
  v7 = (LPVOID *)pv;
  if ( pv )
  {
    CoTaskMemFree(*(LPVOID *)pv);
    CoTaskMemFree(v7[1]);
    CoTaskMemFree(v7);
  }
  if ( v11 )
    SHFree(v11);
  if ( v12 )
    SHFree(v12);
  if ( v15 )
    SHFree(v15);
  if ( v13 )
    SHFree(v13);
  if ( v14 )
    SHFree(v14);
  if ( v18 )
    SHFree(v18);
  if ( *((_QWORD *)&v17 + 1) )
    SHFree(*((void **)&v17 + 1));
  if ( (_QWORD)v17 )
    SHFree((void *)v17);
  return v4;
}

```

## disassembly

```asm
0x1800030e0  mov     r11, rsp
0x1800030e3  mov     [r11+18h], rbx
0x1800030e7  mov     [r11+20h], rsi
0x1800030eb  push    rdi
0x1800030ec  sub     rsp, 0E0h
0x1800030f3  mov     rax, cs:__security_cookie
0x1800030fa  xor     rax, rsp
0x1800030fd  mov     [rsp+0E8h+var_18], rax
0x180003105  mov     rdi, rdx
0x180003108  mov     rbx, rcx
0x18000310b  xor     esi, esi
0x18000310d  mov     [rsp+0E8h+var_C8], esi
0x180003111  xorps   xmm0, xmm0
0x180003114  movdqa  xmmword ptr [r11-48h], xmm0
0x18000311a  mov     [r11-38h], rsi
0x18000311e  mov     dword ptr [r11-50h], 1
0x180003126  mov     [r11-80h], rsi
0x18000312a  mov     [r11-78h], rsi
0x18000312e  mov     [r11-68h], rsi
0x180003132  mov     [r11-58h], rsi
0x180003136  mov     [r11-70h], rsi
0x18000313a  lea     rcx, [rsp+0E8h+var_C0]; this
0x18000313f  call    ?clear@CConFoldEntry@@QEAAXXZ; CConFoldEntry::clear(void)
0x180003144  mov     [rsp+0E8h+pv], rsi
0x18000314c  call    cs:__imp_GetTickCount
0x180003152  mov     [rsp+0E8h+var_28], eax
0x180003159  mov     rdx, [rdi]
0x18000315c  add     rdx, 1Ch; struct _GUID *
0x180003160  lea     r8, [rsp+0E8h+var_C8]; struct ConnListEntry *
0x180003165  lea     rcx, ?g_ccl@@3VCConnectionList@@A; this
0x18000316c  call    ?HrFindConnectionByGuid@CConnectionList@@QEAAJPEFBU_GUID@@AEAVConnListEntry@@@Z; CConnectionList::HrFindConnectionByGuid(_GUID const *,ConnListEntry &)
0x180003171  test    eax, eax
0x180003173  jnz     short loc_180003187
0x180003175  lea     rdx, [rbx+48h]
0x180003179  lea     rcx, [rsp+0E8h+var_C0]
0x18000317e  call    ?ConvertToPidl@CConFoldEntry@@QEBAJAEAV?$CPConFoldPidl@VConFoldPidl_v3@@@@@Z; CConFoldEntry::ConvertToPidl(CPConFoldPidl<ConFoldPidl_v3> &)
0x180003183  mov     edi, eax
0x180003185  jmp     short loc_1800031BC
0x180003187  mov     rcx, [rbx+48h]; pv
0x18000318b  test    rcx, rcx
0x18000318e  jz      short loc_18000319A
0x180003190  call    cs:__imp_SHFree
0x180003196  mov     [rbx+48h], rsi
0x18000319a  mov     rcx, [rdi]; pidl
0x18000319d  call    cs:__imp_ILClone
0x1800031a3  test    rax, rax
0x1800031a6  jnz     short loc_1800031AF
0x1800031a8  mov     edi, 8007000Eh
0x1800031ad  jmp     short loc_1800031BC
0x1800031af  mov     dword ptr [rax+4], 3
0x1800031b6  mov     [rbx+48h], rax
0x1800031ba  mov     edi, esi
0x1800031bc  mov     rbx, [rsp+0E8h+pv]
0x1800031c4  test    rbx, rbx
0x1800031c7  jz      short loc_1800031E5
0x1800031c9  mov     rcx, [rbx]; pv
0x1800031cc  call    cs:__imp_CoTaskMemFree
0x1800031d2  mov     rcx, [rbx+8]; pv
0x1800031d6  call    cs:__imp_CoTaskMemFree
0x1800031dc  mov     rcx, rbx; pv
0x1800031df  call    cs:__imp_CoTaskMemFree
0x1800031e5  mov     rcx, [rsp+0E8h+var_80]; pv
0x1800031ea  test    rcx, rcx
0x1800031ed  jz      short loc_1800031F5
0x1800031ef  call    cs:__imp_SHFree
0x1800031f5  mov     rcx, [rsp+0E8h+var_78]; pv
0x1800031fa  test    rcx, rcx
0x1800031fd  jz      short loc_180003205
0x1800031ff  call    cs:__imp_SHFree
0x180003205  mov     rcx, [rsp+0E8h+var_58]; pv
0x18000320d  test    rcx, rcx
0x180003210  jz      short loc_180003218
0x180003212  call    cs:__imp_SHFree
0x180003218  mov     rcx, [rsp+0E8h+var_70]; pv
0x18000321d  test    rcx, rcx
0x180003220  jz      short loc_180003228
0x180003222  call    cs:__imp_SHFree
0x180003228  mov     rcx, [rsp+0E8h+var_68]; pv
0x180003230  test    rcx, rcx
0x180003233  jz      short loc_18000323B
0x180003235  call    cs:__imp_SHFree
0x18000323b  mov     rcx, [rsp+0E8h+var_38]; pv
0x180003243  test    rcx, rcx
0x180003246  jz      short loc_18000324E
0x180003248  call    cs:__imp_SHFree
0x18000324e  mov     rcx, [rsp+0E8h+var_40]; pv
0x180003256  test    rcx, rcx
0x180003259  jz      short loc_180003261
0x18000325b  call    cs:__imp_SHFree
0x180003261  mov     rcx, [rsp+0E8h+var_48]; pv
0x180003269  test    rcx, rcx
0x18000326c  jz      short loc_180003274
0x18000326e  call    cs:__imp_SHFree
0x180003274  mov     eax, edi
0x180003276  mov     rcx, [rsp+0E8h+var_18]
0x18000327e  xor     rcx, rsp; StackCookie
0x180003281  call    __security_check_cookie
0x180003286  lea     r11, [rsp+0E8h+var_8]
0x18000328e  mov     rbx, [r11+20h]
0x180003292  mov     rsi, [r11+28h]
0x180003296  mov     rsp, r11
0x180003299  pop     rdi
0x18000329a  retn
```
