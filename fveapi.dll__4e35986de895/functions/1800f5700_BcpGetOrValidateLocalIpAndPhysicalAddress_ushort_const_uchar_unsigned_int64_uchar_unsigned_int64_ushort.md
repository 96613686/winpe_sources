# BcpGetOrValidateLocalIpAndPhysicalAddress(ushort const *,uchar *,unsigned __int64,uchar * *,unsigned __int64 *,ushort * *)

- ea: `0x1800f5700`
- end: `0x1800f5c55`
- name: `?BcpGetOrValidateLocalIpAndPhysicalAddress@@YAJPEBGPEAE_KPEAPEAEPEA_KPEAPEAG@Z`
- size: `1365`
- prototype: `__int64 __fastcall(char *, unsigned __int8 *, __int64, unsigned __int8 **, unsigned __int64 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a5d3c`

## callees

- `0x1800421e4`
- `0x18004c458`
- `0x18004c678`
- `0x180060196`
- `0x1800a457c`
- `0x1800a461c`
- `0x1800a471c`
- `0x1800a4810`
- `0x1800f5700`
- `0x1800f5c74`
- `0x1800f5c9c`
- `0x1800f7030`
- `0x1800f71d4`
- `0x1800f7278`
- `0x1800f72e4`
- `0x1800f738c`
- `0x1800f7428`
- `0x18011f010`

## import_xrefs

- `msvcrt!mbstowcs_s` at `0x1800f59f3`
- `msvcrt!mbstowcs_s` at `0x1800f59f3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f5800`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f5b55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f5bdb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f5800`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f5b55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f5bdb`
- `WS2_32!inet_ntop` at `0x1800f598f`
- `WS2_32!inet_ntop` at `0x1800f598f`
- `IPHLPAPI!GetAdaptersAddresses` at `0x1800f57b4`
- `IPHLPAPI!GetAdaptersAddresses` at `0x1800f57b4`

## string_xrefs

- `0x1800f582a`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`
- `0x1800f585e`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`
- `0x1800f58bd`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`
- `0x1800f5bac`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`
- `0x1800f5c11`: `onecore\base\ngscb\cornerstone\nkpcommonlib\network.cpp`

## pseudocode

