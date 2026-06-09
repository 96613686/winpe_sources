# NfsRdrBuildCall

- ea: `0x140001f10`
- end: `0x1400022b5`
- name: `NfsRdrBuildCall`
- size: `933`
- prototype: ``
- caller_count: `17`
- callee_count: `4`
- tags: ``

## callers

- `0x1400029d0`
- `0x140004530`
- `0x14000c8d8`
- `0x14000cf04`
- `0x14000da84`
- `0x14000df64`
- `0x14000e4ec`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x140010904`
- `0x140011298`
- `0x140011984`
- `0x1400124ec`
- `0x1400132cc`
- `0x14002a9e0`
- `0x14002b138`

## callees

- `0x140001f10`
- `0x1400298b0`
- `0x140029df8`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140001ff8`
- `ntoskrnl!KeDelayExecutionThread` at `0x140002147`
- `ntoskrnl!KeDelayExecutionThread` at `0x140001ff8`
- `ntoskrnl!KeDelayExecutionThread` at `0x140002147`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001fb3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400020ba`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002108`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002267`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001fb3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400020ba`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002108`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002267`
- `ntoskrnl!KeReleaseMutex` at `0x140001fdc`
- `ntoskrnl!KeReleaseMutex` at `0x14000201b`
- `ntoskrnl!KeReleaseMutex` at `0x140002053`
- `ntoskrnl!KeReleaseMutex` at `0x140002079`
- `ntoskrnl!KeReleaseMutex` at `0x1400020d9`
- `ntoskrnl!KeReleaseMutex` at `0x14000212b`
- `ntoskrnl!KeReleaseMutex` at `0x140002186`
- `ntoskrnl!KeReleaseMutex` at `0x14000228f`
- `ntoskrnl!KeReleaseMutex` at `0x140001fdc`
- `ntoskrnl!KeReleaseMutex` at `0x14000201b`
- `ntoskrnl!KeReleaseMutex` at `0x140002053`
- `ntoskrnl!KeReleaseMutex` at `0x140002079`
- `ntoskrnl!KeReleaseMutex` at `0x1400020d9`
- `ntoskrnl!KeReleaseMutex` at `0x14000212b`
- `ntoskrnl!KeReleaseMutex` at `0x140002186`
- `ntoskrnl!KeReleaseMutex` at `0x14000228f`
- `rpcxdr!OncRpcDereferenceOutboundGssCtx` at `0x14000227a`
- `rpcxdr!OncRpcDereferenceOutboundGssCtx` at `0x14000227a`
- `rpcxdr!OncRpcReferenceOutboundGssCtx` at `0x14000203e`
- `rpcxdr!OncRpcReferenceOutboundGssCtx` at `0x140002171`
- `rpcxdr!OncRpcReferenceOutboundGssCtx` at `0x14000203e`
- `rpcxdr!OncRpcReferenceOutboundGssCtx` at `0x140002171`
- `rpcxdr!OncRpcBuildCall` at `0x14000223e`
- `rpcxdr!OncRpcBuildCall` at `0x14000223e`

## pseudocode

