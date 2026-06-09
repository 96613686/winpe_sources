# BuildFilteredOutgoingHypotheses(ushort *,tagOCTET_STRING,ushort const *,ulong *,tagHYPOTHESIS * *)

- ea: `0x18000f7c8`
- end: `0x18000fc0e`
- name: `?BuildFilteredOutgoingHypotheses@@YAJPEAGUtagOCTET_STRING@@PEBGPEAKPEAPEAUtagHYPOTHESIS@@@Z`
- size: `1094`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct tagOCTET_STRING *, const unsigned __int16 *, unsigned int *, struct tagHYPOTHESIS **)`
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d730`

## callees

- `0x180006b04`
- `0x18000d42c`
- `0x18000f2d4`
- `0x18000f450`
- `0x18000f4a8`
- `0x18000f560`
- `0x18000f7c8`
- `0x180010f58`
- `0x1800121d8`
- `0x180014660`
- `0x1800149bc`
- `0x1800184c8`
- `0x18001865c`
- `0x180018730`
- `0x18001a5a2`
- `0x18001a5e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f8ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f95c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fa3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f8ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f95c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fa3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f8f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f999`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fa77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f8f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f999`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fa77`

## string_xrefs

- `0x18000f8d4`: `protocol`
- `0x18000f905`: `protocol`

## pseudocode

