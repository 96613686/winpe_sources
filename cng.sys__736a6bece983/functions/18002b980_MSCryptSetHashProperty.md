# MSCryptSetHashProperty

- ea: `0x18002b980`
- end: `0x18002bb2f`
- name: `MSCryptSetHashProperty`
- size: `431`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18002b980`
- `0x18002bb40`
- `0x18002bee0`
- `0x18007d670`
- `0x18009f616`

## string_xrefs

- `0x18002ba44`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x18002ba91`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`
- `0x1800a2798`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

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
0x18002b980  push    rbx
0x18002b982  push    rbp
0x18002b983  push    rsi
0x18002b984  push    rdi
0x18002b985  sub     rsp, 48h
0x18002b989  cmp     [rsp+68h+arg_20], 0
0x18002b991  mov     rbp, r8
0x18002b994  mov     ebx, r9d
0x18002b997  mov     rsi, rdx
0x18002b99a  jnz     loc_18002BA6A
0x18002b9a0  call    validateMSCryptHash
0x18002b9a5  mov     rdi, rax
0x18002b9a8  test    rax, rax
0x18002b9ab  jz      loc_18002BAA7
0x18002b9b1  movzx   edx, word ptr [rdx]
0x18002b9b4  sub     edx, 49h ; 'I'
0x18002b9b7  jnz     short loc_18002B9CD
0x18002b9b9  movzx   edx, word ptr [rsi+2]
0x18002b9bd  sub     edx, 56h ; 'V'
0x18002b9c0  jnz     short loc_18002B9CD
0x18002b9c2  movzx   edx, word ptr [rsi+4]
0x18002b9c6  xor     eax, eax
0x18002b9c8  movzx   ecx, ax
0x18002b9cb  sub     edx, ecx
0x18002b9cd  test    edx, edx
0x18002b9cf  jnz     loc_18002BAE6
0x18002b9d5  cmp     dword ptr [rdi+8], 20008h
0x18002b9dc  jnz     short loc_18002BA1D
0x18002b9de  lea     eax, [rbx-0Ch]
0x18002b9e1  test    eax, eax
0x18002b9e3  jnz     loc_18002BAD1
0x18002b9e9  cmp     [rdi+74h], eax
0x18002b9ec  jnz     loc_18002BABC
0x18002b9f2  mov     r9, rbx
0x18002b9f5  lea     rdx, [rdi+80h]
0x18002b9fc  lea     rcx, [rdi+0AB0h]
0x18002ba03  call    SymCryptGcmInit
0x18002ba08  mov     dword ptr [rdi+74h], 1
0x18002ba0f  xor     ebx, ebx
0x18002ba11  mov     eax, ebx
0x18002ba13  add     rsp, 48h
0x18002ba17  pop     rdi
0x18002ba18  pop     rsi
0x18002ba19  pop     rbp
0x18002ba1a  pop     rbx
0x18002ba1b  retn
0x18002ba1d  mov     ebx, 0C00000BBh
0x18002ba22  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba29  lea     rax, WPP_GLOBAL_Control
0x18002ba30  cmp     rcx, rax
0x18002ba33  jz      short loc_18002BA11
0x18002ba35  mov     eax, [rcx+2Ch]
0x18002ba38  test    al, 1
0x18002ba3a  jz      short loc_18002BA11
0x18002ba3c  mov     [rsp+68h+var_38], 0F11h
0x18002ba44  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002ba4b  mov     [rsp+68h+var_40], r8
0x18002ba50  mov     [rsp+68h+var_48], 0C00000BBh
0x18002ba58  mov     rcx, [rcx+18h]
0x18002ba5c  lea     r9, aStatus; "Status"
0x18002ba63  call    WPP_SF_sDsd
0x18002ba68  jmp     short loc_18002BA11
0x18002ba6a  mov     ebx, 0C000000Dh
0x18002ba6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba76  lea     rax, WPP_GLOBAL_Control
0x18002ba7d  cmp     rcx, rax
0x18002ba80  jz      short loc_18002BA11
0x18002ba82  mov     eax, [rcx+2Ch]
0x18002ba85  test    al, 1
0x18002ba87  jz      short loc_18002BA11
0x18002ba89  mov     [rsp+68h+var_38], 0EFDh
0x18002ba91  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002ba98  mov     [rsp+68h+var_40], r8
0x18002ba9d  mov     [rsp+68h+var_48], 0C000000Dh
0x18002baa5  jmp     short loc_18002BA58
0x18002baa7  mov     ebx, 0C0000008h
0x18002baac  mov     r9d, 0F06h
0x18002bab2  mov     ecx, 0C0000008h
0x18002bab7  jmp     loc_1800A2798
0x18002babc  mov     ebx, 0C000042Ah
0x18002bac1  mov     r9d, 0F26h
0x18002bac7  mov     ecx, 0C000042Ah
0x18002bacc  jmp     loc_1800A2798
0x18002bad1  mov     ebx, 0C0000206h
0x18002bad6  mov     r9d, 0F1Ch
0x18002badc  mov     ecx, 0C0000206h
0x18002bae1  jmp     loc_1800A2798
0x18002bae6  lea     rdx, aFunctionnamest; "FunctionNameString"
0x18002baed  mov     rcx, rsi; Str1
0x18002baf0  call    wcscmp_0
0x18002baf5  test    eax, eax
0x18002baf7  jnz     loc_1800A26B5
0x18002bafd  mov     eax, [rdi+8]
0x18002bb00  cmp     eax, 20015h
0x18002bb05  jnz     loc_1800A2665
0x18002bb0b  lea     rcx, [rdi+78h]
0x18002bb0f  mov     r8d, ebx
0x18002bb12  mov     rdx, rbp
0x18002bb15  call    MSCryptCustomBufferUpdate
0x18002bb1a  mov     ebx, eax
0x18002bb1c  test    eax, eax
0x18002bb1e  jns     loc_1800A2689
0x18002bb24  mov     r9d, 0F37h
0x18002bb2a  jmp     loc_1800A265E
0x1800a2658  mov     r9d, 0F6Dh
0x1800a265e  mov     ecx, eax
0x1800a2660  jmp     loc_1800A2798
0x1800a2665  cmp     eax, 20016h
0x1800a266a  jnz     short loc_1800A2698
0x1800a266c  lea     rcx, [rdi+78h]
0x1800a2670  mov     r8d, ebx
0x1800a2673  mov     rdx, rbp
0x1800a2676  call    MSCryptCustomBufferUpdate
0x1800a267b  mov     ebx, eax
0x1800a267d  test    eax, eax
0x1800a267f  jns     short loc_1800A2689
0x1800a2681  mov     r9d, 0F45h
0x1800a2687  jmp     short loc_1800A265E
0x1800a2689  mov     dword ptr [rdi+118h], 0
0x1800a2693  jmp     loc_18002BA0F
0x1800a2698  mov     r9d, 0F4Eh
0x1800a269e  jmp     short loc_1800A26A6
0x1800a26a0  mov     r9d, 0F92h
0x1800a26a6  mov     ebx, 0C000000Dh
0x1800a26ab  mov     ecx, 0C000000Dh
0x1800a26b0  jmp     loc_1800A2798
0x1800a26b5  lea     rdx, aCustomizations; "CustomizationString"
0x1800a26bc  mov     rcx, rsi; Str1
0x1800a26bf  call    wcscmp_0
0x1800a26c4  test    eax, eax
0x1800a26c6  jnz     loc_1800A2788
0x1800a26cc  mov     eax, [rdi+8]
0x1800a26cf  cmp     eax, 20015h
0x1800a26d4  jnz     short loc_1800A26F9
0x1800a26d6  lea     rcx, [rdi+0C8h]
0x1800a26dd  mov     r8d, ebx
0x1800a26e0  mov     rdx, rbp
0x1800a26e3  call    MSCryptCustomBufferUpdate
0x1800a26e8  mov     ebx, eax
0x1800a26ea  test    eax, eax
0x1800a26ec  jns     short loc_1800A2689
0x1800a26ee  mov     r9d, 0F5Fh
0x1800a26f4  jmp     loc_1800A265E
0x1800a26f9  cmp     eax, 20016h
0x1800a26fe  jnz     short loc_1800A2721
0x1800a2700  lea     rcx, [rdi+0C8h]
0x1800a2707  mov     r8d, ebx
0x1800a270a  mov     rdx, rbp
0x1800a270d  call    MSCryptCustomBufferUpdate
0x1800a2712  mov     ebx, eax
0x1800a2714  test    eax, eax
0x1800a2716  jns     loc_1800A2689
0x1800a271c  jmp     loc_1800A2658
0x1800a2721  cmp     eax, 20017h
0x1800a2726  jnz     short loc_1800A274B
0x1800a2728  lea     rcx, [rdi+1C0h]
0x1800a272f  mov     r8d, ebx
0x1800a2732  mov     rdx, rbp
0x1800a2735  call    MSCryptCustomBufferUpdate
0x1800a273a  mov     ebx, eax
0x1800a273c  test    eax, eax
0x1800a273e  jns     short loc_1800A2779
0x1800a2740  mov     r9d, 0F7Bh
0x1800a2746  jmp     loc_1800A265E
0x1800a274b  cmp     eax, 20018h
0x1800a2750  jnz     loc_1800A26A0
0x1800a2756  lea     rcx, [rdi+1C0h]
0x1800a275d  mov     r8d, ebx
0x1800a2760  mov     rdx, rbp
0x1800a2763  call    MSCryptCustomBufferUpdate
0x1800a2768  mov     ebx, eax
0x1800a276a  test    eax, eax
0x1800a276c  jns     short loc_1800A2779
0x1800a276e  mov     r9d, 0F89h
0x1800a2774  jmp     loc_1800A265E
0x1800a2779  mov     dword ptr [rdi+210h], 0
0x1800a2783  jmp     loc_18002BA0F
0x1800a2788  mov     ebx, 0C00000BBh
0x1800a278d  mov     r9d, 0F9Ch
0x1800a2793  mov     ecx, 0C00000BBh
0x1800a2798  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a279f  lea     rdx, aStatus; "Status"
0x1800a27a6  call    DebugTraceError
0x1800a27ab  nop
0x1800a27ac  jmp     loc_18002BA11
```
