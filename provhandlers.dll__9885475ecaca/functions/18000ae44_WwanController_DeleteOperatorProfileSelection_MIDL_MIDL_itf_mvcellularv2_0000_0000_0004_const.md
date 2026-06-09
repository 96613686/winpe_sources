# WwanController::DeleteOperatorProfileSelection(__MIDL___MIDL_itf_mvcellularv2_0000_0000_0004 const *)

- ea: `0x18000ae44`
- end: `0x18000affc`
- name: `?DeleteOperatorProfileSelection@WwanController@@QEAAJPEBU__MIDL___MIDL_itf_mvcellularv2_0000_0000_0004@@@Z`
- size: `440`
- prototype: `__int64 __fastcall(WwanController *this, const struct __MIDL___MIDL_itf_mvcellularv2_0000_0000_0004 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009030`

## callees

- `0x1800011bc`
- `0x180001264`
- `0x180001700`
- `0x18000ae44`
- `0x18003b9a0`

## import_xrefs

- `wwapi!WwanSetInterface` at `0x18000aeea`
- `wwapi!WwanSetInterface` at `0x18000aeea`

## string_xrefs

- `0x18000ae8f`: `WwanController::DeleteOperatorProfileSelection`
- `0x18000af21`: `WwanController::DeleteOperatorProfileSelection`
- `0x18000af6b`: `WwanController::DeleteOperatorProfileSelection`
- `0x18000afa9`: `WwanController::DeleteOperatorProfileSelection`
- `0x18000afbb`: `Operator profile deleted`

## pseudocode

```c
__int64 __fastcall WwanController::DeleteOperatorProfileSelection(
        WwanController *this,
        const struct __MIDL___MIDL_itf_mvcellularv2_0000_0000_0004 *a2,
        __int64 a3,
        __int64 a4)
{
  signed int *v5; // rbx
  __int16 *v6; // rdx
  signed int *v7; // rax
  __int64 v8; // rcx
  signed int v9; // eax
  signed int v11; // [rsp+40h] [rbp-40h] BYREF
  signed int v12; // [rsp+44h] [rbp-3Ch] BYREF
  const char *v13; // [rsp+48h] [rbp-38h] BYREF
  int v14; // [rsp+50h] [rbp-30h]
  const char *v15; // [rsp+58h] [rbp-28h] BYREF
  __int128 v16; // [rsp+60h] [rbp-20h] BYREF

  if ( a2 )
  {
    v8 = *((_QWORD *)this + 9);
    v14 = 0;
    v11 = 0;
    v16 = 0;
    v9 = WwanSetInterface(v8, &v16, 38);
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    v5 = (signed int *)((char *)this + 56);
    *v5 = v9;
    if ( v9 >= 0 )
    {
      if ( v11 )
      {
        *v5 = -2147467259;
        if ( (unsigned int)dword_180052170 > 2 )
        {
          v12 = *v5;
          v15 = "WwanController::DeleteOperatorProfileSelection";
          LODWORD(v13) = v11;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (__int64)this,
            (__int64)byte_1800487D1,
            a3,
            a4,
            (__int64)&v13,
            (const unsigned __int16 **)&v15,
            (__int64)&v12);
        }
      }
      else if ( (unsigned int)dword_180052170 > 5 )
      {
        v15 = "WwanController::DeleteOperatorProfileSelection";
        v13 = "Operator profile deleted";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (__int64)this,
          (__int64)&unk_180048E30,
          a3,
          a4,
          (const unsigned __int16 **)&v13,
          (const unsigned __int16 **)&v15);
      }
    }
    else if ( (unsigned int)dword_180052170 > 2 )
    {
      v6 = (__int16 *)byte_180047D25;
      v12 = *v5;
      v13 = "WwanController::DeleteOperatorProfileSelection";
      v7 = &v12;
      goto LABEL_9;
    }
  }
  else
  {
    v5 = (signed int *)((char *)this + 56);
    *((_DWORD *)this + 14) = -2147024809;
    if ( (unsigned int)dword_180052170 > 2 )
    {
      v6 = word_180048B6A;
      v11 = *v5;
      v13 = "WwanController::DeleteOperatorProfileSelection";
      v7 = &v11;
LABEL_9:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (__int64)this,
        (__int64)v6,
        a3,
        a4,
        (const unsigned __int16 **)&v13,
        (__int64)v7);
    }
  }
  return (unsigned int)*v5;
}

```

## disassembly

