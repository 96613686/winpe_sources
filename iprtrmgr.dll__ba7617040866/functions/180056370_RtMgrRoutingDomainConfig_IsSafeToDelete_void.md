# RtMgrRoutingDomainConfig::IsSafeToDelete(void)

- ea: `0x180056370`
- end: `0x18005642e`
- name: `?IsSafeToDelete@RtMgrRoutingDomainConfig@@QEAAHXZ`
- size: `190`
- prototype: `__int64 __fastcall(RtMgrRoutingDomainConfig *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180056434`

## callees

- `0x180056370`
- `0x180058068`
- `0x180058124`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180056406`
- `ntdll!RtlReleaseResource` at `0x180056406`
- `ntdll!RtlAcquireResourceShared` at `0x1800563e0`
- `ntdll!RtlAcquireResourceShared` at `0x1800563e0`

## string_xrefs

- `0x1800563c4`: `RtMgrRoutingDomainConfig::IsSafeToDelete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RtMgrRoutingDomainConfig::IsSafeToDelete(
        RtMgrRoutingDomainConfig *this,
        __int64 a2,
        unsigned int *a3,
        void (*a4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))
{
  unsigned int v5; // ebx
  unsigned int i; // ecx
  unsigned __int16 *v8; // [rsp+28h] [rbp-60h]
  unsigned int v9; // [rsp+30h] [rbp-58h]
  __int64 v10; // [rsp+40h] [rbp-48h] BYREF
  __int128 v11; // [rsp+48h] [rbp-40h]
  __int128 v12; // [rsp+58h] [rbp-30h]
  __int64 v13; // [rsp+68h] [rbp-20h]
  int v14; // [rsp+70h] [rbp-18h]
  int v15; // [rsp+74h] [rbp-14h]

  v5 = 1;
  v11 = 0;
  v10 = 0;
  v12 = 0;
  v13 = 0;
  v14 = -1;
  v15 = 0;
  if ( *((_QWORD *)&xmmword_18008B450 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v10,
      L"RtMgrRoutingDomainConfig::IsSafeToDelete",
      a3,
      a4,
      (struct _GUID *)this,
      v8,
      v9);
  RtlAcquireResourceShared((PRTL_RESOURCE)this + 7, 1u);
  for ( i = 0; i < 2; ++i )
  {
    if ( *((_DWORD *)this + 16 * (unsigned __int64)i + 136) )
    {
      v5 = 0;
      break;
    }
  }
  RtlReleaseResource((PRTL_RESOURCE)this + 7);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v10);
  return v5;
}

```

## disassembly

```asm
0x180056370  mov     rax, rsp
0x180056373  mov     [rax+8], rbx
0x180056377  mov     [rax+10h], rsi
0x18005637b  push    rdi
0x18005637c  sub     rsp, 80h
0x180056383  mov     rdi, rcx
0x180056386  mov     ebx, 1
0x18005638b  xorps   xmm0, xmm0
0x18005638e  movdqu  xmmword ptr [rax-40h], xmm0
0x180056393  mov     qword ptr [rax-48h], 0
0x18005639b  movdqu  xmmword ptr [rax-30h], xmm0
0x1800563a0  mov     qword ptr [rax-20h], 0
0x1800563a8  mov     dword ptr [rax-18h], 0FFFFFFFFh
0x1800563af  mov     dword ptr [rax-14h], 0
0x1800563b6  cmp     qword ptr cs:xmmword_18008B450+8, 0
0x1800563be  jz      short loc_1800563D4
0x1800563c0  mov     [rax-68h], rcx
0x1800563c4  lea     rdx, aRtmgrroutingdo_1; "RtMgrRoutingDomainConfig::IsSafeToDelet"...
0x1800563cb  lea     rcx, [rax-48h]; this
0x1800563cf  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x1800563d4  lea     rsi, [rdi+2A0h]
0x1800563db  mov     dl, bl; Wait
0x1800563dd  mov     rcx, rsi; Resource
0x1800563e0  call    cs:__imp_RtlAcquireResourceShared
0x1800563e6  xor     ecx, ecx
0x1800563e8  cmp     ecx, 2
0x1800563eb  jnb     short loc_180056403
0x1800563ed  mov     eax, ecx
0x1800563ef  shl     rax, 6
0x1800563f3  cmp     dword ptr [rax+rdi+220h], 0
0x1800563fb  jnz     short loc_180056401
0x1800563fd  add     ecx, ebx
0x1800563ff  jmp     short loc_1800563E8
0x180056401  xor     ebx, ebx
0x180056403  mov     rcx, rsi; Resource
0x180056406  call    cs:__imp_RtlReleaseResource
0x18005640c  nop
0x18005640d  lea     rcx, [rsp+88h+var_48]; this
0x180056412  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180056417  mov     eax, ebx
0x180056419  lea     r11, [rsp+88h+var_8]
0x180056421  mov     rbx, [r11+10h]
0x180056425  mov     rsi, [r11+18h]
0x180056429  mov     rsp, r11
0x18005642c  pop     rdi
0x18005642d  retn
```
