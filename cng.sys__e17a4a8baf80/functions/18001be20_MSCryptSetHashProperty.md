# MSCryptSetHashProperty

- ea: `0x18001be20`
- end: `0x18001bfcf`
- name: `MSCryptSetHashProperty`
- size: `431`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x18001be20`
- `0x18001bfe0`
- `0x18001c380`
- `0x180086880`
- `0x1800a4232`

## string_xrefs

- `0x18001bee4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18001bf31`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x1800a66fa`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

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
  v9 = (_DWORD *)validateMSCryptHash(a1, a2);
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
0x18001be20  push    rbx
0x18001be22  push    rbp
0x18001be23  push    rsi
0x18001be24  push    rdi
0x18001be25  sub     rsp, 48h
0x18001be29  cmp     [rsp+68h+arg_20], 0
0x18001be31  mov     rbp, r8
0x18001be34  mov     ebx, r9d
0x18001be37  mov     rsi, rdx
0x18001be3a  jnz     loc_18001BF0A
0x18001be40  call    validateMSCryptHash
0x18001be45  mov     rdi, rax
0x18001be48  test    rax, rax
0x18001be4b  jz      loc_18001BF47
0x18001be51  movzx   edx, word ptr [rdx]
0x18001be54  sub     edx, 49h ; 'I'
0x18001be57  jnz     short loc_18001BE6D
0x18001be59  movzx   edx, word ptr [rsi+2]
0x18001be5d  sub     edx, 56h ; 'V'
0x18001be60  jnz     short loc_18001BE6D
0x18001be62  movzx   edx, word ptr [rsi+4]
0x18001be66  xor     eax, eax
0x18001be68  movzx   ecx, ax
0x18001be6b  sub     edx, ecx
0x18001be6d  test    edx, edx
0x18001be6f  jnz     loc_18001BF86
0x18001be75  cmp     dword ptr [rdi+8], 20008h
0x18001be7c  jnz     short loc_18001BEBD
0x18001be7e  lea     eax, [rbx-0Ch]
0x18001be81  test    eax, eax
0x18001be83  jnz     loc_18001BF71
0x18001be89  cmp     [rdi+74h], eax
0x18001be8c  jnz     loc_18001BF5C
0x18001be92  mov     r9, rbx
0x18001be95  lea     rdx, [rdi+80h]
0x18001be9c  lea     rcx, [rdi+0AB0h]
0x18001bea3  call    SymCryptGcmInit
0x18001bea8  mov     dword ptr [rdi+74h], 1
0x18001beaf  xor     ebx, ebx
0x18001beb1  mov     eax, ebx
0x18001beb3  add     rsp, 48h
0x18001beb7  pop     rdi
0x18001beb8  pop     rsi
0x18001beb9  pop     rbp
0x18001beba  pop     rbx
0x18001bebb  retn
0x18001bebd  mov     ebx, 0C00000BBh
0x18001bec2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bec9  lea     rax, WPP_GLOBAL_Control
0x18001bed0  cmp     rcx, rax
0x18001bed3  jz      short loc_18001BEB1
0x18001bed5  mov     eax, [rcx+2Ch]
0x18001bed8  test    al, 1
0x18001beda  jz      short loc_18001BEB1
0x18001bedc  mov     [rsp+68h+var_38], 0F11h
0x18001bee4  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001beeb  mov     [rsp+68h+var_40], r8
0x18001bef0  mov     [rsp+68h+var_48], 0C00000BBh
0x18001bef8  mov     rcx, [rcx+18h]
0x18001befc  lea     r9, aStatus; "Status"
0x18001bf03  call    WPP_SF_sDsd
0x18001bf08  jmp     short loc_18001BEB1
0x18001bf0a  mov     ebx, 0C000000Dh
0x18001bf0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf16  lea     rax, WPP_GLOBAL_Control
0x18001bf1d  cmp     rcx, rax
0x18001bf20  jz      short loc_18001BEB1
0x18001bf22  mov     eax, [rcx+2Ch]
0x18001bf25  test    al, 1
0x18001bf27  jz      short loc_18001BEB1
0x18001bf29  mov     [rsp+68h+var_38], 0EFDh
0x18001bf31  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001bf38  mov     [rsp+68h+var_40], r8
0x18001bf3d  mov     [rsp+68h+var_48], 0C000000Dh
0x18001bf45  jmp     short loc_18001BEF8
0x18001bf47  mov     ebx, 0C0000008h
0x18001bf4c  mov     r9d, 0F06h
0x18001bf52  mov     ecx, 0C0000008h
0x18001bf57  jmp     loc_1800A66FA
0x18001bf5c  mov     ebx, 0C000042Ah
0x18001bf61  mov     r9d, 0F26h
0x18001bf67  mov     ecx, 0C000042Ah
0x18001bf6c  jmp     loc_1800A66FA
0x18001bf71  mov     ebx, 0C0000206h
0x18001bf76  mov     r9d, 0F1Ch
0x18001bf7c  mov     ecx, 0C0000206h
0x18001bf81  jmp     loc_1800A66FA
0x18001bf86  lea     rdx, aFunctionnamest; "FunctionNameString"
0x18001bf8d  mov     rcx, rsi; Str1
0x18001bf90  call    wcscmp_0
0x18001bf95  test    eax, eax
0x18001bf97  jnz     loc_1800A6617
0x18001bf9d  mov     eax, [rdi+8]
0x18001bfa0  cmp     eax, 20015h
0x18001bfa5  jnz     loc_1800A65C7
0x18001bfab  lea     rcx, [rdi+78h]
0x18001bfaf  mov     r8d, ebx
0x18001bfb2  mov     rdx, rbp
0x18001bfb5  call    MSCryptCustomBufferUpdate
0x18001bfba  mov     ebx, eax
0x18001bfbc  test    eax, eax
0x18001bfbe  jns     loc_1800A65EB
0x18001bfc4  mov     r9d, 0F37h
0x18001bfca  jmp     loc_1800A65C0
0x1800a65ba  mov     r9d, 0F6Dh
0x1800a65c0  mov     ecx, eax
0x1800a65c2  jmp     loc_1800A66FA
0x1800a65c7  cmp     eax, 20016h
0x1800a65cc  jnz     short loc_1800A65FA
0x1800a65ce  lea     rcx, [rdi+78h]
0x1800a65d2  mov     r8d, ebx
0x1800a65d5  mov     rdx, rbp
0x1800a65d8  call    MSCryptCustomBufferUpdate
0x1800a65dd  mov     ebx, eax
0x1800a65df  test    eax, eax
0x1800a65e1  jns     short loc_1800A65EB
0x1800a65e3  mov     r9d, 0F45h
0x1800a65e9  jmp     short loc_1800A65C0
0x1800a65eb  mov     dword ptr [rdi+118h], 0
0x1800a65f5  jmp     loc_18001BEAF
0x1800a65fa  mov     r9d, 0F4Eh
0x1800a6600  jmp     short loc_1800A6608
0x1800a6602  mov     r9d, 0F92h
0x1800a6608  mov     ebx, 0C000000Dh
0x1800a660d  mov     ecx, 0C000000Dh
0x1800a6612  jmp     loc_1800A66FA
0x1800a6617  lea     rdx, aCustomizations; "CustomizationString"
0x1800a661e  mov     rcx, rsi; Str1
0x1800a6621  call    wcscmp_0
0x1800a6626  test    eax, eax
0x1800a6628  jnz     loc_1800A66EA
0x1800a662e  mov     eax, [rdi+8]
0x1800a6631  cmp     eax, 20015h
0x1800a6636  jnz     short loc_1800A665B
0x1800a6638  lea     rcx, [rdi+0C8h]
0x1800a663f  mov     r8d, ebx
0x1800a6642  mov     rdx, rbp
0x1800a6645  call    MSCryptCustomBufferUpdate
0x1800a664a  mov     ebx, eax
0x1800a664c  test    eax, eax
0x1800a664e  jns     short loc_1800A65EB
0x1800a6650  mov     r9d, 0F5Fh
0x1800a6656  jmp     loc_1800A65C0
0x1800a665b  cmp     eax, 20016h
0x1800a6660  jnz     short loc_1800A6683
0x1800a6662  lea     rcx, [rdi+0C8h]
0x1800a6669  mov     r8d, ebx
0x1800a666c  mov     rdx, rbp
0x1800a666f  call    MSCryptCustomBufferUpdate
0x1800a6674  mov     ebx, eax
0x1800a6676  test    eax, eax
0x1800a6678  jns     loc_1800A65EB
0x1800a667e  jmp     loc_1800A65BA
0x1800a6683  cmp     eax, 20017h
0x1800a6688  jnz     short loc_1800A66AD
0x1800a668a  lea     rcx, [rdi+1C0h]
0x1800a6691  mov     r8d, ebx
0x1800a6694  mov     rdx, rbp
0x1800a6697  call    MSCryptCustomBufferUpdate
0x1800a669c  mov     ebx, eax
0x1800a669e  test    eax, eax
0x1800a66a0  jns     short loc_1800A66DB
0x1800a66a2  mov     r9d, 0F7Bh
0x1800a66a8  jmp     loc_1800A65C0
0x1800a66ad  cmp     eax, 20018h
0x1800a66b2  jnz     loc_1800A6602
0x1800a66b8  lea     rcx, [rdi+1C0h]
0x1800a66bf  mov     r8d, ebx
0x1800a66c2  mov     rdx, rbp
0x1800a66c5  call    MSCryptCustomBufferUpdate
0x1800a66ca  mov     ebx, eax
0x1800a66cc  test    eax, eax
0x1800a66ce  jns     short loc_1800A66DB
0x1800a66d0  mov     r9d, 0F89h
0x1800a66d6  jmp     loc_1800A65C0
0x1800a66db  mov     dword ptr [rdi+210h], 0
0x1800a66e5  jmp     loc_18001BEAF
0x1800a66ea  mov     ebx, 0C00000BBh
0x1800a66ef  mov     r9d, 0F9Ch
0x1800a66f5  mov     ecx, 0C00000BBh
0x1800a66fa  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a6701  lea     rdx, aStatus; "Status"
0x1800a6708  call    DebugTraceError
0x1800a670d  nop
0x1800a670e  jmp     loc_18001BEB1
```
