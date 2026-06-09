# CPNPPropertyStore::SetValue(_tagpropertykey const &,tagPROPVARIANT const &)

- ea: `0x180019260`
- end: `0x180019447`
- name: `?SetValue@CPNPPropertyStore@@UEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z`
- size: `487`
- prototype: `__int64 __fastcall(CPNPPropertyStore *__hidden this, const struct _tagpropertykey *, PROPVARIANT *pvarSrc)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800091a8`
- `0x180019260`
- `0x180019450`
- `0x18002e600`
- `0x1800598d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800193a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800193a9`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180019323`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800193e5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180019323`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800193e5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800193d9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800193d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001929e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001929e`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180019281`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180019281`
- `RDPBASE!PAL_System_CritSecLeave` at `0x1800193bd`
- `RDPBASE!PAL_System_CritSecLeave` at `0x1800193bd`

## string_xrefs

- `0x180019353`: `PropVariantCopy failed`
- `0x180019415`: `PropVariantCopy failed`

## pseudocode

```c
__int64 __fastcall CPNPPropertyStore::SetValue(
        CPNPPropertyStore *this,
        const struct _tagpropertykey *a2,
        PROPVARIANT *pvarSrc)
{
  _QWORD *v3; // rsi
  struct tagPROP_ENTRY *Internal; // rax
  GUID *v8; // rax
  GUID *v9; // rdi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HRESULT v11; // ebx
  unsigned int v12; // eax
  GUID **v13; // rax
  PROPVARIANT *v15; // rbx
  unsigned int v16; // eax

  v3 = (_QWORD *)((char *)this + 56);
  if ( *((_DWORD *)this + 16) )
    PAL_System_CritSecEnter(*v3, a2, pvarSrc);
  Internal = CPNPPropertyStore::FindInternal(this, a2);
  if ( !Internal )
  {
    v8 = (GUID *)CoTaskMemAlloc(0x40u);
    v9 = v8;
    if ( !v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_01f1986460e93c8fc234b92505f16052_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"PROP_ENTRY");
      }
      v11 = -2147024882;
      goto LABEL_19;
    }
    v8[1] = a2->fmtid;
    v8[2].Data1 = a2->pid;
    *(_OWORD *)v8[2].Data4 = 0;
    *(_QWORD *)v8[3].Data4 = 0;
    v11 = PropVariantCopy((PROPVARIANT *)v8[2].Data4, pvarSrc);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          (unsigned int)WPP_01f1986460e93c8fc234b92505f16052_Traceguids,
          v12,
          (__int64)"PropVariantCopy failed",
          v11);
      }
      goto LABEL_18;
    }
    v13 = (GUID **)*((_QWORD *)this + 11);
    *(_QWORD *)&v9->Data1 = (char *)this + 80;
    *(_QWORD *)v9->Data4 = v13;
    *v13 = v9;
    ++*((_DWORD *)this + 18);
    *((_QWORD *)this + 11) = v9;
LABEL_16:
    if ( !v11 || !v9 )
      goto LABEL_19;
LABEL_18:
    CoTaskMemFree(v9);
    goto LABEL_19;
  }
  v15 = (PROPVARIANT *)((char *)Internal + 40);
  v9 = 0;
  PropVariantClear((PROPVARIANT *)Internal + 5);
  v11 = PropVariantCopy(v15, pvarSrc);
  if ( v11 >= 0 )
    goto LABEL_16;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      (unsigned int)WPP_01f1986460e93c8fc234b92505f16052_Traceguids,
      v16,
      (__int64)"PropVariantCopy failed",
      v11);
  }
LABEL_19:
  if ( v3 && *((_DWORD *)v3 + 2) )
    PAL_System_CritSecLeave(*v3);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180019260  push    rbx
