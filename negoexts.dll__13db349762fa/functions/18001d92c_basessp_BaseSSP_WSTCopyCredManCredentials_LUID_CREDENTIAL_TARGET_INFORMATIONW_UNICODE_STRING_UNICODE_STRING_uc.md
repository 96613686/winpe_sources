# basessp::BaseSSP::WSTCopyCredManCredentials(_LUID *,_CREDENTIAL_TARGET_INFORMATIONW *,_UNICODE_STRING *,_UNICODE_STRING *,uchar * *,ulong *,ulong *,ulong *)

- ea: `0x18001d92c`
- end: `0x18001db3a`
- name: `?WSTCopyCredManCredentials@BaseSSP@basessp@@AEAAJPEAU_LUID@@PEAU_CREDENTIAL_TARGET_INFORMATIONW@@PEAU_UNICODE_STRING@@2PEAPEAEPEAK44@Z`
- size: `526`
- prototype: `__int64 __usercall@<rax>(basessp::BaseSSP *__hidden this@<rcx>, struct _LUID *@<rdx>, struct _CREDENTIAL_TARGET_INFORMATIONW *@<r8>, struct _UNICODE_STRING *@<r9>, PUNICODE_STRING DestinationString, unsigned __int8 **, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006a48`

## callees

- `0x1800027e4`
- `0x180006390`
- `0x180006650`
- `0x18001d92c`
- `0x18001ece2`
- `0x180020010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001d960`
- `ntdll!RtlInitUnicodeString` at `0x18001d96f`
- `ntdll!RtlInitUnicodeString` at `0x18001d960`
- `ntdll!RtlInitUnicodeString` at `0x18001d96f`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x18001da34`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x18001da34`

## pseudocode

