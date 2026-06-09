# NCryptCreateClaim

- ea: `0x1800140b0`
- end: `0x18001430b`
- name: `NCryptCreateClaim`
- size: `603`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000a650`
- `0x18000c8e0`
- `0x18000e120`
- `0x180010684`
- `0x180010a24`
- `0x1800140b0`
- `0x180019980`
- `0x180020010`

## string_xrefs

- `0x18001420d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180014297`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x1800142f3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
SECURITY_STATUS __fastcall NCryptCreateClaim(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        BYTE *a5,
        DWORD a6,
        DWORD *a7,
        DWORD a8)
{
  unsigned int v9; // esi
  __int64 v11; // rdi
  unsigned int v12; // ebx
  __int64 v13; // rbp
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(_QWORD, __int64, __int64, _QWORD, __int64, BYTE *, DWORD, DWORD *, DWORD); // r10
  __int64 v16; // r8
  __int64 v17; // rdx
  unsigned int v18; // eax
  NCRYPT_KEY_HANDLE *v19; // rdx
  NCryptKeyName **v20; // r8
  NCryptAlgorithmName **v21; // r9
  unsigned int v22; // ebx
  __int64 v24; // r9
  __int64 v25; // rax
  __int64 v26; // r9
  __int64 v27; // rcx
  __int64 v28; // rax
  int v29; // r9d
  const size_t *v30; // r8

  v9 = a3;
  v11 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v24 = a1;
    if ( !a1 )
      v24 = a2;
    WPP_SF_PDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, a3, v24, a3, a8);
  }
  v12 = 5;
  if ( v9 != 4 )
    v12 = v9;
  if ( v12 - 5 <= 1 )
    Feature_Key_Guard_Attestation__private_ReportDeviceUsage();
  if ( !v11 && !a2 )
  {
    v22 = -2146893786;
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 4397);
    return NormalizeNteStatus(v22, v19, v20, v21, a5, a6, a7, a8);
  }
  if ( v11 )
  {
    v25 = ValidateClientKeyHandle(v11);
    v13 = v25;
    if ( !v25 )
    {
      v22 = -2146893786;
      v26 = 4412;
      v27 = 2148073510LL;
LABEL_40:
      DebugTraceError(v27, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v26);
      return NormalizeNteStatus(v22, v19, v20, v21, a5, a6, a7, a8);
    }
    v11 = *(_QWORD *)(v25 + 8);
  }
  else
  {
    v13 = 0;
  }
  v14 = 0;
  if ( !a2 )
    goto LABEL_10;
  v28 = ValidateClientKeyHandle(a2);
  v14 = v28;
  if ( !v28 )
  {
    v22 = -2146893786;
    v26 = 4426;
    v27 = 2148073510LL;
    goto LABEL_40;
  }
  if ( !v11 )
    v11 = *(_QWORD *)(v28 + 8);
LABEL_10:
  if ( *(_WORD *)(v11 + 16) < 3u
    || (v15 = *(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, __int64, BYTE *, DWORD, DWORD *, DWORD))(v11 + 240)) == 0 )
  {
    v22 = -2146893783;
    v26 = 4449;
    v27 = 2148073513LL;
    goto LABEL_40;
  }
  if ( v14 )
    v16 = *(_QWORD *)(v14 + 16);
  else
    v16 = 0;
  if ( v13 )
    v17 = *(_QWORD *)(v13 + 16);
  else
    v17 = 0;
  v18 = v15(*(_QWORD *)(v11 + 272), v17, v16, v12, a4, a5, a6, a7, a8);
  v22 = v18;
  if ( v18 )
  {
    DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 4466);
    if ( v13 )
    {
      v30 = *(const size_t **)(v13 + 24);
    }
    else if ( v14 )
    {
      v30 = *(const size_t **)(v14 + 24);
    }
    else
    {
      v30 = &LocaleName;
    }
    EtwLogNCryptOperationFailed(14, *(_QWORD *)(v11 + 280), (_DWORD)v30, v29, v22);
  }
  return NormalizeNteStatus(v22, v19, v20, v21, a5, a6, a7, a8);
}

```

## disassembly

