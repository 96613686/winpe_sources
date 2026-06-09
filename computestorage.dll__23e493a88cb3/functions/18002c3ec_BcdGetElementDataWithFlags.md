# BcdGetElementDataWithFlags

- ea: `0x18002c3ec`
- end: `0x18002c6ae`
- name: `BcdGetElementDataWithFlags`
- size: `706`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x18001dfe4`
- `0x18002d588`
- `0x18002e6d8`
- `0x1800358b8`

## callees

- `0x180002690`
- `0x180003204`
- `0x18002c3ec`
- `0x18002cefc`
- `0x18002d940`
- `0x18002e360`
- `0x18002e8ec`
- `0x18003223c`
- `0x180033260`
- `0x180033914`
- `0x180034254`
- `0x180034e70`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002c652`
- `ntdll!RtlFreeHeap` at `0x18002c652`

## string_xrefs

- `0x18002c4f8`: `BcdGetElementDataWithFlags: Failed to open elements key.Object: %ws Status: %x`
- `0x18002c56c`: `BcdGetElementDataWithFlags: Failed to open key.Object: %ws Type: %ws Status: %x`
- `0x18002c5ed`: `BcdGetElementDataWithFlags: Failed to get registry value.Object: %ws Reg type: %lu Status: %x`

## pseudocode

