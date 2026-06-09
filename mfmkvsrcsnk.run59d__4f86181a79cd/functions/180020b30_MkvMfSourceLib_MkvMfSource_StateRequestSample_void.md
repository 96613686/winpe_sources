# MkvMfSourceLib::MkvMfSource::StateRequestSample(void)

- ea: `0x180020b30`
- end: `0x180020e78`
- name: `?StateRequestSample@MkvMfSource@MkvMfSourceLib@@AEAA_NXZ`
- size: `840`
- prototype: `bool __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18001c244`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180011720`
- `0x180015014`
- `0x180015b5c`
- `0x180016840`
- `0x18001b8b0`
- `0x180020b30`
- `0x180021b58`
- `0x180021b9c`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020b65`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020b65`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020d03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020e43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020d03`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020e43`

## string_xrefs

- `0x180020e0e`: `MkvReader::AsyncReadCancel`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall MkvMfSourceLib::MkvMfSource::StateRequestSample(struct IMFAsyncCallback *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  struct CallStackContext *ThreadRelativeContext; // rsi
  int v4; // edi
  struct IMFAsyncCallback *v5; // r15
  struct IMFAsyncCallback *v6; // rsi
  char v7; // di
  struct IMFAsyncCallback *v8; // r12
  int v9; // eax
  bool HasRequests; // si
  bool v12; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v13[7]; // [rsp+31h] [rbp-2Fh] BYREF
  struct IMFAsyncCallback *v14; // [rsp+38h] [rbp-28h]
  MkvMfSourceLib::MkvMfSource *v15; // [rsp+40h] [rbp-20h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)&this[13];
  v14 = this + 13;
  EnterCriticalSection((LPCRITICAL_SECTION)&this[13]);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v13,
    "MkvMfSourceLib::MkvMfSource::StateRequestSample",
    1388);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && this[86].lpVtbl )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v4 = (*((__int64 (__fastcall **)(struct IMFAsyncCallbackVtbl *))this[86].lpVtbl->QueryInterface + 37))(this[86].lpVtbl);
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*((__int64 (__fastcall **)(struct IMFAsyncCallbackVtbl *, MkvMfSourceLib::MkvMfSource **))this[86].lpVtbl->QueryInterface
                                                           + 35))(
                                                            this[86].lpVtbl,
                                                            &v15);
    *((_DWORD *)ThreadRelativeContext + 504) = v4;
  }
  v15 = (MkvMfSourceLib::MkvMfSource *)this;
  v5 = this + 84;
  v6 = this + 84;
  v7 = 1;
  do
  {
    if ( !HIBYTE(this[60].lpVtbl) )
    {
      if ( LOBYTE(this[74].lpVtbl)
        && *((_QWORD *)this[52].lpVtbl[3].Release + 7) < *((_QWORD *)this[52].lpVtbl[3].Release + 1)
                                                       + *((_QWORD *)this[52].lpVtbl[3].Release + 2) )
      {
        HIBYTE(this[60].lpVtbl) = 1;
        MkvMfSourceLib::MkvMfSource::QueueOperation((MkvMfSourceLib::MkvMfSource *)this, this + 64);
      }
      v6 = this + 84;
    }
    if ( (__int64)this[50].lpVtbl >= 0 )
    {
      if ( (unsigned __int8)byte_1800DC8D3 < 4u )
        v5 = v6;
      else
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 152, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this);
      HasRequests = 0;
      v12 = 0;
      if ( v5->lpVtbl <= (struct IMFAsyncCallbackVtbl *)1 )
      {
        if ( BYTE4(this[60].lpVtbl) )
          HasRequests = MkvMfSourceLib::MkvMfSource::HasRequests((MkvMfSourceLib::MkvMfSource *)this);
      }
      else
      {
        if ( (int)MkvMfSourceLib::MkvMfSource::OnCommand((MkvMfSourceLib::MkvMfSource *)this, 1, &v12) < 0 )
        {
LABEL_28:
          LODWORD(this[65].lpVtbl) = 2;
          v7 = 0;
LABEL_37:
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v13);
          LeaveCriticalSection(v2);
          return v7;
        }
        HasRequests = v12;
      }
      if ( (unsigned __int8)byte_1800DC8D3 >= 4u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          153,
          &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
          this,
          HasRequests);
      if ( HasRequests )
      {
        CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v12, "MkvReader::AsyncReadCancel", 963);
        LOBYTE(this[24].lpVtbl) = 1;
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v12);
      }
      BYTE5(this[60].lpVtbl) = 0;
      goto LABEL_37;
    }
    if ( BYTE6(this[60].lpVtbl) )
    {
      if ( (unsigned __int8)byte_1800DC8D3 >= 4u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 154, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this);
      BYTE5(this[60].lpVtbl) = 0;
      goto LABEL_37;
    }
    v6 = this + 84;
    if ( this[84].lpVtbl > (struct IMFAsyncCallbackVtbl *)1
      && (int)MkvMfSourceLib::MkvMfSource::OnCommand((MkvMfSourceLib::MkvMfSource *)this, 0, 0) < 0 )
    {
      goto LABEL_28;
    }
    v8 = this + 65;
    v9 = MkvMfSourceLib::MkvMfSource::OnRequestSample(
           (MkvMfSourceLib::MkvMfSource *)this,
           (enum MkvMfSourceLib::MkvMfSource::OperationState *)&this[65]);
    if ( v9 < 0 )
    {
      MkvMfSourceLib::MkvMfSource::Error((MkvMfSourceLib::MkvMfSource *)this, L"Error processing samples.", v9);
      LODWORD(v8->lpVtbl) = 2;
    }
  }
  while ( LODWORD(v8->lpVtbl) == 1 );
  if ( (unsigned __int8)byte_1800DC8D3 >= 4u )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      155,
      &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
      this,
      v8->lpVtbl);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v13);
  LeaveCriticalSection(v2);
  return 0;
}

```

