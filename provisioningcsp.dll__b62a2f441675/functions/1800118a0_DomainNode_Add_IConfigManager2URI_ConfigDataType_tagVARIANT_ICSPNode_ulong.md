# DomainNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x1800118a0`
- end: `0x180011e6e`
- name: `?Add@DomainNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `1486`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001a70`
- `0x180006974`
- `0x180009eb0`
- `0x18000fd74`
- `0x1800118a0`
- `0x1800126bc`
- `0x180022e48`
- `0x1800260a0`
- `0x180026248`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180011982`
- `msvcrt!_wcsicmp` at `0x180011b04`
- `msvcrt!_wcsicmp` at `0x180011bfc`
- `msvcrt!_wcsicmp` at `0x180011c8b`
- `msvcrt!_wcsicmp` at `0x180011cfa`
- `msvcrt!_wcsicmp` at `0x180011d6d`
- `msvcrt!_wcsicmp` at `0x180011de0`
- `msvcrt!_wcsicmp` at `0x180011982`
- `msvcrt!_wcsicmp` at `0x180011b04`
- `msvcrt!_wcsicmp` at `0x180011bfc`
- `msvcrt!_wcsicmp` at `0x180011c8b`
- `msvcrt!_wcsicmp` at `0x180011cfa`
- `msvcrt!_wcsicmp` at `0x180011d6d`
- `msvcrt!_wcsicmp` at `0x180011de0`
- `netutils!NetApiBufferFree` at `0x1800119df`
- `netutils!NetApiBufferFree` at `0x180011a59`
- `netutils!NetApiBufferFree` at `0x180011bc5`
- `netutils!NetApiBufferFree` at `0x180011c4b`
- `netutils!NetApiBufferFree` at `0x180011c6a`
- `netutils!NetApiBufferFree` at `0x1800119df`
- `netutils!NetApiBufferFree` at `0x180011a59`
- `netutils!NetApiBufferFree` at `0x180011bc5`
- `netutils!NetApiBufferFree` at `0x180011c4b`
- `netutils!NetApiBufferFree` at `0x180011c6a`
- `wkscli!NetGetJoinInformation` at `0x1800119a8`
- `wkscli!NetGetJoinInformation` at `0x180011b2a`
- `wkscli!NetGetJoinInformation` at `0x1800119a8`
- `wkscli!NetGetJoinInformation` at `0x180011b2a`

## string_xrefs

- `0x180011977`: `ComputerName`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DomainNode::Add(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        struct _EVENT_DATA_DESCRIPTOR *a4,
        __int64 a5,
        _DWORD *a6)
{
  int v10; // r14d
  __int64 v11; // rdx
  int v13; // ebx
  __int64 v14; // rdx
  struct CConfigServiceProvider2Impl *v15; // rdx
  DWORD JoinInformation; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  GenericBStrNode **v19; // rbx
  GenericBStrNode *v20; // rcx
  int v21; // eax
  LPWSTR v22; // rcx
  DWORD v23; // eax
  __int64 *v24; // rbx
  __int64 v25; // rcx
  int v26; // eax
  unsigned int v27; // edi
  const wchar_t *v28; // rdx
  __int64 *v29; // rbx
  __int64 v30; // rcx
  __int64 *v31; // rbx
  __int64 v32; // rcx
  __int64 *v33; // rbx
  __int64 v34; // rcx
  __int64 *v35; // rbx
  __int64 v36; // rcx
  unsigned int v37; // [rsp+20h] [rbp-59h]
  int v38; // [rsp+20h] [rbp-59h]
  LPWSTR NameBuffer; // [rsp+30h] [rbp-49h] BYREF
  _NETSETUP_JOIN_STATUS BufferType; // [rsp+38h] [rbp-41h] BYREF
  wchar_t *String1; // [rsp+40h] [rbp-39h] BYREF
  int v42; // [rsp+48h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v43; // [rsp+50h] [rbp-29h] BYREF
  ULONGLONG Ptr; // [rsp+60h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]

  v42 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 136LL))(a2, &v42);
  if ( v10 < 0 )
  {
    v11 = 44;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\domainnode.cpp",
      (const char *)(unsigned int)v10,
      v37);
    return (unsigned int)v10;
  }
  if ( v42 != 1 )
  {
    v13 = -2147024809;
    v14 = 45;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\domainnode.cpp",
      (const char *)(unsigned int)v13,
      v37);
    return (unsigned int)v13;
  }
  String1 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t **))(*(_QWORD *)a2 + 88LL))(a2, 0, &String1);
  if ( v10 < 0 )
  {
    v11 = 48;
    goto LABEL_3;
  }
  if ( !_wcsicmp(String1, L"ComputerName") )
  {
    BufferType = NetSetupUnknownStatus;
    NameBuffer = 0;
    JoinInformation = NetGetJoinInformation(0, &NameBuffer, &BufferType);
    if ( JoinInformation )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x38,
              (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\domainnode.cpp",
              (const char *)JoinInformation,
              v37);
      goto LABEL_13;
    }
    if ( BufferType == NetSetupDomainName )
    {
      if ( (unsigned int)dword_1800495B0 > 3 )
        tlgWriteTransfer_EventWriteTransfer(
          (__int64)&dword_1800495B0,
          (unsigned __int8 *)&dword_180041194,
          0,
          0,
          2u,
          &v43);
      if ( Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits < 0 )
        McGenEventWrite_EventWriteTransfer(
          v17,
          (const EVENT_DESCRIPTOR *)MachineDomainJoinedBlockedRename,
          v18,
          1u,
          &v43);
      if ( NameBuffer )
        NetApiBufferFree(NameBuffer);
      return 2248146961LL;
    }
    v19 = (GenericBStrNode **)(a1 + 24);
    v20 = *v19;
    if ( *v19 )
    {
      *v19 = 0;
      (*(void (__fastcall **)(GenericBStrNode *))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v43 = *a4;
    Ptr = a4[1].Ptr;
    v21 = ComputerNameNode::AddStringNode(a3, (__int128 *)&v43, a5, a6, v19);
    v13 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\domainnode.cpp",
        (const char *)(unsigned int)v21,
        v38);
      goto LABEL_13;
    }
    v22 = NameBuffer;
    goto LABEL_50;
  }
  v10 = ProvUtil::CheckAllowedConfigSource(*(ProvUtil **)(a1 + 72), v15);
  if ( v10 < 0 )
  {
    v11 = 77;
    goto LABEL_3;
  }
  if ( _wcsicmp(String1, L"DomainName") )
  {
    if ( _wcsicmp(String1, L"AccountOU") )
    {
      if ( _wcsicmp(String1, L"Account") )
      {
        if ( _wcsicmp(String1, L"Password") )
        {
          if ( _wcsicmp(String1, L"Options") )
            return 2248146946LL;
          v35 = (__int64 *)(a1 + 40);
          v36 = *v35;
          if ( *v35 )
          {
            *v35 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          }
          v43 = *a4;
          Ptr = a4[1].Ptr;
          v37 = (unsigned int)v35;
          v13 = GenericIntNode::AddNode(a3, &v43, a5, a6);
          if ( v13 < 0 )
          {
            v14 = 116;
            goto LABEL_6;
          }
        }
        else
        {
          v33 = (__int64 *)(a1 + 64);
          v34 = *v33;
          if ( *v33 )
          {
            *v33 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
          }
          v43 = *a4;
          Ptr = a4[1].Ptr;
          v37 = (unsigned int)v33;
          v13 = GenericBStrNode::AddStringNode(a3, &v43, a5, a6);
          if ( v13 < 0 )
          {
            v14 = 112;
            goto LABEL_6;
          }
        }
      }
      else
      {
        v31 = (__int64 *)(a1 + 56);
        v32 = *v31;
        if ( *v31 )
        {
          *v31 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        }
        v43 = *a4;
        Ptr = a4[1].Ptr;
        v37 = (unsigned int)v31;
        v13 = GenericBStrNode::AddStringNode(a3, &v43, a5, a6);
        if ( v13 < 0 )
        {
          v14 = 108;
          goto LABEL_6;
        }
      }
    }
    else
    {
      v29 = (__int64 *)(a1 + 48);
      v30 = *v29;
      if ( *v29 )
      {
        *v29 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      v43 = *a4;
      Ptr = a4[1].Ptr;
      v37 = (unsigned int)v29;
      v13 = GenericBStrNode::AddStringNode(a3, &v43, a5, a6);
      if ( v13 < 0 )
      {
        v14 = 104;
        goto LABEL_6;
      }
    }
LABEL_52:
    *a6 |= 2u;
    return 0;
  }
  BufferType = NetSetupUnknownStatus;
  NameBuffer = 0;
  v23 = NetGetJoinInformation(0, &NameBuffer, &BufferType);
  if ( v23 )
  {
    v13 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x53,
            (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\domainnode.cpp",
            (const char *)v23,
            v37);
LABEL_13:
    if ( NameBuffer )
      NetApiBufferFree(NameBuffer);
    return (unsigned int)v13;
  }
  v24 = (__int64 *)(a1 + 32);
  v25 = *v24;
  if ( *v24 )
  {
    *v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v43 = *a4;
  Ptr = a4[1].Ptr;
  v26 = GenericBStrNode::AddStringNode(a3, &v43, a5, a6);
  v27 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\domainnode.cpp",
      (const char *)(unsigned int)v26,
      (int)v24);
    if ( NameBuffer )
      NetApiBufferFree(NameBuffer);
    return v27;
  }
  v22 = NameBuffer;
  if ( !NameBuffer || BufferType != NetSetupDomainName )
  {
LABEL_50:
    if ( v22 )
      NetApiBufferFree(v22);
    goto LABEL_52;
  }
  v28 = (const wchar_t *)(*v24 + 24);
  if ( *(_QWORD *)(*v24 + 48) >= 8u )
    v28 = *(const wchar_t **)v28;
  if ( !_wcsicmp(NameBuffer, v28) )
  {
    v22 = NameBuffer;
    goto LABEL_50;
  }
  if ( (unsigned int)dword_1800495B0 > 3 )
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_1800495B0, (unsigned __int8 *)byte_1800411F7, 0, 0, 2u, &v43);
  if ( NameBuffer )
    NetApiBufferFree(NameBuffer);
  return 2147945091LL;
}

```

