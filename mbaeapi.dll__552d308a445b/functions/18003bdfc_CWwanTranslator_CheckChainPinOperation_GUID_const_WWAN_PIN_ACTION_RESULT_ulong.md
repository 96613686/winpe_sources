# CWwanTranslator::_CheckChainPinOperation(_GUID const &,_WWAN_PIN_ACTION_RESULT &,ulong)

- ea: `0x18003bdfc`
- end: `0x18003c7cd`
- name: `?_CheckChainPinOperation@CWwanTranslator@@AEAA_NAEBU_GUID@@AEAU_WWAN_PIN_ACTION_RESULT@@K@Z`
- size: `2513`
- prototype: `char __fastcall(struct _RTL_CRITICAL_SECTION *this, const struct _GUID *, struct _WWAN_PIN_ACTION_RESULT *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003812c`

## callees

- `0x18000178c`
- `0x1800024e0`
- `0x180002efc`
- `0x1800040cd`
- `0x180009ffc`
- `0x18001105c`
- `0x180016bc0`
- `0x1800172bc`
- `0x18001dd10`
- `0x18003bdfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c531`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c6d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c531`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003c6d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bf13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c678`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003bf13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003c678`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003c6e3`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanCloseHandle` at `0x18003c6e3`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18003c557`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x18003c557`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x18003c5a1`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanSetInterface` at `0x18003c5a1`

## pseudocode

```c
char __fastcall CWwanTranslator::_CheckChainPinOperation(
        struct _RTL_CRITICAL_SECTION *this,
        const struct _GUID *a2,
        struct _WWAN_PIN_ACTION_RESULT *a3,
        int a4)
{
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  char v11; // r12
  struct _RTL_CRITICAL_SECTION *v12; // rbx
  HANDLE *p_OwningThread; // r13
  _BYTE *v14; // rdi
  __int128 *v15; // rdi
  const struct _tlgProvider_t *v16; // rax
  __int64 v17; // r8
  __int64 v18; // r9
  __int128 *v19; // rcx
  const struct _tlgProvider_t *v20; // rax
  __int64 v21; // r8
  __int64 v22; // r9
  const struct _tlgProvider_t *v23; // rax
  __int64 v24; // r8
  __int64 v25; // r9
  int v26; // eax
  const struct _tlgProvider_t *v27; // rax
  __int64 v28; // r8
  __int64 v29; // r9
  const struct _tlgProvider_t *v30; // rax
  __int64 v31; // r8
  __int64 v32; // r9
  const struct _tlgProvider_t *v33; // rax
  __int64 v34; // r8
  __int64 v35; // r9
  int v36; // eax
  const struct _tlgProvider_t *v37; // rax
  __int64 v38; // r8
  __int64 v39; // r9
  _BYTE *v40; // rdi
  const struct _tlgProvider_t *v41; // rax
  __int64 v42; // r8
  __int64 v43; // r9
  __int128 *v45; // [rsp+20h] [rbp-E0h]
  __int64 v46; // [rsp+20h] [rbp-E0h]
  __int64 v47; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v48; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v49[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v50; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v51[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v52; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v53[2]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE *v54; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v55; // [rsp+90h] [rbp-70h] BYREF
  int v56; // [rsp+98h] [rbp-68h] BYREF
  __int128 v57; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v58; // [rsp+B0h] [rbp-50h]
  __int128 v59; // [rsp+C0h] [rbp-40h]
  __int128 v60; // [rsp+D0h] [rbp-30h]
  __int128 v61; // [rsp+E0h] [rbp-20h]

  *(_OWORD *)v49 = 0;
  v50 = 0;
  *(_OWORD *)v51 = 0;
  v52 = 0;
  std::vector<unsigned short>::resize(v49);
  std::vector<unsigned short>::resize(v51);
  StringCchPrintfW(v49[0], v49[1] - v49[0], L"Enter");
  StringCchPrintfW(v51[0], v51[1] - v51[0], L"%S(%d):%s", "CWwanTranslator::_CheckChainPinOperation", 1459, v49[0]);
  v8 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v8 > 5u )
  {
    v48 = v51[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v8,
      (__int64)&word_1800770EE,
      v9,
      v10,
      (const unsigned __int16 **)&v48);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v51);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v49);
  v11 = 0;
  memset_0(&v57, 0, 0x50u);
  v12 = this + 1;
  EnterCriticalSection(this + 1);
  v55 = (unsigned __int16 *)&this[1];
  p_OwningThread = &this->OwningThread;
  std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>::_Find_lower_bound<_GUID>(
    (__int64)&this->OwningThread,
    v53,
    a2);
  v14 = v54;
  if ( !v54[25] && memcmp_0(a2, v54 + 32, 0x10u) >= 0 && v14 != *p_OwningThread )
  {
    if ( v14[152] )
    {
      if ( *((_DWORD *)a3 + 2) )
      {
        *(_OWORD *)v51 = 0;
        v52 = 0;
        *(_OWORD *)v49 = 0;
        v50 = 0;
        std::vector<unsigned short>::resize(v51);
        std::vector<unsigned short>::resize(v49);
        LODWORD(v47) = a4;
        LODWORD(v45) = *((_DWORD *)a3 + 3);
        StringCchPrintfW(
          v51[0],
          v51[1] - v51[0],
          L"Chain pin action finishes with action [%d], pintype [%d], result [%d].",
          *((unsigned int *)a3 + 2),
          v45,
          v47);
        LODWORD(v46) = 1527;
        StringCchPrintfW(v49[0], v49[1] - v49[0], L"%S(%d):%s", "CWwanTranslator::_CheckChainPinOperation", v46, v51[0]);
        v30 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v30 > 4u )
        {
          v48 = v49[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v30,
            (__int64)&dword_18007702C,
            v31,
            v32,
            (const unsigned __int16 **)&v48);
        }
      }
      else if ( a4 )
      {
        *(_OWORD *)v51 = 0;
        v52 = 0;
        *(_OWORD *)v49 = 0;
        v50 = 0;
        std::vector<unsigned short>::resize(v51);
        std::vector<unsigned short>::resize(v49);
        StringCchPrintfW(v51[0], v51[1] - v51[0], L"Intermediate EnterPin operation failed.");
        LODWORD(v45) = 1502;
        StringCchPrintfW(v49[0], v49[1] - v49[0], L"%S(%d):%s", "CWwanTranslator::_CheckChainPinOperation", v45, v51[0]);
        v23 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v23 > 4u )
        {
          v48 = v49[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v23,
            (__int64)&dword_18007706C,
            v24,
            v25,
            (const unsigned __int16 **)&v48);
        }
        std::vector<unsigned short>::~vector<unsigned short>((char **)v49);
        std::vector<unsigned short>::~vector<unsigned short>((char **)v51);
        v26 = *((_DWORD *)v14 + 40);
        if ( v26 )
        {
          *((_DWORD *)a3 + 2) = v26;
LABEL_26:
          v14[152] = 0;
          v19 = (__int128 *)(v14 + 156);
LABEL_27:
          memset_0(v19, 0, 0x50u);
          goto LABEL_34;
        }
        *(_OWORD *)v51 = 0;
        v52 = 0;
        *(_OWORD *)v49 = 0;
        v50 = 0;
        std::vector<unsigned short>::resize(v51);
        std::vector<unsigned short>::resize(v49);
        StringCchPrintfW(
          v51[0],
          v51[1] - v51[0],
          L"After a failed EnterPin, the original PIN action information is lost.");
        LODWORD(v45) = 1513;
        StringCchPrintfW(v49[0], v49[1] - v49[0], L"%S(%d):%s", "CWwanTranslator::_CheckChainPinOperation", v45, v51[0]);
        v27 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v27 > 2u )
        {
          v48 = v49[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v27,
            (__int64)&dword_18007708C,
            v28,
            v29,
            (const unsigned __int16 **)&v48);
        }
      }
      else
      {
        v52 = 0;
        if ( *((_DWORD *)v14 + 40) )
        {
          v11 = 1;
          v15 = (__int128 *)(v14 + 156);
          v57 = *v15;
          v58 = v15[1];
          v59 = v15[2];
          v60 = v15[3];
          v61 = v15[4];
          *(_OWORD *)v51 = 0;
          *(_OWORD *)v49 = 0;
          v50 = 0;
          std::vector<unsigned short>::resize(v51);
          std::vector<unsigned short>::resize(v49);
          StringCchPrintfW(v51[0], v51[1] - v51[0], L"Re-initiate pin action [%d].", DWORD1(v57));
          LODWORD(v45) = 1486;
          StringCchPrintfW(
            v49[0],
            v49[1] - v49[0],
            L"%S(%d):%s",
            "CWwanTranslator::_CheckChainPinOperation",
            v45,
            v51[0]);
          v16 = MbaeApiLogging::Provider();
          if ( *(_DWORD *)v16 > 4u )
          {
            v48 = v49[0];
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
              (__int64)v16,
              (__int64)byte_1800770AD,
              v17,
              v18,
              (const unsigned __int16 **)&v48);
          }
          std::vector<unsigned short>::~vector<unsigned short>((char **)v49);
          std::vector<unsigned short>::~vector<unsigned short>((char **)v51);
          v19 = v15;
          goto LABEL_27;
        }
        *(_OWORD *)v51 = 0;
        *(_OWORD *)v49 = 0;
        v50 = 0;
        std::vector<unsigned short>::resize(v51);
        std::vector<unsigned short>::resize(v49);
        StringCchPrintfW(
          v51[0],
          v51[1] - v51[0],
          L"After a successful EnterPin, the original PIN action information is lost.");
        LODWORD(v45) = 1493;
        StringCchPrintfW(v49[0], v49[1] - v49[0], L"%S(%d):%s", "CWwanTranslator::_CheckChainPinOperation", v45, v51[0]);
        v20 = MbaeApiLogging::Provider();
        if ( *(_DWORD *)v20 > 2u )
        {
          v48 = v49[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (__int64)v20,
            (__int64)byte_1800770CD,
            v21,
            v22,
            (const unsigned __int16 **)&v48);
        }
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v49);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v51);
      goto LABEL_26;
    }
    if ( a4 == -1073479674 && (unsigned int)(*((_DWORD *)a3 + 2) - 2) <= 1 )
    {
      *(_OWORD *)v51 = 0;
      v52 = 0;
      *(_OWORD *)v49 = 0;
      v50 = 0;
      std::vector<unsigned short>::resize(v51);
      std::vector<unsigned short>::resize(v49);
      StringCchPrintfW(
        v51[0],
        v51[1] - v51[0],
        L"Got WWAN_STATUS_PIN_REQUIRED and chain pin action mode activated for action [%d].",
        *((unsigned int *)a3 + 2));
      LODWORD(v45) = 1542;
      StringCchPrintfW(v49[0], v49[1] - v49[0], L"%S(%d):%s", "CWwanTranslator::_CheckChainPinOperation", v45, v51[0]);
      v33 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v33 > 4u )
      {
        v48 = v49[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v33,
          (__int64)&dword_18007704C,
          v34,
          v35,
          (const unsigned __int16 **)&v48);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v49);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v51);
      v14[152] = 1;
      v11 = 1;
      v57 = *(_OWORD *)(v14 + 156);
      v58 = *(_OWORD *)(v14 + 172);
      v59 = *(_OWORD *)(v14 + 188);
      v60 = *(_OWORD *)(v14 + 204);
      v61 = *(_OWORD *)(v14 + 220);
      DWORD1(v57) = 0;
      WORD5(v59) = 0;
    }
    else
    {
      memset_0(v14 + 156, 0, 0x50u);
    }
  }
