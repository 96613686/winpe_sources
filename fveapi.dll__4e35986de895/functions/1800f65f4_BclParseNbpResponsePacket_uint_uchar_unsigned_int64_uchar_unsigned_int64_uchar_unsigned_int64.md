# BclParseNbpResponsePacket(uint,uchar *,unsigned __int64,uchar *,unsigned __int64,uchar * *,unsigned __int64 *)

- ea: `0x1800f65f4`
- end: `0x1800f69fd`
- name: `?BclParseNbpResponsePacket@@YAJIPEAE_K01PEAPEAEPEA_K@Z`
- size: `1033`
- prototype: `__int64 __fastcall(int, unsigned __int8 *, unsigned __int64, unsigned __int8 *, unsigned __int64, unsigned __int8 **, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a5d3c`

## callees

- `0x180004a70`
- `0x18003d02c`
- `0x18004ad74`
- `0x18004c458`
- `0x18004c678`
- `0x180060196`
- `0x1800a4530`
- `0x1800a457c`
- `0x1800a4780`
- `0x1800f5c74`
- `0x1800f65f4`
- `0x1800f6a04`
- `0x1800f6ab4`
- `0x1800f6dd4`
- `0x1800f71d4`
- `0x1800f7500`
- `0x1800f77fc`
- `0x18011f010`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x1800f66df`
- `ntdll!RtlCompareMemory` at `0x1800f66df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f68b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f6985`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f68b1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f6985`

## string_xrefs

- `0x1800f6681`: `onecore\base\ngscb\cornerstone\nkpcommonlib\nbppacket.cpp`
- `0x1800f67fb`: `onecore\base\ngscb\cornerstone\nkpcommonlib\nbppacket.cpp`
- `0x1800f6885`: `onecore\base\ngscb\cornerstone\nkpcommonlib\nbppacket.cpp`
- `0x1800f69b8`: `onecore\base\ngscb\cornerstone\nkpcommonlib\nbppacket.cpp`

## pseudocode

