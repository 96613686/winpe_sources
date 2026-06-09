# SslComputeClientAuthHash

- ea: `0x180012a70`
- end: `0x180012b77`
- name: `SslComputeClientAuthHash`
- size: `263`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009a70`
- `0x180009ea0`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180012a70`
- `0x180012b80`
- `0x180020010`

## string_xrefs

- `0x180012a89`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`
- `0x180012b43`: `onecore\ds\security\cryptoapi\ncrypt\crypt\sslprot.c`

## pseudocode

```c
SECURITY_STATUS __fastcall SslComputeClientAuthHash(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        BYTE *a5,
        DWORD a6,
        DWORD *a7)
{
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // ebx
  NCRYPT_KEY_HANDLE *v10; // rdx
  NCryptKeyName **v11; // r8
  NCryptAlgorithmName **v12; // r9
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r10

  if ( !ValidateSslProvHandle(a1) )
  {
    v8 = 211;
LABEL_3:
    v9 = -2146893786;
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c", v8);
    return NormalizeNteStatus((unsigned int)v9, v10, v11, v12, a5, a6, a7);
  }
  v13 = ValidateSslKeyHandle(v7);
  if ( !v13 )
  {
    v8 = 219;
    goto LABEL_3;
  }
  v15 = ValidateSslHashHandle(v14, v13);
  if ( !v15 )
  {
    v8 = 227;
    goto LABEL_3;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v17 + 40))(
         *(_QWORD *)(v17 + 424),
         *(_QWORD *)(v16 + 16),
         *(_QWORD *)(v15 + 16));
  if ( v9 >= 0 )
  {
    v9 = 0;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v10,
      (_DWORD)v11,
      (unsigned int)"Status",
      v9,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\sslprot.c",
      247);
  }
  return NormalizeNteStatus((unsigned int)v9, v10, v11, v12, a5, a6, a7);
}

```

## disassembly

```asm
0x180012a70  push    rbx
0x180012a72  sub     rsp, 50h
0x180012a76  call    ValidateSslProvHandle
0x180012a7b  mov     r10, rax
0x180012a7e  test    rax, rax
0x180012a81  jnz     short loc_180012AAB
0x180012a83  mov     r9d, 0D3h
0x180012a89  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012a90  mov     ecx, 80090026h
0x180012a95  lea     rdx, aStatus; "Status"
0x180012a9c  mov     ebx, 80090026h
0x180012aa1  call    DebugTraceError
0x180012aa6  jmp     loc_180012B6B
0x180012aab  mov     rcx, rdx
0x180012aae  call    ValidateSslKeyHandle
0x180012ab3  mov     rdx, rax
0x180012ab6  test    rax, rax
0x180012ab9  jnz     short loc_180012AC3
0x180012abb  mov     r9d, 0DBh
0x180012ac1  jmp     short loc_180012A89
0x180012ac3  mov     rcx, r8
0x180012ac6  call    ValidateSslHashHandle
0x180012acb  test    rax, rax
0x180012ace  jnz     short loc_180012AD8
0x180012ad0  mov     r9d, 0E3h
0x180012ad6  jmp     short loc_180012A89
0x180012ad8  mov     ecx, [rsp+58h+arg_38]
0x180012adf  mov     r8, [rax+10h]
0x180012ae3  mov     rdx, [rdx+10h]
0x180012ae7  mov     rax, [r10+28h]
0x180012aeb  mov     [rsp+58h+var_20], ecx
0x180012aef  mov     rcx, [rsp+58h+arg_30]
0x180012af7  mov     [rsp+58h+var_28], rcx
0x180012afc  mov     ecx, [rsp+58h+arg_28]
0x180012b03  mov     dword ptr [rsp+58h+var_30], ecx
0x180012b07  mov     rcx, [rsp+58h+arg_20]
0x180012b0f  mov     [rsp+58h+var_38], rcx
0x180012b14  mov     rcx, [r10+1A8h]
0x180012b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b20  mov     ebx, eax
0x180012b22  test    eax, eax
0x180012b24  jns     short loc_180012B69
0x180012b26  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b2d  lea     rax, WPP_GLOBAL_Control
0x180012b34  cmp     rcx, rax
0x180012b37  jz      short loc_180012B6B
0x180012b39  test    byte ptr [rcx+1Ch], 1
0x180012b3d  jz      short loc_180012B6B
0x180012b3f  mov     rcx, [rcx+10h]
0x180012b43  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012b4a  mov     dword ptr [rsp+58h+var_28], 0F7h
0x180012b52  lea     r9, aStatus; "Status"
0x180012b59  mov     [rsp+58h+var_30], rax
0x180012b5e  mov     dword ptr [rsp+58h+var_38], ebx
0x180012b62  call    WPP_SF_sDsd
0x180012b67  jmp     short loc_180012B6B
0x180012b69  xor     ebx, ebx
0x180012b6b  mov     ecx, ebx
0x180012b6d  add     rsp, 50h
0x180012b71  pop     rbx
0x180012b72  jmp     NormalizeNteStatus
```