```c
__int64 __fastcall basessp::BaseSSP::WSTCopyCredManCredentials(
        basessp::BaseSSP *this,
        struct _LUID *a2,
        struct _CREDENTIAL_TARGET_INFORMATIONW *a3,
        struct _UNICODE_STRING *a4,
        PUNICODE_STRING DestinationString,
        unsigned __int8 **a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned int *a9)
{
  PUNICODE_STRING v13; // r13
  unsigned __int8 **v14; // r12
  unsigned int *v15; // rax
  __int64 v17; // r14
  __int64 i; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdi
  int v21; // ebx
  __int64 v22; // rcx
  unsigned __int8 v23; // r9
  __int64 v24; // rcx
  unsigned __int8 *v25; // rax
  __int64 v26; // rdx
  size_t v27; // r8
  const void *v28; // rdx
  int v29; // [rsp+40h] [rbp-38h] BYREF
  __int64 v30; // [rsp+48h] [rbp-30h] BYREF
  struct _UNICODE_STRING v31; // [rsp+50h] [rbp-28h] BYREF
  struct _UNICODE_STRING v32; // [rsp+60h] [rbp-18h] BYREF
  unsigned int v33; // [rsp+C0h] [rbp+48h] BYREF

  v30 = 0;
  v33 = 0;
  v29 = 0;
  RtlInitUnicodeString(a4, 0);
  v13 = DestinationString;
  RtlInitUnicodeString(DestinationString, 0);
  v14 = a6;
  *a8 = 0;
  v15 = a7;
  *v14 = 0;
  *v15 = 0;
  *a9 = 0;
  if ( (*(int (__fastcall **)(struct _LUID *, __int64, struct _CREDENTIAL_TARGET_INFORMATIONW *, _QWORD, unsigned int *, __int64 *))(*((_QWORD *)this + 30) + 336LL))(
         a2,
         1,
         a3,
         0,
         &v33,
         &v30) < 0 )
    return 3221226021LL;
  v17 = v30;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= v33 )
      goto LABEL_18;
    v19 = *(_QWORD *)(v30 + 8 * i);
    v20 = (unsigned int)i;
    v32 = 0;
    v31 = 0;
    if ( ((*(_DWORD *)(v19 + 4) - 2) & 0xFFFFFFFB) == 0 )
      break;
  }
  if ( (*(_BYTE *)v19 & 0xCA) != 0 )
  {
    v21 = -2146893044;
    goto LABEL_19;
  }
  v22 = *(_QWORD *)(v19 + 72);
  if ( !v22 )
  {
LABEL_18:
    v21 = -1073741275;
    goto LABEL_19;
  }
  v21 = CredParseUserNameWithType(v22, &v32, &v31, &v29);
  if ( v21 >= 0 )
  {
    if ( !v31.Buffer || (v21 = basessp::BaseSSP::WSTDuplicateStringEx(this, v13, &v31, v23), v21 >= 0) )
    {
      if ( !v32.Buffer || (v21 = basessp::BaseSSP::WSTDuplicateStringEx(this, a4, &v32, v23), v21 >= 0) )
      {
        _mm_lfence();
        v24 = *(_QWORD *)(v17 + 8 * v20);
        *a9 = *(_DWORD *)(v24 + 4);
        v25 = (unsigned __int8 *)basessp::BaseSSP::WSTAllocate(this, *(unsigned int *)(v24 + 32));
        *v14 = v25;
        if ( v25 )
        {
          _mm_lfence();
          v26 = *(_QWORD *)(v17 + 8 * v20);
          v27 = *(unsigned int *)(v26 + 32);
          v28 = *(const void **)(v26 + 40);
          *a7 = v27;
          memcpy_0(v25, v28, v27);
          *a8 = *(_DWORD *)(*(_QWORD *)(v30 + 8 * v20) + 80LL);
          goto LABEL_20;
        }
        v21 = -1073741801;
      }
    }
  }
LABEL_19:
  basessp::BaseSSP::WSTFreeString(this, a4);
  basessp::BaseSSP::WSTFreeString(this, v13);
  a4->Buffer = 0;
  v13->Buffer = 0;
LABEL_20:
  (*(void (__fastcall **)(_QWORD))(*((_QWORD *)this + 30) + 344LL))(v33);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18001d92c  push    rbp
0x18001d92e  push    rbx
0x18001d92f  push    rsi
0x18001d930  push    rdi
0x18001d931  push    r12
0x18001d933  push    r13
0x18001d935  push    r14
0x18001d937  push    r15
0x18001d939  mov     rbp, rsp
0x18001d93c  sub     rsp, 78h
0x18001d940  xor     r14d, r14d
0x18001d943  mov     rdi, rdx
0x18001d946  mov     rsi, rcx
0x18001d949  mov     [rbp+var_30], r14
0x18001d94d  xor     edx, edx; SourceString
0x18001d94f  mov     [rbp+arg_0], r14d
0x18001d953  mov     rcx, r9; DestinationString
0x18001d956  mov     [rbp+var_38], r14d
0x18001d95a  mov     r15, r9
0x18001d95d  mov     rbx, r8
0x18001d960  call    cs:__imp_RtlInitUnicodeString
0x18001d966  mov     r13, [rbp+DestinationString]
0x18001d96a  xor     edx, edx; SourceString
0x18001d96c  mov     rcx, r13; DestinationString
0x18001d96f  call    cs:__imp_RtlInitUnicodeString
0x18001d975  mov     rax, [rbp+arg_38]
0x18001d97c  lea     rcx, [rbp+var_30]
0x18001d980  mov     r12, [rbp+arg_28]
0x18001d984  lea     edx, [r14+1]
0x18001d988  mov     [rsp+78h+var_50], rcx
0x18001d98d  xor     r9d, r9d
0x18001d990  lea     rcx, [rbp+arg_0]
0x18001d994  mov     r8, rbx
0x18001d997  mov     [rax], r14d
0x18001d99a  mov     rax, [rbp+arg_30]
0x18001d99e  mov     [rsp+78h+var_58], rcx
0x18001d9a3  mov     rcx, rdi
0x18001d9a6  mov     [r12], r14
0x18001d9aa  mov     [rax], r14d
0x18001d9ad  mov     rax, [rbp+arg_40]
0x18001d9b4  mov     [rax], r14d
0x18001d9b7  mov     rax, [rsi+0F0h]
0x18001d9be  mov     rax, [rax+150h]
0x18001d9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9ca  test    eax, eax
0x18001d9cc  jns     short loc_18001D9D8
0x18001d9ce  mov     eax, 0C0000225h
0x18001d9d3  jmp     loc_18001DB29
0x18001d9d8  mov     r14, [rbp+var_30]
0x18001d9dc  xor     ecx, ecx
0x18001d9de  cmp     ecx, [rbp+arg_0]
0x18001d9e1  jnb     loc_18001DAE2
0x18001d9e7  mov     rdx, [r14+rcx*8]
0x18001d9eb  xorps   xmm0, xmm0
0x18001d9ee  xorps   xmm1, xmm1
0x18001d9f1  mov     edi, ecx
0x18001d9f3  movups  xmmword ptr [rbp+var_18.Length], xmm0
0x18001d9f7  movups  xmmword ptr [rbp+var_28.Length], xmm1
0x18001d9fb  mov     eax, [rdx+4]
0x18001d9fe  sub     eax, 2
0x18001da01  test    eax, 0FFFFFFFBh
0x18001da06  jz      short loc_18001DA0C
0x18001da08  inc     ecx
0x18001da0a  jmp     short loc_18001D9DE
0x18001da0c  test    byte ptr [rdx], 0CAh
0x18001da0f  jz      short loc_18001DA1B
0x18001da11  mov     ebx, 8009030Ch
0x18001da16  jmp     loc_18001DAE7
0x18001da1b  mov     rcx, [rdx+48h]
0x18001da1f  test    rcx, rcx
0x18001da22  jz      loc_18001DAE2
0x18001da28  lea     r9, [rbp+var_38]
0x18001da2c  lea     r8, [rbp+var_28]
0x18001da30  lea     rdx, [rbp+var_18]
0x18001da34  call    cs:__imp_CredParseUserNameWithType
0x18001da3a  mov     ebx, eax
0x18001da3c  test    eax, eax
0x18001da3e  js      loc_18001DAE7
0x18001da44  cmp     [rbp+var_28.Buffer], 0
0x18001da49  jz      short loc_18001DA64
0x18001da4b  lea     r8, [rbp+var_28]; struct _UNICODE_STRING *
0x18001da4f  mov     rdx, r13; struct _UNICODE_STRING *
0x18001da52  mov     rcx, rsi; this
0x18001da55  call    ?WSTDuplicateStringEx@BaseSSP@basessp@@QEAAJPEAU_UNICODE_STRING@@0E@Z; basessp::BaseSSP::WSTDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING *,uchar)
0x18001da5a  mov     ebx, eax
0x18001da5c  test    eax, eax
0x18001da5e  js      loc_18001DAE7
0x18001da64  cmp     [rbp+var_18.Buffer], 0
0x18001da69  jz      short loc_18001DA80
0x18001da6b  lea     r8, [rbp+var_18]; struct _UNICODE_STRING *
0x18001da6f  mov     rdx, r15; struct _UNICODE_STRING *
0x18001da72  mov     rcx, rsi; this
0x18001da75  call    ?WSTDuplicateStringEx@BaseSSP@basessp@@QEAAJPEAU_UNICODE_STRING@@0E@Z; basessp::BaseSSP::WSTDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING *,uchar)
0x18001da7a  mov     ebx, eax
0x18001da7c  test    eax, eax
0x18001da7e  js      short loc_18001DAE7
0x18001da80  lfence
0x18001da83  mov     rcx, [r14+rdi*8]
0x18001da87  mov     rdx, [rbp+arg_40]
0x18001da8e  mov     eax, [rcx+4]
0x18001da91  mov     [rdx], eax
0x18001da93  mov     edx, [rcx+20h]; unsigned __int64
0x18001da96  mov     rcx, rsi; this
0x18001da99  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18001da9e  mov     [r12], rax
0x18001daa2  test    rax, rax
0x18001daa5  jnz     short loc_18001DAAE
0x18001daa7  mov     ebx, 0C0000017h
0x18001daac  jmp     short loc_18001DAE7
0x18001daae  lfence
0x18001dab1  mov     rdx, [r14+rdi*8]
0x18001dab5  mov     rcx, [rbp+arg_30]
0x18001dab9  mov     r8d, [rdx+20h]; Size
0x18001dabd  mov     rdx, [rdx+28h]; Src
0x18001dac1  mov     [rcx], r8d
0x18001dac4  mov     rcx, rax; void *
0x18001dac7  call    memcpy_0
0x18001dacc  mov     rdx, [rbp+var_30]
0x18001dad0  mov     rax, [rdx+rdi*8]
0x18001dad4  mov     ecx, [rax+50h]
0x18001dad7  mov     rax, [rbp+arg_38]
0x18001dade  mov     [rax], ecx
0x18001dae0  jmp     short loc_18001DB11
0x18001dae2  mov     ebx, 0C0000225h
0x18001dae7  mov     rdx, r15; struct _UNICODE_STRING *
0x18001daea  mov     rcx, rsi; this
0x18001daed  call    ?WSTFreeString@BaseSSP@basessp@@QEAAXPEAU_UNICODE_STRING@@@Z; basessp::BaseSSP::WSTFreeString(_UNICODE_STRING *)
0x18001daf2  mov     rdx, r13; struct _UNICODE_STRING *
0x18001daf5  mov     rcx, rsi; this
0x18001daf8  call    ?WSTFreeString@BaseSSP@basessp@@QEAAXPEAU_UNICODE_STRING@@@Z; basessp::BaseSSP::WSTFreeString(_UNICODE_STRING *)
0x18001dafd  mov     rdx, [rbp+var_30]
0x18001db01  mov     qword ptr [r15+8], 0
0x18001db09  mov     qword ptr [r13+8], 0
0x18001db11  mov     rax, [rsi+0F0h]
0x18001db18  mov     ecx, [rbp+arg_0]
0x18001db1b  mov     rax, [rax+158h]
0x18001db22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db27  mov     eax, ebx
0x18001db29  add     rsp, 78h
0x18001db2d  pop     r15
0x18001db2f  pop     r14
0x18001db31  pop     r13
0x18001db33  pop     r12
0x18001db35  pop     rdi
0x18001db36  pop     rsi
0x18001db37  pop     rbx
0x18001db38  pop     rbp
0x18001db39  retn
```
