# DiscpFilterV4Create

- ea: `0x1800165c4`
- end: `0x18001677a`
- name: `DiscpFilterV4Create`
- size: `438`
- prototype: `__int64 __fastcall(char, unsigned int, unsigned int, unsigned int, unsigned int, __int16, __int16, char, int, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180016230`

## callees

- `0x180001cfe`
- `0x180015918`
- `0x180016060`
- `0x1800165c4`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x180016605`
- `ISCSIUM!DiscpAllocMemory` at `0x180016605`
- `ISCSIUM!DiscpFreeMemory` at `0x180016763`
- `ISCSIUM!DiscpFreeMemory` at `0x180016763`
- `RPCRT4!UuidCreate` at `0x18001662b`
- `RPCRT4!UuidCreate` at `0x18001662b`

## pseudocode

```c
__int64 __fastcall DiscpFilterV4Create(
        char a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        __int16 a6,
        __int16 a7,
        char a8,
        int a9,
        _QWORD *a10)
{
  _QWORD *v10; // r14
  char *v15; // rax
  char *v16; // rbx
  unsigned int v17; // edi
  RPC_STATUS v18; // eax
  GUID v19; // xmm0
  GUID v20; // xmm0
  unsigned int v22; // [rsp+30h] [rbp-68h]
  __int64 v23[9]; // [rsp+50h] [rbp-48h] BYREF

  v10 = a10;
  a9 = 0;
  v23[0] = 0;
  *a10 = 0;
  v15 = (char *)DiscpAllocMemory(200);
  v16 = v15;
  if ( v15 )
  {
    memset_0(v15, 0, 0xC8u);
    v18 = UuidCreate((UUID *)v16);
    v17 = v18;
    if ( v18 )
      goto LABEL_24;
    *((_QWORD *)v16 + 19) = 0;
    *((_DWORD *)v16 + 24) = 0;
    if ( (a1 & 4) != 0 )
    {
      v18 = 1;
      *((GUID *)v16 + 4) = FWPM_LAYER_IKEEXT_V4;
    }
    if ( (a1 & 8) != 0 )
    {
      v19 = FWPM_LAYER_IPSEC_V4;
    }
    else
    {
      if ( v18 )
        goto LABEL_13;
      if ( (a1 & 1) != 0 )
        v19 = FWPM_LAYER_INBOUND_TRANSPORT_V4;
      else
        v19 = FWPM_LAYER_OUTBOUND_TRANSPORT_V4;
    }
    *((GUID *)v16 + 4) = v19;
LABEL_13:
    if ( (a1 & 0x10) != 0 )
      *((_DWORD *)v16 + 32) = 4097;
    if ( (a1 & 0x40) != 0 )
      *((_DWORD *)v16 + 32) = 4098;
    if ( (a1 & 0x20) != 0 )
    {
      *((_DWORD *)v16 + 32) = 20483;
      if ( (a1 & 1) != 0 )
        v20 = FWPM_CALLOUT_IPSEC_INBOUND_TRANSPORT_V4;
      else
        v20 = FWPM_CALLOUT_IPSEC_OUTBOUND_TRANSPORT_V4;
      *(GUID *)(v16 + 132) = v20;
    }
    LOWORD(v22) = a7;
    v17 = DiscpFilterCondition5TupleV4Create(a1, a2, a3, a4, a5, a6, v22, a8, v23, &a9);
    if ( !v17 )
    {
      *((_DWORD *)v16 + 28) = a9;
      *((_QWORD *)v16 + 15) = v23[0];
      *v10 = v16;
      return v17;
    }
LABEL_24:
    DiscpFilterConditionDestroy((_QWORD *)v16 + 15, (_DWORD *)v16 + 28);
    DiscpFreeMemory(v16);
    return v17;
  }
  return 8;
}

