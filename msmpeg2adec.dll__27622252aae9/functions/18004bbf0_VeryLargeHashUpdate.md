# VeryLargeHashUpdate

- ea: `0x18004bbf0`
- end: `0x18004bf1f`
- name: `VeryLargeHashUpdate`
- size: `815`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18004a97c`

## callees

- `0x1800017b0`
- `0x1800021a8`
- `0x18004bbf0`
- `0x180052520`
- `0x180053780`
- `0x1800537b0`

## pseudocode

```c
__int64 __fastcall VeryLargeHashUpdate(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v6; // rbx
  __int64 v7; // r14
  __int64 v8; // rbx
  __int64 v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // rdx
  _BYTE *v12; // rcx
  __int64 v13; // rdx
  _BYTE *v14; // rcx
  _BYTE v16[4]; // [rsp+20h] [rbp-B9h] BYREF
  int v17; // [rsp+24h] [rbp-B5h]
  _BYTE v18[20]; // [rsp+A0h] [rbp-39h] BYREF
  _BYTE v19[20]; // [rsp+B4h] [rbp-25h] BYREF
  _BYTE v20[20]; // [rsp+C8h] [rbp-11h] BYREF
  _BYTE v21[20]; // [rsp+DCh] [rbp+3h] BYREF

  v17 = 0;
  memset_0(v16, 0, 0x7Cu);
  if ( !a3 )
    return 0;
  if ( !a1 )
    return 0;
  v6 = a2 >> 2;
  if ( !(_DWORD)v6 )
    return 0;
  v7 = (unsigned int)v6;
  v8 = a1 + v6;
  SymCryptSha1Init(v16);
  SymCryptSha1Append(v16, a3, 20);
  SymCryptSha1Append(v16, a1, (unsigned int)v7);
  SymCryptSha1Append(v16, a3 + 20, 20);
  SymCryptSha1Append(v16, v8, (unsigned int)v7);
  SymCryptSha1Result(v16, v18);
  SymCryptSha1Init(v16);
  SymCryptSha1Append(v16, a3 + 20, 20);
  SymCryptSha1Append(v16, v8, (unsigned int)v7);
  SymCryptSha1Append(v16, a3, 20);
  SymCryptSha1Append(v16, a1, (unsigned int)v7);
  SymCryptSha1Result(v16, v19);
  v9 = v8 + v7;
  v10 = v8 + v7 + v7;
  SymCryptSha1Init(v16);
  SymCryptSha1Append(v16, a3 + 40, 20);
  SymCryptSha1Append(v16, v9, (unsigned int)v7);
  SymCryptSha1Append(v16, a3 + 60, 20);
  SymCryptSha1Append(v16, v10, (unsigned int)v7);
  SymCryptSha1Result(v16, v20);
  SymCryptSha1Init(v16);
  SymCryptSha1Append(v16, a3 + 60, 20);
  SymCryptSha1Append(v16, v10, (unsigned int)v7);
  SymCryptSha1Append(v16, a3 + 40, 20);
  SymCryptSha1Append(v16, v9, (unsigned int)v7);
  SymCryptSha1Result(v16, v21);
  SymCryptSha1Init(v16);
  SymCryptSha1Append(v16, v18, 20);
  SymCryptSha1Append(v16, v20, 20);
  SymCryptSha1Result(v16, a3);
  SymCryptSha1Init(v16);
  SymCryptSha1Append(v16, v19, 20);
  SymCryptSha1Append(v16, v21, 20);
  SymCryptSha1Result(v16, a3 + 20);
  SymCryptSha1Init(v16);
  SymCryptSha1Append(v16, v20, 20);
  SymCryptSha1Append(v16, v18, 20);
  SymCryptSha1Result(v16, a3 + 40);
  SymCryptSha1Init(v16);
  SymCryptSha1Append(v16, v21, 20);
  SymCryptSha1Append(v16, v19, 20);
  SymCryptSha1Result(v16, a3 + 60);
  v11 = 128;
  v12 = v16;
  do
  {
    *v12++ = 0;
    --v11;
  }
  while ( v11 );
  v13 = 80;
  v14 = v18;
  do
  {
    *v14++ = 0;
    --v13;
  }
  while ( v13 );
  return 1;
}

