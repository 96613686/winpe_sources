# LPA::EsimManager::GetEmbeddedSlotIndex(_GUID const &)

- ea: `0x18008abd0`
- end: `0x18008adbf`
- name: `?GetEmbeddedSlotIndex@EsimManager@LPA@@AEAAHAEBU_GUID@@@Z`
- size: `495`
- prototype: `__int64 __fastcall(LPA::EsimManager *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180093d90`
- `0x180095b20`

## callees

- `0x1800017c8`
- `0x18000199c`
- `0x18000e46c`
- `0x18008514c`
- `0x180085810`
- `0x18008593c`
- `0x18008aad4`
- `0x18008abd0`

## import_xrefs

- `wwapi!WwanQueryInterface` at `0x18008acdf`
- `wwapi!WwanQueryInterface` at `0x18008acdf`
- `wwapi!WwanFreeMemory` at `0x18008ad20`
- `wwapi!WwanFreeMemory` at `0x18008ad20`

## string_xrefs

- `0x18008ac2a`: `LpaServiceEsimManager`
- `0x18008ad55`: `LpaServiceEsimManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LPA::EsimManager::GetEmbeddedSlotIndex(LPA::EsimManager *this, const struct _GUID *a2)
{
  int v4; // edi
  const unsigned __int16 *v5; // rdx
  const unsigned __int16 *v6; // r8
  signed int DWORD; // eax
  int v8; // r9d
  signed int Interface; // ebx
  const char *v10; // rdx
  const char *v11; // r8
  const char *v12; // rcx
  unsigned int v13; // ebx
  const char *v15; // [rsp+50h] [rbp+7h] BYREF
  const char *v16; // [rsp+58h] [rbp+Fh] BYREF
  const char *v17; // [rsp+60h] [rbp+17h] BYREF
  const char *v18; // [rsp+68h] [rbp+1Fh] BYREF
  StateSeparation *v19; // [rsp+70h] [rbp+27h] BYREF
  _QWORD v20[2]; // [rsp+78h] [rbp+2Fh] BYREF
  char v21; // [rsp+88h] [rbp+3Fh]
  unsigned int v22; // [rsp+C0h] [rbp+77h] BYREF
  void *v23; // [rsp+C8h] [rbp+7Fh] BYREF

  v22 = 0;
  v4 = 0;
  v23 = operator new(0x20u);
  v19 = (StateSeparation *)StateSeparation::StateSeparation(v23, 1);
  DWORD = StateSeparation::GetDWORD(v19, v5, v6, &v22);
  Interface = DWORD;
  v10 = "LPA::EsimManager::GetEmbeddedSlotIndex";
  v11 = "LpaServiceEsimManager";
  if ( DWORD )
  {
    LODWORD(v12) = (_DWORD)CallbackContext;
    if ( (unsigned int)CallbackContext > 3 )
    {
      if ( DWORD > 0 )
        DWORD = (unsigned __int16)DWORD | 0x80070000;
      LODWORD(v23) = DWORD;
      v15 = "LPA::EsimManager::GetEmbeddedSlotIndex";
      v16 = "LpaServiceEsimManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)CallbackContext,
        (unsigned int)&unk_18012F5B8,
        (unsigned int)"LpaServiceEsimManager",
        v8,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v23);
    }
    v22 = 1;
    goto LABEL_15;
  }
  v15 = 0;
  LODWORD(v23) = 0;
  v20[0] = &v15;
  v20[1] = 0;
  v21 = 1;
  Interface = WwanQueryInterface(*((_QWORD *)this + 15), a2, 46);
  wil::details::out_param_ptr_t<unsigned char * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>::~out_param_ptr_t<unsigned char * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>(v20);
  v12 = v15;
  if ( !Interface )
  {
    if ( (unsigned int)v23 < 8 )
    {
      Interface = 13;
    }
    else
    {
      v4 = *(_DWORD *)v15;
      if ( v22 < *(_DWORD *)v15 )
        goto LABEL_13;
    }
  }
  v22 = 1;
LABEL_13:
  v15 = 0;
  if ( v12 )
    WwanFreeMemory(v12);
LABEL_15:
  if ( (unsigned int)CallbackContext > 4 )
  {
    LODWORD(v23) = v4;
    if ( Interface > 0 )
      Interface = (unsigned __int16)Interface | 0x80070000;
    LODWORD(v16) = Interface;
    LODWORD(v15) = v22;
    v17 = "LPA::EsimManager::GetEmbeddedSlotIndex";
    v18 = "LpaServiceEsimManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v12,
      (unsigned int)byte_18012F565,
      (_DWORD)v11,
      v8,
      (__int64)&v18,
      (__int64)&v17,
      (__int64)&v15,
      (__int64)&v16,
      (__int64)&v23);
  }
  v13 = v22;
  std::unique_ptr<StateSeparation>::~unique_ptr<StateSeparation>(&v19, v10, v11);
  return v13;
}

```