```asm
0x18000ae44  mov     [rsp-8+arg_10], rbx
0x18000ae49  push    rbp
0x18000ae4a  mov     rbp, rsp
0x18000ae4d  sub     rsp, 80h
0x18000ae54  mov     rax, cs:__security_cookie
0x18000ae5b  xor     rax, rsp
0x18000ae5e  mov     [rbp+var_10], rax
0x18000ae62  mov     rbx, rcx
0x18000ae65  test    rdx, rdx
0x18000ae68  jnz     short loc_18000AEA3
0x18000ae6a  add     rbx, 38h ; '8'
0x18000ae6e  mov     dword ptr [rbx], 80070057h
0x18000ae74  mov     eax, cs:dword_180052170
0x18000ae7a  cmp     eax, 2
0x18000ae7d  jbe     loc_18000AFDD
0x18000ae83  mov     eax, [rbx]
0x18000ae85  lea     rdx, word_180048B6A
0x18000ae8c  mov     [rbp+var_40], eax
0x18000ae8f  lea     rax, aWwancontroller_13; "WwanController::DeleteOperatorProfileSe"...
0x18000ae96  mov     [rbp+var_38], rax
0x18000ae9a  lea     rax, [rbp+var_40]
0x18000ae9e  jmp     loc_18000AF30
0x18000aea3  mov     rcx, [rcx+48h]
0x18000aea7  lea     rax, [rbp+var_40]
0x18000aeab  mov     [rsp+80h+var_48], 0
0x18000aeb4  mov     r9d, 30h ; '0'
0x18000aeba  mov     [rsp+80h+var_50], rax
0x18000aebf  xorps   xmm0, xmm0
0x18000aec2  lea     rax, [rbp+var_30]
0x18000aec6  mov     [rbp+var_30], 0
0x18000aecd  mov     [rsp+80h+var_58], rax
0x18000aed2  mov     [rsp+80h+var_60], rdx
0x18000aed7  lea     r8d, [r9-0Ah]
0x18000aedb  lea     rdx, [rbp+var_20]
0x18000aedf  mov     [rbp+var_40], 0
0x18000aee6  movups  [rbp+var_20], xmm0
0x18000aeea  call    cs:__imp_WwanSetInterface
0x18000aef0  test    eax, eax
0x18000aef2  jle     short loc_18000AEFC
0x18000aef4  movzx   eax, ax
0x18000aef7  or      eax, 80070000h
0x18000aefc  add     rbx, 38h ; '8'
0x18000af00  mov     [rbx], eax
0x18000af02  test    eax, eax
0x18000af04  jns     short loc_18000AF48
0x18000af06  mov     eax, cs:dword_180052170
0x18000af0c  cmp     eax, 2
0x18000af0f  jbe     loc_18000AFDD
0x18000af15  mov     eax, [rbx]
0x18000af17  lea     rdx, byte_180047D25
0x18000af1e  mov     [rbp+var_3C], eax
0x18000af21  lea     rax, aWwancontroller_13; "WwanController::DeleteOperatorProfileSe"...
0x18000af28  mov     [rbp+var_38], rax
0x18000af2c  lea     rax, [rbp+var_3C]
0x18000af30  mov     [rsp+80h+var_58], rax
0x18000af35  lea     rax, [rbp+var_38]
0x18000af39  mov     [rsp+80h+var_60], rax
0x18000af3e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000af43  jmp     loc_18000AFDD
0x18000af48  cmp     [rbp+var_40], 0
0x18000af4c  jz      short loc_18000AF9E
0x18000af4e  mov     dword ptr [rbx], 80004005h
0x18000af54  mov     eax, cs:dword_180052170
0x18000af5a  cmp     eax, 2
0x18000af5d  jbe     short loc_18000AFDD
0x18000af5f  mov     eax, [rbx]
0x18000af61  lea     rdx, byte_1800487D1
0x18000af68  mov     [rbp+var_3C], eax
0x18000af6b  lea     rax, aWwancontroller_13; "WwanController::DeleteOperatorProfileSe"...
0x18000af72  mov     [rbp+var_28], rax
0x18000af76  mov     eax, [rbp+var_40]
0x18000af79  mov     dword ptr [rbp+var_38], eax
0x18000af7c  lea     rax, [rbp+var_3C]
0x18000af80  mov     [rsp+80h+var_50], rax
0x18000af85  lea     rax, [rbp+var_28]
0x18000af89  mov     [rsp+80h+var_58], rax
0x18000af8e  lea     rax, [rbp+var_38]
0x18000af92  mov     [rsp+80h+var_60], rax
0x18000af97  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000af9c  jmp     short loc_18000AFDD
0x18000af9e  mov     eax, cs:dword_180052170
0x18000afa4  cmp     eax, 5
0x18000afa7  jbe     short loc_18000AFDD
0x18000afa9  lea     rax, aWwancontroller_13; "WwanController::DeleteOperatorProfileSe"...
0x18000afb0  mov     [rbp+var_28], rax
0x18000afb4  lea     rdx, unk_180048E30
0x18000afbb  lea     rax, aOperatorProfil; "Operator profile deleted"
0x18000afc2  mov     [rbp+var_38], rax
0x18000afc6  lea     rax, [rbp+var_28]
0x18000afca  mov     [rsp+80h+var_58], rax
0x18000afcf  lea     rax, [rbp+var_38]
0x18000afd3  mov     [rsp+80h+var_60], rax
0x18000afd8  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000afdd  mov     eax, [rbx]
0x18000afdf  mov     rcx, [rbp+var_10]
0x18000afe3  xor     rcx, rsp; StackCookie
0x18000afe6  call    __security_check_cookie
0x18000afeb  mov     rbx, [rsp+80h+arg_10]
0x18000aff3  add     rsp, 80h
0x18000affa  pop     rbp
0x18000affb  retn
```
