# SecLmfDeserializePolicyConfiguration

- ea: `0x14003e950`
- end: `0x14003ec68`
- name: `SecLmfDeserializePolicyConfiguration`
- size: `792`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14003f3f8`

## callees

- `0x14000f094`
- `0x140011610`
- `0x140011700`
- `0x1400119c0`
- `0x14003e93c`
- `0x14003e950`
- `0x14003ee48`

## import_xrefs

- `ntoskrnl!RtlValidSid` at `0x14003eabd`
- `ntoskrnl!RtlValidSid` at `0x14003eabd`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14003eb61`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14003eb61`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e9c8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003eb13`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003e9c8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003eb13`
- `ntoskrnl!RtlLengthSid` at `0x14003ead4`
- `ntoskrnl!RtlLengthSid` at `0x14003ead4`

## pseudocode

```c
__int64 __fastcall SecLmfDeserializePolicyConfiguration(__int64 a1, unsigned __int64 a2, unsigned int a3, __int64 a4)
{
  __int64 v4; // rdi
  __int64 v7; // rax
  unsigned int v9; // ebx
  SIZE_T v10; // rdx
  bool v11; // zf
  PVOID PoolWithTag; // rax
  unsigned __int64 *v13; // r12
  __int64 v14; // rdx
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // r15
  unsigned __int64 v17; // rax
  unsigned int v18; // eax
  __int64 v19; // rdi
  __int64 v20; // rbp
  char *v21; // rbx
  char *v22; // rcx
  ULONG v23; // eax
  unsigned int v24; // ecx
  PVOID v25; // rax
  __int64 v26; // rdi
  void *v27; // rcx
  __int64 v28; // r8
  __int64 v29; // rcx
  unsigned __int64 v30; // rdi
  __int64 v31; // rax
  int v32; // ebp
  unsigned __int64 v33; // rax
  __int64 v35; // [rsp+20h] [rbp-48h]
  __int64 v36; // [rsp+28h] [rbp-40h]
  unsigned __int64 v37; // [rsp+30h] [rbp-38h]
  unsigned int v38; // [rsp+70h] [rbp+8h]

  v4 = a3;
  *(_OWORD *)a4 = 0;
  *(_OWORD *)(a4 + 16) = 0;
  *(_QWORD *)(a4 + 32) = 0;
  v7 = *(unsigned int *)(a1 + 8);
  v9 = 0;
  if ( (_DWORD)v7 )
  {
    v10 = 56 * v7;
    v11 = qword_140020008 == 0;
    _mm_lfence();
    if ( v11 )
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, v10, 0x634C6353u);
    else
      PoolWithTag = (PVOID)qword_140020008(256, v10, 1665950547);
    *(_QWORD *)(a4 + 16) = PoolWithTag;
    if ( !PoolWithTag )
    {
LABEL_6:
      v9 = -1073741801;
LABEL_46:
      SecLmfFreePolicyConfiguration(a4);
      return v9;
    }
    memset(PoolWithTag, 0, 56LL * *(unsigned int *)(a1 + 8));
  }
  *(_DWORD *)a4 = 1;
  v13 = (unsigned __int64 *)(a4 + 24);
  *(_BYTE *)(a4 + 4) = *(_BYTE *)(a1 + 4);
  *(_BYTE *)(a4 + 5) = *(_BYTE *)(a1 + 5);
  *(_DWORD *)(a4 + 8) = *(_DWORD *)(a1 + 8);
  *(_QWORD *)(a4 + 24) = 0;
  *(_QWORD *)(a4 + 32) = 0;
  v14 = *(unsigned int *)(a1 + 8);
  if ( (_DWORD)v14 )
  {
    v15 = v4 + a2;
    v16 = a2 + *(unsigned int *)(a1 + 12);
    v37 = v4 + a2;
    v17 = v16 + 12 * v14;
    if ( v4 + a2 > a2 && v17 > v16 && v16 >= a2 && v17 <= v15 )
    {
      v18 = 0;
      v38 = 0;
      while ( 1 )
      {
        v19 = v18;
        v20 = 3LL * v18;
        v21 = (char *)(a2 + *(unsigned int *)(v16 + 12LL * v18));
        if ( v21 + 12 < v21 )
          break;
        if ( (unsigned __int64)v21 < a2 )
          break;
        if ( (unsigned __int64)(v21 + 12) > v15 )
          break;
        v22 = &v21[*(unsigned int *)(v16 + 12LL * v18 + 4)];
        if ( v22 <= v21 || (unsigned __int64)v22 > v15 )
          break;
        if ( !RtlValidSid(v21) )
        {
          v9 = -1073741704;
          goto LABEL_46;
        }
        v23 = RtlLengthSid(v21);
        v24 = *(_DWORD *)(v16 + 4 * v20 + 4);
        if ( v23 != v24 )
          goto LABEL_6;
        v25 = qword_140020008
            ? (PVOID)qword_140020008(256, v24, 1665950547)
            : ExAllocatePoolWithTag(PagedPool, v24, 0x634C6353u);
        v26 = 56 * v19;
        *(_QWORD *)(v26 + *(_QWORD *)(a4 + 16) + 24) = v25;
        v27 = *(void **)(v26 + *(_QWORD *)(a4 + 16) + 24);
        if ( !v27 )
          goto LABEL_6;
        memmove(v27, v21, *(unsigned int *)(v16 + 4 * v20 + 4));
        v9 = RtlConvertSidToUnicodeString(
               (PUNICODE_STRING)(v26 + *(_QWORD *)(a4 + 16) + 32LL),
               *(PSID *)(v26 + *(_QWORD *)(a4 + 16) + 24),
               1u);
        if ( (v9 & 0x80000000) != 0 )
          goto LABEL_46;
        _mm_lfence();
        *(_DWORD *)(v26 + *(_QWORD *)(a4 + 16) + 48) = *(_DWORD *)(v16 + 4 * v20 + 8);
        v29 = v26 + *(_QWORD *)(a4 + 16);
        v30 = *v13;
        v36 = v29;
        v31 = v29 + 32;
        v35 = v29 + 32;
        if ( (*(_BYTE *)(a4 + 32) & 1) != 0 && v30 )
          v30 ^= (unsigned __int64)v13;
        LOBYTE(v28) = 0;
        v32 = *(_BYTE *)(a4 + 32) & 1;
        if ( v30 )
        {
          while ( 1 )
          {
            if ( (int)SecLmfCompareUserPolicy(v31, v30, v28) < 0 )
            {
              v33 = *(_QWORD *)v30;
              if ( v32 )
              {
                if ( !v33 )
                  goto LABEL_41;
                v33 ^= v30;
              }
              if ( !v33 )
              {
LABEL_41:
                LOBYTE(v28) = 0;
                break;
              }
            }
            else
            {
              v33 = *(_QWORD *)(v30 + 8);
              if ( v32 )
              {
                if ( !v33 )
                  goto LABEL_35;
                v33 ^= v30;
              }
              if ( !v33 )
              {
LABEL_35:
                LOBYTE(v28) = 1;
                break;
              }
            }
            v30 = v33;
            v31 = v35;
          }
        }
        TreeRbInsertNodeEx(a4 + 24, v30, v28, v36);
        v18 = v38 + 1;
        v38 = v18;
        if ( v18 >= *(_DWORD *)(a1 + 8) )
          return v9;
        v15 = v37;
      }
    }
    v9 = -1073741684;
    goto LABEL_46;
  }
  return v9;
}

