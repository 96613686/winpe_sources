# KeyboardWinRTClient::Run(void)

- ea: `0x1800ad150`
- end: `0x1800ad2ae`
- name: `?Run@KeyboardWinRTClient@@UEAAJXZ`
- size: `350`
- prototype: `__int64 __fastcall(KeyboardWinRTClient *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800ad2c0`

## callees

- `0x180009260`
- `0x18000929c`
- `0x18001daf0`
- `0x18001dcc8`
- `0x1800ac4c8`
- `0x1800ac594`
- `0x1800accc4`
- `0x1800ad150`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ad171`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ad171`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ad19f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ad19f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad294`

## string_xrefs

- `0x1800ad16a`: `CoreMessaging.dll`
- `0x1800ad195`: `CoreUICreate`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KeyboardWinRTClient::Run(KeyboardWinRTClient *this)
{
  HMODULE Library; // rax
  int v3; // ebx
  FARPROC ProcAddress; // rax
  InputProfileHelper *v5; // rax
  InputProfileHelper *v6; // rax
  InputProfileHelper *v7; // rbx
  signed int LastError; // eax
  int v10; // edx
  unsigned int v11; // r8d
  const int *v12; // [rsp+30h] [rbp-18h] BYREF
  HMODULE v13; // [rsp+38h] [rbp-10h]

  Library = LoadLibraryExW(L"CoreMessaging.dll", 0, 0x800u);
  v12 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v13 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "CoreUICreate");
    if ( ProcAddress )
    {
      v3 = ((__int64 (__fastcall *)(struct IMessageSession **))ProcAddress)(&KeyboardWinRTClient::s_pMessageSession);
      if ( v3 >= 0 )
      {
        v3 = (*(__int64 (__fastcall **)(struct IMessageSession *, __int64 (__fastcall *)(void *, const void *, int), KeyboardWinRTClient *, unsigned __int64 *))(*(_QWORD *)KeyboardWinRTClient::s_pMessageSession + 112LL))(
               KeyboardWinRTClient::s_pMessageSession,
               KeyboardWinRTClient::OnMessage,
               this,
               &KeyboardWinRTClient::s_hEndpoint);
        if ( v3 >= 0 )
        {
          v5 = (InputProfileHelper *)operator new(0x40u);
          v6 = InputProfileHelper::InputProfileHelper(v5);
          v7 = (InputProfileHelper *)*((_QWORD *)this + 1);
          *((_QWORD *)this + 1) = v6;
          if ( v7 )
          {
            InputProfileHelper::~InputProfileHelper(v7);
            operator delete(v7);
          }
          v3 = InputProfileHelper::Initialize(*((InputProfileHelper **)this + 1));
          if ( v3 >= 0 )
            v3 = (*(__int64 (__fastcall **)(struct IMessageSession *))(*(_QWORD *)KeyboardWinRTClient::s_pMessageSession
                                                                     + 232LL))(KeyboardWinRTClient::s_pMessageSession);
        }
      }
    }
    else
    {
      v3 = -2147467263;
    }
  }
  else
  {
    v3 = 126;
  }
  if ( KeyboardWinRTClient::s_pMessageSession )
    (*(void (__fastcall **)(struct IMessageSession *))(*(_QWORD *)KeyboardWinRTClient::s_pMessageSession + 16LL))(KeyboardWinRTClient::s_pMessageSession);
  v12 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( v13 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v12) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v10, v11);
    JUMPOUT(0x1800AD2ADLL);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800ad150  mov     [rsp+arg_0], rbx
0x1800ad155  mov     [rsp+arg_8], rsi
0x1800ad15a  push    rdi
0x1800ad15b  sub     rsp, 40h
0x1800ad15f  mov     rdi, rcx
0x1800ad162  xor     edx, edx; hFile
0x1800ad164  mov     r8d, 800h; dwFlags
0x1800ad16a  lea     rcx, aCoremessagingD; "CoreMessaging.dll"
0x1800ad171  call    cs:__imp_LoadLibraryExW
0x1800ad177  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800ad17e  mov     [rsp+48h+var_18], rsi
0x1800ad183  mov     [rsp+48h+var_10], rax
0x1800ad188  test    rax, rax
0x1800ad18b  jnz     short loc_1800AD195
0x1800ad18d  lea     ebx, [rax+7Eh]
0x1800ad190  jmp     loc_1800AD24F
0x1800ad195  lea     rdx, aCoreuicreate; "CoreUICreate"
0x1800ad19c  mov     rcx, rax; hModule
0x1800ad19f  call    cs:__imp_GetProcAddress
0x1800ad1a5  test    rax, rax
0x1800ad1a8  jnz     short loc_1800AD1B4
0x1800ad1aa  mov     ebx, 80004001h
0x1800ad1af  jmp     loc_1800AD24F
0x1800ad1b4  lea     rcx, ?s_pMessageSession@KeyboardWinRTClient@@2PEAUIMessageSession@@EA; IMessageSession * KeyboardWinRTClient::s_pMessageSession
0x1800ad1bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad1c0  mov     ebx, eax
0x1800ad1c2  test    eax, eax
0x1800ad1c4  js      loc_1800AD24F
0x1800ad1ca  mov     rcx, cs:?s_pMessageSession@KeyboardWinRTClient@@2PEAUIMessageSession@@EA; IMessageSession * KeyboardWinRTClient::s_pMessageSession
0x1800ad1d1  mov     rax, [rcx]
0x1800ad1d4  lea     r9, ?s_hEndpoint@KeyboardWinRTClient@@2_KA; unsigned __int64 KeyboardWinRTClient::s_hEndpoint
0x1800ad1db  mov     r8, rdi
0x1800ad1de  lea     rdx, ?OnMessage@KeyboardWinRTClient@@SAJPEAXPEBXH@Z; KeyboardWinRTClient::OnMessage(void *,void const *,int)
0x1800ad1e5  mov     rax, [rax+70h]
0x1800ad1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad1ee  mov     ebx, eax
0x1800ad1f0  test    eax, eax
0x1800ad1f2  js      short loc_1800AD24F
0x1800ad1f4  mov     ecx, 40h ; '@'; Size
0x1800ad1f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ad1fe  mov     rcx, rax; this
0x1800ad201  call    ??0InputProfileHelper@@QEAA@XZ; InputProfileHelper::InputProfileHelper(void)
0x1800ad206  mov     rbx, [rdi+8]
0x1800ad20a  mov     [rdi+8], rax
0x1800ad20e  test    rbx, rbx
0x1800ad211  jz      short loc_1800AD228
0x1800ad213  mov     rcx, rbx; this
0x1800ad216  call    ??1InputProfileHelper@@QEAA@XZ; InputProfileHelper::~InputProfileHelper(void)
0x1800ad21b  mov     edx, 40h ; '@'
0x1800ad220  mov     rcx, rbx; Block
0x1800ad223  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ad228  mov     rcx, [rdi+8]; this
0x1800ad22c  call    ?Initialize@InputProfileHelper@@QEAAJXZ; InputProfileHelper::Initialize(void)
0x1800ad231  mov     ebx, eax
0x1800ad233  test    eax, eax
0x1800ad235  js      short loc_1800AD24F
0x1800ad237  mov     rcx, cs:?s_pMessageSession@KeyboardWinRTClient@@2PEAUIMessageSession@@EA; IMessageSession * KeyboardWinRTClient::s_pMessageSession
0x1800ad23e  mov     rax, [rcx]
0x1800ad241  mov     rax, [rax+0E8h]
0x1800ad248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad24d  mov     ebx, eax
0x1800ad24f  mov     rcx, cs:?s_pMessageSession@KeyboardWinRTClient@@2PEAUIMessageSession@@EA; IMessageSession * KeyboardWinRTClient::s_pMessageSession
0x1800ad256  test    rcx, rcx
0x1800ad259  jz      short loc_1800AD267
0x1800ad25b  mov     rax, [rcx]
0x1800ad25e  mov     rax, [rax+10h]
0x1800ad262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad267  mov     [rsp+48h+var_18], rsi
0x1800ad26c  cmp     [rsp+48h+var_10], 0
0x1800ad272  jz      short loc_1800AD282
0x1800ad274  lea     rcx, [rsp+48h+var_18]
0x1800ad279  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800ad27e  test    al, al
0x1800ad280  jz      short loc_1800AD294
0x1800ad282  mov     eax, ebx
0x1800ad284  mov     rbx, [rsp+48h+arg_0]
0x1800ad289  mov     rsi, [rsp+48h+arg_8]
0x1800ad28e  add     rsp, 40h
0x1800ad292  pop     rdi
0x1800ad293  retn
0x1800ad294  call    cs:__imp_GetLastError
0x1800ad29a  test    eax, eax
0x1800ad29c  jle     short loc_1800AD2A6
0x1800ad29e  movzx   eax, ax
0x1800ad2a1  or      eax, 80070000h
0x1800ad2a6  mov     ecx, eax; this
0x1800ad2a8  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