```

## disassembly

```asm
0x18004bbf0  mov     [rsp-8+arg_18], rbx
0x18004bbf5  push    rbp
0x18004bbf6  push    rsi
0x18004bbf7  push    rdi
0x18004bbf8  push    r12
0x18004bbfa  push    r13
0x18004bbfc  push    r14
0x18004bbfe  push    r15
0x18004bc00  lea     rbp, [rsp-27h]
0x18004bc05  sub     rsp, 100h
0x18004bc0c  mov     rax, cs:__security_cookie
0x18004bc13  xor     rax, rsp
0x18004bc16  mov     [rbp+57h+var_40], rax
0x18004bc1a  xor     eax, eax
0x18004bc1c  mov     r12, r8
0x18004bc1f  mov     ebx, edx
0x18004bc21  mov     [rsp+130h+var_10C], eax
0x18004bc25  mov     rdi, rcx
0x18004bc28  xor     edx, edx; Val
0x18004bc2a  lea     rcx, [rsp+130h+var_110]; void *
0x18004bc2f  lea     r8d, [rax+7Ch]; Size
0x18004bc33  call    memset_0
0x18004bc38  test    r12, r12
0x18004bc3b  jz      loc_18004BEF5
0x18004bc41  test    rdi, rdi
0x18004bc44  jz      loc_18004BEF5
0x18004bc4a  shr     ebx, 2
0x18004bc4d  test    ebx, ebx
0x18004bc4f  jz      loc_18004BEF5
0x18004bc55  mov     r14d, ebx
0x18004bc58  lea     rcx, [rsp+130h+var_110]
0x18004bc5d  add     rbx, rdi
0x18004bc60  lea     r13, [r12+14h]
0x18004bc65  call    SymCryptSha1Init
0x18004bc6a  mov     esi, 14h
0x18004bc6f  lea     rcx, [rsp+130h+var_110]
0x18004bc74  mov     r8d, esi
0x18004bc77  mov     rdx, r12
0x18004bc7a  call    SymCryptSha1Append
0x18004bc7f  mov     r8d, r14d
0x18004bc82  lea     rcx, [rsp+130h+var_110]
0x18004bc87  mov     rdx, rdi
0x18004bc8a  call    SymCryptSha1Append
0x18004bc8f  mov     r8d, esi
0x18004bc92  lea     rcx, [rsp+130h+var_110]
0x18004bc97  mov     rdx, r13
0x18004bc9a  call    SymCryptSha1Append
0x18004bc9f  mov     r8d, r14d
0x18004bca2  lea     rcx, [rsp+130h+var_110]
0x18004bca7  mov     rdx, rbx
0x18004bcaa  call    SymCryptSha1Append
0x18004bcaf  lea     rdx, [rbp+57h+var_90]
0x18004bcb3  lea     rcx, [rsp+130h+var_110]
0x18004bcb8  call    SymCryptSha1Result
0x18004bcbd  lea     rcx, [rsp+130h+var_110]
0x18004bcc2  call    SymCryptSha1Init
0x18004bcc7  mov     r8d, esi
0x18004bcca  lea     rcx, [rsp+130h+var_110]
0x18004bccf  mov     rdx, r13
0x18004bcd2  call    SymCryptSha1Append
0x18004bcd7  mov     r8d, r14d
0x18004bcda  lea     rcx, [rsp+130h+var_110]
0x18004bcdf  mov     rdx, rbx
0x18004bce2  call    SymCryptSha1Append
0x18004bce7  mov     r8d, esi
0x18004bcea  lea     rcx, [rsp+130h+var_110]
0x18004bcef  mov     rdx, r12
0x18004bcf2  call    SymCryptSha1Append
0x18004bcf7  mov     r8d, r14d
0x18004bcfa  lea     rcx, [rsp+130h+var_110]
0x18004bcff  mov     rdx, rdi
0x18004bd02  call    SymCryptSha1Append
0x18004bd07  lea     rdx, [rbp+57h+var_7C]
0x18004bd0b  lea     rcx, [rsp+130h+var_110]
0x18004bd10  call    SymCryptSha1Result
0x18004bd15  lea     rsi, [r13+14h]
0x18004bd19  lea     rdi, [rbx+r14]
0x18004bd1d  lea     rcx, [rsp+130h+var_110]
0x18004bd22  lea     r15, [rsi+14h]
0x18004bd26  lea     rbx, [rdi+r14]
0x18004bd2a  call    SymCryptSha1Init
0x18004bd2f  mov     r8d, 14h
0x18004bd35  lea     rcx, [rsp+130h+var_110]
0x18004bd3a  mov     rdx, rsi
0x18004bd3d  call    SymCryptSha1Append
0x18004bd42  mov     r8d, r14d
0x18004bd45  lea     rcx, [rsp+130h+var_110]
0x18004bd4a  mov     rdx, rdi
0x18004bd4d  call    SymCryptSha1Append
0x18004bd52  mov     r8d, 14h
0x18004bd58  lea     rcx, [rsp+130h+var_110]
0x18004bd5d  mov     rdx, r15
0x18004bd60  call    SymCryptSha1Append
0x18004bd65  mov     r8d, r14d
0x18004bd68  lea     rcx, [rsp+130h+var_110]
0x18004bd6d  mov     rdx, rbx
0x18004bd70  call    SymCryptSha1Append
0x18004bd75  lea     rdx, [rbp+57h+var_68]
0x18004bd79  lea     rcx, [rsp+130h+var_110]
0x18004bd7e  call    SymCryptSha1Result
0x18004bd83  lea     rcx, [rsp+130h+var_110]
0x18004bd88  call    SymCryptSha1Init
0x18004bd8d  mov     r8d, 14h
0x18004bd93  lea     rcx, [rsp+130h+var_110]
0x18004bd98  mov     rdx, r15
0x18004bd9b  call    SymCryptSha1Append
0x18004bda0  mov     r8d, r14d
0x18004bda3  lea     rcx, [rsp+130h+var_110]
0x18004bda8  mov     rdx, rbx
0x18004bdab  call    SymCryptSha1Append
0x18004bdb0  mov     ebx, 14h
0x18004bdb5  lea     rcx, [rsp+130h+var_110]
0x18004bdba  mov     r8d, ebx
0x18004bdbd  mov     rdx, rsi
0x18004bdc0  call    SymCryptSha1Append
0x18004bdc5  mov     r8d, r14d
0x18004bdc8  lea     rcx, [rsp+130h+var_110]
0x18004bdcd  mov     rdx, rdi
0x18004bdd0  call    SymCryptSha1Append
0x18004bdd5  lea     rdx, [rbp+57h+var_54]
0x18004bdd9  lea     rcx, [rsp+130h+var_110]
0x18004bdde  call    SymCryptSha1Result
0x18004bde3  lea     rcx, [rsp+130h+var_110]
0x18004bde8  call    SymCryptSha1Init
0x18004bded  mov     r8d, ebx
0x18004bdf0  lea     rdx, [rbp+57h+var_90]
0x18004bdf4  lea     rcx, [rsp+130h+var_110]
0x18004bdf9  call    SymCryptSha1Append
0x18004bdfe  mov     r8d, ebx
0x18004be01  lea     rdx, [rbp+57h+var_68]
0x18004be05  lea     rcx, [rsp+130h+var_110]
0x18004be0a  call    SymCryptSha1Append
0x18004be0f  mov     rdx, r12
0x18004be12  lea     rcx, [rsp+130h+var_110]
0x18004be17  call    SymCryptSha1Result
0x18004be1c  lea     rcx, [rsp+130h+var_110]
0x18004be21  call    SymCryptSha1Init
0x18004be26  mov     r8d, ebx
0x18004be29  lea     rdx, [rbp+57h+var_7C]
0x18004be2d  lea     rcx, [rsp+130h+var_110]
0x18004be32  call    SymCryptSha1Append
0x18004be37  mov     r8d, ebx
0x18004be3a  lea     rdx, [rbp+57h+var_54]
0x18004be3e  lea     rcx, [rsp+130h+var_110]
0x18004be43  call    SymCryptSha1Append
0x18004be48  mov     rdx, r13
0x18004be4b  lea     rcx, [rsp+130h+var_110]
0x18004be50  call    SymCryptSha1Result
0x18004be55  lea     rcx, [rsp+130h+var_110]
0x18004be5a  call    SymCryptSha1Init
0x18004be5f  mov     r8d, ebx
0x18004be62  lea     rdx, [rbp+57h+var_68]
0x18004be66  lea     rcx, [rsp+130h+var_110]
0x18004be6b  call    SymCryptSha1Append
0x18004be70  mov     r8d, ebx
0x18004be73  lea     rdx, [rbp+57h+var_90]
0x18004be77  lea     rcx, [rsp+130h+var_110]
0x18004be7c  call    SymCryptSha1Append
0x18004be81  mov     rdx, rsi
0x18004be84  lea     rcx, [rsp+130h+var_110]
0x18004be89  call    SymCryptSha1Result
0x18004be8e  lea     rcx, [rsp+130h+var_110]
0x18004be93  call    SymCryptSha1Init
0x18004be98  mov     r8d, ebx
0x18004be9b  lea     rdx, [rbp+57h+var_54]
0x18004be9f  lea     rcx, [rsp+130h+var_110]
0x18004bea4  call    SymCryptSha1Append
0x18004bea9  mov     r8d, ebx
0x18004beac  lea     rdx, [rbp+57h+var_7C]
0x18004beb0  lea     rcx, [rsp+130h+var_110]
0x18004beb5  call    SymCryptSha1Append
0x18004beba  mov     rdx, r15
0x18004bebd  lea     rcx, [rsp+130h+var_110]
0x18004bec2  call    SymCryptSha1Result
0x18004bec7  lea     edx, [rbx+6Ch]
0x18004beca  lea     rcx, [rsp+130h+var_110]
0x18004becf  mov     byte ptr [rcx], 0
0x18004bed2  inc     rcx
0x18004bed5  sub     rdx, 1
0x18004bed9  jnz     short loc_18004BECF
0x18004bedb  mov     edx, 50h ; 'P'
0x18004bee0  lea     rcx, [rbp+57h+var_90]
0x18004bee4  mov     byte ptr [rcx], 0
0x18004bee7  inc     rcx
0x18004beea  sub     rdx, 1
0x18004beee  jnz     short loc_18004BEE4
0x18004bef0  lea     eax, [rdx+1]
0x18004bef3  jmp     short loc_18004BEF7
0x18004bef5  xor     eax, eax
0x18004bef7  mov     rcx, [rbp+57h+var_40]
0x18004befb  xor     rcx, rsp; StackCookie
0x18004befe  call    __security_check_cookie
0x18004bf03  mov     rbx, [rsp+130h+arg_18]
0x18004bf0b  add     rsp, 100h
0x18004bf12  pop     r15
0x18004bf14  pop     r14
0x18004bf16  pop     r13
0x18004bf18  pop     r12
0x18004bf1a  pop     rdi
0x18004bf1b  pop     rsi
0x18004bf1c  pop     rbp
0x18004bf1d  retn
```
