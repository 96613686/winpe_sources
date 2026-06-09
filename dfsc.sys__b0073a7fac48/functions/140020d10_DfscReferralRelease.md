# DfscReferralRelease

- ea: `0x140020d10`
- end: `0x140020dfb`
- name: `DfscReferralRelease`
- size: `235`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x140002cd0`
- `0x14001109c`
- `0x140011c80`
- `0x140014d30`
- `0x14001520c`
- `0x140015520`
- `0x140015f30`
- `0x140016070`
- `0x14001abc0`
- `0x140020660`
- `0x140021300`
- `0x140021410`
- `0x140021688`
- `0x1400219c0`
- `0x140023120`
- `0x1400281ac`
- `0x1400284a0`

## callees

- `0x1400025f4`
- `0x1400026a4`
- `0x140020d10`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140020d85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020dad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020d85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140020dad`

## pseudocode

```c
void __fastcall DfscReferralRelease(PVOID P)
{
  volatile signed __int32 *v2; // rdi

  if ( P && _InterlockedExchangeAdd((volatile signed __int32 *)P + 1, 0xFFFFFFFF) == 1 )
  {
    v2 = (volatile signed __int32 *)*((_QWORD *)P + 2);
    if ( v2 )
    {
      if ( _InterlockedExchangeAdd(v2 + 1, 0xFFFFFFFF) == 1 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
        {
          WPP_SF_qZ(
            WPP_GLOBAL_Control->AttachedDevice,
            27,
            (unsigned int)WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids,
            (_DWORD)v2,
            (__int64)(v2 + 36));
        }
        ExFreePoolWithTag((PVOID)v2, 0);
      }
      *((_QWORD *)P + 2) = 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_55706db06074317498eaf8c01331c814_Traceguids, P);
    }
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x140020d10  test    rcx, rcx
0x140020d13  jz      short locret_140020D33
0x140020d15  push    rbx
0x140020d16  sub     rsp, 30h
0x140020d1a  mov     rbx, rcx
0x140020d1d  mov     ecx, 0FFFFFFFFh
0x140020d22  mov     eax, ecx
0x140020d24  lock xadd [rbx+4], eax
0x140020d29  cmp     eax, 1
0x140020d2c  jz      short loc_140020D35
0x140020d2e  add     rsp, 30h
0x140020d32  pop     rbx
0x140020d33  retn
0x140020d35  mov     [rsp+38h+arg_0], rsi
0x140020d3a  lea     rsi, WPP_GLOBAL_Control
0x140020d41  mov     [rsp+38h+arg_8], rdi
0x140020d46  mov     rdi, [rbx+10h]
0x140020d4a  test    rdi, rdi
0x140020d4d  jz      short loc_140020D61
0x140020d4f  lock xadd [rdi+4], ecx
0x140020d54  cmp     ecx, 1
0x140020d57  jz      short loc_140020D93
0x140020d59  mov     qword ptr [rbx+10h], 0
0x140020d61  mov     rcx, cs:WPP_GLOBAL_Control
0x140020d68  mov     rdi, [rsp+38h+arg_8]
0x140020d6d  cmp     rcx, rsi
0x140020d70  mov     rsi, [rsp+38h+arg_0]
0x140020d75  jz      short loc_140020D80
0x140020d77  test    dword ptr [rcx+2Ch], 400000h
0x140020d7e  jnz     short loc_140020DE1
0x140020d80  xor     edx, edx; Tag
0x140020d82  mov     rcx, rbx; P
0x140020d85  call    cs:__imp_ExFreePoolWithTag
0x140020d8c  nop     dword ptr [rax+rax+00h]
0x140020d91  jmp     short loc_140020D2E
0x140020d93  mov     rcx, cs:WPP_GLOBAL_Control
0x140020d9a  cmp     rcx, rsi
0x140020d9d  jz      short loc_140020DA8
0x140020d9f  test    dword ptr [rcx+2Ch], 200000h
0x140020da6  jnz     short loc_140020DBB
0x140020da8  xor     edx, edx; Tag
0x140020daa  mov     rcx, rdi; P
0x140020dad  call    cs:__imp_ExFreePoolWithTag
0x140020db4  nop     dword ptr [rax+rax+00h]
0x140020db9  jmp     short loc_140020D59
0x140020dbb  mov     rcx, [rcx+18h]
0x140020dbf  lea     rax, [rdi+90h]
0x140020dc6  mov     edx, 1Bh
0x140020dcb  mov     [rsp+38h+var_18], rax
0x140020dd0  mov     r9, rdi
0x140020dd3  lea     r8, WPP_65d7788e2a383f8eac655d84410cd6ec_Traceguids
0x140020dda  call    WPP_SF_qZ
0x140020ddf  jmp     short loc_140020DA8
0x140020de1  mov     rcx, [rcx+18h]
0x140020de5  lea     r8, WPP_55706db06074317498eaf8c01331c814_Traceguids
0x140020dec  mov     edx, 0Ah
0x140020df1  mov     r9, rbx
0x140020df4  call    WPP_SF_q
0x140020df9  jmp     short loc_140020D80
```