```c
__int64 __fastcall BcpGetOrValidateLocalIpAndPhysicalAddress(
        char *a1,
        unsigned __int8 *a2,
        __int64 a3,
        unsigned __int8 **a4,
        unsigned __int64 *a5,
        unsigned __int16 **a6)
{
  IP_ADAPTER_ADDRESSES_LH *v7; // rdi
  int v8; // ebx
  IP_ADAPTER_ADDRESSES_LH *v9; // rsi
  int v10; // eax
  ULONG AdaptersAddresses; // eax
  void **unique_hlocal; // rax
  void *v13; // rdx
  HLOCAL v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // ebx
  IP_ADAPTER_ADDRESSES_LH *v17; // rcx
  char v18; // dl
  IP_ADAPTER_ADDRESSES_LH *i; // rax
  PIP_ADAPTER_UNICAST_ADDRESS_LH j; // rcx
  const char *v21; // rax
  __int64 v22; // rdx
  BclStageOutput *v23; // rcx
  PIP_ADAPTER_UNICAST_ADDRESS_LH k; // r14
  int v25; // eax
  char *v26; // rbx
  IP_DAD_STATE DadState; // ebx
  BclStageOutput *v28; // rcx
  BclStageOutput *v29; // rcx
  const unsigned __int16 *v30; // r8
  char *v31; // rax
  int v32; // ecx
  int v33; // edx
  unsigned __int8 *v34; // rbx
  const char *v35; // r9
  unsigned __int16 *v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r9
  unsigned int SizePointer; // [rsp+20h] [rbp-99h]
  const char *v41; // [rsp+28h] [rbp-91h]
  HLOCAL hMem; // [rsp+30h] [rbp-89h] BYREF
  char v43[8]; // [rsp+38h] [rbp-81h] BYREF
  PIP_ADAPTER_ADDRESSES AdapterAddresses; // [rsp+40h] [rbp-79h] BYREF
  ULONG v45; // [rsp+48h] [rbp-71h] BYREF
  char v46[8]; // [rsp+50h] [rbp-69h] BYREF
  void *v47; // [rsp+58h] [rbp-61h] BYREF
  size_t PtNumOfCharConverted; // [rsp+60h] [rbp-59h] BYREF
  unsigned __int8 **v49; // [rsp+68h] [rbp-51h]
  unsigned __int64 *v50; // [rsp+70h] [rbp-49h]
  CHAR pStringBuf[24]; // [rsp+78h] [rbp-41h] BYREF
  wchar_t DstBuf[24]; // [rsp+90h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+4Fh]

  v49 = a4;
  v50 = a5;
  BclStageOutput::BclStageOutput((BclStageOutput *)v46, 15);
  if ( a1 )
    BclStageOutput::LogFormat((BclStageOutput *)v46, L"SpecifiedIpAddress", L"%ws", a1);
  v45 = 15360;
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&AdapterAddresses, 0x3C00u);
  v7 = AdapterAddresses;
  if ( !AdapterAddresses )
  {
    v15 = 162;
    goto LABEL_66;
  }
  v8 = 3;
  while ( 1 )
  {
    v9 = v7;
    v10 = v8--;
    if ( v10 <= 0 )
      break;
    AdaptersAddresses = GetAdaptersAddresses(2u, 0xEu, 0, v7, &v45);
    if ( !AdaptersAddresses )
      break;
    if ( AdaptersAddresses != 111 )
    {
      v16 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xB8,
              (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
              (const char *)AdaptersAddresses,
              SizePointer);
      goto LABEL_13;
    }
    unique_hlocal = (void **)wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, v45);
    v13 = *unique_hlocal;
    *unique_hlocal = 0;
    wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset<unsigned char *>(
      (HLOCAL *)&AdapterAddresses,
      v13);
    v14 = hMem;
    hMem = 0;
    if ( v14 )
      LocalFree(v14);
    v7 = AdapterAddresses;
    if ( !AdapterAddresses )
    {
      v15 = 180;
LABEL_66:
      v16 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
        (const char *)0x8007000ELL,
        SizePointer);
      goto LABEL_67;
    }
  }
  if ( v8 < 0 )
  {
    v16 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
      (const char *)0x8000FFFFLL,
      SizePointer);
LABEL_13:
    if ( !v7 )
      goto LABEL_67;
    v17 = v7;
LABEL_63:
    LocalFree(v17);
    goto LABEL_67;
  }
  if ( !a1 )
  {
    v18 = 0;
    for ( i = v7; i; i = i->Next )
    {
      if ( i->IfType == 6 )
      {
        for ( j = i->FirstUnicastAddress; j; j = j->Next )
        {
          if ( j->DadState == NldsPreferred )
          {
            if ( v18 )
            {
              BclSaveKnownFailure(3);
              v21 = "Multiple preferred local IP addresses found.";
              v22 = 209;
              goto LABEL_29;
            }
            v18 = 1;
          }
        }
      }
    }
  }
  while ( 1 )
  {
    if ( !v9 )
    {
      BclSaveKnownFailure(3);
      v21 = "No preferred local IP addresses found.";
      v22 = 293;
LABEL_29:
      v16 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)v22,
              (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
              (const char *)0x139F,
              (unsigned int)v21,
              v41);
LABEL_61:
      if ( !v7 )
        goto LABEL_67;
      v17 = v7;
      goto LABEL_63;
    }
    BclStageOutput::BclStageOutput((BclStageOutput *)v43, 16);
    BclStageOutput::LogFormat((BclStageOutput *)v43, L"FriendlyName", v9->FriendlyName);
    BclStageOutput::LogFormat((BclStageOutput *)v43, L"DNSSuffix", v9->DnsSuffix);
    BclStageOutput::LogByteArray(v23, L"PhysicalAddress", v9->PhysicalAddress, v9->PhysicalAddressLength);
    BclStageOutput::LogFormat((BclStageOutput *)v43, L"IfType", L"0x%x", v9->IfType);
    if ( v9->IfType == 6 )
      break;
LABEL_47:
    BclStageOutput::~BclStageOutput((BclStageOutput *)v43);
    v9 = v9->Next;
  }
  for ( k = v9->FirstUnicastAddress; ; k = k->Next )
  {
    if ( !k )
      goto LABEL_47;
    BclStageOutput::BclStageOutput((BclStageOutput *)&hMem, 17);
    inet_ntop(2, &k->Address.lpSockaddr->sa_data[2], pStringBuf, 0x16u);
    v47 = 0;
    v25 = StringCchLengthA(pStringBuf, 0x7FFFFFFFu, (unsigned __int64 *)&v47);
    v16 = v25;
    if ( v25 < 0 )
    {
      v38 = (unsigned int)v25;
      v37 = 244;
      goto LABEL_60;
    }
    v26 = (char *)v47 + 1;
    if ( (char *)v47 + 1 < v47 )
    {
      v16 = -2147024362;
      v38 = 2147942934LL;
      v37 = 245;
      goto LABEL_60;
    }
    PtNumOfCharConverted = 0;
    if ( mbstowcs_s(&PtNumOfCharConverted, DstBuf, 0x16u, pStringBuf, 0x15u) )
    {
      v16 = -2147024809;
      v38 = 2147942487LL;
      v37 = 249;
      goto LABEL_60;
    }
    if ( (char *)PtNumOfCharConverted != v26 )
    {
      v16 = -2147024809;
      v38 = 2147942487LL;
      v37 = 250;
      goto LABEL_60;
    }
    BclStageOutput::LogFormat((BclStageOutput *)&hMem, L"IPV4Address", L"%s", DstBuf);
    BclStageOutput::LogFormat((BclStageOutput *)&hMem, L"DadState", L"%u", (unsigned int)k->DadState);
    DadState = k->DadState;
    BclStageOutput::LogIndent(v28);
    v30 = L"True";
    if ( DadState != NldsPreferred )
      v30 = L"False";
    BclStageOutput::LogStringInternal(v29, L"DadStateIsPreferred", v30);
    if ( DadState == NldsPreferred )
    {
      if ( !a1 )
        break;
      v31 = a1;
      do
      {
        v32 = *(unsigned __int16 *)&v31[(char *)DstBuf - a1];
        v33 = *(unsigned __int16 *)v31 - v32;
        if ( v33 )
          break;
        v31 += 2;
      }
      while ( v32 );
      if ( !v33 )
        break;
    }
    BclStageOutput::~BclStageOutput((BclStageOutput *)&hMem);
  }
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&v47, v9->PhysicalAddressLength);
  v34 = (unsigned __int8 *)v47;
  if ( !v47 )
  {
    v37 = 280;
LABEL_55:
    v16 = -2147024882;
    v38 = 2147942414LL;
LABEL_60:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v37,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\network.cpp",
      (const char *)v38,
      SizePointer);
    BclStageOutput::~BclStageOutput((BclStageOutput *)&hMem);
    BclStageOutput::~BclStageOutput((BclStageOutput *)v43);
    goto LABEL_61;
  }
  memcpy_0(v47, v9->PhysicalAddress, v9->PhysicalAddressLength);
  *v49 = v34;
  *v50 = v9->PhysicalAddressLength;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &AdapterAddresses,
    (char *)DstBuf,
    0xFFFFFFFFFFFFFFFFuLL,
    v35);
  v36 = (unsigned __int16 *)AdapterAddresses;
  AdapterAddresses = 0;
  *a6 = v36;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&AdapterAddresses);
  if ( !*a6 )
  {
    v37 = 286;
    goto LABEL_55;
  }
  BclStageOutput::~BclStageOutput((BclStageOutput *)&hMem);
  BclStageOutput::~BclStageOutput((BclStageOutput *)v43);
  if ( v7 )
    LocalFree(v7);
  v16 = 0;
LABEL_67:
  BclStageOutput::~BclStageOutput((BclStageOutput *)v46);
  return v16;
}

```

