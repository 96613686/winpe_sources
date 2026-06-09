# W3_TRACE_EVENT_MANAGER::W3_TRACE_EVENT_MANAGER(bool,W3_TRACE_EVENT_MANAGER *)

- ea: `0x180015ae0`
- end: `0x180015c57`
- name: `??0W3_TRACE_EVENT_MANAGER@@QEAA@_NPEAV0@@Z`
- size: `375`
- prototype: `W3_TRACE_EVENT_MANAGER *__fastcall(W3_TRACE_EVENT_MANAGER *__hidden this, bool, struct W3_TRACE_EVENT_MANAGER *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800147d0`

## callees

- `0x180015ae0`
- `0x180032774`

## import_xrefs

- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180015af2`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180015af2`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180015be9`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x180015be9`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180015c26`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180015c26`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180015bab`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180015bab`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180015b84`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180015b84`

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
0x180015ae0  push    rbx
0x180015ae2  push    rbp
0x180015ae3  push    rsi
0x180015ae4  push    rdi
0x180015ae5  sub     rsp, 28h
0x180015ae9  mov     rbx, r8
0x180015aec  movzx   edi, dl
0x180015aef  mov     rsi, rcx
0x180015af2  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180015af9  nop     dword ptr [rax+rax+00h]
0x180015afe  mov     [rsi+2Ch], dil
0x180015b02  xor     eax, eax
0x180015b04  xorps   xmm0, xmm0
0x180015b07  xor     ebp, ebp
0x180015b09  mov     [rsi+28h], ebp
0x180015b0c  mov     [rsi+2Dh], bp
0x180015b10  movups  xmmword ptr [rsi+30h], xmm0
0x180015b14  mov     [rsi+40h], rbp
0x180015b18  movups  xmmword ptr [rsi+48h], xmm0
0x180015b1c  mov     [rsi+58h], rax
0x180015b20  movups  xmmword ptr [rsi+60h], xmm0
0x180015b24  mov     [rsi+70h], al
0x180015b27  movups  xmmword ptr [rsi+78h], xmm0
0x180015b2b  mov     [rsi+88h], rbp
0x180015b32  movups  xmmword ptr [rsi+90h], xmm0
0x180015b39  mov     [rsi+0A0h], rax
0x180015b40  movups  xmmword ptr [rsi+0A8h], xmm0
0x180015b47  mov     [rsi+0B8h], al
0x180015b4d  movups  xmmword ptr [rsi+0C0h], xmm0
0x180015b54  mov     [rsi+0D0h], rax
0x180015b5b  lea     rax, [rsi+8]
0x180015b5f  mov     [rax+8], rax
0x180015b63  mov     [rax], rax
0x180015b66  lea     rax, [rsi+18h]
0x180015b6a  mov     [rax+8], rax
0x180015b6e  mov     [rax], rax
0x180015b71  test    rbx, rbx
0x180015b74  jz      short loc_180015BB7
0x180015b76  mov     [rsp+48h+arg_10], r14
0x180015b7b  cmp     [rbx+2Ch], bpl
0x180015b7f  jz      short loc_180015B90
0x180015b81  mov     rcx, rbx
0x180015b84  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180015b8b  nop     dword ptr [rax+rax+00h]
0x180015b90  mov     r14, [rbx+8]
0x180015b94  lea     rdi, [rbx+8]
0x180015b98  cmp     r14, rdi
0x180015b9b  jnz     short loc_180015BC4
0x180015b9d  cmp     byte ptr [rbx+2Ch], 0
0x180015ba1  mov     r14, [rsp+48h+arg_10]
0x180015ba6  jz      short loc_180015BB7
0x180015ba8  mov     rcx, rbx
0x180015bab  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180015bb2  nop     dword ptr [rax+rax+00h]
0x180015bb7  mov     rax, rsi
0x180015bba  add     rsp, 28h
0x180015bbe  pop     rdi
0x180015bbf  pop     rsi
0x180015bc0  pop     rbp
0x180015bc1  pop     rbx
0x180015bc2  retn
0x180015bc4  mov     [rsp+48h+arg_0], r12
0x180015bc9  mov     [rsp+48h+arg_8], r13
0x180015bce  mov     [rsp+48h+var_28], r15
0x180015bd3  lea     r15, [r14+18h]
0x180015bd7  test    r15, r15
0x180015bda  jz      short loc_180015C43
0x180015bdc  cmp     byte ptr [rsi+2Ch], 0
0x180015be0  mov     r13, [r14+10h]
0x180015be4  jz      short loc_180015BF5
0x180015be6  mov     rcx, rsi
0x180015be9  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180015bf0  nop     dword ptr [rax+rax+00h]
0x180015bf5  mov     r12d, ebp
0x180015bf8  mov     eax, r12d
0x180015bfb  mov     rdx, r13; void *
0x180015bfe  lea     rcx, [rax+rax*2]
0x180015c02  lea     r8, [r15+rcx*8]; struct HTTP_TRACE_CONFIGURATION *
0x180015c06  mov     rcx, rsi; this
0x180015c09  call    ?SetTraceConfigurationWorker@W3_TRACE_EVENT_MANAGER@@QEAAJPEAXPEAUHTTP_TRACE_CONFIGURATION@@@Z; W3_TRACE_EVENT_MANAGER::SetTraceConfigurationWorker(void *,HTTP_TRACE_CONFIGURATION *)
0x180015c0e  mov     ebp, eax
0x180015c10  test    eax, eax
0x180015c12  js      short loc_180015C1D
0x180015c14  inc     r12d
0x180015c17  cmp     r12d, 1
0x180015c1b  jb      short loc_180015BF8
0x180015c1d  cmp     byte ptr [rsi+2Ch], 0
0x180015c21  jz      short loc_180015C32
0x180015c23  mov     rcx, rsi
0x180015c26  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180015c2d  nop     dword ptr [rax+rax+00h]
0x180015c32  test    ebp, ebp
0x180015c34  js      short loc_180015C43
0x180015c36  mov     r14, [r14]
0x180015c39  mov     ebp, 0
0x180015c3e  cmp     r14, rdi
0x180015c41  jnz     short loc_180015BD3
0x180015c43  mov     r13, [rsp+48h+arg_8]
0x180015c48  mov     r12, [rsp+48h+arg_0]
0x180015c4d  mov     r15, [rsp+48h+var_28]
0x180015c52  jmp     loc_180015B9D
```
