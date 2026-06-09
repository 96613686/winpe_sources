# SettingStore::HandleActiveXCompatKeys(SettingStore::CKey *,SettingStore::HIVEID,ulong,SettingStore::KEYNODE const *)

- ea: `0x180072284`
- end: `0x180072681`
- name: `?HandleActiveXCompatKeys@SettingStore@@YAJPEAVCKey@1@W4HIVEID@1@KPEBUKEYNODE@1@@Z`
- size: `1021`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800727d8`

## callees

- `0x18001e108`
- `0x18004cb70`
- `0x180054400`
- `0x1800544ec`
- `0x180072284`
- `0x1800727b4`
- `0x1800727d8`
- `0x18007308c`
- `0x1800753c8`
- `0x180076f4c`
- `0x18007720c`
- `0x180077238`
- `0x180077570`
- `0x18007759c`
- `0x1800778ac`
- `0x1800778e4`
- `0x180077910`
- `0x180083c10`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072565`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072615`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072648`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072565`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072615`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072648`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072573`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072623`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072656`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072573`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072623`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072656`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800725f0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800725f0`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007237b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18007237b`

## string_xrefs

- `0x1800722b1`: `Compatibility Flags`

## pseudocode

```c
__int64 __fastcall SettingStore::HandleActiveXCompatKeys(
        struct SettingStore::CKey *a1,
        unsigned int a2,
        const struct SettingStore::KEYNODE **a3,
        SettingStore::SchemaStore *a4)
{
  struct SettingStore::CKey *v4; // r14
  unsigned int v5; // ebx
  unsigned int v6; // r12d
  int v7; // edi
  const struct SettingStore::KEYNODE *v8; // r8
  SettingStore::SchemaStore *v9; // rsi
  unsigned int v10; // edx
  const struct SettingStore::KEYNODE *v11; // r8
  const OLECHAR *v12; // rax
  const unsigned __int16 *v13; // rax
  SettingStore::SchemaStore *v14; // r14
  int i; // eax
  const struct SettingStore::VALUENODE **v16; // r8
  const unsigned __int16 *v17; // rax
  const struct SettingStore::DEFAULTINFO **v18; // r9
  SettingStore::SchemaStore *v19; // r15
  const struct SettingStore::DEFAULTINFO *v20; // r8
  int *v21; // r13
  __int64 v22; // rax
  int (__fastcall *v23)(SettingStore::SchemaStore *, __int64, __int64); // rbx
  __int64 v24; // rax
  void (__fastcall *v25)(SettingStore::SchemaStore *, __int64); // rbx
  __int64 v26; // rax
  int v27; // eax
  unsigned int v28; // ebx
  __int64 (__fastcall *v29)(SettingStore::SchemaStore *, __int64, _QWORD, _QWORD, int *, int); // rdi
  __int64 v30; // rax
  void *v31; // rbx
  HANDLE ProcessHeap; // rax
  const WCHAR *v33; // rax
  void *v34; // rbx
  HANDLE v35; // rax
  void *v36; // rbx
  HANDLE v37; // rax
  SettingStore::SchemaStore *v39; // [rsp+48h] [rbp-B8h] BYREF
  int v40; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v41; // [rsp+54h] [rbp-ACh]
  SettingStore::SchemaStore *v42; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v43[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v44[2]; // [rsp+70h] [rbp-90h] BYREF
  struct SettingStore::CKey *v45; // [rsp+78h] [rbp-88h]
  GUID pclsid; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v48; // [rsp+98h] [rbp-68h]
  int v49; // [rsp+A0h] [rbp-60h]
  __int16 v50; // [rsp+A4h] [rbp-5Ch]
  __int64 v51; // [rsp+1B0h] [rbp+B0h] BYREF
  LPVOID lpMem; // [rsp+1B8h] [rbp+B8h]
  int v53; // [rsp+1C0h] [rbp+C0h]
  __int16 v54; // [rsp+1C4h] [rbp+C4h]
  _OWORD v55[2]; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int64 v56; // [rsp+2F0h] [rbp+1F0h]

  v4 = a1;
  v45 = a1;
  v5 = a2;
  v55[0] = *(_OWORD *)L"Compatibility Flags";
  v41 = a2;
  v56 = *(_QWORD *)L"ags";
  v6 = (unsigned int)a3;
  pclsid = 0;
  v7 = 0;
  v40 = 0;
  v55[1] = *(_OWORD *)L"ility Flags";
  v42 = 0;
  if ( (int)SettingStore::SchemaStore::GetFirstChildKeyNodeFromKeyNode(
              a4,
              (const struct SettingStore::KEYNODE *)&v42,
              a3) >= 0 )
  {
    do
    {
      v9 = v42;
      if ( SettingStore::SchemaStore::IsKeyInTarget((SettingStore::SchemaStore *)v6, (unsigned int)v42, v8)
        && !SettingStore::SchemaStore::IsKeyInPreserve((SettingStore::SchemaStore *)v6, v10, v11) )
      {
        v47 = *(_QWORD *)v9;
        v48 = 0;
        v49 = 0;
        v50 = 0;
        if ( *((_WORD *)v9 + 5) == 0xFFFF
          && (v12 = (const OLECHAR *)SettingStore::CUTF8ToWideChar::operator unsigned short const *(&v47),
              CLSIDFromString(v12, &pclsid) >= 0) )
        {
          v39 = 0;
          v13 = (const unsigned __int16 *)SettingStore::CUTF8ToWideChar::operator unsigned short const *(&v47);
          v7 = SettingStore::CRegistryStore::CreateKeyRelative(
                 (SettingStore::CRegistryStore *)&SettingStore::g_SettingStore,
                 v4,
                 v13,
                 7u,
                 &v39);
          if ( v7 >= 0 )
          {
            v14 = v39;
            v43[0] = 0;
            v43[1] = 0;
            for ( i = (*(__int64 (__fastcall **)(SettingStore::SchemaStore *, _QWORD *))(*(_QWORD *)v39 + 56LL))(
                        v39,
                        v43);
                  ;
                  i = SettingStore::CRegistryStore::DeleteKeyRecurse(
                        (SettingStore::CRegistryStore *)&SettingStore::g_SettingStore,
                        v14,
                        v17) )
            {
              v7 = i;
              if ( i < 0 )
                break;
              v17 = SettingStore::CEnum::Next((SettingStore::CEnum *)v43);
              if ( !v17 )
                break;
            }
            v39 = 0;
            if ( (int)SettingStore::SchemaStore::GetFirstValueNodeFromKeyNode(
                        v9,
                        (const struct SettingStore::KEYNODE *)&v39,
                        v16) >= 0 )
            {
              do
              {
                *(_QWORD *)v44 = 0;
                v19 = v39;
                if ( SettingStore::SchemaStore::GetDefaultByValueNode(
                       v39,
                       (const struct SettingStore::VALUENODE *)v6,
                       (unsigned int)v44,
                       v18) >= 0 )
                {
                  v21 = *(int **)v44;
                  if ( SettingStore::SchemaStore::IsDefaultResettable((SettingStore::SchemaStore *)v6, v44[0], v20) )
                  {
                    if ( (unsigned __int8)SettingStore::IsNodeNameEqual_Ascii<char const *>(*(_QWORD *)v19, v55) )
                    {
                      v22 = *(_QWORD *)v19;
                      lpMem = 0;
                      v53 = 0;
                      v54 = 0;
                      v51 = v22;
                      v23 = *(int (__fastcall **)(SettingStore::SchemaStore *, __int64, __int64))(*(_QWORD *)v14 + 8LL);
                      v24 = SettingStore::CUTF8ToWideChar::operator unsigned short const *(&v51);
                      if ( v23(v14, v24, 1) < 0 )
                      {
                        v25 = *(void (__fastcall **)(SettingStore::SchemaStore *, __int64))(*(_QWORD *)v14 + 48LL);
                        v26 = SettingStore::CUTF8ToWideChar::operator unsigned short const *(&v51);
                        v25(v14, v26);
                      }
                      v27 = *v21;
                      v40 = v27;
                      if ( v27 && (v27 & 0x400) != 0 )
                      {
                        v28 = *((char *)v21 + 12);
                        v29 = **(__int64 (__fastcall ***)(SettingStore::SchemaStore *, __int64, _QWORD, _QWORD, int *, int))v14;
                        v30 = SettingStore::CUTF8ToWideChar::operator unsigned short const *(&v51);
                        v7 = v29(v14, v30, v28, 0, &v40, 4);
                      }
                      v31 = lpMem;
                      ProcessHeap = GetProcessHeap();
                      HeapFree(ProcessHeap, 0, v31);
                      v5 = v41;
                    }
                    else
                    {
                      SettingStore::ResetRegValue(v5, v19, v6);
                    }
                  }
                }
              }
              while ( (int)SettingStore::SchemaStore::GetSiblingValueNodeFromValueNode(
                             v19,
                             (const struct SettingStore::VALUENODE *)&v39,
                             (const struct SettingStore::VALUENODE **)v20) >= 0 );
            }
            (*(void (__fastcall **)(SettingStore::SchemaStore *))(*(_QWORD *)v14 + 80LL))(v14);
            SettingStore::CEnum::Clear((SettingStore::CEnum *)v43);
            v4 = v45;
          }
        }
        else
        {
          v33 = (const WCHAR *)SettingStore::CUTF8ToWideChar::operator unsigned short const *(&v47);
          if ( CompareStringW(0x7Fu, 1u, v33, -1, L"%s", -1) != 2 )
          {
            v7 = SettingStore::RecurseResetRegistrySettings(v4, v5, v9, v6);
            if ( v7 < 0 )
            {
              v36 = v48;
              v37 = GetProcessHeap();
              HeapFree(v37, 0, v36);
              return (unsigned int)v7;
            }
          }
        }
        v34 = v48;
        v35 = GetProcessHeap();
        HeapFree(v35, 0, v34);
        v5 = v41;
      }
    }
    while ( (int)SettingStore::SchemaStore::GetSiblingKeyNodeFromKeyNode(
                   v9,
                   (const struct SettingStore::KEYNODE *)&v42,
                   (const struct SettingStore::KEYNODE **)v11) >= 0 );
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180072284  push    rbp
0x180072286  push    rbx
0x180072287  push    rsi
0x180072288  push    rdi
0x180072289  push    r12
0x18007228b  push    r13
0x18007228d  push    r14
0x18007228f  push    r15
0x180072291  lea     rbp, [rsp-208h]
0x180072299  sub     rsp, 308h
0x1800722a0  mov     rax, cs:__security_cookie
0x1800722a7  xor     rax, rsp
0x1800722aa  mov     [rbp+240h+var_48], rax
0x1800722b1  movups  xmm0, xmmword ptr cs:aCompatibilityF; "Compatibility Flags"
0x1800722b8  xor     r15d, r15d
0x1800722bb  mov     r14, rcx
0x1800722be  movups  xmm1, xmmword ptr cs:aCompatibilityF+10h; "ility Flags"
0x1800722c5  mov     [rsp+340h+var_2C8], rcx
0x1800722ca  mov     ebx, edx
0x1800722cc  movups  [rbp+240h+var_70], xmm0
0x1800722d3  mov     rcx, r9; this
0x1800722d6  mov     [rsp+340h+var_2EC], edx
0x1800722da  movsd   xmm0, qword ptr cs:aCompatibilityF+20h; "ags"
0x1800722e2  lea     rdx, [rsp+340h+var_2E8]; struct SettingStore::KEYNODE *
0x1800722e7  movsd   [rbp+240h+var_50], xmm0
0x1800722ef  mov     r12d, r8d
0x1800722f2  xorps   xmm0, xmm0
0x1800722f5  mov     [rsp+340h+var_300], r15d
0x1800722fa  movups  xmmword ptr [rbp+240h+pclsid.Data1], xmm0
0x1800722fe  mov     edi, r15d
0x180072301  mov     [rsp+340h+var_2F0], r15d
0x180072306  movups  [rbp+240h+var_60], xmm1
0x18007230d  mov     [rsp+340h+var_2E8], r15
0x180072312  call    ?GetFirstChildKeyNodeFromKeyNode@SchemaStore@SettingStore@@YAJPEBUKEYNODE@2@PEAPEBU32@@Z; SettingStore::SchemaStore::GetFirstChildKeyNodeFromKeyNode(SettingStore::KEYNODE const *,SettingStore::KEYNODE const * *)
0x180072317  test    eax, eax
0x180072319  js      loc_18007265C
0x18007231f  or      r13d, 0FFFFFFFFh
0x180072323  mov     rsi, [rsp+340h+var_2E8]
0x180072328  mov     ecx, r12d; this
0x18007232b  mov     rdx, rsi; unsigned int
0x18007232e  call    ?IsKeyInTarget@SchemaStore@SettingStore@@YA_NKPEBUKEYNODE@2@@Z; SettingStore::SchemaStore::IsKeyInTarget(ulong,SettingStore::KEYNODE const *)
0x180072333  test    al, al
0x180072335  jz      loc_18007262D
0x18007233b  mov     ecx, r12d; this
0x18007233e  call    ?IsKeyInPreserve@SchemaStore@SettingStore@@YA_NKPEBUKEYNODE@2@@Z; SettingStore::SchemaStore::IsKeyInPreserve(ulong,SettingStore::KEYNODE const *)
0x180072343  test    al, al
0x180072345  jnz     loc_18007262D
0x18007234b  mov     rax, [rsi]
0x18007234e  mov     [rbp+240h+var_2B0], rax
0x180072352  mov     [rbp+240h+var_2A8], r15
0x180072356  mov     [rbp+240h+var_2A0], r15d
0x18007235a  mov     [rbp+240h+var_29C], 0
0x180072360  cmp     [rsi+0Ah], r13w
0x180072365  jnz     loc_1800725C8
0x18007236b  lea     rcx, [rbp+240h+var_2B0]
0x18007236f  call    ??BCUTF8ToWideChar@SettingStore@@QEAAPEBGXZ; SettingStore::CUTF8ToWideChar::operator ushort const *(void)
0x180072374  mov     rcx, rax; lpsz
0x180072377  lea     rdx, [rbp+240h+pclsid]; pclsid
0x18007237b  call    cs:__imp_CLSIDFromString
0x180072381  test    eax, eax
0x180072383  js      loc_1800725C8
0x180072389  lea     rcx, [rbp+240h+var_2B0]
0x18007238d  mov     [rsp+340h+var_2F8], r15
0x180072392  call    ??BCUTF8ToWideChar@SettingStore@@QEAAPEBGXZ; SettingStore::CUTF8ToWideChar::operator ushort const *(void)
0x180072397  mov     r8, rax; unsigned __int16 *
0x18007239a  lea     rcx, ?g_SettingStore@SettingStore@@3VCRegistryStore@1@A; this
0x1800723a1  lea     rax, [rsp+340h+var_2F8]
0x1800723a6  mov     r9d, 7; unsigned int
0x1800723ac  mov     rdx, r14; struct SettingStore::CKey *
0x1800723af  mov     [rsp+340h+lpString2], rax; struct SettingStore::CKey **
0x1800723b4  call    ?CreateKeyRelative@CRegistryStore@SettingStore@@UEAAJPEAVCKey@2@PEBGKPEAPEAV32@@Z; SettingStore::CRegistryStore::CreateKeyRelative(SettingStore::CKey *,ushort const *,ulong,SettingStore::CKey * *)
0x1800723b9  mov     edi, eax
0x1800723bb  test    eax, eax
0x1800723bd  js      loc_180072611
0x1800723c3  mov     r14, [rsp+340h+var_2F8]
0x1800723c8  lea     rdx, [rsp+340h+var_2E0]
0x1800723cd  mov     [rsp+340h+var_2E0], r15
0x1800723d2  mov     rcx, r14
0x1800723d5  mov     [rsp+340h+var_2D8], 0
0x1800723de  mov     rax, [r14]
0x1800723e1  mov     rax, [rax+38h]
0x1800723e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800723ea  jmp     short loc_1800723FE
0x1800723ec  mov     r8, rax; unsigned __int16 *
0x1800723ef  lea     rcx, ?g_SettingStore@SettingStore@@3VCRegistryStore@1@A; this
0x1800723f6  mov     rdx, r14; struct SettingStore::CKey *
0x1800723f9  call    ?DeleteKeyRecurse@CRegistryStore@SettingStore@@UEAAJPEAVCKey@2@PEBG@Z; SettingStore::CRegistryStore::DeleteKeyRecurse(SettingStore::CKey *,ushort const *)
0x1800723fe  mov     edi, eax
0x180072400  test    eax, eax
0x180072402  js      short loc_180072413
0x180072404  lea     rcx, [rsp+340h+var_2E0]; this
0x180072409  call    ?Next@CEnum@SettingStore@@QEAAPEBGXZ; SettingStore::CEnum::Next(void)
0x18007240e  test    rax, rax
0x180072411  jnz     short loc_1800723EC
0x180072413  lea     rdx, [rsp+340h+var_2F8]; struct SettingStore::KEYNODE *
0x180072418  mov     [rsp+340h+var_2F8], r15
0x18007241d  mov     rcx, rsi; this
0x180072420  call    ?GetFirstValueNodeFromKeyNode@SchemaStore@SettingStore@@YAJPEBUKEYNODE@2@PEAPEBUVALUENODE@2@@Z; SettingStore::SchemaStore::GetFirstValueNodeFromKeyNode(SettingStore::KEYNODE const *,SettingStore::VALUENODE const * *)
0x180072425  test    eax, eax
0x180072427  js      loc_1800725A8
0x18007242d  mov     qword ptr [rsp+340h+var_2D0], r15
0x180072432  lea     r8, [rsp+340h+var_2D0]; unsigned int
0x180072437  mov     r15, [rsp+340h+var_2F8]
0x18007243c  mov     edx, r12d; struct SettingStore::VALUENODE *
0x18007243f  mov     rcx, r15; this
0x180072442  call    ?GetDefaultByValueNode@SchemaStore@SettingStore@@YAJPEBUVALUENODE@2@KPEAPEBUDEFAULTINFO@2@@Z; SettingStore::SchemaStore::GetDefaultByValueNode(SettingStore::VALUENODE const *,ulong,SettingStore::DEFAULTINFO const * *)
0x180072447  test    eax, eax
0x180072449  js      loc_18007258C
0x18007244f  mov     r13, qword ptr [rsp+340h+var_2D0]
0x180072454  mov     ecx, r12d; this
0x180072457  mov     rdx, r13; unsigned int
0x18007245a  call    ?IsDefaultResettable@SchemaStore@SettingStore@@YA_NKPEBUDEFAULTINFO@2@@Z; SettingStore::SchemaStore::IsDefaultResettable(ulong,SettingStore::DEFAULTINFO const *)
0x18007245f  test    al, al
0x180072461  jz      loc_18007258C
0x180072467  mov     rcx, [r15]
0x18007246a  lea     rdx, [rbp+240h+var_70]
0x180072471  call    ??$IsNodeNameEqual_Ascii@PEBD@SettingStore@@YA_NQEBDPEBG@Z; SettingStore::IsNodeNameEqual_Ascii<char const *>(char const * const,ushort const *)
0x180072476  xor     ecx, ecx
0x180072478  test    al, al
0x18007247a  jz      loc_18007257F
0x180072480  mov     [rsp+340h+var_300], ecx
0x180072484  mov     rax, [r15]
0x180072487  mov     [rbp+240h+lpMem], rcx
0x18007248e  mov     [rbp+240h+var_180], ecx
0x180072494  mov     [rbp+240h+var_17C], cx
0x18007249b  lea     rcx, [rbp+240h+var_190]
0x1800724a2  mov     [rbp+240h+var_190], rax
0x1800724a9  mov     rax, [r14]
0x1800724ac  mov     rbx, [rax+8]
0x1800724b0  call    ??BCUTF8ToWideChar@SettingStore@@QEAAPEBGXZ; SettingStore::CUTF8ToWideChar::operator ushort const *(void)
0x1800724b5  xor     r9d, r9d
0x1800724b8  mov     [rsp+340h+cchCount2], 4
0x1800724c0  lea     rcx, [rsp+340h+var_300]
0x1800724c5  mov     rdx, rax
0x1800724c8  mov     [rsp+340h+lpString2], rcx
0x1800724cd  mov     rax, rbx
0x1800724d0  mov     rcx, r14
0x1800724d3  lea     r8d, [r9+1]
0x1800724d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800724dc  test    eax, eax
0x1800724de  jns     short loc_180072509
0x1800724e0  mov     rax, [r14]
0x1800724e3  lea     rcx, [rbp+240h+var_190]
0x1800724ea  mov     rbx, [rax+30h]
0x1800724ee  call    ??BCUTF8ToWideChar@SettingStore@@QEAAPEBGXZ; SettingStore::CUTF8ToWideChar::operator ushort const *(void)
0x1800724f3  mov     rdx, rax
0x1800724f6  mov     rcx, r14
0x1800724f9  mov     rax, rbx
0x1800724fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072501  xor     ecx, ecx
0x180072503  mov     [rsp+340h+var_300], ecx
0x180072507  jmp     short loc_18007250D
0x180072509  mov     ecx, [rsp+340h+var_300]
0x18007250d  mov     eax, [r13+0]
0x180072511  mov     [rsp+340h+var_2F0], eax
0x180072515  cmp     ecx, eax
0x180072517  jz      short loc_18007255E
0x180072519  bt      eax, 0Ah
0x18007251d  jnb     short loc_18007255E
0x18007251f  mov     rax, [r14]
0x180072522  lea     rcx, [rbp+240h+var_190]
0x180072529  movsx   ebx, byte ptr [r13+0Ch]
0x18007252e  mov     rdi, [rax]
0x180072531  call    ??BCUTF8ToWideChar@SettingStore@@QEAAPEBGXZ; SettingStore::CUTF8ToWideChar::operator ushort const *(void)
0x180072536  lea     rcx, [rsp+340h+var_2F0]
0x18007253b  mov     [rsp+340h+cchCount2], 4
0x180072543  mov     [rsp+340h+lpString2], rcx
0x180072548  mov     rdx, rax
0x18007254b  mov     rcx, r14
0x18007254e  xor     r9d, r9d
0x180072551  mov     r8d, ebx
0x180072554  mov     rax, rdi
0x180072557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007255c  mov     edi, eax
0x18007255e  mov     rbx, [rbp+240h+lpMem]
0x180072565  call    cs:__imp_GetProcessHeap
0x18007256b  mov     r8, rbx; lpMem
0x18007256e  xor     edx, edx; dwFlags
0x180072570  mov     rcx, rax; hHeap
0x180072573  call    cs:__imp_HeapFree
0x180072579  mov     ebx, [rsp+340h+var_2EC]
0x18007257d  jmp     short loc_18007258C
0x18007257f  mov     r8d, r12d
0x180072582  mov     rdx, r15
0x180072585  mov     ecx, ebx
0x180072587  call    ?ResetRegValue@SettingStore@@YAJW4HIVEID@1@PEBUVALUENODE@1@K@Z; SettingStore::ResetRegValue(SettingStore::HIVEID,SettingStore::VALUENODE const *,ulong)
0x18007258c  lea     rdx, [rsp+340h+var_2F8]; struct SettingStore::VALUENODE *
0x180072591  mov     rcx, r15; this
0x180072594  call    ?GetSiblingValueNodeFromValueNode@SchemaStore@SettingStore@@YAJPEBUVALUENODE@2@PEAPEBU32@@Z; SettingStore::SchemaStore::GetSiblingValueNodeFromValueNode(SettingStore::VALUENODE const *,SettingStore::VALUENODE const * *)
0x180072599  xor     r15d, r15d
0x18007259c  test    eax, eax
0x18007259e  jns     loc_18007242D
0x1800725a4  or      r13d, 0FFFFFFFFh
0x1800725a8  mov     rax, [r14]
0x1800725ab  mov     rcx, r14
0x1800725ae  mov     rax, [rax+50h]
0x1800725b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800725b7  lea     rcx, [rsp+340h+var_2E0]; this
0x1800725bc  call    ?Clear@CEnum@SettingStore@@QEAAXXZ; SettingStore::CEnum::Clear(void)
0x1800725c1  mov     r14, [rsp+340h+var_2C8]
0x1800725c6  jmp     short loc_180072611
0x1800725c8  lea     rcx, [rbp+240h+var_2B0]
0x1800725cc  call    ??BCUTF8ToWideChar@SettingStore@@QEAAPEBGXZ; SettingStore::CUTF8ToWideChar::operator ushort const *(void)
0x1800725d1  mov     edx, 1; dwCmpFlags
0x1800725d6  mov     [rsp+340h+cchCount2], r13d; cchCount2
0x1800725db  mov     r8, rax; lpString1
0x1800725de  mov     r9d, r13d; cchCount1
0x1800725e1  lea     rax, aS_5; "%s"
0x1800725e8  mov     [rsp+340h+lpString2], rax; lpString2
0x1800725ed  lea     ecx, [rdx+7Eh]; Locale
0x1800725f0  call    cs:__imp_CompareStringW
0x1800725f6  cmp     eax, 2
0x1800725f9  jz      short loc_180072611
0x1800725fb  mov     r9d, r12d
0x1800725fe  mov     r8, rsi
0x180072601  mov     edx, ebx
0x180072603  mov     rcx, r14
0x180072606  call    ?RecurseResetRegistrySettings@SettingStore@@YAJPEAVCKey@1@W4HIVEID@1@PEBUKEYNODE@1@K@Z; SettingStore::RecurseResetRegistrySettings(SettingStore::CKey *,SettingStore::HIVEID,SettingStore::KEYNODE const *,ulong)
0x18007260b  mov     edi, eax
0x18007260d  test    eax, eax
0x18007260f  js      short loc_180072644
0x180072611  mov     rbx, [rbp+240h+var_2A8]
0x180072615  call    cs:__imp_GetProcessHeap
0x18007261b  mov     r8, rbx; lpMem
0x18007261e  xor     edx, edx; dwFlags
0x180072620  mov     rcx, rax; hHeap
0x180072623  call    cs:__imp_HeapFree
0x180072629  mov     ebx, [rsp+340h+var_2EC]
0x18007262d  lea     rdx, [rsp+340h+var_2E8]; struct SettingStore::KEYNODE *
0x180072632  mov     rcx, rsi; this
0x180072635  call    ?GetSiblingKeyNodeFromKeyNode@SchemaStore@SettingStore@@YAJPEBUKEYNODE@2@PEAPEBU32@@Z; SettingStore::SchemaStore::GetSiblingKeyNodeFromKeyNode(SettingStore::KEYNODE const *,SettingStore::KEYNODE const * *)
0x18007263a  test    eax, eax
0x18007263c  jns     loc_180072323
0x180072642  jmp     short loc_18007265C
0x180072644  mov     rbx, [rbp+240h+var_2A8]
0x180072648  call    cs:__imp_GetProcessHeap
0x18007264e  mov     r8, rbx; lpMem
0x180072651  xor     edx, edx; dwFlags
0x180072653  mov     rcx, rax; hHeap
0x180072656  call    cs:__imp_HeapFree
0x18007265c  mov     eax, edi
0x18007265e  mov     rcx, [rbp+240h+var_48]
0x180072665  xor     rcx, rsp; StackCookie
0x180072668  call    __security_check_cookie
0x18007266d  add     rsp, 308h
0x180072674  pop     r15
0x180072676  pop     r14
0x180072678  pop     r13
0x18007267a  pop     r12
0x18007267c  pop     rdi
0x18007267d  pop     rsi
0x18007267e  pop     rbx
0x18007267f  pop     rbp
0x180072680  retn
```
