# Ssl3ComputeFinishedHash

- ea: `0x18001fd90`
- end: `0x180020242`
- name: `Ssl3ComputeFinishedHash`
- size: `1202`
- prototype: `__int64 __fastcall(__int64, __int64, void *, void *, UCHAR *, int, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800091e0`

## callees

- `0x180009160`
- `0x18000b654`
- `0x180018ac0`
- `0x18001fd90`
- `0x180024ef0`
- `0x180026010`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18001fef9`
- `bcrypt!BCryptHashData` at `0x18001ff23`
- `bcrypt!BCryptHashData` at `0x18001ff48`
- `bcrypt!BCryptHashData` at `0x18001ffcf`
- `bcrypt!BCryptHashData` at `0x18001fff7`
- `bcrypt!BCryptHashData` at `0x180020020`
- `bcrypt!BCryptHashData` at `0x18002007e`
- `bcrypt!BCryptHashData` at `0x1800200a2`
- `bcrypt!BCryptHashData` at `0x1800200ca`
- `bcrypt!BCryptHashData` at `0x180020152`
- `bcrypt!BCryptHashData` at `0x18002017b`
- `bcrypt!BCryptHashData` at `0x1800201a0`
- `bcrypt!BCryptHashData` at `0x18001fef9`
- `bcrypt!BCryptHashData` at `0x18001ff23`
- `bcrypt!BCryptHashData` at `0x18001ff48`
- `bcrypt!BCryptHashData` at `0x18001ffcf`
- `bcrypt!BCryptHashData` at `0x18001fff7`
- `bcrypt!BCryptHashData` at `0x180020020`
- `bcrypt!BCryptHashData` at `0x18002007e`
- `bcrypt!BCryptHashData` at `0x1800200a2`
- `bcrypt!BCryptHashData` at `0x1800200ca`
- `bcrypt!BCryptHashData` at `0x180020152`
- `bcrypt!BCryptHashData` at `0x18002017b`
- `bcrypt!BCryptHashData` at `0x1800201a0`
- `bcrypt!BCryptCreateHash` at `0x18001ffa7`
- `bcrypt!BCryptCreateHash` at `0x18002012d`
- `bcrypt!BCryptCreateHash` at `0x18001ffa7`
- `bcrypt!BCryptCreateHash` at `0x18002012d`
- `bcrypt!BCryptFinishHash` at `0x18001ff6a`
- `bcrypt!BCryptFinishHash` at `0x180020048`
- `bcrypt!BCryptFinishHash` at `0x1800200f2`
- `bcrypt!BCryptFinishHash` at `0x1800201c5`
- `bcrypt!BCryptFinishHash` at `0x18001ff6a`
- `bcrypt!BCryptFinishHash` at `0x180020048`
- `bcrypt!BCryptFinishHash` at `0x1800200f2`
- `bcrypt!BCryptFinishHash` at `0x1800201c5`
- `bcrypt!BCryptDestroyHash` at `0x180020063`
- `bcrypt!BCryptDestroyHash` at `0x1800201e0`
- `bcrypt!BCryptDestroyHash` at `0x180020200`
- `bcrypt!BCryptDestroyHash` at `0x180020063`
- `bcrypt!BCryptDestroyHash` at `0x1800201e0`
- `bcrypt!BCryptDestroyHash` at `0x180020200`

## string_xrefs

- `0x18001fdf8`: `onecore\ds\security\cryptoapi\ncrypt\schannel\ssl3key.c`

## pseudocode

```c
__int64 __fastcall Ssl3ComputeFinishedHash(__int64 a1, __int64 a2, void *a3, void *a4, UCHAR *a5, int a6, char a7)
{
  UCHAR *p_phHash; // rdi
  NTSTATUS v12; // ebx
  __int64 v13; // r9
  __int64 v14; // rcx
  unsigned int v15; // eax
  __int64 v16; // rbx
  unsigned __int64 v17; // rcx
  __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  void *v20; // rsp
  void *v21; // rsp
  UCHAR *v22; // rax
  UCHAR *v23; // rsi
  NTSTATUS v24; // eax
  UCHAR *v25; // r14
  PUCHAR v26; // r15
  __int64 v28; // [rsp+0h] [rbp-40h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp+0h] BYREF
  PUCHAR v30[2]; // [rsp+48h] [rbp+8h] BYREF
  UCHAR pbOutput[48]; // [rsp+58h] [rbp+18h] BYREF

  v30[0] = a5;
  phHash = 0;
  if ( a6 != 36 )
  {
    p_phHash = 0;
    v12 = -2146893785;
    v13 = 659;
    v14 = 2148073511LL;
LABEL_3:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\ssl3key.c", v13);
    goto LABEL_63;
  }
  v15 = *(_DWORD *)(a1 + 352);
  v16 = *(unsigned int *)(a1 + 320);
  if ( (unsigned int)v16 <= v15 )
    v16 = v15;
  p_phHash = 0;
  if ( !(_DWORD)v16 )
    goto LABEL_71;
  if ( (unsigned int)v16 > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_71;
  v17 = (unsigned int)v16 + g_ulAdditionalProbeSize + 8;
  if ( v17 < (unsigned int)v16 || !(unsigned int)VerifyStackAvailable(v17) )
    goto LABEL_71;
  v18 = v16 + 23;
  if ( v16 + 23 <= (unsigned __int64)(v16 + 8) )
    v18 = 0xFFFFFFFFFFFFFF0LL;
  v19 = v18 & 0xFFFFFFFFFFFFFFF0uLL;
  v20 = alloca(v19);
  v21 = alloca(v19);
  p_phHash = (UCHAR *)&phHash;
  if ( &v28 == (__int64 *)-64LL || (LODWORD(phHash) = 1801679955, (p_phHash = (UCHAR *)v30) == 0) )
  {
LABEL_71:
    if ( v16 + 8 >= (unsigned __int64)(unsigned int)v16 )
    {
      v22 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      p_phHash = v22;
      if ( v22 )
      {
        *(_DWORD *)v22 = 1885431112;
        p_phHash = v22 + 8;
      }
    }
  }
  if ( !p_phHash )
  {
    v12 = -2146893810;
    v13 = 676;
    v14 = 2148073486LL;
    goto LABEL_3;
  }
  if ( (a7 & 1) != 0 )
  {
    v23 = (UCHAR *)"CLNT";
    goto LABEL_23;
  }
  if ( (a7 & 2) != 0 )
  {
    v23 = (UCHAR *)"SRVR";
LABEL_23:
    v24 = BCryptHashData(a3, v23, 4u, 0);
    v12 = v24;
    if ( v24 >= 0 )
    {
      v25 = (UCHAR *)(a2 + 28);
      v24 = BCryptHashData(a3, v25, 0x30u, 0);
      v12 = v24;
      if ( v24 >= 0 )
      {
        v24 = BCryptHashData(
                a3,
                (PUCHAR)"666666666666666666666666666666666666666666666666ERROR_INVALID_PARAMETER",
                0x30u,
                0);
        v12 = v24;
        if ( v24 >= 0 )
        {
          v12 = BCryptFinishHash(a3, pbOutput, 0x10u, 0);
          if ( v12 >= 0 )
          {
            v24 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)(a1 + 304), &phHash, p_phHash, *(_DWORD *)(a1 + 320), 0, 0, 0);
            v12 = v24;
            if ( v24 < 0 )
            {
              v13 = 764;
              goto LABEL_25;
            }
            v24 = BCryptHashData(phHash, v25, 0x30u, 0);
            v12 = v24;
            if ( v24 < 0 )
            {
              v13 = 775;
              goto LABEL_25;
            }
            v24 = BCryptHashData(phHash, (PUCHAR)&g_rgbPad2, 0x30u, 0);
            v12 = v24;
            if ( v24 < 0 )
            {
              v13 = 786;
              goto LABEL_25;
            }
            v24 = BCryptHashData(phHash, pbOutput, 0x10u, 0);
            v12 = v24;
            if ( v24 < 0 )
            {
              v13 = 797;
              goto LABEL_25;
            }
            v26 = v30[0];
            v24 = BCryptFinishHash(phHash, v30[0], 0x10u, 0);
            v12 = v24;
            if ( v24 < 0 )
            {
              v13 = 808;
              goto LABEL_25;
            }
            BCryptDestroyHash(phHash);
            phHash = 0;
            v24 = BCryptHashData(a4, v23, 4u, 0);
            v12 = v24;
            if ( v24 < 0 )
            {
              v13 = 827;
              goto LABEL_25;
            }
            v24 = BCryptHashData(a4, v25, 0x30u, 0);
            v12 = v24;
            if ( v24 < 0 )
            {
              v13 = 838;
              goto LABEL_25;
            }
            v24 = BCryptHashData(
                    a4,
                    (PUCHAR)"666666666666666666666666666666666666666666666666ERROR_INVALID_PARAMETER",
                    0x28u,
                    0);
            v12 = v24;
            if ( v24 < 0 )
            {
              v13 = 849;
              goto LABEL_25;
            }
            v12 = BCryptFinishHash(a4, pbOutput, 0x14u, 0);
            if ( v12 >= 0 )
            {
              v24 = BCryptCreateHash(
                      *(BCRYPT_ALG_HANDLE *)(a1 + 336),
                      &phHash,
                      p_phHash,
                      *(_DWORD *)(a1 + 352),
                      0,
                      0,
                      0);
              v12 = v24;
              if ( v24 >= 0 )
              {
                v24 = BCryptHashData(phHash, v25, 0x30u, 0);
                v12 = v24;
                if ( v24 >= 0 )
                {
                  v24 = BCryptHashData(phHash, (PUCHAR)&g_rgbPad2, 0x28u, 0);
                  v12 = v24;
                  if ( v24 >= 0 )
                  {
                    v24 = BCryptHashData(phHash, pbOutput, 0x14u, 0);
                    v12 = v24;
                    if ( v24 >= 0 )
                    {
                      v24 = BCryptFinishHash(phHash, v26 + 16, 0x14u, 0);
                      v12 = v24;
                      if ( v24 >= 0 )
                      {
                        BCryptDestroyHash(phHash);
                        v12 = 0;
                        phHash = 0;
LABEL_66:
                        if ( *((_DWORD *)p_phHash - 2) == 1885431112 )
                          ((void (*)(void))g_pfnFree)();
                        return (unsigned int)v12;
                      }
                      v13 = 922;
                    }
                    else
                    {
                      v13 = 911;
                    }
                  }
                  else
                  {
                    v13 = 900;
                  }
                }
                else
                {
                  v13 = 889;
                }
              }
              else
              {
                v13 = 878;
              }
              goto LABEL_25;
            }
            v13 = 860;
          }
          else
          {
            v13 = 746;
          }
          v14 = (unsigned int)v12;
          goto LABEL_3;
        }
        v13 = 735;
      }
      else
      {
        v13 = 724;
      }
    }
    else
    {
      v13 = 713;
    }
LABEL_25:
    v14 = (unsigned int)v24;
    goto LABEL_3;
  }
  v12 = -2146893815;
