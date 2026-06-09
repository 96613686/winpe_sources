# DwmUnregisterThumbnail

- ea: `0x180001a10`
- end: `0x180001c06`
- name: `DwmUnregisterThumbnail`
- size: `502`
- prototype: `HRESULT __stdcall(HTHUMBNAIL hThumbnailId)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001a10`
- `0x18000352c`
- `0x180003820`
- `0x18000387c`
- `0x180004594`
- `0x180005b5c`
- `0x18000b05c`
- `0x18000b880`
- `0x18000bab0`
- `0x18000d0a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001a8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001b12`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001a8a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001b12`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001a64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ace`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001a64`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001ace`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001a48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001a48`

## pseudocode

```c
HRESULT __stdcall DwmUnregisterThumbnail(HTHUMBNAIL hThumbnailId)
{
  __int64 v1; // r8
  int v2; // ebx
  HRESULT v3; // edi
  CApiPortClient *v4; // rcx
  int v5; // eax
  int v6; // ebx
  int v7; // ebx
  int v8; // eax
  void *v10; // [rsp+28h] [rbp-60h]
  void *v11; // [rsp+28h] [rbp-60h]
  int v12; // [rsp+40h] [rbp-48h] BYREF
  void **v13; // [rsp+48h] [rbp-40h]
  __int128 v14; // [rsp+50h] [rbp-38h] BYREF
  _DWORD v15[4]; // [rsp+60h] [rbp-28h] BYREF

  v2 = (int)hThumbnailId;
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(
      Microsoft_Windows_Dwm_Api_Provider_Context,
      (__int64)ApiUnregisterThumbnail_Start,
      v1,
      1,
      (__int64)v15);
  v15[0] = 1073741857;
  v15[1] = v2;
  v15[2] = GetCurrentProcessId();
  v3 = 0;
  v14 = 0;
  EnterCriticalSection(&CriticalSection);
  v12 = 0;
  v5 = CApiPortClient::EnsureConnected(v4);
  v6 = v5;
  if ( v5 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(4u, &CApiPortClient::MILINSTRUMENTATIONHRESULTLIST, 2u, v5, 0xACu, v10);
  }
  else
  {
    ++dword_18001F948;
    LeaveCriticalSection(&CriticalSection);
    v7 = CPortClient::SendComplexSyncRequest(g_PortClient, 1073741857, v15, 12, 0, 0, 0, &v12);
    EnterCriticalSection(&CriticalSection);
    if ( !--dword_18001F948 && *(_DWORD *)(g_PortClient + 8LL) )
      CApiPortClient::Disconnect((CApiPortClient *)&g_PortClient);
    v8 = CApiPortClient::Translate(v7);
    v6 = v8;
    if ( v8 < 0 )
      MilInstrumentationCheckHR_MaybeFailFast(4u, &CApiPortClient::MILINSTRUMENTATIONHRESULTLIST, 2u, v8, 0xC1u, v11);
    else
      v3 = CApiPortClient::Translate(v12);
  }
  LeaveCriticalSection(&CriticalSection);
  v13 = &CStandardData::`vftable';
  std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>((char *)&v14 + 8);
  if ( v6 < 0 )
  {
    v3 = v6;
    MilInstrumentationCheckHR_MaybeFailFast(4u, &dword_180019284, 1u, v6, 0x1D3u, v11);
  }
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(Microsoft_Windows_Dwm_Api_Provider_Context, ApiUnregisterThumbnail_Stop);
  return v3;
}

```

## disassembly

```asm
0x180001a10  mov     [rsp+arg_8], rbx
0x180001a15  push    rdi
0x180001a16  sub     rsp, 80h
0x180001a1d  mov     rax, cs:__security_cookie
0x180001a24  xor     rax, rsp
0x180001a27  mov     [rsp+88h+var_18], rax
0x180001a2c  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x180001a33  mov     rbx, rcx
0x180001a36  jnz     loc_180001B82
0x180001a3c  mov     [rsp+88h+var_28], 40000021h
0x180001a44  mov     [rsp+88h+var_24], ebx
0x180001a48  call    cs:__imp_GetCurrentProcessId
0x180001a4e  xorps   xmm0, xmm0
0x180001a51  lea     rcx, CriticalSection; lpCriticalSection
0x180001a58  mov     [rsp+88h+var_20], eax
0x180001a5c  xor     edi, edi
0x180001a5e  movdqu  [rsp+88h+var_38], xmm0
0x180001a64  call    cs:__imp_EnterCriticalSection
0x180001a6a  mov     [rsp+88h+var_48], edi
0x180001a6e  call    ?EnsureConnected@CApiPortClient@@AEAAJXZ; CApiPortClient::EnsureConnected(void)
0x180001a73  mov     ebx, eax
0x180001a75  test    eax, eax
0x180001a77  js      loc_180001BC5
0x180001a7d  inc     cs:dword_18001F948
0x180001a83  lea     rcx, CriticalSection; lpCriticalSection
0x180001a8a  call    cs:__imp_LeaveCriticalSection
0x180001a90  xor     eax, eax
0x180001a92  lea     rcx, [rsp+88h+var_48]
0x180001a97  mov     [rsp+88h+var_50], rcx; int *
0x180001a9c  lea     r9d, [rdi+0Ch]; __int16
0x180001aa0  mov     rcx, cs:?g_PortClient@@3VCApiPortClient@@A; this
0x180001aa7  lea     r8, [rsp+88h+var_28]; void *
0x180001aac  mov     [rsp+88h+var_58], ax; __int16
0x180001ab1  mov     edx, 40000021h; unsigned int
0x180001ab6  mov     [rsp+88h+var_60], rax; void *
0x180001abb  mov     [rsp+88h+var_68], rax; struct CAlpcView *
0x180001ac0  call    ?SendComplexSyncRequest@CPortClient@@QEAAJKPEBXFPEBVCAlpcView@@PEAXFPEAJ@Z; CPortClient::SendComplexSyncRequest(ulong,void const *,short,CAlpcView const *,void *,short,long *)
0x180001ac5  lea     rcx, CriticalSection; lpCriticalSection
0x180001acc  mov     ebx, eax
0x180001ace  call    cs:__imp_EnterCriticalSection
0x180001ad4  add     cs:dword_18001F948, 0FFFFFFFFh
0x180001adb  jnz     short loc_180001AEF
0x180001add  mov     rcx, cs:?g_PortClient@@3VCApiPortClient@@A; CApiPortClient g_PortClient
0x180001ae4  mov     edx, [rcx+8]
0x180001ae7  test    edx, edx
0x180001ae9  jnz     loc_180001BAA
0x180001aef  mov     ecx, ebx; int
0x180001af1  call    ?Translate@CApiPortClient@@CAJJ@Z; CApiPortClient::Translate(long)
0x180001af6  mov     ebx, eax
0x180001af8  test    eax, eax
0x180001afa  js      loc_180001BBB
0x180001b00  mov     ecx, [rsp+88h+var_48]; int
0x180001b04  call    ?Translate@CApiPortClient@@CAJJ@Z; CApiPortClient::Translate(long)
0x180001b09  mov     edi, eax
0x180001b0b  lea     rcx, CriticalSection; lpCriticalSection
0x180001b12  call    cs:__imp_LeaveCriticalSection
0x180001b18  lea     rax, ??_7CStandardData@@6B@; const CStandardData::`vftable'
0x180001b1f  lea     rcx, [rsp+88h+var_38+8]
0x180001b24  mov     [rsp+88h+var_40], rax
0x180001b29  call    ??1?$unique_ptr@VCAlpcView@@U?$default_delete@VCAlpcView@@@std@@@std@@QEAA@XZ; std::unique_ptr<CAlpcView>::~unique_ptr<CAlpcView>(void)
0x180001b2e  test    ebx, ebx
0x180001b30  jns     short loc_180001B55
0x180001b32  mov     r8d, 1; unsigned int
0x180001b38  mov     dword ptr [rsp+88h+var_68], 1D3h; unsigned int
0x180001b40  mov     r9d, ebx; int
0x180001b43  lea     rdx, dword_180019284; int *
0x180001b4a  mov     edi, ebx
0x180001b4c  lea     ecx, [r8+3]; unsigned int
0x180001b50  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180001b55  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x180001b5c  jnz     loc_180001BEB
0x180001b62  mov     eax, edi
0x180001b64  mov     rcx, [rsp+88h+var_18]
0x180001b69  xor     rcx, rsp; StackCookie
0x180001b6c  call    __security_check_cookie
0x180001b71  mov     rbx, [rsp+88h+arg_8]
0x180001b79  add     rsp, 80h
0x180001b80  pop     rdi
0x180001b81  retn
0x180001b82  lea     rax, [rsp+88h+var_28]
0x180001b87  mov     r9d, 1
0x180001b8d  lea     rdx, ApiUnregisterThumbnail_Start
0x180001b94  mov     [rsp+88h+var_68], rax
0x180001b99  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x180001ba0  call    McGenEventWrite_EtwEventWriteTransfer
0x180001ba5  jmp     loc_180001A3C
0x180001baa  lea     rcx, ?g_PortClient@@3VCApiPortClient@@A; this
0x180001bb1  call    ?Disconnect@CApiPortClient@@AEAAXXZ; CApiPortClient::Disconnect(void)
0x180001bb6  jmp     loc_180001AEF
0x180001bbb  mov     dword ptr [rsp+88h+var_68], 0C1h
0x180001bc3  jmp     short loc_180001BCD
0x180001bc5  mov     dword ptr [rsp+88h+var_68], 0ACh; unsigned int
0x180001bcd  mov     r8d, 2; unsigned int
0x180001bd3  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CApiPortClient@@0QBJB; int *
0x180001bda  mov     r9d, eax; int
0x180001bdd  lea     ecx, [r8+2]; unsigned int
0x180001be1  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180001be6  jmp     loc_180001B0B
0x180001beb  mov     r8d, edi
0x180001bee  lea     rdx, ApiUnregisterThumbnail_Stop
0x180001bf5  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x180001bfc  call    McTemplateU0q_EtwEventWriteTransfer
0x180001c01  jmp     loc_180001B62
```
