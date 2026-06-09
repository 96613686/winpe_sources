# MODULE_DLL::GetModuleDll(ushort const *,MODULE_DLL * *)

- ea: `0x180017b2c`
- end: `0x180017d12`
- name: `?GetModuleDll@MODULE_DLL@@SAJPEBGPEAPEAV1@@Z`
- size: `486`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _LIST_ENTRY **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001c6fc`

## callees

- `0x180017b2c`
- `0x180019094`
- `0x180019558`
- `0x18001add8`
- `0x18002cfa8`
- `0x1800343f0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180017b88`
- `msvcrt!_wcsicmp` at `0x180017b88`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180017c3a`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180017c3a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180017bce`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180017bce`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180017b7c`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180017b7c`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180017c94`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x180017c94`
- `iisutil!PuDbgPrintError` at `0x180017cd3`
- `iisutil!PuDbgPrintError` at `0x180017cd3`

## string_xrefs

- `0x180017cb6`: `MODULE_DLL::GetModuleDll`
- `0x180017cc2`: `servercommon\inetsrv\iis\iisrearc\iis70\core\moduledll.cxx`

## pseudocode

```c
__int64 __fastcall MODULE_DLL::GetModuleDll(const unsigned __int16 *a1, struct _LIST_ENTRY **a2)
{
  struct _LIST_ENTRY *Flink; // rdi
  struct _LIST_ENTRY *v5; // rbx
  const wchar_t *Str; // rax
  int v8; // esi
  const unsigned __int16 *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // edx
  unsigned __int16 v12; // r8
  int v13; // [rsp+40h] [rbp-88h] BYREF
  const unsigned __int16 *v14; // [rsp+48h] [rbp-80h] BYREF
  WCHAR *v15; // [rsp+50h] [rbp-78h]
  WCHAR Buffer[32]; // [rsp+60h] [rbp-68h] BYREF

  Flink = MODULE_DLL::sm_ModuleListHead.Flink;
  v13 = 0;
  while ( Flink != &MODULE_DLL::sm_ModuleListHead )
  {
    v5 = Flink - 1;
    Str = STRU::QueryStr((STRU *)&Flink[2].Blink);
    if ( !_wcsicmp(Str, a1) )
      goto LABEL_5;
    Flink = Flink->Flink;
  }
  v5 = (struct _LIST_ENTRY *)operator new(0x70u);
  if ( !v5 )
    return 2147942408LL;
  v5->Flink = (struct _LIST_ENTRY *)&MODULE_DLL::`vftable';
  STRU::STRU((STRU *)&v5[3].Blink);
  HIDWORD(v5->Blink) = 1280066637;
  LODWORD(v5->Blink) = 1;
  v8 = MODULE_DLL::Create((MODULE_DLL *)v5, a1, (enum MODULE_FAILURE_TYPE *)&v13);
  if ( v8 >= 0 )
  {
LABEL_5:
    _InterlockedAdd((volatile signed __int32 *)&v5->Blink, 1u);
    *a2 = v5;
    return 0;
  }
  v9 = &dword_180039134;
  if ( a1 )
    v9 = a1;
  v15 = L"???";
  v14 = v9;
  if ( v13 )
  {
    v10 = WIN32_FROM_HRESULT(v8);
    v11 = -1073739529;
  }
  else
  {
    if ( v8 == -2147024703 )
    {
      if ( GetEnvironmentVariableW(L"PROCESSOR_ARCHITECTURE", Buffer, 0x20u) )
        v15 = Buffer;
      v10 = WIN32_FROM_HRESULT(-2147024703);
      v11 = -1073739542;
      v12 = 2;
      goto LABEL_18;
    }
    v10 = WIN32_FROM_HRESULT(v8);
    v11 = -1073739544;
  }
  v12 = 1;
LABEL_18:
  EVENT_LOG::LogEvent((W3_SERVER *)((char *)g_pW3Server + 28), v11, v12, &v14, v10);
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\core\\moduledll.cxx",
      218,
      "MODULE_DLL::GetModuleDll",
      v8,
      "Failed to load global module %S\n",
      a1);
  MODULE_DLL::DereferenceModuleDll((MODULE_DLL *)v5);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180017b2c  mov     [rsp+arg_10], rbx
