# CPersistSession::SetProperties(ulong,tagDBPROPSET * const)

- ea: `0x1800230a0`
- end: `0x1800231c1`
- name: `?SetProperties@CPersistSession@@UEAAJKQEAUtagDBPROPSET@@@Z`
- size: `289`
- prototype: `int(CPersistSession *__hidden this, unsigned int, struct tagDBPROPSET *const)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180016584`
- `0x1800230a0`
- `0x18002d9a4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800230e5`
- `KERNEL32!GetCurrentThreadId` at `0x1800230e5`
- `KERNEL32!LeaveCriticalSection` at `0x18002319c`
- `KERNEL32!LeaveCriticalSection` at `0x18002319c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002310b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002310b`
- `MSDART!UMSEnterCSWraper` at `0x1800230cb`
- `MSDART!UMSEnterCSWraper` at `0x1800230cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistSession::SetProperties(
        CPersistSession *this,
        unsigned int a2,
        struct tagDBPROPSET *const a3)
{
  CPersistSession *v5; // rbx
  _QWORD *v6; // rsi
  _DWORD *v7; // rdi
  _DWORD *v8; // r14
  unsigned int v9; // edx
  int v10; // eax
  unsigned int v11; // r15d
  __int64 v13; // rcx
  int v15; // [rsp+30h] [rbp-58h] BYREF
  char *v16; // [rsp+38h] [rbp-50h]
  _DWORD *v17; // [rsp+40h] [rbp-48h]
  _DWORD *v18; // [rsp+48h] [rbp-40h]
  _QWORD *v19; // [rsp+50h] [rbp-38h]
  int v23; // [rsp+A8h] [rbp+20h]
  int v24; // [rsp+A8h] [rbp+20h]

  v5 = this;
  v6 = (_QWORD *)((char *)this + 32);
  v16 = (char *)this + 32;
  UMSEnterCSWraper((char *)this + 32);
  v7 = (_DWORD *)((char *)v5 + 44);
  v17 = (_DWORD *)((char *)v5 + 44);
  if ( !*((_DWORD *)v5 + 11) )
    *((_DWORD *)v5 + 10) = GetCurrentThreadId();
  ++*v7;
  v8 = (_DWORD *)((char *)v5 + 48);
  v18 = (_DWORD *)((char *)v5 + 48);
  ++*((_DWORD *)v5 + 12);
  v19 = v6;
  SetErrorInfo(0, 0);
  try
  {
    *((GUID *)v5 + 5) = IID_ISessionProperties;
    *((_DWORD *)v5 + 1049) = 0;
    v10 = CUtlProps::utlSetProperties(
            (CPersistSession *)((char *)v5 + 4536),
            v9,
            a2,
            a3,
            (CPersistSession *)((char *)v5 + 4520),
            0);
  }
  catch ( long v15 )
  {
    v23 = v15;
    v8 = v18;
    v7 = v17;
    v6 = v16;
    v10 = v23;
    v5 = this;
  }
  catch ( ... )
  {
    v24 = -2147467259;
    v8 = v18;
    v7 = v17;
    v6 = v16;
    v10 = v24;
    v5 = this;
  }
  v11 = Exit(v10, 0xBB8u);
  --*v8;
  if ( (*v7)-- == 1 )
    *((_DWORD *)v5 + 10) = -1;
  v13 = *v6;
  --*(_DWORD *)(v13 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
  return v11;
}

```

## disassembly

```asm
0x1800230a0  mov     [rsp+arg_8], rbx
0x1800230a5  mov     [rsp+arg_0], rcx
0x1800230aa  push    rsi
0x1800230ab  push    rdi
0x1800230ac  push    r12
0x1800230ae  push    r14
0x1800230b0  push    r15
0x1800230b2  sub     rsp, 60h
0x1800230b6  mov     r15, r8
0x1800230b9  mov     r12d, edx
0x1800230bc  mov     rbx, rcx
0x1800230bf  lea     rsi, [rcx+20h]
0x1800230c3  mov     [rsp+88h+var_50], rsi
0x1800230c8  mov     rcx, rsi
0x1800230cb  call    cs:__imp_UMSEnterCSWraper
0x1800230d2  nop     dword ptr [rax+rax+00h]
0x1800230d7  lea     rdi, [rbx+2Ch]
0x1800230db  mov     [rsp+88h+var_48], rdi
0x1800230e0  cmp     dword ptr [rdi], 0
0x1800230e3  jnz     short loc_1800230F4
0x1800230e5  call    cs:__imp_GetCurrentThreadId
0x1800230ec  nop     dword ptr [rax+rax+00h]
0x1800230f1  mov     [rbx+28h], eax
0x1800230f4  inc     dword ptr [rdi]
0x1800230f6  lea     r14, [rbx+30h]
0x1800230fa  mov     [rsp+88h+var_40], r14
0x1800230ff  inc     dword ptr [r14]
0x180023102  mov     [rsp+88h+var_38], rsi
0x180023107  xor     edx, edx; perrinfo
0x180023109  xor     ecx, ecx; dwReserved
0x18002310b  call    cs:__imp_SetErrorInfo
0x180023112  nop     dword ptr [rax+rax+00h]
0x180023117  movups  xmm0, xmmword ptr cs:IID_ISessionProperties.Data1
0x18002311e  movdqu  xmmword ptr [rbx+50h], xmm0
0x180023123  mov     dword ptr [rbx+1064h], 0
0x18002312d  lea     rax, [rbx+11A8h]
0x180023134  lea     rcx, [rbx+11B8h]; this
0x18002313b  mov     [rsp+88h+var_60], 0; int
0x180023143  mov     [rsp+88h+var_68], rax; struct CBidGenericBase *
0x180023148  mov     r9, r15; struct tagDBPROPSET *
0x18002314b  mov     r8d, r12d; unsigned int
0x18002314e  call    ?utlSetProperties@CUtlProps@@QEAAJKKQEBUtagDBPROPSET@@AEBVCBidGenericBase@@H@Z; CUtlProps::utlSetProperties(ulong,ulong,tagDBPROPSET const * const,CBidGenericBase const &,int)
0x180023153  nop
0x180023154  jmp     short loc_180023176
0x180023156  jmp     short $+2
0x180023158  mov     r14, [rsp+88h+var_40]
0x18002315d  mov     rdi, [rsp+88h+var_48]
0x180023162  mov     rsi, [rsp+88h+var_50]
0x180023167  mov     eax, [rsp+88h+arg_18]
0x18002316e  mov     rbx, [rsp+88h+arg_0]
0x180023176  mov     edx, 0BB8h; unsigned int
0x18002317b  mov     ecx, eax; int
0x18002317d  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180023182  mov     r15d, eax
0x180023185  or      eax, 0FFFFFFFFh
0x180023188  add     [r14], eax
0x18002318b  add     [rdi], eax
0x18002318d  jnz     short loc_180023192
0x18002318f  mov     [rbx+28h], eax
0x180023192  mov     rcx, [rsi]
0x180023195  dec     dword ptr [rcx+30h]
0x180023198  add     rcx, 8; lpCriticalSection
0x18002319c  call    cs:__imp_LeaveCriticalSection
0x1800231a3  nop     dword ptr [rax+rax+00h]
0x1800231a8  mov     eax, r15d
0x1800231ab  mov     rbx, [rsp+88h+arg_8]
0x1800231b3  add     rsp, 60h
0x1800231b7  pop     r15
0x1800231b9  pop     r14
0x1800231bb  pop     r12
0x1800231bd  pop     rdi
0x1800231be  pop     rsi
0x1800231bf  retn
```
