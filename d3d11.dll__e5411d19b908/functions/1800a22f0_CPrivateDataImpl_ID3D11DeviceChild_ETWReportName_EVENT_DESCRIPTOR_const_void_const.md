# CPrivateDataImpl<ID3D11DeviceChild>::ETWReportName(_EVENT_DESCRIPTOR const *,void const *)

- ea: `0x1800a22f0`
- end: `0x1800a2544`
- name: `?ETWReportName@?$CPrivateDataImpl@UID3D11DeviceChild@@@@QEAAXPEBU_EVENT_DESCRIPTOR@@PEBX@Z`
- size: `596`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180033914`
- `0x1800a3aa4`
- `0x1800c395c`

## callees

- `0x1800a22f0`
- `0x1800a2558`
- `0x1800a2598`
- `0x1800a25bc`
- `0x1800a2600`
- `0x1800a2698`
- `0x1800a26cc`
- `0x1800a2714`
- `0x1800a2754`
- `0x1800a278c`
- `0x1800a279c`
- `0x1800a9d20`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800a2538`
- `ntdll!EtwEventWrite` at `0x1800a2538`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a232e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800a232e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a23c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800a23c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CPrivateDataImpl<ID3D11DeviceChild>::ETWReportName(RTL_SRWLOCK *a1, __int64 a2, __int64 a3)
{
  RTL_SRWLOCK *v4; // rsi
  _BYTE *v5; // r14
  _QWORD *Ptr; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  _BYTE v11[4]; // [rsp+20h] [rbp-148h] BYREF
  int v12; // [rsp+24h] [rbp-144h] BYREF
  RTL_SRWLOCK *v13; // [rsp+28h] [rbp-140h]
  char v14[8]; // [rsp+30h] [rbp-138h] BYREF
  RTL_SRWLOCK *v15; // [rsp+38h] [rbp-130h]
  _QWORD v16[2]; // [rsp+40h] [rbp-128h] BYREF
  int v17; // [rsp+50h] [rbp-118h]
  _OWORD v18[2]; // [rsp+60h] [rbp-108h] BYREF
  _BYTE v19[32]; // [rsp+80h] [rbp-E8h] BYREF
  _BYTE v20[128]; // [rsp+A0h] [rbp-C8h] BYREF
  _QWORD v21[5]; // [rsp+120h] [rbp-48h] BYREF
  int v22; // [rsp+148h] [rbp-20h]
  int v23; // [rsp+14Ch] [rbp-1Ch]
  __int64 v24; // [rsp+180h] [rbp+18h] BYREF

  v24 = a3;
  v4 = a1 + 1;
  v13 = a1 + 1;
  v15 = a1 + 1;
  AcquireSRWLockShared(a1 + 1);
  v11[0] = 0;
  v5 = v11;
  v12 = 0;
  std::string::string(v16);
  Ptr = a1[2].Ptr;
  if ( Ptr )
  {
    v18[0] = WKPDID_D3DDebugObjectName;
    v7 = *(_QWORD *)std::_Hash<std::_Umap_traits<SGuid,CPrivateData,std::_Uhash_compare<SGuid,std::hash<SGuid>,std::equal_to<SGuid>>,std::allocator<std::pair<SGuid const,CPrivateData>>,0>>::find(
                      Ptr,
                      v14,
                      v18);
    if ( v7 == Ptr[1] )
    {
      v18[0] = WKPDID_D3DDebugObjectNameW;
      v8 = std::_Hash<std::_Umap_traits<SGuid,CPrivateData,std::_Uhash_compare<SGuid,std::hash<SGuid>,std::equal_to<SGuid>>,std::allocator<std::pair<SGuid const,CPrivateData>>,0>>::find(
             Ptr,
             v14,
             v18);
      if ( *(_QWORD *)v8 != Ptr[1] && !*(_DWORD *)(*(_QWORD *)v8 + 44LL) )
      {
        try
        {
          std::wstring::wstring(v18);
          v9 = std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v20);
          v10 = std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
                  v9,
                  v19,
                  v18);
          std::string::operator=(v16, v10);
          std::string::_Tidy_deallocate(v19);
          std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v20);
          v5 = v16;
          if ( (unsigned __int8)std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(v16) )
            v5 = (_BYTE *)v16[0];
          v12 = v17;
          std::wstring::_Tidy_deallocate(v18);
        }
        catch ( std::bad_alloc )
        {
          std::string::_Tidy_deallocate(v16);
          v4 = v13;
          goto LABEL_11;
        }
      }
    }
    else if ( !*(_DWORD *)(v7 + 44) )
    {
      if ( *(_DWORD *)(v7 + 40) <= 8u )
        v5 = (_BYTE *)(v7 + 32);
      else
        v5 = *(_BYTE **)(v7 + 32);
      v12 = *(_DWORD *)(v7 + 40);
    }
  }
  if ( v5 != v11 )
  {
    v21[0] = &v24;
    v21[1] = 8;
    v21[2] = &v12;
    v21[3] = 4;
    v21[4] = v5;
    v22 = v12;
    v23 = 0;
    EtwEventWrite(Direct3D11EtwProviderGuid_Context, EventD3D11ReportName, 3, v21);
  }
  std::string::_Tidy_deallocate(v16);
