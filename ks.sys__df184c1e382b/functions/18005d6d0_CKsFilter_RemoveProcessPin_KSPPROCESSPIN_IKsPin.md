# CKsFilter::RemoveProcessPin(_KSPPROCESSPIN *,IKsPin *)

- ea: `0x18005d6d0`
- end: `0x18005d8fd`
- name: `?RemoveProcessPin@CKsFilter@@UEAAXPEAU_KSPPROCESSPIN@@PEAUIKsPin@@@Z`
- size: `557`
- prototype: `void __fastcall(CKsFilter *__hidden this, struct _KSPPROCESSPIN *, struct IKsPin *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000513c`
- `0x180005550`
- `0x18000b7bc`
- `0x18000da50`
- `0x18000fe40`
- `0x180019cb0`
- `0x180019d00`
- `0x18005d6d0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x18005d720`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005d720`

## pseudocode

```c
void __fastcall CKsFilter::RemoveProcessPin(CKsFilter *this, struct _KSPPROCESSPIN *a2, struct IKsPin *a3)
{
  struct _KSPPROCESSPIN *v3; // r14
  _KSPPROCESSPIN_INDEXENTRY *m_ProcessPinsIndex; // rdi
  __int64 Id; // rbx
  _KSPPROCESSPIN **Pins; // rcx
  unsigned int Count; // eax
  int v9; // edx
  _DWORD *v10; // r8

  v3 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        1,
        46,
        (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_qq(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        (_DWORD)a3,
        47,
        (char)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids,
        (char)this);
    }
  }
  if ( v3->PipeSection )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(a2) = 5;
      WPP_RECORDER_SF_qq(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)a2,
        (_DWORD)a3,
        48,
        (char)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids,
        (char)this);
    }
    v3->PipeSection->PipeSection->SetDeviceState(v3->PipeSection->PipeSection, 0, KSSTATE_STOP);
    if ( v3->PipeSection )
      ((void (__fastcall *)(CKsFilter *))this->UnbindProcessPinsFromPipeSection)(this);
  }
  KeWaitForSingleObject(&this->m_Mutex, Executive, 0, 0, 0);
  m_ProcessPinsIndex = this->m_ProcessPinsIndex;
  Id = v3->Pin->Id;
  if ( v3->Pin->Communication == KSPIN_COMMUNICATION_BRIDGE
    && m_ProcessPinsIndex[Id].Count == v3->Pin->Descriptor->InstancesNecessary )
  {
    KsGateTurnInputOff(&this->m_AndGate);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LOBYTE(v9) = 5;
        WPP_RECORDER_SF_qqd(
          WPP_GLOBAL_Control->DeviceExtension,
          v9,
          (_DWORD)v10,
          49,
          (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids,
          (char)this,
          (char)v10,
          *v10);
      }
    }
  }
  Pins = m_ProcessPinsIndex[Id].Pins;
  Count = m_ProcessPinsIndex[Id].Count;
  while ( Count )
  {
    --Count;
    if ( *Pins == v3 )
    {
      if ( Count )
        memmove(Pins, Pins + 1, 8LL * Count);
      m_ProcessPinsIndex[Id].Pins[--m_ProcessPinsIndex[Id].Count] = 0;
      break;
    }
    ++Pins;
  }
  CKsFilter::ReleaseProcessSync(this);
}

