# myCngConfigEnumAlgorithms(ulong,ulong *,_NCryptAlgorithmName * *)

- ea: `0x180021948`
- end: `0x180021bb7`
- name: `?myCngConfigEnumAlgorithms@@YAJKPEAKPEAPEAU_NCryptAlgorithmName@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(__int64, unsigned int *, struct _NCryptAlgorithmName **, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800169e0`

## callees

- `0x180008400`
- `0x18000f718`
- `0x180013a86`
- `0x180021608`
- `0x180021904`
- `0x180021948`
- `0x180021bc0`
- `0x180038262`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021a2b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021a2b`
- `bcrypt!BCryptFreeBuffer` at `0x180021b8a`
- `bcrypt!BCryptFreeBuffer` at `0x180021b8a`

## pseudocode

```c
__int64 __fastcall myCngConfigEnumAlgorithms(
        __int64 a1,
        unsigned int *a2,
        struct _NCryptAlgorithmName **a3,
        unsigned int a4)
{
  struct _NCryptAlgorithmName *v4; // rsi
  unsigned int v6; // eax
  unsigned int v7; // ebx
  int v8; // edx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  SIZE_T v11; // r14
  unsigned int i; // r11d
  unsigned int v13; // eax
  int v14; // r11d
  struct _NCryptAlgorithmName *v15; // rax
  unsigned int v16; // r8d
  WCHAR *v17; // r12
  unsigned int v18; // r15d
  unsigned int v19; // eax
  __int64 v20; // rdi
  unsigned int v21; // eax
  __int64 v22; // r11
  unsigned __int64 v23; // rbx
  __int64 v24; // rcx
  _DWORD *v25; // rdx
  unsigned __int64 v26; // rdi
  DWORD v27; // eax
  size_t v28; // rbx
  unsigned int v29; // eax
  unsigned int *v30; // rcx
  unsigned int v31; // eax
  unsigned __int64 v33; // [rsp+20h] [rbp-20h] BYREF
  PVOID pvBuffer; // [rsp+28h] [rbp-18h] BYREF
  _DWORD *v35; // [rsp+30h] [rbp-10h]
  unsigned int v36; // [rsp+80h] [rbp+40h] BYREF
  unsigned int *v37; // [rsp+88h] [rbp+48h]
  unsigned __int64 v38; // [rsp+98h] [rbp+58h] BYREF

  v37 = a2;
  v4 = 0;
  v36 = 0;
  pvBuffer = 0;
  if ( !a2 || !a3 )
  {
    v7 = -2147467261;
    v9 = 39190980;
    goto LABEL_27;
  }
  *a3 = 0;
  v6 = myBCEnumAlgorithms(0x9Cu, &v36, (struct _BCRYPT_ALGORITHM_IDENTIFIER **)&pvBuffer, a4);
  v7 = v6;
  if ( v6 )
  {
    v8 = v6;
    v9 = 40174020;
    goto LABEL_28;
  }
  v10 = v36;
  if ( v36 > 0x10000 )
  {
    v8 = -2147024362;
    v9 = 40501700;
    v7 = -2147024362;
    goto LABEL_28;
  }
  v11 = 24LL * v36;
  for ( i = 0; i < v10; i = v14 + 1 )
  {
    v38 = 0;
    v13 = StringCchLengthW(*((const unsigned __int16 **)pvBuffer + 2 * i), 0x10000u, &v38);
    v7 = v13;
    if ( v13 )
    {
      v8 = v13;
      v9 = 41222596;
      goto LABEL_28;
    }
    v10 = v36;
    v11 += (2 * v38 + 5) & 0xFFFFFFFFFFFFFFFCuLL;
  }
  v15 = (struct _NCryptAlgorithmName *)LocalAlloc(0, v11);
  v4 = v15;
  if ( !v15 )
  {
    v7 = -1073741801;
    v9 = 41812420;
LABEL_27:
    v8 = v7;
    goto LABEL_28;
  }
  v16 = v36;
  v17 = (WCHAR *)&v15[v36];
  v18 = v11 - 24 * v36;
  v19 = 0;
  while ( 1 )
  {
    LODWORD(v38) = v19;
    if ( v19 >= v16 )
      break;
    v20 = v19;
    v35 = pvBuffer;
    v33 = 0;
    v21 = StringCchLengthW(*((const unsigned __int16 **)pvBuffer + 2 * v19), 0x10000u, &v33);
    v7 = v21;
    if ( v21 )
    {
      v8 = v21;
      v9 = 42729924;
      goto LABEL_28;
    }
    v23 = v33;
    v24 = v20;
    v25 = v35;
    v4[v24].pszName = v17;
    v26 = (2 * (_DWORD)v23 + 5) & 0xFFFFFFFC;
    v4[v24].dwClass = v25[2 * v22 + 2];
    v4[v24].dwAlgOperations = 0;
    v27 = v25[2 * v22 + 3];
    LODWORD(v33) = (2 * v23 + 5) & 0xFFFFFFFC;
    v4[v24].dwFlags = v27;
    if ( (unsigned int)v26 > v18 )
    {
      v8 = -2147024362;
      v9 = 43516356;
      v7 = -2147024362;
      goto LABEL_28;
    }
    v28 = 2 * v23;
    memcpy_0(v17, *(const void **)&v25[2 * v22], v28);
    memset_0(&v17[v28 / 2], 0, (unsigned int)v26 - v28);
    v18 -= v33;
    v16 = v36;
    v19 = v38 + 1;
    v17 += v26 >> 1;
  }
  if ( v17 != (WCHAR *)((char *)v4 + v11) )
  {
    v7 = -2147418113;
    v9 = 44564932;
    goto LABEL_27;
  }
  v29 = SetAlgOperations(v16, v4);
  v7 = v29;
  if ( !v29 )
  {
    v30 = v37;
    v31 = v36;
    *a3 = v4;
    v4 = 0;
    v7 = 0;
    *v30 = v31;
    goto LABEL_29;
  }
  v8 = v29;
  v9 = 44761540;
LABEL_28:
  CSPrintErrorLineFile(v9, v8);
LABEL_29:
  if ( pvBuffer )
    BCryptFreeBuffer(pvBuffer);
  if ( v4 )
    myCngConfigFreeBuffer(v4);
  return v7;
}

