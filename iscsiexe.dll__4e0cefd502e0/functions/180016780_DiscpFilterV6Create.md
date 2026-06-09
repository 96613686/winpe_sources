# DiscpFilterV6Create

- ea: `0x180016780`
- end: `0x18001692b`
- name: `DiscpFilterV6Create`
- size: `427`
- prototype: `__int64 __fastcall(char, _QWORD *, __int64, _QWORD *, __int64, __int16, __int16, char, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180016400`

## callees

- `0x180001cfe`
- `0x180015c9c`
- `0x180016060`
- `0x180016780`

## import_xrefs

- `ISCSIUM!DiscpAllocMemory` at `0x1800167c0`
- `ISCSIUM!DiscpAllocMemory` at `0x1800167c0`
- `ISCSIUM!DiscpFreeMemory` at `0x180016916`
- `ISCSIUM!DiscpFreeMemory` at `0x180016916`
- `RPCRT4!UuidCreate` at `0x1800167e6`
- `RPCRT4!UuidCreate` at `0x1800167e6`

## pseudocode

```c
__int64 __fastcall DiscpFilterV6Create(
        char a1,
        _QWORD *a2,
        __int64 a3,
        _QWORD *a4,
        __int64 a5,
        __int16 a6,
        __int16 a7,
        char a8,
        __int64 a9,
        _QWORD *a10)
{
  _QWORD *v10; // r14
  char *v14; // rax
  char *v15; // rbx
  unsigned int v16; // edi
  RPC_STATUS v17; // eax
  __int64 v18; // r8
  GUID v19; // xmm0
  GUID v20; // xmm0
  int v22; // [rsp+20h] [rbp-68h]
  int v23; // [rsp+A0h] [rbp+18h] BYREF

  v10 = a10;
  v23 = 0;
  a9 = 0;
  *a10 = 0;
  v14 = (char *)DiscpAllocMemory(200);
  v15 = v14;
  if ( v14 )
  {
    memset_0(v14, 0, 0xC8u);
    v17 = UuidCreate((UUID *)v15);
    v16 = v17;
    if ( v17 )
      goto LABEL_24;
    *((_QWORD *)v15 + 19) = 0;
    *((_DWORD *)v15 + 24) = 0;
    if ( (a1 & 4) != 0 )
    {
      v17 = 1;
      *((GUID *)v15 + 4) = FWPM_LAYER_IKEEXT_V6;
    }
    if ( (a1 & 8) != 0 )
    {
      v19 = FWPM_LAYER_IPSEC_V6;
    }
    else
    {
      if ( v17 )
        goto LABEL_13;
      if ( (a1 & 1) != 0 )
        v19 = FWPM_LAYER_INBOUND_TRANSPORT_V6;
      else
        v19 = FWPM_LAYER_OUTBOUND_TRANSPORT_V6;
    }
    *((GUID *)v15 + 4) = v19;
LABEL_13:
    if ( (a1 & 0x10) != 0 )
      *((_DWORD *)v15 + 32) = 4097;
    if ( (a1 & 0x40) != 0 )
      *((_DWORD *)v15 + 32) = 4098;
    if ( (a1 & 0x20) != 0 )
    {
      *((_DWORD *)v15 + 32) = 20483;
      if ( (a1 & 1) != 0 )
        v20 = FWPM_CALLOUT_IPSEC_INBOUND_TRANSPORT_V6;
      else
        v20 = FWPM_CALLOUT_IPSEC_OUTBOUND_TRANSPORT_V6;
      *(GUID *)(v15 + 132) = v20;
    }
    v16 = DiscpFilterCondition5TupleV6Create(a1, a2, v18, a4, v22, a6, a7, a8, &a9, &v23);
    if ( !v16 )
    {
      *((_DWORD *)v15 + 28) = v23;
      *((_QWORD *)v15 + 15) = a9;
      *v10 = v15;
      return v16;
    }
LABEL_24:
    DiscpFilterConditionDestroy((_QWORD *)v15 + 15, (_DWORD *)v15 + 28);
    DiscpFreeMemory(v15);
    return v16;
  }
  return 8;
}

```

## disassembly