0x180019262  push    rbp
0x180019263  push    rsi
0x180019264  push    rdi
0x180019265  push    r14
0x180019267  sub     rsp, 30h
0x18001926b  lea     rsi, [rcx+38h]
0x18001926f  mov     r14, r8
0x180019272  cmp     dword ptr [rsi+8], 0
0x180019276  mov     rbx, rdx
0x180019279  mov     rbp, rcx
0x18001927c  jz      short loc_180019287
0x18001927e  mov     rcx, [rsi]
0x180019281  call    cs:__imp_PAL_System_CritSecEnter
0x180019287  mov     rdx, rbx; struct _tagpropertykey *
0x18001928a  mov     rcx, rbp; this
0x18001928d  call    ?FindInternal@CPNPPropertyStore@@AEAAPEAUtagPROP_ENTRY@@AEBU_tagpropertykey@@@Z; CPNPPropertyStore::FindInternal(_tagpropertykey const &)
0x180019292  test    rax, rax
0x180019295  jnz     loc_1800193D0
0x18001929b  lea     ecx, [rax+40h]; cb
0x18001929e  call    cs:__imp_CoTaskMemAlloc
0x1800192a4  mov     rdi, rax
0x1800192a7  test    rax, rax
0x1800192aa  jnz     short loc_180019303
0x1800192ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192b3  lea     rax, WPP_GLOBAL_Control
0x1800192ba  cmp     rcx, rax
0x1800192bd  jz      short loc_1800192F9
0x1800192bf  test    byte ptr [rcx+1Ch], 8
0x1800192c3  jz      short loc_1800192F9
0x1800192c5  cmp     byte ptr [rcx+19h], 2
0x1800192c9  jb      short loc_1800192F9
0x1800192cb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800192d0  lea     rcx, aPropEntry; "PROP_ENTRY"
0x1800192d7  mov     r9d, eax
0x1800192da  mov     [rsp+58h+var_38], rcx
0x1800192df  lea     edx, [rdi+0Eh]
0x1800192e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800192e9  lea     r8, WPP_01f1986460e93c8fc234b92505f16052_Traceguids
0x1800192f0  mov     rcx, [rcx+10h]
0x1800192f4  call    WPP_SF_Ds
0x1800192f9  mov     ebx, 8007000Eh
0x1800192fe  jmp     loc_1800193AF
0x180019303  movups  xmm0, xmmword ptr [rbx]
0x180019306  lea     rcx, [rdi+28h]; pvarDest
0x18001930a  mov     rdx, r14; pvarSrc
0x18001930d  movups  xmmword ptr [rax+10h], xmm0
0x180019311  mov     eax, [rbx+10h]
0x180019314  mov     [rdi+20h], eax
0x180019317  xorps   xmm0, xmm0
0x18001931a  xor     eax, eax
0x18001931c  movups  xmmword ptr [rcx], xmm0
0x18001931f  mov     [rcx+10h], rax
0x180019323  call    cs:__imp_PropVariantCopy
0x180019329  mov     ebx, eax
0x18001932b  test    eax, eax
0x18001932d  jns     short loc_180019384
0x18001932f  mov     rcx, cs:WPP_GLOBAL_Control
0x180019336  lea     rax, WPP_GLOBAL_Control
0x18001933d  cmp     rcx, rax
0x180019340  jz      short loc_1800193A6
0x180019342  test    byte ptr [rcx+1Ch], 8
0x180019346  jz      short loc_1800193A6
0x180019348  cmp     byte ptr [rcx+19h], 2
0x18001934c  jb      short loc_1800193A6
0x18001934e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180019353  lea     rcx, aPropvariantcop_0; "PropVariantCopy failed"
0x18001935a  mov     [rsp+58h+var_30], ebx
0x18001935e  mov     [rsp+58h+var_38], rcx
0x180019363  lea     r8, WPP_01f1986460e93c8fc234b92505f16052_Traceguids
0x18001936a  mov     rcx, cs:WPP_GLOBAL_Control
0x180019371  mov     edx, 0Fh
0x180019376  mov     r9d, eax
0x180019379  mov     rcx, [rcx+10h]
0x18001937d  call    WPP_SF_DsD
0x180019382  jmp     short loc_1800193A6
0x180019384  lea     rcx, [rbp+50h]
0x180019388  mov     rax, [rcx+8]
0x18001938c  mov     [rdi], rcx
0x18001938f  mov     [rdi+8], rax
0x180019393  mov     [rax], rdi
0x180019396  inc     dword ptr [rbp+48h]
0x180019399  mov     [rcx+8], rdi
0x18001939d  test    ebx, ebx
0x18001939f  jz      short loc_1800193AF
0x1800193a1  test    rdi, rdi
0x1800193a4  jz      short loc_1800193AF
0x1800193a6  mov     rcx, rdi; pv
0x1800193a9  call    cs:__imp_CoTaskMemFree
0x1800193af  test    rsi, rsi
0x1800193b2  jz      short loc_1800193C3
0x1800193b4  cmp     dword ptr [rsi+8], 0
0x1800193b8  jz      short loc_1800193C3
0x1800193ba  mov     rcx, [rsi]
0x1800193bd  call    cs:__imp_PAL_System_CritSecLeave
0x1800193c3  mov     eax, ebx
0x1800193c5  add     rsp, 30h
0x1800193c9  pop     r14
0x1800193cb  pop     rdi
0x1800193cc  pop     rsi
0x1800193cd  pop     rbp
0x1800193ce  pop     rbx
0x1800193cf  retn
0x1800193d0  lea     rbx, [rax+28h]
0x1800193d4  xor     edi, edi
0x1800193d6  mov     rcx, rbx; pvar
0x1800193d9  call    cs:__imp_PropVariantClear
0x1800193df  mov     rdx, r14; pvarSrc
0x1800193e2  mov     rcx, rbx; pvarDest
0x1800193e5  call    cs:__imp_PropVariantCopy
0x1800193eb  mov     ebx, eax
0x1800193ed  test    eax, eax
0x1800193ef  jns     short loc_18001939D
0x1800193f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800193f8  lea     rax, WPP_GLOBAL_Control
0x1800193ff  cmp     rcx, rax
0x180019402  jz      short loc_1800193AF
0x180019404  test    byte ptr [rcx+1Ch], 8
0x180019408  jz      short loc_1800193AF
0x18001940a  cmp     byte ptr [rcx+19h], 2
0x18001940e  jb      short loc_1800193AF
0x180019410  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180019415  lea     rcx, aPropvariantcop_0; "PropVariantCopy failed"
0x18001941c  mov     [rsp+58h+var_30], ebx
0x180019420  mov     [rsp+58h+var_38], rcx
0x180019425  lea     edx, [rdi+10h]
0x180019428  mov     rcx, cs:WPP_GLOBAL_Control
0x18001942f  lea     r8, WPP_01f1986460e93c8fc234b92505f16052_Traceguids
0x180019436  mov     r9d, eax
0x180019439  mov     rcx, [rcx+10h]
0x18001943d  call    WPP_SF_DsD
0x180019442  jmp     loc_1800193AF
```
