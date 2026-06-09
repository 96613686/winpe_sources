# CClfsMarshallingContext::ReleaseFlushElements(_CLS_LSN &)

- ea: `0x1800130a0`
- end: `0x180013171`
- name: `?ReleaseFlushElements@CClfsMarshallingContext@@AEAAXAEAT_CLS_LSN@@@Z`
- size: `209`
- prototype: `void __fastcall(CClfsMarshallingContext *__hidden this, union _CLS_LSN *)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000efa0`
- `0x18000fa24`
- `0x18000fcdc`
- `0x180014328`

## callees

- `0x18000f7f0`
- `0x1800101c8`
- `0x1800130a0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180013125`
- `ntdll!RtlLeaveCriticalSection` at `0x180013153`
- `ntdll!RtlLeaveCriticalSection` at `0x180013125`
- `ntdll!RtlLeaveCriticalSection` at `0x180013153`
- `ntdll!RtlEnterCriticalSection` at `0x1800130c7`
- `ntdll!RtlEnterCriticalSection` at `0x1800130c7`

## pseudocode

```c
void __fastcall CClfsMarshallingContext::ReleaseFlushElements(CClfsMarshallingContext *this, union _CLS_LSN *a2)
{
  CFlushQ *v3; // r14
  struct _RTL_CRITICAL_SECTION *v5; // rdi
  union _CLS_LSN *v6; // rax
  struct CLogIocb *ullOffset; // r15
  union _CLS_LSN v8; // rax
  int v9; // ebp
  unsigned int v10; // eax
  union _CLS_LSN v11; // [rsp+50h] [rbp+8h] BYREF
  struct CLogIocb *v12; // [rsp+60h] [rbp+18h] BYREF

  v3 = (CClfsMarshallingContext *)((char *)this + 232);
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 248);
  while ( 1 )
  {
    RtlEnterCriticalSection(v5);
    if ( !*(_DWORD *)v3 )
      break;
    v6 = (union _CLS_LSN *)*((_QWORD *)v3 + 1);
    ullOffset = (struct CLogIocb *)v6[1].ullOffset;
    v8 = *v6;
    v11 = v8;
    v12 = ullOffset;
    if ( a2 && __PAIR64__(v11.offset.cidContainer, v8.offset.idxRecord) > a2->ullOffset )
    {
      v9 = 4306;
    }
    else
    {
      v10 = CFlushQ::Dequeue(v3, &v11, &v12);
      ullOffset = v12;
      v9 = v10;
    }
    RtlLeaveCriticalSection(v5);
    if ( v9 == 4306 )
      return;
    CClfsMarshallingContext::FreeIocb(this, ullOffset);
    _InterlockedDecrement((volatile signed __int32 *)this + 35);
  }
  RtlLeaveCriticalSection(v5);
}

```

## disassembly

```asm
0x1800130a0  mov     [rsp+arg_8], rbx
0x1800130a5  push    rbp
0x1800130a6  push    rsi
0x1800130a7  push    rdi
0x1800130a8  push    r14
0x1800130aa  push    r15
0x1800130ac  sub     rsp, 20h
0x1800130b0  mov     rsi, rdx
0x1800130b3  lea     r14, [rcx+0E8h]
0x1800130ba  mov     rbx, rcx
0x1800130bd  lea     rdi, [rcx+0F8h]
0x1800130c4  mov     rcx, rdi; CriticalSection
0x1800130c7  call    cs:__imp_RtlEnterCriticalSection
0x1800130ce  nop     dword ptr [rax+rax+00h]
0x1800130d3  cmp     dword ptr [r14], 0
0x1800130d7  jz      short loc_180013150
0x1800130d9  mov     rax, [r14+8]
0x1800130dd  mov     r15, [rax+8]
0x1800130e1  mov     rax, [rax]
0x1800130e4  mov     qword ptr [rsp+48h+arg_0], rax
0x1800130e9  mov     [rsp+48h+arg_10], r15
0x1800130ee  test    rsi, rsi
0x1800130f1  jz      short loc_180013109
0x1800130f3  mov     ecx, dword ptr [rsp+48h+arg_0+4]
0x1800130f7  cmp     ecx, [rsi+4]
0x1800130fa  jb      short loc_180013109
0x1800130fc  jnz     short loc_180013102
0x1800130fe  cmp     eax, [rsi]
0x180013100  jbe     short loc_180013109
0x180013102  mov     ebp, 10D2h
0x180013107  jmp     short loc_180013122
0x180013109  lea     r8, [rsp+48h+arg_10]; struct CLogIocb **
0x18001310e  mov     rcx, r14; this
0x180013111  lea     rdx, [rsp+48h+arg_0]; union _CLS_LSN *
0x180013116  call    ?Dequeue@CFlushQ@@QEAAKAEAT_CLS_LSN@@AEAPEAVCLogIocb@@@Z; CFlushQ::Dequeue(_CLS_LSN &,CLogIocb * &)
0x18001311b  mov     r15, [rsp+48h+arg_10]
0x180013120  mov     ebp, eax
0x180013122  mov     rcx, rdi; CriticalSection
0x180013125  call    cs:__imp_RtlLeaveCriticalSection
0x18001312c  nop     dword ptr [rax+rax+00h]
0x180013131  cmp     ebp, 10D2h
0x180013137  jz      short loc_18001315F
0x180013139  mov     rdx, r15; struct CLogIocb *
0x18001313c  mov     rcx, rbx; this
0x18001313f  call    ?FreeIocb@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z; CClfsMarshallingContext::FreeIocb(CLogIocb *)
0x180013144  lock dec dword ptr [rbx+8Ch]
0x18001314b  jmp     loc_1800130C4
0x180013150  mov     rcx, rdi; CriticalSection
0x180013153  call    cs:__imp_RtlLeaveCriticalSection
0x18001315a  nop     dword ptr [rax+rax+00h]
0x18001315f  mov     rbx, [rsp+48h+arg_8]
0x180013164  add     rsp, 20h
0x180013168  pop     r15
0x18001316a  pop     r14
0x18001316c  pop     rdi
0x18001316d  pop     rsi
0x18001316e  pop     rbp
0x18001316f  retn
```
