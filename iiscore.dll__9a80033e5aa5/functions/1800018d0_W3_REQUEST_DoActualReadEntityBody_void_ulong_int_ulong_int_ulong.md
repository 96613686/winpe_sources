# W3_REQUEST::DoActualReadEntityBody(void *,ulong,int,ulong *,int *,ulong)

- ea: `0x1800018d0`
- end: `0x1800019f9`
- name: `?DoActualReadEntityBody@W3_REQUEST@@QEAAJPEAXKHPEAKPEAHK@Z`
- size: `297`
- prototype: `__int64 __fastcall(W3_REQUEST *this, void *, unsigned int, int, unsigned int *, int *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180001acc`
- `0x1800274f0`

## callees

- `0x1800018d0`
- `0x180008930`
- `0x18002424c`
- `0x180027d64`
- `0x180029184`

## import_xrefs

- `w3dt!UlAtqReceiveEntityBody` at `0x180001967`
- `w3dt!UlAtqReceiveEntityBody` at `0x180001967`

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
  int v14; // ebx
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
0x1800018d0  push    rbx
0x1800018d2  push    rbp
0x1800018d3  push    rsi
0x1800018d4  push    rdi
0x1800018d5  push    r12
0x1800018d7  push    r14
0x1800018d9  push    r15
0x1800018db  sub     rsp, 30h
0x1800018df  mov     r10, [rcx+70h]
0x1800018e3  mov     rdi, rcx
0x1800018e6  mov     rbx, rdx
0x1800018e9  mov     r12d, r8d
0x1800018ec  mov     ebp, r9d
0x1800018ef  mov     rsi, [r10+188h]
0x1800018f6  lea     rax, [r10+8]
0x1800018fa  neg     r10
0x1800018fd  sbb     rcx, rcx
0x180001900  xor     edx, edx
0x180001902  mov     r15, [rsi+24E0h]
0x180001909  and     rcx, rax
0x18000190c  lea     r8d, [rdx+4]
0x180001910  call    ?CheckTracingEnabled@WWWServerTraceProvider@@SAHPEAVIHttpTraceContext@@W4enumAreaFlags@1@K@Z; WWWServerTraceProvider::CheckTracingEnabled(IHttpTraceContext *,WWWServerTraceProvider::enumAreaFlags,ulong)
0x180001915  test    eax, eax
0x180001917  jnz     short loc_180001995
0x180001919  test    ebp, ebp
0x18000191b  jz      short loc_180001939
0x18000191d  mov     dword ptr [rdi+0D8h], 1
0x180001927  mov     rax, [rsi+24D0h]
0x18000192e  mov     [rdi+8], rax
0x180001932  mov     [rsi+24D0h], rdi
0x180001939  mov     [rdi+108h], rbx
0x180001940  test    r15, r15
0x180001943  jz      short loc_1800019B0
0x180001945  mov     r14, [rsp+68h+arg_20]
0x18000194d  mov     r9, rbx
0x180001950  mov     r8d, [rsp+68h+arg_30]
0x180001958  mov     edx, ebp
0x18000195a  mov     [rsp+68h+var_40], r14
0x18000195f  mov     rcx, r15
0x180001962  mov     [rsp+68h+var_48], r12d
0x180001967  call    cs:__imp_?UlAtqReceiveEntityBody@@YAJPEAXHK0KPEAK@Z; UlAtqReceiveEntityBody(void *,int,ulong,void *,ulong,ulong *)
0x18000196d  mov     ebx, eax
0x18000196f  cmp     eax, 800703E5h
0x180001974  mov     rax, [rsp+68h+arg_28]
0x18000197c  jnz     short loc_1800019EA
0x18000197e  mov     dword ptr [rax], 1
0x180001984  xor     eax, eax
0x180001986  add     rsp, 30h
0x18000198a  pop     r15
0x18000198c  pop     r14
0x18000198e  pop     r12
0x180001990  pop     rdi
0x180001991  pop     rsi
0x180001992  pop     rbp
0x180001993  pop     rbx
0x180001994  retn
0x180001995  mov     rax, [rdi+70h]
0x180001999  lea     rdx, [rax+8]; struct _GUID *
0x18000199d  neg     rax
0x1800019a0  sbb     rcx, rcx
0x1800019a3  and     rcx, rdx; struct IHttpTraceContext *
0x1800019a6  call    ?RaiseEvent@GENERAL_READ_ENTITY_START@IISGeneralEvents@@SAJPEAVIHttpTraceContext@@PEBU_GUID@@@Z; IISGeneralEvents::GENERAL_READ_ENTITY_START::RaiseEvent(IHttpTraceContext *,_GUID const *)
0x1800019ab  jmp     loc_180001919
0x1800019b0  mov     rax, [rsp+68h+arg_28]
0x1800019b8  mov     ebx, 80070026h
0x1800019bd  mov     dword ptr [rax], 0
0x1800019c3  xor     edx, edx; unsigned int
0x1800019c5  mov     r8d, ebx; int
0x1800019c8  mov     rcx, rdi; this
0x1800019cb  call    ?UpdateRemainingEntityBytes@W3_REQUEST@@QEAAXKJ@Z; W3_REQUEST::UpdateRemainingEntityBytes(ulong,long)
0x1800019d0  test    ebp, ebp
0x1800019d2  jz      short loc_1800019E6
0x1800019d4  mov     rcx, rsi; this
0x1800019d7  call    ?PopAsyncReceiveContext@W3_MAIN_CONTEXT@@QEAAPEAVIISCORE_ASYNC_CONTEXT@@XZ; W3_MAIN_CONTEXT::PopAsyncReceiveContext(void)
0x1800019dc  mov     dword ptr [rdi+0D8h], 0
0x1800019e6  mov     eax, ebx
0x1800019e8  jmp     short loc_180001986
0x1800019ea  mov     dword ptr [rax], 0
0x1800019f0  test    ebx, ebx
0x1800019f2  js      short loc_1800019C3
0x1800019f4  mov     edx, [r14]
0x1800019f7  jmp     short loc_1800019C5
```
