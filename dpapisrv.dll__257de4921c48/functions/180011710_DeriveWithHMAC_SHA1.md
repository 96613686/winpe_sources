# DeriveWithHMAC_SHA1

- ea: `0x180011710`
- end: `0x180011962`
- name: `DeriveWithHMAC_SHA1`
- size: `594`
- prototype: `__int64 __fastcall(void *Src, size_t Size, PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180004e60`
- `0x180012838`
- `0x18001866c`
- `0x1800285dc`
- `0x18002955c`
- `0x18002ad50`

## callees

- `0x1800029d0`
- `0x180011710`
- `0x18001d810`
- `0x18001e1b4`
- `0x18003c62c`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x180011868`
- `bcrypt!BCryptFinishHash` at `0x180011903`
- `bcrypt!BCryptFinishHash` at `0x180011868`
- `bcrypt!BCryptFinishHash` at `0x180011903`
- `bcrypt!BCryptDestroyHash` at `0x180011879`
- `bcrypt!BCryptDestroyHash` at `0x180011914`
- `bcrypt!BCryptDestroyHash` at `0x180011879`
- `bcrypt!BCryptDestroyHash` at `0x180011914`
- `bcrypt!BCryptHashData` at `0x180011830`
- `bcrypt!BCryptHashData` at `0x18001184a`
- `bcrypt!BCryptHashData` at `0x1800118cf`
- `bcrypt!BCryptHashData` at `0x1800118e9`
- `bcrypt!BCryptHashData` at `0x180011830`
- `bcrypt!BCryptHashData` at `0x18001184a`
- `bcrypt!BCryptHashData` at `0x1800118cf`
- `bcrypt!BCryptHashData` at `0x1800118e9`
- `bcrypt!BCryptCreateHash` at `0x18001180d`
- `bcrypt!BCryptCreateHash` at `0x1800118ac`
- `bcrypt!BCryptCreateHash` at `0x18001180d`
- `bcrypt!BCryptCreateHash` at `0x1800118ac`

## pseudocode

```c
int __fastcall DeriveWithHMAC_SHA1(void *Src, size_t Size, PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)
{
  unsigned int v6; // ebx
  __int64 v8; // rsi
  unsigned int v10; // eax
  unsigned int v11; // ebx
  __int64 i; // rax
  __m128 v13; // xmm0
  UCHAR *BCryptProviderHandle; // rax
  UCHAR *v15; // rbx
  __int64 v16; // rcx
  UCHAR *v17; // rax
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+40h] [rbp-81h] BYREF
  UCHAR pbInputa[64]; // [rsp+50h] [rbp-71h] BYREF
  UCHAR v21[64]; // [rsp+90h] [rbp-31h] BYREF

  v6 = Size;
  phHash[0] = 0;
  v8 = 64;
  memset_0(pbInputa, 0, sizeof(pbInputa));
  memset_0(v21, 0, sizeof(v21));
  v10 = 64;
  if ( v6 <= 0x40 )
    v10 = v6;
  v11 = v10;
  memcpy_0(pbInputa, Src, v10);
  memcpy_0(v21, Src, v11);
  for ( i = 0; i != 8; i += 2 )
  {
    v13 = (__m128)_mm_loadu_si128((const __m128i *)&v21[8 * i]);
    *(__m128 *)&pbInputa[8 * i] = _mm_xor_ps(
                                    (__m128)_mm_load_si128((const __m128i *)&_xmm),
                                    (__m128)_mm_loadu_si128((const __m128i *)&pbInputa[8 * i]));
    *(__m128 *)&v21[8 * i] = _mm_xor_ps(v13, (__m128)_xmm);
  }
  BCryptProviderHandle = (UCHAR *)GetBCryptProviderHandle(0x8004u);
  v15 = BCryptProviderHandle;
  if ( BCryptProviderHandle )
  {
    LODWORD(BCryptProviderHandle) = BCryptCreateHash(BCryptProviderHandle, phHash, 0, 0, 0, 0, 0);
    if ( (int)BCryptProviderHandle >= 0 )
    {
      BCryptHashData(phHash[0], pbInputa, 0x40u, 0);
      BCryptHashData(phHash[0], pbInput, cbInput, 0);
      BCryptFinishHash(phHash[0], pbOutput, 0x14u, 0);
      BCryptDestroyHash(phHash[0]);
      LODWORD(BCryptProviderHandle) = BCryptCreateHash(v15, phHash, 0, 0, 0, 0, 0);
      if ( (int)BCryptProviderHandle >= 0 )
      {
        BCryptHashData(phHash[0], v21, 0x40u, 0);
        BCryptHashData(phHash[0], pbOutput, 0x14u, 0);
        BCryptFinishHash(phHash[0], pbOutput, 0x14u, 0);
        BCryptDestroyHash(phHash[0]);
        v16 = 64;
        v17 = pbInputa;
        do
        {
          *v17++ = 0;
          --v16;
        }
        while ( v16 );
        BCryptProviderHandle = v21;
        do
        {
          *BCryptProviderHandle++ = 0;
          --v8;
        }
        while ( v8 );
      }
    }
  }
  return (int)BCryptProviderHandle;
}

