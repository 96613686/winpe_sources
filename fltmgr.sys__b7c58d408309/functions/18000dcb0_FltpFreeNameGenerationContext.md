# FltpFreeNameGenerationContext

- ea: `0x18000dcb0`
- end: `0x18000dfe6`
- name: `FltpFreeNameGenerationContext`
- size: `822`
- prototype: `void __fastcall(PVOID Entry)`
- caller_count: `11`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18000dff0`
- `0x18000e2e0`
- `0x180058640`
- `0x18005aa30`
- `0x18005b4b0`
- `0x18005b920`
- `0x18005c8e0`
- `0x18005e010`
- `0x18005e410`
- `0x180065600`
- `0x180065e90`

## callees

- `0x18000dcb0`
- `0x180022a24`
- `0x180024c00`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000dce6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000dfcb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000dce6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000dfcb`
- `ntoskrnl!ExReleaseRundownProtection` at `0x18000dd20`
- `ntoskrnl!ExReleaseRundownProtection` at `0x18000dd5d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x18000dd9b`
- `ntoskrnl!ExReleaseRundownProtection` at `0x18000dd20`
- `ntoskrnl!ExReleaseRundownProtection` at `0x18000dd5d`
- `ntoskrnl!ExReleaseRundownProtection` at `0x18000dd9b`
- `ntoskrnl!RtlWalkFrameChain` at `0x18000de47`
- `ntoskrnl!RtlWalkFrameChain` at `0x18000dec8`
- `ntoskrnl!RtlWalkFrameChain` at `0x18000df49`
- `ntoskrnl!RtlWalkFrameChain` at `0x18000de47`
- `ntoskrnl!RtlWalkFrameChain` at `0x18000dec8`
- `ntoskrnl!RtlWalkFrameChain` at `0x18000df49`

## pseudocode

