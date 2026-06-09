# UpdateECCHandleWithCurve

- ea: `0x18000c050`
- end: `0x18000c3bf`
- name: `UpdateECCHandleWithCurve`
- size: `879`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, UCHAR *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180033a10`
- `0x18005100c`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000c050`
- `0x18000d3d0`
- `0x1800398b0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000c163`
- `ntdll!RtlAllocateHeap` at `0x18000c265`
- `ntdll!RtlAllocateHeap` at `0x18000c163`
- `ntdll!RtlAllocateHeap` at `0x18000c265`
- `bcrypt!BCryptGenerateKeyPair` at `0x18000c097`
- `bcrypt!BCryptGenerateKeyPair` at `0x18000c097`
- `bcrypt!BCryptDestroyKey` at `0x18000c222`
- `bcrypt!BCryptDestroyKey` at `0x18000c222`
- `bcrypt!BCryptSetProperty` at `0x18000c0c0`
- `bcrypt!BCryptSetProperty` at `0x18000c0c0`
- `bcrypt!BCryptGetProperty` at `0x18000c0fc`
- `bcrypt!BCryptGetProperty` at `0x18000c136`
- `bcrypt!BCryptGetProperty` at `0x18000c1a4`
- `bcrypt!BCryptGetProperty` at `0x18000c0fc`
- `bcrypt!BCryptGetProperty` at `0x18000c136`
- `bcrypt!BCryptGetProperty` at `0x18000c1a4`

## string_xrefs

- `0x18000c2be`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x18000c310`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`
- `0x18000c3a1`: `onecore\ds\security\cryptoapi\ncrypt\storage\property.c`

## pseudocode

```c
__int64 __fastcall UpdateECCHandleWithCurve(__int64 a1, const WCHAR *a2, UCHAR *a3, unsigned int a4)
{
  SIZE_T v4; // r15
  void *v8; // rcx
  UCHAR *Heap; // rsi
  unsigned int v10; // eax
  unsigned int Property; // edi
  int v12; // edx
  int v13; // r8d
  __int64 v14; // rax
  int v15; // edx
  ULONG v16; // eax
  PVOID v18; // rax
  int v19; // edx
  int v20; // r8d
  _QWORD *v21; // rcx
  __int64 v22; // r9
  __int64 v23; // rcx
  char v24; // [rsp+30h] [rbp-48h]
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-38h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-34h] BYREF
  BCRYPT_HANDLE hObject; // [rsp+48h] [rbp-30h] BYREF
  ULONG cbOutput; // [rsp+80h] [rbp+8h] BYREF

  v4 = a4;
  hObject = 0;
  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  v8 = *(void **)(a1 + 88);
  cbOutput = 0;
  Heap = 0;
  v10 = BCryptGenerateKeyPair(v8, &hObject, 0, 0);
  Property = v10;
  if ( v10 )
  {
    v22 = 249;
LABEL_35:
    v23 = v10;
LABEL_37:
    DebugTraceError(v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c", v22);
    goto LABEL_13;
  }
  Property = BCryptSetProperty(hObject, a2, a3, v4, 0);
  if ( Property )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v24 = 0;
LABEL_26:
    WPP_SF_sDsd(
      v21[2],
      v12,
      v13,
      (unsigned int)"Status",
      Property,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
      v24);
    goto LABEL_13;
  }
  Property = BCryptGetProperty(hObject, L"PublicKeyLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v24 = 9;
    goto LABEL_26;
  }
  v10 = BCryptGetProperty(hObject, L"ECCParameters", 0, 0, &cbOutput, 0);
  Property = v10;
  if ( v10 )
  {
    v22 = 274;
    goto LABEL_35;
  }
  Heap = (UCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, cbOutput);
  if ( !Heap )
  {
    Property = -2146893810;
    v22 = 282;
    v23 = 2148073486LL;
    goto LABEL_37;
  }
  Property = BCryptGetProperty(hObject, L"ECCParameters", Heap, cbOutput, &cbOutput, 0);
  if ( Property )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_13;
    v24 = 33;
    goto LABEL_26;
  }
  v14 = -1;
  do
  {
    v15 = a2[v14 + 1] - aEcccurvename[v14 + 1];
    if ( v15 )
      break;
    v14 += 2;
    if ( v14 == 13 )
      break;
    v15 = a2[v14] - aEcccurvename[v14];
  }
  while ( !v15 );
  if ( v15 )
    goto LABEL_12;
  v18 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  *(_QWORD *)(a1 + 544) = v18;
  if ( v18 )
  {
    memcpy_0(v18, a3, v4);
LABEL_12:
    *(_DWORD *)(a1 + 28) = *(_DWORD *)pbOutput;
    v16 = cbOutput;
    *(_QWORD *)(a1 + 552) = Heap;
    Heap = 0;
    *(_DWORD *)(a1 + 560) = v16;
    goto LABEL_13;
  }
  Property = -2146893810;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      v20,
      (unsigned int)"Status",
      14,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\property.c",
      44);
LABEL_13:
  if ( hObject )
    BCryptDestroyKey(hObject);
  if ( Heap )
    MSCryptFree(Heap);
  return Property;
}

```

