# MRxSmbBuildReadRequest

- ea: `0x14003b980`
- end: `0x14003bb4e`
- name: `MRxSmbBuildReadRequest`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14003bd40`

## callees

- `0x14000b9c0`
- `0x14003b980`
- `0x140046380`
- `0x14004a590`

## import_xrefs

- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14003bb27`

## pseudocode

```c
__int64 __fastcall MRxSmbBuildReadRequest(__int64 a1)
{
  __int64 v1; // r15
  __int64 ExchangeNetRoot; // rax
  __int64 v4; // rcx
  __int64 v5; // rsi
  __int64 v6; // rbp
  __int64 v7; // rdi
  unsigned int v8; // ecx
  unsigned int v9; // eax
  unsigned int v10; // r12d
  int v11; // r14d
  __int64 result; // rax
  __int64 v13; // [rsp+20h] [rbp-98h]

  v1 = *(_QWORD *)(a1 + 80);
  ExchangeNetRoot = SmbCeGetExchangeNetRoot();
  v5 = *(_QWORD *)(v4 + 24);
  v6 = v4 + 888;
  v7 = *(_QWORD *)(*(_QWORD *)(v5 + 64) + 32LL);
  if ( v7 )
    v7 = *(_QWORD *)(v7 + 48);
  v8 = *(_DWORD *)(ExchangeNetRoot + 8);
  v9 = *(_DWORD *)(a1 + 488);
  v10 = *(_DWORD *)(a1 + 504);
  if ( v9 >= v8 )
    v9 = v8;
  *(_DWORD *)(a1 + 496) = v9;
  v11 = *(_DWORD *)(v1 + 420) & 0x10;
  result = MRxSmbStartSMBCommand(v6, 2, v11 != 0 ? 46 : 10, v11 != 0 ? 27 : 13, v13, 0);
  if ( !(_DWORD)result )
  {
    if ( v11 )
    {
      if ( (*(_DWORD *)(v1 + 420) & 0x40000) != 0 && (*(_DWORD *)(v5 + 536) & 1) != 0 )
        *(_WORD *)(*(_QWORD *)(v6 + 32) + 10LL) |= 0x2000u;
      MRxSmbStuffSMB(v6, (__int64)"XwdwWdw", *(unsigned __int16 *)(v7 + 8), v10);
    }
    else
    {
      MRxSmbStuffSMB(v6, (__int64)"0wwdwB!", *(unsigned __int16 *)(v7 + 8), *(unsigned int *)(a1 + 496));
    }
    _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 8)
                                                    + MRxSmbLegacyPerfCtrs
                                                    + 116));
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14003b980  push    rbx
0x14003b982  push    rbp
0x14003b983  push    rsi
0x14003b984  push    rdi
0x14003b985  push    r12
0x14003b987  push    r13
0x14003b989  push    r14
0x14003b98b  push    r15
0x14003b98d  sub     rsp, 78h
0x14003b991  mov     r15, [rcx+50h]
0x14003b995  mov     rbx, rcx
0x14003b998  call    SmbCeGetExchangeNetRoot
0x14003b99d  mov     rsi, [rcx+18h]
0x14003b9a1  lea     rbp, [rcx+378h]
0x14003b9a8  mov     rdx, [rsi+48h]
0x14003b9ac  mov     r13, [rdx+28h]
0x14003b9b0  mov     rdx, [rsi+40h]
0x14003b9b4  mov     rdi, [rdx+20h]
0x14003b9b8  test    rdi, rdi
0x14003b9bb  jz      short loc_14003B9C1
0x14003b9bd  mov     rdi, [rdi+30h]
0x14003b9c1  mov     ecx, [rax+8]
0x14003b9c4  mov     edx, 2
0x14003b9c9  mov     eax, [rbx+1E8h]
0x14003b9cf  cmp     eax, ecx
0x14003b9d1  mov     r12d, [rbx+1F8h]
0x14003b9d8  cmovnb  eax, ecx
0x14003b9db  mov     [rsp+0B8h+var_90], 0
0x14003b9e3  mov     [rbx+1F0h], eax
0x14003b9e9  mov     rcx, rbp
0x14003b9ec  mov     eax, [rbx+1FCh]
0x14003b9f2  mov     r14d, [r15+1A4h]
0x14003b9f9  mov     [rsp+0B8h+arg_0], eax
0x14003ba00  and     r14d, 10h
0x14003ba04  mov     eax, r14d
0x14003ba07  neg     eax
0x14003ba09  mov     eax, r14d
0x14003ba0c  sbb     r9d, r9d
0x14003ba0f  and     r9d, 0Eh
0x14003ba13  add     r9d, 0Dh
0x14003ba17  neg     eax
0x14003ba19  sbb     r8b, r8b
0x14003ba1c  and     r8b, 24h
0x14003ba20  add     r8b, 0Ah
0x14003ba24  call    MRxSmbStartSMBCommand
0x14003ba29  test    eax, eax
0x14003ba2b  jnz     loc_14003BB3C
0x14003ba31  lea     r10d, [rax+1]
0x14003ba35  test    r14d, r14d
0x14003ba38  jz      loc_14003BAEA
0x14003ba3e  mov     rcx, [r13+20h]
0x14003ba42  or      r9d, 0FFFFFFFFh
0x14003ba46  cmp     [rcx+4Dh], r10b
0x14003ba4a  cmovnz  r9d, eax
0x14003ba4e  test    dword ptr [r15+1A4h], 40000h
0x14003ba59  jnz     short loc_14003BA60
0x14003ba5b  mov     ecx, r10d
0x14003ba5e  jmp     short loc_14003BA7C
0x14003ba60  mov     eax, [rsi+218h]
0x14003ba66  xor     ecx, ecx
0x14003ba68  test    r10b, al
0x14003ba6b  jz      short loc_14003BA7C
0x14003ba6d  mov     rax, [rbp+20h]
0x14003ba71  mov     ecx, 2000h
0x14003ba76  or      [rax+0Ah], cx
0x14003ba7a  xor     ecx, ecx
0x14003ba7c  mov     edx, [rbx+1F0h]
0x14003ba82  lea     eax, [rcx+1]
0x14003ba85  movzx   r8d, word ptr [rdi+8]
0x14003ba8a  lea     rcx, aB; "B!"
0x14003ba91  mov     [rsp+0B8h+var_50], 0
0x14003ba9a  mov     [rsp+0B8h+var_58], rcx
0x14003ba9f  mov     ecx, [rsp+0B8h+arg_0]
0x14003baa6  mov     [rsp+0B8h+var_60], r10d
0x14003baab  mov     [rsp+0B8h+var_68], ecx
0x14003baaf  lea     rcx, aD; "D"
0x14003bab6  mov     [rsp+0B8h+var_70], rcx
0x14003babb  mov     rcx, rbp
0x14003babe  mov     [rsp+0B8h+var_78], eax
0x14003bac2  mov     eax, [rbx+1E8h]
0x14003bac8  mov     [rsp+0B8h+var_80], eax
0x14003bacc  mov     dword ptr [rsp+0B8h+var_88], r9d
0x14003bad1  mov     r9d, r12d
0x14003bad4  mov     [rsp+0B8h+var_90], edx
0x14003bad8  mov     dword ptr [rsp+0B8h+var_98], edx
0x14003badc  lea     rdx, aXwdwwdw; "XwdwWdw"
0x14003bae3  call    MRxSmbStuffSMB
0x14003bae8  jmp     short loc_14003BB1D
0x14003baea  mov     eax, [rbx+1E8h]
0x14003baf0  lea     rdx, a0wwdwb; "0wwdwB!"
0x14003baf7  movzx   r8d, word ptr [rdi+8]
0x14003bafc  mov     rcx, rbp
0x14003baff  mov     r9d, [rbx+1F0h]
0x14003bb06  mov     [rsp+0B8h+var_88], 0
0x14003bb0f  mov     [rsp+0B8h+var_90], eax
0x14003bb13  mov     dword ptr [rsp+0B8h+var_98], r12d
0x14003bb18  call    MRxSmbStuffSMB
0x14003bb1d  mov     eax, gs:1A4h
0x14003bb25  mov     edx, eax
0x14003bb27  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x14003bb2e  shl     rdx, 8
0x14003bb32  mov     rcx, [rax]
0x14003bb35  lock inc dword ptr [rdx+rcx+74h]
0x14003bb3a  xor     eax, eax
0x14003bb3c  add     rsp, 78h
0x14003bb40  pop     r15
0x14003bb42  pop     r14
0x14003bb44  pop     r13
0x14003bb46  pop     r12
0x14003bb48  pop     rdi
0x14003bb49  pop     rsi
0x14003bb4a  pop     rbp
0x14003bb4b  pop     rbx
0x14003bb4c  retn
```
