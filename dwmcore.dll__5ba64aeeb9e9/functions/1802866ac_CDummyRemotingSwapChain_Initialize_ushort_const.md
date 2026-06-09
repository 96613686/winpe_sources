# CDummyRemotingSwapChain::Initialize(ushort const *)

- ea: `0x1802866ac`
- end: `0x180286853`
- name: `?Initialize@CDummyRemotingSwapChain@@IEAAJPEBG@Z`
- size: `423`
- prototype: `__int64 __fastcall(CDummyRemotingSwapChain *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180286174`

## callees

- `0x18001dfb0`
- `0x180050270`
- `0x18015adb4`
- `0x18022945c`
- `0x1802866ac`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802866d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802866d0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802867bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802867dd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802867bf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1802867dd`

## string_xrefs

- `0x1802866c9`: `DwmIndirectCreate`

## pseudocode

```c
__int64 __fastcall CDummyRemotingSwapChain::Initialize(HMODULE *this, const unsigned __int16 *a2)
{
  FARPROC ProcAddress; // rbx
  int v5; // eax
  unsigned int v6; // edi
  __int64 (__fastcall ***v7)(_QWORD, _QWORD, _QWORD); // rdi
  _QWORD *v8; // r14
  __int64 (__fastcall *v9)(_QWORD, GUID *, HMODULE *); // rbx
  __int64 v10; // rcx
  HANDLE EventW; // rax
  HANDLE v12; // rax
  int v13; // r9d
  unsigned int v15; // [rsp+20h] [rbp-49h]
  __int128 v16; // [rsp+30h] [rbp-39h] BYREF
  const unsigned __int16 *v17; // [rsp+40h] [rbp-29h]
  __int64 v18; // [rsp+48h] [rbp-21h]
  __int64 v19; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v20[104]; // [rsp+58h] [rbp-11h] BYREF

  ProcAddress = GetProcAddress(this[8], "DwmIndirectCreate");
  if ( !ProcAddress )
  {
    v6 = -2147024809;
    v13 = -2147024809;
    v15 = 92;
    goto LABEL_11;
  }
  v17 = a2;
  v16 = 0;
  v18 = 0;
  wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(this + 9);
  v5 = ((__int64 (__fastcall *)(__int128 *, HMODULE *))ProcAddress)(&v16, this + 9);
  v6 = v5;
  if ( v5 < 0 )
  {
    v15 = 66;
    goto LABEL_8;
  }
  v7 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))this[9];
  v8 = this + 10;
  v9 = (__int64 (__fastcall *)(_QWORD, GUID *, HMODULE *))**v7;
  wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(this + 10);
  v5 = v9(v7, &IID_IDWMRemotingIndirectEx, this + 10);
  v6 = v5;
  if ( v5 < 0 )
  {
    v15 = 69;
LABEL_8:
    v13 = v5;
LABEL_11:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v13, v15, 0);
    return v6;
  }
  v19 = 7;
  memset_0(v20, 0, 0x40u);
  (*(void (__fastcall **)(_QWORD, __int64 *, __int64))(*(_QWORD *)*v8 + 56LL))(*v8, &v19, 1);
  if ( *((_BYTE *)g_pComposition + 808) )
  {
    v10 = *v8;
    LODWORD(v19) = 11;
    v20[8] = 1;
    (*(void (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v10 + 56LL))(v10, &v19, 1);
  }
  EventW = CreateEventW(0, 1, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    this + 13,
    EventW);
  v12 = CreateEventW(0, 1, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    this + 25,
    v12);
  return v6;
}

