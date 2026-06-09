# DhcpRegistryPersistentRequestParams

- ea: `0x180009920`
- end: `0x180009c7e`
- name: `DhcpRegistryPersistentRequestParams`
- size: `862`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, int, STRSAFE_PCNZWCH psz)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180001490`
- `0x180008390`

## callees

- `0x1800042d4`
- `0x1800048c0`
- `0x180009060`
- `0x180009584`
- `0x180009920`
- `0x18000d4a4`
- `0x180011190`
- `0x180011ce0`
- `0x180012a00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009c28`

## pseudocode

```c
__int64 __fastcall DhcpRegistryPersistentRequestParams(
        const wchar_t *a1,
        BYTE *a2,
        DWORD a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7,
        STRSAFE_PCNZWCH psz)
{
  BYTE *v9; // r12
  unsigned int v10; // ebx
  __int64 v11; // rcx
  unsigned int v12; // r11d
  unsigned int i; // ecx
  __int64 v14; // rdi
  int v15; // r8d
  unsigned int j; // edx
  __int64 v17; // rax
  __int64 k; // rcx
  int v19; // r8d
  unsigned int v20; // eax
  unsigned int v21; // esi
  BYTE *v22; // rdi
  unsigned int v23; // eax
  unsigned int v24; // r12d
  unsigned int v25; // eax
  unsigned int v26; // edi
  DWORD v28; // [rsp+60h] [rbp-A0h]
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  size_t pcchLength; // [rsp+70h] [rbp-90h] BYREF
  BYTE *v31; // [rsp+78h] [rbp-88h]
  STRSAFE_PCNZWCH v32; // [rsp+80h] [rbp-80h]
  __int64 v33[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v34; // [rsp+98h] [rbp-68h]
  _BYTE v35[256]; // [rsp+B0h] [rbp-50h] BYREF

  *(_OWORD *)v33 = 0;
  v28 = a3;
  v9 = a2;
  v34 = 0;
  v31 = a2;
  v32 = a1;
  hKey = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    WPP_SF_SqdqdqdS((_DWORD)a1, (_DWORD)a2, a3, (_DWORD)a1, (char)a2, a3, a4, a5, a6, a7, (__int64)psz);
    a3 = v28;
  }
  if ( !psz || (a4 == 0) != (a5 == 0) || (a6 == 0) != (a7 == 0) || (v9 == 0) != (a3 == 0) )
    goto LABEL_4;
  if ( StringCchLengthW(psz, 0x100u, &pcchLength) >= 0 )
  {
    for ( i = 0; i < a5; ++i )
    {
      if ( !*(_DWORD *)(32LL * i + a4 + 24) )
        goto LABEL_4;
    }
    v14 = 0;
    v15 = 0;
    LODWORD(pcchLength) = 0;
    for ( j = 0; j < a7; ++j )
    {
      v17 = 32LL * j;
      if ( *(_DWORD *)(v17 + a6 + 8) )
      {
        v15 = 1;
      }
      else
      {
        if ( (unsigned int)v14 >= v12 )
          goto LABEL_4;
        v35[v14] = *(_BYTE *)(v17 + a6 + 4);
        v14 = (unsigned int)(v14 + 1);
        LODWORD(pcchLength) = v14;
      }
    }
    if ( !v15 )
      goto LABEL_27;
    for ( k = 0; (unsigned int)k < (unsigned int)v14; k = (unsigned int)(k + 1) )
    {
      if ( v35[k] == 43 )
        break;
    }
    if ( (_DWORD)k != (_DWORD)v14 )
      goto LABEL_27;
    if ( (unsigned int)v14 < v12 )
    {
      v35[v14] = 43;
      LODWORD(v14) = v14 + 1;
      LODWORD(pcchLength) = v14;
LABEL_27:
      LODWORD(v33[0]) = 0;
      *(_QWORD *)&v34 = v35;
      *(__int64 *)((char *)v33 + 4) = 55;
      DWORD2(v34) = v14;
      v10 = DhcpRegistryCreateUniqueKey(psz, &hKey, v15);
      if ( !v10 )
      {
        v20 = DhcpRegistryFillParamsList(psz, a5 + ((_DWORD)v14 != 0), v19);
        v10 = v20;
        if ( v20 )
        {
          if ( (xmmword_18001E1E0 & 2) != 0 )
            WPP_SF_d(1025, 99, WPP_e15037783097355a5233924022d92169_Traceguids, v20);
        }
        else
        {
          v10 = 0;
          v21 = 0;
          if ( a5 )
          {
            v22 = v9;
            do
            {
              v23 = DhcpRegistryFillParams(v32, v22, v28, v21, hKey, a4 + 32LL * v21, psz);
              v24 = v23;
              if ( v23 )
              {
                if ( (xmmword_18001E1E0 & 2) != 0 )
                  WPP_SF_d(1025, 100, WPP_e15037783097355a5233924022d92169_Traceguids, v23);
                v10 = v24;
              }
              ++v21;
            }
            while ( v21 < a5 );
            LODWORD(v14) = pcchLength;
            v9 = v31;
          }
          if ( (_DWORD)v14 )
          {
            v25 = DhcpRegistryFillParams(v32, v9, v28, v21, hKey, (__int64)v33, psz);
            v26 = v25;
            if ( v25 )
            {
              if ( (xmmword_18001E1E0 & 2) != 0 )
                WPP_SF_d(1025, 101, WPP_e15037783097355a5233924022d92169_Traceguids, v25);
              v10 = v26;
            }
          }
        }
      }
      goto LABEL_46;
    }
LABEL_4:
    v10 = 87;
    goto LABEL_46;
  }
  v10 = 111;
  if ( (xmmword_18001E1E0 & 2) != 0 )
    WPP_SF_Dd(v11);
LABEL_46:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 102, WPP_e15037783097355a5233924022d92169_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180009920  push    rbp
0x180009922  push    rbx
0x180009923  push    rsi
0x180009924  push    rdi
0x180009925  push    r12
0x180009927  push    r13
0x180009929  push    r14
0x18000992b  push    r15
0x18000992d  lea     rbp, [rsp-0C8h]
0x180009935  sub     rsp, 1C8h
0x18000993c  mov     rax, cs:__security_cookie
0x180009943  xor     rax, rsp
0x180009946  mov     [rbp+100h+var_50], rax
0x18000994d  mov     rbx, [rbp+100h+arg_28]
0x180009954  xorps   xmm0, xmm0
0x180009957  mov     r15, [rbp+100h+psz]
0x18000995e  mov     r13, r9
0x180009961  movups  xmmword ptr [rbp+100h+var_178], xmm0
0x180009965  mov     [rsp+200h+var_1A0], r8d
0x18000996a  mov     r12, rdx
0x18000996d  movups  [rbp+100h+var_168], xmm0
0x180009971  mov     [rsp+200h+var_188], rdx
0x180009976  mov     [rbp+100h+var_180], rcx
0x18000997a  mov     [rsp+200h+hKey], 0
0x180009983  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000998a  mov     esi, [rbp+100h+arg_30]
0x180009990  mov     r14d, [rbp+100h+arg_20]
0x180009997  jz      short loc_1800099C8
0x180009999  mov     [rsp+200h+var_1B0], r15
0x18000999e  mov     [rsp+200h+var_1B8], esi
0x1800099a2  mov     [rsp+200h+var_1C0], rbx
0x1800099a7  mov     [rsp+200h+var_1C8], r14d
0x1800099ac  mov     [rsp+200h+var_1D0], r9
0x1800099b1  mov     r9, rcx
0x1800099b4  mov     dword ptr [rsp+200h+var_1D8], r8d
0x1800099b9  mov     [rsp+200h+var_1E0], rdx
0x1800099be  call    WPP_SF_SqdqdqdS
0x1800099c3  mov     r8d, [rsp+200h+var_1A0]
0x1800099c8  test    r15, r15
0x1800099cb  jnz     short loc_1800099D7
0x1800099cd  mov     ebx, 57h ; 'W'
0x1800099d2  jmp     loc_180009C1E
0x1800099d7  xor     ecx, ecx
0x1800099d9  test    r13, r13
0x1800099dc  setz    cl
0x1800099df  xor     eax, eax
0x1800099e1  test    r14d, r14d
0x1800099e4  setz    al
0x1800099e7  cmp     ecx, eax
0x1800099e9  jnz     short loc_1800099CD
0x1800099eb  xor     ecx, ecx
0x1800099ed  test    rbx, rbx
0x1800099f0  setz    cl
0x1800099f3  xor     eax, eax
0x1800099f5  test    esi, esi
0x1800099f7  setz    al
0x1800099fa  cmp     ecx, eax
0x1800099fc  jnz     short loc_1800099CD
0x1800099fe  xor     ecx, ecx
0x180009a00  test    r8d, r8d
0x180009a03  setz    cl
0x180009a06  xor     eax, eax
0x180009a08  test    r12, r12
0x180009a0b  setz    al
0x180009a0e  cmp     eax, ecx
0x180009a10  jnz     short loc_1800099CD
0x180009a12  mov     r11d, 100h
0x180009a18  lea     r8, [rsp+200h+pcchLength]; pcchLength
0x180009a1d  mov     edx, r11d; cchMax
0x180009a20  mov     rcx, r15; psz
0x180009a23  call    StringCchLengthW
0x180009a28  test    eax, eax
0x180009a2a  js      loc_180009C07
0x180009a30  xor     ecx, ecx
0x180009a32  lea     r9d, [rcx+1]
0x180009a36  cmp     ecx, r14d
0x180009a39  jnb     short loc_180009A4E
0x180009a3b  mov     eax, ecx
0x180009a3d  shl     rax, 5
0x180009a41  cmp     dword ptr [rax+r13+18h], 0
0x180009a47  jbe     short loc_1800099CD
0x180009a49  add     ecx, r9d
0x180009a4c  jmp     short loc_180009A36
0x180009a4e  xor     edi, edi
0x180009a50  xor     r8d, r8d
0x180009a53  mov     dword ptr [rsp+200h+pcchLength], edi
0x180009a57  xor     edx, edx
0x180009a59  cmp     edx, esi
0x180009a5b  jnb     short loc_180009A8C
0x180009a5d  mov     eax, edx
0x180009a5f  shl     rax, 5
0x180009a63  cmp     dword ptr [rax+rbx+8], 0
0x180009a68  jz      short loc_180009A6F
0x180009a6a  mov     r8d, r9d
0x180009a6d  jmp     short loc_180009A87
0x180009a6f  cmp     edi, r11d
0x180009a72  jnb     loc_1800099CD
0x180009a78  mov     al, [rax+rbx+4]
0x180009a7c  mov     [rbp+rdi+100h+var_150], al
0x180009a80  add     edi, r9d
0x180009a83  mov     dword ptr [rsp+200h+pcchLength], edi
0x180009a87  add     edx, r9d
0x180009a8a  jmp     short loc_180009A59
0x180009a8c  test    r8d, r8d
0x180009a8f  jz      short loc_180009ABE
0x180009a91  xor     ecx, ecx
0x180009a93  test    edi, edi
0x180009a95  jz      short loc_180009AA5
0x180009a97  cmp     [rbp+rcx+100h+var_150], 2Bh ; '+'
0x180009a9c  jz      short loc_180009AA5
0x180009a9e  add     ecx, r9d
0x180009aa1  cmp     ecx, edi
0x180009aa3  jb      short loc_180009A97
0x180009aa5  cmp     ecx, edi
0x180009aa7  jnz     short loc_180009ABE
0x180009aa9  cmp     edi, r11d
0x180009aac  jnb     loc_1800099CD
0x180009ab2  mov     [rbp+rdi+100h+var_150], 2Bh ; '+'
0x180009ab7  add     edi, r9d
0x180009aba  mov     dword ptr [rsp+200h+pcchLength], edi
0x180009abe  lea     rax, [rbp+100h+var_150]
0x180009ac2  mov     dword ptr [rbp+100h+var_178], 0
0x180009ac9  lea     rdx, [rsp+200h+hKey]; phkResult
0x180009ace  mov     qword ptr [rbp+100h+var_168], rax
0x180009ad2  mov     rcx, r15; psz
0x180009ad5  mov     [rbp+100h+var_178+4], 37h ; '7'
0x180009add  mov     dword ptr [rbp+100h+var_168+8], edi
0x180009ae0  call    DhcpRegistryCreateUniqueKey
0x180009ae5  mov     ebx, eax
0x180009ae7  test    eax, eax
0x180009ae9  jnz     loc_180009C1E
0x180009aef  xor     edx, edx
0x180009af1  mov     rcx, r15; psz
0x180009af4  test    edi, edi
0x180009af6  setnz   dl
0x180009af9  add     edx, r14d
0x180009afc  call    DhcpRegistryFillParamsList
0x180009b01  mov     ebx, eax
0x180009b03  test    eax, eax
0x180009b05  jz      short loc_180009B32
0x180009b07  test    byte ptr cs:xmmword_18001E1E0, 2
0x180009b0e  jz      loc_180009C1E
0x180009b14  mov     edx, 63h ; 'c'
0x180009b19  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180009b20  mov     ecx, 401h
0x180009b25  mov     r9d, eax
0x180009b28  call    WPP_SF_d
0x180009b2d  jmp     loc_180009C1E
0x180009b32  xor     ebx, ebx
0x180009b34  xor     esi, esi
0x180009b36  test    r14d, r14d
0x180009b39  jz      short loc_180009BAB
0x180009b3b  mov     rdi, r12
0x180009b3e  mov     r8d, [rsp+200h+var_1A0]
0x180009b43  mov     r9d, esi
0x180009b46  mov     rcx, [rbp+100h+var_180]; psz
0x180009b4a  mov     rdx, rdi
0x180009b4d  mov     [rsp+200h+var_1D0], r15; STRSAFE_PCNZWCH
0x180009b52  mov     eax, esi
0x180009b54  shl     rax, 5
0x180009b58  add     rax, r13
0x180009b5b  mov     [rsp+200h+var_1D8], rax; __int64
0x180009b60  mov     rax, [rsp+200h+hKey]
0x180009b65  mov     [rsp+200h+var_1E0], rax; __int64
0x180009b6a  call    DhcpRegistryFillParams
0x180009b6f  mov     r12d, eax
0x180009b72  test    eax, eax
0x180009b74  jz      short loc_180009B9B
0x180009b76  test    byte ptr cs:xmmword_18001E1E0, 2
0x180009b7d  jz      short loc_180009B98
0x180009b7f  mov     edx, 64h ; 'd'
0x180009b84  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180009b8b  mov     ecx, 401h
0x180009b90  mov     r9d, eax
0x180009b93  call    WPP_SF_d
0x180009b98  mov     ebx, r12d
0x180009b9b  inc     esi
0x180009b9d  cmp     esi, r14d
0x180009ba0  jb      short loc_180009B3E
0x180009ba2  mov     edi, dword ptr [rsp+200h+pcchLength]
0x180009ba6  mov     r12, [rsp+200h+var_188]
0x180009bab  test    edi, edi
0x180009bad  jz      short loc_180009C1E
0x180009baf  mov     r8d, [rsp+200h+var_1A0]
0x180009bb4  lea     rax, [rbp+100h+var_178]
0x180009bb8  mov     rcx, [rbp+100h+var_180]; psz
0x180009bbc  mov     r9d, esi
0x180009bbf  mov     [rsp+200h+var_1D0], r15; STRSAFE_PCNZWCH
0x180009bc4  mov     rdx, r12
0x180009bc7  mov     [rsp+200h+var_1D8], rax; __int64
0x180009bcc  mov     rax, [rsp+200h+hKey]
0x180009bd1  mov     [rsp+200h+var_1E0], rax; __int64
0x180009bd6  call    DhcpRegistryFillParams
0x180009bdb  mov     edi, eax
0x180009bdd  test    eax, eax
0x180009bdf  jz      short loc_180009C1E
0x180009be1  test    byte ptr cs:xmmword_18001E1E0, 2
0x180009be8  jz      short loc_180009C03
0x180009bea  mov     edx, 65h ; 'e'
0x180009bef  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180009bf6  mov     ecx, 401h
0x180009bfb  mov     r9d, eax
0x180009bfe  call    WPP_SF_d
0x180009c03  mov     ebx, edi
0x180009c05  jmp     short loc_180009C1E
0x180009c07  mov     ebx, 6Fh ; 'o'
0x180009c0c  test    byte ptr cs:xmmword_18001E1E0, 2
0x180009c13  jz      short loc_180009C1E
0x180009c15  mov     dword ptr [rsp+200h+var_1E0], eax
0x180009c19  call    WPP_SF_Dd
0x180009c1e  mov     rcx, [rsp+200h+hKey]; hKey
0x180009c23  test    rcx, rcx
0x180009c26  jz      short loc_180009C37
0x180009c28  call    cs:__imp_RegCloseKey
0x180009c2e  mov     [rsp+200h+hKey], 0
0x180009c37  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180009c3e  jz      short loc_180009C59
0x180009c40  mov     edx, 66h ; 'f'
0x180009c45  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180009c4c  mov     ecx, 404h
0x180009c51  mov     r9d, ebx
0x180009c54  call    WPP_SF_d
0x180009c59  mov     eax, ebx
0x180009c5b  mov     rcx, [rbp+100h+var_50]
0x180009c62  xor     rcx, rsp; StackCookie
0x180009c65  call    __security_check_cookie
0x180009c6a  add     rsp, 1C8h
0x180009c71  pop     r15
0x180009c73  pop     r14
0x180009c75  pop     r13
0x180009c77  pop     r12
0x180009c79  pop     rdi
0x180009c7a  pop     rsi
0x180009c7b  pop     rbx
0x180009c7c  pop     rbp
0x180009c7d  retn
```
