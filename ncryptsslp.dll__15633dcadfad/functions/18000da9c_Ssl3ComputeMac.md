# Ssl3ComputeMac

- ea: `0x18000da9c`
- end: `0x18000de97`
- name: `Ssl3ComputeMac`
- size: `1019`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, ULONG cbInput, __int64, ULONG cbOutput)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000c1c0`
- `0x18000f2d0`

## callees

- `0x180009160`
- `0x18000b594`
- `0x18000b654`
- `0x18000da9c`
- `0x180018ac0`
- `0x180024ef0`
- `0x180026010`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18000dc77`
- `bcrypt!BCryptHashData` at `0x18000dc9c`
- `bcrypt!BCryptHashData` at `0x18000dce4`
- `bcrypt!BCryptHashData` at `0x18000dd09`
- `bcrypt!BCryptHashData` at `0x18000dda0`
- `bcrypt!BCryptHashData` at `0x18000ddc9`
- `bcrypt!BCryptHashData` at `0x18000ddf3`
- `bcrypt!BCryptHashData` at `0x18000dc77`
- `bcrypt!BCryptHashData` at `0x18000dc9c`
- `bcrypt!BCryptHashData` at `0x18000dce4`
- `bcrypt!BCryptHashData` at `0x18000dd09`
- `bcrypt!BCryptHashData` at `0x18000dda0`
- `bcrypt!BCryptHashData` at `0x18000ddc9`
- `bcrypt!BCryptHashData` at `0x18000ddf3`
- `bcrypt!BCryptCreateHash` at `0x18000dc3c`
- `bcrypt!BCryptCreateHash` at `0x18000dd7a`
- `bcrypt!BCryptCreateHash` at `0x18000dc3c`
- `bcrypt!BCryptCreateHash` at `0x18000dd7a`
- `bcrypt!BCryptFinishHash` at `0x18000dd36`
- `bcrypt!BCryptFinishHash` at `0x18000de1c`
- `bcrypt!BCryptFinishHash` at `0x18000dd36`
- `bcrypt!BCryptFinishHash` at `0x18000de1c`
- `bcrypt!BCryptDestroyHash` at `0x18000dd51`
- `bcrypt!BCryptDestroyHash` at `0x18000de37`
- `bcrypt!BCryptDestroyHash` at `0x18000de4c`
- `bcrypt!BCryptDestroyHash` at `0x18000dd51`
- `bcrypt!BCryptDestroyHash` at `0x18000de37`
- `bcrypt!BCryptDestroyHash` at `0x18000de4c`

## string_xrefs

- `0x18000dbe6`: `onecore\ds\security\cryptoapi\ncrypt\schannel\ssl3key.c`
- `0x18000dc4e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\ssl3key.c`

## pseudocode

