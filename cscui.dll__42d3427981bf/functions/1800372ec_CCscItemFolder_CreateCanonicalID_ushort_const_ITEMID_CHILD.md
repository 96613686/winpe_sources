# CCscItemFolder::CreateCanonicalID(ushort const *,_ITEMID_CHILD * *)

- ea: `0x1800372ec`
- end: `0x1800373df`
- name: `?CreateCanonicalID@CCscItemFolder@@QEAAJPEBGPEAPEAU_ITEMID_CHILD@@@Z`
- size: `243`
- prototype: `__int64 __fastcall(CCscItemFolder *this, const unsigned __int16 *FileNameW, struct _ITEMID_CHILD **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800470f8`

## callees

- `0x1800372ec`
- `0x180037c80`
- `0x18003a47c`
- `0x18004d010`

## import_xrefs

- `SHLWAPI!PathIsUNCServerW` at `0x180037337`
- `SHLWAPI!PathIsUNCServerW` at `0x180037337`
- `SHLWAPI!PathFindFileNameW` at `0x180037351`
- `SHLWAPI!PathFindFileNameW` at `0x180037351`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800373b2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800373b2`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180037324`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180037324`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCscItemFolder::CreateCanonicalID(
        CCscItemFolder *this,
        const unsigned __int16 *FileNameW,
        struct _ITEMID_CHILD **a3)
{
  int inited; // ebx
  __int64 v7; // r9
  struct tagPROPVARIANT pvar; // [rsp+20h] [rbp-40h] BYREF
  _OWORD v10[2]; // [rsp+38h] [rbp-28h] BYREF
  void *ppv; // [rsp+90h] [rbp+30h] BYREF

  *a3 = 0;
  ppv = 0;
  inited = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  if ( inited >= 0 )
  {
    memset(&pvar, 0, sizeof(pvar));
    if ( !PathIsUNCServerW(FileNameW) )
      FileNameW = PathFindFileNameW(FileNameW);
    inited = InitPropVariantFromString(FileNameW, &pvar);
    if ( inited >= 0 )
    {
      inited = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, struct tagPROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                 ppv,
                 &PKEY_ItemNameDisplay,
                 &pvar);
      if ( inited >= 0 )
      {
        v7 = *((_QWORD *)this + 10);
        memset(v10, 0, 28);
        inited = CItemIDFactory<tagCSCITEMDATA,86514056>::s_CreateItemID(
                   v10,
                   (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))ppv,
                   (__int64 *)a3,
                   v7);
      }
      PropVariantClear((PROPVARIANT *)&pvar);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800372ec  mov     [rsp-18h+arg_0], rbx
0x1800372f1  mov     [rsp-18h+arg_8], rsi
0x1800372f6  push    rbp
0x1800372f7  push    rdi
0x1800372f8  push    r14
0x1800372fa  mov     rbp, rsp
0x1800372fd  sub     rsp, 60h
0x180037301  mov     rdi, rdx
0x180037304  mov     qword ptr [r8], 0
0x18003730b  mov     r14, rcx
0x18003730e  mov     [rbp+ppv], 0
0x180037316  lea     rdx, [rbp+ppv]; ppv
0x18003731a  mov     rsi, r8
0x18003731d  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180037324  call    cs:__imp_PSCreateMemoryPropertyStore
0x18003732a  mov     ebx, eax
0x18003732c  test    eax, eax
0x18003732e  js      loc_1800373C8
0x180037334  mov     rcx, rdi; pszPath
0x180037337  call    cs:__imp_PathIsUNCServerW
0x18003733d  xor     ecx, ecx
0x18003733f  xorps   xmm0, xmm0
0x180037342  mov     [rbp+var_30], rcx
0x180037346  movups  xmmword ptr [rbp+pvar], xmm0
0x18003734a  test    eax, eax
0x18003734c  jnz     short loc_18003735A
0x18003734e  mov     rcx, rdi; pszPath
0x180037351  call    cs:__imp_PathFindFileNameW
0x180037357  mov     rdi, rax
0x18003735a  lea     rdx, [rbp+pvar]; struct tagPROPVARIANT *
0x18003735e  mov     rcx, rdi; Source
0x180037361  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x180037366  mov     ebx, eax
0x180037368  test    eax, eax
0x18003736a  js      short loc_1800373B8
0x18003736c  mov     rcx, [rbp+ppv]
0x180037370  lea     r8, [rbp+pvar]
0x180037374  lea     rdx, PKEY_ItemNameDisplay
0x18003737b  mov     rax, [rcx]
0x18003737e  mov     rax, [rax+30h]
0x180037382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037387  mov     ebx, eax
0x180037389  test    eax, eax
0x18003738b  js      short loc_1800373AE
0x18003738d  mov     r9, [r14+50h]
0x180037391  lea     rcx, [rbp+var_28]
0x180037395  mov     rdx, [rbp+ppv]
0x180037399  xorps   xmm0, xmm0
0x18003739c  movups  xmmword ptr [rbp+var_28], xmm0
0x1800373a0  mov     r8, rsi
0x1800373a3  movups  xmmword ptr [rbp+var_28+0Ch], xmm0
0x1800373a7  call    ?s_CreateItemID@?$CItemIDFactory@UtagCSCITEMDATA@@$0FCIBJII@@@SAJPEFBUtagCSCITEMDATA@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@PEAUIMalloc@@@Z; CItemIDFactory<tagCSCITEMDATA,86514056>::s_CreateItemID(tagCSCITEMDATA const *,IPropertyStore *,_ITEMID_CHILD * *,IMalloc *)
0x1800373ac  mov     ebx, eax
0x1800373ae  lea     rcx, [rbp+pvar]; pvar
0x1800373b2  call    cs:__imp_PropVariantClear
0x1800373b8  mov     rcx, [rbp+ppv]
0x1800373bc  mov     rax, [rcx]
0x1800373bf  mov     rax, [rax+10h]
0x1800373c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373c8  lea     r11, [rsp+60h+var_s0]
0x1800373cd  mov     eax, ebx
0x1800373cf  mov     rbx, [r11+20h]
0x1800373d3  mov     rsi, [r11+28h]
0x1800373d7  mov     rsp, r11
0x1800373da  pop     r14
0x1800373dc  pop     rdi
0x1800373dd  pop     rbp
0x1800373de  retn
```
