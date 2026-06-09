# GetProtocolLaunchParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)

- ea: `0x1800b84ec`
- end: `0x1800b89fc`
- name: `?GetProtocolLaunchParameters@@YA_NPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@AEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z`
- size: `1296`
- prototype: `bool(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, struct StateRepository::Cache::Manager_NoThrow *, __int64, struct ActivationProperties *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b6398`

## callees

- `0x1800053a0`
- `0x18000c37c`
- `0x18000e234`
- `0x180010a84`
- `0x180011300`
- `0x180011820`
- `0x180011a64`
- `0x1800b17ac`
- `0x1800b3c14`
- `0x1800b5598`
- `0x1800b5f44`
- `0x1800b84ec`
- `0x1800b9c4c`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8590`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b862a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8779`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b878f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b88c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b88d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8590`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b862a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b8779`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b878f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b88c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b88d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b85cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b8666`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b85cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b8666`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b874c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b8767`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b8894`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b88af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b874c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b8767`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b8894`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800b88af`

## string_xrefs

- `0x1800b8834`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800b8949`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b895e`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b8973`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b8988`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b899d`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b89b2`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b89d5`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b89ea`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
bool __fastcall GetProtocolLaunchParameters(
        struct Windows::ApplicationModel::Activation::IActivatedEventArgs *a1,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3,
        struct ActivationProperties *a4)
{
  int v7; // eax
  int v8; // eax
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rdi
  int v11; // eax
  PCWSTR StringRawBuffer; // rax
  _QWORD *v13; // rsi
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rdi
  int v16; // eax
  PCWSTR v17; // rax
  const unsigned __int16 *v18; // rbx
  char *v19; // r8
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  unsigned int v26; // eax
  int v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+40h] [rbp-C0h]
  UINT32 length; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v31; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v34; // [rsp+68h] [rbp-98h]
  __int128 v35; // [rsp+78h] [rbp-88h]
  __int128 v36; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v37; // [rsp+F0h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v30 = 0;
  v7 = (**(__int64 (__fastcall ***)(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, GUID *, __int64 *))a1)(
         a1,
         &GUID_6095f4dd_b7c0_46ab_81fe_d90f36d00d24,
         &v30);
  if ( v7 != -2147467262 )
  {
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x302,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v7,
        v27);
    v33 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 48LL))(v30, &v33);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x305,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v8,
        v27);
    string = 0;
    v9 = v33;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 136LL);
    WindowsDeleteString(0);
    string = 0;
    v11 = v10(v9, &string);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x308,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v11,
        v27);
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    v36 = 0;
    v37 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v36, StringRawBuffer, length);
    v13 = (_QWORD *)((char *)a4 + 328);
    std::wstring::operator=((char *)a4 + 328, &v36);
    std::wstring::~wstring(&v36);
    v31 = 0;
    v14 = v33;
    v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 128LL);
    WindowsDeleteString(0);
    v31 = 0;
    v16 = v15(v14, &v31);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30C,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v16,
        v27);
    length = 0;
    v17 = WindowsGetStringRawBuffer(v31, &length);
    v36 = 0;
    v37 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v36, v17, length);
    std::wstring::operator=((char *)a4 + 360, &v36);
    std::wstring::~wstring(&v36);
    LOBYTE(v28) = 0;
    v34 = 0;
    v35 = 0;
    if ( *((_QWORD *)a4 + 44) > 7u )
      v13 = (_QWORD *)*v13;
    v18 = (const unsigned __int16 *)((char *)a4 + 64);
    v19 = (char *)a4 + 64;
    if ( *((_QWORD *)a4 + 11) > 7u )
      v19 = *(char **)v18;
    v20 = StateRepository::Cache::Entity::Protocol_NoThrow::GetByUserAndApplicationUserModelIdAndName(a2, a3, v19, v13);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x313,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v20,
        3);
    if ( *((_QWORD *)a4 + 11) > 7u )
      v18 = *(const unsigned __int16 **)v18;
    if ( !IsRuntimeBehaviorUniversal(a2, a3, v18) )
    {
      v26 = wil::verify_hresult(2147943568LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x320,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)v26,
        3);
    }
    v21 = *((_QWORD *)&v35 + 1);
    *((_QWORD *)&v35 + 1) = 0;
    if ( v21 )
      SRCache_Free();
    v22 = v35;
    *(_QWORD *)&v35 = 0;
    if ( v22 )
      SRCache_Free();
    WindowsDeleteString(v31);
    v31 = 0;
    WindowsDeleteString(string);
    string = 0;
    v23 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
  }
  v24 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  return 0;
}

```

