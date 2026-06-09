# NcsiConfigData::HandleWinInetProxyConfigForCurrentUser(_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG const &)

- ea: `0x180051b7c`
- end: `0x180051c9f`
- name: `?HandleWinInetProxyConfigForCurrentUser@NcsiConfigData@@QEAAXAEBU_WINHTTP_CURRENT_USER_IE_PROXY_CONFIG@@@Z`
- size: `291`
- prototype: `void __fastcall(NcsiConfigData *__hidden this, const struct _WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800150f8`
- `0x18005d170`

## callees

- `0x1800257b8`
- `0x180051b7c`
- `0x180052b04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180051c98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051b98`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180051b98`

## string_xrefs

- `0x180051bb4`: `IE is set to auto-config, but NCSI will do that anyway.`
- `0x180051c08`: `Store as proxy config URL`
- `0x180051c5c`: `No IE proxy identified, clearing registry entry`

## pseudocode

```c
void __fastcall NcsiConfigData::HandleWinInetProxyConfigForCurrentUser(
        NcsiConfigData *this,
        const struct _WINHTTP_CURRENT_USER_IE_PROXY_CONFIG *a2)
{
  int v3; // r8d
  int v4; // r9d
  bool v5; // zf
  wchar_t *v6; // rcx
  int v7; // r8d
  int v8; // r9d
  const char *v9; // rax
  char *v10; // rdx
  wchar_t *v11; // rcx
  _QWORD v12[3]; // [rsp+30h] [rbp-18h] BYREF

  EnterCriticalSection(&stru_18009D378);
  v12[1] = &stru_18009D378;
  v5 = *(_DWORD *)a2 == 0;
  if ( *(_DWORD *)a2 )
  {
    if ( (unsigned int)dword_18009A048 > 5 )
    {
      v12[0] = "IE is set to auto-config, but NCSI will do that anyway.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_18009A048,
        (unsigned int)&dword_180086544,
        v3,
        v4,
        (__int64)v12);
    }
    v5 = *(_DWORD *)a2 == 0;
  }
  byte_18009B420 = !v5;
  v6 = (wchar_t *)*((_QWORD *)a2 + 1);
  if ( v6 && *v6 )
  {
    StoreNcsiIEProxyString(v6, 0);
    if ( (unsigned int)dword_18009A048 > 5 )
    {
      v9 = "Store as proxy config URL";
      v10 = byte_180086501;
LABEL_15:
      v12[0] = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_18009A048,
        (_DWORD)v10,
        v7,
        v8,
        (__int64)v12);
    }
  }
  else
  {
    v11 = (wchar_t *)*((_QWORD *)a2 + 2);
    if ( v11 && *v11 )
    {
      StoreNcsiIEProxyString(v11, 1);
      if ( (unsigned int)dword_18009A048 > 5 )
      {
        v9 = "Store as proxy list";
        v10 = (char *)&word_1800864BE;
        goto LABEL_15;
      }
    }
    else
    {
      StoreNcsiIEProxyString(0, 0);
      if ( (unsigned int)dword_18009A048 > 5 )
      {
        v9 = "No IE proxy identified, clearing registry entry";
        v10 = byte_18008647B;
        goto LABEL_15;
      }
    }
  }
  LeaveCriticalSection(&stru_18009D378);
}

```

## disassembly

```asm
0x180051b7c  mov     [rsp+arg_0], rbx
0x180051b81  mov     [rsp+arg_10], rbp
0x180051b86  push    rdi
0x180051b87  sub     rsp, 40h
0x180051b8b  mov     rbx, rdx
0x180051b8e  lea     rbp, stru_18009D378
0x180051b95  mov     rcx, rbp; lpCriticalSection
0x180051b98  call    cs:__imp_EnterCriticalSection
0x180051b9e  mov     [rsp+48h+var_10], rbp
0x180051ba3  xor     edi, edi
0x180051ba5  cmp     [rbx], edi
0x180051ba7  jz      short loc_180051BDF
0x180051ba9  mov     eax, cs:dword_18009A048
0x180051baf  cmp     eax, 5
0x180051bb2  jbe     short loc_180051BDD
0x180051bb4  lea     rax, aIeIsSetToAutoC; "IE is set to auto-config, but NCSI will"...
0x180051bbb  mov     [rsp+48h+var_18], rax
0x180051bc0  lea     rax, [rsp+48h+var_18]
0x180051bc5  mov     [rsp+48h+var_28], rax
0x180051bca  lea     rdx, dword_180086544
0x180051bd1  lea     rcx, dword_18009A048
0x180051bd8  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180051bdd  cmp     [rbx], edi
0x180051bdf  setnz   al
0x180051be2  xchg    al, cs:byte_18009B420
0x180051be8  mov     rcx, [rbx+8]; Str
0x180051bec  test    rcx, rcx
0x180051bef  jz      short loc_180051C18
0x180051bf1  cmp     [rcx], di
0x180051bf4  jz      short loc_180051C18
0x180051bf6  xor     edx, edx
0x180051bf8  call    StoreNcsiIEProxyString
0x180051bfd  mov     eax, cs:dword_18009A048
0x180051c03  cmp     eax, 5
0x180051c06  jbe     short loc_180051C86
0x180051c08  lea     rax, aStoreAsProxyCo; "Store as proxy config URL"
0x180051c0f  lea     rdx, byte_180086501
0x180051c16  jmp     short loc_180051C6A
0x180051c18  mov     rcx, [rbx+10h]; Str
0x180051c1c  test    rcx, rcx
0x180051c1f  jz      short loc_180051C48
0x180051c21  cmp     [rcx], di
0x180051c24  jz      short loc_180051C48
0x180051c26  mov     dl, 1
0x180051c28  call    StoreNcsiIEProxyString
0x180051c2d  mov     eax, cs:dword_18009A048
0x180051c33  cmp     eax, 5
0x180051c36  jbe     short loc_180051C86
0x180051c38  lea     rax, aStoreAsProxyLi; "Store as proxy list"
0x180051c3f  lea     rdx, word_1800864BE
0x180051c46  jmp     short loc_180051C6A
0x180051c48  xor     edx, edx
0x180051c4a  xor     ecx, ecx; Str
0x180051c4c  call    StoreNcsiIEProxyString
0x180051c51  mov     eax, cs:dword_18009A048
0x180051c57  cmp     eax, 5
0x180051c5a  jbe     short loc_180051C86
0x180051c5c  lea     rax, aNoIeProxyIdent; "No IE proxy identified, clearing regist"...
0x180051c63  lea     rdx, byte_18008647B
0x180051c6a  mov     [rsp+48h+var_18], rax
0x180051c6f  lea     rax, [rsp+48h+var_18]
0x180051c74  mov     [rsp+48h+var_28], rax
0x180051c79  lea     rcx, dword_18009A048
0x180051c80  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180051c85  nop
0x180051c86  mov     rcx, rbp
0x180051c89  mov     rbx, [rsp+48h+arg_0]
0x180051c8e  mov     rbp, [rsp+48h+arg_10]
0x180051c93  add     rsp, 40h
0x180051c97  pop     rdi
0x180051c98  jmp     cs:__imp_LeaveCriticalSection
```
