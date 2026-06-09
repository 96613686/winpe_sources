# MSCryptSetHashProperty

- ea: `0x180011d40`
- end: `0x180011eef`
- name: `MSCryptSetHashProperty`
- size: `431`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x180011d40`
- `0x180011f00`
- `0x1800122a0`
- `0x18007c680`
- `0x18009d746`

## string_xrefs

- `0x180011e04`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x180011e51`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18009f95c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptSetHashProperty(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, int a5)
{
  __int64 v6; // rbx
  unsigned __int16 *v8; // rdx
  _DWORD *v9; // rdi
  __int64 v10; // r8
  int v11; // edx
  unsigned int v12; // ebx
  __int64 v14; // r9
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  int v18; // eax

  v6 = a4;
  if ( a5 )
  {
    v12 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
        253);
    return v12;
  }
  v9 = (_DWORD *)validateMSCryptHash();
  if ( !v9 )
  {
    v12 = -1073741816;
    v14 = 3846;
    v15 = 3221225480LL;
    goto LABEL_50;
  }
  v11 = *v8 - 73;
  if ( !v11 )
  {
    v11 = *(unsigned __int16 *)(a2 + 2) - 86;
    if ( *(_WORD *)(a2 + 2) == 86 )
      v11 = *(unsigned __int16 *)(a2 + 4);
  }
  if ( v11 )
  {
    if ( !wcscmp_0((const wchar_t *)a2, L"FunctionNameString") )
    {
      v16 = v9[2];
      if ( v16 == 131093 )
      {
        v17 = MSCryptCustomBufferUpdate(v9 + 30, a3, (unsigned int)v6);
        v12 = v17;
        if ( v17 < 0 )
        {
          v14 = 3895;
LABEL_27:
          v15 = (unsigned int)v17;
          goto LABEL_50;
        }
        goto LABEL_31;
      }
      if ( v16 == 131094 )
      {
        v17 = MSCryptCustomBufferUpdate(v9 + 30, a3, (unsigned int)v6);
        v12 = v17;
        if ( v17 < 0 )
        {
          v14 = 3909;
          goto LABEL_27;
        }
LABEL_31:
        v9[70] = 0;
        return 0;
      }
      v14 = 3918;
LABEL_34:
      v12 = -1073741811;
      v15 = 3221225485LL;
      goto LABEL_50;
    }
    if ( wcscmp_0((const wchar_t *)a2, L"CustomizationString") )
    {
      v12 = -1073741637;
      v14 = 3996;
      v15 = 3221225659LL;
      goto LABEL_50;
    }
    v18 = v9[2];
    switch ( v18 )
    {
      case 131093:
        v17 = MSCryptCustomBufferUpdate(v9 + 50, a3, (unsigned int)v6);
        v12 = v17;
        if ( v17 < 0 )
        {
          v14 = 3935;
          goto LABEL_27;
        }
        goto LABEL_31;
      case 131094:
        v17 = MSCryptCustomBufferUpdate(v9 + 50, a3, (unsigned int)v6);
        v12 = v17;
        if ( v17 < 0 )
        {
          v14 = 3949;
          goto LABEL_27;
        }
        goto LABEL_31;
      case 131095:
        v17 = MSCryptCustomBufferUpdate(v9 + 112, a3, (unsigned int)v6);
        v12 = v17;
        if ( v17 < 0 )
        {
          v14 = 3963;
          goto LABEL_27;
        }
        break;
      case 131096:
        v17 = MSCryptCustomBufferUpdate(v9 + 112, a3, (unsigned int)v6);
        v12 = v17;
        if ( v17 < 0 )
        {
          v14 = 3977;
          goto LABEL_27;
        }
        break;
      default:
        v14 = 3986;
        goto LABEL_34;
    }
    v9[132] = 0;
    return 0;
  }
  if ( v9[2] == 131080 )
  {
    if ( (_DWORD)v6 == 12 )
    {
      if ( !v9[29] )
      {
        SymCryptGcmInit(v9 + 684, v9 + 32, v10, v6);
        v9[29] = 1;
        return 0;
      }
      v12 = -1073740758;
      v14 = 3878;
      v15 = 3221226538LL;
    }
    else
    {
      v12 = -1073741306;
      v14 = 3868;
      v15 = 3221225990LL;
    }
LABEL_50:
    DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v14);
    return v12;
  }
  v12 = -1073741637;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      0,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
      (unsigned int)"Status",
      187,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c",
      17);
  return v12;
}