```c
__int64 __fastcall NfsRdrBuildCall(__int64 a1, unsigned int a2, unsigned int a3, int a4, int a5, int a6, __int64 a7)
{
  __int64 v11; // rdi
  char v13; // si
  int v14; // eax
  unsigned int v15; // esi
  unsigned int i; // eax
  int v17; // eax
  __int64 v18; // rbx
  int v19; // eax
  struct _KMUTANT *v20; // rcx
  struct _KMUTANT *v21; // rcx
  __int64 v23; // [rsp+40h] [rbp-81h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+48h] [rbp-79h] BYREF
  __int64 v25; // [rsp+50h] [rbp-71h] BYREF
  _QWORD v26[20]; // [rsp+60h] [rbp-61h] BYREF
  unsigned int v27; // [rsp+140h] [rbp+7Fh]
  int v28; // [rsp+140h] [rbp+7Fh]

  v23 = 0;
  HIDWORD(v26[0]) = 0;
  v11 = *(_QWORD *)(a7 + 40);
  v13 = 0;
  memset(v26, 0, 0x54u);
  v14 = *(_DWORD *)(v11 + 176);
  if ( (v14 & 0xE) != 0 )
  {
    v25 = 0;
    if ( (v14 & 8) != 0 )
      v15 = 3;
    else
      v15 = ((v14 & 4) != 0) + 1;
    for ( i = 0; ; i = v27 + 1 )
    {
      v27 = i;
      if ( i >= 0x32 )
        goto LABEL_21;
      KeWaitForSingleObject(*(PVOID *)(v11 + 184), Executive, 0, 0, 0);
      v17 = *(_DWORD *)(v11 + 200);
      if ( v17 == 2 )
        break;
      if ( v17 != 1 )
      {
        v18 = 0;
        if ( v17 == 3 )
        {
          KeReleaseMutex(*(PRKMUTEX *)(v11 + 184), 0);
          v19 = -1073741790;
          v28 = -1073741790;
        }
        else
        {
          v28 = 0;
          OncRpcReferenceOutboundGssCtx(*(_QWORD *)(v11 + 192));
          KeReleaseMutex(*(PRKMUTEX *)(v11 + 184), 0);
          v19 = 0;
        }
        goto LABEL_18;
      }
      KeReleaseMutex(*(PRKMUTEX *)(v11 + 184), 0);
      Interval.QuadPart = -1000000;
      KeDelayExecutionThread(0, 0, &Interval);
    }
    v20 = *(struct _KMUTANT **)(v11 + 184);
    *(_DWORD *)(v11 + 200) = 1;
    KeReleaseMutex(v20, 0);
    v28 = NfsRdrpInitializeOutboundGssContext(StartContext, a7, v15, &v25);
    if ( v28 >= 0 )
    {
      while ( 1 )
      {
        KeWaitForSingleObject(*(PVOID *)(v11 + 184), Executive, 0, 0, 0);
        if ( !*(_DWORD *)(*(_QWORD *)(v11 + 192) + 4LL) )
          break;
        KeReleaseMutex(*(PRKMUTEX *)(v11 + 184), 0);
        Interval.QuadPart = -1000000;
        KeDelayExecutionThread(0, 0, &Interval);
      }
      v18 = *(_QWORD *)(v11 + 192);
      *(_QWORD *)(v11 + 192) = v25;
      *(_DWORD *)(v11 + 200) = 0;
      ((void (*)(void))OncRpcReferenceOutboundGssCtx)();
      KeReleaseMutex(*(PRKMUTEX *)(v11 + 184), 0);
      v19 = v28;
    }
    else
    {
      KeWaitForSingleObject(*(PVOID *)(v11 + 184), Executive, 0, 0, 0);
      v21 = *(struct _KMUTANT **)(v11 + 184);
      *(_DWORD *)(v11 + 200) = 3;
      KeReleaseMutex(v21, 0);
      v19 = v28;
      v18 = 0;
    }
LABEL_18:
    v13 = 1;
    if ( v18 )
    {
      NfsRdrpTeardownOutboundGssContext(v18);
      v19 = v28;
    }
    if ( v19 < 0 )
    {
LABEL_21:
      if ( v25 )
        NfsRdrpTeardownOutboundGssContext(v25);
      return v23;
    }
  }
  if ( *(_QWORD *)(v11 + 192) )
  {
    LODWORD(v26[0]) = 6;
    v26[1] = *(_QWORD *)(v11 + 192);
  }
  else
  {
    LODWORD(v26[0]) = 1;
    *(_OWORD *)&v26[1] = *(_OWORD *)(v11 + 36);
    *(_OWORD *)&v26[3] = *(_OWORD *)(v11 + 52);
    *(_OWORD *)&v26[5] = *(_OWORD *)(v11 + 68);
    *(_OWORD *)&v26[7] = *(_OWORD *)(v11 + 84);
    *(_OWORD *)((char *)&v26[8] + 4) = *(_OWORD *)(v11 + 96);
  }
  OncRpcBuildCall(&v23, a1, a2, a3, a4, a5, a6, v26);
  if ( v13 )
  {
    KeWaitForSingleObject(*(PVOID *)(v11 + 184), Executive, 0, 0, 0);
    OncRpcDereferenceOutboundGssCtx(*(_QWORD *)(v11 + 192));
    KeReleaseMutex(*(PRKMUTEX *)(v11 + 184), 0);
  }
  return v23;
}

```

## disassembly

