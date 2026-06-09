# NetworkListManager::GetNetworkInterfaces(_GUID const *,ulong *,wchar_t * * *)

- ea: `0x1800a6ed0`
- end: `0x1800a7165`
- name: `?GetNetworkInterfaces@NetworkListManager@@UEAAJPEBU_GUID@@PEAKPEAPEAPEA_W@Z`
- size: `661`
- prototype: `__int64 __fastcall(NetworkListManager *this, const struct _GUID *, unsigned int *, wchar_t ***)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800babb0`
- `0x1800babc0`

## callees

- `0x18000e56c`
- `0x18000fab0`
- `0x180010340`
- `0x1800120a0`
- `0x1800131c4`
- `0x180015608`
- `0x180015710`
- `0x18002061c`
- `0x180026a10`
- `0x18002e6e8`
- `0x180040844`
- `0x1800459ac`
- `0x1800a6ed0`
- `0x1800a716c`
- `0x1800a88a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a7079`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800a7079`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a7033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a7057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a7033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a7057`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a7097`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a7097`

## string_xrefs

- `0x1800a6f80`: `onecore\net\netprofiles\service\src\host\lib\profmani.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NetworkListManager::GetNetworkInterfaces(
        NetworkListManager *this,
        const struct _GUID *a2,
        unsigned int *a3,
        wchar_t ***a4)
{
  int ClientInformation; // eax
  __int128 v8; // xmm0
  __int64 v9; // r8
  __int64 i; // rbx
  __int64 v11; // rdi
  __int64 v12; // rdx
  unsigned int v13; // ebx
  wchar_t **v14; // rax
  __int64 v15; // rdi
  const GUID *v16; // rbx
  GUID *v17; // r15
  OLECHAR *v18; // rdx
  int v20; // [rsp+20h] [rbp-78h]
  unsigned int v21[2]; // [rsp+30h] [rbp-68h] BYREF
  GUID *rguid[2]; // [rsp+38h] [rbp-60h] BYREF
  __int64 v23; // [rsp+48h] [rbp-50h]
  __int128 v24; // [rsp+50h] [rbp-48h] BYREF
  __int64 v25; // [rsp+60h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids);
  StandbyMonitor::ProcessClientActivity(7);
  if ( a2 && a3 && a4 )
  {
    *a3 = 0;
    *a4 = 0;
    v21[0] = 0;
    ClientInformation = HrGetClientInformation(0, v21, 0);
    if ( ClientInformation < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC4E,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\profmani.cpp",
        (const char *)(unsigned int)ClientInformation,
        v20);
    v8 = 0;
    *(_OWORD *)rguid = 0;
    v23 = 0;
    *(double *)&v8 = std::vector<std::pair<_GUID,StructDifference::StructDifference>>::vector<std::pair<_GUID,StructDifference::StructDifference>>(rguid);
    v24 = v8;
    v25 = 0;
    NetworkPropertyMaps::FindConnectedNetworksByNetworkId(&v24, a2, v9, v21[0]);
    v11 = *((_QWORD *)&v24 + 1);
    for ( i = v24; i != v11; i += 696 )
    {
      v12 = **(_QWORD **)(i + 112);
      *(_QWORD *)v21 = v12;
      while ( !*(_BYTE *)(v12 + 25) )
      {
        std::vector<_GUID>::emplace_back<_GUID const &>(rguid, v12 + 32);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,NlmDomain::DnsSuffixInfo>>>,std::_Iterator_base0>::operator++(v21);
        v12 = *(_QWORD *)v21;
      }
    }
    if ( rguid[0] == rguid[1] )
    {
      v13 = 0;
    }
    else
    {
      v14 = (wchar_t **)CoTaskMemAlloc(8 * (rguid[1] - rguid[0]));
      *a4 = v14;
      if ( v14 )
      {
        v15 = 0;
        v16 = rguid[0];
        v17 = rguid[1];
        while ( 1 )
        {
          if ( v16 == v17 )
          {
            v13 = LongLongToULong(rguid[1] - rguid[0], a3);
            goto LABEL_28;
          }
          (*a4)[v15] = (wchar_t *)CoTaskMemAlloc(0x4Eu);
          v18 = (*a4)[v15];
          if ( !v18 )
            break;
          StringFromGUID2(v16, v18, 39);
          v15 = (unsigned int)(v15 + 1);
          ++v16;
        }
        v13 = -2147024882;
        while ( (_DWORD)v15 )
        {
          LODWORD(v15) = v15 - 1;
          CoTaskMemFree((*a4)[(unsigned int)v15]);
        }
      }
      else
      {
        v13 = -2147024882;
      }
    }
LABEL_28:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 160, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids, *a3, v13);
    std::vector<ACTIVE_NETWORK>::_Tidy(&v24);
    std::vector<_GUID>::~vector<_GUID>(rguid);
    return v13;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, &WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids, 2147500035LL);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800a6ed0  mov     [rsp+arg_0], rbx
0x1800a6ed5  push    rsi
0x1800a6ed6  push    rdi
0x1800a6ed7  push    r13
0x1800a6ed9  push    r14
0x1800a6edb  push    r15
0x1800a6edd  sub     rsp, 70h
0x1800a6ee1  mov     rax, cs:__security_cookie
0x1800a6ee8  xor     rax, rsp
0x1800a6eeb  mov     [rsp+98h+var_30], rax
0x1800a6ef0  mov     rsi, r9
0x1800a6ef3  mov     r14, r8
0x1800a6ef6  mov     rbx, rdx
0x1800a6ef9  lea     r13, WPP_GLOBAL_Control
0x1800a6f00  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a6f07  cmp     rcx, r13
0x1800a6f0a  jz      short loc_1800A6F27
0x1800a6f0c  test    byte ptr [rcx+1Ch], 8
0x1800a6f10  jz      short loc_1800A6F27
0x1800a6f12  mov     edx, 9Eh
0x1800a6f17  lea     r8, WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids
0x1800a6f1e  mov     rcx, [rcx+10h]
0x1800a6f22  call    WPP_SF_
0x1800a6f27  mov     ecx, 7
0x1800a6f2c  call    ?ProcessClientActivity@StandbyMonitor@@YAXW4ClientActivity@1@@Z; StandbyMonitor::ProcessClientActivity(StandbyMonitor::ClientActivity)
0x1800a6f31  test    rbx, rbx
0x1800a6f34  jz      loc_1800A710A
0x1800a6f3a  test    r14, r14
0x1800a6f3d  jz      loc_1800A710A
0x1800a6f43  test    rsi, rsi
0x1800a6f46  jz      loc_1800A710A
0x1800a6f4c  mov     dword ptr [r14], 0
0x1800a6f53  mov     qword ptr [rsi], 0
0x1800a6f5a  mov     [rsp+98h+var_68], 0
0x1800a6f62  xor     r8d, r8d; int *
0x1800a6f65  lea     rdx, [rsp+98h+var_68]; unsigned int *
0x1800a6f6a  xor     ecx, ecx; unsigned int *
0x1800a6f6c  call    ?HrGetClientInformation@@YAJPEAKPEAIPEAH@Z; HrGetClientInformation(ulong *,uint *,int *)
0x1800a6f71  mov     rcx, [rsp+98h]; this
0x1800a6f79  test    eax, eax
0x1800a6f7b  jns     short loc_1800A6F91
0x1800a6f7d  mov     r9d, eax; char *
0x1800a6f80  lea     r8, aOnecoreNetNetp_53; "onecore\\net\\netprofiles\\service\\src"...
0x1800a6f87  mov     edx, 0C4Eh; void *
0x1800a6f8c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a6f91  xorps   xmm0, xmm0
0x1800a6f94  xor     eax, eax
0x1800a6f96  movups  xmmword ptr [rsp+98h+rguid], xmm0
0x1800a6f9b  mov     [rsp+98h+var_50], rax
0x1800a6fa0  lea     rcx, [rsp+98h+rguid]
0x1800a6fa5  call    ??0?$vector@U?$pair@U_GUID@@UStructDifference@2@@std@@V?$allocator@U?$pair@U_GUID@@UStructDifference@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<_GUID,StructDifference::StructDifference>>::vector<std::pair<_GUID,StructDifference::StructDifference>>(void)
0x1800a6faa  nop
0x1800a6fab  xor     eax, eax
0x1800a6fad  movups  [rsp+98h+var_48], xmm0
0x1800a6fb2  mov     [rsp+98h+var_38], rax
0x1800a6fb7  mov     r9d, [rsp+98h+var_68]
0x1800a6fbc  mov     rdx, rbx
0x1800a6fbf  lea     rcx, [rsp+98h+var_48]
0x1800a6fc4  call    ?FindConnectedNetworksByNetworkId@NetworkPropertyMaps@@SA?AV?$vector@UACTIVE_NETWORK@@V?$allocator@UACTIVE_NETWORK@@@std@@@std@@PEBU_GUID@@_NI@Z; NetworkPropertyMaps::FindConnectedNetworksByNetworkId(_GUID const *,bool,uint)
0x1800a6fc9  nop
0x1800a6fca  mov     rbx, qword ptr [rsp+98h+var_48]
0x1800a6fcf  mov     rdi, qword ptr [rsp+98h+var_48+8]
0x1800a6fd4  cmp     rbx, rdi
0x1800a6fd7  jz      short loc_1800A7013
0x1800a6fd9  mov     rdx, [rbx+70h]
0x1800a6fdd  mov     rdx, [rdx]
0x1800a6fe0  mov     qword ptr [rsp+98h+var_68], rdx
0x1800a6fe5  cmp     byte ptr [rdx+19h], 0
0x1800a6fe9  jz      short loc_1800A6FF4
0x1800a6feb  add     rbx, 2B8h
0x1800a6ff2  jmp     short loc_1800A6FD4
0x1800a6ff4  add     rdx, 20h ; ' '
0x1800a6ff8  lea     rcx, [rsp+98h+rguid]
0x1800a6ffd  call    ??$emplace_back@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAAAEAU_GUID@@AEBU2@@Z; std::vector<_GUID>::emplace_back<_GUID const &>(_GUID const &)
0x1800a7002  lea     rcx, [rsp+98h+var_68]
0x1800a7007  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UDnsSuffixInfo@NlmDomain@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,NlmDomain::DnsSuffixInfo>>>,std::_Iterator_base0>::operator++(void)
0x1800a700c  mov     rdx, qword ptr [rsp+98h+var_68]
0x1800a7011  jmp     short loc_1800A6FE5
0x1800a7013  mov     rcx, [rsp+98h+rguid+8]
0x1800a7018  cmp     [rsp+98h+rguid], rcx
0x1800a701d  jnz     short loc_1800A7026
0x1800a701f  xor     ebx, ebx
0x1800a7021  jmp     loc_1800A70C2
0x1800a7026  sub     rcx, [rsp+98h+rguid]
0x1800a702b  sar     rcx, 4
0x1800a702f  shl     rcx, 3; cb
0x1800a7033  call    cs:__imp_CoTaskMemAlloc
0x1800a7039  mov     [rsi], rax
0x1800a703c  test    rax, rax
0x1800a703f  jz      short loc_1800A70BD
0x1800a7041  xor     edi, edi
0x1800a7043  mov     rbx, [rsp+98h+rguid]
0x1800a7048  mov     r15, [rsp+98h+rguid+8]
0x1800a704d  cmp     rbx, r15
0x1800a7050  jz      short loc_1800A70A3
0x1800a7052  mov     ecx, 4Eh ; 'N'; cb
0x1800a7057  call    cs:__imp_CoTaskMemAlloc
0x1800a705d  mov     rcx, [rsi]
0x1800a7060  mov     [rcx+rdi*8], rax
0x1800a7064  mov     rax, [rsi]
0x1800a7067  mov     rdx, [rax+rdi*8]; lpsz
0x1800a706b  test    rdx, rdx
0x1800a706e  jz      short loc_1800A7087
0x1800a7070  mov     r8d, 27h ; '''; cchMax
0x1800a7076  mov     rcx, rbx; rguid
0x1800a7079  call    cs:__imp_StringFromGUID2
0x1800a707f  inc     edi
0x1800a7081  add     rbx, 10h
0x1800a7085  jmp     short loc_1800A704D
0x1800a7087  mov     ebx, 8007000Eh
0x1800a708c  jmp     short loc_1800A709D
0x1800a708e  dec     edi
0x1800a7090  mov     rcx, [rsi]
0x1800a7093  mov     rcx, [rcx+rdi*8]; pv
0x1800a7097  call    cs:__imp_CoTaskMemFree
0x1800a709d  test    edi, edi
0x1800a709f  jnz     short loc_1800A708E
0x1800a70a1  jmp     short loc_1800A70C2
0x1800a70a3  mov     rcx, [rsp+98h+rguid+8]
0x1800a70a8  sub     rcx, [rsp+98h+rguid]
0x1800a70ad  sar     rcx, 4; __int64
0x1800a70b1  mov     rdx, r14; unsigned int *
0x1800a70b4  call    ?LongLongToULong@@YAJ_JPEAK@Z; LongLongToULong(__int64,ulong *)
0x1800a70b9  mov     ebx, eax
0x1800a70bb  jmp     short loc_1800A70C2
0x1800a70bd  mov     ebx, 8007000Eh
0x1800a70c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a70c9  cmp     rcx, r13
0x1800a70cc  jz      short loc_1800A70F1
0x1800a70ce  test    byte ptr [rcx+1Ch], 8
0x1800a70d2  jz      short loc_1800A70F1
0x1800a70d4  mov     edx, 0A0h
0x1800a70d9  mov     [rsp+98h+var_78], ebx
0x1800a70dd  mov     r9d, [r14]
0x1800a70e0  lea     r8, WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids
0x1800a70e7  mov     rcx, [rcx+10h]
0x1800a70eb  call    WPP_SF_dd
0x1800a70f0  nop
0x1800a70f1  lea     rcx, [rsp+98h+var_48]
0x1800a70f6  call    ?_Tidy@?$vector@UACTIVE_NETWORK@@V?$allocator@UACTIVE_NETWORK@@@std@@@std@@AEAAXXZ; std::vector<ACTIVE_NETWORK>::_Tidy(void)
0x1800a70fb  nop
0x1800a70fc  lea     rcx, [rsp+98h+rguid]
0x1800a7101  call    ??1?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::~vector<_GUID>(void)
0x1800a7106  mov     eax, ebx
0x1800a7108  jmp     short loc_1800A7142
0x1800a710a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a7111  cmp     rcx, r13
0x1800a7114  jz      short loc_1800A7137
0x1800a7116  test    byte ptr [rcx+1Ch], 8
0x1800a711a  jz      short loc_1800A7137
0x1800a711c  mov     edx, 9Fh
0x1800a7121  mov     r9d, 80004003h
0x1800a7127  lea     r8, WPP_fb2d8f400dcf3745e23572aff3eff1fd_Traceguids
0x1800a712e  mov     rcx, [rcx+10h]
0x1800a7132  call    WPP_SF_d
0x1800a7137  mov     eax, 80004003h
0x1800a713c  jmp     short loc_1800A7142
0x1800a713e  mov     eax, [rsp+98h+var_68]
0x1800a7142  mov     rcx, [rsp+98h+var_30]
0x1800a7147  xor     rcx, rsp; StackCookie
0x1800a714a  call    __security_check_cookie
0x1800a714f  mov     rbx, [rsp+98h+arg_0]
0x1800a7157  add     rsp, 70h
0x1800a715b  pop     r15
0x1800a715d  pop     r14
0x1800a715f  pop     r13
0x1800a7161  pop     rdi
0x1800a7162  pop     rsi
0x1800a7163  retn
```