LABEL_34:
  if ( v12 )
    LeaveCriticalSection(v12);
  if ( v11 )
  {
    v48 = 0;
    v56 = 0;
    v36 = WwanOpenHandle(1, 0, &v56, &v48);
    v51[0] = (unsigned __int16 *)&v48;
    LOBYTE(v51[1]) = 1;
    if ( v36 < 0 || (LODWORD(v55) = 0, v45 = &v57, (int)WwanSetInterface(v48, a2, 0, 80) < 0) )
    {
      v11 = 0;
      *(_OWORD *)v53 = 0;
      v54 = 0;
      *(_OWORD *)v49 = 0;
      v50 = 0;
      std::vector<unsigned short>::resize(v53);
      std::vector<unsigned short>::resize(v49);
      StringCchPrintfW(
        v53[0],
        v53[1] - v53[0],
        L"WwanSetInterface failed in a chain pin action [%d]. Clear the chain action mode.",
        DWORD1(v57));
      LODWORD(v45) = 1582;
      StringCchPrintfW(v49[0], v49[1] - v49[0], L"%S(%d):%s", "CWwanTranslator::_CheckChainPinOperation", v45, v53[0]);
      v37 = MbaeApiLogging::Provider();
      if ( *(_DWORD *)v37 > 2u )
      {
        v55 = v49[0];
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (__int64)v37,
          (__int64)qword_180076FE8,
          v38,
          v39,
          (const unsigned __int16 **)&v55);
      }
      std::vector<unsigned short>::~vector<unsigned short>((char **)v49);
      std::vector<unsigned short>::~vector<unsigned short>((char **)v53);
      EnterCriticalSection(v12);
      std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>::_Find_lower_bound<_GUID>(
        (__int64)p_OwningThread,
        v53,
        a2);
      v40 = v54;
      if ( !v54[25] && memcmp_0(a2, v54 + 32, 0x10u) >= 0 && v40 != *p_OwningThread )
      {
        v40[152] = 0;
        memset_0(v40 + 156, 0, 0x50u);
      }
      if ( v12 )
        LeaveCriticalSection(v12);
    }
    WwanCloseHandle(v48, 0);
  }
  *(_OWORD *)v49 = 0;
  v50 = 0;
  *(_OWORD *)v53 = 0;
  v54 = 0;
  std::vector<unsigned short>::resize(v49);
  std::vector<unsigned short>::resize(v53);
  StringCchPrintfW(v49[0], v49[1] - v49[0], L"Exit");
  LODWORD(v45) = 1594;
  StringCchPrintfW(v53[0], v53[1] - v53[0], L"%S(%d):%s", "CWwanTranslator::_CheckChainPinOperation", v45, v49[0]);
  v41 = MbaeApiLogging::Provider();
  if ( *(_DWORD *)v41 > 5u )
  {
    v48 = v53[0];
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (__int64)v41,
      (__int64)byte_180077009,
      v42,
      v43,
      (const unsigned __int16 **)&v48);
  }
  std::vector<unsigned short>::~vector<unsigned short>((char **)v53);
  std::vector<unsigned short>::~vector<unsigned short>((char **)v49);
  return v11;
}