```c
__int64 __fastcall Ssl3ComputeMac(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned __int64 a4,
        UCHAR *a5,
        ULONG cbInput,
        UCHAR *a7,
        ULONG cbOutput)
{
  __int64 v10; // rax
  int v11; // edx
  ULONG v12; // r14d
  bool v13; // zf
  __int64 v14; // r15
  UCHAR *p_phHash; // rdi
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // rcx
  __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  void *v20; // rsp
  void *v21; // rsp
  UCHAR *v22; // rax
  unsigned int v23; // ebx
  NTSTATUS v24; // eax
  __int64 v25; // r9
  ULONG v26; // r9d
  void *v27; // rcx
  __int64 v29; // [rsp+0h] [rbp-40h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp+0h] BYREF
  int v31; // [rsp+48h] [rbp+8h] BYREF
  ULONG v32; // [rsp+4Ch] [rbp+Ch]
  unsigned __int64 v33; // [rsp+50h] [rbp+10h]
  PUCHAR v34; // [rsp+58h] [rbp+18h]
  PUCHAR v35; // [rsp+60h] [rbp+20h]
  UCHAR pbInput[8]; // [rsp+70h] [rbp+30h] BYREF
  char v37; // [rsp+78h] [rbp+38h]
  char v38; // [rsp+79h] [rbp+39h]
  char v39; // [rsp+7Ah] [rbp+3Ah]
  UCHAR pbOutput[48]; // [rsp+80h] [rbp+40h] BYREF

  v34 = a5;
  v35 = a7;
  v10 = *(_QWORD *)(a2 + 16);
  v11 = 32771;
  v12 = 48;
  phHash = 0;
  v33 = a4;
  v31 = a3;
  v13 = *(_DWORD *)(v10 + 64) == 32771;
  if ( *(_DWORD *)(v10 + 64) != 32771 )
    v12 = 40;
  v32 = v12;
  v14 = 304;
  if ( !v13 )
    v14 = 336;
  p_phHash = 0;
  v16 = *(unsigned int *)(v14 + a1 + 16);
  if ( *(_DWORD *)(v14 + a1 + 16) )
  {
    if ( v16 <= g_ulMaxStackAllocSize )
    {
      v17 = v16 + g_ulAdditionalProbeSize + 8;
      if ( v17 >= v16 )
      {
        if ( (unsigned int)VerifyStackAvailable(v17) )
        {
          v18 = v16 + 23;
          if ( v16 + 23 <= v16 + 8 )
            v18 = 0xFFFFFFFFFFFFFF0LL;
          v19 = v18 & 0xFFFFFFFFFFFFFFF0uLL;
          v20 = alloca(v19);
          v21 = alloca(v19);
          p_phHash = (UCHAR *)&phHash;
          if ( &v29 != (__int64 *)-64LL )
          {
            LODWORD(phHash) = 1801679955;
            p_phHash = (UCHAR *)&v31;
            if ( &v31 )
              goto LABEL_20;
          }
        }
      }
    }
  }
  if ( v16 + 8 < v16 )
  {
LABEL_16:
    if ( !p_phHash )
      goto LABEL_17;
LABEL_20:
    v24 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)(v14 + a1), &phHash, p_phHash, *(_DWORD *)(v14 + a1 + 16), 0, 0, 0);
    v23 = v24;
    if ( v24 >= 0 )
    {
      v24 = BCryptHashData(phHash, (PUCHAR)(a2 + 56), *(_DWORD *)(a2 + 104), 0);
      v23 = v24;
      if ( v24 >= 0 )
      {
        v24 = BCryptHashData(
                phHash,
                (PUCHAR)"666666666666666666666666666666666666666666666666ERROR_INVALID_PARAMETER",
                v12,
                0);
        v23 = v24;
        if ( v24 >= 0 )
        {
          *(_QWORD *)pbInput = _byteswap_uint64(v33);
          v37 = v31;
          v38 = BYTE1(cbInput);
          v39 = cbInput;
          v24 = BCryptHashData(phHash, pbInput, 0xBu, 0);
          v23 = v24;
          if ( v24 >= 0 )
          {
            v24 = BCryptHashData(phHash, v34, cbInput, 0);
            v23 = v24;
            if ( v24 >= 0 )
            {
              v24 = BCryptFinishHash(phHash, pbOutput, *(_DWORD *)(*(_QWORD *)(a2 + 16) + 68LL), 0);
              v23 = v24;
              if ( v24 >= 0 )
              {
                BCryptDestroyHash(phHash);
                v26 = *(_DWORD *)(v14 + a1 + 16);
                v27 = *(void **)(v14 + a1);
                phHash = 0;
                v24 = BCryptCreateHash(v27, &phHash, p_phHash, v26, 0, 0, 0);
                v23 = v24;
                if ( v24 >= 0 )
                {
                  v24 = BCryptHashData(phHash, (PUCHAR)(a2 + 56), *(_DWORD *)(a2 + 104), 0);
                  v23 = v24;
                  if ( v24 >= 0 )
                  {
                    v24 = BCryptHashData(phHash, (PUCHAR)&g_rgbPad2, v32, 0);
                    v23 = v24;
                    if ( v24 >= 0 )
                    {
                      v24 = BCryptHashData(phHash, pbOutput, *(_DWORD *)(*(_QWORD *)(a2 + 16) + 68LL), 0);
                      v23 = v24;
                      if ( v24 >= 0 )
                      {
                        v24 = BCryptFinishHash(phHash, v35, cbOutput, 0);
                        v23 = v24;
                        if ( v24 >= 0 )
                        {
                          BCryptDestroyHash(phHash);
                          v23 = 0;
                          phHash = 0;
                          goto LABEL_44;
                        }
                        v25 = 582;
                      }
                      else
                      {
                        v25 = 570;
                      }
                    }
                    else
                    {
                      v25 = 559;
                    }
                  }
                  else
                  {
                    v25 = 547;
                  }
                }
                else
                {
                  v25 = 535;
                }
              }
              else
              {
                v25 = 514;
              }
            }
            else
            {
              v25 = 502;
            }
          }
          else
          {
            v25 = 490;
          }
        }
        else
        {
          v25 = 461;
        }
      }
      else
      {
        v25 = 449;
      }
    }
    else
    {
      v25 = 437;
    }
    DebugTraceError((unsigned int)v24, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\ssl3key.c", v25);
    goto LABEL_44;
  }
  v22 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
  p_phHash = v22;
  if ( v22 )
  {
    *(_DWORD *)v22 = 1885431112;
    p_phHash = v22 + 8;
    goto LABEL_16;
  }
LABEL_17:
  v23 = -2146893810;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\ssl3key.c",
      (unsigned int)"Status",
      14,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\ssl3key.c",
      163);
LABEL_44:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( p_phHash && *((_DWORD *)p_phHash - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return v23;
}

```

