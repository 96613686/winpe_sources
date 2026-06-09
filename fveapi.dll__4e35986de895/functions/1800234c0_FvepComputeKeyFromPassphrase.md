# FvepComputeKeyFromPassphrase

- ea: `0x1800234c0`
- end: `0x18002371a`
- name: `FvepComputeKeyFromPassphrase`
- size: `602`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180048fbc`

## callees

- `0x1800234c0`
- `0x18011d480`
- `0x18011f010`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x180023655`
- `bcrypt!BCryptDestroyHash` at `0x1800236f3`
- `bcrypt!BCryptDestroyHash` at `0x180023655`
- `bcrypt!BCryptDestroyHash` at `0x1800236f3`
- `bcrypt!BCryptCreateHash` at `0x180023558`
- `bcrypt!BCryptCreateHash` at `0x1800235bb`
- `bcrypt!BCryptCreateHash` at `0x180023558`
- `bcrypt!BCryptCreateHash` at `0x1800235bb`
- `bcrypt!BCryptHashData` at `0x1800235e3`
- `bcrypt!BCryptHashData` at `0x1800236ab`
- `bcrypt!BCryptHashData` at `0x1800235e3`
- `bcrypt!BCryptHashData` at `0x1800236ab`
- `bcrypt!BCryptFinishHash` at `0x180023606`
- `bcrypt!BCryptFinishHash` at `0x1800236ce`
- `bcrypt!BCryptFinishHash` at `0x180023606`
- `bcrypt!BCryptFinishHash` at `0x1800236ce`

## pseudocode