```

## disassembly

```asm
0x14003e950  mov     [rsp+arg_8], rbx
0x14003e955  mov     [rsp+arg_10], rbp
0x14003e95a  mov     [rsp+arg_18], rsi
0x14003e95f  push    rdi
0x14003e960  push    r12
0x14003e962  push    r13
0x14003e964  push    r14
0x14003e966  push    r15
0x14003e968  sub     rsp, 40h
0x14003e96c  xor     eax, eax
0x14003e96e  mov     edi, r8d
0x14003e971  xor     ebp, ebp
0x14003e973  xorps   xmm0, xmm0
0x14003e976  movups  xmmword ptr [r9], xmm0
0x14003e97a  mov     r14, rcx
0x14003e97d  mov     rsi, r9
0x14003e980  movups  xmmword ptr [r9+10h], xmm0
0x14003e985  mov     [r9+20h], rax
0x14003e989  lea     r15d, [rbp+1]
0x14003e98d  mov     eax, [rcx+8]
0x14003e990  mov     r13, rdx
0x14003e993  mov     ebx, ebp
0x14003e995  mov     ecx, 634C6353h
0x14003e99a  test    eax, eax
0x14003e99c  jz      short loc_14003E9F9
0x14003e99e  imul    rdx, rax, 38h ; '8'; NumberOfBytes
0x14003e9a2  cmp     cs:qword_140020008, rbp
0x14003e9a9  mov     r8d, ecx; Tag
0x14003e9ac  lfence
0x14003e9af  jz      short loc_14003E9C5
0x14003e9b1  mov     rax, cs:qword_140020008
0x14003e9b8  mov     ecx, 100h
0x14003e9bd  call    cs:__guard_dispatch_icall_fptr
0x14003e9c3  jmp     short loc_14003E9D4
0x14003e9c5  mov     ecx, r15d; PoolType
0x14003e9c8  call    cs:__imp_ExAllocatePoolWithTag
0x14003e9cf  nop     dword ptr [rax+rax+00h]
0x14003e9d4  mov     [rsi+10h], rax
0x14003e9d8  mov     rcx, rax; void *
0x14003e9db  test    rax, rax
0x14003e9de  jnz     short loc_14003E9EA
0x14003e9e0  mov     ebx, 0C0000017h
0x14003e9e5  jmp     loc_14003EC3F
0x14003e9ea  mov     eax, [r14+8]
0x14003e9ee  xor     edx, edx; Val
0x14003e9f0  imul    r8, rax, 38h ; '8'; Size
0x14003e9f4  call    memset
0x14003e9f9  mov     [rsi], r15d
0x14003e9fc  lea     r12, [rsi+18h]
0x14003ea00  mov     al, [r14+4]
0x14003ea04  mov     [rsi+4], al
0x14003ea07  mov     al, [r14+5]
0x14003ea0b  mov     [rsi+5], al
0x14003ea0e  mov     eax, [r14+8]
0x14003ea12  mov     [rsi+8], eax
0x14003ea15  mov     [r12], rbp
0x14003ea19  mov     [r12+8], rbp
0x14003ea1e  mov     edx, [r14+8]
0x14003ea22  test    edx, edx
0x14003ea24  jz      loc_14003EC47
0x14003ea2a  mov     r15d, [r14+0Ch]
0x14003ea2e  lea     r8, [rdi+r13]
0x14003ea32  add     r15, r13
0x14003ea35  mov     [rsp+68h+var_38], r8
0x14003ea3a  lea     rcx, [rdx+rdx*2]
0x14003ea3e  lea     rax, [r15+rcx*4]
0x14003ea42  cmp     r8, r13
0x14003ea45  jbe     loc_14003EC3A
0x14003ea4b  cmp     rax, r15
0x14003ea4e  jbe     loc_14003EC3A
0x14003ea54  cmp     r15, r13
0x14003ea57  jb      loc_14003EC3A
0x14003ea5d  cmp     rax, r8
0x14003ea60  ja      loc_14003EC3A
0x14003ea66  mov     eax, ebp
0x14003ea68  mov     [rsp+68h+arg_0], eax
0x14003ea6c  test    edx, edx
0x14003ea6e  jz      loc_14003EC47
0x14003ea74  mov     edi, eax
0x14003ea76  lea     rbp, [rdi+rdi*2]
0x14003ea7a  mov     ebx, [r15+rbp*4]
0x14003ea7e  add     rbx, r13
0x14003ea81  lea     rax, [rbx+0Ch]
0x14003ea85  cmp     rax, rbx
0x14003ea88  jbe     loc_14003EC3A
0x14003ea8e  cmp     rbx, r13
0x14003ea91  jb      loc_14003EC3A
0x14003ea97  cmp     rax, r8
0x14003ea9a  ja      loc_14003EC3A
0x14003eaa0  mov     ecx, [r15+rbp*4+4]
0x14003eaa5  add     rcx, rbx
0x14003eaa8  cmp     rcx, rbx
0x14003eaab  jbe     loc_14003EC3A
0x14003eab1  cmp     rcx, r8
0x14003eab4  ja      loc_14003EC3A
0x14003eaba  mov     rcx, rbx; Sid
0x14003eabd  call    cs:__imp_RtlValidSid
0x14003eac4  nop     dword ptr [rax+rax+00h]
0x14003eac9  test    al, al
0x14003eacb  jz      loc_14003EC33
0x14003ead1  mov     rcx, rbx; Sid
0x14003ead4  call    cs:__imp_RtlLengthSid
0x14003eadb  nop     dword ptr [rax+rax+00h]
0x14003eae0  mov     ecx, [r15+rbp*4+4]
0x14003eae5  cmp     eax, ecx
0x14003eae7  jnz     loc_14003E9E0
0x14003eaed  mov     rax, cs:qword_140020008
0x14003eaf4  mov     edx, ecx; NumberOfBytes
0x14003eaf6  mov     r8d, 634C6353h; Tag
0x14003eafc  test    rax, rax
0x14003eaff  jz      short loc_14003EB0E
0x14003eb01  mov     ecx, 100h
0x14003eb06  call    cs:__guard_dispatch_icall_fptr
0x14003eb0c  jmp     short loc_14003EB1F
0x14003eb0e  mov     ecx, 1; PoolType
0x14003eb13  call    cs:__imp_ExAllocatePoolWithTag
0x14003eb1a  nop     dword ptr [rax+rax+00h]
0x14003eb1f  mov     rcx, rax
0x14003eb22  mov     rax, [rsi+10h]
0x14003eb26  imul    rdi, 38h ; '8'
0x14003eb2a  mov     [rdi+rax+18h], rcx
0x14003eb2f  mov     rax, [rsi+10h]
0x14003eb33  mov     rcx, [rdi+rax+18h]; void *
0x14003eb38  test    rcx, rcx
0x14003eb3b  jz      loc_14003E9E0
0x14003eb41  mov     r8d, [r15+rbp*4+4]; Size
0x14003eb46  mov     rdx, rbx; Src
0x14003eb49  call    memmove
0x14003eb4e  mov     rdx, [rsi+10h]
0x14003eb52  mov     r8b, 1; AllocateDestinationString
0x14003eb55  lea     rcx, [rdx+20h]
0x14003eb59  mov     rdx, [rdi+rdx+18h]; Sid
0x14003eb5e  add     rcx, rdi; UnicodeString
0x14003eb61  call    cs:__imp_RtlConvertSidToUnicodeString
0x14003eb68  nop     dword ptr [rax+rax+00h]
0x14003eb6d  mov     ebx, eax
0x14003eb6f  test    eax, eax
0x14003eb71  js      loc_14003EC3F
0x14003eb77  lfence
0x14003eb7a  mov     ecx, [r15+rbp*4+8]
0x14003eb7f  mov     rdx, [rsi+10h]
0x14003eb83  mov     [rdi+rdx+30h], ecx
0x14003eb87  mov     rcx, [rsi+10h]
0x14003eb8b  add     rcx, rdi
0x14003eb8e  mov     rdi, [r12]
0x14003eb92  test    byte ptr [rsi+20h], 1
0x14003eb96  mov     [rsp+68h+var_40], rcx
0x14003eb9b  lea     rax, [rcx+20h]
0x14003eb9f  mov     [rsp+68h+var_48], rax
0x14003eba4  jz      short loc_14003EBAE
0x14003eba6  test    rdi, rdi
0x14003eba9  jz      short loc_14003EBAE
0x14003ebab  xor     rdi, r12
0x14003ebae  movzx   ebp, byte ptr [r12+8]
0x14003ebb4  xor     r8b, r8b
0x14003ebb7  and     ebp, 1
0x14003ebba  test    rdi, rdi
0x14003ebbd  jz      short loc_14003EC09
0x14003ebbf  mov     rdx, rdi
0x14003ebc2  mov     rcx, rax
0x14003ebc5  call    SecLmfCompareUserPolicy
0x14003ebca  test    eax, eax
0x14003ebcc  js      short loc_14003EBE8
0x14003ebce  mov     rax, [rdi+8]
0x14003ebd2  test    ebp, ebp
0x14003ebd4  jz      short loc_14003EBDE
0x14003ebd6  test    rax, rax
0x14003ebd9  jz      short loc_14003EBE3
0x14003ebdb  xor     rax, rdi
0x14003ebde  test    rax, rax
0x14003ebe1  jnz     short loc_14003EBFC
0x14003ebe3  mov     r8b, 1
0x14003ebe6  jmp     short loc_14003EC09
0x14003ebe8  mov     rax, [rdi]
0x14003ebeb  test    ebp, ebp
0x14003ebed  jz      short loc_14003EBF7
0x14003ebef  test    rax, rax
0x14003ebf2  jz      short loc_14003EC06
0x14003ebf4  xor     rax, rdi
0x14003ebf7  test    rax, rax
0x14003ebfa  jz      short loc_14003EC06
0x14003ebfc  mov     rdi, rax
0x14003ebff  mov     rax, [rsp+68h+var_48]
0x14003ec04  jmp     short loc_14003EBBF
0x14003ec06  xor     r8b, r8b
0x14003ec09  mov     r9, [rsp+68h+var_40]
0x14003ec0e  mov     rdx, rdi
0x14003ec11  mov     rcx, r12
0x14003ec14  call    TreeRbInsertNodeEx
0x14003ec19  mov     eax, [rsp+68h+arg_0]
0x14003ec1d  inc     eax
0x14003ec1f  mov     [rsp+68h+arg_0], eax
0x14003ec23  cmp     eax, [r14+8]
0x14003ec27  jnb     short loc_14003EC47
0x14003ec29  mov     r8, [rsp+68h+var_38]
0x14003ec2e  jmp     loc_14003EA74
0x14003ec33  mov     ebx, 0C0000078h
0x14003ec38  jmp     short loc_14003EC3F
0x14003ec3a  mov     ebx, 0C000008Ch
0x14003ec3f  mov     rcx, rsi
0x14003ec42  call    SecLmfFreePolicyConfiguration
0x14003ec47  lea     r11, [rsp+68h+var_28]
0x14003ec4c  mov     eax, ebx
0x14003ec4e  mov     rbx, [r11+38h]
0x14003ec52  mov     rbp, [r11+40h]
0x14003ec56  mov     rsi, [r11+48h]
0x14003ec5a  mov     rsp, r11
0x14003ec5d  pop     r15
0x14003ec5f  pop     r14
0x14003ec61  pop     r13
0x14003ec63  pop     r12
0x14003ec65  pop     rdi
0x14003ec66  retn
```