```

## disassembly

```asm
0x1800165c4  mov     rax, rsp
0x1800165c7  push    rbx
0x1800165c8  push    rbp
0x1800165c9  push    rsi
0x1800165ca  push    rdi
0x1800165cb  push    r12
0x1800165cd  push    r14
0x1800165cf  push    r15
0x1800165d1  sub     rsp, 60h
0x1800165d5  mov     r14, [rsp+98h+arg_48]
0x1800165dd  mov     esi, ecx
0x1800165df  mov     edi, 0C8h
0x1800165e4  mov     dword ptr [rax+48h], 0
0x1800165eb  mov     ecx, edi
0x1800165ed  mov     qword ptr [rax-48h], 0
0x1800165f5  mov     ebp, r9d
0x1800165f8  mov     r15d, r8d
0x1800165fb  mov     qword ptr [r14], 0
0x180016602  mov     r12d, edx
0x180016605  call    cs:__imp_DiscpAllocMemory
0x18001660b  mov     rbx, rax
0x18001660e  test    rax, rax
0x180016611  jnz     short loc_18001661B
0x180016613  lea     edi, [rax+8]
0x180016616  jmp     loc_180016769
0x18001661b  mov     r8, rdi; Size
0x18001661e  xor     edx, edx; Val
0x180016620  mov     rcx, rbx; void *
0x180016623  call    memset_0
0x180016628  mov     rcx, rbx; Uuid
0x18001662b  call    cs:__imp_UuidCreate
0x180016631  mov     edi, eax
0x180016633  test    eax, eax
0x180016635  jnz     loc_180016753
0x18001663b  mov     qword ptr [rbx+98h], 0
0x180016646  mov     [rbx+60h], eax
0x180016649  test    sil, 4
0x18001664d  jz      short loc_18001665E
0x18001664f  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IKEEXT_V4.Data1
0x180016656  lea     eax, [rdi+1]
0x180016659  movdqu  xmmword ptr [rbx+40h], xmm0
0x18001665e  mov     edi, 8
0x180016663  test    dil, sil
0x180016666  jz      short loc_180016671
0x180016668  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPSEC_V4.Data1
0x18001666f  jmp     short loc_18001668B
0x180016671  test    eax, eax
0x180016673  jnz     short loc_180016690
0x180016675  test    sil, 1
0x180016679  jz      short loc_180016684
0x18001667b  movups  xmm0, xmmword ptr cs:FWPM_LAYER_INBOUND_TRANSPORT_V4.Data1
0x180016682  jmp     short loc_18001668B
0x180016684  movups  xmm0, xmmword ptr cs:FWPM_LAYER_OUTBOUND_TRANSPORT_V4.Data1
0x18001668b  movdqu  xmmword ptr [rbx+40h], xmm0
0x180016690  test    sil, 10h
0x180016694  jz      short loc_1800166A0
0x180016696  mov     dword ptr [rbx+80h], 1001h
0x1800166a0  test    sil, 40h
0x1800166a4  jz      short loc_1800166B0
0x1800166a6  mov     dword ptr [rbx+80h], 1002h
0x1800166b0  test    sil, 20h
0x1800166b4  jz      short loc_1800166DE
0x1800166b6  mov     dword ptr [rbx+80h], 5003h
0x1800166c0  test    sil, 1
0x1800166c4  jz      short loc_1800166CF
0x1800166c6  movups  xmm0, xmmword ptr cs:FWPM_CALLOUT_IPSEC_INBOUND_TRANSPORT_V4.Data1
0x1800166cd  jmp     short loc_1800166D6
0x1800166cf  movups  xmm0, xmmword ptr cs:FWPM_CALLOUT_IPSEC_OUTBOUND_TRANSPORT_V4.Data1
0x1800166d6  movdqu  xmmword ptr [rbx+84h], xmm0
0x1800166de  lea     rax, [rsp+98h+arg_40]
0x1800166e6  mov     r9d, ebp
0x1800166e9  mov     [rsp+98h+var_50], rax
0x1800166ee  mov     r8d, r15d
0x1800166f1  lea     rax, [rsp+98h+var_48]
0x1800166f6  mov     edx, r12d
0x1800166f9  mov     [rsp+98h+var_58], rax
0x1800166fe  mov     ecx, esi
0x180016700  mov     al, [rsp+98h+arg_38]
0x180016707  mov     [rsp+98h+var_60], al
0x18001670b  movzx   eax, [rsp+98h+arg_30]
0x180016713  mov     [rsp+98h+var_68], ax
0x180016718  movzx   eax, [rsp+98h+arg_28]
0x180016720  mov     [rsp+98h+var_70], ax
0x180016725  mov     eax, [rsp+98h+arg_20]
0x18001672c  mov     [rsp+98h+var_78], eax
0x180016730  call    DiscpFilterCondition5TupleV4Create
0x180016735  mov     edi, eax
0x180016737  test    eax, eax
0x180016739  jnz     short loc_180016753
0x18001673b  mov     ecx, [rsp+98h+arg_40]
0x180016742  mov     [rbx+70h], ecx
0x180016745  mov     rcx, [rsp+98h+var_48]
0x18001674a  mov     [rbx+78h], rcx
0x18001674e  mov     [r14], rbx
0x180016751  jmp     short loc_180016769
0x180016753  lea     rdx, [rbx+70h]
0x180016757  lea     rcx, [rbx+78h]
0x18001675b  call    DiscpFilterConditionDestroy
0x180016760  mov     rcx, rbx
0x180016763  call    cs:__imp_DiscpFreeMemory
0x180016769  mov     eax, edi
0x18001676b  add     rsp, 60h
0x18001676f  pop     r15
0x180016771  pop     r14
0x180016773  pop     r12
0x180016775  pop     rdi
0x180016776  pop     rsi
0x180016777  pop     rbp
0x180016778  pop     rbx
0x180016779  retn
```
