# SmbCryptoReadSigningAlgorithmOrderPolicySetting

- ea: `0x140086778`
- end: `0x140086998`
- name: `SmbCryptoReadSigningAlgorithmOrderPolicySetting`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14007fd3c`

## callees

- `0x14004cccc`
- `0x140059dc0`
- `0x140059ea0`
- `0x140059f00`
- `0x14005a200`
- `0x140086778`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValues` at `0x140086832`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140086961`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140086961`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140086813`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140086813`
- `ntoskrnl!RtlInitUnicodeString` at `0x140086803`
- `ntoskrnl!RtlInitUnicodeString` at `0x140086803`
- `ntoskrnl!_wcsicmp` at `0x1400868aa`
- `ntoskrnl!_wcsicmp` at `0x1400868c9`
- `ntoskrnl!_wcsicmp` at `0x1400868e8`
- `ntoskrnl!_wcsicmp` at `0x1400868aa`
- `ntoskrnl!_wcsicmp` at `0x1400868c9`
- `ntoskrnl!_wcsicmp` at `0x1400868e8`

## string_xrefs

- `0x1400867c6`: `RtlQueryRegistryValuesEx`
- `0x14008682b`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanWorkstation`

## pseudocode

```c
__int64 __fastcall SmbCryptoReadSigningAlgorithmOrderPolicySetting(__int64 a1, void *a2, unsigned __int16 *a3)
{
  PVOID SystemRoutineAddress; // rax
  int v6; // eax
  size_t v7; // rdx
  unsigned int v8; // ebx
  const wchar_t *v9; // rbx
  unsigned __int16 i; // di
  unsigned __int16 j; // cx
  __int64 v12; // rax
  size_t pcchLength; // [rsp+30h] [rbp-89h] BYREF
  STRSAFE_PCNZWCH psz[2]; // [rsp+38h] [rbp-81h] BYREF
  UNICODE_STRING DestinationString; // [rsp+48h] [rbp-71h] BYREF
  _QWORD v17[14]; // [rsp+60h] [rbp-59h] BYREF
  __int64 Src; // [rsp+D0h] [rbp+17h] BYREF
  int v19; // [rsp+D8h] [rbp+1Fh]

  memset(v17, 0, sizeof(v17));
  LODWORD(v17[1]) = 304;
  Src = 0;
  v19 = 0;
  LODWORD(v17[4]) = 117440512;
  v17[2] = L"SigningAlgorithmOrder";
  v17[3] = psz;
  *(_OWORD *)psz = 0;
  pcchLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  v6 = ((__int64 (__fastcall *)(_QWORD, const wchar_t *, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(
         0,
         L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanWorkstation",
         v17,
         0,
         0);
  v8 = v6;
  if ( v6 >= 0 )
  {
    v9 = psz[1];
    if ( !psz[1] )
    {
      v8 = -1073741772;
      goto LABEL_25;
    }
    for ( i = 0; *v9 && i < 3u; ++i )
    {
      if ( RtlStringCchLengthW(v9, v7, &pcchLength) < 0 )
        goto LABEL_5;
      if ( _wcsicmp(v9, L"AES_GMAC") )
      {
        if ( _wcsicmp(v9, L"AES_CMAC") )
        {
          if ( _wcsicmp(v9, L"HMAC_SHA_256") )
            goto LABEL_5;
          v7 = 0;
        }
        else
        {
          v7 = 1;
        }
      }
      else
      {
        v7 = 2;
      }
      for ( j = 0; j < i; ++j )
      {
        if ( *((_DWORD *)&Src + j) == (_DWORD)v7 )
          goto LABEL_5;
      }
      v12 = i;
      *((_DWORD *)&Src + v12) = v7;
      v9 += pcchLength + 1;
    }
    if ( i )
    {
      memmove(a2, &Src, 4LL * i);
      *a3 = i;
      v8 = 0;
      goto LABEL_25;
    }
    goto LABEL_5;
  }
  if ( v6 == -1073741788 )
LABEL_5:
    v8 = -1073739509;
LABEL_25:
  RtlFreeUnicodeString((PUNICODE_STRING)psz);
  return v8;
}

```

## disassembly

```asm
0x140086778  mov     [rsp-8+arg_0], rbx
0x14008677d  mov     [rsp-8+arg_18], rsi
0x140086782  push    rbp
0x140086783  push    rdi
0x140086784  push    r12
0x140086786  push    r14
0x140086788  push    r15
0x14008678a  lea     rbp, [rsp-37h]
0x14008678f  sub     rsp, 0F0h
0x140086796  mov     rax, cs:__security_cookie
0x14008679d  xor     rax, rsp
0x1400867a0  mov     [rbp+57h+var_30], rax
0x1400867a4  mov     rsi, rdx
0x1400867a7  lea     rcx, [rbp+57h+var_B0]; void *
0x1400867ab  xor     edx, edx; Val
0x1400867ad  mov     r14, r8
0x1400867b0  lea     r8d, [rdx+70h]; Size
0x1400867b4  call    memset
0x1400867b9  xor     eax, eax
0x1400867bb  mov     [rbp+57h+var_A8], 130h
0x1400867c2  mov     [rbp+57h+Src], rax
0x1400867c6  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x1400867cd  mov     [rbp+57h+var_38], eax
0x1400867d0  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400867d4  xorps   xmm0, xmm0
0x1400867d7  mov     [rbp+57h+var_90], 7000000h
0x1400867de  lea     rax, aSigningalgorit; "SigningAlgorithmOrder"
0x1400867e5  xor     r15d, r15d
0x1400867e8  mov     [rbp+57h+var_A0], rax
0x1400867ec  lea     rax, [rsp+110h+psz]
0x1400867f1  mov     [rbp+57h+var_98], rax
0x1400867f5  movups  xmmword ptr [rsp+110h+psz], xmm0
0x1400867fa  mov     [rsp+110h+pcchLength], r15
0x1400867ff  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140086803  call    cs:__imp_RtlInitUnicodeString
0x14008680a  nop     dword ptr [rax+rax+00h]
0x14008680f  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x140086813  call    cs:__imp_MmGetSystemRoutineAddress
0x14008681a  nop     dword ptr [rax+rax+00h]
0x14008681f  lea     r8, [rbp+57h+var_B0]
0x140086823  mov     [rsp+110h+var_F0], r15
0x140086828  test    rax, rax
0x14008682b  lea     rdx, aRegistryMachin_13; "\\Registry\\Machine\\Software\\Policies"...
0x140086832  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14008683a  xor     r9d, r9d
0x14008683d  xor     ecx, ecx
0x14008683f  call    _guard_dispatch_icall
0x140086844  mov     ebx, eax
0x140086846  test    eax, eax
0x140086848  jns     short loc_14008685F
0x14008684a  cmp     eax, 0C0000024h
0x14008684f  jnz     loc_14008695C
0x140086855  mov     ebx, 0C000090Bh
0x14008685a  jmp     loc_14008695C
0x14008685f  mov     rbx, [rbp+57h+psz+8]
0x140086863  test    rbx, rbx
0x140086866  jnz     short loc_140086872
0x140086868  mov     ebx, 0C0000034h
0x14008686d  jmp     loc_14008695C
0x140086872  mov     edi, r15d
0x140086875  mov     r12d, 1
0x14008687b  cmp     [rbx], r15w
0x14008687f  jz      loc_140086937
0x140086885  cmp     di, 3
0x140086889  jnb     loc_140086937
0x14008688f  lea     r8, [rsp+110h+pcchLength]; pcchLength
0x140086894  mov     rcx, rbx; psz
0x140086897  call    RtlStringCchLengthW
0x14008689c  test    eax, eax
0x14008689e  js      short loc_140086855
0x1400868a0  lea     rdx, aAesGmac; "AES_GMAC"
0x1400868a7  mov     rcx, rbx; Str1
0x1400868aa  call    cs:__imp__wcsicmp
0x1400868b1  nop     dword ptr [rax+rax+00h]
0x1400868b6  test    eax, eax
0x1400868b8  jnz     short loc_1400868BF
0x1400868ba  lea     edx, [rax+2]
0x1400868bd  jmp     short loc_1400868FF
0x1400868bf  lea     rdx, aAesCmac; "AES_CMAC"
0x1400868c6  mov     rcx, rbx; Str1
0x1400868c9  call    cs:__imp__wcsicmp
0x1400868d0  nop     dword ptr [rax+rax+00h]
0x1400868d5  test    eax, eax
0x1400868d7  jnz     short loc_1400868DE
0x1400868d9  mov     edx, r12d
0x1400868dc  jmp     short loc_1400868FF
0x1400868de  lea     rdx, aHmacSha256; "HMAC_SHA_256"
0x1400868e5  mov     rcx, rbx; Str1
0x1400868e8  call    cs:__imp__wcsicmp
0x1400868ef  nop     dword ptr [rax+rax+00h]
0x1400868f4  test    eax, eax
0x1400868f6  jnz     loc_140086855
0x1400868fc  mov     edx, r15d
0x1400868ff  mov     ecx, r15d
0x140086902  cmp     cx, di
0x140086905  jnb     short loc_14008691A
0x140086907  movzx   eax, cx
0x14008690a  cmp     dword ptr [rbp+rax*4+57h+Src], edx
0x14008690e  jz      loc_140086855
0x140086914  add     cx, r12w
0x140086918  jmp     short loc_140086902
0x14008691a  movzx   eax, di
0x14008691d  add     di, r12w
0x140086921  mov     dword ptr [rbp+rax*4+57h+Src], edx
0x140086925  mov     rax, [rsp+110h+pcchLength]
0x14008692a  lea     rbx, [rbx+rax*2]
0x14008692e  add     rbx, 2
0x140086932  jmp     loc_14008687B
0x140086937  cmp     r15w, di
0x14008693b  jz      loc_140086855
0x140086941  movzx   r8d, di
0x140086945  lea     rdx, [rbp+57h+Src]; Src
0x140086949  shl     r8, 2; Size
0x14008694d  mov     rcx, rsi; void *
0x140086950  call    memmove
0x140086955  mov     [r14], di
0x140086959  mov     ebx, r15d
0x14008695c  lea     rcx, [rsp+110h+psz]; UnicodeString
0x140086961  call    cs:__imp_RtlFreeUnicodeString
0x140086968  nop     dword ptr [rax+rax+00h]
0x14008696d  mov     eax, ebx
0x14008696f  mov     rcx, [rbp+57h+var_30]
0x140086973  xor     rcx, rsp; StackCookie
0x140086976  call    __security_check_cookie
0x14008697b  lea     r11, [rsp+110h+var_20]
0x140086983  mov     rbx, [r11+30h]
0x140086987  mov     rsi, [r11+48h]
0x14008698b  mov     rsp, r11
0x14008698e  pop     r15
0x140086990  pop     r14
0x140086992  pop     r12
0x140086994  pop     rdi
0x140086995  pop     rbp
0x140086996  retn
```
