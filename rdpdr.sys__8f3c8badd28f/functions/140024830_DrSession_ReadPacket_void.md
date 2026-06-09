# DrSession::ReadPacket(void)

- ea: `0x140024830`
- end: `0x140024a47`
- name: `?ReadPacket@DrSession@@AEAAXXZ`
- size: `535`
- prototype: `void __fastcall(DrSession *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14001bf2c`
- `0x140024360`

## callees

- `0x140001660`
- `0x140001890`
- `0x1400018a0`
- `0x140003188`
- `0x14000324c`
- `0x14000327c`
- `0x140006560`
- `0x1400111d0`
- `0x140024830`
- `0x140025480`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14002483f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002483f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140024854`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140024854`

## pseudocode

```c
void __fastcall DrSession::ReadPacket(DrSession *this)
{
  RefCount *v2; // rsi
  int v3; // r14d
  RefCount *v4; // r15
  RefCount **v5; // rax
  RefCount **v6; // rdi
  __int64 v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // edx
  int v10; // r14d

  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite((PERESOURCE)((char *)this + 480), 1u);
  v2 = (RefCount *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    RefCount::AddRef(v2);
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 58) + 32LL))((char *)this + 464);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_5c887063686c325024567ba4647d07cf_Traceguids);
    RefCount::AddRef(this);
    v3 = *((_DWORD *)this + 154);
    v4 = (RefCount *)*((_QWORD *)this + 76);
    *((_DWORD *)this + 186) = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_8ecd16b07aab3e5d2130d6f744ebb8b4_Traceguids);
    v5 = (RefCount **)operator new(0x30u, 0x40u);
    v6 = v5;
    if ( !v5 )
      goto LABEL_16;
    *v5 = v2;
    RefCount::AddRef(v2);
    v6[2] = this;
    v6[1] = (RefCount *)DrSession::ReadCompletionRoutine;
    v6[3] = v4;
    *((_DWORD *)v6 + 8) = v3;
    *(RefCount **)((char *)v6 + 36) = (RefCount *)3;
    *((_DWORD *)v6 + 11) = 0;
    v8 = TSAddWorkItemToQueue(v7, v6, VirtualChannel::IoWorker);
    v10 = v8;
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_8ecd16b07aab3e5d2130d6f744ebb8b4_Traceguids, v8);
      tagCHANNELCLOSECONTEXT::`scalar deleting destructor'(v6, v9);
      if ( v10 < 0 )
      {
LABEL_16:
        RefCount::Release(this);
        DrSession::ChannelIoFailed(this);
      }
    }
    RefCount::Release(v2);
  }
  else
  {
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 58) + 32LL))((char *)this + 464);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_5c887063686c325024567ba4647d07cf_Traceguids);
  }
}

