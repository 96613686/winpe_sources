# MRxSmb2Write

- ea: `0x140055bd0`
- end: `0x140055ea2`
- name: `MRxSmb2Write`
- size: `722`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x140014650`
- `0x140014a00`
- `0x14002fb78`
- `0x140055bd0`

## import_xrefs

- `mrxsmb!SmbCeInitiateExchange` at `0x140055dc4`
- `mrxsmb!SmbCeInitiateExchange` at `0x140055dc4`
- `mrxsmb!SmbCeInitializeExchange` at `0x140055ce0`
- `mrxsmb!SmbCeInitializeExchange` at `0x140055ce0`

## pseudocode

```c
__int64 __fastcall MRxSmb2Write(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rdi
  __int64 v4; // rsi
  __int64 v5; // rbp
  __int64 v6; // r15
  __int64 v7; // rax
  __int64 v8; // rcx
  int v9; // edx
  __int64 v10; // rax
  unsigned int v11; // edi
  __int64 result; // rax
  __int64 v13; // rax
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int32 v18; // r14d
  __int64 v19; // [rsp+70h] [rbp+8h] BYREF

  v19 = 0;
  if ( !*(_DWORD *)(a1 + 568) )
  {
    result = 0;
    *(_DWORD *)(a1 + 176) = 0;
    *(_QWORD *)(a1 + 184) = 0;
    return result;
  }
  v2 = *(_QWORD *)(a1 + 72);
  v3 = a1 + 56;
  v4 = *(_QWORD *)(*(_QWORD *)(v2 + 40) + 40LL);
  v5 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 120LL);
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 136LL);
  *(_BYTE *)(*(_QWORD *)(v2 + 48) + 320LL) = 1;
  if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 136LL) + 81LL) )
    Smb2InvalidateFileInfoCacheEntry(a1, *(_QWORD *)(v4 + 424) + 376LL);
  v7 = *(_QWORD *)(*(_QWORD *)v3 + 288LL);
  if ( v7 )
  {
    v17 = *(_QWORD *)(v7 + 136);
    if ( v17 )
    {
      v18 = *(_DWORD *)(v17 + 88);
      if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v3 + 136LL) + 84LL) == v18 )
        goto LABEL_5;
      v3 = a1 + 56;
    }
    else
    {
      v18 = 0;
    }
    Smb2InvalidateSingleFileInDirInfoCache(a1, *(_QWORD *)(v4 + 424) + 1112LL);
    _InterlockedExchange((volatile __int32 *)(*(_QWORD *)(*(_QWORD *)v3 + 136LL) + 84LL), v18);
  }
