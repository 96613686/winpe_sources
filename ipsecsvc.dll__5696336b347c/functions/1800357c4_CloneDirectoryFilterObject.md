# CloneDirectoryFilterObject

- ea: `0x1800357c4`
- end: `0x180035a00`
- name: `CloneDirectoryFilterObject`
- size: `572`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180035a08`

## callees

- `0x180006f00`
- `0x18000c828`
- `0x18000e510`
- `0x1800357c4`
- `0x180036a94`
- `0x180036bd0`
- `0x180036c54`
- `0x180042afc`

## pseudocode

```c
__int64 __fastcall CloneDirectoryFilterObject(__int64 a1, __int64 *a2)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  unsigned int v6; // edi
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  unsigned __int16 *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // r9
  unsigned __int16 *v12; // rcx
  __int64 v13; // rax
  unsigned __int16 *v14; // rcx
  __int64 v15; // rax
  void *v16; // rcx
  __int64 v17; // rcx

  v4 = IpsecAllocMem(72);
  v5 = v4;
  if ( !v4 )
  {
    v6 = 14;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, 14);
    goto LABEL_40;
  }
  if ( *(_QWORD *)a1 )
  {
    v6 = CopyDSToFQRegString(*(_QWORD *)a1, 0, v4);
    if ( v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_39;
      v8 = 107;
      goto LABEL_37;
    }
  }
  else
  {
    v6 = 0;
  }
  v9 = *(unsigned __int16 **)(a1 + 64);
  if ( v9 )
  {
    v10 = IpsecAllocStr(v9);
    *(_QWORD *)(v5 + 64) = v10;
    if ( !v10 )
    {
      v11 = 14;
      v6 = 14;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_39;
      v8 = 108;
      goto LABEL_38;
    }
  }
  v12 = *(unsigned __int16 **)(a1 + 8);
  if ( v12 )
  {
    v13 = IpsecAllocStr(v12);
    *(_QWORD *)(v5 + 8) = v13;
    if ( !v13 )
    {
      v11 = 14;
      v6 = 14;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_39;
      v8 = 109;
      goto LABEL_38;
    }
  }
  v14 = *(unsigned __int16 **)(a1 + 16);
  if ( v14 )
  {
    v15 = IpsecAllocStr(v14);
    *(_QWORD *)(v5 + 16) = v15;
    if ( !v15 )
    {
      v11 = 14;
      v6 = 14;
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_39;
      v8 = 110;
      goto LABEL_38;
    }
  }
  *(_DWORD *)(v5 + 24) = *(_DWORD *)(a1 + 24);
  v16 = *(void **)(a1 + 32);
  if ( v16 )
  {
    v6 = CopyBinaryValue(v16, *(unsigned int *)(a1 + 40));
    if ( v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_39;
      v8 = 111;
      goto LABEL_37;
    }
    *(_DWORD *)(v5 + 40) = *(_DWORD *)(a1 + 40);
  }
  v17 = *(_QWORD *)(a1 + 48);
  if ( !v17 || (v6 = CloneNFAReferencesDSToRegistry(v17, *(unsigned int *)(a1 + 56), v5 + 48, v5 + 56)) == 0 )
  {
    *(_DWORD *)(v5 + 60) = *(_DWORD *)(a1 + 60);
    *a2 = v5;
    return v6;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
    goto LABEL_39;
  v8 = 112;
LABEL_37:
  v11 = v6;
LABEL_38:
  WPP_SF_d(v7[2], v8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v11);
LABEL_39:
  FreeIpsecFilterObject((LPVOID)v5);
LABEL_40:
  *a2 = 0;
  return v6;
}

