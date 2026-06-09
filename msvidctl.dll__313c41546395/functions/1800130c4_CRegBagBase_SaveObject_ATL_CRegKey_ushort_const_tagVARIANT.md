# CRegBagBase::SaveObject(ATL::CRegKey &,ushort const *,tagVARIANT *)

- ea: `0x1800130c4`
- end: `0x1800134d0`
- name: `?SaveObject@CRegBagBase@@IEAAJAEAVCRegKey@ATL@@PEBGPEAUtagVARIANT@@@Z`
- size: `1036`
- prototype: `int(CRegBagBase *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013760`

## callees

- `0x180004640`
- `0x180004b54`
- `0x180006b38`
- `0x18000dba4`
- `0x18000dbe4`
- `0x18000dc24`
- `0x1800103e8`
- `0x180010e9c`
- `0x180011110`
- `0x180012218`
- `0x1800130c4`
- `0x1800f8010`

## import_xrefs

- `ole32!StringFromGUID2` at `0x1800131ca`
- `ole32!StringFromGUID2` at `0x18001335f`
- `ole32!StringFromGUID2` at `0x1800131ca`
- `ole32!StringFromGUID2` at `0x18001335f`
- `ADVAPI32!RegSetValueW` at `0x18001320b`
- `ADVAPI32!RegSetValueW` at `0x1800133a0`
- `ADVAPI32!RegSetValueW` at `0x18001320b`
- `ADVAPI32!RegSetValueW` at `0x1800133a0`
- `ADVAPI32!RegDeleteValueW` at `0x180013119`
- `ADVAPI32!RegDeleteValueW` at `0x180013119`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CRegBagBase::SaveObject(HKEY *this, HKEY *a2, const unsigned __int16 *a3, struct tagVARIANT *a4)
{
  unsigned int v9; // ebx
  unsigned __int16 *v10; // r9
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  CRegBag *v14; // rax
  unsigned __int16 *v15; // r9
  LSTATUS v16; // eax
  bool v17; // cc
  __int64 v18; // rax
  CRegBag *v19; // rdx
  DWORD cbData; // [rsp+20h] [rbp-1F8h]
  struct _SECURITY_ATTRIBUTES *v21; // [rsp+30h] [rbp-1E8h]
  unsigned int *v22; // [rsp+38h] [rbp-1E0h]
  __int64 v23; // [rsp+40h] [rbp-1D8h] BYREF
  CRegBag *v24; // [rsp+48h] [rbp-1D0h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-1C8h] BYREF
  __int64 v26; // [rsp+58h] [rbp-1C0h]
  __int64 v27; // [rsp+60h] [rbp-1B8h]
  __int64 v28; // [rsp+68h] [rbp-1B0h] BYREF
  unsigned int v29; // [rsp+70h] [rbp-1A8h] BYREF
  unsigned int v30; // [rsp+74h] [rbp-1A4h] BYREF
  ComException *v31; // [rsp+78h] [rbp-1A0h] BYREF
  ComException *v32; // [rsp+80h] [rbp-198h] BYREF
  GUID rguid; // [rsp+88h] [rbp-190h] BYREF
  GUID v34; // [rsp+98h] [rbp-180h] BYREF
  OLECHAR sz[64]; // [rsp+B0h] [rbp-168h] BYREF
  OLECHAR Data[64]; // [rsp+130h] [rbp-E8h] BYREF
  std::bad_alloc *v37; // [rsp+1B0h] [rbp-68h] BYREF
  std::exception *v38; // [rsp+1B8h] [rbp-60h] BYREF
  std::bad_alloc *v39; // [rsp+1C0h] [rbp-58h] BYREF
  std::exception *v40; // [rsp+1C8h] [rbp-50h] BYREF

  if ( a4->vt != 13 )
    return 2147549183LL;
  v9 = 0;
  if ( a4->llVal )
  {
    ATL::CComQIPtr<IPersistPropertyBag2,&__s_GUID const _GUID_22f55881_280b_11d0_a8a9_00a0c90c2004>::CComQIPtr<IPersistPropertyBag2,&__s_GUID const _GUID_22f55881_280b_11d0_a8a9_00a0c90c2004>(&v28);
    if ( v28 )
    {
      hKey = 0;
      v26 = 0;
      v27 = 0;
      v11 = ATL::CRegKey::Create((ATL::CRegKey *)&hKey, this[11], a3, v10, cbData, 0x2001Fu, v21, v22);
      v9 = v11;
      if ( v11 )
      {
        if ( v11 > 0 )
          v9 = (unsigned __int16)v11 | 0x80070000;
      }
      else
      {
        rguid = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v28 + 24LL))(v28, &rguid) >= 0
          && StringFromGUID2(&rguid, sz, 64) )
        {
          v12 = -1;
          do
            ++v12;
          while ( sz[v12] );
          v13 = RegSetValueW(hKey, 0, 1u, sz, 2 * v12);
          if ( v13 )
          {
            if ( v13 > 0 )
              v13 = (unsigned __int16)v13 | 0x80070000;
            v9 = v13;
          }
          else
          {
            try
            {
              v24 = (CRegBag *)operator new(0x70u);
              v14 = CRegBag::CRegBag(v24, hKey, 0, 0, 0x2001Fu);
              ATL::CComQIPtr<IMSVidAudioRendererDevices,&__s_GUID const _GUID_c5702cd4_9b79_11d3_b654_00c04f79498e>::CComQIPtr<IMSVidAudioRendererDevices,&__s_GUID const _GUID_c5702cd4_9b79_11d3_b654_00c04f79498e>(
                &v23,
                ((unsigned __int64)v14 + 8) & ((unsigned __int128)-(__int128)(unsigned __int64)v14 >> 64));
              if ( v23 )
                v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v28 + 48LL))(
                       v28,
                       v23,
                       0,
                       1);
              else
                v9 = -2147024882;
              ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
            }
            catch ( long v29 )
            {
              v9 = v29;
            }
            catch ( ComException *v31 )
            {
              LODWORD(v24) = *(_DWORD *)v31;
              v9 = (unsigned int)v24;
            }
            catch ( std::bad_alloc *v37 )
            {
              v9 = -2147024882;
            }
            catch ( std::exception *v38 )
            {
              goto LABEL_22;
            }
          }
        }
        else
        {
LABEL_22:
          v9 = -2147418113;
        }
      }
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      goto LABEL_39;
    }
    ATL::CComQIPtr<IPersistPropertyBag,&__s_GUID const _GUID_37d84f60_42cb_11ce_8135_00aa004bb851>::CComQIPtr<IPersistPropertyBag,&__s_GUID const _GUID_37d84f60_42cb_11ce_8135_00aa004bb851>(
      &v23,
      a4->llVal);
    if ( v23 )
    {
      hKey = 0;
      v26 = 0;
      v27 = 0;
      v16 = ATL::CRegKey::Create((ATL::CRegKey *)&hKey, this[11], a3, v15, cbData, 0x2001Fu, v21, v22);
      v9 = v16;
      v17 = v16 <= 0;
      if ( v16 )
        goto LABEL_25;
      v34 = 0;
      if ( (*(int (__fastcall **)(__int64, GUID *))(*(_QWORD *)v23 + 24LL))(v23, &v34) < 0
        || !StringFromGUID2(&v34, Data, 64) )
      {
LABEL_41:
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
        ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
        v9 = -2147418113;
        goto LABEL_39;
      }
      v18 = -1;
      do
        ++v18;
      while ( Data[v18] );
      v16 = RegSetValueW(hKey, 0, 1u, Data, 2 * v18);
      v9 = v16;
      v17 = v16 <= 0;
      if ( v16 )
      {
LABEL_25:
        if ( !v17 )
          v9 = (unsigned __int16)v16 | 0x80070000;
      }
      else
      {
        try
        {
          *(_QWORD *)&rguid.Data1 = operator new(0x70u);
          v19 = CRegBag::CRegBag(*(CRegBag **)&rguid.Data1, hKey, 0, 0, 0x2001Fu);
          ATL::CComQIPtr<IMSVidAudioRendererDevices,&__s_GUID const _GUID_c5702cd4_9b79_11d3_b654_00c04f79498e>::CComQIPtr<IMSVidAudioRendererDevices,&__s_GUID const _GUID_c5702cd4_9b79_11d3_b654_00c04f79498e>(
            &v24,
            v19);
          if ( v24 )
            v9 = (*(__int64 (__fastcall **)(__int64, CRegBag *, _QWORD, __int64))(*(_QWORD *)v23 + 48LL))(
                   v23,
                   v24,
                   0,
                   1);
          else
            v9 = -2147024882;
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v24);
        }
        catch ( long v30 )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
          v9 = v30;
          goto LABEL_39;
        }
        catch ( ComException *v32 )
        {
          LODWORD(v24) = *(_DWORD *)v32;
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
          v9 = (unsigned int)v24;
          goto LABEL_39;
        }
        catch ( std::bad_alloc *v39 )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
          v9 = -2147024882;
          goto LABEL_39;
        }
        catch ( std::exception *v40 )
        {
          goto LABEL_41;
        }
      }
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
    }
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v23);
LABEL_39:
    ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(&v28);
    return v9;
  }
  RegDeleteValueW(*a2, a3);
  ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)a2, a3);
  return v9;
}

