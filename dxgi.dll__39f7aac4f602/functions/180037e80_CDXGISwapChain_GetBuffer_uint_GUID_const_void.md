# CDXGISwapChain::GetBuffer(uint,_GUID const &,void * *)

- ea: `0x180037e80`
- end: `0x18003821c`
- name: `?GetBuffer@CDXGISwapChain@@UEAAJIAEBU_GUID@@PEAPEAX@Z`
- size: `924`
- prototype: `__int64 __fastcall(CDXGISwapChain *__hidden this, unsigned int, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800983f0`

## callees

- `0x18000c6b0`
- `0x18000ce70`
- `0x180037e80`
- `0x180038224`
- `0x180038288`
- `0x180075fa0`
- `0x1800cb010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180037ffa`
- `ntdll!EtwEventWrite` at `0x1800380ab`
- `ntdll!EtwEventWrite` at `0x180038123`
- `ntdll!EtwEventWrite` at `0x180037ffa`
- `ntdll!EtwEventWrite` at `0x1800380ab`
- `ntdll!EtwEventWrite` at `0x180038123`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDXGISwapChain::GetBuffer(
        struct IDXGIDebugProducer **this,
        unsigned int a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v6; // edi
  char *v8; // rsi
  __int64 v9; // rcx
  __int64 (__fastcall ***v10)(_QWORD, const struct _GUID *, void **); // rcx
  __int64 v11; // rax
  unsigned int v12; // eax
  CModule *v13; // rcx
  bool v14; // r9
  unsigned int v15; // ebx
  CModule *v16; // rcx
  bool v17; // r9
  CModule *v19; // rcx
  bool v20; // r9
  bool v21; // zf
  CModule *v22; // rcx
  bool v23; // r9
  CModule *v24; // rcx
  bool v25; // r9
  void (*v26)(void); // rax
  CModule *v27; // rcx
  bool v28; // r9
  char v29[4]; // [rsp+20h] [rbp-59h] BYREF
  int v30; // [rsp+24h] [rbp-55h] BYREF
  unsigned int v31; // [rsp+28h] [rbp-51h] BYREF
  struct IDXGIDebugProducer **v32; // [rsp+30h] [rbp-49h] BYREF
  int *v33; // [rsp+38h] [rbp-41h] BYREF
  __int64 v34; // [rsp+40h] [rbp-39h]
  _QWORD v35[6]; // [rsp+50h] [rbp-29h] BYREF
  void **v36; // [rsp+80h] [rbp+7h]
  __int64 v37; // [rsp+88h] [rbp+Fh]

  v6 = a2;
  v31 = a2;
  v32 = this;
  v29[0] = 0;
  if ( dword_180108134
    && (qword_180108120 & 0x4000000000000000LL) != 0
    && (qword_180108128 & 0x4000000000000000LL) == qword_180108128 )
  {
    v29[0] = 1;
    v35[0] = &v32;
    v35[1] = 8;
    v35[2] = &v31;
    v35[3] = 4;
    v35[4] = a3;
    v35[5] = 16;
    v37 = 8;
    if ( a4 )
      v36 = a4;
    else
      v36 = (void **)&v33;
    EtwEventWrite(DXGIEtwProviderGuid_Context, IDXGISwapChain_GetBuffer_Start, 4, v35);
  }
  if ( a4 )
  {
    *a4 = 0;
    v8 = (char *)(this + 17);
    if ( !this )
      v8 = 0;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 + 1) + 24LL))(*((_QWORD *)v8 + 1));
    if ( !this[220] )
    {
      DXGI_SDK_MSG_SWAPCHAIN(this[38], DXGI_MSG_IDXGISwapChain_GetBuffer_NoAllocatedBuffers);
      CModule::RecordJournalImpl(v24, 0x887A0001, "Non-zero return value", v25);
      v30 = -2005270527;
      if ( !v8 )
      {
LABEL_40:
        CETWEvent_IDXGISwapChain_GetBuffer::~CETWEvent_IDXGISwapChain_GetBuffer((CETWEvent_IDXGISwapChain_GetBuffer *)v29);
        return 2289696769LL;
      }
      v26 = *(void (**)(void))(**((_QWORD **)v8 + 1) + 32LL);
LABEL_39:
      v26();
      goto LABEL_40;
    }
    if ( v6 && !(unsigned __int8)CDXGISwapChain::IsSequential<1>(this) && *((char *)this + 288) >= 0 )
    {
      DXGI_SDK_MSG_SWAPCHAIN(this[38], DXGI_MSG_IDXGISwapChain_GetBuffer_iBufferMustBeZero);
      CModule::RecordJournalImpl(v27, 0x887A0001, "Non-zero return value", v28);
      v30 = -2005270527;
      if ( !v8 )
        goto LABEL_40;
      v26 = *(void (**)(void))(**((_QWORD **)v8 + 1) + 32LL);
      goto LABEL_39;
    }
    if ( v6 < *((_DWORD *)this + 105) )
    {
      if ( ((_DWORD)this[36] & 0x80) != 0 )
        v6 = (*((_DWORD *)this + 1141) + v6 - *((_DWORD *)this + 310)) % *((_DWORD *)this + 1141);
      if ( v6 >= *((_DWORD *)this + 529) )
      {
        v9 = 1896;
      }
      else
      {
        _mm_lfence();
        v9 = 8LL * v6 + 1760;
      }
      v10 = *(__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))((char *)this + v9);
      if ( ((_DWORD)this[36] & 0x80) != 0 )
      {
        v11 = (__int64)(v10 + 9);
        if ( !v10 )
          v11 = 80;
        v10 = *(__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))v11;
      }
      v12 = (**v10)(v10, a3, a4);
      v15 = v12;
      if ( v12 )
      {
        CModule::RecordJournalImpl(v13, v12, "Non-zero return value", v14);
        if ( v15 != -2147467262 && v15 != -2005270527 )
          CModule::RecordJournalImpl(v16, v15, "Contract breached!", v17);
      }
      v30 = v15;
      if ( v8 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 + 1) + 32LL))(*((_QWORD *)v8 + 1));
      if ( v29[0] )
      {
        v33 = &v30;
        v34 = 4;
        EtwEventWrite(DXGIEtwProviderGuid_Context, IDXGISwapChain_GetBuffer_Stop, 1, &v33);
      }
      return v15;
    }
    DXGI_SDK_MSG_SWAPCHAIN(this[38], DXGI_MSG_IDXGISwapChain_GetBuffer_iBufferOOB);
    CModule::RecordJournalImpl(v19, 0x887A0001, "Non-zero return value", v20);
    v30 = -2005270527;
    if ( v8 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v8 + 1) + 32LL))(*((_QWORD *)v8 + 1));
    v21 = v29[0] == 0;
  }
  else
  {
    DXGI_SDK_MSG_SWAPCHAIN(this[38], DXGI_MSG_IDXGISwapChain_GetBuffer_ppSurfaceIsNULL);
    CModule::RecordJournalImpl(v22, 0x887A0001, "Non-zero return value", v23);
    v21 = v29[0] == 0;
  }
  if ( !v21 )
  {
    v33 = &v30;
    v34 = 4;
    EtwEventWrite(DXGIEtwProviderGuid_Context, IDXGISwapChain_GetBuffer_Stop, 1, &v33);
  }
  return 2289696769LL;
}