## disassembly

```asm
0x18000da9c  push    rbp
0x18000da9e  push    rsi
0x18000da9f  push    rdi
0x18000daa0  push    r12
0x18000daa2  push    r13
0x18000daa4  push    r14
0x18000daa6  push    r15
0x18000daa8  sub     rsp, 0C0h
0x18000daaf  lea     rbp, [rsp+40h]
0x18000dab4  mov     [rbp+0B0h+arg_10], rbx
0x18000dabb  mov     rax, cs:__security_cookie
0x18000dac2  xor     rax, rbp
0x18000dac5  mov     [rbp+0B0h+var_40], rax
0x18000dac9  mov     rax, [rbp+0B0h+arg_20]
0x18000dad0  mov     r12, rcx
0x18000dad3  mov     ecx, 28h ; '('
0x18000dad8  mov     [rbp+0B0h+var_98], rax
0x18000dadc  mov     rax, [rbp+0B0h+arg_30]
0x18000dae3  mov     rsi, rdx
0x18000dae6  mov     [rbp+0B0h+var_90], rax
0x18000daea  mov     rax, [rdx+10h]
0x18000daee  mov     edx, 8003h
0x18000daf3  lea     r14d, [rcx+8]
0x18000daf7  mov     [rbp+0B0h+phHash], 0
0x18000daff  mov     [rbp+0B0h+var_A0], r9
0x18000db03  mov     [rbp+0B0h+var_A8], r8d
0x18000db07  cmp     [rax+40h], edx
0x18000db0a  cmovnz  r14d, ecx
0x18000db0e  mov     ecx, 150h
0x18000db13  mov     [rbp+0B0h+var_A4], r14d
0x18000db17  lea     r15d, [rcx-20h]
0x18000db1b  cmovnz  r15d, ecx
0x18000db1f  xor     edi, edi
0x18000db21  mov     ebx, [r15+r12+10h]
0x18000db26  test    rbx, rbx
0x18000db29  jz      short loc_18000DB90
0x18000db2b  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18000db32  ja      short loc_18000DB90
0x18000db34  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000db3b  add     rcx, 8
0x18000db3f  add     rcx, rbx
0x18000db42  cmp     rcx, rbx
0x18000db45  jb      short loc_18000DB90
0x18000db47  call    VerifyStackAvailable
0x18000db4c  test    eax, eax
0x18000db4e  jz      short loc_18000DB90
0x18000db50  lea     rax, [rbx+8]
0x18000db54  lea     rcx, [rax+0Fh]
0x18000db58  cmp     rcx, rax
0x18000db5b  ja      short loc_18000DB67
0x18000db5d  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18000db67  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18000db6b  mov     rax, rcx
0x18000db6e  call    _alloca_probe
0x18000db73  sub     rsp, rcx
0x18000db76  lea     rdi, [rsp+0F0h+phHash]
0x18000db7b  test    rdi, rdi
0x18000db7e  jz      short loc_18000DB90
0x18000db80  mov     dword ptr [rdi], 6B637453h
0x18000db86  add     rdi, 8
0x18000db8a  jnz     loc_18000DC13
0x18000db90  lea     rcx, [rbx+8]
0x18000db94  cmp     rcx, rbx
0x18000db97  jb      short loc_18000DBB7
0x18000db99  mov     rax, cs:g_pfnAllocate
0x18000dba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dba5  mov     rdi, rax
0x18000dba8  test    rax, rax
0x18000dbab  jz      short loc_18000DBBC
0x18000dbad  mov     dword ptr [rax], 70616548h
0x18000dbb3  add     rdi, 8
0x18000dbb7  test    rdi, rdi
0x18000dbba  jnz     short loc_18000DC13
0x18000dbbc  mov     ebx, 8009000Eh
0x18000dbc1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbc8  lea     rax, WPP_GLOBAL_Control
0x18000dbcf  cmp     rcx, rax
0x18000dbd2  jz      loc_18000DE43
0x18000dbd8  test    byte ptr [rcx+1Ch], 1
0x18000dbdc  jz      loc_18000DE43
0x18000dbe2  mov     rcx, [rcx+10h]
0x18000dbe6  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dbed  mov     [rsp+0F0h+dwFlags], 1A3h
0x18000dbf5  lea     r9, aStatus; "Status"
0x18000dbfc  mov     qword ptr [rsp+0F0h+cbSecret], r8
0x18000dc01  mov     dword ptr [rsp+0F0h+pbSecret], 8009000Eh
0x18000dc09  call    WPP_SF_sDsd
0x18000dc0e  jmp     loc_18000DE43
0x18000dc13  mov     r9d, [r15+r12+10h]; cbHashObject
0x18000dc18  lea     rdx, [rbp+0B0h+phHash]; phHash
0x18000dc1c  mov     rcx, [r15+r12]; hAlgorithm
0x18000dc20  mov     r8, rdi; pbHashObject
0x18000dc23  mov     [rsp+0F0h+dwFlags], 0; dwFlags
0x18000dc2b  mov     [rsp+0F0h+cbSecret], 0; cbSecret
0x18000dc33  mov     [rsp+0F0h+pbSecret], 0; pbSecret
0x18000dc3c  call    cs:__imp_BCryptCreateHash
0x18000dc42  mov     ebx, eax
0x18000dc44  test    eax, eax
0x18000dc46  jns     short loc_18000DC68
0x18000dc48  mov     r9d, 1B5h
0x18000dc4e  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dc55  mov     ecx, eax
0x18000dc57  lea     rdx, aStatus; "Status"
0x18000dc5e  call    DebugTraceError
0x18000dc63  jmp     loc_18000DE43
0x18000dc68  mov     r8d, [rsi+68h]; cbInput
0x18000dc6c  lea     rdx, [rsi+38h]; pbInput
0x18000dc70  mov     rcx, [rbp+0B0h+phHash]; hHash
0x18000dc74  xor     r9d, r9d; dwFlags
0x18000dc77  call    cs:__imp_BCryptHashData
0x18000dc7d  mov     ebx, eax
0x18000dc7f  test    eax, eax
0x18000dc81  jns     short loc_18000DC8B
0x18000dc83  mov     r9d, 1C1h
0x18000dc89  jmp     short loc_18000DC4E
0x18000dc8b  mov     rcx, [rbp+0B0h+phHash]; hHash
0x18000dc8f  lea     rdx, g_rgbPad1; "666666666666666666666666666666666666666"...
0x18000dc96  xor     r9d, r9d; dwFlags
0x18000dc99  mov     r8d, r14d; cbInput
0x18000dc9c  call    cs:__imp_BCryptHashData
0x18000dca2  mov     ebx, eax
0x18000dca4  test    eax, eax
0x18000dca6  jns     short loc_18000DCB0
0x18000dca8  mov     r9d, 1CDh
0x18000dcae  jmp     short loc_18000DC4E
0x18000dcb0  mov     r14d, [rbp+0B0h+cbInput]
0x18000dcb7  lea     rdx, [rbp+0B0h+pbInput]; pbInput
0x18000dcbb  mov     rax, [rbp+0B0h+var_A0]
0x18000dcbf  xor     r9d, r9d; dwFlags
0x18000dcc2  mov     rcx, [rbp+0B0h+phHash]; hHash
0x18000dcc6  bswap   rax
0x18000dcc9  mov     qword ptr [rbp+0B0h+pbInput], rax
0x18000dccd  mov     eax, [rbp+0B0h+var_A8]
0x18000dcd0  lea     r8d, [r9+0Bh]; cbInput
0x18000dcd4  mov     [rbp+0B0h+var_78], al
0x18000dcd7  mov     eax, r14d
0x18000dcda  shr     eax, 8
0x18000dcdd  mov     [rbp+0B0h+var_77], al
0x18000dce0  mov     [rbp+0B0h+var_76], r14b
0x18000dce4  call    cs:__imp_BCryptHashData
0x18000dcea  mov     ebx, eax
0x18000dcec  test    eax, eax
0x18000dcee  jns     short loc_18000DCFB
0x18000dcf0  mov     r9d, 1EAh
0x18000dcf6  jmp     loc_18000DC4E
0x18000dcfb  mov     rdx, [rbp+0B0h+var_98]; pbInput
0x18000dcff  xor     r9d, r9d; dwFlags
0x18000dd02  mov     rcx, [rbp+0B0h+phHash]; hHash
0x18000dd06  mov     r8d, r14d; cbInput
0x18000dd09  call    cs:__imp_BCryptHashData
0x18000dd0f  xor     r14d, r14d
0x18000dd12  mov     ebx, eax
0x18000dd14  test    eax, eax
0x18000dd16  jns     short loc_18000DD23
0x18000dd18  mov     r9d, 1F6h
0x18000dd1e  jmp     loc_18000DC4E
0x18000dd23  mov     r8, [rsi+10h]
0x18000dd27  lea     rdx, [rbp+0B0h+pbOutput]; pbOutput
0x18000dd2b  mov     rcx, [rbp+0B0h+phHash]; hHash
0x18000dd2f  xor     r9d, r9d; dwFlags
0x18000dd32  mov     r8d, [r8+44h]; cbOutput
0x18000dd36  call    cs:__imp_BCryptFinishHash
0x18000dd3c  mov     ebx, eax
0x18000dd3e  test    eax, eax
0x18000dd40  jns     short loc_18000DD4D
0x18000dd42  mov     r9d, 202h
0x18000dd48  jmp     loc_18000DC4E
0x18000dd4d  mov     rcx, [rbp+0B0h+phHash]; hHash
0x18000dd51  call    cs:__imp_BCryptDestroyHash
0x18000dd57  mov     r9d, [r15+r12+10h]; cbHashObject
0x18000dd5c  lea     rdx, [rbp+0B0h+phHash]; phHash
0x18000dd60  mov     rcx, [r15+r12]; hAlgorithm
0x18000dd64  mov     r8, rdi; pbHashObject
0x18000dd67  mov     [rsp+0F0h+dwFlags], r14d; dwFlags
0x18000dd6c  mov     [rsp+0F0h+cbSecret], r14d; cbSecret
0x18000dd71  mov     [rsp+0F0h+pbSecret], r14; pbSecret
0x18000dd76  mov     [rbp+0B0h+phHash], r14
0x18000dd7a  call    cs:__imp_BCryptCreateHash
0x18000dd80  mov     ebx, eax
0x18000dd82  test    eax, eax
0x18000dd84  jns     short loc_18000DD91
0x18000dd86  mov     r9d, 217h
0x18000dd8c  jmp     loc_18000DC4E
0x18000dd91  mov     r8d, [rsi+68h]; cbInput
0x18000dd95  lea     rdx, [rsi+38h]; pbInput
0x18000dd99  mov     rcx, [rbp+0B0h+phHash]; hHash
0x18000dd9d  xor     r9d, r9d; dwFlags
0x18000dda0  call    cs:__imp_BCryptHashData
0x18000dda6  mov     ebx, eax
0x18000dda8  test    eax, eax
0x18000ddaa  jns     short loc_18000DDB7
0x18000ddac  mov     r9d, 223h
0x18000ddb2  jmp     loc_18000DC4E
0x18000ddb7  mov     r8d, [rbp+0B0h+var_A4]; cbInput
0x18000ddbb  lea     rdx, g_rgbPad2; pbInput
0x18000ddc2  mov     rcx, [rbp+0B0h+phHash]; hHash
0x18000ddc6  xor     r9d, r9d; dwFlags
0x18000ddc9  call    cs:__imp_BCryptHashData
0x18000ddcf  mov     ebx, eax
0x18000ddd1  test    eax, eax
0x18000ddd3  jns     short loc_18000DDE0
0x18000ddd5  mov     r9d, 22Fh
0x18000dddb  jmp     loc_18000DC4E
0x18000dde0  mov     r8, [rsi+10h]
0x18000dde4  lea     rdx, [rbp+0B0h+pbOutput]; pbInput
0x18000dde8  mov     rcx, [rbp+0B0h+phHash]; hHash
0x18000ddec  xor     r9d, r9d; dwFlags
0x18000ddef  mov     r8d, [r8+44h]; cbInput
0x18000ddf3  call    cs:__imp_BCryptHashData
0x18000ddf9  mov     ebx, eax
0x18000ddfb  test    eax, eax
0x18000ddfd  jns     short loc_18000DE0A
0x18000ddff  mov     r9d, 23Ah
0x18000de05  jmp     loc_18000DC4E
0x18000de0a  mov     r8d, [rbp+0B0h+cbOutput]; cbOutput
0x18000de11  xor     r9d, r9d; dwFlags
0x18000de14  mov     rdx, [rbp+0B0h+var_90]; pbOutput
0x18000de18  mov     rcx, [rbp+0B0h+phHash]; hHash
0x18000de1c  call    cs:__imp_BCryptFinishHash
0x18000de22  mov     ebx, eax
0x18000de24  test    eax, eax
0x18000de26  jns     short loc_18000DE33
0x18000de28  mov     r9d, 246h
0x18000de2e  jmp     loc_18000DC4E
0x18000de33  mov     rcx, [rbp+0B0h+phHash]; hHash
0x18000de37  call    cs:__imp_BCryptDestroyHash
0x18000de3d  xor     ebx, ebx
0x18000de3f  mov     [rbp+0B0h+phHash], r14
0x18000de43  mov     rcx, [rbp+0B0h+phHash]; hHash
0x18000de47  test    rcx, rcx
0x18000de4a  jz      short loc_18000DE52
0x18000de4c  call    cs:__imp_BCryptDestroyHash
0x18000de52  test    rdi, rdi
0x18000de55  jz      short loc_18000DE6F
0x18000de57  lea     rcx, [rdi-8]
0x18000de5b  cmp     dword ptr [rcx], 70616548h
0x18000de61  jnz     short loc_18000DE6F
0x18000de63  mov     rax, cs:g_pfnFree
0x18000de6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de6f  mov     eax, ebx
0x18000de71  mov     rcx, [rbp+0B0h+var_40]
0x18000de75  xor     rcx, rbp; StackCookie
0x18000de78  call    __security_check_cookie
0x18000de7d  mov     rbx, [rbp+0B0h+arg_10]
0x18000de84  lea     rsp, [rbp+80h]
0x18000de8b  pop     r15
0x18000de8d  pop     r14
0x18000de8f  pop     r13
0x18000de91  pop     r12
0x18000de93  pop     rdi
0x18000de94  pop     rsi
0x18000de95  pop     rbp
0x18000de96  retn
```