```c
__int64 __fastcall BcdGetElementDataWithFlags(unsigned __int64 a1, unsigned int a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  _DWORD *v6; // rcx
  unsigned int v8; // edi
  char v9; // r15
  int v10; // eax
  unsigned int v11; // ebx
  const wchar_t *v13; // r14
  int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  HANDLE v17; // r12
  __int64 v18; // rcx
  int RegistryValue; // eax
  PVOID v20; // rsi
  __int64 v21; // [rsp+20h] [rbp-E0h]
  unsigned int v23; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE v24; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v28; // [rsp+68h] [rbp-98h]
  _DWORD *v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h]
  unsigned __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h] BYREF
  WCHAR v33[28]; // [rsp+98h] [rbp-68h] BYREF
  char v34; // [rsp+D0h] [rbp-30h] BYREF

  v31 = a1;
  v30 = a4;
  v6 = a5;
  v29 = a5;
  v27 = 5111808;
  v28 = (const wchar_t *)&v34;
  v23 = 0;
  v32 = 0;
  if ( a5 && (a4 || !*a5) )
  {
    v8 = 1;
    v9 = a1 & 1;
    LOBYTE(v6) = a1 & 1;
    v10 = BiAcquireBcdSyncMutant(v6);
    v11 = v10;
    if ( v10 < 0 )
    {
      BiLogMessage(4, L"BcdGetElementDataWithFlags: Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v10);
      return v11;
    }
    v24 = 0;
    Handle = 0;
    P = 0;
    if ( (int)BiGetObjectIdentifier(a1, &v32) < 0 )
    {
      v13 = L"N/A";
    }
    else
    {
      BiStringFromGUID(&v32, &v27);
      v13 = v28;
    }
    v14 = BiOpenKey(a1, L"Elements", 131097, &v24);
    v11 = v14;
    if ( v14 < 0 )
    {
      BiLogMessage(
        4,
        L"BcdGetElementDataWithFlags: Failed to open elements key.Object: %ws Status: %x",
        v13,
        (unsigned int)v14);
LABEL_31:
      if ( v24 )
        BiCloseKey((unsigned __int64)v24);
      LOBYTE(v15) = v9;
      BiReleaseBcdSyncMutant(v15);
      return v11;
    }
    if ( (unsigned int)o__ultow_s_0(a2, v33, 22) )
    {
      v11 = -1073741823;
      goto LABEL_31;
    }
    v16 = BiOpenKey((unsigned __int64)v24, v33, 131097, &Handle);
    v17 = Handle;
    if ( v16 < 0 )
    {
      v18 = 2;
      if ( v16 != -1073741772 )
        v18 = 4;
      BiLogMessage(
        v18,
        L"BcdGetElementDataWithFlags: Failed to open key.Object: %ws Type: %ws Status: %x",
        v13,
        v33,
        v16);
      v11 = -1073741275;
LABEL_29:
      if ( v17 )
        BiCloseKey((unsigned __int64)v17);
      goto LABEL_31;
    }
    switch ( HIBYTE(a2) & 0xF )
    {
      case 1:
        goto LABEL_22;
      case 2:
      case 3:
        break;
      case 4:
        v8 = 7;
        break;
      default:
LABEL_22:
        v8 = 3;
        break;
    }
    RegistryValue = BiGetRegistryValue(Handle, L"Element", 0, v8, &P, &v23);
    v20 = P;
    v11 = RegistryValue;
    if ( RegistryValue >= 0 )
    {
      v11 = BiConvertRegistryDataToElement(v31, P, v23, a2, 0, v30, v29);
    }
    else
    {
      LODWORD(v21) = RegistryValue;
      BiLogMessage(
        4,
        L"BcdGetElementDataWithFlags: Failed to get registry value.Object: %ws Reg type: %lu Status: %x",
        v13,
        v8,
        v21);
    }
    if ( v20 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
    goto LABEL_29;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x18002c3ec  push    rbp
0x18002c3ee  push    rbx
0x18002c3ef  push    rsi
0x18002c3f0  push    rdi
0x18002c3f1  push    r12
0x18002c3f3  push    r14
0x18002c3f5  push    r15
0x18002c3f7  lea     rbp, [rsp-30h]
0x18002c3fc  sub     rsp, 130h
0x18002c403  mov     rax, cs:__security_cookie
0x18002c40a  xor     rax, rsp
0x18002c40d  mov     [rbp+60h+var_40], rax
0x18002c411  xor     r14d, r14d
0x18002c414  mov     [rbp+60h+var_E0], rcx
0x18002c418  mov     rsi, rcx
0x18002c41b  mov     [rsp+160h+var_E8], r9
0x18002c420  mov     rcx, [rbp+60h+arg_20]
0x18002c427  lea     rax, [rbp+60h+var_90]
0x18002c42b  mov     [rsp+160h+var_120], edx
0x18002c42f  xorps   xmm0, xmm0
0x18002c432  mov     [rsp+160h+var_F0], rcx
0x18002c437  mov     r12d, edx
0x18002c43a  mov     [rsp+160h+var_100], 4E0000h
0x18002c443  mov     [rsp+160h+var_F8], rax
0x18002c448  mov     [rsp+160h+var_11C], r14d
0x18002c44d  movups  [rbp+60h+var_D8], xmm0
0x18002c451  test    rcx, rcx
0x18002c454  jz      loc_18002C68A
0x18002c45a  test    r9, r9
0x18002c45d  jnz     short loc_18002C468
0x18002c45f  cmp     [rcx], r14d
0x18002c462  jnz     loc_18002C68A
0x18002c468  mov     r15b, sil
0x18002c46b  mov     edi, 1
0x18002c470  and     r15b, dil
0x18002c473  mov     cl, r15b
0x18002c476  call    BiAcquireBcdSyncMutant
0x18002c47b  mov     ebx, eax
0x18002c47d  test    eax, eax
0x18002c47f  jns     short loc_18002C49A
0x18002c481  mov     r8d, eax
0x18002c484  lea     rdx, aBcdgetelementd_2; "BcdGetElementDataWithFlags: Failed to a"...
0x18002c48b  lea     ecx, [rdi+3]
0x18002c48e  call    BiLogMessage
0x18002c493  mov     eax, ebx
0x18002c495  jmp     loc_18002C68F
0x18002c49a  lea     rdx, [rbp+60h+var_D8]
0x18002c49e  mov     [rsp+160h+var_118], r14
0x18002c4a3  mov     rcx, rsi
0x18002c4a6  mov     [rsp+160h+Handle], r14
0x18002c4ab  mov     [rsp+160h+P], r14
0x18002c4b0  call    BiGetObjectIdentifier
0x18002c4b5  test    eax, eax
0x18002c4b7  js      short loc_18002C4CE
0x18002c4b9  lea     rdx, [rsp+160h+var_100]
0x18002c4be  lea     rcx, [rbp+60h+var_D8]
0x18002c4c2  call    BiStringFromGUID
0x18002c4c7  mov     r14, [rsp+160h+var_F8]
0x18002c4cc  jmp     short loc_18002C4D5
0x18002c4ce  lea     r14, aNA; "N/A"
0x18002c4d5  lea     r9, [rsp+160h+var_118]
0x18002c4da  mov     r8d, 20019h
0x18002c4e0  lea     rdx, aElements; "Elements"
0x18002c4e7  mov     rcx, rsi
0x18002c4ea  call    BiOpenKey
0x18002c4ef  mov     ebx, eax
0x18002c4f1  test    eax, eax
0x18002c4f3  jns     short loc_18002C511
0x18002c4f5  mov     r9d, eax
0x18002c4f8  lea     rdx, aBcdgetelementd_0; "BcdGetElementDataWithFlags: Failed to o"...
0x18002c4ff  mov     r8, r14
0x18002c502  mov     ecx, 4
0x18002c507  call    BiLogMessage
0x18002c50c  jmp     loc_18002C66B
0x18002c511  mov     r9d, 10h
0x18002c517  lea     rdx, [rbp+60h+var_C8]
0x18002c51b  mov     ecx, r12d
0x18002c51e  lea     r8d, [r9+6]
0x18002c522  call    _o__ultow_s_0
0x18002c527  test    eax, eax
0x18002c529  jz      short loc_18002C535
0x18002c52b  mov     ebx, 0C0000001h
0x18002c530  jmp     loc_18002C66B
0x18002c535  mov     rcx, [rsp+160h+var_118]
0x18002c53a  lea     r9, [rsp+160h+Handle]
0x18002c53f  mov     r8d, 20019h
0x18002c545  lea     rdx, [rbp+60h+var_C8]
0x18002c549  call    BiOpenKey
0x18002c54e  mov     r12, [rsp+160h+Handle]
0x18002c553  test    eax, eax
0x18002c555  jns     short loc_18002C58A
0x18002c557  mov     ecx, 2
0x18002c55c  mov     dword ptr [rsp+160h+var_140], eax
0x18002c560  cmp     eax, 0C0000034h
0x18002c565  lea     r9, [rbp+60h+var_C8]
0x18002c569  mov     r8, r14
0x18002c56c  lea     rdx, aBcdgetelementd_1; "BcdGetElementDataWithFlags: Failed to o"...
0x18002c573  lea     r10d, [rcx+2]
0x18002c577  cmovnz  ecx, r10d
0x18002c57b  call    BiLogMessage
0x18002c580  mov     ebx, 0C0000225h
0x18002c585  jmp     loc_18002C65E
0x18002c58a  mov     eax, [rsp+160h+var_120]
0x18002c58e  shr     eax, 18h
0x18002c591  and     eax, 0Fh
0x18002c594  sub     eax, edi
0x18002c596  jz      short loc_18002C5AA
0x18002c598  sub     eax, edi
0x18002c59a  jz      short loc_18002C5AF
0x18002c59c  sub     eax, edi
0x18002c59e  jz      short loc_18002C5AF
0x18002c5a0  sub     eax, edi
0x18002c5a2  jz      short loc_18002C600
0x18002c5a4  sub     eax, edi
0x18002c5a6  jz      short loc_18002C5AA
0x18002c5a8  sub     eax, edi
0x18002c5aa  mov     edi, 3
0x18002c5af  lea     rax, [rsp+160h+var_11C]
0x18002c5b4  mov     r9d, edi
0x18002c5b7  mov     [rsp+160h+var_138], rax
0x18002c5bc  lea     rdx, aElement; "Element"
0x18002c5c3  lea     rax, [rsp+160h+P]
0x18002c5c8  xor     r8d, r8d
0x18002c5cb  mov     rcx, r12
0x18002c5ce  mov     [rsp+160h+var_140], rax
0x18002c5d3  call    BiGetRegistryValue
0x18002c5d8  mov     rsi, [rsp+160h+P]
0x18002c5dd  mov     ebx, eax
0x18002c5df  test    eax, eax
0x18002c5e1  jns     short loc_18002C607
0x18002c5e3  mov     r9d, edi
0x18002c5e6  mov     dword ptr [rsp+160h+var_140], eax
0x18002c5ea  mov     r8, r14
0x18002c5ed  lea     rdx, aBcdgetelementd; "BcdGetElementDataWithFlags: Failed to g"...
0x18002c5f4  mov     ecx, 4
0x18002c5f9  call    BiLogMessage
0x18002c5fe  jmp     short loc_18002C63B
0x18002c600  mov     edi, 7
0x18002c605  jmp     short loc_18002C5AF
0x18002c607  mov     rax, [rsp+160h+var_F0]
0x18002c60c  mov     rdx, rsi
0x18002c60f  mov     r9d, [rsp+160h+var_120]
0x18002c614  mov     r8d, [rsp+160h+var_11C]
0x18002c619  mov     rcx, [rbp+60h+var_E0]
0x18002c61d  mov     [rsp+160h+var_130], rax
0x18002c622  mov     rax, [rsp+160h+var_E8]
0x18002c627  mov     [rsp+160h+var_138], rax
0x18002c62c  mov     dword ptr [rsp+160h+var_140], 0
0x18002c634  call    BiConvertRegistryDataToElement
0x18002c639  mov     ebx, eax
0x18002c63b  test    rsi, rsi
0x18002c63e  jz      short loc_18002C65E
0x18002c640  mov     rcx, gs:60h
0x18002c649  mov     r8, rsi; P
0x18002c64c  xor     edx, edx; Flags
0x18002c64e  mov     rcx, [rcx+30h]; HeapHandle
0x18002c652  call    cs:__imp_RtlFreeHeap
0x18002c659  nop     dword ptr [rax+rax+00h]
0x18002c65e  test    r12, r12
0x18002c661  jz      short loc_18002C66B
0x18002c663  mov     rcx, r12; Handle
0x18002c666  call    BiCloseKey
0x18002c66b  cmp     [rsp+160h+var_118], 0
0x18002c671  jz      short loc_18002C67D
0x18002c673  mov     rcx, [rsp+160h+var_118]; Handle
0x18002c678  call    BiCloseKey
0x18002c67d  mov     cl, r15b
0x18002c680  call    BiReleaseBcdSyncMutant
0x18002c685  jmp     loc_18002C493
0x18002c68a  mov     eax, 0C000000Dh
0x18002c68f  mov     rcx, [rbp+60h+var_40]
0x18002c693  xor     rcx, rsp; StackCookie
0x18002c696  call    __security_check_cookie
0x18002c69b  add     rsp, 130h
0x18002c6a2  pop     r15
0x18002c6a4  pop     r14
0x18002c6a6  pop     r12
0x18002c6a8  pop     rdi
0x18002c6a9  pop     rsi
0x18002c6aa  pop     rbx
0x18002c6ab  pop     rbp
0x18002c6ac  retn
```
