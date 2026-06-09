# DecryptMasterKeyToMemoryEx(uchar *,ulong,uchar *,ulong,void * (*)(unsigned __int64),uchar * *,ulong *,uint *,uint *,ulong *)

- ea: `0x18000ad44`
- end: `0x18000b551`
- name: `?DecryptMasterKeyToMemoryEx@@YAKPEAEK0KP6APEAX_K@ZPEAPEAEPEAKPEAI54@Z`
- size: `2061`
- prototype: `__int64 __fastcall(unsigned __int8 *, ULONG, unsigned __int8 *, unsigned int, void *(*)(unsigned __int64), unsigned __int8 **, unsigned int *, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000abf0`
- `0x18000e9c0`
- `0x180019f40`

## callees

- `0x180002480`
- `0x1800029d0`
- `0x18000ad44`
- `0x180010ba0`
- `0x18001d810`
- `0x18003c620`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b51b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b51b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000adf0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000adf0`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000b0b7`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000b1ad`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000b262`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000b0b7`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000b1ad`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18000b262`
- `bcrypt!BCryptDecrypt` at `0x18000b119`
- `bcrypt!BCryptDecrypt` at `0x18000b119`
- `bcrypt!BCryptFinishHash` at `0x18000b026`
- `bcrypt!BCryptFinishHash` at `0x18000b395`
- `bcrypt!BCryptFinishHash` at `0x18000b479`
- `bcrypt!BCryptFinishHash` at `0x18000b026`
- `bcrypt!BCryptFinishHash` at `0x18000b395`
- `bcrypt!BCryptFinishHash` at `0x18000b479`
- `bcrypt!BCryptDestroyHash` at `0x18000b054`
- `bcrypt!BCryptDestroyHash` at `0x18000b3b5`
- `bcrypt!BCryptDestroyHash` at `0x18000b497`
- `bcrypt!BCryptDestroyHash` at `0x18000b054`
- `bcrypt!BCryptDestroyHash` at `0x18000b3b5`
- `bcrypt!BCryptDestroyHash` at `0x18000b497`
- `bcrypt!BCryptHashData` at `0x18000b007`
- `bcrypt!BCryptHashData` at `0x18000b376`
- `bcrypt!BCryptHashData` at `0x18000b45a`
- `bcrypt!BCryptHashData` at `0x18000b007`
- `bcrypt!BCryptHashData` at `0x18000b376`
- `bcrypt!BCryptHashData` at `0x18000b45a`
- `bcrypt!BCryptDestroyKey` at `0x18000b12c`
- `bcrypt!BCryptDestroyKey` at `0x18000b12c`
- `bcrypt!BCryptCreateHash` at `0x18000afe3`
- `bcrypt!BCryptCreateHash` at `0x18000b355`
- `bcrypt!BCryptCreateHash` at `0x18000b43c`
- `bcrypt!BCryptCreateHash` at `0x18000afe3`
- `bcrypt!BCryptCreateHash` at `0x18000b355`
- `bcrypt!BCryptCreateHash` at `0x18000b43c`
- `ntdll!RtlNtStatusToDosError` at `0x18000b0c9`
- `ntdll!RtlNtStatusToDosError` at `0x18000b0c9`

## pseudocode

```c
__int64 __fastcall DecryptMasterKeyToMemoryEx(
        unsigned __int8 *a1,
        ULONG a2,
        unsigned __int8 *a3,
        unsigned int a4,
        void *(*a5)(unsigned __int64),
        unsigned __int8 **a6,
        unsigned int *a7,
        unsigned int *a8,
        unsigned int *a9,
        unsigned int *a10)
{
  unsigned int v11; // r14d
  unsigned __int64 v12; // r12
  HLOCAL v13; // rax
  char *v14; // rdx
  ULONG v15; // r13d
  ULONG v16; // r8d
  __int64 v17; // r9
  unsigned int v18; // edi
  UCHAR *v19; // rax
  unsigned int v20; // r12d
  __int128 *v21; // rsi
  unsigned int v22; // ebx
  int v23; // eax
  _DWORD *v24; // r15
  unsigned int v25; // ecx
  ULONG v26; // ebx
  int v27; // esi
  void *BCryptProviderHandle; // rax
  NTSTATUS v29; // eax
  void *v30; // rax
  NTSTATUS v31; // eax
  NTSTATUS v32; // ecx
  ULONG v33; // ebx
  unsigned int v34; // ebx
  UCHAR *v35; // r14
  NTSTATUS v36; // eax
  int v37; // esi
  ULONG v38; // esi
  void *v39; // rax
  void *v40; // rax
  UCHAR *v41; // r12
  ULONG v42; // ebx
  unsigned int v43; // ecx
  ULONG v44; // esi
  int v45; // r14d
  void *v46; // rax
  ULONG v47; // r14d
  int v48; // esi
  void *v49; // rax
  unsigned __int8 *v50; // rax
  __int64 v51; // rdx
  _BYTE *v52; // rax
  ULONG cbSecret; // [rsp+28h] [rbp-D8h]
  UCHAR *dwFlags; // [rsp+30h] [rbp-D0h]
  ULONG v56; // [rsp+38h] [rbp-C8h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-B0h] BYREF
  ULONG pcbResult; // [rsp+58h] [rbp-A8h] BYREF
  int v59; // [rsp+5Ch] [rbp-A4h]
  unsigned int v60; // [rsp+60h] [rbp-A0h]
  ULONG cbOutput; // [rsp+64h] [rbp-9Ch]
  unsigned int v62; // [rsp+68h] [rbp-98h]
  ULONG v63; // [rsp+6Ch] [rbp-94h]
  PUCHAR pbInput; // [rsp+70h] [rbp-90h]
  ULONG v65[2]; // [rsp+78h] [rbp-88h]
  PUCHAR pbSecret; // [rsp+80h] [rbp-80h]
  unsigned __int8 **v67; // [rsp+88h] [rbp-78h]
  unsigned int *v68; // [rsp+90h] [rbp-70h]
  HLOCAL hMem[3]; // [rsp+98h] [rbp-68h] BYREF
  UCHAR pbOutput[24]; // [rsp+B0h] [rbp-50h] BYREF
  void *v71; // [rsp+C8h] [rbp-38h]
  __int128 v72; // [rsp+D0h] [rbp-30h]
  UCHAR v73[64]; // [rsp+F0h] [rbp-10h] BYREF
  UCHAR Buf2[64]; // [rsp+130h] [rbp+30h] BYREF

  pbSecret = a1;
  v60 = a4;
  v63 = a2;
  v67 = a6;
  *a7 = 0;
  *a6 = 0;
  v68 = a7;
  if ( a8 )
    *a8 = 0;
  if ( a9 )
    *a9 = 0;
  if ( a10 )
    *a10 = 0;
  if ( a4 - 72 > 0x3B8 )
    return (ULONG)-2146893821;
  v11 = 2;
  if ( *(_DWORD *)a3 > 2u )
    return (ULONG)-2146893821;
  v12 = a4;
  v13 = LocalAlloc(0, a4);
  hMem[0] = v13;
  if ( !v13 )
    return (ULONG)-2146893821;
  cbOutput = 40;
  v62 = 4;
  memcpy_0(v13, a3, (unsigned int)v12);
  v14 = (char *)hMem[0];
  if ( *(_DWORD *)hMem[0] == 1 )
  {
    v15 = 20;
    v16 = 26625;
    v17 = 20;
    pcbResult = 26625;
    v11 = 1;
    *(_QWORD *)v65 = 20;
    v18 = 32777;
    v59 = 20;
    v19 = (UCHAR *)hMem[0] + 20;
    v20 = 0;
  }
  else
  {
    v16 = *((_DWORD *)hMem[0] + 7);
    v18 = *((_DWORD *)hMem[0] + 6);
    pcbResult = v16;
    if ( v16 == 26115 )
    {
      v62 = 4;
      cbOutput = 40;
    }
    else
    {
      v11 = 1;
      if ( v16 == 26128 )
      {
        v62 = 0;
        cbOutput = 64;
      }
    }
    v17 = 64;
    v15 = 20;
    if ( v18 != 32782 )
      v17 = 20;
    *(_QWORD *)v65 = v17;
    if ( v12 < v17 + (unsigned __int64)v62 + 64 )
      goto LABEL_107;
    v20 = *((_DWORD *)hMem[0] + 5);
    v19 = (UCHAR *)hMem[0] + 32;
    v59 = 32;
  }
  pbInput = v19;
  if ( a8 )
    *a8 = v16;
  if ( a9 )
    *a9 = v18;
  if ( a10 )
    *a10 = v20;
  if ( v20 )
  {
    v21 = (__int128 *)(v14 + 4);
    v22 = 0;
    while ( 1 )
    {
      v23 = v17 * v22++;
      if ( !PKCS5DerivePBKDF2(pbSecret, v63, v21, v17, v18, v20, v22, &pbOutput[v23], cbOutput - v23) )
        break;
      v17 = *(_QWORD *)v65;
      if ( v22 >= v11 )
      {
        v24 = hMem[0];
        goto LABEL_50;
      }
    }
    v24 = hMem[0];
    goto LABEL_108;
  }
  phHash = 0;
  if ( v18 == 32777 )
  {
    v25 = 32772;
LABEL_35:
    v26 = 20;
    goto LABEL_38;
  }
  v25 = v18;
  if ( v18 == 32772 )
    goto LABEL_35;
  if ( v18 != 32782 )
  {
LABEL_107:
    v24 = v14;
    goto LABEL_108;
  }
  v26 = 64;
LABEL_38:
  v27 = 0;
  if ( cbOutput <= v26 )
    v26 = cbOutput;
  BCryptProviderHandle = (void *)GetBCryptProviderHandle(v25);
  if ( BCryptProviderHandle )
  {
    v29 = BCryptCreateHash(BCryptProviderHandle, &phHash, 0, 0, pbSecret, v63, 0);
    v24 = hMem[0];
    if ( v29 >= 0
      && BCryptHashData(phHash, (PUCHAR)hMem[0] + 4, 0x10u, 0) >= 0
      && BCryptFinishHash(phHash, pbOutput, v26, 0) >= 0 )
    {
      v27 = 1;
    }
  }
  else
  {
    v24 = hMem[0];
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( !v27 )
    goto LABEL_108;
LABEL_50:
  if ( pcbResult != 26625 )
  {
    if ( pcbResult == 26115 )
    {
      v34 = v60 - v59;
      phHash = 0;
      v38 = (v60 - v59) & 0xFFFFFFF8;
      pcbResult = 0;
      if ( v38 != v60 - v59 )
        goto LABEL_108;
      v39 = (void *)GetBCryptProviderHandle(0x6603u);
      if ( !v39 )
      {
LABEL_61:
        v33 = 13;
        goto LABEL_109;
      }
      v31 = BCryptGenerateSymmetricKey(v39, &phHash, 0, 0, pbOutput, 0x18u, 0);
      if ( v31 < 0 )
        goto LABEL_53;
      v35 = pbInput;
      hMem[0] = v71;
      v56 = v38;
      dwFlags = pbInput;
      cbSecret = 8;
    }
    else
    {
      if ( pcbResult != 26128 )
        goto LABEL_108;
      v34 = v60 - v59;
      phHash = 0;
      v38 = (v60 - v59) & 0xFFFFFFF0;
      pcbResult = 0;
      if ( v38 != v60 - v59 )
        goto LABEL_108;
      v40 = (void *)GetBCryptProviderHandle(0x6610u);
      if ( !v40 )
        goto LABEL_61;
      v31 = BCryptGenerateSymmetricKey(v40, &phHash, 0, 0, pbOutput, 0x20u, 0);
      if ( v31 < 0 )
        goto LABEL_53;
      v35 = pbInput;
      v56 = v38;
      dwFlags = pbInput;
      cbSecret = 16;
      *(_OWORD *)hMem = v72;
    }
    v36 = BCryptDecrypt(phHash, v35, v38, 0, (PUCHAR)hMem, cbSecret, dwFlags, v56, &pcbResult, 0);
    goto LABEL_56;
  }
  v30 = (void *)GetBCryptProviderHandle(0x6801u);
  phHash = 0;
  pcbResult = 0;
  if ( !v30 )
    goto LABEL_108;
  v31 = BCryptGenerateSymmetricKey(v30, &phHash, 0, 0, pbOutput, 0x14u, 0);
  if ( v31 >= 0 )
  {
    v34 = v60 - v59;
    v35 = pbInput;
    v36 = BCryptDecrypt(phHash, pbInput, v60 - v59, 0, 0, 0, pbInput, v60 - v59, &pcbResult, 1u);
LABEL_56:
    v37 = v36;
    BCryptDestroyKey(phHash);
    if ( v37 < 0 )
    {
      v32 = v37;
      goto LABEL_54;
    }
    if ( *v24 == 1 )
    {
      v41 = v35 + 36;
      v42 = v34 - 36;
    }
    else
    {
      v41 = &v35[v62 + 16 + v65[0]];
      v42 = v60 - v62 - v65[0] - v59 - 16;
    }
    phHash = 0;
    if ( v18 == 32777 )
    {
      v43 = 32772;
LABEL_76:
      v44 = 20;
      goto LABEL_79;
    }
    v43 = v18;
    if ( v18 == 32772 )
      goto LABEL_76;
    if ( v18 == 32782 )
    {
      v44 = 64;
LABEL_79:
      v45 = 0;
      if ( v65[0] <= v44 )
        v44 = v65[0];
      v46 = (void *)GetBCryptProviderHandle(v43);
      if ( v46
        && BCryptCreateHash(v46, &phHash, 0, 0, pbSecret, v63, 0) >= 0
        && BCryptHashData(phHash, pbInput, 0x10u, 0) >= 0
        && BCryptFinishHash(phHash, v73, v44, 0) >= 0 )
      {
        v45 = 1;
      }
      if ( phHash )
        BCryptDestroyHash(phHash);
      if ( v45 )
      {
        phHash = 0;
        if ( v18 == 32777 )
        {
          v18 = 32772;
        }
        else if ( v18 != 32772 )
        {
          v15 = 64;
        }
        v47 = v65[0];
        v48 = 0;
        if ( v65[0] <= v15 )
          v15 = v65[0];
        v49 = (void *)GetBCryptProviderHandle(v18);
        if ( v49
          && BCryptCreateHash(v49, &phHash, 0, 0, v73, v47, 0) >= 0
          && BCryptHashData(phHash, v41, v42, 0) >= 0
          && BCryptFinishHash(phHash, Buf2, v15, 0) >= 0 )
        {
          v48 = 1;
        }
        if ( phHash )
          BCryptDestroyHash(phHash);
        if ( v48 && !memcmp_0(pbInput + 16, Buf2, v47) )
        {
          v50 = (unsigned __int8 *)SSAlloc(v42);
          *v67 = v50;
          if ( v50 )
          {
            memcpy_0(v50, v41, v42);
            *v68 = v42;
            v33 = 0;
          }
          else
          {
            v33 = 1130;
          }
          goto LABEL_109;
        }
      }
    }
LABEL_108:
    v33 = -2146893792;
    goto LABEL_109;
  }
LABEL_53:
  v32 = v31;
LABEL_54:
  v33 = RtlNtStatusToDosError(v32);
LABEL_109:
  v51 = v60;
  v52 = v24;
  if ( v60 )
  {
    do
    {
      *v52++ = 0;
      --v51;
    }
    while ( v51 );
  }
  LocalFree(v24);
  return v33;
}

```

## disassembly

```asm
0x18000ad44  push    rbp
0x18000ad46  push    rbx
0x18000ad47  push    rsi
0x18000ad48  push    rdi
0x18000ad49  push    r12
0x18000ad4b  push    r13
0x18000ad4d  push    r14
0x18000ad4f  push    r15
0x18000ad51  lea     rbp, [rsp-88h]
0x18000ad59  sub     rsp, 188h
0x18000ad60  mov     rax, cs:__security_cookie
0x18000ad67  xor     rax, rsp
0x18000ad6a  mov     [rbp+0C0h+var_50], rax
0x18000ad6e  mov     rax, [rbp+0C0h+arg_28]
0x18000ad75  xor     r13d, r13d
0x18000ad78  mov     rsi, [rbp+0C0h+arg_38]
0x18000ad7f  mov     rdi, r8
0x18000ad82  mov     rbx, [rbp+0C0h+arg_40]
0x18000ad89  mov     r15, [rbp+0C0h+arg_48]
0x18000ad90  mov     [rbp+0C0h+var_140], rcx
0x18000ad94  mov     rcx, [rbp+0C0h+arg_30]
0x18000ad9b  mov     [rsp+1C0h+var_160], r9d
0x18000ada0  mov     [rsp+1C0h+var_154], edx
0x18000ada4  mov     [rbp+0C0h+var_138], rax
0x18000ada8  mov     [rcx], r13d
0x18000adab  mov     [rax], r13
0x18000adae  mov     [rbp+0C0h+var_130], rcx
0x18000adb2  test    rsi, rsi
0x18000adb5  jz      short loc_18000ADBA
0x18000adb7  mov     [rsi], r13d
0x18000adba  test    rbx, rbx
0x18000adbd  jz      short loc_18000ADC2
0x18000adbf  mov     [rbx], r13d
0x18000adc2  test    r15, r15
0x18000adc5  jz      short loc_18000ADCA
0x18000adc7  mov     [r15], r13d
0x18000adca  lea     eax, [r9-48h]
0x18000adce  cmp     eax, 3B8h
0x18000add3  ja      loc_18000B529
0x18000add9  mov     r14d, 2
0x18000addf  cmp     [r8], r14d
0x18000ade2  ja      loc_18000B529
0x18000ade8  mov     edx, r9d; uBytes
0x18000adeb  xor     ecx, ecx; uFlags
0x18000aded  mov     r12d, r9d
0x18000adf0  call    cs:__imp_LocalAlloc
0x18000adf7  nop     dword ptr [rax+rax+00h]
0x18000adfc  mov     [rbp+0C0h+hMem], rax
0x18000ae00  test    rax, rax
0x18000ae03  jz      loc_18000B529
0x18000ae09  lea     r13d, [r14+2]
0x18000ae0d  mov     [rsp+1C0h+cbOutput], 28h ; '('
0x18000ae15  mov     r8d, r12d; Size
0x18000ae18  mov     [rsp+1C0h+var_158], r13d
0x18000ae1d  mov     rdx, rdi; Src
0x18000ae20  mov     rcx, rax; void *
0x18000ae23  call    memcpy_0
0x18000ae28  mov     rdx, [rbp+0C0h+hMem]
0x18000ae2c  lea     eax, [r14-1]
0x18000ae30  lea     r10d, [r14+3Eh]
0x18000ae34  mov     r11d, 800Eh
0x18000ae3a  cmp     [rdx], eax
0x18000ae3c  jnz     short loc_18000AE6A
0x18000ae3e  lea     r13d, [rax+13h]
0x18000ae42  mov     r8d, 6801h
0x18000ae48  mov     r9d, r13d
0x18000ae4b  mov     [rsp+1C0h+var_168], r8d
0x18000ae50  mov     r14d, eax
0x18000ae53  mov     qword ptr [rsp+1C0h+var_148], r9
0x18000ae58  lea     edi, [r11-5]
0x18000ae5c  mov     [rsp+1C0h+var_164], r13d
0x18000ae61  lea     rax, [rdx+14h]
0x18000ae65  xor     r12d, r12d
0x18000ae68  jmp     short loc_18000AEDF
0x18000ae6a  mov     r8d, [rdx+1Ch]
0x18000ae6e  mov     edi, [rdx+18h]
0x18000ae71  mov     [rsp+1C0h+var_168], r8d
0x18000ae76  cmp     r8d, 6603h
0x18000ae7d  jnz     short loc_18000AE8E
0x18000ae7f  mov     [rsp+1C0h+var_158], r13d
0x18000ae84  mov     [rsp+1C0h+cbOutput], 28h ; '('
0x18000ae8c  jmp     short loc_18000AEA7
0x18000ae8e  mov     r14d, eax
0x18000ae91  cmp     r8d, 6610h
0x18000ae98  jnz     short loc_18000AEA7
0x18000ae9a  mov     [rsp+1C0h+var_158], 0
0x18000aea2  mov     [rsp+1C0h+cbOutput], r10d
0x18000aea7  mov     ecx, [rsp+1C0h+var_158]
0x18000aeab  mov     r9d, r10d
0x18000aeae  cmp     edi, r11d
0x18000aeb1  mov     r13d, 14h
0x18000aeb7  cmovnz  r9d, r13d; int
0x18000aebb  add     rcx, r10
0x18000aebe  add     rcx, r9
0x18000aec1  mov     qword ptr [rsp+1C0h+var_148], r9
0x18000aec6  cmp     r12, rcx
0x18000aec9  jb      loc_18000B4F4
0x18000aecf  mov     r12d, [rdx+14h]
0x18000aed3  lea     rax, [rdx+20h]
0x18000aed7  mov     [rsp+1C0h+var_164], 20h ; ' '
0x18000aedf  mov     [rsp+1C0h+pbInput], rax
0x18000aee4  test    rsi, rsi
0x18000aee7  jz      short loc_18000AEEC
0x18000aee9  mov     [rsi], r8d
0x18000aeec  test    rbx, rbx
0x18000aeef  jz      short loc_18000AEF3
0x18000aef1  mov     [rbx], edi
0x18000aef3  test    r15, r15
0x18000aef6  jz      short loc_18000AEFB
0x18000aef8  mov     [r15], r12d
0x18000aefb  mov     eax, 8004h
0x18000af00  test    r12d, r12d
0x18000af03  jz      short loc_18000AF74
0x18000af05  mov     r15d, [rsp+1C0h+cbOutput]
0x18000af0a  lea     rsi, [rdx+4]
0x18000af0e  xor     ebx, ebx
0x18000af10  mov     eax, ebx
0x18000af12  mov     ecx, r15d
0x18000af15  imul    eax, r9d
0x18000af19  mov     r8, rsi; int
0x18000af1c  inc     ebx
0x18000af1e  sub     ecx, eax
0x18000af20  mov     edx, eax
0x18000af22  mov     dword ptr [rsp+1C0h+pcbResult], ecx; int
0x18000af26  lea     rax, [rbp+0C0h+pbOutput]
0x18000af2a  mov     rcx, [rbp+0C0h+var_140]; int
0x18000af2e  add     rax, rdx
0x18000af31  mov     edx, [rsp+1C0h+var_154]; int
0x18000af35  mov     qword ptr [rsp+1C0h+var_188], rax; PUCHAR
0x18000af3a  mov     [rsp+1C0h+dwFlags], ebx; char
0x18000af3e  mov     [rsp+1C0h+cbSecret], r12d; int
0x18000af43  mov     dword ptr [rsp+1C0h+pbSecret], edi; unsigned int
0x18000af47  call    PKCS5DerivePBKDF2
0x18000af4c  test    eax, eax
0x18000af4e  jz      short loc_18000AF6B
0x18000af50  mov     r9, qword ptr [rsp+1C0h+var_148]
0x18000af55  cmp     ebx, r14d
0x18000af58  jb      short loc_18000AF10
0x18000af5a  mov     r15, [rbp+0C0h+hMem]
0x18000af5e  xor     r12d, r12d
0x18000af61  lea     r14d, [r12+1]
0x18000af66  jmp     loc_18000B068
0x18000af6b  mov     r15, [rbp+0C0h+hMem]
0x18000af6f  jmp     loc_18000B4F7
0x18000af74  xor     r12d, r12d
0x18000af77  mov     [rsp+1C0h+phHash], r12
0x18000af7c  cmp     edi, 8009h
0x18000af82  jnz     short loc_18000AF88
0x18000af84  mov     ecx, eax
0x18000af86  jmp     short loc_18000AF8E
0x18000af88  mov     ecx, edi; unsigned int
0x18000af8a  cmp     edi, eax
0x18000af8c  jnz     short loc_18000AF93
0x18000af8e  mov     ebx, r13d
0x18000af91  jmp     short loc_18000AF9F
0x18000af93  cmp     edi, r11d
0x18000af96  jnz     loc_18000B4F4
0x18000af9c  mov     ebx, r10d
0x18000af9f  cmp     [rsp+1C0h+cbOutput], ebx
0x18000afa3  mov     esi, r12d
0x18000afa6  cmovbe  ebx, [rsp+1C0h+cbOutput]
0x18000afab  xor     edx, edx
0x18000afad  lea     r8d, [rdx+28h]
0x18000afb1  call    GetBCryptProviderHandle
0x18000afb6  test    rax, rax
0x18000afb9  jz      loc_18000B040
0x18000afbf  mov     ecx, [rsp+1C0h+var_154]
0x18000afc3  lea     rdx, [rsp+1C0h+phHash]; phHash
0x18000afc8  mov     [rsp+1C0h+dwFlags], r12d; dwFlags
0x18000afcd  xor     r9d, r9d; cbHashObject
0x18000afd0  mov     [rsp+1C0h+cbSecret], ecx; cbSecret
0x18000afd4  xor     r8d, r8d; pbHashObject
0x18000afd7  mov     rcx, [rbp+0C0h+var_140]
0x18000afdb  mov     [rsp+1C0h+pbSecret], rcx; pbSecret
0x18000afe0  mov     rcx, rax; hAlgorithm
0x18000afe3  call    cs:__imp_BCryptCreateHash
0x18000afea  nop     dword ptr [rax+rax+00h]
0x18000afef  mov     r15, [rbp+0C0h+hMem]
0x18000aff3  test    eax, eax
0x18000aff5  js      short loc_18000B044
0x18000aff7  mov     rcx, [rsp+1C0h+phHash]; hHash
0x18000affc  lea     rdx, [r15+4]; pbInput
0x18000b000  xor     r9d, r9d; dwFlags
0x18000b003  lea     r8d, [r9+10h]; cbInput
0x18000b007  call    cs:__imp_BCryptHashData
0x18000b00e  nop     dword ptr [rax+rax+00h]
0x18000b013  test    eax, eax
0x18000b015  js      short loc_18000B044
0x18000b017  mov     rcx, [rsp+1C0h+phHash]; hHash
0x18000b01c  lea     rdx, [rbp+0C0h+pbOutput]; pbOutput
0x18000b020  xor     r9d, r9d; dwFlags
0x18000b023  mov     r8d, ebx; cbOutput
0x18000b026  call    cs:__imp_BCryptFinishHash
0x18000b02d  nop     dword ptr [rax+rax+00h]
0x18000b032  test    eax, eax
0x18000b034  mov     r14d, 1
0x18000b03a  cmovns  esi, r14d
0x18000b03e  jmp     short loc_18000B04A
0x18000b040  mov     r15, [rbp+0C0h+hMem]
0x18000b044  mov     r14d, 1
0x18000b04a  mov     rcx, [rsp+1C0h+phHash]; hHash
0x18000b04f  test    rcx, rcx
0x18000b052  jz      short loc_18000B060
0x18000b054  call    cs:__imp_BCryptDestroyHash
0x18000b05b  nop     dword ptr [rax+rax+00h]
0x18000b060  test    esi, esi
0x18000b062  jz      loc_18000B4F7
0x18000b068  mov     eax, [rsp+1C0h+var_168]
0x18000b06c  mov     ecx, 6801h; unsigned int
0x18000b071  cmp     eax, ecx
0x18000b073  jnz     loc_18000B144
0x18000b079  xor     r8d, r8d
0x18000b07c  xor     edx, edx
0x18000b07e  call    GetBCryptProviderHandle
0x18000b083  mov     [rsp+1C0h+phHash], r12
0x18000b088  mov     [rsp+1C0h+var_168], r12d
0x18000b08d  test    rax, rax
0x18000b090  jz      loc_18000B4F7
0x18000b096  mov     [rsp+1C0h+dwFlags], r12d; dwFlags
0x18000b09b  lea     rcx, [rbp+0C0h+pbOutput]
0x18000b09f  mov     [rsp+1C0h+cbSecret], r13d; cbSecret
0x18000b0a4  lea     rdx, [rsp+1C0h+phHash]; phKey
0x18000b0a9  mov     [rsp+1C0h+pbSecret], rcx; pbSecret
0x18000b0ae  xor     r9d, r9d; cbKeyObject
0x18000b0b1  mov     rcx, rax; hAlgorithm
0x18000b0b4  xor     r8d, r8d; pbKeyObject
0x18000b0b7  call    cs:__imp_BCryptGenerateSymmetricKey
0x18000b0be  nop     dword ptr [rax+rax+00h]
0x18000b0c3  test    eax, eax
0x18000b0c5  jns     short loc_18000B0DC
0x18000b0c7  mov     ecx, eax; Status
0x18000b0c9  call    cs:__imp_RtlNtStatusToDosError
0x18000b0d0  nop     dword ptr [rax+rax+00h]
0x18000b0d5  mov     ebx, eax
0x18000b0d7  jmp     loc_18000B4FC
0x18000b0dc  mov     ebx, [rsp+1C0h+var_160]
0x18000b0e0  lea     rax, [rsp+1C0h+var_168]
0x18000b0e5  sub     ebx, [rsp+1C0h+var_164]
0x18000b0e9  mov     [rsp+1C0h+var_178], r14d; dwFlags
0x18000b0ee  mov     r8d, ebx; cbInput
0x18000b0f1  mov     r14, [rsp+1C0h+pbInput]
0x18000b0f6  mov     [rsp+1C0h+pcbResult], rax; pcbResult
0x18000b0fb  mov     [rsp+1C0h+var_188], ebx; cbOutput
0x18000b0ff  mov     qword ptr [rsp+1C0h+dwFlags], r14; pbOutput
0x18000b104  mov     [rsp+1C0h+cbSecret], r12d; cbIV
0x18000b109  mov     [rsp+1C0h+pbSecret], r12; pbIV
0x18000b10e  mov     rcx, [rsp+1C0h+phHash]; hKey
0x18000b113  xor     r9d, r9d; pPaddingInfo
0x18000b116  mov     rdx, r14; pbInput
0x18000b119  call    cs:__imp_BCryptDecrypt
0x18000b120  nop     dword ptr [rax+rax+00h]
0x18000b125  mov     rcx, [rsp+1C0h+phHash]; hKey
0x18000b12a  mov     esi, eax
0x18000b12c  call    cs:__imp_BCryptDestroyKey
0x18000b133  nop     dword ptr [rax+rax+00h]
0x18000b138  test    esi, esi
0x18000b13a  jns     loc_18000B2AD
0x18000b140  mov     ecx, esi
0x18000b142  jmp     short loc_18000B0C9
0x18000b144  mov     ecx, 6603h; unsigned int
0x18000b149  cmp     eax, ecx
0x18000b14b  jnz     loc_18000B1FF
0x18000b151  mov     ebx, [rsp+1C0h+var_160]
0x18000b155  sub     ebx, [rsp+1C0h+var_164]
0x18000b159  mov     esi, ebx
0x18000b15b  mov     [rsp+1C0h+phHash], r12
0x18000b160  and     esi, 0FFFFFFF8h
0x18000b163  mov     [rsp+1C0h+var_168], r12d
0x18000b168  cmp     esi, ebx
0x18000b16a  jnz     loc_18000B4F7
0x18000b170  xor     r8d, r8d
0x18000b173  xor     edx, edx
0x18000b175  call    GetBCryptProviderHandle
0x18000b17a  test    rax, rax
0x18000b17d  jnz     short loc_18000B189
0x18000b17f  mov     ebx, 0Dh
0x18000b184  jmp     loc_18000B4FC
0x18000b189  mov     [rsp+1C0h+dwFlags], r12d; dwFlags
0x18000b18e  lea     rcx, [rbp+0C0h+pbOutput]
0x18000b192  mov     [rsp+1C0h+cbSecret], 18h; cbSecret
0x18000b19a  lea     rdx, [rsp+1C0h+phHash]; phKey
0x18000b19f  mov     [rsp+1C0h+pbSecret], rcx; pbSecret
0x18000b1a4  xor     r9d, r9d; cbKeyObject
0x18000b1a7  mov     rcx, rax; hAlgorithm
0x18000b1aa  xor     r8d, r8d; pbKeyObject
0x18000b1ad  call    cs:__imp_BCryptGenerateSymmetricKey
0x18000b1b4  nop     dword ptr [rax+rax+00h]
0x18000b1b9  test    eax, eax
0x18000b1bb  js      loc_18000B0C7
0x18000b1c1  mov     rax, [rbp+0C0h+var_F8]
0x18000b1c5  mov     r14, [rsp+1C0h+pbInput]
0x18000b1ca  mov     [rsp+1C0h+var_178], r12d
0x18000b1cf  mov     [rbp+0C0h+hMem], rax
0x18000b1d3  lea     rax, [rsp+1C0h+var_168]
0x18000b1d8  mov     [rsp+1C0h+pcbResult], rax
0x18000b1dd  lea     rax, [rbp+0C0h+hMem]
0x18000b1e1  mov     [rsp+1C0h+var_188], esi
0x18000b1e5  mov     qword ptr [rsp+1C0h+dwFlags], r14
0x18000b1ea  mov     [rsp+1C0h+cbSecret], 8
0x18000b1f2  mov     [rsp+1C0h+pbSecret], rax
  ... truncated ...
```