0x180017b31  mov     [rsp+arg_18], rbp
0x180017b36  push    rsi
0x180017b37  push    rdi
0x180017b38  push    r14
0x180017b3a  sub     rsp, 0B0h
0x180017b41  mov     rax, cs:__security_cookie
0x180017b48  xor     rax, rsp
0x180017b4b  mov     [rsp+0C8h+var_28], rax
0x180017b53  mov     rdi, cs:?sm_ModuleListHead@MODULE_DLL@@0U_LIST_ENTRY@@A; _LIST_ENTRY MODULE_DLL::sm_ModuleListHead
0x180017b5a  mov     r14, rdx
0x180017b5d  mov     rbp, rcx
0x180017b60  mov     [rsp+0C8h+var_88], 0
0x180017b68  lea     rax, ?sm_ModuleListHead@MODULE_DLL@@0U_LIST_ENTRY@@A; _LIST_ENTRY MODULE_DLL::sm_ModuleListHead
0x180017b6f  cmp     rdi, rax
0x180017b72  jz      short loc_180017BAA
0x180017b74  lea     rbx, [rdi-10h]
0x180017b78  lea     rcx, [rbx+38h]
0x180017b7c  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180017b82  mov     rcx, rax; String1
0x180017b85  mov     rdx, rbp; String2
0x180017b88  call    cs:__imp__wcsicmp
0x180017b8e  test    eax, eax
0x180017b90  jz      short loc_180017B97
0x180017b92  mov     rdi, [rdi]
0x180017b95  jmp     short loc_180017B68
0x180017b97  mov     edi, 1
0x180017b9c  lock add [rbx+8], edi
0x180017ba0  mov     [r14], rbx
0x180017ba3  xor     eax, eax
0x180017ba5  jmp     loc_180017CEA
0x180017baa  mov     ecx, 70h ; 'p'; Size
0x180017baf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017bb4  mov     rbx, rax
0x180017bb7  test    rax, rax
0x180017bba  jz      loc_180017CE5
0x180017bc0  lea     rax, ??_7MODULE_DLL@@6B@; const MODULE_DLL::`vftable'
0x180017bc7  lea     rcx, [rbx+38h]
0x180017bcb  mov     [rbx], rax
0x180017bce  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180017bd4  mov     edi, 1
0x180017bd9  mov     dword ptr [rbx+0Ch], 4C4C444Dh
0x180017be0  lea     r8, [rsp+0C8h+var_88]; enum MODULE_FAILURE_TYPE *
0x180017be5  mov     [rbx+8], edi
0x180017be8  mov     rdx, rbp; unsigned __int16 *
0x180017beb  mov     rcx, rbx; this
0x180017bee  call    ?Create@MODULE_DLL@@AEAAJPEBGPEAW4MODULE_FAILURE_TYPE@@@Z; MODULE_DLL::Create(ushort const *,MODULE_FAILURE_TYPE *)
0x180017bf3  mov     esi, eax
0x180017bf5  test    eax, eax
0x180017bf7  jns     short loc_180017B9C
0x180017bf9  test    rbp, rbp
0x180017bfc  lea     rcx, dword_180039134
0x180017c03  lea     rax, asc_18003C580; "???"
0x180017c0a  cmovnz  rcx, rbp
0x180017c0e  mov     [rsp+0C8h+var_78], rax
0x180017c13  cmp     [rsp+0C8h+var_88], 0
0x180017c18  mov     [rsp+0C8h+var_80], rcx
0x180017c1d  jnz     short loc_180017C71
0x180017c1f  mov     r14d, 800700C1h
0x180017c25  cmp     esi, r14d
0x180017c28  jnz     short loc_180017C63
0x180017c2a  lea     r8d, [rdi+1Fh]; nSize
0x180017c2e  lea     rdx, [rsp+0C8h+Buffer]; lpBuffer
0x180017c33  lea     rcx, Name; "PROCESSOR_ARCHITECTURE"
0x180017c3a  call    cs:__imp_GetEnvironmentVariableW
0x180017c40  test    eax, eax
0x180017c42  jz      short loc_180017C4E
0x180017c44  lea     rax, [rsp+0C8h+Buffer]
0x180017c49  mov     [rsp+0C8h+var_78], rax
0x180017c4e  mov     ecx, r14d; int
0x180017c51  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180017c56  mov     edx, 0C00008EAh
0x180017c5b  mov     r8d, 2
0x180017c61  jmp     short loc_180017C80
0x180017c63  mov     ecx, esi; int
0x180017c65  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180017c6a  mov     edx, 0C00008E8h
0x180017c6f  jmp     short loc_180017C7D
0x180017c71  mov     ecx, esi; int
0x180017c73  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180017c78  mov     edx, 0C00008F7h
0x180017c7d  mov     r8d, edi
0x180017c80  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x180017c87  lea     r9, [rsp+0C8h+var_80]
0x180017c8c  add     rcx, 1Ch
0x180017c90  mov     [rsp+0C8h+var_A8], eax
0x180017c94  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x180017c9a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180017ca1  jz      short loc_180017CD9
0x180017ca3  mov     rcx, cs:g_pDebug
0x180017caa  lea     rax, aFailedToLoadGl; "Failed to load global module %S\n"
0x180017cb1  mov     [rsp+0C8h+var_98], rbp
0x180017cb6  lea     r9, aModuleDllGetmo; "MODULE_DLL::GetModuleDll"
0x180017cbd  mov     [rsp+0C8h+var_A0], rax
0x180017cc2  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180017cc9  mov     r8d, 0DAh
0x180017ccf  mov     [rsp+0C8h+var_A8], esi
0x180017cd3  call    cs:__imp_PuDbgPrintError
0x180017cd9  mov     rcx, rbx; this
0x180017cdc  call    ?DereferenceModuleDll@MODULE_DLL@@QEAAXXZ; MODULE_DLL::DereferenceModuleDll(void)
0x180017ce1  mov     eax, esi
0x180017ce3  jmp     short loc_180017CEA
0x180017ce5  mov     eax, 80070008h
0x180017cea  mov     rcx, [rsp+0C8h+var_28]
0x180017cf2  xor     rcx, rsp; StackCookie
0x180017cf5  call    __security_check_cookie
0x180017cfa  lea     r11, [rsp+0C8h+var_18]
0x180017d02  mov     rbx, [r11+30h]
0x180017d06  mov     rbp, [r11+38h]
0x180017d0a  mov     rsp, r11
0x180017d0d  pop     r14
0x180017d0f  pop     rdi
0x180017d10  pop     rsi
0x180017d11  retn
```
