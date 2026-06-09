# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x140008c20`
- end: `0x140008d13`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `243`
- prototype: `bool __fastcall(wil::details **this, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x14000d7c0`

## callees

- `0x140008c20`
- `0x140008d1c`
- `0x140009b80`
- `0x14000a170`
- `0x14000f3c8`
- `0x14000fe5c`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(
        wil::details **this,
        int a2,
        int a3)
{
  void *v5[2]; // [rsp+30h] [rbp-28h] BYREF
  __int128 v6; // [rsp+40h] [rbp-18h] BYREF
  int v7; // [rsp+68h] [rbp+10h] BYREF
  int v8; // [rsp+70h] [rbp+18h] BYREF

  v8 = a3;
  v7 = a2;
  if ( wil::details_abi::RawUsageIndex::RecordUsageInternal(
         (wil::details_abi::RawUsageIndex *)this,
         &v7,
         4u,
         &v8,
         4u,
         1u) )
  {
    return 1;
  }
  if ( this[3] )
  {
    if ( *((_BYTE *)this + 58) )
      wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(this + 3), 0x28u);
  }
  else
  {
    *(_OWORD *)v5 = 0;
    v6 = 0;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)v5, 0x32u) )
    {
      wil::details_abi::RawUsageIndex::SetBuffer(
        (wil::details_abi::RawUsageIndex *)this,
        (char *)v5[0],
        0,
        (const char *)(v6 - (unsigned __int64)v5[0]));
      wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(this + 6, (wil::details **)&v6 + 1);
      *((_BYTE *)this + 58) = 1;
    }
    wistd::unique_ptr<void,wil::process_heap_deleter>::reset((char *)&v6 + 8, 0);
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(
           (wil::details_abi::RawUsageIndex *)this,
           &v7,
           4u,
           &v8,
           4u,
           1u);
}

```

## disassembly

```asm
0x140008c20  mov     [rsp+arg_10], r8d
0x140008c25  mov     [rsp+arg_8], edx
0x140008c29  push    rbx
0x140008c2a  sub     rsp, 50h
0x140008c2e  mov     [rsp+58h+var_30], 1; unsigned int
0x140008c36  lea     r9, [rsp+58h+arg_10]; void *
0x140008c3b  mov     r8d, 4; unsigned __int64
0x140008c41  mov     [rsp+58h+var_38], 4; unsigned __int64
0x140008c4a  lea     rdx, [rsp+58h+arg_8]; void *
0x140008c4f  mov     rbx, rcx
0x140008c52  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140008c57  test    al, al
0x140008c59  jz      short loc_140008C63
0x140008c5b  mov     al, 1
0x140008c5d  add     rsp, 50h
0x140008c61  pop     rbx
0x140008c62  retn
0x140008c63  cmp     qword ptr [rbx+18h], 0
0x140008c68  mov     [rsp+58h+arg_0], rdi
0x140008c6d  jnz     short loc_140008CCC
0x140008c6f  xorps   xmm0, xmm0
0x140008c72  lea     rcx, [rsp+58h+var_28]; this
0x140008c77  xorps   xmm1, xmm1
0x140008c7a  mov     edx, 32h ; '2'; unsigned __int64
0x140008c7f  movdqu  xmmword ptr [rsp+58h+var_28], xmm0
0x140008c85  movdqu  [rsp+58h+var_18], xmm1
0x140008c8b  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140008c90  test    al, al
0x140008c92  jz      short loc_140008CBE
0x140008c94  mov     rdx, [rsp+58h+var_28]; void *
0x140008c99  xor     r8d, r8d; unsigned __int64
0x140008c9c  mov     r9, qword ptr [rsp+58h+var_18]
0x140008ca1  mov     rcx, rbx; this
0x140008ca4  sub     r9, rdx; unsigned __int64
0x140008ca7  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x140008cac  lea     rcx, [rbx+30h]
0x140008cb0  lea     rdx, [rsp+58h+var_18+8]
0x140008cb5  call    ??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x140008cba  mov     byte ptr [rbx+3Ah], 1
0x140008cbe  xor     edx, edx
0x140008cc0  lea     rcx, [rsp+58h+var_18+8]
0x140008cc5  call    ?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)
0x140008cca  jmp     short loc_140008CE0
0x140008ccc  cmp     byte ptr [rbx+3Ah], 0
0x140008cd0  jz      short loc_140008CE0
0x140008cd2  mov     edx, 28h ; '('; unsigned __int64
0x140008cd7  lea     rcx, [rbx+18h]; this
0x140008cdb  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x140008ce0  mov     [rsp+58h+var_30], 1; unsigned int
0x140008ce8  lea     r9, [rsp+58h+arg_10]; void *
0x140008ced  mov     r8d, 4; unsigned __int64
0x140008cf3  mov     [rsp+58h+var_38], 4; unsigned __int64
0x140008cfc  lea     rdx, [rsp+58h+arg_8]; void *
0x140008d01  mov     rcx, rbx; this
0x140008d04  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140008d09  mov     rdi, [rsp+58h+arg_0]
0x140008d0e  jmp     loc_140008C5D
```
