# WwanController::LoadOperatorProfileSelection(__MIDL___MIDL_itf_mvcellularv2_0000_0000_0004 const *,ulong *,uchar * *)

- ea: `0x18000c078`
- end: `0x18000c264`
- name: `?LoadOperatorProfileSelection@WwanController@@QEAAJPEBU__MIDL___MIDL_itf_mvcellularv2_0000_0000_0004@@PEAKPEAPEAE@Z`
- size: `492`
- prototype: `__int64 __fastcall(WwanController *__hidden this, const struct __MIDL___MIDL_itf_mvcellularv2_0000_0000_0004 *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009190`

## callees

- `0x1800011bc`
- `0x180001264`
- `0x18000c078`
- `0x18003b9a0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000c19d`
- `msvcrt!memcpy_s` at `0x18000c19d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c13c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c13c`
- `wwapi!WwanFreeMemory` at `0x18000c1e6`
- `wwapi!WwanFreeMemory` at `0x18000c1e6`
- `wwapi!WwanQueryInterfaceEx` at `0x18000c11a`
- `wwapi!WwanQueryInterfaceEx` at `0x18000c11a`

## pseudocode

```c
__int64 __fastcall WwanController::LoadOperatorProfileSelection(
        WwanController *this,
        const struct __MIDL___MIDL_itf_mvcellularv2_0000_0000_0004 *a2,
        unsigned int *a3,
        unsigned __int8 **a4)
{
  __int64 v7; // rcx
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  signed int Interface; // eax
  __int64 v11; // rcx
  signed int *v12; // rbx
  unsigned __int8 *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int *v20; // rdx
  const char *v22; // [rsp+40h] [rbp-39h] BYREF
  const char *v23; // [rsp+48h] [rbp-31h] BYREF
  int v24; // [rsp+50h] [rbp-29h]
  void *Source; // [rsp+58h] [rbp-21h]
  _OWORD v26[4]; // [rsp+60h] [rbp-19h] BYREF

  if ( !a2 || !a3 || !a4 )
  {
    v12 = (signed int *)((char *)this + 56);
    *((_DWORD *)this + 14) = -2147024809;
    if ( (unsigned int)dword_180052170 <= 2 )
      return (unsigned int)*v12;
    v11 = (unsigned int)*v12;
    v20 = (int *)byte_1800481AB;
    LODWORD(v22) = *v12;
    goto LABEL_17;
  }
  v7 = *((_QWORD *)this + 9);
  v8 = *((_OWORD *)a2 + 1);
  v26[1] = *(_OWORD *)a2;
  v24 = 0;
  v9 = *((_OWORD *)a2 + 2);
  Source = 0;
  v26[2] = v8;
  v26[3] = v9;
  v26[0] = 0;
  Interface = WwanQueryInterfaceEx(v7, v26, 38);
  if ( Interface > 0 )
    Interface = (unsigned __int16)Interface | 0x80070000;
  v12 = (signed int *)((char *)this + 56);
  *v12 = Interface;
  if ( Interface < 0 )
  {
    if ( (unsigned int)dword_180052170 <= 2 )
      return (unsigned int)*v12;
    v20 = &dword_180049394;
    LODWORD(v22) = *v12;
LABEL_17:
    v23 = "WwanController::LoadOperatorProfileSelection";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v11,
      (__int64)v20,
      (__int64)a3,
      (__int64)a4,
      (const unsigned __int16 **)&v23,
      (__int64)&v22);
    return (unsigned int)*v12;
  }
  v13 = (unsigned __int8 *)CoTaskMemAlloc(*a3);
  *a4 = v13;
  if ( v13 )
  {
    memcpy_s(v13, *a3, Source, *a3);
    if ( (unsigned int)dword_180052170 > 5 )
    {
      v23 = "WwanController::LoadOperatorProfileSelection";
      v22 = "Operator profile loaded";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v17,
        (__int64)&byte_1800486AF,
        v18,
        v19,
        (const unsigned __int16 **)&v22,
        (const unsigned __int16 **)&v23);
    }
  }
  else
  {
    *a3 = 0;
    *v12 = -2147024882;
    if ( (unsigned int)dword_180052170 > 2 )
    {
      LODWORD(v22) = *v12;
      v23 = "WwanController::LoadOperatorProfileSelection";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v14,
        (__int64)byte_180047E95,
        v15,
        v16,
        (const unsigned __int16 **)&v23,
        (__int64)&v22);
    }
  }
  WwanFreeMemory(Source);
  return (unsigned int)*v12;
}

```

