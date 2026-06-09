# KsecIoctlHandleFunctionReturn

- ea: `0x180005e94`
- end: `0x180006040`
- name: `KsecIoctlHandleFunctionReturn`
- size: `428`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800053e0`
- `0x180026fb8`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180005e94`
- `0x180007a64`
- `0x180007ba8`
- `0x18000fdc4`
- `0x18000fe34`
- `0x1800263a0`
- `0x1800267a0`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x180005f2a`
- `ntoskrnl!ProbeForRead` at `0x180005f2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x180006013`
- `ntoskrnl!ExFreePoolWithTag` at `0x180006013`
- `ntoskrnl!ExAllocatePool2` at `0x180005f44`
- `ntoskrnl!ExAllocatePool2` at `0x180005f44`

## pseudocode

```c
__int64 __fastcall KsecIoctlHandleFunctionReturn(void *Src, size_t Size)
{
  SIZE_T v2; // rsi
  void *Pool2; // rax
  void *v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // [rsp+70h] [rbp+18h] BYREF

  v2 = (unsigned int)Size;
  if ( (unsigned int)Size < 0x10 )
    return 3221225507LL;
  if ( !Src )
    return 3221225485LL;
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v8);
  if ( v8 )
    _InterlockedDecrement64((volatile signed __int64 *)(KsecGetCurrentAsyncPerfCounterSet(v8) + 16));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 17, &WPP_f9740104427135617d8c60794f45a901_Traceguids);
  ProbeForRead(Src, v2, 1u);
  Pool2 = (void *)ExAllocatePool2(256, v2, 1399157579);
  v6 = Pool2;
  if ( Pool2 )
  {
    RtlCopyFromUser(Pool2, Src, v2);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 20, &WPP_f9740104427135617d8c60794f45a901_Traceguids);
    v7 = CallInProgressCompleted((__int64)v6, (__int64)v6, v2);
    if ( v6 )
      ExFreePoolWithTag(v6, 0x5365734Bu);
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v8);
    return v7;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 3));
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v8);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x180005e94  mov     [rsp+arg_8], rbx
0x180005e99  mov     [rsp+arg_18], rsi
0x180005e9e  mov     [rsp+arg_0], rcx
0x180005ea3  push    rdi
0x180005ea4  push    r14
0x180005ea6  push    r15
0x180005ea8  sub     rsp, 40h
0x180005eac  mov     esi, edx
0x180005eae  mov     rdi, rcx
0x180005eb1  cmp     edx, 10h
0x180005eb4  jnb     short loc_180005EC0
0x180005eb6  mov     eax, 0C0000023h
0x180005ebb  jmp     loc_18000602B
0x180005ec0  test    rdi, rdi
0x180005ec3  jnz     short loc_180005ECF
0x180005ec5  mov     eax, 0C000000Dh
0x180005eca  jmp     loc_18000602B
0x180005ecf  lea     rcx, [rsp+58h+arg_10]; this
0x180005ed4  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180005ed9  mov     rcx, [rsp+58h+arg_10]
0x180005ede  test    rcx, rcx
0x180005ee1  jz      short loc_180005EED
0x180005ee3  call    KsecGetCurrentAsyncPerfCounterSet
0x180005ee8  lock dec qword ptr [rax+10h]
0x180005eed  mov     [rsp+58h+var_28], 0
0x180005ef6  lea     r15, WPP_GLOBAL_Control
0x180005efd  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f04  cmp     rcx, r15
0x180005f07  jz      short loc_180005F1E
0x180005f09  mov     edx, 11h
0x180005f0e  lea     r8, WPP_f9740104427135617d8c60794f45a901_Traceguids
0x180005f15  mov     rcx, [rcx+18h]
0x180005f19  call    WPP_SF_
0x180005f1e  mov     r8d, 1; Alignment
0x180005f24  mov     rdx, rsi; Length
0x180005f27  mov     rcx, rdi; Address
0x180005f2a  call    cs:__imp_ProbeForRead
0x180005f31  nop     dword ptr [rax+rax+00h]
0x180005f36  mov     r8d, 5365734Bh
0x180005f3c  mov     rdx, rsi
0x180005f3f  mov     ecx, 100h
0x180005f44  call    cs:__imp_ExAllocatePool2
0x180005f4b  nop     dword ptr [rax+rax+00h]
0x180005f50  mov     rbx, rax
0x180005f53  mov     [rsp+58h+var_28], rax
0x180005f58  test    rax, rax
0x180005f5b  jnz     short loc_180005F8D
0x180005f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f64  cmp     rcx, r15
0x180005f67  jz      short loc_180005F79
0x180005f69  mov     eax, [rcx+2Ch]
0x180005f6c  test    al, 1
0x180005f6e  jz      short loc_180005F79
0x180005f70  mov     rcx, [rcx+18h]
0x180005f74  call    WPP_SF_s
0x180005f79  lea     rcx, [rsp+58h+arg_10]; this
0x180005f7e  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180005f83  mov     eax, 0C000009Ah
0x180005f88  jmp     loc_18000602B
0x180005f8d  mov     r8, rsi; Size
0x180005f90  mov     rdx, rdi; Src
0x180005f93  mov     rcx, rbx; void *
0x180005f96  call    RtlCopyFromUser
0x180005f9b  nop
0x180005f9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fa3  cmp     rcx, r15
0x180005fa6  jz      short loc_180005FBD
0x180005fa8  mov     edx, 14h
0x180005fad  lea     r8, WPP_f9740104427135617d8c60794f45a901_Traceguids
0x180005fb4  mov     rcx, [rcx+18h]
0x180005fb8  call    WPP_SF_
0x180005fbd  mov     r8d, esi
0x180005fc0  mov     rdx, rbx
0x180005fc3  mov     rcx, rbx
0x180005fc6  call    CallInProgressCompleted
0x180005fcb  mov     edi, eax
0x180005fcd  jmp     short loc_180006006
0x180005fcf  mov     edi, eax
0x180005fd1  lea     rax, WPP_GLOBAL_Control
0x180005fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fdf  cmp     rcx, rax
0x180005fe2  jz      short loc_180006001
0x180005fe4  mov     eax, [rcx+2Ch]
0x180005fe7  test    al, 1
0x180005fe9  jz      short loc_180006001
0x180005feb  mov     rax, [rsp+58h+arg_0]
0x180005ff0  mov     [rsp+58h+var_38], rax
0x180005ff5  mov     r9d, edi
0x180005ff8  mov     rcx, [rcx+18h]
0x180005ffc  call    WPP_SF_dqs
0x180006001  mov     rbx, [rsp+58h+var_28]
0x180006006  test    rbx, rbx
0x180006009  jz      short loc_18000601F
0x18000600b  mov     edx, 5365734Bh; Tag
0x180006010  mov     rcx, rbx; P
0x180006013  call    cs:__imp_ExFreePoolWithTag
0x18000601a  nop     dword ptr [rax+rax+00h]
0x18000601f  lea     rcx, [rsp+58h+arg_10]; this
0x180006024  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180006029  mov     eax, edi
0x18000602b  mov     rbx, [rsp+58h+arg_8]
0x180006030  mov     rsi, [rsp+58h+arg_18]
0x180006035  add     rsp, 40h
0x180006039  pop     r15
0x18000603b  pop     r14
0x18000603d  pop     rdi
0x18000603e  retn
```