```

## disassembly

```asm
0x1800130c4  push    rbx
0x1800130c6  push    rsi
0x1800130c7  push    rdi
0x1800130c8  push    r12
0x1800130ca  push    r14
0x1800130cc  push    r15
0x1800130ce  sub     rsp, 1E8h
0x1800130d5  mov     rax, cs:__security_cookie
0x1800130dc  xor     rax, rsp
0x1800130df  mov     [rsp+218h+var_48], rax
0x1800130e7  mov     rsi, r9
0x1800130ea  mov     rdi, r8
0x1800130ed  mov     r14, rdx
0x1800130f0  mov     r15, rcx
0x1800130f3  cmp     word ptr [r9], 0Dh
0x1800130f8  jz      short loc_180013104
0x1800130fa  mov     eax, 8000FFFFh
0x1800130ff  jmp     loc_18001343D
0x180013104  xor     r12d, r12d
0x180013107  mov     ebx, r12d
0x18001310a  mov     rdx, [r9+8]
0x18001310e  test    rdx, rdx
0x180013111  jnz     short loc_18001312F
0x180013113  mov     rdx, rdi; lpValueName
0x180013116  mov     rcx, [r14]; hKey
0x180013119  call    cs:__imp_RegDeleteValueW
0x18001311f  mov     rdx, rdi; unsigned __int16 *
0x180013122  mov     rcx, r14; this
0x180013125  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18001312a  jmp     loc_18001343B
0x18001312f  lea     rcx, [rsp+218h+var_1B0]
0x180013134  call    ??0?$CComQIPtr@UIPersistPropertyBag2@@$1?_GUID_22f55881_280b_11d0_a8a9_00a0c90c2004@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IPersistPropertyBag2,&__s_GUID const _GUID_22f55881_280b_11d0_a8a9_00a0c90c2004>::CComQIPtr<IPersistPropertyBag2,&__s_GUID const _GUID_22f55881_280b_11d0_a8a9_00a0c90c2004>(IUnknown *)
0x180013139  nop
0x18001313a  cmp     [rsp+218h+var_1B0], r12
0x18001313f  jz      loc_1800132C0
0x180013145  mov     [rsp+218h+hKey], r12
0x18001314a  mov     [rsp+218h+var_1C0], r12
0x18001314f  mov     [rsp+218h+var_1B8], r12
0x180013154  mov     esi, 2001Fh
0x180013159  mov     [rsp+218h+var_1F0], esi; unsigned int
0x18001315d  mov     r8, rdi; lpSubKey
0x180013160  mov     rdx, [r15+58h]; hKey
0x180013164  lea     rcx, [rsp+218h+hKey]; this
0x180013169  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18001316e  mov     ebx, eax
0x180013170  test    eax, eax
0x180013172  jz      short loc_180013188
0x180013174  jle     loc_180013297
0x18001317a  movzx   ebx, ax
0x18001317d  or      ebx, 80070000h
0x180013183  jmp     loc_180013297
0x180013188  xorps   xmm0, xmm0
0x18001318b  movups  xmmword ptr [rsp+218h+rguid.Data1], xmm0
0x180013193  mov     rcx, [rsp+218h+var_1B0]
0x180013198  mov     rax, [rcx]
0x18001319b  lea     rdx, [rsp+218h+rguid]
0x1800131a3  mov     rax, [rax+18h]
0x1800131a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131ac  test    eax, eax
0x1800131ae  js      loc_1800132B9
0x1800131b4  mov     r8d, 40h ; '@'; cchMax
0x1800131ba  lea     rdx, [rsp+218h+sz]; lpsz
0x1800131c2  lea     rcx, [rsp+218h+rguid]; rguid
0x1800131ca  call    cs:__imp_StringFromGUID2
0x1800131d0  test    eax, eax
0x1800131d2  jz      loc_1800132B9
0x1800131d8  lea     rcx, [rsp+218h+sz]
0x1800131e0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800131e4  inc     rax
0x1800131e7  cmp     [rcx+rax*2], r12w
0x1800131ec  jnz     short loc_1800131E4
0x1800131ee  add     eax, eax
0x1800131f0  mov     [rsp+218h+cbData], eax; cbData
0x1800131f4  lea     r9, [rsp+218h+sz]; lpData
0x1800131fc  mov     edi, 1
0x180013201  mov     r8d, edi; dwType
0x180013204  xor     edx, edx; lpSubKey
0x180013206  mov     rcx, [rsp+218h+hKey]; hKey
0x18001320b  call    cs:__imp_RegSetValueW
0x180013211  test    eax, eax
0x180013213  jz      short loc_180013223
0x180013215  jle     short loc_18001321F
0x180013217  movzx   eax, ax
0x18001321a  or      eax, 80070000h
0x18001321f  mov     ebx, eax
0x180013221  jmp     short loc_180013297
0x180013223  mov     ecx, 70h ; 'p'; Size
0x180013228  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001322d  mov     [rsp+218h+var_1D0], rax
0x180013232  mov     [rsp+218h+cbData], esi; unsigned int
0x180013236  xor     r9d, r9d; unsigned int
0x180013239  xor     r8d, r8d; unsigned __int16 *
0x18001323c  mov     rdx, [rsp+218h+hKey]; HKEY
0x180013241  mov     rcx, rax; this
0x180013244  call    ??0CRegBag@@QEAA@PEAUHKEY__@@PEBGKK@Z; CRegBag::CRegBag(HKEY__ *,ushort const *,ulong,ulong)
0x180013249  nop
0x18001324a  lea     rcx, [rax+8]
0x18001324e  neg     rax
0x180013251  sbb     rdx, rdx
0x180013254  and     rdx, rcx
0x180013257  lea     rcx, [rsp+218h+var_1D8]
0x18001325c  call    ??0?$CComQIPtr@UIMSVidAudioRendererDevices@@$1?_GUID_c5702cd4_9b79_11d3_b654_00c04f79498e@@3U__s_GUID@@B@ATL@@QEAA@PEAUIMSVidAudioRendererDevices@@@Z; ATL::CComQIPtr<IMSVidAudioRendererDevices,&__s_GUID const _GUID_c5702cd4_9b79_11d3_b654_00c04f79498e>::CComQIPtr<IMSVidAudioRendererDevices,&__s_GUID const _GUID_c5702cd4_9b79_11d3_b654_00c04f79498e>(IMSVidAudioRendererDevices *)
0x180013261  nop
0x180013262  mov     rdx, [rsp+218h+var_1D8]
0x180013267  test    rdx, rdx
0x18001326a  jz      short loc_180013287
0x18001326c  mov     rcx, [rsp+218h+var_1B0]
0x180013271  mov     rax, [rcx]
0x180013274  mov     r9d, edi
0x180013277  xor     r8d, r8d
0x18001327a  mov     rax, [rax+30h]
0x18001327e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013283  mov     ebx, eax
0x180013285  jmp     short loc_18001328C
0x180013287  mov     ebx, 8007000Eh
0x18001328c  lea     rcx, [rsp+218h+var_1D8]
0x180013291  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180013296  nop
0x180013297  lea     rcx, [rsp+218h+hKey]; this
0x18001329c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800132a1  jmp     loc_180013431
0x1800132a6  mov     ebx, [rsp+218h+var_1A8]
0x1800132aa  jmp     short loc_180013297
0x1800132ac  mov     ebx, dword ptr [rsp+218h+var_1D0]
0x1800132b0  jmp     short loc_180013297
0x1800132b2  mov     ebx, 8007000Eh
0x1800132b7  jmp     short loc_180013297
0x1800132b9  mov     ebx, 8000FFFFh
0x1800132be  jmp     short loc_180013297
0x1800132c0  mov     rdx, [rsi+8]
0x1800132c4  lea     rcx, [rsp+218h+var_1D8]
0x1800132c9  call    ??0?$CComQIPtr@UIPersistPropertyBag@@$1?_GUID_37d84f60_42cb_11ce_8135_00aa004bb851@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IPersistPropertyBag,&__s_GUID const _GUID_37d84f60_42cb_11ce_8135_00aa004bb851>::CComQIPtr<IPersistPropertyBag,&__s_GUID const _GUID_37d84f60_42cb_11ce_8135_00aa004bb851>(IUnknown *)
0x1800132ce  nop
0x1800132cf  cmp     [rsp+218h+var_1D8], r12
0x1800132d4  jz      loc_180013426
0x1800132da  mov     [rsp+218h+hKey], r12
0x1800132df  mov     [rsp+218h+var_1C0], r12
0x1800132e4  mov     [rsp+218h+var_1B8], r12
0x1800132e9  mov     esi, 2001Fh
0x1800132ee  mov     [rsp+218h+var_1F0], esi; unsigned int
0x1800132f2  mov     r8, rdi; lpSubKey
0x1800132f5  mov     rdx, [r15+58h]; hKey
0x1800132f9  lea     rcx, [rsp+218h+hKey]; this
0x1800132fe  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180013303  mov     ebx, eax
0x180013305  test    eax, eax
0x180013307  jz      short loc_18001331D
0x180013309  jle     loc_18001341B
0x18001330f  movzx   ebx, ax
0x180013312  or      ebx, 80070000h
0x180013318  jmp     loc_18001341B
0x18001331d  xorps   xmm0, xmm0
0x180013320  movups  xmmword ptr [rsp+218h+var_180.Data1], xmm0
0x180013328  mov     rcx, [rsp+218h+var_1D8]
0x18001332d  mov     rax, [rcx]
0x180013330  lea     rdx, [rsp+218h+var_180]
0x180013338  mov     rax, [rax+18h]
0x18001333c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013341  test    eax, eax
0x180013343  js      loc_1800134B0
0x180013349  mov     r8d, 40h ; '@'; cchMax
0x18001334f  lea     rdx, [rsp+218h+Data]; lpsz
0x180013357  lea     rcx, [rsp+218h+var_180]; rguid
0x18001335f  call    cs:__imp_StringFromGUID2
0x180013365  test    eax, eax
0x180013367  jz      loc_1800134B0
0x18001336d  lea     rcx, [rsp+218h+Data]
0x180013375  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013379  inc     rax
0x18001337c  cmp     [rcx+rax*2], r12w
0x180013381  jnz     short loc_180013379
0x180013383  add     eax, eax
0x180013385  mov     [rsp+218h+cbData], eax; cbData
0x180013389  lea     r9, [rsp+218h+Data]; lpData
0x180013391  mov     edi, 1
0x180013396  mov     r8d, edi; dwType
0x180013399  xor     edx, edx; lpSubKey
0x18001339b  mov     rcx, [rsp+218h+hKey]; hKey
0x1800133a0  call    cs:__imp_RegSetValueW
0x1800133a6  mov     ebx, eax
0x1800133a8  test    eax, eax
0x1800133aa  jnz     loc_180013309
0x1800133b0  lea     ecx, [rdi+6Fh]; Size
0x1800133b3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800133b8  mov     qword ptr [rsp+218h+rguid.Data1], rax
0x1800133c0  mov     [rsp+218h+cbData], esi; unsigned int
0x1800133c4  xor     r9d, r9d; unsigned int
0x1800133c7  xor     r8d, r8d; unsigned __int16 *
0x1800133ca  mov     rdx, [rsp+218h+hKey]; HKEY
0x1800133cf  mov     rcx, rax; this
0x1800133d2  call    ??0CRegBag@@QEAA@PEAUHKEY__@@PEBGKK@Z; CRegBag::CRegBag(HKEY__ *,ushort const *,ulong,ulong)
0x1800133d7  nop
0x1800133d8  mov     rdx, rax
0x1800133db  lea     rcx, [rsp+218h+var_1D0]
0x1800133e0  call    ??0?$CComQIPtr@UIMSVidAudioRendererDevices@@$1?_GUID_c5702cd4_9b79_11d3_b654_00c04f79498e@@3U__s_GUID@@B@ATL@@QEAA@PEAUIMSVidAudioRendererDevices@@@Z; ATL::CComQIPtr<IMSVidAudioRendererDevices,&__s_GUID const _GUID_c5702cd4_9b79_11d3_b654_00c04f79498e>::CComQIPtr<IMSVidAudioRendererDevices,&__s_GUID const _GUID_c5702cd4_9b79_11d3_b654_00c04f79498e>(IMSVidAudioRendererDevices *)
0x1800133e5  nop
0x1800133e6  mov     rdx, [rsp+218h+var_1D0]
0x1800133eb  test    rdx, rdx
0x1800133ee  jz      short loc_18001340B
0x1800133f0  mov     rcx, [rsp+218h+var_1D8]
0x1800133f5  mov     rax, [rcx]
0x1800133f8  mov     r9d, edi
0x1800133fb  xor     r8d, r8d
0x1800133fe  mov     rax, [rax+30h]
0x180013402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013407  mov     ebx, eax
0x180013409  jmp     short loc_180013410
0x18001340b  mov     ebx, 8007000Eh
0x180013410  lea     rcx, [rsp+218h+var_1D0]
0x180013415  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18001341a  nop
0x18001341b  lea     rcx, [rsp+218h+hKey]; this
0x180013420  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180013425  nop
0x180013426  lea     rcx, [rsp+218h+var_1D8]
0x18001342b  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180013430  nop
0x180013431  lea     rcx, [rsp+218h+var_1B0]
0x180013436  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18001343b  mov     eax, ebx
0x18001343d  mov     rcx, [rsp+218h+var_48]
0x180013445  xor     rcx, rsp; StackCookie
0x180013448  call    __security_check_cookie
0x18001344d  add     rsp, 1E8h
0x180013454  pop     r15
0x180013456  pop     r14
0x180013458  pop     r12
0x18001345a  pop     rdi
0x18001345b  pop     rsi
0x18001345c  pop     rbx
0x18001345d  retn
0x18001345e  lea     rcx, [rsp+218h+hKey]; this
0x180013463  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180013468  nop
0x180013469  lea     rcx, [rsp+218h+var_1D8]
0x18001346e  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x180013473  mov     ebx, [rsp+218h+var_1A4]
0x180013477  jmp     short loc_180013431
0x180013479  lea     rcx, [rsp+218h+hKey]; this
0x18001347e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180013483  nop
0x180013484  lea     rcx, [rsp+218h+var_1D8]
0x180013489  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x18001348e  mov     ebx, dword ptr [rsp+218h+var_1D0]
0x180013492  jmp     short loc_180013431
0x180013494  lea     rcx, [rsp+218h+hKey]; this
0x180013499  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001349e  nop
0x18001349f  lea     rcx, [rsp+218h+var_1D8]
0x1800134a4  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800134a9  mov     ebx, 8007000Eh
0x1800134ae  jmp     short loc_180013431
0x1800134b0  lea     rcx, [rsp+218h+hKey]; this
0x1800134b5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800134ba  nop
0x1800134bb  lea     rcx, [rsp+218h+var_1D8]
0x1800134c0  call    ??1?$CComPtr@UIEventInsert@@@ATL@@QEAA@XZ; ATL::CComPtr<IEventInsert>::~CComPtr<IEventInsert>(void)
0x1800134c5  mov     ebx, 8000FFFFh
0x1800134ca  jmp     loc_180013431
```