```

## disassembly

```asm
0x180037e80  push    rbp
0x180037e82  push    rbx
0x180037e83  push    rsi
0x180037e84  push    rdi
0x180037e85  push    r12
0x180037e87  push    r14
0x180037e89  push    r15
0x180037e8b  lea     rbp, [rsp-27h]
0x180037e90  sub     rsp, 0A0h
0x180037e97  mov     rax, cs:__security_cookie
0x180037e9e  xor     rax, rsp
0x180037ea1  mov     [rbp+57h+var_40], rax
0x180037ea5  mov     r14, r9
0x180037ea8  mov     r15, r8
0x180037eab  mov     edi, edx
0x180037ead  mov     rbx, rcx
0x180037eb0  mov     [rbp+57h+var_A8], edx
0x180037eb3  mov     [rbp+57h+var_A0], rcx
0x180037eb7  mov     [rbp+57h+var_B0], 0
0x180037ebb  xor     r12d, r12d
0x180037ebe  cmp     cs:dword_180108134, r12d
0x180037ec5  jnz     loc_180038020
0x180037ecb  test    r14, r14
0x180037ece  jz      loc_180038133
0x180037ed4  mov     [r14], r12
0x180037ed7  lea     rsi, [rbx+88h]
0x180037ede  test    rbx, rbx
0x180037ee1  cmovz   rsi, r12
0x180037ee5  mov     rcx, [rsi+8]
0x180037ee9  mov     rax, [rcx]
0x180037eec  mov     rax, [rax+18h]
0x180037ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037ef5  cmp     [rbx+6E0h], r12
0x180037efc  jz      loc_18003815B
0x180037f02  test    edi, edi
0x180037f04  jnz     loc_1800381AD
0x180037f0a  cmp     edi, [rbx+1A4h]
0x180037f10  jnb     loc_1800380B6
0x180037f16  mov     r8d, [rbx+120h]
0x180037f1d  and     r8d, 80h
0x180037f24  jz      short loc_180037F3B
0x180037f26  mov     ecx, [rbx+11D4h]
0x180037f2c  sub     edi, [rbx+4D8h]
0x180037f32  lea     eax, [rcx+rdi]
0x180037f35  xor     edx, edx
0x180037f37  div     ecx
0x180037f39  mov     edi, edx
0x180037f3b  cmp     edi, [rbx+844h]
0x180037f41  jnb     loc_180038212
0x180037f47  lfence
0x180037f4a  mov     eax, edi
0x180037f4c  lea     rcx, ds:6E0h[rax*8]
0x180037f54  mov     rcx, [rcx+rbx]
0x180037f58  test    r8d, r8d
0x180037f5b  jz      short loc_180037F70
0x180037f5d  lea     rax, [rcx+48h]
0x180037f61  mov     edx, 50h ; 'P'
0x180037f66  test    rcx, rcx
0x180037f69  cmovz   rax, rdx
0x180037f6d  mov     rcx, [rax]
0x180037f70  mov     rax, [rcx]
0x180037f73  mov     r8, r14
0x180037f76  mov     rdx, r15
0x180037f79  mov     rax, [rax]
0x180037f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f81  mov     ebx, eax
0x180037f83  test    eax, eax
0x180037f85  jz      short loc_180037FB3
0x180037f87  lea     r8, aNonZeroReturnV; "Non-zero return value"
0x180037f8e  mov     edx, eax; unsigned int
0x180037f90  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180037f95  cmp     ebx, 80004002h
0x180037f9b  jz      short loc_180037FB3
0x180037f9d  cmp     ebx, 887A0001h
0x180037fa3  jz      short loc_180037FB3
0x180037fa5  lea     r8, aContractBreach; "Contract breached!"
0x180037fac  mov     edx, ebx; unsigned int
0x180037fae  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180037fb3  mov     [rbp+57h+var_AC], ebx
0x180037fb6  test    rsi, rsi
0x180037fb9  jz      short loc_180037FCC
0x180037fbb  mov     rcx, [rsi+8]
0x180037fbf  mov     rax, [rcx]
0x180037fc2  mov     rax, [rax+20h]
0x180037fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037fcb  nop
0x180037fcc  cmp     [rbp+57h+var_B0], 0
0x180037fd0  jz      short loc_180038000
0x180037fd2  lea     rax, [rbp+57h+var_AC]
0x180037fd6  mov     [rbp+57h+var_98], rax
0x180037fda  mov     [rbp+57h+var_90], 4
0x180037fe2  lea     r9, [rbp+57h+var_98]
0x180037fe6  mov     r8d, 1
0x180037fec  lea     rdx, IDXGISwapChain_GetBuffer_Stop
0x180037ff3  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x180037ffa  call    cs:__imp_EtwEventWrite
0x180038000  mov     eax, ebx
0x180038002  mov     rcx, [rbp+57h+var_40]
0x180038006  xor     rcx, rsp; StackCookie
0x180038009  call    __security_check_cookie
0x18003800e  add     rsp, 0A0h
0x180038015  pop     r15
0x180038017  pop     r14
0x180038019  pop     r12
0x18003801b  pop     rdi
0x18003801c  pop     rsi
0x18003801d  pop     rbx
0x18003801e  pop     rbp
0x18003801f  retn
0x180038020  mov     rdx, 4000000000000000h
0x18003802a  test    cs:qword_180108120, rdx
0x180038031  jz      loc_180037ECB
0x180038037  mov     rax, cs:qword_180108128
0x18003803e  and     rax, rdx
0x180038041  cmp     rax, cs:qword_180108128
0x180038048  jnz     loc_180037ECB
0x18003804e  mov     [rbp+57h+var_B0], 1
0x180038052  lea     rax, [rbp+57h+var_A0]
0x180038056  mov     [rbp+57h+var_80], rax
0x18003805a  mov     [rbp+57h+var_78], 8
0x180038062  lea     rax, [rbp+57h+var_A8]
0x180038066  mov     [rbp+57h+var_70], rax
0x18003806a  mov     [rbp+57h+var_68], 4
0x180038072  mov     [rbp+57h+var_60], r15
0x180038076  mov     [rbp+57h+var_58], 10h
0x18003807e  mov     [rbp+57h+var_48], 8
0x180038086  test    r14, r14
0x180038089  jz      loc_180038205
0x18003808f  mov     [rbp+57h+var_50], r14
0x180038093  lea     r9, [rbp+57h+var_80]
0x180038097  mov     r8d, 4
0x18003809d  lea     rdx, IDXGISwapChain_GetBuffer_Start
0x1800380a4  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x1800380ab  call    cs:__imp_EtwEventWrite
0x1800380b1  jmp     loc_180037ECB
0x1800380b6  mov     edx, 0Ch; enum DXGI_Message_Id
0x1800380bb  mov     rcx, [rbx+130h]; struct IDXGIDebugProducer *
0x1800380c2  call    ?DXGI_SDK_MSG_SWAPCHAIN@@YAXPEAUIDXGIDebugProducer@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG_SWAPCHAIN(IDXGIDebugProducer *,DXGI_Message_Id,...)
0x1800380c7  lea     r8, aNonZeroReturnV; "Non-zero return value"
0x1800380ce  mov     edx, 887A0001h; unsigned int
0x1800380d3  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800380d8  mov     [rbp+57h+var_AC], 887A0001h
0x1800380df  test    rsi, rsi
0x1800380e2  jz      short loc_1800380F5
0x1800380e4  mov     rcx, [rsi+8]
0x1800380e8  mov     rax, [rcx]
0x1800380eb  mov     rax, [rax+20h]
0x1800380ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380f4  nop
0x1800380f5  cmp     [rbp+57h+var_B0], 0
0x1800380f9  jz      short loc_180038129
0x1800380fb  lea     rax, [rbp+57h+var_AC]
0x1800380ff  mov     [rbp+57h+var_98], rax
0x180038103  mov     [rbp+57h+var_90], 4
0x18003810b  lea     r9, [rbp+57h+var_98]
0x18003810f  mov     r8d, 1
0x180038115  lea     rdx, IDXGISwapChain_GetBuffer_Stop
0x18003811c  mov     rcx, cs:DXGIEtwProviderGuid_Context
0x180038123  call    cs:__imp_EtwEventWrite
0x180038129  mov     eax, 887A0001h
0x18003812e  jmp     loc_180038002
0x180038133  mov     edx, 9; enum DXGI_Message_Id
0x180038138  mov     rcx, [rbx+130h]; struct IDXGIDebugProducer *
0x18003813f  call    ?DXGI_SDK_MSG_SWAPCHAIN@@YAXPEAUIDXGIDebugProducer@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG_SWAPCHAIN(IDXGIDebugProducer *,DXGI_Message_Id,...)
0x180038144  lea     r8, aNonZeroReturnV; "Non-zero return value"
0x18003814b  mov     edx, 887A0001h; unsigned int
0x180038150  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180038155  cmp     [rbp+57h+var_B0], r12b
0x180038159  jmp     short loc_1800380F9
0x18003815b  mov     edx, 0Ah; enum DXGI_Message_Id
0x180038160  mov     rcx, [rbx+130h]; struct IDXGIDebugProducer *
0x180038167  call    ?DXGI_SDK_MSG_SWAPCHAIN@@YAXPEAUIDXGIDebugProducer@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG_SWAPCHAIN(IDXGIDebugProducer *,DXGI_Message_Id,...)
0x18003816c  lea     r8, aNonZeroReturnV; "Non-zero return value"
0x180038173  mov     edx, 887A0001h; unsigned int
0x180038178  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18003817d  mov     [rbp+57h+var_AC], 887A0001h
0x180038184  test    rsi, rsi
0x180038187  jz      short loc_18003819A
0x180038189  mov     rcx, [rsi+8]
0x18003818d  mov     rax, [rcx]
0x180038190  mov     rax, [rax+20h]
0x180038194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038199  nop
0x18003819a  lea     rcx, [rbp+57h+var_B0]; this
0x18003819e  call    ??1CETWEvent_IDXGISwapChain_GetBuffer@@QEAA@XZ; CETWEvent_IDXGISwapChain_GetBuffer::~CETWEvent_IDXGISwapChain_GetBuffer(void)
0x1800381a3  mov     eax, 887A0001h
0x1800381a8  jmp     loc_180038002
0x1800381ad  mov     rcx, rbx
0x1800381b0  call    ??$IsSequential@$00@CDXGISwapChain@@QEBA_NXZ; CDXGISwapChain::IsSequential<1>(void)
0x1800381b5  test    al, al
0x1800381b7  jnz     loc_180037F0A
0x1800381bd  test    byte ptr [rbx+120h], 80h
0x1800381c4  jnz     loc_180037F0A
0x1800381ca  mov     edx, 0Bh; enum DXGI_Message_Id
0x1800381cf  mov     rcx, [rbx+130h]; struct IDXGIDebugProducer *
0x1800381d6  call    ?DXGI_SDK_MSG_SWAPCHAIN@@YAXPEAUIDXGIDebugProducer@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG_SWAPCHAIN(IDXGIDebugProducer *,DXGI_Message_Id,...)
0x1800381db  lea     r8, aNonZeroReturnV; "Non-zero return value"
0x1800381e2  mov     edx, 887A0001h; unsigned int
0x1800381e7  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x1800381ec  mov     [rbp+57h+var_AC], 887A0001h
0x1800381f3  test    rsi, rsi
0x1800381f6  jz      short loc_18003819A
0x1800381f8  mov     rcx, [rsi+8]
0x1800381fc  mov     rdx, [rcx]
0x1800381ff  mov     rax, [rdx+20h]
0x180038203  jmp     short loc_180038194
0x180038205  lea     rax, [rbp+57h+var_98]
0x180038209  mov     [rbp+57h+var_50], rax
0x18003820d  jmp     loc_180038093
0x180038212  mov     ecx, 768h
0x180038217  jmp     loc_180037F54
```
