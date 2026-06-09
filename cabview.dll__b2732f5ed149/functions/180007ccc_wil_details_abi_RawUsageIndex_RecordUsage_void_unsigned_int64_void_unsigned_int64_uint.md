# wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180007ccc`
- end: `0x180007dd3`
- name: `?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z`
- size: `263`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x1800042f0`
- `0x180007ba0`
- `0x180007bf4`

## callees

- `0x180002620`
- `0x1800042b8`
- `0x180005abc`
- `0x180007ccc`
- `0x180007ddc`
- `0x1800086d0`
- `0x180009e5c`

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
0x180007ccc  push    rbx
0x180007cce  push    rbp
0x180007ccf  push    rsi
0x180007cd0  push    rdi
0x180007cd1  push    r12
0x180007cd3  push    r14
0x180007cd5  push    r15
0x180007cd7  sub     rsp, 60h
0x180007cdb  mov     rax, cs:__security_cookie
0x180007ce2  xor     rax, rsp
0x180007ce5  mov     [rsp+98h+var_48], rax
0x180007cea  mov     r12d, [rsp+98h+arg_28]
0x180007cf2  mov     r15, r9
0x180007cf5  mov     rbp, [rsp+98h+arg_20]
0x180007cfd  mov     rsi, r8
0x180007d00  mov     [rsp+98h+var_70], r12d; unsigned int
0x180007d05  mov     r14, rdx
0x180007d08  mov     [rsp+98h+var_78], rbp; unsigned __int64
0x180007d0d  mov     rbx, rcx
0x180007d10  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180007d15  test    al, al
0x180007d17  jz      short loc_180007D20
0x180007d19  mov     al, 1
0x180007d1b  jmp     loc_180007DB7
0x180007d20  lea     rdx, [rbp+20h]
0x180007d24  add     rdx, rsi; unsigned __int64
0x180007d27  cmp     qword ptr [rbx+18h], 0
0x180007d2c  jnz     short loc_180007D8D
0x180007d2e  xorps   xmm0, xmm0
0x180007d31  lea     rcx, [rsp+98h+var_68]; this
0x180007d36  xorps   xmm1, xmm1
0x180007d39  add     rdx, 0Ah; unsigned __int64
0x180007d3d  movdqu  xmmword ptr [rsp+98h+var_68], xmm0
0x180007d43  movdqu  xmmword ptr [rsp+98h+var_58], xmm1
0x180007d49  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007d4e  test    al, al
0x180007d50  jz      short loc_180007D7C
0x180007d52  mov     rdx, [rsp+98h+var_68]; void *
0x180007d57  xor     r8d, r8d; unsigned __int64
0x180007d5a  mov     r9, [rsp+98h+var_58]
0x180007d5f  mov     rcx, rbx; this
0x180007d62  sub     r9, rdx; unsigned __int64
0x180007d65  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180007d6a  lea     rcx, [rbx+30h]
0x180007d6e  lea     rdx, [rsp+98h+var_58+8]
0x180007d73  call    ??4?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::operator=(wistd::unique_ptr<void,wil::process_heap_deleter> &&)
0x180007d78  mov     byte ptr [rbx+3Ah], 1
0x180007d7c  mov     rcx, [rsp+98h+var_58+8]; this
0x180007d81  test    rcx, rcx
0x180007d84  jz      short loc_180007D9C
0x180007d86  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180007d8b  jmp     short loc_180007D9C
0x180007d8d  cmp     byte ptr [rbx+3Ah], 0
0x180007d91  jz      short loc_180007D9C
0x180007d93  lea     rcx, [rbx+18h]; this
0x180007d97  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x180007d9c  mov     [rsp+98h+var_70], r12d; unsigned int
0x180007da1  mov     r9, r15; void *
0x180007da4  mov     r8, rsi; unsigned __int64
0x180007da7  mov     [rsp+98h+var_78], rbp; unsigned __int64
0x180007dac  mov     rdx, r14; void *
0x180007daf  mov     rcx, rbx; this
0x180007db2  call    ?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180007db7  mov     rcx, [rsp+98h+var_48]
0x180007dbc  xor     rcx, rsp; StackCookie
0x180007dbf  call    __security_check_cookie
0x180007dc4  add     rsp, 60h
0x180007dc8  pop     r15
0x180007dca  pop     r14
0x180007dcc  pop     r12
0x180007dce  pop     rdi
0x180007dcf  pop     rsi
0x180007dd0  pop     rbp
0x180007dd1  pop     rbx
0x180007dd2  retn
```