```

## disassembly

```asm
0x18003bdfc  push    rbp
0x18003bdfe  push    rbx
0x18003bdff  push    rsi
0x18003be00  push    rdi
0x18003be01  push    r12
0x18003be03  push    r13
0x18003be05  push    r14
0x18003be07  push    r15
0x18003be09  lea     rbp, [rsp-8]
0x18003be0e  sub     rsp, 108h
0x18003be15  mov     rax, cs:__security_cookie
0x18003be1c  xor     rax, rsp
0x18003be1f  mov     [rbp+40h+var_50], rax
0x18003be23  mov     r14d, r9d
0x18003be26  mov     rsi, r8
0x18003be29  mov     r15, rdx
0x18003be2c  mov     rdi, rcx
0x18003be2f  xorps   xmm0, xmm0
0x18003be32  movdqu  xmmword ptr [rsp+140h+var_F8], xmm0
0x18003be38  mov     [rsp+140h+var_E8], 0
0x18003be41  movdqu  xmmword ptr [rsp+140h+var_E0], xmm0
0x18003be47  mov     [rsp+140h+var_D0], 0
0x18003be50  lea     rcx, [rsp+140h+var_F8]
0x18003be55  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003be5a  lea     rcx, [rsp+140h+var_E0]
0x18003be5f  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003be64  mov     rdx, [rsp+140h+var_F8+8]
0x18003be69  mov     rcx, [rsp+140h+var_F8]; unsigned __int16 *
0x18003be6e  sub     rdx, rcx
0x18003be71  sar     rdx, 1; unsigned __int64
0x18003be74  lea     r8, aEnter; "Enter"
0x18003be7b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003be80  mov     rdx, [rsp+140h+var_E0+8]
0x18003be85  mov     rcx, [rsp+140h+var_E0]; unsigned __int16 *
0x18003be8a  sub     rdx, rcx
0x18003be8d  sar     rdx, 1; unsigned __int64
0x18003be90  mov     rax, [rsp+140h+var_F8]
0x18003be95  mov     [rsp+140h+var_118], rax
0x18003be9a  mov     dword ptr [rsp+140h+var_120], 5B3h
0x18003bea2  lea     r9, aCwwantranslato_17; "CWwanTranslator::_CheckChainPinOperatio"...
0x18003bea9  lea     r8, aSDS; "%S(%d):%s"
0x18003beb0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003beb5  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003beba  mov     ecx, [rax]
0x18003bebc  cmp     ecx, 5
0x18003bebf  jbe     short loc_18003BEE5
0x18003bec1  mov     rcx, [rsp+140h+var_E0]
0x18003bec6  mov     [rsp+140h+var_100], rcx
0x18003becb  lea     rcx, [rsp+140h+var_100]
0x18003bed0  mov     [rsp+140h+var_120], rcx
0x18003bed5  lea     rdx, word_1800770EE
0x18003bedc  mov     rcx, rax
0x18003bedf  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003bee4  nop
0x18003bee5  lea     rcx, [rsp+140h+var_E0]
0x18003beea  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003beef  nop
0x18003bef0  lea     rcx, [rsp+140h+var_F8]
0x18003bef5  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003befa  xor     r12b, r12b
0x18003befd  xor     edx, edx; Val
0x18003beff  lea     r8d, [rdx+50h]; Size
0x18003bf03  lea     rcx, [rbp+40h+var_A0]; void *
0x18003bf07  call    memset_0
0x18003bf0c  lea     rbx, [rdi+28h]
0x18003bf10  mov     rcx, rbx; lpCriticalSection
0x18003bf13  call    cs:__imp_EnterCriticalSection
0x18003bf19  mov     [rbp+40h+var_B0], rbx
0x18003bf1d  lea     r13, [rdi+10h]
0x18003bf21  mov     r8, r15
0x18003bf24  lea     rdx, [rsp+140h+var_C8]
0x18003bf29  mov     rcx, r13
0x18003bf2c  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@UGUID_COMP@@V?$allocator@U?$pair@$$CBU_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$CComPtr@UICellularSettingsApi@@@ATL@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,ATL::CComPtr<ICellularSettingsApi>,GUID_COMP,std::allocator<std::pair<_GUID const,ATL::CComPtr<ICellularSettingsApi>>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x18003bf31  mov     rdi, [rbp+40h+var_B8]
0x18003bf35  cmp     [rdi+19h], r12b
0x18003bf39  jnz     loc_18003C526
0x18003bf3f  lea     rdx, [rdi+20h]; Buf2
0x18003bf43  mov     r8d, 10h; Size
0x18003bf49  mov     rcx, r15; Buf1
0x18003bf4c  call    memcmp_0
0x18003bf51  xor     ecx, ecx
0x18003bf53  test    eax, eax
0x18003bf55  js      loc_18003C526
0x18003bf5b  cmp     rdi, [r13+0]
0x18003bf5f  jz      loc_18003C526
0x18003bf65  cmp     [rdi+98h], cl
0x18003bf6b  jz      loc_18003C3E2
0x18003bf71  cmp     [rsi+8], ecx
0x18003bf74  jnz     loc_18003C2EC
0x18003bf7a  test    r14d, r14d
0x18003bf7d  jnz     loc_18003C156
0x18003bf83  xor     r14d, r14d
0x18003bf86  mov     [rsp+140h+var_D0], r14
0x18003bf8b  cmp     [rdi+0A0h], r14d
0x18003bf92  jz      loc_18003C093
0x18003bf98  mov     r12b, 1
0x18003bf9b  add     rdi, 9Ch
0x18003bfa2  movups  xmm0, xmmword ptr [rdi]
0x18003bfa5  movaps  [rbp+40h+var_A0], xmm0
0x18003bfa9  movups  xmm1, xmmword ptr [rdi+10h]
0x18003bfad  movaps  [rbp+40h+var_90], xmm1
0x18003bfb1  movups  xmm0, xmmword ptr [rdi+20h]
0x18003bfb5  movaps  [rbp+40h+var_80], xmm0
0x18003bfb9  movups  xmm1, xmmword ptr [rdi+30h]
0x18003bfbd  movaps  [rbp+40h+var_70], xmm1
0x18003bfc1  movups  xmm0, xmmword ptr [rdi+40h]
0x18003bfc5  movaps  [rbp+40h+var_60], xmm0
0x18003bfc9  xorps   xmm0, xmm0
0x18003bfcc  movdqu  xmmword ptr [rsp+140h+var_E0], xmm0
0x18003bfd2  movdqu  xmmword ptr [rsp+140h+var_F8], xmm0
0x18003bfd8  mov     [rsp+140h+var_E8], r14
0x18003bfdd  lea     rcx, [rsp+140h+var_E0]
0x18003bfe2  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003bfe7  lea     rcx, [rsp+140h+var_F8]
0x18003bfec  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003bff1  mov     rdx, [rsp+140h+var_E0+8]
0x18003bff6  mov     rcx, [rsp+140h+var_E0]; unsigned __int16 *
0x18003bffb  sub     rdx, rcx
0x18003bffe  sar     rdx, 1; unsigned __int64
0x18003c001  mov     r9d, dword ptr [rbp+40h+var_A0+4]
0x18003c005  lea     r8, aReInitiatePinA; "Re-initiate pin action [%d]."
0x18003c00c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c011  mov     rdx, [rsp+140h+var_F8+8]
0x18003c016  mov     rcx, [rsp+140h+var_F8]; unsigned __int16 *
0x18003c01b  sub     rdx, rcx
0x18003c01e  sar     rdx, 1; unsigned __int64
0x18003c021  mov     rax, [rsp+140h+var_E0]
0x18003c026  mov     [rsp+140h+var_118], rax
0x18003c02b  mov     dword ptr [rsp+140h+var_120], 5CEh
0x18003c033  lea     r9, aCwwantranslato_17; "CWwanTranslator::_CheckChainPinOperatio"...
0x18003c03a  lea     r8, aSDS; "%S(%d):%s"
0x18003c041  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c046  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003c04b  mov     ecx, [rax]
0x18003c04d  cmp     ecx, 4
0x18003c050  jbe     short loc_18003C076
0x18003c052  mov     rcx, [rsp+140h+var_F8]
0x18003c057  mov     [rsp+140h+var_100], rcx
0x18003c05c  lea     rcx, [rsp+140h+var_100]
0x18003c061  mov     [rsp+140h+var_120], rcx
0x18003c066  lea     rdx, byte_1800770AD
0x18003c06d  mov     rcx, rax
0x18003c070  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003c075  nop
0x18003c076  lea     rcx, [rsp+140h+var_F8]
0x18003c07b  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003c080  nop
0x18003c081  lea     rcx, [rsp+140h+var_E0]
0x18003c086  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003c08b  mov     rcx, rdi
0x18003c08e  jmp     loc_18003C3D0
0x18003c093  xorps   xmm0, xmm0
0x18003c096  movdqu  xmmword ptr [rsp+140h+var_E0], xmm0
0x18003c09c  movdqu  xmmword ptr [rsp+140h+var_F8], xmm0
0x18003c0a2  mov     [rsp+140h+var_E8], r14
0x18003c0a7  lea     rcx, [rsp+140h+var_E0]
0x18003c0ac  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003c0b1  lea     rcx, [rsp+140h+var_F8]
0x18003c0b6  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003c0bb  mov     rdx, [rsp+140h+var_E0+8]
0x18003c0c0  mov     rcx, [rsp+140h+var_E0]; unsigned __int16 *
0x18003c0c5  sub     rdx, rcx
0x18003c0c8  sar     rdx, 1; unsigned __int64
0x18003c0cb  lea     r8, aAfterASuccessf; "After a successful EnterPin, the origin"...
0x18003c0d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c0d7  mov     rdx, [rsp+140h+var_F8+8]
0x18003c0dc  mov     rcx, [rsp+140h+var_F8]; unsigned __int16 *
0x18003c0e1  sub     rdx, rcx
0x18003c0e4  sar     rdx, 1; unsigned __int64
0x18003c0e7  mov     rax, [rsp+140h+var_E0]
0x18003c0ec  mov     [rsp+140h+var_118], rax
0x18003c0f1  mov     dword ptr [rsp+140h+var_120], 5D5h
0x18003c0f9  lea     r9, aCwwantranslato_17; "CWwanTranslator::_CheckChainPinOperatio"...
0x18003c100  lea     r8, aSDS; "%S(%d):%s"
0x18003c107  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c10c  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003c111  mov     ecx, [rax]
0x18003c113  cmp     ecx, 2
0x18003c116  jbe     short loc_18003C13C
0x18003c118  mov     rcx, [rsp+140h+var_F8]
0x18003c11d  mov     [rsp+140h+var_100], rcx
0x18003c122  lea     rcx, [rsp+140h+var_100]
0x18003c127  mov     [rsp+140h+var_120], rcx
0x18003c12c  lea     rdx, byte_1800770CD
0x18003c133  mov     rcx, rax
0x18003c136  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003c13b  nop
0x18003c13c  lea     rcx, [rsp+140h+var_F8]
0x18003c141  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003c146  nop
0x18003c147  lea     rcx, [rsp+140h+var_E0]
0x18003c14c  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003c151  jmp     loc_18003C3C2
0x18003c156  xorps   xmm0, xmm0
0x18003c159  movdqu  xmmword ptr [rsp+140h+var_E0], xmm0
0x18003c15f  xor     r14d, r14d
0x18003c162  mov     [rsp+140h+var_D0], r14
0x18003c167  movdqu  xmmword ptr [rsp+140h+var_F8], xmm0
0x18003c16d  mov     [rsp+140h+var_E8], r14
0x18003c172  lea     rcx, [rsp+140h+var_E0]
0x18003c177  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003c17c  lea     rcx, [rsp+140h+var_F8]
0x18003c181  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003c186  mov     rdx, [rsp+140h+var_E0+8]
0x18003c18b  mov     rcx, [rsp+140h+var_E0]; unsigned __int16 *
0x18003c190  sub     rdx, rcx
0x18003c193  sar     rdx, 1; unsigned __int64
0x18003c196  lea     r8, aIntermediateEn; "Intermediate EnterPin operation failed."
0x18003c19d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c1a2  mov     rdx, [rsp+140h+var_F8+8]
0x18003c1a7  mov     rcx, [rsp+140h+var_F8]; unsigned __int16 *
0x18003c1ac  sub     rdx, rcx
0x18003c1af  sar     rdx, 1; unsigned __int64
0x18003c1b2  mov     rax, [rsp+140h+var_E0]
0x18003c1b7  mov     [rsp+140h+var_118], rax
0x18003c1bc  mov     dword ptr [rsp+140h+var_120], 5DEh
0x18003c1c4  lea     r9, aCwwantranslato_17; "CWwanTranslator::_CheckChainPinOperatio"...
0x18003c1cb  lea     r8, aSDS; "%S(%d):%s"
0x18003c1d2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c1d7  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003c1dc  mov     ecx, [rax]
0x18003c1de  cmp     ecx, 4
0x18003c1e1  jbe     short loc_18003C207
0x18003c1e3  mov     rcx, [rsp+140h+var_F8]
0x18003c1e8  mov     [rsp+140h+var_100], rcx
0x18003c1ed  lea     rcx, [rsp+140h+var_100]
0x18003c1f2  mov     [rsp+140h+var_120], rcx
0x18003c1f7  lea     rdx, dword_18007706C
0x18003c1fe  mov     rcx, rax
0x18003c201  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003c206  nop
0x18003c207  lea     rcx, [rsp+140h+var_F8]
0x18003c20c  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003c211  nop
0x18003c212  lea     rcx, [rsp+140h+var_E0]
0x18003c217  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003c21c  mov     eax, [rdi+0A0h]
0x18003c222  test    eax, eax
0x18003c224  jz      short loc_18003C22E
0x18003c226  mov     [rsi+8], eax
0x18003c229  jmp     loc_18003C3C2
0x18003c22e  xorps   xmm0, xmm0
0x18003c231  movdqu  xmmword ptr [rsp+140h+var_E0], xmm0
0x18003c237  mov     [rsp+140h+var_D0], r14
0x18003c23c  movdqu  xmmword ptr [rsp+140h+var_F8], xmm0
0x18003c242  mov     [rsp+140h+var_E8], r14
0x18003c247  lea     rcx, [rsp+140h+var_E0]
0x18003c24c  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003c251  lea     rcx, [rsp+140h+var_F8]
0x18003c256  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003c25b  mov     rdx, [rsp+140h+var_E0+8]
0x18003c260  mov     rcx, [rsp+140h+var_E0]; unsigned __int16 *
0x18003c265  sub     rdx, rcx
0x18003c268  sar     rdx, 1; unsigned __int64
0x18003c26b  lea     r8, aAfterAFailedEn; "After a failed EnterPin, the original P"...
0x18003c272  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c277  mov     rdx, [rsp+140h+var_F8+8]
0x18003c27c  mov     rcx, [rsp+140h+var_F8]; unsigned __int16 *
0x18003c281  sub     rdx, rcx
0x18003c284  sar     rdx, 1; unsigned __int64
0x18003c287  mov     rax, [rsp+140h+var_E0]
0x18003c28c  mov     [rsp+140h+var_118], rax
0x18003c291  mov     dword ptr [rsp+140h+var_120], 5E9h
0x18003c299  lea     r9, aCwwantranslato_17; "CWwanTranslator::_CheckChainPinOperatio"...
0x18003c2a0  lea     r8, aSDS; "%S(%d):%s"
0x18003c2a7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003c2ac  call    ?Provider@MbaeApiLogging@@SAPEBU_tlgProvider_t@@XZ; MbaeApiLogging::Provider(void)
0x18003c2b1  mov     ecx, [rax]
0x18003c2b3  cmp     ecx, 2
0x18003c2b6  jbe     short loc_18003C2DC
0x18003c2b8  mov     rcx, [rsp+140h+var_F8]
0x18003c2bd  mov     [rsp+140h+var_100], rcx
0x18003c2c2  lea     rcx, [rsp+140h+var_100]
0x18003c2c7  mov     [rsp+140h+var_120], rcx
0x18003c2cc  lea     rdx, dword_18007708C
0x18003c2d3  mov     rcx, rax
0x18003c2d6  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003c2db  nop
0x18003c2dc  lea     rcx, [rsp+140h+var_F8]
0x18003c2e1  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18003c2e6  nop
0x18003c2e7  jmp     loc_18003C147
0x18003c2ec  xorps   xmm0, xmm0
0x18003c2ef  movdqu  xmmword ptr [rsp+140h+var_E0], xmm0
0x18003c2f5  mov     [rsp+140h+var_D0], rcx
0x18003c2fa  movdqu  xmmword ptr [rsp+140h+var_F8], xmm0
0x18003c300  mov     [rsp+140h+var_E8], rcx
0x18003c305  lea     rcx, [rsp+140h+var_E0]
0x18003c30a  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003c30f  lea     rcx, [rsp+140h+var_F8]
0x18003c314  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x18003c319  mov     rdx, [rsp+140h+var_E0+8]
0x18003c31e  mov     rcx, [rsp+140h+var_E0]; unsigned __int16 *
0x18003c323  sub     rdx, rcx
0x18003c326  sar     rdx, 1; unsigned __int64
0x18003c329  mov     dword ptr [rsp+140h+var_118], r14d
0x18003c32e  mov     eax, [rsi+0Ch]
0x18003c331  mov     dword ptr [rsp+140h+var_120], eax
0x18003c335  mov     r9d, [rsi+8]
0x18003c339  lea     r8, aChainPinAction; "Chain pin action finishes with action ["...
  ... truncated ...
```
