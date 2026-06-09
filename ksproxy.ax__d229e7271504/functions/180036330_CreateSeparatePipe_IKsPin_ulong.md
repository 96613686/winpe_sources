# CreateSeparatePipe(IKsPin *,ulong)

- ea: `0x180036330`
- end: `0x1800364fb`
- name: `?CreateSeparatePipe@@YAJPEAUIKsPin@@K@Z`
- size: `459`
- prototype: `__int64 __fastcall(struct IKsPin *, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001de40`
- `0x1800280d0`
- `0x180034b18`

## callees

- `0x180002b58`
- `0x18000f7e0`
- `0x1800105c4`
- `0x180025a74`
- `0x180032cf0`
- `0x180036330`
- `0x180038f1c`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall CreateSeparatePipe(struct IKsPin *a1, unsigned int a2)
{
  __int64 v4; // rcx
  unsigned int PipeBasedOnOnePin; // ebx
  __int64 v6; // rcx
  __int64 v7; // rax
  unsigned int v8; // edi
  unsigned int *v10; // [rsp+28h] [rbp-28h]
  struct _GUID v11; // [rsp+40h] [rbp-10h] BYREF
  __int64 v12; // [rsp+70h] [rbp+20h] BYREF
  __int64 v13; // [rsp+80h] [rbp+30h] BYREF
  struct IKsPin *v14; // [rsp+88h] [rbp+38h] BYREF

  v14 = 0;
  v12 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 0x96u, &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids, a1);
  FindConnectedPinOnPipe(a1, 0, 0, &v14);
  if ( a1->QueryInterface(a1, &GUID_e539cd90_a8b4_11d1_8189_00a0c9062802, (void **)&v12) >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v4 = v12;
  }
  else
  {
    v4 = 0;
    v12 = 0;
  }
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 48LL))(v4, 0);
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 56LL))(v12, 0);
  a1->KsReceiveAllocator(a1, 0);
  PipeBasedOnOnePin = MakePipeBasedOnOnePin(a1, a2, 0);
  if ( v14 )
  {
    v13 = 0;
    if ( v14->QueryInterface(v14, &GUID_e539cd90_a8b4_11d1_8189_00a0c9062802, (void **)&v13) >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      v6 = v13;
    }
    else
    {
      v6 = 0;
      v13 = 0;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v6 + 48LL))(v6, 0);
    v8 = 4 - a2;
    v11 = *(struct _GUID *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 56LL))(v7) + 16);
    AssignPipeAllocatorHandler(v14, 5 - (v8 != 0), &v11, 2, 0, v10, 1);
    PipeBasedOnOnePin = ResolvePipeDimensions(v14, 5 - (unsigned int)(v8 != 0));
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0x97u,
      &WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids,
      PipeBasedOnOnePin);
  return PipeBasedOnOnePin;
}