```

## disassembly

```asm
0x180021948  mov     [rsp-38h+arg_10], rbx
0x18002194d  mov     [rsp-38h+arg_8], rdx
0x180021952  mov     [rsp-38h+arg_0], ecx
0x180021956  push    rbp
0x180021957  push    rsi
0x180021958  push    rdi
0x180021959  push    r12
0x18002195b  push    r13
0x18002195d  push    r14
0x18002195f  push    r15
0x180021961  mov     rbp, rsp
0x180021964  sub     rsp, 40h
0x180021968  xor     esi, esi
0x18002196a  mov     r13, r8
0x18002196d  mov     [rbp+arg_0], esi
0x180021970  mov     [rbp+pvBuffer], rsi
0x180021974  test    rdx, rdx
0x180021977  jz      loc_180021B70
0x18002197d  test    r8, r8
0x180021980  jz      loc_180021B70
0x180021986  mov     [r8], rsi
0x180021989  lea     rdx, [rbp+arg_0]; unsigned int *
0x18002198d  lea     r8, [rbp+pvBuffer]; struct _BCRYPT_ALGORITHM_IDENTIFIER **
0x180021991  mov     ecx, 9Ch; unsigned int
0x180021996  call    ?myBCEnumAlgorithms@@YAJKPEAKPEAPEAU_BCRYPT_ALGORITHM_IDENTIFIER@@K@Z; myBCEnumAlgorithms(ulong,ulong *,_BCRYPT_ALGORITHM_IDENTIFIER * *,ulong)
0x18002199b  mov     ebx, eax
0x18002199d  test    eax, eax
0x18002199f  jz      short loc_1800219AD
0x1800219a1  mov     edx, eax
0x1800219a3  mov     ecx, 26501C4h
0x1800219a8  jmp     loc_180021B7C
0x1800219ad  mov     ecx, [rbp+arg_0]
0x1800219b0  cmp     ecx, 10000h
0x1800219b6  jbe     short loc_1800219C9
0x1800219b8  mov     edx, 80070216h
0x1800219bd  mov     ecx, 26A01C4h
0x1800219c2  mov     ebx, edx
0x1800219c4  jmp     loc_180021B7C
0x1800219c9  lea     r14, [rcx+rcx*2]
0x1800219cd  shl     r14, 3
0x1800219d1  xor     r11d, r11d
0x1800219d4  cmp     r11d, ecx
0x1800219d7  jnb     short loc_180021A26
0x1800219d9  mov     rcx, [rbp+pvBuffer]
0x1800219dd  lea     r8, [rbp+arg_18]; unsigned __int64 *
0x1800219e1  mov     eax, r11d
0x1800219e4  mov     edx, 10000h; unsigned __int64
0x1800219e9  add     rax, rax
0x1800219ec  mov     [rbp+arg_18], rsi
0x1800219f0  mov     rcx, [rcx+rax*8]; unsigned __int16 *
0x1800219f4  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800219f9  mov     ebx, eax
0x1800219fb  test    eax, eax
0x1800219fd  jnz     short loc_180021A1A
0x1800219ff  mov     rax, [rbp+arg_18]
0x180021a03  mov     ecx, [rbp+arg_0]
0x180021a06  lea     rax, ds:5[rax*2]
0x180021a0e  and     rax, 0FFFFFFFFFFFFFFFCh
0x180021a12  add     r14, rax
0x180021a15  inc     r11d
0x180021a18  jmp     short loc_1800219D4
0x180021a1a  mov     edx, eax
0x180021a1c  mov     ecx, 27501C4h
0x180021a21  jmp     loc_180021B7C
0x180021a26  mov     rdx, r14; uBytes
0x180021a29  xor     ecx, ecx; uFlags
0x180021a2b  call    cs:__imp_LocalAlloc
0x180021a31  mov     rsi, rax
0x180021a34  test    rax, rax
0x180021a37  jnz     short loc_180021A48
0x180021a39  mov     ebx, 0C0000017h
0x180021a3e  mov     ecx, 27E01C4h
0x180021a43  jmp     loc_180021B7A
0x180021a48  mov     r8d, [rbp+arg_0]
0x180021a4c  mov     r15d, r14d
0x180021a4f  lea     rcx, [r8+r8*2]
0x180021a53  lea     r12, [rax+rcx*8]
0x180021a57  sub     r15d, r12d
0x180021a5a  add     r15d, esi
0x180021a5d  xor     eax, eax
0x180021a5f  mov     dword ptr [rbp+arg_18], eax
0x180021a62  cmp     eax, r8d
0x180021a65  jnb     loc_180021B2E
0x180021a6b  mov     r11d, eax
0x180021a6e  lea     r8, [rbp+var_20]; unsigned __int64 *
0x180021a72  mov     edi, eax
0x180021a74  add     r11, r11
0x180021a77  mov     rax, [rbp+pvBuffer]
0x180021a7b  mov     edx, 10000h; unsigned __int64
0x180021a80  mov     [rbp+var_10], rax
0x180021a84  mov     [rbp+var_20], 0
0x180021a8c  mov     rcx, [rax+r11*8]; unsigned __int16 *
0x180021a90  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180021a95  mov     ebx, eax
0x180021a97  test    eax, eax
0x180021a99  jnz     loc_180021B25
0x180021a9f  mov     rbx, [rbp+var_20]
0x180021aa3  lea     rcx, [rdi+rdi*2]
0x180021aa7  mov     rdx, [rbp+var_10]
0x180021aab  mov     [rsi+rcx*8], r12
0x180021aaf  lea     edi, ds:5[rbx*2]
0x180021ab6  mov     eax, [rdx+r11*8+8]
0x180021abb  and     edi, 0FFFFFFFCh
0x180021abe  mov     [rsi+rcx*8+8], eax
0x180021ac2  mov     dword ptr [rsi+rcx*8+0Ch], 0
0x180021aca  mov     eax, [rdx+r11*8+0Ch]
0x180021acf  mov     dword ptr [rbp+var_20], edi
0x180021ad2  mov     [rsi+rcx*8+10h], eax
0x180021ad6  cmp     edi, r15d
0x180021ad9  ja      short loc_180021B17
0x180021adb  mov     rdx, [rdx+r11*8]; Src
0x180021adf  add     rbx, rbx
0x180021ae2  mov     r8, rbx; Size
0x180021ae5  mov     rcx, r12; void *
0x180021ae8  call    memcpy_0
0x180021aed  mov     r8d, edi
0x180021af0  lea     rcx, [rbx+r12]; void *
0x180021af4  sub     r8, rbx; Size
0x180021af7  xor     edx, edx; Val
0x180021af9  call    memset_0
0x180021afe  sub     r15d, dword ptr [rbp+var_20]
0x180021b02  mov     eax, dword ptr [rbp+arg_18]
0x180021b05  mov     r8d, [rbp+arg_0]
0x180021b09  shr     rdi, 1
0x180021b0c  inc     eax
0x180021b0e  lea     r12, [r12+rdi*2]
0x180021b12  jmp     loc_180021A5F
0x180021b17  mov     edx, 80070216h
0x180021b1c  mov     ecx, 29801C4h
0x180021b21  mov     ebx, edx
0x180021b23  jmp     short loc_180021B7C
0x180021b25  mov     edx, eax
0x180021b27  mov     ecx, 28C01C4h
0x180021b2c  jmp     short loc_180021B7C
0x180021b2e  lea     rax, [r14+rsi]
0x180021b32  cmp     r12, rax
0x180021b35  jz      short loc_180021B43
0x180021b37  mov     ebx, 8000FFFFh
0x180021b3c  mov     ecx, 2A801C4h
0x180021b41  jmp     short loc_180021B7A
0x180021b43  mov     rdx, rsi; struct _NCryptAlgorithmName *
0x180021b46  mov     ecx, r8d; unsigned int
0x180021b49  call    ?SetAlgOperations@@YAJKPEAU_NCryptAlgorithmName@@@Z; SetAlgOperations(ulong,_NCryptAlgorithmName *)
0x180021b4e  mov     ebx, eax
0x180021b50  test    eax, eax
0x180021b52  jz      short loc_180021B5D
0x180021b54  mov     edx, eax
0x180021b56  mov     ecx, 2AB01C4h
0x180021b5b  jmp     short loc_180021B7C
0x180021b5d  mov     rcx, [rbp+arg_8]
0x180021b61  mov     eax, [rbp+arg_0]
0x180021b64  mov     [r13+0], rsi
0x180021b68  xor     esi, esi
0x180021b6a  xor     ebx, ebx
0x180021b6c  mov     [rcx], eax
0x180021b6e  jmp     short loc_180021B81
0x180021b70  mov     ebx, 80004003h
0x180021b75  mov     ecx, 25601C4h; unsigned int
0x180021b7a  mov     edx, ebx; int
0x180021b7c  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180021b81  mov     rcx, [rbp+pvBuffer]; pvBuffer
0x180021b85  test    rcx, rcx
0x180021b88  jz      short loc_180021B90
0x180021b8a  call    cs:__imp_BCryptFreeBuffer
0x180021b90  test    rsi, rsi
0x180021b93  jz      short loc_180021B9D
0x180021b95  mov     rcx, rsi; void *
0x180021b98  call    ?myCngConfigFreeBuffer@@YAJPEAX@Z; myCngConfigFreeBuffer(void *)
0x180021b9d  mov     eax, ebx
0x180021b9f  mov     rbx, [rsp+40h+arg_10]
0x180021ba7  add     rsp, 40h
0x180021bab  pop     r15
0x180021bad  pop     r14
0x180021baf  pop     r13
0x180021bb1  pop     r12
0x180021bb3  pop     rdi
0x180021bb4  pop     rsi
0x180021bb5  pop     rbp
0x180021bb6  retn
```
