# FveDatum2CreateEncryptingKeyForRecoveryPassword

- ea: `0x18010bf0c`
- end: `0x18010c296`
- name: `FveDatum2CreateEncryptingKeyForRecoveryPassword`
- size: `906`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180107118`

## callees

- `0x180104740`
- `0x180105928`
- `0x180106158`
- `0x180106538`
- `0x180106eb0`
- `0x18010bf0c`
- `0x180118da0`
- `0x180118dcc`
- `0x180118df8`
- `0x18011d1d0`
- `0x18011f010`

## string_xrefs

- `0x18010bf52`: `FveDatum2CreateEncryptingKeyForRecoveryPassword`
- `0x18010bfe3`: `FveDatum2CreateEncryptingKeyForRecoveryPassword`
- `0x18010c03b`: `FveDatum2CreateEncryptingKeyForRecoveryPassword`
- `0x18010c07c`: `FveDatum2CreateEncryptingKeyForRecoveryPassword`
- `0x18010c0af`: `FveDatum2CreateEncryptingKeyForRecoveryPassword`
- `0x18010c11f`: `FveDatum2CreateEncryptingKeyForRecoveryPassword`
- `0x18010c1d1`: `FveDatum2CreateEncryptingKeyForRecoveryPassword`
- `0x18010c21d`: `FveDatum2CreateEncryptingKeyForRecoveryPassword`
- `0x18010c25b`: `FveDatum2CreateEncryptingKeyForRecoveryPassword`
- `0x18010c13a`: `Computing PBKDF2`

## pseudocode

```c
__int64 __fastcall FveDatum2CreateEncryptingKeyForRecoveryPassword(
        unsigned __int16 *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v7; // r15
  __int64 v9; // r14
  int MustBe; // eax
  unsigned int v11; // edi
  int v12; // edx
  int v13; // edx
  int v14; // edx
  char v15; // r14
  int KeyDataPointer; // eax
  int v17; // edx
  __int64 v18; // rsi
  int v19; // eax
  _BYTE *v20; // rax
  char *Format; // [rsp+20h] [rbp-69h]
  char hAlgorithm; // [rsp+28h] [rbp-61h]
  int v24; // [rsp+30h] [rbp-59h]
  ULONG cbPassword; // [rsp+40h] [rbp-49h] BYREF
  ULONG v26; // [rsp+44h] [rbp-45h]
  __int64 v27; // [rsp+48h] [rbp-41h] BYREF
  _TBYTE v28; // [rsp+50h] [rbp-39h] BYREF
  __int64 v29; // [rsp+60h] [rbp-29h] BYREF
  ULONGLONG v30; // [rsp+68h] [rbp-21h]
  PUCHAR pbSalt; // [rsp+70h] [rbp-19h]
  _OWORD v32[2]; // [rsp+78h] [rbp-11h] BYREF

  v29 = 0;
  cbPassword = 0;
  v28 = 0.0;
  v27 = 0;
  memset(v32, 0, sizeof(v32));
  v7 = 0;
  FveLibTraceEntryHelper(
    "minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2encryptedkdfkey.c",
    293,
    "FveDatum2CreateEncryptingKeyForRecoveryPassword");
  v9 = 32;
  if ( !a1 || !a2 || !a3 || !a4 )
  {
    LOBYTE(MustBe) = 13;
    v12 = 299;
    v11 = -1073741811;
    goto LABEL_29;
  }
  *a4 = 0;
  MustBe = FveDatum2TypeMustBe(a3, 5);
  v11 = MustBe;
  if ( MustBe < 0 )
  {
    v12 = 306;
LABEL_29:
    FveLibTraceHelper(
      (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2encryptedkdfkey.c",
      v12,
      (int)"FveDatum2CreateEncryptingKeyForRecoveryPassword",
      1,
      "Error: 0x%x",
      MustBe);
    goto LABEL_30;
  }
  v13 = *a1;
  if ( v13 != 1 )
  {
    FveLibTraceHelper(
      (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2encryptedkdfkey.c",
      409,
      (int)"FveDatum2CreateEncryptingKeyForRecoveryPassword",
      1,
      "Unsupported crypto key KDF algorithm ID %u",
      v13);
    LOBYTE(MustBe) = 2;
    v12 = 410;
    v11 = -1073741822;
    goto LABEL_29;
  }
  v14 = a1[1];
  switch ( v14 )
  {
    case 1:
      v15 = 1;
      break;
    case 2:
      v15 = 2;
      break;
    case 3:
      v15 = 3;
      break;
    default:
      FveLibTraceHelper(
        (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2encryptedkdfkey.c",
        338,
        (int)"FveDatum2CreateEncryptingKeyForRecoveryPassword",
        1,
        "Unsupported crypto key KDF algorithm sub ID %u",
        v14);
      LOBYTE(MustBe) = 2;
      v12 = 339;
      v11 = -1073741822;
      goto LABEL_29;
  }
  if ( *(_DWORD *)a2 != 1 )
  {
    FveLibTraceHelper(
      (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2encryptedkdfkey.c",
      344,
      (int)"FveDatum2CreateEncryptingKeyForRecoveryPassword",
      1,
      "Invalid crypto KDF param type %u",
      *(_DWORD *)a2);
    LOBYTE(KeyDataPointer) = 13;
    v17 = 345;
    v11 = -1073741811;
LABEL_18:
    FveLibTraceHelper(
      (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2encryptedkdfkey.c",
      v17,
      (int)"FveDatum2CreateEncryptingKeyForRecoveryPassword",
      1,
      "Error: 0x%x",
      KeyDataPointer);
    v9 = 32;
    goto LABEL_30;
  }
  v30 = *(_QWORD *)(a2 + 16);
  pbSalt = *(PUCHAR *)(a2 + 4);
  v26 = *(_DWORD *)(a2 + 12);
  KeyDataPointer = FveDatum2KeyGetKeyDataPointer(a3, &v29);
  v11 = KeyDataPointer;
  if ( KeyDataPointer < 0 )
  {
    v17 = 355;
    goto LABEL_18;
  }
  v18 = v29;
  KeyDataPointer = FveDatum2AllPurposeArrayGetBytesSize(v29, &cbPassword);
  v11 = KeyDataPointer;
  if ( KeyDataPointer < 0 )
  {
    v17 = 361;
    goto LABEL_18;
  }
  FveLibTraceHelper(
    (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2encryptedkdfkey.c",
    376,
    (int)"FveDatum2CreateEncryptingKeyForRecoveryPassword",
    0,
    "Computing PBKDF2",
    hAlgorithm);
  KeyDataPointer = FveComputeKey2Pbkdf2(v15, (PUCHAR)(v18 + 64), cbPassword, pbSalt, v26, v32, v24, v30);
  v11 = KeyDataPointer;
  if ( KeyDataPointer < 0 )
  {
    v17 = 387;
    goto LABEL_18;
  }
  v28 = COERCE__TBYTE(2u);
  v9 = 32;
  v19 = FveDatum2KeyCreate(0, (__int64)&v28, (__int64)v32, 32, (__int64)Format, 13, &v27);
  v11 = v19;
  if ( v19 >= 0 )
  {
    *a4 = v27;
  }
  else
  {
    FveLibTraceHelper(
      (int)"minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2encryptedkdfkey.c",
      402,
      (int)"FveDatum2CreateEncryptingKeyForRecoveryPassword",
      1,
      "Error: 0x%x",
      v19);
    v7 = v27;
  }
LABEL_30:
  v20 = v32;
  do
  {
    *v20++ = 0;
    --v9;
  }
  while ( v9 );
  if ( v7 )
    FveDatum2Free(v7);
  FveLibTraceExitHelper(
    "minkernel\\ngscb\\cornerstone\\fvevollib2\\datum2encryptedkdfkey.c",
    425,
    "FveDatum2CreateEncryptingKeyForRecoveryPassword");
  return v11;
}

```

## disassembly

```asm
0x18010bf0c  push    rbp
0x18010bf0e  push    rbx
0x18010bf0f  push    rsi
0x18010bf10  push    rdi
0x18010bf11  push    r12
0x18010bf13  push    r13
0x18010bf15  push    r14
0x18010bf17  push    r15
0x18010bf19  lea     rbp, [rsp-1Fh]
0x18010bf1e  sub     rsp, 0A8h
0x18010bf25  mov     rax, cs:__security_cookie
0x18010bf2c  xor     rax, rsp
0x18010bf2f  mov     [rbp+57h+var_48], rax
0x18010bf33  xor     edi, edi
0x18010bf35  xorps   xmm0, xmm0
0x18010bf38  xor     eax, eax
0x18010bf3a  mov     [rbp+57h+var_80], rdi
0x18010bf3e  mov     r12, r8
0x18010bf41  mov     [rbp+57h+cbPassword], edi
0x18010bf44  mov     rsi, rdx
0x18010bf47  mov     [rbp+57h+var_90], rax
0x18010bf4b  mov     rbx, rcx
0x18010bf4e  mov     [rbp+57h+var_88], ax
0x18010bf52  lea     r8, aFvedatum2creat_0; "FveDatum2CreateEncryptingKeyForRecovery"...
0x18010bf59  mov     [rbp+57h+var_98], rdi
0x18010bf5d  mov     edx, 125h
0x18010bf62  lea     rcx, aMinkernelNgscb_19; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18010bf69  movups  [rbp+57h+var_68], xmm0
0x18010bf6d  mov     r15d, edi
0x18010bf70  mov     r13, r9
0x18010bf73  movups  [rbp+57h+var_58], xmm0
0x18010bf77  call    FveLibTraceEntryHelper
0x18010bf7c  lea     r14d, [rdi+20h]
0x18010bf80  test    rbx, rbx
0x18010bf83  jz      loc_18010C208
0x18010bf89  test    rsi, rsi
0x18010bf8c  jz      loc_18010C208
0x18010bf92  test    r12, r12
0x18010bf95  jz      loc_18010C208
0x18010bf9b  test    r13, r13
0x18010bf9e  jz      loc_18010C208
0x18010bfa4  lea     edx, [rdi+5]
0x18010bfa7  mov     [r13+0], rdi
0x18010bfab  mov     rcx, r12
0x18010bfae  call    FveDatum2TypeMustBe
0x18010bfb3  mov     edi, eax
0x18010bfb5  test    eax, eax
0x18010bfb7  jns     short loc_18010BFC3
0x18010bfb9  mov     edx, 132h
0x18010bfbe  jmp     loc_18010C214
0x18010bfc3  movzx   edx, word ptr [rbx]
0x18010bfc6  cmp     edx, 1
0x18010bfc9  jz      short loc_18010C00C
0x18010bfcb  mov     dword ptr [rsp+0E0h+hAlgorithm], edx; char
0x18010bfcf  lea     rax, aUnsupportedCry; "Unsupported crypto key KDF algorithm ID"...
0x18010bfd6  mov     ebx, 1
0x18010bfdb  mov     [rsp+0E0h+Format], rax; Format
0x18010bfe0  mov     r9d, ebx; int
0x18010bfe3  lea     r8, aFvedatum2creat_0; "FveDatum2CreateEncryptingKeyForRecovery"...
0x18010bfea  mov     edx, 199h; int
0x18010bfef  lea     rcx, aMinkernelNgscb_19; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18010bff6  call    FveLibTraceHelper
0x18010bffb  mov     eax, 0C0000002h
0x18010c000  mov     edx, 19Ah
0x18010c005  mov     edi, eax
0x18010c007  jmp     loc_18010C219
0x18010c00c  movzx   edx, word ptr [rbx+2]
0x18010c010  mov     ebx, 1
0x18010c015  mov     ecx, edx
0x18010c017  sub     ecx, ebx
0x18010c019  jz      short loc_18010C06F
0x18010c01b  sub     ecx, ebx
0x18010c01d  jz      short loc_18010C067
0x18010c01f  cmp     ecx, ebx
0x18010c021  jz      short loc_18010C05F
0x18010c023  mov     dword ptr [rsp+0E0h+hAlgorithm], edx; char
0x18010c027  lea     rax, aUnsupportedCry_1; "Unsupported crypto key KDF algorithm su"...
0x18010c02e  mov     edx, 152h; int
0x18010c033  mov     [rsp+0E0h+Format], rax; Format
0x18010c038  mov     r9d, ebx; int
0x18010c03b  lea     r8, aFvedatum2creat_0; "FveDatum2CreateEncryptingKeyForRecovery"...
0x18010c042  lea     rcx, aMinkernelNgscb_19; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18010c049  call    FveLibTraceHelper
0x18010c04e  mov     eax, 0C0000002h
0x18010c053  mov     edx, 153h
0x18010c058  mov     edi, eax
0x18010c05a  jmp     loc_18010C219
0x18010c05f  mov     r14d, 3
0x18010c065  jmp     short loc_18010C072
0x18010c067  mov     r14d, 2
0x18010c06d  jmp     short loc_18010C072
0x18010c06f  mov     r14d, ebx
0x18010c072  mov     eax, [rsi]
0x18010c074  cmp     eax, ebx
0x18010c076  jz      short loc_18010C0E0
0x18010c078  mov     dword ptr [rsp+0E0h+hAlgorithm], eax; char
0x18010c07c  lea     r8, aFvedatum2creat_0; "FveDatum2CreateEncryptingKeyForRecovery"...
0x18010c083  lea     rax, aInvalidCryptoK; "Invalid crypto KDF param type %u"
0x18010c08a  mov     r9d, ebx; int
0x18010c08d  mov     edx, 158h; int
0x18010c092  mov     [rsp+0E0h+Format], rax; Format
0x18010c097  lea     rcx, aMinkernelNgscb_19; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18010c09e  call    FveLibTraceHelper
0x18010c0a3  mov     eax, 0C000000Dh
0x18010c0a8  mov     edx, 159h; int
0x18010c0ad  mov     edi, eax
0x18010c0af  lea     r8, aFvedatum2creat_0; "FveDatum2CreateEncryptingKeyForRecovery"...
0x18010c0b6  lea     rcx, aMinkernelNgscb_19; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18010c0bd  mov     dword ptr [rsp+0E0h+hAlgorithm], eax; char
0x18010c0c1  mov     r9d, ebx; int
0x18010c0c4  lea     rax, aError0xX; "Error: 0x%x"
0x18010c0cb  mov     [rsp+0E0h+Format], rax; Format
0x18010c0d0  call    FveLibTraceHelper
0x18010c0d5  mov     r14d, 20h ; ' '
0x18010c0db  jmp     loc_18010C23F
0x18010c0e0  mov     rax, [rsi+10h]
0x18010c0e4  lea     rdx, [rbp+57h+var_80]
0x18010c0e8  mov     [rbp+57h+var_78], rax
0x18010c0ec  mov     rcx, r12
0x18010c0ef  mov     rax, [rsi+4]
0x18010c0f3  mov     [rbp+57h+pbSalt], rax
0x18010c0f7  mov     eax, [rsi+0Ch]
0x18010c0fa  mov     [rbp+57h+var_9C], eax
0x18010c0fd  call    FveDatum2KeyGetKeyDataPointer
0x18010c102  mov     edi, eax
0x18010c104  test    eax, eax
0x18010c106  jns     short loc_18010C10F
0x18010c108  mov     edx, 163h
0x18010c10d  jmp     short loc_18010C0AF
0x18010c10f  mov     rsi, [rbp+57h+var_80]
0x18010c113  lea     rdx, [rbp+57h+cbPassword]
0x18010c117  mov     rcx, rsi
0x18010c11a  call    FveDatum2AllPurposeArrayGetBytesSize
0x18010c11f  lea     r8, aFvedatum2creat_0; "FveDatum2CreateEncryptingKeyForRecovery"...
0x18010c126  mov     edi, eax
0x18010c128  lea     rcx, aMinkernelNgscb_19; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18010c12f  test    eax, eax
0x18010c131  jns     short loc_18010C13A
0x18010c133  mov     edx, 169h
0x18010c138  jmp     short loc_18010C0BD
0x18010c13a  lea     rax, aComputingPbkdf; "Computing PBKDF2"
0x18010c141  xor     r9d, r9d; int
0x18010c144  mov     edx, 178h; int
0x18010c149  mov     [rsp+0E0h+Format], rax; Format
0x18010c14e  call    FveLibTraceHelper
0x18010c153  mov     rax, [rbp+57h+var_78]
0x18010c157  lea     rdx, [rsi+40h]; pbPassword
0x18010c15b  mov     r9, [rbp+57h+pbSalt]; pbSalt
0x18010c15f  mov     ecx, r14d; char
0x18010c162  mov     r8d, [rbp+57h+cbPassword]; cbPassword
0x18010c166  mov     [rsp+0E0h+var_A8], rax; ULONGLONG
0x18010c16b  lea     rax, [rbp+57h+var_68]
0x18010c16f  mov     [rsp+0E0h+hAlgorithm], rax; hAlgorithm
0x18010c174  mov     eax, [rbp+57h+var_9C]
0x18010c177  mov     dword ptr [rsp+0E0h+Format], eax; ULONG
0x18010c17b  call    FveComputeKey2Pbkdf2
0x18010c180  mov     edi, eax
0x18010c182  test    eax, eax
0x18010c184  jns     short loc_18010C190
0x18010c186  mov     edx, 183h
0x18010c18b  jmp     loc_18010C0AF
0x18010c190  mov     eax, 2
0x18010c195  mov     [rbp+57h+var_90+2], r15
0x18010c199  mov     word ptr [rbp+57h+var_90], ax
0x18010c19d  lea     r8, [rbp+57h+var_68]
0x18010c1a1  lea     rax, [rbp+57h+var_98]
0x18010c1a5  mov     r14d, 20h ; ' '
0x18010c1ab  mov     [rsp+0E0h+var_B0], rax
0x18010c1b0  lea     rdx, [rbp+57h+var_90]
0x18010c1b4  mov     r9d, r14d
0x18010c1b7  mov     [rsp+0E0h+hAlgorithm], 0Dh
0x18010c1c0  xor     ecx, ecx
0x18010c1c2  call    FveDatum2KeyCreate
0x18010c1c7  mov     edi, eax
0x18010c1c9  test    eax, eax
0x18010c1cb  jns     short loc_18010C1FE
0x18010c1cd  mov     dword ptr [rsp+0E0h+hAlgorithm], eax; char
0x18010c1d1  lea     r8, aFvedatum2creat_0; "FveDatum2CreateEncryptingKeyForRecovery"...
0x18010c1d8  lea     rax, aError0xX; "Error: 0x%x"
0x18010c1df  mov     r9d, ebx; int
0x18010c1e2  mov     edx, 192h; int
0x18010c1e7  mov     [rsp+0E0h+Format], rax; Format
0x18010c1ec  lea     rcx, aMinkernelNgscb_19; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18010c1f3  call    FveLibTraceHelper
0x18010c1f8  mov     r15, [rbp+57h+var_98]
0x18010c1fc  jmp     short loc_18010C23F
0x18010c1fe  mov     rax, [rbp+57h+var_98]
0x18010c202  mov     [r13+0], rax
0x18010c206  jmp     short loc_18010C23F
0x18010c208  mov     eax, 0C000000Dh
0x18010c20d  mov     edx, 12Bh; int
0x18010c212  mov     edi, eax
0x18010c214  mov     ebx, 1
0x18010c219  mov     dword ptr [rsp+0E0h+hAlgorithm], eax; char
0x18010c21d  lea     r8, aFvedatum2creat_0; "FveDatum2CreateEncryptingKeyForRecovery"...
0x18010c224  lea     rax, aError0xX; "Error: 0x%x"
0x18010c22b  mov     r9d, ebx; int
0x18010c22e  lea     rcx, aMinkernelNgscb_19; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18010c235  mov     [rsp+0E0h+Format], rax; Format
0x18010c23a  call    FveLibTraceHelper
0x18010c23f  lea     rax, [rbp+57h+var_68]
0x18010c243  mov     byte ptr [rax], 0
0x18010c246  add     rax, rbx
0x18010c249  sub     r14, rbx
0x18010c24c  jnz     short loc_18010C243
0x18010c24e  test    r15, r15
0x18010c251  jz      short loc_18010C25B
0x18010c253  mov     rcx, r15
0x18010c256  call    FveDatum2Free
0x18010c25b  lea     r8, aFvedatum2creat_0; "FveDatum2CreateEncryptingKeyForRecovery"...
0x18010c262  mov     edx, 1A9h
0x18010c267  lea     rcx, aMinkernelNgscb_19; "minkernel\\ngscb\\cornerstone\\fvevolli"...
0x18010c26e  call    FveLibTraceExitHelper
0x18010c273  mov     eax, edi
0x18010c275  mov     rcx, [rbp+57h+var_48]
0x18010c279  xor     rcx, rsp; StackCookie
0x18010c27c  call    __security_check_cookie
0x18010c281  add     rsp, 0A8h
0x18010c288  pop     r15
0x18010c28a  pop     r14
0x18010c28c  pop     r13
0x18010c28e  pop     r12
0x18010c290  pop     rdi
0x18010c291  pop     rsi
0x18010c292  pop     rbx
0x18010c293  pop     rbp
0x18010c294  retn
```
