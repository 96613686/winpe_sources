# FTP_SITE::Initialize(IAppHostElement *,ulong)

- ea: `0x180009d2c`
- end: `0x180009f6f`
- name: `?Initialize@FTP_SITE@@QEAAJPEAUIAppHostElement@@K@Z`
- size: `579`
- prototype: `__int64 __fastcall(FTP_SITE *__hidden this, struct IAppHostElement *, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x18000cb74`
- `0x18000cfe0`

## callees

- `0x180001210`
- `0x1800086c0`
- `0x180008bb0`
- `0x180009d2c`
- `0x180009f78`
- `0x180026df8`
- `0x180026fdc`
- `0x180027010`
- `0x18002b0c4`
- `0x18002b5bc`
- `0x180045dac`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180009e07`
- `msvcrt!swprintf_s` at `0x180009e07`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009ee5`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180009ee5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180009de3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180009de3`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009ef5`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180009ef5`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180009e2d`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180009e2d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180009e16`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180009e16`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FTP_SITE::Initialize(FTP_SITE *this, struct IAppHostElement *a2, unsigned int a3)
{
  const unsigned __int16 **v6; // r12
  unsigned int *v7; // rsi
  int StringProperty; // ebx
  FTP_SITE_CONFIG *v9; // rax
  __int64 v10; // r13
  FTP_LOGGING *v11; // rax
  FTP_LOGGING *v12; // r15
  unsigned int v13; // esi
  BOOL v14; // ebp
  int v15; // edi
  __int64 v18; // [rsp+38h] [rbp-70h]
  wchar_t Buffer[12]; // [rsp+48h] [rbp-60h] BYREF

  v18 = *(_QWORD *)((**(__int64 (__fastcall ***)(FTP_SERVERP *))g_pFtpServer)(g_pFtpServer) + 184);
  *((_DWORD *)this + 75) = a3;
  *((_DWORD *)this + 76) = a3;
  v6 = (const unsigned __int16 **)((char *)this + 8);
  if ( a2 )
  {
    StringProperty = Config_GetStringProperty(a2, L"name", (unsigned __int16 **)this + 1);
    if ( StringProperty < 0 )
      return (unsigned int)StringProperty;
    v7 = (unsigned int *)((char *)this + 4);
    StringProperty = Config_GetDWORDProperty(a2, L"id", (unsigned int *)this + 1);
    if ( StringProperty < 0 )
      return (unsigned int)StringProperty;
    StringProperty = STRU::Copy((FTP_SITE *)((char *)this + 16), L"FTPSVC");
    if ( StringProperty < 0 )
      return (unsigned int)StringProperty;
    swprintf_s(Buffer, 0xBu, L"%lu", *v7);
    StringProperty = STRU::Append((FTP_SITE *)((char *)this + 16), Buffer);
    if ( StringProperty < 0 )
      return (unsigned int)StringProperty;
  }
  else
  {
    v7 = (unsigned int *)((char *)this + 4);
    *((_DWORD *)this + 1) = 0;
  }
  v9 = (FTP_SITE_CONFIG *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler);
  if ( v9 )
    v9 = FTP_SITE_CONFIG::FTP_SITE_CONFIG(v9);
  *((_QWORD *)this + 24) = v9;
  if ( !v9 )
    return (unsigned int)-2147024888;
  StringProperty = FTP_SITE_CONFIG::Initialize(v9, a2);
  if ( StringProperty >= 0 )
  {
    StringProperty = FTP_SITE_PERF_CTRS::Initialize((FTP_SITE *)((char *)this + 72), *v6, *v7);
    if ( StringProperty >= 0 )
    {
      v10 = *((_QWORD *)this + 24);
      *((_DWORD *)this + 45) = *(_DWORD *)(v10 + 72);
      v11 = (FTP_LOGGING *)operator new(0x68u);
      if ( v11 )
        v12 = FTP_LOGGING::FTP_LOGGING(v11);
      else
        v12 = 0;
      *((_QWORD *)this + 23) = v12;
      if ( !v12 )
        return (unsigned int)-2147024888;
      v13 = *v7;
      v14 = *v6 != 0;
      CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v18 + 48));
      v15 = *(_DWORD *)(*(_QWORD *)(v18 + 16) + 12LL);
      CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(v18 + 48));
      StringProperty = FTP_LOGGING::Initialize(v12, (const unsigned __int16 **)(v10 + 1152), v15, v14, v13);
      if ( StringProperty >= 0 )
      {
        StringProperty = FTP_SITE::InitializeOrUpdateEndpoints(this, a3);
        if ( StringProperty >= 0 )
          return 0;
      }
      else
      {
        FTP_LOGGING::DereferenceFtpLogging(*((FTP_LOGGING **)this + 23));
        *((_QWORD *)this + 23) = 0;
      }
    }
  }
  return (unsigned int)StringProperty;
}