## disassembly

```asm
0x180020b30  mov     [rsp-28h+arg_8], rbx
0x180020b35  mov     [rsp-28h+arg_10], rsi
0x180020b3a  push    rbp
0x180020b3b  push    rdi
0x180020b3c  push    r12
0x180020b3e  push    r14
0x180020b40  push    r15
0x180020b42  mov     rbp, rsp
0x180020b45  sub     rsp, 60h
0x180020b49  mov     rax, cs:__security_cookie
0x180020b50  xor     rax, rsp
0x180020b53  mov     [rbp+var_10], rax
0x180020b57  mov     r14, rcx
0x180020b5a  lea     rbx, [rcx+68h]
0x180020b5e  mov     [rbp+var_28], rbx
0x180020b62  mov     rcx, rbx; lpCriticalSection
0x180020b65  call    cs:__imp_EnterCriticalSection
0x180020b6c  nop     dword ptr [rax+rax+00h]
0x180020b71  nop
0x180020b72  mov     r8d, 56Ch; int
0x180020b78  lea     rdx, aMkvmfsourcelib_22; "MkvMfSourceLib::MkvMfSource::StateReque"...
0x180020b7f  lea     rcx, [rbp+var_2F]; this
0x180020b83  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180020b88  nop
0x180020b89  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180020b90  cmp     byte ptr [rcx+8], 0
0x180020b94  jz      short loc_180020BF1
0x180020b96  cmp     qword ptr [r14+2B0h], 0
0x180020b9e  jz      short loc_180020BF1
0x180020ba0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180020ba5  mov     rsi, rax
0x180020ba8  mov     rdx, [r14+2B0h]
0x180020baf  mov     rcx, [rdx]
0x180020bb2  mov     rax, [rcx+128h]
0x180020bb9  mov     rcx, rdx
0x180020bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bc1  mov     edi, eax
0x180020bc3  mov     r8, [r14+2B0h]
0x180020bca  mov     rcx, [r8]
0x180020bcd  mov     rax, [rcx+118h]
0x180020bd4  lea     rdx, [rbp+var_20]
0x180020bd8  mov     rcx, r8
0x180020bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020be0  movups  xmm0, xmmword ptr [rax]
0x180020be3  movdqu  xmmword ptr [rsi+7D0h], xmm0
0x180020beb  mov     [rsi+7E0h], edi
0x180020bf1  mov     [rbp+var_20], r14
0x180020bf5  lea     r15, [r14+2A0h]
0x180020bfc  mov     rsi, r15
0x180020bff  mov     edi, 1
0x180020c04  cmp     byte ptr [r14+1E7h], 0
0x180020c0c  jnz     short loc_180020C4D
0x180020c0e  cmp     byte ptr [r14+250h], 0
0x180020c16  jz      short loc_180020C4A
0x180020c18  mov     rax, [r14+1A0h]
0x180020c1f  mov     rcx, [rax+88h]
0x180020c26  mov     rax, [rcx+10h]
0x180020c2a  add     rax, [rcx+8]
0x180020c2e  cmp     [rcx+38h], rax
0x180020c32  jge     short loc_180020C4A
0x180020c34  mov     [r14+1E7h], dil
0x180020c3b  lea     rdx, [r14+200h]; struct IMFAsyncCallback *
0x180020c42  mov     rcx, r14; this
0x180020c45  call    ?QueueOperation@MkvMfSource@MkvMfSourceLib@@AEAAJPEAUIMFAsyncCallback@@@Z; MkvMfSourceLib::MkvMfSource::QueueOperation(IMFAsyncCallback *)
0x180020c4a  mov     rsi, r15
0x180020c4d  cmp     qword ptr [r14+190h], 0
0x180020c55  jge     loc_180020D4E
0x180020c5b  cmp     byte ptr [r14+1E6h], 0
0x180020c63  jnz     loc_180020D16
0x180020c69  lea     rsi, [r14+2A0h]
0x180020c70  cmp     [rsi], rdi
0x180020c73  jbe     short loc_180020C8A
0x180020c75  xor     r8d, r8d; bool *
0x180020c78  xor     edx, edx; bool
0x180020c7a  mov     rcx, r14; this
0x180020c7d  call    ?OnCommand@MkvMfSource@MkvMfSourceLib@@AEAAJ_NPEA_N@Z; MkvMfSourceLib::MkvMfSource::OnCommand(bool,bool *)
0x180020c82  test    eax, eax
0x180020c84  js      loc_180020D9D
0x180020c8a  lea     r12, [r14+208h]
0x180020c91  mov     rdx, r12; enum MkvMfSourceLib::MkvMfSource::OperationState *
0x180020c94  mov     rcx, r14; this
0x180020c97  call    ?OnRequestSample@MkvMfSource@MkvMfSourceLib@@AEAAJPEAW4OperationState@12@@Z; MkvMfSourceLib::MkvMfSource::OnRequestSample(MkvMfSourceLib::MkvMfSource::OperationState *)
0x180020c9c  test    eax, eax
0x180020c9e  jns     short loc_180020CBA
0x180020ca0  mov     r8d, eax; int
0x180020ca3  lea     rdx, aErrorProcessin; "Error processing samples."
0x180020caa  mov     rcx, r14; this
0x180020cad  call    ?Error@MkvMfSource@MkvMfSourceLib@@AEAAJPEBGJ@Z; MkvMfSourceLib::MkvMfSource::Error(ushort const *,long)
0x180020cb2  mov     dword ptr [r12], 2
0x180020cba  mov     eax, [r12]
0x180020cbe  cmp     eax, edi
0x180020cc0  jz      loc_180020C04
0x180020cc6  cmp     cs:byte_1800DC8D3, 4
0x180020ccd  jb      short loc_180020CF6
0x180020ccf  mov     edx, 9Bh
0x180020cd4  mov     [rsp+60h+var_40], eax
0x180020cd8  mov     r9, r14
0x180020cdb  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180020ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ce9  mov     rcx, [rcx+88h]
0x180020cf0  call    WPP_SF_qD
0x180020cf5  nop
0x180020cf6  lea     rcx, [rbp+var_2F]; this
0x180020cfa  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180020cff  nop
0x180020d00  mov     rcx, rbx; lpCriticalSection
0x180020d03  call    cs:__imp_LeaveCriticalSection
0x180020d0a  nop     dword ptr [rax+rax+00h]
0x180020d0f  xor     al, al
0x180020d11  jmp     loc_180020E52
0x180020d16  cmp     cs:byte_1800DC8D3, 4
0x180020d1d  jb      short loc_180020D41
0x180020d1f  mov     edx, 9Ah
0x180020d24  mov     r9, r14
0x180020d27  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180020d2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d35  mov     rcx, [rcx+88h]
0x180020d3c  call    WPP_SF_q
0x180020d41  mov     byte ptr [r14+1E5h], 0
0x180020d49  jmp     loc_180020E36
0x180020d4e  cmp     cs:byte_1800DC8D3, 4
0x180020d55  jb      short loc_180020D7B
0x180020d57  mov     edx, 98h
0x180020d5c  mov     r9, r14
0x180020d5f  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180020d66  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d6d  mov     rcx, [rcx+88h]
0x180020d74  call    WPP_SF_q
0x180020d79  jmp     short loc_180020D7E
0x180020d7b  mov     r15, rsi
0x180020d7e  xor     sil, sil
0x180020d81  mov     [rbp+var_30], sil
0x180020d85  cmp     [r15], rdi
0x180020d88  jbe     short loc_180020DB6
0x180020d8a  lea     r8, [rbp+var_30]; bool *
0x180020d8e  mov     dl, dil; bool
0x180020d91  mov     rcx, r14; this
0x180020d94  call    ?OnCommand@MkvMfSource@MkvMfSourceLib@@AEAAJ_NPEA_N@Z; MkvMfSourceLib::MkvMfSource::OnCommand(bool,bool *)
0x180020d99  test    eax, eax
0x180020d9b  jns     short loc_180020DB0
0x180020d9d  mov     dword ptr [r14+208h], 2
0x180020da8  xor     dil, dil
0x180020dab  jmp     loc_180020E36
0x180020db0  mov     sil, [rbp+var_30]
0x180020db4  jmp     short loc_180020DD0
0x180020db6  cmp     [r14+1E4h], sil
0x180020dbd  jz      short loc_180020DD0
0x180020dbf  mov     rcx, r14; this
0x180020dc2  call    ?HasRequests@MkvMfSource@MkvMfSourceLib@@AEAA_NXZ; MkvMfSourceLib::MkvMfSource::HasRequests(void)
0x180020dc7  movzx   esi, sil
0x180020dcb  test    al, al
0x180020dcd  cmovnz  esi, edi
0x180020dd0  cmp     cs:byte_1800DC8D3, 4
0x180020dd7  jb      short loc_180020E03
0x180020dd9  movzx   eax, sil
0x180020ddd  mov     edx, 99h
0x180020de2  mov     [rsp+60h+var_40], eax
0x180020de6  mov     r9, r14
0x180020de9  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180020df0  mov     rcx, cs:WPP_GLOBAL_Control
0x180020df7  mov     rcx, [rcx+88h]
0x180020dfe  call    WPP_SF_qD
0x180020e03  test    sil, sil
0x180020e06  jz      short loc_180020E2E
0x180020e08  mov     r8d, 3C3h; int
0x180020e0e  lea     rdx, aMkvreaderAsync; "MkvReader::AsyncReadCancel"
0x180020e15  lea     rcx, [rbp+var_30]; this
0x180020e19  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180020e1e  mov     [r14+0C0h], dil
0x180020e25  lea     rcx, [rbp+var_30]; this
0x180020e29  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180020e2e  mov     byte ptr [r14+1E5h], 0
0x180020e36  lea     rcx, [rbp+var_2F]; this
0x180020e3a  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180020e3f  nop
0x180020e40  mov     rcx, rbx; lpCriticalSection
0x180020e43  call    cs:__imp_LeaveCriticalSection
0x180020e4a  nop     dword ptr [rax+rax+00h]
0x180020e4f  mov     al, dil
0x180020e52  mov     rcx, [rbp+var_10]
0x180020e56  xor     rcx, rsp; StackCookie
0x180020e59  call    __security_check_cookie
0x180020e5e  lea     r11, [rsp+60h+var_s0]
0x180020e63  mov     rbx, [r11+38h]
0x180020e67  mov     rsi, [r11+40h]
0x180020e6b  mov     rsp, r11
0x180020e6e  pop     r15
0x180020e70  pop     r14
0x180020e72  pop     r12
0x180020e74  pop     rdi
0x180020e75  pop     rbp
0x180020e76  retn
```
