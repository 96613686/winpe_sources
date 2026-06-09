# SerializeCurveNameList

- ea: `0x180020c70`
- end: `0x180020e31`
- name: `SerializeCurveNameList`
- size: `449`
- prototype: `__int64 __fastcall(BCRYPT_HANDLE hObject)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180032c10`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18000def0`
- `0x180020c70`
- `0x1800398b0`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x180020cad`
- `bcrypt!BCryptGetProperty` at `0x180020cf9`
- `bcrypt!BCryptGetProperty` at `0x180020cad`
- `bcrypt!BCryptGetProperty` at `0x180020cf9`

## string_xrefs

- `0x180020d84`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x180020dde`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x180020e0d`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`

## pseudocode

```c
__int64 __fastcall SerializeCurveNameList(BCRYPT_HANDLE hObject, _DWORD *a2, unsigned int a3, _DWORD *a4)
{
  int v8; // edx
  unsigned int Property; // ebx
  int v10; // edx
  __int64 v11; // rdi
  unsigned int v12; // eax
  const void **v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rcx
  const void *v16; // r9
  unsigned int v17; // edx
  ULONG cbOutput[18]; // [rsp+40h] [rbp-48h] BYREF

  cbOutput[0] = 0;
  Property = BCryptGetProperty(hObject, L"ECCCurveNameList", 0, 0, cbOutput, 0);
  if ( Property )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
        (unsigned int)"Status",
        Property,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
        129);
  }
  else
  {
    v11 = SafeAllocaAllocateFromHeap(cbOutput[0]);
    if ( v11 )
    {
      v12 = BCryptGetProperty(hObject, L"ECCCurveNameList", (PUCHAR)v11, cbOutput[0], cbOutput, 0);
      Property = v12;
      if ( v12 )
      {
        DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", 400);
      }
      else
      {
        v13 = *(const void ***)(v11 + 8);
        v14 = (unsigned int)(*(_DWORD *)v11 - 1);
        v15 = -1;
        v16 = *v13;
        do
          ++v15;
        while ( *((_WORD *)v13[v14] + v15) );
        v17 = 2 * v15 + 2 - (_DWORD)v16 + LODWORD(v13[v14]);
        *a4 = v17 + 4;
        if ( a2 )
        {
          if ( a3 < v17 + 4 )
          {
            Property = -2146893784;
            goto LABEL_8;
          }
          *a2 = *(_DWORD *)v11;
          memcpy_0(a2 + 1, v16, v17);
        }
        Property = 0;
      }
LABEL_8:
      MSCryptFree(v11);
      return Property;
    }
    Property = -2146893810;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v10,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
        (unsigned int)"Status",
        14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
        137);
  }
  return Property;
}

