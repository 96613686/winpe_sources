# CUiccHandler2::PostProcess(long,_MVProvisionData *,long)

- ea: `0x180031100`
- end: `0x1800313fe`
- name: `?PostProcess@CUiccHandler2@@UEAAJJPEAU_MVProvisionData@@J@Z`
- size: `766`
- prototype: `__int64 __fastcall(CUiccHandler2 *__hidden this, int, struct _MVProvisionData *, int)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180002034`
- `0x1800076a4`
- `0x18000e1f8`
- `0x180012390`
- `0x180012e18`
- `0x180026620`
- `0x18002b358`
- `0x18002c1fc`
- `0x180030840`
- `0x180031100`
- `0x1800317c4`
- `0x1800320e0`
- `0x18003575c`
- `0x1800376bc`
- `0x18003b9a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031377`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031377`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180031283`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180031283`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031347`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180031347`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CUiccHandler2::PostProcess(CUiccHandler2 *this, int a2, struct _MVProvisionData *a3, int a4)
{
  __int64 *v7; // rax
  unsigned __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 v10; // r14
  void **v11; // rdx
  __int64 v12; // r15
  _QWORD *v13; // rax
  _QWORD *v14; // rbx
  const unsigned int *v15; // rdx
  const unsigned __int16 *v16; // r8
  const unsigned __int16 *v17; // r9
  int ContextSubKeyPath; // ebx
  LSTATUS ValueW; // eax
  const char *v20; // r9
  __int64 result; // rax
  __int64 v22; // rax
  int v23; // r8d
  unsigned int Key; // eax
  int i; // ebx
  int pdwType; // [rsp+20h] [rbp-2E8h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-2E8h]
  int v28; // [rsp+50h] [rbp-2B8h] BYREF
  DWORD pcbData[2]; // [rsp+58h] [rbp-2B0h] BYREF
  WCHAR v30[8]; // [rsp+70h] [rbp-298h] BYREF
  __int64 v31; // [rsp+80h] [rbp-288h]
  __int64 v32; // [rsp+88h] [rbp-280h]
  _QWORD *v33; // [rsp+90h] [rbp-278h]
  int v34; // [rsp+98h] [rbp-270h]
  int pvData; // [rsp+9Ch] [rbp-26Ch] BYREF
  _QWORD v36[2]; // [rsp+A0h] [rbp-268h] BYREF
  WCHAR SubKey[264]; // [rsp+B0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+0h]

  try
  {
    v28 = a2;
    v7 = (__int64 *)*((_QWORD *)this + 6);
    v8 = *((unsigned int *)this + 7);
    v9 = *v7;
    if ( 0xAAAAAAAAAAAAAAABuLL * ((v7[1] - *v7) >> 4) <= v8 )
      std::vector<UiccKeySet>::_Xran();
    v10 = 6 * v8;
    v11 = *(void ***)(v9 + 48 * v8);
    v32 = 7;
    v31 = 0;
    v30[0] = 0;
    std::wstring::assign((void **)v30, v11, 0, 0xFFFFFFFFFFFFFFFFuLL);
    v12 = *(_QWORD *)(*(_QWORD *)(v9 + 8 * v10) + 56LL);
    v13 = operator new(0x20u);
    v14 = v13;
    *(_QWORD *)pcbData = v13;
    if ( v13 )
    {
      v13[3] = 7;
      v13[2] = 0;
      *(_WORD *)v13 = 0;
      std::wstring::assign((void **)v13, (void **)(v12 + 32), 0, 0xFFFFFFFFFFFFFFFFuLL);
    }
    else
    {
      v14 = 0;
    }
    v33 = v14;
    v34 = *(_DWORD *)(*(_QWORD *)(v9 + 8 * v10) + 100LL);
    pvData = 0;
    v36[0] = 0;
    v36[1] = 0;
    v36[0] = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>>::_Buyheadnode();
    pcbData[0] = 4;
    ContextSubKeyPath = MvGetContextSubKeyPath(this, v15, v16, v17, SubKey);
    if ( ContextSubKeyPath >= 0 )
    {
      ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"UIRequired", 0x10u, 0, &pvData, pcbData);
      ContextSubKeyPath = ValueW;
      if ( ValueW == 2 )
      {
        pvData = 0;
LABEL_14:
        v22 = std::_Tree_buy<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>::_Buynode<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 &,long &>(
                v36,
                (char *)this + 24,
                &v28);
        std::_Tree<std::_Tmap_traits<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>::_Insert_nohint<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long> &,std::_Tree_node<std::pair<enum __MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>,void *> *>(
          (unsigned int)v36,
          (unsigned int)pcbData,
          v23,
          v22 + 28,
          v22);
        *(_QWORD *)pcbData = 0;
        Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, gc_wszRegUicc, 0, 0, 0, 2u, 0, (PHKEY)pcbData, 0);
        if ( Key )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x167,
            (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
            (const char *)Key,
            pdwTypea);
        KnownUicc::ToRegKey(v30, *(HKEY *)pcbData);
        if ( *(_QWORD *)pcbData )
          RegCloseKey(*(HKEY *)pcbData);
        *(_BYTE *)(v9 + 8 * v10 + 16) = 0;
        for ( i = 0; i < a4; ++i )
        {
          if ( CUiccHandler2::IsSystemStateValidForProvisioning((struct _MVProvisionData *)((char *)a3 + 104 * i))
            && v28 >= 0 )
          {
            CUiccHandler2::RemoveLogonTriggerFromCellularTask();
          }
        }
        KnownUicc::~KnownUicc((void **)v30);
        return 0;
      }
      if ( !ValueW )
        goto LABEL_14;
      if ( ValueW > 0 )
        ContextSubKeyPath = (unsigned __int16)ValueW | 0x80070000;
      if ( ContextSubKeyPath >= 0 )
        goto LABEL_14;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A1,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)(unsigned int)ContextSubKeyPath,
      pdwType);
    KnownUicc::~KnownUicc((void **)v30);
    result = (unsigned int)ContextSubKeyPath;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1B3,
                           (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x180031100  push    rbx
0x180031102  push    rsi
0x180031103  push    rdi
0x180031104  push    r12
0x180031106  push    r13
0x180031108  push    r14
0x18003110a  push    r15
0x18003110c  sub     rsp, 2D0h
0x180031113  mov     rax, cs:__security_cookie
0x18003111a  xor     rax, rsp
0x18003111d  mov     [rsp+308h+var_48], rax
0x180031125  mov     r12d, r9d
0x180031128  mov     r13, r8
0x18003112b  mov     rsi, rcx
0x18003112e  mov     [rsp+308h+var_2B8], edx
0x180031132  mov     rax, [rcx+30h]
0x180031136  mov     ecx, [rcx+1Ch]
0x180031139  mov     rdi, [rax]
0x18003113c  mov     rdx, [rax+8]
0x180031140  sub     rdx, rdi
0x180031143  sar     rdx, 4
0x180031147  mov     rax, 0AAAAAAAAAAAAAAABh
0x180031151  imul    rdx, rax
0x180031155  cmp     rdx, rcx
0x180031158  jbe     loc_1800313E2
0x18003115e  lea     r14, [rcx+rcx*2]
0x180031162  add     r14, r14
0x180031165  mov     rdx, [rdi+r14*8]
0x180031169  mov     [rsp+308h+var_280], 7
0x180031175  mov     [rsp+308h+var_288], 0
0x180031181  xor     eax, eax
0x180031183  mov     [rsp+308h+var_298], ax
0x180031188  or      r9, 0FFFFFFFFFFFFFFFFh
0x18003118c  xor     r8d, r8d
0x18003118f  lea     rcx, [rsp+308h+var_298]; void *
0x180031194  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180031199  nop
0x18003119a  mov     rax, [rdi+r14*8]
0x18003119e  mov     r15, [rax+38h]
0x1800311a2  mov     ecx, 20h ; ' '; Size
0x1800311a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800311ac  mov     rbx, rax
0x1800311af  mov     qword ptr [rsp+308h+var_2B0], rax
0x1800311b4  test    rax, rax
0x1800311b7  jz      short loc_1800311E6
0x1800311b9  mov     qword ptr [rax+18h], 7
0x1800311c1  mov     qword ptr [rax+10h], 0
0x1800311c9  xor     ecx, ecx
0x1800311cb  mov     [rax], cx
0x1800311ce  lea     rdx, [r15+20h]
0x1800311d2  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800311d6  xor     r8d, r8d
0x1800311d9  mov     rcx, rax; void *
0x1800311dc  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800311e1  xor     r15d, r15d
0x1800311e4  jmp     short loc_1800311EC
0x1800311e6  xor     r15d, r15d
0x1800311e9  mov     ebx, r15d
0x1800311ec  mov     [rsp+308h+var_278], rbx
0x1800311f4  mov     rax, [rdi+r14*8]
0x1800311f8  mov     ecx, [rax+64h]
0x1800311fb  mov     [rsp+308h+var_270], ecx
0x180031202  xor     eax, eax
0x180031204  mov     [rsp+308h+var_26C], eax
0x18003120b  mov     [rsp+308h+var_268], r15
0x180031213  mov     [rsp+308h+var_260], r15
0x18003121b  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>>::_Buyheadnode(void)
0x180031220  mov     [rsp+308h+var_268], rax
0x180031228  mov     [rsp+308h+var_2B0], 4
0x180031230  lea     rax, [rsp+308h+SubKey]
0x180031238  mov     [rsp+308h+pdwType], rax; unsigned __int16 *
0x18003123d  mov     rcx, rsi; struct IMVHandler *
0x180031240  call    ?MvGetContextSubKeyPath@@YAJPEAUIMVHandler@@PEBKPEBG2PEAGKPEAU_MVProvisionData@@@Z; MvGetContextSubKeyPath(IMVHandler *,ulong const *,ushort const *,ushort const *,ushort *,ulong,_MVProvisionData *)
0x180031245  mov     ebx, eax
0x180031247  test    eax, eax
0x180031249  js      short loc_1800312AD
0x18003124b  lea     rax, [rsp+308h+var_2B0]
0x180031250  mov     [rsp+308h+pcbData], rax; pcbData
0x180031255  lea     rax, [rsp+308h+var_26C]
0x18003125d  mov     [rsp+308h+pvData], rax; pvData
0x180031262  mov     [rsp+308h+pdwType], r15; int
0x180031267  mov     r9d, 10h; dwFlags
0x18003126d  lea     r8, ?gc_wszUIRequired@@3QBGB; "UIRequired"
0x180031274  lea     rdx, [rsp+308h+SubKey]; lpSubKey
0x18003127c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180031283  call    cs:__imp_RegGetValueW
0x180031289  mov     ebx, eax
0x18003128b  cmp     eax, 2
0x18003128e  jnz     short loc_18003129A
0x180031290  mov     [rsp+308h+var_26C], r15d
0x180031298  jmp     short loc_1800312DB
0x18003129a  test    eax, eax
0x18003129c  jz      short loc_1800312DB
0x18003129e  jle     short loc_1800312A9
0x1800312a0  movzx   ebx, ax
0x1800312a3  or      ebx, 80070000h
0x1800312a9  test    ebx, ebx
0x1800312ab  jns     short loc_1800312DB
0x1800312ad  mov     rcx, [rsp+308h]; this
0x1800312b5  mov     r9d, ebx; char *
0x1800312b8  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800312bf  mov     edx, 1A1h; void *
0x1800312c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800312c9  nop
0x1800312ca  lea     rcx, [rsp+308h+var_298]; this
0x1800312cf  call    ??1KnownUicc@@QEAA@XZ; KnownUicc::~KnownUicc(void)
0x1800312d4  mov     eax, ebx
0x1800312d6  jmp     loc_1800313BF
0x1800312db  lea     rdx, [rsi+18h]
0x1800312df  lea     r8, [rsp+308h+var_2B8]
0x1800312e4  lea     rcx, [rsp+308h+var_268]
0x1800312ec  call    ??$_Buynode@AEAW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@AEAJ@?$_Tree_buy@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@PEAX@1@AEAW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@AEAJ@Z; std::_Tree_buy<std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>::_Buynode<__MIDL___MIDL_itf_mvengine_0000_0000_0001 &,long &>(__MIDL___MIDL_itf_mvengine_0000_0000_0001 &,long &)
0x1800312f1  lea     r9, [rax+1Ch]
0x1800312f5  mov     [rsp+308h+pdwType], rax
0x1800312fa  lea     rdx, [rsp+308h+var_2B0]
0x1800312ff  lea     rcx, [rsp+308h+var_268]
0x180031307  call    ??$_Insert_nohint@AEAU?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@PEAU?$_Tree_node@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@W4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@JU?$less@W4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@@std@@V?$allocator@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@@3@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@1@PEAU?$_Tree_node@U?$pair@$$CBW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@J@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<__MIDL___MIDL_itf_mvengine_0000_0000_0001,long,std::less<__MIDL___MIDL_itf_mvengine_0000_0000_0001>,std::allocator<std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>>,0>>::_Insert_nohint<std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long> &,std::_Tree_node<std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>,void *> *>(bool,std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long> &,std::_Tree_node<std::pair<__MIDL___MIDL_itf_mvengine_0000_0000_0001 const,long>,void *> *)
0x18003130c  nop
0x18003130d  mov     qword ptr [rsp+308h+var_2B0], r15
0x180031312  mov     [rsp+308h+lpdwDisposition], r15; lpdwDisposition
0x180031317  lea     rax, [rsp+308h+var_2B0]
0x18003131c  mov     [rsp+308h+phkResult], rax; phkResult
0x180031321  mov     [rsp+308h+pcbData], r15; lpSecurityAttributes
0x180031326  mov     dword ptr [rsp+308h+pvData], 2; samDesired
0x18003132e  mov     dword ptr [rsp+308h+pdwType], r15d; unsigned int
0x180031333  xor     r9d, r9d; lpClass
0x180031336  xor     r8d, r8d; Reserved
0x180031339  mov     rdx, cs:?gc_wszRegUicc@@3PEBGEB; lpSubKey
0x180031340  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031347  call    cs:__imp_RegCreateKeyExW
0x18003134d  mov     rcx, [rsp+308h]; this
0x180031355  test    eax, eax
0x180031357  jnz     loc_1800313E8
0x18003135d  mov     rdx, qword ptr [rsp+308h+var_2B0]; hKey
0x180031362  lea     rcx, [rsp+308h+var_298]; lpSubKey
0x180031367  call    ?ToRegKey@KnownUicc@@QEBAXPEAUHKEY__@@@Z; KnownUicc::ToRegKey(HKEY__ *)
0x18003136c  nop
0x18003136d  mov     rcx, qword ptr [rsp+308h+var_2B0]; hKey
0x180031372  test    rcx, rcx
0x180031375  jz      short loc_18003137D
0x180031377  call    cs:__imp_RegCloseKey
0x18003137d  mov     [rdi+r14*8+10h], r15b
0x180031382  mov     ebx, r15d
0x180031385  cmp     ebx, r12d
0x180031388  jge     short loc_1800313AD
0x18003138a  movsxd  rax, ebx
0x18003138d  imul    rcx, rax, 68h ; 'h'
0x180031391  add     rcx, r13; struct _MVProvisionData *
0x180031394  call    ?IsSystemStateValidForProvisioning@CUiccHandler2@@KA_NAEAU_MVProvisionData@@@Z; CUiccHandler2::IsSystemStateValidForProvisioning(_MVProvisionData &)
0x180031399  test    al, al
0x18003139b  jz      short loc_1800313A9
0x18003139d  cmp     [rsp+308h+var_2B8], r15d
0x1800313a2  jl      short loc_1800313A9
0x1800313a4  call    ?RemoveLogonTriggerFromCellularTask@CUiccHandler2@@KAXXZ; CUiccHandler2::RemoveLogonTriggerFromCellularTask(void)
0x1800313a9  inc     ebx
0x1800313ab  jmp     short loc_180031385
0x1800313ad  lea     rcx, [rsp+308h+var_298]; this
0x1800313b2  call    ??1KnownUicc@@QEAA@XZ; KnownUicc::~KnownUicc(void)
0x1800313b7  xor     eax, eax
0x1800313b9  jmp     short loc_1800313BF
0x1800313bb  mov     eax, [rsp+308h+var_2B0]
0x1800313bf  mov     rcx, [rsp+308h+var_48]
0x1800313c7  xor     rcx, rsp; StackCookie
0x1800313ca  call    __security_check_cookie
0x1800313cf  add     rsp, 2D0h
0x1800313d6  pop     r15
0x1800313d8  pop     r14
0x1800313da  pop     r13
0x1800313dc  pop     r12
0x1800313de  pop     rdi
0x1800313df  pop     rsi
0x1800313e0  pop     rbx
0x1800313e1  retn
0x1800313e2  call    ?_Xran@?$vector@UUiccKeySet@@V?$allocator@UUiccKeySet@@@std@@@std@@IEBAXXZ; std::vector<UiccKeySet>::_Xran(void)
0x1800313e8  mov     r9d, eax; char *
0x1800313eb  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x1800313f2  mov     edx, 167h; void *
0x1800313f7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
