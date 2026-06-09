# BuildAAHypotheses(ulong *,tagHYPOTHESIS * *)

- ea: `0x18000f5bc`
- end: `0x18000f7c1`
- name: `?BuildAAHypotheses@@YAJPEAKPEAPEAUtagHYPOTHESIS@@@Z`
- size: `517`
- prototype: `__int64 __fastcall(unsigned int *, struct tagHYPOTHESIS **)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d730`

## callees

- `0x180006b04`
- `0x18000d42c`
- `0x18000f2d4`
- `0x18000f560`
- `0x18000f5bc`
- `0x180010f58`
- `0x1800121d8`
- `0x180014660`
- `0x1800184c8`
- `0x18001865c`
- `0x180018730`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f63c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f6d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f63c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f6d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f677`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f712`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f677`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000f712`

## pseudocode

```c
__int64 __fastcall BuildAAHypotheses(unsigned int *a1, struct tagHYPOTHESIS **a2)
{
  const struct _EVENT_DESCRIPTOR *v4; // rdx
  CEventLogger *v5; // rcx
  signed int v6; // ebx
  unsigned __int64 v7; // rbx
  unsigned __int16 *v8; // rax
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CEventLogger *v10; // rcx
  unsigned __int64 v11; // rbx
  unsigned __int16 *v12; // rax
  const struct _EVENT_DESCRIPTOR *v13; // rdx
  CEventLogger *v14; // rcx
  unsigned int *v15; // r9
  signed int v16; // eax
  const struct _EVENT_DESCRIPTOR *v17; // rdx
  CEventLogger *v18; // rcx
  unsigned __int16 *v20[2]; // [rsp+30h] [rbp-89h] BYREF
  int v21; // [rsp+40h] [rbp-79h]
  __int128 v22; // [rsp+48h] [rbp-71h]
  unsigned __int16 *v23; // [rsp+58h] [rbp-61h] BYREF
  int v24; // [rsp+60h] [rbp-59h]
  int v25; // [rsp+68h] [rbp-51h]
  unsigned __int64 v26; // [rsp+120h] [rbp+67h] BYREF

  *(_OWORD *)v20 = 0;
  v21 = 0;
  v22 = 0;
  *a1 = 0;
  *a2 = 0;
  _hypothesis_builder::FreeAll((_hypothesis_builder *)v20);
  v6 = _hypothesis_builder::SetName(v20, L"AddressAcquisition");
  if ( v6 >= 0 && (v6 = _hypothesis_builder::SetCount((_hypothesis_builder *)v20, 2u), v6 >= 0) )
  {
    CoTaskMemFree(0);
    v23 = 0;
    v26 = 0;
    if ( (int)StringCchLengthW(L"index", 0xFFFEu, &v26) >= 0 )
    {
      v7 = v26;
      v8 = (unsigned __int16 *)CoTaskMemAlloc(2 * v26 + 2);
      v23 = v8;
      if ( v8 )
        StringCchCopyW(v8, v7 + 1, L"index");
    }
    v24 = 7;
    v25 = 0;
    v6 = _hypothesis_builder::SetAt((_hypothesis_builder *)v20, 0, (struct _attribute_t *)&v23);
    _attribute_t::FreeAll((_attribute_t *)&v23);
    if ( v6 >= 0 )
    {
      CoTaskMemFree(0);
      v23 = 0;
      v26 = 0;
      if ( (int)StringCchLengthW(L"flags", 0xFFFEu, &v26) >= 0 )
      {
        v11 = v26;
        v12 = (unsigned __int16 *)CoTaskMemAlloc(2 * v26 + 2);
        v23 = v12;
        if ( v12 )
          StringCchCopyW(v12, v11 + 1, L"flags");
      }
      v24 = 7;
      v25 = 7;
      v6 = _hypothesis_builder::SetAt((_hypothesis_builder *)v20, 1u, (struct _attribute_t *)&v23);
      _attribute_t::FreeAll((_attribute_t *)&v23);
      if ( v6 >= 0 )
      {
        v16 = _hypothesis_builder::Detach((_hypothesis_builder *)v20, a1, a2, v15);
        v6 = v16;
        if ( v16 < 0 )
          CEventLogger::LogError(
            v18,
            v17,
            L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
            0x53u,
            L"BuildAAHypotheses",
            v16);
      }
      else
      {
        CEventLogger::LogError(
          v14,
          v13,
          L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
          0x51u,
          L"BuildAAHypotheses",
          v6);
      }
    }
    else
    {
      CEventLogger::LogError(
        v10,
        v9,
        L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
        0x4Eu,
        L"BuildAAHypotheses",
        v6);
    }
  }
  else
  {
    CEventLogger::LogError(
      v5,
      v4,
      L"base\\diagnosis\\ra\\rahelperclass\\rahcutils.cpp",
      0x4Bu,
      L"BuildAAHypotheses",
      v6);
  }
  _hypothesis_builder::~_hypothesis_builder((_hypothesis_builder *)v20);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000f5bc  push    rbp
0x18000f5be  push    rbx
0x18000f5bf  push    rsi
0x18000f5c0  push    rdi
0x18000f5c1  lea     rbp, [rsp-3Fh]
0x18000f5c6  sub     rsp, 0F8h
0x18000f5cd  mov     rdi, rdx
0x18000f5d0  mov     rsi, rcx
0x18000f5d3  xorps   xmm0, xmm0
0x18000f5d6  movdqu  xmmword ptr [rsp+110h+var_E0], xmm0
0x18000f5dc  mov     [rbp+57h+var_D0], 0
0x18000f5e3  movdqu  [rbp+57h+var_C8], xmm0
0x18000f5e8  mov     dword ptr [rcx], 0
0x18000f5ee  mov     qword ptr [rdx], 0
0x18000f5f5  lea     rcx, [rsp+110h+var_E0]; this
0x18000f5fa  call    ?FreeAll@_hypothesis_builder@@QEAAXXZ; _hypothesis_builder::FreeAll(void)
0x18000f5ff  lea     rdx, aAddressacquisi; "AddressAcquisition"
0x18000f606  lea     rcx, [rsp+110h+var_E0]; this
0x18000f60b  call    ?SetName@_hypothesis_builder@@QEAAJPEBG@Z; _hypothesis_builder::SetName(ushort const *)
0x18000f610  mov     ebx, eax
0x18000f612  test    eax, eax
0x18000f614  js      short loc_18000F62B
0x18000f616  mov     edx, 2; unsigned int
0x18000f61b  lea     rcx, [rsp+110h+var_E0]; this
0x18000f620  call    ?SetCount@_hypothesis_builder@@QEAAJK@Z; _hypothesis_builder::SetCount(ulong)
0x18000f625  mov     ebx, eax
0x18000f627  test    eax, eax
0x18000f629  jns     short loc_18000F63A
0x18000f62b  mov     [rsp+110h+var_E8], ebx
0x18000f62f  mov     r9d, 4Bh ; 'K'
0x18000f635  jmp     loc_18000F790
0x18000f63a  xor     ecx, ecx; pv
0x18000f63c  call    cs:__imp_CoTaskMemFree
0x18000f642  mov     [rbp+57h+var_B8], 0
0x18000f64a  mov     [rbp+57h+arg_0], 0
0x18000f652  lea     r8, [rbp+57h+arg_0]; unsigned __int64 *
0x18000f656  mov     edx, 0FFFEh; unsigned __int64
0x18000f65b  lea     rcx, aIndex; "index"
0x18000f662  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000f667  test    eax, eax
0x18000f669  js      short loc_18000F699
0x18000f66b  mov     rbx, [rbp+57h+arg_0]
0x18000f66f  lea     rcx, ds:2[rbx*2]; cb
0x18000f677  call    cs:__imp_CoTaskMemAlloc
0x18000f67d  mov     [rbp+57h+var_B8], rax
0x18000f681  test    rax, rax
0x18000f684  jz      short loc_18000F699
0x18000f686  lea     rdx, [rbx+1]; unsigned __int64
0x18000f68a  lea     r8, aIndex; "index"
0x18000f691  mov     rcx, rax; unsigned __int16 *
0x18000f694  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f699  mov     [rbp+57h+var_B0], 7
0x18000f6a0  mov     [rbp+57h+var_A8], 0
0x18000f6a7  lea     r8, [rbp+57h+var_B8]; struct _attribute_t *
0x18000f6ab  xor     edx, edx; unsigned int
0x18000f6ad  lea     rcx, [rsp+110h+var_E0]; this
0x18000f6b2  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x18000f6b7  mov     ebx, eax
0x18000f6b9  lea     rcx, [rbp+57h+var_B8]; this
0x18000f6bd  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000f6c2  test    ebx, ebx
0x18000f6c4  jns     short loc_18000F6D5
0x18000f6c6  mov     [rsp+110h+var_E8], ebx
0x18000f6ca  mov     r9d, 4Eh ; 'N'
0x18000f6d0  jmp     loc_18000F790
0x18000f6d5  xor     ecx, ecx; pv
0x18000f6d7  call    cs:__imp_CoTaskMemFree
0x18000f6dd  mov     [rbp+57h+var_B8], 0
0x18000f6e5  mov     [rbp+57h+arg_0], 0
0x18000f6ed  lea     r8, [rbp+57h+arg_0]; unsigned __int64 *
0x18000f6f1  mov     edx, 0FFFEh; unsigned __int64
0x18000f6f6  lea     rcx, aFlags; "flags"
0x18000f6fd  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000f702  test    eax, eax
0x18000f704  js      short loc_18000F734
0x18000f706  mov     rbx, [rbp+57h+arg_0]
0x18000f70a  lea     rcx, ds:2[rbx*2]; cb
0x18000f712  call    cs:__imp_CoTaskMemAlloc
0x18000f718  mov     [rbp+57h+var_B8], rax
0x18000f71c  test    rax, rax
0x18000f71f  jz      short loc_18000F734
0x18000f721  lea     rdx, [rbx+1]; unsigned __int64
0x18000f725  lea     r8, aFlags; "flags"
0x18000f72c  mov     rcx, rax; unsigned __int16 *
0x18000f72f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f734  mov     [rbp+57h+var_B0], 7
0x18000f73b  mov     [rbp+57h+var_A8], 7
0x18000f742  lea     r8, [rbp+57h+var_B8]; struct _attribute_t *
0x18000f746  mov     edx, 1; unsigned int
0x18000f74b  lea     rcx, [rsp+110h+var_E0]; this
0x18000f750  call    ?SetAt@_hypothesis_builder@@QEAAJKAEAV_attribute_t@@@Z; _hypothesis_builder::SetAt(ulong,_attribute_t &)
0x18000f755  mov     ebx, eax
0x18000f757  lea     rcx, [rbp+57h+var_B8]; this
0x18000f75b  call    ?FreeAll@_attribute_t@@QEAAXXZ; _attribute_t::FreeAll(void)
0x18000f760  test    ebx, ebx
0x18000f762  jns     short loc_18000F770
0x18000f764  mov     [rsp+110h+var_E8], ebx
0x18000f768  mov     r9d, 51h ; 'Q'
0x18000f76e  jmp     short loc_18000F790
0x18000f770  mov     r8, rdi; struct tagHYPOTHESIS **
0x18000f773  mov     rdx, rsi; unsigned int *
0x18000f776  lea     rcx, [rsp+110h+var_E0]; this
0x18000f77b  call    ?Detach@_hypothesis_builder@@QEAAJPEAKPEAPEAUtagHYPOTHESIS@@0@Z; _hypothesis_builder::Detach(ulong *,tagHYPOTHESIS * *,ulong *)
0x18000f780  mov     ebx, eax
0x18000f782  test    eax, eax
0x18000f784  jns     short loc_18000F7A9
0x18000f786  mov     [rsp+110h+var_E8], eax; unsigned int
0x18000f78a  mov     r9d, 53h ; 'S'; unsigned int
0x18000f790  lea     rax, aBuildaahypothe; "BuildAAHypotheses"
0x18000f797  mov     [rsp+110h+var_F0], rax; unsigned __int16 *
0x18000f79c  lea     r8, aBaseDiagnosisR_5; "base\\diagnosis\\ra\\rahelperclass\\rah"...
0x18000f7a3  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x18000f7a8  nop
0x18000f7a9  lea     rcx, [rsp+110h+var_E0]; this
0x18000f7ae  call    ??1_hypothesis_builder@@QEAA@XZ; _hypothesis_builder::~_hypothesis_builder(void)
0x18000f7b3  mov     eax, ebx
0x18000f7b5  add     rsp, 0F8h
0x18000f7bc  pop     rdi
0x18000f7bd  pop     rsi
0x18000f7be  pop     rbx
0x18000f7bf  pop     rbp
0x18000f7c0  retn
```
