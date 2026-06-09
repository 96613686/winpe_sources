# PROVIDER_DEFINITIONS_STORED_ENTRY::InitializeInstance(ushort const *,ushort const *,ulong,ushort const *)

- ea: `0x18000795c`
- end: `0x180007a79`
- name: `?InitializeInstance@PROVIDER_DEFINITIONS_STORED_ENTRY@@QEAAJPEBG0K0@Z`
- size: `285`
- prototype: `int(PROVIDER_DEFINITIONS_STORED_ENTRY *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180006354`

## callees

- `0x180001008`
- `0x180007934`
- `0x18000795c`
- `0x18000a4dc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180007983`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180007983`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000796e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000796e`
- `iisutil!PuDbgPrintError` at `0x180007a03`
- `iisutil!PuDbgPrintError` at `0x180007a03`

## string_xrefs

- `0x1800079f2`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\provider_definitions_stored_list.cxx`

## pseudocode

```c
HRESULT __fastcall PROVIDER_DEFINITIONS_STORED_ENTRY::InitializeInstance(
        PROVIDER_DEFINITIONS_STORED_ENTRY *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  unsigned __int64 v5; // rsi
  HRESULT result; // eax
  HRESULT v9; // eax
  HRESULT v10; // ebx
  unsigned __int64 v11; // rdi
  __int64 v12; // rax
  bool v13; // cf
  size_t v14; // rax
  unsigned __int64 *v15; // rax
  _QWORD *v16; // rbx
  TRACE_AREA_VALUES_STORED_ENTRY *i; // rsi
  unsigned __int16 *v18[9]; // [rsp+40h] [rbp-48h] BYREF

  v5 = a4;
  result = STRU::Copy(this, a2);
  if ( result >= 0 )
  {
    v9 = CLSIDFromString(a3, (LPCLSID)((char *)this + 56));
    v10 = v9;
    if ( v9 >= 0 )
    {
      *((_DWORD *)this + 18) = v5;
      v11 = v5;
      v12 = v5 << 6;
      if ( !is_mul_ok(v5, 0x40u) )
        v12 = -1;
      v13 = __CFADD__(v12, 8);
      v14 = v12 + 8;
      if ( v13 )
        v14 = -1;
      v15 = (unsigned __int64 *)operator new(v14);
      if ( v15 )
      {
        *v15 = v5;
        v16 = v15 + 1;
        for ( i = (TRACE_AREA_VALUES_STORED_ENTRY *)(v15 + 1); v11; --v11 )
        {
          TRACE_AREA_VALUES_STORED_ENTRY::TRACE_AREA_VALUES_STORED_ENTRY(i);
          i = (TRACE_AREA_VALUES_STORED_ENTRY *)((char *)i + 64);
        }
      }
      else
      {
        v16 = 0;
      }
      *((_QWORD *)this + 10) = v16;
      return v16 == 0 ? 0x80070008 : 0;
    }
    else
    {
      v18[3] = a5;
      v18[0] = 0;
      v18[1] = 0;
      v18[2] = (unsigned __int16 *)a3;
      FREB_LOG_NT_EVENT_TABLE::LogEvent(0x800008F3, 4u, (const unsigned __int16 **const)v18, v9);
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrintError(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\provider_definitions_stored_list.cxx",
          80,
          "PROVIDER_DEFINITIONS_STORED_ENTRY::InitializeInstance",
          v10,
          "Failed to process GUID (%S)\n",
          a3);
      return v10;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000795c  push    rbx
0x18000795e  push    rbp
0x18000795f  push    rsi
0x180007960  push    rdi
0x180007961  sub     rsp, 68h
0x180007965  mov     esi, r9d
0x180007968  mov     rdi, r8
0x18000796b  mov     rbp, rcx
0x18000796e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180007974  test    eax, eax
0x180007976  js      loc_180007A70
0x18000797c  lea     rdx, [rbp+38h]; pclsid
0x180007980  mov     rcx, rdi; lpsz
0x180007983  call    cs:__imp_CLSIDFromString
0x180007989  mov     ebx, eax
0x18000798b  test    eax, eax
0x18000798d  jns     short loc_180007A0D
0x18000798f  mov     rcx, [rsp+88h+arg_20]
0x180007997  lea     r8, [rsp+88h+var_48]; unsigned __int16 **
0x18000799c  mov     [rsp+88h+var_30], rcx
0x1800079a1  mov     edx, 4; unsigned __int16
0x1800079a6  mov     ecx, 800008F3h; unsigned int
0x1800079ab  mov     [rsp+88h+var_48], 0
0x1800079b4  mov     r9d, eax; unsigned int
0x1800079b7  mov     [rsp+88h+var_40], 0
0x1800079c0  mov     [rsp+88h+var_38], rdi
0x1800079c5  call    ?LogEvent@FREB_LOG_NT_EVENT_TABLE@@SAXKGQEAPEBGK@Z; FREB_LOG_NT_EVENT_TABLE::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x1800079ca  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800079d1  jz      short loc_180007A09
0x1800079d3  mov     rcx, cs:g_pDebug
0x1800079da  lea     rax, aFailedToProces; "Failed to process GUID (%S)\n"
0x1800079e1  mov     [rsp+88h+var_58], rdi
0x1800079e6  lea     r9, aProviderDefini_0; "PROVIDER_DEFINITIONS_STORED_ENTRY::Init"...
0x1800079ed  mov     [rsp+88h+var_60], rax
0x1800079f2  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800079f9  mov     r8d, 50h ; 'P'
0x1800079ff  mov     [rsp+88h+var_68], ebx
0x180007a03  call    cs:__imp_PuDbgPrintError
0x180007a09  mov     eax, ebx
0x180007a0b  jmp     short loc_180007A70
0x180007a0d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180007a14  mov     [rbp+48h], esi
0x180007a17  mov     eax, 40h ; '@'
0x180007a1c  mov     rdi, rsi
0x180007a1f  mul     rsi
0x180007a22  cmovb   rax, rcx
0x180007a26  add     rax, 8
0x180007a2a  cmovb   rax, rcx
0x180007a2e  mov     rcx, rax; Size
0x180007a31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007a36  test    rax, rax
0x180007a39  jz      short loc_180007A5E
0x180007a3b  mov     [rax], rsi
0x180007a3e  lea     rbx, [rax+8]
0x180007a42  mov     rsi, rbx
0x180007a45  test    rdi, rdi
0x180007a48  jz      short loc_180007A60
0x180007a4a  mov     rcx, rsi; this
0x180007a4d  call    ??0TRACE_AREA_VALUES_STORED_ENTRY@@QEAA@XZ; TRACE_AREA_VALUES_STORED_ENTRY::TRACE_AREA_VALUES_STORED_ENTRY(void)
0x180007a52  add     rsi, 40h ; '@'
0x180007a56  sub     rdi, 1
0x180007a5a  jnz     short loc_180007A4A
0x180007a5c  jmp     short loc_180007A60
0x180007a5e  xor     ebx, ebx
0x180007a60  mov     [rbp+50h], rbx
0x180007a64  neg     rbx
0x180007a67  sbb     eax, eax
0x180007a69  not     eax
0x180007a6b  and     eax, 80070008h
0x180007a70  add     rsp, 68h
0x180007a74  pop     rdi
0x180007a75  pop     rsi
0x180007a76  pop     rbp
0x180007a77  pop     rbx
0x180007a78  retn
```
