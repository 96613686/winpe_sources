# NCryptEnumAlgorithms

- ea: `0x180011470`
- end: `0x1800116a4`
- name: `NCryptEnumAlgorithms`
- size: `564`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_PROV_HANDLE hProvider, DWORD dwAlgOperations, DWORD *pdwAlgCount, NCryptAlgorithmName **ppAlgList, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009cd0`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000cb50`
- `0x18000d02c`
- `0x18000e120`
- `0x180010a24`
- `0x180011470`
- `0x180011cb0`
- `0x180011cd0`
- `0x180020010`

## string_xrefs

- `0x18001159a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180011602`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180011632`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
SECURITY_STATUS __stdcall NCryptEnumAlgorithms(
        NCRYPT_PROV_HANDLE hProvider,
        DWORD dwAlgOperations,
        DWORD *pdwAlgCount,
        NCryptAlgorithmName **ppAlgList,
        DWORD dwFlags)
{
  NCRYPT_KEY_HANDLE *v9; // rdx
  __int64 v10; // rsi
  NCryptKeyName **v11; // r8
  NCryptAlgorithmName **v12; // r9
  __int64 *v13; // rax
  int v14; // edx
  __int64 *v15; // rdi
  unsigned int v16; // eax
  unsigned int v17; // ebx
  __int64 v19; // r9
  __int64 v20; // rcx
  DWORD v21; // [rsp+B8h] [rbp+30h]
  DWORD *v22; // [rsp+C0h] [rbp+38h]
  DWORD v23; // [rsp+C8h] [rbp+40h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_PDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, pdwAlgCount, hProvider, dwAlgOperations, dwFlags);
  v10 = ValidateAndReferenceProvider(hProvider);
  if ( v10 )
  {
    if ( pdwAlgCount && ppAlgList )
    {
      v13 = (__int64 *)SafeAllocaAllocateFromHeap(32);
      v15 = v13;
      if ( !v13 )
      {
        v17 = -2146893810;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v14,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
            (unsigned int)"Status",
            14,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
            138);
        goto LABEL_23;
      }
      *(_OWORD *)v13 = 0;
      *((_OWORD *)v13 + 1) = 0;
      while ( 1 )
      {
        v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, DWORD *, NCryptAlgorithmName **, DWORD))(v10 + 144))(
                *(_QWORD *)(v10 + 272),
                dwAlgOperations,
                pdwAlgCount,
                ppAlgList,
                dwFlags);
        v17 = v16;
        if ( v16 != -2146893778 )
        {
          if ( !v16 )
          {
            v15[1] = (__int64)*ppAlgList;
            *v15 = v10;
            MSCryptAddMemoryBuffer(KspRouterBufferList, v15);
            return NormalizeNteStatus(v17, v9, v11, v12, *(PBYTE *)&dwFlags, v21, v22, v23);
          }
LABEL_18:
          v19 = 2740;
          v20 = v17;
          goto LABEL_19;
        }
        if ( (dwFlags & 0x40) != 0 )
          break;
        v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD))(v10 + 192))(
                *(_QWORD *)(v10 + 272),
                0,
                L"NCryptEnumAlgorithms",
                0);
        if ( v17 )
          goto LABEL_18;
      }
      v17 = -2146893790;
      v19 = 2722;
      v20 = 2148073506LL;
    }
    else
    {
      v15 = 0;
      v17 = -2146893785;
      v19 = 2685;
      v20 = 2148073511LL;
    }
LABEL_19:
    DebugTraceError(v20, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v19);
LABEL_23:
    DereferenceProvider(v10);
    if ( v15 )
      MSCryptFree(v15);
    return NormalizeNteStatus(v17, v9, v11, v12, *(PBYTE *)&dwFlags, v21, v22, v23);
  }
  v17 = -2146893786;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v9,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
      (unsigned int)"Status",
      38,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
      118);
  return NormalizeNteStatus(v17, v9, v11, v12, *(PBYTE *)&dwFlags, v21, v22, v23);
}

```

## disassembly

