# BuildIncomingHypotheses(ushort const *,ushort const *,tagOCTET_STRING,ulong *,tagHYPOTHESIS * *)

- ea: `0x18000fc14`
- end: `0x18001017b`
- name: `?BuildIncomingHypotheses@@YAJPEBG0UtagOCTET_STRING@@PEAKPEAPEAUtagHYPOTHESIS@@@Z`
- size: `1383`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct tagOCTET_STRING *, unsigned int *, struct tagHYPOTHESIS **)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d730`

## callees

- `0x1800020b4`
- `0x1800020cc`
- `0x180006b04`
- `0x18000d42c`
- `0x18000f2d4`
- `0x18000f450`
- `0x18000f4a8`
- `0x18000f584`
- `0x18000fc14`
- `0x180010f58`
- `0x1800121d8`
- `0x180014660`
- `0x180018378`
- `0x18001865c`
- `0x180018730`
- `0x18001a5a2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ff1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010086`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fd63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fe81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ff1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010086`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fd9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000feb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ff4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800100bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fd9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000feb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ff4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800100bd`

## string_xrefs

- `0x18000fcbf`: `BuildIncomingHypotheses`
- `0x180010145`: `BuildIncomingHypotheses`
- `0x18000ff32`: `protocol`
- `0x18000ff63`: `protocol`

## pseudocode

```c
__int64 __fastcall BuildIncomingHypotheses(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct tagOCTET_STRING *a3,
        unsigned int *a4,
        struct tagHYPOTHESIS **a5)
{
  _QWORD *v9; // rax
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rdi
  signed int v13; // ebx
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  CEventLogger *v15; // rcx
  const struct _EVENT_DESCRIPTOR *v16; // rdx
  struct _attribute_t *v17; // rax
  const struct _EVENT_DESCRIPTOR *v18; // rdx
  CEventLogger *v19; // rcx
  unsigned __int64 v20; // rbx
  unsigned __int16 *v21; // rax
  unsigned int v22; // r14d
  const struct _EVENT_DESCRIPTOR *v23; // rdx
  CEventLogger *v24; // rcx
  const unsigned __int16 *v25; // r8
  struct _attribute_t *v26; // rax
  const struct _EVENT_DESCRIPTOR *v27; // rdx
  CEventLogger *v28; // rcx
  unsigned __int64 v29; // rbx
  unsigned __int16 *v30; // rax
  const struct _EVENT_DESCRIPTOR *v31; // rdx
  CEventLogger *v32; // rcx
  unsigned __int64 v33; // rbx
  unsigned __int16 *v34; // rax
  const struct _EVENT_DESCRIPTOR *v35; // rdx
  CEventLogger *v36; // rcx
  const struct _EVENT_DESCRIPTOR *v37; // rdx
  CEventLogger *v38; // rcx
  struct _attribute_t *v39; // rax
  const struct _EVENT_DESCRIPTOR *v40; // rdx
  CEventLogger *v41; // rcx
  struct _attribute_t *v42; // rax
  const struct _EVENT_DESCRIPTOR *v43; // rdx
  CEventLogger *v44; // rcx
  unsigned __int64 v45; // rbx
  unsigned __int16 *v46; // rax
  const struct _EVENT_DESCRIPTOR *v47; // rdx
  CEventLogger *v48; // rcx
  signed int v49; // eax
  CEventLogger *v50; // rcx
  unsigned __int64 v52; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v53; // [rsp+38h] [rbp-C8h] BYREF
  int v54; // [rsp+40h] [rbp-C0h]
  __int128 v55; // [rsp+48h] [rbp-B8h]
  __int128 v56; // [rsp+58h] [rbp-A8h]
  __int128 v57; // [rsp+68h] [rbp-98h]
  __int128 v58; // [rsp+78h] [rbp-88h]
  __int128 v59; // [rsp+88h] [rbp-78h]
  __int128 v60; // [rsp+98h] [rbp-68h]
  __int128 v61; // [rsp+A8h] [rbp-58h]
  __int128 v62; // [rsp+B8h] [rbp-48h]
  struct tagHYPOTHESIS **v63; // [rsp+C8h] [rbp-38h]
  _OWORD v64[12]; // [rsp+D0h] [rbp-30h] BYREF