```asm
0x180016780  mov     rax, rsp
0x180016783  mov     [rax+18h], r8b
0x180016787  push    rbx
0x180016788  push    rbp
0x180016789  push    rsi
0x18001678a  push    rdi
0x18001678b  push    r14
0x18001678d  push    r15
0x18001678f  sub     rsp, 58h
0x180016793  mov     r14, [rsp+88h+arg_48]
0x18001679b  mov     esi, ecx
0x18001679d  mov     edi, 0C8h
0x1800167a2  mov     dword ptr [rax+18h], 0
0x1800167a9  mov     ecx, edi
0x1800167ab  mov     qword ptr [rax+48h], 0
0x1800167b3  mov     rbp, r9
0x1800167b6  mov     r15, rdx
0x1800167b9  mov     qword ptr [r14], 0
0x1800167c0  call    cs:__imp_DiscpAllocMemory
0x1800167c6  mov     rbx, rax
0x1800167c9  test    rax, rax
0x1800167cc  jnz     short loc_1800167D6
0x1800167ce  lea     edi, [rax+8]
0x1800167d1  jmp     loc_18001691C
0x1800167d6  mov     r8, rdi; Size
0x1800167d9  xor     edx, edx; Val
0x1800167db  mov     rcx, rbx; void *
0x1800167de  call    memset_0
0x1800167e3  mov     rcx, rbx; Uuid
0x1800167e6  call    cs:__imp_UuidCreate
0x1800167ec  mov     edi, eax
0x1800167ee  test    eax, eax
0x1800167f0  jnz     loc_180016906
0x1800167f6  mov     qword ptr [rbx+98h], 0
0x180016801  mov     [rbx+60h], eax
0x180016804  test    sil, 4
0x180016808  jz      short loc_180016819
0x18001680a  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IKEEXT_V6.Data1
0x180016811  lea     eax, [rdi+1]
0x180016814  movdqu  xmmword ptr [rbx+40h], xmm0
0x180016819  mov     edi, 8
0x18001681e  test    dil, sil
0x180016821  jz      short loc_18001682C
0x180016823  movups  xmm0, xmmword ptr cs:FWPM_LAYER_IPSEC_V6.Data1
0x18001682a  jmp     short loc_180016846
0x18001682c  test    eax, eax
0x18001682e  jnz     short loc_18001684B
0x180016830  test    sil, 1
0x180016834  jz      short loc_18001683F
0x180016836  movups  xmm0, xmmword ptr cs:FWPM_LAYER_INBOUND_TRANSPORT_V6.Data1
0x18001683d  jmp     short loc_180016846
0x18001683f  movups  xmm0, xmmword ptr cs:FWPM_LAYER_OUTBOUND_TRANSPORT_V6.Data1
0x180016846  movdqu  xmmword ptr [rbx+40h], xmm0
0x18001684b  test    sil, 10h
0x18001684f  jz      short loc_18001685B
0x180016851  mov     dword ptr [rbx+80h], 1001h
0x18001685b  test    sil, 40h
0x18001685f  jz      short loc_18001686B
0x180016861  mov     dword ptr [rbx+80h], 1002h
0x18001686b  test    sil, 20h
0x18001686f  jz      short loc_180016899
0x180016871  mov     dword ptr [rbx+80h], 5003h
0x18001687b  test    sil, 1
0x18001687f  jz      short loc_18001688A
0x180016881  movups  xmm0, xmmword ptr cs:FWPM_CALLOUT_IPSEC_INBOUND_TRANSPORT_V6.Data1
0x180016888  jmp     short loc_180016891
0x18001688a  movups  xmm0, xmmword ptr cs:FWPM_CALLOUT_IPSEC_OUTBOUND_TRANSPORT_V6.Data1
0x180016891  movdqu  xmmword ptr [rbx+84h], xmm0
0x180016899  lea     rax, [rsp+88h+arg_10]
0x1800168a1  mov     r9, rbp
0x1800168a4  mov     [rsp+88h+var_40], rax
0x1800168a9  mov     rdx, r15
0x1800168ac  lea     rax, [rsp+88h+arg_40]
0x1800168b4  mov     ecx, esi
0x1800168b6  mov     [rsp+88h+var_48], rax
0x1800168bb  mov     al, [rsp+88h+arg_38]
0x1800168c2  mov     [rsp+88h+var_50], al
0x1800168c6  movzx   eax, [rsp+88h+arg_30]
0x1800168ce  mov     [rsp+88h+var_58], ax
0x1800168d3  movzx   eax, [rsp+88h+arg_28]
0x1800168db  mov     [rsp+88h+var_60], ax
0x1800168e0  call    DiscpFilterCondition5TupleV6Create
0x1800168e5  mov     edi, eax
0x1800168e7  test    eax, eax
0x1800168e9  jnz     short loc_180016906
0x1800168eb  mov     ecx, [rsp+88h+arg_10]
0x1800168f2  mov     [rbx+70h], ecx
0x1800168f5  mov     rcx, [rsp+88h+arg_40]
0x1800168fd  mov     [rbx+78h], rcx
0x180016901  mov     [r14], rbx
0x180016904  jmp     short loc_18001691C
0x180016906  lea     rdx, [rbx+70h]
0x18001690a  lea     rcx, [rbx+78h]
0x18001690e  call    DiscpFilterConditionDestroy
0x180016913  mov     rcx, rbx
0x180016916  call    cs:__imp_DiscpFreeMemory
0x18001691c  mov     eax, edi
0x18001691e  add     rsp, 58h
0x180016922  pop     r15
0x180016924  pop     r14
0x180016926  pop     rdi
0x180016927  pop     rsi
0x180016928  pop     rbp
0x180016929  pop     rbx
0x18001692a  retn
```
