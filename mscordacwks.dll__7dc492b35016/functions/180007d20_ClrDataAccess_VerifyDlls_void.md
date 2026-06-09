# ClrDataAccess::VerifyDlls(void)

- ea: `0x180007d20`
- end: `0x180007ea7`
- name: `?VerifyDlls@ClrDataAccess@@AEAAJXZ`
- size: `391`
- prototype: `__int64 __fastcall(ClrDataAccess *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180006560`

## callees

- `0x180007d20`
- `0x18000a498`
- `0x18000b30c`
- `0x1800210f0`
- `0x180078540`
- `0x180078a98`
- `0x1800f0d20`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180007d81`
- `KERNEL32!EnterCriticalSection` at `0x180007d81`
- `KERNEL32!LeaveCriticalSection` at `0x180007e59`
- `KERNEL32!LeaveCriticalSection` at `0x180007e59`

## string_xrefs

- `0x180007e1d`: `Failed to find any valid codeview debug directory entry in %s image`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ClrDataAccess::VerifyDlls(ClrDataAccess *this, bool a2)
{
  int v4; // esi
  int v5; // r14d
  ClrDataAccess *v6; // r15
  unsigned __int64 v7; // rbx
  unsigned int i; // edi
  struct Exception *v9; // rbx
  BOOL v10; // edi
  struct IExecutionEngine *ExecutionEngine; // rax
  struct Exception *v12; // rcx
  bool v13; // [rsp+20h] [rbp-4A8h] BYREF
  int v14; // [rsp+24h] [rbp-4A4h]
  int v15; // [rsp+28h] [rbp-4A0h] BYREF
  unsigned __int64 v16; // [rsp+30h] [rbp-498h]
  BOOL v17; // [rsp+38h] [rbp-490h]
  unsigned int v18; // [rsp+40h] [rbp-488h]
  ClrDataAccess *v19; // [rsp+48h] [rbp-480h]
  char v20; // [rsp+50h] [rbp-478h] BYREF
  unsigned __int64 v21; // [rsp+58h] [rbp-470h]
  _QWORD v22[6]; // [rsp+60h] [rbp-468h] BYREF
  unsigned __int64 v23; // [rsp+90h] [rbp-438h] BYREF
  char Buffer[1024]; // [rsp+A0h] [rbp-428h] BYREF

  if ( CLRConfig::GetConfigValue(
         (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::INTERNAL_DbgDACSkipVerifyDlls,
         a2,
         &v13) )
  {
    return 0;
  }
  v4 = 0;
  v14 = 0;
  v5 = 0;
  v15 = 0;
  EnterCriticalSection(&g_dacCritSec);
  v6 = g_dacImpl;
  v19 = g_dacImpl;
  g_dacImpl = this;
  v21 = 0;
  try
  {
    try
    {
      v16 = (unsigned __int64)&v20;
      v16 = *((_QWORD *)this + 7);
      PEDecoder::PEDecoder(v22, v16);
      for ( i = 0; ; ++i )
      {
        v18 = i;
        if ( i >= 0x20 )
          break;
        PEDecoder::GetDebugDirectoryEntry((PEDecoder *)v22);
        v7 = v16;
        if ( !v16 )
          break;
        if ( *((_DWORD *)DacInstantiateTypeByAddressHelper(v16, 0x1Cu, 1, 1) + 3) == 2 )
        {
          v4 = *((_DWORD *)DacInstantiateTypeByAddressHelper(v7, 0x1Cu, 1, 1) + 1);
          v14 = v4;
          break;
        }
      }
      _snprintf_s<1024>(Buffer, 0x400u, "Failed to find any valid codeview debug directory entry in %s image");
    }
    catch ( Exception *v23 )
    {
      v21 = v23;
      throw;
    }
  }
  catch ( ... )
  {
    v22[1] = 0;
    v22[0] = &DelegatingException::`vftable';
    v22[2] = -1;
    v9 = (struct Exception *)v21;
    v16 = v21;
    v10 = v21 != 0;
    v17 = v10;
    if ( !(__int64)__ClrFlsGetBlock() )
    {
      ExecutionEngine = GetExecutionEngine();
      (*(void (__fastcall **)(struct IExecutionEngine *, __int64))(*(_QWORD *)ExecutionEngine + 40LL))(
        ExecutionEngine,
        18);
    }
    v12 = (struct Exception *)v22;
    if ( v9 )
      v12 = v9;
    if ( !DacExceptionFilter(v12, this, &v15) )
    {
      v17 = 0;
      throw;
    }
    if ( v10 )
    {
      if ( v9 )
      {
        if ( !(*(unsigned int (__fastcall **)(struct Exception *))(*(_QWORD *)v9 + 80LL))(v9) )
          (**(void (__fastcall ***)(struct Exception *, __int64))v9)(v9, 5);
      }
      v17 = 0;
    }
    DelegatingException::~DelegatingException((DelegatingException *)v22);
    v4 = v14;
    v5 = v15;
    v6 = v19;
  }
  g_dacImpl = v6;
  LeaveCriticalSection(&g_dacCritSec);
  if ( v5 < 0 )
    return (unsigned int)v5;
  if ( v4 && v4 == g_dacTableInfo )
    return 0;
  return 2148736057LL;
}

