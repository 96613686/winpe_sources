# RtMgrRoutingDomainConfig::SetLoopbackInterface(ulong,_ICB *)

- ea: `0x180056864`
- end: `0x180056902`
- name: `?SetLoopbackInterface@RtMgrRoutingDomainConfig@@QEAAXKPEAU_ICB@@@Z`
- size: `158`
- prototype: `void __fastcall(struct _GUID *this, unsigned int, struct _ICB *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180056908`

## callees

- `0x180056864`
- `0x180058068`
- `0x180058124`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800568ca`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800568ca`
- `ntdll!RtlReleaseResource` at `0x1800568e5`
- `ntdll!RtlReleaseResource` at `0x1800568e5`

## string_xrefs

- `0x1800568ad`: `RtMgrRoutingDomainConfig::SetLoopbackInterface`

## pseudocode

```c
void __fastcall RtMgrRoutingDomainConfig::SetLoopbackInterface(
        struct _GUID *this,
        int a2,
        struct _ICB *a3,
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
      L"RtMgrRoutingDomainConfig::SetLoopbackInterface",
      (unsigned int *)a3,
      a4,
      this,
      v8,
      v9);
  RtlAcquireResourceExclusive((PRTL_RESOURCE)&this[42], 1u);
  v7 = 552;
  if ( a2 != 33 )
    v7 = 616;
  *(_QWORD *)((char *)&this->Data1 + v7) = a3;
  RtlReleaseResource((PRTL_RESOURCE)&this[42]);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v10);
}

```

## disassembly

```asm
0x180056864  push    rbx
0x180056866  push    rbp
0x180056867  push    rsi
0x180056868  push    rdi
0x180056869  sub     rsp, 88h
0x180056870  mov     rsi, r8
0x180056873  mov     ebp, edx
0x180056875  mov     rdi, rcx
0x180056878  xorps   xmm0, xmm0
0x18005687b  movdqu  [rsp+0A8h+var_60], xmm0
0x180056881  xor     eax, eax
0x180056883  mov     [rsp+0A8h+var_68], rax
0x180056888  movdqu  [rsp+0A8h+var_50], xmm0
0x18005688e  mov     [rsp+0A8h+var_40], rax
0x180056893  mov     [rsp+0A8h+var_38], 0FFFFFFFFh
0x18005689b  mov     [rsp+0A8h+var_34], eax
0x18005689f  cmp     qword ptr cs:xmmword_18008B450+8, rax
0x1800568a6  jz      short loc_1800568BE
0x1800568a8  mov     [rsp+0A8h+var_88], rcx; struct _GUID *
0x1800568ad  lea     rdx, aRtmgrroutingdo; "RtMgrRoutingDomainConfig::SetLoopbackIn"...
0x1800568b4  lea     rcx, [rsp+0A8h+var_68]; this
0x1800568b9  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x1800568be  lea     rbx, [rdi+2A0h]
0x1800568c5  mov     dl, 1; Wait
0x1800568c7  mov     rcx, rbx; Resource
0x1800568ca  call    cs:__imp_RtlAcquireResourceExclusive
0x1800568d0  mov     eax, 228h
0x1800568d5  lea     ecx, [rax+40h]
0x1800568d8  cmp     ebp, 21h ; '!'
0x1800568db  cmovnz  eax, ecx
0x1800568de  mov     [rax+rdi], rsi
0x1800568e2  mov     rcx, rbx; Resource
0x1800568e5  call    cs:__imp_RtlReleaseResource
0x1800568eb  nop
0x1800568ec  lea     rcx, [rsp+0A8h+var_68]; this
0x1800568f1  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x1800568f6  add     rsp, 88h
0x1800568fd  pop     rdi
0x1800568fe  pop     rsi
0x1800568ff  pop     rbp
0x180056900  pop     rbx
0x180056901  retn
```