## disassembly

```asm
0x1800b84ec  push    rbp
0x1800b84ee  push    rbx
0x1800b84ef  push    rsi
0x1800b84f0  push    rdi
0x1800b84f1  push    r12
0x1800b84f3  push    r13
0x1800b84f5  push    r14
0x1800b84f7  push    r15
0x1800b84f9  lea     rbp, [rsp-18h]
0x1800b84fe  sub     rsp, 118h
0x1800b8505  mov     rax, cs:__security_cookie
0x1800b850c  xor     rax, rsp
0x1800b850f  mov     [rbp+50h+var_50], rax
0x1800b8513  mov     r15, r9
0x1800b8516  mov     r12, r8
0x1800b8519  mov     r14, rdx
0x1800b851c  xor     r13d, r13d
0x1800b851f  mov     [rsp+150h+var_108], r13
0x1800b8524  mov     rax, [rcx]
0x1800b8527  lea     r8, [rsp+150h+var_108]
0x1800b852c  lea     rdx, _GUID_6095f4dd_b7c0_46ab_81fe_d90f36d00d24
0x1800b8533  mov     rax, [rax]
0x1800b8536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b853b  cmp     eax, 80004002h
0x1800b8540  jnz     short loc_1800B8547
0x1800b8542  jmp     loc_1800B87BC
0x1800b8547  mov     rcx, [rbp+58h]; this
0x1800b854b  test    eax, eax
0x1800b854d  js      loc_1800B895B
0x1800b8553  mov     [rsp+150h+var_F0], r13
0x1800b8558  mov     rcx, [rsp+150h+var_108]
0x1800b855d  mov     rax, [rcx]
0x1800b8560  lea     rdx, [rsp+150h+var_F0]
0x1800b8565  mov     rax, [rax+30h]
0x1800b8569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b856e  mov     rcx, [rbp+58h]; this
0x1800b8572  test    eax, eax
0x1800b8574  js      loc_1800B8970
0x1800b857a  mov     [rsp+150h+string], r13
0x1800b857f  mov     rbx, [rsp+150h+var_F0]
0x1800b8584  mov     rax, [rbx]
0x1800b8587  mov     rdi, [rax+88h]
0x1800b858e  xor     ecx, ecx; string
0x1800b8590  call    cs:__imp_WindowsDeleteString
0x1800b8597  nop     dword ptr [rax+rax+00h]
0x1800b859c  mov     [rsp+150h+string], r13
0x1800b85a1  lea     rdx, [rsp+150h+string]
0x1800b85a6  mov     rcx, rbx
0x1800b85a9  mov     rax, rdi
0x1800b85ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b85b1  mov     rcx, [rbp+58h]; this
0x1800b85b5  test    eax, eax
0x1800b85b7  js      loc_1800B8985
0x1800b85bd  mov     [rsp+150h+length], r13d
0x1800b85c2  lea     rdx, [rsp+150h+length]; length
0x1800b85c7  mov     rcx, [rsp+150h+string]; string
0x1800b85cc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b85d3  nop     dword ptr [rax+rax+00h]
0x1800b85d8  mov     r8d, [rsp+150h+length]
0x1800b85dd  xorps   xmm0, xmm0
0x1800b85e0  movups  [rbp+50h+var_70], xmm0
0x1800b85e4  xorps   xmm1, xmm1
0x1800b85e7  movdqu  [rbp+50h+var_60], xmm1
0x1800b85ec  mov     rdx, rax
0x1800b85ef  lea     rcx, [rbp+50h+var_70]
0x1800b85f3  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800b85f8  lea     rsi, [r15+148h]
0x1800b85ff  lea     rdx, [rbp+50h+var_70]
0x1800b8603  mov     rcx, rsi
0x1800b8606  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b860b  lea     rcx, [rbp+50h+var_70]; void *
0x1800b860f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b8614  mov     [rsp+150h+var_100], r13
0x1800b8619  mov     rbx, [rsp+150h+var_F0]
0x1800b861e  mov     rax, [rbx]
0x1800b8621  mov     rdi, [rax+80h]
0x1800b8628  xor     ecx, ecx; string
0x1800b862a  call    cs:__imp_WindowsDeleteString
0x1800b8631  nop     dword ptr [rax+rax+00h]
0x1800b8636  mov     [rsp+150h+var_100], r13
0x1800b863b  lea     rdx, [rsp+150h+var_100]
0x1800b8640  mov     rcx, rbx
0x1800b8643  mov     rax, rdi
0x1800b8646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b864b  mov     rcx, [rbp+58h]; this
0x1800b864f  test    eax, eax
0x1800b8651  js      loc_1800B899A
0x1800b8657  mov     [rsp+150h+length], r13d
0x1800b865c  lea     rdx, [rsp+150h+length]; length
0x1800b8661  mov     rcx, [rsp+150h+var_100]; string
0x1800b8666  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b866d  nop     dword ptr [rax+rax+00h]
0x1800b8672  mov     r8d, [rsp+150h+length]
0x1800b8677  xorps   xmm0, xmm0
0x1800b867a  movups  [rbp+50h+var_70], xmm0
0x1800b867e  xorps   xmm1, xmm1
0x1800b8681  movdqu  [rbp+50h+var_60], xmm1
0x1800b8686  mov     rdx, rax
0x1800b8689  lea     rcx, [rbp+50h+var_70]
0x1800b868d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800b8692  lea     rcx, [r15+168h]
0x1800b8699  lea     rdx, [rbp+50h+var_70]
0x1800b869d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b86a2  lea     rcx, [rbp+50h+var_70]; void *
0x1800b86a6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b86ab  mov     byte ptr [rsp+150h+var_110], r13b
0x1800b86b0  xorps   xmm0, xmm0
0x1800b86b3  movdqu  [rsp+150h+var_E8], xmm0
0x1800b86b9  xorps   xmm1, xmm1
0x1800b86bc  movdqu  [rsp+150h+var_D8], xmm1
0x1800b86c2  cmp     qword ptr [rsi+18h], 7
0x1800b86c7  jbe     short loc_1800B86CC
0x1800b86c9  mov     rsi, [rsi]
0x1800b86cc  lea     rbx, [r15+40h]
0x1800b86d0  mov     r8, rbx
0x1800b86d3  cmp     qword ptr [rbx+18h], 7
0x1800b86d8  jbe     short loc_1800B86DD
0x1800b86da  mov     r8, [rbx]
0x1800b86dd  lea     rax, [rsp+150h+var_110]
0x1800b86e2  mov     [rsp+150h+var_120], rax
0x1800b86e7  lea     rax, [rsp+150h+var_E8]
0x1800b86ec  mov     [rsp+150h+var_128], rax
0x1800b86f1  mov     qword ptr [rsp+150h+var_130], 3; int
0x1800b86fa  mov     r9, rsi
0x1800b86fd  mov     rdx, r12
0x1800b8700  mov     rcx, r14
0x1800b8703  call    ?GetByUserAndApplicationUserModelIdAndName@Protocol_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBG2W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Protocol_NoThrow::GetByUserAndApplicationUserModelIdAndName(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,ushort const *,StateRepository::Cache::Entity::Protocol_NoThrow::CacheFlags,StateRepository::Cache::Entity::Protocol_NoThrow &,bool &)
0x1800b8708  mov     rcx, [rbp+58h]; this
0x1800b870c  test    eax, eax
0x1800b870e  js      loc_1800B89AF
0x1800b8714  cmp     byte ptr [rsp+150h+var_110], r13b
0x1800b8719  jnz     loc_1800B87DF
0x1800b871f  cmp     qword ptr [rbx+18h], 7
0x1800b8724  jbe     short loc_1800B8729
0x1800b8726  mov     rbx, [rbx]
0x1800b8729  mov     r8, rbx; unsigned __int16 *
0x1800b872c  mov     rdx, r12; __int64
0x1800b872f  mov     rcx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x1800b8732  call    ?IsRuntimeBehaviorUniversal@@YA_NAEAVManager_NoThrow@Cache@StateRepository@@_JPEBG@Z; IsRuntimeBehaviorUniversal(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)
0x1800b8737  test    al, al
0x1800b8739  jz      loc_1800B89C4
0x1800b873f  mov     rcx, qword ptr [rbp+50h+var_D8+8]
0x1800b8743  mov     qword ptr [rbp+50h+var_D8+8], r13
0x1800b8747  test    rcx, rcx
0x1800b874a  jz      short loc_1800B8758
0x1800b874c  call    cs:__imp_SRCache_Free
0x1800b8753  nop     dword ptr [rax+rax+00h]
0x1800b8758  mov     rcx, qword ptr [rsp+150h+var_D8]
0x1800b875d  mov     qword ptr [rsp+150h+var_D8], r13
0x1800b8762  test    rcx, rcx
0x1800b8765  jz      short loc_1800B8774
0x1800b8767  call    cs:__imp_SRCache_Free
0x1800b876e  nop     dword ptr [rax+rax+00h]
0x1800b8773  nop
0x1800b8774  mov     rcx, [rsp+150h+var_100]; string
0x1800b8779  call    cs:__imp_WindowsDeleteString
0x1800b8780  nop     dword ptr [rax+rax+00h]
0x1800b8785  mov     [rsp+150h+var_100], r13
0x1800b878a  mov     rcx, [rsp+150h+string]; string
0x1800b878f  call    cs:__imp_WindowsDeleteString
0x1800b8796  nop     dword ptr [rax+rax+00h]
0x1800b879b  mov     [rsp+150h+string], r13
0x1800b87a0  mov     rcx, [rsp+150h+var_F0]
0x1800b87a5  test    rcx, rcx
0x1800b87a8  jz      short loc_1800B87BC
0x1800b87aa  mov     [rsp+150h+var_F0], r13
0x1800b87af  mov     rax, [rcx]
0x1800b87b2  mov     rax, [rax+10h]
0x1800b87b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b87bb  nop
0x1800b87bc  mov     rcx, [rsp+150h+var_108]
0x1800b87c1  test    rcx, rcx
0x1800b87c4  jz      short loc_1800B87D8
0x1800b87c6  mov     [rsp+150h+var_108], r13
0x1800b87cb  mov     rax, [rcx]
0x1800b87ce  mov     rax, [rax+10h]
0x1800b87d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b87d7  nop
0x1800b87d8  xor     al, al
0x1800b87da  jmp     loc_1800B8922
0x1800b87df  mov     byte ptr [rsp+150h+var_110], r13b
0x1800b87e4  xorps   xmm0, xmm0
0x1800b87e7  movdqa  [rbp+50h+var_C0], xmm0
0x1800b87ec  mov     [rbp+50h+var_B0], r13
0x1800b87f0  mov     [rbp+50h+var_A8], r13
0x1800b87f4  movdqa  [rbp+50h+var_A0], xmm0
0x1800b87f9  xorps   xmm1, xmm1
0x1800b87fc  movdqa  [rbp+50h+var_90], xmm1
0x1800b8801  mov     [rbp+50h+var_80], r13
0x1800b8805  mov     [rbp+50h+var_78], r13d
0x1800b8809  lea     rax, [rsp+150h+var_110]
0x1800b880e  mov     qword ptr [rsp+150h+var_130], rax; int
0x1800b8813  lea     r9, [rbp+50h+var_C0]
0x1800b8817  xor     r8d, r8d
0x1800b881a  mov     rdx, qword ptr [rsp+150h+var_E8+8]
0x1800b881f  mov     rcx, r14
0x1800b8822  call    ?Get@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1800b8827  mov     ebx, eax
0x1800b8829  test    eax, eax
0x1800b882b  jns     short loc_1800B8847
0x1800b882d  mov     rcx, [rbp+58h]; this
0x1800b8831  mov     r9d, eax; char *
0x1800b8834  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b883b  mov     edx, 2E0h; void *
0x1800b8840  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8845  jmp     short loc_1800B884A
0x1800b8847  mov     ebx, r13d
0x1800b884a  mov     rcx, [rbp+58h]; this
0x1800b884e  test    ebx, ebx
0x1800b8850  js      loc_1800B89E7
0x1800b8856  cmp     byte ptr [rsp+150h+var_110], r13b
0x1800b885b  setz    al
0x1800b885e  mov     rcx, [rbp+58h]; this
0x1800b8862  test    al, al
0x1800b8864  jnz     loc_1800B8943
0x1800b886a  mov     r9, r15; struct ActivationProperties *
0x1800b886d  mov     r8, r12; __int64
0x1800b8870  lea     rdx, [rbp+50h+var_C0]; struct StateRepository::Cache::Entity::ApplicationExtension_NoThrow *
0x1800b8874  mov     rcx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x1800b8877  call    ?GetExecutableInformationForExtension@@YAXAEAVManager_NoThrow@Cache@StateRepository@@AEAVApplicationExtension_NoThrow@Entity@23@_JAEAUActivationProperties@@@Z; GetExecutableInformationForExtension(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,__int64,ActivationProperties &)
0x1800b887c  nop
0x1800b887d  lea     rcx, [rbp+50h+var_C0]; this
0x1800b8881  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800b8886  nop
0x1800b8887  mov     rcx, qword ptr [rbp+50h+var_D8+8]
0x1800b888b  mov     qword ptr [rbp+50h+var_D8+8], r13
0x1800b888f  test    rcx, rcx
0x1800b8892  jz      short loc_1800B88A0
0x1800b8894  call    cs:__imp_SRCache_Free
0x1800b889b  nop     dword ptr [rax+rax+00h]
0x1800b88a0  mov     rcx, qword ptr [rsp+150h+var_D8]
0x1800b88a5  mov     qword ptr [rsp+150h+var_D8], r13
0x1800b88aa  test    rcx, rcx
0x1800b88ad  jz      short loc_1800B88BC
0x1800b88af  call    cs:__imp_SRCache_Free
0x1800b88b6  nop     dword ptr [rax+rax+00h]
0x1800b88bb  nop
0x1800b88bc  mov     rcx, [rsp+150h+var_100]; string
0x1800b88c1  call    cs:__imp_WindowsDeleteString
0x1800b88c8  nop     dword ptr [rax+rax+00h]
0x1800b88cd  mov     [rsp+150h+var_100], r13
0x1800b88d2  mov     rcx, [rsp+150h+string]; string
0x1800b88d7  call    cs:__imp_WindowsDeleteString
0x1800b88de  nop     dword ptr [rax+rax+00h]
0x1800b88e3  mov     [rsp+150h+string], r13
0x1800b88e8  mov     rcx, [rsp+150h+var_F0]
0x1800b88ed  test    rcx, rcx
0x1800b88f0  jz      short loc_1800B8904
0x1800b88f2  mov     [rsp+150h+var_F0], r13
0x1800b88f7  mov     rax, [rcx]
0x1800b88fa  mov     rax, [rax+10h]
0x1800b88fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8903  nop
0x1800b8904  mov     rcx, [rsp+150h+var_108]
0x1800b8909  test    rcx, rcx
0x1800b890c  jz      short loc_1800B8920
0x1800b890e  mov     [rsp+150h+var_108], r13
0x1800b8913  mov     rax, [rcx]
0x1800b8916  mov     rax, [rax+10h]
0x1800b891a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b891f  nop
0x1800b8920  mov     al, 1
0x1800b8922  mov     rcx, [rbp+50h+var_50]
0x1800b8926  xor     rcx, rsp; StackCookie
0x1800b8929  call    __security_check_cookie
0x1800b892e  add     rsp, 118h
0x1800b8935  pop     r15
0x1800b8937  pop     r14
0x1800b8939  pop     r13
0x1800b893b  pop     r12
0x1800b893d  pop     rdi
0x1800b893e  pop     rsi
0x1800b893f  pop     rbx
0x1800b8940  pop     rbp
0x1800b8941  retn
0x1800b8943  mov     r9d, 80070490h; char *
0x1800b8949  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800b8950  mov     edx, 327h; void *
0x1800b8955  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b895b  mov     r9d, eax; char *
0x1800b895e  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800b8965  mov     edx, 302h; void *
0x1800b896a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b8970  mov     r9d, eax; char *
0x1800b8973  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800b897a  mov     edx, 305h; void *
0x1800b897f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b8985  mov     r9d, eax; char *
0x1800b8988  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800b898f  mov     edx, 308h; void *
0x1800b8994  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b899a  mov     r9d, eax; char *
0x1800b899d  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800b89a4  mov     edx, 30Ch; void *
0x1800b89a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b89af  mov     r9d, eax; char *
0x1800b89b2  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800b89b9  mov     edx, 313h; void *
0x1800b89be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b89c4  mov     ecx, 80070490h
  ... truncated ...
```