LABEL_63:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( p_phHash )
    goto LABEL_66;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001fd90  push    rbp
0x18001fd92  push    rbx
0x18001fd93  push    rsi
0x18001fd94  push    rdi
0x18001fd95  push    r12
0x18001fd97  push    r13
0x18001fd99  push    r14
0x18001fd9b  push    r15
0x18001fd9d  sub     rsp, 98h
0x18001fda4  lea     rbp, [rsp+40h]
0x18001fda9  mov     rax, cs:__security_cookie
0x18001fdb0  xor     rax, rbp
0x18001fdb3  mov     [rbp+90h+var_48], rax
0x18001fdb7  cmp     [rbp+90h+arg_28], 24h ; '$'
0x18001fdbe  mov     r12, r9
0x18001fdc1  mov     rax, [rbp+90h+arg_20]
0x18001fdc8  mov     r15, r8
0x18001fdcb  mov     [rbp+90h+var_88], rax
0x18001fdcf  mov     r14, rdx
0x18001fdd2  mov     r13, rcx
0x18001fdd5  mov     [rbp+90h+phHash], 0
0x18001fddd  jz      short loc_18001FE09
0x18001fddf  xor     edi, edi
0x18001fde1  mov     ebx, 80090027h
0x18001fde6  mov     r9d, 293h
0x18001fdec  mov     ecx, 80090027h
0x18001fdf1  lea     rdx, aStatus; "Status"
0x18001fdf8  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001fdff  call    DebugTraceError
0x18001fe04  jmp     loc_1800201F7
0x18001fe09  mov     eax, [rcx+160h]
0x18001fe0f  mov     ebx, [rcx+140h]
0x18001fe15  cmp     ebx, eax
0x18001fe17  cmovbe  ebx, eax
0x18001fe1a  xor     edi, edi
0x18001fe1c  test    ebx, ebx
0x18001fe1e  jz      short loc_18001FE83
0x18001fe20  mov     esi, ebx
0x18001fe22  cmp     rsi, cs:g_ulMaxStackAllocSize
0x18001fe29  ja      short loc_18001FE83
0x18001fe2b  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001fe32  add     rcx, 8
0x18001fe36  add     rcx, rsi
0x18001fe39  cmp     rcx, rsi
0x18001fe3c  jb      short loc_18001FE83
0x18001fe3e  call    VerifyStackAvailable
0x18001fe43  test    eax, eax
0x18001fe45  jz      short loc_18001FE83
0x18001fe47  lea     rax, [rbx+8]
0x18001fe4b  lea     rcx, [rax+0Fh]
0x18001fe4f  cmp     rcx, rax
0x18001fe52  ja      short loc_18001FE5E
0x18001fe54  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001fe5e  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001fe62  mov     rax, rcx
0x18001fe65  call    _alloca_probe
0x18001fe6a  sub     rsp, rcx
0x18001fe6d  lea     rdi, [rsp+0D0h+phHash]
0x18001fe72  test    rdi, rdi
0x18001fe75  jz      short loc_18001FE83
0x18001fe77  mov     dword ptr [rdi], 6B637453h
0x18001fe7d  add     rdi, 8
0x18001fe81  jnz     short loc_18001FEAC
0x18001fe83  mov     eax, ebx
0x18001fe85  lea     rcx, [rbx+8]
0x18001fe89  cmp     rcx, rax
0x18001fe8c  jb      short loc_18001FEAC
0x18001fe8e  mov     rax, cs:g_pfnAllocate
0x18001fe95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe9a  mov     rdi, rax
0x18001fe9d  test    rax, rax
0x18001fea0  jz      short loc_18001FEAC
0x18001fea2  mov     dword ptr [rax], 70616548h
0x18001fea8  add     rdi, 8
0x18001feac  test    rdi, rdi
0x18001feaf  jnz     short loc_18001FEC6
0x18001feb1  mov     ebx, 8009000Eh
0x18001feb6  mov     r9d, 2A4h
0x18001febc  mov     ecx, 8009000Eh
0x18001fec1  jmp     loc_18001FDF1
0x18001fec6  test    [rbp+90h+arg_30], 1
0x18001fecd  jz      short loc_18001FED8
0x18001fecf  lea     rsi, aClnt; "CLNT"
0x18001fed6  jmp     short loc_18001FEEC
0x18001fed8  test    [rbp+90h+arg_30], 2
0x18001fedf  jz      loc_1800201F2
0x18001fee5  lea     rsi, aSrvr; "SRVR"
0x18001feec  xor     r9d, r9d; dwFlags
0x18001feef  mov     rdx, rsi; pbInput
0x18001fef2  mov     rcx, r15; hHash
0x18001fef5  lea     r8d, [r9+4]; cbInput
0x18001fef9  call    cs:__imp_BCryptHashData
0x18001feff  mov     ebx, eax
0x18001ff01  test    eax, eax
0x18001ff03  jns     short loc_18001FF12
0x18001ff05  mov     r9d, 2C9h
0x18001ff0b  mov     ecx, eax
0x18001ff0d  jmp     loc_18001FDF1
0x18001ff12  xor     r9d, r9d; dwFlags
0x18001ff15  add     r14, 1Ch
0x18001ff19  mov     rdx, r14; pbInput
0x18001ff1c  mov     rcx, r15; hHash
0x18001ff1f  lea     r8d, [r9+30h]; cbInput
0x18001ff23  call    cs:__imp_BCryptHashData
0x18001ff29  mov     ebx, eax
0x18001ff2b  test    eax, eax
0x18001ff2d  jns     short loc_18001FF37
0x18001ff2f  mov     r9d, 2D4h
0x18001ff35  jmp     short loc_18001FF0B
0x18001ff37  xor     r9d, r9d; dwFlags
0x18001ff3a  lea     rdx, g_rgbPad1; "666666666666666666666666666666666666666"...
0x18001ff41  mov     rcx, r15; hHash
0x18001ff44  lea     r8d, [r9+30h]; cbInput
0x18001ff48  call    cs:__imp_BCryptHashData
0x18001ff4e  mov     ebx, eax
0x18001ff50  test    eax, eax
0x18001ff52  jns     short loc_18001FF5C
0x18001ff54  mov     r9d, 2DFh
0x18001ff5a  jmp     short loc_18001FF0B
0x18001ff5c  xor     r9d, r9d; dwFlags
0x18001ff5f  lea     rdx, [rbp+90h+pbOutput]; pbOutput
0x18001ff63  mov     rcx, r15; hHash
0x18001ff66  lea     r8d, [r9+10h]; cbOutput
0x18001ff6a  call    cs:__imp_BCryptFinishHash
0x18001ff70  mov     ebx, eax
0x18001ff72  xor     eax, eax
0x18001ff74  test    ebx, ebx
0x18001ff76  jns     short loc_18001FF85
0x18001ff78  mov     r9d, 2EAh
0x18001ff7e  mov     ecx, ebx
0x18001ff80  jmp     loc_18001FDF1
0x18001ff85  mov     r9d, [r13+140h]; cbHashObject
0x18001ff8c  lea     rdx, [rbp+90h+phHash]; phHash
0x18001ff90  mov     rcx, [r13+130h]; hAlgorithm
0x18001ff97  mov     r8, rdi; pbHashObject
0x18001ff9a  mov     [rsp+0D0h+dwFlags], eax; dwFlags
0x18001ff9e  mov     [rsp+0D0h+cbSecret], eax; cbSecret
0x18001ffa2  mov     [rsp+0D0h+pbSecret], rax; pbSecret
0x18001ffa7  call    cs:__imp_BCryptCreateHash
0x18001ffad  mov     ebx, eax
0x18001ffaf  test    eax, eax
0x18001ffb1  jns     short loc_18001FFBE
0x18001ffb3  mov     r9d, 2FCh
0x18001ffb9  jmp     loc_18001FF0B
0x18001ffbe  mov     rcx, [rbp+90h+phHash]; hHash
0x18001ffc2  xor     r9d, r9d; dwFlags
0x18001ffc5  mov     rdx, r14; pbInput
0x18001ffc8  lea     r15d, [r9+30h]
0x18001ffcc  mov     r8d, r15d; cbInput
0x18001ffcf  call    cs:__imp_BCryptHashData
0x18001ffd5  mov     ebx, eax
0x18001ffd7  test    eax, eax
0x18001ffd9  jns     short loc_18001FFE6
0x18001ffdb  mov     r9d, 307h
0x18001ffe1  jmp     loc_18001FF0B
0x18001ffe6  mov     rcx, [rbp+90h+phHash]; hHash
0x18001ffea  lea     rdx, g_rgbPad2; pbInput
0x18001fff1  xor     r9d, r9d; dwFlags
0x18001fff4  mov     r8d, r15d; cbInput
0x18001fff7  call    cs:__imp_BCryptHashData
0x18001fffd  mov     ebx, eax
0x18001ffff  test    eax, eax
0x180020001  jns     short loc_18002000E
0x180020003  mov     r9d, 312h
0x180020009  jmp     loc_18001FF0B
0x18002000e  mov     rcx, [rbp+90h+phHash]; hHash
0x180020012  lea     rdx, [rbp+90h+pbOutput]; pbInput
0x180020016  xor     r9d, r9d; dwFlags
0x180020019  lea     r15d, [r9+10h]
0x18002001d  mov     r8d, r15d; cbInput
0x180020020  call    cs:__imp_BCryptHashData
0x180020026  mov     ebx, eax
0x180020028  test    eax, eax
0x18002002a  jns     short loc_180020037
0x18002002c  mov     r9d, 31Dh
0x180020032  jmp     loc_18001FF0B
0x180020037  mov     rcx, [rbp+90h+phHash]; hHash
0x18002003b  mov     r8d, r15d; cbOutput
0x18002003e  mov     r15, [rbp+90h+var_88]
0x180020042  xor     r9d, r9d; dwFlags
0x180020045  mov     rdx, r15; pbOutput
0x180020048  call    cs:__imp_BCryptFinishHash
0x18002004e  mov     ebx, eax
0x180020050  test    eax, eax
0x180020052  jns     short loc_18002005F
0x180020054  mov     r9d, 328h
0x18002005a  jmp     loc_18001FF0B
0x18002005f  mov     rcx, [rbp+90h+phHash]; hHash
0x180020063  call    cs:__imp_BCryptDestroyHash
0x180020069  xor     r9d, r9d; dwFlags
0x18002006c  mov     [rbp+90h+phHash], 0
0x180020074  mov     rdx, rsi; pbInput
0x180020077  mov     rcx, r12; hHash
0x18002007a  lea     r8d, [r9+4]; cbInput
0x18002007e  call    cs:__imp_BCryptHashData
0x180020084  mov     ebx, eax
0x180020086  test    eax, eax
0x180020088  jns     short loc_180020095
0x18002008a  mov     r9d, 33Bh
0x180020090  jmp     loc_18001FF0B
0x180020095  xor     r9d, r9d; dwFlags
0x180020098  mov     rdx, r14; pbInput
0x18002009b  mov     rcx, r12; hHash
0x18002009e  lea     r8d, [r9+30h]; cbInput
0x1800200a2  call    cs:__imp_BCryptHashData
0x1800200a8  mov     ebx, eax
0x1800200aa  test    eax, eax
0x1800200ac  jns     short loc_1800200B9
0x1800200ae  mov     r9d, 346h
0x1800200b4  jmp     loc_18001FF0B
0x1800200b9  xor     r9d, r9d; dwFlags
0x1800200bc  lea     rdx, g_rgbPad1; "666666666666666666666666666666666666666"...
0x1800200c3  mov     rcx, r12; hHash
0x1800200c6  lea     r8d, [r9+28h]; cbInput
0x1800200ca  call    cs:__imp_BCryptHashData
0x1800200d0  mov     ebx, eax
0x1800200d2  test    eax, eax
0x1800200d4  jns     short loc_1800200E1
0x1800200d6  mov     r9d, 351h
0x1800200dc  jmp     loc_18001FF0B
0x1800200e1  xor     r9d, r9d; dwFlags
0x1800200e4  lea     rdx, [rbp+90h+pbOutput]; pbOutput
0x1800200e8  mov     rcx, r12; hHash
0x1800200eb  lea     esi, [r9+14h]
0x1800200ef  mov     r8d, esi; cbOutput
0x1800200f2  call    cs:__imp_BCryptFinishHash
0x1800200f8  mov     ebx, eax
0x1800200fa  xor     eax, eax
0x1800200fc  test    ebx, ebx
0x1800200fe  jns     short loc_18002010B
0x180020100  mov     r9d, 35Ch
0x180020106  jmp     loc_18001FF7E
0x18002010b  mov     r9d, [r13+160h]; cbHashObject
0x180020112  lea     rdx, [rbp+90h+phHash]; phHash
0x180020116  mov     rcx, [r13+150h]; hAlgorithm
0x18002011d  mov     r8, rdi; pbHashObject
0x180020120  mov     [rsp+0D0h+dwFlags], eax; dwFlags
0x180020124  mov     [rsp+0D0h+cbSecret], eax; cbSecret
0x180020128  mov     [rsp+0D0h+pbSecret], rax; pbSecret
0x18002012d  call    cs:__imp_BCryptCreateHash
0x180020133  mov     ebx, eax
0x180020135  test    eax, eax
0x180020137  jns     short loc_180020144
0x180020139  mov     r9d, 36Eh
0x18002013f  jmp     loc_18001FF0B
0x180020144  mov     rcx, [rbp+90h+phHash]; hHash
0x180020148  xor     r9d, r9d; dwFlags
0x18002014b  mov     rdx, r14; pbInput
0x18002014e  lea     r8d, [r9+30h]; cbInput
0x180020152  call    cs:__imp_BCryptHashData
0x180020158  mov     ebx, eax
0x18002015a  test    eax, eax
0x18002015c  jns     short loc_180020169
0x18002015e  mov     r9d, 379h
0x180020164  jmp     loc_18001FF0B
0x180020169  mov     rcx, [rbp+90h+phHash]; hHash
0x18002016d  lea     rdx, g_rgbPad2; pbInput
0x180020174  xor     r9d, r9d; dwFlags
0x180020177  lea     r8d, [r9+28h]; cbInput
0x18002017b  call    cs:__imp_BCryptHashData
0x180020181  mov     ebx, eax
0x180020183  test    eax, eax
0x180020185  jns     short loc_180020192
0x180020187  mov     r9d, 384h
0x18002018d  jmp     loc_18001FF0B
0x180020192  mov     rcx, [rbp+90h+phHash]; hHash
0x180020196  lea     rdx, [rbp+90h+pbOutput]; pbInput
0x18002019a  xor     r9d, r9d; dwFlags
0x18002019d  mov     r8d, esi; cbInput
0x1800201a0  call    cs:__imp_BCryptHashData
0x1800201a6  mov     ebx, eax
0x1800201a8  test    eax, eax
0x1800201aa  jns     short loc_1800201B7
0x1800201ac  mov     r9d, 38Fh
0x1800201b2  jmp     loc_18001FF0B
0x1800201b7  mov     rcx, [rbp+90h+phHash]; hHash
0x1800201bb  lea     rdx, [r15+10h]; pbOutput
0x1800201bf  xor     r9d, r9d; dwFlags
0x1800201c2  mov     r8d, esi; cbOutput
0x1800201c5  call    cs:__imp_BCryptFinishHash
0x1800201cb  mov     ebx, eax
0x1800201cd  test    eax, eax
0x1800201cf  jns     short loc_1800201DC
0x1800201d1  mov     r9d, 39Ah
0x1800201d7  jmp     loc_18001FF0B
0x1800201dc  mov     rcx, [rbp+90h+phHash]; hHash
0x1800201e0  call    cs:__imp_BCryptDestroyHash
0x1800201e6  xor     ebx, ebx
0x1800201e8  mov     [rbp+90h+phHash], 0
0x1800201f0  jmp     short loc_18002020B
0x1800201f2  mov     ebx, 80090009h
0x1800201f7  mov     rcx, [rbp+90h+phHash]; hHash
0x1800201fb  test    rcx, rcx
0x1800201fe  jz      short loc_180020206
0x180020200  call    cs:__imp_BCryptDestroyHash
0x180020206  test    rdi, rdi
0x180020209  jz      short loc_180020223
0x18002020b  lea     rcx, [rdi-8]
0x18002020f  cmp     dword ptr [rcx], 70616548h
0x180020215  jnz     short loc_180020223
  ... truncated ...
```
