# RespondToProxyOpportunity(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x180068b20`
- end: `0x180068cd3`
- name: `?RespondToProxyOpportunity@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `435`
- prototype: `void __fastcall(struct _TP_CALLBACK_INSTANCE *, void *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x18000d990`
- `0x18000e870`
- `0x180010200`
- `0x180011a58`
- `0x18001d444`
- `0x180023304`
- `0x18005deec`
- `0x18005defc`
- `0x180068b20`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180068b2d`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x180068b2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068c03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068c03`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068b8e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068b8e`

## string_xrefs

- `0x180068ca4`: `there are real proxies already`
- `0x180068cad`: `all connections are internet already`

## pseudocode

```c
void __fastcall RespondToProxyOpportunity(struct _TP_CALLBACK_INSTANCE *a1, void *a2)
{
  __int64 v3; // rcx
  int v4; // esi
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // ecx
  int v10; // ecx
  char v11; // bl
  __int64 v12; // rdx
  void (__fastcall *v13)(const struct Ncsi::Proxy::Info *, const struct _GUID *); // rcx
  const char *v14; // r9
  _QWORD v15[7]; // [rsp+20h] [rbp-78h] BYREF
  _QWORD *v16; // [rsp+58h] [rbp-40h]

  CallbackMayRunLong(a1);
  v3 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 52, &WPP_c67a6644af093602b51c782a1df615fe_Traceguids, a2 != 0);
  }
  v4 = *(_DWORD *)Ncsi::Proxy::Detector::GetProxyInfo(v3, v15);
  Ncsi::Proxy::Info::~Info((Ncsi::Proxy::Info *)v15);
  EnterCriticalSection(&g_ncsiLock);
  v5 = std::vector<NCSI_INTERFACE_ATTRIBUTES>::_Unchecked_begin();
  v8 = std::vector<NCSI_INTERFACE_ATTRIBUTES>::_Unchecked_end(v6, v5);
  while ( v7 != v8 )
  {
    if ( !*(_DWORD *)(v7 + 24) )
    {
      if ( *(_BYTE *)(v7 + 4353) )
      {
        v9 = *(_DWORD *)(v7 + 4428);
        if ( *(_DWORD *)(v7 + 4424) >= v9 )
          v9 = *(_DWORD *)(v7 + 4424);
        if ( v9 != 2 )
          goto LABEL_17;
      }
      if ( *(_BYTE *)(v7 + 8297) )
      {
        v10 = *(_DWORD *)(v7 + 8372);
        if ( *(_DWORD *)(v7 + 8368) >= v10 )
          v10 = *(_DWORD *)(v7 + 8368);
        if ( v10 != 2 )
        {
LABEL_17:
          v11 = 0;
          goto LABEL_19;
        }
      }
    }
    v7 += 12888;
  }
  v11 = 1;
LABEL_19:
  LeaveCriticalSection(&g_ncsiLock);
  if ( !v11 && (v4 == 3 || a2) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 53, &WPP_c67a6644af093602b51c782a1df615fe_Traceguids);
    }
    v13 = OnProxyDetectionFinished;
    v16 = 0;
    if ( !a2 )
      v13 = 0;
    if ( v13 )
    {
      v15[1] = v13;
      v15[0] = &std::_Func_impl_no_alloc<void (*)(Ncsi::Proxy::Info const &,_GUID const *),void,Ncsi::Proxy::Info const &,_GUID *>::`vftable';
      v16 = v15;
    }
    Ncsi::Proxy::QueueRedetection(v15, v12, 0);
  }
  else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
         && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    v14 = "all connections are internet already";
    if ( !v11 )
      v14 = "there are real proxies already";
    WPP_SF_s(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 54, &WPP_c67a6644af093602b51c782a1df615fe_Traceguids, v14);
  }
}

