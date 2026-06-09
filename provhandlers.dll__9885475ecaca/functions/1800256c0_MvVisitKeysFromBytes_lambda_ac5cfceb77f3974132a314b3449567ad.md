# MvVisitKeysFromBytes__lambda_ac5cfceb77f3974132a314b3449567ad_

- ea: `0x1800256c0`
- end: `0x180025b8d`
- name: `MvVisitKeysFromBytes__lambda_ac5cfceb77f3974132a314b3449567ad___`
- size: `1229`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180026240`

## callees

- `0x180012d80`
- `0x180015c3c`
- `0x1800256c0`
- `0x180025c04`
- `0x180025ee8`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800258ef`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180025922`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800258ef`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180025922`

## string_xrefs

- `0x180025a34`: `onecoreuap\admin\prov\multivariant\common\inc\MvProvisionDataHelper.h`
- `0x180025a61`: `onecoreuap\admin\prov\multivariant\common\inc\MvProvisionDataHelper.h`
- `0x180025a7c`: `onecoreuap\admin\prov\multivariant\common\inc\MvProvisionDataHelper.h`
- `0x180025a97`: `onecoreuap\admin\prov\multivariant\common\inc\MvProvisionDataHelper.h`
- `0x180025b00`: `onecoreuap\admin\prov\multivariant\common\inc\MvProvisionDataHelper.h`
- `0x180025b15`: `onecoreuap\admin\prov\multivariant\common\inc\MvProvisionDataHelper.h`
- `0x180025b2a`: `onecoreuap\admin\prov\multivariant\common\inc\MvProvisionDataHelper.h`
- `0x180025b3f`: `onecoreuap\admin\prov\multivariant\common\inc\MvProvisionDataHelper.h`
- `0x180025b51`: `onecoreuap\admin\prov\multivariant\common\inc\MvProvisionDataHelper.h`
- `0x180025b66`: `onecoreuap\admin\prov\multivariant\common\inc\MvProvisionDataHelper.h`
- `0x180025b7b`: `onecoreuap\admin\prov\multivariant\common\inc\MvProvisionDataHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall MvVisitKeysFromBytes__lambda_ac5cfceb77f3974132a314b3449567ad_(_DWORD *a1, int a2, __int64 a3)
{
  char v3; // al
  unsigned int v4; // r11d
  unsigned int v5; // r13d
  unsigned int v6; // ebx
  unsigned int v7; // eax
  char *v8; // r15
  unsigned __int64 v9; // rcx
  char *i; // rax
  __int64 v11; // r9
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rax
  unsigned int v14; // ecx
  unsigned int v15; // eax
  unsigned int v16; // edx
  unsigned int v17; // ebx
  char *v18; // r12
  unsigned __int64 v19; // rcx
  char *j; // rax
  __int64 v21; // r9
  unsigned __int64 v22; // rdx
  unsigned __int64 v23; // rax
  unsigned int v24; // r14d
  unsigned int v25; // ecx
  unsigned int v26; // eax
  __int64 *v27; // rsi
  __int64 *v28; // rax
  HRESULT v29; // eax
  __int64 *v30; // rax
  HRESULT ClassObject; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // r8
  __int64 v37; // rcx
  int ppv; // [rsp+20h] [rbp-38h]
  __int64 v40; // [rsp+30h] [rbp-28h] BYREF
  char v41[32]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  unsigned int v43; // [rsp+A0h] [rbp+48h]
  unsigned int v44; // [rsp+A8h] [rbp+50h]
  __int64 v45; // [rsp+B0h] [rbp+58h]
  __int64 v46; // [rsp+B8h] [rbp+60h] BYREF

  v45 = a3;
  if ( *a1 != a2 || (v3 = 0, *a1 < 0xCu) )
    v3 = 1;
  if ( v3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvProvisionDataHelper.h",
      (const char *)0x8000FFFFLL,
      ppv);
  v4 = a1[1];
  v43 = v4;
  if ( (_WORD)v4 != 1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvProvisionDataHelper.h",
      (const char *)0x8000FFFFLL,
      ppv);
  v5 = a1[2];
  v6 = a2 - 12;
  if ( !v5 && a2 != 12 || (LOBYTE(v7) = 0, (v6 & 1) != 0) )
    LOBYTE(v7) = 1;
  if ( (_BYTE)v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvProvisionDataHelper.h",
      (const char *)0x80070057LL,
      ppv);
  if ( v5 )
  {
    v44 = 0;
    v8 = (char *)(a1 + 3);
    while ( 1 )
    {
      if ( v6 < 2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x44,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvProvisionDataHelper.h",
          (const char *)0x80070057LL,
          ppv);
      if ( v8 )
      {
        v9 = (unsigned __int64)v6 >> 1;
        for ( i = v8; v9; --v9 )
        {
          if ( !*(_WORD *)i )
            break;
          i += 2;
        }
        v11 = v9 == 0 ? 0x80070057 : 0;
        if ( v9 )
          v12 = ((unsigned __int64)v6 >> 1) - v9;
        else
          v12 = 0;
        if ( v9 )
        {
          v13 = 2 * v12;
          goto LABEL_25;
        }
      }
      else
      {
        v11 = 2147942487LL;
      }
      v13 = 0;
LABEL_25:
      if ( (int)v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x47,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvProvisionDataHelper.h",
          (const char *)v11,
          ppv);
      v14 = v13;
      if ( v13 > 0xFFFFFFFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x49,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvProvisionDataHelper.h",
          v13 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
          ppv);
      v15 = v13 + 2;
      v16 = -1;
      if ( v14 + 2 >= v14 )
        v16 = v14 + 2;
      if ( v15 < v14 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4A,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvProvisionDataHelper.h",
          v15 < v14 ? (const char *)0x80070216LL : 0,
          ppv);
      v17 = v6 - v16;
      if ( v17 < 2 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x50,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvProvisionDataHelper.h",
          (const char *)0x80070057LL,
          ppv);
      v18 = &v8[v16];
      if ( v18 )
      {
        v19 = (unsigned __int64)v17 >> 1;
        for ( j = &v8[v16]; v19; --v19 )
        {
          if ( !*(_WORD *)j )
            break;
          j += 2;
        }
        v21 = v19 == 0 ? 0x80070057 : 0;
        if ( v19 )
          v22 = ((unsigned __int64)v17 >> 1) - v19;
        else
          v22 = 0;
        if ( v19 )
        {
          v23 = 2 * v22;
          goto LABEL_43;
        }
      }
      else
      {
        v21 = 2147942487LL;
      }
      v23 = 0;
LABEL_43:
      if ( (int)v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x52,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvProvisionDataHelper.h",
          (const char *)v21,
          ppv);
      v24 = -1;
      v25 = v23;
      if ( v23 > 0xFFFFFFFF )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x53,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvProvisionDataHelper.h",
          v23 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
          ppv);
      v26 = v23 + 2;
      if ( v25 + 2 >= v25 )
        v24 = v25 + 2;
      if ( v26 < v25 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x54,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvProvisionDataHelper.h",
          v26 < v25 ? (const char *)0x80070216LL : 0,
          ppv);
      v27 = *(__int64 **)a3;
      if ( !**(_QWORD **)a3 )
      {
        *(_DWORD *)(*(_QWORD *)(a3 + 8) + 16LL) = HIWORD(v4);
        if ( HIWORD(v4) )
        {
          v30 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IClassFactory>>(v27);
          ClassObject = CoGetClassObject(
                          &GUID_d83e8cbe_841d_4397_b6e4_f64f2e3ab469,
                          1u,
                          0,
                          &GUID_00000001_0000_0000_c000_000000000046,
                          (LPVOID *)v30);
          if ( ClassObject < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x2E,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
              (const char *)(unsigned int)ClassObject,
              ppv);
        }
        else
        {
          v28 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IClassFactory>>(v27);
          v29 = CoGetClassObject(
                  &GUID_38be0989_9830_49a8_985b_7741219fd0fb,
                  1u,
                  0,
                  &GUID_00000001_0000_0000_c000_000000000046,
                  (LPVOID *)v28);
          if ( v29 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x28,
              (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
              (const char *)(unsigned int)v29,
              ppv);
        }
      }
      v46 = 0;
      v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)*v27 + 24LL))(
              *v27,
              0,
              &GUID_401e2463_465f_4bc9_9dc9_c6daf36894b0,
              &v46);
      if ( v32 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x34,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
          (const char *)(unsigned int)v32,
          ppv);
      v33 = (*(__int64 (__fastcall **)(__int64, char *, char *))(*(_QWORD *)v46 + 24LL))(v46, v8, v18);
      if ( v33 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x35,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
          (const char *)(unsigned int)v33,
          ppv);
      v40 = 0;
      v34 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v46 + 40LL))(v46, &v40);
      if ( v34 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x39,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
          (const char *)(unsigned int)v34,
          ppv);
      v35 = std::_Tree_buy<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>::_Buynode<unsigned short * &,Microsoft::WRL::ComPtr<IMVKey> &>(
              *(_QWORD *)(v45 + 8),
              &v40,
              &v46);
      std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_nohint<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(
        *(__int64 ***)(v45 + 8),
        (__int64)v41,
        v36,
        (const wchar_t **)(v35 + 32),
        (_QWORD *)v35);
      v37 = v46;
      if ( v46 )
      {
        v46 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
      v8 = &v18[v24];
      v6 = v17 - v24;
      v7 = v44 + 1;
      v44 = v7;
      if ( v7 >= v5 )
        return v7;
      a3 = v45;
      v4 = v43;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x1800256c0  mov     [rsp-40h+arg_10], r8
0x1800256c5  push    rbp
0x1800256c6  push    rbx
0x1800256c7  push    rsi
0x1800256c8  push    rdi
0x1800256c9  push    r12
0x1800256cb  push    r13
0x1800256cd  push    r14
0x1800256cf  push    r15
0x1800256d1  mov     rbp, rsp
0x1800256d4  sub     rsp, 58h
0x1800256d8  xor     esi, esi
0x1800256da  lea     r14d, [rsi+1]
0x1800256de  cmp     [rcx], edx
0x1800256e0  jnz     short loc_1800256EA
0x1800256e2  cmp     dword ptr [rcx], 0Ch
0x1800256e5  mov     al, sil
0x1800256e8  jnb     short loc_1800256ED
0x1800256ea  mov     al, r14b
0x1800256ed  mov     r10, [rbp+40h]
0x1800256f1  test    al, al
0x1800256f3  jnz     loc_180025A5B
0x1800256f9  mov     r11d, [rcx+4]
0x1800256fd  mov     [rbp+arg_0], r11d
0x180025701  mov     rax, [rbp+40h]
0x180025705  cmp     r14w, r11w
0x180025709  jnz     loc_180025A76
0x18002570f  mov     r13d, [rcx+8]
0x180025713  lea     ebx, [rdx-0Ch]
0x180025716  test    r13d, r13d
0x180025719  jnz     short loc_18002571F
0x18002571b  test    ebx, ebx
0x18002571d  jnz     short loc_18002572B
0x18002571f  mov     eax, ebx
0x180025721  and     eax, r14d
0x180025724  test    al, al
0x180025726  mov     al, sil
0x180025729  jz      short loc_18002572E
0x18002572b  mov     al, r14b
0x18002572e  mov     r10, [rbp+40h]
0x180025732  test    al, al
0x180025734  jnz     loc_180025A91
0x18002573a  test    r13d, r13d
0x18002573d  jz      loc_180025A20
0x180025743  mov     [rbp+arg_8], esi
0x180025746  lea     r15, [rcx+0Ch]
0x18002574a  mov     edi, 80070057h
0x18002574f  mov     r12d, 0FFFFFFFFh
0x180025755  mov     rcx, [rbp+40h]; this
0x180025759  cmp     ebx, 2
0x18002575c  jb      loc_180025A31
0x180025762  test    r15, r15
0x180025765  jz      short loc_1800257A9
0x180025767  mov     ecx, ebx
0x180025769  shr     rcx, 1
0x18002576c  mov     rax, r15
0x18002576f  mov     rdx, rcx
0x180025772  jz      short loc_180025782
0x180025774  cmp     [rax], si
0x180025777  jz      short loc_180025782
0x180025779  add     rax, 2
0x18002577d  sub     rcx, r14
0x180025780  jnz     short loc_180025774
0x180025782  mov     rax, rcx
0x180025785  neg     rax
0x180025788  sbb     r9d, r9d
0x18002578b  not     r9d
0x18002578e  and     r9d, edi
0x180025791  test    rcx, rcx
0x180025794  jz      short loc_18002579B
0x180025796  sub     rdx, rcx
0x180025799  jmp     short loc_18002579E
0x18002579b  mov     rdx, rsi
0x18002579e  test    rcx, rcx
0x1800257a1  jz      short loc_1800257AC
0x1800257a3  lea     rax, [rdx+rdx]
0x1800257a7  jmp     short loc_1800257AF
0x1800257a9  mov     r9d, edi; char *
0x1800257ac  mov     rax, rsi
0x1800257af  mov     rcx, [rbp+40h]; this
0x1800257b3  test    r9d, r9d
0x1800257b6  js      loc_180025B7B
0x1800257bc  cmp     rax, r12
0x1800257bf  mov     ecx, eax
0x1800257c1  jbe     short loc_1800257C6
0x1800257c3  mov     ecx, r12d
0x1800257c6  cmp     r12, rax
0x1800257c9  sbb     r9d, r9d
0x1800257cc  and     r9d, 80070216h; char *
0x1800257d3  mov     r10, [rbp+40h]
0x1800257d7  cmp     rax, r12
0x1800257da  ja      loc_180025B66
0x1800257e0  lea     eax, [rcx+2]
0x1800257e3  mov     edx, r12d
0x1800257e6  cmp     eax, ecx
0x1800257e8  cmovnb  edx, eax
0x1800257eb  sbb     r9d, r9d
0x1800257ee  and     r9d, 80070216h; char *
0x1800257f5  mov     r10, [rbp+40h]
0x1800257f9  cmp     eax, ecx
0x1800257fb  jb      loc_180025B51
0x180025801  sub     ebx, edx
0x180025803  mov     rcx, [rbp+40h]; this
0x180025807  cmp     ebx, 2
0x18002580a  jb      loc_180025B3C
0x180025810  mov     r12d, edx
0x180025813  add     r12, r15
0x180025816  jz      short loc_18002585A
0x180025818  mov     ecx, ebx
0x18002581a  shr     rcx, 1
0x18002581d  mov     rax, r12
0x180025820  mov     rdx, rcx
0x180025823  jz      short loc_180025833
0x180025825  cmp     [rax], si
0x180025828  jz      short loc_180025833
0x18002582a  add     rax, 2
0x18002582e  sub     rcx, r14
0x180025831  jnz     short loc_180025825
0x180025833  mov     rax, rcx
0x180025836  neg     rax
0x180025839  sbb     r9d, r9d
0x18002583c  not     r9d
0x18002583f  and     r9d, edi
0x180025842  test    rcx, rcx
0x180025845  jz      short loc_18002584C
0x180025847  sub     rdx, rcx
0x18002584a  jmp     short loc_18002584F
0x18002584c  mov     rdx, rsi
0x18002584f  test    rcx, rcx
0x180025852  jz      short loc_18002585D
0x180025854  lea     rax, [rdx+rdx]
0x180025858  jmp     short loc_180025860
0x18002585a  mov     r9d, edi; char *
0x18002585d  mov     rax, rsi
0x180025860  mov     rcx, [rbp+40h]; this
0x180025864  test    r9d, r9d
0x180025867  js      loc_180025B2A
0x18002586d  mov     r14d, 0FFFFFFFFh
0x180025873  cmp     rax, r14
0x180025876  mov     ecx, eax
0x180025878  jbe     short loc_18002587D
0x18002587a  mov     ecx, r14d
0x18002587d  cmp     r14, rax
0x180025880  sbb     r9d, r9d
0x180025883  mov     edx, 80070216h
0x180025888  and     r9d, edx; char *
0x18002588b  mov     r10, [rbp+40h]
0x18002588f  cmp     rax, r14
0x180025892  ja      loc_180025B15
0x180025898  lea     eax, [rcx+2]
0x18002589b  cmp     eax, ecx
0x18002589d  cmovnb  r14d, eax
0x1800258a1  sbb     r9d, r9d
0x1800258a4  and     r9d, edx; char *
0x1800258a7  mov     r10, [rbp+40h]
0x1800258ab  cmp     eax, ecx
0x1800258ad  jb      loc_180025B00
0x1800258b3  mov     rsi, [r8]
0x1800258b6  cmp     qword ptr [rsi], 0
0x1800258ba  jnz     short loc_180025934
0x1800258bc  mov     ecx, r11d
0x1800258bf  shr     ecx, 10h
0x1800258c2  mov     rax, [r8+8]
0x1800258c6  mov     [rax+10h], ecx
0x1800258c9  test    ecx, ecx
0x1800258cb  mov     rcx, rsi
0x1800258ce  jnz     short loc_180025903
0x1800258d0  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIClassFactory@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIClassFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IClassFactory>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IClassFactory>>)
0x1800258d5  mov     qword ptr [rsp+58h+ppv], rax; int
0x1800258da  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x1800258e1  xor     r8d, r8d; pvReserved
0x1800258e4  lea     edx, [r8+1]; dwClsContext
0x1800258e8  lea     rcx, _GUID_38be0989_9830_49a8_985b_7741219fd0fb; rclsid
0x1800258ef  call    cs:__imp_CoGetClassObject
0x1800258f5  mov     rcx, [rbp+40h]; this
0x1800258f9  test    eax, eax
0x1800258fb  js      loc_180025A46
0x180025901  jmp     short loc_180025934
0x180025903  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIClassFactory@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIClassFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IClassFactory>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IClassFactory>>)
0x180025908  mov     qword ptr [rsp+58h+ppv], rax; int
0x18002590d  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180025914  xor     r8d, r8d; pvReserved
0x180025917  lea     edx, [r8+1]; dwClsContext
0x18002591b  lea     rcx, _GUID_d83e8cbe_841d_4397_b6e4_f64f2e3ab469; rclsid
0x180025922  call    cs:__imp_CoGetClassObject
0x180025928  mov     rcx, [rbp+40h]; this
0x18002592c  test    eax, eax
0x18002592e  js      loc_180025AAC
0x180025934  mov     [rbp+arg_18], 0
0x18002593c  mov     rcx, [rsi]
0x18002593f  mov     rax, [rcx]
0x180025942  lea     r9, [rbp+arg_18]
0x180025946  lea     r8, _GUID_401e2463_465f_4bc9_9dc9_c6daf36894b0
0x18002594d  xor     edx, edx
0x18002594f  mov     rax, [rax+18h]
0x180025953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025958  mov     rcx, [rbp+40h]; this
0x18002595c  test    eax, eax
0x18002595e  js      loc_180025AEB
0x180025964  mov     rcx, [rbp+arg_18]
0x180025968  mov     rax, [rcx]
0x18002596b  mov     r8, r12
0x18002596e  mov     rdx, r15
0x180025971  mov     rax, [rax+18h]
0x180025975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002597a  mov     rcx, [rbp+40h]; this
0x18002597e  test    eax, eax
0x180025980  js      loc_180025AD6
0x180025986  mov     [rbp+var_28], 0
0x18002598e  mov     rcx, [rbp+arg_18]
0x180025992  mov     rax, [rcx]
0x180025995  lea     rdx, [rbp+var_28]
0x180025999  mov     rax, [rax+28h]
0x18002599d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259a2  mov     rcx, [rbp+40h]; this
0x1800259a6  test    eax, eax
0x1800259a8  js      loc_180025AC1
0x1800259ae  lea     r8, [rbp+arg_18]
0x1800259b2  lea     rdx, [rbp+var_28]
0x1800259b6  mov     rsi, [rbp+arg_10]
0x1800259ba  mov     rcx, [rsi+8]
0x1800259be  call    ??$_Buynode@AEAPEAGAEAV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@?$_Tree_buy@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@1@AEAPEAGAEAV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@Z; std::_Tree_buy<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>::_Buynode<ushort * &,Microsoft::WRL::ComPtr<IMVKey> &>(ushort * &,Microsoft::WRL::ComPtr<IMVKey> &)
0x1800259c3  lea     r9, [rax+20h]
0x1800259c7  mov     qword ptr [rsp+58h+ppv], rax
0x1800259cc  lea     rdx, [rbp+var_20]
0x1800259d0  mov     rcx, [rsi+8]
0x1800259d4  call    ??$_Insert_nohint@AEAU?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@1@PEAU?$_Tree_node@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::_Insert_nohint<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *>(bool,std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>> &,std::_Tree_node<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>,void *> *)
0x1800259d9  nop
0x1800259da  mov     rcx, [rbp+arg_18]
0x1800259de  xor     esi, esi
0x1800259e0  test    rcx, rcx
0x1800259e3  jz      short loc_1800259F6
0x1800259e5  mov     [rbp+arg_18], rsi
0x1800259e9  mov     rax, [rcx]
0x1800259ec  mov     rax, [rax+10h]
0x1800259f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259f5  nop
0x1800259f6  mov     r15d, r14d
0x1800259f9  add     r15, r12
0x1800259fc  sub     ebx, r14d
0x1800259ff  mov     eax, [rbp+arg_8]
0x180025a02  mov     r14d, 1
0x180025a08  add     eax, r14d
0x180025a0b  mov     [rbp+arg_8], eax
0x180025a0e  cmp     eax, r13d
0x180025a11  jnb     short loc_180025A20
0x180025a13  mov     r8, [rbp+arg_10]
0x180025a17  mov     r11d, [rbp+arg_0]
0x180025a1b  jmp     loc_18002574F
0x180025a20  add     rsp, 58h
0x180025a24  pop     r15
0x180025a26  pop     r14
0x180025a28  pop     r13
0x180025a2a  pop     r12
0x180025a2c  pop     rdi
0x180025a2d  pop     rsi
0x180025a2e  pop     rbx
0x180025a2f  pop     rbp
0x180025a30  retn
0x180025a31  mov     r9d, edi; char *
0x180025a34  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180025a3b  mov     edx, 44h ; 'D'; void *
0x180025a40  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025a46  mov     r9d, eax; char *
0x180025a49  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180025a50  mov     edx, 28h ; '('; void *
0x180025a55  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025a5b  mov     r9d, 8000FFFFh; char *
0x180025a61  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180025a68  mov     edx, 32h ; '2'; void *
0x180025a6d  mov     rcx, r10; this
0x180025a70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025a76  mov     r9d, 8000FFFFh; char *
0x180025a7c  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180025a83  mov     edx, 38h ; '8'; void *
0x180025a88  mov     rcx, rax; this
0x180025a8b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025a91  mov     r9d, 80070057h; char *
0x180025a97  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180025a9e  mov     edx, 40h ; '@'; void *
0x180025aa3  mov     rcx, r10; this
0x180025aa6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025aac  mov     r9d, eax; char *
0x180025aaf  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180025ab6  mov     edx, 2Eh ; '.'; void *
0x180025abb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025ac1  mov     r9d, eax; char *
0x180025ac4  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180025acb  mov     edx, 39h ; '9'; void *
0x180025ad0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025ad6  mov     r9d, eax; char *
0x180025ad9  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180025ae0  mov     edx, 35h ; '5'; void *
0x180025ae5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025aeb  mov     r9d, eax; char *
0x180025aee  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180025af5  mov     edx, 34h ; '4'; void *
0x180025afa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025b00  lea     r8, aOnecoreuapAdmi_3; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180025b07  mov     edx, 54h ; 'T'; void *
  ... truncated ...
```