## disassembly

```asm
0x1800f5700  mov     [rsp-8+arg_8], rbx
0x1800f5705  push    rbp
0x1800f5706  push    rsi
0x1800f5707  push    rdi
0x1800f5708  push    r12
0x1800f570a  push    r13
0x1800f570c  push    r14
0x1800f570e  push    r15
0x1800f5710  lea     rbp, [rsp-17h]
0x1800f5715  sub     rsp, 0D0h
0x1800f571c  mov     rax, cs:__security_cookie
0x1800f5723  xor     rax, rsp
0x1800f5726  mov     [rbp+47h+var_40], rax
0x1800f572a  mov     [rbp+47h+var_98], r9
0x1800f572e  mov     r15, rcx
0x1800f5731  mov     rax, [rbp+47h+arg_20]
0x1800f5735  mov     [rbp+47h+var_90], rax
0x1800f5739  mov     r13, [rbp+47h+arg_28]
0x1800f573d  mov     edx, 0Fh
0x1800f5742  lea     rcx, [rbp+47h+var_B0]
0x1800f5746  call    ??0BclStageOutput@@QEAA@W4BCL_STAGE_ID@@@Z; BclStageOutput::BclStageOutput(BCL_STAGE_ID)
0x1800f574b  nop
0x1800f574c  test    r15, r15
0x1800f574f  jz      short loc_1800F576B
0x1800f5751  mov     r9, r15
0x1800f5754  lea     r8, aWs; "%ws"
0x1800f575b  lea     rdx, aSpecifiedipadd; "SpecifiedIpAddress"
0x1800f5762  lea     rcx, [rbp+47h+var_B0]; this
0x1800f5766  call    ?LogFormat@BclStageOutput@@QEAAXPEBG0ZZ; BclStageOutput::LogFormat(ushort const *,ushort const *,...)
0x1800f576b  mov     edx, 3C00h
0x1800f5770  mov     [rbp+47h+var_B8], edx
0x1800f5773  lea     rcx, [rbp+47h+AdapterAddresses]
0x1800f5777  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x1800f577c  nop
0x1800f577d  mov     rdi, [rbp+47h+AdapterAddresses]
0x1800f5781  test    rdi, rdi
0x1800f5784  jz      loc_1800F5C04
0x1800f578a  mov     ebx, 3
0x1800f578f  mov     rsi, rdi
0x1800f5792  mov     eax, ebx
0x1800f5794  dec     ebx
0x1800f5796  test    eax, eax
0x1800f5798  jle     loc_1800F584E
0x1800f579e  lea     rax, [rbp+47h+var_B8]
0x1800f57a2  mov     [rsp+100h+SizePointer], rax; unsigned int
0x1800f57a7  mov     r9, rdi; AdapterAddresses
0x1800f57aa  xor     r8d, r8d; Reserved
0x1800f57ad  lea     edx, [r8+0Eh]; Flags
0x1800f57b1  lea     ecx, [rdx-0Ch]; Family
0x1800f57b4  call    cs:__imp_GetAdaptersAddresses
0x1800f57bb  nop     dword ptr [rax+rax+00h]
0x1800f57c0  test    eax, eax
0x1800f57c2  jz      loc_1800F584E
0x1800f57c8  cmp     eax, 6Fh ; 'o'
0x1800f57cb  jnz     short loc_1800F5823
0x1800f57cd  mov     edx, [rbp+47h+var_B8]
0x1800f57d0  lea     rcx, [rsp+100h+hMem]
0x1800f57d5  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x1800f57da  mov     rdx, [rax]
0x1800f57dd  mov     qword ptr [rax], 0
0x1800f57e4  lea     rcx, [rbp+47h+AdapterAddresses]
0x1800f57e8  call    ??$reset@PEAE@?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAE@Z; wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset<uchar *>(uchar *)
0x1800f57ed  mov     rcx, [rsp+100h+hMem]; hMem
0x1800f57f2  mov     [rsp+100h+hMem], 0
0x1800f57fb  test    rcx, rcx
0x1800f57fe  jz      short loc_1800F580C
0x1800f5800  call    cs:__imp_LocalFree
0x1800f5807  nop     dword ptr [rax+rax+00h]
0x1800f580c  mov     rdi, [rbp+47h+AdapterAddresses]
0x1800f5810  test    rdi, rdi
0x1800f5813  jnz     loc_1800F578F
0x1800f5819  mov     edx, 0B4h
0x1800f581e  jmp     loc_1800F5C09
0x1800f5823  mov     rcx, [rbp+4Fh]; this
0x1800f5827  mov     r9d, eax; char *
0x1800f582a  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f5831  mov     edx, 0B8h; void *
0x1800f5836  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800f583b  mov     ebx, eax
0x1800f583d  test    rsi, rsi
0x1800f5840  jz      loc_1800F5C22
0x1800f5846  mov     rcx, rsi
0x1800f5849  jmp     loc_1800F5BDB
0x1800f584e  test    ebx, ebx
0x1800f5850  jns     short loc_1800F5871
0x1800f5852  mov     rcx, [rbp+4Fh]; this
0x1800f5856  mov     ebx, 8000FFFFh
0x1800f585b  mov     r9d, ebx; char *
0x1800f585e  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f5865  mov     edx, 0BAh; void *
0x1800f586a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f586f  jmp     short loc_1800F583D
0x1800f5871  test    r15, r15
0x1800f5874  jnz     short loc_1800F58DF
0x1800f5876  xor     dl, dl
0x1800f5878  mov     rax, rsi
0x1800f587b  test    rax, rax
0x1800f587e  jz      short loc_1800F58DF
0x1800f5880  cmp     dword ptr [rax+64h], 6
0x1800f5884  jnz     short loc_1800F58A1
0x1800f5886  mov     rcx, [rax+18h]
0x1800f588a  test    rcx, rcx
0x1800f588d  jz      short loc_1800F58A1
0x1800f588f  cmp     dword ptr [rcx+28h], 4
0x1800f5893  jnz     short loc_1800F589B
0x1800f5895  test    dl, dl
0x1800f5897  jnz     short loc_1800F58A7
0x1800f5899  mov     dl, 1
0x1800f589b  mov     rcx, [rcx+8]
0x1800f589f  jmp     short loc_1800F588A
0x1800f58a1  mov     rax, [rax+8]
0x1800f58a5  jmp     short loc_1800F587B
0x1800f58a7  mov     ecx, 3
0x1800f58ac  call    ?BclSaveKnownFailure@@YAXW4BCL_KNOWN_FAILURE_ID@@@Z; BclSaveKnownFailure(BCL_KNOWN_FAILURE_ID)
0x1800f58b1  lea     rax, aMultiplePrefer; "Multiple preferred local IP addresses f"...
0x1800f58b8  mov     edx, 0D1h; void *
0x1800f58bd  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f58c4  mov     r9d, 139Fh; char *
0x1800f58ca  mov     [rsp+100h+SizePointer], rax; unsigned int
0x1800f58cf  mov     rcx, [rbp+4Fh]; this
0x1800f58d3  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800f58d8  mov     ebx, eax
0x1800f58da  jmp     loc_1800F5BD3
0x1800f58df  test    rsi, rsi
0x1800f58e2  jz      loc_1800F5BE9
0x1800f58e8  mov     edx, 10h
0x1800f58ed  lea     rcx, [rsp+100h+var_C8]
0x1800f58f2  call    ??0BclStageOutput@@QEAA@W4BCL_STAGE_ID@@@Z; BclStageOutput::BclStageOutput(BCL_STAGE_ID)
0x1800f58f7  nop
0x1800f58f8  mov     r8, [rsi+48h]; unsigned __int16 *
0x1800f58fc  lea     rdx, aFriendlyname; "FriendlyName"
0x1800f5903  lea     rcx, [rsp+100h+var_C8]; this
0x1800f5908  call    ?LogFormat@BclStageOutput@@QEAAXPEBG0ZZ; BclStageOutput::LogFormat(ushort const *,ushort const *,...)
0x1800f590d  mov     r8, [rsi+38h]; unsigned __int16 *
0x1800f5911  lea     rdx, aDnssuffix; "DNSSuffix"
0x1800f5918  lea     rcx, [rsp+100h+var_C8]; this
0x1800f591d  call    ?LogFormat@BclStageOutput@@QEAAXPEBG0ZZ; BclStageOutput::LogFormat(ushort const *,ushort const *,...)
0x1800f5922  mov     r9d, [rsi+58h]; unsigned __int64
0x1800f5926  lea     r8, [rsi+50h]; unsigned __int8 *
0x1800f592a  lea     rdx, aPhysicaladdres; "PhysicalAddress"
0x1800f5931  call    ?LogByteArray@BclStageOutput@@QEAAXPEBGPEAE_K@Z; BclStageOutput::LogByteArray(ushort const *,uchar *,unsigned __int64)
0x1800f5936  mov     r9d, [rsi+64h]
0x1800f593a  lea     r8, a0xX; "0x%x"
0x1800f5941  lea     rdx, aIftype; "IfType"
0x1800f5948  lea     rcx, [rsp+100h+var_C8]; this
0x1800f594d  call    ?LogFormat@BclStageOutput@@QEAAXPEBG0ZZ; BclStageOutput::LogFormat(ushort const *,ushort const *,...)
0x1800f5952  cmp     dword ptr [rsi+64h], 6
0x1800f5956  jnz     loc_1800F5AB2
0x1800f595c  mov     r14, [rsi+18h]
0x1800f5960  test    r14, r14
0x1800f5963  jz      loc_1800F5AB2
0x1800f5969  mov     edx, 11h
0x1800f596e  lea     rcx, [rsp+100h+hMem]
0x1800f5973  call    ??0BclStageOutput@@QEAA@W4BCL_STAGE_ID@@@Z; BclStageOutput::BclStageOutput(BCL_STAGE_ID)
0x1800f5978  nop
0x1800f5979  mov     rdx, [r14+10h]
0x1800f597d  add     rdx, 4; pAddr
0x1800f5981  mov     r9d, 16h; StringBufSize
0x1800f5987  lea     r8, [rbp+47h+pStringBuf]; pStringBuf
0x1800f598b  lea     ecx, [r9-14h]; Family
0x1800f598f  call    cs:__imp_inet_ntop
0x1800f5996  nop     dword ptr [rax+rax+00h]
0x1800f599b  mov     [rbp+47h+var_A8], 0
0x1800f59a3  lea     r8, [rbp+47h+var_A8]; unsigned __int64 *
0x1800f59a7  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800f59ac  lea     rcx, [rbp+47h+pStringBuf]; char *
0x1800f59b0  call    ?StringCchLengthA@@YAJPEBD_KPEA_K@Z; StringCchLengthA(char const *,unsigned __int64,unsigned __int64 *)
0x1800f59b5  mov     ebx, eax
0x1800f59b7  test    eax, eax
0x1800f59b9  js      loc_1800F5BA4
0x1800f59bf  mov     rax, [rbp+47h+var_A8]
0x1800f59c3  lea     rbx, [rax+1]
0x1800f59c7  cmp     rbx, rax
0x1800f59ca  jb      loc_1800F5B95
0x1800f59d0  mov     [rbp+47h+PtNumOfCharConverted], 0
0x1800f59d8  mov     [rsp+100h+SizePointer], 15h; MaxCount
0x1800f59e1  lea     r9, [rbp+47h+pStringBuf]; SrcBuf
0x1800f59e5  mov     r8d, 16h; SizeInWords
0x1800f59eb  lea     rdx, [rbp+47h+DstBuf]; DstBuf
0x1800f59ef  lea     rcx, [rbp+47h+PtNumOfCharConverted]; PtNumOfCharConverted
0x1800f59f3  call    cs:__imp_mbstowcs_s
0x1800f59fa  nop     dword ptr [rax+rax+00h]
0x1800f59ff  test    eax, eax
0x1800f5a01  jnz     loc_1800F5B86
0x1800f5a07  cmp     [rbp+47h+PtNumOfCharConverted], rbx
0x1800f5a0b  jnz     loc_1800F5B77
0x1800f5a11  lea     r9, [rbp+47h+DstBuf]
0x1800f5a15  lea     r8, aS; "%s"
0x1800f5a1c  lea     rdx, aIpv4address; "IPV4Address"
0x1800f5a23  lea     rcx, [rsp+100h+hMem]; this
0x1800f5a28  call    ?LogFormat@BclStageOutput@@QEAAXPEBG0ZZ; BclStageOutput::LogFormat(ushort const *,ushort const *,...)
0x1800f5a2d  mov     r9d, [r14+28h]
0x1800f5a31  lea     r8, aU; "%u"
0x1800f5a38  lea     rdx, aDadstate; "DadState"
0x1800f5a3f  lea     rcx, [rsp+100h+hMem]; this
0x1800f5a44  call    ?LogFormat@BclStageOutput@@QEAAXPEBG0ZZ; BclStageOutput::LogFormat(ushort const *,ushort const *,...)
0x1800f5a49  mov     ebx, [r14+28h]
0x1800f5a4d  call    ?LogIndent@BclStageOutput@@AEAAXXZ; BclStageOutput::LogIndent(void)
0x1800f5a52  lea     rax, aFalse_1; "False"
0x1800f5a59  lea     r8, aTrue_1; "True"
0x1800f5a60  cmp     ebx, 4
0x1800f5a63  cmovnz  r8, rax; unsigned __int16 *
0x1800f5a67  lea     rdx, aDadstateispref; "DadStateIsPreferred"
0x1800f5a6e  call    ?LogStringInternal@BclStageOutput@@AEAAXPEBG0@Z; BclStageOutput::LogStringInternal(ushort const *,ushort const *)
0x1800f5a73  cmp     ebx, 4
0x1800f5a76  jnz     short loc_1800F5A9F
0x1800f5a78  test    r15, r15
0x1800f5a7b  jz      short loc_1800F5AC5
0x1800f5a7d  mov     rax, r15
0x1800f5a80  lea     r8, [rbp+47h+DstBuf]
0x1800f5a84  sub     r8, r15
0x1800f5a87  movzx   edx, word ptr [rax]
0x1800f5a8a  movzx   ecx, word ptr [rax+r8]
0x1800f5a8f  sub     edx, ecx
0x1800f5a91  jnz     short loc_1800F5A9B
0x1800f5a93  add     rax, 2
0x1800f5a97  test    ecx, ecx
0x1800f5a99  jnz     short loc_1800F5A87
0x1800f5a9b  test    edx, edx
0x1800f5a9d  jz      short loc_1800F5AC5
0x1800f5a9f  lea     rcx, [rsp+100h+hMem]; this
0x1800f5aa4  call    ??1BclStageOutput@@QEAA@XZ; BclStageOutput::~BclStageOutput(void)
0x1800f5aa9  mov     r14, [r14+8]
0x1800f5aad  jmp     loc_1800F5960
0x1800f5ab2  lea     rcx, [rsp+100h+var_C8]; this
0x1800f5ab7  call    ??1BclStageOutput@@QEAA@XZ; BclStageOutput::~BclStageOutput(void)
0x1800f5abc  mov     rsi, [rsi+8]
0x1800f5ac0  jmp     loc_1800F58DF
0x1800f5ac5  mov     edx, [rsi+58h]
0x1800f5ac8  lea     rcx, [rbp+47h+var_A8]
0x1800f5acc  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x1800f5ad1  mov     rbx, [rbp+47h+var_A8]
0x1800f5ad5  test    rbx, rbx
0x1800f5ad8  jz      loc_1800F5B68
0x1800f5ade  mov     r8d, [rsi+58h]; Size
0x1800f5ae2  lea     rdx, [rsi+50h]; Src
0x1800f5ae6  mov     rcx, rbx; void *
0x1800f5ae9  call    memcpy_0
0x1800f5aee  mov     rax, [rbp+47h+var_98]
0x1800f5af2  mov     [rax], rbx
0x1800f5af5  mov     eax, [rsi+58h]
0x1800f5af8  mov     rcx, [rbp+47h+var_90]
0x1800f5afc  mov     [rcx], rax
0x1800f5aff  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800f5b03  lea     rdx, [rbp+47h+DstBuf]
0x1800f5b07  lea     rcx, [rbp+47h+AdapterAddresses]
0x1800f5b0b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800f5b10  mov     rax, [rbp+47h+AdapterAddresses]
0x1800f5b14  mov     [rbp+47h+AdapterAddresses], 0
0x1800f5b1c  mov     [r13+0], rax
0x1800f5b20  lea     rcx, [rbp+47h+AdapterAddresses]
0x1800f5b24  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800f5b29  cmp     qword ptr [r13+0], 0
0x1800f5b2e  jnz     short loc_1800F5B37
0x1800f5b30  mov     edx, 11Eh
0x1800f5b35  jmp     short loc_1800F5B6D
0x1800f5b37  lea     rcx, [rsp+100h+hMem]; this
0x1800f5b3c  call    ??1BclStageOutput@@QEAA@XZ; BclStageOutput::~BclStageOutput(void)
0x1800f5b41  nop
0x1800f5b42  lea     rcx, [rsp+100h+var_C8]; this
0x1800f5b47  call    ??1BclStageOutput@@QEAA@XZ; BclStageOutput::~BclStageOutput(void)
0x1800f5b4c  nop
0x1800f5b4d  test    rdi, rdi
0x1800f5b50  jz      short loc_1800F5B61
0x1800f5b52  mov     rcx, rdi; hMem
0x1800f5b55  call    cs:__imp_LocalFree
0x1800f5b5c  nop     dword ptr [rax+rax+00h]
0x1800f5b61  xor     ebx, ebx
0x1800f5b63  jmp     loc_1800F5C22
0x1800f5b68  mov     edx, 118h
0x1800f5b6d  mov     ebx, 8007000Eh
0x1800f5b72  mov     r9d, ebx
0x1800f5b75  jmp     short loc_1800F5BAC
0x1800f5b77  mov     ebx, 80070057h
0x1800f5b7c  mov     r9d, ebx
0x1800f5b7f  mov     edx, 0FAh
0x1800f5b84  jmp     short loc_1800F5BAC
0x1800f5b86  mov     ebx, 80070057h
0x1800f5b8b  mov     r9d, ebx
0x1800f5b8e  mov     edx, 0F9h
0x1800f5b93  jmp     short loc_1800F5BAC
0x1800f5b95  mov     ebx, 80070216h
0x1800f5b9a  mov     r9d, ebx
0x1800f5b9d  mov     edx, 0F5h
0x1800f5ba2  jmp     short loc_1800F5BAC
0x1800f5ba4  mov     r9d, eax; char *
0x1800f5ba7  mov     edx, 0F4h; void *
0x1800f5bac  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f5bb3  mov     rcx, [rbp+4Fh]; this
0x1800f5bb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5bbc  nop
0x1800f5bbd  lea     rcx, [rsp+100h+hMem]; this
0x1800f5bc2  call    ??1BclStageOutput@@QEAA@XZ; BclStageOutput::~BclStageOutput(void)
0x1800f5bc7  nop
0x1800f5bc8  lea     rcx, [rsp+100h+var_C8]; this
0x1800f5bcd  call    ??1BclStageOutput@@QEAA@XZ; BclStageOutput::~BclStageOutput(void)
0x1800f5bd2  nop
0x1800f5bd3  test    rdi, rdi
0x1800f5bd6  jz      short loc_1800F5C22
0x1800f5bd8  mov     rcx, rdi; hMem
  ... truncated ...
```
