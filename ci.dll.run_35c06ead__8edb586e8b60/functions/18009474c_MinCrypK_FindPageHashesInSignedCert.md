# MinCrypK_FindPageHashesInSignedCert

- ea: `0x18009474c`
- end: `0x18009499a`
- name: `MinCrypK_FindPageHashesInSignedCert`
- size: `590`
- prototype: `__int64 __usercall@<rax>(void *Source1@<rcx>, SIZE_T Length@<rdx>, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180061f24`
- `0x18008c760`

## callees

- `0x180012c86`
- `0x18002c0d0`
- `0x180094574`
- `0x18009474c`
- `0x1800949a0`
- `0x180094c3c`
- `0x180094db8`
- `0x1800958ac`
- `0x180097560`
- `0x180097918`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1800948fb`
- `ntoskrnl!RtlCompareMemory` at `0x1800948fb`

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
  v11 = qword_18002E4E0;
  if ( (g_CiPolicyState & 0x10000) == 0 )
    v11 = (__int64 *)&qword_18002E560;
  result = MinCrypK_VerifySignedDataKModeEx(*(_QWORD *)a4, *(_DWORD *)(a4 + 8), 0, 0, (__int64)v11, a6, &v20, a7, 0);
  if ( (int)result < 0 )
    goto LABEL_19;
  if ( v20 != 10 || RtlCompareMemory_0(qword_1800F6968, Source2, 0xAu) != 10 )
    goto LABEL_20;
  v16 = 8;
  Values = MinAsn1ExtractValues(v23, v22, (unsigned int)&v16, (unsigned int)&qword_18002E750, 6, (__int64)v24);
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
0x18009474c  mov     [rsp-8+arg_10], rbx
0x180094751  push    rbp
0x180094752  push    rsi
0x180094753  push    rdi
0x180094754  push    r12
0x180094756  push    r13
0x180094758  push    r14
0x18009475a  push    r15
0x18009475c  lea     rbp, [rsp-30h]
0x180094761  sub     rsp, 130h
0x180094768  mov     rax, cs:__security_cookie
0x18009476f  xor     rax, rsp
0x180094772  mov     [rbp+60h+var_40], rax
0x180094776  mov     r12, [rbp+60h+arg_20]
0x18009477d  xor     eax, eax
0x18009477f  mov     rsi, [rbp+60h+arg_28]
0x180094786  mov     r15d, r8d
0x180094789  mov     rdi, [rbp+60h+arg_30]
0x180094790  mov     r8d, edx
0x180094793  mov     ebx, edx
0x180094795  mov     r13, rcx
0x180094798  mov     rdx, rcx
0x18009479b  mov     qword ptr [rsp+160h+var_FC], rax
0x1800947a0  mov     ecx, r15d
0x1800947a3  mov     [rsp+60h], rax
0x1800947a8  mov     r14, r9
0x1800947ab  mov     [rsp+160h+var_108], rax
0x1800947b0  call    I_MinCryptIsHashRevoked
0x1800947b5  test    rax, rax
0x1800947b8  jnz     loc_180094993
0x1800947be  test    byte ptr cs:g_CiPolicyState+2, 1
0x1800947c5  lea     rcx, qword_18002E560
0x1800947cc  mov     edx, [r14+8]; int
0x1800947d0  lea     rax, qword_18002E4E0
0x1800947d7  cmovz   rax, rcx
0x1800947db  mov     [rsp+160h+var_120], 0; __int64
0x1800947e4  mov     [rsp+160h+var_128], rdi; __int64
0x1800947e9  lea     rcx, [rsp+160h+var_F0]
0x1800947ee  mov     [rsp+160h+var_130], rcx; void *
0x1800947f3  xor     r9d, r9d; int
0x1800947f6  mov     rcx, [r14]; int
0x1800947f9  xor     r8d, r8d; int
0x1800947fc  mov     qword ptr [rsp+160h+var_138], rsi; int
0x180094801  mov     [rsp+160h+var_140], rax; __int64
0x180094806  call    MinCrypK_VerifySignedDataKModeEx
0x18009480b  test    eax, eax
0x18009480d  js      loc_180094924
0x180094813  cmp     [rsp+160h+var_F0], 0Ah
0x180094818  jnz     loc_180094951
0x18009481e  mov     rdx, [rsp+160h+Source2]; Source2
0x180094823  lea     rcx, qword_1800F6968; Source1
0x18009482a  mov     r8d, 0Ah; Length
0x180094830  call    RtlCompareMemory_0
0x180094835  cmp     rax, 0Ah
0x180094839  jnz     loc_180094951
0x18009483f  mov     edx, [rbp+60h+var_E0]
0x180094842  lea     rax, [rbp+60h+var_A0]
0x180094846  mov     rcx, [rbp+60h+var_D8]
0x18009484a  lea     r9, qword_18002E750
0x180094851  mov     qword ptr [rsp+160h+var_138], rax
0x180094856  lea     r8, [rsp+160h+var_110]
0x18009485b  mov     dword ptr [rsp+160h+var_140], 6
0x180094863  mov     [rsp+160h+var_110], 8
0x18009486b  call    MinAsn1ExtractValues
0x180094870  test    eax, eax
0x180094872  cmovg   eax, [rbp+60h+var_90]
0x180094876  test    eax, eax
0x180094878  js      loc_180094951
0x18009487e  lea     rcx, [rbp+60h+var_60]
0x180094882  call    MinCryptDecodeHashAlgorithmIdentifier
0x180094887  mov     ecx, eax
0x180094889  mov     edi, eax
0x18009488b  sub     ecx, 8004h
0x180094891  jnz     loc_180094958
0x180094897  lea     eax, [rcx+14h]
0x18009489a  cmp     eax, ebx
0x18009489c  jnz     loc_180094951
0x1800948a2  cmp     [rbp+60h+var_50], ebx
0x1800948a5  jnz     loc_180094951
0x1800948ab  cmp     r15d, edi
0x1800948ae  jnz     loc_180094951
0x1800948b4  lea     rdx, [rsp+160h+var_F0]
0x1800948b9  lea     rcx, [rbp+60h+var_70]
0x1800948bd  call    MinAsn1FindPageHashesAttribute
0x1800948c2  test    al, al
0x1800948c4  jz      loc_180094951
0x1800948ca  mov     r8d, [r14+8]
0x1800948ce  lea     rax, [rsp+160h+var_100]
0x1800948d3  mov     rdx, [r14]
0x1800948d6  lea     rcx, [rsp+160h+var_F0]
0x1800948db  mov     r9d, ebx
0x1800948de  mov     [rsp+160h+var_140], rax
0x1800948e3  call    I_ValidatePageHashesBlob
0x1800948e8  test    eax, eax
0x1800948ea  jz      short loc_180094951
0x1800948ec  mov     rdx, qword ptr [rsp+160h+var_FC+4]
0x1800948f1  mov     r8, rbx; Length
0x1800948f4  add     rdx, 4; Source2
0x1800948f8  mov     rcx, r13; Source1
0x1800948fb  call    cs:__imp_RtlCompareMemory
0x180094902  nop     dword ptr [rax+rax+00h]
0x180094907  cmp     rax, rbx
0x18009490a  jnz     short loc_180094981
0x18009490c  lea     r9, [rsp+160h+var_108]
0x180094911  xor     r8d, r8d
0x180094914  mov     edx, edi
0x180094916  lea     rcx, [rsp+160h+var_100]
0x18009491b  call    I_AllocatePageHashes
0x180094920  test    eax, eax
0x180094922  jns     short loc_180094988
0x180094924  bts     dword ptr [rsi+8], 14h
0x180094929  mov     rcx, [rbp+60h+var_40]
0x18009492d  xor     rcx, rsp; StackCookie
0x180094930  call    __security_check_cookie
0x180094935  mov     rbx, [rsp+160h+arg_10]
0x18009493d  add     rsp, 130h
0x180094944  pop     r15
0x180094946  pop     r14
0x180094948  pop     r13
0x18009494a  pop     r12
0x18009494c  pop     rdi
0x18009494d  pop     rsi
0x18009494e  pop     rbp
0x18009494f  retn
0x180094951  mov     eax, 0C0000428h
0x180094956  jmp     short loc_180094924
0x180094958  sub     ecx, 8
0x18009495b  jnz     short loc_180094965
0x18009495d  lea     eax, [rcx+20h]
0x180094960  jmp     loc_18009489A
0x180094965  sub     ecx, 1
0x180094968  jz      short loc_180094977
0x18009496a  cmp     ecx, 1
0x18009496d  jnz     short loc_180094951
0x18009496f  lea     eax, [rcx+3Fh]
0x180094972  jmp     loc_18009489A
0x180094977  mov     eax, 30h ; '0'
0x18009497c  jmp     loc_18009489A
0x180094981  mov     eax, 0C0000225h
0x180094986  jmp     short loc_180094924
0x180094988  mov     rcx, [rsp+160h+var_108]
0x18009498d  mov     [r12], rcx
0x180094991  jmp     short loc_180094929
0x180094993  mov     eax, 0C0000603h
0x180094998  jmp     short loc_180094924
```
