# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180003494`
- end: `0x18000359b`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `263`
- prototype: `bool __fastcall(wil::details **this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x180006190`
- `0x1800085ac`
- `0x180008600`

## callees

- `0x180003494`
- `0x1800035a4`
- `0x180003ea8`
- `0x180004310`
- `0x180006b7c`
- `0x180008ddc`
- `0x18000a00c`

## pseudocode

```c
bool __fastcall wil::details_abi::RawUsageIndex::RecordUsage(
        wil::details **this,
        void *a2,
        unsigned __int64 a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  unsigned __int64 v11; // rdx
  void *v12; // rdx
  void *v13[2]; // [rsp+30h] [rbp-68h] BYREF
  wil::details *v14[2]; // [rsp+40h] [rbp-58h] BYREF

  if ( wil::details_abi::RawUsageIndex::RecordUsageInternal((wil::details_abi::RawUsageIndex *)this, a2, a3, a4, a5, a6) )
    return 1;
  v11 = a3 + a5 + 32;
  if ( this[3] )
  {
    if ( *((_BYTE *)this + 58) )
      wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)(this + 3), v11);
  }
  else
  {
    *(_OWORD *)v13 = 0;
    *(_OWORD *)v14 = 0;
    if ( wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)v13, v11 + 10) )
    {
      wil::details_abi::RawUsageIndex::SetBuffer(
        (wil::details_abi::RawUsageIndex *)this,
        v13[0],
        0,
        (char *)v14[0] - (char *)v13[0]);
      wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(this + 6, &v14[1]);
      *((_BYTE *)this + 58) = 1;
    }
    if ( v14[1] )
      wil::details::FreeProcessHeap(v14[1], v12);
  }
  return wil::details_abi::RawUsageIndex::RecordUsageInternal(
           (wil::details_abi::RawUsageIndex *)this,
           a2,
           a3,
           a4,
           a5,
           a6);
}

```

## disassembly

```asm
0x180003494  push    rbx
0x180003496  push    rbp
0x180003497  push    rsi
0x180003498  push    rdi
0x180003499  push    r12
0x18000349b  push    r14
0x18000349d  push    r15
0x18000349f  sub     rsp, 60h
0x1800034a3  mov     rax, cs:__security_cookie
0x1800034aa  xor     rax, rsp
0x1800034ad  mov     [rsp+98h+var_48], rax
0x1800034b2  mov     r12d, [rsp+98h+arg_28]
0x1800034ba  mov     r15, r9
0x1800034bd  mov     rbp, [rsp+98h+arg_20]
0x1800034c5  mov     rsi, r8
0x1800034c8  mov     [rsp+98h+var_70], r12d; unsigned int
0x1800034cd  mov     r14, rdx
0x1800034d0  mov     [rsp+98h+var_78], rbp; unsigned __int64
0x1800034d5  mov     rbx, rcx
0x1800034d8  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800034dd  test    al, al
0x1800034df  jz      short loc_1800034E8
0x1800034e1  mov     al, 1
0x1800034e3  jmp     loc_18000357F
0x1800034e8  lea     rdx, [rbp+20h]
0x1800034ec  add     rdx, rsi; unsigned __int64
0x1800034ef  cmp     qword ptr [rbx+18h], 0
0x1800034f4  jnz     short loc_180003555
0x1800034f6  xorps   xmm0, xmm0
0x1800034f9  lea     rcx, [rsp+98h+var_68]; this
0x1800034fe  xorps   xmm1, xmm1
0x180003501  add     rdx, 0Ah; unsigned __int64
0x180003505  movdqu  xmmword ptr [rsp+98h+var_68], xmm0
0x18000350b  movdqu  xmmword ptr [rsp+98h+var_58], xmm1
0x180003511  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180003516  test    al, al
0x180003518  jz      short loc_180003544
0x18000351a  mov     rdx, [rsp+98h+var_68]; void *
0x18000351f  xor     r8d, r8d; unsigned __int64
0x180003522  mov     r9, [rsp+98h+var_58]
0x180003527  mov     rcx, rbx; this
0x18000352a  sub     r9, rdx; unsigned __int64
0x18000352d  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180003532  lea     rcx, [rbx+30h]
0x180003536  lea     rdx, [rsp+98h+var_58+8]
0x18000353b  call    ??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x180003540  mov     byte ptr [rbx+3Ah], 1
0x180003544  mov     rcx, [rsp+98h+var_58+8]; this
0x180003549  test    rcx, rcx
0x18000354c  jz      short loc_180003564
0x18000354e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180003553  jmp     short loc_180003564
0x180003555  cmp     byte ptr [rbx+3Ah], 0
0x180003559  jz      short loc_180003564
0x18000355b  lea     rcx, [rbx+18h]; this
0x18000355f  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180003564  mov     [rsp+98h+var_70], r12d; unsigned int
0x180003569  mov     r9, r15; void *
0x18000356c  mov     r8, rsi; unsigned __int64
0x18000356f  mov     [rsp+98h+var_78], rbp; unsigned __int64
0x180003574  mov     rdx, r14; void *
0x180003577  mov     rcx, rbx; this
0x18000357a  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000357f  mov     rcx, [rsp+98h+var_48]
0x180003584  xor     rcx, rsp; StackCookie
0x180003587  call    __security_check_cookie
0x18000358c  add     rsp, 60h
0x180003590  pop     r15
0x180003592  pop     r14
0x180003594  pop     r12
0x180003596  pop     rdi
0x180003597  pop     rsi
0x180003598  pop     rbp
0x180003599  pop     rbx
0x18000359a  retn
```