## disassembly

```asm
0x18008abd0  mov     [rsp-8+arg_0], rbx
0x18008abd5  mov     [rsp-8+arg_8], rsi
0x18008abda  push    rbp
0x18008abdb  push    rdi
0x18008abdc  push    r14
0x18008abde  lea     rbp, [rsp-47h]
0x18008abe3  sub     rsp, 90h
0x18008abea  mov     rsi, rdx
0x18008abed  mov     r14, rcx
0x18008abf0  mov     [rbp+57h+arg_10], 0
0x18008abf7  xor     edi, edi
0x18008abf9  lea     ecx, [rdi+20h]; Size
0x18008abfc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008ac01  mov     [rbp+57h+arg_18], rax
0x18008ac05  lea     edx, [rdi+1]
0x18008ac08  mov     rcx, rax
0x18008ac0b  call    ??0StateSeparation@@QEAA@W4_REG_ROOT_PATH@@@Z; StateSeparation::StateSeparation(_REG_ROOT_PATH)
0x18008ac10  nop
0x18008ac11  mov     [rbp+57h+var_30], rax
0x18008ac15  lea     r9, [rbp+57h+arg_10]; unsigned int *
0x18008ac19  mov     rcx, rax; this
0x18008ac1c  call    ?GetDWORD@StateSeparation@@QEAAKPEBG0PEAK@Z; StateSeparation::GetDWORD(ushort const *,ushort const *,ulong *)
0x18008ac21  mov     ebx, eax
0x18008ac23  lea     rdx, aLpaEsimmanager_56; "LPA::EsimManager::GetEmbeddedSlotIndex"
0x18008ac2a  lea     r8, aLpaserviceesim; "LpaServiceEsimManager"
0x18008ac31  test    eax, eax
0x18008ac33  jz      short loc_18008AC8A
0x18008ac35  mov     ecx, cs:CallbackContext
0x18008ac3b  cmp     ecx, 3
0x18008ac3e  jbe     short loc_18008AC7E
0x18008ac40  test    eax, eax
0x18008ac42  jle     short loc_18008AC4C
0x18008ac44  movzx   eax, ax
0x18008ac47  or      eax, 80070000h
0x18008ac4c  mov     dword ptr [rbp+57h+arg_18], eax
0x18008ac4f  mov     [rbp+57h+var_50], rdx
0x18008ac53  mov     [rbp+57h+var_48], r8
0x18008ac57  lea     rax, [rbp+57h+arg_18]
0x18008ac5b  mov     [rsp+0A0h+var_70], rax
0x18008ac60  lea     rax, [rbp+57h+var_50]
0x18008ac64  mov     [rsp+0A0h+var_78], rax
0x18008ac69  lea     rax, [rbp+57h+var_48]
0x18008ac6d  mov     [rsp+0A0h+var_80], rax
0x18008ac72  lea     rdx, unk_18012F5B8
0x18008ac79  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008ac7e  mov     [rbp+57h+arg_10], 1
0x18008ac85  jmp     loc_18008AD26
0x18008ac8a  mov     [rbp+57h+var_50], 0
0x18008ac92  mov     dword ptr [rbp+57h+arg_18], 0
0x18008ac99  lea     rax, [rbp+57h+var_50]
0x18008ac9d  mov     [rbp+57h+var_28], rax
0x18008aca1  mov     [rbp+57h+var_20], 0
0x18008aca9  mov     [rbp+57h+var_18], 1
0x18008acad  mov     [rsp+0A0h+var_68], 0
0x18008acb6  mov     [rsp+0A0h+var_70], 0
0x18008acbf  lea     rax, [rbp+57h+var_20]
0x18008acc3  mov     [rsp+0A0h+var_78], rax
0x18008acc8  lea     rax, [rbp+57h+arg_18]
0x18008accc  mov     [rsp+0A0h+var_80], rax
0x18008acd1  xor     r9d, r9d
0x18008acd4  lea     r8d, [r9+2Eh]
0x18008acd8  mov     rdx, rsi
0x18008acdb  mov     rcx, [r14+78h]
0x18008acdf  call    cs:__imp_WwanQueryInterface
0x18008ace5  mov     ebx, eax
0x18008ace7  lea     rcx, [rbp+57h+var_28]
0x18008aceb  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_ptr@U_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>::~out_param_ptr_t<uchar * *,wistd::unique_ptr<_WWAN_MULTI_SIM_SLOT_MAPPING_STATUS,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>(void)
0x18008acf0  mov     rcx, [rbp+57h+var_50]
0x18008acf4  test    ebx, ebx
0x18008acf6  jnz     short loc_18008AD0C
0x18008acf8  cmp     dword ptr [rbp+57h+arg_18], 8
0x18008acfc  jb      short loc_18008AD07
0x18008acfe  mov     edi, [rcx]
0x18008ad00  cmp     [rbp+57h+arg_10], edi
0x18008ad03  jb      short loc_18008AD13
0x18008ad05  jmp     short loc_18008AD0C
0x18008ad07  mov     ebx, 0Dh
0x18008ad0c  mov     [rbp+57h+arg_10], 1
0x18008ad13  mov     [rbp+57h+var_50], 0
0x18008ad1b  test    rcx, rcx
0x18008ad1e  jz      short loc_18008AD26
0x18008ad20  call    cs:__imp_WwanFreeMemory
0x18008ad26  mov     eax, cs:CallbackContext
0x18008ad2c  cmp     eax, 4
0x18008ad2f  jbe     short loc_18008AD99
0x18008ad31  mov     dword ptr [rbp+57h+arg_18], edi
0x18008ad34  test    ebx, ebx
0x18008ad36  jle     short loc_18008AD41
0x18008ad38  movzx   ebx, bx
0x18008ad3b  or      ebx, 80070000h
0x18008ad41  mov     dword ptr [rbp+57h+var_48], ebx
0x18008ad44  mov     eax, [rbp+57h+arg_10]
0x18008ad47  mov     dword ptr [rbp+57h+var_50], eax
0x18008ad4a  lea     rax, aLpaEsimmanager_56; "LPA::EsimManager::GetEmbeddedSlotIndex"
0x18008ad51  mov     [rbp+57h+var_40], rax
0x18008ad55  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x18008ad5c  mov     [rbp+57h+var_38], rax
0x18008ad60  lea     rax, [rbp+57h+arg_18]
0x18008ad64  mov     [rsp+0A0h+var_60], rax
0x18008ad69  lea     rax, [rbp+57h+var_48]
0x18008ad6d  mov     [rsp+0A0h+var_68], rax
0x18008ad72  lea     rax, [rbp+57h+var_50]
0x18008ad76  mov     [rsp+0A0h+var_70], rax
0x18008ad7b  lea     rax, [rbp+57h+var_40]
0x18008ad7f  mov     [rsp+0A0h+var_78], rax
0x18008ad84  lea     rax, [rbp+57h+var_38]
0x18008ad88  mov     [rsp+0A0h+var_80], rax
0x18008ad8d  lea     rdx, byte_18012F565
0x18008ad94  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18008ad99  mov     ebx, [rbp+57h+arg_10]
0x18008ad9c  lea     rcx, [rbp+57h+var_30]
0x18008ada0  call    ??1?$unique_ptr@VStateSeparation@@U?$default_delete@VStateSeparation@@@std@@@std@@QEAA@XZ; std::unique_ptr<StateSeparation>::~unique_ptr<StateSeparation>(void)
0x18008ada5  mov     eax, ebx
0x18008ada7  lea     r11, [rsp+0A0h+var_10]
0x18008adaf  mov     rbx, [r11+20h]
0x18008adb3  mov     rsi, [r11+28h]
0x18008adb7  mov     rsp, r11
0x18008adba  pop     r14
0x18008adbc  pop     rdi
0x18008adbd  pop     rbp
0x18008adbe  retn
```