```c
__int64 __fastcall BclParseNbpResponsePacket(
        int a1,
        unsigned __int8 *a2,
        unsigned __int64 a3,
        unsigned __int8 *a4,
        unsigned __int64 a5,
        unsigned __int8 **a6,
        unsigned __int64 *a7)
{
  int v11; // eax
  int v12; // ecx
  int v13; // r9d
  unsigned int v14; // ebx
  const void *Dhcpv4Option; // rax
  __int64 v16; // rdx
  int v17; // ecx
  int v18; // r9d
  __int64 v19; // rdi
  __int16 v20; // bx
  const struct _tlgProvider_t *v21; // rax
  int v22; // esi
  __int64 v23; // r8
  __int64 v24; // r9
  SIZE_T v25; // rsi
  UCHAR *v26; // rbx
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // r9
  int KeyRawKeyFromNbpResponse; // edi
  __int64 v30; // rdx
  __int64 v31; // rcx
  unsigned __int8 *v32; // rdx
  bool v33; // zf
  const struct _tlgProvider_t *v34; // rax
  int v35; // edi
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v38; // rcx
  unsigned __int8 *v39; // rdx
  unsigned int pbInput; // [rsp+20h] [rbp-A1h]
  int pbInputa; // [rsp+20h] [rbp-A1h]
  int v43; // [rsp+40h] [rbp-81h] BYREF
  unsigned __int16 v44; // [rsp+44h] [rbp-7Dh] BYREF
  unsigned __int8 *v45; // [rsp+48h] [rbp-79h] BYREF
  unsigned __int64 v46; // [rsp+50h] [rbp-71h] BYREF
  _BYTE v47[8]; // [rsp+58h] [rbp-69h] BYREF
  __int64 v48; // [rsp+60h] [rbp-61h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-59h] BYREF
  __int64 v50; // [rsp+70h] [rbp-51h] BYREF
  struct _GUID v51; // [rsp+78h] [rbp-49h] BYREF
  char v52; // [rsp+88h] [rbp-39h]
  __int128 v53; // [rsp+90h] [rbp-31h] BYREF
  struct _GUID v54; // [rsp+A0h] [rbp-21h] BYREF
  unsigned __int8 v55[16]; // [rsp+B0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]

  BclStageOutput::BclStageOutput((BclStageOutput *)v47, 6);
  if ( *a2 != 2 || *((_DWORD *)a2 + 1) != a1 || *((_DWORD *)a2 + 59) != 1666417251 )
  {
    v16 = 483;
    goto LABEL_41;
  }
  v44 = 0;
  v11 = UIntPtrToUShort(a3, &v44);
  v14 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\nbppacket.cpp",
      (const char *)(unsigned int)v11,
      pbInput);
LABEL_42:
    BclStageOutput::~BclStageOutput((BclStageOutput *)v47);
    return v14;
  }
  LOBYTE(v43) = 0;
  LOBYTE(v12) = 60;
  Dhcpv4Option = (const void *)FindDhcpv4Option(v12, (_DWORD)a2, v44, v13, (__int64)&v43);
  if ( !Dhcpv4Option )
  {
    v16 = 495;
LABEL_41:
    v14 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v16,
            (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\nbppacket.cpp",
            (const char *)0xD,
            pbInput);
    goto LABEL_42;
  }
  if ( (_BYTE)v43 != 9 || RtlCompareMemory(Dhcpv4Option, "BITLOCKER", 9u) != 9 )
  {
    v16 = 502;
    goto LABEL_41;
  }
  LOBYTE(v43) = 0;
  LOBYTE(v17) = 43;
  v19 = FindDhcpv4Option(v17, (_DWORD)a2, v44, v18, (__int64)&v43);
  if ( !v19 )
  {
    v16 = 511;
    goto LABEL_41;
  }
  if ( (unsigned __int8)v43 <= 0x12u )
  {
    v16 = 515;
    goto LABEL_41;
  }
  if ( *(_BYTE *)v19 != 2 || (v20 = (unsigned __int8)v43 - 2, *(unsigned __int8 *)(v19 + 1) != (unsigned __int8)v43 - 2) )
  {
    v16 = 520;
    goto LABEL_41;
  }
  v21 = BlazeCheckProvider::Provider();
  v22 = (int)v21;
  if ( *(_DWORD *)v21 > 4u && (unsigned __int8)tlgKeywordOn(v21, 0x400000000000LL) )
  {
    v46 = a3;
    v48 = 0x1000000;
    v53 = (__int128)*BclAppSessionGuid(&v54);
    hMem = &v53;
    LOBYTE(v43) = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v22,
      (int)word_180160672,
      v23,
      v24,
      (__int64)&v43,
      (__int64 *)&hMem,
      (__int64)&v48,
      (__int64)&v46);
  }
  v25 = (unsigned __int16)(v20 - 16);
  wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, v25);
  v26 = (UCHAR *)hMem;
  if ( !hMem )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x217,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\nbppacket.cpp",
      (const char *)0x8007000ELL,
      pbInput);
    goto LABEL_42;
  }
  *(_OWORD *)v55 = *(_OWORD *)(v19 + 2);
  memcpy_0(hMem, (const void *)(v19 + 18), v25);
  v46 = 0;
  v45 = 0;
  *(_QWORD *)&v51.Data1 = &v45;
  *(_QWORD *)v51.Data4 = 0;
  v52 = 1;
  KeyRawKeyFromNbpResponse = BcpDecryptWithAesCcm(a4, v27, v55, v28, v26, v25, (unsigned __int8 **)v51.Data4, &v46);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>>((__int64)&v51);
  if ( KeyRawKeyFromNbpResponse < 0 )
  {
    v30 = 542;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\nkpcommonlib\\nbppacket.cpp",
      (const char *)(unsigned int)KeyRawKeyFromNbpResponse,
      pbInputa);
    v32 = v45;
    v33 = v45 == 0;
    v45 = 0;
    if ( !v33 )
      wil::hlocal_secure_deleter::operator()<unsigned char>(v31, v32);
    if ( v26 )
      LocalFree(v26);
    v14 = KeyRawKeyFromNbpResponse;
    goto LABEL_42;
  }
  v34 = BlazeCheckProvider::Provider();
  v35 = (int)v34;
  if ( *(_DWORD *)v34 > 4u && (unsigned __int8)tlgKeywordOn(v34, 0x400000000000LL) )
  {
    v48 = a3;
    v50 = 0x1000000;
    v54 = *BclAppSessionGuid(&v51);
    *(_QWORD *)&v53 = &v54;
    LOBYTE(v43) = 1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v35,
      (int)byte_1801605FB,
      v36,
      v37,
      (__int64)&v43,
      (__int64 *)&v53,
      (__int64)&v50,
      (__int64)&v48);
  }
  KeyRawKeyFromNbpResponse = BcpGetKeyRawKeyFromNbpResponse(v45, v46, a6, a7);
  if ( KeyRawKeyFromNbpResponse < 0 )
  {
    v30 = 548;
    goto LABEL_23;
  }
  v39 = v45;
  v45 = 0;
  if ( v39 )
    wil::hlocal_secure_deleter::operator()<unsigned char>(v38, v39);
  if ( v26 )
    LocalFree(v26);
  BclStageOutput::~BclStageOutput((BclStageOutput *)v47);
  return 0;
}

```

