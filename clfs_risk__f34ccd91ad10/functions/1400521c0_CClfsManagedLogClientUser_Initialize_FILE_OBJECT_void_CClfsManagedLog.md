# CClfsManagedLogClientUser::Initialize(_FILE_OBJECT *,void *,CClfsManagedLog *)

- ea: `0x1400521c0`
- end: `0x140052506`
- name: `?Initialize@CClfsManagedLogClientUser@@EEAAJPEAU_FILE_OBJECT@@PEAXPEAVCClfsManagedLog@@@Z`
- size: `838`
- prototype: `__int64 __fastcall(CClfsManagedLogClientUser *__hidden this, struct _FILE_OBJECT *, void *, struct CClfsManagedLog *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update`

## callees

- `0x140010d88`
- `0x140017b98`
- `0x140017f20`
- `0x140018280`
- `0x14004c3c8`
- `0x1400521c0`
- `0x14006fe80`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140052275`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x1400522eb`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x1400523a8`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x1400523ee`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x140052275`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x1400522eb`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x1400523a8`
- `ntoskrnl!ExAllocatePoolWithQuotaTag` at `0x1400523ee`
- `ntoskrnl!ObfReferenceObject` at `0x140052382`
- `ntoskrnl!ObfReferenceObject` at `0x140052382`
- `ntoskrnl!ProbeForRead` at `0x14005231c`
- `ntoskrnl!ProbeForRead` at `0x14005231c`
- `ntoskrnl!KeInitializeQueue` at `0x14005241c`
- `ntoskrnl!KeInitializeQueue` at `0x14005241c`

## pseudocode

```c
__int64 __fastcall CClfsManagedLogClientUser::Initialize(
        CClfsManagedLogClientUser *this,
        struct _FILE_OBJECT *a2,
        _QWORD *a3,
        struct CClfsManagedLog *a4)
{
  int PendingRequestQueueInterface; // ebx
  _QWORD *v7; // r13
  char v8; // cl
  _QWORD *v9; // r14
  _BYTE *v10; // r12
  unsigned int v12; // ecx
  _OWORD *PoolWithQuotaTag; // rax
  _OWORD *v14; // rbx
  char *v15; // r14
  _QWORD *v16; // rax
  struct _KQUEUE *v17; // rcx
  __int64 v18; // rdx

  PendingRequestQueueInterface = -1073741811;
  v7 = (_QWORD *)a3[4];
  v8 = *((_BYTE *)a3 + 40);
  v9 = v7 + 33;
  v10 = (_BYTE *)v7[33];
  if ( v10 && !v10[232] )
    return 3222929444LL;
  *((_BYTE *)this + 232) = v8 != 0;
  if ( v8 )
    goto LABEL_23;
  if ( *a3 )
  {
    v12 = *((_DWORD *)a3 + 4);
    if ( v12 && v12 + 24 >= v12 )
    {
      PoolWithQuotaTag = ExAllocatePoolWithQuotaTag((POOL_TYPE)1033, 0x48u, 0x714D6C43u);
      v14 = PoolWithQuotaTag;
      if ( !ExPoolZeroingNativelySupported && PoolWithQuotaTag )
        memset(PoolWithQuotaTag, 0, 0x48u);
      v15 = (char *)this + 216;
      *((_QWORD *)this + 27) = v14;
      if ( v14 )
      {
        *v14 = *(_OWORD *)a3;
        v14[1] = *((_OWORD *)a3 + 1);
        *(_DWORD *)(*(_QWORD *)v15 + 40LL) = *(_DWORD *)(*(_QWORD *)v15 + 16LL);
        *(_QWORD *)(*(_QWORD *)v15 + 32LL) = ExAllocatePoolWithQuotaTag(
                                               (POOL_TYPE)9,
                                               *(unsigned int *)(*(_QWORD *)v15 + 40LL),
                                               0x784D6C43u);
        if ( *(_QWORD *)(*(_QWORD *)v15 + 32LL) )
        {
          ProbeForRead(*(volatile void **)(*(_QWORD *)v15 + 8LL), *(unsigned int *)(*(_QWORD *)v15 + 16LL), 4u);
          RtlCopyFromUser(
            *(void **)(*(_QWORD *)v15 + 32LL),
            *(void **)(*(_QWORD *)v15 + 8LL),
            *(unsigned int *)(*(_QWORD *)v15 + 40LL));
          *(_QWORD *)(*(_QWORD *)v15 + 48LL) = KeGetCurrentThread();
          ObfReferenceObject(*(PVOID *)(*(_QWORD *)v15 + 48LL));
          v9 = v7 + 33;
LABEL_23:
          if ( v10 )
          {
            (**(void (__fastcall ***)(_BYTE *))v10)(v10);
            LOBYTE(v18) = 1;
            (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v10 + 40LL))(v10, v18);
            (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v10 + 8LL))(v10);
          }
          PendingRequestQueueInterface = CClfsManagedLogClient::Initialize(this, a2, a3, a4);
          if ( PendingRequestQueueInterface >= 0 )
          {
            PendingRequestQueueInterface = CClfsLogCcb::InstallLifetimeListener(
                                             (CClfsLogCcb *)v7,
                                             (struct ILifetimeListener *)(((unsigned __int64)this + 8)
                                                                        & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)));
            if ( PendingRequestQueueInterface >= 0 )
            {
              *v9 = this;
              *((_QWORD *)this + 26) = v7;
            }
          }
          goto LABEL_28;
        }
      }
      goto LABEL_12;
    }
  }
  else
  {
    v16 = ExAllocatePoolWithQuotaTag((POOL_TYPE)1544, 0x18u, 0x714D6C43u);
    if ( !ExPoolZeroingNativelySupported && v16 )
    {
      *(_OWORD *)v16 = 0;
      v16[2] = 0;
    }
    *((_QWORD *)this + 28) = v16;
    if ( !v16
      || (**((_QWORD **)this + 28) = ExAllocatePoolWithQuotaTag((POOL_TYPE)520, 0x40u, 0x714D6C43u),
          (v17 = (struct _KQUEUE *)**((_QWORD **)this + 28)) == 0) )
    {
LABEL_12:
      PendingRequestQueueInterface = -1073741670;
      goto LABEL_28;
    }
    KeInitializeQueue(v17, 0);
    PendingRequestQueueInterface = ClfsGetPendingRequestQueueInterface(
                                     *((_QWORD *)a4 + 42),
                                     *((_QWORD *)this + 28) + 16LL);
    if ( PendingRequestQueueInterface >= 0 )
      goto LABEL_23;
    *(_QWORD *)(*((_QWORD *)this + 28) + 16LL) = 0;
  }
