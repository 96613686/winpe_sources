# SettingStore::RecurseResetRegistrySettings(SettingStore::CKey *,SettingStore::HIVEID,SettingStore::KEYNODE const *,ulong)

- ea: `0x1800727d8`
- end: `0x180072b96`
- name: `?RecurseResetRegistrySettings@SettingStore@@YAJPEAVCKey@1@W4HIVEID@1@PEBUKEYNODE@1@K@Z`
- size: `958`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180072284`
- `0x1800727d8`
- `0x18007333c`

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
- `0x180076e34`
- `0x18007720c`
- `0x180077238`
- `0x180077570`
- `0x18007759c`
- `0x1800778e4`
- `0x180077910`
- `0x180083c10`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007291e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072b7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007291e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180072b7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007292c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072b89`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007292c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180072b89`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180072a31`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180072a31`

## string_xrefs

- `0x180072805`: `ActiveX Compatibility`

## pseudocode

```c
__int64 __fastcall SettingStore::RecurseResetRegistrySettings(
        struct SettingStore::CKey *a1,
        unsigned int a2,
        __int64 *a3,
        unsigned int a4)
{
  unsigned int v8; // edx
  const struct SettingStore::KEYNODE *v9; // r8
  const struct SettingStore::VALUENODE **v10; // r8
  int i; // eax
  const struct SettingStore::VALUENODE **v12; // r8
  const unsigned __int16 *v13; // rax
  const struct SettingStore::KEYNODE *v14; // rdx
  int active; // edi
  void *v16; // rbx
  HANDLE ProcessHeap; // rax
  bool v19; // al
  struct SettingStore::CKey *v20; // rbx
  const struct SettingStore::VALUENODE **v21; // r8
  const unsigned __int16 *v22; // r14
  int j; // eax
  SettingStore::SchemaStore *v24; // r12
  const struct SettingStore::VALUENODE **v25; // r8
  const WCHAR *v26; // rax
  const struct SettingStore::KEYNODE **v27; // r8
  const struct SettingStore::KEYNODE *v28; // rdx
  SettingStore::SchemaStore *v29; // r14
  const struct SettingStore::KEYNODE **v30; // r8
  int k; // eax
  SettingStore::SchemaStore *v32; // r15
  const struct SettingStore::KEYNODE **v33; // r8
  const struct SettingStore::KEYNODE **v34; // r8
  const unsigned __int16 *v35; // r14
  void *v36; // rbx
  HANDLE v37; // rax
  SettingStore::SchemaStore *v38; // [rsp+30h] [rbp-D0h] BYREF
  struct SettingStore::CKey *v39; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v40; // [rsp+40h] [rbp-C0h]
  __int64 v41; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-A8h]
  int v43; // [rsp+60h] [rbp-A0h]
  __int16 v44; // [rsp+64h] [rbp-9Ch]
  WCHAR String2[24]; // [rsp+170h] [rbp+70h] BYREF

  v39 = 0;
  wcscpy(String2, L"ActiveX Compibility");
  if ( *((_WORD *)a3 + 4) != 0xFFFF
    && (dword_1800D4E0C[10 * *((__int16 *)a3 + 4)] & 0x200) != 0
    && !SettingStore::_fDeletePersonalSettings
    || SettingStore::SchemaStore::IsKeyInPreserve(
         (SettingStore::SchemaStore *)a4,
         (unsigned int)a3,
         (const struct SettingStore::KEYNODE *)a3)
    || !SettingStore::SchemaStore::IsKeyInTarget((SettingStore::SchemaStore *)a4, v8, v9) )
  {
    return 0;
  }
  v38 = 0;
  for ( i = SettingStore::SchemaStore::GetFirstValueNodeFromKeyNode(
              (SettingStore::SchemaStore *)a3,
              (const struct SettingStore::KEYNODE *)&v38,
              v10);
        i >= 0 && (int)SettingStore::ResetRegValue(a2, v38, a4) >= 0;
        i = SettingStore::SchemaStore::GetSiblingValueNodeFromValueNode(
              v38,
              (const struct SettingStore::VALUENODE *)&v38,
              v12) )
  {
    ;
  }
  v41 = *a3;
  lpMem = 0;
  v43 = 0;
  v44 = 0;
  v13 = (const unsigned __int16 *)SettingStore::CUTF8ToWideChar::operator unsigned short const *(&v41);
  active = SettingStore::CRegistryStore::CreateKeyRelative(
             (SettingStore::CRegistryStore *)&SettingStore::g_SettingStore,
             a1,
             v13,
             7u,
             &v39);
  if ( active < 0 )
  {
    v16 = lpMem;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v16);
    return 0;
  }
  v19 = SettingStore::SchemaStore::DoesKeyDeleteDirectSubKeys((SettingStore::SchemaStore *)a3, v14);
  v20 = v39;
  if ( v19 )
  {
    v39 = 0;
    v40 = 0;
    active = (*(__int64 (__fastcall **)(struct SettingStore::CKey *, struct SettingStore::CKey **))(*(_QWORD *)v20 + 64LL))(
               v20,
               &v39);
    if ( active >= 0 )
    {
LABEL_15:
      while ( 1 )
      {
        v22 = SettingStore::CEnum::Next((SettingStore::CEnum *)&v39);
        if ( !v22 )
          break;
        v38 = 0;
        for ( j = SettingStore::SchemaStore::GetFirstValueNodeFromKeyNode(
                    (SettingStore::SchemaStore *)a3,
                    (const struct SettingStore::KEYNODE *)&v38,
                    v21);
              j >= 0;
              j = SettingStore::SchemaStore::GetSiblingValueNodeFromValueNode(
                    v24,
                    (const struct SettingStore::VALUENODE *)&v38,
                    v25) )
        {
          v24 = v38;
          if ( (unsigned __int8)SettingStore::IsNodeNameEqual_Ascii<char const *>(*(_QWORD *)v38, v22) )
            goto LABEL_15;
        }
        active = (*(__int64 (__fastcall **)(struct SettingStore::CKey *, const unsigned __int16 *))(*(_QWORD *)v20 + 48LL))(
                   v20,
                   v22);
        if ( active < 0 )
          active = 0;
      }
    }
    SettingStore::CEnum::Clear((SettingStore::CEnum *)&v39);
  }
  v26 = (const WCHAR *)SettingStore::CUTF8ToWideChar::operator unsigned short const *(&v41);
  if ( CompareStringW(0x7Fu, 1u, v26, -1, String2, -1) == 2 )
  {
    active = SettingStore::HandleActiveXCompatKeys(
               v20,
               a2,
               (const struct SettingStore::KEYNODE **)a4,
               (SettingStore::SchemaStore *)a3);
  }
  else if ( active >= 0 )
  {
    v38 = 0;
    if ( (int)SettingStore::SchemaStore::GetFirstChildKeyNodeFromKeyNode(
                (SettingStore::SchemaStore *)a3,
                (const struct SettingStore::KEYNODE *)&v38,
                v27) < 0 )
    {
LABEL_32:
      if ( SettingStore::SchemaStore::DoesKeyDeleteDirectSubKeys((SettingStore::SchemaStore *)a3, v28) )
      {
        v39 = 0;
        v40 = 0;
        active = (*(__int64 (__fastcall **)(struct SettingStore::CKey *, struct SettingStore::CKey **))(*(_QWORD *)v20 + 56LL))(
                   v20,
                   &v39);
        if ( active >= 0 )
        {
LABEL_41:
          while ( 1 )
          {
            v35 = SettingStore::CEnum::Next((SettingStore::CEnum *)&v39);
            if ( !v35 )
              break;
            v38 = 0;
            for ( k = SettingStore::SchemaStore::GetFirstChildKeyNodeFromKeyNode(
                        (SettingStore::SchemaStore *)a3,
                        (const struct SettingStore::KEYNODE *)&v38,
                        v34);
                  k >= 0;
                  k = SettingStore::SchemaStore::GetSiblingKeyNodeFromKeyNode(
                        v32,
                        (const struct SettingStore::KEYNODE *)&v38,
                        v33) )
            {
              v32 = v38;
              if ( (unsigned __int8)SettingStore::IsNodeNameEqual_Ascii<char const *>(*(_QWORD *)v38, v35) )
                goto LABEL_41;
            }
            active = SettingStore::CRegistryStore::DeleteKeyRecurse(
                       (SettingStore::CRegistryStore *)&SettingStore::g_SettingStore,
                       v20,
                       v35);
            if ( active < 0 )
              active = 0;
          }
        }
        SettingStore::CEnum::Clear((SettingStore::CEnum *)&v39);
      }
    }
    else
    {
      while ( 1 )
      {
        v29 = v38;
        if ( !(unsigned __int8)SettingStore::IsNodeNameEqual_Ascii<char const *>(*(_QWORD *)v38, L"%s") )
        {
          active = SettingStore::RecurseResetRegistrySettings(v20, a2, v29, a4);
          if ( active < 0 )
            break;
        }
        if ( (int)SettingStore::SchemaStore::GetSiblingKeyNodeFromKeyNode(
                    v29,
                    (const struct SettingStore::KEYNODE *)&v38,
                    v30) < 0 )
          goto LABEL_32;
      }
    }
  }
  (*(void (__fastcall **)(struct SettingStore::CKey *))(*(_QWORD *)v20 + 80LL))(v20);
  v36 = lpMem;
  v37 = GetProcessHeap();
  HeapFree(v37, 0, v36);
  return (unsigned int)active;
}

