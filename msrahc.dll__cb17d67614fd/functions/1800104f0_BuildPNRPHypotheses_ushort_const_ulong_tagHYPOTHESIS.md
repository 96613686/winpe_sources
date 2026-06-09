# BuildPNRPHypotheses(ushort const *,ulong *,tagHYPOTHESIS * *)

- ea: `0x1800104f0`
- end: `0x180010712`
- name: `?BuildPNRPHypotheses@@YAJPEBGPEAKPEAPEAUtagHYPOTHESIS@@@Z`
- size: `546`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *, struct tagHYPOTHESIS **)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d730`

## callees

- `0x180006b04`
- `0x18000d42c`
- `0x18000f2d4`
- `0x18000f4a8`
- `0x18000f560`
- `0x1800104f0`
- `0x180010f58`
- `0x1800121d8`
- `0x180014660`
- `0x1800184c8`
- `0x18001865c`
- `0x180018730`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001061b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001061b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010656`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010656`

## pseudocode

```c
__int64 __fastcall BuildPNRPHypotheses(const unsigned __int16 *a1, unsigned int *a2, struct tagHYPOTHESIS **a3)
{
  unsigned int v6; // esi
  const struct _EVENT_DESCRIPTOR *v7; // rdx
  CEventLogger *v8; // rcx
  signed int v9; // ebx
  struct _attribute_t *v10; // rax
  const struct _EVENT_DESCRIPTOR *v11; // rdx
  CEventLogger *v12; // rcx
  unsigned int *v13; // r9
  struct _attribute_t *v14; // rax
  const struct _EVENT_DESCRIPTOR *v15; // rdx
  CEventLogger *v16; // rcx
  unsigned __int64 v17; // rbx
  unsigned __int16 *v18; // rax
  const struct _EVENT_DESCRIPTOR *v19; // rdx
  CEventLogger *v20; // rcx
  signed int v21; // eax
  const struct _EVENT_DESCRIPTOR *v22; // rdx
  CEventLogger *v23; // rcx
  unsigned __int16 *v25[2]; // [rsp+30h] [rbp-89h] BYREF
  int v26; // [rsp+40h] [rbp-79h]
  __int128 v27; // [rsp+48h] [rbp-71h]
  unsigned __int16 *v28; // [rsp+58h] [rbp-61h] BYREF
  int v29; // [rsp+60h] [rbp-59h]
  int v30; // [rsp+68h] [rbp-51h]
  unsigned __int64 v31; // [rsp+120h] [rbp+67h] BYREF

  *(_OWORD *)v25 = 0;
  v26 = 0;
  v27 = 0;
  *a2 = 0;
  *a3 = 0;
  v6 = 3;
  if ( !a1 )
    v6 = 1;
  _hypothesis_builder::FreeAll((_hypothesis_builder *)v25);
  v9 = _hypothesis_builder::SetName(v25, L"PnrpHelperClass");
  if ( v9 >= 0 && (v9 = _hypothesis_builder::SetCount((_hypothesis_builder *)v25, v6), v9 >= 0) )
  {
    v10 = _attribute_t::_attribute_t((_attribute_t *)&v28, L"Global_", L"cloudname");
    v9 = _hypothesis_builder::SetAt((_hypothesis_builder *)v25, 0, v10);
    _attribute_t::FreeAll((_attribute_t *)&v28);
    if ( v9 >= 0 )
    {
      if ( a1 )
      {
        v14 = _attribute_t::_attribute_t((_attribute_t *)&v28, a1, L"peername");
        v9 = _hypothesis_builder::SetAt((_hypothesis_builder *)v25, 1u, v14);
        _attribute_t::FreeAll((_attribute_t *)&v28);
        if ( v9 < 0 )
        {
          CEventLogger::LogError(
            v16,
            v15,
            L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
            0x8Fu,
            L"BuildPNRPHypotheses",
            v9);
          goto LABEL_18;
        }
        CoTaskMemFree(0);
        v28 = 0;
        v31 = 0;
        if ( (int)StringCchLengthW(L"publishmode", 0xFFFEu, &v31) >= 0 )
        {
          v17 = v31;
          v18 = (unsigned __int16 *)CoTaskMemAlloc(2 * v31 + 2);
          v28 = v18;
          if ( v18 )
            StringCchCopyW(v18, v17 + 1, L"publishmode");
        }
        v29 = 1;
        v30 = 0;
        v9 = _hypothesis_builder::SetAt((_hypothesis_builder *)v25, 2u, (struct _attribute_t *)&v28);
        _attribute_t::FreeAll((_attribute_t *)&v28);
        if ( v9 < 0 )
        {
          CEventLogger::LogError(
            v20,
            v19,
            L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
            0x92u,
            L"BuildPNRPHypotheses",
            v9);
          goto LABEL_18;
        }
      }
      v21 = _hypothesis_builder::Detach((_hypothesis_builder *)v25, a2, a3, v13);
      v9 = v21;
      if ( v21 < 0 )
        CEventLogger::LogError(
          v23,
          v22,
          L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
          0x96u,
          L"BuildPNRPHypotheses",
          v21);
    }
    else
    {
      CEventLogger::LogError(
        v12,
        v11,
        L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
        0x8Au,
        L"BuildPNRPHypotheses",
        v9);
    }
  }
  else
  {
    CEventLogger::LogError(
      v8,
      v7,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x87u,
      L"BuildPNRPHypotheses",
      v9);
  }
LABEL_18:
  _hypothesis_builder::~_hypothesis_builder((_hypothesis_builder *)v25);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800104f0  mov     [rsp-8+arg_8], rbx
0x1800104f5  mov     [rsp-8+arg_10], rsi
0x1800104fa  push    rbp
0x1800104fb  push    rdi
0x1800104fc  push    r13
0x1800104fe  push    r14
0x180010500  push    r15
0x180010502  lea     rbp, [rsp-37h]
0x180010507  sub     rsp, 0F0h
0x18001050e  mov     r14, r8
0x180010511  mov     r15, rdx
0x180010514  mov     rdi, rcx
0x180010517  xorps   xmm0, xmm0
0x18001051a  movdqu  xmmword ptr [rsp+110h+var_E0], xmm0
0x180010520  mov     [rbp+57h+var_D0], 0
0x180010527  movdqu  [rbp+57h+var_C8], xmm0
0x18001052c  mov     dword ptr [rdx], 0
0x180010532  mov     qword ptr [r8], 0
0x180010539  mov     esi, 3
0x18001053e  lea     r13d, [rsi-2]
0x180010542  test    rcx, rcx
0x180010545  cmovz   esi, r13d
0x180010549  lea     rcx, [rsp+110h+var_E0]; this
0x18001054e  call    ?FreeAll@_hypothesis_builder@@QEAAXXZ; _hypothesis_builder::FreeAll(void)
0x180010553  lea     rdx, aPnrphelperclas; "PnrpHelperClass"
0x18001055a  lea     rcx, [rsp+110h+var_E0]; this
0x18001055f  call    ?SetName@_hypothesis_builder@@QEAAJPEBG@Z; _hypothesis_builder::SetName(ushort const *)
0x180010564  mov     ebx, eax
0x180010566  test    eax, eax
0x180010568  js      short loc_18001057C
0x18001056a  mov     edx, esi; unsigned int
0x18001056c  lea     rcx, [rsp+110h+var_E0]; this
0x180010571  call    ?SetCount@_hypothesis_builder@@QEAAJK@Z; _hypothesis_builder::SetCount(ulong)
0x180010576  mov     ebx, eax
0x180010578  test    eax, eax
0x18001057a  jns     short loc_18001058B
0x18001057c  mov     [rsp+110h+var_E8], ebx
0x180010580  mov     r9d, 87h
0x180010586  jmp     loc_1800106D1
0x18001058b  lea     r8, aCloudname; "cloudname"
0x180010592  lea     rdx, aGlobal; "Global_"
0x180010599  lea     rcx, [rbp+57h+var_B8]; this
0x18001059d  call    ??0_attribute_t@@QEAA@PEBG0@Z; _attribute_t::_attribute_t(ushort const *,ushort const *)
0x1800105a2  mov     r8, rax; struct _attribute_t *
0x1800105a5  xor     edx, edx; unsigned int
0x1800105a7  lea     rcx, [rsp+110h+var_E0]; this
0x1800105ac  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x1800105b1  mov     ebx, eax
0x1800105b3  lea     rcx, [rbp+57h+var_B8]; this
0x1800105b7  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x1800105bc  test    ebx, ebx
0x1800105be  jns     short loc_1800105CF
0x1800105c0  mov     [rsp+110h+var_E8], ebx
0x1800105c4  mov     r9d, 8Ah
0x1800105ca  jmp     loc_1800106D1
0x1800105cf  test    rdi, rdi
0x1800105d2  jz      loc_1800106B1
0x1800105d8  lea     r8, aPeername; "peername"
0x1800105df  mov     rdx, rdi; unsigned __int16 *
0x1800105e2  lea     rcx, [rbp+57h+var_B8]; this
0x1800105e6  call    ??0_attribute_t@@QEAA@PEBG0@Z; _attribute_t::_attribute_t(ushort const *,ushort const *)
0x1800105eb  mov     r8, rax; struct _attribute_t *
0x1800105ee  mov     edx, r13d; unsigned int
0x1800105f1  lea     rcx, [rsp+110h+var_E0]; this
0x1800105f6  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x1800105fb  mov     ebx, eax
0x1800105fd  lea     rcx, [rbp+57h+var_B8]; this
0x180010601  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180010606  test    ebx, ebx
0x180010608  jns     short loc_180010619
0x18001060a  mov     [rsp+110h+var_E8], ebx
0x18001060e  mov     r9d, 8Fh
0x180010614  jmp     loc_1800106D1
0x180010619  xor     ecx, ecx; pv
0x18001061b  call    cs:__imp_CoTaskMemFree
0x180010621  mov     [rbp+57h+var_B8], 0
0x180010629  mov     [rbp+57h+arg_0], 0
0x180010631  lea     r8, [rbp+57h+arg_0]; unsigned __int64 *
0x180010635  mov     edx, 0FFFEh; unsigned __int64
0x18001063a  lea     rcx, aPublishmode; "publishmode"
0x180010641  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180010646  test    eax, eax
0x180010648  js      short loc_180010678
0x18001064a  mov     rbx, [rbp+57h+arg_0]
0x18001064e  lea     rcx, ds:2[rbx*2]; cb
0x180010656  call    cs:__imp_CoTaskMemAlloc
0x18001065c  mov     [rbp+57h+var_B8], rax
0x180010660  test    rax, rax
0x180010663  jz      short loc_180010678
0x180010665  lea     rdx, [rbx+1]; unsigned __int64
0x180010669  lea     r8, aPublishmode; "publishmode"
0x180010670  mov     rcx, rax; unsigned __int16 *
0x180010673  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010678  mov     [rbp+57h+var_B0], r13d
0x18001067c  mov     [rbp+57h+var_A8], 0
0x180010683  lea     r8, [rbp+57h+var_B8]; struct _attribute_t *
0x180010687  mov     edx, 2; unsigned int
0x18001068c  lea     rcx, [rsp+110h+var_E0]; this
0x180010691  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x180010696  mov     ebx, eax
0x180010698  lea     rcx, [rbp+57h+var_B8]; this
0x18001069c  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x1800106a1  test    ebx, ebx
0x1800106a3  jns     short loc_1800106B1
0x1800106a5  mov     [rsp+110h+var_E8], ebx
0x1800106a9  mov     r9d, 92h
0x1800106af  jmp     short loc_1800106D1
0x1800106b1  mov     r8, r14; struct tagHYPOTHESIS **
0x1800106b4  mov     rdx, r15; unsigned int *
0x1800106b7  lea     rcx, [rsp+110h+var_E0]; this
0x1800106bc  call    ?Detach@_hypothesis_builder@@QEAAJPEAKPEAPEAUtagHYPOTHESIS@@0@Z; _hypothesis_builder::Detach(ulong *,tagHYPOTHESIS * *,ulong *)
0x1800106c1  mov     ebx, eax
0x1800106c3  test    eax, eax
0x1800106c5  jns     short loc_1800106EA
0x1800106c7  mov     [rsp+110h+var_E8], eax; unsigned int
0x1800106cb  mov     r9d, 96h; unsigned int
0x1800106d1  lea     rax, aBuildpnrphypot; "BuildPNRPHypotheses"
0x1800106d8  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x1800106dd  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x1800106e4  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800106e9  nop
0x1800106ea  lea     rcx, [rsp+110h+var_E0]; this
0x1800106ef  call    ??1_hypothesis_builder@@QEAA@XZ; _hypothesis_builder::~_hypothesis_builder(void)
0x1800106f4  mov     eax, ebx
0x1800106f6  lea     r11, [rsp+110h+var_20]
0x1800106fe  mov     rbx, [r11+38h]
0x180010702  mov     rsi, [r11+40h]
0x180010706  mov     rsp, r11
0x180010709  pop     r15
0x18001070b  pop     r14
0x18001070d  pop     r13
0x18001070f  pop     rdi
0x180010710  pop     rbp
0x180010711  retn
```