```

## disassembly

```asm
0x18005d6d0  push    rbx
0x18005d6d2  push    rbp
0x18005d6d3  push    rsi
0x18005d6d4  push    rdi
0x18005d6d5  push    r12
0x18005d6d7  push    r14
0x18005d6d9  push    r15
0x18005d6db  sub     rsp, 40h
0x18005d6df  mov     r14, rdx
0x18005d6e2  mov     rsi, rcx
0x18005d6e5  lea     r15, WPP_RECORDER_INITIALIZED
0x18005d6ec  xor     ebp, ebp
0x18005d6ee  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18005d6f5  lea     r12, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x18005d6fc  jnz     loc_18005D794
0x18005d702  cmp     [r14+40h], rbp
0x18005d706  jnz     loc_18005D803
0x18005d70c  lea     rcx, [rsi+290h]; Object
0x18005d713  mov     [rsp+78h+Timeout], rbp; Timeout
0x18005d718  xor     r9d, r9d; Alertable
0x18005d71b  xor     r8d, r8d; WaitMode
0x18005d71e  xor     edx, edx; WaitReason
0x18005d720  call    cs:__imp_KeWaitForSingleObject
0x18005d727  nop     dword ptr [rax+rax+00h]
0x18005d72c  mov     rax, [r14]
0x18005d72f  mov     rdi, [rsi+1F8h]
0x18005d736  mov     ebx, [rax+18h]
0x18005d739  shl     rbx, 4
0x18005d73d  cmp     dword ptr [rax+1Ch], 4
0x18005d741  jz      loc_18005D876
0x18005d747  mov     rcx, [rbx+rdi]; void *
0x18005d74b  or      r15d, 0FFFFFFFFh
0x18005d74f  mov     eax, [rbx+rdi+8]
0x18005d753  test    eax, eax
0x18005d755  jz      short loc_18005D77C
0x18005d757  add     eax, r15d
0x18005d75a  cmp     [rcx], r14
0x18005d75d  jnz     loc_18005D8DF
0x18005d763  test    eax, eax
0x18005d765  jnz     loc_18005D8E8
0x18005d76b  add     [rbx+rdi+8], r15d
0x18005d770  mov     ecx, [rbx+rdi+8]
0x18005d774  mov     rax, [rbx+rdi]
0x18005d778  mov     [rax+rcx*8], rbp
0x18005d77c  mov     rcx, rsi; this
0x18005d77f  call    ?ReleaseProcessSync@CKsFilter@@QEAAXXZ; CKsFilter::ReleaseProcessSync(void)
0x18005d784  add     rsp, 40h
0x18005d788  pop     r15
0x18005d78a  pop     r14
0x18005d78c  pop     r12
0x18005d78e  pop     rdi
0x18005d78f  pop     rsi
0x18005d790  pop     rbp
0x18005d791  pop     rbx
0x18005d792  retn
0x18005d794  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d79b  cmp     [rcx+48h], bp
0x18005d79f  jnz     short loc_18005D7E7
0x18005d7a1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18005d7a8  jz      loc_18005D702
0x18005d7ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d7b5  cmp     [rcx+48h], bp
0x18005d7b9  jz      loc_18005D702
0x18005d7bf  mov     rax, [r14]
0x18005d7c2  mov     r9d, 2Fh ; '/'
0x18005d7c8  mov     rcx, [rcx+40h]
0x18005d7cc  mov     dl, 5
0x18005d7ce  mov     [rsp+78h+var_48], rax
0x18005d7d3  mov     [rsp+78h+var_50], rsi
0x18005d7d8  mov     [rsp+78h+Timeout], r12
0x18005d7dd  call    WPP_RECORDER_SF_qq
0x18005d7e2  jmp     loc_18005D702
0x18005d7e7  mov     rcx, [rcx+40h]
0x18005d7eb  mov     r9d, 2Eh ; '.'
0x18005d7f1  mov     dl, 5
0x18005d7f3  mov     [rsp+78h+Timeout], r12
0x18005d7f8  lea     r8d, [r9-2Dh]
0x18005d7fc  call    WPP_RECORDER_SF_
0x18005d801  jmp     short loc_18005D7A1
0x18005d803  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18005d80a  jz      short loc_18005D83C
0x18005d80c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d813  cmp     [rcx+48h], bp
0x18005d817  jz      short loc_18005D83C
0x18005d819  mov     rax, [r14]
0x18005d81c  mov     r9d, 30h ; '0'
0x18005d822  mov     rcx, [rcx+40h]
0x18005d826  mov     dl, 5
0x18005d828  mov     [rsp+78h+var_48], rax
0x18005d82d  mov     [rsp+78h+var_50], rsi
0x18005d832  mov     [rsp+78h+Timeout], r12
0x18005d837  call    WPP_RECORDER_SF_qq
0x18005d83c  mov     rax, [r14+40h]
0x18005d840  xor     r8d, r8d
0x18005d843  xor     edx, edx
0x18005d845  mov     rcx, [rax+10h]
0x18005d849  mov     rax, [rcx]
0x18005d84c  mov     rax, [rax+18h]
0x18005d850  call    _guard_dispatch_icall
0x18005d855  mov     rdx, [r14+40h]
0x18005d859  test    rdx, rdx
0x18005d85c  jz      loc_18005D70C
0x18005d862  mov     rax, [rsi]
0x18005d865  mov     rcx, rsi
0x18005d868  mov     rax, [rax+38h]
0x18005d86c  call    _guard_dispatch_icall
0x18005d871  jmp     loc_18005D70C
0x18005d876  mov     rax, [rax]
0x18005d879  mov     ecx, [rax+70h]
0x18005d87c  cmp     [rbx+rdi+8], ecx
0x18005d880  jnz     loc_18005D747
0x18005d886  lea     r8, [rsi+258h]
0x18005d88d  mov     rcx, r8; Gate
0x18005d890  call    KsGateTurnInputOff
0x18005d895  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18005d89c  jz      loc_18005D747
0x18005d8a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d8a9  cmp     [rcx+48h], bp
0x18005d8ad  jz      loc_18005D747
0x18005d8b3  mov     eax, [r8]
0x18005d8b6  mov     r9d, 31h ; '1'
0x18005d8bc  mov     rcx, [rcx+40h]
0x18005d8c0  mov     dl, 5
0x18005d8c2  mov     [rsp+78h+var_40], eax
0x18005d8c6  mov     [rsp+78h+var_48], r8
0x18005d8cb  mov     [rsp+78h+var_50], rsi
0x18005d8d0  mov     [rsp+78h+Timeout], r12
0x18005d8d5  call    WPP_RECORDER_SF_qqd
0x18005d8da  jmp     loc_18005D747
0x18005d8df  add     rcx, 8
0x18005d8e3  jmp     loc_18005D753
0x18005d8e8  mov     r8d, eax
0x18005d8eb  lea     rdx, [rcx+8]; Src
0x18005d8ef  shl     r8, 3; Size
0x18005d8f3  call    memmove
0x18005d8f8  jmp     loc_18005D76B
```