```asm
0x180011470  push    rbx
0x180011472  push    rbp
0x180011473  push    rsi
0x180011474  push    rdi
0x180011475  push    r12
0x180011477  push    r13
0x180011479  push    r14
0x18001147b  push    r15
0x18001147d  sub     rsp, 48h
0x180011481  mov     r14, r9
0x180011484  mov     r15, r8
0x180011487  mov     r12d, edx
0x18001148a  mov     rbx, rcx
0x18001148d  mov     rcx, cs:WPP_GLOBAL_Control
0x180011494  lea     r13, WPP_GLOBAL_Control
0x18001149b  mov     ebp, [rsp+88h+dwFlags]
0x1800114a2  cmp     rcx, r13
0x1800114a5  jnz     loc_180011556
0x1800114ab  mov     rcx, rbx
0x1800114ae  call    ValidateAndReferenceProvider
0x1800114b3  mov     rsi, rax
0x1800114b6  test    rax, rax
0x1800114b9  jz      loc_18001157F
0x1800114bf  test    r15, r15
0x1800114c2  jz      loc_18001168D
0x1800114c8  test    r14, r14
0x1800114cb  jz      loc_18001168D
0x1800114d1  mov     ecx, 20h ; ' '
0x1800114d6  call    SafeAllocaAllocateFromHeap
0x1800114db  mov     rdi, rax
0x1800114de  test    rax, rax
0x1800114e1  jz      loc_180011617
0x1800114e7  xorps   xmm0, xmm0
0x1800114ea  movups  xmmword ptr [rax], xmm0
0x1800114ed  movups  xmmword ptr [rax+10h], xmm0
0x1800114f1  mov     rcx, [rsi+110h]
0x1800114f8  mov     r9, r14
0x1800114fb  mov     rax, [rsi+90h]
0x180011502  mov     r8, r15
0x180011505  mov     edx, r12d
0x180011508  mov     [rsp+88h+var_68], ebp
0x18001150c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011511  mov     ebx, eax
0x180011513  cmp     eax, 8009002Eh
0x180011518  jz      loc_1800115C7
0x18001151e  test    eax, eax
0x180011520  jnz     loc_1800115FA
0x180011526  mov     rax, [r14]
0x180011529  lea     rcx, KspRouterBufferList
0x180011530  mov     rdx, rdi
0x180011533  mov     [rdi+8], rax
0x180011537  mov     [rdi], rsi
0x18001153a  call    MSCryptAddMemoryBuffer
0x18001153f  mov     ecx, ebx
0x180011541  add     rsp, 48h
0x180011545  pop     r15
0x180011547  pop     r14
0x180011549  pop     r13
0x18001154b  pop     r12
0x18001154d  pop     rdi
0x18001154e  pop     rsi
0x18001154f  pop     rbp
0x180011550  pop     rbx
0x180011551  jmp     NormalizeNteStatus
0x180011556  test    byte ptr [rcx+1Ch], 4
0x18001155a  jz      loc_1800114AB
0x180011560  mov     rcx, [rcx+10h]
0x180011564  mov     edx, 19h
0x180011569  mov     dword ptr [rsp+88h+var_60], ebp
0x18001156d  mov     r9, rbx
0x180011570  mov     [rsp+88h+var_68], r12d
0x180011575  call    WPP_SF_PDD
0x18001157a  jmp     loc_1800114AB
0x18001157f  mov     ebx, 80090026h
0x180011584  mov     rcx, cs:WPP_GLOBAL_Control
0x18001158b  cmp     rcx, r13
0x18001158e  jz      short loc_18001153F
0x180011590  test    byte ptr [rcx+1Ch], 1
0x180011594  jz      short loc_18001153F
0x180011596  mov     rcx, [rcx+10h]
0x18001159a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800115a1  mov     [rsp+88h+var_58], 0A76h
0x1800115a9  lea     r9, aStatus; "Status"
0x1800115b0  mov     [rsp+88h+var_60], r8
0x1800115b5  mov     [rsp+88h+var_68], 80090026h
0x1800115bd  call    WPP_SF_sDsd
0x1800115c2  jmp     loc_18001153F
0x1800115c7  test    bpl, 40h
0x1800115cb  jnz     loc_180011678
0x1800115d1  mov     rcx, [rsi+110h]
0x1800115d8  lea     r8, aNcryptenumalgo_0; "NCryptEnumAlgorithms"
0x1800115df  mov     rax, [rsi+0C0h]
0x1800115e6  xor     r9d, r9d
0x1800115e9  xor     edx, edx
0x1800115eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115f0  mov     ebx, eax
0x1800115f2  test    eax, eax
0x1800115f4  jz      loc_1800114F1
0x1800115fa  mov     r9d, 0AB4h
0x180011600  mov     ecx, ebx
0x180011602  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011609  lea     rdx, aStatus; "Status"
0x180011610  call    DebugTraceError
0x180011615  jmp     short loc_18001165A
0x180011617  mov     ebx, 8009000Eh
0x18001161c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011623  cmp     rcx, r13
0x180011626  jz      short loc_18001165A
0x180011628  test    byte ptr [rcx+1Ch], 1
0x18001162c  jz      short loc_18001165A
0x18001162e  mov     rcx, [rcx+10h]
0x180011632  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011639  mov     [rsp+88h+var_58], 0A8Ah
0x180011641  lea     r9, aStatus; "Status"
0x180011648  mov     [rsp+88h+var_60], r8
0x18001164d  mov     [rsp+88h+var_68], 8009000Eh
0x180011655  call    WPP_SF_sDsd
0x18001165a  mov     rcx, rsi
0x18001165d  call    DereferenceProvider
0x180011662  test    rdi, rdi
0x180011665  jz      loc_18001153F
0x18001166b  mov     rcx, rdi
0x18001166e  call    MSCryptFree
0x180011673  jmp     loc_18001153F
0x180011678  mov     ebx, 80090022h
0x18001167d  mov     r9d, 0AA2h
0x180011683  mov     ecx, 80090022h
0x180011688  jmp     loc_180011602
0x18001168d  xor     edi, edi
0x18001168f  mov     ebx, 80090027h
0x180011694  mov     r9d, 0A7Dh
0x18001169a  mov     ecx, 80090027h
0x18001169f  jmp     loc_180011602
```