```c
__int64 __fastcall FvepComputeKeyFromPassphrase(PUCHAR pbInput, unsigned __int64 cbInput, __int128 *a3, _OWORD *a4)
{
  __int128 v7; // xmm0
  NTSTATUS v8; // ebx
  __int64 v9; // rsi
  __int64 v10; // rdi
  int i; // ecx
  UCHAR *v13; // rax
  __int128 v15; // xmm1
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-61h] BYREF
  char v17; // [rsp+50h] [rbp-59h]
  int v18; // [rsp+51h] [rbp-58h]
  __int16 v19; // [rsp+55h] [rbp-54h]
  char v20; // [rsp+57h] [rbp-52h]
  BCRYPT_HASH_HANDLE hHash; // [rsp+58h] [rbp-51h] BYREF
  UCHAR pbInputa[16]; // [rsp+60h] [rbp-49h] BYREF
  __int128 v23; // [rsp+70h] [rbp-39h]
  UCHAR pbOutput[16]; // [rsp+80h] [rbp-29h] BYREF
  __int128 v25; // [rsp+90h] [rbp-19h]
  __int128 v26; // [rsp+A0h] [rbp-9h]
  _QWORD v27[2]; // [rsp+B0h] [rbp+7h]

  *(_OWORD *)pbInputa = 0;
  v23 = 0;
  *(_OWORD *)pbOutput = 0;
  phHash = 0;
  v25 = 0;
  v17 = 0;
  v7 = *a3;
  v18 = 0;
  v19 = 0;
  v26 = v7;
  v20 = 0;
  v27[0] = 0;
  v8 = FveSha256Initialize();
  v9 = 88;
  if ( v8 < 0 )
    goto LABEL_19;
  v8 = BCryptCreateHash(hAlgorithm, &phHash, 0, 0, 0, 0, 0);
  if ( v8 < 0 )
    goto LABEL_19;
  v17 = 1;
  if ( cbInput <= 0xFFFF )
  {
    if ( pbInput )
    {
      v8 = BCryptHashData(phHash, pbInput, cbInput, 0);
      if ( v8 >= 0 )
      {
        v8 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
        if ( v8 >= 0 )
        {
          v10 = 0x100000;
          hHash = 0;
          v8 = BCryptCreateHash(hAlgorithm, &hHash, 0, 0, 0, 0, 0);
          if ( v8 >= 0 )
          {
LABEL_7:
            if ( v10 )
            {
              v8 = BCryptHashData(hHash, pbInputa, 0x58u, 0);
              if ( v8 >= 0 )
              {
                v8 = BCryptFinishHash(hHash, pbInputa, 0x20u, 0);
                if ( v8 >= 0 )
                {
                  for ( i = 0; i < 8; ++i )
                  {
                    if ( (*((_BYTE *)v27 + i))++ != 0xFF )
                    {
                      --v10;
                      goto LABEL_7;
                    }
                  }
                  v8 = -1073741811;
                }
              }
            }
          }
          if ( hHash )
            BCryptDestroyHash(hHash);
          if ( v8 >= 0 )
          {
            v15 = v23;
            *a4 = *(_OWORD *)pbInputa;
            a4[1] = v15;
          }
        }
      }
    }
    else
    {
      v8 = -1073741811;
    }
LABEL_19:
    if ( !v17 )
      goto LABEL_22;
    goto LABEL_20;
  }
  v8 = -1073741811;
LABEL_20:
  if ( BCryptDestroyHash(phHash) >= 0 )
    v17 = 0;
LABEL_22:
  v13 = pbInputa;
  do
  {
    *v13++ = 0;
    --v9;
  }
  while ( v9 );
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800234c0  push    rbp
0x1800234c2  push    rbx
0x1800234c3  push    rsi
0x1800234c4  push    rdi
0x1800234c5  push    r12
0x1800234c7  push    r14
0x1800234c9  push    r15
0x1800234cb  lea     rbp, [rsp-27h]
0x1800234d0  sub     rsp, 0D0h
0x1800234d7  mov     rax, cs:__security_cookie
0x1800234de  xor     rax, rsp
0x1800234e1  mov     [rbp+57h+var_40], rax
0x1800234e5  xorps   xmm0, xmm0
0x1800234e8  xor     eax, eax
0x1800234ea  movups  xmmword ptr [rbp+57h+pbInput], xmm0
0x1800234ee  xor     r12d, r12d
0x1800234f1  mov     r15, r9
0x1800234f4  movups  [rbp+57h+var_90], xmm0
0x1800234f8  mov     r14, rdx
0x1800234fb  mov     rdi, rcx
0x1800234fe  movups  xmmword ptr [rbp+57h+pbOutput], xmm0
0x180023502  mov     [rbp+57h+phHash], r12
0x180023506  movups  [rbp+57h+var_70], xmm0
0x18002350a  mov     [rbp+57h+var_B0], r12b
0x18002350e  movups  xmm0, xmmword ptr [r8]
0x180023512  mov     [rbp+57h+var_AF], eax
0x180023515  mov     [rbp+57h+var_AB], ax
0x180023519  movaps  [rbp+57h+var_60], xmm0
0x18002351d  mov     [rbp+57h+var_A9], al
0x180023520  mov     [rbp+57h+var_50], rax
0x180023524  call    FveSha256Initialize
0x180023529  mov     ebx, eax
0x18002352b  mov     esi, 58h ; 'X'
0x180023530  test    eax, eax
0x180023532  js      loc_18002364B
0x180023538  mov     rcx, cs:hAlgorithm; hAlgorithm
0x18002353f  lea     rdx, [rbp+57h+phHash]; phHash
0x180023543  mov     [rsp+100h+dwFlags], r12d; dwFlags
0x180023548  xor     r9d, r9d; cbHashObject
0x18002354b  mov     [rsp+100h+cbSecret], r12d; cbSecret
0x180023550  xor     r8d, r8d; pbHashObject
0x180023553  mov     [rsp+100h+pbSecret], r12; pbSecret
0x180023558  call    cs:__imp_BCryptCreateHash
0x18002355f  nop     dword ptr [rax+rax+00h]
0x180023564  mov     ebx, eax
0x180023566  test    eax, eax
0x180023568  js      loc_18002364B
0x18002356e  mov     [rbp+57h+var_B0], 1
0x180023572  cmp     r14, 0FFFFh
0x180023579  ja      loc_1800236E9
0x18002357f  test    rdi, rdi
0x180023582  jnz     loc_18002369E
0x180023588  mov     ebx, 0C000000Dh
0x18002358d  jmp     loc_18002364B
0x180023592  mov     rcx, cs:hAlgorithm; hAlgorithm
0x180023599  lea     rdx, [rbp+57h+hHash]; phHash
0x18002359d  mov     [rsp+100h+dwFlags], r12d; dwFlags
0x1800235a2  xor     r9d, r9d; cbHashObject
0x1800235a5  mov     [rsp+100h+cbSecret], r12d; cbSecret
0x1800235aa  xor     r8d, r8d; pbHashObject
0x1800235ad  mov     [rsp+100h+pbSecret], r12; pbSecret
0x1800235b2  mov     edi, 100000h
0x1800235b7  mov     [rbp+57h+hHash], r12
0x1800235bb  call    cs:__imp_BCryptCreateHash
0x1800235c2  nop     dword ptr [rax+rax+00h]
0x1800235c7  mov     ebx, eax
0x1800235c9  test    eax, eax
0x1800235cb  js      short loc_180023636
0x1800235cd  nop     dword ptr [rax]
0x1800235d0  test    rdi, rdi
0x1800235d3  jz      short loc_180023636
0x1800235d5  mov     rcx, [rbp+57h+hHash]; hHash
0x1800235d9  lea     rdx, [rbp+57h+pbInput]; pbInput
0x1800235dd  xor     r9d, r9d; dwFlags
0x1800235e0  mov     r8d, esi; cbInput
0x1800235e3  call    cs:__imp_BCryptHashData
0x1800235ea  nop     dword ptr [rax+rax+00h]
0x1800235ef  mov     ebx, eax
0x1800235f1  test    eax, eax
0x1800235f3  js      short loc_180023636
0x1800235f5  mov     rcx, [rbp+57h+hHash]; hHash
0x1800235f9  lea     rdx, [rbp+57h+pbInput]; pbOutput
0x1800235fd  xor     r9d, r9d; dwFlags
0x180023600  mov     r8d, 20h ; ' '; cbOutput
0x180023606  call    cs:__imp_BCryptFinishHash
0x18002360d  nop     dword ptr [rax+rax+00h]
0x180023612  mov     ebx, eax
0x180023614  test    eax, eax
0x180023616  js      short loc_180023636
0x180023618  mov     ecx, r12d
0x18002361b  movsxd  rax, ecx
0x18002361e  add     byte ptr [rbp+rax+57h+var_50], 1
0x180023623  jz      short loc_18002362A
0x180023625  dec     rdi
0x180023628  jmp     short loc_1800235D0
0x18002362a  inc     ecx
0x18002362c  cmp     ecx, 8
0x18002362f  jl      short loc_18002361B
0x180023631  mov     ebx, 0C000000Dh
0x180023636  mov     rcx, [rbp+57h+hHash]; hHash
0x18002363a  test    rcx, rcx
0x18002363d  jnz     loc_1800236F3
0x180023643  test    ebx, ebx
0x180023645  jns     loc_180023704
0x18002364b  cmp     [rbp+57h+var_B0], r12b
0x18002364f  jz      short loc_180023669
0x180023651  mov     rcx, [rbp+57h+phHash]; hHash
0x180023655  call    cs:__imp_BCryptDestroyHash
0x18002365c  nop     dword ptr [rax+rax+00h]
0x180023661  test    eax, eax
0x180023663  js      short loc_180023669
0x180023665  mov     [rbp+57h+var_B0], r12b
0x180023669  lea     rax, [rbp+57h+pbInput]
0x18002366d  nop     dword ptr [rax]
0x180023670  mov     [rax], r12b
0x180023673  lea     rax, [rax+1]
0x180023677  sub     rsi, 1
0x18002367b  jnz     short loc_180023670
0x18002367d  mov     eax, ebx
0x18002367f  mov     rcx, [rbp+57h+var_40]
0x180023683  xor     rcx, rsp; StackCookie
0x180023686  call    __security_check_cookie
0x18002368b  add     rsp, 0D0h
0x180023692  pop     r15
0x180023694  pop     r14
0x180023696  pop     r12
0x180023698  pop     rdi
0x180023699  pop     rsi
0x18002369a  pop     rbx
0x18002369b  pop     rbp
0x18002369c  retn
0x18002369e  mov     rcx, [rbp+57h+phHash]; hHash
0x1800236a2  mov     r8d, r14d; cbInput
0x1800236a5  xor     r9d, r9d; dwFlags
0x1800236a8  mov     rdx, rdi; pbInput
0x1800236ab  call    cs:__imp_BCryptHashData
0x1800236b2  nop     dword ptr [rax+rax+00h]
0x1800236b7  mov     ebx, eax
0x1800236b9  test    eax, eax
0x1800236bb  js      short loc_18002364B
0x1800236bd  mov     rcx, [rbp+57h+phHash]; hHash
0x1800236c1  lea     rdx, [rbp+57h+pbOutput]; pbOutput
0x1800236c5  xor     r9d, r9d; dwFlags
0x1800236c8  mov     r8d, 20h ; ' '; cbOutput
0x1800236ce  call    cs:__imp_BCryptFinishHash
0x1800236d5  nop     dword ptr [rax+rax+00h]
0x1800236da  mov     ebx, eax
0x1800236dc  test    eax, eax
0x1800236de  js      loc_18002364B
0x1800236e4  jmp     loc_180023592
0x1800236e9  mov     ebx, 0C000000Dh
0x1800236ee  jmp     loc_180023651
0x1800236f3  call    cs:__imp_BCryptDestroyHash
0x1800236fa  nop     dword ptr [rax+rax+00h]
0x1800236ff  jmp     loc_180023643
0x180023704  movaps  xmm0, xmmword ptr [rbp+57h+pbInput]
0x180023708  movaps  xmm1, [rbp+57h+var_90]
0x18002370c  movups  xmmword ptr [r15], xmm0
0x180023710  movups  xmmword ptr [r15+10h], xmm1
0x180023715  jmp     loc_18002364B
```
