# W3_TRACE_EVENT_MANAGER::W3_TRACE_EVENT_MANAGER(bool,W3_TRACE_EVENT_MANAGER *)

- ea: `0x1800149d0`
- end: `0x180014b28`
- name: `??0W3_TRACE_EVENT_MANAGER@@QEAA@_NPEAV0@@Z`
- size: `344`
- prototype: `W3_TRACE_EVENT_MANAGER *__fastcall(W3_TRACE_EVENT_MANAGER *__hidden this, bool, struct W3_TRACE_EVENT_MANAGER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180013690`

## callees

- `0x1800149d0`
- `0x18002fb14`

## import_xrefs

- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x1800149e2`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x1800149e2`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180014ac6`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180014ac6`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180014afd`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180014afd`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180014a8f`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180014a8f`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180014a6e`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180014a6e`

## pseudocode

```c
W3_TRACE_EVENT_MANAGER *__fastcall W3_TRACE_EVENT_MANAGER::W3_TRACE_EVENT_MANAGER(
        W3_TRACE_EVENT_MANAGER *this,
        char a2,
        struct W3_TRACE_EVENT_MANAGER *a3)
{
  _QWORD *i; // r14
  void *v8; // r13
  unsigned int v9; // r12d
  int v10; // ebp

  CReaderWriterLock3::CReaderWriterLock3(this);
  *((_BYTE *)this + 44) = a2;
  *((_DWORD *)this + 10) = 0;
  *(_WORD *)((char *)this + 45) = 0;
  *((_OWORD *)this + 3) = 0;
  *((_QWORD *)this + 8) = 0;
  *(_OWORD *)((char *)this + 72) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_OWORD *)this + 6) = 0;
  *((_BYTE *)this + 112) = 0;
  *(_OWORD *)((char *)this + 120) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_OWORD *)this + 9) = 0;
  *((_QWORD *)this + 20) = 0;
  *(_OWORD *)((char *)this + 168) = 0;
  *((_BYTE *)this + 184) = 0;
  *((_OWORD *)this + 12) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 2) = (char *)this + 8;
  *((_QWORD *)this + 1) = (char *)this + 8;
  *((_QWORD *)this + 4) = (char *)this + 24;
  *((_QWORD *)this + 3) = (char *)this + 24;
  if ( a3 )
  {
    if ( *((_BYTE *)a3 + 44) )
      CReaderWriterLock3::ReadLock(a3);
    for ( i = (_QWORD *)*((_QWORD *)a3 + 1); i != (_QWORD *)((char *)a3 + 8); i = (_QWORD *)*i )
    {
      if ( i == (_QWORD *)-24LL )
        break;
      v8 = (void *)i[2];
      if ( *((_BYTE *)this + 44) )
        CReaderWriterLock3::WriteLock(this);
      v9 = 0;
      do
      {
        v10 = W3_TRACE_EVENT_MANAGER::SetTraceConfigurationWorker(
                this,
                v8,
                (struct HTTP_TRACE_CONFIGURATION *)&i[3 * v9 + 3]);
        if ( v10 < 0 )
          break;
        ++v9;
      }
      while ( !v9 );
      if ( *((_BYTE *)this + 44) )
        CReaderWriterLock3::WriteUnlock(this);
      if ( v10 < 0 )
        break;
    }
    if ( *((_BYTE *)a3 + 44) )
      CReaderWriterLock3::ReadUnlock(a3);
  }
  return this;
}

```

## disassembly