```

## disassembly

```asm
0x1802866ac  push    rbp
0x1802866ae  push    rbx
0x1802866af  push    rsi
0x1802866b0  push    rdi
0x1802866b1  push    r14
0x1802866b3  lea     rbp, [rsp-37h]
0x1802866b8  sub     rsp, 0A0h
0x1802866bf  mov     rdi, rdx
0x1802866c2  mov     rsi, rcx
0x1802866c5  mov     rcx, [rcx+40h]; hModule
0x1802866c9  lea     rdx, aDwmindirectcre; "DwmIndirectCreate"
0x1802866d0  call    cs:__imp_GetProcAddress
0x1802866d6  mov     rbx, rax
0x1802866d9  test    rax, rax
0x1802866dc  jz      loc_18028681D
0x1802866e2  xorps   xmm0, xmm0
0x1802866e5  mov     [rbp+57h+var_80], rdi
0x1802866e9  lea     r14, [rsi+48h]
0x1802866ed  movdqa  [rbp+57h+var_90], xmm0
0x1802866f2  mov     rcx, r14
0x1802866f5  mov     [rbp+57h+var_78], 0
0x1802866fd  call    ?reset@?$com_ptr_t@UIDXGISwapChain1@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(void)
0x180286702  mov     rdx, r14
0x180286705  lea     rcx, [rbp+57h+var_90]
0x180286709  mov     rax, rbx
0x18028670c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180286711  mov     edi, eax
0x180286713  test    eax, eax
0x180286715  js      loc_18028680A
0x18028671b  mov     rdi, [r14]
0x18028671e  lea     r14, [rsi+50h]
0x180286722  mov     rcx, r14
0x180286725  mov     rax, [rdi]
0x180286728  mov     rbx, [rax]
0x18028672b  call    ?reset@?$com_ptr_t@UIDXGISwapChain1@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IDXGISwapChain1,wil::err_returncode_policy>::reset(void)
0x180286730  mov     r8, r14
0x180286733  lea     rdx, IID_IDWMRemotingIndirectEx
0x18028673a  mov     rcx, rdi
0x18028673d  mov     rax, rbx
0x180286740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180286745  mov     edi, eax
0x180286747  test    eax, eax
0x180286749  js      loc_1802867F4
0x18028674f  xor     edx, edx; Val
0x180286751  mov     [rbp+57h+var_70], 7
0x180286759  lea     rcx, [rbp+57h+var_68]; void *
0x18028675d  lea     r8d, [rdx+40h]; Size
0x180286761  call    memset_0
0x180286766  mov     rcx, [r14]
0x180286769  lea     rdx, [rbp+57h+var_70]
0x18028676d  mov     r8d, 1
0x180286773  mov     rax, [rcx]
0x180286776  mov     rax, [rax+38h]
0x18028677a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18028677f  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x180286786  cmp     byte ptr [rax+328h], 0
0x18028678d  jz      short loc_1802867B3
0x18028678f  mov     rcx, [r14]
0x180286792  lea     rdx, [rbp+57h+var_70]
0x180286796  mov     dword ptr [rbp+57h+var_70], 0Bh
0x18028679d  mov     r8d, 1
0x1802867a3  mov     [rbp+57h+var_60], 1
0x1802867a7  mov     rax, [rcx]
0x1802867aa  mov     rax, [rax+38h]
0x1802867ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802867b3  xor     r9d, r9d; lpName
0x1802867b6  xor     r8d, r8d; bInitialState
0x1802867b9  xor     ecx, ecx; lpEventAttributes
0x1802867bb  lea     edx, [r9+1]; bManualReset
0x1802867bf  call    cs:__imp_CreateEventW
0x1802867c5  mov     rdx, rax
0x1802867c8  lea     rcx, [rsi+68h]
0x1802867cc  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802867d1  xor     r9d, r9d; lpName
0x1802867d4  xor     r8d, r8d; bInitialState
0x1802867d7  xor     ecx, ecx; lpEventAttributes
0x1802867d9  lea     edx, [r9+1]; bManualReset
0x1802867dd  call    cs:__imp_CreateEventW
0x1802867e3  mov     rdx, rax
0x1802867e6  lea     rcx, [rsi+0C8h]
0x1802867ed  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1802867f2  jmp     short loc_180286843
0x1802867f4  mov     [rsp+0C0h+var_98], 0
0x1802867fd  mov     [rsp+0C0h+var_A0], 45h ; 'E'
0x180286805  mov     r9d, eax
0x180286808  jmp     short loc_180286836
0x18028680a  mov     [rsp+0C0h+var_98], 0
0x180286813  mov     [rsp+0C0h+var_A0], 42h ; 'B'
0x18028681b  jmp     short loc_180286805
0x18028681d  mov     edi, 80070057h
0x180286822  mov     [rsp+0C0h+var_98], 0; void *
0x18028682b  mov     r9d, edi; int
0x18028682e  mov     [rsp+0C0h+var_A0], 5Ch ; '\'; unsigned int
0x180286836  xor     edx, edx; int *
0x180286838  xor     r8d, r8d; unsigned int
0x18028683b  lea     ecx, [rdx+14h]; unsigned int
0x18028683e  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180286843  mov     eax, edi
0x180286845  add     rsp, 0A0h
0x18028684c  pop     r14
0x18028684e  pop     rdi
0x18028684f  pop     rsi
0x180286850  pop     rbx
0x180286851  pop     rbp
0x180286852  retn
```