LABEL_11:
  if ( v4 )
    ReleaseSRWLockShared(v4);
}

```

## disassembly

```asm
0x1800a22f0  mov     [rsp+arg_8], rbx
0x1800a22f5  mov     [rsp+arg_18], rsi
0x1800a22fa  mov     [rsp+arg_10], r8
0x1800a22ff  push    r14
0x1800a2301  sub     rsp, 160h
0x1800a2308  mov     rax, cs:__security_cookie
0x1800a230f  xor     rax, rsp
0x1800a2312  mov     [rsp+168h+var_18], rax
0x1800a231a  mov     rbx, rcx
0x1800a231d  lea     rsi, [rcx+8]
0x1800a2321  mov     [rsp+168h+var_140], rsi
0x1800a2326  mov     [rsp+168h+var_130], rsi
0x1800a232b  mov     rcx, rsi; SRWLock
0x1800a232e  call    cs:__imp_AcquireSRWLockShared
0x1800a2334  nop
0x1800a2335  mov     [rsp+168h+var_148], 0
0x1800a233a  lea     r14, [rsp+168h+var_148]
0x1800a233f  mov     [rsp+168h+var_144], 0
0x1800a2347  lea     rcx, [rsp+168h+var_128]
0x1800a234c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1800a2351  nop
0x1800a2352  mov     rbx, [rbx+10h]
0x1800a2356  test    rbx, rbx
0x1800a2359  jz      short loc_1800A239F
0x1800a235b  movups  xmm0, xmmword ptr cs:WKPDID_D3DDebugObjectName.Data1
0x1800a2362  movdqu  [rsp+168h+var_108], xmm0
0x1800a2368  lea     r8, [rsp+168h+var_108]
0x1800a236d  lea     rdx, [rsp+168h+var_138]
0x1800a2372  mov     rcx, rbx
0x1800a2375  call    ?find@?$_Hash@V?$_Umap_traits@USGuid@@VCPrivateData@@V?$_Uhash_compare@USGuid@@V?$hash@USGuid@@@std@@U?$equal_to@USGuid@@@3@@std@@V?$allocator@U?$pair@$$CBUSGuid@@VCPrivateData@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUSGuid@@VCPrivateData@@@std@@@std@@@std@@@2@AEBUSGuid@@@Z; std::_Hash<std::_Umap_traits<SGuid,CPrivateData,std::_Uhash_compare<SGuid,std::hash<SGuid>,std::equal_to<SGuid>>,std::allocator<std::pair<SGuid const,CPrivateData>>,0>>::find(SGuid const &)
0x1800a237a  mov     rax, [rax]
0x1800a237d  cmp     rax, [rbx+8]
0x1800a2381  jz      short loc_1800A23ED
0x1800a2383  cmp     dword ptr [rax+2Ch], 0
0x1800a2387  jnz     short loc_1800A239F
0x1800a2389  mov     ecx, [rax+28h]
0x1800a238c  cmp     ecx, 8
0x1800a238f  jbe     short loc_1800A2397
0x1800a2391  mov     r14, [rax+20h]
0x1800a2395  jmp     short loc_1800A239B
0x1800a2397  lea     r14, [rax+20h]
0x1800a239b  mov     [rsp+168h+var_144], ecx
0x1800a239f  lea     rax, [rsp+168h+var_148]
0x1800a23a4  cmp     r14, rax
0x1800a23a7  jnz     loc_1800A24C9
0x1800a23ad  lea     rcx, [rsp+168h+var_128]
0x1800a23b2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800a23b7  nop
0x1800a23b8  test    rsi, rsi
0x1800a23bb  jz      short loc_1800A23C7
0x1800a23bd  mov     rcx, rsi; SRWLock
0x1800a23c0  call    cs:__imp_ReleaseSRWLockShared
0x1800a23c6  nop
0x1800a23c7  mov     rcx, [rsp+168h+var_18]
0x1800a23cf  xor     rcx, rsp; StackCookie
0x1800a23d2  call    __security_check_cookie
0x1800a23d7  lea     r11, [rsp+168h+var_8]
0x1800a23df  mov     rbx, [r11+18h]
0x1800a23e3  mov     rsi, [r11+28h]
0x1800a23e7  mov     rsp, r11
0x1800a23ea  pop     r14
0x1800a23ec  retn
0x1800a23ed  movups  xmm0, xmmword ptr cs:WKPDID_D3DDebugObjectNameW.Data1
0x1800a23f4  movdqu  [rsp+168h+var_108], xmm0
0x1800a23fa  lea     r8, [rsp+168h+var_108]
0x1800a23ff  lea     rdx, [rsp+168h+var_138]
0x1800a2404  mov     rcx, rbx
0x1800a2407  call    ?find@?$_Hash@V?$_Umap_traits@USGuid@@VCPrivateData@@V?$_Uhash_compare@USGuid@@V?$hash@USGuid@@@std@@U?$equal_to@USGuid@@@3@@std@@V?$allocator@U?$pair@$$CBUSGuid@@VCPrivateData@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUSGuid@@VCPrivateData@@@std@@@std@@@std@@@2@AEBUSGuid@@@Z; std::_Hash<std::_Umap_traits<SGuid,CPrivateData,std::_Uhash_compare<SGuid,std::hash<SGuid>,std::equal_to<SGuid>>,std::allocator<std::pair<SGuid const,CPrivateData>>,0>>::find(SGuid const &)
0x1800a240c  mov     rdx, [rax]
0x1800a240f  cmp     rdx, [rbx+8]
0x1800a2413  jz      short loc_1800A239F
0x1800a2415  add     rdx, 20h ; ' '
0x1800a2419  cmp     dword ptr [rdx+0Ch], 0
0x1800a241d  jnz     short loc_1800A239F
0x1800a241f  mov     eax, [rdx+8]
0x1800a2422  mov     r8d, eax
0x1800a2425  shr     r8, 1
0x1800a2428  cmp     eax, 8
0x1800a242b  jbe     short loc_1800A2430
0x1800a242d  mov     rdx, [rdx]
0x1800a2430  lea     rcx, [rsp+168h+var_108]
0x1800a2435  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x1800a243a  nop
0x1800a243b  lea     rcx, [rsp+168h+var_C8]
0x1800a2443  call    ??0?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800a2448  nop
0x1800a2449  lea     r8, [rsp+168h+var_108]
0x1800a244e  lea     rdx, [rsp+168h+var_E8]
0x1800a2456  mov     rcx, rax
0x1800a2459  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(std::wstring const &)
0x1800a245e  mov     rdx, rax
0x1800a2461  lea     rcx, [rsp+168h+var_128]
0x1800a2466  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800a246b  lea     rcx, [rsp+168h+var_E8]
0x1800a2473  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800a2478  nop
0x1800a2479  lea     rcx, [rsp+168h+var_C8]
0x1800a2481  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800a2486  lea     rcx, [rsp+168h+var_128]
0x1800a248b  call    ?_Large_mode_engaged@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBA_NXZ; std::_String_val<std::_Simple_types<char>>::_Large_mode_engaged(void)
0x1800a2490  lea     r14, [rsp+168h+var_128]
0x1800a2495  test    al, al
0x1800a2497  cmovnz  r14, [rsp+168h+var_128]
0x1800a249d  mov     eax, [rsp+168h+var_118]
0x1800a24a1  mov     [rsp+168h+var_144], eax
0x1800a24a5  lea     rcx, [rsp+168h+var_108]
0x1800a24aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a24af  jmp     loc_1800A239F
0x1800a24b4  lea     rcx, [rsp+168h+var_128]
0x1800a24b9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800a24be  nop
0x1800a24bf  mov     rsi, [rsp+168h+var_140]
0x1800a24c4  jmp     loc_1800A23B8
0x1800a24c9  lea     rax, [rsp+168h+arg_10]
0x1800a24d1  mov     [rsp+168h+var_48], rax
0x1800a24d9  mov     [rsp+168h+var_40], 8
0x1800a24e5  lea     rax, [rsp+168h+var_144]
0x1800a24ea  mov     [rsp+168h+var_38], rax
0x1800a24f2  mov     [rsp+168h+var_30], 4
0x1800a24fe  mov     [rsp+168h+var_28], r14
0x1800a2506  mov     eax, [rsp+168h+var_144]
0x1800a250a  mov     [rsp+168h+var_20], eax
0x1800a2511  mov     [rsp+168h+var_1C], 0
0x1800a251c  lea     r9, [rsp+168h+var_48]
0x1800a2524  mov     r8d, 3
0x1800a252a  lea     rdx, EventD3D11ReportName
0x1800a2531  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x1800a2538  call    cs:__imp_EtwEventWrite
0x1800a253e  jmp     loc_1800A23AD
```
