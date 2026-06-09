# RtMgrRoutingDomainConfig::SetIpChangeNotificationHandle(ulong,void *)

- ea: `0x1800566e4`
- end: `0x180056782`
- name: `?SetIpChangeNotificationHandle@RtMgrRoutingDomainConfig@@QEAAXKPEAX@Z`
- size: `158`
- prototype: `void __fastcall(struct _GUID *this, unsigned int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180056788`

## callees

- `0x1800566e4`
- `0x180058068`
- `0x180058124`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18005674a`
- `ntdll!RtlAcquireResourceExclusive` at `0x18005674a`
- `ntdll!RtlReleaseResource` at `0x180056765`
- `ntdll!RtlReleaseResource` at `0x180056765`

## string_xrefs

- `0x18005672d`: `RtMgrRoutingDomainConfig::SetIpChangeNotificationHandle`

## pseudocode

```c
void __fastcall RtMgrRoutingDomainConfig::SetIpChangeNotificationHandle(
        struct _GUID *this,
        int a2,
        unsigned int *a3,
        void (*a4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))
{
  __int64 v7; // rax
  unsigned __int16 *v8; // [rsp+28h] [rbp-80h]
  unsigned int v9; // [rsp+30h] [rbp-78h]
  __int64 v10; // [rsp+40h] [rbp-68h] BYREF
  __int128 v11; // [rsp+48h] [rbp-60h]
  __int128 v12; // [rsp+58h] [rbp-50h]
  __int64 v13; // [rsp+68h] [rbp-40h]
  int v14; // [rsp+70h] [rbp-38h]
  int v15; // [rsp+74h] [rbp-34h]

  v11 = 0;
  v10 = 0;
  v12 = 0;
  v13 = 0;
  v14 = -1;
  v15 = 0;
  if ( *((_QWORD *)&xmmword_18008B450 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v10,
      L"RtMgrRoutingDomainConfig::SetIpChangeNotificationHandle",
      a3,
      a4,
      this,
      v8,
      v9);
  RtlAcquireResourceExclusive((PRTL_RESOURCE)&this[42], 1u);
  v7 = 600;
  if ( a2 != 33 )
    v7 = 664;
  *(_QWORD *)((char *)&this->Data1 + v7) = a3;
  RtlReleaseResource((PRTL_RESOURCE)&this[42]);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v10);
}

```

## disassembly

```asm
0x1800566e4  push    rbx
0x1800566e6  push    rbp
0x1800566e7  push    rsi
0x1800566e8  push    rdi
0x1800566e9  sub     rsp, 88h
0x1800566f0  mov     rsi, r8
0x1800566f3  mov     ebp, edx
0x1800566f5  mov     rdi, rcx
0x1800566f8  xorps   xmm0, xmm0
0x1800566fb  movdqu  [rsp+0A8h+var_60], xmm0
0x180056701  xor     eax, eax
0x180056703  mov     [rsp+0A8h+var_68], rax
0x180056708  movdqu  [rsp+0A8h+var_50], xmm0
0x18005670e  mov     [rsp+0A8h+var_40], rax
0x180056713  mov     [rsp+0A8h+var_38], 0FFFFFFFFh
0x18005671b  mov     [rsp+0A8h+var_34], eax
0x18005671f  cmp     qword ptr cs:xmmword_18008B450+8, rax
0x180056726  jz      short loc_18005673E
0x180056728  mov     [rsp+0A8h+var_88], rcx; struct _GUID *
0x18005672d  lea     rdx, aRtmgrroutingdo_3; "RtMgrRoutingDomainConfig::SetIpChangeNo"...
0x180056734  lea     rcx, [rsp+0A8h+var_68]; this
0x180056739  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x18005673e  lea     rbx, [rdi+2A0h]
0x180056745  mov     dl, 1; Wait
0x180056747  mov     rcx, rbx; Resource
0x18005674a  call    cs:__imp_RtlAcquireResourceExclusive
0x180056750  mov     eax, 258h
0x180056755  lea     ecx, [rax+40h]
0x180056758  cmp     ebp, 21h ; '!'
0x18005675b  cmovnz  eax, ecx
0x18005675e  mov     [rax+rdi], rsi
0x180056762  mov     rcx, rbx; Resource
0x180056765  call    cs:__imp_RtlReleaseResource
0x18005676b  nop
0x18005676c  lea     rcx, [rsp+0A8h+var_68]; this
0x180056771  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180056776  add     rsp, 88h
0x18005677d  pop     rdi
0x18005677e  pop     rsi
0x18005677f  pop     rbp
0x180056780  pop     rbx
0x180056781  retn
```
