# MODULE_DLL::GetModuleDll(ushort const *,MODULE_DLL * *)

- ea: `0x180018f70`
- end: `0x18001917b`
- name: `?GetModuleDll@MODULE_DLL@@SAJPEBGPEAPEAV1@@Z`
- size: `523`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _LIST_ENTRY **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e020`

## callees

- `0x180018f70`
- `0x18001a64c`
- `0x18001ab30`
- `0x18001c4ec`
- `0x18002f958`
- `0x180037790`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180018fd2`
- `msvcrt!_wcsicmp` at `0x180018fd2`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180019090`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x180019090`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001901e`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001901e`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180018fc0`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180018fc0`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800190f0`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x1800190f0`
- `iisutil!PuDbgPrintError` at `0x180019135`
- `iisutil!PuDbgPrintError` at `0x180019135`

## string_xrefs

- `0x180019118`: `MODULE_DLL::GetModuleDll`
- `0x180019124`: `servercommon\inetsrv\iis\iisrearc\iis70\core\moduledll.cxx`

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
  v9 = &dword_18003C134;
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
0x180018f70  mov     [rsp+arg_10], rbx
0x180018f75  mov     [rsp+arg_18], rbp
0x180018f7a  push    rsi
0x180018f7b  push    rdi
0x180018f7c  push    r14
0x180018f7e  sub     rsp, 0B0h
0x180018f85  mov     rax, cs:__security_cookie
0x180018f8c  xor     rax, rsp
0x180018f8f  mov     [rsp+0C8h+var_28], rax
0x180018f97  mov     rdi, cs:?sm_ModuleListHead@MODULE_DLL@@0U_LIST_ENTRY@@A; _LIST_ENTRY MODULE_DLL::sm_ModuleListHead
0x180018f9e  mov     r14, rdx
0x180018fa1  mov     rbp, rcx
0x180018fa4  mov     [rsp+0C8h+var_88], 0
0x180018fac  lea     rax, ?sm_ModuleListHead@MODULE_DLL@@0U_LIST_ENTRY@@A; _LIST_ENTRY MODULE_DLL::sm_ModuleListHead
0x180018fb3  cmp     rdi, rax
0x180018fb6  jz      short loc_180018FFA
0x180018fb8  lea     rbx, [rdi-10h]
0x180018fbc  lea     rcx, [rbx+38h]
0x180018fc0  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180018fc7  nop     dword ptr [rax+rax+00h]
0x180018fcc  mov     rcx, rax; String1
0x180018fcf  mov     rdx, rbp; String2
0x180018fd2  call    cs:__imp__wcsicmp
0x180018fd9  nop     dword ptr [rax+rax+00h]
0x180018fde  test    eax, eax
0x180018fe0  jz      short loc_180018FE7
0x180018fe2  mov     rdi, [rdi]
0x180018fe5  jmp     short loc_180018FAC
0x180018fe7  mov     edi, 1
0x180018fec  lock add [rbx+8], edi
0x180018ff0  mov     [r14], rbx
0x180018ff3  xor     eax, eax
0x180018ff5  jmp     loc_180019152
0x180018ffa  mov     ecx, 70h ; 'p'; Size
0x180018fff  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019004  mov     rbx, rax
0x180019007  test    rax, rax
0x18001900a  jz      loc_18001914D
0x180019010  lea     rax, ??_7MODULE_DLL@@6B@; const MODULE_DLL::`vftable'
0x180019017  lea     rcx, [rbx+38h]
0x18001901b  mov     [rbx], rax
0x18001901e  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180019025  nop     dword ptr [rax+rax+00h]
0x18001902a  mov     edi, 1
0x18001902f  mov     dword ptr [rbx+0Ch], 4C4C444Dh
0x180019036  lea     r8, [rsp+0C8h+var_88]; enum MODULE_FAILURE_TYPE *
0x18001903b  mov     [rbx+8], edi
0x18001903e  mov     rdx, rbp; unsigned __int16 *
0x180019041  mov     rcx, rbx; this
0x180019044  call    ?Create@MODULE_DLL@@AEAAJPEBGPEAW4MODULE_FAILURE_TYPE@@@Z; MODULE_DLL::Create(ushort const *,MODULE_FAILURE_TYPE *)
0x180019049  mov     esi, eax
0x18001904b  test    eax, eax
0x18001904d  jns     short loc_180018FEC
0x18001904f  test    rbp, rbp
0x180019052  lea     rcx, dword_18003C134
0x180019059  lea     rax, asc_18003F580; "???"
0x180019060  cmovnz  rcx, rbp
0x180019064  mov     [rsp+0C8h+var_78], rax
0x180019069  cmp     [rsp+0C8h+var_88], 0
0x18001906e  mov     [rsp+0C8h+var_80], rcx
0x180019073  jnz     short loc_1800190CD
0x180019075  mov     r14d, 800700C1h
0x18001907b  cmp     esi, r14d
0x18001907e  jnz     short loc_1800190BF
0x180019080  lea     r8d, [rdi+1Fh]; nSize
0x180019084  lea     rdx, [rsp+0C8h+Buffer]; lpBuffer
0x180019089  lea     rcx, Name; "PROCESSOR_ARCHITECTURE"
0x180019090  call    cs:__imp_GetEnvironmentVariableW
0x180019097  nop     dword ptr [rax+rax+00h]
0x18001909c  test    eax, eax
0x18001909e  jz      short loc_1800190AA
0x1800190a0  lea     rax, [rsp+0C8h+Buffer]
0x1800190a5  mov     [rsp+0C8h+var_78], rax
0x1800190aa  mov     ecx, r14d; int
0x1800190ad  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800190b2  mov     edx, 0C00008EAh
0x1800190b7  mov     r8d, 2
0x1800190bd  jmp     short loc_1800190DC
0x1800190bf  mov     ecx, esi; int
0x1800190c1  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800190c6  mov     edx, 0C00008E8h
0x1800190cb  jmp     short loc_1800190D9
0x1800190cd  mov     ecx, esi; int
0x1800190cf  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x1800190d4  mov     edx, 0C00008F7h
0x1800190d9  mov     r8d, edi
0x1800190dc  mov     rcx, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x1800190e3  lea     r9, [rsp+0C8h+var_80]
0x1800190e8  add     rcx, 1Ch
0x1800190ec  mov     [rsp+0C8h+var_A8], eax
0x1800190f0  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x1800190f7  nop     dword ptr [rax+rax+00h]
0x1800190fc  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180019103  jz      short loc_180019141
0x180019105  mov     rcx, cs:g_pDebug
0x18001910c  lea     rax, aFailedToLoadGl; "Failed to load global module %S\n"
0x180019113  mov     [rsp+0C8h+var_98], rbp
0x180019118  lea     r9, aModuleDllGetmo; "MODULE_DLL::GetModuleDll"
0x18001911f  mov     [rsp+0C8h+var_A0], rax
0x180019124  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001912b  mov     r8d, 0DAh
0x180019131  mov     [rsp+0C8h+var_A8], esi
0x180019135  call    cs:__imp_PuDbgPrintError
0x18001913c  nop     dword ptr [rax+rax+00h]
0x180019141  mov     rcx, rbx; this
0x180019144  call    ?DereferenceModuleDll@MODULE_DLL@@QEAAXXZ; MODULE_DLL::DereferenceModuleDll(void)
0x180019149  mov     eax, esi
0x18001914b  jmp     short loc_180019152
0x18001914d  mov     eax, 80070008h
0x180019152  mov     rcx, [rsp+0C8h+var_28]
0x18001915a  xor     rcx, rsp; StackCookie
0x18001915d  call    __security_check_cookie
0x180019162  lea     r11, [rsp+0C8h+var_18]
0x18001916a  mov     rbx, [r11+30h]
0x18001916e  mov     rbp, [r11+38h]
0x180019172  mov     rsp, r11
0x180019175  pop     r14
0x180019177  pop     rdi
0x180019178  pop     rsi
0x180019179  retn
```