```asm
0x1800149d0  push    rbx
0x1800149d2  push    rbp
0x1800149d3  push    rsi
0x1800149d4  push    rdi
0x1800149d5  sub     rsp, 28h
0x1800149d9  mov     rbx, r8
0x1800149dc  movzx   edi, dl
0x1800149df  mov     rsi, rcx
0x1800149e2  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x1800149e8  mov     [rsi+2Ch], dil
0x1800149ec  xor     eax, eax
0x1800149ee  xorps   xmm0, xmm0
0x1800149f1  xor     ebp, ebp
0x1800149f3  mov     [rsi+28h], ebp
0x1800149f6  mov     [rsi+2Dh], bp
0x1800149fa  movups  xmmword ptr [rsi+30h], xmm0
0x1800149fe  mov     [rsi+40h], rbp
0x180014a02  movups  xmmword ptr [rsi+48h], xmm0
0x180014a06  mov     [rsi+58h], rax
0x180014a0a  movups  xmmword ptr [rsi+60h], xmm0
0x180014a0e  mov     [rsi+70h], al
0x180014a11  movups  xmmword ptr [rsi+78h], xmm0
0x180014a15  mov     [rsi+88h], rbp
0x180014a1c  movups  xmmword ptr [rsi+90h], xmm0
0x180014a23  mov     [rsi+0A0h], rax
0x180014a2a  movups  xmmword ptr [rsi+0A8h], xmm0
0x180014a31  mov     [rsi+0B8h], al
0x180014a37  movups  xmmword ptr [rsi+0C0h], xmm0
0x180014a3e  mov     [rsi+0D0h], rax
0x180014a45  lea     rax, [rsi+8]
0x180014a49  mov     [rax+8], rax
0x180014a4d  mov     [rax], rax
0x180014a50  lea     rax, [rsi+18h]
0x180014a54  mov     [rax+8], rax
0x180014a58  mov     [rax], rax
0x180014a5b  test    rbx, rbx
0x180014a5e  jz      short loc_180014A95
0x180014a60  mov     [rsp+48h+arg_10], r14
0x180014a65  cmp     [rbx+2Ch], bpl
0x180014a69  jz      short loc_180014A74
0x180014a6b  mov     rcx, rbx
0x180014a6e  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180014a74  mov     r14, [rbx+8]
0x180014a78  lea     rdi, [rbx+8]
0x180014a7c  cmp     r14, rdi
0x180014a7f  jnz     short loc_180014AA1
0x180014a81  cmp     byte ptr [rbx+2Ch], 0
0x180014a85  mov     r14, [rsp+48h+arg_10]
0x180014a8a  jz      short loc_180014A95
0x180014a8c  mov     rcx, rbx
0x180014a8f  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180014a95  mov     rax, rsi
0x180014a98  add     rsp, 28h
0x180014a9c  pop     rdi
0x180014a9d  pop     rsi
0x180014a9e  pop     rbp
0x180014a9f  pop     rbx
0x180014aa0  retn
0x180014aa1  mov     [rsp+48h+arg_0], r12
0x180014aa6  mov     [rsp+48h+arg_8], r13
0x180014aab  mov     [rsp+48h+var_28], r15
0x180014ab0  lea     r15, [r14+18h]
0x180014ab4  test    r15, r15
0x180014ab7  jz      short loc_180014B14
0x180014ab9  cmp     byte ptr [rsi+2Ch], 0
0x180014abd  mov     r13, [r14+10h]
0x180014ac1  jz      short loc_180014ACC
0x180014ac3  mov     rcx, rsi
0x180014ac6  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180014acc  mov     r12d, ebp
0x180014acf  mov     eax, r12d
0x180014ad2  mov     rdx, r13; void *
0x180014ad5  lea     rcx, [rax+rax*2]
0x180014ad9  lea     r8, [r15+rcx*8]; struct HTTP_TRACE_CONFIGURATION *
0x180014add  mov     rcx, rsi; this
0x180014ae0  call    ?SetTraceConfigurationWorker@W3_TRACE_EVENT_MANAGER@@QEAAJPEAXPEAUHTTP_TRACE_CONFIGURATION@@@Z; W3_TRACE_EVENT_MANAGER::SetTraceConfigurationWorker(void *,HTTP_TRACE_CONFIGURATION *)
0x180014ae5  mov     ebp, eax
0x180014ae7  test    eax, eax
0x180014ae9  js      short loc_180014AF4
0x180014aeb  inc     r12d
0x180014aee  cmp     r12d, 1
0x180014af2  jb      short loc_180014ACF
0x180014af4  cmp     byte ptr [rsi+2Ch], 0
0x180014af8  jz      short loc_180014B03
0x180014afa  mov     rcx, rsi
0x180014afd  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180014b03  test    ebp, ebp
0x180014b05  js      short loc_180014B14
0x180014b07  mov     r14, [r14]
0x180014b0a  mov     ebp, 0
0x180014b0f  cmp     r14, rdi
0x180014b12  jnz     short loc_180014AB0
0x180014b14  mov     r13, [rsp+48h+arg_8]
0x180014b19  mov     r12, [rsp+48h+arg_0]
0x180014b1e  mov     r15, [rsp+48h+var_28]
0x180014b23  jmp     loc_180014A81
```