  v63 = a5;
  memset_0((char *)v64 + 2, 0, 0x7Eu);
  *a4 = 0;
  *a5 = 0;
  LOWORD(v64[0]) = 0;
  v9 = operator new[](0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v52 = (unsigned __int64)v9;
  v11 = 2;
  if ( v9 )
  {
    *v9 = 2;
    v12 = v9 + 1;
    `eh vector constructor iterator'(
      v9 + 1,
      0x28u,
      2u,
      (void (*)(void *))_hypothesis_builder::_hypothesis_builder,
      (void (*)(void *))_hypothesis_builder::~_hypothesis_builder);
  }
  else
  {
    v12 = 0;
  }
  if ( v12 )
  {
    _hypothesis_builder::FreeAll((_hypothesis_builder *)v12);
    v13 = _hypothesis_builder::SetName((unsigned __int16 **)v12, L"Winsock");
    if ( v13 >= 0 && (v13 = _hypothesis_builder::SetCount((_hypothesis_builder *)v12, 5u), v13 >= 0) )
    {
      v17 = _attribute_t::_attribute_t((_attribute_t *)&v53, a2, L"appid");
      v13 = _hypothesis_builder::SetAt((_hypothesis_builder *)v12, 0, v17);
      _attribute_t::FreeAll((_attribute_t *)&v53);
      if ( v13 >= 0 )
      {
        CoTaskMemFree(0);
        v53 = 0;
        v52 = 0;
        if ( (int)StringCchLengthW(L"localaddr", 0xFFFEu, &v52) >= 0 )
        {
          v20 = v52;
          v21 = (unsigned __int16 *)CoTaskMemAlloc(2 * v52 + 2);
          v53 = v21;
          if ( v21 )
            StringCchCopyW(v21, v20 + 1, L"localaddr");
        }
        v54 = 13;
        v55 = v64[0];
        v56 = v64[1];
        v57 = v64[2];
        v58 = v64[3];
        v59 = v64[4];
        v60 = v64[5];
        v61 = v64[6];
        v62 = v64[7];
        v22 = 1;
        v13 = _hypothesis_builder::SetAt((_hypothesis_builder *)v12, 1u, (struct _attribute_t *)&v53);
        _attribute_t::FreeAll((_attribute_t *)&v53);
        if ( v13 >= 0 )
        {
          v26 = _attribute_t::_attribute_t((_attribute_t *)&v53, a3, v25);
          v13 = _hypothesis_builder::SetAt((_hypothesis_builder *)v12, 2u, v26);
          _attribute_t::FreeAll((_attribute_t *)&v53);
          if ( v13 >= 0 )
          {
            CoTaskMemFree(0);
            v53 = 0;
            v52 = 0;
            if ( (int)StringCchLengthW(L"inboundflags", 0xFFFEu, &v52) >= 0 )
            {
              v29 = v52;
              v30 = (unsigned __int16 *)CoTaskMemAlloc(2 * v52 + 2);
              v53 = v30;
              if ( v30 )
                StringCchCopyW(v30, v29 + 1, L"inboundflags");
            }
            v54 = 7;
            LODWORD(v55) = 3;
            v13 = _hypothesis_builder::SetAt((_hypothesis_builder *)v12, 3u, (struct _attribute_t *)&v53);
            _attribute_t::FreeAll((_attribute_t *)&v53);
            if ( v13 >= 0 )
            {
              CoTaskMemFree(0);
              v53 = 0;
              v52 = 0;
              if ( (int)StringCchLengthW(L"protocol", 0xFFFEu, &v52) >= 0 )
              {
                v33 = v52;
                v34 = (unsigned __int16 *)CoTaskMemAlloc(2 * v52 + 2);
                v53 = v34;
                if ( v34 )
                  StringCchCopyW(v34, v33 + 1, L"protocol");
              }
              v54 = 7;
              LODWORD(v55) = 6;
              v13 = _hypothesis_builder::SetAt((_hypothesis_builder *)v12, 4u, (struct _attribute_t *)&v53);
              _attribute_t::FreeAll((_attribute_t *)&v53);
              if ( v13 >= 0 )
              {
                if ( a1 )
                {
                  _hypothesis_builder::FreeAll((_hypothesis_builder *)(v12 + 5));
                  v13 = _hypothesis_builder::SetName((unsigned __int16 **)v12 + 5, L"PnrpHelperClass");
                  if ( v13 < 0 || (v13 = _hypothesis_builder::SetCount((_hypothesis_builder *)(v12 + 5), 3u), v13 < 0) )
                  {
                    CEventLogger::LogError(
                      v38,
                      v37,
                      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
                      0x134u,
                      L"BuildIncomingHypotheses",
                      v13);
                    goto LABEL_44;
                  }
                  v39 = _attribute_t::_attribute_t((_attribute_t *)&v53, L"Global_", L"cloudname");
                  v13 = _hypothesis_builder::SetAt((_hypothesis_builder *)(v12 + 5), 0, v39);
                  _attribute_t::FreeAll((_attribute_t *)&v53);
                  if ( v13 < 0 )
                  {
                    CEventLogger::LogError(
                      v41,
                      v40,
                      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
                      0x137u,
                      L"BuildIncomingHypotheses",
                      v13);
                    goto LABEL_44;
                  }
                  v42 = _attribute_t::_attribute_t((_attribute_t *)&v53, a1, L"peername");
                  v13 = _hypothesis_builder::SetAt((_hypothesis_builder *)(v12 + 5), 1u, v42);
                  _attribute_t::FreeAll((_attribute_t *)&v53);
                  if ( v13 < 0 )
                  {
                    CEventLogger::LogError(
                      v44,
                      v43,
                      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
                      0x13Au,
                      L"BuildIncomingHypotheses",
                      v13);
                    goto LABEL_44;
                  }
                  CoTaskMemFree(0);
                  v53 = 0;
                  v52 = 0;
                  if ( (int)StringCchLengthW(L"publishmode", 0xFFFEu, &v52) >= 0 )
                  {
                    v45 = v52;
                    v46 = (unsigned __int16 *)CoTaskMemAlloc(2 * v52 + 2);
                    v53 = v46;
                    if ( v46 )
                      StringCchCopyW(v46, v45 + 1, L"publishmode");
                  }
                  v54 = 1;
                  LODWORD(v55) = 1;
                  v13 = _hypothesis_builder::SetAt((_hypothesis_builder *)(v12 + 5), 2u, (struct _attribute_t *)&v53);
                  _attribute_t::FreeAll((_attribute_t *)&v53);
                  if ( v13 < 0 )
                  {
                    CEventLogger::LogError(
                      v48,
                      v47,
                      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
                      0x13Du,
                      L"BuildIncomingHypotheses",
                      v13);
                    goto LABEL_44;
                  }
                }
                else
                {
                  v22 = 0;
                }
                v49 = _hypothesis_builder::AppendAndDetach(
                        (_hypothesis_builder *)v12,
                        v22,
                        (struct _hypothesis_builder *)(v12 + 5),
                        a4,
                        v63);
                v13 = v49;
                if ( v49 < 0 )
                  CEventLogger::LogError(
                    v50,
                    v16,
                    L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
                    0x146u,
                    L"BuildIncomingHypotheses",
                    v49);
                goto LABEL_44;
              }
              CEventLogger::LogError(
                v36,
                v35,
                L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
                0x12Du,
                L"BuildIncomingHypotheses",
                v13);
            }
            else
            {
              CEventLogger::LogError(
                v32,
                v31,
                L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
                0x12Au,
                L"BuildIncomingHypotheses",
                v13);
            }
          }
          else
          {
            CEventLogger::LogError(
              v28,
              v27,
              L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
              0x127u,
              L"BuildIncomingHypotheses",
              v13);
          }
        }
        else
        {
          CEventLogger::LogError(
            v24,
            v23,
            L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
            0x124u,
            L"BuildIncomingHypotheses",
            v13);
        }
      }
      else
      {
        CEventLogger::LogError(
          v19,
          v18,
          L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
          0x121u,
          L"BuildIncomingHypotheses",
          v13);
      }
    }
    else
    {
      CEventLogger::LogError(
        v15,
        v14,
        L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
        0x11Eu,
        L"BuildIncomingHypotheses",
        v13);
    }
LABEL_44:
    _hypothesis_builder::`vector deleting destructor'((_hypothesis_builder *)v12, (unsigned int)v16);
    return (unsigned int)v13;
  }
  v13 = -2147024882;
  CEventLogger::LogError(
    (CEventLogger *)v11,
    v10,
    L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
    0x11Bu,
    L"BuildIncomingHypotheses",
    0x8007000E);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000fc14  push    rbp
0x18000fc16  push    rbx
0x18000fc17  push    rsi
0x18000fc18  push    rdi
0x18000fc19  push    r12
0x18000fc1b  push    r13
0x18000fc1d  push    r14
0x18000fc1f  push    r15
0x18000fc21  lea     rbp, [rsp-58h]
0x18000fc26  sub     rsp, 158h
0x18000fc2d  mov     r13, r9
0x18000fc30  mov     r15, r8
0x18000fc33  mov     rsi, rdx
0x18000fc36  mov     r12, rcx
0x18000fc39  mov     rbx, [rbp+90h+arg_20]
0x18000fc40  mov     [rbp+90h+var_C8], rbx
0x18000fc44  xor     edx, edx; Val
0x18000fc46  lea     r8d, [rdx+7Eh]; Size
0x18000fc4a  lea     rcx, [rbp+90h+var_C0+2]; void *
0x18000fc4e  call    memset_0
0x18000fc53  xor     r14d, r14d
0x18000fc56  mov     [r13+0], r14d
0x18000fc5a  mov     [rbx], r14
0x18000fc5d  mov     word ptr [rbp+90h+var_C0], r14w
0x18000fc62  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fc69  lea     ecx, [r14+58h]; unsigned __int64
0x18000fc6d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000fc72  mov     [rsp+190h+var_160], rax
0x18000fc77  lea     ecx, [r14+2]; this
0x18000fc7b  test    rax, rax
0x18000fc7e  jz      short loc_18000FCAA
0x18000fc80  mov     [rax], rcx
0x18000fc83  lea     rdi, [rax+8]
0x18000fc87  lea     rax, ??1_hypothesis_builder@@QEAA@XZ; _hypothesis_builder::~_hypothesis_builder(void)
0x18000fc8e  mov     [rsp+190h+var_170], rax; void (*)(void *)
0x18000fc93  lea     r9, ??0_hypothesis_builder@@QEAA@XZ; void (*)(void *)
0x18000fc9a  mov     r8d, ecx; unsigned __int64
0x18000fc9d  lea     edx, [rcx+26h]; unsigned __int64
0x18000fca0  mov     rcx, rdi; void *
0x18000fca3  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18000fca8  jmp     short loc_18000FCAD
0x18000fcaa  mov     rdi, r14
0x18000fcad  test    rdi, rdi
0x18000fcb0  jnz     short loc_18000FCE2
0x18000fcb2  mov     ebx, 8007000Eh
0x18000fcb7  mov     [rsp+190h+var_168], 8007000Eh; unsigned int
0x18000fcbf  lea     rax, aBuildincomingh; "BuildIncomingHypotheses"
0x18000fcc6  mov     [rsp+190h+var_170], rax; unsigned __int16 *
0x18000fccb  mov     r9d, 11Bh; unsigned int
0x18000fcd1  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000fcd8  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000fcdd  jmp     loc_180010165
0x18000fce2  mov     rcx, rdi; this
0x18000fce5  call    ?FreeAll@_hypothesis_builder@@QEAAXXZ; _hypothesis_builder::FreeAll(void)
0x18000fcea  lea     rdx, aWinsock; "Winsock"
0x18000fcf1  mov     rcx, rdi; this
0x18000fcf4  call    ?SetName@_hypothesis_builder@@QEAAJPEBG@Z; _hypothesis_builder::SetName(ushort const *)
0x18000fcf9  mov     ebx, eax
0x18000fcfb  test    eax, eax
0x18000fcfd  js      short loc_18000FD12
0x18000fcff  mov     edx, 5; unsigned int
0x18000fd04  mov     rcx, rdi; this
0x18000fd07  call    ?SetCount@_hypothesis_builder@@QEAAJK@Z; _hypothesis_builder::SetCount(ulong)
0x18000fd0c  mov     ebx, eax
0x18000fd0e  test    eax, eax
0x18000fd10  jns     short loc_18000FD21
0x18000fd12  mov     [rsp+190h+var_168], ebx
0x18000fd16  mov     r9d, 11Eh
0x18000fd1c  jmp     loc_180010145
0x18000fd21  lea     r8, aAppid; "appid"
0x18000fd28  mov     rdx, rsi; unsigned __int16 *
0x18000fd2b  lea     rcx, [rsp+190h+var_158]; this
0x18000fd30  call    ??0_attribute_t@@QEAA@PEBG0@Z; _attribute_t::_attribute_t(ushort const *,ushort const *)
0x18000fd35  mov     r8, rax; struct _attribute_t *
0x18000fd38  xor     edx, edx; unsigned int
0x18000fd3a  mov     rcx, rdi; this
0x18000fd3d  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x18000fd42  mov     ebx, eax
0x18000fd44  lea     rcx, [rsp+190h+var_158]; this
0x18000fd49  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000fd4e  test    ebx, ebx
0x18000fd50  jns     short loc_18000FD61
0x18000fd52  mov     [rsp+190h+var_168], ebx
0x18000fd56  mov     r9d, 121h
0x18000fd5c  jmp     loc_180010145
0x18000fd61  xor     ecx, ecx; pv
0x18000fd63  call    cs:__imp_CoTaskMemFree
0x18000fd69  mov     [rsp+190h+var_158], r14
0x18000fd6e  mov     [rsp+190h+var_160], r14
0x18000fd73  lea     r8, [rsp+190h+var_160]; unsigned __int64 *
0x18000fd78  mov     esi, 0FFFEh
0x18000fd7d  mov     edx, esi; unsigned __int64
0x18000fd7f  lea     rcx, aLocaladdr; "localaddr"
0x18000fd86  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000fd8b  test    eax, eax
0x18000fd8d  js      short loc_18000FDBF
0x18000fd8f  mov     rbx, [rsp+190h+var_160]
0x18000fd94  lea     rcx, ds:2[rbx*2]; cb
0x18000fd9c  call    cs:__imp_CoTaskMemAlloc
0x18000fda2  mov     [rsp+190h+var_158], rax
0x18000fda7  test    rax, rax
0x18000fdaa  jz      short loc_18000FDBF
0x18000fdac  lea     rdx, [rbx+1]; unsigned __int64
0x18000fdb0  lea     r8, aLocaladdr; "localaddr"
0x18000fdb7  mov     rcx, rax; unsigned __int16 *
0x18000fdba  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fdbf  mov     [rsp+190h+var_150], 0Dh
0x18000fdc7  movaps  xmm0, [rbp+90h+var_C0]
0x18000fdcb  movups  [rsp+190h+var_148], xmm0
0x18000fdd0  movaps  xmm1, [rbp+90h+var_B0]
0x18000fdd4  movups  [rsp+190h+var_138], xmm1
0x18000fdd9  movaps  xmm0, [rbp+90h+var_A0]
0x18000fddd  movups  [rsp+190h+var_128], xmm0
0x18000fde2  movaps  xmm1, [rbp+90h+var_90]
0x18000fde6  movups  [rsp+190h+var_118], xmm1
0x18000fdeb  movaps  xmm0, [rbp+90h+var_80]
0x18000fdef  movups  [rbp+90h+var_108], xmm0
0x18000fdf3  movaps  xmm1, [rbp+90h+var_70]
0x18000fdf7  movups  [rbp+90h+var_F8], xmm1
0x18000fdfb  movaps  xmm0, [rbp+90h+var_60]
0x18000fdff  movups  [rbp+90h+var_E8], xmm0
0x18000fe03  movaps  xmm1, [rbp+90h+var_50]
0x18000fe07  movups  [rbp+90h+var_D8], xmm1
0x18000fe0b  lea     r8, [rsp+190h+var_158]; struct _attribute_t *
0x18000fe10  mov     r14d, 1
0x18000fe16  mov     edx, r14d; unsigned int
0x18000fe19  mov     rcx, rdi; this
0x18000fe1c  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x18000fe21  mov     ebx, eax
0x18000fe23  lea     rcx, [rsp+190h+var_158]; this
0x18000fe28  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000fe2d  test    ebx, ebx
0x18000fe2f  jns     short loc_18000FE40
0x18000fe31  mov     [rsp+190h+var_168], ebx
0x18000fe35  mov     r9d, 124h
0x18000fe3b  jmp     loc_180010145
0x18000fe40  mov     rdx, r15; struct tagOCTET_STRING *
0x18000fe43  lea     rcx, [rsp+190h+var_158]; this
0x18000fe48  call    ??0_attribute_t@@QEAA@AEBUtagOCTET_STRING@@PEBG@Z; _attribute_t::_attribute_t(tagOCTET_STRING const &,ushort const *)
0x18000fe4d  mov     r8, rax; struct _attribute_t *
0x18000fe50  mov     edx, 2; unsigned int
0x18000fe55  mov     rcx, rdi; this
0x18000fe58  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x18000fe5d  mov     ebx, eax
0x18000fe5f  lea     rcx, [rsp+190h+var_158]; this
0x18000fe64  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000fe69  xor     r15d, r15d
0x18000fe6c  test    ebx, ebx
0x18000fe6e  jns     short loc_18000FE7F
0x18000fe70  mov     [rsp+190h+var_168], ebx
0x18000fe74  mov     r9d, 127h
0x18000fe7a  jmp     loc_180010145
0x18000fe7f  xor     ecx, ecx; pv
0x18000fe81  call    cs:__imp_CoTaskMemFree
0x18000fe87  mov     [rsp+190h+var_158], r15
0x18000fe8c  mov     [rsp+190h+var_160], r15
0x18000fe91  lea     r8, [rsp+190h+var_160]; unsigned __int64 *
0x18000fe96  mov     rdx, rsi; unsigned __int64
0x18000fe99  lea     rcx, aInboundflags; "inboundflags"
0x18000fea0  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000fea5  test    eax, eax
0x18000fea7  js      short loc_18000FED9
0x18000fea9  mov     rbx, [rsp+190h+var_160]
0x18000feae  lea     rcx, ds:2[rbx*2]; cb
0x18000feb6  call    cs:__imp_CoTaskMemAlloc
0x18000febc  mov     [rsp+190h+var_158], rax
0x18000fec1  test    rax, rax
0x18000fec4  jz      short loc_18000FED9
0x18000fec6  lea     rdx, [rbx+1]; unsigned __int64
0x18000feca  lea     r8, aInboundflags; "inboundflags"
0x18000fed1  mov     rcx, rax; unsigned __int16 *
0x18000fed4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fed9  mov     [rsp+190h+var_150], 7
0x18000fee1  mov     eax, 3
0x18000fee6  mov     dword ptr [rsp+190h+var_148], eax
0x18000feea  lea     r8, [rsp+190h+var_158]; struct _attribute_t *
0x18000feef  mov     edx, eax; unsigned int
0x18000fef1  mov     rcx, rdi; this
0x18000fef4  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x18000fef9  mov     ebx, eax
0x18000fefb  lea     rcx, [rsp+190h+var_158]; this
0x18000ff00  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000ff05  test    ebx, ebx
0x18000ff07  jns     short loc_18000FF18
0x18000ff09  mov     [rsp+190h+var_168], ebx
0x18000ff0d  mov     r9d, 12Ah
0x18000ff13  jmp     loc_180010145
0x18000ff18  xor     ecx, ecx; pv
0x18000ff1a  call    cs:__imp_CoTaskMemFree
0x18000ff20  mov     [rsp+190h+var_158], r15
0x18000ff25  mov     [rsp+190h+var_160], r15
0x18000ff2a  lea     r8, [rsp+190h+var_160]; unsigned __int64 *
0x18000ff2f  mov     rdx, rsi; unsigned __int64
0x18000ff32  lea     rcx, aProtocol; "protocol"
0x18000ff39  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000ff3e  test    eax, eax
0x18000ff40  js      short loc_18000FF72
0x18000ff42  mov     rbx, [rsp+190h+var_160]
0x18000ff47  lea     rcx, ds:2[rbx*2]; cb
0x18000ff4f  call    cs:__imp_CoTaskMemAlloc
0x18000ff55  mov     [rsp+190h+var_158], rax
0x18000ff5a  test    rax, rax
0x18000ff5d  jz      short loc_18000FF72
0x18000ff5f  lea     rdx, [rbx+1]; unsigned __int64
0x18000ff63  lea     r8, aProtocol; "protocol"
0x18000ff6a  mov     rcx, rax; unsigned __int16 *
0x18000ff6d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ff72  mov     [rsp+190h+var_150], 7
0x18000ff7a  mov     dword ptr [rsp+190h+var_148], 6
0x18000ff82  lea     r8, [rsp+190h+var_158]; struct _attribute_t *
0x18000ff87  mov     edx, 4; unsigned int
0x18000ff8c  mov     rcx, rdi; this
0x18000ff8f  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x18000ff94  mov     ebx, eax
0x18000ff96  lea     rcx, [rsp+190h+var_158]; this
0x18000ff9b  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000ffa0  test    ebx, ebx
0x18000ffa2  jns     short loc_18000FFB3
0x18000ffa4  mov     [rsp+190h+var_168], ebx
0x18000ffa8  mov     r9d, 12Dh
0x18000ffae  jmp     loc_180010145
0x18000ffb3  lea     rsi, [rdi+28h]
0x18000ffb7  test    r12, r12
0x18000ffba  jz      loc_180010118
0x18000ffc0  mov     rcx, rsi; this
0x18000ffc3  call    ?FreeAll@_hypothesis_builder@@QEAAXXZ; _hypothesis_builder::FreeAll(void)
0x18000ffc8  lea     rdx, aPnrphelperclas; "PnrpHelperClass"
0x18000ffcf  mov     rcx, rsi; this
0x18000ffd2  call    ?SetName@_hypothesis_builder@@QEAAJPEBG@Z; _hypothesis_builder::SetName(ushort const *)
0x18000ffd7  mov     ebx, eax
0x18000ffd9  test    eax, eax
0x18000ffdb  js      short loc_18000FFF0
0x18000ffdd  mov     edx, 3; unsigned int
0x18000ffe2  mov     rcx, rsi; this
0x18000ffe5  call    ?SetCount@_hypothesis_builder@@QEAAJK@Z; _hypothesis_builder::SetCount(ulong)
0x18000ffea  mov     ebx, eax
0x18000ffec  test    eax, eax
0x18000ffee  jns     short loc_18000FFFF
0x18000fff0  mov     [rsp+190h+var_168], ebx
0x18000fff4  mov     r9d, 134h
0x18000fffa  jmp     loc_180010145
0x18000ffff  lea     r8, aCloudname; "cloudname"
0x180010006  lea     rdx, aGlobal; "Global_"
0x18001000d  lea     rcx, [rsp+190h+var_158]; this
0x180010012  call    ??0_attribute_t@@QEAA@PEBG0@Z; _attribute_t::_attribute_t(ushort const *,ushort const *)
0x180010017  mov     r8, rax; struct _attribute_t *
0x18001001a  xor     edx, edx; unsigned int
0x18001001c  mov     rcx, rsi; this
0x18001001f  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x180010024  mov     ebx, eax
0x180010026  lea     rcx, [rsp+190h+var_158]; this
0x18001002b  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180010030  test    ebx, ebx
0x180010032  jns     short loc_180010043
0x180010034  mov     [rsp+190h+var_168], ebx
0x180010038  mov     r9d, 137h
0x18001003e  jmp     loc_180010145
0x180010043  lea     r8, aPeername; "peername"
0x18001004a  mov     rdx, r12; unsigned __int16 *
0x18001004d  lea     rcx, [rsp+190h+var_158]; this
0x180010052  call    ??0_attribute_t@@QEAA@PEBG0@Z; _attribute_t::_attribute_t(ushort const *,ushort const *)
0x180010057  mov     r8, rax; struct _attribute_t *
0x18001005a  mov     edx, r14d; unsigned int
0x18001005d  mov     rcx, rsi; this
0x180010060  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x180010065  mov     ebx, eax
0x180010067  lea     rcx, [rsp+190h+var_158]; this
0x18001006c  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x180010071  test    ebx, ebx
0x180010073  jns     short loc_180010084
0x180010075  mov     [rsp+190h+var_168], ebx
0x180010079  mov     r9d, 13Ah
0x18001007f  jmp     loc_180010145
0x180010084  xor     ecx, ecx; pv
0x180010086  call    cs:__imp_CoTaskMemFree
0x18001008c  mov     [rsp+190h+var_158], r15
0x180010091  mov     [rsp+190h+var_160], r15
0x180010096  lea     r8, [rsp+190h+var_160]; unsigned __int64 *
0x18001009b  mov     edx, 0FFFEh; unsigned __int64
0x1800100a0  lea     rcx, aPublishmode; "publishmode"
0x1800100a7  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800100ac  test    eax, eax
0x1800100ae  js      short loc_1800100E0
0x1800100b0  mov     rbx, [rsp+190h+var_160]
0x1800100b5  lea     rcx, ds:2[rbx*2]; cb
0x1800100bd  call    cs:__imp_CoTaskMemAlloc
0x1800100c3  mov     [rsp+190h+var_158], rax
0x1800100c8  test    rax, rax
0x1800100cb  jz      short loc_1800100E0
0x1800100cd  lea     rdx, [rbx+1]; unsigned __int64
0x1800100d1  lea     r8, aPublishmode; "publishmode"
0x1800100d8  mov     rcx, rax; unsigned __int16 *
0x1800100db  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800100e0  mov     [rsp+190h+var_150], r14d
0x1800100e5  mov     dword ptr [rsp+190h+var_148], r14d
0x1800100ea  lea     r8, [rsp+190h+var_158]; struct _attribute_t *
0x1800100ef  mov     edx, 2; unsigned int
0x1800100f4  mov     rcx, rsi; this
0x1800100f7  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x1800100fc  mov     ebx, eax
  ... truncated ...
```
