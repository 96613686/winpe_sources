# ATL::CCommand<ATL::CDynamicAccessor,ATL::CRowset,ATL::CNoMultipleResults>::Open(ATL::CSession const &,ushort const *,tagDBPROPSET *,__int64 *,_GUID const &,bool,ulong)

- ea: `0x180009790`
- end: `0x180009853`
- name: `?Open@?$CCommand@VCDynamicAccessor@ATL@@VCRowset@2@VCNoMultipleResults@2@@ATL@@QEAAJAEBVCSession@2@PEBGPEAUtagDBPROPSET@@PEA_JAEBU_GUID@@_NK@Z`
- size: `195`
- prototype: `__int64(ATL::CDynamicAccessor *this, const struct ATL::CSession *, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800099e4`

## callees

- `0x180007dac`
- `0x180008ca0`
- `0x180009790`
- `0x18000c010`

## pseudocode

```c
__int64 ATL::CCommand<ATL::CDynamicAccessor,ATL::CRowset,ATL::CNoMultipleResults>::Open(
        ATL::CDynamicAccessor *this,
        const struct ATL::CSession *a2,
        const unsigned __int16 *a3,
        ...)
{
  __int64 result; // rax
  struct IUnknown **v5; // rdi
  int v6; // ebx
  int v7; // eax
  const struct _GUID *v8; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  va_list va1; // [rsp+90h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v8 = va_arg(va1, const struct _GUID *);
  result = ATL::CCommandBase::Create((ATL::CDynamicAccessor *)((char *)this + 112), a2, a3, v8);
  if ( (int)result >= 0 )
  {
    v5 = (struct IUnknown **)((char *)this + 72);
    v8 = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, _QWORD, const struct _GUID **, char *))(**((_QWORD **)this + 14)
                                                                                                  + 32LL))(
           *((_QWORD *)this + 14),
           0,
           &GUID_0c733a7c_2a1c_11ce_ade5_00aa0044773d,
           0,
           (const struct _GUID **)va,
           (char *)this + 72);
    if ( v6 >= 0 && *v5 )
      ((void (__fastcall *)(struct IUnknown *, GUID *, char *))(*v5)->lpVtbl->QueryInterface)(
        *v5,
        &GUID_0c733a05_2a1c_11ce_ade5_00aa0044773d,
        (char *)this + 80);
    if ( v6 >= 0 && *v5 )
    {
      v7 = ATL::CDynamicAccessor::BindColumns(this, *v5);
      v6 = 0;
      if ( v7 < 0 )
        return (unsigned int)v7;
    }
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x180009790  mov     [rsp+arg_0], rbx
0x180009795  mov     [rsp+arg_8], rsi
0x18000979a  mov     [rsp+arg_18], r9
0x18000979f  push    rdi
0x1800097a0  sub     rsp, 60h
0x1800097a4  mov     rsi, rcx
0x1800097a7  add     rcx, 70h ; 'p'; this
0x1800097ab  call    ?Create@CCommandBase@ATL@@QEAAJAEBVCSession@2@PEBGAEBU_GUID@@@Z; ATL::CCommandBase::Create(ATL::CSession const &,ushort const *,_GUID const &)
0x1800097b0  test    eax, eax
0x1800097b2  js      loc_180009843
0x1800097b8  xorps   xmm0, xmm0
0x1800097bb  xor     eax, eax
0x1800097bd  movups  [rsp+68h+var_28], xmm0
0x1800097c2  mov     [rsp+68h+var_18], rax
0x1800097c7  lea     rdi, [rsi+48h]
0x1800097cb  mov     [rsp+68h+arg_18], rax
0x1800097d3  mov     rcx, [rsi+70h]
0x1800097d7  mov     rax, [rcx]
0x1800097da  mov     [rsp+68h+var_40], rdi
0x1800097df  lea     rdx, [rsp+68h+arg_18]
0x1800097e7  mov     [rsp+68h+var_48], rdx
0x1800097ec  xor     r9d, r9d
0x1800097ef  lea     r8, _GUID_0c733a7c_2a1c_11ce_ade5_00aa0044773d
0x1800097f6  xor     edx, edx
0x1800097f8  mov     rax, [rax+20h]
0x1800097fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009801  mov     ebx, eax
0x180009803  test    eax, eax
0x180009805  js      short loc_180009826
0x180009807  mov     rcx, [rdi]
0x18000980a  test    rcx, rcx
0x18000980d  jz      short loc_180009826
0x18000980f  mov     rax, [rcx]
0x180009812  lea     r8, [rdi+8]
0x180009816  lea     rdx, _GUID_0c733a05_2a1c_11ce_ade5_00aa0044773d
0x18000981d  mov     rax, [rax]
0x180009820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009825  nop
0x180009826  test    ebx, ebx
0x180009828  js      short loc_180009841
0x18000982a  mov     rdx, [rdi]; struct IUnknown *
0x18000982d  test    rdx, rdx
0x180009830  jz      short loc_180009841
0x180009832  mov     rcx, rsi; this
0x180009835  call    ?BindColumns@CDynamicAccessor@ATL@@QEAAJPEAUIUnknown@@@Z; ATL::CDynamicAccessor::BindColumns(IUnknown *)
0x18000983a  xor     ebx, ebx
0x18000983c  test    eax, eax
0x18000983e  cmovs   ebx, eax
0x180009841  mov     eax, ebx
0x180009843  mov     rbx, [rsp+68h+arg_0]
0x180009848  mov     rsi, [rsp+68h+arg_8]
0x18000984d  add     rsp, 60h
0x180009851  pop     rdi
0x180009852  retn
```
