# TlmInitializeCorrelationVector

- ea: `0x14000a44c`
- end: `0x14000a602`
- name: `TlmInitializeCorrelationVector`
- size: `438`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003cf0`
- `0x14007f6a0`
- `0x1400843f8`

## callees

- `0x140003c50`
- `0x14000a44c`
- `0x14001e140`

## import_xrefs

- `ntoskrnl!RtlInitializeCorrelationVector` at `0x14000a549`
- `ntoskrnl!RtlInitializeCorrelationVector` at `0x14000a549`
- `ntoskrnl!ExUuidCreate` at `0x14000a521`
- `ntoskrnl!ExUuidCreate` at `0x14000a521`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a5d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a5d3`
- `ntoskrnl!ExAllocatePool2` at `0x14000a4f2`
- `ntoskrnl!ExAllocatePool2` at `0x14000a4f2`

## pseudocode

```c
__int64 __fastcall TlmInitializeCorrelationVector(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  __int64 v4; // rdx
  __int64 v6; // r14
  void *Pool2; // rsi
  __int64 v8; // rcx
  UUID Uuid; // [rsp+20h] [rbp-38h] BYREF

  LODWORD(v3) = 0;
  v4 = *(_QWORD *)(a1 + 96);
  Uuid = 0;
  if ( v4 )
  {
    if ( a2 )
    {
      *(_OWORD *)v4 = *(_OWORD *)a2;
      *(_OWORD *)(v4 + 16) = *(_OWORD *)(a2 + 16);
      *(_OWORD *)(v4 + 32) = *(_OWORD *)(a2 + 32);
      *(_OWORD *)(v4 + 48) = *(_OWORD *)(a2 + 48);
      *(_OWORD *)(v4 + 64) = *(_OWORD *)(a2 + 64);
      *(_OWORD *)(v4 + 80) = *(_OWORD *)(a2 + 80);
      *(_OWORD *)(v4 + 96) = *(_OWORD *)(a2 + 96);
      *(_OWORD *)(v4 + 112) = *(_OWORD *)(a2 + 112);
      *(_WORD *)(v4 + 128) = *(_WORD *)(a2 + 128);
    }
  }
  else
  {
    v6 = *(_QWORD *)(a1 + 16);
    Pool2 = (void *)ExAllocatePool2(256, 130, 1984131912);
    if ( Pool2 )
    {
      if ( !a2
        && ((v3 = (unsigned int)ExUuidCreate(&Uuid), HsmDbgBreakOnStatus(v3), (int)v3 < 0)
         || (LODWORD(v3) = RtlInitializeCorrelationVector(Pool2, 2, &Uuid),
             HsmDbgBreakOnStatus((unsigned int)v3),
             (int)v3 < 0))
        || _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 96), (signed __int64)Pool2, 0) )
      {
        ExFreePoolWithTag(Pool2, 0x76437348u);
      }
      else
      {
        if ( a2 )
        {
          v8 = *(_QWORD *)(a1 + 96);
          *(_OWORD *)v8 = *(_OWORD *)a2;
          *(_OWORD *)(v8 + 16) = *(_OWORD *)(a2 + 16);
          *(_OWORD *)(v8 + 32) = *(_OWORD *)(a2 + 32);
          *(_OWORD *)(v8 + 48) = *(_OWORD *)(a2 + 48);
          *(_OWORD *)(v8 + 64) = *(_OWORD *)(a2 + 64);
          *(_OWORD *)(v8 + 80) = *(_OWORD *)(a2 + 80);
          *(_OWORD *)(v8 + 96) = *(_OWORD *)(a2 + 96);
          *(_OWORD *)(v8 + 112) = *(_OWORD *)(a2 + 112);
          *(_WORD *)(v8 + 128) = *(_WORD *)(a2 + 128);
        }
        _InterlockedCompareExchange64((volatile signed __int64 *)(v6 + 104), (signed __int64)Pool2, 0);
      }
    }
    else
    {
      LODWORD(v3) = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000a44c  mov     [rsp+arg_8], rbx
0x14000a451  mov     [rsp+arg_10], rbp
0x14000a456  push    rsi
0x14000a457  push    rdi
0x14000a458  push    r14
0x14000a45a  sub     rsp, 40h
0x14000a45e  mov     rax, cs:__security_cookie
0x14000a465  xor     rax, rsp
0x14000a468  mov     [rsp+58h+var_28], rax
0x14000a46d  mov     rbx, rdx
0x14000a470  xor     edi, edi
0x14000a472  mov     rdx, [rcx+60h]
0x14000a476  xorps   xmm0, xmm0
0x14000a479  mov     rbp, rcx
0x14000a47c  movups  xmmword ptr [rsp+58h+Uuid.Data1], xmm0
0x14000a481  test    rdx, rdx
0x14000a484  jz      short loc_14000A4E0
0x14000a486  test    rbx, rbx
0x14000a489  jz      loc_14000A5DF
0x14000a48f  movups  xmm0, xmmword ptr [rbx]
0x14000a492  movups  xmmword ptr [rdx], xmm0
0x14000a495  movups  xmm1, xmmword ptr [rbx+10h]
0x14000a499  movups  xmmword ptr [rdx+10h], xmm1
0x14000a49d  movups  xmm0, xmmword ptr [rbx+20h]
0x14000a4a1  movups  xmmword ptr [rdx+20h], xmm0
0x14000a4a5  movups  xmm1, xmmword ptr [rbx+30h]
0x14000a4a9  movups  xmmword ptr [rdx+30h], xmm1
0x14000a4ad  movups  xmm0, xmmword ptr [rbx+40h]
0x14000a4b1  movups  xmmword ptr [rdx+40h], xmm0
0x14000a4b5  movups  xmm1, xmmword ptr [rbx+50h]
0x14000a4b9  movups  xmmword ptr [rdx+50h], xmm1
0x14000a4bd  movups  xmm0, xmmword ptr [rbx+60h]
0x14000a4c1  movups  xmmword ptr [rdx+60h], xmm0
0x14000a4c5  movups  xmm1, xmmword ptr [rbx+70h]
0x14000a4c9  movups  xmmword ptr [rdx+70h], xmm1
0x14000a4cd  movzx   eax, word ptr [rbx+80h]
0x14000a4d4  mov     [rdx+80h], ax
0x14000a4db  jmp     loc_14000A5DF
0x14000a4e0  mov     r14, [rcx+10h]
0x14000a4e4  mov     edx, 82h
0x14000a4e9  mov     r8d, 76437348h
0x14000a4ef  lea     ecx, [rdx+7Eh]
0x14000a4f2  call    cs:__imp_ExAllocatePool2
0x14000a4f9  nop     dword ptr [rax+rax+00h]
0x14000a4fe  mov     rsi, rax
0x14000a501  test    rax, rax
0x14000a504  jnz     short loc_14000A517
0x14000a506  mov     edi, 0C000009Ah
0x14000a50b  mov     ecx, edi
0x14000a50d  call    HsmDbgBreakOnStatus
0x14000a512  jmp     loc_14000A5DF
0x14000a517  test    rbx, rbx
0x14000a51a  jnz     short loc_14000A562
0x14000a51c  lea     rcx, [rsp+58h+Uuid]; Uuid
0x14000a521  call    cs:__imp_ExUuidCreate
0x14000a528  nop     dword ptr [rax+rax+00h]
0x14000a52d  mov     ecx, eax
0x14000a52f  mov     edi, eax
0x14000a531  call    HsmDbgBreakOnStatus
0x14000a536  test    edi, edi
0x14000a538  js      loc_14000A5CB
0x14000a53e  lea     r8, [rsp+58h+Uuid]
0x14000a543  mov     rcx, rsi
0x14000a546  lea     edx, [rbx+2]
0x14000a549  call    cs:__imp_RtlInitializeCorrelationVector
0x14000a550  nop     dword ptr [rax+rax+00h]
0x14000a555  mov     ecx, eax
0x14000a557  mov     edi, eax
0x14000a559  call    HsmDbgBreakOnStatus
0x14000a55e  test    edi, edi
0x14000a560  js      short loc_14000A5CB
0x14000a562  xor     eax, eax
0x14000a564  lock cmpxchg [rbp+60h], rsi
0x14000a56a  jnz     short loc_14000A5CB
0x14000a56c  test    rbx, rbx
0x14000a56f  jz      short loc_14000A5C1
0x14000a571  movups  xmm0, xmmword ptr [rbx]
0x14000a574  mov     rcx, [rbp+60h]
0x14000a578  movups  xmmword ptr [rcx], xmm0
0x14000a57b  movups  xmm1, xmmword ptr [rbx+10h]
0x14000a57f  movups  xmmword ptr [rcx+10h], xmm1
0x14000a583  movups  xmm0, xmmword ptr [rbx+20h]
0x14000a587  movups  xmmword ptr [rcx+20h], xmm0
0x14000a58b  movups  xmm1, xmmword ptr [rbx+30h]
0x14000a58f  movups  xmmword ptr [rcx+30h], xmm1
0x14000a593  movups  xmm0, xmmword ptr [rbx+40h]
0x14000a597  movups  xmmword ptr [rcx+40h], xmm0
0x14000a59b  movups  xmm1, xmmword ptr [rbx+50h]
0x14000a59f  movups  xmmword ptr [rcx+50h], xmm1
0x14000a5a3  movups  xmm0, xmmword ptr [rbx+60h]
0x14000a5a7  movups  xmmword ptr [rcx+60h], xmm0
0x14000a5ab  movups  xmm1, xmmword ptr [rbx+70h]
0x14000a5af  movups  xmmword ptr [rcx+70h], xmm1
0x14000a5b3  movzx   eax, word ptr [rbx+80h]
0x14000a5ba  mov     [rcx+80h], ax
0x14000a5c1  xor     eax, eax
0x14000a5c3  lock cmpxchg [r14+68h], rsi
0x14000a5c9  jmp     short loc_14000A5DF
0x14000a5cb  mov     edx, 76437348h; Tag
0x14000a5d0  mov     rcx, rsi; P
0x14000a5d3  call    cs:__imp_ExFreePoolWithTag
0x14000a5da  nop     dword ptr [rax+rax+00h]
0x14000a5df  mov     eax, edi
0x14000a5e1  mov     rcx, [rsp+58h+var_28]
0x14000a5e6  xor     rcx, rsp; StackCookie
0x14000a5e9  call    __security_check_cookie
0x14000a5ee  mov     rbx, [rsp+58h+arg_8]
0x14000a5f3  mov     rbp, [rsp+58h+arg_10]
0x14000a5f8  add     rsp, 40h
0x14000a5fc  pop     r14
0x14000a5fe  pop     rdi
0x14000a5ff  pop     rsi
0x14000a600  retn
```
