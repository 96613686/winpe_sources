# CMediaServerFolder::CompareIDs(__int64,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *)

- ea: `0x18001ede0`
- end: `0x18001ef27`
- name: `?CompareIDs@CMediaServerFolder@@UEAAJ_JPEFBU_ITEMIDLIST_RELATIVE@@1@Z`
- size: `327`
- prototype: `int(CMediaServerFolder *__hidden this, __int64, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180006790`
- `0x180011930`
- `0x180015bac`
- `0x180019b84`
- `0x18001ede0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001eeb7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ef06`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001eeb7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001ef06`
- `PROPSYS!PropVariantCompareEx` at `0x18001ee7a`
- `PROPSYS!PropVariantCompareEx` at `0x18001ee7a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMediaServerFolder::CompareIDs(
        CMediaServerFolder *this,
        __int64 a2,
        const struct _ITEMIDLIST_RELATIVE *a3,
        const struct _ITEMIDLIST_RELATIVE *a4)
{
  GUID fmtid; // xmm0
  DWORD pid; // eax
  CMediaServerFolder *v10; // rcx
  int PropertyWithFallback; // ebx
  int v12; // eax
  PROPVARIANT propvar2; // [rsp+20h] [rbp-58h] BYREF
  PROPVARIANT propvar1; // [rsp+38h] [rbp-40h] BYREF
  struct _tagpropertykey v16; // [rsp+50h] [rbp-28h] BYREF

  if ( (a2 & 0x10000000) != 0 )
  {
    fmtid = PKEY_ParsingName.fmtid;
    pid = PKEY_ParsingName.pid;
  }
  else
  {
    fmtid = PKEY_ItemNameDisplay.fmtid;
    pid = PKEY_ItemNameDisplay.pid;
  }
  v16.fmtid = fmtid;
  v16.pid = pid;
  propvar1.vt = 0;
  PropertyWithFallback = CMediaServerFolder::_GetPropertyWithFallback(this, a3, &v16, &propvar1);
  if ( PropertyWithFallback >= 0 )
  {
    propvar2.vt = 0;
    PropertyWithFallback = CMediaServerFolder::_GetPropertyWithFallback(v10, a4, &v16, &propvar2);
    if ( PropertyWithFallback >= 0 )
    {
      v12 = PropVariantCompareEx(&propvar1, &propvar2, PVCU_DEFAULT, 0);
      if ( v12 )
      {
        if ( v12 >= 0 )
          PropertyWithFallback = v12 > 0;
        else
          PropertyWithFallback = 0xFFFF;
      }
      else
      {
        PropertyWithFallback = CContentDirectoryFolder::CompareRelativeIDLists(
                                 (struct IShellFolder *)((unsigned __int64)this
                                                       & -(__int64)(this != (CMediaServerFolder *)16)),
                                 a3,
                                 a4,
                                 a2);
      }
    }
    PropVariantClear(&propvar2);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((PropertyWithFallback >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      &WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids,
      (unsigned int)PropertyWithFallback);
  }
  PropVariantClear(&propvar1);
  return (unsigned int)PropertyWithFallback;
}

```

## disassembly

```asm
0x18001ede0  push    rbp
0x18001ede2  push    rbx
0x18001ede3  push    rsi
0x18001ede4  push    rdi
0x18001ede5  push    r14
0x18001ede7  push    r15
0x18001ede9  mov     rbp, rsp
0x18001edec  sub     rsp, 78h
0x18001edf0  mov     rax, cs:__security_cookie
0x18001edf7  xor     rax, rsp
0x18001edfa  mov     [rbp+var_10], rax
0x18001edfe  mov     rdi, r9
0x18001ee01  mov     r15, r8
0x18001ee04  mov     r14, rdx
0x18001ee07  mov     rsi, rcx
0x18001ee0a  bt      rdx, 1Ch
0x18001ee0f  jnb     short loc_18001EE20
0x18001ee11  movups  xmm0, xmmword ptr cs:PKEY_ParsingName.fmtid.Data1
0x18001ee18  mov     eax, cs:PKEY_ParsingName.pid
0x18001ee1e  jmp     short loc_18001EE2D
0x18001ee20  movups  xmm0, xmmword ptr cs:PKEY_ItemNameDisplay.fmtid.Data1
0x18001ee27  mov     eax, cs:PKEY_ItemNameDisplay.pid
0x18001ee2d  movups  xmmword ptr [rbp+var_28.fmtid.Data1], xmm0
0x18001ee31  mov     [rbp+var_28.pid], eax
0x18001ee34  xor     eax, eax
0x18001ee36  mov     word ptr [rbp+propvar1], ax
0x18001ee3a  lea     r9, [rbp+propvar1]; struct tagPROPVARIANT *
0x18001ee3e  lea     r8, [rbp+var_28]; struct _tagpropertykey *
0x18001ee42  mov     rdx, r15; struct _ITEMID_CHILD *
0x18001ee45  call    ?_GetPropertyWithFallback@CMediaServerFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CMediaServerFolder::_GetPropertyWithFallback(_ITEMID_CHILD const *,_tagpropertykey const &,tagPROPVARIANT *)
0x18001ee4a  mov     ebx, eax
0x18001ee4c  test    eax, eax
0x18001ee4e  js      short loc_18001EEBD
0x18001ee50  xor     eax, eax
0x18001ee52  mov     word ptr [rbp+propvar2], ax
0x18001ee56  lea     r9, [rbp+propvar2]; struct tagPROPVARIANT *
0x18001ee5a  lea     r8, [rbp+var_28]; struct _tagpropertykey *
0x18001ee5e  mov     rdx, rdi; struct _ITEMID_CHILD *
0x18001ee61  call    ?_GetPropertyWithFallback@CMediaServerFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CMediaServerFolder::_GetPropertyWithFallback(_ITEMID_CHILD const *,_tagpropertykey const &,tagPROPVARIANT *)
0x18001ee66  mov     ebx, eax
0x18001ee68  test    eax, eax
0x18001ee6a  js      short loc_18001EEB3
0x18001ee6c  xor     r9d, r9d; flags
0x18001ee6f  xor     r8d, r8d; unit
0x18001ee72  lea     rdx, [rbp+propvar2]; propvar2
0x18001ee76  lea     rcx, [rbp+propvar1]; propvar1
0x18001ee7a  call    cs:__imp_PropVariantCompareEx
0x18001ee80  test    eax, eax
0x18001ee82  jnz     short loc_18001EEA3
0x18001ee84  lea     rax, [rsi-10h]
0x18001ee88  neg     rax
0x18001ee8b  sbb     rcx, rcx
0x18001ee8e  and     rcx, rsi; struct IShellFolder *
0x18001ee91  mov     r9, r14; __int64
0x18001ee94  mov     r8, rdi; struct _ITEMIDLIST_RELATIVE *
0x18001ee97  mov     rdx, r15; struct _ITEMIDLIST_RELATIVE *
0x18001ee9a  call    ?CompareRelativeIDLists@CContentDirectoryFolder@@SAJPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@1_J@Z; CContentDirectoryFolder::CompareRelativeIDLists(IShellFolder *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *,__int64)
0x18001ee9f  mov     ebx, eax
0x18001eea1  jmp     short loc_18001EEB3
0x18001eea3  jns     short loc_18001EEAC
0x18001eea5  mov     ebx, 0FFFFh
0x18001eeaa  jmp     short loc_18001EEB3
0x18001eeac  xor     ebx, ebx
0x18001eeae  test    eax, eax
0x18001eeb0  setnle  bl
0x18001eeb3  lea     rcx, [rbp+propvar2]; pvar
0x18001eeb7  call    cs:__imp_PropVariantClear
0x18001eebd  lea     rax, WPP_GLOBAL_Control
0x18001eec4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eecb  cmp     rcx, rax
0x18001eece  jz      short loc_18001EF02
0x18001eed0  test    byte ptr [rcx+1Ch], 2
0x18001eed4  jz      short loc_18001EF02
0x18001eed6  mov     edx, ebx
0x18001eed8  sar     edx, 1Fh
0x18001eedb  and     edx, 0FFFFFFFDh
0x18001eede  add     edx, 5
0x18001eee1  movzx   eax, byte ptr [rcx+19h]
0x18001eee5  cmp     eax, edx
0x18001eee7  jb      short loc_18001EF02
0x18001eee9  mov     edx, 13h
0x18001eeee  mov     r9d, ebx
0x18001eef1  lea     r8, WPP_6632fb49d9da3da9a4f7f4d7d56b782d_Traceguids
0x18001eef8  mov     rcx, [rcx+10h]
0x18001eefc  call    WPP_SF_d
0x18001ef01  nop
0x18001ef02  lea     rcx, [rbp+propvar1]; pvar
0x18001ef06  call    cs:__imp_PropVariantClear
0x18001ef0c  mov     eax, ebx
0x18001ef0e  mov     rcx, [rbp+var_10]
0x18001ef12  xor     rcx, rsp; StackCookie
0x18001ef15  call    __security_check_cookie
0x18001ef1a  add     rsp, 78h
0x18001ef1e  pop     r15
0x18001ef20  pop     r14
0x18001ef22  pop     rdi
0x18001ef23  pop     rsi
0x18001ef24  pop     rbx
0x18001ef25  pop     rbp
0x18001ef26  retn
```