## disassembly

```asm
0x1800118a0  push    rbp
0x1800118a2  push    rbx
0x1800118a3  push    rsi
0x1800118a4  push    rdi
0x1800118a5  push    r12
0x1800118a7  push    r13
0x1800118a9  push    r14
0x1800118ab  push    r15
0x1800118ad  lea     rbp, [rsp-0Fh]
0x1800118b2  sub     rsp, 88h
0x1800118b9  mov     rax, cs:__security_cookie
0x1800118c0  xor     rax, rsp
0x1800118c3  mov     [rbp+47h+var_50], rax
0x1800118c7  mov     rdi, r9
0x1800118ca  mov     r15d, r8d
0x1800118cd  mov     r13, rdx
0x1800118d0  mov     rbx, rcx
0x1800118d3  mov     r12, [rbp+47h+arg_20]
0x1800118d7  mov     rsi, [rbp+47h+arg_28]
0x1800118db  mov     [rbp+47h+var_78], 0
0x1800118e2  mov     rax, [rdx]
0x1800118e5  lea     rdx, [rbp+47h+var_78]
0x1800118e9  mov     rcx, r13
0x1800118ec  mov     rax, [rax+88h]
0x1800118f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118f8  mov     r14d, eax
0x1800118fb  test    eax, eax
0x1800118fd  jns     short loc_18001191F
0x1800118ff  mov     edx, 2Ch ; ','; void *
0x180011904  mov     rcx, [rbp+4Fh]; this
0x180011908  mov     r9d, r14d; char *
0x18001190b  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\provcsp\\domai"...
0x180011912  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011917  mov     eax, r14d
0x18001191a  jmp     loc_180011E4D
0x18001191f  cmp     [rbp+47h+var_78], 1
0x180011923  jz      short loc_180011949
0x180011925  mov     ebx, 80070057h
0x18001192a  mov     edx, 2Dh ; '-'; void *
0x18001192f  mov     rcx, [rbp+4Fh]; this
0x180011933  mov     r9d, ebx; char *
0x180011936  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\provcsp\\domai"...
0x18001193d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011942  mov     eax, ebx
0x180011944  jmp     loc_180011E4D
0x180011949  mov     [rbp+47h+String1], 0
0x180011951  mov     rax, [r13+0]
0x180011955  lea     r8, [rbp+47h+String1]
0x180011959  xor     edx, edx
0x18001195b  mov     rcx, r13
0x18001195e  mov     rax, [rax+58h]
0x180011962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011967  mov     r14d, eax
0x18001196a  xor     r13d, r13d
0x18001196d  test    eax, eax
0x18001196f  jns     short loc_180011977
0x180011971  lea     edx, [r13+30h]
0x180011975  jmp     short loc_180011904
0x180011977  lea     rdx, ?gc_wszAccountsDomainComputerNameNode@@3QBGB; "ComputerName"
0x18001197e  mov     rcx, [rbp+47h+String1]; String1
0x180011982  call    cs:__imp__wcsicmp
0x180011989  nop     dword ptr [rax+rax+00h]
0x18001198e  test    eax, eax
0x180011990  jnz     loc_180011ADF
0x180011996  mov     [rbp+47h+BufferType], r13d
0x18001199a  mov     [rbp+47h+NameBuffer], r13
0x18001199e  lea     r8, [rbp+47h+BufferType]; BufferType
0x1800119a2  lea     rdx, [rbp+47h+NameBuffer]; lpNameBuffer
0x1800119a6  xor     ecx, ecx; lpServer
0x1800119a8  call    cs:__imp_NetGetJoinInformation
0x1800119af  nop     dword ptr [rax+rax+00h]
0x1800119b4  test    eax, eax
0x1800119b6  jz      short loc_1800119F0
0x1800119b8  mov     rcx, [rbp+4Fh]; this
0x1800119bc  mov     r9d, eax; char *
0x1800119bf  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\provcsp\\domai"...
0x1800119c6  mov     edx, 38h ; '8'; void *
0x1800119cb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800119d0  mov     ebx, eax
0x1800119d2  mov     rcx, [rbp+47h+NameBuffer]; Buffer
0x1800119d6  test    rcx, rcx
0x1800119d9  jz      loc_180011942
0x1800119df  call    cs:__imp_NetApiBufferFree
0x1800119e6  nop     dword ptr [rax+rax+00h]
0x1800119eb  jmp     loc_180011942
0x1800119f0  cmp     [rbp+47h+BufferType], 3
0x1800119f4  jnz     short loc_180011A6F
0x1800119f6  mov     eax, cs:dword_1800495B0
0x1800119fc  cmp     eax, 3
0x1800119ff  jbe     short loc_180011A2B
0x180011a01  lea     rax, [rbp+47h+var_70]
0x180011a05  mov     [rsp+0C0h+var_98], rax
0x180011a0a  mov     [rsp+0C0h+var_A0], 2
0x180011a12  xor     r9d, r9d
0x180011a15  xor     r8d, r8d
0x180011a18  lea     rdx, dword_180041194
0x180011a1f  lea     rcx, dword_1800495B0
0x180011a26  call    _tlgWriteTransfer_EventWriteTransfer
0x180011a2b  cmp     cs:Microsoft_Windows_Provisioning_Diagnostics_ProviderEnableBits, r13b
0x180011a32  jge     short loc_180011A50
0x180011a34  lea     rax, [rbp+47h+var_70]
0x180011a38  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180011a3d  mov     r9d, 1
0x180011a43  lea     rdx, MachineDomainJoinedBlockedRename
0x180011a4a  call    McGenEventWrite_EventWriteTransfer
0x180011a4f  nop
0x180011a50  mov     rcx, [rbp+47h+NameBuffer]; Buffer
0x180011a54  test    rcx, rcx
0x180011a57  jz      short loc_180011A65
0x180011a59  call    cs:__imp_NetApiBufferFree
0x180011a60  nop     dword ptr [rax+rax+00h]
0x180011a65  mov     eax, 86000011h
0x180011a6a  jmp     loc_180011E4D
0x180011a6f  add     rbx, 18h
0x180011a73  mov     rcx, [rbx]
0x180011a76  test    rcx, rcx
0x180011a79  jz      short loc_180011A8B
0x180011a7b  mov     [rbx], r13
0x180011a7e  mov     rax, [rcx]
0x180011a81  mov     rax, [rax+10h]
0x180011a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a8a  nop
0x180011a8b  movups  xmm0, xmmword ptr [rdi]
0x180011a8e  movaps  [rbp+47h+var_70], xmm0
0x180011a92  movsd   xmm1, qword ptr [rdi+10h]
0x180011a97  movsd   [rbp+47h+var_60], xmm1
0x180011a9c  mov     qword ptr [rsp+0C0h+var_A0], rbx; int
0x180011aa1  mov     r9, rsi
0x180011aa4  mov     r8, r12
0x180011aa7  lea     rdx, [rbp+47h+var_70]
0x180011aab  mov     ecx, r15d
0x180011aae  call    ?AddStringNode@ComputerNameNode@@SAJW4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAKPEAPEAV1@@Z; ComputerNameNode::AddStringNode(ConfigDataType,tagVARIANT,ICSPNode * *,ulong *,ComputerNameNode * *)
0x180011ab3  mov     ebx, eax
0x180011ab5  test    eax, eax
0x180011ab7  jns     short loc_180011AD6
0x180011ab9  mov     rcx, [rbp+4Fh]; this
0x180011abd  mov     r9d, eax; char *
0x180011ac0  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\provcsp\\domai"...
0x180011ac7  mov     edx, 48h ; 'H'; void *
0x180011acc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011ad1  jmp     loc_1800119D2
0x180011ad6  mov     rcx, [rbp+47h+NameBuffer]
0x180011ada  jmp     loc_180011C65
0x180011adf  mov     rcx, [rbx+48h]; this
0x180011ae3  call    ?CheckAllowedConfigSource@ProvUtil@@YAJPEAVCConfigServiceProvider2Impl@@@Z; ProvUtil::CheckAllowedConfigSource(CConfigServiceProvider2Impl *)
0x180011ae8  mov     r14d, eax
0x180011aeb  test    eax, eax
0x180011aed  jns     short loc_180011AF9
0x180011aef  mov     edx, 4Dh ; 'M'
0x180011af4  jmp     loc_180011904
0x180011af9  lea     rdx, ?gc_wszAccountsDomainDomainNameNode@@3QBGB; "DomainName"
0x180011b00  mov     rcx, [rbp+47h+String1]; String1
0x180011b04  call    cs:__imp__wcsicmp
0x180011b0b  nop     dword ptr [rax+rax+00h]
0x180011b10  test    eax, eax
0x180011b12  jnz     loc_180011C80
0x180011b18  mov     [rbp+47h+BufferType], r13d
0x180011b1c  mov     [rbp+47h+NameBuffer], r13
0x180011b20  lea     r8, [rbp+47h+BufferType]; BufferType
0x180011b24  lea     rdx, [rbp+47h+NameBuffer]; lpNameBuffer
0x180011b28  xor     ecx, ecx; lpServer
0x180011b2a  call    cs:__imp_NetGetJoinInformation
0x180011b31  nop     dword ptr [rax+rax+00h]
0x180011b36  test    eax, eax
0x180011b38  jz      short loc_180011B59
0x180011b3a  mov     rcx, [rbp+4Fh]; this
0x180011b3e  mov     r9d, eax; char *
0x180011b41  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\provcsp\\domai"...
0x180011b48  mov     edx, 53h ; 'S'; void *
0x180011b4d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180011b52  mov     ebx, eax
0x180011b54  jmp     loc_1800119D2
0x180011b59  add     rbx, 20h ; ' '
0x180011b5d  mov     rcx, [rbx]
0x180011b60  test    rcx, rcx
0x180011b63  jz      short loc_180011B75
0x180011b65  mov     [rbx], r13
0x180011b68  mov     rax, [rcx]
0x180011b6b  mov     rax, [rax+10h]
0x180011b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b74  nop
0x180011b75  movups  xmm0, xmmword ptr [rdi]
0x180011b78  movaps  [rbp+47h+var_70], xmm0
0x180011b7c  movsd   xmm1, qword ptr [rdi+10h]
0x180011b81  movsd   [rbp+47h+var_60], xmm1
0x180011b86  mov     qword ptr [rsp+0C0h+var_A0], rbx; int
0x180011b8b  mov     r9, rsi
0x180011b8e  mov     r8, r12
0x180011b91  lea     rdx, [rbp+47h+var_70]
0x180011b95  mov     ecx, r15d
0x180011b98  call    ?AddStringNode@GenericBStrNode@@SAJW4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAKPEAPEAV1@@Z; GenericBStrNode::AddStringNode(ConfigDataType,tagVARIANT,ICSPNode * *,ulong *,GenericBStrNode * *)
0x180011b9d  mov     edi, eax
0x180011b9f  test    eax, eax
0x180011ba1  jns     short loc_180011BD8
0x180011ba3  mov     rcx, [rbp+4Fh]; this
0x180011ba7  mov     r9d, eax; char *
0x180011baa  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\provcsp\\domai"...
0x180011bb1  mov     edx, 55h ; 'U'; void *
0x180011bb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011bbb  nop
0x180011bbc  mov     rcx, [rbp+47h+NameBuffer]; Buffer
0x180011bc0  test    rcx, rcx
0x180011bc3  jz      short loc_180011BD1
0x180011bc5  call    cs:__imp_NetApiBufferFree
0x180011bcc  nop     dword ptr [rax+rax+00h]
0x180011bd1  mov     eax, edi
0x180011bd3  jmp     loc_180011E4D
0x180011bd8  mov     rcx, [rbp+47h+NameBuffer]; String1
0x180011bdc  test    rcx, rcx
0x180011bdf  jz      loc_180011C65
0x180011be5  cmp     [rbp+47h+BufferType], 3
0x180011be9  jnz     short loc_180011C65
0x180011beb  mov     rdx, [rbx]
0x180011bee  add     rdx, 18h
0x180011bf2  cmp     qword ptr [rdx+18h], 8
0x180011bf7  jb      short loc_180011BFC
0x180011bf9  mov     rdx, [rdx]; String2
0x180011bfc  call    cs:__imp__wcsicmp
0x180011c03  nop     dword ptr [rax+rax+00h]
0x180011c08  test    eax, eax
0x180011c0a  jz      short loc_180011C61
0x180011c0c  mov     eax, cs:dword_1800495B0
0x180011c12  cmp     eax, 3
0x180011c15  jbe     short loc_180011C42
0x180011c17  lea     rax, [rbp+47h+var_70]
0x180011c1b  mov     [rsp+0C0h+var_98], rax
0x180011c20  mov     [rsp+0C0h+var_A0], 2
0x180011c28  xor     r9d, r9d
0x180011c2b  xor     r8d, r8d
0x180011c2e  lea     rdx, byte_1800411F7
0x180011c35  lea     rcx, dword_1800495B0
0x180011c3c  call    _tlgWriteTransfer_EventWriteTransfer
0x180011c41  nop
0x180011c42  mov     rcx, [rbp+47h+NameBuffer]; Buffer
0x180011c46  test    rcx, rcx
0x180011c49  jz      short loc_180011C57
0x180011c4b  call    cs:__imp_NetApiBufferFree
0x180011c52  nop     dword ptr [rax+rax+00h]
0x180011c57  mov     eax, 80070A83h
0x180011c5c  jmp     loc_180011E4D
0x180011c61  mov     rcx, [rbp+47h+NameBuffer]; Buffer
0x180011c65  test    rcx, rcx
0x180011c68  jz      short loc_180011C76
0x180011c6a  call    cs:__imp_NetApiBufferFree
0x180011c71  nop     dword ptr [rax+rax+00h]
0x180011c76  or      dword ptr [rsi], 2
0x180011c79  xor     eax, eax
0x180011c7b  jmp     loc_180011E4D
0x180011c80  lea     rdx, ?gc_wszAccountsDomainAccountOUNode@@3QBGB; "AccountOU"
0x180011c87  mov     rcx, [rbp+47h+String1]; String1
0x180011c8b  call    cs:__imp__wcsicmp
0x180011c92  nop     dword ptr [rax+rax+00h]
0x180011c97  test    eax, eax
0x180011c99  jnz     short loc_180011CEF
0x180011c9b  add     rbx, 30h ; '0'
0x180011c9f  mov     rcx, [rbx]
0x180011ca2  test    rcx, rcx
0x180011ca5  jz      short loc_180011CB7
0x180011ca7  mov     [rbx], r13
0x180011caa  mov     rax, [rcx]
0x180011cad  mov     rax, [rax+10h]
0x180011cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cb6  nop
0x180011cb7  movups  xmm0, xmmword ptr [rdi]
0x180011cba  movaps  [rbp+47h+var_70], xmm0
0x180011cbe  movsd   xmm1, qword ptr [rdi+10h]
0x180011cc3  movsd   [rbp+47h+var_60], xmm1
0x180011cc8  mov     qword ptr [rsp+0C0h+var_A0], rbx
0x180011ccd  mov     r9, rsi
0x180011cd0  mov     r8, r12
0x180011cd3  lea     rdx, [rbp+47h+var_70]
0x180011cd7  mov     ecx, r15d
0x180011cda  call    ?AddStringNode@GenericBStrNode@@SAJW4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAKPEAPEAV1@@Z; GenericBStrNode::AddStringNode(ConfigDataType,tagVARIANT,ICSPNode * *,ulong *,GenericBStrNode * *)
0x180011cdf  mov     ebx, eax
0x180011ce1  test    eax, eax
0x180011ce3  jns     short loc_180011C76
0x180011ce5  mov     edx, 68h ; 'h'
0x180011cea  jmp     loc_18001192F
0x180011cef  lea     rdx, ?gc_wszAccountsDomainAccountNode@@3QBGB; "Account"
0x180011cf6  mov     rcx, [rbp+47h+String1]; String1
0x180011cfa  call    cs:__imp__wcsicmp
0x180011d01  nop     dword ptr [rax+rax+00h]
0x180011d06  test    eax, eax
0x180011d08  jnz     short loc_180011D62
0x180011d0a  add     rbx, 38h ; '8'
0x180011d0e  mov     rcx, [rbx]
0x180011d11  test    rcx, rcx
0x180011d14  jz      short loc_180011D26
0x180011d16  mov     [rbx], r13
0x180011d19  mov     rax, [rcx]
0x180011d1c  mov     rax, [rax+10h]
0x180011d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d25  nop
0x180011d26  movups  xmm0, xmmword ptr [rdi]
0x180011d29  movaps  [rbp+47h+var_70], xmm0
0x180011d2d  movsd   xmm1, qword ptr [rdi+10h]
0x180011d32  movsd   [rbp+47h+var_60], xmm1
0x180011d37  mov     qword ptr [rsp+0C0h+var_A0], rbx
0x180011d3c  mov     r9, rsi
0x180011d3f  mov     r8, r12
  ... truncated ...
```