```c
void __fastcall FltpFreeNameGenerationContext(PVOID Entry)
{
  void *v2; // rcx
  __int64 v3; // rsi
  __int64 v4; // rsi
  __int64 v5; // rsi
  volatile signed __int32 *v6; // rcx
  unsigned __int64 v7; // rdi
  volatile signed __int32 *v8; // rax
  unsigned __int64 v9; // rdi
  volatile signed __int32 *v10; // rcx
  unsigned __int64 v11; // rdi

  if ( (*((_DWORD *)Entry + 10) & 0x200) != 0 )
  {
    v3 = *((_QWORD *)Entry + 1);
    if ( v3 )
    {
      if ( (ExReleaseRundownProtection((PEX_RUNDOWN_REF)(v3 + 8)), (FltGlobals[0] & 0x2000) != 0)
        && (*(_DWORD *)v3 & 0x2000000) != 0
        || (FltGlobals[0] & 0x4000) != 0 && (*(_DWORD *)v3 & 0x4000000) != 0
        || (FltGlobals[0] & 0x8000) != 0 && (*(_DWORD *)v3 & 0x1000000) != 0 )
      {
        v10 = *(volatile signed __int32 **)(v3 + 32);
        if ( v10 )
        {
          v11 = (unsigned __int64)(((unsigned __int16)_InterlockedExchangeAdd(v10, 1u) + 1) & 0x3FF) << 7;
          *(_DWORD *)(v11 + *(_QWORD *)(v3 + 32) + 8) = -1;
          *(_QWORD *)(v11 + *(_QWORD *)(v3 + 32) + 16) = *(_QWORD *)(v3 + 8);
          memset((void *)(v11 + *(_QWORD *)(v3 + 32) + 24LL), 0, 0x70u);
          RtlWalkFrameChain((PVOID *)(v11 + *(_QWORD *)(v3 + 32) + 24LL), 0xEu, 0);
        }
      }
    }
    v4 = *((_QWORD *)Entry + 2);
    if ( v4 )
    {
      if ( (ExReleaseRundownProtection((PEX_RUNDOWN_REF)(v4 + 8)), (FltGlobals[0] & 0x2000) != 0)
        && (*(_DWORD *)v4 & 0x2000000) != 0
        || (FltGlobals[0] & 0x4000) != 0 && (*(_DWORD *)v4 & 0x4000000) != 0
        || (FltGlobals[0] & 0x8000) != 0 && (*(_DWORD *)v4 & 0x1000000) != 0 )
      {
        v6 = *(volatile signed __int32 **)(v4 + 32);
        if ( v6 )
        {
          v7 = (unsigned __int64)(((unsigned __int16)_InterlockedExchangeAdd(v6, 1u) + 1) & 0x3FF) << 7;
          *(_DWORD *)(v7 + *(_QWORD *)(v4 + 32) + 8) = -1;
          *(_QWORD *)(v7 + *(_QWORD *)(v4 + 32) + 16) = *(_QWORD *)(v4 + 8);
          memset((void *)(v7 + *(_QWORD *)(v4 + 32) + 24LL), 0, 0x70u);
          RtlWalkFrameChain((PVOID *)(v7 + *(_QWORD *)(v4 + 32) + 24LL), 0xEu, 0);
        }
      }
    }
    v5 = *((_QWORD *)Entry + 3);
    if ( v5 )
    {
      if ( (ExReleaseRundownProtection((PEX_RUNDOWN_REF)(v5 + 8)), (FltGlobals[0] & 0x2000) != 0)
        && (*(_DWORD *)v5 & 0x2000000) != 0
        || (FltGlobals[0] & 0x4000) != 0 && (*(_DWORD *)v5 & 0x4000000) != 0
        || (FltGlobals[0] & 0x8000) != 0 && (*(_DWORD *)v5 & 0x1000000) != 0 )
      {
        v8 = *(volatile signed __int32 **)(v5 + 32);
        if ( v8 )
        {
          v9 = (unsigned __int64)(((unsigned __int16)_InterlockedExchangeAdd(v8, 1u) + 1) & 0x3FF) << 7;
          *(_DWORD *)(v9 + *(_QWORD *)(v5 + 32) + 8) = -1;
          *(_QWORD *)(v9 + *(_QWORD *)(v5 + 32) + 16) = *(_QWORD *)(v5 + 8);
          memset((void *)(v9 + *(_QWORD *)(v5 + 32) + 24LL), 0, 0x70u);
          RtlWalkFrameChain((PVOID *)(v9 + *(_QWORD *)(v5 + 32) + 24LL), 0xEu, 0);
        }
      }
    }
  }
  if ( (*((_DWORD *)Entry + 10) & 0x800) != 0 )
    ExFreeToNPagedLookasideList(&stru_18003EFC0, *((PVOID *)Entry + 9));
  v2 = (void *)*((_QWORD *)Entry + 4);
  if ( v2 )
    FltpFreeNameSupportVolumeInfo(v2);
  ExFreeToNPagedLookasideList(&stru_18003EEC0, Entry);
}

```

## disassembly

