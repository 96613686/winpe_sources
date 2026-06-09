# RRasRoutingDomainConfig::Initialize(void)

- ea: `0x18003dd3c`
- end: `0x18003de95`
- name: `?Initialize@RRasRoutingDomainConfig@@AEAAXXZ`
- size: `345`
- prototype: `void __fastcall(RRasRoutingDomainConfig *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180038828`

## callees

- `0x18003dd3c`
- `0x18004583c`
- `0x180045ad4`
- `0x180046e2a`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x18003de7e`
- `ntdll!RtlInitializeResource` at `0x18003de7e`

## string_xrefs

- `0x18003dd7f`: `RRasRoutingDomainConfig::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RRasRoutingDomainConfig::Initialize(
        RRasRoutingDomainConfig *this,
        __int64 a2,
        __int64 a3,
        void (*a4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))
{
  __int64 v5; // r8
  __int64 v6; // [rsp+20h] [rbp-48h] BYREF
  __int128 v7; // [rsp+28h] [rbp-40h]
  __int128 v8; // [rsp+38h] [rbp-30h]
  __int64 v9; // [rsp+48h] [rbp-20h]
  int v10; // [rsp+50h] [rbp-18h]
  int v11; // [rsp+54h] [rbp-14h]

  v7 = 0;
  v6 = 0;
  v8 = 0;
  v9 = 0;
  v10 = -1;
  v11 = 0;
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v6, L"RRasRoutingDomainConfig::Initialize", 0, a4);
  memset_0(this, 0, 0x202u);
  *(_OWORD *)((char *)this + 584) = 0;
  *(_OWORD *)((char *)this + 600) = 0;
  *((_DWORD *)this + 154) = 0;
  *(_OWORD *)((char *)this + 516) = 0;
  *(_QWORD *)((char *)this + 572) = 0;
  memset_0((char *)this + 624, 0, 0x68u);
  *(_QWORD *)((char *)this + 548) = 0;
  *(_QWORD *)((char *)this + 556) = 0;
  *(_QWORD *)((char *)this + 564) = 0;
  *(_OWORD *)((char *)this + 840) = 0;
  *((_QWORD *)this + 104) = -2147483646;
  *(_QWORD *)((char *)this + 532) = 0;
  *((_DWORD *)this + 135) = 0;
  *((_QWORD *)this + 103) = 0;
  *((_DWORD *)this + 136) = 2;
  v5 = 0;
  do
  {
    *((_DWORD *)this + 3 * v5 + 138) = v5 != 0;
    *((_DWORD *)this + 3 * v5 + 139) = _InterlockedIncrement(&dword_180071170);
    v5 = (unsigned int)(v5 + 1);
  }
  while ( (unsigned int)v5 < *((_DWORD *)this + 136) );
  RtlInitializeResource((PRTL_RESOURCE)((char *)this + 728));
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v6);
}

```

## disassembly

```asm
0x18003dd3c  mov     rax, rsp
0x18003dd3f  push    rbx
0x18003dd40  sub     rsp, 60h
0x18003dd44  mov     rbx, rcx
0x18003dd47  xorps   xmm0, xmm0
0x18003dd4a  movdqu  xmmword ptr [rax-40h], xmm0
0x18003dd4f  mov     qword ptr [rax-48h], 0
0x18003dd57  movdqu  xmmword ptr [rax-30h], xmm0
0x18003dd5c  mov     qword ptr [rax-20h], 0
0x18003dd64  mov     dword ptr [rax-18h], 0FFFFFFFFh
0x18003dd6b  mov     dword ptr [rax-14h], 0
0x18003dd72  cmp     qword ptr cs:xmmword_180071090+8, 0
0x18003dd7a  jz      short loc_18003DD8F
0x18003dd7c  xor     r8d, r8d; unsigned int *
0x18003dd7f  lea     rdx, aRrasroutingdom_24; "RRasRoutingDomainConfig::Initialize"
0x18003dd86  lea     rcx, [rax-48h]; this
0x18003dd8a  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18003dd8f  xor     edx, edx; Val
0x18003dd91  mov     r8d, 202h; Size
0x18003dd97  mov     rcx, rbx; void *
0x18003dd9a  call    memset_0
0x18003dd9f  xorps   xmm0, xmm0
0x18003dda2  movups  xmmword ptr [rbx+248h], xmm0
0x18003dda9  xorps   xmm1, xmm1
0x18003ddac  xor     eax, eax
0x18003ddae  movups  xmmword ptr [rbx+258h], xmm1
0x18003ddb5  mov     [rbx+268h], eax
0x18003ddbb  movups  xmmword ptr [rbx+204h], xmm0
0x18003ddc2  mov     [rbx+23Ch], rax
0x18003ddc9  lea     rcx, [rbx+270h]; void *
0x18003ddd0  xor     edx, edx; Val
0x18003ddd2  lea     r8d, [rax+68h]; Size
0x18003ddd6  call    memset_0
0x18003dddb  mov     qword ptr [rbx+224h], 0
0x18003dde6  mov     qword ptr [rbx+22Ch], 0
0x18003ddf1  mov     qword ptr [rbx+234h], 0
0x18003ddfc  xorps   xmm0, xmm0
0x18003ddff  movups  xmmword ptr [rbx+348h], xmm0
0x18003de06  mov     qword ptr [rbx+340h], 0FFFFFFFF80000002h
0x18003de11  mov     qword ptr [rbx+214h], 0
0x18003de1c  mov     dword ptr [rbx+21Ch], 0
0x18003de26  mov     qword ptr [rbx+338h], 0
0x18003de31  mov     dword ptr [rbx+220h], 2
0x18003de3b  xor     r8d, r8d
0x18003de3e  xor     ecx, ecx
0x18003de40  test    r8d, r8d
0x18003de43  setnz   cl
0x18003de46  lea     rax, [r8+r8*2]
0x18003de4a  mov     [rbx+rax*4+228h], ecx
0x18003de51  mov     ecx, 1
0x18003de56  lock xadd cs:dword_180071170, ecx
0x18003de5e  inc     ecx
0x18003de60  lea     rax, [r8+r8*2]
0x18003de64  mov     [rbx+rax*4+22Ch], ecx
0x18003de6b  inc     r8d
0x18003de6e  cmp     r8d, [rbx+220h]
0x18003de75  jb      short loc_18003DE3E
0x18003de77  lea     rcx, [rbx+2D8h]; Resource
0x18003de7e  call    cs:__imp_RtlInitializeResource
0x18003de84  nop
0x18003de85  lea     rcx, [rsp+68h+var_48]; this
0x18003de8a  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003de8f  add     rsp, 60h
0x18003de93  pop     rbx
0x18003de94  retn
```