```asm
0x1800140b0  push    rbx
0x1800140b2  push    rsi
0x1800140b3  push    rdi
0x1800140b4  push    r12
0x1800140b6  push    r14
0x1800140b8  push    r15
0x1800140ba  sub     rsp, 58h
0x1800140be  mov     r12, r9
0x1800140c1  mov     esi, r8d
0x1800140c4  mov     r14, rdx
0x1800140c7  mov     rdi, rcx
0x1800140ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140d1  lea     rax, WPP_GLOBAL_Control
0x1800140d8  mov     r15d, [rsp+88h+arg_38]
0x1800140e0  cmp     rcx, rax
0x1800140e3  jnz     loc_1800141CE
0x1800140e9  cmp     esi, 4
0x1800140ec  mov     ebx, 5
0x1800140f1  cmovnz  ebx, esi
0x1800140f4  lea     eax, [rbx-5]
0x1800140f7  cmp     eax, 1
0x1800140fa  jbe     loc_1800141C4
0x180014100  test    rdi, rdi
0x180014103  jz      loc_1800141FE
0x180014109  mov     [rsp+88h+arg_0], rbp
0x180014111  test    rdi, rdi
0x180014114  jnz     loc_18001422F
0x18001411a  xor     ebp, ebp
0x18001411c  xor     esi, esi
0x18001411e  test    r14, r14
0x180014121  jnz     loc_18001425D
0x180014127  cmp     word ptr [rdi+10h], 3
0x18001412c  jb      loc_1800142E3
0x180014132  mov     r10, [rdi+0F0h]
0x180014139  test    r10, r10
0x18001413c  jz      loc_1800142E3
0x180014142  test    rsi, rsi
0x180014145  jz      short loc_1800141BB
0x180014147  mov     r8, [rsi+10h]
0x18001414b  test    rbp, rbp
0x18001414e  jz      short loc_1800141C0
0x180014150  mov     rdx, [rbp+10h]
0x180014154  mov     rax, [rsp+88h+arg_30]
0x18001415c  mov     r9d, ebx
0x18001415f  mov     rcx, [rdi+110h]
0x180014166  mov     [rsp+88h+var_48], r15d
0x18001416b  mov     [rsp+88h+var_50], rax
0x180014170  mov     eax, [rsp+88h+arg_28]
0x180014177  mov     [rsp+88h+var_58], eax
0x18001417b  mov     rax, [rsp+88h+arg_20]
0x180014183  mov     [rsp+88h+var_60], rax
0x180014188  mov     rax, r10
0x18001418b  mov     [rsp+88h+var_68], r12
0x180014190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014195  mov     ebx, eax
0x180014197  test    eax, eax
0x180014199  jnz     loc_180014291
0x18001419f  mov     rbp, [rsp+88h+arg_0]
0x1800141a7  mov     ecx, ebx
0x1800141a9  add     rsp, 58h
0x1800141ad  pop     r15
0x1800141af  pop     r14
0x1800141b1  pop     r12
0x1800141b3  pop     rdi
0x1800141b4  pop     rsi
0x1800141b5  pop     rbx
0x1800141b6  jmp     NormalizeNteStatus
0x1800141bb  xor     r8d, r8d
0x1800141be  jmp     short loc_18001414B
0x1800141c0  xor     edx, edx
0x1800141c2  jmp     short loc_180014154
0x1800141c4  call    Feature_Key_Guard_Attestation__private_ReportDeviceUsage
0x1800141c9  jmp     loc_180014100
0x1800141ce  test    byte ptr [rcx+1Ch], 4
0x1800141d2  jz      loc_1800140E9
0x1800141d8  mov     rcx, [rcx+10h]
0x1800141dc  test    rdi, rdi
0x1800141df  mov     r9, rdi
0x1800141e2  mov     dword ptr [rsp+88h+var_60], r15d
0x1800141e7  cmovz   r9, r14
0x1800141eb  mov     dword ptr [rsp+88h+var_68], esi
0x1800141ef  mov     edx, 24h ; '$'
0x1800141f4  call    WPP_SF_PDD
0x1800141f9  jmp     loc_1800140E9
0x1800141fe  test    r14, r14
0x180014201  jnz     loc_180014109
0x180014207  mov     r9d, 112Dh
0x18001420d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014214  lea     rdx, aStatus; "Status"
0x18001421b  mov     ecx, 80090026h
0x180014220  mov     ebx, 80090026h
0x180014225  call    DebugTraceError
0x18001422a  jmp     loc_1800141A7
0x18001422f  mov     rcx, rdi
0x180014232  call    ValidateClientKeyHandle
0x180014237  mov     rbp, rax
0x18001423a  test    rax, rax
0x18001423d  jnz     short loc_180014254
0x18001423f  mov     ebx, 80090026h
0x180014244  mov     r9d, 113Ch
0x18001424a  mov     ecx, 80090026h
0x18001424f  jmp     loc_1800142F3
0x180014254  mov     rdi, [rax+8]
0x180014258  jmp     loc_18001411C
0x18001425d  mov     rcx, r14
0x180014260  call    ValidateClientKeyHandle
0x180014265  mov     rsi, rax
0x180014268  test    rax, rax
0x18001426b  jnz     short loc_18001427F
0x18001426d  mov     ebx, 80090026h
0x180014272  mov     r9d, 114Ah
0x180014278  mov     ecx, 80090026h
0x18001427d  jmp     short loc_1800142F3
0x18001427f  test    rdi, rdi
0x180014282  jnz     loc_180014127
0x180014288  mov     rdi, [rax+8]
0x18001428c  jmp     loc_180014127
0x180014291  mov     r9d, 1172h
0x180014297  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001429e  lea     rdx, aStatus; "Status"
0x1800142a5  mov     ecx, ebx
0x1800142a7  call    DebugTraceError
0x1800142ac  test    rbp, rbp
0x1800142af  jz      short loc_1800142B7
0x1800142b1  mov     r8, [rbp+18h]
0x1800142b5  jmp     short loc_1800142C9
0x1800142b7  test    rsi, rsi
0x1800142ba  jz      short loc_1800142C2
0x1800142bc  mov     r8, [rsi+18h]
0x1800142c0  jmp     short loc_1800142C9
0x1800142c2  lea     r8, LocaleName
0x1800142c9  mov     rdx, [rdi+118h]
0x1800142d0  mov     ecx, 0Eh
0x1800142d5  mov     dword ptr [rsp+88h+var_68], ebx
0x1800142d9  call    EtwLogNCryptOperationFailed
0x1800142de  jmp     loc_18001419F
0x1800142e3  mov     ebx, 80090029h
0x1800142e8  mov     r9d, 1161h
0x1800142ee  mov     ecx, 80090029h
0x1800142f3  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800142fa  lea     rdx, aStatus; "Status"
0x180014301  call    DebugTraceError
0x180014306  jmp     loc_18001419F
```
