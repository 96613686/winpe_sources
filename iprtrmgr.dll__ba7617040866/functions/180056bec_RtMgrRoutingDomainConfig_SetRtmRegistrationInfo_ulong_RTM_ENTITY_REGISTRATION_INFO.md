# RtMgrRoutingDomainConfig::SetRtmRegistrationInfo(ulong,_RTM_ENTITY_REGISTRATION_INFO *)

- ea: `0x180056bec`
- end: `0x180056c8a`
- name: `?SetRtmRegistrationInfo@RtMgrRoutingDomainConfig@@QEAAXKPEAU_RTM_ENTITY_REGISTRATION_INFO@@@Z`
- size: `158`
- prototype: `void __fastcall(struct _GUID *this, unsigned int, struct _RTM_ENTITY_REGISTRATION_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800569e4`

## callees

- `0x180056bec`
- `0x180058068`
- `0x180058124`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180056c52`
- `ntdll!RtlAcquireResourceExclusive` at `0x180056c52`
- `ntdll!RtlReleaseResource` at `0x180056c6d`
- `ntdll!RtlReleaseResource` at `0x180056c6d`

## string_xrefs

- `0x180056c35`: `RtMgrRoutingDomainConfig::SetRtmRegistrationInfo`

## pseudocode

```c
void __fastcall RtMgrRoutingDomainConfig::SetRtmRegistrationInfo(
        struct _GUID *this,
        int a2,
        struct _RTM_ENTITY_REGISTRATION_INFO *a3,
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
      L"RtMgrRoutingDomainConfig::SetRtmRegistrationInfo",
      (unsigned int *)a3,
      a4,
      this,
      v8,
      v9);
  RtlAcquireResourceExclusive((PRTL_RESOURCE)&this[42], 1u);
  v7 = 568;
  if ( a2 != 33 )
    v7 = 632;
  *(_QWORD *)((char *)&this->Data1 + v7) = a3;
  RtlReleaseResource((PRTL_RESOURCE)&this[42]);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v10);
}

```

## disassembly

```asm
0x180056bec  push    rbx
0x180056bee  push    rbp
0x180056bef  push    rsi
0x180056bf0  push    rdi
0x180056bf1  sub     rsp, 88h
0x180056bf8  mov     rsi, r8
0x180056bfb  mov     ebp, edx
0x180056bfd  mov     rdi, rcx
0x180056c00  xorps   xmm0, xmm0
0x180056c03  movdqu  [rsp+0A8h+var_60], xmm0
0x180056c09  xor     eax, eax
0x180056c0b  mov     [rsp+0A8h+var_68], rax
0x180056c10  movdqu  [rsp+0A8h+var_50], xmm0
0x180056c16  mov     [rsp+0A8h+var_40], rax
0x180056c1b  mov     [rsp+0A8h+var_38], 0FFFFFFFFh
0x180056c23  mov     [rsp+0A8h+var_34], eax
0x180056c27  cmp     qword ptr cs:xmmword_18008B450+8, rax
0x180056c2e  jz      short loc_180056C46
0x180056c30  mov     [rsp+0A8h+var_88], rcx; struct _GUID *
0x180056c35  lea     rdx, aRtmgrroutingdo_8; "RtMgrRoutingDomainConfig::SetRtmRegistr"...
0x180056c3c  lea     rcx, [rsp+0A8h+var_68]; this
0x180056c41  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180056c46  lea     rbx, [rdi+2A0h]
0x180056c4d  mov     dl, 1; Wait
0x180056c4f  mov     rcx, rbx; Resource
0x180056c52  call    cs:__imp_RtlAcquireResourceExclusive
0x180056c58  mov     eax, 238h
0x180056c5d  lea     ecx, [rax+40h]
0x180056c60  cmp     ebp, 21h ; '!'
0x180056c63  cmovnz  eax, ecx
0x180056c66  mov     [rax+rdi], rsi
0x180056c6a  mov     rcx, rbx; Resource
0x180056c6d  call    cs:__imp_RtlReleaseResource
0x180056c73  nop
0x180056c74  lea     rcx, [rsp+0A8h+var_68]; this
0x180056c79  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180056c7e  add     rsp, 88h
0x180056c85  pop     rdi
0x180056c86  pop     rsi
0x180056c87  pop     rbp
0x180056c88  pop     rbx
0x180056c89  retn
```