```

## disassembly

```asm
0x180011710  push    rbp
0x180011712  push    rbx
0x180011713  push    rsi
0x180011714  push    rdi
0x180011715  push    r12
0x180011717  push    r14
0x180011719  push    r15
0x18001171b  lea     rbp, [rsp-1Fh]
0x180011720  sub     rsp, 0E0h
0x180011727  mov     rax, cs:__security_cookie
0x18001172e  xor     rax, rsp
0x180011731  mov     [rbp+4Fh+var_40], rax
0x180011735  mov     r14, [rbp+4Fh+pbOutput]
0x180011739  mov     r15, r8
0x18001173c  mov     ebx, edx
0x18001173e  mov     [rsp+110h+phHash], 0
0x180011747  mov     rdi, rcx
0x18001174a  mov     esi, 40h ; '@'
0x18001174f  mov     r8d, esi; Size
0x180011752  lea     rcx, [rbp+4Fh+pbInput]; void *
0x180011756  xor     edx, edx; Val
0x180011758  mov     r12d, r9d
0x18001175b  call    memset_0
0x180011760  mov     r8d, esi; Size
0x180011763  lea     rcx, [rbp+4Fh+var_80]; void *
0x180011767  xor     edx, edx; Val
0x180011769  call    memset_0
0x18001176e  cmp     ebx, esi
0x180011770  lea     rcx, [rbp+4Fh+pbInput]; void *
0x180011774  mov     eax, esi
0x180011776  mov     rdx, rdi; Src
0x180011779  cmovbe  eax, ebx
0x18001177c  mov     r8d, eax; Size
0x18001177f  mov     ebx, eax
0x180011781  call    memcpy_0
0x180011786  mov     r8d, ebx; Size
0x180011789  lea     rcx, [rbp+4Fh+var_80]; void *
0x18001178d  mov     rdx, rdi; Src
0x180011790  call    memcpy_0
0x180011795  xor     eax, eax
0x180011797  movdqu  xmm0, xmmword ptr [rbp+rax*8+4Fh+pbInput]
0x18001179d  movdqa  xmm1, cs:__xmm@36363636363636363636363636363636
0x1800117a5  xorps   xmm1, xmm0
0x1800117a8  movdqu  xmm0, xmmword ptr [rbp+rax*8+4Fh+var_80]
0x1800117ae  movdqu  xmmword ptr [rbp+rax*8+4Fh+pbInput], xmm1
0x1800117b4  xorps   xmm0, cs:__xmm@5c5c5c5c5c5c5c5c5c5c5c5c5c5c5c5c
0x1800117bb  movdqu  xmmword ptr [rbp+rax*8+4Fh+var_80], xmm0
0x1800117c1  add     rax, 2
0x1800117c5  cmp     rax, 8
0x1800117c9  jnz     short loc_180011797
0x1800117cb  xor     r8d, r8d
0x1800117ce  xor     edx, edx
0x1800117d0  mov     ecx, 8004h; unsigned int
0x1800117d5  call    GetBCryptProviderHandle
0x1800117da  mov     rbx, rax
0x1800117dd  test    rax, rax
0x1800117e0  jz      loc_180011943
0x1800117e6  mov     [rsp+110h+dwFlags], 0; dwFlags
0x1800117ee  lea     rdx, [rsp+110h+phHash]; phHash
0x1800117f3  mov     [rsp+110h+cbSecret], 0; cbSecret
0x1800117fb  xor     r9d, r9d; cbHashObject
0x1800117fe  xor     r8d, r8d; pbHashObject
0x180011801  mov     [rsp+110h+pbSecret], 0; pbSecret
0x18001180a  mov     rcx, rax; hAlgorithm
0x18001180d  call    cs:__imp_BCryptCreateHash
0x180011814  nop     dword ptr [rax+rax+00h]
0x180011819  test    eax, eax
0x18001181b  js      loc_180011943
0x180011821  mov     rcx, [rsp+110h+phHash]; hHash
0x180011826  lea     rdx, [rbp+4Fh+pbInput]; pbInput
0x18001182a  xor     r9d, r9d; dwFlags
0x18001182d  mov     r8d, esi; cbInput
0x180011830  call    cs:__imp_BCryptHashData
0x180011837  nop     dword ptr [rax+rax+00h]
0x18001183c  mov     rcx, [rsp+110h+phHash]; hHash
0x180011841  xor     r9d, r9d; dwFlags
0x180011844  mov     r8d, r12d; cbInput
0x180011847  mov     rdx, r15; pbInput
0x18001184a  call    cs:__imp_BCryptHashData
0x180011851  nop     dword ptr [rax+rax+00h]
0x180011856  mov     rcx, [rsp+110h+phHash]; hHash
0x18001185b  xor     r9d, r9d; dwFlags
0x18001185e  mov     rdx, r14; pbOutput
0x180011861  lea     edi, [r9+14h]
0x180011865  mov     r8d, edi; cbOutput
0x180011868  call    cs:__imp_BCryptFinishHash
0x18001186f  nop     dword ptr [rax+rax+00h]
0x180011874  mov     rcx, [rsp+110h+phHash]; hHash
0x180011879  call    cs:__imp_BCryptDestroyHash
0x180011880  nop     dword ptr [rax+rax+00h]
0x180011885  mov     [rsp+110h+dwFlags], 0; dwFlags
0x18001188d  lea     rdx, [rsp+110h+phHash]; phHash
0x180011892  mov     [rsp+110h+cbSecret], 0; cbSecret
0x18001189a  xor     r9d, r9d; cbHashObject
0x18001189d  xor     r8d, r8d; pbHashObject
0x1800118a0  mov     [rsp+110h+pbSecret], 0; pbSecret
0x1800118a9  mov     rcx, rbx; hAlgorithm
0x1800118ac  call    cs:__imp_BCryptCreateHash
0x1800118b3  nop     dword ptr [rax+rax+00h]
0x1800118b8  test    eax, eax
0x1800118ba  js      loc_180011943
0x1800118c0  mov     rcx, [rsp+110h+phHash]; hHash
0x1800118c5  lea     rdx, [rbp+4Fh+var_80]; pbInput
0x1800118c9  xor     r9d, r9d; dwFlags
0x1800118cc  mov     r8d, esi; cbInput
0x1800118cf  call    cs:__imp_BCryptHashData
0x1800118d6  nop     dword ptr [rax+rax+00h]
0x1800118db  mov     rcx, [rsp+110h+phHash]; hHash
0x1800118e0  xor     r9d, r9d; dwFlags
0x1800118e3  mov     r8d, edi; cbInput
0x1800118e6  mov     rdx, r14; pbInput
0x1800118e9  call    cs:__imp_BCryptHashData
0x1800118f0  nop     dword ptr [rax+rax+00h]
0x1800118f5  mov     rcx, [rsp+110h+phHash]; hHash
0x1800118fa  xor     r9d, r9d; dwFlags
0x1800118fd  mov     r8d, edi; cbOutput
0x180011900  mov     rdx, r14; pbOutput
0x180011903  call    cs:__imp_BCryptFinishHash
0x18001190a  nop     dword ptr [rax+rax+00h]
0x18001190f  mov     rcx, [rsp+110h+phHash]; hHash
0x180011914  call    cs:__imp_BCryptDestroyHash
0x18001191b  nop     dword ptr [rax+rax+00h]
0x180011920  mov     rcx, rsi
0x180011923  lea     rax, [rbp+4Fh+pbInput]
0x180011927  mov     byte ptr [rax], 0
0x18001192a  inc     rax
0x18001192d  sub     rcx, 1
0x180011931  jnz     short loc_180011927
0x180011933  lea     rax, [rbp+4Fh+var_80]
0x180011937  mov     byte ptr [rax], 0
0x18001193a  inc     rax
0x18001193d  sub     rsi, 1
0x180011941  jnz     short loc_180011937
0x180011943  mov     rcx, [rbp+4Fh+var_40]
0x180011947  xor     rcx, rsp; StackCookie
0x18001194a  call    __security_check_cookie
0x18001194f  add     rsp, 0E0h
0x180011956  pop     r15
0x180011958  pop     r14
0x18001195a  pop     r12
0x18001195c  pop     rdi
0x18001195d  pop     rsi
0x18001195e  pop     rbx
0x18001195f  pop     rbp
0x180011960  retn
```
