# RtMgrRoutingDomainConfig::EnableOrDisableTransport(ulong,int)

- ea: `0x180055ab8`
- end: `0x180055b55`
- name: `?EnableOrDisableTransport@RtMgrRoutingDomainConfig@@QEAAXKH@Z`
- size: `157`
- prototype: `void __fastcall(struct _GUID *this, unsigned int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180055654`
- `0x180056434`

## callees

- `0x180055ab8`
- `0x180058068`
- `0x180058124`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180055b1e`
- `ntdll!RtlAcquireResourceExclusive` at `0x180055b1e`
- `ntdll!RtlReleaseResource` at `0x180055b38`
- `ntdll!RtlReleaseResource` at `0x180055b38`

## string_xrefs

- `0x180055b01`: `RtMgrRoutingDomainConfig::EnableOrDisableTransport`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RtMgrRoutingDomainConfig::EnableOrDisableTransport(
        struct _GUID *this,
        int a2,
        unsigned int *a3,
        void (*a4)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))
{
  unsigned int v4; // esi
  __int64 v7; // rax
  unsigned __int16 *v8; // [rsp+28h] [rbp-80h]
  unsigned int v9; // [rsp+30h] [rbp-78h]
  __int64 v10; // [rsp+40h] [rbp-68h] BYREF
  __int128 v11; // [rsp+48h] [rbp-60h]
  __int128 v12; // [rsp+58h] [rbp-50h]
  __int64 v13; // [rsp+68h] [rbp-40h]
  int v14; // [rsp+70h] [rbp-38h]
  int v15; // [rsp+74h] [rbp-34h]

  v4 = (unsigned int)a3;
  v11 = 0;
  v10 = 0;
  v12 = 0;
  v13 = 0;
  v14 = -1;
  v15 = 0;
  if ( *((_QWORD *)&xmmword_18008B450 + 1) )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v10,
      L"RtMgrRoutingDomainConfig::EnableOrDisableTransport",
      a3,
      a4,
      this,
      v8,
      v9);
  RtlAcquireResourceExclusive((PRTL_RESOURCE)&this[42], 1u);
  v7 = 34;
  if ( a2 != 33 )
    v7 = 38;
  this[v7].Data1 = v4;
  RtlReleaseResource((PRTL_RESOURCE)&this[42]);
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v10);
}

```

## disassembly

```asm
0x180055ab8  push    rbx
0x180055aba  push    rbp
0x180055abb  push    rsi
0x180055abc  push    rdi
0x180055abd  sub     rsp, 88h
0x180055ac4  mov     esi, r8d
0x180055ac7  mov     ebp, edx
0x180055ac9  mov     rdi, rcx
0x180055acc  xorps   xmm0, xmm0
0x180055acf  movdqu  [rsp+0A8h+var_60], xmm0
0x180055ad5  xor     eax, eax
0x180055ad7  mov     [rsp+0A8h+var_68], rax
0x180055adc  movdqu  [rsp+0A8h+var_50], xmm0
0x180055ae2  mov     [rsp+0A8h+var_40], rax
0x180055ae7  mov     [rsp+0A8h+var_38], 0FFFFFFFFh
0x180055aef  mov     [rsp+0A8h+var_34], eax
0x180055af3  cmp     qword ptr cs:xmmword_18008B450+8, rax
0x180055afa  jz      short loc_180055B12
0x180055afc  mov     [rsp+0A8h+var_88], rcx; struct _GUID *
0x180055b01  lea     rdx, aRtmgrroutingdo_4; "RtMgrRoutingDomainConfig::EnableOrDisab"...
0x180055b08  lea     rcx, [rsp+0A8h+var_68]; this
0x180055b0d  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z30K@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),_GUID *,ushort *,ulong)
0x180055b12  lea     rbx, [rdi+2A0h]
0x180055b19  mov     dl, 1; Wait
0x180055b1b  mov     rcx, rbx; Resource
0x180055b1e  call    cs:__imp_RtlAcquireResourceExclusive
0x180055b24  mov     eax, 220h
0x180055b29  lea     ecx, [rax+40h]
0x180055b2c  cmp     ebp, 21h ; '!'
0x180055b2f  cmovnz  eax, ecx
0x180055b32  mov     [rax+rdi], esi
0x180055b35  mov     rcx, rbx; Resource
0x180055b38  call    cs:__imp_RtlReleaseResource
0x180055b3e  nop
0x180055b3f  lea     rcx, [rsp+0A8h+var_68]; this
0x180055b44  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180055b49  add     rsp, 88h
0x180055b50  pop     rdi
0x180055b51  pop     rsi
0x180055b52  pop     rbp
0x180055b53  pop     rbx
0x180055b54  retn
```