```c
__int64 __fastcall BuildFilteredOutgoingHypotheses(
        unsigned __int16 *a1,
        struct tagOCTET_STRING *a2,
        const unsigned __int16 *a3,
        unsigned int *a4,
        struct tagHYPOTHESIS **a5)
{
  signed int v9; // eax
  const struct _EVENT_DESCRIPTOR *v10; // rdx
  CEventLogger *v11; // rcx
  signed int v12; // ebx
  unsigned int v13; // r9d
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  CEventLogger *v15; // rcx
  unsigned __int64 v16; // rbx
  unsigned __int16 *v17; // rax
  const struct _EVENT_DESCRIPTOR *v18; // rdx
  CEventLogger *v19; // rcx
  unsigned __int64 v20; // rbx
  unsigned __int16 *v21; // rax
  const struct _EVENT_DESCRIPTOR *v22; // rdx
  CEventLogger *v23; // rcx
  unsigned __int64 v24; // rbx
  unsigned __int16 *v25; // rax
  const struct _EVENT_DESCRIPTOR *v26; // rdx
  CEventLogger *v27; // rcx
  const unsigned __int16 *v28; // r8
  struct _attribute_t *v29; // rax
  const struct _EVENT_DESCRIPTOR *v30; // rdx
  CEventLogger *v31; // rcx
  struct _attribute_t *v32; // rax
  const struct _EVENT_DESCRIPTOR *v33; // rdx
  CEventLogger *v34; // rcx
  unsigned int *v35; // r9
  unsigned __int64 v37; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v38[2]; // [rsp+38h] [rbp-C8h] BYREF
  int v39; // [rsp+48h] [rbp-B8h]
  __int128 v40; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v41; // [rsp+60h] [rbp-A0h] BYREF
  int v42; // [rsp+68h] [rbp-98h]
  sockaddr_storage v43; // [rsp+70h] [rbp-90h]
  sockaddr_storage v44; // [rsp+F0h] [rbp-10h] BYREF
  sockaddr_storage v45; // [rsp+170h] [rbp+70h] BYREF

  memset_0(v44.__ss_pad1, 0, 0x7Eu);
  memset_0(&v45, 0, sizeof(v45));
  *(_OWORD *)v38 = 0;
  v39 = 0;
  v40 = 0;
  *a4 = 0;
  *a5 = 0;
  v9 = FilterIPAddressList(a1, &v45);
  v12 = v9;
  if ( v9 < 0 )
  {
    v13 = 377;
LABEL_27:
    CEventLogger::LogError(
      v11,
      v10,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      v13,
      L"BuildFilteredOutgoingHypotheses",
      v9);
    goto LABEL_28;
  }
  _hypothesis_builder::FreeAll((_hypothesis_builder *)v38);
  v12 = _hypothesis_builder::SetName(v38, L"Winsock");
  if ( v12 >= 0 && (v12 = _hypothesis_builder::SetCount((_hypothesis_builder *)v38, 5u), v12 >= 0) )
  {
    CoTaskMemFree(0);
    v41 = 0;
    v37 = 0;
    if ( (int)StringCchLengthW(L"protocol", 0xFFFEu, &v37) >= 0 )
    {
      v16 = v37;
      v17 = (unsigned __int16 *)CoTaskMemAlloc(2 * v37 + 2);
      v41 = v17;
      if ( v17 )
        StringCchCopyW(v17, v16 + 1, L"protocol");
    }
    v42 = 7;
    *(_DWORD *)&v43.ss_family = 6;
    v12 = _hypothesis_builder::SetAt((_hypothesis_builder *)v38, 0, (struct _attribute_t *)&v41);
    _attribute_t::FreeAll((_attribute_t *)&v41);
    if ( v12 >= 0 )
    {
      v44.ss_family = 0;
      CoTaskMemFree(0);
      v41 = 0;
      v37 = 0;
      if ( (int)StringCchLengthW(L"localaddr", 0xFFFEu, &v37) >= 0 )
      {
        v20 = v37;
        v21 = (unsigned __int16 *)CoTaskMemAlloc(2 * v37 + 2);
        v41 = v21;
        if ( v21 )
          StringCchCopyW(v21, v20 + 1, L"localaddr");
      }
      v42 = 13;
      v43 = v44;
      v12 = _hypothesis_builder::SetAt((_hypothesis_builder *)v38, 1u, (struct _attribute_t *)&v41);
      _attribute_t::FreeAll((_attribute_t *)&v41);
      if ( v12 >= 0 )
      {
        CoTaskMemFree(0);
        v41 = 0;
        v37 = 0;
        if ( (int)StringCchLengthW(L"remoteaddr", 0xFFFEu, &v37) >= 0 )
        {
          v24 = v37;
          v25 = (unsigned __int16 *)CoTaskMemAlloc(2 * v37 + 2);
          v41 = v25;
          if ( v25 )
            StringCchCopyW(v25, v24 + 1, L"remoteaddr");
        }
        v42 = 13;
        v43 = v45;
        v12 = _hypothesis_builder::SetAt((_hypothesis_builder *)v38, 4u, (struct _attribute_t *)&v41);
        _attribute_t::FreeAll((_attribute_t *)&v41);
        if ( v12 >= 0 )
        {
          v29 = _attribute_t::_attribute_t((_attribute_t *)&v41, a2, v28);
          v12 = _hypothesis_builder::SetAt((_hypothesis_builder *)v38, 2u, v29);
          _attribute_t::FreeAll((_attribute_t *)&v41);
          if ( v12 >= 0 )
          {
            v32 = _attribute_t::_attribute_t((_attribute_t *)&v41, a3, L"appid");
            v12 = _hypothesis_builder::SetAt((_hypothesis_builder *)v38, 3u, v32);
            _attribute_t::FreeAll((_attribute_t *)&v41);
            if ( v12 >= 0 )
            {
              v9 = _hypothesis_builder::Detach((_hypothesis_builder *)v38, a4, a5, v35);
              v12 = v9;
              if ( v9 < 0 )
              {
                v13 = 408;
                goto LABEL_27;
              }
            }
            else
            {
              CEventLogger::LogError(
                v34,
                v33,
                L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
                0x195u,
                L"BuildFilteredOutgoingHypotheses",
                v12);
            }
          }
          else
          {
            CEventLogger::LogError(
              v31,
              v30,
              L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
              0x190u,
              L"BuildFilteredOutgoingHypotheses",
              v12);
          }
        }
        else
        {
          CEventLogger::LogError(
            v27,
            v26,
            L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
            0x18Cu,
            L"BuildFilteredOutgoingHypotheses",
            v12);
        }
      }
      else
      {
        CEventLogger::LogError(
          v23,
          v22,
          L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
          0x188u,
          L"BuildFilteredOutgoingHypotheses",
          v12);
      }
    }
    else
    {
      CEventLogger::LogError(
        v19,
        v18,
        L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
        0x182u,
        L"BuildFilteredOutgoingHypotheses",
        v12);
    }
  }
  else
  {
    CEventLogger::LogError(
      v15,
      v14,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x17Eu,
      L"BuildFilteredOutgoingHypotheses",
      v12);
  }
LABEL_28:
  _hypothesis_builder::~_hypothesis_builder((_hypothesis_builder *)v38);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000f7c8  push    rbp
0x18000f7ca  push    rbx
0x18000f7cb  push    rsi
0x18000f7cc  push    rdi
0x18000f7cd  push    r13
0x18000f7cf  push    r14
0x18000f7d1  push    r15
0x18000f7d3  lea     rbp, [rsp-100h]
0x18000f7db  sub     rsp, 200h
0x18000f7e2  mov     rax, cs:__security_cookie
0x18000f7e9  xor     rax, rsp
0x18000f7ec  mov     [rbp+130h+var_40], rax
0x18000f7f3  mov     rdi, r9
0x18000f7f6  mov     r15, r8
0x18000f7f9  mov     r14, rdx
0x18000f7fc  mov     rbx, rcx
0x18000f7ff  mov     rsi, [rbp+130h+arg_20]
0x18000f806  xor     edx, edx; Val
0x18000f808  lea     r8d, [rdx+7Eh]; Size
0x18000f80c  lea     rcx, [rbp+130h+var_140+2]; void *
0x18000f810  call    memset_0
0x18000f815  xor     edx, edx; Val
0x18000f817  mov     r8d, 80h; Size
0x18000f81d  lea     rcx, [rbp+130h+var_C0]; void *
0x18000f821  call    memset_0
0x18000f826  xorps   xmm0, xmm0
0x18000f829  movdqu  xmmword ptr [rsp+230h+var_1F8], xmm0
0x18000f82f  mov     [rsp+230h+var_1E8], 0
0x18000f837  movdqu  [rsp+230h+var_1E0], xmm0
0x18000f83d  mov     dword ptr [rdi], 0
0x18000f843  mov     qword ptr [rsi], 0
0x18000f84a  lea     rdx, [rbp+130h+var_C0]; struct sockaddr_storage *
0x18000f84e  mov     rcx, rbx; unsigned __int16 *
0x18000f851  call    ?FilterIPAddressList@@YAJPEAGPEAUsockaddr_storage@@@Z; FilterIPAddressList(ushort *,sockaddr_storage *)
0x18000f856  mov     ebx, eax
0x18000f858  test    eax, eax
0x18000f85a  jns     short loc_18000F867
0x18000f85c  mov     r9d, 179h
0x18000f862  jmp     loc_18000FBC4
0x18000f867  lea     rcx, [rsp+230h+var_1F8]; this
0x18000f86c  call    ?FreeAll@_hypothesis_builder@@QEAAXXZ; _hypothesis_builder::FreeAll(void)
0x18000f871  lea     rdx, aWinsock; "Winsock"
0x18000f878  lea     rcx, [rsp+230h+var_1F8]; this
0x18000f87d  call    ?SetName@_hypothesis_builder@@QEAAJPEBG@Z; _hypothesis_builder::SetName(ushort const *)
0x18000f882  mov     ebx, eax
0x18000f884  test    eax, eax
0x18000f886  js      short loc_18000F89D
0x18000f888  mov     edx, 5; unsigned int
0x18000f88d  lea     rcx, [rsp+230h+var_1F8]; this
0x18000f892  call    ?SetCount@_hypothesis_builder@@QEAAJK@Z; _hypothesis_builder::SetCount(ulong)
0x18000f897  mov     ebx, eax
0x18000f899  test    eax, eax
0x18000f89b  jns     short loc_18000F8AC
0x18000f89d  mov     [rsp+230h+var_208], ebx
0x18000f8a1  mov     r9d, 17Eh
0x18000f8a7  jmp     loc_18000FBC8
0x18000f8ac  xor     ecx, ecx; pv
0x18000f8ae  call    cs:__imp_CoTaskMemFree
0x18000f8b4  mov     [rsp+230h+var_1D0], 0
0x18000f8bd  mov     [rsp+230h+var_200], 0
0x18000f8c6  lea     r8, [rsp+230h+var_200]; unsigned __int64 *
0x18000f8cb  mov     r13d, 0FFFEh
0x18000f8d1  mov     edx, r13d; unsigned __int64
0x18000f8d4  lea     rcx, aProtocol; "protocol"
0x18000f8db  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000f8e0  test    eax, eax
0x18000f8e2  js      short loc_18000F914
0x18000f8e4  mov     rbx, [rsp+230h+var_200]
0x18000f8e9  lea     rcx, ds:2[rbx*2]; cb
0x18000f8f1  call    cs:__imp_CoTaskMemAlloc
0x18000f8f7  mov     [rsp+230h+var_1D0], rax
0x18000f8fc  test    rax, rax
0x18000f8ff  jz      short loc_18000F914
0x18000f901  lea     rdx, [rbx+1]; unsigned __int64
0x18000f905  lea     r8, aProtocol; "protocol"
0x18000f90c  mov     rcx, rax; unsigned __int16 *
0x18000f90f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f914  mov     [rsp+230h+var_1C8], 7
0x18000f91c  mov     dword ptr [rsp+230h+var_1C0], 6
0x18000f924  lea     r8, [rsp+230h+var_1D0]; struct _attribute_t *
0x18000f929  xor     edx, edx; unsigned int
0x18000f92b  lea     rcx, [rsp+230h+var_1F8]; this
0x18000f930  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x18000f935  mov     ebx, eax
0x18000f937  lea     rcx, [rsp+230h+var_1D0]; this
0x18000f93c  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000f941  test    ebx, ebx
0x18000f943  jns     short loc_18000F954
0x18000f945  mov     [rsp+230h+var_208], ebx
0x18000f949  mov     r9d, 182h
0x18000f94f  jmp     loc_18000FBC8
0x18000f954  xor     eax, eax
0x18000f956  mov     word ptr [rbp+130h+var_140], ax
0x18000f95a  xor     ecx, ecx; pv
0x18000f95c  call    cs:__imp_CoTaskMemFree
0x18000f962  mov     [rsp+230h+var_1D0], 0
0x18000f96b  mov     [rsp+230h+var_200], 0
0x18000f974  lea     r8, [rsp+230h+var_200]; unsigned __int64 *
0x18000f979  mov     rdx, r13; unsigned __int64
0x18000f97c  lea     rcx, aLocaladdr; "localaddr"
0x18000f983  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000f988  test    eax, eax
0x18000f98a  js      short loc_18000F9BC
0x18000f98c  mov     rbx, [rsp+230h+var_200]
0x18000f991  lea     rcx, ds:2[rbx*2]; cb
0x18000f999  call    cs:__imp_CoTaskMemAlloc
0x18000f99f  mov     [rsp+230h+var_1D0], rax
0x18000f9a4  test    rax, rax
0x18000f9a7  jz      short loc_18000F9BC
0x18000f9a9  lea     rdx, [rbx+1]; unsigned __int64
0x18000f9ad  lea     r8, aLocaladdr; "localaddr"
0x18000f9b4  mov     rcx, rax; unsigned __int16 *
0x18000f9b7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f9bc  mov     [rsp+230h+var_1C8], 0Dh
0x18000f9c4  movaps  xmm0, [rbp+130h+var_140]
0x18000f9c8  movups  [rsp+230h+var_1C0], xmm0
0x18000f9cd  movaps  xmm1, [rbp+130h+var_130]
0x18000f9d1  movups  [rbp+130h+var_1B0], xmm1
0x18000f9d5  movaps  xmm0, [rbp+130h+var_120]
0x18000f9d9  movups  [rbp+130h+var_1A0], xmm0
0x18000f9dd  movaps  xmm1, [rbp+130h+var_110]
0x18000f9e1  movups  [rbp+130h+var_190], xmm1
0x18000f9e5  movaps  xmm0, [rbp+130h+var_100]
0x18000f9e9  movups  [rbp+130h+var_180], xmm0
0x18000f9ed  movaps  xmm1, [rbp+130h+var_F0]
0x18000f9f1  movups  [rbp+130h+var_170], xmm1
0x18000f9f5  movaps  xmm0, [rbp+130h+var_E0]
0x18000f9f9  movups  [rbp+130h+var_160], xmm0
0x18000f9fd  movaps  xmm1, [rbp+130h+var_D0]
0x18000fa01  movups  [rbp+130h+var_150], xmm1
0x18000fa05  lea     r8, [rsp+230h+var_1D0]; struct _attribute_t *
0x18000fa0a  mov     edx, 1; unsigned int
0x18000fa0f  lea     rcx, [rsp+230h+var_1F8]; this
0x18000fa14  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x18000fa19  mov     ebx, eax
0x18000fa1b  lea     rcx, [rsp+230h+var_1D0]; this
0x18000fa20  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000fa25  test    ebx, ebx
0x18000fa27  jns     short loc_18000FA38
0x18000fa29  mov     [rsp+230h+var_208], ebx
0x18000fa2d  mov     r9d, 188h
0x18000fa33  jmp     loc_18000FBC8
0x18000fa38  xor     ecx, ecx; pv
0x18000fa3a  call    cs:__imp_CoTaskMemFree
0x18000fa40  mov     [rsp+230h+var_1D0], 0
0x18000fa49  mov     [rsp+230h+var_200], 0
0x18000fa52  lea     r8, [rsp+230h+var_200]; unsigned __int64 *
0x18000fa57  mov     rdx, r13; unsigned __int64
0x18000fa5a  lea     rcx, aRemoteaddr; "remoteaddr"
0x18000fa61  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000fa66  test    eax, eax
0x18000fa68  js      short loc_18000FA9A
0x18000fa6a  mov     rbx, [rsp+230h+var_200]
0x18000fa6f  lea     rcx, ds:2[rbx*2]; cb
0x18000fa77  call    cs:__imp_CoTaskMemAlloc
0x18000fa7d  mov     [rsp+230h+var_1D0], rax
0x18000fa82  test    rax, rax
0x18000fa85  jz      short loc_18000FA9A
0x18000fa87  lea     rdx, [rbx+1]; unsigned __int64
0x18000fa8b  lea     r8, aRemoteaddr; "remoteaddr"
0x18000fa92  mov     rcx, rax; unsigned __int16 *
0x18000fa95  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fa9a  mov     [rsp+230h+var_1C8], 0Dh
0x18000faa2  movaps  xmm0, xmmword ptr [rbp+130h+var_C0.ss_family]
0x18000faa6  movups  [rsp+230h+var_1C0], xmm0
0x18000faab  movaps  xmm1, xmmword ptr [rbp+130h+var_C0.__ss_pad2]
0x18000fab2  movups  [rbp+130h+var_1B0], xmm1
0x18000fab6  movaps  xmm0, xmmword ptr [rbp+130h+var_C0.__ss_pad2+10h]
0x18000fabd  movups  [rbp+130h+var_1A0], xmm0
0x18000fac1  movaps  xmm1, xmmword ptr [rbp+130h+var_C0.__ss_pad2+20h]
0x18000fac8  movups  [rbp+130h+var_190], xmm1
0x18000facc  movaps  xmm0, xmmword ptr [rbp+130h+var_C0.__ss_pad2+30h]
0x18000fad3  movups  [rbp+130h+var_180], xmm0
0x18000fad7  movaps  xmm1, xmmword ptr [rbp+130h+var_C0.__ss_pad2+40h]
0x18000fade  movups  [rbp+130h+var_170], xmm1
0x18000fae2  movaps  xmm0, xmmword ptr [rbp+130h+var_C0.__ss_pad2+50h]
0x18000fae9  movups  [rbp+130h+var_160], xmm0
0x18000faed  movaps  xmm1, xmmword ptr [rbp+130h+var_C0.__ss_pad2+60h]
0x18000faf4  movups  [rbp+130h+var_150], xmm1
0x18000faf8  lea     r8, [rsp+230h+var_1D0]; struct _attribute_t *
0x18000fafd  mov     edx, 4; unsigned int
0x18000fb02  lea     rcx, [rsp+230h+var_1F8]; this
0x18000fb07  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x18000fb0c  mov     ebx, eax
0x18000fb0e  lea     rcx, [rsp+230h+var_1D0]; this
0x18000fb13  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000fb18  test    ebx, ebx
0x18000fb1a  jns     short loc_18000FB2B
0x18000fb1c  mov     [rsp+230h+var_208], ebx
0x18000fb20  mov     r9d, 18Ch
0x18000fb26  jmp     loc_18000FBC8
0x18000fb2b  mov     rdx, r14; struct tagOCTET_STRING *
0x18000fb2e  lea     rcx, [rsp+230h+var_1D0]; this
0x18000fb33  call    ??0_attribute_t@@QEAA@AEBUtagOCTET_STRING@@PEBG@Z; _attribute_t::_attribute_t(tagOCTET_STRING const &,ushort const *)
0x18000fb38  mov     r8, rax; struct _attribute_t *
0x18000fb3b  mov     edx, 2; unsigned int
0x18000fb40  lea     rcx, [rsp+230h+var_1F8]; this
0x18000fb45  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x18000fb4a  mov     ebx, eax
0x18000fb4c  lea     rcx, [rsp+230h+var_1D0]; this
0x18000fb51  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000fb56  test    ebx, ebx
0x18000fb58  jns     short loc_18000FB66
0x18000fb5a  mov     [rsp+230h+var_208], ebx
0x18000fb5e  mov     r9d, 190h
0x18000fb64  jmp     short loc_18000FBC8
0x18000fb66  lea     r8, aAppid; "appid"
0x18000fb6d  mov     rdx, r15; unsigned __int16 *
0x18000fb70  lea     rcx, [rsp+230h+var_1D0]; this
0x18000fb75  call    ??0_attribute_t@@QEAA@PEBG0@Z; _attribute_t::_attribute_t(ushort const *,ushort const *)
0x18000fb7a  mov     r8, rax; struct _attribute_t *
0x18000fb7d  mov     edx, 3; unsigned int
0x18000fb82  lea     rcx, [rsp+230h+var_1F8]; this
0x18000fb87  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x18000fb8c  mov     ebx, eax
0x18000fb8e  lea     rcx, [rsp+230h+var_1D0]; this
0x18000fb93  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000fb98  test    ebx, ebx
0x18000fb9a  jns     short loc_18000FBA8
0x18000fb9c  mov     [rsp+230h+var_208], ebx
0x18000fba0  mov     r9d, 195h
0x18000fba6  jmp     short loc_18000FBC8
0x18000fba8  mov     r8, rsi; struct tagHYPOTHESIS **
0x18000fbab  mov     rdx, rdi; unsigned int *
0x18000fbae  lea     rcx, [rsp+230h+var_1F8]; this
0x18000fbb3  call    ?Detach@_hypothesis_builder@@QEAAJPEAKPEAPEAUtagHYPOTHESIS@@0@Z; _hypothesis_builder::Detach(ulong *,tagHYPOTHESIS * *,ulong *)
0x18000fbb8  mov     ebx, eax
0x18000fbba  test    eax, eax
0x18000fbbc  jns     short loc_18000FBE1
0x18000fbbe  mov     r9d, 198h; unsigned int
0x18000fbc4  mov     [rsp+230h+var_208], eax; unsigned int
0x18000fbc8  lea     rax, aBuildfilteredo; "BuildFilteredOutgoingHypotheses"
0x18000fbcf  mov     [rsp+230h+var_210], rax; unsigned __int16 *
0x18000fbd4  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000fbdb  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000fbe0  nop
0x18000fbe1  lea     rcx, [rsp+230h+var_1F8]; this
0x18000fbe6  call    ??1_hypothesis_builder@@QEAA@XZ; _hypothesis_builder::~_hypothesis_builder(void)
0x18000fbeb  mov     eax, ebx
0x18000fbed  mov     rcx, [rbp+130h+var_40]
0x18000fbf4  xor     rcx, rsp; StackCookie
0x18000fbf7  call    __security_check_cookie
0x18000fbfc  add     rsp, 200h
0x18000fc03  pop     r15
0x18000fc05  pop     r14
0x18000fc07  pop     r13
0x18000fc09  pop     rdi
0x18000fc0a  pop     rsi
0x18000fc0b  pop     rbx
0x18000fc0c  pop     rbp
0x18000fc0d  retn
```