## disassembly

```asm
0x18000c050  mov     rax, rsp
0x18000c053  mov     [rax+10h], rbx
0x18000c057  mov     [rax+18h], rbp
0x18000c05b  push    rsi
0x18000c05c  push    rdi
0x18000c05d  push    r12
0x18000c05f  push    r14
0x18000c061  push    r15
0x18000c063  sub     rsp, 50h
0x18000c067  xor     r12d, r12d
0x18000c06a  mov     r15d, r9d
0x18000c06d  mov     r14, r8
0x18000c070  mov     [rax-30h], r12
0x18000c074  mov     rbx, rdx
0x18000c077  mov     [rax-38h], r12d
0x18000c07b  mov     rbp, rcx
0x18000c07e  mov     [rax-34h], r12d
0x18000c082  mov     rcx, [rcx+58h]; hAlgorithm
0x18000c086  lea     rdx, [rax-30h]; phKey
0x18000c08a  xor     r9d, r9d; dwFlags
0x18000c08d  mov     [rax+8], r12d
0x18000c091  xor     r8d, r8d; dwLength
0x18000c094  mov     esi, r12d
0x18000c097  call    cs:__imp_BCryptGenerateKeyPair
0x18000c09e  nop     dword ptr [rax+rax+00h]
0x18000c0a3  mov     edi, eax
0x18000c0a5  test    eax, eax
0x18000c0a7  jnz     loc_18000C378
0x18000c0ad  mov     rcx, [rsp+78h+hObject]; hObject
0x18000c0b2  mov     r9d, r15d; cbInput
0x18000c0b5  mov     r8, r14; pbInput
0x18000c0b8  mov     [rsp+78h+dwFlags], r12d; dwFlags
0x18000c0bd  mov     rdx, rbx; pszProperty
0x18000c0c0  call    cs:__imp_BCryptSetProperty
0x18000c0c7  nop     dword ptr [rax+rax+00h]
0x18000c0cc  mov     edi, eax
0x18000c0ce  test    eax, eax
0x18000c0d0  jnz     loc_18000C322
0x18000c0d6  mov     rcx, [rsp+78h+hObject]; hObject
0x18000c0db  lea     rax, [rsp+78h+pcbResult]
0x18000c0e0  mov     [rsp+78h+var_50], r12d; dwFlags
0x18000c0e5  lea     r8, [rsp+78h+pbOutput]; pbOutput
0x18000c0ea  mov     r9d, 4; cbOutput
0x18000c0f0  mov     qword ptr [rsp+78h+dwFlags], rax; pcbResult
0x18000c0f5  lea     rdx, aPublickeylengt; "PublicKeyLength"
0x18000c0fc  call    cs:__imp_BCryptGetProperty
0x18000c103  nop     dword ptr [rax+rax+00h]
0x18000c108  mov     edi, eax
0x18000c10a  test    eax, eax
0x18000c10c  jnz     loc_18000C34D
0x18000c112  mov     rcx, [rsp+78h+hObject]; hObject
0x18000c117  lea     rax, [rsp+78h+cbOutput]
0x18000c11f  mov     [rsp+78h+var_50], r12d; dwFlags
0x18000c124  lea     rdx, aEccparameters; "ECCParameters"
0x18000c12b  xor     r9d, r9d; cbOutput
0x18000c12e  mov     qword ptr [rsp+78h+dwFlags], rax; pcbResult
0x18000c133  xor     r8d, r8d; pbOutput
0x18000c136  call    cs:__imp_BCryptGetProperty
0x18000c13d  nop     dword ptr [rax+rax+00h]
0x18000c142  mov     edi, eax
0x18000c144  test    eax, eax
0x18000c146  jnz     loc_18000C380
0x18000c14c  mov     rcx, gs:60h
0x18000c155  xor     edx, edx; Flags
0x18000c157  mov     r8d, [rsp+78h+cbOutput]; Size
0x18000c15f  mov     rcx, [rcx+30h]; HeapHandle
0x18000c163  call    cs:__imp_RtlAllocateHeap
0x18000c16a  nop     dword ptr [rax+rax+00h]
0x18000c16f  mov     rsi, rax
0x18000c172  test    rax, rax
0x18000c175  jz      loc_18000C38A
0x18000c17b  mov     r9d, [rsp+78h+cbOutput]; cbOutput
0x18000c183  lea     rax, [rsp+78h+cbOutput]
0x18000c18b  mov     rcx, [rsp+78h+hObject]; hObject
0x18000c190  lea     rdx, aEccparameters; "ECCParameters"
0x18000c197  mov     [rsp+78h+var_50], r12d; dwFlags
0x18000c19c  mov     r8, rsi; pbOutput
0x18000c19f  mov     qword ptr [rsp+78h+dwFlags], rax; pcbResult
0x18000c1a4  call    cs:__imp_BCryptGetProperty
0x18000c1ab  nop     dword ptr [rax+rax+00h]
0x18000c1b0  mov     edi, eax
0x18000c1b2  test    eax, eax
0x18000c1b4  jnz     loc_18000C2E7
0x18000c1ba  lea     r8, aEcccurvename; "ECCCurveName"
0x18000c1c1  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000c1c8  nop     dword ptr [rax+rax+00000000h]
0x18000c1d0  movzx   edx, word ptr [rbx+rax*2+2]
0x18000c1d5  movzx   ecx, word ptr [r8+rax*2+2]
0x18000c1db  sub     edx, ecx
0x18000c1dd  jnz     short loc_18000C1F6
0x18000c1df  add     rax, 2
0x18000c1e3  cmp     rax, 0Dh
0x18000c1e7  jz      short loc_18000C1F6
0x18000c1e9  movzx   edx, word ptr [rbx+rax*2]
0x18000c1ed  movzx   ecx, word ptr [r8+rax*2]
0x18000c1f2  sub     edx, ecx
0x18000c1f4  jz      short loc_18000C1D0
0x18000c1f6  test    edx, edx
0x18000c1f8  jz      short loc_18000C253
0x18000c1fa  mov     eax, dword ptr [rsp+78h+pbOutput]
0x18000c1fe  mov     [rbp+1Ch], eax
0x18000c201  mov     eax, [rsp+78h+cbOutput]
0x18000c208  mov     [rbp+228h], rsi
0x18000c20f  mov     rsi, r12
0x18000c212  mov     [rbp+230h], eax
0x18000c218  mov     rcx, [rsp+78h+hObject]; hKey
0x18000c21d  test    rcx, rcx
0x18000c220  jz      short loc_18000C22E
0x18000c222  call    cs:__imp_BCryptDestroyKey
0x18000c229  nop     dword ptr [rax+rax+00h]
0x18000c22e  test    rsi, rsi
0x18000c231  jnz     loc_18000C3B2
0x18000c237  lea     r11, [rsp+78h+var_28]
0x18000c23c  mov     eax, edi
0x18000c23e  mov     rbx, [r11+38h]
0x18000c242  mov     rbp, [r11+40h]
0x18000c246  mov     rsp, r11
0x18000c249  pop     r15
0x18000c24b  pop     r14
0x18000c24d  pop     r12
0x18000c24f  pop     rdi
0x18000c250  pop     rsi
0x18000c251  retn
0x18000c253  mov     rcx, gs:60h
0x18000c25c  mov     r8, r15; Size
0x18000c25f  xor     edx, edx; Flags
0x18000c261  mov     rcx, [rcx+30h]; HeapHandle
0x18000c265  call    cs:__imp_RtlAllocateHeap
0x18000c26c  nop     dword ptr [rax+rax+00h]
0x18000c271  mov     [rbp+220h], rax
0x18000c278  test    rax, rax
0x18000c27b  jz      short loc_18000C290
0x18000c27d  mov     r8, r15; Size
0x18000c280  mov     rdx, r14; Src
0x18000c283  mov     rcx, rax; void *
0x18000c286  call    memcpy_0
0x18000c28b  jmp     loc_18000C1FA
0x18000c290  mov     edi, 8009000Eh
0x18000c295  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c29c  lea     rax, WPP_GLOBAL_Control
0x18000c2a3  cmp     rcx, rax
0x18000c2a6  jz      loc_18000C218
0x18000c2ac  test    byte ptr [rcx+1Ch], 1
0x18000c2b0  jz      loc_18000C218
0x18000c2b6  mov     dword ptr [rsp+78h+var_48], 12Ch
0x18000c2be  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c2c5  mov     qword ptr [rsp+78h+var_50], rax
0x18000c2ca  mov     [rsp+78h+dwFlags], 8009000Eh
0x18000c2d2  mov     rcx, [rcx+10h]
0x18000c2d6  lea     r9, aStatus; "Status"
0x18000c2dd  call    WPP_SF_sDsd
0x18000c2e2  jmp     loc_18000C218
0x18000c2e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2ee  lea     rax, WPP_GLOBAL_Control
0x18000c2f5  cmp     rcx, rax
0x18000c2f8  jz      loc_18000C218
0x18000c2fe  test    byte ptr [rcx+1Ch], 1
0x18000c302  jz      loc_18000C218
0x18000c308  mov     dword ptr [rsp+78h+var_48], 121h
0x18000c310  lea     rax, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c317  mov     qword ptr [rsp+78h+var_50], rax
0x18000c31c  mov     [rsp+78h+dwFlags], edi
0x18000c320  jmp     short loc_18000C2D2
0x18000c322  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c329  lea     rax, WPP_GLOBAL_Control
0x18000c330  cmp     rcx, rax
0x18000c333  jz      loc_18000C218
0x18000c339  test    byte ptr [rcx+1Ch], 1
0x18000c33d  jz      loc_18000C218
0x18000c343  mov     dword ptr [rsp+78h+var_48], 100h
0x18000c34b  jmp     short loc_18000C310
0x18000c34d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c354  lea     rax, WPP_GLOBAL_Control
0x18000c35b  cmp     rcx, rax
0x18000c35e  jz      loc_18000C218
0x18000c364  test    byte ptr [rcx+1Ch], 1
0x18000c368  jz      loc_18000C218
0x18000c36e  mov     dword ptr [rsp+78h+var_48], 109h
0x18000c376  jmp     short loc_18000C310
0x18000c378  mov     r9d, 0F9h
0x18000c37e  jmp     short loc_18000C386
0x18000c380  mov     r9d, 112h
0x18000c386  mov     ecx, eax
0x18000c388  jmp     short loc_18000C39A
0x18000c38a  mov     edi, 8009000Eh
0x18000c38f  mov     r9d, 11Ah
0x18000c395  mov     ecx, 8009000Eh
0x18000c39a  lea     rdx, aStatus; "Status"
0x18000c3a1  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c3a8  call    DebugTraceError
0x18000c3ad  jmp     loc_18000C218
0x18000c3b2  mov     rcx, rsi
0x18000c3b5  call    MSCryptFree
0x18000c3ba  jmp     loc_18000C237
```
