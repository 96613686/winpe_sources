# RtMgrRoutingDomainConfig::~RtMgrRoutingDomainConfig(void)

- ea: `0x180055404`
- end: `0x180055509`
- name: `??1RtMgrRoutingDomainConfig@@QEAA@XZ`
- size: `261`
- prototype: `void __fastcall(RtMgrRoutingDomainConfig *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800555e8`

## callees

- `0x180055404`
- `0x180058068`
- `0x180058124`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x1800554e3`
- `ntdll!RtlDeleteResource` at `0x1800554e3`
- `KERNEL32!HeapFree` at `0x18005547d`
- `KERNEL32!HeapFree` at `0x1800554bd`
- `KERNEL32!HeapFree` at `0x18005547d`
- `KERNEL32!HeapFree` at `0x1800554bd`

## string_xrefs

- `0x180055453`: `RtMgrRoutingDomainConfig::~RtMgrRoutingDomainConfig`

## pseudocode

```c
void __fastcall RtMgrRoutingDomainConfig::~RtMgrRoutingDomainConfig(
        RtMgrRoutingDomainConfig *this,
        __int64 a2,
        unsigned int *a3,
        void (*a4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))
{
  __int64 v5; // rsi
  __int64 v6; // rbx
  void *v7; // r8
  void *v8; // r8
  unsigned __int16 *v9; // [rsp+28h] [rbp-60h]
  unsigned int v10; // [rsp+30h] [rbp-58h]
  __int64 v11; // [rsp+40h] [rbp-48h] BYREF
  __int128 v12; // [rsp+48h] [rbp-40h]
  __int128 v13; // [rsp+58h] [rbp-30h]
  __int64 v14; // [rsp+68h] [rbp-20h]
  int v15; // [rsp+70h] [rbp-18h]
  int v16; // [rsp+74h] [rbp-14h]

  v12 = 0;
  v11 = 0;
  v13 = 0;
  v14 = 0;
  v15 = -1;
  v16 = 0;
  if ( *((_QWORD *)&xmmword_18008B450 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v11,
      L"RtMgrRoutingDomainConfig::~RtMgrRoutingDomainConfig",
      a3,
      a4,
      (struct _GUID *)this,
      v9,
      v10);
  v5 = 0;
  v6 = 0;
  do
  {
    v7 = *(void **)((char *)this + v6 + 568);
    if ( v7 )
    {
      HeapFree(IPRouterHeap, 0, v7);
      *(_QWORD *)((char *)this + v6 + 568) = 0;
      *(_QWORD *)((char *)this + v6 + 552) = 0;
      *(_QWORD *)((char *)this + v6 + 560) = 0;
    }
    v8 = *(void **)((char *)this + v6 + 584);
    if ( v8 )
    {
      HeapFree(IPRouterHeap, 0, v8);
      *(_QWORD *)((char *)this + v6 + 584) = 0;
    }
    ++v5;
    v6 += 64;
  }
  while ( v5 != 2 );
  RtlDeleteResource((PRTL_RESOURCE)this + 7);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v11);
}

```

## disassembly

```asm
0x180055404  mov     rax, rsp
0x180055407  mov     [rax+8], rbx
0x18005540b  mov     [rax+10h], rsi
0x18005540f  push    rdi
0x180055410  sub     rsp, 80h
0x180055417  mov     rdi, rcx
0x18005541a  xorps   xmm0, xmm0
0x18005541d  movdqu  xmmword ptr [rax-40h], xmm0
0x180055422  mov     qword ptr [rax-48h], 0
0x18005542a  movdqu  xmmword ptr [rax-30h], xmm0
0x18005542f  mov     qword ptr [rax-20h], 0
0x180055437  mov     dword ptr [rax-18h], 0FFFFFFFFh
0x18005543e  mov     dword ptr [rax-14h], 0
0x180055445  cmp     qword ptr cs:xmmword_18008B450+8, 0
0x18005544d  jz      short loc_180055463
0x18005544f  mov     [rax-68h], rcx
0x180055453  lea     rdx, aRtmgrroutingdo_2; "RtMgrRoutingDomainConfig::~RtMgrRouting"...
0x18005545a  lea     rcx, [rax-48h]; this
0x18005545e  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180055463  xor     esi, esi
0x180055465  xor     ebx, ebx
0x180055467  mov     r8, [rdi+rbx+238h]; lpMem
0x18005546f  test    r8, r8
0x180055472  jz      short loc_1800554A7
0x180055474  xor     edx, edx; dwFlags
0x180055476  mov     rcx, cs:?IPRouterHeap@@3PEAXEA; hHeap
0x18005547d  call    cs:__imp_HeapFree
0x180055483  mov     qword ptr [rdi+rbx+238h], 0
0x18005548f  mov     qword ptr [rdi+rbx+228h], 0
0x18005549b  mov     qword ptr [rdi+rbx+230h], 0
0x1800554a7  mov     r8, [rdi+rbx+248h]; lpMem
0x1800554af  test    r8, r8
0x1800554b2  jz      short loc_1800554CF
0x1800554b4  xor     edx, edx; dwFlags
0x1800554b6  mov     rcx, cs:?IPRouterHeap@@3PEAXEA; hHeap
0x1800554bd  call    cs:__imp_HeapFree
0x1800554c3  mov     qword ptr [rdi+rbx+248h], 0
0x1800554cf  inc     rsi
0x1800554d2  add     rbx, 40h ; '@'
0x1800554d6  cmp     rsi, 2
0x1800554da  jnz     short loc_180055467
0x1800554dc  lea     rcx, [rdi+2A0h]; Resource
0x1800554e3  call    cs:__imp_RtlDeleteResource
0x1800554e9  lea     rcx, [rsp+88h+var_48]; this
0x1800554ee  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800554f3  nop
0x1800554f4  lea     r11, [rsp+88h+var_8]
0x1800554fc  mov     rbx, [r11+10h]
0x180055500  mov     rsi, [r11+18h]
0x180055504  mov     rsp, r11
0x180055507  pop     rdi
0x180055508  retn
```