## disassembly

```asm
0x1800f65f4  mov     [rsp-8+arg_0], rbx
0x1800f65f9  push    rbp
0x1800f65fa  push    rsi
0x1800f65fb  push    rdi
0x1800f65fc  push    r12
0x1800f65fe  push    r13
0x1800f6600  push    r14
0x1800f6602  push    r15
0x1800f6604  lea     rbp, [rsp-0Fh]
0x1800f6609  sub     rsp, 0D0h
0x1800f6610  mov     rax, cs:__security_cookie
0x1800f6617  xor     rax, rsp
0x1800f661a  mov     [rbp+3Fh+var_40], rax
0x1800f661e  mov     r13, r9
0x1800f6621  mov     r14, r8
0x1800f6624  mov     rdi, rdx
0x1800f6627  mov     ebx, ecx
0x1800f6629  mov     r15, [rbp+3Fh+arg_28]
0x1800f662d  mov     r12, [rbp+3Fh+arg_30]
0x1800f6631  mov     edx, 6
0x1800f6636  lea     rcx, [rbp+3Fh+var_A8]
0x1800f663a  call    ??0BclStageOutput@@QEAA@W4BCL_STAGE_ID@@@Z; BclStageOutput::BclStageOutput(BCL_STAGE_ID)
0x1800f663f  nop
0x1800f6640  cmp     byte ptr [rdi], 2
0x1800f6643  jnz     loc_1800F69AD
0x1800f6649  cmp     [rdi+4], ebx
0x1800f664c  jnz     loc_1800F69AD
0x1800f6652  cmp     dword ptr [rdi+0ECh], 63538263h
0x1800f665c  jnz     loc_1800F69AD
0x1800f6662  xor     eax, eax
0x1800f6664  mov     [rbp+3Fh+var_BC], ax
0x1800f6668  lea     rdx, [rbp+3Fh+var_BC]; unsigned __int16 *
0x1800f666c  mov     rcx, r14; unsigned __int64
0x1800f666f  call    ?UIntPtrToUShort@@YAJ_KPEAG@Z; UIntPtrToUShort(unsigned __int64,ushort *)
0x1800f6674  mov     ebx, eax
0x1800f6676  test    eax, eax
0x1800f6678  jns     short loc_1800F6697
0x1800f667a  mov     rcx, [rbp+47h]; this
0x1800f667e  mov     r9d, eax; char *
0x1800f6681  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f6688  mov     edx, 1E7h; void *
0x1800f668d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6692  jmp     loc_1800F69CA
0x1800f6697  mov     byte ptr [rsp+100h+var_C0], 0
0x1800f669c  lea     rax, [rsp+100h+var_C0]
0x1800f66a1  mov     [rsp+100h+pbInput], rax
0x1800f66a6  movzx   r8d, [rbp+3Fh+var_BC]
0x1800f66ab  mov     rdx, rdi
0x1800f66ae  mov     cl, 3Ch ; '<'
0x1800f66b0  call    FindDhcpv4Option
0x1800f66b5  test    rax, rax
0x1800f66b8  jnz     short loc_1800F66C4
0x1800f66ba  mov     edx, 1EFh
0x1800f66bf  jmp     loc_1800F69B2
0x1800f66c4  cmp     byte ptr [rsp+100h+var_C0], 9
0x1800f66c9  jnz     loc_1800F69A6
0x1800f66cf  mov     r8d, 9; Length
0x1800f66d5  lea     rdx, aBitlocker; "BITLOCKER"
0x1800f66dc  mov     rcx, rax; Source1
0x1800f66df  call    cs:__imp_RtlCompareMemory
0x1800f66e6  nop     dword ptr [rax+rax+00h]
0x1800f66eb  cmp     rax, 9
0x1800f66ef  jnz     loc_1800F69A6
0x1800f66f5  mov     byte ptr [rsp+100h+var_C0], 0
0x1800f66fa  lea     rax, [rsp+100h+var_C0]
0x1800f66ff  mov     [rsp+100h+pbInput], rax
0x1800f6704  movzx   r8d, [rbp+3Fh+var_BC]
0x1800f6709  mov     rdx, rdi
0x1800f670c  mov     cl, 2Bh ; '+'
0x1800f670e  call    FindDhcpv4Option
0x1800f6713  mov     rdi, rax
0x1800f6716  test    rax, rax
0x1800f6719  jnz     short loc_1800F6725
0x1800f671b  mov     edx, 1FFh
0x1800f6720  jmp     loc_1800F69B2
0x1800f6725  movzx   eax, byte ptr [rsp+100h+var_C0]
0x1800f672a  cmp     al, 12h
0x1800f672c  ja      short loc_1800F6738
0x1800f672e  mov     edx, 203h
0x1800f6733  jmp     loc_1800F69B2
0x1800f6738  cmp     byte ptr [rdi], 2
0x1800f673b  jnz     loc_1800F699F
0x1800f6741  lea     ebx, [rax-2]
0x1800f6744  movzx   eax, byte ptr [rdi+1]
0x1800f6748  cmp     eax, ebx
0x1800f674a  jnz     loc_1800F699F
0x1800f6750  call    ?Provider@BlazeCheckProvider@@SAPEBU_tlgProvider_t@@XZ; BlazeCheckProvider::Provider(void)
0x1800f6755  mov     rsi, rax
0x1800f6758  mov     ecx, [rax]
0x1800f675a  cmp     ecx, 4
0x1800f675d  jbe     short loc_1800F67D3
0x1800f675f  mov     rdx, 400000000000h
0x1800f6769  mov     rcx, rax
0x1800f676c  call    _tlgKeywordOn
0x1800f6771  test    al, al
0x1800f6773  jz      short loc_1800F67D3
0x1800f6775  mov     [rbp+3Fh+var_B0], r14
0x1800f6779  mov     [rbp+3Fh+var_A0], 1000000h
0x1800f6781  lea     rcx, [rbp+3Fh+var_60]; retstr
0x1800f6785  call    ?BclAppSessionGuid@@YA?AU_GUID@@XZ; BclAppSessionGuid(void)
0x1800f678a  movups  xmm0, xmmword ptr [rax]
0x1800f678d  movdqu  [rbp+3Fh+var_70], xmm0
0x1800f6792  lea     rax, [rbp+3Fh+var_70]
0x1800f6796  mov     [rbp+3Fh+hMem], rax
0x1800f679a  mov     byte ptr [rsp+100h+var_C0], 1
0x1800f679f  lea     rax, [rbp+3Fh+var_B0]
0x1800f67a3  mov     [rsp+100h+var_C8], rax
0x1800f67a8  lea     rax, [rbp+3Fh+var_A0]
0x1800f67ac  mov     [rsp+100h+var_D0], rax
0x1800f67b1  lea     rax, [rbp+3Fh+hMem]
0x1800f67b5  mov     [rsp+100h+var_D8], rax
0x1800f67ba  lea     rax, [rsp+100h+var_C0]
0x1800f67bf  mov     [rsp+100h+pbInput], rax; int
0x1800f67c4  lea     rdx, word_180160672
0x1800f67cb  mov     rcx, rsi
0x1800f67ce  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800f67d3  sub     bx, 10h
0x1800f67d7  movzx   esi, bx
0x1800f67da  mov     edx, esi
0x1800f67dc  lea     rcx, [rbp+3Fh+hMem]
0x1800f67e0  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x1800f67e5  nop
0x1800f67e6  mov     rbx, [rbp+3Fh+hMem]
0x1800f67ea  test    rbx, rbx
0x1800f67ed  jnz     short loc_1800F6812
0x1800f67ef  mov     rcx, [rbp+47h]; this
0x1800f67f3  mov     ebx, 8007000Eh
0x1800f67f8  mov     r9d, ebx; char *
0x1800f67fb  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f6802  mov     edx, 217h; void *
0x1800f6807  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f680c  nop
0x1800f680d  jmp     loc_1800F69CA
0x1800f6812  movups  xmm0, xmmword ptr [rdi+2]
0x1800f6816  movdqu  xmmword ptr [rbp+3Fh+var_50], xmm0
0x1800f681b  lea     rdx, [rdi+12h]; Src
0x1800f681f  mov     r8, rsi; Size
0x1800f6822  mov     rcx, rbx; void *
0x1800f6825  call    memcpy_0
0x1800f682a  xor     ecx, ecx
0x1800f682c  mov     [rbp+3Fh+var_B0], rcx
0x1800f6830  mov     [rbp+3Fh+var_B8], rcx
0x1800f6834  lea     rax, [rbp+3Fh+var_B8]
0x1800f6838  mov     qword ptr [rbp+3Fh+var_88.Data1], rax
0x1800f683c  mov     qword ptr [rbp+3Fh+var_88.Data4], rcx
0x1800f6840  mov     [rbp+3Fh+var_78], 1
0x1800f6844  lea     rax, [rbp+3Fh+var_B0]
0x1800f6848  mov     [rsp+100h+var_C8], rax; unsigned __int64 *
0x1800f684d  lea     rax, [rbp+3Fh+var_88.Data4]
0x1800f6851  mov     [rsp+100h+var_D0], rax; unsigned __int8 **
0x1800f6856  mov     [rsp+100h+var_D8], rsi; unsigned __int64
0x1800f685b  mov     [rsp+100h+pbInput], rbx; int
0x1800f6860  lea     r8, [rbp+3Fh+var_50]; unsigned __int8 *
0x1800f6864  mov     rcx, r13; unsigned __int8 *
0x1800f6867  call    ?BcpDecryptWithAesCcm@@YAJPEAE_K0101PEAPEAEPEA_K@Z; BcpDecryptWithAesCcm(uchar *,unsigned __int64,uchar *,unsigned __int64,uchar *,unsigned __int64,uchar * *,unsigned __int64 *)
0x1800f686c  mov     edi, eax
0x1800f686e  lea     rcx, [rbp+3Fh+var_88]
0x1800f6872  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>>(void)
0x1800f6877  xor     esi, esi
0x1800f6879  test    edi, edi
0x1800f687b  jns     short loc_1800F68C4
0x1800f687d  mov     edx, 21Eh; void *
0x1800f6882  mov     r9d, edi; char *
0x1800f6885  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f688c  mov     rcx, [rbp+47h]; this
0x1800f6890  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f6895  nop
0x1800f6896  mov     rdx, [rbp+3Fh+var_B8]
0x1800f689a  test    rdx, rdx
0x1800f689d  mov     [rbp+3Fh+var_B8], rsi
0x1800f68a1  jz      short loc_1800F68A9
0x1800f68a3  call    ??$?RE@hlocal_secure_deleter@wil@@QEBAXPEAE@Z; wil::hlocal_secure_deleter::operator()<uchar>(uchar *)
0x1800f68a8  nop
0x1800f68a9  test    rbx, rbx
0x1800f68ac  jz      short loc_1800F68BD
0x1800f68ae  mov     rcx, rbx; hMem
0x1800f68b1  call    cs:__imp_LocalFree
0x1800f68b8  nop     dword ptr [rax+rax+00h]
0x1800f68bd  mov     ebx, edi
0x1800f68bf  jmp     loc_1800F69CA
0x1800f68c4  call    ?Provider@BlazeCheckProvider@@SAPEBU_tlgProvider_t@@XZ; BlazeCheckProvider::Provider(void)
0x1800f68c9  mov     rdi, rax
0x1800f68cc  mov     ecx, [rax]
0x1800f68ce  cmp     ecx, 4
0x1800f68d1  jbe     short loc_1800F6947
0x1800f68d3  mov     rdx, 400000000000h
0x1800f68dd  mov     rcx, rax
0x1800f68e0  call    _tlgKeywordOn
0x1800f68e5  test    al, al
0x1800f68e7  jz      short loc_1800F6947
0x1800f68e9  mov     [rbp+3Fh+var_A0], r14
0x1800f68ed  mov     [rbp+3Fh+var_90], 1000000h
0x1800f68f5  lea     rcx, [rbp+3Fh+var_88]; retstr
0x1800f68f9  call    ?BclAppSessionGuid@@YA?AU_GUID@@XZ; BclAppSessionGuid(void)
0x1800f68fe  movups  xmm0, xmmword ptr [rax]
0x1800f6901  movdqu  xmmword ptr [rbp+3Fh+var_60.Data1], xmm0
0x1800f6906  lea     rax, [rbp+3Fh+var_60]
0x1800f690a  mov     qword ptr [rbp+3Fh+var_70], rax
0x1800f690e  mov     byte ptr [rsp+100h+var_C0], 1
0x1800f6913  lea     rax, [rbp+3Fh+var_A0]
0x1800f6917  mov     [rsp+100h+var_C8], rax
0x1800f691c  lea     rax, [rbp+3Fh+var_90]
0x1800f6920  mov     [rsp+100h+var_D0], rax
0x1800f6925  lea     rax, [rbp+3Fh+var_70]
0x1800f6929  mov     [rsp+100h+var_D8], rax
0x1800f692e  lea     rax, [rsp+100h+var_C0]
0x1800f6933  mov     [rsp+100h+pbInput], rax
0x1800f6938  lea     rdx, byte_1801605FB
0x1800f693f  mov     rcx, rdi
0x1800f6942  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800f6947  mov     r9, r12; unsigned __int64 *
0x1800f694a  mov     r8, r15; unsigned __int8 **
0x1800f694d  mov     rdx, [rbp+3Fh+var_B0]; unsigned __int64
0x1800f6951  mov     rcx, [rbp+3Fh+var_B8]; unsigned __int8 *
0x1800f6955  call    ?BcpGetKeyRawKeyFromNbpResponse@@YAJPEAE_KPEAPEAEPEA_K@Z; BcpGetKeyRawKeyFromNbpResponse(uchar *,unsigned __int64,uchar * *,unsigned __int64 *)
0x1800f695a  mov     edi, eax
0x1800f695c  test    eax, eax
0x1800f695e  jns     short loc_1800F696A
0x1800f6960  mov     edx, 224h
0x1800f6965  jmp     loc_1800F6882
0x1800f696a  mov     rdx, [rbp+3Fh+var_B8]
0x1800f696e  mov     [rbp+3Fh+var_B8], rsi
0x1800f6972  test    rdx, rdx
0x1800f6975  jz      short loc_1800F697D
0x1800f6977  call    ??$?RE@hlocal_secure_deleter@wil@@QEBAXPEAE@Z; wil::hlocal_secure_deleter::operator()<uchar>(uchar *)
0x1800f697c  nop
0x1800f697d  test    rbx, rbx
0x1800f6980  jz      short loc_1800F6992
0x1800f6982  mov     rcx, rbx; hMem
0x1800f6985  call    cs:__imp_LocalFree
0x1800f698c  nop     dword ptr [rax+rax+00h]
0x1800f6991  nop
0x1800f6992  lea     rcx, [rbp+3Fh+var_A8]; this
0x1800f6996  call    ??1BclStageOutput@@QEAA@XZ; BclStageOutput::~BclStageOutput(void)
0x1800f699b  xor     eax, eax
0x1800f699d  jmp     short loc_1800F69D5
0x1800f699f  mov     edx, 208h
0x1800f69a4  jmp     short loc_1800F69B2
0x1800f69a6  mov     edx, 1F6h
0x1800f69ab  jmp     short loc_1800F69B2
0x1800f69ad  mov     edx, 1E3h; void *
0x1800f69b2  mov     r9d, 0Dh; char *
0x1800f69b8  lea     r8, aOnecoreBaseNgs_15; "onecore\\base\\ngscb\\cornerstone\\nkpc"...
0x1800f69bf  mov     rcx, [rbp+47h]; this
0x1800f69c3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800f69c8  mov     ebx, eax
0x1800f69ca  lea     rcx, [rbp+3Fh+var_A8]; this
0x1800f69ce  call    ??1BclStageOutput@@QEAA@XZ; BclStageOutput::~BclStageOutput(void)
0x1800f69d3  mov     eax, ebx
0x1800f69d5  mov     rcx, [rbp+3Fh+var_40]
0x1800f69d9  xor     rcx, rsp; StackCookie
0x1800f69dc  call    __security_check_cookie
0x1800f69e1  mov     rbx, [rsp+100h+arg_0]
0x1800f69e9  add     rsp, 0D0h
0x1800f69f0  pop     r15
0x1800f69f2  pop     r14
0x1800f69f4  pop     r13
0x1800f69f6  pop     r12
0x1800f69f8  pop     rdi
0x1800f69f9  pop     rsi
0x1800f69fa  pop     rbp
0x1800f69fb  retn
```