```

## disassembly

```asm
0x180020c70  mov     r11, rsp
0x180020c73  push    rbx
0x180020c74  push    rbp
0x180020c75  push    rsi
0x180020c76  push    rdi
0x180020c77  push    r12
0x180020c79  push    r14
0x180020c7b  push    r15
0x180020c7d  sub     rsp, 50h
0x180020c81  xor     r12d, r12d
0x180020c84  lea     rax, [r11-48h]
0x180020c88  mov     r15, r9
0x180020c8b  mov     [r11-60h], r12d
0x180020c8f  mov     r14d, r8d
0x180020c92  mov     [r11-68h], rax
0x180020c96  mov     rsi, rdx
0x180020c99  mov     [r11-48h], r12d
0x180020c9d  xor     r9d, r9d; cbOutput
0x180020ca0  lea     rdx, aEcccurvenameli; "ECCCurveNameList"
0x180020ca7  xor     r8d, r8d; pbOutput
0x180020caa  mov     rbp, rcx
0x180020cad  call    cs:__imp_BCryptGetProperty
0x180020cb4  nop     dword ptr [rax+rax+00h]
0x180020cb9  mov     ebx, eax
0x180020cbb  test    eax, eax
0x180020cbd  jnz     loc_180020D63
0x180020cc3  mov     ecx, [rsp+88h+cbOutput]
0x180020cc7  call    SafeAllocaAllocateFromHeap
0x180020ccc  mov     rdi, rax
0x180020ccf  test    rax, rax
0x180020cd2  jz      loc_180020DB4
0x180020cd8  mov     r9d, [rsp+88h+cbOutput]; cbOutput
0x180020cdd  lea     rax, [rsp+88h+cbOutput]
0x180020ce2  mov     [rsp+88h+dwFlags], r12d; dwFlags
0x180020ce7  lea     rdx, aEcccurvenameli; "ECCCurveNameList"
0x180020cee  mov     r8, rdi; pbOutput
0x180020cf1  mov     [rsp+88h+pcbResult], rax; pcbResult
0x180020cf6  mov     rcx, rbp; hObject
0x180020cf9  call    cs:__imp_BCryptGetProperty
0x180020d00  nop     dword ptr [rax+rax+00h]
0x180020d05  mov     ebx, eax
0x180020d07  test    eax, eax
0x180020d09  jnz     loc_180020E07
0x180020d0f  mov     eax, [rdi]
0x180020d11  mov     rdx, [rdi+8]
0x180020d15  dec     eax
0x180020d17  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180020d1b  mov     r8, [rdx+rax*8]
0x180020d1f  mov     r9, [rdx]
0x180020d22  inc     rcx
0x180020d25  cmp     [r8+rcx*2], r12w
0x180020d2a  jnz     short loc_180020D22
0x180020d2c  mov     edx, [rdx+rax*8]
0x180020d2f  lea     ecx, ds:2[rcx*2]
0x180020d36  sub     ecx, r9d
0x180020d39  add     edx, ecx
0x180020d3b  lea     eax, [rdx+4]
0x180020d3e  mov     [r15], eax
0x180020d41  test    rsi, rsi
0x180020d44  jnz     short loc_180020D96
0x180020d46  mov     ebx, r12d
0x180020d49  mov     rcx, rdi
0x180020d4c  call    MSCryptFree
0x180020d51  mov     eax, ebx
0x180020d53  add     rsp, 50h
0x180020d57  pop     r15
0x180020d59  pop     r14
0x180020d5b  pop     r12
0x180020d5d  pop     rdi
0x180020d5e  pop     rsi
0x180020d5f  pop     rbp
0x180020d60  pop     rbx
0x180020d61  retn
0x180020d63  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d6a  lea     rax, WPP_GLOBAL_Control
0x180020d71  cmp     rcx, rax
0x180020d74  jz      short loc_180020D51
0x180020d76  test    byte ptr [rcx+1Ch], 1
0x180020d7a  jz      short loc_180020D51
0x180020d7c  mov     [rsp+88h+var_58], 181h
0x180020d84  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180020d8b  mov     qword ptr [rsp+88h+dwFlags], r8
0x180020d90  mov     dword ptr [rsp+88h+pcbResult], ebx
0x180020d94  jmp     short loc_180020DF2
0x180020d96  cmp     r14d, eax
0x180020d99  jb      loc_180020E27
0x180020d9f  mov     eax, [rdi]
0x180020da1  lea     rcx, [rsi+4]; void *
0x180020da5  mov     r8d, edx; Size
0x180020da8  mov     rdx, r9; Src
0x180020dab  mov     [rsi], eax
0x180020dad  call    memcpy_0
0x180020db2  jmp     short loc_180020D46
0x180020db4  mov     ebx, 8009000Eh
0x180020db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180020dc0  lea     rax, WPP_GLOBAL_Control
0x180020dc7  cmp     rcx, rax
0x180020dca  jz      short loc_180020D51
0x180020dcc  test    byte ptr [rcx+1Ch], 1
0x180020dd0  jz      loc_180020D51
0x180020dd6  mov     [rsp+88h+var_58], 189h
0x180020dde  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180020de5  mov     qword ptr [rsp+88h+dwFlags], r8
0x180020dea  mov     dword ptr [rsp+88h+pcbResult], 8009000Eh
0x180020df2  mov     rcx, [rcx+10h]
0x180020df6  lea     r9, aStatus; "Status"
0x180020dfd  call    WPP_SF_sDsd
0x180020e02  jmp     loc_180020D51
0x180020e07  mov     r9d, 190h
0x180020e0d  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180020e14  lea     rdx, aStatus; "Status"
0x180020e1b  mov     ecx, eax
0x180020e1d  call    DebugTraceError
0x180020e22  jmp     loc_180020D49
0x180020e27  mov     ebx, 80090028h
0x180020e2c  jmp     loc_180020D49
```