LABEL_28:
  if ( PendingRequestQueueInterface < 0 )
    (*(void (__fastcall **)(CClfsManagedLogClientUser *))(*(_QWORD *)this + 88LL))(this);
  return (unsigned int)PendingRequestQueueInterface;
}

```

## disassembly

```asm
0x1400521c0  mov     rax, rsp
0x1400521c3  mov     [rax+20h], r9
0x1400521c7  mov     [rax+18h], r8
0x1400521cb  mov     [rax+10h], rdx
0x1400521cf  mov     [rax+8], rcx
0x1400521d3  push    rbx
0x1400521d4  push    rsi
0x1400521d5  push    r12
0x1400521d7  push    r13
0x1400521d9  push    r14
0x1400521db  push    r15
0x1400521dd  sub     rsp, 58h
0x1400521e1  mov     r15, r8
0x1400521e4  mov     rsi, rcx
0x1400521e7  mov     ebx, 0C000000Dh
0x1400521ec  mov     [rax-68h], ebx
0x1400521ef  mov     r13, [r8+20h]
0x1400521f3  mov     [rsp+88h+var_58], r13
0x1400521f8  mov     cl, [r8+28h]
0x1400521fc  lea     r14, [r13+108h]
0x140052203  mov     [rsp+88h+var_48], r14
0x140052208  mov     r12, [r14]
0x14005220b  mov     [rsp+88h+var_60], r12
0x140052210  test    r12, r12
0x140052213  jz      short loc_140052235
0x140052215  cmp     byte ptr [r12+0E8h], 0
0x14005221e  jnz     short loc_140052235
0x140052220  mov     eax, 0C01A0024h
0x140052225  add     rsp, 58h
0x140052229  pop     r15
0x14005222b  pop     r14
0x14005222d  pop     r13
0x14005222f  pop     r12
0x140052231  pop     rsi
0x140052232  pop     rbx
0x140052233  retn
0x140052235  test    cl, cl
0x140052237  setnz   al
0x14005223a  mov     [rsi+0E8h], al
0x140052240  test    cl, cl
0x140052242  jnz     loc_140052465
0x140052248  cmp     qword ptr [r8], 0
0x14005224c  jz      loc_140052398
0x140052252  mov     ecx, [r8+10h]
0x140052256  test    ecx, ecx
0x140052258  jz      short loc_1400522B8
0x14005225a  lea     eax, [rcx+18h]
0x14005225d  cmp     eax, ecx
0x14005225f  jb      short loc_1400522B8
0x140052261  mov     r8d, 714D6C43h; Tag
0x140052267  mov     r14d, 48h ; 'H'
0x14005226d  mov     edx, r14d; NumberOfBytes
0x140052270  mov     ecx, 409h; PoolType
0x140052275  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x14005227c  nop     dword ptr [rax+rax+00h]
0x140052281  mov     rbx, rax
0x140052284  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14005228b  jnz     short loc_14005229F
0x14005228d  test    rax, rax
0x140052290  jz      short loc_14005229F
0x140052292  mov     r8d, r14d; Size
0x140052295  xor     edx, edx; Val
0x140052297  mov     rcx, rax; void *
0x14005229a  call    memset
0x14005229f  lea     r14, [rsi+0D8h]
0x1400522a6  mov     [rsp+88h+var_50], r14
0x1400522ab  mov     [r14], rbx
0x1400522ae  test    rbx, rbx
0x1400522b1  jnz     short loc_1400522C1
0x1400522b3  mov     ebx, 0C000009Ah
0x1400522b8  mov     [rsp+88h+var_68], ebx
0x1400522bc  jmp     loc_1400524EC
0x1400522c1  movups  xmm0, xmmword ptr [r15]
0x1400522c5  movups  xmmword ptr [rbx], xmm0
0x1400522c8  movups  xmm1, xmmword ptr [r15+10h]
0x1400522cd  movups  xmmword ptr [rbx+10h], xmm1
0x1400522d1  mov     rcx, [r14]
0x1400522d4  mov     eax, [rcx+10h]
0x1400522d7  mov     [rcx+28h], eax
0x1400522da  mov     rax, [r14]
0x1400522dd  mov     edx, [rax+28h]; NumberOfBytes
0x1400522e0  mov     ecx, 9; PoolType
0x1400522e5  mov     r8d, 784D6C43h; Tag
0x1400522eb  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x1400522f2  nop     dword ptr [rax+rax+00h]
0x1400522f7  mov     rcx, rax
0x1400522fa  mov     rax, [r14]
0x1400522fd  mov     [rax+20h], rcx
0x140052301  mov     rcx, [r14]
0x140052304  cmp     qword ptr [rcx+20h], 0
0x140052309  jz      short loc_1400522B3
0x14005230b  xor     ebx, ebx
0x14005230d  mov     [rsp+88h+var_68], ebx
0x140052311  mov     edx, [rcx+10h]; Length
0x140052314  lea     r8d, [rbx+4]; Alignment
0x140052318  mov     rcx, [rcx+8]; Address
0x14005231c  call    cs:__imp_ProbeForRead
0x140052323  nop     dword ptr [rax+rax+00h]
0x140052328  mov     rcx, [r14]
0x14005232b  mov     r8d, [rcx+28h]; Size
0x14005232f  mov     rdx, [rcx+8]; Src
0x140052333  mov     rcx, [rcx+20h]; void *
0x140052337  call    RtlCopyFromUser
0x14005233c  jmp     short loc_140052363
0x14005233e  mov     ebx, eax
0x140052340  mov     [rsp+88h+var_68], eax
0x140052344  mov     rsi, [rsp+88h+arg_0]
0x14005234c  mov     r15, [rsp+88h+arg_10]
0x140052354  mov     r12, [rsp+88h+var_60]
0x140052359  mov     r13, [rsp+88h+var_58]
0x14005235e  mov     r14, [rsp+88h+var_50]
0x140052363  test    ebx, ebx
0x140052365  js      loc_1400524EC
0x14005236b  mov     rcx, gs:188h
0x140052374  mov     rax, [r14]
0x140052377  mov     [rax+30h], rcx
0x14005237b  mov     rcx, [r14]
0x14005237e  mov     rcx, [rcx+30h]; Object
0x140052382  call    cs:__imp_ObfReferenceObject
0x140052389  nop     dword ptr [rax+rax+00h]
0x14005238e  mov     r14, [rsp+88h+var_48]
0x140052393  jmp     loc_140052465
0x140052398  mov     edx, 18h; NumberOfBytes
0x14005239d  mov     ecx, 608h; PoolType
0x1400523a2  mov     r8d, 714D6C43h; Tag
0x1400523a8  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x1400523af  nop     dword ptr [rax+rax+00h]
0x1400523b4  cmp     cs:ExPoolZeroingNativelySupported, 0
0x1400523bb  jnz     short loc_1400523CE
0x1400523bd  test    rax, rax
0x1400523c0  jz      short loc_1400523CE
0x1400523c2  xorps   xmm0, xmm0
0x1400523c5  xor     ecx, ecx
0x1400523c7  movups  xmmword ptr [rax], xmm0
0x1400523ca  mov     [rax+10h], rcx
0x1400523ce  mov     [rsi+0E0h], rax
0x1400523d5  test    rax, rax
0x1400523d8  jz      loc_1400522B3
0x1400523de  mov     edx, 40h ; '@'; NumberOfBytes
0x1400523e3  mov     ecx, 208h; PoolType
0x1400523e8  mov     r8d, 714D6C43h; Tag
0x1400523ee  call    cs:__imp_ExAllocatePoolWithQuotaTag
0x1400523f5  nop     dword ptr [rax+rax+00h]
0x1400523fa  mov     rcx, rax
0x1400523fd  mov     rax, [rsi+0E0h]
0x140052404  mov     [rax], rcx
0x140052407  mov     rax, [rsi+0E0h]
0x14005240e  mov     rcx, [rax]; Queue
0x140052411  test    rcx, rcx
0x140052414  jz      loc_1400522B3
0x14005241a  xor     edx, edx; Count
0x14005241c  call    cs:__imp_KeInitializeQueue
0x140052423  nop     dword ptr [rax+rax+00h]
0x140052428  mov     rdx, [rsi+0E0h]
0x14005242f  add     rdx, 10h
0x140052433  mov     rcx, [rsp+88h+arg_18]
0x14005243b  mov     rcx, [rcx+150h]
0x140052442  call    ClfsGetPendingRequestQueueInterface
0x140052447  mov     ebx, eax
0x140052449  mov     [rsp+88h+var_68], eax
0x14005244d  test    eax, eax
0x14005244f  jns     short loc_140052465
0x140052451  mov     rax, [rsi+0E0h]
0x140052458  mov     qword ptr [rax+10h], 0
0x140052460  jmp     loc_1400524EC
0x140052465  test    r12, r12
0x140052468  jz      short loc_14005249B
0x14005246a  mov     rax, [r12]
0x14005246e  mov     rax, [rax]
0x140052471  mov     rcx, r12
0x140052474  call    _guard_dispatch_icall
0x140052479  mov     rax, [r12]
0x14005247d  mov     rax, [rax+28h]
0x140052481  mov     dl, 1
0x140052483  mov     rcx, r12
0x140052486  call    _guard_dispatch_icall
0x14005248b  mov     rax, [r12]
0x14005248f  mov     rax, [rax+8]
0x140052493  mov     rcx, r12
0x140052496  call    _guard_dispatch_icall
0x14005249b  mov     r9, [rsp+88h+arg_18]; struct CClfsManagedLog *
0x1400524a3  mov     r8, r15; void *
0x1400524a6  mov     rdx, [rsp+88h+plfoLog]; plfoLog
0x1400524ae  mov     rcx, rsi; this
0x1400524b1  call    ?Initialize@CClfsManagedLogClient@@UEAAJPEAU_FILE_OBJECT@@PEAXPEAVCClfsManagedLog@@@Z; CClfsManagedLogClient::Initialize(_FILE_OBJECT *,void *,CClfsManagedLog *)
0x1400524b6  mov     ebx, eax
0x1400524b8  mov     [rsp+88h+var_68], eax
0x1400524bc  test    eax, eax
0x1400524be  js      short loc_1400524EC
0x1400524c0  mov     rax, rsi
0x1400524c3  lea     rcx, [rsi+8]
0x1400524c7  neg     rax
0x1400524ca  sbb     rdx, rdx
0x1400524cd  and     rdx, rcx; struct ILifetimeListener *
0x1400524d0  mov     rcx, r13; this
0x1400524d3  call    ?InstallLifetimeListener@CClfsLogCcb@@QEAAJPEAUILifetimeListener@@@Z; CClfsLogCcb::InstallLifetimeListener(ILifetimeListener *)
0x1400524d8  mov     ebx, eax
0x1400524da  mov     [rsp+88h+var_68], eax
0x1400524de  test    eax, eax
0x1400524e0  js      short loc_1400524EC
0x1400524e2  mov     [r14], rsi
0x1400524e5  mov     [rsi+0D0h], r13
0x1400524ec  test    ebx, ebx
0x1400524ee  jns     short loc_1400524FF
0x1400524f0  mov     rax, [rsi]
0x1400524f3  mov     rax, [rax+58h]
0x1400524f7  mov     rcx, rsi
0x1400524fa  call    _guard_dispatch_icall
0x1400524ff  mov     eax, ebx
0x140052501  jmp     loc_140052225
0x140080b49  push    rbp
0x140080b4b  sub     rsp, 20h
0x140080b4f  mov     rbp, rdx
0x140080b52  cmp     dword ptr [rbp+20h], 0
0x140080b56  jge     short loc_140080B6C
0x140080b58  mov     rcx, [rbp+90h]
0x140080b5f  mov     rax, [rcx]
0x140080b62  mov     rax, [rax+58h]
0x140080b66  call    _guard_dispatch_icall
0x140080b6b  nop
0x140080b6c  add     rsp, 20h
0x140080b70  pop     rbp
0x140080b71  retn
```
