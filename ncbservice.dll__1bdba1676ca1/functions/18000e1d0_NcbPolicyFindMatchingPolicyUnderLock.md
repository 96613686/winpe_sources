# NcbPolicyFindMatchingPolicyUnderLock

- ea: `0x18000e1d0`
- end: `0x18000e379`
- name: `NcbPolicyFindMatchingPolicyUnderLock`
- size: `425`
- prototype: `__int64 __usercall@<rax>(PSID Sid1@<rcx>, PSID@<rdx>, __int64, char)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000dda4`
- `0x180022b80`

## callees

- `0x18000a0a0`
- `0x18000e1d0`
- `0x180025c04`
- `0x180025ce8`

## import_xrefs

- `ntdll!RtlLookupEntryHashTable` at `0x18000e263`
- `ntdll!RtlLookupEntryHashTable` at `0x18000e263`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000e2a8`
- `ntdll!RtlGetNextEntryHashTable` at `0x18000e2a8`
- `ntdll!RtlEqualSid` at `0x18000e27c`
- `ntdll!RtlEqualSid` at `0x18000e292`
- `ntdll!RtlEqualSid` at `0x18000e27c`
- `ntdll!RtlEqualSid` at `0x18000e292`
- `ntdll!RtlLengthSid` at `0x18000e20f`
- `ntdll!RtlLengthSid` at `0x18000e20f`

## string_xrefs

- `0x18000e344`: `NcbPolicy: NcbCheckHardwareSlotAccessByAppId returned error code - `

## pseudocode

```c
__int64 __fastcall NcbPolicyFindMatchingPolicyUnderLock(
        unsigned __int8 *Sid1,
        PSID a2,
        unsigned __int16 *a3,
        char a4,
        __int64 a5,
        char a6)
{
  __int64 result; // rax
  __int64 v11; // r14
  ULONG v12; // eax
  ULONG v13; // r8d
  unsigned __int8 *v14; // rdx
  ULONG v15; // r9d
  unsigned int v16; // eax
  int v17; // ecx
  __int64 i; // rax
  __int64 v19; // rbx
  __int64 v20; // r8
  unsigned __int16 *v21; // rcx
  int v22; // edx
  int v23; // eax
  __int64 v24; // rdx
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rcx
  unsigned int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int128 v33; // [rsp+20h] [rbp-38h] BYREF
  __int64 v34; // [rsp+30h] [rbp-28h]
  char v35; // [rsp+60h] [rbp+8h] BYREF

  result = 0;
  v34 = 0;
  v33 = 0;
  if ( Sid1 )
  {
    v11 = 0;
    v12 = RtlLengthSid(Sid1);
    v13 = 0;
    v14 = Sid1;
    v15 = v12;
    v16 = 0;
    if ( v15 )
    {
      do
      {
        v17 = *v14++;
        ++v13;
        v16 = v17 + 37 * v16;
      }
      while ( v13 < v15 );
    }
    v33 = 0;
    for ( i = RtlLookupEntryHashTable(g_NcbPolicies, v16 | 0x80000000LL, &v33);
          ;
          i = RtlGetNextEntryHashTable(g_NcbPolicies, &v33) )
    {
      v19 = i;
      if ( !i )
        break;
      if ( RtlEqualSid(Sid1, *(PSID *)(i + 24)) && (!a2 || RtlEqualSid(a2, *(PSID *)(v19 + 40))) )
      {
        if ( !a3 )
          goto LABEL_15;
        v21 = a3;
        v20 = *(_QWORD *)(v19 + 48) - (_QWORD)a3;
        do
        {
          v22 = *(unsigned __int16 *)((char *)v21 + v20);
          v23 = *v21 - v22;
          if ( v23 )
            break;
          ++v21;
        }
        while ( v22 );
        if ( !v23 )
        {
LABEL_15:
          if ( !a4 )
            goto LABEL_19;
          v24 = *(_QWORD *)(v19 + 64);
          v35 = 0;
          v25 = NcbCheckApplicationCapabilityByAppId(a5, v24, &v35);
          if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
            McTemplateU0zq_EventWriteTransfer(
              v27,
              v26,
              L"NcbPolicy: NcbCheckApplicationCapabilityByAppId returned error code - ",
              v25);
          if ( v35 )
          {
LABEL_19:
            if ( !a6 )
              return v19;
            v28 = *(_QWORD *)(v19 + 56);
            v29 = *(_QWORD *)(v19 + 32);
            v35 = 0;
            v30 = NcbCheckHardwareSlotAccessByAppId(v29, v28, v20, &v35);
            if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
              McTemplateU0zq_EventWriteTransfer(
                v32,
                v31,
                L"NcbPolicy: NcbCheckHardwareSlotAccessByAppId returned error code - ",
                v30);
            if ( v35 )
              return v19;
          }
        }
      }
    }
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x18000e1d0  mov     [rsp+arg_18], rbp
0x18000e1d5  push    rsi
0x18000e1d6  push    rdi
0x18000e1d7  push    r15
0x18000e1d9  sub     rsp, 40h
0x18000e1dd  xor     eax, eax
0x18000e1df  xorps   xmm0, xmm0
0x18000e1e2  mov     [rsp+58h+var_28], rax
0x18000e1e7  movzx   r15d, r9b
0x18000e1eb  mov     rbp, r8
0x18000e1ee  mov     rdi, rdx
0x18000e1f1  mov     rsi, rcx
0x18000e1f4  movups  [rsp+58h+var_38], xmm0
0x18000e1f9  test    rcx, rcx
0x18000e1fc  jz      loc_18000E36B
0x18000e202  mov     [rsp+58h+arg_8], rbx
0x18000e207  mov     [rsp+58h+arg_10], r14
0x18000e20c  xor     r14d, r14d
0x18000e20f  call    cs:__imp_RtlLengthSid
0x18000e215  xor     r8d, r8d
0x18000e218  mov     rdx, rsi
0x18000e21b  mov     r9d, eax
0x18000e21e  xor     eax, eax
0x18000e220  test    r9d, r9d
0x18000e223  jz      short loc_18000E244
0x18000e225  nop     word ptr [rax+rax+00000000h]
0x18000e230  movzx   ecx, byte ptr [rdx]
0x18000e233  lea     rdx, [rdx+1]
0x18000e237  imul    eax, 25h ; '%'
0x18000e23a  inc     r8d
0x18000e23d  add     eax, ecx
0x18000e23f  cmp     r8d, r9d
0x18000e242  jb      short loc_18000E230
0x18000e244  mov     edx, eax
0x18000e246  lea     r8, [rsp+58h+var_38]
0x18000e24b  mov     eax, 80000000h
0x18000e250  lea     rcx, g_NcbPolicies
0x18000e257  xorps   xmm0, xmm0
0x18000e25a  or      rdx, rax
0x18000e25d  movdqu  [rsp+58h+var_38], xmm0
0x18000e263  call    cs:__imp_RtlLookupEntryHashTable
0x18000e269  mov     rbx, rax
0x18000e26c  test    rax, rax
0x18000e26f  jz      loc_18000E35E
0x18000e275  mov     rdx, [rax+18h]; Sid2
0x18000e279  mov     rcx, rsi; Sid1
0x18000e27c  call    cs:__imp_RtlEqualSid
0x18000e282  test    al, al
0x18000e284  jz      short loc_18000E29C
0x18000e286  test    rdi, rdi
0x18000e289  jz      short loc_18000E2B0
0x18000e28b  mov     rdx, [rbx+28h]; Sid2
0x18000e28f  mov     rcx, rdi; Sid1
0x18000e292  call    cs:__imp_RtlEqualSid
0x18000e298  test    al, al
0x18000e29a  jnz     short loc_18000E2B0
0x18000e29c  lea     rdx, [rsp+58h+var_38]
0x18000e2a1  lea     rcx, g_NcbPolicies
0x18000e2a8  call    cs:__imp_RtlGetNextEntryHashTable
0x18000e2ae  jmp     short loc_18000E269
0x18000e2b0  test    rbp, rbp
0x18000e2b3  jz      short loc_18000E2D8
0x18000e2b5  mov     r8, [rbx+30h]
0x18000e2b9  mov     rcx, rbp
0x18000e2bc  sub     r8, rbp
0x18000e2bf  nop
0x18000e2c0  movzx   eax, word ptr [rcx]
0x18000e2c3  movzx   edx, word ptr [rcx+r8]
0x18000e2c8  sub     eax, edx
0x18000e2ca  jnz     short loc_18000E2D4
0x18000e2cc  add     rcx, 2
0x18000e2d0  test    edx, edx
0x18000e2d2  jnz     short loc_18000E2C0
0x18000e2d4  test    eax, eax
0x18000e2d6  jnz     short loc_18000E29C
0x18000e2d8  test    r15b, r15b
0x18000e2db  jz      short loc_18000E317
0x18000e2dd  mov     rdx, [rbx+40h]
0x18000e2e1  lea     r8, [rsp+58h+arg_0]
0x18000e2e6  mov     rcx, [rsp+58h+arg_20]
0x18000e2ee  mov     [rsp+58h+arg_0], r14b
0x18000e2f3  call    NcbCheckApplicationCapabilityByAppId
0x18000e2f8  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000e2ff  jz      short loc_18000E310
0x18000e301  mov     r9d, eax
0x18000e304  lea     r8, aNcbpolicyNcbch_0; "NcbPolicy: NcbCheckApplicationCapabilit"...
0x18000e30b  call    McTemplateU0zq_EventWriteTransfer
0x18000e310  cmp     [rsp+58h+arg_0], r14b
0x18000e315  jz      short loc_18000E29C
0x18000e317  cmp     [rsp+58h+arg_28], r14b
0x18000e31f  jz      short loc_18000E35B
0x18000e321  mov     rdx, [rbx+38h]
0x18000e325  lea     r9, [rsp+58h+arg_0]
0x18000e32a  mov     rcx, [rbx+20h]
0x18000e32e  mov     [rsp+58h+arg_0], r14b
0x18000e333  call    NcbCheckHardwareSlotAccessByAppId
0x18000e338  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18000e33f  jz      short loc_18000E350
0x18000e341  mov     r9d, eax
0x18000e344  lea     r8, aNcbpolicyNcbch; "NcbPolicy: NcbCheckHardwareSlotAccessBy"...
0x18000e34b  call    McTemplateU0zq_EventWriteTransfer
0x18000e350  cmp     [rsp+58h+arg_0], r14b
0x18000e355  jz      loc_18000E29C
0x18000e35b  mov     r14, rbx
0x18000e35e  mov     rbx, [rsp+58h+arg_8]
0x18000e363  mov     rax, r14
0x18000e366  mov     r14, [rsp+58h+arg_10]
0x18000e36b  mov     rbp, [rsp+58h+arg_18]
0x18000e370  add     rsp, 40h
0x18000e374  pop     r15
0x18000e376  pop     rdi
0x18000e377  pop     rsi
0x18000e378  retn
```
