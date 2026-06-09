# LogMsgHR(long,wchar_t *,ushort)

- ea: `0x180013c74`
- end: `0x180013d17`
- name: `?LogMsgHR@@YAXJPEA_WG@Z`
- size: `163`
- prototype: `void __fastcall(int, wchar_t *, unsigned __int16)`
- caller_count: `170`
- callee_count: `3`
- tags: ``

## callers

- `0x180005488`
- `0x1800055e0`
- `0x180005680`
- `0x180008490`
- `0x180008550`
- `0x180009254`
- `0x1800094b4`
- `0x180009874`
- `0x180009b20`
- `0x18000a120`
- `0x18000a6c4`
- `0x18000a8b8`
- `0x18000ac70`
- `0x18000acd0`
- `0x18000ad40`
- `0x18000adf0`
- `0x18000b080`
- `0x18000b360`
- `0x18000b480`
- `0x18000b4e0`
- `0x18000b540`
- `0x18000b620`
- `0x18000b680`
- `0x18000b6d0`
- `0x18000b760`
- `0x18000b890`
- `0x18000b9b0`
- `0x18000bb00`
- `0x18000bb50`
- `0x18000bbe0`
- `0x18000bce0`
- `0x18000bd30`
- `0x18000be60`
- `0x18000bf10`
- `0x18000bf80`
- `0x18000c0c0`
- `0x18000c220`
- `0x18000c290`
- `0x18000c320`
- `0x18000c3a0`
- `0x18000c400`
- `0x18000c4ec`
- `0x18000c5f4`
- `0x18000c764`
- `0x18000c994`
- `0x18000cafc`
- `0x18000cc28`
- `0x18000cee8`
- `0x18000d238`
- `0x18000d460`

## callees

- `0x180007e10`
- `0x180013c74`
- `0x1800211e0`

## import_xrefs

- `mqsec!?KeepErrorHistory@COutputReport@@QEAAXPEB_WGJ@Z` at `0x180013c90`
- `mqsec!?KeepErrorHistory@COutputReport@@QEAAXPEB_WGJ@Z` at `0x180013c90`
- `mqsec!Report` at `0x180013c89`

## pseudocode

```c
void __fastcall LogMsgHR(int a1, wchar_t *a2, unsigned __int16 a3)
{
  const wchar_t *v3; // rbx
  unsigned int v4; // eax
  int v5; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int16 v6; // [rsp+80h] [rbp+18h] BYREF

  v6 = a3;
  v5 = a1;
  v3 = a2;
  COutputReport::KeepErrorHistory(Report, a2, a3, a1);
  if ( g_pMSMQErrorLoggingTrace )
  {
    if ( !v3 )
      v3 = L"Not Found";
    v4 = mqwcslen(v3);
    CMSMQTrace::MSMQTraceEvent(g_pMSMQErrorLoggingTrace, 1, 1, 2LL * (v4 + 1), v3, 2, &v6, 4, &v5, 0, 0);
  }
}

```

## disassembly

```asm
0x180013c74  mov     [rsp+arg_10], r8w
0x180013c7a  mov     [rsp+arg_0], ecx
0x180013c7e  push    rbx
0x180013c7f  sub     rsp, 60h
0x180013c83  mov     r9d, ecx
0x180013c86  mov     rbx, rdx
0x180013c89  mov     rcx, cs:__imp_?Report@@3VCOutputReport@@A; COutputReport Report
0x180013c90  call    cs:__imp_?KeepErrorHistory@COutputReport@@QEAAXPEB_WGJ@Z; COutputReport::KeepErrorHistory(wchar_t const *,ushort,long)
0x180013c96  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180013c9e  jz      short loc_180013D11
0x180013ca0  lea     rax, aNotFound; "Not Found"
0x180013ca7  test    rbx, rbx
0x180013caa  cmovz   rbx, rax
0x180013cae  mov     rcx, rbx; wchar_t *
0x180013cb1  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180013cb6  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180013cbd  mov     edx, 1
0x180013cc2  mov     [rsp+68h+var_18], 0
0x180013ccb  mov     r8d, edx
0x180013cce  mov     [rsp+68h+var_20], 0
0x180013cd7  lea     r9d, [rdx+rax]
0x180013cdb  lea     rax, [rsp+68h+arg_0]
0x180013ce0  add     r9, r9
0x180013ce3  mov     [rsp+68h+var_28], rax
0x180013ce8  lea     rax, [rsp+68h+arg_10]
0x180013cf0  mov     [rsp+68h+var_30], 4
0x180013cf9  mov     [rsp+68h+var_38], rax
0x180013cfe  mov     [rsp+68h+var_40], 2
0x180013d07  mov     [rsp+68h+var_48], rbx
0x180013d0c  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x180013d11  add     rsp, 60h
0x180013d15  pop     rbx
0x180013d16  retn
```