```

## disassembly

```asm
0x140024830  mov     [rsp+arg_18], rbx
0x140024835  push    rbp
0x140024836  push    rsi
0x140024837  push    rdi
0x140024838  sub     rsp, 20h
0x14002483c  mov     rbx, rcx
0x14002483f  call    cs:__imp_KeEnterCriticalRegion
0x140024846  nop     dword ptr [rax+rax+00h]
0x14002484b  lea     rcx, [rbx+1E0h]; Resource
0x140024852  mov     dl, 1; Wait
0x140024854  call    cs:__imp_ExAcquireResourceSharedLite
0x14002485b  nop     dword ptr [rax+rax+00h]
0x140024860  mov     rsi, [rbx+28h]
0x140024864  test    rsi, rsi
0x140024867  jz      loc_140024994
0x14002486d  mov     [rsp+38h+arg_0], r12
0x140024872  mov     rcx, rsi; this
0x140024875  mov     [rsp+38h+arg_8], r14
0x14002487a  mov     [rsp+38h+arg_10], r15
0x14002487f  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x140024884  mov     rax, [rbx+1D0h]
0x14002488b  lea     rcx, [rbx+1D0h]
0x140024892  mov     rax, [rax+20h]
0x140024896  call    _guard_dispatch_icall
0x14002489b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400248a2  lea     rbp, WPP_GLOBAL_Control
0x1400248a9  cmp     rcx, rbp
0x1400248ac  jnz     loc_140024970
0x1400248b2  mov     rcx, rbx; this
0x1400248b5  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x1400248ba  mov     r14d, [rbx+268h]
0x1400248c1  xor     r12d, r12d
0x1400248c4  mov     r15, [rbx+260h]
0x1400248cb  mov     [rbx+2E8h], r12d
0x1400248d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400248d9  cmp     rcx, rbp
0x1400248dc  jz      short loc_1400248E8
0x1400248de  cmp     byte ptr [rcx+29h], 4
0x1400248e2  jnb     loc_140024A01
0x1400248e8  mov     edx, 40h ; '@'; unsigned __int64
0x1400248ed  mov     ecx, 30h ; '0'; unsigned __int64
0x1400248f2  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x1400248f7  mov     rdi, rax
0x1400248fa  test    rax, rax
0x1400248fd  jz      loc_1400249EC
0x140024903  mov     rcx, rsi; this
0x140024906  mov     [rax], rsi
0x140024909  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14002490e  lea     rax, ?ReadCompletionRoutine@DrSession@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; DrSession::ReadCompletionRoutine(_DEVICE_OBJECT *,_IRP *,void *)
0x140024915  mov     [rdi+10h], rbx
0x140024919  lea     r8, ?IoWorker@VirtualChannel@@CAXPEAU_DEVICE_OBJECT@@PEAX@Z; VirtualChannel::IoWorker(_DEVICE_OBJECT *,void *)
0x140024920  mov     [rdi+8], rax
0x140024924  mov     rdx, rdi
0x140024927  mov     [rdi+18h], r15
0x14002492b  mov     [rdi+20h], r14d
0x14002492f  mov     qword ptr [rdi+24h], 3
0x140024937  mov     [rdi+2Ch], r12d
0x14002493b  call    TSAddWorkItemToQueue
0x140024940  mov     r14d, eax
0x140024943  test    eax, eax
0x140024945  jnz     loc_140024A1B
0x14002494b  mov     rcx, rsi; this
0x14002494e  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140024953  mov     r15, [rsp+38h+arg_10]
0x140024958  mov     r14, [rsp+38h+arg_8]
0x14002495d  mov     r12, [rsp+38h+arg_0]
0x140024962  mov     rbx, [rsp+38h+arg_18]
0x140024967  add     rsp, 20h
0x14002496b  pop     rdi
0x14002496c  pop     rsi
0x14002496d  pop     rbp
0x14002496e  retn
0x140024970  cmp     byte ptr [rcx+29h], 5
0x140024974  jb      loc_1400248B2
0x14002497a  mov     rcx, [rcx+18h]
0x14002497e  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140024985  mov     edx, 3Ch ; '<'
0x14002498a  call    WPP_SF_
0x14002498f  jmp     loc_1400248B2
0x140024994  mov     rax, [rbx+1D0h]
0x14002499b  lea     rcx, [rbx+1D0h]
0x1400249a2  mov     rax, [rax+20h]
0x1400249a6  call    _guard_dispatch_icall
0x1400249ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400249b2  lea     rbp, WPP_GLOBAL_Control
0x1400249b9  cmp     rcx, rbp
0x1400249bc  jz      short loc_140024962
0x1400249be  cmp     byte ptr [rcx+29h], 4
0x1400249c2  jb      short loc_140024962
0x1400249c4  mov     rcx, [rcx+18h]
0x1400249c8  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x1400249cf  mov     edx, 3Dh ; '='
0x1400249d4  call    WPP_SF_
0x1400249d9  jmp     short loc_140024962
0x1400249db  mov     rcx, rdi; P
0x1400249de  call    ??_GtagCHANNELCLOSECONTEXT@@QEAAPEAXI@Z; tagCHANNELCLOSECONTEXT::`scalar deleting destructor'(uint)
0x1400249e3  test    r14d, r14d
0x1400249e6  jns     loc_14002494B
0x1400249ec  mov     rcx, rbx; this
0x1400249ef  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x1400249f4  mov     rcx, rbx; this
0x1400249f7  call    ?ChannelIoFailed@DrSession@@AEAAXXZ; DrSession::ChannelIoFailed(void)
0x1400249fc  jmp     loc_14002494B
0x140024a01  mov     rcx, [rcx+18h]
0x140024a05  lea     r8, WPP_8ecd16b07aab3e5d2130d6f744ebb8b4_Traceguids
0x140024a0c  mov     edx, 0Ah
0x140024a11  call    WPP_SF_
0x140024a16  jmp     loc_1400248E8
0x140024a1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140024a22  cmp     rcx, rbp
0x140024a25  jz      short loc_1400249DB
0x140024a27  cmp     byte ptr [rcx+29h], 2
0x140024a2b  jb      short loc_1400249DB
0x140024a2d  mov     rcx, [rcx+18h]
0x140024a31  lea     r8, WPP_8ecd16b07aab3e5d2130d6f744ebb8b4_Traceguids
0x140024a38  mov     edx, 0Bh
0x140024a3d  mov     r9d, r14d
0x140024a40  call    WPP_SF_d
0x140024a45  jmp     short loc_1400249DB
```
