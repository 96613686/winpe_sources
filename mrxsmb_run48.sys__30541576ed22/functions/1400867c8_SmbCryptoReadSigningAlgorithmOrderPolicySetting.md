# SmbCryptoReadSigningAlgorithmOrderPolicySetting

- ea: `0x1400867c8`
- end: `0x1400869e8`
- name: `SmbCryptoReadSigningAlgorithmOrderPolicySetting`
- size: `544`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
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
- `0x1400867c8`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValues` at `0x140086882`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400869b1`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400869b1`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140086863`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140086863`
- `ntoskrnl!RtlInitUnicodeString` at `0x140086853`
- `ntoskrnl!RtlInitUnicodeString` at `0x140086853`
- `ntoskrnl!_wcsicmp` at `0x1400868fa`
- `ntoskrnl!_wcsicmp` at `0x140086919`
- `ntoskrnl!_wcsicmp` at `0x140086938`
- `ntoskrnl!_wcsicmp` at `0x1400868fa`
- `ntoskrnl!_wcsicmp` at `0x140086919`
- `ntoskrnl!_wcsicmp` at `0x140086938`

## string_xrefs

- `0x140086816`: `RtlQueryRegistryValuesEx`
- `0x14008687b`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanWorkstation`

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
0x1400867c8  mov     [rsp-8+arg_0], rbx
0x1400867cd  mov     [rsp-8+arg_18], rsi
0x1400867d2  push    rbp
0x1400867d3  push    rdi
0x1400867d4  push    r12
0x1400867d6  push    r14
0x1400867d8  push    r15
0x1400867da  lea     rbp, [rsp-37h]
0x1400867df  sub     rsp, 0F0h
0x1400867e6  mov     rax, cs:__security_cookie
0x1400867ed  xor     rax, rsp
0x1400867f0  mov     [rbp+57h+var_30], rax
0x1400867f4  mov     rsi, rdx
0x1400867f7  lea     rcx, [rbp+57h+var_B0]; void *
0x1400867fb  xor     edx, edx; Val
0x1400867fd  mov     r14, r8
0x140086800  lea     r8d, [rdx+70h]; Size
0x140086804  call    memset
0x140086809  xor     eax, eax
0x14008680b  mov     [rbp+57h+var_A8], 130h
0x140086812  mov     [rbp+57h+Src], rax
0x140086816  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14008681d  mov     [rbp+57h+var_38], eax
0x140086820  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140086824  xorps   xmm0, xmm0
0x140086827  mov     [rbp+57h+var_90], 7000000h
0x14008682e  lea     rax, aSigningalgorit; "SigningAlgorithmOrder"
0x140086835  xor     r15d, r15d
0x140086838  mov     [rbp+57h+var_A0], rax
0x14008683c  lea     rax, [rsp+110h+psz]
0x140086841  mov     [rbp+57h+var_98], rax
0x140086845  movups  xmmword ptr [rsp+110h+psz], xmm0
0x14008684a  mov     [rsp+110h+pcchLength], r15
0x14008684f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140086853  call    cs:__imp_RtlInitUnicodeString
0x14008685a  nop     dword ptr [rax+rax+00h]
0x14008685f  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x140086863  call    cs:__imp_MmGetSystemRoutineAddress
0x14008686a  nop     dword ptr [rax+rax+00h]
0x14008686f  lea     r8, [rbp+57h+var_B0]
0x140086873  mov     [rsp+110h+var_F0], r15
0x140086878  test    rax, rax
0x14008687b  lea     rdx, aRegistryMachin_13; "\\Registry\\Machine\\Software\\Policies"...
0x140086882  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14008688a  xor     r9d, r9d
0x14008688d  xor     ecx, ecx
0x14008688f  call    _guard_dispatch_icall
0x140086894  mov     ebx, eax
0x140086896  test    eax, eax
0x140086898  jns     short loc_1400868AF
0x14008689a  cmp     eax, 0C0000024h
0x14008689f  jnz     loc_1400869AC
0x1400868a5  mov     ebx, 0C000090Bh
0x1400868aa  jmp     loc_1400869AC
0x1400868af  mov     rbx, [rbp+57h+psz+8]
0x1400868b3  test    rbx, rbx
0x1400868b6  jnz     short loc_1400868C2
0x1400868b8  mov     ebx, 0C0000034h
0x1400868bd  jmp     loc_1400869AC
0x1400868c2  mov     edi, r15d
0x1400868c5  mov     r12d, 1
0x1400868cb  cmp     [rbx], r15w
0x1400868cf  jz      loc_140086987
0x1400868d5  cmp     di, 3
0x1400868d9  jnb     loc_140086987
0x1400868df  lea     r8, [rsp+110h+pcchLength]; pcchLength
0x1400868e4  mov     rcx, rbx; psz
0x1400868e7  call    RtlStringCchLengthW
0x1400868ec  test    eax, eax
0x1400868ee  js      short loc_1400868A5
0x1400868f0  lea     rdx, aAesGmac; "AES_GMAC"
0x1400868f7  mov     rcx, rbx; Str1
0x1400868fa  call    cs:__imp__wcsicmp
0x140086901  nop     dword ptr [rax+rax+00h]
0x140086906  test    eax, eax
0x140086908  jnz     short loc_14008690F
0x14008690a  lea     edx, [rax+2]
0x14008690d  jmp     short loc_14008694F
0x14008690f  lea     rdx, aAesCmac; "AES_CMAC"
0x140086916  mov     rcx, rbx; Str1
0x140086919  call    cs:__imp__wcsicmp
0x140086920  nop     dword ptr [rax+rax+00h]
0x140086925  test    eax, eax
0x140086927  jnz     short loc_14008692E
0x140086929  mov     edx, r12d
0x14008692c  jmp     short loc_14008694F
0x14008692e  lea     rdx, aHmacSha256; "HMAC_SHA_256"
0x140086935  mov     rcx, rbx; Str1
0x140086938  call    cs:__imp__wcsicmp
0x14008693f  nop     dword ptr [rax+rax+00h]
0x140086944  test    eax, eax
0x140086946  jnz     loc_1400868A5
0x14008694c  mov     edx, r15d
0x14008694f  mov     ecx, r15d
0x140086952  cmp     cx, di
0x140086955  jnb     short loc_14008696A
0x140086957  movzx   eax, cx
0x14008695a  cmp     dword ptr [rbp+rax*4+57h+Src], edx
0x14008695e  jz      loc_1400868A5
0x140086964  add     cx, r12w
0x140086968  jmp     short loc_140086952
0x14008696a  movzx   eax, di
0x14008696d  add     di, r12w
0x140086971  mov     dword ptr [rbp+rax*4+57h+Src], edx
0x140086975  mov     rax, [rsp+110h+pcchLength]
0x14008697a  lea     rbx, [rbx+rax*2]
0x14008697e  add     rbx, 2
0x140086982  jmp     loc_1400868CB
0x140086987  cmp     r15w, di
0x14008698b  jz      loc_1400868A5
0x140086991  movzx   r8d, di
0x140086995  lea     rdx, [rbp+57h+Src]; Src
0x140086999  shl     r8, 2; Size
0x14008699d  mov     rcx, rsi; void *
0x1400869a0  call    memmove
0x1400869a5  mov     [r14], di
0x1400869a9  mov     ebx, r15d
0x1400869ac  lea     rcx, [rsp+110h+psz]; UnicodeString
0x1400869b1  call    cs:__imp_RtlFreeUnicodeString
0x1400869b8  nop     dword ptr [rax+rax+00h]
0x1400869bd  mov     eax, ebx
0x1400869bf  mov     rcx, [rbp+57h+var_30]
0x1400869c3  xor     rcx, rsp; StackCookie
0x1400869c6  call    __security_check_cookie
0x1400869cb  lea     r11, [rsp+110h+var_20]
0x1400869d3  mov     rbx, [r11+30h]
0x1400869d7  mov     rsi, [r11+48h]
0x1400869db  mov     rsp, r11
0x1400869de  pop     r15
0x1400869e0  pop     r14
0x1400869e2  pop     r12
0x1400869e4  pop     rdi
0x1400869e5  pop     rbp
0x1400869e6  retn
```
