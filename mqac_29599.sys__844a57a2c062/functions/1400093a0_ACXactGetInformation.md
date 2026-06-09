# ACXactGetInformation

- ea: `0x1400093a0`
- end: `0x140009499`
- name: `ACXactGetInformation`
- size: `249`
- prototype: `__int64 __fastcall(struct CQueueBase *, volatile void *Address)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140001010`
- `0x140003d84`
- `0x1400093a0`
- `0x14000b5d8`
- `0x14001a564`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x1400093f3`
- `ntoskrnl!ProbeForWrite` at `0x1400093f3`

## pseudocode

```c
__int64 __fastcall ACXactGetInformation(struct CQueueBase *a1, _DWORD *Address)
{
  int v4; // eax
  unsigned int v5; // esi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 184, &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a1);
  }
  ProbeForWrite(Address, 8u, 1u);
  v4 = CQueueBase::Validate(a1);
  v5 = v4;
  if ( v4 >= 0 )
  {
    Address[1] = *((_DWORD *)a1 + 23);
    *Address = *((_DWORD *)a1 + 22);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_Dq(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        185,
        &WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
        (unsigned int)v4,
        a1);
    }
    return v5;
  }
}

```

## disassembly

```asm
0x1400093a0  mov     [rsp+arg_0], rcx
0x1400093a5  push    rbx
0x1400093a6  push    rsi
0x1400093a7  push    rdi
0x1400093a8  push    r14
0x1400093aa  sub     rsp, 38h
0x1400093ae  mov     rdi, rdx
0x1400093b1  mov     rbx, rcx
0x1400093b4  lea     r14, WPP_GLOBAL_Control
0x1400093bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400093c2  cmp     rcx, r14
0x1400093c5  jz      short loc_1400093E7
0x1400093c7  mov     eax, [rcx+6Ch]
0x1400093ca  test    al, 4
0x1400093cc  jz      short loc_1400093E7
0x1400093ce  mov     edx, 0B8h
0x1400093d3  mov     r9, rbx
0x1400093d6  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400093dd  mov     rcx, [rcx+58h]
0x1400093e1  call    WPP_SF_q
0x1400093e6  nop
0x1400093e7  mov     edx, 8; Length
0x1400093ec  lea     r8d, [rdx-7]; Alignment
0x1400093f0  mov     rcx, rdi; Address
0x1400093f3  call    cs:__imp_ProbeForWrite
0x1400093fa  nop     dword ptr [rax+rax+00h]
0x1400093ff  mov     rcx, rbx; struct CQueueBase *
0x140009402  call    ?Validate@CQueueBase@@SAJPEBV1@@Z; CQueueBase::Validate(CQueueBase const *)
0x140009407  mov     esi, eax
0x140009409  test    eax, eax
0x14000940b  jns     short loc_140009442
0x14000940d  mov     rcx, cs:WPP_GLOBAL_Control
0x140009414  cmp     rcx, r14
0x140009417  jz      short loc_14000943E
0x140009419  mov     edx, [rcx+6Ch]
0x14000941c  test    dl, 1
0x14000941f  jz      short loc_14000943E
0x140009421  mov     edx, 0B9h
0x140009426  mov     [rsp+58h+var_38], rbx
0x14000942b  mov     r9d, eax
0x14000942e  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140009435  mov     rcx, [rcx+58h]
0x140009439  call    WPP_SF_Dq
0x14000943e  mov     eax, esi
0x140009440  jmp     short loc_14000948E
0x140009442  mov     eax, [rbx+5Ch]
0x140009445  mov     [rdi+4], eax
0x140009448  mov     eax, [rbx+58h]
0x14000944b  mov     [rdi], eax
0x14000944d  xor     eax, eax
0x14000944f  jmp     short loc_14000948E
0x140009451  mov     ebx, eax
0x140009453  lea     rax, WPP_GLOBAL_Control
0x14000945a  mov     rcx, cs:WPP_GLOBAL_Control
0x140009461  cmp     rcx, rax
0x140009464  jz      short loc_14000948C
0x140009466  mov     edx, [rcx+6Ch]
0x140009469  test    dl, 1
0x14000946c  jz      short loc_14000948C
0x14000946e  mov     edx, 0BAh
0x140009473  mov     dword ptr [rsp+58h+var_38], ebx
0x140009477  mov     r9, [rsp+58h+arg_0]
0x14000947c  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140009483  mov     rcx, [rcx+58h]
0x140009487  call    WPP_SF_qD
0x14000948c  mov     eax, ebx
0x14000948e  add     rsp, 38h
0x140009492  pop     r14
0x140009494  pop     rdi
0x140009495  pop     rsi
0x140009496  pop     rbx
0x140009497  retn
```
