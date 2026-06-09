# NDXGI::CUMDAdapter::OpenAdapter10_2(void)

- ea: `0x1800475a0`
- end: `0x18004771c`
- name: `?OpenAdapter10_2@CUMDAdapter@NDXGI@@QEAAJXZ`
- size: `380`
- prototype: `__int64 __fastcall(NDXGI::CUMDAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18006a958`

## callees

- `0x1800229a0`
- `0x1800475a0`
- `0x180048f24`
- `0x1801cb010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800476b2`
- `ntdll!EtwEventWrite` at `0x1800476b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800476bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800476bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800475ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800475ec`

## string_xrefs

- `0x1800475e5`: `OpenAdapter10_2`
- `0x180047674`: `OpenAdapter10_2`
- `0x1800476d6`: `Failed to retrieve OpenAdapter10_2`

## pseudocode

```c
__int64 __fastcall NDXGI::CUMDAdapter::OpenAdapter10_2(NDXGI::CUMDAdapter *this)
{
  HMODULE v2; // rcx
  FARPROC ProcAddress; // rsi
  signed int v4; // ebx
  __int64 v5; // r9
  signed int LastError; // eax
  __int64 v8; // r9
  NDXGI::CUMDAdapter *v9; // [rsp+30h] [rbp-38h] BYREF
  __int64 v10; // [rsp+38h] [rbp-30h]
  int v11; // [rsp+40h] [rbp-28h]
  int v12; // [rsp+44h] [rbp-24h]
  char *v13; // [rsp+48h] [rbp-20h]
  char *v14; // [rsp+50h] [rbp-18h]
  const struct _EVENT_DESCRIPTOR *v15; // [rsp+90h] [rbp+28h] BYREF

  v14 = 0;
  v9 = this;
  v10 = 0;
  v11 = 720913;
  v12 = 393216;
  v13 = (char *)this + 40;
  v2 = *(HMODULE *)this;
  if ( !v2 )
    v2 = (HMODULE)*((_QWORD *)this + 10);
  ProcAddress = GetProcAddress(v2, "OpenAdapter10_2");
  v14 = (char *)this + 864;
  if ( ProcAddress )
    goto LABEL_13;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 >= 0 )
  {
LABEL_13:
    if ( dword_1802282A4
      && (qword_180228290 & 0x2000000000000002LL) != 0
      && (qword_180228298 & 0x2000000000000002LL) == qword_180228298 )
    {
      EtwEventWrite(Direct3D11EtwProviderGuid_Context, &EventInitiatingUMDOpenAdapter, 0, 0);
    }
    v15 = &EventFinishedUMDOpenAdapter;
    v4 = ((__int64 (__fastcall *)(NDXGI::CUMDAdapter **))ProcAddress)(&v9);
    if ( v4 == -2147467263 )
    {
      v11 = 720907;
      v12 = 131081;
      v4 = ((__int64 (__fastcall *)(NDXGI::CUMDAdapter **))ProcAddress)(&v9);
    }
    if ( v4 < 0 )
      CModule::RecordJournal((CModule *)&g_Module, v4, "OpenAdapter10_2", v5, 1);
    else
      *((_QWORD *)this + 113) = v10;
    CETWEventPair::~CETWEventPair((CETWEventPair *)&v15);
  }
  else
  {
    CModule::RecordJournal((CModule *)&g_Module, v4, "Failed to retrieve OpenAdapter10_2", v8, 1);
  }
  *((_DWORD *)this + 9) = v4;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800475a0  push    rbp
0x1800475a2  push    rbx
0x1800475a3  push    rsi
0x1800475a4  push    rdi
0x1800475a5  mov     rbp, rsp
0x1800475a8  sub     rsp, 68h
0x1800475ac  mov     rdi, rcx
0x1800475af  mov     [rbp+var_18], 0
0x1800475b7  mov     [rbp+var_38], rcx
0x1800475bb  mov     [rbp+var_30], 0
0x1800475c3  mov     [rbp+var_28], 0B0011h
0x1800475ca  mov     [rbp+var_24], 60000h
0x1800475d1  lea     rax, [rcx+28h]
0x1800475d5  mov     [rbp+var_20], rax
0x1800475d9  mov     rcx, [rcx]
0x1800475dc  test    rcx, rcx
0x1800475df  jnz     short loc_1800475E5
0x1800475e1  mov     rcx, [rdi+50h]; hModule
0x1800475e5  lea     rdx, aOpenadapter102_0; "OpenAdapter10_2"
0x1800475ec  call    cs:__imp_GetProcAddress
0x1800475f2  mov     rsi, rax
0x1800475f5  lea     rcx, [rdi+360h]
0x1800475fc  mov     [rbp+var_18], rcx
0x180047600  test    rax, rax
0x180047603  jz      loc_1800476BD
0x180047609  cmp     cs:dword_1802282A4, 0
0x180047610  jz      short loc_180047625
0x180047612  mov     rdx, 2000000000000002h
0x18004761c  test    cs:qword_180228290, rdx
0x180047623  jnz     short loc_18004768B
0x180047625  lea     rax, EventFinishedUMDOpenAdapter
0x18004762c  mov     [rbp+arg_0], rax
0x180047630  lea     rcx, [rbp+var_38]
0x180047634  mov     rax, rsi
0x180047637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004763c  mov     ebx, eax
0x18004763e  cmp     eax, 80004001h
0x180047643  jz      loc_1800476FB
0x180047649  test    ebx, ebx
0x18004764b  js      short loc_18004766F
0x18004764d  mov     rax, [rbp+var_30]
0x180047651  mov     [rdi+388h], rax
0x180047658  lea     rcx, [rbp+arg_0]; this
0x18004765c  call    ??1CETWEventPair@@QEAA@XZ; CETWEventPair::~CETWEventPair(void)
0x180047661  mov     [rdi+24h], ebx
0x180047664  mov     eax, ebx
0x180047666  add     rsp, 68h
0x18004766a  pop     rdi
0x18004766b  pop     rsi
0x18004766c  pop     rbx
0x18004766d  pop     rbp
0x18004766e  retn
0x18004766f  mov     [rsp+68h+var_48], 1; bool
0x180047674  lea     r8, aOpenadapter102_0; "OpenAdapter10_2"
0x18004767b  mov     edx, ebx; unsigned int
0x18004767d  lea     rcx, ?g_Module@@3VCModule@@A; this
0x180047684  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x180047689  jmp     short loc_180047658
0x18004768b  mov     rax, cs:qword_180228298
0x180047692  and     rax, rdx
0x180047695  cmp     rax, cs:qword_180228298
0x18004769c  jnz     short loc_180047625
0x18004769e  xor     r9d, r9d
0x1800476a1  xor     r8d, r8d
0x1800476a4  lea     rdx, EventInitiatingUMDOpenAdapter
0x1800476ab  mov     rcx, cs:Direct3D11EtwProviderGuid_Context
0x1800476b2  call    cs:__imp_EtwEventWrite
0x1800476b8  jmp     loc_180047625
0x1800476bd  call    cs:__imp_GetLastError
0x1800476c3  mov     ebx, eax
0x1800476c5  test    eax, eax
0x1800476c7  jg      short loc_1800476F0
0x1800476c9  test    ebx, ebx
0x1800476cb  jns     loc_180047609
0x1800476d1  mov     [rsp+68h+var_48], 1; bool
0x1800476d6  lea     r8, aFailedToRetrie_0; "Failed to retrieve OpenAdapter10_2"
0x1800476dd  mov     edx, ebx; unsigned int
0x1800476df  lea     rcx, ?g_Module@@3VCModule@@A; this
0x1800476e6  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x1800476eb  jmp     loc_180047661
0x1800476f0  movzx   ebx, ax
0x1800476f3  or      ebx, 80070000h
0x1800476f9  jmp     short loc_1800476C9
0x1800476fb  mov     [rbp+var_28], 0B000Bh
0x180047702  mov     [rbp+var_24], 20009h
0x180047709  lea     rcx, [rbp+var_38]
0x18004770d  mov     rax, rsi
0x180047710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047715  mov     ebx, eax
0x180047717  jmp     loc_180047649
```
