# CSearchQueryMapping::MapIConditionToUpnpQuery(ICondition2 *,int,CMFBaseStringT<ushort> *,CSearchQueryMapping *)

- ea: `0x180029d04`
- end: `0x18002a2c7`
- name: `?MapIConditionToUpnpQuery@CSearchQueryMapping@@KAJPEAUICondition2@@HPEAV?$CMFBaseStringT@G@@PEAV1@@Z`
- size: `1475`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800290b4`
- `0x180029d04`

## callees

- `0x180001710`
- `0x18000a4a0`
- `0x18000d9bc`
- `0x180011930`
- `0x18001bbe0`
- `0x18001bfc0`
- `0x18001c648`
- `0x18001d41c`
- `0x180028fb8`
- `0x1800296d8`
- `0x180029d04`
- `0x18002a6c0`
- `0x18002b588`
- `0x1800333e8`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029e89`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029e89`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a149`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a149`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSearchQueryMapping::MapIConditionToUpnpQuery(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rsi
  int v8; // ebx
  __int64 v9; // rdx
  __int64 i; // r8
  __int64 v11; // r8
  __int64 v12; // r9
  __int16 v13; // r10
  __int64 (__fastcall *v14)(PROPVARIANT *, __int64, __int64); // rax
  int v15; // eax
  __int64 *v16; // rcx
  __int64 (__fastcall *v17)(__int64, GUID *, __int64 *); // rbx
  int v18; // edi
  unsigned int v19; // r13d
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rsi
  __int64 (__fastcall *v23)(__int64, _QWORD, GUID *, __int64 *); // rbx
  int v24; // r9d
  __int64 v25; // rdi
  const wchar_t *v26; // rdx
  int v27; // r9d
  int v28; // ebx
  const WCHAR *v29; // rax
  int v30; // r9d
  int v31; // eax
  int v32; // ecx
  int v33; // eax
  __int64 v34; // rdi
  int v35; // ebx
  __int64 v36; // rbx
  int v38; // [rsp+30h] [rbp-89h] BYREF
  _BYTE v39[12]; // [rsp+38h] [rbp-81h] BYREF
  int v40; // [rsp+44h] [rbp-75h]
  __int64 v41; // [rsp+48h] [rbp-71h]
  int v42; // [rsp+50h] [rbp-69h] BYREF
  __int64 v43; // [rsp+58h] [rbp-61h] BYREF
  unsigned int v44; // [rsp+60h] [rbp-59h] BYREF
  __int64 v45; // [rsp+68h] [rbp-51h] BYREF
  unsigned int v46; // [rsp+70h] [rbp-49h] BYREF
  __int64 v47; // [rsp+78h] [rbp-41h] BYREF
  int v48; // [rsp+80h] [rbp-39h]
  int v49; // [rsp+84h] [rbp-35h]
  __int64 v50; // [rsp+88h] [rbp-31h]
  __int64 v51; // [rsp+90h] [rbp-29h]
  PROPVARIANT v52[2]; // [rsp+98h] [rbp-21h] BYREF
  __int64 v53; // [rsp+C8h] [rbp+Fh]

  v45 = a4;
  v5 = a3;
  v51 = a3;
  v44 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 64LL))(a1, &v44);
  if ( v8 < 0 )
    return (unsigned int)v8;
  if ( v44 >= 2 )
  {
    if ( v44 == 2 )
    {
      v43 = 0;
      v17 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)a1 + 72LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v43);
      v8 = v17(a1, &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7, &v43);
      if ( v8 >= 0 )
        v8 = CSearchQueryMapping::MapIConditionToUpnpQuery(v43, a2 == 0, v5, a4);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v43);
    }
    else if ( v44 == 3 )
    {
      memset(v52, 0, sizeof(v52));
      v53 = a2;
      v8 = (*(__int64 (__fastcall **)(__int64, PROPVARIANT *, char *, PROPVARIANT *))(*(_QWORD *)a1 + 128LL))(
             a1,
             v52,
             (char *)&v52[0].decVal + 20,
             &v52[1]);
      if ( v8 >= 0 )
      {
        v48 = 0;
        v47 = (unsigned int)v47 & 0xFFFFFFF8;
        v50 = 0;
        v49 = 0;
        for ( i = 0; (unsigned int)i < 0x22; i = (unsigned int)(v11 + 1) )
        {
          if ( (unsigned int)operator==(v52, &CSearchQueryMapping::rgPropKeyMapping + 10 * (unsigned int)i)
            && (v13 == *((_WORD *)&CSearchQueryMapping::rgPropKeyMapping + 4 * v12 + 10) || v13 == 1) )
          {
            v14 = (__int64 (__fastcall *)(PROPVARIANT *, __int64, __int64))*(&funcs_180029E39 + v12);
            if ( v14 )
              v15 = v14(v52, v5, a4);
            else
              v15 = CSearchQueryMapping::MapCommon(v52, v5, v11, v9);
            v8 = v15;
            goto LABEL_21;
          }
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF__guid_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, i, v52, *((_DWORD *)&v52[0].decVal + 4));
        }
        v8 = 1;
LABEL_21:
        PropVariantClear(&v52[1]);
        v16 = &v47;
        goto LABEL_80;
      }
    }
    return (unsigned int)v8;
  }
  if ( a2 )
    v44 = v44 != 1;
  v43 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)a1 + 72LL))(
         a1,
         &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
         &v43);
  if ( v8 < 0 )
    return (unsigned int)v8;
  v38 = 0;
  v46 = 0;
  v18 = 0;
  *(_DWORD *)&v39[8] = 0;
  *(_QWORD *)v39 = *(_DWORD *)v39 & 0xFFFFFFF8;
  v19 = 0;
  v41 = 0;
  v40 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v43 + 24LL))(v43, &v46);
  if ( v8 < 0 )
    goto LABEL_53;
  v22 = v45;
  while ( v19 < v46 )
  {
    v45 = 0;
    v23 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v43 + 32LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v45);
    v8 = v23(v43, v19, &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7, &v45);
    if ( v8 >= 0 )
    {
      v48 = 0;
      v47 = (unsigned int)v47 & 0xFFFFFFF8;
      v50 = 0;
      v49 = 0;
      v8 = CSearchQueryMapping::MapIConditionToUpnpQuery(v45, a2, &v47, v22);
      if ( v47 < 0 || !v48 || v18 < 0 || !*(_DWORD *)&v39[8] )
        goto LABEL_48;
      v38 = 1;
      v42 = -1;
      if ( v44 )
      {
        if ( (int)UIntPtrToLong(4u, &v42) >= 0 )
        {
          v25 = v42;
          if ( (unsigned int)v42 <= 0x4000000 )
          {
            if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(v39, (unsigned int)(v42 + v27)) >= 0 )
            {
              v26 = L" or ";
              goto LABEL_46;
            }
LABEL_40:
            v18 = *(_DWORD *)&v39[4];
            v8 = *(_DWORD *)&v39[4];
LABEL_48:
            if ( v8 >= 0 )
            {
              v8 = CMFBaseStringT<unsigned short>::Append(v39, &v47);
              v18 = *(_DWORD *)&v39[4];
            }
            CMFBaseStringT<unsigned short>::~CMFBaseStringT<unsigned short>(&v47);
            goto LABEL_51;
          }
        }
      }
      else if ( (int)UIntPtrToLong(5u, &v42) >= 0 )
      {
        v25 = v42;
        if ( (unsigned int)v42 <= 0x4000000 )
        {
          if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(v39, (unsigned int)(v42 + v24)) < 0 )
            goto LABEL_40;
          v26 = L" and ";
LABEL_46:
          v28 = *(_DWORD *)&v39[8];
          memcpy_0((void *)(v41 + 2LL * *(int *)&v39[8]), v26, 2 * v25);
          CMFBaseStringT<unsigned short>::ReleaseBuffer(v39, (unsigned int)(v28 + v25));
          v18 = *(_DWORD *)&v39[4];
          v8 = 0;
          goto LABEL_48;
        }
      }
      v8 = -2147024785;
      *(_DWORD *)&v39[4] = -2147024785;
      v18 = -2147024785;
      goto LABEL_48;
    }
LABEL_51:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v45);
    ++v19;
    if ( v8 < 0 )
      break;
  }
  v5 = v51;
LABEL_53:
  v29 = (const WCHAR *)CMFBaseStringT<unsigned short>::PContents(v39, v20, v21);
  v31 = CompareStringW(
          0x7Fu,
          1u,
          v29,
          v30,
          L"upnp:class derivedfrom \"object.item.imageItem\" or upnp:class derivedfrom \"object.item.audioItem\" or upnp:c"
           "lass derivedfrom \"object.item.videoItem\" or upnp:class derivedfrom \"object.item.videoItem.videoBroadcast\"",
          211);
  if ( v31 == 2 )
  {
    *(_QWORD *)&v39[4] = 0;
    v18 = 0;
  }
  v32 = 0;
  if ( v31 != 2 )
    v32 = v38;
  if ( v8 < 0 )
    goto LABEL_79;
  if ( !v32 )
    goto LABEL_77;
  v38 = -1;
  if ( (int)UIntPtrToLong(1u, &v38) < 0 )
    goto LABEL_60;
  if ( v18 < 0 )
  {
    v8 = v18;
    goto LABEL_66;
  }
  v34 = v38;
  if ( (unsigned int)v38 > 0x4000000 )
  {
LABEL_60:
    v33 = -2147024785;
    *(_DWORD *)&v39[4] = -2147024785;
LABEL_78:
    v8 = v33;
    goto LABEL_79;
  }
  if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(v39, (unsigned int)(v38 + *(_DWORD *)&v39[8])) >= 0 )
  {
    v35 = *(_DWORD *)&v39[8];
    memcpy_0((void *)(v41 + 2LL * *(int *)&v39[8]), L")", 2 * v34);
    CMFBaseStringT<unsigned short>::ReleaseBuffer(v39, (unsigned int)(v35 + v34));
  }
  else
  {
    v8 = *(_DWORD *)&v39[4];
LABEL_66:
    if ( v8 < 0 )
      goto LABEL_79;
  }
  v38 = -1;
  if ( (int)UIntPtrToLong(1u, &v38) < 0 )
    goto LABEL_75;
  v8 = *(_DWORD *)(v5 + 4);
  if ( v8 < 0 )
    goto LABEL_79;
  v36 = v38;
  if ( (unsigned int)v38 > 0x4000000 )
  {
LABEL_75:
    v8 = -2147024785;
    *(_DWORD *)(v5 + 4) = -2147024785;
  }
  else if ( (int)CMFBaseStringT<unsigned short>::_EnsureSpace(v5, (unsigned int)(v38 + *(_DWORD *)(v5 + 8))) >= 0 )
  {
    memcpy_0((void *)(*(_QWORD *)(v5 + 16) + 2LL * *(int *)(v5 + 8)), L"(", 2 * v36);
    CMFBaseStringT<unsigned short>::ReleaseBuffer(v5, (unsigned int)(v36 + *(_DWORD *)(v5 + 8)));
    v8 = 0;
  }
  else
  {
    v8 = *(_DWORD *)(v5 + 4);
  }
  if ( v8 >= 0 )
  {
LABEL_77:
    v33 = CMFBaseStringT<unsigned short>::Append(v5, v39);
    goto LABEL_78;
  }
LABEL_79:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  v16 = (__int64 *)v39;
LABEL_80:
  CMFBaseStringT<unsigned short>::~CMFBaseStringT<unsigned short>(v16);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180029d04  push    rbp
0x180029d06  push    rbx
0x180029d07  push    rsi
0x180029d08  push    rdi
0x180029d09  push    r12
0x180029d0b  push    r13
0x180029d0d  push    r14
0x180029d0f  lea     rbp, [rsp-27h]
0x180029d14  sub     rsp, 0E0h
0x180029d1b  mov     rax, cs:__security_cookie
0x180029d22  xor     rax, rsp
0x180029d25  mov     [rbp+57h+var_40], rax
0x180029d29  mov     r13, r9
0x180029d2c  mov     [rbp+57h+var_A8], r9
0x180029d30  mov     rsi, r8
0x180029d33  mov     [rbp+57h+var_80], r8
0x180029d37  mov     r12d, edx
0x180029d3a  mov     rdi, rcx
0x180029d3d  mov     [rbp+57h+var_B0], 0
0x180029d44  mov     rax, [rcx]
0x180029d47  lea     rdx, [rbp+57h+var_B0]
0x180029d4b  mov     rax, [rax+40h]
0x180029d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d54  mov     ebx, eax
0x180029d56  test    eax, eax
0x180029d58  js      loc_18002A2A7
0x180029d5e  mov     edx, [rbp+57h+var_B0]
0x180029d61  mov     eax, edx
0x180029d63  test    edx, edx
0x180029d65  jz      loc_180029EF4
0x180029d6b  sub     eax, 1
0x180029d6e  jz      loc_180029EF4
0x180029d74  sub     eax, 1
0x180029d77  jz      loc_180029E99
0x180029d7d  cmp     eax, 1
0x180029d80  jnz     loc_18002A2A7
0x180029d86  xorps   xmm0, xmm0
0x180029d89  xor     eax, eax
0x180029d8b  movups  [rbp+57h+var_78], xmm0
0x180029d8f  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180029d93  movups  xmmword ptr [rbp+57h+pvar+10h], xmm0
0x180029d97  mov     [rbp+57h+var_48], rax
0x180029d9b  mov     dword ptr [rbp+57h+var_48], r12d
0x180029d9f  mov     rax, [rdi]
0x180029da2  lea     r9, [rbp+57h+pvar+8]
0x180029da6  lea     r8, [rbp+57h+pvar+4]
0x180029daa  lea     rdx, [rbp+57h+var_78]
0x180029dae  mov     rcx, rdi
0x180029db1  mov     rax, [rax+80h]
0x180029db8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dbd  mov     ebx, eax
0x180029dbf  test    eax, eax
0x180029dc1  js      loc_18002A2A7
0x180029dc7  mov     [rbp+57h+var_94], 0
0x180029dcf  and     [rbp+57h+var_98], 0FFFFFFF8h
0x180029dd3  xor     r11d, r11d
0x180029dd6  mov     [rbp+57h+var_88], r11
0x180029dda  mov     [rbp+57h+var_8C], r11d
0x180029dde  mov     r8d, r11d
0x180029de1  lea     rbx, ?rgPropKeyMapping@CSearchQueryMapping@@1QBUPropKeyMapping@1@B; CSearchQueryMapping::PropKeyMapping const near * const CSearchQueryMapping::rgPropKeyMapping
0x180029de8  lea     r14d, [r11+1]
0x180029dec  movzx   r10d, word ptr [rbp+57h+pvar+8]
0x180029df1  cmp     r8d, 22h ; '"'
0x180029df5  jnb     short loc_180029E4F
0x180029df7  mov     eax, r8d
0x180029dfa  lea     r9, [rax+rax*4]
0x180029dfe  add     r9, r9
0x180029e01  lea     rdx, [rbx+r9*8]
0x180029e05  lea     rcx, [rbp+57h+var_78]
0x180029e09  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x180029e0e  test    eax, eax
0x180029e10  jz      short loc_180029E20
0x180029e12  cmp     r10w, [rbx+r9*8+14h]
0x180029e18  jz      short loc_180029E25
0x180029e1a  cmp     r14w, r10w
0x180029e1e  jz      short loc_180029E25
0x180029e20  add     r8d, r14d
0x180029e23  jmp     short loc_180029DF1
0x180029e25  mov     rax, (funcs_180029E39 - 180048050h)[rbx+r9*8]
0x180029e2a  lea     rcx, [rbp+57h+var_78]
0x180029e2e  test    rax, rax
0x180029e31  jz      short loc_180029E40
0x180029e33  mov     r8, r13
0x180029e36  mov     rdx, rsi
0x180029e39  call    _guard_dispatch_icall$thunk$10345483385596137414; CSearchQueryMapping::MapPKey_SFGAO(LeaveInfo *,CMFBaseStringT<ushort> *,CSearchQueryMapping *) ...
0x180029e3e  jmp     short loc_180029E4B
0x180029e40  mov     r9, rdx
0x180029e43  mov     rdx, rsi
0x180029e46  call    ?MapCommon@CSearchQueryMapping@@KAJPEAULeaveInfo@@PEAV?$CMFBaseStringT@G@@PEAV1@PEAUPropKeyMapping@1@@Z; CSearchQueryMapping::MapCommon(LeaveInfo *,CMFBaseStringT<ushort> *,CSearchQueryMapping *,CSearchQueryMapping::PropKeyMapping *)
0x180029e4b  mov     ebx, eax
0x180029e4d  jmp     short loc_180029E85
0x180029e4f  lea     rax, WPP_GLOBAL_Control
0x180029e56  mov     rcx, cs:WPP_GLOBAL_Control
0x180029e5d  cmp     rcx, rax
0x180029e60  jz      short loc_180029E82
0x180029e62  test    byte ptr [rcx+1Ch], 40h
0x180029e66  jz      short loc_180029E82
0x180029e68  cmp     byte ptr [rcx+19h], 4
0x180029e6c  jb      short loc_180029E82
0x180029e6e  mov     eax, dword ptr [rbp+57h+pvar]
0x180029e71  mov     dword ptr [rsp+110h+lpString2], eax
0x180029e75  lea     r9, [rbp+57h+var_78]
0x180029e79  mov     rcx, [rcx+10h]
0x180029e7d  call    WPP_SF__guid_d
0x180029e82  mov     ebx, r14d
0x180029e85  lea     rcx, [rbp+57h+pvar+8]; pvar
0x180029e89  call    cs:__imp_PropVariantClear
0x180029e8f  nop
0x180029e90  lea     rcx, [rbp+57h+var_98]
0x180029e94  jmp     loc_18002A2A2
0x180029e99  mov     [rbp+57h+var_B8], 0
0x180029ea1  mov     rax, [rdi]
0x180029ea4  mov     rbx, [rax+48h]
0x180029ea8  lea     rcx, [rbp+57h+var_B8]
0x180029eac  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180029eb1  lea     r8, [rbp+57h+var_B8]
0x180029eb5  lea     rdx, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x180029ebc  mov     rcx, rdi
0x180029ebf  mov     rax, rbx
0x180029ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ec7  mov     ebx, eax
0x180029ec9  test    eax, eax
0x180029ecb  js      short loc_180029EE6
0x180029ecd  xor     edx, edx
0x180029ecf  test    r12d, r12d
0x180029ed2  setz    dl
0x180029ed5  mov     r9, r13
0x180029ed8  mov     r8, rsi
0x180029edb  mov     rcx, [rbp+57h+var_B8]
0x180029edf  call    ?MapIConditionToUpnpQuery@CSearchQueryMapping@@KAJPEAUICondition2@@HPEAV?$CMFBaseStringT@G@@PEAV1@@Z; CSearchQueryMapping::MapIConditionToUpnpQuery(ICondition2 *,int,CMFBaseStringT<ushort> *,CSearchQueryMapping *)
0x180029ee4  mov     ebx, eax
0x180029ee6  lea     rcx, [rbp+57h+var_B8]
0x180029eea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180029eef  jmp     loc_18002A2A7
0x180029ef4  mov     r14d, 1
0x180029efa  test    r12d, r12d
0x180029efd  jz      short loc_180029F0A
0x180029eff  xor     eax, eax
0x180029f01  cmp     edx, r14d
0x180029f04  setnz   al
0x180029f07  mov     [rbp+57h+var_B0], eax
0x180029f0a  mov     [rbp+57h+var_B8], 0
0x180029f12  mov     rax, [rdi]
0x180029f15  lea     r8, [rbp+57h+var_B8]
0x180029f19  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x180029f20  mov     rcx, rdi
0x180029f23  mov     rax, [rax+48h]
0x180029f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f2c  mov     ebx, eax
0x180029f2e  test    eax, eax
0x180029f30  js      loc_18002A2A7
0x180029f36  mov     [rsp+110h+var_E0], 0
0x180029f3e  mov     [rbp+57h+var_A0], 0
0x180029f45  xor     edi, edi
0x180029f47  mov     [rbp+57h+var_D4], rdi
0x180029f4b  and     [rsp+110h+var_D8], 0FFFFFFF8h
0x180029f50  xor     r13d, r13d
0x180029f53  mov     [rbp+57h+var_C8], r13
0x180029f57  mov     [rbp+57h+var_CC], r13d
0x180029f5b  mov     rcx, [rbp+57h+var_B8]
0x180029f5f  mov     rax, [rcx]
0x180029f62  lea     rdx, [rbp+57h+var_A0]
0x180029f66  mov     rax, [rax+18h]
0x180029f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f6f  mov     ebx, eax
0x180029f71  test    eax, eax
0x180029f73  js      loc_18002A11C
0x180029f79  mov     rsi, [rbp+57h+var_A8]
0x180029f7d  cmp     r13d, [rbp+57h+var_A0]
0x180029f81  jnb     loc_18002A10F
0x180029f87  mov     [rbp+57h+var_A8], 0
0x180029f8f  mov     rax, [rbp+57h+var_B8]
0x180029f93  mov     rcx, [rax]
0x180029f96  mov     rbx, [rcx+20h]
0x180029f9a  lea     rcx, [rbp+57h+var_A8]
0x180029f9e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x180029fa3  lea     r9, [rbp+57h+var_A8]
0x180029fa7  lea     r8, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x180029fae  mov     edx, r13d
0x180029fb1  mov     rcx, [rbp+57h+var_B8]
0x180029fb5  mov     rax, rbx
0x180029fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fbd  mov     ebx, eax
0x180029fbf  xor     eax, eax
0x180029fc1  test    ebx, ebx
0x180029fc3  js      loc_18002A0FB
0x180029fc9  mov     [rbp+57h+var_94], rax
0x180029fcd  and     [rbp+57h+var_98], 0FFFFFFF8h
0x180029fd1  mov     [rbp+57h+var_88], rax
0x180029fd5  mov     [rbp+57h+var_8C], eax
0x180029fd8  mov     r9, rsi
0x180029fdb  lea     r8, [rbp+57h+var_98]
0x180029fdf  mov     edx, r12d
0x180029fe2  mov     rcx, [rbp+57h+var_A8]
0x180029fe6  call    ?MapIConditionToUpnpQuery@CSearchQueryMapping@@KAJPEAUICondition2@@HPEAV?$CMFBaseStringT@G@@PEAV1@@Z; CSearchQueryMapping::MapIConditionToUpnpQuery(ICondition2 *,int,CMFBaseStringT<ushort> *,CSearchQueryMapping *)
0x180029feb  mov     ebx, eax
0x180029fed  cmp     dword ptr [rbp+57h+var_94], 0
0x180029ff1  jl      loc_18002A0DA
0x180029ff7  cmp     dword ptr [rbp+57h+var_94+4], 0
0x180029ffb  jz      loc_18002A0DA
0x18002a001  test    edi, edi
0x18002a003  js      loc_18002A0DA
0x18002a009  mov     r9d, dword ptr [rbp+57h+var_D4+4]
0x18002a00d  test    r9d, r9d
0x18002a010  jz      loc_18002A0DA
0x18002a016  mov     [rsp+110h+var_E0], r14d
0x18002a01b  mov     [rbp+57h+var_C0], 0FFFFFFFFh
0x18002a022  lea     rdx, [rbp+57h+var_C0]; int *
0x18002a026  cmp     [rbp+57h+var_B0], 0
0x18002a02a  jnz     short loc_18002A070
0x18002a02c  mov     ecx, 5; unsigned __int64
0x18002a031  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x18002a036  test    eax, eax
0x18002a038  js      loc_18002A0CE
0x18002a03e  movsxd  rdi, [rbp+57h+var_C0]
0x18002a042  cmp     edi, 4000000h
0x18002a048  ja      loc_18002A0CE
0x18002a04e  lea     edx, [rdi+r9]
0x18002a052  lea     rcx, [rsp+110h+var_D8]
0x18002a057  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x18002a05c  test    eax, eax
0x18002a05e  jns     short loc_18002A067
0x18002a060  mov     edi, dword ptr [rbp+57h+var_D4]
0x18002a063  mov     ebx, edi
0x18002a065  jmp     short loc_18002A0DA
0x18002a067  lea     rdx, aAnd_0; " and "
0x18002a06e  jmp     short loc_18002A0A3
0x18002a070  mov     ecx, 4; unsigned __int64
0x18002a075  call    ?UIntPtrToLong@@YAJ_KPEAJ@Z; UIntPtrToLong(unsigned __int64,long *)
0x18002a07a  test    eax, eax
0x18002a07c  js      short loc_18002A0CE
0x18002a07e  movsxd  rdi, [rbp+57h+var_C0]
0x18002a082  cmp     edi, 4000000h
0x18002a088  ja      short loc_18002A0CE
0x18002a08a  lea     edx, [rdi+r9]
0x18002a08e  lea     rcx, [rsp+110h+var_D8]
0x18002a093  call    ?_EnsureSpace@?$CMFBaseStringT@G@@IEAAJJ@Z; CMFBaseStringT<ushort>::_EnsureSpace(long)
0x18002a098  test    eax, eax
0x18002a09a  js      short loc_18002A060
0x18002a09c  lea     rdx, aOr_0; " or "
0x18002a0a3  mov     r8, rdi
0x18002a0a6  movsxd  rbx, dword ptr [rbp+57h+var_D4+4]
0x18002a0aa  mov     rax, [rbp+57h+var_C8]
0x18002a0ae  add     r8, r8; Size
0x18002a0b1  lea     rcx, [rax+rbx*2]; void *
0x18002a0b5  call    memcpy_0
0x18002a0ba  lea     edx, [rbx+rdi]
0x18002a0bd  lea     rcx, [rsp+110h+var_D8]
0x18002a0c2  call    ?ReleaseBuffer@?$CMFBaseStringT@G@@QEAAJJ@Z; CMFBaseStringT<ushort>::ReleaseBuffer(long)
0x18002a0c7  mov     edi, dword ptr [rbp+57h+var_D4]
0x18002a0ca  xor     ebx, ebx
0x18002a0cc  jmp     short loc_18002A0DA
0x18002a0ce  mov     eax, 8007006Fh
0x18002a0d3  mov     ebx, eax
0x18002a0d5  mov     dword ptr [rbp+57h+var_D4], eax
0x18002a0d8  mov     edi, eax
0x18002a0da  test    ebx, ebx
0x18002a0dc  js      short loc_18002A0F1
0x18002a0de  lea     rdx, [rbp+57h+var_98]
0x18002a0e2  lea     rcx, [rsp+110h+var_D8]
0x18002a0e7  call    ?Append@?$CMFBaseStringT@G@@QEAAJAEAV1@@Z; CMFBaseStringT<ushort>::Append(CMFBaseStringT<ushort> &)
0x18002a0ec  mov     ebx, eax
0x18002a0ee  mov     edi, dword ptr [rbp+57h+var_D4]
0x18002a0f1  lea     rcx, [rbp+57h+var_98]
0x18002a0f5  call    ??1?$CMFBaseStringT@G@@QEAA@XZ; CMFBaseStringT<ushort>::~CMFBaseStringT<ushort>(void)
0x18002a0fa  nop
0x18002a0fb  lea     rcx, [rbp+57h+var_A8]
0x18002a0ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18002a104  add     r13d, r14d
0x18002a107  test    ebx, ebx
0x18002a109  jns     loc_180029F7D
0x18002a10f  test    edi, edi
0x18002a111  mov     rsi, [rbp+57h+var_80]
0x18002a115  jns     short loc_18002A11C
0x18002a117  xor     r9d, r9d
0x18002a11a  jmp     short loc_18002A120
0x18002a11c  mov     r9d, dword ptr [rbp+57h+var_D4+4]
0x18002a120  lea     rcx, [rsp+110h+var_D8]
0x18002a125  call    ?PContents@?$CMFBaseStringT@G@@QEBAPEBGXZ; CMFBaseStringT<ushort>::PContents(void)
0x18002a12a  mov     r8, rax; lpString1
0x18002a12d  mov     [rsp+110h+cchCount2], 0D3h; cchCount2
0x18002a135  lea     rax, aUpnpClassDeriv; "upnp:class derivedfrom \"object.item.im"...
0x18002a13c  mov     [rsp+110h+lpString2], rax; lpString2
0x18002a141  mov     edx, r14d; dwCmpFlags
0x18002a144  mov     ecx, 7Fh; Locale
0x18002a149  call    cs:__imp_CompareStringW
0x18002a14f  cmp     eax, 2
0x18002a152  jnz     short loc_18002A15E
0x18002a154  mov     [rbp+57h+var_D4], 0
0x18002a15c  xor     edi, edi
0x18002a15e  xor     ecx, ecx
0x18002a160  cmp     eax, 2
0x18002a163  cmovnz  ecx, [rsp+110h+var_E0]
0x18002a168  test    ebx, ebx
0x18002a16a  js      loc_18002A28C
0x18002a170  test    ecx, ecx
0x18002a172  jz      loc_18002A27D
0x18002a178  mov     [rsp+110h+var_E0], 0FFFFFFFFh
0x18002a180  lea     rdx, [rsp+110h+var_E0]; int *
0x18002a185  mov     rcx, r14; unsigned __int64
  ... truncated ...
```
