# MinCrypK_FindPageHashesInSignedCert

- ea: `0x18008edec`
- end: `0x18008f03a`
- name: `MinCrypK_FindPageHashesInSignedCert`
- size: `590`
- prototype: `__int64 __usercall@<rax>(void *Source1@<rcx>, SIZE_T Length@<rdx>, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180061dc0`
- `0x1800965a0`

## callees

- `0x180012c26`
- `0x18002bf20`
- `0x18008ec14`
- `0x18008edec`
- `0x18008f040`
- `0x18008f2dc`
- `0x18008f458`
- `0x18008ff4c`
- `0x180091c00`
- `0x180091fb8`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x18008ef9b`
- `ntoskrnl!RtlCompareMemory` at `0x18008ef9b`

## pseudocode

```c
__int64 __fastcall MinCrypK_FindPageHashesInSignedCert(
        void *Source1,
        SIZE_T Length,
        unsigned int a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        __int64 a7)
{
  SIZE_T v8; // rbx
  __int64 *v11; // rax
  __int64 result; // rax
  int Values; // eax
  unsigned int v14; // edi
  int v15; // eax
  int v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v19; // [rsp+68h] [rbp-98h]
  int v20; // [rsp+70h] [rbp-90h] BYREF
  void *Source2; // [rsp+78h] [rbp-88h]
  int v22; // [rsp+80h] [rbp-80h]
  __int64 v23; // [rsp+88h] [rbp-78h]
  _BYTE v24[16]; // [rsp+C0h] [rbp-40h] BYREF
  int v25; // [rsp+D0h] [rbp-30h]
  _BYTE v26[16]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v27[16]; // [rsp+100h] [rbp+0h] BYREF
  int v28; // [rsp+110h] [rbp+10h]

  v8 = (unsigned int)Length;
  LODWORD(v19) = 0;
  v18 = 0;
  v17 = 0;
  if ( I_MinCryptIsHashRevoked(a3, Source1, (unsigned int)Length) )
  {
    result = 3221227011LL;
    goto LABEL_19;
  }
  v11 = qword_18002E530;
  if ( (g_CiPolicyState & 0x10000) == 0 )
    v11 = (__int64 *)&qword_18002E5B0;
  result = MinCrypK_VerifySignedDataKModeEx(*(_QWORD *)a4, *(_DWORD *)(a4 + 8), 0, 0, (__int64)v11, a6, &v20, a7, 0);
  if ( (int)result < 0 )
    goto LABEL_19;
  if ( v20 != 10 || RtlCompareMemory_0(qword_1800F5968, Source2, 0xAu) != 10 )
    goto LABEL_20;
  v16 = 8;
  Values = MinAsn1ExtractValues(v23, v22, (unsigned int)&v16, (unsigned int)&qword_18002E7A0, 6, (__int64)v24);
  if ( Values > 0 )
    Values = v25;
  if ( Values < 0 )
    goto LABEL_20;
  v14 = MinCryptDecodeHashAlgorithmIdentifier(v27);
  switch ( v14 )
  {
    case 0x8004u:
      v15 = 20;
      break;
    case 0x800Cu:
      v15 = 32;
      break;
    case 0x800Du:
      v15 = 48;
      break;
    case 0x800Eu:
      v15 = 64;
      break;
    default:
LABEL_20:
      result = 3221226536LL;
      goto LABEL_19;
  }
  if ( v15 != (_DWORD)v8
    || v28 != (_DWORD)v8
    || a3 != v14
    || !(unsigned __int8)MinAsn1FindPageHashesAttribute(v26, &v20)
    || !I_ValidatePageHashesBlob((__int64)&v20, *(_QWORD *)a4, *(_DWORD *)(a4 + 8), v8, (__int64)&v18) )
  {
    goto LABEL_20;
  }
  if ( RtlCompareMemory(Source1, (const void *)(v19 + 4), v8) != v8 )
  {
    result = 3221226021LL;
    goto LABEL_19;
  }
  result = I_AllocatePageHashes(&v18, v14, 0, &v17);
  if ( (int)result < 0 )
  {
LABEL_19:
    *(_DWORD *)(a6 + 8) |= 0x100000u;
    return result;
  }
  *a5 = v17;
  return result;
}