```

## disassembly

```asm
0x180011d40  push    rbx
0x180011d42  push    rbp
0x180011d43  push    rsi
0x180011d44  push    rdi
0x180011d45  sub     rsp, 48h
0x180011d49  cmp     [rsp+68h+arg_20], 0
0x180011d51  mov     rbp, r8
0x180011d54  mov     ebx, r9d
0x180011d57  mov     rsi, rdx
0x180011d5a  jnz     loc_180011E2A
0x180011d60  call    validateMSCryptHash
0x180011d65  mov     rdi, rax
0x180011d68  test    rax, rax
0x180011d6b  jz      loc_180011E67
0x180011d71  movzx   edx, word ptr [rdx]
0x180011d74  sub     edx, 49h ; 'I'
0x180011d77  jnz     short loc_180011D8D
0x180011d79  movzx   edx, word ptr [rsi+2]
0x180011d7d  sub     edx, 56h ; 'V'
0x180011d80  jnz     short loc_180011D8D
0x180011d82  movzx   edx, word ptr [rsi+4]
0x180011d86  xor     eax, eax
0x180011d88  movzx   ecx, ax
0x180011d8b  sub     edx, ecx
0x180011d8d  test    edx, edx
0x180011d8f  jnz     loc_180011EA6
0x180011d95  cmp     dword ptr [rdi+8], 20008h
0x180011d9c  jnz     short loc_180011DDD
0x180011d9e  lea     eax, [rbx-0Ch]
0x180011da1  test    eax, eax
0x180011da3  jnz     loc_180011E91
0x180011da9  cmp     [rdi+74h], eax
0x180011dac  jnz     loc_180011E7C
0x180011db2  mov     r9, rbx
0x180011db5  lea     rdx, [rdi+80h]
0x180011dbc  lea     rcx, [rdi+0AB0h]
0x180011dc3  call    SymCryptGcmInit
0x180011dc8  mov     dword ptr [rdi+74h], 1
0x180011dcf  xor     ebx, ebx
0x180011dd1  mov     eax, ebx
0x180011dd3  add     rsp, 48h
0x180011dd7  pop     rdi
0x180011dd8  pop     rsi
0x180011dd9  pop     rbp
0x180011dda  pop     rbx
0x180011ddb  retn
0x180011ddd  mov     ebx, 0C00000BBh
0x180011de2  mov     rcx, cs:WPP_GLOBAL_Control
0x180011de9  lea     rax, WPP_GLOBAL_Control
0x180011df0  cmp     rcx, rax
0x180011df3  jz      short loc_180011DD1
0x180011df5  mov     eax, [rcx+2Ch]
0x180011df8  test    al, 1
0x180011dfa  jz      short loc_180011DD1
0x180011dfc  mov     [rsp+68h+var_38], 0F11h
0x180011e04  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011e0b  mov     [rsp+68h+var_40], r8
0x180011e10  mov     [rsp+68h+var_48], 0C00000BBh
0x180011e18  mov     rcx, [rcx+18h]
0x180011e1c  lea     r9, aStatus; "Status"
0x180011e23  call    WPP_SF_sDsd
0x180011e28  jmp     short loc_180011DD1
0x180011e2a  mov     ebx, 0C000000Dh
0x180011e2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e36  lea     rax, WPP_GLOBAL_Control
0x180011e3d  cmp     rcx, rax
0x180011e40  jz      short loc_180011DD1
0x180011e42  mov     eax, [rcx+2Ch]
0x180011e45  test    al, 1
0x180011e47  jz      short loc_180011DD1
0x180011e49  mov     [rsp+68h+var_38], 0EFDh
0x180011e51  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011e58  mov     [rsp+68h+var_40], r8
0x180011e5d  mov     [rsp+68h+var_48], 0C000000Dh
0x180011e65  jmp     short loc_180011E18
0x180011e67  mov     ebx, 0C0000008h
0x180011e6c  mov     r9d, 0F06h
0x180011e72  mov     ecx, 0C0000008h
0x180011e77  jmp     loc_18009F95C
0x180011e7c  mov     ebx, 0C000042Ah
0x180011e81  mov     r9d, 0F26h
0x180011e87  mov     ecx, 0C000042Ah
0x180011e8c  jmp     loc_18009F95C
0x180011e91  mov     ebx, 0C0000206h
0x180011e96  mov     r9d, 0F1Ch
0x180011e9c  mov     ecx, 0C0000206h
0x180011ea1  jmp     loc_18009F95C
0x180011ea6  lea     rdx, aFunctionnamest; "FunctionNameString"
0x180011ead  mov     rcx, rsi; Str1
0x180011eb0  call    wcscmp_0
0x180011eb5  test    eax, eax
0x180011eb7  jnz     loc_18009F879
0x180011ebd  mov     eax, [rdi+8]
0x180011ec0  cmp     eax, 20015h
0x180011ec5  jnz     loc_18009F829
0x180011ecb  lea     rcx, [rdi+78h]
0x180011ecf  mov     r8d, ebx
0x180011ed2  mov     rdx, rbp
0x180011ed5  call    MSCryptCustomBufferUpdate
0x180011eda  mov     ebx, eax
0x180011edc  test    eax, eax
0x180011ede  jns     loc_18009F84D
0x180011ee4  mov     r9d, 0F37h
0x180011eea  jmp     loc_18009F822
0x18009f81c  mov     r9d, 0F6Dh
0x18009f822  mov     ecx, eax
0x18009f824  jmp     loc_18009F95C
0x18009f829  cmp     eax, 20016h
0x18009f82e  jnz     short loc_18009F85C
0x18009f830  lea     rcx, [rdi+78h]
0x18009f834  mov     r8d, ebx
0x18009f837  mov     rdx, rbp
0x18009f83a  call    MSCryptCustomBufferUpdate
0x18009f83f  mov     ebx, eax
0x18009f841  test    eax, eax
0x18009f843  jns     short loc_18009F84D
0x18009f845  mov     r9d, 0F45h
0x18009f84b  jmp     short loc_18009F822
0x18009f84d  mov     dword ptr [rdi+118h], 0
0x18009f857  jmp     loc_180011DCF
0x18009f85c  mov     r9d, 0F4Eh
0x18009f862  jmp     short loc_18009F86A
0x18009f864  mov     r9d, 0F92h
0x18009f86a  mov     ebx, 0C000000Dh
0x18009f86f  mov     ecx, 0C000000Dh
0x18009f874  jmp     loc_18009F95C
0x18009f879  lea     rdx, aCustomizations; "CustomizationString"
0x18009f880  mov     rcx, rsi; Str1
0x18009f883  call    wcscmp_0
0x18009f888  test    eax, eax
0x18009f88a  jnz     loc_18009F94C
0x18009f890  mov     eax, [rdi+8]
0x18009f893  cmp     eax, 20015h
0x18009f898  jnz     short loc_18009F8BD
0x18009f89a  lea     rcx, [rdi+0C8h]
0x18009f8a1  mov     r8d, ebx
0x18009f8a4  mov     rdx, rbp
0x18009f8a7  call    MSCryptCustomBufferUpdate
0x18009f8ac  mov     ebx, eax
0x18009f8ae  test    eax, eax
0x18009f8b0  jns     short loc_18009F84D
0x18009f8b2  mov     r9d, 0F5Fh
0x18009f8b8  jmp     loc_18009F822
0x18009f8bd  cmp     eax, 20016h
0x18009f8c2  jnz     short loc_18009F8E5
0x18009f8c4  lea     rcx, [rdi+0C8h]
0x18009f8cb  mov     r8d, ebx
0x18009f8ce  mov     rdx, rbp
0x18009f8d1  call    MSCryptCustomBufferUpdate
0x18009f8d6  mov     ebx, eax
0x18009f8d8  test    eax, eax
0x18009f8da  jns     loc_18009F84D
0x18009f8e0  jmp     loc_18009F81C
0x18009f8e5  cmp     eax, 20017h
0x18009f8ea  jnz     short loc_18009F90F
0x18009f8ec  lea     rcx, [rdi+1C0h]
0x18009f8f3  mov     r8d, ebx
0x18009f8f6  mov     rdx, rbp
0x18009f8f9  call    MSCryptCustomBufferUpdate
0x18009f8fe  mov     ebx, eax
0x18009f900  test    eax, eax
0x18009f902  jns     short loc_18009F93D
0x18009f904  mov     r9d, 0F7Bh
0x18009f90a  jmp     loc_18009F822
0x18009f90f  cmp     eax, 20018h
0x18009f914  jnz     loc_18009F864
0x18009f91a  lea     rcx, [rdi+1C0h]
0x18009f921  mov     r8d, ebx
0x18009f924  mov     rdx, rbp
0x18009f927  call    MSCryptCustomBufferUpdate
0x18009f92c  mov     ebx, eax
0x18009f92e  test    eax, eax
0x18009f930  jns     short loc_18009F93D
0x18009f932  mov     r9d, 0F89h
0x18009f938  jmp     loc_18009F822
0x18009f93d  mov     dword ptr [rdi+210h], 0
0x18009f947  jmp     loc_180011DCF
0x18009f94c  mov     ebx, 0C00000BBh
0x18009f951  mov     r9d, 0F9Ch
0x18009f957  mov     ecx, 0C00000BBh
0x18009f95c  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18009f963  lea     rdx, aStatus; "Status"
0x18009f96a  call    DebugTraceError
0x18009f96f  nop
0x18009f970  jmp     loc_180011DD1
```