```

## disassembly

```asm
0x1800727d8  push    rbp
0x1800727da  push    rbx
0x1800727db  push    rsi
0x1800727dc  push    rdi
0x1800727dd  push    r12
0x1800727df  push    r13
0x1800727e1  push    r14
0x1800727e3  push    r15
0x1800727e5  lea     rbp, [rsp-0B8h]
0x1800727ed  sub     rsp, 1B8h
0x1800727f4  mov     rax, cs:__security_cookie
0x1800727fb  xor     rax, rsp
0x1800727fe  mov     [rbp+0F0h+var_50], rax
0x180072805  movups  xmm0, xmmword ptr cs:aActivexCompati_0; "ActiveX Compatibility"
0x18007280c  xor     r12d, r12d
0x18007280f  or      r14d, 0FFFFFFFFh
0x180072813  mov     r15d, r9d
0x180072816  mov     rsi, r8
0x180072819  mov     r13d, edx
0x18007281c  mov     rbx, rcx
0x18007281f  movups  xmm1, xmmword ptr cs:aActivexCompati_0+10h; "Compatibility"
0x180072826  mov     [rsp+1F0h+var_1B8], r12
0x18007282b  movups  xmmword ptr [rbp+0F0h+String2], xmm0
0x18007282f  movups  xmm0, xmmword ptr cs:aActivexCompati_0+1Ch; "ibility"
0x180072836  movups  [rbp+0F0h+var_70], xmm1
0x18007283d  movups  [rbp+0F0h+var_70+0Ch], xmm0
0x180072844  cmp     [r8+8], r14w
0x180072849  jz      short loc_180072871
0x18007284b  movsx   rax, word ptr [r8+8]
0x180072850  lea     rcx, [rax+rax*4]
0x180072854  lea     rax, dword_1800D4E0C
0x18007285b  test    dword ptr [rax+rcx*8], 200h
0x180072862  jz      short loc_180072871
0x180072864  cmp     cs:?_fDeletePersonalSettings@SettingStore@@3HA, r12d; int SettingStore::_fDeletePersonalSettings
0x18007286b  jz      loc_180072932
0x180072871  mov     rdx, rsi; unsigned int
0x180072874  mov     ecx, r15d; this
0x180072877  call    ?IsKeyInPreserve@SchemaStore@SettingStore@@YA_NKPEBUKEYNODE@2@@Z; SettingStore::SchemaStore::IsKeyInPreserve(ulong,SettingStore::KEYNODE const *)
0x18007287c  test    al, al
0x18007287e  jnz     loc_180072932
0x180072884  mov     ecx, r15d; this
0x180072887  call    ?IsKeyInTarget@SchemaStore@SettingStore@@YA_NKPEBUKEYNODE@2@@Z; SettingStore::SchemaStore::IsKeyInTarget(ulong,SettingStore::KEYNODE const *)
0x18007288c  test    al, al
0x18007288e  jz      loc_180072932
0x180072894  lea     rdx, [rsp+1F0h+var_1C0]; struct SettingStore::KEYNODE *
0x180072899  mov     [rsp+1F0h+var_1C0], r12
0x18007289e  mov     rcx, rsi; this
0x1800728a1  call    ?GetFirstValueNodeFromKeyNode@SchemaStore@SettingStore@@YAJPEBUKEYNODE@2@PEAPEBUVALUENODE@2@@Z; SettingStore::SchemaStore::GetFirstValueNodeFromKeyNode(SettingStore::KEYNODE const *,SettingStore::VALUENODE const * *)
0x1800728a6  jmp     short loc_1800728CB
0x1800728a8  mov     rdx, [rsp+1F0h+var_1C0]
0x1800728ad  mov     r8d, r15d
0x1800728b0  mov     ecx, r13d
0x1800728b3  call    ?ResetRegValue@SettingStore@@YAJW4HIVEID@1@PEBUVALUENODE@1@K@Z; SettingStore::ResetRegValue(SettingStore::HIVEID,SettingStore::VALUENODE const *,ulong)
0x1800728b8  test    eax, eax
0x1800728ba  js      short loc_1800728CF
0x1800728bc  mov     rcx, [rsp+1F0h+var_1C0]; this
0x1800728c1  lea     rdx, [rsp+1F0h+var_1C0]; struct SettingStore::VALUENODE *
0x1800728c6  call    ?GetSiblingValueNodeFromValueNode@SchemaStore@SettingStore@@YAJPEBUVALUENODE@2@PEAPEBU32@@Z; SettingStore::SchemaStore::GetSiblingValueNodeFromValueNode(SettingStore::VALUENODE const *,SettingStore::VALUENODE const * *)
0x1800728cb  test    eax, eax
0x1800728cd  jns     short loc_1800728A8
0x1800728cf  mov     rax, [rsi]
0x1800728d2  lea     rcx, [rsp+1F0h+var_1A0]
0x1800728d7  mov     [rsp+1F0h+var_1A0], rax
0x1800728dc  mov     [rsp+1F0h+lpMem], r12
0x1800728e1  mov     [rsp+1F0h+var_190], r12d
0x1800728e6  mov     [rsp+1F0h+var_18C], r12w
0x1800728ec  call    ??BCUTF8ToWideChar@SettingStore@@QEAAPEBGXZ; SettingStore::CUTF8ToWideChar::operator ushort const *(void)
0x1800728f1  mov     r8, rax; unsigned __int16 *
0x1800728f4  lea     rcx, ?g_SettingStore@SettingStore@@3VCRegistryStore@1@A; this
0x1800728fb  lea     rax, [rsp+1F0h+var_1B8]
0x180072900  mov     r9d, 7; unsigned int
0x180072906  mov     rdx, rbx; struct SettingStore::CKey *
0x180072909  mov     [rsp+1F0h+lpString2], rax; struct SettingStore::CKey **
0x18007290e  call    ?CreateKeyRelative@CRegistryStore@SettingStore@@UEAAJPEAVCKey@2@PEBGKPEAPEAV32@@Z; SettingStore::CRegistryStore::CreateKeyRelative(SettingStore::CKey *,ushort const *,ulong,SettingStore::CKey * *)
0x180072913  mov     edi, eax
0x180072915  test    eax, eax
0x180072917  jns     short loc_180072957
0x180072919  mov     rbx, [rsp+1F0h+lpMem]
0x18007291e  call    cs:__imp_GetProcessHeap
0x180072924  mov     r8, rbx; lpMem
0x180072927  xor     edx, edx; dwFlags
0x180072929  mov     rcx, rax; hHeap
0x18007292c  call    cs:__imp_HeapFree
0x180072932  xor     eax, eax
0x180072934  mov     rcx, [rbp+0F0h+var_50]
0x18007293b  xor     rcx, rsp; StackCookie
0x18007293e  call    __security_check_cookie
0x180072943  add     rsp, 1B8h
0x18007294a  pop     r15
0x18007294c  pop     r14
0x18007294e  pop     r13
0x180072950  pop     r12
0x180072952  pop     rdi
0x180072953  pop     rsi
0x180072954  pop     rbx
0x180072955  pop     rbp
0x180072956  retn
0x180072957  mov     rcx, rsi; this
0x18007295a  call    ?DoesKeyDeleteDirectSubKeys@SchemaStore@SettingStore@@YA_NPEBUKEYNODE@2@@Z; SettingStore::SchemaStore::DoesKeyDeleteDirectSubKeys(SettingStore::KEYNODE const *)
0x18007295f  mov     rbx, [rsp+1F0h+var_1B8]
0x180072964  test    al, al
0x180072966  jz      loc_180072A0B
0x18007296c  mov     [rsp+1F0h+var_1B8], r12
0x180072971  lea     rdx, [rsp+1F0h+var_1B8]
0x180072976  mov     [rsp+1F0h+var_1B0], r12
0x18007297b  mov     rcx, rbx
0x18007297e  mov     rax, [rbx]
0x180072981  mov     rax, [rax+40h]
0x180072985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007298a  mov     edi, eax
0x18007298c  test    eax, eax
0x18007298e  js      short loc_180072A01
0x180072990  lea     rcx, [rsp+1F0h+var_1B8]; this
0x180072995  call    ?Next@CEnum@SettingStore@@QEAAPEBGXZ; SettingStore::CEnum::Next(void)
0x18007299a  mov     r14, rax
0x18007299d  test    rax, rax
0x1800729a0  jz      short loc_1800729FD
0x1800729a2  lea     rdx, [rsp+1F0h+var_1C0]; struct SettingStore::KEYNODE *
0x1800729a7  mov     [rsp+1F0h+var_1C0], r12
0x1800729ac  mov     rcx, rsi; this
0x1800729af  call    ?GetFirstValueNodeFromKeyNode@SchemaStore@SettingStore@@YAJPEBUKEYNODE@2@PEAPEBUVALUENODE@2@@Z; SettingStore::SchemaStore::GetFirstValueNodeFromKeyNode(SettingStore::KEYNODE const *,SettingStore::VALUENODE const * *)
0x1800729b4  jmp     short loc_1800729D8
0x1800729b6  mov     r12, [rsp+1F0h+var_1C0]
0x1800729bb  mov     rcx, [r12]
0x1800729bf  call    ??$IsNodeNameEqual_Ascii@PEBD@SettingStore@@YA_NQEBDPEBG@Z; SettingStore::IsNodeNameEqual_Ascii<char const *>(char const * const,ushort const *)
0x1800729c4  test    al, al
0x1800729c6  jnz     short loc_1800729F8
0x1800729c8  lea     rdx, [rsp+1F0h+var_1C0]; struct SettingStore::VALUENODE *
0x1800729cd  mov     rcx, r12; this
0x1800729d0  call    ?GetSiblingValueNodeFromValueNode@SchemaStore@SettingStore@@YAJPEBUVALUENODE@2@PEAPEBU32@@Z; SettingStore::SchemaStore::GetSiblingValueNodeFromValueNode(SettingStore::VALUENODE const *,SettingStore::VALUENODE const * *)
0x1800729d5  xor     r12d, r12d
0x1800729d8  mov     rdx, r14
0x1800729db  test    eax, eax
0x1800729dd  jns     short loc_1800729B6
0x1800729df  mov     rax, [rbx]
0x1800729e2  mov     rcx, rbx
0x1800729e5  mov     rax, [rax+30h]
0x1800729e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800729ee  test    eax, eax
0x1800729f0  mov     edi, eax
0x1800729f2  cmovs   edi, r12d
0x1800729f6  jmp     short loc_180072990
0x1800729f8  xor     r12d, r12d
0x1800729fb  jmp     short loc_180072990
0x1800729fd  or      r14d, 0FFFFFFFFh
0x180072a01  lea     rcx, [rsp+1F0h+var_1B8]; this
0x180072a06  call    ?Clear@CEnum@SettingStore@@QEAAXXZ; SettingStore::CEnum::Clear(void)
0x180072a0b  lea     rcx, [rsp+1F0h+var_1A0]
0x180072a10  call    ??BCUTF8ToWideChar@SettingStore@@QEAAPEBGXZ; SettingStore::CUTF8ToWideChar::operator ushort const *(void)
0x180072a15  mov     edx, 1; dwCmpFlags
0x180072a1a  mov     [rsp+1F0h+cchCount2], r14d; cchCount2
0x180072a1f  mov     r8, rax; lpString1
0x180072a22  mov     r9d, r14d; cchCount1
0x180072a25  lea     rax, [rbp+0F0h+String2]
0x180072a29  mov     [rsp+1F0h+lpString2], rax; lpString2
0x180072a2e  lea     ecx, [rdx+7Eh]; Locale
0x180072a31  call    cs:__imp_CompareStringW
0x180072a37  cmp     eax, 2
0x180072a3a  jnz     short loc_180072A54
0x180072a3c  mov     r9, rsi
0x180072a3f  mov     r8d, r15d
0x180072a42  mov     edx, r13d
0x180072a45  mov     rcx, rbx
0x180072a48  call    ?HandleActiveXCompatKeys@SettingStore@@YAJPEAVCKey@1@W4HIVEID@1@KPEBUKEYNODE@1@@Z; SettingStore::HandleActiveXCompatKeys(SettingStore::CKey *,SettingStore::HIVEID,ulong,SettingStore::KEYNODE const *)
0x180072a4d  mov     edi, eax
0x180072a4f  jmp     loc_180072B67
0x180072a54  test    edi, edi
0x180072a56  js      loc_180072B67
0x180072a5c  lea     rdx, [rsp+1F0h+var_1C0]; struct SettingStore::KEYNODE *
0x180072a61  mov     [rsp+1F0h+var_1C0], r12
0x180072a66  mov     rcx, rsi; this
0x180072a69  call    ?GetFirstChildKeyNodeFromKeyNode@SchemaStore@SettingStore@@YAJPEBUKEYNODE@2@PEAPEBU32@@Z; SettingStore::SchemaStore::GetFirstChildKeyNodeFromKeyNode(SettingStore::KEYNODE const *,SettingStore::KEYNODE const * *)
0x180072a6e  test    eax, eax
0x180072a70  js      short loc_180072ABE
0x180072a72  mov     r14, [rsp+1F0h+var_1C0]
0x180072a77  lea     rdx, aS_5; "%s"
0x180072a7e  mov     rcx, [r14]
0x180072a81  call    ??$IsNodeNameEqual_Ascii@PEBD@SettingStore@@YA_NQEBDPEBG@Z; SettingStore::IsNodeNameEqual_Ascii<char const *>(char const * const,ushort const *)
0x180072a86  test    al, al
0x180072a88  jnz     short loc_180072AA5
0x180072a8a  mov     r9d, r15d
0x180072a8d  mov     r8, r14
0x180072a90  mov     edx, r13d
0x180072a93  mov     rcx, rbx
0x180072a96  call    ?RecurseResetRegistrySettings@SettingStore@@YAJPEAVCKey@1@W4HIVEID@1@PEBUKEYNODE@1@K@Z; SettingStore::RecurseResetRegistrySettings(SettingStore::CKey *,SettingStore::HIVEID,SettingStore::KEYNODE const *,ulong)
0x180072a9b  mov     edi, eax
0x180072a9d  test    eax, eax
0x180072a9f  js      loc_180072B67
0x180072aa5  lea     rdx, [rsp+1F0h+var_1C0]; struct SettingStore::KEYNODE *
0x180072aaa  mov     rcx, r14; this
0x180072aad  call    ?GetSiblingKeyNodeFromKeyNode@SchemaStore@SettingStore@@YAJPEBUKEYNODE@2@PEAPEBU32@@Z; SettingStore::SchemaStore::GetSiblingKeyNodeFromKeyNode(SettingStore::KEYNODE const *,SettingStore::KEYNODE const * *)
0x180072ab2  test    eax, eax
0x180072ab4  jns     short loc_180072A72
0x180072ab6  test    edi, edi
0x180072ab8  js      loc_180072B67
0x180072abe  mov     rcx, rsi; this
0x180072ac1  call    ?DoesKeyDeleteDirectSubKeys@SchemaStore@SettingStore@@YA_NPEBUKEYNODE@2@@Z; SettingStore::SchemaStore::DoesKeyDeleteDirectSubKeys(SettingStore::KEYNODE const *)
0x180072ac6  test    al, al
0x180072ac8  jz      loc_180072B67
0x180072ace  mov     [rsp+1F0h+var_1B8], r12
0x180072ad3  lea     rdx, [rsp+1F0h+var_1B8]
0x180072ad8  mov     [rsp+1F0h+var_1B0], 0
0x180072ae1  mov     rcx, rbx
0x180072ae4  mov     rax, [rbx]
0x180072ae7  mov     rax, [rax+38h]
0x180072aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072af0  mov     edi, eax
0x180072af2  test    eax, eax
0x180072af4  js      short loc_180072B5D
0x180072af6  jmp     short loc_180072B4B
0x180072af8  lea     rdx, [rsp+1F0h+var_1C0]; struct SettingStore::KEYNODE *
0x180072afd  mov     [rsp+1F0h+var_1C0], r12
0x180072b02  mov     rcx, rsi; this
0x180072b05  call    ?GetFirstChildKeyNodeFromKeyNode@SchemaStore@SettingStore@@YAJPEBUKEYNODE@2@PEAPEBU32@@Z; SettingStore::SchemaStore::GetFirstChildKeyNodeFromKeyNode(SettingStore::KEYNODE const *,SettingStore::KEYNODE const * *)
0x180072b0a  jmp     short loc_180072B2D
0x180072b0c  mov     r15, [rsp+1F0h+var_1C0]
0x180072b11  mov     rdx, r14
0x180072b14  mov     rcx, [r15]
0x180072b17  call    ??$IsNodeNameEqual_Ascii@PEBD@SettingStore@@YA_NQEBDPEBG@Z; SettingStore::IsNodeNameEqual_Ascii<char const *>(char const * const,ushort const *)
0x180072b1c  test    al, al
0x180072b1e  jnz     short loc_180072B4B
0x180072b20  lea     rdx, [rsp+1F0h+var_1C0]; struct SettingStore::KEYNODE *
0x180072b25  mov     rcx, r15; this
0x180072b28  call    ?GetSiblingKeyNodeFromKeyNode@SchemaStore@SettingStore@@YAJPEBUKEYNODE@2@PEAPEBU32@@Z; SettingStore::SchemaStore::GetSiblingKeyNodeFromKeyNode(SettingStore::KEYNODE const *,SettingStore::KEYNODE const * *)
0x180072b2d  test    eax, eax
0x180072b2f  jns     short loc_180072B0C
0x180072b31  mov     r8, r14; unsigned __int16 *
0x180072b34  lea     rcx, ?g_SettingStore@SettingStore@@3VCRegistryStore@1@A; this
0x180072b3b  mov     rdx, rbx; struct SettingStore::CKey *
0x180072b3e  call    ?DeleteKeyRecurse@CRegistryStore@SettingStore@@UEAAJPEAVCKey@2@PEBG@Z; SettingStore::CRegistryStore::DeleteKeyRecurse(SettingStore::CKey *,ushort const *)
0x180072b43  test    eax, eax
0x180072b45  mov     edi, eax
0x180072b47  cmovs   edi, r12d
0x180072b4b  lea     rcx, [rsp+1F0h+var_1B8]; this
0x180072b50  call    ?Next@CEnum@SettingStore@@QEAAPEBGXZ; SettingStore::CEnum::Next(void)
0x180072b55  mov     r14, rax
0x180072b58  test    rax, rax
0x180072b5b  jnz     short loc_180072AF8
0x180072b5d  lea     rcx, [rsp+1F0h+var_1B8]; this
0x180072b62  call    ?Clear@CEnum@SettingStore@@QEAAXXZ; SettingStore::CEnum::Clear(void)
0x180072b67  mov     rax, [rbx]
0x180072b6a  mov     rcx, rbx
0x180072b6d  mov     rax, [rax+50h]
0x180072b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072b76  mov     rbx, [rsp+1F0h+lpMem]
0x180072b7b  call    cs:__imp_GetProcessHeap
0x180072b81  mov     r8, rbx; lpMem
0x180072b84  xor     edx, edx; dwFlags
0x180072b86  mov     rcx, rax; hHeap
0x180072b89  call    cs:__imp_HeapFree
0x180072b8f  mov     eax, edi
0x180072b91  jmp     loc_180072934
```