```

## disassembly

```asm
0x180007d20  mov     [rsp+arg_8], rbx
0x180007d25  mov     [rsp+arg_10], rsi
0x180007d2a  mov     [rsp+arg_0], rcx
0x180007d2f  push    rdi
0x180007d30  push    r14
0x180007d32  push    r15
0x180007d34  sub     rsp, 4B0h
0x180007d3b  mov     rax, cs:__security_cookie
0x180007d42  xor     rax, rsp
0x180007d45  mov     [rsp+4C8h+var_28], rax
0x180007d4d  mov     rbx, rcx
0x180007d50  lea     r8, [rsp+4C8h+var_4A8]; bool *
0x180007d55  lea     rcx, ?INTERNAL_DbgDACSkipVerifyDlls@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x180007d5c  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x180007d61  test    eax, eax
0x180007d63  jz      short loc_180007D6C
0x180007d65  xor     eax, eax
0x180007d67  jmp     loc_180007E7E
0x180007d6c  xor     esi, esi
0x180007d6e  mov     [rsp+4C8h+var_4A4], esi
0x180007d72  xor     r14d, r14d
0x180007d75  mov     [rsp+4C8h+var_4A0], r14d
0x180007d7a  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180007d81  call    cs:__imp_EnterCriticalSection
0x180007d87  mov     r15, cs:?g_dacImpl@@3PEAVClrDataAccess@@EA; ClrDataAccess * g_dacImpl
0x180007d8e  mov     [rsp+4C8h+var_480], r15
0x180007d93  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, rbx; ClrDataAccess * g_dacImpl
0x180007d9a  and     [rsp+4C8h+var_470], rsi
0x180007d9f  lea     rax, [rsp+4C8h+var_478]
0x180007da4  mov     [rsp+4C8h+var_498], rax
0x180007da9  mov     rdx, [rbx+38h]
0x180007dad  mov     [rsp+4C8h+var_498], rdx
0x180007db2  lea     rcx, [rsp+4C8h+var_468]
0x180007db7  call    ??0PEDecoder@@QEAA@V__VoidPtr@@_N@Z; PEDecoder::PEDecoder(__VoidPtr,bool)
0x180007dbc  xor     edi, edi
0x180007dbe  mov     [rsp+4C8h+var_488], edi
0x180007dc2  cmp     edi, 20h ; ' '
0x180007dc5  jnb     short loc_180007E16
0x180007dc7  mov     r8d, edi
0x180007dca  lea     rdx, [rsp+4C8h+var_498]
0x180007dcf  lea     rcx, [rsp+4C8h+var_468]; this
0x180007dd4  call    ?GetDebugDirectoryEntry@PEDecoder@@QEBA?AV?$__DPtr@U_IMAGE_DEBUG_DIRECTORY@@@@I@Z; PEDecoder::GetDebugDirectoryEntry(uint)
0x180007dd9  mov     rbx, [rsp+4C8h+var_498]
0x180007dde  test    rbx, rbx
0x180007de1  jz      short loc_180007E16
0x180007de3  mov     r9b, 1; bool
0x180007de6  mov     r8b, r9b; bool
0x180007de9  mov     edx, 1Ch; unsigned int
0x180007dee  mov     rcx, rbx; unsigned __int64
0x180007df1  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180007df6  cmp     dword ptr [rax+0Ch], 2
0x180007dfa  jnz     short loc_180007E39
0x180007dfc  mov     r9b, 1; bool
0x180007dff  mov     r8b, r9b; bool
0x180007e02  mov     edx, 1Ch; unsigned int
0x180007e07  mov     rcx, rbx; unsigned __int64
0x180007e0a  call    ?DacInstantiateTypeByAddressHelper@@YAPEAX_KI_N1@Z; DacInstantiateTypeByAddressHelper(unsigned __int64,uint,bool,bool)
0x180007e0f  mov     esi, [rax+4]
0x180007e12  mov     [rsp+4C8h+var_4A4], esi
0x180007e16  lea     r9, aClr_0; "clr"
0x180007e1d  lea     r8, aFailedToFindAn; "Failed to find any valid codeview debug"...
0x180007e24  mov     edx, 400h; MaxCount
0x180007e29  lea     rcx, [rsp+4C8h+Buffer]; Buffer
0x180007e31  call    ??$_snprintf_s@$0EAA@@@YAHAEAY0EAA@D_KPEBDZZ; _snprintf_s<1024>(char (&)[1024],unsigned __int64,char const *,...)
0x180007e36  nop
0x180007e37  jmp     short loc_180007E4B
0x180007e39  inc     edi
0x180007e3b  jmp     short loc_180007DBE
0x180007e3d  mov     esi, [rsp+4C8h+var_4A4]
0x180007e41  mov     r14d, [rsp+4C8h+var_4A0]
0x180007e46  mov     r15, [rsp+4C8h+var_480]
0x180007e4b  mov     cs:?g_dacImpl@@3PEAVClrDataAccess@@EA, r15; ClrDataAccess * g_dacImpl
0x180007e52  lea     rcx, ?g_dacCritSec@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180007e59  call    cs:__imp_LeaveCriticalSection
0x180007e5f  test    r14d, r14d
0x180007e62  jns     short loc_180007E69
0x180007e64  mov     eax, r14d
0x180007e67  jmp     short loc_180007E7E
0x180007e69  test    esi, esi
0x180007e6b  jz      short loc_180007E79
0x180007e6d  cmp     esi, dword ptr cs:?g_dacTableInfo@@3UDacTableInfo@@A; DacTableInfo g_dacTableInfo
0x180007e73  jz      loc_180007D65
0x180007e79  mov     eax, 80131C39h
0x180007e7e  mov     rcx, [rsp+4C8h+var_28]
0x180007e86  xor     rcx, rsp; StackCookie
0x180007e89  call    __security_check_cookie
0x180007e8e  lea     r11, [rsp+4C8h+var_18]
0x180007e96  mov     rbx, [r11+28h]
0x180007e9a  mov     rsi, [r11+30h]
0x180007e9e  mov     rsp, r11
0x180007ea1  pop     r15
0x180007ea3  pop     r14
0x180007ea5  pop     rdi
0x180007ea6  retn
```
