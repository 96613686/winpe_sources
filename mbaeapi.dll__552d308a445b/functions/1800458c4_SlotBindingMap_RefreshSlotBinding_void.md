# SlotBindingMap::_RefreshSlotBinding(void)

- ea: `0x1800458c4`
- end: `0x180045e42`
- name: `?_RefreshSlotBinding@SlotBindingMap@@AEAAJXZ`
- size: `1406`
- prototype: `int __fastcall(SlotBindingMap *this)`
- caller_count: `3`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180034f14`
- `0x180035ef4`
- `0x18003b004`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x1800028b0`
- `0x1800028ec`
- `0x1800040cd`
- `0x180009ffc`
- `0x18001105c`
- `0x1800156cc`
- `0x180016910`
- `0x180016a94`
- `0x180016b64`
- `0x1800172bc`
- `0x180017330`
- `0x18001d174`
- `0x18001d8f8`
- `0x18001dd10`
- `0x180033184`
- `0x180033630`
- `0x1800458c4`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180045d31`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180045e0c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180045d31`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x180045e0c`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180045c23`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180045ca4`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180045d23`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180045dfe`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180045c23`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180045ca4`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180045d23`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180045dfe`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180045a56`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x180045a56`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180045c7e`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanQueryInterface` at `0x180045c7e`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x180045a9b`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x180045a9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
int __fastcall SlotBindingMap::_RefreshSlotBinding(SlotBindingMap *this)
{
  const struct _tlgProvider_t *v2; // rax
  __int64 v3; // r8
  __int64 v4; // r9
  _QWORD *v5; // rbx
  _QWORD *v6; // rsi
  void *v7; // rcx
  _QWORD *v8; // rsi
  _QWORD *v9; // r14
  void *v10; // rbx
  _QWORD *v11; // rcx
  unsigned int v12; // eax
  unsigned int v14; // eax
  int v15; // ebx
  unsigned int *v16; // rsi
  unsigned int v17; // r14d
  unsigned int *v18; // r12
  bool v19; // bl
  _QWORD *lower; // rax
  __int128 v21; // xmm6
  __int64 v22; // rdx
  __int64 v23; // rbx
  char *v24; // rax
  __int64 v25; // rax
  _OWORD *v26; // rdx
  __int64 *v27; // rbx
  unsigned int Interface; // eax
  __int64 **v29; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  const struct _tlgProvider_t *v32; // rax
  __int64 v33; // r8
  __int64 v34; // r9
  unsigned int *v35; // [rsp+28h] [rbp-E0h]
  unsigned int *v36; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v37; // [rsp+50h] [rbp-B8h] BYREF
  int v38; // [rsp+58h] [rbp-B0h]
  unsigned __int16 *v39[2]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+78h] [rbp-90h]
  unsigned int v41[2]; // [rsp+88h] [rbp-80h] BYREF
  __int64 v42; // [rsp+90h] [rbp-78h]
  int v43; // [rsp+98h] [rbp-70h] BYREF
  __int128 Buf1; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v45; // [rsp+B0h] [rbp-58h]
  __int64 v46; // [rsp+C0h] [rbp-48h]
  __int64 *v47; // [rsp+C8h] [rbp-40h]
  char v48; // [rsp+D0h] [rbp-38h]
  unsigned int **v49; // [rsp+D8h] [rbp-30h]
  char v50; // [rsp+E0h] [rbp-28h]
  unsigned __int16 *v51[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v52; // [rsp+F8h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  *(_OWORD *)v39 = 0;
  v40 = 0;
  *(_OWORD *)v51 = 0;
  v52 = 0;
  std::vector<unsigned short>::resize(v39);
  std::vector<unsigned short>::resize(v51);
  StringCchPrintfW(v39[0], v39[1] - v39[0], L"Enter");
  LODWORD(v35) = 37;
  StringCchPrintfW(v51[0], v51[1] - v51[0], L"%S(%d):%s", "SlotBindingMap::_RefreshSlotBinding");
  v2 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v2 > 5u )
  {
    *(unsigned __int16 **)v41 = v51[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v2,
      (__int64)&dword_18007897C,
      v3,
      v4,
      (const unsigned __int16 **)v41);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v51);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v39);
  v5 = *(_QWORD **)this;
  v6 = *(_QWORD **)(*(_QWORD *)this + 8LL);
  while ( !*((_BYTE *)v6 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,SlotBindingMap::AdapterParameters>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,SlotBindingMap::AdapterParameters>,void *>>>(
      this,
      this,
      v6[2]);
    v7 = v6;
    v6 = (_QWORD *)*v6;
    operator delete(v7);
  }
  v5[1] = v5;
  *v5 = v5;
  v5[2] = v5;
  *((_QWORD *)this + 1) = 0;
  v8 = (_QWORD *)*((_QWORD *)this + 2);
  v9 = (_QWORD *)v8[1];
  while ( !*((_BYTE *)v9 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::vector<_GUID>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,std::vector<_GUID>>,void *>>>(
      (char *)this + 16,
      (char *)this + 16,
      v9[2]);
    v10 = v9;
    v11 = v9;
    v9 = (_QWORD *)*v9;
    std::vector<_GUID>::~vector<_GUID>(v11 + 6);
    operator delete(v10);
  }
  v8[1] = v8;
  *v8 = v8;
  v8[2] = v8;
  *((_QWORD *)this + 3) = 0;
  v37 = 0;
  v43 = 0;
  v12 = WwanOpenHandle(1, 0, &v43, &v37);
  if ( v12 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x2B,
             (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
             (const char *)v12,
             (unsigned int)v35);
  v47 = &v37;
  v48 = 1;
  v36 = 0;
  v14 = WwanEnumerateInterfaces(v37, 0, &v36);
  if ( v14 )
  {
    v15 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x2E,
            (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
            (const char *)v14,
            (unsigned int)v35);
LABEL_43:
    WwanCloseHandle(v37, 0);
    return v15;
  }
  else
  {
    v49 = &v36;
    v50 = 1;
    v16 = v36;
    v17 = 0;
    if ( *v36 )
    {
      do
      {
        v52 = 0;
        v18 = &v16[147 * v17];
        *(_OWORD *)v51 = *((_OWORD *)v18 + 35);
        v19 = v18[144] > 1;
        LOBYTE(v52) = v19;
        HIDWORD(v52) = -1;
        Buf1 = *(_OWORD *)(v18 + 1);
        v45 = *(_OWORD *)v51;
        v46 = v52;
        lower = std::_Tree<std::_Tmap_traits<_GUID,SlotBindingMap::AdapterParameters,GUID_COMP,std::allocator<std::pair<_GUID const,SlotBindingMap::AdapterParameters>>,0>>::_Find_lower_bound<_GUID>(
                  (__int64)this,
                  v39,
                  &Buf1);
        v21 = *(_OWORD *)lower;
        v22 = lower[2];
        if ( *(_BYTE *)(v22 + 25) || memcmp_0(&Buf1, (const void *)(v22 + 28), 0x10u) < 0 )
        {
          if ( *((_QWORD *)this + 1) == 0x38E38E38E38E38ELL )
            std::_Throw_tree_length_error();
          v23 = *(_QWORD *)this;
          *(_QWORD *)v41 = this;
          v42 = 0;
          v24 = (char *)operator new(0x48u);
          *(_OWORD *)(v24 + 28) = Buf1;
          *(_OWORD *)(v24 + 44) = v45;
          *(_QWORD *)(v24 + 60) = v46;
          *(_QWORD *)v24 = v23;
          *((_QWORD *)v24 + 1) = v23;
          *((_QWORD *)v24 + 2) = v23;
          *((_WORD *)v24 + 12) = 0;
          v42 = 0;
          *(_OWORD *)v39 = v21;
          std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,WTModemParameters>>>::_Insert_node(
            this,
            v39,
            v24);
          v19 = v52;
        }
        if ( v19 )
        {
          v25 = std::map<_GUID,std::vector<_GUID>,GUID_COMP,std::allocator<std::pair<_GUID const,std::vector<_GUID>>>>::operator[](
                  (__int64 *)this + 2,
                  v51);
          v26 = *(_OWORD **)(v25 + 8);
          if ( v26 == *(_OWORD **)(v25 + 16) )
          {
            std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(v25, v26, v18 + 1);
          }
          else
          {
            *v26 = *(_OWORD *)(v18 + 1);
            *(_QWORD *)(v25 + 8) += 16LL;
          }
        }
        ++v17;
      }
      while ( v17 < *v16 );
      v16 = v36;
    }
    WwanFreeMemory(v16);
    v36 = 0;
    v27 = **(__int64 ***)this;
    while ( v27 != *(__int64 **)this )
    {
      if ( *((_BYTE *)v27 + 60) )
      {
        v41[0] = 0;
        v38 = 0;
        v35 = v41;
        Interface = WwanQueryInterface(v37, (char *)v27 + 28, 23);
        if ( Interface )
        {
          v15 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x4C,
                  (unsigned int)"onecoreuap\\net\\mobilebroadbandexperience\\mbae\\mbaeapi\\lib\\cwwantranslator.cpp",
                  (const char *)Interface,
                  (unsigned int)v41);
          WwanFreeMemory(v36);
          goto LABEL_43;
        }
        if ( !v38 && v41[0] == 16 )
          *((_DWORD *)v27 + 16) = *v36;
        WwanFreeMemory(v36);
        v36 = 0;
      }
      else
      {
        *((_DWORD *)v27 + 16) = 0;
      }
      v29 = (__int64 **)v27[2];
      if ( *((_BYTE *)v29 + 25) )
      {
        for ( i = (__int64 *)v27[1]; !*((_BYTE *)i + 25) && v27 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v27 = i;
        v27 = i;
      }
      else
      {
        v27 = (__int64 *)v27[2];
        for ( j = *v29; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v27 = j;
      }
    }
    *(_OWORD *)v39 = 0;
    v40 = 0;
    *(_OWORD *)v51 = 0;
    v52 = 0;
    std::vector<unsigned short>::resize(v39);
    std::vector<unsigned short>::resize(v51);
    StringCchPrintfW(v39[0], v39[1] - v39[0], L"Exit");
    LODWORD(v35) = 92;
    StringCchPrintfW(v51[0], v51[1] - v51[0], L"%S(%d):%s", "SlotBindingMap::_RefreshSlotBinding", v35, v39[0]);
    v32 = MbaeApiLogging::Provider();
    if ( *(_DWORD *)v32 > 5u )
    {
      *(unsigned __int16 **)v41 = v51[0];
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (__int64)v32,
        (__int64)byte_180078959,
        v33,
        v34,
        (const unsigned __int16 **)v41);
    }
    std::vector<unsigned short>::~vector<unsigned short>((char **)v51);
    std::vector<unsigned short>::~vector<unsigned short>((char **)v39);
    WwanFreeMemory(v36);
    WwanCloseHandle(v37, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x1800458c4  mov     rax, rsp
0x1800458c7  push    rbp
0x1800458c8  push    rbx
0x1800458c9  push    rsi
0x1800458ca  push    rdi
0x1800458cb  push    r12
0x1800458cd  push    r13
0x1800458cf  push    r14
0x1800458d1  push    r15
0x1800458d3  lea     rbp, [rax-58h]
0x1800458d7  sub     rsp, 118h
0x1800458de  movaps  xmmword ptr [rax-58h], xmm6
0x1800458e2  mov     rax, cs:__security_cookie
0x1800458e9  xor     rax, rsp
0x1800458ec  mov     qword ptr [rbp+50h+var_58], rax
0x1800458f0  mov     rdi, rcx
0x1800458f3  xorps   xmm0, xmm0
0x1800458f6  movdqu  xmmword ptr [rsp+150h+var_F8+8], xmm0
0x1800458fc  xor     r13d, r13d
0x1800458ff  mov     [rsp+150h+var_E0], r13
0x180045904  movdqu  xmmword ptr [rbp+50h+var_70], xmm0
0x180045909  mov     [rbp+50h+var_60], r13
0x18004590d  lea     rcx, [rsp+150h+var_F8+8]
0x180045912  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180045917  lea     rcx, [rbp+50h+var_70]
0x18004591b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180045920  mov     rdx, [rsp+150h+var_E8]
0x180045925  mov     rcx, [rsp+150h+var_F8+8]; unsigned __int16 *
0x18004592a  sub     rdx, rcx
0x18004592d  sar     rdx, 1; unsigned __int64
0x180045930  lea     r8, aEnter; "Enter"
0x180045937  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004593c  mov     rdx, [rbp+50h+var_70+8]
0x180045940  mov     rcx, [rbp+50h+var_70]; unsigned __int16 *
0x180045944  sub     rdx, rcx
0x180045947  sar     rdx, 1; unsigned __int64
0x18004594a  mov     rax, [rsp+150h+var_F8+8]
0x18004594f  mov     [rsp+150h+var_128], rax
0x180045954  mov     [rsp+150h+var_130], 25h ; '%'
0x18004595c  lea     r9, aSlotbindingmap; "SlotBindingMap::_RefreshSlotBinding"
0x180045963  lea     r8, aSDS; "%S(%d):%s"
0x18004596a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004596f  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x180045974  mov     ecx, [rax]
0x180045976  cmp     ecx, 5
0x180045979  jbe     short loc_18004599C
0x18004597b  mov     rcx, [rbp+50h+var_70]
0x18004597f  mov     qword ptr [rbp+50h+var_D0], rcx
0x180045983  lea     rcx, [rbp+50h+var_D0]
0x180045987  mov     qword ptr [rsp+150h+var_130], rcx
0x18004598c  lea     rdx, dword_18007897C
0x180045993  mov     rcx, rax
0x180045996  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18004599b  nop
0x18004599c  lea     rcx, [rbp+50h+var_70]
0x1800459a0  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800459a5  nop
0x1800459a6  lea     rcx, [rsp+150h+var_F8+8]
0x1800459ab  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x1800459b0  mov     rbx, [rdi]
0x1800459b3  mov     rsi, [rbx+8]
0x1800459b7  mov     r12d, 48h ; 'H'
0x1800459bd  jmp     short loc_1800459DC
0x1800459bf  mov     r8, [rsi+10h]
0x1800459c3  mov     rdx, rdi
0x1800459c6  mov     rcx, rdi
0x1800459c9  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,SlotBindingMap::AdapterParameters>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,SlotBindingMap::AdapterParameters>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,SlotBindingMap::AdapterParameters>,void *>> &,std::_Tree_node<std::pair<_GUID const,SlotBindingMap::AdapterParameters>,void *> *)
0x1800459ce  mov     rcx, rsi; Block
0x1800459d1  mov     rsi, [rsi]
0x1800459d4  mov     rdx, r12
0x1800459d7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800459dc  cmp     [rsi+19h], r13b
0x1800459e0  jz      short loc_1800459BF
0x1800459e2  mov     [rbx+8], rbx
0x1800459e6  mov     [rbx], rbx
0x1800459e9  mov     [rbx+10h], rbx
0x1800459ed  mov     [rdi+8], r13
0x1800459f1  lea     r15, [rdi+10h]
0x1800459f5  mov     rsi, [r15]
0x1800459f8  mov     r14, [rsi+8]
0x1800459fc  jmp     short loc_180045A2A
0x1800459fe  mov     r8, [r14+10h]
0x180045a02  mov     rdx, r15
0x180045a05  mov     rcx, r15
0x180045a08  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@V?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::vector<_GUID>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,std::vector<_GUID>>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,std::vector<_GUID>>,void *>> &,std::_Tree_node<std::pair<_GUID const,std::vector<_GUID>>,void *> *)
0x180045a0d  mov     rbx, r14
0x180045a10  mov     rcx, r14
0x180045a13  mov     r14, [r14]
0x180045a16  add     rcx, 30h ; '0'
0x180045a1a  call    ??1?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::~vector<_GUID>(void)
0x180045a1f  mov     rdx, r12
0x180045a22  mov     rcx, rbx; Block
0x180045a25  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180045a2a  cmp     [r14+19h], r13b
0x180045a2e  jz      short loc_1800459FE
0x180045a30  mov     [rsi+8], rsi
0x180045a34  mov     [rsi], rsi
0x180045a37  mov     [rsi+10h], rsi
0x180045a3b  mov     [r15+8], r13
0x180045a3f  mov     [rsp+150h+var_108], r13
0x180045a44  mov     [rbp+50h+var_C0], r13d
0x180045a48  lea     r9, [rsp+150h+var_108]
0x180045a4d  lea     r8, [rbp+50h+var_C0]
0x180045a51  xor     edx, edx
0x180045a53  lea     ecx, [rdx+1]
0x180045a56  call    cs:__imp_WwanOpenHandle
0x180045a5c  test    eax, eax
0x180045a5e  jz      short loc_180045A7D
0x180045a60  mov     rcx, [rbp+58h]; this
0x180045a64  mov     r9d, eax; char *
0x180045a67  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180045a6e  mov     edx, 2Bh ; '+'; void *
0x180045a73  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180045a78  jmp     loc_180045E14
0x180045a7d  lea     rax, [rsp+150h+var_108]
0x180045a82  mov     [rbp+50h+var_90], rax
0x180045a86  mov     [rbp+50h+var_88], 1
0x180045a8a  mov     [rsp+150h+var_110], r13
0x180045a8f  lea     r8, [rsp+150h+var_110]
0x180045a94  xor     edx, edx
0x180045a96  mov     rcx, [rsp+150h+var_108]
0x180045a9b  call    cs:__imp_WwanEnumerateInterfaces
0x180045aa1  test    eax, eax
0x180045aa3  jz      short loc_180045AC4
0x180045aa5  mov     rcx, [rbp+58h]; this
0x180045aa9  mov     r9d, eax; char *
0x180045aac  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180045ab3  mov     edx, 2Eh ; '.'; void *
0x180045ab8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180045abd  mov     ebx, eax
0x180045abf  jmp     loc_180045D2A
0x180045ac4  lea     rax, [rsp+150h+var_110]
0x180045ac9  mov     [rbp+50h+var_80], rax
0x180045acd  mov     [rbp+50h+var_78], 1
0x180045ad1  mov     rsi, [rsp+150h+var_110]
0x180045ad6  mov     r14d, r13d
0x180045ad9  cmp     [rsi], r13d
0x180045adc  jbe     loc_180045C20
0x180045ae2  xor     eax, eax
0x180045ae4  mov     [rbp+50h+var_60], rax
0x180045ae8  mov     eax, r14d
0x180045aeb  imul    r12, rax, 24Ch
0x180045af2  add     r12, rsi
0x180045af5  movups  xmm1, xmmword ptr [r12+230h]
0x180045afe  movups  xmmword ptr [rbp+50h+var_70], xmm1
0x180045b02  cmp     dword ptr [r12+240h], 1
0x180045b0b  setnbe  bl
0x180045b0e  mov     byte ptr [rbp+50h+var_60], bl
0x180045b11  mov     dword ptr [rbp+50h+var_60+4], 0FFFFFFFFh
0x180045b18  movups  xmm0, xmmword ptr [r12+4]
0x180045b1e  movdqu  [rbp+50h+Buf1], xmm0
0x180045b23  movups  [rbp+50h+var_A8], xmm1
0x180045b27  movsd   xmm0, [rbp+50h+var_60]
0x180045b2c  movsd   [rbp+50h+var_98], xmm0
0x180045b31  lea     r8, [rbp+50h+Buf1]
0x180045b35  lea     rdx, [rsp+150h+var_F8+8]
0x180045b3a  mov     rcx, rdi
0x180045b3d  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UAdapterParameters@SlotBindingMap@@UGUID_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UAdapterParameters@SlotBindingMap@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,SlotBindingMap::AdapterParameters,GUID_COMP,std::allocator<std::pair<_GUID const,SlotBindingMap::AdapterParameters>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x180045b42  movups  xmm6, xmmword ptr [rax]
0x180045b45  mov     rdx, [rax+10h]
0x180045b49  cmp     [rdx+19h], r13b
0x180045b4d  jnz     short loc_180045B66
0x180045b4f  add     rdx, 1Ch; Buf2
0x180045b53  mov     r8d, 10h; Size
0x180045b59  lea     rcx, [rbp+50h+Buf1]; Buf1
0x180045b5d  call    memcmp_0
0x180045b62  test    eax, eax
0x180045b64  jns     short loc_180045BD7
0x180045b66  mov     rax, 38E38E38E38E38Eh
0x180045b70  cmp     [rdi+8], rax
0x180045b74  jz      loc_180045E3C
0x180045b7a  mov     rbx, [rdi]
0x180045b7d  mov     qword ptr [rbp+50h+var_D0], rdi
0x180045b81  mov     [rbp+50h+var_C8], r13
0x180045b85  mov     ecx, 48h ; 'H'; Size
0x180045b8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180045b8f  nop
0x180045b90  movups  xmm0, [rbp+50h+Buf1]
0x180045b94  movups  xmmword ptr [rax+1Ch], xmm0
0x180045b98  movups  xmm1, [rbp+50h+var_A8]
0x180045b9c  movups  xmmword ptr [rax+2Ch], xmm1
0x180045ba0  movsd   xmm0, [rbp+50h+var_98]
0x180045ba5  movsd   qword ptr [rax+3Ch], xmm0
0x180045baa  mov     [rax], rbx
0x180045bad  mov     [rax+8], rbx
0x180045bb1  mov     [rax+10h], rbx
0x180045bb5  mov     [rax+18h], r13w
0x180045bba  mov     [rbp+50h+var_C8], r13
0x180045bbe  movdqu  xmmword ptr [rsp+150h+var_F8+8], xmm6
0x180045bc4  mov     r8, rax
0x180045bc7  lea     rdx, [rsp+150h+var_F8+8]
0x180045bcc  mov     rcx, rdi
0x180045bcf  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UWTModemParameters@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UWTModemParameters@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UWTModemParameters@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,WTModemParameters>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<_GUID const,WTModemParameters>,void *> *>,std::_Tree_node<std::pair<_GUID const,WTModemParameters>,void *> * const)
0x180045bd4  mov     bl, byte ptr [rbp+50h+var_60]
0x180045bd7  test    bl, bl
0x180045bd9  jz      short loc_180045C0F
0x180045bdb  lea     rdx, [rbp+50h+var_70]
0x180045bdf  mov     rcx, r15
0x180045be2  call    ??A?$map@U_GUID@@V?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@UGUID_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@V?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@@std@@@3@@std@@QEAAAEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@1@AEBU_GUID@@@Z; std::map<_GUID,std::vector<_GUID>,GUID_COMP,std::allocator<std::pair<_GUID const,std::vector<_GUID>>>>::operator[](_GUID const &)
0x180045be7  mov     rdx, [rax+8]
0x180045beb  cmp     rdx, [rax+10h]
0x180045bef  jz      short loc_180045C02
0x180045bf1  movups  xmm0, xmmword ptr [r12+4]
0x180045bf7  movdqu  xmmword ptr [rdx], xmm0
0x180045bfb  add     qword ptr [rax+8], 10h
0x180045c00  jmp     short loc_180045C0F
0x180045c02  lea     r8, [r12+4]
0x180045c07  mov     rcx, rax
0x180045c0a  call    ??$_Emplace_reallocate@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEBU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(_GUID * const,_GUID const &)
0x180045c0f  inc     r14d
0x180045c12  cmp     r14d, [rsi]
0x180045c15  jb      loc_180045AE2
0x180045c1b  mov     rsi, [rsp+150h+var_110]
0x180045c20  mov     rcx, rsi
0x180045c23  call    cs:__imp_WwanFreeMemory
0x180045c29  mov     [rsp+150h+var_110], r13
0x180045c2e  mov     rbx, [rdi]
0x180045c31  mov     rbx, [rbx]
0x180045c34  cmp     rbx, [rdi]
0x180045c37  jz      loc_180045D3E
0x180045c3d  cmp     [rbx+3Ch], r13b
0x180045c41  jz      short loc_180045CB1
0x180045c43  mov     [rbp+50h+var_D0], r13d
0x180045c47  mov     [rsp+150h+var_100], r13d
0x180045c4c  lea     rdx, [rbx+1Ch]
0x180045c50  lea     rax, [rsp+150h+var_100]
0x180045c55  mov     [rsp+150h+var_118], rax
0x180045c5a  mov     [rsp+150h+var_120], r13
0x180045c5f  lea     rax, [rsp+150h+var_110]
0x180045c64  mov     [rsp+150h+var_128], rax
0x180045c69  lea     rax, [rbp+50h+var_D0]
0x180045c6d  mov     qword ptr [rsp+150h+var_130], rax; unsigned int
0x180045c72  xor     r9d, r9d
0x180045c75  lea     r8d, [r9+17h]
0x180045c79  mov     rcx, [rsp+150h+var_108]
0x180045c7e  call    cs:__imp_WwanQueryInterface
0x180045c84  test    eax, eax
0x180045c86  jnz     short loc_180045D04
0x180045c88  cmp     [rsp+150h+var_100], r13d
0x180045c8d  jnz     short loc_180045C9F
0x180045c8f  cmp     [rbp+50h+var_D0], 10h
0x180045c93  jnz     short loc_180045C9F
0x180045c95  mov     rax, [rsp+150h+var_110]
0x180045c9a  mov     ecx, [rax]
0x180045c9c  mov     [rbx+40h], ecx
0x180045c9f  mov     rcx, [rsp+150h+var_110]
0x180045ca4  call    cs:__imp_WwanFreeMemory
0x180045caa  mov     [rsp+150h+var_110], r13
0x180045caf  jmp     short loc_180045CB5
0x180045cb1  mov     [rbx+40h], r13d
0x180045cb5  mov     rcx, [rbx+10h]
0x180045cb9  cmp     [rcx+19h], r13b
0x180045cbd  jz      short loc_180045CE0
0x180045cbf  mov     rax, [rbx+8]
0x180045cc3  jmp     short loc_180045CD2
0x180045cc5  cmp     rbx, [rax+10h]
0x180045cc9  jnz     short loc_180045CD8
0x180045ccb  mov     rbx, rax
0x180045cce  mov     rax, [rax+8]
0x180045cd2  cmp     [rax+19h], r13b
0x180045cd6  jz      short loc_180045CC5
0x180045cd8  mov     rbx, rax
0x180045cdb  jmp     loc_180045C34
0x180045ce0  mov     rbx, rcx
0x180045ce3  mov     rcx, [rcx]
0x180045ce6  cmp     [rcx+19h], r13b
0x180045cea  jnz     loc_180045C34
0x180045cf0  mov     rbx, rcx
0x180045cf3  mov     rax, [rcx]
0x180045cf6  mov     rcx, rax
0x180045cf9  cmp     [rax+19h], r13b
0x180045cfd  jz      short loc_180045CF0
0x180045cff  jmp     loc_180045C34
0x180045d04  mov     rcx, [rbp+58h]; this
0x180045d08  mov     r9d, eax; char *
0x180045d0b  lea     r8, aOnecoreuapNetM_8; "onecoreuap\\net\\mobilebroadbandexperie"...
0x180045d12  mov     edx, 4Ch ; 'L'; void *
0x180045d17  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180045d1c  mov     ebx, eax
0x180045d1e  mov     rcx, [rsp+150h+var_110]
0x180045d23  call    cs:__imp_WwanFreeMemory
0x180045d29  nop
0x180045d2a  xor     edx, edx
0x180045d2c  mov     rcx, [rsp+150h+var_108]
0x180045d31  call    cs:__imp_WwanCloseHandle
0x180045d37  mov     eax, ebx
0x180045d39  jmp     loc_180045E14
0x180045d3e  xorps   xmm0, xmm0
0x180045d41  movdqu  xmmword ptr [rsp+150h+var_F8+8], xmm0
0x180045d47  mov     [rsp+150h+var_E0], r13
0x180045d4c  movdqu  xmmword ptr [rbp+50h+var_70], xmm0
0x180045d51  mov     [rbp+50h+var_60], r13
0x180045d55  lea     rcx, [rsp+150h+var_F8+8]
0x180045d5a  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180045d5f  lea     rcx, [rbp+50h+var_70]
0x180045d63  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180045d68  mov     rdx, [rsp+150h+var_E8]
0x180045d6d  mov     rcx, [rsp+150h+var_F8+8]; unsigned __int16 *
0x180045d72  sub     rdx, rcx
0x180045d75  sar     rdx, 1; unsigned __int64
  ... truncated ...
```