```

## disassembly

```asm
0x18008edec  mov     [rsp-8+arg_10], rbx
0x18008edf1  push    rbp
0x18008edf2  push    rsi
0x18008edf3  push    rdi
0x18008edf4  push    r12
0x18008edf6  push    r13
0x18008edf8  push    r14
0x18008edfa  push    r15
0x18008edfc  lea     rbp, [rsp-30h]
0x18008ee01  sub     rsp, 130h
0x18008ee08  mov     rax, cs:__security_cookie
0x18008ee0f  xor     rax, rsp
0x18008ee12  mov     [rbp+60h+var_40], rax
0x18008ee16  mov     r12, [rbp+60h+arg_20]
0x18008ee1d  xor     eax, eax
0x18008ee1f  mov     rsi, [rbp+60h+arg_28]
0x18008ee26  mov     r15d, r8d
0x18008ee29  mov     rdi, [rbp+60h+arg_30]
0x18008ee30  mov     r8d, edx
0x18008ee33  mov     ebx, edx
0x18008ee35  mov     r13, rcx
0x18008ee38  mov     rdx, rcx
0x18008ee3b  mov     qword ptr [rsp+160h+var_FC], rax
0x18008ee40  mov     ecx, r15d
0x18008ee43  mov     [rsp+60h], rax
0x18008ee48  mov     r14, r9
0x18008ee4b  mov     [rsp+160h+var_108], rax
0x18008ee50  call    I_MinCryptIsHashRevoked
0x18008ee55  test    rax, rax
0x18008ee58  jnz     loc_18008F033
0x18008ee5e  test    byte ptr cs:g_CiPolicyState+2, 1
0x18008ee65  lea     rcx, qword_18002E5B0
0x18008ee6c  mov     edx, [r14+8]; int
0x18008ee70  lea     rax, qword_18002E530
0x18008ee77  cmovz   rax, rcx
0x18008ee7b  mov     [rsp+160h+var_120], 0; __int64
0x18008ee84  mov     [rsp+160h+var_128], rdi; __int64
0x18008ee89  lea     rcx, [rsp+160h+var_F0]
0x18008ee8e  mov     [rsp+160h+var_130], rcx; void *
0x18008ee93  xor     r9d, r9d; int
0x18008ee96  mov     rcx, [r14]; int
0x18008ee99  xor     r8d, r8d; int
0x18008ee9c  mov     qword ptr [rsp+160h+var_138], rsi; int
0x18008eea1  mov     [rsp+160h+var_140], rax; __int64
0x18008eea6  call    MinCrypK_VerifySignedDataKModeEx
0x18008eeab  test    eax, eax
0x18008eead  js      loc_18008EFC4
0x18008eeb3  cmp     [rsp+160h+var_F0], 0Ah
0x18008eeb8  jnz     loc_18008EFF1
0x18008eebe  mov     rdx, [rsp+160h+Source2]; Source2
0x18008eec3  lea     rcx, qword_1800F5968; Source1
0x18008eeca  mov     r8d, 0Ah; Length
0x18008eed0  call    RtlCompareMemory_0
0x18008eed5  cmp     rax, 0Ah
0x18008eed9  jnz     loc_18008EFF1
0x18008eedf  mov     edx, [rbp+60h+var_E0]
0x18008eee2  lea     rax, [rbp+60h+var_A0]
0x18008eee6  mov     rcx, [rbp+60h+var_D8]
0x18008eeea  lea     r9, qword_18002E7A0
0x18008eef1  mov     qword ptr [rsp+160h+var_138], rax
0x18008eef6  lea     r8, [rsp+160h+var_110]
0x18008eefb  mov     dword ptr [rsp+160h+var_140], 6
0x18008ef03  mov     [rsp+160h+var_110], 8
0x18008ef0b  call    MinAsn1ExtractValues
0x18008ef10  test    eax, eax
0x18008ef12  cmovg   eax, [rbp+60h+var_90]
0x18008ef16  test    eax, eax
0x18008ef18  js      loc_18008EFF1
0x18008ef1e  lea     rcx, [rbp+60h+var_60]
0x18008ef22  call    MinCryptDecodeHashAlgorithmIdentifier
0x18008ef27  mov     ecx, eax
0x18008ef29  mov     edi, eax
0x18008ef2b  sub     ecx, 8004h
0x18008ef31  jnz     loc_18008EFF8
0x18008ef37  lea     eax, [rcx+14h]
0x18008ef3a  cmp     eax, ebx
0x18008ef3c  jnz     loc_18008EFF1
0x18008ef42  cmp     [rbp+60h+var_50], ebx
0x18008ef45  jnz     loc_18008EFF1
0x18008ef4b  cmp     r15d, edi
0x18008ef4e  jnz     loc_18008EFF1
0x18008ef54  lea     rdx, [rsp+160h+var_F0]
0x18008ef59  lea     rcx, [rbp+60h+var_70]
0x18008ef5d  call    MinAsn1FindPageHashesAttribute
0x18008ef62  test    al, al
0x18008ef64  jz      loc_18008EFF1
0x18008ef6a  mov     r8d, [r14+8]
0x18008ef6e  lea     rax, [rsp+160h+var_100]
0x18008ef73  mov     rdx, [r14]
0x18008ef76  lea     rcx, [rsp+160h+var_F0]
0x18008ef7b  mov     r9d, ebx
0x18008ef7e  mov     [rsp+160h+var_140], rax
0x18008ef83  call    I_ValidatePageHashesBlob
0x18008ef88  test    eax, eax
0x18008ef8a  jz      short loc_18008EFF1
0x18008ef8c  mov     rdx, qword ptr [rsp+160h+var_FC+4]
0x18008ef91  mov     r8, rbx; Length
0x18008ef94  add     rdx, 4; Source2
0x18008ef98  mov     rcx, r13; Source1
0x18008ef9b  call    cs:__imp_RtlCompareMemory
0x18008efa2  nop     dword ptr [rax+rax+00h]
0x18008efa7  cmp     rax, rbx
0x18008efaa  jnz     short loc_18008F021
0x18008efac  lea     r9, [rsp+160h+var_108]
0x18008efb1  xor     r8d, r8d
0x18008efb4  mov     edx, edi
0x18008efb6  lea     rcx, [rsp+160h+var_100]
0x18008efbb  call    I_AllocatePageHashes
0x18008efc0  test    eax, eax
0x18008efc2  jns     short loc_18008F028
0x18008efc4  bts     dword ptr [rsi+8], 14h
0x18008efc9  mov     rcx, [rbp+60h+var_40]
0x18008efcd  xor     rcx, rsp; StackCookie
0x18008efd0  call    __security_check_cookie
0x18008efd5  mov     rbx, [rsp+160h+arg_10]
0x18008efdd  add     rsp, 130h
0x18008efe4  pop     r15
0x18008efe6  pop     r14
0x18008efe8  pop     r13
0x18008efea  pop     r12
0x18008efec  pop     rdi
0x18008efed  pop     rsi
0x18008efee  pop     rbp
0x18008efef  retn
0x18008eff1  mov     eax, 0C0000428h
0x18008eff6  jmp     short loc_18008EFC4
0x18008eff8  sub     ecx, 8
0x18008effb  jnz     short loc_18008F005
0x18008effd  lea     eax, [rcx+20h]
0x18008f000  jmp     loc_18008EF3A
0x18008f005  sub     ecx, 1
0x18008f008  jz      short loc_18008F017
0x18008f00a  cmp     ecx, 1
0x18008f00d  jnz     short loc_18008EFF1
0x18008f00f  lea     eax, [rcx+3Fh]
0x18008f012  jmp     loc_18008EF3A
0x18008f017  mov     eax, 30h ; '0'
0x18008f01c  jmp     loc_18008EF3A
0x18008f021  mov     eax, 0C0000225h
0x18008f026  jmp     short loc_18008EFC4
0x18008f028  mov     rcx, [rsp+160h+var_108]
0x18008f02d  mov     [r12], rcx
0x18008f031  jmp     short loc_18008EFC9
0x18008f033  mov     eax, 0C0000603h
0x18008f038  jmp     short loc_18008EFC4
```
