# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180003864`
- end: `0x18000394f`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `235`
- prototype: `bool __fastcall(wil::details **this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180005bd0`
- `0x180008304`
- `0x180008338`

## callees

- `0x180003864`
- `0x180003958`
- `0x180004330`
- `0x1800064e4`
- `0x1800089dc`
- `0x180009ac4`

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
  void *v13[2]; // [rsp+30h] [rbp-58h] BYREF
  wil::details *v14[2]; // [rsp+40h] [rbp-48h] BYREF

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
0x180003864  push    rbx
0x180003866  push    rbp
0x180003867  push    rsi
0x180003868  push    rdi
0x180003869  push    r12
0x18000386b  push    r14
0x18000386d  push    r15
0x18000386f  sub     rsp, 50h
0x180003873  mov     r12d, [rsp+88h+arg_28]
0x18000387b  mov     r14, r9
0x18000387e  mov     rbp, [rsp+88h+arg_20]
0x180003886  mov     rsi, r8
0x180003889  mov     [rsp+88h+var_60], r12d; unsigned int
0x18000388e  mov     r15, rdx
0x180003891  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x180003896  mov     rbx, rcx
0x180003899  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000389e  test    al, al
0x1800038a0  jz      short loc_1800038A9
0x1800038a2  mov     al, 1
0x1800038a4  jmp     loc_180003940
0x1800038a9  lea     rdx, [rbp+20h]
0x1800038ad  add     rdx, rsi; unsigned __int64
0x1800038b0  cmp     qword ptr [rbx+18h], 0
0x1800038b5  jnz     short loc_180003916
0x1800038b7  xorps   xmm0, xmm0
0x1800038ba  lea     rcx, [rsp+88h+var_58]; this
0x1800038bf  xorps   xmm1, xmm1
0x1800038c2  add     rdx, 0Ah; unsigned __int64
0x1800038c6  movdqu  xmmword ptr [rsp+88h+var_58], xmm0
0x1800038cc  movdqu  xmmword ptr [rsp+88h+var_48], xmm1
0x1800038d2  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800038d7  test    al, al
0x1800038d9  jz      short loc_180003905
0x1800038db  mov     rdx, [rsp+88h+var_58]; void *
0x1800038e0  xor     r8d, r8d; unsigned __int64
0x1800038e3  mov     r9, [rsp+88h+var_48]
0x1800038e8  mov     rcx, rbx; this
0x1800038eb  sub     r9, rdx; unsigned __int64
0x1800038ee  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1800038f3  lea     rcx, [rbx+30h]
0x1800038f7  lea     rdx, [rsp+88h+var_48+8]
0x1800038fc  call    ??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x180003901  mov     byte ptr [rbx+3Ah], 1
0x180003905  mov     rcx, [rsp+88h+var_48+8]; this
0x18000390a  test    rcx, rcx
0x18000390d  jz      short loc_180003925
0x18000390f  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180003914  jmp     short loc_180003925
0x180003916  cmp     byte ptr [rbx+3Ah], 0
0x18000391a  jz      short loc_180003925
0x18000391c  lea     rcx, [rbx+18h]; this
0x180003920  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180003925  mov     [rsp+88h+var_60], r12d; unsigned int
0x18000392a  mov     r9, r14; void *
0x18000392d  mov     r8, rsi; unsigned __int64
0x180003930  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x180003935  mov     rdx, r15; void *
0x180003938  mov     rcx, rbx; this
0x18000393b  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180003940  add     rsp, 50h
0x180003944  pop     r15
0x180003946  pop     r14
0x180003948  pop     r12
0x18000394a  pop     rdi
0x18000394b  pop     rsi
0x18000394c  pop     rbp
0x18000394d  pop     rbx
0x18000394e  retn
```
