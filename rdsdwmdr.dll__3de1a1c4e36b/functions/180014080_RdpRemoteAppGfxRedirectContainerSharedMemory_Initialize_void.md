# RdpRemoteAppGfxRedirectContainerSharedMemory::Initialize(void *)

- ea: `0x180014080`
- end: `0x1800141ca`
- name: `?Initialize@RdpRemoteAppGfxRedirectContainerSharedMemory@@UEAAJPEAX@Z`
- size: `330`
- prototype: `__int64 __fastcall(RdpRemoteAppGfxRedirectContainerSharedMemory *__hidden this, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000160c`
- `0x180014080`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014099`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014099`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800140a7`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1800140a7`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001413d`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18001413d`

## pseudocode

```c
__int64 __fastcall RdpRemoteAppGfxRedirectContainerSharedMemory::Initialize(
        RdpRemoteAppGfxRedirectContainerSharedMemory *this,
        void *a2)
{
  int v2; // edi
  DWORD CurrentProcessId; // eax
  __int16 v5; // bx
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // ebx
  const char *v12; // [rsp+50h] [rbp-18h] BYREF
  const char *v13; // [rsp+58h] [rbp-10h] BYREF
  DWORD pSessionId; // [rsp+90h] [rbp+28h] BYREF
  int v15; // [rsp+98h] [rbp+30h] BYREF
  int v16; // [rsp+A0h] [rbp+38h] BYREF
  const char *v17; // [rsp+A8h] [rbp+40h] BYREF

  v2 = (int)a2;
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  v5 = CurrentProcessId;
  ProcessIdToSessionId(CurrentProcessId, &pSessionId);
  *((_WORD *)this + 267) = pSessionId;
  *((_BYTE *)this + 538) = HIBYTE(v2);
  *((_BYTE *)this + 539) = BYTE2(v2);
  *((_BYTE *)this + 540) = BYTE1(v2);
  *((_BYTE *)this + 542) = byte_180044C79;
  v6 = RdpRemoteAppGfxRedirectContainerSharedMemory::m_uiCreationId;
  *((_BYTE *)this + 543) = RdpRemoteAppGfxRedirectContainerSharedMemory::m_uiCreationId;
  *((_BYTE *)this + 536) = HIBYTE(v5);
  *((_DWORD *)this + 132) = -409130983;
  *((_WORD *)this + 266) = 7519;
  *((_BYTE *)this + 537) = v5;
  *((_BYTE *)this + 541) = v2;
  RdpRemoteAppGfxRedirectContainerSharedMemory::m_uiCreationId = v6 + 1;
  if ( StringFromGUID2((const GUID *const)this + 33, (LPOLESTR)this + 4, 260) )
  {
    return 0;
  }
  else
  {
    v10 = -2147467259;
    if ( (unsigned int)dword_180044008 > 2 )
    {
      v15 = 71;
      v17 = "Initialize";
      v16 = -2147467259;
      v12 = "clientcore\\termsrv\\rdsdwmdirect\\remoteappgfxredirection.cpp";
      v13 = "Failed to convert section GUID to section name";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v7,
        (__int64)&dword_18003D844,
        v8,
        v9,
        (const unsigned __int16 **)&v13,
        (__int64)&v16,
        (const unsigned __int16 **)&v12,
        (__int64)&v15,
        (const unsigned __int16 **)&v17);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x180014080  push    rbp
0x180014082  push    rbx
0x180014083  push    rsi
0x180014084  push    rdi
0x180014085  mov     rbp, rsp
0x180014088  sub     rsp, 68h
0x18001408c  mov     rdi, rdx
0x18001408f  mov     [rbp+pSessionId], 0
0x180014096  mov     rsi, rcx
0x180014099  call    cs:__imp_GetCurrentProcessId
0x18001409f  mov     ecx, eax; dwProcessId
0x1800140a1  lea     rdx, [rbp+pSessionId]; pSessionId
0x1800140a5  mov     ebx, eax
0x1800140a7  call    cs:__imp_ProcessIdToSessionId
0x1800140ad  movzx   edx, word ptr [rbp+pSessionId]
0x1800140b1  lea     r9, [rsi+210h]
0x1800140b8  mov     [rsi+216h], dx
0x1800140bf  mov     ecx, ebx
0x1800140c1  shr     ecx, 8
0x1800140c4  mov     rax, rdi
0x1800140c7  shr     rax, 18h
0x1800140cb  mov     r8d, 104h; cchMax
0x1800140d1  mov     [rsi+21Ah], al
0x1800140d7  mov     rax, rdi
0x1800140da  shr     rax, 10h
0x1800140de  mov     [rsi+21Bh], al
0x1800140e4  mov     rax, rdi
0x1800140e7  shr     rax, 8
0x1800140eb  mov     [rsi+21Ch], al
0x1800140f1  mov     al, cs:byte_180044C79
0x1800140f7  mov     [rsi+21Eh], al
0x1800140fd  mov     eax, dword ptr cs:?m_uiCreationId@RdpRemoteAppGfxRedirectContainerSharedMemory@@0IA; uint RdpRemoteAppGfxRedirectContainerSharedMemory::m_uiCreationId
0x180014103  mov     edx, eax
0x180014105  mov     [rsi+21Fh], dl
0x18001410b  inc     eax
0x18001410d  mov     [rsi+218h], cl
0x180014113  lea     rdx, [rsi+8]; lpsz
0x180014117  mov     rcx, r9; rguid
0x18001411a  mov     dword ptr [r9], 0E79D2819h
0x180014121  mov     word ptr [rsi+214h], 1D5Fh
0x18001412a  mov     [rsi+219h], bl
0x180014130  mov     [rsi+21Dh], dil
0x180014137  mov     dword ptr cs:?m_uiCreationId@RdpRemoteAppGfxRedirectContainerSharedMemory@@0IA, eax; uint RdpRemoteAppGfxRedirectContainerSharedMemory::m_uiCreationId
0x18001413d  call    cs:__imp_StringFromGUID2
0x180014143  test    eax, eax
0x180014145  jnz     short loc_1800141BD
0x180014147  mov     eax, cs:dword_180044008
0x18001414d  mov     ebx, 80004005h
0x180014152  cmp     eax, 2
0x180014155  jbe     short loc_1800141BF
0x180014157  lea     rax, aInitialize; "Initialize"
0x18001415e  mov     [rbp+arg_8], 47h ; 'G'
0x180014165  mov     [rbp+arg_18], rax
0x180014169  lea     rdx, dword_18003D844
0x180014170  lea     rax, aClientcoreTerm_0; "clientcore\\termsrv\\rdsdwmdirect\\remo"...
0x180014177  mov     [rbp+arg_10], ebx
0x18001417a  mov     [rbp+var_18], rax
0x18001417e  lea     rax, aFailedToConver; "Failed to convert section GUID to secti"...
0x180014185  mov     [rbp+var_10], rax
0x180014189  lea     rax, [rbp+arg_18]
0x18001418d  mov     [rsp+68h+var_28], rax
0x180014192  lea     rax, [rbp+arg_8]
0x180014196  mov     [rsp+68h+var_30], rax
0x18001419b  lea     rax, [rbp+var_18]
0x18001419f  mov     [rsp+68h+var_38], rax
0x1800141a4  lea     rax, [rbp+arg_10]
0x1800141a8  mov     [rsp+68h+var_40], rax
0x1800141ad  lea     rax, [rbp+var_10]
0x1800141b1  mov     [rsp+68h+var_48], rax
0x1800141b6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800141bb  jmp     short loc_1800141BF
0x1800141bd  xor     ebx, ebx
0x1800141bf  mov     eax, ebx
0x1800141c1  add     rsp, 68h
0x1800141c5  pop     rdi
0x1800141c6  pop     rsi
0x1800141c7  pop     rbx
0x1800141c8  pop     rbp
0x1800141c9  retn
```