```asm
0x18000dcb0  push    rbx
0x18000dcb2  sub     rsp, 20h
0x18000dcb6  test    dword ptr [rcx+28h], 200h
0x18000dcbd  mov     rbx, rcx
0x18000dcc0  jnz     short loc_18000DCF9
0x18000dcc2  test    dword ptr [rbx+28h], 800h
0x18000dcc9  jnz     loc_18000DFC0
0x18000dccf  mov     rcx, [rbx+20h]; Entry
0x18000dcd3  test    rcx, rcx
0x18000dcd6  jnz     loc_18000DFDC
0x18000dcdc  mov     rdx, rbx; Entry
0x18000dcdf  lea     rcx, stru_18003EEC0; Lookaside
0x18000dce6  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000dced  nop     dword ptr [rax+rax+00h]
0x18000dcf2  add     rsp, 20h
0x18000dcf6  pop     rbx
0x18000dcf7  retn
0x18000dcf9  mov     [rsp+28h+arg_0], rsi
0x18000dcfe  mov     rsi, [rcx+8]
0x18000dd02  mov     [rsp+28h+arg_18], r15
0x18000dd07  mov     r15d, 1
0x18000dd0d  mov     [rsp+28h+arg_8], rdi
0x18000dd12  mov     [rsp+28h+arg_10], r14
0x18000dd17  test    rsi, rsi
0x18000dd1a  jz      short loc_18000DD50
0x18000dd1c  lea     rcx, [rsi+8]; RunRef
0x18000dd20  call    cs:__imp_ExReleaseRundownProtection
0x18000dd27  nop     dword ptr [rax+rax+00h]
0x18000dd2c  mov     ecx, cs:FltGlobals
0x18000dd32  bt      ecx, 0Dh
0x18000dd36  jb      loc_18000DF7C
0x18000dd3c  bt      ecx, 0Eh
0x18000dd40  jb      loc_18000DED9
0x18000dd46  bt      ecx, 0Fh
0x18000dd4a  jb      loc_18000DF8D
0x18000dd50  mov     rsi, [rbx+10h]
0x18000dd54  test    rsi, rsi
0x18000dd57  jz      short loc_18000DD89
0x18000dd59  lea     rcx, [rsi+8]; RunRef
0x18000dd5d  call    cs:__imp_ExReleaseRundownProtection
0x18000dd64  nop     dword ptr [rax+rax+00h]
0x18000dd69  mov     ecx, cs:FltGlobals
0x18000dd6f  bt      ecx, 0Dh
0x18000dd73  jb      loc_18000DF5A
0x18000dd79  bt      ecx, 0Eh
0x18000dd7d  jb      short loc_18000DDDF
0x18000dd7f  bt      ecx, 0Fh
0x18000dd83  jb      loc_18000DF9E
0x18000dd89  mov     rsi, [rbx+18h]
0x18000dd8d  mov     r14, [rsp+28h+arg_10]
0x18000dd92  test    rsi, rsi
0x18000dd95  jz      short loc_18000DDCB
0x18000dd97  lea     rcx, [rsi+8]; RunRef
0x18000dd9b  call    cs:__imp_ExReleaseRundownProtection
0x18000dda2  nop     dword ptr [rax+rax+00h]
0x18000dda7  mov     ecx, cs:FltGlobals
0x18000ddad  bt      ecx, 0Dh
0x18000ddb1  jb      loc_18000DF6B
0x18000ddb7  bt      ecx, 0Eh
0x18000ddbb  jb      loc_18000DE58
0x18000ddc1  bt      ecx, 0Fh
0x18000ddc5  jb      loc_18000DFAF
0x18000ddcb  mov     rdi, [rsp+28h+arg_8]
0x18000ddd0  mov     rsi, [rsp+28h+arg_0]
0x18000ddd5  mov     r15, [rsp+28h+arg_18]
0x18000ddda  jmp     loc_18000DCC2
0x18000dddf  test    dword ptr [rsi], 4000000h
0x18000dde5  jz      short loc_18000DD7F
0x18000dde7  mov     rcx, [rsi+20h]
0x18000ddeb  test    rcx, rcx
0x18000ddee  jz      short loc_18000DD89
0x18000ddf0  mov     edi, r15d
0x18000ddf3  lock xadd [rcx], edi
0x18000ddf7  mov     rax, [rsi+20h]
0x18000ddfb  inc     edi
0x18000ddfd  and     edi, 3FFh
0x18000de03  xor     edx, edx; Val
0x18000de05  shl     rdi, 7
0x18000de09  mov     r8d, 70h ; 'p'; Size
0x18000de0f  mov     dword ptr [rdi+rax+8], 0FFFFFFFFh
0x18000de17  mov     rcx, [rsi+20h]
0x18000de1b  mov     rax, [rsi+8]
0x18000de1f  mov     [rdi+rcx+10h], rax
0x18000de24  mov     rcx, [rsi+20h]
0x18000de28  add     rcx, 18h
0x18000de2c  add     rcx, rdi; void *
0x18000de2f  call    memset
0x18000de34  mov     rcx, [rsi+20h]
0x18000de38  xor     r8d, r8d; Flags
0x18000de3b  add     rcx, 18h
0x18000de3f  mov     edx, 0Eh; Count
0x18000de44  add     rcx, rdi; Callers
0x18000de47  call    cs:__imp_RtlWalkFrameChain
0x18000de4e  nop     dword ptr [rax+rax+00h]
0x18000de53  jmp     loc_18000DD89
0x18000de58  test    dword ptr [rsi], 4000000h
0x18000de5e  jz      loc_18000DDC1
0x18000de64  mov     rax, [rsi+20h]
0x18000de68  test    rax, rax
0x18000de6b  jz      loc_18000DDCB
0x18000de71  lock xadd [rax], r15d
0x18000de76  mov     rax, [rsi+20h]
0x18000de7a  lea     edi, [r15+1]
0x18000de7e  and     edi, 3FFh
0x18000de84  xor     edx, edx; Val
0x18000de86  shl     rdi, 7
0x18000de8a  mov     r8d, 70h ; 'p'; Size
0x18000de90  mov     dword ptr [rdi+rax+8], 0FFFFFFFFh
0x18000de98  mov     rcx, [rsi+20h]
0x18000de9c  mov     rax, [rsi+8]
0x18000dea0  mov     [rdi+rcx+10h], rax
0x18000dea5  mov     rcx, [rsi+20h]
0x18000dea9  add     rcx, 18h
0x18000dead  add     rcx, rdi; void *
0x18000deb0  call    memset
0x18000deb5  mov     rcx, [rsi+20h]
0x18000deb9  xor     r8d, r8d; Flags
0x18000debc  add     rcx, 18h
0x18000dec0  mov     edx, 0Eh; Count
0x18000dec5  add     rcx, rdi; Callers
0x18000dec8  call    cs:__imp_RtlWalkFrameChain
0x18000decf  nop     dword ptr [rax+rax+00h]
0x18000ded4  jmp     loc_18000DDCB
0x18000ded9  test    dword ptr [rsi], 4000000h
0x18000dedf  jz      loc_18000DD46
0x18000dee5  mov     rcx, [rsi+20h]
0x18000dee9  test    rcx, rcx
0x18000deec  jz      loc_18000DD50
0x18000def2  mov     edi, r15d
0x18000def5  lock xadd [rcx], edi
0x18000def9  mov     rax, [rsi+20h]
0x18000defd  inc     edi
0x18000deff  and     edi, 3FFh
0x18000df05  xor     edx, edx; Val
0x18000df07  shl     rdi, 7
0x18000df0b  mov     r8d, 70h ; 'p'; Size
0x18000df11  mov     dword ptr [rdi+rax+8], 0FFFFFFFFh
0x18000df19  mov     rcx, [rsi+20h]
0x18000df1d  mov     rax, [rsi+8]
0x18000df21  mov     [rdi+rcx+10h], rax
0x18000df26  mov     rcx, [rsi+20h]
0x18000df2a  add     rcx, 18h
0x18000df2e  add     rcx, rdi; void *
0x18000df31  call    memset
0x18000df36  mov     rcx, [rsi+20h]
0x18000df3a  xor     r8d, r8d; Flags
0x18000df3d  add     rcx, 18h
0x18000df41  mov     edx, 0Eh; Count
0x18000df46  add     rcx, rdi; Callers
0x18000df49  call    cs:__imp_RtlWalkFrameChain
0x18000df50  nop     dword ptr [rax+rax+00h]
0x18000df55  jmp     loc_18000DD50
0x18000df5a  test    dword ptr [rsi], 2000000h
0x18000df60  jnz     loc_18000DDE7
0x18000df66  jmp     loc_18000DD79
0x18000df6b  test    dword ptr [rsi], 2000000h
0x18000df71  jnz     loc_18000DE64
0x18000df77  jmp     loc_18000DDB7
0x18000df7c  test    dword ptr [rsi], 2000000h
0x18000df82  jnz     loc_18000DEE5
0x18000df88  jmp     loc_18000DD3C
0x18000df8d  test    dword ptr [rsi], 1000000h
0x18000df93  jz      loc_18000DD50
0x18000df99  jmp     loc_18000DEE5
0x18000df9e  test    dword ptr [rsi], 1000000h
0x18000dfa4  jz      loc_18000DD89
0x18000dfaa  jmp     loc_18000DDE7
0x18000dfaf  test    dword ptr [rsi], 1000000h
0x18000dfb5  jz      loc_18000DDCB
0x18000dfbb  jmp     loc_18000DE64
0x18000dfc0  mov     rdx, [rbx+48h]; Entry
0x18000dfc4  lea     rcx, stru_18003EFC0; Lookaside
0x18000dfcb  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000dfd2  nop     dword ptr [rax+rax+00h]
0x18000dfd7  jmp     loc_18000DCCF
0x18000dfdc  call    FltpFreeNameSupportVolumeInfo
0x18000dfe1  jmp     loc_18000DCDC
```
