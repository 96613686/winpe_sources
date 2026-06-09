# DomainNode::Commit(void)

- ea: `0x180011e80`
- end: `0x1800122c1`
- name: `?Commit@DomainNode@@UEAAJXZ`
- size: `1089`
- prototype: `__int64 __fastcall(DomainNode *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001a70`
- `0x180001b14`
- `0x180006974`
- `0x18000848c`
- `0x180009020`
- `0x1800090e0`
- `0x18000918c`
- `0x180009eb0`
- `0x180009fac`
- `0x18000f054`
- `0x180011e80`
- `0x1800123ac`
- `0x1800124ac`
- `0x1800125f4`
- `0x18002b100`
- `0x18002b5c4`
- `0x1800358a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001213b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001216d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012249`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012266`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001213b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001216d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012249`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012266`
- `wkscli!NetJoinDomain` at `0x18001220e`
- `wkscli!NetJoinDomain` at `0x18001220e`
- `ext-ms-win-provisioning-platform-l1-1-0!SetDeviceName` at `0x180011f50`
- `ext-ms-win-provisioning-platform-l1-1-0!SetDeviceName` at `0x180011f50`

## string_xrefs

- `0x18001229a`: `onecoreuap\admin\prov\provcsp\computernamenode.cpp`
- `0x1800122ae`: `onecoreuap\admin\prov\provcsp\computernamenode.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DomainNode::Commit(DomainNode *this)
{
  DWORD fJoinOptions; // r14d
  _QWORD *v3; // rdx
  _QWORD *v4; // rdi
  _QWORD *v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rdx
  int RandomComputerName; // eax
  const char *v9; // r9
  int SerialNumberComputerName; // eax
  int v11; // eax
  unsigned int v12; // edi
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rdi
  __int64 v17; // rsi
  __int64 v18; // rdx
  void **v19; // rcx
  __int64 v20; // rax
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  _QWORD *v24; // rax
  const WCHAR *v25; // rcx
  const WCHAR *v26; // r9
  __int64 v27; // r8
  const WCHAR *v28; // r8
  const WCHAR *v29; // rdx
  DWORD v30; // eax
  const char *v31; // r9
  unsigned int v32; // ebx
  int lpPassword; // [rsp+20h] [rbp-C8h]
  unsigned int lpPassworda; // [rsp+20h] [rbp-C8h]
  _BYTE v35[8]; // [rsp+30h] [rbp-B8h] BYREF
  _QWORD *v36; // [rsp+38h] [rbp-B0h] BYREF
  void *v37[2]; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-98h]
  unsigned __int64 v39; // [rsp+58h] [rbp-90h]
  LPCWSTR lpAccount[3]; // [rsp+60h] [rbp-88h] BYREF
  unsigned __int64 v41; // [rsp+78h] [rbp-70h]
  struct _EVENT_DATA_DESCRIPTOR Src; // [rsp+80h] [rbp-68h] BYREF
  __int64 v43; // [rsp+90h] [rbp-58h]
  unsigned __int64 v44; // [rsp+98h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  LODWORD(v36) = 0;
  fJoinOptions = 3;
  if ( *((_QWORD *)this + 4) )
    fJoinOptions = *((_DWORD *)this + 8);
  v3 = (_QWORD *)*((_QWORD *)this + 2);
  if ( v3 )
  {
    v4 = v3 + 7;
    if ( !v3[9] )
    {
      v5 = v3 + 3;
      if ( v5[3] >= 8u )
        v5 = (_QWORD *)*v5;
      if ( *(_WORD *)v5 )
      {
        v6 = -1;
        do
          ++v6;
        while ( *((_WORD *)v5 + v6) );
      }
      try
      {
        std::wstring::assign(v4, v5);
        v35[0] = 0;
        RandomComputerName = GenerateRandomComputerName(v4, v7, v35);
        if ( RandomComputerName < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x13,
            (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\computernamenode.cpp",
            (const char *)(unsigned int)RandomComputerName,
            lpPassword);
        if ( !v35[0] )
        {
          SerialNumberComputerName = GenerateSerialNumberComputerName(v4);
          if ( SerialNumberComputerName < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1A,
              (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\computernamenode.cpp",
              (const char *)(unsigned int)SerialNumberComputerName,
              lpPassword);
        }
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x9B,
                               (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\domainnode.cpp",
                               v9);
      }
    }
    if ( v4[3] >= 8u )
      v4 = (_QWORD *)*v4;
    v11 = SetDeviceName(v4);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\domainnode.cpp",
        (const char *)(unsigned int)v11,
        lpPassword);
      return v12;
    }
    fJoinOptions |= 0x400u;
  }
  if ( !*((_QWORD *)this + 3) )
    return 0;
  if ( !*((_QWORD *)this + 6) )
  {
    v14 = 160;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\domainnode.cpp",
      (const char *)0x86000005LL,
      lpPassword);
    return 2248146949LL;
  }
  if ( !*((_QWORD *)this + 7) )
  {
    v14 = 161;
    goto LABEL_23;
  }
  if ( !*((_QWORD *)this + 2) && (unsigned int)dword_1800495B0 > 3 )
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_1800495B0, (unsigned __int8 *)byte_18004116D, 0, 0, 2u, &Src);
  try
  {
    v41 = 7;
    lpAccount[2] = 0;
    LOWORD(lpAccount[0]) = 0;
    std::wstring::assign(lpAccount);
    if ( std::wstring::find(lpAccount, 92, 0) == -1 )
    {
      v16 = *((_QWORD *)this + 6);
      v17 = *((_QWORD *)this + 3);
      v39 = 7;
      v38 = 0;
      LOWORD(v37[0]) = 0;
      LODWORD(v36) = 1;
      v18 = (asc_18003C970[0] != 0) + *(_QWORD *)(v17 + 40);
      if ( v18 != 7 )
      {
        LOBYTE(v15) = 1;
        if ( (unsigned __int8)std::wstring::_Grow(v37, v18, v15) )
        {
          v19 = v37;
          if ( v39 >= 8 )
            v19 = (void **)v37[0];
          v38 = 0;
          *(_WORD *)v19 = 0;
        }
      }
      std::wstring::append(v37, v17 + 24, 0, -1);
      std::wstring::append(v37, L"\\");
      v20 = std::wstring::append(v37, v16 + 24, 0, -1);
      std::wstring::wstring(&Src, v20);
      std::wstring::operator=(lpAccount, &Src);
      if ( v44 >= 8 )
        operator delete((void *)Src.Ptr);
      v44 = 7;
      v43 = 0;
      LOWORD(Src.Ptr) = 0;
      if ( v39 >= 8 )
        operator delete(v37[0]);
      if ( (unsigned int)dword_1800495B0 > 3 )
      {
        v24 = (_QWORD *)(*((_QWORD *)this + 6) + 24LL);
        if ( *(_QWORD *)(*((_QWORD *)this + 6) + 48LL) >= 8u )
          v24 = (_QWORD *)*v24;
        v36 = v24;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v21,
          (unsigned int)&dword_1800411C4,
          v22,
          v23,
          (__int64)&v36);
      }
    }
    v25 = (const WCHAR *)(*((_QWORD *)this + 7) + 24LL);
    if ( *(_QWORD *)(*((_QWORD *)this + 7) + 48LL) >= 8u )
      v25 = *(const WCHAR **)v25;
    v26 = (const WCHAR *)lpAccount;
    if ( v41 >= 8 )
      v26 = lpAccount[0];
    v27 = *((_QWORD *)this + 5);
    if ( v27 )
    {
      v28 = (const WCHAR *)(v27 + 24);
      if ( *((_QWORD *)v28 + 3) >= 8u )
        v28 = *(const WCHAR **)v28;
    }
    else
    {
      v28 = 0;
    }
    v29 = (const WCHAR *)(*((_QWORD *)this + 3) + 24LL);
    if ( *(_QWORD *)(*((_QWORD *)this + 3) + 48LL) >= 8u )
      v29 = *(const WCHAR **)v29;
    v30 = NetJoinDomain(0, v29, v28, v26, v25, fJoinOptions);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xC1,
                           (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\domainnode.cpp",
                           v31);
  }
  if ( !v30 )
  {
    if ( v41 >= 8 )
      operator delete((void *)lpAccount[0]);
    return 0;
  }
  v32 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0xBF,
          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\domainnode.cpp",
          (const char *)v30,
          lpPassworda);
  if ( v41 >= 8 )
    operator delete((void *)lpAccount[0]);
  return v32;
}