## disassembly

```asm
0x18000c078  push    rbp
0x18000c07a  push    rbx
0x18000c07b  push    rsi
0x18000c07c  push    rdi
0x18000c07d  lea     rbp, [rsp-3Fh]
0x18000c082  sub     rsp, 0B8h
0x18000c089  mov     rax, cs:__security_cookie
0x18000c090  xor     rax, rsp
0x18000c093  mov     [rbp+57h+var_30], rax
0x18000c097  mov     rsi, r9
0x18000c09a  mov     rdi, r8
0x18000c09d  mov     rbx, rcx
0x18000c0a0  test    rdx, rdx
0x18000c0a3  jz      loc_18000C207
0x18000c0a9  test    r8, r8
0x18000c0ac  jz      loc_18000C207
0x18000c0b2  test    r9, r9
0x18000c0b5  jz      loc_18000C207
0x18000c0bb  movups  xmm0, xmmword ptr [rdx]
0x18000c0be  mov     rcx, [rcx+48h]
0x18000c0c2  lea     rax, [rbp+57h+Source]
0x18000c0c6  movups  xmm1, xmmword ptr [rdx+10h]
0x18000c0ca  mov     [rsp+0D0h+var_98], rax
0x18000c0cf  mov     r9d, 30h ; '0'
0x18000c0d5  mov     [rsp+0D0h+var_A0], r8
0x18000c0da  lea     rax, [rbp+57h+var_80]
0x18000c0de  mov     [rsp+0D0h+var_A8], rax
0x18000c0e3  lea     rax, [rbp+57h+var_60]
0x18000c0e7  movups  [rbp+57h+var_60], xmm0
0x18000c0eb  lea     r8d, [r9-0Ah]
0x18000c0ef  mov     [rbp+57h+var_80], 0
0x18000c0f6  movups  xmm0, xmmword ptr [rdx+20h]
0x18000c0fa  lea     rdx, [rbp+57h+var_70]
0x18000c0fe  mov     [rbp+57h+Source], 0
0x18000c106  movups  [rbp+57h+var_50], xmm1
0x18000c10a  mov     [rsp+0D0h+var_B0], rax
0x18000c10f  xorps   xmm1, xmm1
0x18000c112  movups  [rbp+57h+var_40], xmm0
0x18000c116  movups  [rbp+57h+var_70], xmm1
0x18000c11a  call    cs:__imp_WwanQueryInterfaceEx
0x18000c120  test    eax, eax
0x18000c122  jle     short loc_18000C12C
0x18000c124  movzx   eax, ax
0x18000c127  or      eax, 80070000h
0x18000c12c  add     rbx, 38h ; '8'
0x18000c130  mov     [rbx], eax
0x18000c132  test    eax, eax
0x18000c134  js      loc_18000C1EE
0x18000c13a  mov     ecx, [rdi]; cb
0x18000c13c  call    cs:__imp_CoTaskMemAlloc
0x18000c142  mov     [rsi], rax
0x18000c145  test    rax, rax
0x18000c148  jnz     short loc_18000C191
0x18000c14a  mov     [rdi], eax
0x18000c14c  mov     dword ptr [rbx], 8007000Eh
0x18000c152  mov     eax, cs:dword_180052170
0x18000c158  cmp     eax, 2
0x18000c15b  jbe     loc_18000C1E2
0x18000c161  mov     eax, [rbx]
0x18000c163  lea     rdx, byte_180047E95
0x18000c16a  mov     dword ptr [rbp+57h+var_90], eax
0x18000c16d  lea     rax, aWwancontroller; "WwanController::LoadOperatorProfileSele"...
0x18000c174  mov     [rbp+57h+var_88], rax
0x18000c178  lea     rax, [rbp+57h+var_90]
0x18000c17c  mov     [rsp+0D0h+var_A8], rax
0x18000c181  lea     rax, [rbp+57h+var_88]
0x18000c185  mov     [rsp+0D0h+var_B0], rax
0x18000c18a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000c18f  jmp     short loc_18000C1E2
0x18000c191  mov     edx, [rdi]; DestinationSize
0x18000c193  mov     rcx, rax; Destination
0x18000c196  mov     r8, [rbp+57h+Source]; Source
0x18000c19a  mov     r9d, edx; SourceSize
0x18000c19d  call    cs:__imp_memcpy_s
0x18000c1a3  mov     eax, cs:dword_180052170
0x18000c1a9  cmp     eax, 5
0x18000c1ac  jbe     short loc_18000C1E2
0x18000c1ae  lea     rax, aWwancontroller; "WwanController::LoadOperatorProfileSele"...
0x18000c1b5  mov     [rbp+57h+var_88], rax
0x18000c1b9  lea     rdx, byte_1800486AF
0x18000c1c0  lea     rax, aOperatorProfil_1; "Operator profile loaded"
0x18000c1c7  mov     [rbp+57h+var_90], rax
0x18000c1cb  lea     rax, [rbp+57h+var_88]
0x18000c1cf  mov     [rsp+0D0h+var_A8], rax
0x18000c1d4  lea     rax, [rbp+57h+var_90]
0x18000c1d8  mov     [rsp+0D0h+var_B0], rax
0x18000c1dd  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000c1e2  mov     rcx, [rbp+57h+Source]
0x18000c1e6  call    cs:__imp_WwanFreeMemory
0x18000c1ec  jmp     short loc_18000C24A
0x18000c1ee  mov     eax, cs:dword_180052170
0x18000c1f4  cmp     eax, 2
0x18000c1f7  jbe     short loc_18000C24A
0x18000c1f9  mov     eax, [rbx]
0x18000c1fb  lea     rdx, dword_180049394
0x18000c202  mov     dword ptr [rbp+57h+var_90], eax
0x18000c205  jmp     short loc_18000C228
0x18000c207  add     rbx, 38h ; '8'
0x18000c20b  mov     dword ptr [rbx], 80070057h
0x18000c211  mov     eax, cs:dword_180052170
0x18000c217  cmp     eax, 2
0x18000c21a  jbe     short loc_18000C24A
0x18000c21c  mov     ecx, [rbx]
0x18000c21e  lea     rdx, byte_1800481AB
0x18000c225  mov     dword ptr [rbp+57h+var_90], ecx
0x18000c228  lea     rax, aWwancontroller; "WwanController::LoadOperatorProfileSele"...
0x18000c22f  mov     [rbp+57h+var_88], rax
0x18000c233  lea     rax, [rbp+57h+var_90]
0x18000c237  mov     [rsp+0D0h+var_A8], rax
0x18000c23c  lea     rax, [rbp+57h+var_88]
0x18000c240  mov     [rsp+0D0h+var_B0], rax
0x18000c245  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000c24a  mov     eax, [rbx]
0x18000c24c  mov     rcx, [rbp+57h+var_30]
0x18000c250  xor     rcx, rsp; StackCookie
0x18000c253  call    __security_check_cookie
0x18000c258  add     rsp, 0B8h
0x18000c25f  pop     rdi
0x18000c260  pop     rsi
0x18000c261  pop     rbx
0x18000c262  pop     rbp
0x18000c263  retn
```
