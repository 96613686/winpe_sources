# SharedFileToken::ToString(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180014050`
- end: `0x1800143bd`
- name: `?ToString@SharedFileToken@@UEBAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `877`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config`

## callees

- `0x1800041a0`
- `0x180006cb0`
- `0x180006d54`
- `0x180006f00`
- `0x180006f78`
- `0x18000bf80`
- `0x180011b38`
- `0x1800132b0`
- `0x180013368`
- `0x180013814`
- `0x180013978`
- `0x180014050`
- `0x180019624`
- `0x18001b30a`
- `0x18001b340`

## string_xrefs

- `0x18001435e`: `SharedFileToken::ToString`
- `0x18001430a`: `<SharedFileToken Id="%s">\n  <Owner>%s</Owner>\n  <OwnerProductId>%s</OwnerProductId>\n  <Usage>%s</Usage>\n  <LifeTime CreateTime="%s" ExpiryTime="%s" />\n  <ShareAccessControl>\n     <SharePermission>%s</SharePermission>\n     <ShareMode>%s</ShareMode>\n     <ShareScope>%s</ShareScope>\n  </ShareAccessControl>\n  <SharedFilePath>%s</SharedFilePath>\n</SharedFileToken>\n`

## pseudocode

```c
__int64 __fastcall SharedFileToken::ToString(__int64 a1, __int64 a2)
{
  unsigned __int64 v4; // rdx
  const unsigned __int16 *v5; // rcx
  __int64 v6; // r8
  unsigned int *v7; // r9
  const unsigned __int16 * near *v8; // r14
  unsigned __int64 v9; // rbx
  const unsigned __int16 * near *v10; // r15
  const unsigned __int16 * near *v11; // r12
  int v12; // eax
  unsigned __int64 v13; // rax
  int v14; // ebx
  unsigned __int64 v15; // rax
  int v16; // eax
  _QWORD *i; // rbx
  DSLogger *v18; // rax
  __int64 v20; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v21[4]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v22[4]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v23[4]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v24[4]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v25[4]; // [rsp+C8h] [rbp-38h] BYREF
  struct _FILETIME v26[5]; // [rsp+E8h] [rbp-18h] BYREF
  struct _FILETIME v27; // [rsp+110h] [rbp+10h] BYREF
  struct _FILETIME v28; // [rsp+190h] [rbp+90h] BYREF

  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v23);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v26);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v25);
  memset_0(&v28, 0, 0x80u);
  memset_0(&v27, 0, 0x80u);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v24);
  *(_DWORD *)v21 = 64;
  if ( (int)SharingToken::ConvertTokenIdToString(a1 + 12, v26) < 0 )
    goto LABEL_27;
  if ( (int)SharingToken::ConvertTokenIdToString(a1 + 64, v25) < 0 )
    goto LABEL_27;
  if ( *(_DWORD *)(a1 + 80) > 1u )
    goto LABEL_27;
  v8 = (&c_rgpwszTokenUsageTypeNames)[*(int *)(a1 + 80)];
  if ( (int)DSUtils::FormatFileTime((FILETIME *)(a1 + 88), &v28, v21, v7) < 0 )
    goto LABEL_27;
  *(_DWORD *)v21 = 64;
  if ( (int)DSUtils::FormatFileTime((FILETIME *)(a1 + 96), &v27, v21, v7) < 0 )
    goto LABEL_27;
  if ( *(_DWORD *)(a1 + 120) > 2u )
    goto LABEL_27;
  if ( *(_DWORD *)(a1 + 124) > 3u )
    goto LABEL_27;
  v5 = *(const unsigned __int16 **)(a1 + 184);
  v9 = (__int64)(*(_QWORD *)(a1 + 192) - (_QWORD)v5) >> 1;
  if ( v9 > 0x7FFFFFFF )
    goto LABEL_27;
  v10 = (&c_rgpwszSharePermissionNames)[*(int *)(a1 + 120)];
  v11 = (&c_rgpwszShareModeNames)[*(int *)(a1 + 124)];
  v12 = ATL::EscapeXML(v5, v9, 0, 0, v20);
  v13 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::capacity(
          v23,
          v12);
  if ( v4 > v13
    && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Grow(v23) )
  {
    v14 = -2147024882;
LABEL_28:
    v18 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v5,
                        v4,
                        v6,
                        v7);
    LODWORD(v20) = v14;
    DSLogger::LogError(v18, L"SharedFileToken::ToString", 0x7Fu, L"hr=0x%x.", v20);
    goto LABEL_29;
  }
  v15 = utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::capacity(
          v23,
          v4);
  if ( v15 > 0x7FFFFFFF )
  {
LABEL_27:
    v14 = -1055719420;
    goto LABEL_28;
  }
  v16 = ATL::EscapeXML(*(const unsigned __int16 **)(a1 + 184), v9, v23[0], v15, v20);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Resize(v23, v16);
  for ( i = *(_QWORD **)(a1 + 128); i != (_QWORD *)(a1 + 128); i = (_QWORD *)*i )
  {
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(v22);
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v24,
                             *(_QWORD *)(i[2] + 8LL),
                             (__int64)(*(_QWORD *)(i[2] + 16LL) - *(_QWORD *)(i[2] + 8LL)) >> 1) )
      goto LABEL_23;
    if ( (int)SharingToken::ConvertTokenIdToString(i[2] + 44LL, v22) < 0 )
    {
      v14 = -1055719420;
      goto LABEL_24;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v24,
                             L",",
                             1)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v24,
                             v22[0],
                             (__int64)(v22[1] - v22[0]) >> 1) )
    {
LABEL_23:
      v14 = -2147024882;
      goto LABEL_24;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             v24,
                             L";",
                             1) )
    {
      v14 = -2147024882;
LABEL_24:
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v22);
      goto LABEL_28;
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v22);
  }
  v14 = tlx::assign_sprintf<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
          a2,
          L"<SharedFileToken Id=\"%s\">\r\n"
           "  <Owner>%s</Owner>\r\n"
           "  <OwnerProductId>%s</OwnerProductId>\r\n"
           "  <Usage>%s</Usage>\r\n"
           "  <LifeTime CreateTime=\"%s\" ExpiryTime=\"%s\" />\r\n"
           "  <ShareAccessControl>\r\n"
           "     <SharePermission>%s</SharePermission>\r\n"
           "     <ShareMode>%s</ShareMode>\r\n"
           "     <ShareScope>%s</ShareScope>\r\n"
           "  </ShareAccessControl>\r\n"
           "  <SharedFilePath>%s</SharedFilePath>\r\n"
           "</SharedFileToken>\r\n",
          *(_QWORD *)v26,
          *(_QWORD *)(a1 + 32),
          v25[0],
          v8,
          &v28,
          &v27,
          v10,
          v11,
          v24[0],
          v23[0]);
  if ( v14 < 0 )
    goto LABEL_28;
LABEL_29:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v24);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v25);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v26);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(v23);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180014050  mov     [rsp-8+arg_10], rbx
0x180014055  push    rbp
0x180014056  push    rsi
0x180014057  push    rdi
0x180014058  push    r12
0x18001405a  push    r13
0x18001405c  push    r14
0x18001405e  push    r15
0x180014060  lea     rbp, [rsp-120h]
0x180014068  sub     rsp, 220h
0x18001406f  mov     rax, cs:__security_cookie
0x180014076  xor     rax, rsp
0x180014079  mov     [rbp+150h+var_40], rax
0x180014080  mov     rdi, rcx
0x180014083  mov     r13, rdx
0x180014086  lea     rcx, [rbp+150h+var_1C8]
0x18001408a  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001408f  lea     rcx, [rbp+150h+var_168]
0x180014093  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180014098  lea     rcx, [rbp+150h+var_188]
0x18001409c  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800140a1  mov     ebx, 80h
0x1800140a6  lea     rcx, [rbp+150h+var_C0]; void *
0x1800140ad  mov     r8d, ebx; Size
0x1800140b0  xor     edx, edx; Val
0x1800140b2  call    memset_0
0x1800140b7  mov     r8d, ebx; Size
0x1800140ba  lea     rcx, [rbp+150h+var_140]; void *
0x1800140be  xor     edx, edx; Val
0x1800140c0  call    memset_0
0x1800140c5  lea     rcx, [rbp+150h+var_1A8]
0x1800140c9  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x1800140ce  lea     esi, [rbx-40h]
0x1800140d1  lea     rdx, [rbp+150h+var_168]
0x1800140d5  mov     dword ptr [rsp+250h+var_1F0], esi
0x1800140d9  lea     rcx, [rdi+0Ch]
0x1800140dd  call    ?ConvertTokenIdToString@SharingToken@@SAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; SharingToken::ConvertTokenIdToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800140e2  test    eax, eax
0x1800140e4  js      loc_180014343
0x1800140ea  lea     rcx, [rdi+40h]
0x1800140ee  lea     rdx, [rbp+150h+var_188]
0x1800140f2  call    ?ConvertTokenIdToString@SharingToken@@SAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; SharingToken::ConvertTokenIdToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x1800140f7  test    eax, eax
0x1800140f9  js      loc_180014343
0x1800140ff  cmp     dword ptr [rdi+50h], 1
0x180014103  ja      loc_180014343
0x180014109  movsxd  rax, dword ptr [rdi+50h]
0x18001410d  lea     r12, __ImageBase
0x180014114  mov     r14, ds:rva ?c_rgpwszTokenUsageTypeNames@@3PAPEBGA[r12+rax*8]; ushort const * near * c_rgpwszTokenUsageTypeNames ...
0x18001411c  lea     r8, [rsp+250h+var_1F0]; unsigned __int16 *
0x180014121  lea     rdx, [rbp+150h+var_C0]; struct _FILETIME *
0x180014128  lea     rcx, [rdi+58h]; lpFileTime
0x18001412c  call    ?FormatFileTime@DSUtils@@YAJAEBU_FILETIME@@PEAGPEAK@Z; DSUtils::FormatFileTime(_FILETIME const &,ushort *,ulong *)
0x180014131  test    eax, eax
0x180014133  js      loc_180014343
0x180014139  lea     rcx, [rdi+60h]; lpFileTime
0x18001413d  mov     dword ptr [rsp+250h+var_1F0], esi
0x180014141  lea     r8, [rsp+250h+var_1F0]; unsigned __int16 *
0x180014146  lea     rdx, [rbp+150h+var_140]; struct _FILETIME *
0x18001414a  call    ?FormatFileTime@DSUtils@@YAJAEBU_FILETIME@@PEAGPEAK@Z; DSUtils::FormatFileTime(_FILETIME const &,ushort *,ulong *)
0x18001414f  test    eax, eax
0x180014151  js      loc_180014343
0x180014157  cmp     dword ptr [rdi+78h], 2
0x18001415b  ja      loc_180014343
0x180014161  cmp     dword ptr [rdi+7Ch], 3
0x180014165  ja      loc_180014343
0x18001416b  mov     rcx, [rdi+0B8h]; unsigned __int16 *
0x180014172  mov     esi, 7FFFFFFFh
0x180014177  mov     rbx, [rdi+0C0h]
0x18001417e  sub     rbx, rcx
0x180014181  sar     rbx, 1
0x180014184  cmp     rbx, rsi
0x180014187  ja      loc_180014343
0x18001418d  movsxd  rax, dword ptr [rdi+78h]
0x180014191  xor     r9d, r9d; int
0x180014194  xor     r8d, r8d; unsigned __int16 *
0x180014197  mov     edx, ebx; int
0x180014199  mov     r15, ds:rva ?c_rgpwszSharePermissionNames@@3PAPEBGA[r12+rax*8]; ushort const * near * c_rgpwszSharePermissionNames ...
0x1800141a1  movsxd  rax, dword ptr [rdi+7Ch]
0x1800141a5  mov     r12, ds:rva ?c_rgpwszShareModeNames@@3PAPEBGA[r12+rax*8]; ushort const * near * c_rgpwszShareModeNames ...
0x1800141ad  call    ?EscapeXML@ATL@@YAHPEBGHPEAGHK@Z; ATL::EscapeXML(ushort const *,int,ushort *,int,ulong)
0x1800141b2  lea     rcx, [rbp+150h+var_1C8]
0x1800141b6  movsxd  rdx, eax
0x1800141b9  call    ?capacity@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::capacity(void)
0x1800141be  cmp     rdx, rax
0x1800141c1  jbe     short loc_1800141DA
0x1800141c3  lea     rcx, [rbp+150h+var_1C8]
0x1800141c7  call    ?_Grow@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA_N_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Grow(unsigned __int64)
0x1800141cc  test    al, al
0x1800141ce  jnz     short loc_1800141DA
0x1800141d0  mov     ebx, 8007000Eh
0x1800141d5  jmp     loc_180014348
0x1800141da  lea     rcx, [rbp+150h+var_1C8]
0x1800141de  call    ?capacity@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEBA_KXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::capacity(void)
0x1800141e3  cmp     rax, rsi
0x1800141e6  ja      loc_180014343
0x1800141ec  mov     r8, [rbp+150h+var_1C8]; unsigned __int16 *
0x1800141f0  mov     r9d, eax; int
0x1800141f3  mov     rcx, [rdi+0B8h]; unsigned __int16 *
0x1800141fa  mov     edx, ebx; int
0x1800141fc  call    ?EscapeXML@ATL@@YAHPEBGHPEAGHK@Z; ATL::EscapeXML(ushort const *,int,ushort *,int,ulong)
0x180014201  movsxd  rdx, eax
0x180014204  lea     rcx, [rbp+150h+var_1C8]
0x180014208  call    ?_Resize@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAX_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Resize(unsigned __int64)
0x18001420d  lea     rsi, [rdi+80h]
0x180014214  mov     rbx, [rsi]
0x180014217  cmp     rbx, rsi
0x18001421a  jz      loc_1800142E5
0x180014220  lea     rcx, [rsp+250h+var_1E8]
0x180014225  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x18001422a  mov     rax, [rbx+10h]
0x18001422e  lea     rcx, [rbp+150h+var_1A8]
0x180014232  mov     rdx, [rax+8]
0x180014236  mov     r8, [rax+10h]
0x18001423a  sub     r8, rdx
0x18001423d  sar     r8, 1
0x180014240  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180014245  test    al, al
0x180014247  jz      loc_1800142D4
0x18001424d  mov     rcx, [rbx+10h]
0x180014251  lea     rdx, [rsp+250h+var_1E8]
0x180014256  add     rcx, 2Ch ; ','
0x18001425a  call    ?ConvertTokenIdToString@SharingToken@@SAJAEBU_GUID@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; SharingToken::ConvertTokenIdToString(_GUID const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x18001425f  test    eax, eax
0x180014261  js      short loc_1800142CD
0x180014263  mov     r8d, 1
0x180014269  lea     rdx, asc_180022100; ","
0x180014270  lea     rcx, [rbp+150h+var_1A8]
0x180014274  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180014279  test    al, al
0x18001427b  jz      short loc_1800142D4
0x18001427d  mov     r8, [rsp+250h+var_1E0]
0x180014282  lea     rcx, [rbp+150h+var_1A8]
0x180014286  mov     rdx, [rsp+250h+var_1E8]
0x18001428b  sub     r8, rdx
0x18001428e  sar     r8, 1
0x180014291  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180014296  test    al, al
0x180014298  jz      short loc_1800142D4
0x18001429a  mov     r8d, 1
0x1800142a0  lea     rdx, asc_180022104; ";"
0x1800142a7  lea     rcx, [rbp+150h+var_1A8]
0x1800142ab  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800142b0  lea     rcx, [rsp+250h+var_1E8]
0x1800142b5  test    al, al
0x1800142b7  jz      short loc_1800142C6
0x1800142b9  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800142be  mov     rbx, [rbx]
0x1800142c1  jmp     loc_180014217
0x1800142c6  mov     ebx, 8007000Eh
0x1800142cb  jmp     short loc_1800142DE
0x1800142cd  mov     ebx, 0C1130004h
0x1800142d2  jmp     short loc_1800142D9
0x1800142d4  mov     ebx, 8007000Eh
0x1800142d9  lea     rcx, [rsp+250h+var_1E8]
0x1800142de  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800142e3  jmp     short loc_180014348
0x1800142e5  mov     rax, [rbp+150h+var_1C8]
0x1800142e9  mov     rcx, r13
0x1800142ec  mov     rdx, [rbp+150h+var_1A8]
0x1800142f0  mov     r10, [rbp+150h+var_188]
0x1800142f4  mov     r9, [rdi+20h]
0x1800142f8  mov     r8, [rbp+150h+var_168]
0x1800142fc  mov     [rsp+250h+var_1F8], rax
0x180014301  lea     rax, [rbp+150h+var_140]
0x180014305  mov     [rsp+250h+var_200], rdx
0x18001430a  lea     rdx, aSharedfiletoke_3; "<SharedFileToken Id=\"%s\">\r\n  <Owner"...
0x180014311  mov     [rsp+250h+var_208], r12
0x180014316  mov     [rsp+250h+var_210], r15
0x18001431b  mov     [rsp+250h+var_218], rax
0x180014320  lea     rax, [rbp+150h+var_C0]
0x180014327  mov     [rsp+250h+var_220], rax
0x18001432c  mov     [rsp+250h+var_228], r14
0x180014331  mov     [rsp+250h+var_230], r10
0x180014336  call    ??$assign_sprintf@GU?$char_traits@G@utl@@V?$allocator@G@2@@tlx@@YAJAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBGZZ; tlx::assign_sprintf<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *,...)
0x18001433b  mov     ebx, eax
0x18001433d  test    eax, eax
0x18001433f  js      short loc_180014348
0x180014341  jmp     short loc_18001436D
0x180014343  mov     ebx, 0C1130004h
0x180014348  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001434d  lea     r9, aHr0xX; "hr=0x%x."
0x180014354  mov     dword ptr [rsp+250h+var_230], ebx
0x180014358  mov     r8d, 7Fh; unsigned int
0x18001435e  lea     rdx, aSharedfiletoke_1; "SharedFileToken::ToString"
0x180014365  mov     rcx, rax; this
0x180014368  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18001436d  lea     rcx, [rbp+150h+var_1A8]
0x180014371  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180014376  lea     rcx, [rbp+150h+var_188]
0x18001437a  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x18001437f  lea     rcx, [rbp+150h+var_168]
0x180014383  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180014388  lea     rcx, [rbp+150h+var_1C8]
0x18001438c  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180014391  mov     eax, ebx
0x180014393  mov     rcx, [rbp+150h+var_40]
0x18001439a  xor     rcx, rsp; StackCookie
0x18001439d  call    __security_check_cookie
0x1800143a2  mov     rbx, [rsp+250h+arg_10]
0x1800143aa  add     rsp, 220h
0x1800143b1  pop     r15
0x1800143b3  pop     r14
0x1800143b5  pop     r13
0x1800143b7  pop     r12
0x1800143b9  pop     rdi
0x1800143ba  pop     rsi
0x1800143bb  pop     rbp
0x1800143bc  retn
```
