# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180007240`
- end: `0x18000732b`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `235`
- prototype: `bool __fastcall(wil::details **this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x180004c40`
- `0x180007170`
- `0x1800071a4`

## callees

- `0x180004c04`
- `0x18000563c`
- `0x180007240`
- `0x180007334`
- `0x180007b6c`
- `0x180008c6c`

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
0x180007240  push    rbx
0x180007242  push    rbp
0x180007243  push    rsi
0x180007244  push    rdi
0x180007245  push    r12
0x180007247  push    r14
0x180007249  push    r15
0x18000724b  sub     rsp, 50h
0x18000724f  mov     r12d, [rsp+88h+arg_28]
0x180007257  mov     r14, r9
0x18000725a  mov     rbp, [rsp+88h+arg_20]
0x180007262  mov     rsi, r8
0x180007265  mov     [rsp+88h+var_60], r12d; unsigned int
0x18000726a  mov     r15, rdx
0x18000726d  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x180007272  mov     rbx, rcx
0x180007275  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000727a  test    al, al
0x18000727c  jz      short loc_180007285
0x18000727e  mov     al, 1
0x180007280  jmp     loc_18000731C
0x180007285  lea     rdx, [rbp+20h]
0x180007289  add     rdx, rsi; unsigned __int64
0x18000728c  cmp     qword ptr [rbx+18h], 0
0x180007291  jnz     short loc_1800072F2
0x180007293  xorps   xmm0, xmm0
0x180007296  lea     rcx, [rsp+88h+var_58]; this
0x18000729b  xorps   xmm1, xmm1
0x18000729e  add     rdx, 0Ah; unsigned __int64
0x1800072a2  movdqu  xmmword ptr [rsp+88h+var_58], xmm0
0x1800072a8  movdqu  xmmword ptr [rsp+88h+var_48], xmm1
0x1800072ae  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x1800072b3  test    al, al
0x1800072b5  jz      short loc_1800072E1
0x1800072b7  mov     rdx, [rsp+88h+var_58]; void *
0x1800072bc  xor     r8d, r8d; unsigned __int64
0x1800072bf  mov     r9, [rsp+88h+var_48]
0x1800072c4  mov     rcx, rbx; this
0x1800072c7  sub     r9, rdx; unsigned __int64
0x1800072ca  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1800072cf  lea     rcx, [rbx+30h]
0x1800072d3  lea     rdx, [rsp+88h+var_48+8]
0x1800072d8  call    ??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x1800072dd  mov     byte ptr [rbx+3Ah], 1
0x1800072e1  mov     rcx, [rsp+88h+var_48+8]; this
0x1800072e6  test    rcx, rcx
0x1800072e9  jz      short loc_180007301
0x1800072eb  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800072f0  jmp     short loc_180007301
0x1800072f2  cmp     byte ptr [rbx+3Ah], 0
0x1800072f6  jz      short loc_180007301
0x1800072f8  lea     rcx, [rbx+18h]; this
0x1800072fc  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007301  mov     [rsp+88h+var_60], r12d; unsigned int
0x180007306  mov     r9, r14; void *
0x180007309  mov     r8, rsi; unsigned __int64
0x18000730c  mov     [rsp+88h+var_68], rbp; unsigned __int64
0x180007311  mov     rdx, r15; void *
0x180007314  mov     rcx, rbx; this
0x180007317  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000731c  add     rsp, 50h
0x180007320  pop     r15
0x180007322  pop     r14
0x180007324  pop     r12
0x180007326  pop     rdi
0x180007327  pop     rsi
0x180007328  pop     rbp
0x180007329  pop     rbx
0x18000732a  retn
```