```

## disassembly

```asm
0x180009d2c  mov     [rsp+arg_10], rbx
0x180009d31  push    rbp
0x180009d32  push    rsi
0x180009d33  push    rdi
0x180009d34  push    r12
0x180009d36  push    r13
0x180009d38  push    r14
0x180009d3a  push    r15
0x180009d3c  sub     rsp, 70h
0x180009d40  mov     rax, cs:__security_cookie
0x180009d47  xor     rax, rsp
0x180009d4a  mov     [rsp+0A8h+var_48], rax
0x180009d4f  mov     ebx, r8d
0x180009d52  mov     [rsp+0A8h+var_78], ebx
0x180009d56  mov     rdi, rdx
0x180009d59  mov     r14, rcx
0x180009d5c  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180009d63  mov     rax, [rcx]
0x180009d66  mov     rax, [rax]
0x180009d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d6e  mov     rax, [rax+0B8h]
0x180009d75  mov     [rsp+0A8h+var_70], rax
0x180009d7a  mov     [r14+12Ch], ebx
0x180009d81  mov     [r14+130h], ebx
0x180009d88  lea     r12, [r14+8]
0x180009d8c  test    rdi, rdi
0x180009d8f  jnz     short loc_180009D9C
0x180009d91  lea     rsi, [r14+4]
0x180009d95  mov     [rsi], edi
0x180009d97  jmp     loc_180009E26
0x180009d9c  mov     r8, r12; unsigned __int16 **
0x180009d9f  lea     rdx, aName; "name"
0x180009da6  mov     rcx, rdi; struct IAppHostElement *
0x180009da9  call    ?Config_GetStringProperty@@YAJPEAUIAppHostElement@@PEBGPEAPEAG@Z; Config_GetStringProperty(IAppHostElement *,ushort const *,ushort * *)
0x180009dae  mov     ebx, eax
0x180009db0  test    eax, eax
0x180009db2  js      loc_180009F48
0x180009db8  lea     rsi, [r14+4]
0x180009dbc  mov     r8, rsi; unsigned int *
0x180009dbf  lea     rdx, aId; "id"
0x180009dc6  mov     rcx, rdi; struct IAppHostElement *
0x180009dc9  call    ?Config_GetDWORDProperty@@YAJPEAUIAppHostElement@@PEBGPEAK@Z; Config_GetDWORDProperty(IAppHostElement *,ushort const *,ulong *)
0x180009dce  mov     ebx, eax
0x180009dd0  test    eax, eax
0x180009dd2  js      loc_180009F48
0x180009dd8  lea     rdx, aFtpsvc; "FTPSVC"
0x180009ddf  lea     rcx, [r14+10h]
0x180009de3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180009de9  mov     ebx, eax
0x180009deb  test    eax, eax
0x180009ded  js      loc_180009F48
0x180009df3  mov     r9d, [rsi]
0x180009df6  lea     r8, aLu; "%lu"
0x180009dfd  mov     edx, 0Bh; BufferCount
0x180009e02  lea     rcx, [rsp+0A8h+Buffer]; Buffer
0x180009e07  call    cs:__imp_swprintf_s
0x180009e0d  lea     rdx, [rsp+0A8h+Buffer]
0x180009e12  lea     rcx, [r14+10h]
0x180009e16  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180009e1c  mov     ebx, eax
0x180009e1e  test    eax, eax
0x180009e20  js      loc_180009F48
0x180009e26  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x180009e2d  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180009e33  mov     [rsp+0A8h+var_68], rax
0x180009e38  test    rax, rax
0x180009e3b  jz      short loc_180009E46
0x180009e3d  mov     rcx, rax; this
0x180009e40  call    ??0FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::FTP_SITE_CONFIG(void)
0x180009e45  nop
0x180009e46  mov     [r14+0C0h], rax
0x180009e4d  test    rax, rax
0x180009e50  jnz     short loc_180009E5C
0x180009e52  mov     ebx, 80070008h
0x180009e57  jmp     loc_180009F48
0x180009e5c  mov     rdx, rdi; struct IAppHostElement *
0x180009e5f  mov     rcx, rax; this
0x180009e62  call    ?Initialize@FTP_SITE_CONFIG@@QEAAJPEAUIAppHostElement@@@Z; FTP_SITE_CONFIG::Initialize(IAppHostElement *)
0x180009e67  mov     ebx, eax
0x180009e69  test    eax, eax
0x180009e6b  js      loc_180009F48
0x180009e71  lea     rcx, [r14+48h]; this
0x180009e75  mov     r8d, [rsi]; unsigned int
0x180009e78  mov     rdx, [r12]; unsigned __int16 *
0x180009e7c  call    ?Initialize@FTP_SITE_PERF_CTRS@@QEAAJPEBGK@Z; FTP_SITE_PERF_CTRS::Initialize(ushort const *,ulong)
0x180009e81  mov     ebx, eax
0x180009e83  test    eax, eax
0x180009e85  js      loc_180009F48
0x180009e8b  mov     r13, [r14+0C0h]
0x180009e92  mov     eax, [r13+48h]
0x180009e96  mov     [r14+0B4h], eax
0x180009e9d  mov     ecx, 68h ; 'h'; Size
0x180009ea2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009ea7  mov     [rsp+0A8h+var_68], rax
0x180009eac  test    rax, rax
0x180009eaf  jz      short loc_180009EBE
0x180009eb1  mov     rcx, rax; this
0x180009eb4  call    ??0FTP_LOGGING@@QEAA@XZ; FTP_LOGGING::FTP_LOGGING(void)
0x180009eb9  mov     r15, rax
0x180009ebc  jmp     short loc_180009EC1
0x180009ebe  xor     r15d, r15d
0x180009ec1  mov     [r14+0B8h], r15
0x180009ec8  test    r15, r15
0x180009ecb  jz      short loc_180009E52
0x180009ecd  mov     esi, [rsi]
0x180009ecf  xor     ebp, ebp
0x180009ed1  cmp     [r12], rbp
0x180009ed5  setnz   bpl
0x180009ed9  mov     rdi, [rsp+0A8h+var_70]
0x180009ede  lea     rbx, [rdi+30h]
0x180009ee2  mov     rcx, rbx
0x180009ee5  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180009eeb  mov     rax, [rdi+10h]
0x180009eef  mov     edi, [rax+0Ch]
0x180009ef2  mov     rcx, rbx
0x180009ef5  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180009efb  lea     rdx, [r13+480h]; struct FTP_LOG_FILE_CONFIG_ELEMENT *
0x180009f02  mov     [rsp+0A8h+var_88], esi; unsigned int
0x180009f06  mov     r9d, ebp; int
0x180009f09  mov     r8d, edi; int
0x180009f0c  mov     rcx, r15; this
0x180009f0f  call    ?Initialize@FTP_LOGGING@@QEAAJPEAVFTP_LOG_FILE_CONFIG_ELEMENT@@HHK@Z; FTP_LOGGING::Initialize(FTP_LOG_FILE_CONFIG_ELEMENT *,int,int,ulong)
0x180009f14  mov     ebx, eax
0x180009f16  test    eax, eax
0x180009f18  jns     short loc_180009F33
0x180009f1a  mov     rcx, [r14+0B8h]; this
0x180009f21  call    ?DereferenceFtpLogging@FTP_LOGGING@@QEAAXXZ; FTP_LOGGING::DereferenceFtpLogging(void)
0x180009f26  mov     qword ptr [r14+0B8h], 0
0x180009f31  jmp     short loc_180009F48
0x180009f33  mov     edx, [rsp+0A8h+var_78]; unsigned int
0x180009f37  mov     rcx, r14; this
0x180009f3a  call    ?InitializeOrUpdateEndpoints@FTP_SITE@@AEAAJK@Z; FTP_SITE::InitializeOrUpdateEndpoints(ulong)
0x180009f3f  mov     ebx, eax
0x180009f41  xor     eax, eax
0x180009f43  test    ebx, ebx
0x180009f45  cmovns  ebx, eax
0x180009f48  mov     eax, ebx
0x180009f4a  mov     rcx, [rsp+0A8h+var_48]
0x180009f4f  xor     rcx, rsp; StackCookie
0x180009f52  call    __security_check_cookie
0x180009f57  mov     rbx, [rsp+0A8h+arg_10]
0x180009f5f  add     rsp, 70h
0x180009f63  pop     r15
0x180009f65  pop     r14
0x180009f67  pop     r13
0x180009f69  pop     r12
0x180009f6b  pop     rdi
0x180009f6c  pop     rsi
0x180009f6d  pop     rbp
0x180009f6e  retn
```
