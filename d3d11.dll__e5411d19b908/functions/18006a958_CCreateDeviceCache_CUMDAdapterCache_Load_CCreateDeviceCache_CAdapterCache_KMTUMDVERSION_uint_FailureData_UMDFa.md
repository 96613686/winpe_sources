# CCreateDeviceCache::CUMDAdapterCache::Load(CCreateDeviceCache::CAdapterCache &,_KMTUMDVERSION,uint,FailureData::UMDFailureData &,bool &)

- ea: `0x18006a958`
- end: `0x18006af8b`
- name: `?Load@CUMDAdapterCache@CCreateDeviceCache@@QEAAJAEAVCAdapterCache@2@W4_KMTUMDVERSION@@IAEAUUMDFailureData@FailureData@@AEA_N@Z`
- size: `1587`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x180049bf8`

## callees

- `0x180011080`
- `0x1800229a0`
- `0x1800475a0`
- `0x180049310`
- `0x180051ddc`
- `0x18005a574`
- `0x18006a958`
- `0x18006af94`
- `0x18006afa0`
- `0x18006afd0`
- `0x18006b9c8`
- `0x18006bb14`
- `0x18006c184`
- `0x18006c1e8`
- `0x18006c47c`
- `0x18009797c`
- `0x1800a54a0`
- `0x1800a8674`
- `0x1800ac684`
- `0x1800acae8`
- `0x1800ae16c`
- `0x1800dd664`

## import_xrefs

- `ext-ms-mf-pal-l2-1-0!XboxIsAsyncComputeOnlyDevice` at `0x18006ae3f`
- `ext-ms-mf-pal-l2-1-0!XboxIsAsyncComputeOnlyDevice` at `0x18006ae3f`
- `ext-ms-mf-pal-l2-1-0!XboxGetAsyncCompute3DPipeplineCaps` at `0x18006ae4d`
- `ext-ms-mf-pal-l2-1-0!XboxGetAsyncCompute3DPipeplineCaps` at `0x18006ae4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCreateDeviceCache::CUMDAdapterCache::Load(
        _QWORD *a1,
        _QWORD *a2,
        int a3,
        unsigned int a4,
        __int64 a5,
        _BYTE *a6)
{
  _BYTE *v10; // rax
  unsigned int v11; // edx
  NDXGI::CUMDAdapter *v12; // rcx
  bool v13; // zf
  NDXGI::CUMDAdapter *v14; // rcx
  int v15; // eax
  __int64 v17; // r14
  _DWORD *v18; // rdi
  signed int Caps; // eax
  bool v20; // r9
  bool v21; // r9
  int v22; // r12d
  int v23; // r15d
  int v24; // ebx
  unsigned int *v25; // rcx
  unsigned int *v26; // rcx
  int v27; // r8d
  unsigned int *v28; // rcx
  int v29; // r8d
  int v30; // eax
  int v31; // r9d
  int v32; // r10d
  unsigned __int64 **v33; // rdi
  signed int SupportedVersions; // eax
  bool v35; // r9
  __int64 v36; // r9
  unsigned __int64 *v37; // r8
  unsigned __int64 v38; // rdx
  signed int v39; // eax
  _BOOL8 v40; // r9
  unsigned __int64 *v41; // rcx
  __int64 v42; // rax
  int v43; // eax
  __int64 v44; // rbx
  __int64 pExceptionObject; // [rsp+30h] [rbp-49h] BYREF
  __int64 v46; // [rsp+38h] [rbp-41h]
  __int128 v47; // [rsp+40h] [rbp-39h]
  __int128 v48; // [rsp+50h] [rbp-29h] BYREF
  __int128 v49; // [rsp+60h] [rbp-19h]
  __int128 v50; // [rsp+70h] [rbp-9h]
  int v51; // [rsp+80h] [rbp+7h]
  int v52; // [rsp+84h] [rbp+Bh]
  __int128 v53; // [rsp+88h] [rbp+Fh]
  unsigned int *v54; // [rsp+D0h] [rbp+57h] BYREF

  if ( dword_18022B910 < 4 )
    dword_18022B914 = 4;
  dword_18022B910 = 4;
  *a6 = 0;
  if ( !*a1 )
  {
    if ( qword_18022B840 )
    {
      std::unique_ptr<NDXGI::CUMDAdapter>::operator=<std::default_delete<NDXGI::CUMDAdapter>,0>(a1, &qword_18022B840);
      *((_DWORD *)a1 + 2) = 0;
    }
    else
    {
      if ( a2[2] )
      {
        v10 = operator new(0x3B8u);
        a6 = v10;
        if ( v10 )
          v10 = (_BYTE *)NDXGI::CUMDAdapter::CUMDAdapter(v10, a2[2], (unsigned int)a3, a4);
      }
      else
      {
        v10 = operator new(0x3B8u);
        a6 = v10;
        if ( v10 )
          v10 = (_BYTE *)NDXGI::CUMDAdapter::CUMDAdapter((__int64)v10, a2[4], a3, a4);
      }
      v12 = (NDXGI::CUMDAdapter *)*a1;
      v13 = *a1 == 0;
      *a1 = v10;
      if ( !v13 )
        NDXGI::CUMDAdapter::`scalar deleting destructor'(v12, v11);
    }
  }
  if ( (int)NDXGI::CUMDAdapter::UMDLoadStatus((NDXGI::CUMDAdapter *)*a1) < 0 )
    return NDXGI::CUMDAdapter::UMDLoadStatus(v14);
  v15 = *((_DWORD *)a1 + 2);
  if ( v15 == 1 )
  {
    v48 = 0;
    v49 = 0;
    v50 = 0;
    v52 = 7;
    v53 = 0;
    a6 = 0;
    DWORD2(v49) = 0;
    v51 = BYTE1(a4) & 1;
    v42 = a2[3];
    if ( !v42 )
      v42 = a2[4];
    *(_QWORD *)&v49 = v42;
    *(_QWORD *)&v53 = &a6;
    if ( a3 == 3 )
      v15 = NDXGI::CUMDAdapter::OpenAdapterD3D11On12(v14, (struct D3D11On12::SOpenAdapterArgs *)&v48);
    else
      v15 = NDXGI::CUMDAdapter::OpenAdapter10_2(v14);
    *((_DWORD *)a1 + 2) = v15;
  }
  if ( v15 >= 0 )
  {
    v17 = a5;
    if ( a3 >= 2 && *((_DWORD *)a1 + 4) == 1 )
    {
      v18 = (_DWORD *)a1 + 3;
      Caps = NDXGI::CUMDAdapter::GetCaps(*a1, 130, 0, (char *)a1 + 12, 4);
      *((_DWORD *)a1 + 4) = Caps;
      if ( Caps < 0 )
      {
        CModule::RecordJournal((CModule *)&g_Module, Caps, "Get3DPipelineSupportCaps", v20, 1);
      }
      else
      {
        if ( (unsigned __int8)IsXboxIsAsyncComputeOnlyDevicePresent() && (unsigned int)XboxIsAsyncComputeOnlyDevice(a4) )
          *v18 = XboxGetAsyncCompute3DPipeplineCaps();
        v22 = *v18 & 0xF;
        v23 = (*v18 >> 7) & 3;
        v24 = (*v18 >> 4) & 7;
        if ( (((v22 | (16 * v23)) + 1) & (v22 | (16 * v23))) != 0 )
        {
          CModule::RecordJournal((CModule *)&g_Module, 0x887A0020, "Driver returned invalid pipeline caps", v21, 1);
          *v18 = 0;
        }
        if ( ((v24 + 1) & v24) != 0 )
          CModule::RecordJournal((CModule *)&g_Module, 0x887A0020, "Driver returned invalid pipeline caps", v21, 1);
        LODWORD(a6) = v23;
        v25 = *(unsigned int **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                  &pExceptionObject,
                                  &a6);
        v54 = v25;
        if ( _isa_available < 2 )
          _lambda_47fe307f83534bca195fd7fa7f4de4c9_::operator()(*v25);
        else
          _lambda_0fa26aec79ad2a0f7e7ecd9dbd46e9ca_::operator()<_lambda_bd243a0c92b4070442334672389c73ef_>(&v54);
        LODWORD(a6) = v22 & 0xF;
        v26 = *(unsigned int **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                  &pExceptionObject,
                                  &a6);
        v54 = v26;
        if ( v27 >= 2 )
          _lambda_0fa26aec79ad2a0f7e7ecd9dbd46e9ca_::operator()<_lambda_bd243a0c92b4070442334672389c73ef_>(&v54);
        else
          _lambda_47fe307f83534bca195fd7fa7f4de4c9_::operator()(*v26);
        LODWORD(a6) = v24 & 7;
        v28 = *(unsigned int **)wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                                  &pExceptionObject,
                                  &a6);
        v54 = v28;
        if ( v29 >= 2 )
          v30 = _lambda_0fa26aec79ad2a0f7e7ecd9dbd46e9ca_::operator()<_lambda_bd243a0c92b4070442334672389c73ef_>(&v54);
        else
          v30 = _lambda_47fe307f83534bca195fd7fa7f4de4c9_::operator()(*v28);
        *(_DWORD *)(v17 + 24) = 0;
        if ( v30 )
        {
          v43 = v30 - 1;
          if ( v43 )
          {
            if ( v43 == 1 )
              *(_DWORD *)(v17 + 24) = 37376;
            else
              *(_DWORD *)(v17 + 24) = 37632;
          }
          else
          {
            *(_DWORD *)(v17 + 24) = 37120;
          }
        }
        switch ( v31 )
        {
          case 1:
            *(_DWORD *)(v17 + 24) = 40960;
            break;
          case 2:
            *(_DWORD *)(v17 + 24) = 41216;
            break;
          case 3:
            *(_DWORD *)(v17 + 24) = 45056;
            break;
          case 4:
            *(_DWORD *)(v17 + 24) = 45312;
            break;
        }
        if ( v32 )
        {
          if ( v32 == 1 )
            *(_DWORD *)(v17 + 24) = 49152;
          else
            *(_DWORD *)(v17 + 24) = 49408;
        }
      }
    }
    v33 = (unsigned __int64 **)(a1 + 3);
    if ( a1[3] == a1[4] )
    {
      LODWORD(a6) = 0;
      SupportedVersions = NDXGI::CUMDAdapter::GetSupportedVersions((NDXGI::CUMDAdapter *)*a1, (unsigned int *)&a6, 0);
      if ( SupportedVersions < 0 )
      {
        CModule::RecordJournal(
          (CModule *)&g_Module,
          SupportedVersions,
          "Driver failed to return number of available versions.",
          v35,
          1);
        pExceptionObject = (__int64)&_com_error::`vftable';
        LODWORD(v46) = -2005270496;
        v47 = 0;
        throw (_com_error *)&pExceptionObject;
      }
      v36 = a1[4];
      v37 = *v33;
      v38 = (v36 - a1[3]) >> 3;
      if ( (unsigned int)a6 < v38 )
      {
        a1[4] = &v37[(unsigned int)a6];
      }
      else if ( (unsigned int)a6 > v38 )
      {
        if ( (unsigned int)a6 <= (unsigned __int64)((__int64)(a1[5] - (_QWORD)v37) >> 3) )
        {
          v44 = v36 + 8 * ((unsigned int)a6 - v38);
          std::_Zero_range<unsigned __int64 *>(a1[4], v44);
          a1[4] = v44;
        }
        else
        {
          std::vector<unsigned __int64>::_Resize_reallocate<std::_Value_init_tag>(a1 + 3, (unsigned int)a6);
        }
      }
      v39 = NDXGI::CUMDAdapter::GetSupportedVersions((NDXGI::CUMDAdapter *)*a1, (unsigned int *)&a6, *v33);
      if ( v39 < 0 )
      {
        CModule::RecordJournal((CModule *)&g_Module, v39, "Driver failed to fill DDI version info.", v40, 1);
        pExceptionObject = (__int64)&_com_error::`vftable';
        LODWORD(v46) = -2005270496;
        v47 = 0;
        throw (_com_error *)&pExceptionObject;
      }
      v41 = *v33;
      if ( (unsigned int)a6 < (unsigned __int64)((__int64)(a1[4] - a1[3]) >> 3) )
        a1[4] = &v41[(unsigned int)a6];
      if ( (unsigned __int64 **)v17 != v33 )
        std::vector<unsigned __int64>::_Assign_counted_range<unsigned __int64 *>(
          v17,
          v41,
          (__int64)(a1[4] - (_QWORD)v41) >> 3);
      LOBYTE(v40) = (_BYTE)a6;
      std::_Sort_unchecked<unsigned __int64 *,std::greater<unsigned __int64>>(
        *v33,
        a1[4],
        (__int64)(a1[4] - (_QWORD)*v33) >> 3,
        v40);
    }
  }
  else
  {
    pExceptionObject = 0xA000200010000LL;
    v46 = 0xA000100040000LL;
    std::vector<CAsynchronous<ID3D11Asynchronous> *,std::allocator<CAsynchronous<ID3D11Asynchronous> *>>::_Insert_counted_range<CAsynchronous<ID3D11Asynchronous> * *>(
      a1 + 3,
      a1[4],
      &pExceptionObject,
      2);
    *(_DWORD *)(a5 + 24) = 41216;
  }
  return 0;
}

```

## disassembly

```asm
0x18006a958  mov     [rsp-8+arg_8], rbx
0x18006a95d  mov     [rsp-8+arg_10], rsi
0x18006a962  push    rbp
0x18006a963  push    rdi
0x18006a964  push    r12
0x18006a966  push    r14
0x18006a968  push    r15
0x18006a96a  lea     rbp, [rsp-27h]
0x18006a96f  sub     rsp, 0A0h
0x18006a976  mov     r15d, r9d
0x18006a979  mov     edi, r8d
0x18006a97c  mov     rbx, rdx
0x18006a97f  mov     rsi, rcx
0x18006a982  mov     r12d, 4
0x18006a988  cmp     cs:dword_18022B910, r12d
0x18006a98f  jl      loc_18006ADEF
0x18006a995  mov     cs:dword_18022B910, r12d
0x18006a99c  mov     rax, [rbp+47h+arg_28]
0x18006a9a0  mov     byte ptr [rax], 0
0x18006a9a3  cmp     qword ptr [rcx], 0
0x18006a9a7  jnz     short loc_18006A9F7
0x18006a9a9  cmp     cs:qword_18022B840, 0
0x18006a9b1  jnz     loc_18006AD67
0x18006a9b7  mov     ecx, 3B8h; dwBytes
0x18006a9bc  cmp     qword ptr [rdx+10h], 0
0x18006a9c1  jz      loc_18006ADFB
0x18006a9c7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006a9cc  mov     [rbp+47h+arg_28], rax
0x18006a9d0  test    rax, rax
0x18006a9d3  jz      short loc_18006A9E8
0x18006a9d5  mov     r9d, r15d
0x18006a9d8  mov     r8d, edi
0x18006a9db  mov     rdx, [rbx+10h]
0x18006a9df  mov     rcx, rax
0x18006a9e2  call    ??0CUMDAdapter@NDXGI@@QEAA@PEAUIDXGIAdapterInternal2@@W4_KMTUMDVERSION@@I@Z; NDXGI::CUMDAdapter::CUMDAdapter(IDXGIAdapterInternal2 *,_KMTUMDVERSION,uint)
0x18006a9e7  nop
0x18006a9e8  mov     rcx, [rsi]; this
0x18006a9eb  test    rcx, rcx
0x18006a9ee  mov     [rsi], rax
0x18006a9f1  jnz     loc_18006AD5D
0x18006a9f7  mov     rcx, [rsi]; this
0x18006a9fa  call    ?UMDLoadStatus@CUMDAdapter@NDXGI@@QEBAJXZ; NDXGI::CUMDAdapter::UMDLoadStatus(void)
0x18006a9ff  test    eax, eax
0x18006aa01  js      loc_18006AD7F
0x18006aa07  mov     eax, [rsi+8]
0x18006aa0a  cmp     eax, 1
0x18006aa0d  jz      loc_18006ACAC
0x18006aa13  test    eax, eax
0x18006aa15  jns     short loc_18006AA73
0x18006aa17  mov     rax, 0A000200010000h
0x18006aa21  mov     [rbp+47h+pExceptionObject], rax
0x18006aa25  mov     rax, 0A000100040000h
0x18006aa2f  mov     [rbp+47h+var_88], rax
0x18006aa33  lea     rcx, [rsi+18h]
0x18006aa37  mov     r9d, 2
0x18006aa3d  lea     r8, [rbp+47h+pExceptionObject]
0x18006aa41  mov     rdx, [rsi+20h]
0x18006aa45  call    ??$_Insert_counted_range@PEAPEAV?$CAsynchronous@UID3D11Asynchronous@@@@@?$vector@PEAV?$CAsynchronous@UID3D11Asynchronous@@@@V?$allocator@PEAV?$CAsynchronous@UID3D11Asynchronous@@@@@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@PEAV?$CAsynchronous@UID3D11Asynchronous@@@@@std@@@std@@@1@PEAPEAV?$CAsynchronous@UID3D11Asynchronous@@@@_K@Z; std::vector<CAsynchronous<ID3D11Asynchronous> *,std::allocator<CAsynchronous<ID3D11Asynchronous> *>>::_Insert_counted_range<CAsynchronous<ID3D11Asynchronous> * *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CAsynchronous<ID3D11Asynchronous> *>>>,CAsynchronous<ID3D11Asynchronous> * *,unsigned __int64)
0x18006aa4a  mov     rax, [rbp+47h+arg_20]
0x18006aa4e  mov     dword ptr [rax+18h], 0A100h
0x18006aa55  xor     eax, eax
0x18006aa57  lea     r11, [rsp+0C0h+var_20]
0x18006aa5f  mov     rbx, [r11+38h]
0x18006aa63  mov     rsi, [r11+40h]
0x18006aa67  mov     rsp, r11
0x18006aa6a  pop     r15
0x18006aa6c  pop     r14
0x18006aa6e  pop     r12
0x18006aa70  pop     rdi
0x18006aa71  pop     rbp
0x18006aa72  retn
0x18006aa73  mov     r14, [rbp+47h+arg_20]
0x18006aa77  cmp     edi, 2
0x18006aa7a  jl      loc_18006ABD5
0x18006aa80  cmp     dword ptr [rsi+10h], 1
0x18006aa84  jnz     loc_18006ABD5
0x18006aa8a  lea     rdi, [rsi+0Ch]
0x18006aa8e  mov     dword ptr [rsp+0C0h+var_A0], r12d
0x18006aa93  mov     r9, rdi
0x18006aa96  xor     r8d, r8d
0x18006aa99  mov     edx, 82h
0x18006aa9e  mov     rcx, [rsi]
0x18006aaa1  call    ?GetCaps@CUMDAdapter@NDXGI@@QEAAJW4D3D10_2DDICAPS_TYPE@@PEAX1I@Z; NDXGI::CUMDAdapter::GetCaps(D3D10_2DDICAPS_TYPE,void *,void *,uint)
0x18006aaa6  mov     [rsi+10h], eax
0x18006aaa9  test    eax, eax
0x18006aaab  js      loc_18006ADD0
0x18006aab1  call    IsXboxIsAsyncComputeOnlyDevicePresent
0x18006aab6  test    al, al
0x18006aab8  jnz     loc_18006AE3C
0x18006aabe  mov     ebx, [rdi]
0x18006aac0  mov     r12d, ebx
0x18006aac3  and     r12d, 0Fh
0x18006aac7  mov     r15d, ebx
0x18006aaca  shr     r15d, 7
0x18006aace  and     r15d, 3
0x18006aad2  shr     ebx, 4
0x18006aad5  and     ebx, 7
0x18006aad8  mov     ecx, r15d
0x18006aadb  shl     ecx, 4
0x18006aade  or      ecx, r12d
0x18006aae1  lea     eax, [rcx+1]
0x18006aae4  test    ecx, eax
0x18006aae6  jnz     loc_18006AE5A
0x18006aaec  lea     eax, [rbx+1]
0x18006aaef  test    ebx, eax
0x18006aaf1  jnz     loc_18006AE82
0x18006aaf7  and     r15d, 3
0x18006aafb  mov     dword ptr [rbp+47h+arg_28], r15d
0x18006aaff  lea     rdx, [rbp+47h+arg_28]
0x18006ab03  lea     rcx, [rbp+47h+pExceptionObject]
0x18006ab07  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18006ab0c  mov     rcx, [rax]
0x18006ab0f  mov     [rbp+47h+arg_0], rcx
0x18006ab13  mov     r8d, cs:__isa_available
0x18006ab1a  cmp     r8d, 2
0x18006ab1e  jl      loc_18006AD2B
0x18006ab24  lea     rcx, [rbp+47h+arg_0]
0x18006ab28  call    ??$?RV_lambda_bd243a0c92b4070442334672389c73ef_@@@_lambda_0fa26aec79ad2a0f7e7ecd9dbd46e9ca_@@QEBA?A_PV_lambda_bd243a0c92b4070442334672389c73ef_@@@Z
0x18006ab2d  mov     r10, rax
0x18006ab30  and     r12d, 0Fh
0x18006ab34  mov     dword ptr [rbp+47h+arg_28], r12d
0x18006ab38  lea     rdx, [rbp+47h+arg_28]
0x18006ab3c  lea     rcx, [rbp+47h+pExceptionObject]
0x18006ab40  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18006ab45  mov     rcx, [rax]
0x18006ab48  mov     [rbp+47h+arg_0], rcx
0x18006ab4c  cmp     r8d, 2
0x18006ab50  jge     loc_18006AD0C
0x18006ab56  mov     ecx, [rcx]
0x18006ab58  call    ??R_lambda_47fe307f83534bca195fd7fa7f4de4c9_@@SA@K@Z; _lambda_47fe307f83534bca195fd7fa7f4de4c9_::operator()(ulong)
0x18006ab5d  movsxd  r9, eax
0x18006ab60  and     ebx, 7
0x18006ab63  mov     dword ptr [rbp+47h+arg_28], ebx
0x18006ab66  lea     rdx, [rbp+47h+arg_28]
0x18006ab6a  lea     rcx, [rbp+47h+pExceptionObject]
0x18006ab6e  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18006ab73  mov     rcx, [rax]
0x18006ab76  mov     [rbp+47h+arg_0], rcx
0x18006ab7a  cmp     r8d, 2
0x18006ab7e  jge     loc_18006AD1D
0x18006ab84  mov     ecx, [rcx]
0x18006ab86  call    ??R_lambda_47fe307f83534bca195fd7fa7f4de4c9_@@SA@K@Z; _lambda_47fe307f83534bca195fd7fa7f4de4c9_::operator()(ulong)
0x18006ab8b  cdqe
0x18006ab8d  mov     dword ptr [r14+18h], 0
0x18006ab95  add     eax, 3
0x18006ab98  sub     eax, 3
0x18006ab9b  jnz     loc_18006AD96
0x18006aba1  lea     eax, [r9-1]
0x18006aba5  test    eax, eax
0x18006aba7  jz      loc_18006AED8
0x18006abad  cmp     eax, 1
0x18006abb0  jz      loc_18006AECB
0x18006abb6  cmp     eax, 2
0x18006abb9  jz      loc_18006AEBE
0x18006abbf  cmp     eax, 3
0x18006abc2  jz      loc_18006AD3A
0x18006abc8  lea     eax, [r10+6]
0x18006abcc  sub     eax, 6
0x18006abcf  jnz     loc_18006AD47
0x18006abd5  lea     rdi, [rsi+18h]
0x18006abd9  mov     rax, [rdi+8]
0x18006abdd  cmp     [rdi], rax
0x18006abe0  jnz     loc_18006AA55
0x18006abe6  mov     dword ptr [rbp+47h+arg_28], 0
0x18006abed  xor     r8d, r8d; unsigned __int64 *
0x18006abf0  lea     rdx, [rbp+47h+arg_28]; unsigned int *
0x18006abf4  mov     rcx, [rsi]; this
0x18006abf7  call    ?GetSupportedVersions@CUMDAdapter@NDXGI@@QEAAJPEAIPEA_K@Z; NDXGI::CUMDAdapter::GetSupportedVersions(uint *,unsigned __int64 *)
0x18006abfc  test    eax, eax
0x18006abfe  js      loc_18006AEF2
0x18006ac04  mov     ecx, dword ptr [rbp+47h+arg_28]
0x18006ac07  mov     r9, [rdi+8]
0x18006ac0b  mov     r8, [rdi]
0x18006ac0e  mov     rdx, r9
0x18006ac11  sub     rdx, r8
0x18006ac14  sar     rdx, 3
0x18006ac18  cmp     rcx, rdx
0x18006ac1b  jb      loc_18006AD89
0x18006ac21  jbe     short loc_18006AC41
0x18006ac23  mov     rax, [rdi+10h]
0x18006ac27  sub     rax, r8
0x18006ac2a  sar     rax, 3
0x18006ac2e  cmp     rcx, rax
0x18006ac31  jbe     loc_18006ADB5
0x18006ac37  mov     edx, ecx
0x18006ac39  mov     rcx, rdi
0x18006ac3c  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@_KV?$allocator@_K@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<unsigned __int64>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18006ac41  mov     r8, [rdi]; unsigned __int64 *
0x18006ac44  lea     rdx, [rbp+47h+arg_28]; unsigned int *
0x18006ac48  mov     rcx, [rsi]; this
0x18006ac4b  call    ?GetSupportedVersions@CUMDAdapter@NDXGI@@QEAAJPEAIPEA_K@Z; NDXGI::CUMDAdapter::GetSupportedVersions(uint *,unsigned __int64 *)
0x18006ac50  test    eax, eax
0x18006ac52  js      loc_18006AF38
0x18006ac58  mov     rcx, [rdi]
0x18006ac5b  mov     edx, dword ptr [rbp+47h+arg_28]
0x18006ac5e  mov     rax, [rdi+8]
0x18006ac62  sub     rax, rcx
0x18006ac65  sar     rax, 3
0x18006ac69  cmp     rdx, rax
0x18006ac6c  jb      loc_18006AF7E
0x18006ac72  cmp     r14, rdi
0x18006ac75  jz      short loc_18006AC8D
0x18006ac77  mov     r8, [rdi+8]
0x18006ac7b  sub     r8, rcx
0x18006ac7e  sar     r8, 3
0x18006ac82  mov     rdx, rcx
0x18006ac85  mov     rcx, r14
0x18006ac88  call    ??$_Assign_counted_range@PEA_K@?$vector@_KV?$allocator@_K@std@@@std@@AEAAXPEA_K_K@Z; std::vector<unsigned __int64>::_Assign_counted_range<unsigned __int64 *>(unsigned __int64 *,unsigned __int64)
0x18006ac8d  mov     rdx, [rsi+20h]
0x18006ac91  mov     r8, rdx
0x18006ac94  sub     r8, [rdi]
0x18006ac97  sar     r8, 3
0x18006ac9b  mov     r9b, byte ptr [rbp+47h+arg_28]
0x18006ac9f  mov     rcx, [rdi]
0x18006aca2  call    ??$_Sort_unchecked@PEA_KU?$greater@_K@std@@@std@@YAXPEA_K0_JU?$greater@_K@0@@Z; std::_Sort_unchecked<unsigned __int64 *,std::greater<unsigned __int64>>(unsigned __int64 *,unsigned __int64 *,__int64,std::greater<unsigned __int64>)
0x18006aca7  jmp     loc_18006AA55
0x18006acac  xor     eax, eax
0x18006acae  xorps   xmm0, xmm0
0x18006acb1  movups  [rbp+47h+var_70], xmm0
0x18006acb5  movups  [rbp+47h+var_60], xmm0
0x18006acb9  movups  [rbp+47h+var_50], xmm0
0x18006acbd  mov     [rbp+47h+var_40], eax
0x18006acc0  mov     [rbp+47h+var_3C], 7
0x18006acc7  movups  [rbp+47h+var_38], xmm0
0x18006accb  mov     [rbp+47h+arg_28], rax
0x18006accf  mov     dword ptr [rbp+47h+var_60+8], eax
0x18006acd2  mov     eax, r15d
0x18006acd5  shr     eax, 8
0x18006acd8  and     al, 1
0x18006acda  mov     byte ptr [rbp+47h+var_40], al
0x18006acdd  mov     rax, [rbx+18h]
0x18006ace1  test    rax, rax
0x18006ace4  jz      loc_18006AE25
0x18006acea  mov     qword ptr [rbp+47h+var_60], rax
0x18006acee  lea     rax, [rbp+47h+arg_28]
0x18006acf2  mov     qword ptr [rbp+47h+var_38], rax
0x18006acf6  cmp     edi, 3
0x18006acf9  jz      loc_18006AE2E
0x18006acff  call    ?OpenAdapter10_2@CUMDAdapter@NDXGI@@QEAAJXZ; NDXGI::CUMDAdapter::OpenAdapter10_2(void)
0x18006ad04  mov     [rsi+8], eax
0x18006ad07  jmp     loc_18006AA13
0x18006ad0c  lea     rcx, [rbp+47h+arg_0]
0x18006ad10  call    ??$?RV_lambda_bd243a0c92b4070442334672389c73ef_@@@_lambda_0fa26aec79ad2a0f7e7ecd9dbd46e9ca_@@QEBA?A_PV_lambda_bd243a0c92b4070442334672389c73ef_@@@Z
0x18006ad15  mov     r9, rax
0x18006ad18  jmp     loc_18006AB60
0x18006ad1d  lea     rcx, [rbp+47h+arg_0]
0x18006ad21  call    ??$?RV_lambda_bd243a0c92b4070442334672389c73ef_@@@_lambda_0fa26aec79ad2a0f7e7ecd9dbd46e9ca_@@QEBA?A_PV_lambda_bd243a0c92b4070442334672389c73ef_@@@Z
0x18006ad26  jmp     loc_18006AB8D
0x18006ad2b  mov     ecx, [rcx]
0x18006ad2d  call    ??R_lambda_47fe307f83534bca195fd7fa7f4de4c9_@@SA@K@Z; _lambda_47fe307f83534bca195fd7fa7f4de4c9_::operator()(ulong)
0x18006ad32  movsxd  r10, eax
0x18006ad35  jmp     loc_18006AB30
0x18006ad3a  mov     dword ptr [r14+18h], 0B100h
0x18006ad42  jmp     loc_18006ABC8
0x18006ad47  cmp     eax, 1
0x18006ad4a  jz      loc_18006AEE5
0x18006ad50  mov     dword ptr [r14+18h], 0C100h
0x18006ad58  jmp     loc_18006ABD5
0x18006ad5d  call    ??_GCUMDAdapter@NDXGI@@QEAAPEAXI@Z; NDXGI::CUMDAdapter::`scalar deleting destructor'(uint)
0x18006ad62  jmp     loc_18006A9F7
0x18006ad67  lea     rdx, qword_18022B840
0x18006ad6e  call    ??$?4U?$default_delete@VCUMDAdapter@NDXGI@@@std@@$0A@@?$unique_ptr@VCUMDAdapter@NDXGI@@U?$default_delete@VCUMDAdapter@NDXGI@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<NDXGI::CUMDAdapter>::operator=<std::default_delete<NDXGI::CUMDAdapter>,0>(std::unique_ptr<NDXGI::CUMDAdapter> &&)
0x18006ad73  mov     dword ptr [rsi+8], 0
0x18006ad7a  jmp     loc_18006A9F7
0x18006ad7f  call    ?UMDLoadStatus@CUMDAdapter@NDXGI@@QEBAJXZ; NDXGI::CUMDAdapter::UMDLoadStatus(void)
0x18006ad84  jmp     loc_18006AA57
0x18006ad89  lea     rax, [r8+rcx*8]
0x18006ad8d  mov     [rdi+8], rax
0x18006ad91  jmp     loc_18006AC41
0x18006ad96  sub     eax, 1
0x18006ad99  jz      loc_18006AEB1
0x18006ad9f  cmp     eax, 1
0x18006ada2  jz      loc_18006AEA4
0x18006ada8  mov     dword ptr [r14+18h], 9300h
0x18006adb0  jmp     loc_18006ABA1
0x18006adb5  sub     rcx, rdx
0x18006adb8  lea     rbx, [r9+rcx*8]
0x18006adbc  mov     rdx, rbx
0x18006adbf  mov     rcx, r9
0x18006adc2  call    ??$_Zero_range@PEA_K@std@@YAPEA_KQEA_K0@Z; std::_Zero_range<unsigned __int64 *>(unsigned __int64 * const,unsigned __int64 * const)
0x18006adc7  mov     [rdi+8], rbx
0x18006adcb  jmp     loc_18006AC41
0x18006add0  mov     [rsp+0C0h+var_A0], 1; bool
0x18006add5  lea     r8, aGet3dpipelines; "Get3DPipelineSupportCaps"
0x18006addc  mov     edx, eax; unsigned int
0x18006adde  lea     rcx, ?g_Module@@3VCModule@@A; this
0x18006ade5  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x18006adea  jmp     loc_18006ABD5
0x18006adef  mov     cs:dword_18022B914, r12d
0x18006adf6  jmp     loc_18006A995
0x18006adfb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006ae00  mov     [rbp+47h+arg_28], rax
0x18006ae04  test    rax, rax
0x18006ae07  jz      loc_1800EC9E6
0x18006ae0d  mov     r9d, r15d
0x18006ae10  mov     r8d, edi
0x18006ae13  mov     rdx, [rbx+20h]
0x18006ae17  mov     rcx, rax
0x18006ae1a  call    ??0CUMDAdapter@NDXGI@@QEAA@PEAUIDXCoreAdapter@@W4_KMTUMDVERSION@@I@Z; NDXGI::CUMDAdapter::CUMDAdapter(IDXCoreAdapter *,_KMTUMDVERSION,uint)
0x18006ae1f  nop
  ... truncated ...
```