LABEL_5:
  v8 = *(_QWORD *)(v4 + 416);
  v9 = *(_DWORD *)(v8 + 4);
  if ( (v9 & 8) == 0 )
  {
    v10 = *(_QWORD *)(v8 + 384);
    if ( *(_QWORD *)(v10 + 576) )
    {
      if ( (*(_DWORD *)(v10 + 4) & 1) != 0 && (v9 & 3) == 0 )
        Smb2TryToEstablishMultipleChannelsImpl((PVOID)v8);
    }
  }
  v11 = ((unsigned int)(*(_DWORD *)(a1 + 568) - 1) >> 16) + 1;
  if ( v11 > 1 && *(_BYTE *)(v5 + 77) == 1 )
  {
    *(_DWORD *)(a1 + 176) = -1073741811;
    result = 3221225485LL;
    *(_QWORD *)(a1 + 184) = 0;
  }
  else
  {
    result = SmbCeInitializeExchange(&v19, a1, 0, 0, 0, v4, 8 * v11 + 2528, &WriteDispatch);
    if ( !(_DWORD)result )
    {
      *(_DWORD *)(v19 + 64) = 1;
      if ( v11 > 1 )
        _InterlockedOr((volatile signed __int32 *)(v19 + 68), 0x1000u);
      if ( (*(_BYTE *)(a1 + 522) & 8) != 0 )
        _InterlockedOr((volatile signed __int32 *)(v19 + 68), 0x40000u);
      *(_DWORD *)(v19 + 1052) = v11;
      *(_BYTE *)(v19 + 1048) = *(_BYTE *)(v5 + 77);
      v13 = v19;
      *(_QWORD *)(v19 + 2488) = 0;
      *(_QWORD *)(v13 + 2496) = 0;
      *(_QWORD *)(v13 + 2504) = 0;
      *(_QWORD *)(v13 + 2512) = 0;
      *(_DWORD *)(v13 + 2520) = 0;
      *(_WORD *)(v13 + 2524) = 0;
      v14 = 0;
      v15 = v19;
      if ( *(_DWORD *)(v19 + 1052) )
      {
        do
        {
          v16 = v14++;
          *(_DWORD *)(v15 + 8 * v16 + 2528) = -1;
          *(_DWORD *)(v15 + 8 * v16 + 2532) = 0;
        }
        while ( v14 < *(_DWORD *)(v15 + 1052) );
        v15 = v19;
      }
      if ( *(_BYTE *)(v5 + 77) == 1 )
        _InterlockedOr((volatile signed __int32 *)(v15 + 68), 0x40u);
      *(_QWORD *)(v19 + 504) = *(_QWORD *)(v6 + 96);
      return SmbCeInitiateExchange(v19);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140055bd0  mov     rax, rsp
0x140055bd3  push    rbx
0x140055bd4  push    r12
0x140055bd6  sub     rsp, 58h
0x140055bda  xor     r12d, r12d
0x140055bdd  mov     rbx, rcx
0x140055be0  mov     [rax+8], r12
0x140055be4  cmp     [rcx+238h], r12d
0x140055beb  jz      loc_140055E48
0x140055bf1  mov     rcx, [rcx+48h]
0x140055bf5  mov     [rax+10h], rbp
0x140055bf9  mov     [rax+18h], rsi
0x140055bfd  mov     [rax-18h], rdi
0x140055c01  lea     rdi, [rbx+38h]
0x140055c05  mov     [rax-20h], r14
0x140055c09  mov     [rax-28h], r15
0x140055c0d  mov     rax, [rcx+28h]
0x140055c11  mov     rsi, [rax+28h]
0x140055c15  mov     rax, [rdi]
0x140055c18  mov     rbp, [rax+78h]
0x140055c1c  mov     r15, [rax+88h]
0x140055c23  mov     rax, [rcx+30h]
0x140055c27  mov     byte ptr [rax+140h], 1
0x140055c2e  mov     rax, [rdi]
0x140055c31  mov     rcx, [rax+88h]
0x140055c38  nop
0x140055c39  movzx   eax, byte ptr [rcx+51h]
0x140055c3d  nop
0x140055c3e  test    al, al
0x140055c40  jz      loc_140055E80
0x140055c46  mov     rdx, [rsi+1A8h]
0x140055c4d  mov     rcx, rbx
0x140055c50  add     rdx, 178h
0x140055c57  call    Smb2InvalidateFileInfoCacheEntry
0x140055c5c  lea     rdx, [rbx+38h]
0x140055c60  mov     rcx, [rdi]
0x140055c63  mov     rax, [rcx+120h]
0x140055c6a  test    rax, rax
0x140055c6d  jnz     loc_140055E12
0x140055c73  mov     rcx, [rsi+1A0h]; pContext
0x140055c7a  mov     r14, [rsp+68h+var_20]
0x140055c7f  mov     edx, [rcx+4]
0x140055c82  test    dl, 8
0x140055c85  jnz     short loc_140055C9B
0x140055c87  mov     rax, [rcx+180h]
0x140055c8e  cmp     [rax+240h], r12
0x140055c95  jnz     loc_140055E62
0x140055c9b  mov     edi, [rbx+238h]
0x140055ca1  dec     edi
0x140055ca3  shr     edi, 10h
0x140055ca6  inc     edi
0x140055ca8  cmp     edi, 1
0x140055cab  ja      loc_140055DF0
0x140055cb1  lea     rcx, WriteDispatch
0x140055cb8  xor     r9d, r9d
0x140055cbb  mov     [rsp+68h+var_30], rcx
0x140055cc0  lea     eax, ds:9E0h[rdi*8]
0x140055cc7  mov     [rsp+68h+var_38], eax
0x140055ccb  lea     rcx, [rsp+68h+arg_0]
0x140055cd0  mov     [rsp+68h+var_40], rsi
0x140055cd5  xor     r8d, r8d
0x140055cd8  mov     rdx, rbx
0x140055cdb  mov     [rsp+68h+var_48], r12
0x140055ce0  call    cs:__imp_SmbCeInitializeExchange
0x140055ce7  nop     dword ptr [rax+rax+00h]
0x140055cec  test    eax, eax
0x140055cee  jnz     loc_140055DD0
0x140055cf4  mov     rax, [rsp+68h+arg_0]
0x140055cf9  mov     dword ptr [rax+40h], 1
0x140055d00  cmp     edi, 1
0x140055d03  jbe     short loc_140055D12
0x140055d05  mov     rax, [rsp+68h+arg_0]
0x140055d0a  lock or dword ptr [rax+44h], 1000h
0x140055d12  test    byte ptr [rbx+20Ah], 8
0x140055d19  jnz     loc_140055E90
0x140055d1f  mov     rax, [rsp+68h+arg_0]
0x140055d24  mov     [rax+41Ch], edi
0x140055d2a  mov     rax, [rsp+68h+arg_0]
0x140055d2f  movzx   ecx, byte ptr [rbp+4Dh]
0x140055d33  mov     [rax+418h], cl
0x140055d39  mov     rax, [rsp+68h+arg_0]
0x140055d3e  mov     [rax+9B8h], r12
0x140055d45  mov     [rax+9C0h], r12
0x140055d4c  mov     [rax+9C8h], r12
0x140055d53  mov     [rax+9D0h], r12
0x140055d5a  mov     [rax+9D8h], r12d
0x140055d61  mov     [rax+9DCh], r12w
0x140055d69  mov     eax, r12d
0x140055d6c  mov     rdx, [rsp+68h+arg_0]
0x140055d71  cmp     [rdx+41Ch], r12d
0x140055d78  jbe     short loc_140055DA4
0x140055d7a  nop     word ptr [rax+rax+00h]
0x140055d80  mov     ecx, eax
0x140055d82  inc     eax
0x140055d84  mov     dword ptr [rdx+rcx*8+9E0h], 0FFFFFFFFh
0x140055d8f  mov     [rdx+rcx*8+9E4h], r12d
0x140055d97  cmp     eax, [rdx+41Ch]
0x140055d9d  jb      short loc_140055D80
0x140055d9f  mov     rdx, [rsp+68h+arg_0]
0x140055da4  cmp     byte ptr [rbp+4Dh], 1
0x140055da8  jnz     short loc_140055DAF
0x140055daa  lock or dword ptr [rdx+44h], 40h
0x140055daf  mov     rcx, [r15+60h]
0x140055db3  mov     rax, [rsp+68h+arg_0]
0x140055db8  mov     [rax+1F8h], rcx
0x140055dbf  mov     rcx, [rsp+68h+arg_0]
0x140055dc4  call    cs:__imp_SmbCeInitiateExchange
0x140055dcb  nop     dword ptr [rax+rax+00h]
0x140055dd0  mov     rdi, [rsp+68h+var_18]
0x140055dd5  mov     rsi, [rsp+68h+arg_10]
0x140055ddd  mov     rbp, [rsp+68h+arg_8]
0x140055de2  mov     r15, [rsp+68h+var_28]
0x140055de7  add     rsp, 58h
0x140055deb  pop     r12
0x140055ded  pop     rbx
0x140055dee  retn
0x140055df0  cmp     byte ptr [rbp+4Dh], 1
0x140055df4  jnz     loc_140055CB1
0x140055dfa  mov     dword ptr [rbx+0B0h], 0C000000Dh
0x140055e04  mov     eax, 0C000000Dh
0x140055e09  mov     [rbx+0B8h], r12
0x140055e10  jmp     short loc_140055DD0
0x140055e12  mov     r8, [rax+88h]
0x140055e19  mov     r9, [rsi+1A8h]
0x140055e20  test    r8, r8
0x140055e23  jz      short loc_140055E88
0x140055e25  mov     rax, [rcx+88h]
0x140055e2c  nop
0x140055e2d  mov     r14d, [r8+58h]
0x140055e31  nop
0x140055e32  nop
0x140055e33  mov     eax, [rax+54h]
0x140055e36  nop
0x140055e37  cmp     eax, r14d
0x140055e3a  jz      loc_140055C73
0x140055e40  mov     rdi, rdx
0x140055e43  jmp     loc_1400585D2
0x140055e48  mov     eax, r12d
0x140055e4b  mov     [rcx+0B0h], r12d
0x140055e52  mov     [rcx+0B8h], r12
0x140055e59  add     rsp, 58h
0x140055e5d  pop     r12
0x140055e5f  pop     rbx
0x140055e60  retn
0x140055e62  mov     eax, [rax+4]
0x140055e65  test    al, 1
0x140055e67  jz      loc_140055C9B
0x140055e6d  test    dl, 3
0x140055e70  jnz     loc_140055C9B
0x140055e76  call    Smb2TryToEstablishMultipleChannelsImpl
0x140055e7b  jmp     loc_140055C9B
0x140055e80  mov     rdx, rdi
0x140055e83  jmp     loc_140055C60
0x140055e88  mov     r14d, r12d
0x140055e8b  jmp     loc_1400585D2
0x140055e90  mov     rax, [rsp+68h+arg_0]
0x140055e95  lock or dword ptr [rax+44h], 40000h
0x140055e9d  jmp     loc_140055D1F
0x1400585d2  lea     rdx, [r9+458h]
0x1400585d9  mov     rcx, rbx
0x1400585dc  call    Smb2InvalidateSingleFileInDirInfoCache
0x1400585e1  mov     rax, [rdi]
0x1400585e4  mov     rcx, [rax+88h]
0x1400585eb  xchg    r14d, [rcx+54h]
0x1400585ef  jmp     loc_140055C73
```