```

## disassembly

```asm
0x1800357c4  push    rbx
0x1800357c6  push    rsi
0x1800357c7  push    rdi
0x1800357c8  push    r14
0x1800357ca  sub     rsp, 28h
0x1800357ce  mov     rbx, rcx
0x1800357d1  mov     r14, rdx
0x1800357d4  mov     ecx, 48h ; 'H'
0x1800357d9  call    IpsecAllocMem
0x1800357de  mov     rsi, rax
0x1800357e1  test    rax, rax
0x1800357e4  jnz     short loc_180035826
0x1800357e6  lea     r9d, [rax+0Eh]
0x1800357ea  mov     edi, r9d
0x1800357ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800357f4  lea     rax, WPP_GLOBAL_Control
0x1800357fb  cmp     rcx, rax
0x1800357fe  jz      loc_1800359E2
0x180035804  test    byte ptr [rcx+1Ch], 10h
0x180035808  jz      loc_1800359E2
0x18003580e  mov     rcx, [rcx+10h]
0x180035812  lea     edx, [rsi+6Ah]
0x180035815  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x18003581c  call    WPP_SF_d
0x180035821  jmp     loc_1800359E2
0x180035826  mov     rcx, [rbx]
0x180035829  test    rcx, rcx
0x18003582c  jz      short loc_180035869
0x18003582e  mov     r8, rsi
0x180035831  xor     edx, edx
0x180035833  call    CopyDSToFQRegString
0x180035838  mov     edi, eax
0x18003583a  test    eax, eax
0x18003583c  jz      short loc_18003586B
0x18003583e  mov     rcx, cs:WPP_GLOBAL_Control
0x180035845  lea     rax, WPP_GLOBAL_Control
0x18003584c  cmp     rcx, rax
0x18003584f  jz      loc_1800359DA
0x180035855  test    byte ptr [rcx+1Ch], 10h
0x180035859  jz      loc_1800359DA
0x18003585f  mov     edx, 6Bh ; 'k'
0x180035864  jmp     loc_1800359C7
0x180035869  xor     edi, edi
0x18003586b  mov     rcx, [rbx+40h]; unsigned __int16 *
0x18003586f  test    rcx, rcx
0x180035872  jz      short loc_1800358B3
0x180035874  call    IpsecAllocStr
0x180035879  mov     [rsi+40h], rax
0x18003587d  test    rax, rax
0x180035880  jnz     short loc_1800358B3
0x180035882  lea     r9d, [rax+0Eh]
0x180035886  mov     edi, r9d
0x180035889  mov     rcx, cs:WPP_GLOBAL_Control
0x180035890  lea     rax, WPP_GLOBAL_Control
0x180035897  cmp     rcx, rax
0x18003589a  jz      loc_1800359DA
0x1800358a0  test    byte ptr [rcx+1Ch], 10h
0x1800358a4  jz      loc_1800359DA
0x1800358aa  lea     edx, [r9+5Eh]
0x1800358ae  jmp     loc_1800359CA
0x1800358b3  mov     rcx, [rbx+8]; unsigned __int16 *
0x1800358b7  test    rcx, rcx
0x1800358ba  jz      short loc_1800358FB
0x1800358bc  call    IpsecAllocStr
0x1800358c1  mov     [rsi+8], rax
0x1800358c5  test    rax, rax
0x1800358c8  jnz     short loc_1800358FB
0x1800358ca  lea     r9d, [rax+0Eh]
0x1800358ce  mov     edi, r9d
0x1800358d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800358d8  lea     rax, WPP_GLOBAL_Control
0x1800358df  cmp     rcx, rax
0x1800358e2  jz      loc_1800359DA
0x1800358e8  test    byte ptr [rcx+1Ch], 10h
0x1800358ec  jz      loc_1800359DA
0x1800358f2  lea     edx, [r9+5Fh]
0x1800358f6  jmp     loc_1800359CA
0x1800358fb  mov     rcx, [rbx+10h]; unsigned __int16 *
0x1800358ff  test    rcx, rcx
0x180035902  jz      short loc_180035943
0x180035904  call    IpsecAllocStr
0x180035909  mov     [rsi+10h], rax
0x18003590d  test    rax, rax
0x180035910  jnz     short loc_180035943
0x180035912  lea     r9d, [rax+0Eh]
0x180035916  mov     edi, r9d
0x180035919  mov     rcx, cs:WPP_GLOBAL_Control
0x180035920  lea     rax, WPP_GLOBAL_Control
0x180035927  cmp     rcx, rax
0x18003592a  jz      loc_1800359DA
0x180035930  test    byte ptr [rcx+1Ch], 10h
0x180035934  jz      loc_1800359DA
0x18003593a  lea     edx, [r9+60h]
0x18003593e  jmp     loc_1800359CA
0x180035943  mov     eax, [rbx+18h]
0x180035946  mov     [rsi+18h], eax
0x180035949  mov     rcx, [rbx+20h]; Src
0x18003594d  test    rcx, rcx
0x180035950  jz      short loc_18003598A
0x180035952  mov     edx, [rbx+28h]; Size
0x180035955  lea     r8, [rsi+20h]
0x180035959  call    CopyBinaryValue
0x18003595e  mov     edi, eax
0x180035960  test    eax, eax
0x180035962  jz      short loc_180035984
0x180035964  mov     rcx, cs:WPP_GLOBAL_Control
0x18003596b  lea     rax, WPP_GLOBAL_Control
0x180035972  cmp     rcx, rax
0x180035975  jz      short loc_1800359DA
0x180035977  test    byte ptr [rcx+1Ch], 10h
0x18003597b  jz      short loc_1800359DA
0x18003597d  mov     edx, 6Fh ; 'o'
0x180035982  jmp     short loc_1800359C7
0x180035984  mov     eax, [rbx+28h]
0x180035987  mov     [rsi+28h], eax
0x18003598a  mov     rcx, [rbx+30h]
0x18003598e  test    rcx, rcx
0x180035991  jz      short loc_1800359EB
0x180035993  mov     edx, [rbx+38h]
0x180035996  lea     r9, [rsi+38h]
0x18003599a  lea     r8, [rsi+30h]
0x18003599e  call    CloneNFAReferencesDSToRegistry
0x1800359a3  mov     edi, eax
0x1800359a5  test    eax, eax
0x1800359a7  jz      short loc_1800359EB
0x1800359a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800359b0  lea     rax, WPP_GLOBAL_Control
0x1800359b7  cmp     rcx, rax
0x1800359ba  jz      short loc_1800359DA
0x1800359bc  test    byte ptr [rcx+1Ch], 10h
0x1800359c0  jz      short loc_1800359DA
0x1800359c2  mov     edx, 70h ; 'p'
0x1800359c7  mov     r9d, edi
0x1800359ca  mov     rcx, [rcx+10h]
0x1800359ce  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x1800359d5  call    WPP_SF_d
0x1800359da  mov     rcx, rsi; lpMem
0x1800359dd  call    FreeIpsecFilterObject
0x1800359e2  mov     qword ptr [r14], 0
0x1800359e9  jmp     short loc_1800359F4
0x1800359eb  mov     eax, [rbx+3Ch]
0x1800359ee  mov     [rsi+3Ch], eax
0x1800359f1  mov     [r14], rsi
0x1800359f4  mov     eax, edi
0x1800359f6  add     rsp, 28h
0x1800359fa  pop     r14
0x1800359fc  pop     rdi
0x1800359fd  pop     rsi
0x1800359fe  pop     rbx
0x1800359ff  retn
```
