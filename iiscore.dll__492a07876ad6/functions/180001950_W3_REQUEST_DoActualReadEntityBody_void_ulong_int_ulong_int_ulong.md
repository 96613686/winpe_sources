# W3_REQUEST::DoActualReadEntityBody(void *,ulong,int,ulong *,int *,ulong)

- ea: `0x180001950`
- end: `0x180001a84`
- name: `?DoActualReadEntityBody@W3_REQUEST@@QEAAJPEAXKHPEAKPEAHK@Z`
- size: `308`
- prototype: `__int64 __usercall@<rax>(W3_REQUEST *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, int@<r9d>, unsigned int *, int *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180001b60`
- `0x1800296b0`

## callees

- `0x180001950`
- `0x180009030`
- `0x1800260f0`
- `0x180029f50`
- `0x18002b5dc`

## import_xrefs

- `w3dt!UlAtqReceiveEntityBody` at `0x1800019eb`
- `w3dt!UlAtqReceiveEntityBody` at `0x1800019eb`

## pseudocode

```c
__int64 __fastcall W3_REQUEST::DoActualReadEntityBody(
        W3_REQUEST *this,
        void *a2,
        unsigned int a3,
        int a4,
        unsigned int *a5,
        int *a6,
        unsigned int a7)
{
  __int64 v7; // r10
  W3_MAIN_CONTEXT *v12; // rsi
  void *v13; // r15
  signed int v14; // ebx
  unsigned int v16; // edx

  v7 = *((_QWORD *)this + 14);
  v12 = *(W3_MAIN_CONTEXT **)(v7 + 392);
  v13 = (void *)*((_QWORD *)v12 + 1180);
  if ( (unsigned int)WWWServerTraceProvider::CheckTracingEnabled((v7 + 8) & -(__int64)(v7 != 0), 0, 4) )
    IISGeneralEvents::GENERAL_READ_ENTITY_START::RaiseEvent(
      (struct IHttpTraceContext *)((*((_QWORD *)this + 14) + 8LL) & -(__int64)(*((_QWORD *)this + 14) != 0)),
      (const struct _GUID *)(*((_QWORD *)this + 14) + 8LL));
  if ( a4 )
  {
    *((_DWORD *)this + 54) = 1;
    *((_QWORD *)this + 1) = *((_QWORD *)v12 + 1178);
    *((_QWORD *)v12 + 1178) = this;
  }
  *((_QWORD *)this + 33) = a2;
  if ( v13 )
  {
    v14 = UlAtqReceiveEntityBody(v13, a4, a7, a2, a3, a5);
    if ( v14 == -2147023899 )
    {
      *a6 = 1;
      return 0;
    }
    *a6 = 0;
    if ( v14 >= 0 )
    {
      v16 = *a5;
      goto LABEL_10;
    }
  }
  else
  {
    v14 = -2147024858;
    *a6 = 0;
  }
  v16 = 0;
LABEL_10:
  W3_REQUEST::UpdateRemainingEntityBytes(this, v16, v14);
  if ( a4 )
  {
    W3_MAIN_CONTEXT::PopAsyncReceiveContext(v12);
    *((_DWORD *)this + 54) = 0;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180001950  push    rbx
0x180001952  push    rbp
0x180001953  push    rsi
0x180001954  push    rdi
0x180001955  push    r12
0x180001957  push    r14
0x180001959  push    r15
0x18000195b  sub     rsp, 30h
0x18000195f  mov     r10, [rcx+70h]
0x180001963  mov     rdi, rcx
0x180001966  mov     rbx, rdx
0x180001969  mov     r12d, r8d
0x18000196c  mov     ebp, r9d
0x18000196f  mov     rsi, [r10+188h]
0x180001976  lea     rax, [r10+8]
0x18000197a  neg     r10
0x18000197d  sbb     rcx, rcx
0x180001980  xor     edx, edx
0x180001982  mov     r15, [rsi+24E0h]
0x180001989  and     rcx, rax
0x18000198c  lea     r8d, [rdx+4]
0x180001990  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180001995  test    eax, eax
0x180001997  jnz     loc_180001A20
0x18000199d  test    ebp, ebp
0x18000199f  jz      short loc_1800019BD
0x1800019a1  mov     dword ptr [rdi+0D8h], 1
0x1800019ab  mov     rax, [rsi+24D0h]
0x1800019b2  mov     [rdi+8], rax
0x1800019b6  mov     [rsi+24D0h], rdi
0x1800019bd  mov     [rdi+108h], rbx
0x1800019c4  test    r15, r15
0x1800019c7  jz      short loc_180001A3B
0x1800019c9  mov     r14, [rsp+68h+arg_20]
0x1800019d1  mov     r9, rbx
0x1800019d4  mov     r8d, [rsp+68h+arg_30]
0x1800019dc  mov     edx, ebp
0x1800019de  mov     [rsp+68h+var_40], r14
0x1800019e3  mov     rcx, r15
0x1800019e6  mov     [rsp+68h+var_48], r12d
0x1800019eb  call    cs:__imp_?UlAtqReceiveEntityBody@@YAJPEAXHK0KPEAK@Z; UlAtqReceiveEntityBody(void *,int,ulong,void *,ulong,ulong *)
0x1800019f2  nop     dword ptr [rax+rax+00h]
0x1800019f7  mov     ebx, eax
0x1800019f9  cmp     eax, 800703E5h
0x1800019fe  mov     rax, [rsp+68h+arg_28]
0x180001a06  jnz     short loc_180001A75
0x180001a08  mov     dword ptr [rax], 1
0x180001a0e  xor     eax, eax
0x180001a10  add     rsp, 30h
0x180001a14  pop     r15
0x180001a16  pop     r14
0x180001a18  pop     r12
0x180001a1a  pop     rdi
0x180001a1b  pop     rsi
0x180001a1c  pop     rbp
0x180001a1d  pop     rbx
0x180001a1e  retn
0x180001a20  mov     rax, [rdi+70h]
0x180001a24  lea     rdx, [rax+8]; struct _GUID *
0x180001a28  neg     rax
0x180001a2b  sbb     rcx, rcx
0x180001a2e  and     rcx, rdx; struct IHttpTraceContext *
0x180001a31  call    ?RaiseEvent@GENERAL_READ_ENTITY_START@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISGeneralEvents::GENERAL_READ_ENTITY_START::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x180001a36  jmp     loc_18000199D
0x180001a3b  mov     rax, [rsp+68h+arg_28]
0x180001a43  mov     ebx, 80070026h
0x180001a48  mov     dword ptr [rax], 0
0x180001a4e  xor     edx, edx; unsigned int
0x180001a50  mov     r8d, ebx; int
0x180001a53  mov     rcx, rdi; this
0x180001a56  call    ?UpdateRemainingEntityBytes@W3_REQUEST@@QEAAXKJ@Z; W3_REQUEST::UpdateRemainingEntityBytes(ulong,long)
0x180001a5b  test    ebp, ebp
0x180001a5d  jz      short loc_180001A71
0x180001a5f  mov     rcx, rsi; this
0x180001a62  call    ?PopAsyncReceiveContext@W3_MAIN_CONTEXT@@QEAAPEAVIISCORE_ASYNC_CONTEXT@@XZ; W3_MAIN_CONTEXT::PopAsyncReceiveContext(void)
0x180001a67  mov     dword ptr [rdi+0D8h], 0
0x180001a71  mov     eax, ebx
0x180001a73  jmp     short loc_180001A10
0x180001a75  mov     dword ptr [rax], 0
0x180001a7b  test    ebx, ebx
0x180001a7d  js      short loc_180001A4E
0x180001a7f  mov     edx, [r14]
0x180001a82  jmp     short loc_180001A50
```
