# RegistryWatcher::Initialize(HKEY__ *,ushort const *)

- ea: `0x18003b724`
- end: `0x18003b86c`
- name: `?Initialize@RegistryWatcher@@IEAAJPEAUHKEY__@@PEBG@Z`
- size: `328`
- prototype: `int(RegistryWatcher *__hidden this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008e2f8`

## callees

- `0x180012b74`
- `0x18003b724`
- `0x18003d138`
- `0x18008daac`
- `0x18008ead4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b7c3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b7c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b780`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b780`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003b7ed`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003b7ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b796`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b796`
- `CoreMessaging!CoreUICreate` at `0x18003b74e`
- `CoreMessaging!CoreUICreate` at `0x18003b74e`

## string_xrefs

- `0x18003b76b`: `onecoreuap\windows\moderncore\inputv2\utilities\registrywatcher\lib\registrywatcher.cpp`
- `0x18003b801`: `onecoreuap\windows\moderncore\inputv2\utilities\registrywatcher\lib\registrywatcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegistryWatcher::Initialize(HKEY *this, HKEY a2, const unsigned __int16 *a3)
{
  _QWORD *v5; // r14
  signed int LastError; // esi
  HKEY *v7; // rdi
  __int64 v8; // rdx
  HKEY v9; // rcx
  LSTATUS v11; // eax
  HKEY EventW; // rax
  const char *v13; // r9
  int phkResult; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v5 = this + 2;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 2);
  LastError = CoreUICreate(v5);
  v7 = this + 3;
  if ( LastError >= 0 )
  {
    v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20019u, this + 3);
    LastError = v11;
    if ( v11 > 0 )
      LastError = (unsigned __int16)v11 | 0x80070000;
    if ( LastError >= 0 )
    {
      EventW = (HKEY)CreateEventW(0, 0, 0, 0);
      this[4] = EventW;
      if ( !EventW )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x4C,
                      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\registrywatcher\\lib\\registrywatcher.cpp",
                      v13);
        goto LABEL_4;
      }
      LastError = RegistryWatcher::OnKeyChange((RegistryWatcher *)this);
      if ( LastError >= 0 )
      {
        LastError = (*(__int64 (__fastcall **)(_QWORD, HKEY, int (*)(void *, unsigned int, void *), HKEY *))(*(_QWORD *)*v5 + 272LL))(
                      *v5,
                      this[4],
                      RegistryWatcher::OnChangeCallbackStatic,
                      this);
        if ( LastError >= 0 )
          return 0;
        v8 = 82;
      }
      else
      {
        v8 = 77;
      }
    }
    else
    {
      v8 = 73;
    }
  }
  else
  {
    v8 = 65;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\utilities\\registrywatcher\\lib\\registrywatcher.cpp",
    (const char *)(unsigned int)LastError,
    phkResult);
LABEL_4:
  if ( *v7 )
  {
    RegCloseKey(*v7);
    *v7 = 0;
  }
  v9 = this[4];
  if ( v9 )
  {
    CloseHandle(v9);
    this[4] = 0;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18003b724  push    rbx
0x18003b726  push    rbp
0x18003b727  push    rsi
0x18003b728  push    rdi
0x18003b729  push    r14
0x18003b72b  sub     rsp, 40h
0x18003b72f  mov     rbp, r8
0x18003b732  mov     rbx, rcx
0x18003b735  mov     [rsp+68h+var_38], rcx
0x18003b73a  mov     [rsp+68h+var_30], 1
0x18003b73f  lea     r14, [rcx+10h]
0x18003b743  mov     rcx, r14
0x18003b746  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003b74b  mov     rcx, r14
0x18003b74e  call    cs:__imp_CoreUICreate
0x18003b754  mov     esi, eax
0x18003b756  lea     rdi, [rbx+18h]
0x18003b75a  test    eax, eax
0x18003b75c  jns     short loc_18003B7AB
0x18003b75e  mov     edx, 41h ; 'A'; void *
0x18003b763  mov     rcx, [rsp+68h]; this
0x18003b768  mov     r9d, esi; char *
0x18003b76b  lea     r8, aOnecoreuapWind_72; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003b772  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b777  nop
0x18003b778  mov     rcx, [rdi]; hKey
0x18003b77b  test    rcx, rcx
0x18003b77e  jz      short loc_18003B78D
0x18003b780  call    cs:__imp_RegCloseKey
0x18003b786  mov     qword ptr [rdi], 0
0x18003b78d  mov     rcx, [rbx+20h]; hObject
0x18003b791  test    rcx, rcx
0x18003b794  jz      short loc_18003B7A4
0x18003b796  call    cs:__imp_CloseHandle
0x18003b79c  mov     qword ptr [rbx+20h], 0
0x18003b7a4  mov     eax, esi
0x18003b7a6  jmp     loc_18003B861
0x18003b7ab  mov     qword ptr [rsp+68h+phkResult], rdi; phkResult
0x18003b7b0  mov     r9d, 20019h; samDesired
0x18003b7b6  xor     r8d, r8d; ulOptions
0x18003b7b9  mov     rdx, rbp; lpSubKey
0x18003b7bc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003b7c3  call    cs:__imp_RegOpenKeyExW
0x18003b7c9  mov     esi, eax
0x18003b7cb  test    eax, eax
0x18003b7cd  jle     short loc_18003B7D8
0x18003b7cf  movzx   esi, ax
0x18003b7d2  or      esi, 80070000h
0x18003b7d8  test    esi, esi
0x18003b7da  jns     short loc_18003B7E3
0x18003b7dc  mov     edx, 49h ; 'I'
0x18003b7e1  jmp     short loc_18003B763
0x18003b7e3  xor     r9d, r9d; lpName
0x18003b7e6  xor     r8d, r8d; bInitialState
0x18003b7e9  xor     edx, edx; bManualReset
0x18003b7eb  xor     ecx, ecx; lpEventAttributes
0x18003b7ed  call    cs:__imp_CreateEventW
0x18003b7f3  mov     [rbx+20h], rax
0x18003b7f7  test    rax, rax
0x18003b7fa  jnz     short loc_18003B817
0x18003b7fc  mov     rcx, [rsp+68h]; this
0x18003b801  lea     r8, aOnecoreuapWind_72; "onecoreuap\\windows\\moderncore\\inputv"...
0x18003b808  lea     edx, [rax+4Ch]; void *
0x18003b80b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b810  mov     esi, eax
0x18003b812  jmp     loc_18003B778
0x18003b817  mov     rcx, rbx; this
0x18003b81a  call    ?OnKeyChange@RegistryWatcher@@AEAAJXZ; RegistryWatcher::OnKeyChange(void)
0x18003b81f  mov     esi, eax
0x18003b821  test    eax, eax
0x18003b823  jns     short loc_18003B82F
0x18003b825  mov     edx, 4Dh ; 'M'
0x18003b82a  jmp     loc_18003B763
0x18003b82f  mov     rcx, [r14]
0x18003b832  mov     rax, [rcx]
0x18003b835  mov     r9, rbx
0x18003b838  lea     r8, ?OnChangeCallbackStatic@RegistryWatcher@@SAJPEAXK0@Z; RegistryWatcher::OnChangeCallbackStatic(void *,ulong,void *)
0x18003b83f  mov     rdx, [rbx+20h]
0x18003b843  mov     rax, [rax+110h]
0x18003b84a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b84f  mov     esi, eax
0x18003b851  test    eax, eax
0x18003b853  jns     short loc_18003B85F
0x18003b855  mov     edx, 52h ; 'R'
0x18003b85a  jmp     loc_18003B763
0x18003b85f  xor     eax, eax
0x18003b861  add     rsp, 40h
0x18003b865  pop     r14
0x18003b867  pop     rdi
0x18003b868  pop     rsi
0x18003b869  pop     rbp
0x18003b86a  pop     rbx
0x18003b86b  retn
```
