# CKsFilter::RemoveProcessPin(_KSPPROCESSPIN *,IKsPin *)

- ea: `0x18005d530`
- end: `0x18005d75d`
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
- `0x18000fe2c`
- `0x180019c60`
- `0x180019cc0`
- `0x18005d530`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x18005d580`
- `ntoskrnl!KeWaitForSingleObject` at `0x18005d580`

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
        (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids,
        (char)this,
        (char)v3->Pin);
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
        (__int64)WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids,
        (char)this,
        (char)v3->Pin);
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
0x18005d530  push    rbx
0x18005d532  push    rbp
0x18005d533  push    rsi
0x18005d534  push    rdi
0x18005d535  push    r12
0x18005d537  push    r14
0x18005d539  push    r15
0x18005d53b  sub     rsp, 40h
0x18005d53f  mov     r14, rdx
0x18005d542  mov     rsi, rcx
0x18005d545  lea     r15, WPP_RECORDER_INITIALIZED
0x18005d54c  xor     ebp, ebp
0x18005d54e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18005d555  lea     r12, WPP_001f1e784e56319d01cbbdcd1f1acdab_Traceguids
0x18005d55c  jnz     loc_18005D5F4
0x18005d562  cmp     [r14+40h], rbp
0x18005d566  jnz     loc_18005D663
0x18005d56c  lea     rcx, [rsi+290h]; Object
0x18005d573  mov     [rsp+78h+Timeout], rbp; Timeout
0x18005d578  xor     r9d, r9d; Alertable
0x18005d57b  xor     r8d, r8d; WaitMode
0x18005d57e  xor     edx, edx; WaitReason
0x18005d580  call    cs:__imp_KeWaitForSingleObject
0x18005d587  nop     dword ptr [rax+rax+00h]
0x18005d58c  mov     rax, [r14]
0x18005d58f  mov     rdi, [rsi+1F8h]
0x18005d596  mov     ebx, [rax+18h]
0x18005d599  shl     rbx, 4
0x18005d59d  cmp     dword ptr [rax+1Ch], 4
0x18005d5a1  jz      loc_18005D6D6
0x18005d5a7  mov     rcx, [rbx+rdi]; void *
0x18005d5ab  or      r15d, 0FFFFFFFFh
0x18005d5af  mov     eax, [rbx+rdi+8]
0x18005d5b3  test    eax, eax
0x18005d5b5  jz      short loc_18005D5DC
0x18005d5b7  add     eax, r15d
0x18005d5ba  cmp     [rcx], r14
0x18005d5bd  jnz     loc_18005D73F
0x18005d5c3  test    eax, eax
0x18005d5c5  jnz     loc_18005D748
0x18005d5cb  add     [rbx+rdi+8], r15d
0x18005d5d0  mov     ecx, [rbx+rdi+8]
0x18005d5d4  mov     rax, [rbx+rdi]
0x18005d5d8  mov     [rax+rcx*8], rbp
0x18005d5dc  mov     rcx, rsi; this
0x18005d5df  call    ?ReleaseProcessSync@CKsFilter@@QEAAXXZ; CKsFilter::ReleaseProcessSync(void)
0x18005d5e4  add     rsp, 40h
0x18005d5e8  pop     r15
0x18005d5ea  pop     r14
0x18005d5ec  pop     r12
0x18005d5ee  pop     rdi
0x18005d5ef  pop     rsi
0x18005d5f0  pop     rbp
0x18005d5f1  pop     rbx
0x18005d5f2  retn
0x18005d5f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d5fb  cmp     [rcx+48h], bp
0x18005d5ff  jnz     short loc_18005D647
0x18005d601  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18005d608  jz      loc_18005D562
0x18005d60e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d615  cmp     [rcx+48h], bp
0x18005d619  jz      loc_18005D562
0x18005d61f  mov     rax, [r14]
0x18005d622  mov     r9d, 2Fh ; '/'
0x18005d628  mov     rcx, [rcx+40h]
0x18005d62c  mov     dl, 5
0x18005d62e  mov     [rsp+78h+var_48], rax
0x18005d633  mov     [rsp+78h+var_50], rsi
0x18005d638  mov     [rsp+78h+Timeout], r12
0x18005d63d  call    WPP_RECORDER_SF_qq
0x18005d642  jmp     loc_18005D562
0x18005d647  mov     rcx, [rcx+40h]
0x18005d64b  mov     r9d, 2Eh ; '.'
0x18005d651  mov     dl, 5
0x18005d653  mov     [rsp+78h+Timeout], r12
0x18005d658  lea     r8d, [r9-2Dh]
0x18005d65c  call    WPP_RECORDER_SF_
0x18005d661  jmp     short loc_18005D601
0x18005d663  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18005d66a  jz      short loc_18005D69C
0x18005d66c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d673  cmp     [rcx+48h], bp
0x18005d677  jz      short loc_18005D69C
0x18005d679  mov     rax, [r14]
0x18005d67c  mov     r9d, 30h ; '0'
0x18005d682  mov     rcx, [rcx+40h]
0x18005d686  mov     dl, 5
0x18005d688  mov     [rsp+78h+var_48], rax
0x18005d68d  mov     [rsp+78h+var_50], rsi
0x18005d692  mov     [rsp+78h+Timeout], r12
0x18005d697  call    WPP_RECORDER_SF_qq
0x18005d69c  mov     rax, [r14+40h]
0x18005d6a0  xor     r8d, r8d
0x18005d6a3  xor     edx, edx
0x18005d6a5  mov     rcx, [rax+10h]
0x18005d6a9  mov     rax, [rcx]
0x18005d6ac  mov     rax, [rax+18h]
0x18005d6b0  call    _guard_dispatch_icall
0x18005d6b5  mov     rdx, [r14+40h]
0x18005d6b9  test    rdx, rdx
0x18005d6bc  jz      loc_18005D56C
0x18005d6c2  mov     rax, [rsi]
0x18005d6c5  mov     rcx, rsi
0x18005d6c8  mov     rax, [rax+38h]
0x18005d6cc  call    _guard_dispatch_icall
0x18005d6d1  jmp     loc_18005D56C
0x18005d6d6  mov     rax, [rax]
0x18005d6d9  mov     ecx, [rax+70h]
0x18005d6dc  cmp     [rbx+rdi+8], ecx
0x18005d6e0  jnz     loc_18005D5A7
0x18005d6e6  lea     r8, [rsi+258h]
0x18005d6ed  mov     rcx, r8; Gate
0x18005d6f0  call    KsGateTurnInputOff
0x18005d6f5  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18005d6fc  jz      loc_18005D5A7
0x18005d702  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d709  cmp     [rcx+48h], bp
0x18005d70d  jz      loc_18005D5A7
0x18005d713  mov     eax, [r8]
0x18005d716  mov     r9d, 31h ; '1'
0x18005d71c  mov     rcx, [rcx+40h]
0x18005d720  mov     dl, 5
0x18005d722  mov     [rsp+78h+var_40], eax
0x18005d726  mov     [rsp+78h+var_48], r8
0x18005d72b  mov     [rsp+78h+var_50], rsi
0x18005d730  mov     [rsp+78h+Timeout], r12
0x18005d735  call    WPP_RECORDER_SF_qqd
0x18005d73a  jmp     loc_18005D5A7
0x18005d73f  add     rcx, 8
0x18005d743  jmp     loc_18005D5B3
0x18005d748  mov     r8d, eax
0x18005d74b  lea     rdx, [rcx+8]; Src
0x18005d74f  shl     r8, 3; Size
0x18005d753  call    memmove
0x18005d758  jmp     loc_18005D5CB
```