```asm
0x140001f10  push    rbp
0x140001f12  push    rbx
0x140001f13  push    rsi
0x140001f14  push    rdi
0x140001f15  push    r12
0x140001f17  push    r13
0x140001f19  push    r14
0x140001f1b  push    r15
0x140001f1d  lea     rbp, [rsp-7]
0x140001f22  sub     rsp, 0C8h
0x140001f29  mov     rbx, [rbp+3Fh+arg_30]
0x140001f2d  mov     r15d, r8d
0x140001f30  mov     r12d, edx
0x140001f33  mov     [rsp+100h+var_C0], 0
0x140001f3c  mov     r13, rcx
0x140001f3f  xor     eax, eax
0x140001f41  xor     edx, edx; Val
0x140001f43  mov     [rbp+3Fh+var_9C], eax
0x140001f46  mov     rdi, [rbx+28h]
0x140001f4a  lea     rcx, [rbp+3Fh+var_A0]; void *
0x140001f4e  mov     r8d, 54h ; 'T'; Size
0x140001f54  mov     r14d, r9d
0x140001f57  xor     sil, sil
0x140001f5a  call    memset
0x140001f5f  mov     eax, [rdi+0B0h]
0x140001f65  test    al, 0Eh
0x140001f67  jz      loc_1400021C7
0x140001f6d  mov     [rbp+3Fh+var_B0], 0
0x140001f75  test    al, 8
0x140001f77  jz      short loc_140001F80
0x140001f79  mov     esi, 3
0x140001f7e  jmp     short loc_140001F8D
0x140001f80  test    al, 4
0x140001f82  mov     esi, 0
0x140001f87  setnz   sil
0x140001f8b  inc     esi
0x140001f8d  xor     eax, eax
0x140001f8f  mov     dword ptr [rbp+3Fh+arg_30], eax
0x140001f92  cmp     eax, 32h ; '2'
0x140001f95  jnb     loc_1400021B0
0x140001f9b  mov     rcx, [rdi+0B8h]; Object
0x140001fa2  xor     r9d, r9d; Alertable
0x140001fa5  xor     r8d, r8d; WaitMode
0x140001fa8  mov     [rsp+100h+Timeout], 0; Timeout
0x140001fb1  xor     edx, edx; WaitReason
0x140001fb3  call    cs:__imp_KeWaitForSingleObject
0x140001fba  nop     dword ptr [rax+rax+00h]
0x140001fbf  mov     eax, [rdi+0C8h]
0x140001fc5  cmp     eax, 2
0x140001fc8  jz      loc_140002066
0x140001fce  cmp     eax, 1
0x140001fd1  jnz     short loc_14000200B
0x140001fd3  mov     rcx, [rdi+0B8h]; Mutex
0x140001fda  xor     edx, edx; Wait
0x140001fdc  call    cs:__imp_KeReleaseMutex
0x140001fe3  nop     dword ptr [rax+rax+00h]
0x140001fe8  lea     r8, [rbp+3Fh+Interval]; Interval
0x140001fec  mov     qword ptr [rbp+3Fh+Interval], 0FFFFFFFFFFF0BDC0h
0x140001ff4  xor     edx, edx; Alertable
0x140001ff6  xor     ecx, ecx; WaitMode
0x140001ff8  call    cs:__imp_KeDelayExecutionThread
0x140001fff  nop     dword ptr [rax+rax+00h]
0x140002004  mov     eax, dword ptr [rbp+3Fh+arg_30]
0x140002007  inc     eax
0x140002009  jmp     short loc_140001F8F
0x14000200b  xor     ebx, ebx
0x14000200d  cmp     eax, 3
0x140002010  jnz     short loc_140002034
0x140002012  mov     rcx, [rdi+0B8h]; Mutex
0x140002019  xor     edx, edx; Wait
0x14000201b  call    cs:__imp_KeReleaseMutex
0x140002022  nop     dword ptr [rax+rax+00h]
0x140002027  mov     eax, 0C0000022h
0x14000202c  mov     dword ptr [rbp+3Fh+arg_30], eax
0x14000202f  jmp     loc_140002199
0x140002034  mov     rcx, [rdi+0C0h]
0x14000203b  mov     dword ptr [rbp+3Fh+arg_30], ebx
0x14000203e  call    cs:__imp_OncRpcReferenceOutboundGssCtx
0x140002045  nop     dword ptr [rax+rax+00h]
0x14000204a  mov     rcx, [rdi+0B8h]; Mutex
0x140002051  xor     edx, edx; Wait
0x140002053  call    cs:__imp_KeReleaseMutex
0x14000205a  nop     dword ptr [rax+rax+00h]
0x14000205f  mov     eax, ebx
0x140002061  jmp     loc_140002199
0x140002066  mov     rcx, [rdi+0B8h]; Mutex
0x14000206d  xor     edx, edx; Wait
0x14000206f  mov     dword ptr [rdi+0C8h], 1
0x140002079  call    cs:__imp_KeReleaseMutex
0x140002080  nop     dword ptr [rax+rax+00h]
0x140002085  mov     rcx, cs:StartContext
0x14000208c  lea     r9, [rbp+3Fh+var_B0]
0x140002090  mov     r8d, esi
0x140002093  mov     rdx, rbx
0x140002096  call    NfsRdrpInitializeOutboundGssContext
0x14000209b  mov     dword ptr [rbp+3Fh+arg_30], eax
0x14000209e  test    eax, eax
0x1400020a0  jns     short loc_1400020F0
0x1400020a2  mov     rcx, [rdi+0B8h]; Object
0x1400020a9  xor     r9d, r9d; Alertable
0x1400020ac  xor     r8d, r8d; WaitMode
0x1400020af  mov     [rsp+100h+Timeout], 0; Timeout
0x1400020b8  xor     edx, edx; WaitReason
0x1400020ba  call    cs:__imp_KeWaitForSingleObject
0x1400020c1  nop     dword ptr [rax+rax+00h]
0x1400020c6  mov     rcx, [rdi+0B8h]; Mutex
0x1400020cd  xor     edx, edx; Wait
0x1400020cf  mov     dword ptr [rdi+0C8h], 3
0x1400020d9  call    cs:__imp_KeReleaseMutex
0x1400020e0  nop     dword ptr [rax+rax+00h]
0x1400020e5  mov     eax, dword ptr [rbp+3Fh+arg_30]
0x1400020e8  test    eax, eax
0x1400020ea  js      loc_140002197
0x1400020f0  mov     rcx, [rdi+0B8h]; Object
0x1400020f7  xor     r9d, r9d; Alertable
0x1400020fa  xor     r8d, r8d; WaitMode
0x1400020fd  mov     [rsp+100h+Timeout], 0; Timeout
0x140002106  xor     edx, edx; WaitReason
0x140002108  call    cs:__imp_KeWaitForSingleObject
0x14000210f  nop     dword ptr [rax+rax+00h]
0x140002114  mov     rax, [rdi+0C0h]
0x14000211b  mov     ecx, [rax+4]
0x14000211e  test    ecx, ecx
0x140002120  jz      short loc_140002155
0x140002122  mov     rcx, [rdi+0B8h]; Mutex
0x140002129  xor     edx, edx; Wait
0x14000212b  call    cs:__imp_KeReleaseMutex
0x140002132  nop     dword ptr [rax+rax+00h]
0x140002137  lea     r8, [rbp+3Fh+Interval]; Interval
0x14000213b  mov     qword ptr [rbp+3Fh+Interval], 0FFFFFFFFFFF0BDC0h
0x140002143  xor     edx, edx; Alertable
0x140002145  xor     ecx, ecx; WaitMode
0x140002147  call    cs:__imp_KeDelayExecutionThread
0x14000214e  nop     dword ptr [rax+rax+00h]
0x140002153  jmp     short loc_1400020F0
0x140002155  mov     rcx, [rbp+3Fh+var_B0]
0x140002159  mov     rbx, [rdi+0C0h]
0x140002160  mov     [rdi+0C0h], rcx
0x140002167  mov     dword ptr [rdi+0C8h], 0
0x140002171  call    cs:__imp_OncRpcReferenceOutboundGssCtx
0x140002178  nop     dword ptr [rax+rax+00h]
0x14000217d  mov     rcx, [rdi+0B8h]; Mutex
0x140002184  xor     edx, edx; Wait
0x140002186  call    cs:__imp_KeReleaseMutex
0x14000218d  nop     dword ptr [rax+rax+00h]
0x140002192  mov     eax, dword ptr [rbp+3Fh+arg_30]
0x140002195  jmp     short loc_140002199
0x140002197  xor     ebx, ebx
0x140002199  mov     sil, 1
0x14000219c  test    rbx, rbx
0x14000219f  jz      short loc_1400021AC
0x1400021a1  mov     rcx, rbx
0x1400021a4  call    NfsRdrpTeardownOutboundGssContext
0x1400021a9  mov     eax, dword ptr [rbp+3Fh+arg_30]
0x1400021ac  test    eax, eax
0x1400021ae  jns     short loc_1400021C7
0x1400021b0  mov     rcx, [rbp+3Fh+var_B0]
0x1400021b4  test    rcx, rcx
0x1400021b7  jz      loc_14000229B
0x1400021bd  call    NfsRdrpTeardownOutboundGssContext
0x1400021c2  jmp     loc_14000229B
0x1400021c7  cmp     qword ptr [rdi+0C0h], 0
0x1400021cf  jz      short loc_1400021E5
0x1400021d1  mov     [rbp+3Fh+var_A0], 6
0x1400021d8  mov     rax, [rdi+0C0h]
0x1400021df  mov     qword ptr [rbp+3Fh+var_98], rax
0x1400021e3  jmp     short loc_140002214
0x1400021e5  mov     [rbp+3Fh+var_A0], 1
0x1400021ec  movups  xmm0, xmmword ptr [rdi+24h]
0x1400021f0  movups  [rbp+3Fh+var_98], xmm0
0x1400021f4  movups  xmm1, xmmword ptr [rdi+34h]
0x1400021f8  movups  [rbp+3Fh+var_88], xmm1
0x1400021fc  movups  xmm0, xmmword ptr [rdi+44h]
0x140002200  movups  [rbp+3Fh+var_78], xmm0
0x140002204  movups  xmm1, xmmword ptr [rdi+54h]
0x140002208  movups  [rbp+3Fh+var_68], xmm1
0x14000220c  movups  xmm0, xmmword ptr [rdi+60h]
0x140002210  movups  [rbp+3Fh+var_68+0Ch], xmm0
0x140002214  lea     rax, [rbp+3Fh+var_A0]
0x140002218  mov     r9d, r15d
0x14000221b  mov     [rsp+100h+var_C8], rax
0x140002220  lea     rcx, [rsp+100h+var_C0]
0x140002225  mov     eax, [rbp+3Fh+arg_28]
0x140002228  mov     r8d, r12d
0x14000222b  mov     [rsp+100h+var_D0], eax
0x14000222f  mov     rdx, r13
0x140002232  mov     eax, [rbp+3Fh+arg_20]
0x140002235  mov     [rsp+100h+var_D8], eax
0x140002239  mov     dword ptr [rsp+100h+Timeout], r14d
0x14000223e  call    cs:__imp_OncRpcBuildCall
0x140002245  nop     dword ptr [rax+rax+00h]
0x14000224a  test    sil, sil
0x14000224d  jz      short loc_14000229B
0x14000224f  mov     rcx, [rdi+0B8h]; Object
0x140002256  xor     r9d, r9d; Alertable
0x140002259  xor     r8d, r8d; WaitMode
0x14000225c  mov     [rsp+100h+Timeout], 0; Timeout
0x140002265  xor     edx, edx; WaitReason
0x140002267  call    cs:__imp_KeWaitForSingleObject
0x14000226e  nop     dword ptr [rax+rax+00h]
0x140002273  mov     rcx, [rdi+0C0h]
0x14000227a  call    cs:__imp_OncRpcDereferenceOutboundGssCtx
0x140002281  nop     dword ptr [rax+rax+00h]
0x140002286  mov     rcx, [rdi+0B8h]; Mutex
0x14000228d  xor     edx, edx; Wait
0x14000228f  call    cs:__imp_KeReleaseMutex
0x140002296  nop     dword ptr [rax+rax+00h]
0x14000229b  mov     rax, [rsp+100h+var_C0]
0x1400022a0  add     rsp, 0C8h
0x1400022a7  pop     r15
0x1400022a9  pop     r14
0x1400022ab  pop     r13
0x1400022ad  pop     r12
0x1400022af  pop     rdi
0x1400022b0  pop     rsi
0x1400022b1  pop     rbx
0x1400022b2  pop     rbp
0x1400022b3  retn
```