```

## disassembly

```asm
0x180011e80  push    rbx
0x180011e82  push    rsi
0x180011e83  push    rdi
0x180011e84  push    r12
0x180011e86  push    r14
0x180011e88  push    r15
0x180011e8a  sub     rsp, 0B8h
0x180011e91  mov     rax, cs:__security_cookie
0x180011e98  xor     rax, rsp
0x180011e9b  mov     [rsp+0E8h+var_48], rax
0x180011ea3  mov     rbx, rcx
0x180011ea6  xor     r15d, r15d
0x180011ea9  mov     dword ptr [rsp+0E8h+var_B0], r15d
0x180011eae  lea     r14d, [r15+3]
0x180011eb2  cmp     [rcx+20h], r15
0x180011eb6  jz      short loc_180011EBC
0x180011eb8  mov     r14d, [rcx+20h]
0x180011ebc  mov     rdx, [rcx+10h]
0x180011ec0  test    rdx, rdx
0x180011ec3  jz      loc_180011F95
0x180011ec9  lea     rdi, [rdx+38h]
0x180011ecd  cmp     [rdi+10h], r15
0x180011ed1  jnz     short loc_180011F43
0x180011ed3  add     rdx, 18h
0x180011ed7  cmp     qword ptr [rdx+18h], 8
0x180011edc  jb      short loc_180011EE1
0x180011ede  mov     rdx, [rdx]; Src
0x180011ee1  cmp     [rdx], r15w
0x180011ee5  jnz     short loc_180011EEC
0x180011ee7  mov     r8, r15
0x180011eea  jmp     short loc_180011EFA
0x180011eec  or      r8, 0FFFFFFFFFFFFFFFFh
0x180011ef0  inc     r8
0x180011ef3  cmp     [rdx+r8*2], r15w
0x180011ef8  jnz     short loc_180011EF0
0x180011efa  mov     rcx, rdi; void *
0x180011efd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180011f02  mov     [rsp+0E8h+var_B8], r15b
0x180011f07  lea     r8, [rsp+0E8h+var_B8]
0x180011f0c  mov     rcx, rdi; void *
0x180011f0f  call    ?GenerateRandomComputerName@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEA_N@Z; GenerateRandomComputerName(std::wstring &,ulong,bool *)
0x180011f14  mov     rcx, [rsp+0E8h]; this
0x180011f1c  test    eax, eax
0x180011f1e  js      loc_180012297
0x180011f24  cmp     [rsp+0E8h+var_B8], r15b
0x180011f29  jnz     short loc_180011F43
0x180011f2b  mov     rcx, rdi; void *
0x180011f2e  call    ?GenerateSerialNumberComputerName@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; GenerateSerialNumberComputerName(std::wstring &,ulong)
0x180011f33  mov     rcx, [rsp+0E8h]; this
0x180011f3b  test    eax, eax
0x180011f3d  js      loc_1800122AB
0x180011f43  cmp     qword ptr [rdi+18h], 8
0x180011f48  jb      short loc_180011F4D
0x180011f4a  mov     rdi, [rdi]
0x180011f4d  mov     rcx, rdi
0x180011f50  call    cs:__imp_SetDeviceName
0x180011f57  nop     dword ptr [rax+rax+00h]
0x180011f5c  mov     edi, eax
0x180011f5e  test    eax, eax
0x180011f60  jns     short loc_180011F85
0x180011f62  mov     rcx, [rsp+0E8h]; this
0x180011f6a  mov     r9d, eax; char *
0x180011f6d  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\provcsp\\domai"...
0x180011f74  mov     edx, 97h; void *
0x180011f79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011f7e  mov     eax, edi
0x180011f80  jmp     loc_180012275
0x180011f85  bts     r14d, 0Ah
0x180011f8a  jmp     short loc_180011F95
0x180011f8c  mov     eax, dword ptr [rsp+0E8h+var_B0]
0x180011f90  jmp     loc_180012275
0x180011f95  cmp     [rbx+18h], r15
0x180011f99  jz      loc_180012273
0x180011f9f  cmp     [rbx+30h], r15
0x180011fa3  jnz     short loc_180011FCD
0x180011fa5  mov     edx, 0A0h; void *
0x180011faa  mov     ebx, 86000005h
0x180011faf  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\provcsp\\domai"...
0x180011fb6  mov     r9d, ebx; char *
0x180011fb9  mov     rcx, [rsp+0E8h]; this
0x180011fc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011fc6  mov     eax, ebx
0x180011fc8  jmp     loc_180012275
0x180011fcd  cmp     [rbx+38h], r15
0x180011fd1  jnz     short loc_180011FDA
0x180011fd3  mov     edx, 0A1h
0x180011fd8  jmp     short loc_180011FAA
0x180011fda  cmp     [rbx+10h], r15
0x180011fde  jnz     short loc_18001201A
0x180011fe0  mov     eax, cs:dword_1800495B0
0x180011fe6  cmp     eax, 3
0x180011fe9  jbe     short loc_18001201A
0x180011feb  lea     rax, [rsp+0E8h+Src]
0x180011ff3  mov     qword ptr [rsp+0E8h+fJoinOptions], rax
0x180011ff8  mov     dword ptr [rsp+0E8h+lpPassword], 2
0x180012000  xor     r9d, r9d
0x180012003  xor     r8d, r8d
0x180012006  lea     rdx, byte_18004116D
0x18001200d  lea     rcx, dword_1800495B0
0x180012014  call    _tlgWriteTransfer_EventWriteTransfer
0x180012019  nop
0x18001201a  mov     r12d, 7
0x180012020  mov     [rsp+0E8h+var_70], r12
0x180012025  mov     [rsp+0E8h+var_78], r15
0x18001202a  mov     word ptr [rsp+0E8h+lpAccount], r15w
0x180012030  mov     rdx, [rbx+30h]
0x180012034  add     rdx, 18h
0x180012038  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001203c  xor     r8d, r8d
0x18001203f  lea     rcx, [rsp+0E8h+lpAccount]; void *
0x180012044  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180012049  nop
0x18001204a  lea     edx, [r12+55h]
0x18001204f  xor     r8d, r8d
0x180012052  lea     rcx, [rsp+0E8h+lpAccount]
0x180012057  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x18001205c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012060  jnz     loc_1800121B1
0x180012066  mov     rdi, [rbx+30h]
0x18001206a  mov     rsi, [rbx+18h]
0x18001206e  mov     [rsp+0E8h+var_90], r12
0x180012073  mov     [rsp+0E8h+var_98], r15
0x180012078  mov     word ptr [rsp+0E8h+var_A8], r15w
0x18001207e  mov     dword ptr [rsp+0E8h+var_B0], 1
0x180012086  mov     rcx, r15
0x180012089  cmp     word ptr cs:asc_18003C970, r15w; "\\"
0x180012091  setnz   cl
0x180012094  mov     rdx, [rsi+28h]
0x180012098  add     rdx, rcx
0x18001209b  cmp     rdx, r12
0x18001209e  jz      short loc_1800120CB
0x1800120a0  mov     r8b, 1
0x1800120a3  lea     rcx, [rsp+0E8h+var_A8]
0x1800120a8  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x1800120ad  test    al, al
0x1800120af  jz      short loc_1800120CB
0x1800120b1  lea     rcx, [rsp+0E8h+var_A8]
0x1800120b6  cmp     [rsp+0E8h+var_90], 8
0x1800120bc  cmovnb  rcx, [rsp+0E8h+var_A8]
0x1800120c2  mov     [rsp+0E8h+var_98], r15
0x1800120c7  mov     [rcx], r15w
0x1800120cb  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800120cf  xor     r8d, r8d
0x1800120d2  lea     rdx, [rsi+18h]
0x1800120d6  lea     rcx, [rsp+0E8h+var_A8]
0x1800120db  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800120e0  lea     rdx, asc_18003C970; "\\"
0x1800120e7  lea     rcx, [rsp+0E8h+var_A8]; Src
0x1800120ec  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1800120f1  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800120f5  xor     r8d, r8d
0x1800120f8  lea     rdx, [rdi+18h]
0x1800120fc  lea     rcx, [rsp+0E8h+var_A8]
0x180012101  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180012106  mov     rdx, rax
0x180012109  lea     rcx, [rsp+0E8h+Src]
0x180012111  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180012116  lea     rdx, [rsp+0E8h+Src]; Src
0x18001211e  lea     rcx, [rsp+0E8h+lpAccount]; void *
0x180012123  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180012128  cmp     [rsp+0E8h+var_50], 8
0x180012131  jb      short loc_180012147
0x180012133  mov     rcx, qword ptr [rsp+0E8h+Src]
0x18001213b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012142  nop     dword ptr [rax+rax+00h]
0x180012147  mov     [rsp+0E8h+var_50], r12
0x18001214f  mov     [rsp+0E8h+var_58], r15
0x180012157  mov     word ptr [rsp+0E8h+Src], r15w
0x180012160  cmp     [rsp+0E8h+var_90], 8
0x180012166  jb      short loc_180012179
0x180012168  mov     rcx, [rsp+0E8h+var_A8]
0x18001216d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012174  nop     dword ptr [rax+rax+00h]
0x180012179  mov     eax, cs:dword_1800495B0
0x18001217f  cmp     eax, 3
0x180012182  jbe     short loc_1800121B1
0x180012184  mov     rax, [rbx+30h]
0x180012188  add     rax, 18h
0x18001218c  cmp     qword ptr [rax+18h], 8
0x180012191  jb      short loc_180012196
0x180012193  mov     rax, [rax]
0x180012196  mov     [rsp+0E8h+var_B0], rax
0x18001219b  lea     rax, [rsp+0E8h+var_B0]
0x1800121a0  mov     [rsp+0E8h+lpPassword], rax
0x1800121a5  lea     rdx, dword_1800411C4
0x1800121ac  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800121b1  mov     rcx, [rbx+38h]
0x1800121b5  add     rcx, 18h
0x1800121b9  cmp     qword ptr [rcx+18h], 8
0x1800121be  jb      short loc_1800121C3
0x1800121c0  mov     rcx, [rcx]
0x1800121c3  lea     r9, [rsp+0E8h+lpAccount]
0x1800121c8  cmp     [rsp+0E8h+var_70], 8
0x1800121ce  cmovnb  r9, [rsp+0E8h+lpAccount]; lpAccount
0x1800121d4  mov     r8, [rbx+28h]
0x1800121d8  test    r8, r8
0x1800121db  jz      short loc_1800121ED
0x1800121dd  add     r8, 18h
0x1800121e1  cmp     qword ptr [r8+18h], 8
0x1800121e6  jb      short loc_1800121F0
0x1800121e8  mov     r8, [r8]
0x1800121eb  jmp     short loc_1800121F0
0x1800121ed  mov     r8, r15; lpMachineAccountOU
0x1800121f0  mov     rdx, [rbx+18h]
0x1800121f4  add     rdx, 18h
0x1800121f8  cmp     qword ptr [rdx+18h], 8
0x1800121fd  jb      short loc_180012202
0x1800121ff  mov     rdx, [rdx]; lpDomain
0x180012202  mov     [rsp+0E8h+fJoinOptions], r14d; fJoinOptions
0x180012207  mov     [rsp+0E8h+lpPassword], rcx; unsigned int
0x18001220c  xor     ecx, ecx; lpServer
0x18001220e  call    cs:__imp_NetJoinDomain
0x180012215  nop     dword ptr [rax+rax+00h]
0x18001221a  test    eax, eax
0x18001221c  jz      short loc_180012259
0x18001221e  mov     rcx, [rsp+0E8h]; this
0x180012226  mov     r9d, eax; char *
0x180012229  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\provcsp\\domai"...
0x180012230  mov     edx, 0BFh; void *
0x180012235  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001223a  mov     ebx, eax
0x18001223c  cmp     [rsp+0E8h+var_70], 8
0x180012242  jb      short loc_180012255
0x180012244  mov     rcx, [rsp+0E8h+lpAccount]
0x180012249  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012250  nop     dword ptr [rax+rax+00h]
0x180012255  mov     eax, ebx
0x180012257  jmp     short loc_180012275
0x180012259  cmp     [rsp+0E8h+var_70], 8
0x18001225f  jb      short loc_180012273
0x180012261  mov     rcx, [rsp+0E8h+lpAccount]
0x180012266  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001226d  nop     dword ptr [rax+rax+00h]
0x180012272  nop
0x180012273  xor     eax, eax
0x180012275  mov     rcx, [rsp+0E8h+var_48]
0x18001227d  xor     rcx, rsp; StackCookie
0x180012280  call    __security_check_cookie
0x180012285  add     rsp, 0B8h
0x18001228c  pop     r15
0x18001228e  pop     r14
0x180012290  pop     r12
0x180012292  pop     rdi
0x180012293  pop     rsi
0x180012294  pop     rbx
0x180012295  retn
0x180012297  mov     r9d, eax; char *
0x18001229a  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\provcsp\\compu"...
0x1800122a1  mov     edx, 13h; void *
0x1800122a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800122ab  mov     r9d, eax; char *
0x1800122ae  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\provcsp\\compu"...
0x1800122b5  mov     edx, 1Ah; void *
0x1800122ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