```

## disassembly

```asm
0x180068b20  push    rbx
0x180068b22  push    rsi
0x180068b23  push    rdi
0x180068b24  push    r12
0x180068b26  sub     rsp, 78h
0x180068b2a  mov     rdi, rdx
0x180068b2d  call    cs:__imp_CallbackMayRunLong
0x180068b33  mov     rcx, cs:WPP_GLOBAL_Control
0x180068b3a  lea     r12, WPP_GLOBAL_Control
0x180068b41  cmp     rcx, r12
0x180068b44  jz      short loc_180068B71
0x180068b46  test    byte ptr [rcx+1Ch], 10h
0x180068b4a  jz      short loc_180068B71
0x180068b4c  cmp     byte ptr [rcx+19h], 5
0x180068b50  jb      short loc_180068B71
0x180068b52  mov     rcx, [rcx+10h]
0x180068b56  lea     r8, WPP_c67a6644af093602b51c782a1df615fe_Traceguids
0x180068b5d  xor     r9d, r9d
0x180068b60  mov     edx, 34h ; '4'
0x180068b65  test    rdi, rdi
0x180068b68  setnz   r9b
0x180068b6c  call    WPP_SF_d
0x180068b71  lea     rdx, [rsp+98h+var_78]
0x180068b76  call    ?GetProxyInfo@Detector@Proxy@Ncsi@@QEAA?AVInfo@23@XZ; Ncsi::Proxy::Detector::GetProxyInfo(void)
0x180068b7b  lea     rcx, [rsp+98h+var_78]; this
0x180068b80  mov     esi, [rax]
0x180068b82  call    ??1Info@Proxy@Ncsi@@QEAA@XZ; Ncsi::Proxy::Info::~Info(void)
0x180068b87  lea     rcx, ?g_ncsiLock@@3Vcritical_section@wil@@A; lpCriticalSection
0x180068b8e  call    cs:__imp_EnterCriticalSection
0x180068b94  call    ?_Unchecked_begin@?$vector@VNCSI_INTERFACE_ATTRIBUTES@@V?$allocator@VNCSI_INTERFACE_ATTRIBUTES@@@std@@@std@@QEBAPEBVNCSI_INTERFACE_ATTRIBUTES@@XZ; std::vector<NCSI_INTERFACE_ATTRIBUTES>::_Unchecked_begin(void)
0x180068b99  mov     rdx, rax
0x180068b9c  call    ?_Unchecked_end@?$vector@VNCSI_INTERFACE_ATTRIBUTES@@V?$allocator@VNCSI_INTERFACE_ATTRIBUTES@@@std@@@std@@QEBAPEBVNCSI_INTERFACE_ATTRIBUTES@@XZ; std::vector<NCSI_INTERFACE_ATTRIBUTES>::_Unchecked_end(void)
0x180068ba1  mov     r8, rax
0x180068ba4  cmp     rdx, r8
0x180068ba7  jz      short loc_180068BFA
0x180068ba9  cmp     dword ptr [rdx+18h], 0
0x180068bad  jnz     short loc_180068BED
0x180068baf  cmp     byte ptr [rdx+1101h], 0
0x180068bb6  jz      short loc_180068BCE
0x180068bb8  mov     ecx, [rdx+114Ch]
0x180068bbe  mov     eax, [rdx+1148h]
0x180068bc4  cmp     eax, ecx
0x180068bc6  cmovge  ecx, eax
0x180068bc9  cmp     ecx, 2
0x180068bcc  jnz     short loc_180068BF6
0x180068bce  cmp     byte ptr [rdx+2069h], 0
0x180068bd5  jz      short loc_180068BED
0x180068bd7  mov     ecx, [rdx+20B4h]
0x180068bdd  mov     eax, [rdx+20B0h]
0x180068be3  cmp     eax, ecx
0x180068be5  cmovge  ecx, eax
0x180068be8  cmp     ecx, 2
0x180068beb  jnz     short loc_180068BF6
0x180068bed  add     rdx, 3258h
0x180068bf4  jmp     short loc_180068BA4
0x180068bf6  xor     bl, bl
0x180068bf8  jmp     short loc_180068BFC
0x180068bfa  mov     bl, 1
0x180068bfc  lea     rcx, ?g_ncsiLock@@3Vcritical_section@wil@@A; lpCriticalSection
0x180068c03  call    cs:__imp_LeaveCriticalSection
0x180068c09  test    bl, bl
0x180068c0b  jnz     short loc_180068C88
0x180068c0d  cmp     esi, 3
0x180068c10  jz      short loc_180068C17
0x180068c12  test    rdi, rdi
0x180068c15  jz      short loc_180068C88
0x180068c17  mov     rcx, cs:WPP_GLOBAL_Control
0x180068c1e  cmp     rcx, r12
0x180068c21  jz      short loc_180068C44
0x180068c23  test    byte ptr [rcx+1Ch], 10h
0x180068c27  jz      short loc_180068C44
0x180068c29  cmp     byte ptr [rcx+19h], 5
0x180068c2d  jb      short loc_180068C44
0x180068c2f  mov     rcx, [rcx+10h]
0x180068c33  lea     r8, WPP_c67a6644af093602b51c782a1df615fe_Traceguids
0x180068c3a  mov     edx, 35h ; '5'
0x180068c3f  call    WPP_SF_
0x180068c44  xor     eax, eax
0x180068c46  lea     rcx, ?OnProxyDetectionFinished@@YAXAEBVInfo@Proxy@Ncsi@@PEBU_GUID@@@Z; OnProxyDetectionFinished(Ncsi::Proxy::Info const &,_GUID const *)
0x180068c4d  test    rdi, rdi
0x180068c50  mov     [rsp+98h+var_40], rax
0x180068c55  cmovz   rcx, rax
0x180068c59  test    rcx, rcx
0x180068c5c  jz      short loc_180068C79
0x180068c5e  lea     rax, ??_7?$_Func_impl_no_alloc@P6AXAEBVInfo@Proxy@Ncsi@@PEBU_GUID@@@ZXAEBV123@PEAU4@@std@@6B@; const std::_Func_impl_no_alloc<void (*)(Ncsi::Proxy::Info const &,_GUID const *),void,Ncsi::Proxy::Info const &,_GUID *>::`vftable'
0x180068c65  mov     [rsp+98h+var_70], rcx
0x180068c6a  mov     [rsp+98h+var_78], rax
0x180068c6f  lea     rax, [rsp+98h+var_78]
0x180068c74  mov     [rsp+98h+var_40], rax
0x180068c79  xor     r8d, r8d
0x180068c7c  lea     rcx, [rsp+98h+var_78]
0x180068c81  call    ?QueueRedetection@Proxy@Ncsi@@YAXV?$function@$$A6AXAEBVInfo@Proxy@Ncsi@@PEAU_GUID@@@Z@std@@_NPEBU_GUID@@@Z; Ncsi::Proxy::QueueRedetection(std::function<void (Ncsi::Proxy::Info const &,_GUID *)>,bool,_GUID const *)
0x180068c86  jmp     short loc_180068CC9
0x180068c88  mov     rcx, cs:WPP_GLOBAL_Control
0x180068c8f  cmp     rcx, r12
0x180068c92  jz      short loc_180068CC9
0x180068c94  test    byte ptr [rcx+1Ch], 10h
0x180068c98  jz      short loc_180068CC9
0x180068c9a  cmp     byte ptr [rcx+19h], 5
0x180068c9e  jb      short loc_180068CC9
0x180068ca0  mov     rcx, [rcx+10h]
0x180068ca4  lea     rax, aThereAreRealPr; "there are real proxies already"
0x180068cab  test    bl, bl
0x180068cad  lea     r9, aAllConnections; "all connections are internet already"
0x180068cb4  mov     edx, 36h ; '6'
0x180068cb9  lea     r8, WPP_c67a6644af093602b51c782a1df615fe_Traceguids
0x180068cc0  cmovz   r9, rax
0x180068cc4  call    WPP_SF_s
0x180068cc9  add     rsp, 78h
0x180068ccd  pop     r12
0x180068ccf  pop     rdi
0x180068cd0  pop     rsi
0x180068cd1  pop     rbx
0x180068cd2  retn
```