```

## disassembly

```asm
0x180036330  mov     [rsp-18h+arg_8], rbx
0x180036335  push    rbp
0x180036336  push    rdi
0x180036337  push    r14
0x180036339  mov     rbp, rsp
0x18003633c  sub     rsp, 50h
0x180036340  mov     edi, edx
0x180036342  mov     [rbp+arg_18], 0
0x18003634a  mov     rbx, rcx
0x18003634d  mov     [rbp+arg_0], 0
0x180036355  mov     rcx, cs:WPP_GLOBAL_Control
0x18003635c  lea     r14, WPP_GLOBAL_Control
0x180036363  cmp     rcx, r14
0x180036366  jz      short loc_180036386
0x180036368  cmp     byte ptr [rcx+19h], 2
0x18003636c  jb      short loc_180036386
0x18003636e  mov     rcx, [rcx+10h]
0x180036372  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x180036379  mov     edx, 96h
0x18003637e  mov     r9, rbx
0x180036381  call    WPP_SF_q
0x180036386  lea     r9, [rbp+arg_18]; struct IKsPin **
0x18003638a  xor     r8d, r8d; int
0x18003638d  xor     edx, edx; struct IKsAllocatorEx *
0x18003638f  mov     rcx, rbx; struct IKsPin *
0x180036392  call    ?FindConnectedPinOnPipe@@YAHPEAUIKsPin@@PEAUIKsAllocatorEx@@HPEAPEAU1@@Z; FindConnectedPinOnPipe(IKsPin *,IKsAllocatorEx *,int,IKsPin * *)
0x180036397  mov     rax, [rbx]
0x18003639a  lea     r8, [rbp+arg_0]
0x18003639e  lea     rdx, _GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x1800363a5  mov     rcx, rbx
0x1800363a8  mov     rax, [rax]
0x1800363ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363b0  test    eax, eax
0x1800363b2  jns     short loc_1800363BC
0x1800363b4  xor     ecx, ecx
0x1800363b6  mov     [rbp+arg_0], rcx
0x1800363ba  jmp     short loc_1800363D0
0x1800363bc  mov     rcx, [rbp+arg_0]
0x1800363c0  mov     rax, [rcx]
0x1800363c3  mov     rax, [rax+10h]
0x1800363c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363cc  mov     rcx, [rbp+arg_0]
0x1800363d0  mov     rax, [rcx]
0x1800363d3  xor     edx, edx
0x1800363d5  mov     rax, [rax+30h]
0x1800363d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363de  mov     rcx, [rbp+arg_0]
0x1800363e2  xor     edx, edx
0x1800363e4  mov     rax, [rcx]
0x1800363e7  mov     rax, [rax+38h]
0x1800363eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800363f0  mov     rax, [rbx]
0x1800363f3  xor     edx, edx
0x1800363f5  mov     rcx, rbx
0x1800363f8  mov     rax, [rax+58h]
0x1800363fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036401  xor     r8d, r8d; struct IKsPin *
0x180036404  mov     edx, edi; unsigned int
0x180036406  mov     rcx, rbx; struct IKsPin *
0x180036409  call    ?MakePipeBasedOnOnePin@@YAJPEAUIKsPin@@K0@Z; MakePipeBasedOnOnePin(IKsPin *,ulong,IKsPin *)
0x18003640e  mov     rcx, [rbp+arg_18]
0x180036412  mov     ebx, eax
0x180036414  test    rcx, rcx
0x180036417  jz      loc_1800364C0
0x18003641d  mov     [rbp+arg_10], 0
0x180036425  lea     r8, [rbp+arg_10]
0x180036429  mov     rax, [rcx]
0x18003642c  lea     rdx, _GUID_e539cd90_a8b4_11d1_8189_00a0c9062802
0x180036433  mov     rax, [rax]
0x180036436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003643b  test    eax, eax
0x18003643d  jns     short loc_180036447
0x18003643f  xor     ecx, ecx
0x180036441  mov     [rbp+arg_10], rcx
0x180036445  jmp     short loc_18003645B
0x180036447  mov     rcx, [rbp+arg_10]
0x18003644b  mov     rax, [rcx]
0x18003644e  mov     rax, [rax+10h]
0x180036452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036457  mov     rcx, [rbp+arg_10]
0x18003645b  mov     rax, [rcx]
0x18003645e  xor     edx, edx
0x180036460  mov     rax, [rax+30h]
0x180036464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036469  mov     rdx, rax
0x18003646c  mov     rcx, [rax]
0x18003646f  mov     rax, [rcx+38h]
0x180036473  mov     rcx, rdx
0x180036476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003647b  mov     rcx, [rbp+arg_18]; struct IKsPin *
0x18003647f  lea     r8, [rbp+var_10]; struct _GUID
0x180036483  sub     edi, 4
0x180036486  mov     [rsp+50h+var_20], 1; int
0x18003648e  neg     edi
0x180036490  mov     [rsp+50h+var_30], 0; struct IKsPin **
0x180036499  movups  xmm0, xmmword ptr [rax+10h]
0x18003649d  sbb     ebx, ebx
0x18003649f  mov     r9d, 2; unsigned int
0x1800364a5  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x1800364aa  lea     edx, [rbx+5]; unsigned int
0x1800364ad  call    ?AssignPipeAllocatorHandler@@YAHPEAUIKsPin@@KU_GUID@@KPEAPEAU1@PEAKH@Z; AssignPipeAllocatorHandler(IKsPin *,ulong,_GUID,ulong,IKsPin * *,ulong *,int)
0x1800364b2  mov     rcx, [rbp+arg_18]; struct IKsPin *
0x1800364b6  lea     edx, [rbx+5]; unsigned int
0x1800364b9  call    ?ResolvePipeDimensions@@YAJPEAUIKsPin@@KK@Z; ResolvePipeDimensions(IKsPin *,ulong,ulong)
0x1800364be  mov     ebx, eax
0x1800364c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800364c7  cmp     rcx, r14
0x1800364ca  jz      short loc_1800364EA
0x1800364cc  cmp     byte ptr [rcx+19h], 2
0x1800364d0  jb      short loc_1800364EA
0x1800364d2  mov     rcx, [rcx+10h]
0x1800364d6  lea     r8, WPP_b4224db57a533ec369249cc514b4e1a5_Traceguids
0x1800364dd  mov     edx, 97h
0x1800364e2  mov     r9d, ebx
0x1800364e5  call    WPP_SF_d
0x1800364ea  mov     eax, ebx
0x1800364ec  mov     rbx, [rsp+50h+arg_8]
0x1800364f1  add     rsp, 50h
0x1800364f5  pop     r14
0x1800364f7  pop     rdi
0x1800364f8  pop     rbp
0x1800364f9  retn
```
