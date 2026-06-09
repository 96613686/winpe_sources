# PiDevCfgResolveVariableKeyHandle

- ea: `0x140ade9ec`
- end: `0x140adf11d`
- name: `PiDevCfgResolveVariableKeyHandle`
- size: `1841`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x140770050`
- `0x140770130`

## callees

- `0x140403380`
- `0x1404d1f40`
- `0x140544600`
- `0x140545fe0`
- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406f6f80`
- `0x14086b898`
- `0x14087852c`
- `0x1408ee610`
- `0x1408eef70`
- `0x1409bcb10`
- `0x140a4b070`
- `0x140a7a2f4`
- `0x140ade9ec`
- `0x140bb1410`
- `0x140bb19d0`
- `0x140bb19f0`

## string_xrefs

- `0x140adec30`: `\Registry\Machine\SYSTEM`
- `0x140adec4c`: `\Registry\Machine\SOFTWARE`
- `0x140adec6c`: `\Registry\Machine\HARDWARE`
- `0x140adecb8`: `KeyPath`

## pseudocode

```c
__int64 __fastcall PiDevCfgResolveVariableKeyHandle(_QWORD *a1, void *a2, _QWORD *a3)
{
  void *v5; // r12
  int RegistryValue; // ebx
  unsigned int v7; // esi
  const wchar_t *v8; // rbx
  wchar_t **v9; // rdi
  int v10; // ecx
  int v11; // r8d
  __int64 v12; // rdx
  unsigned int v13; // edi
  int v14; // eax
  int v15; // eax
  const WCHAR *v16; // rsi
  int v17; // eax
  wchar_t *v18; // rax
  int v19; // eax
  const wchar_t *v20; // rsi
  wchar_t *v21; // rax
  int v22; // r15d
  unsigned int v23; // r13d
  _WORD *v24; // r12
  wchar_t *v25; // rax
  wchar_t *v26; // rsi
  __int64 v27; // rdi
  int v28; // edi
  char *v29; // r15
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rdi
  __int64 v33; // rax
  PVOID v34; // rcx
  __int64 v36; // rax
  unsigned int v37; // ebx
  wchar_t *v38; // rsi
  _WORD *v39; // r13
  unsigned int v40; // r12d
  wchar_t *v41; // rax
  wchar_t *v42; // r15
  __int64 v43; // rdi
  unsigned int v44; // edi
  wchar_t *v45; // r9
  __int64 v46; // rdx
  __int64 v47; // rdi
  wchar_t *v48; // r15
  __int64 v49; // rax
  bool v50; // zf
  UNICODE_STRING v51; // xmm0
  HANDLE v52; // rax
  int v53; // [rsp+40h] [rbp-C0h]
  unsigned int v54; // [rsp+40h] [rbp-C0h]
  PVOID P; // [rsp+48h] [rbp-B8h]
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v57; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  PVOID Pool2; // [rsp+70h] [rbp-90h]
  int v60; // [rsp+78h] [rbp-88h] BYREF
  int v61; // [rsp+7Ch] [rbp-84h] BYREF
  HANDLE v62; // [rsp+80h] [rbp-80h] BYREF
  void *v63; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *Str; // [rsp+90h] [rbp-70h]
  UNICODE_STRING v65; // [rsp+A0h] [rbp-60h]
  _QWORD *v66; // [rsp+B0h] [rbp-50h]
  _QWORD *v67; // [rsp+B8h] [rbp-48h]
  _BYTE v68[76]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v69; // [rsp+10Ch] [rbp+Ch]

  v67 = a3;
  *a3 = 0;
  v66 = a1;
  v53 = 0;
  v65.MaximumLength = 0;
  *(_DWORD *)(&v65.MaximumLength + 1) = 0;
  Handle = 0;
  v63 = 0;
  DestinationString = 0;
  v62 = 0;
  v5 = 0;
  v60 = 0;
  v61 = 0;
  RegistryValue = IopGetRegistryValue(a2);
  if ( RegistryValue >= 0 )
  {
    if ( !(unsigned __int8)PnpValidateRegistryString(0) )
    {
LABEL_3:
      RegistryValue = -1073741823;
      goto LABEL_67;
    }
    v7 = 0;
    v8 = (const wchar_t *)MEMORY[8];
    Pool2 = 0;
    while ( 1 )
    {
      if ( v7 >= 7 )
        goto LABEL_22;
      v9 = &(&off_140B7D7D0)[4 * v7];
      if ( !wcsicmp(*v9, v8) )
        break;
      ++v7;
    }
    if ( v9 )
    {
      v11 = *((_DWORD *)v9 + 4);
      v12 = *a1;
      if ( !v11 )
      {
        v15 = *((_DWORD *)v9 + 3);
        if ( !v15 )
        {
          RegistryValue = -1073741595;
          goto LABEL_67;
        }
        if ( v15 == 7 )
        {
          v60 = 78;
          RegistryValue = CmGetDeviceRegProp(
                            PiPnpRtlCtx,
                            *(_QWORD *)(v12 + 48),
                            0,
                            9,
                            (__int64)&v61,
                            (__int64)v68,
                            (__int64)&v60,
                            0);
          if ( RegistryValue < 0 )
            goto LABEL_67;
          if ( v61 != 1 )
            goto LABEL_3;
          v69 = 0;
          v16 = (const WCHAR *)v68;
        }
        else
        {
          v16 = v9[3];
        }
        v17 = PnpCtxOpenContextBaseKey(v10, *((_DWORD *)v9 + 3), v11, 131097, (__int64)&Handle);
        v13 = 0;
        RegistryValue = v17;
        if ( v17 < 0 )
          goto LABEL_67;
        if ( v16 )
        {
          RtlInitUnicodeString(&DestinationString, v16);
          RegistryValue = IopOpenRegistryKeyEx(&v63, Handle, &DestinationString, 131097);
          if ( RegistryValue < 0 )
            goto LABEL_67;
          ZwClose(Handle);
          Handle = v63;
        }
LABEL_31:
        ExFreePoolWithTag(0, 0);
        v19 = IopGetRegistryValue(a2);
        RegistryValue = v19;
        if ( v19 < 0 )
        {
          if ( v19 != -1073741772 )
            goto LABEL_67;
          v52 = Handle;
          RegistryValue = 0;
          v62 = Handle;
          Handle = 0;
        }
        else
        {
          if ( !(unsigned __int8)PnpValidateRegistryString(0) )
            goto LABEL_3;
          Str = (wchar_t *)MEMORY[8];
          v20 = (const wchar_t *)MEMORY[8];
          v21 = wcschr((const wchar_t *)MEMORY[8], 0x24u);
          if ( !v21 )
            goto LABEL_104;
          do
          {
            ++v13;
            v21 = wcschr(v21 + 1, 0x24u);
          }
          while ( v21 );
          v57 = v13;
          if ( v13 )
          {
            Pool2 = (PVOID)ExAllocatePool2(256, 8LL * v13, 0x63647050u);
            if ( !Pool2 )
            {
              RegistryValue = -1073741670;
              goto LABEL_67;
            }
            v22 = 0;
            v23 = 0;
            while ( 1 )
            {
              v24 = v20;
              if ( !*v20 || v23 >= v13 )
                break;
              v25 = wcschr(v20, 0x5Cu);
              v26 = v25;
              if ( v25 )
              {
                *v25 = 0;
                v27 = v25 - v24;
              }
              else
              {
                v27 = -1;
                do
                  ++v27;
                while ( v24[v27] );
              }
              v28 = 2 * v27;
              if ( *v24 == 36 )
              {
                v29 = (char *)Pool2 + 8 * v23;
                v30 = PiDevCfgResolveVariable(v66, v24 + 1, v29);
                RegistryValue = v30;
                if ( v30 < 0 )
                {
                  if ( v30 != -1073741772 )
                    goto LABEL_65;
                  RegistryValue = 0;
                }
                else
                {
                  v31 = *(_QWORD *)v29;
                  if ( *(_DWORD *)(*(_QWORD *)v29 + 32LL) == 1 || *(_DWORD *)(*(_QWORD *)v29 + 32LL) == 2 )
                  {
                    v28 = *(_DWORD *)(v31 + 36) - 2;
                  }
                  else if ( *(_DWORD *)(*(_QWORD *)v29 + 32LL) == 7 )
                  {
                    v32 = -1;
                    do
                      ++v32;
                    while ( *(_WORD *)(*(_QWORD *)(v31 + 40) + 2 * v32) );
                    v28 = 2 * v32;
                  }
                }
                v22 = v53;
                ++v23;
              }
              if ( (unsigned __int64)(v28 + (unsigned int)(unsigned __int16)v22) + 2 >= 0xFFFE )
              {
                RegistryValue = -2147483643;
LABEL_65:
                v34 = Pool2;
                goto LABEL_66;
              }
              LOWORD(v22) = v28 + 2 + v22;
              v53 = v22;
              v65.MaximumLength = v22;
              if ( v26 )
              {
                *v26 = 92;
                v20 = v26 + 1;
              }
              else
              {
                v33 = -1;
                do
                  ++v33;
                while ( v24[v33] );
                v20 = &v24[v33];
              }
              v13 = v57;
            }
            if ( RegistryValue < 0 )
              goto LABEL_65;
            v65.Length = v22 - 2;
            v36 = ExAllocatePool2(256, (unsigned __int16)v22, 0x63647050u);
            v37 = 0;
            P = (PVOID)v36;
            v65.Buffer = (wchar_t *)v36;
            if ( !v36 )
            {
              RegistryValue = -1073741670;
LABEL_73:
              v5 = P;
LABEL_111:
              if ( v5 )
                ExFreePool(v5);
              v34 = Pool2;
              if ( Pool2 )
LABEL_66:
                ExFreePoolWithTag(v34, 0);
              goto LABEL_67;
            }
            v38 = Str;
            v39 = (_WORD *)v36;
            v40 = (unsigned __int16)v22;
            v54 = 0;
            while ( *v38 && v37 < v57 )
            {
              v41 = wcschr(v38, 0x5Cu);
              v42 = v41;
              if ( v41 )
              {
                *v41 = 0;
                v43 = v41 - v38;
              }
              else
              {
                v43 = -1;
                do
                  ++v43;
                while ( v38[v43] );
              }
              if ( v38 != Str )
              {
                if ( v40 <= 2 )
                  goto LABEL_100;
                *v39++ = 92;
                v40 -= 2;
              }
              v44 = 2 * v43;
              v45 = v38;
              if ( *v38 == 36 )
              {
                v54 = v37 + 1;
                v46 = *((_QWORD *)Pool2 + v37);
                if ( v46 )
                {
                  if ( *(_DWORD *)(v46 + 32) == 1 || *(_DWORD *)(v46 + 32) == 2 )
                  {
                    v45 = *(wchar_t **)(v46 + 40);
                    v44 = *(_DWORD *)(v46 + 36) - 2;
                  }
                  else if ( *(_DWORD *)(v46 + 32) == 7 )
                  {
                    v45 = *(wchar_t **)(v46 + 40);
                    v47 = -1;
                    do
                      ++v47;
                    while ( v45[v47] );
                    v44 = 2 * v47;
                  }
                }
              }
              if ( v40 <= v44 )
              {
LABEL_100:
                RegistryValue = -1073741823;
                goto LABEL_73;
              }
              memmove(v39, v45, v44);
              v40 -= v44;
              v39 += (unsigned __int64)v44 >> 1;
              if ( v42 )
              {
                *v42 = 92;
                v48 = v42 + 1;
              }
              else
              {
                v49 = -1;
                do
                  ++v49;
                while ( v38[v49] );
                v48 = &v38[v49];
              }
              v37 = v54;
              v38 = v48;
            }
            v50 = v40 == 2;
            v5 = P;
            if ( !v50 )
            {
              RegistryValue = -1073741823;
              goto LABEL_111;
            }
            v51 = v65;
            *v39 = 0;
            DestinationString = v51;
          }
          else
          {
LABEL_104:
            v57 = 0;
            PnpRegSzToString(MEMORY[8], MEMORY[0xC], &v57);
            DestinationString.Length = v57;
            DestinationString.MaximumLength = MEMORY[0xC];
            DestinationString.Buffer = (wchar_t *)MEMORY[8];
          }
          RegistryValue = IopOpenRegistryKeyEx(&v62, Handle, &DestinationString, 131097);
          if ( RegistryValue < 0 )
            goto LABEL_111;
          v52 = v62;
        }
        *v67 = v52;
        goto LABEL_111;
      }
      v13 = 0;
      v14 = CmOpenDeviceRegKey(PiPnpRtlCtx, *(_QWORD *)(v12 + 48), v11, 0, 131097, 0, (__int64)&Handle, 0);
    }
    else
    {
LABEL_22:
      v13 = 0;
      if ( wcsicmp(v8, L"SYSTEM") )
      {
        if ( wcsicmp(v8, L"SOFTWARE") )
        {
          if ( wcsicmp(v8, L"HARDWARE") )
          {
            RegistryValue = -1073741772;
            goto LABEL_111;
          }
          v18 = L"\\Registry\\Machine\\HARDWARE";
        }
        else
        {
          v18 = L"\\Registry\\Machine\\SOFTWARE";
        }
        *(_DWORD *)&DestinationString.Length = 3538996;
      }
      else
      {
        *(_DWORD *)&DestinationString.Length = 3276848;
        v18 = L"\\Registry\\Machine\\SYSTEM";
      }
      DestinationString.Buffer = v18;
      v14 = IopOpenRegistryKeyEx(&Handle, 0, &DestinationString, 131097);
    }
    RegistryValue = v14;
    if ( v14 < 0 )
      goto LABEL_67;
    goto LABEL_31;
  }
LABEL_67:
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)RegistryValue;
}

```

## disassembly

```asm
0x140ade9ec  mov     [rsp-8+arg_18], rbx
0x140ade9f1  push    rbp
0x140ade9f2  push    rsi
0x140ade9f3  push    rdi
0x140ade9f4  push    r12
0x140ade9f6  push    r13
0x140ade9f8  push    r14
0x140ade9fa  push    r15
0x140ade9fc  lea     rbp, [rsp-20h]
0x140adea01  sub     rsp, 120h
0x140adea08  mov     rax, cs:__security_cookie
0x140adea0f  xor     rax, rsp
0x140adea12  mov     [rbp+50h+var_40], rax
0x140adea16  xor     edi, edi
0x140adea18  mov     [rbp+50h+var_98], r8
0x140adea1c  mov     eax, edi
0x140adea1e  mov     [r8], rdi
0x140adea21  mov     r15, rdx
0x140adea24  mov     [rbp+50h+var_A0], rcx
0x140adea28  mov     r13, rcx
0x140adea2b  mov     [rsp+150h+var_110], eax
0x140adea2f  xorps   xmm0, xmm0
0x140adea32  mov     word ptr [rbp+50h+var_B0+2], ax
0x140adea36  xor     r8d, r8d
0x140adea39  mov     dword ptr [rbp+50h+var_B0+4], eax
0x140adea3c  lea     r9, [rsp+150h+P]
0x140adea41  mov     [rsp+150h+P], rdi
0x140adea46  lea     rdx, aKeyroot; "KeyRoot"
0x140adea4d  mov     [rsp+150h+Handle], rdi
0x140adea52  mov     rcx, r15; KeyHandle
0x140adea55  mov     [rbp+50h+var_C8], rdi
0x140adea59  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x140adea5e  mov     [rbp+50h+var_D0], rdi
0x140adea62  mov     r12d, edi
0x140adea65  mov     [rsp+150h+var_D8], edi
0x140adea69  mov     [rsp+150h+var_D4], edi
0x140adea6d  call    IopGetRegistryValue
0x140adea72  mov     r14, [rsp+150h+P]
0x140adea77  mov     ebx, eax
0x140adea79  test    eax, eax
0x140adea7b  js      loc_140ADEE97
0x140adea81  mov     rcx, r14
0x140adea84  call    PnpValidateRegistryString
0x140adea89  test    al, al
0x140adea8b  jnz     short loc_140ADEA97
0x140adea8d  mov     ebx, 0C0000001h
0x140adea92  jmp     loc_140ADEE97
0x140adea97  mov     ebx, [r14+8]
0x140adea9b  mov     esi, edi
0x140adea9d  add     rbx, r14
0x140adeaa0  mov     [rsp+150h+var_E0], rdi
0x140adeaa5  cmp     esi, 7
0x140adeaa8  jnb     loc_140ADEC13
0x140adeaae  lea     rcx, off_140B7D7D0; "Device"
0x140adeab5  mov     edi, esi
0x140adeab7  shl     rdi, 5
0x140adeabb  mov     rdx, rbx; Str2
0x140adeabe  add     rdi, rcx
0x140adeac1  mov     rcx, [rdi]; Str1
0x140adeac4  call    _wcsicmp
0x140adeac9  test    eax, eax
0x140adeacb  jz      short loc_140ADEAD1
0x140adeacd  inc     esi
0x140adeacf  jmp     short loc_140ADEAA5
0x140adead1  xor     esi, esi
0x140adead3  test    rdi, rdi
0x140adead6  jz      loc_140ADEC13
0x140adeadc  mov     r8d, [rdi+10h]
0x140adeae0  mov     rdx, [r13+0]
0x140adeae4  test    r8d, r8d
0x140adeae7  jz      short loc_140ADEB1F
0x140adeae9  mov     rdx, [rdx+30h]
0x140adeaed  lea     rax, [rsp+150h+Handle]
0x140adeaf2  mov     rcx, cs:PiPnpRtlCtx
0x140adeaf9  xor     edi, edi
0x140adeafb  mov     [rsp+150h+var_118], rdi
0x140adeb00  xor     r9d, r9d
0x140adeb03  mov     [rsp+150h+var_120], rax
0x140adeb08  mov     byte ptr [rsp+150h+var_128], dil
0x140adeb0d  mov     dword ptr [rsp+150h+var_130], 20019h
0x140adeb15  call    _CmOpenDeviceRegKey
0x140adeb1a  jmp     loc_140ADEC97
0x140adeb1f  mov     eax, [rdi+0Ch]
0x140adeb22  test    eax, eax
0x140adeb24  jz      loc_140ADEC09
0x140adeb2a  cmp     eax, 7
0x140adeb2d  jz      short loc_140ADEB35
0x140adeb2f  mov     rsi, [rdi+18h]
0x140adeb33  jmp     short loc_140ADEB94
0x140adeb35  mov     rcx, cs:PiPnpRtlCtx
0x140adeb3c  lea     rax, [rsp+150h+var_D8]
0x140adeb41  mov     dword ptr [rsp+150h+var_118], esi
0x140adeb45  mov     r9d, 9
0x140adeb4b  mov     [rsp+150h+var_120], rax
0x140adeb50  xor     r8d, r8d
0x140adeb53  lea     rax, [rbp+50h+var_90]
0x140adeb57  mov     [rsp+150h+var_D8], 4Eh ; 'N'
0x140adeb5f  mov     rdx, [rdx+30h]
0x140adeb63  mov     [rsp+150h+var_128], rax
0x140adeb68  lea     rax, [rsp+150h+var_D4]
0x140adeb6d  mov     [rsp+150h+var_130], rax
0x140adeb72  call    _CmGetDeviceRegProp
0x140adeb77  mov     ebx, eax
0x140adeb79  test    eax, eax
0x140adeb7b  js      loc_140ADEE97
0x140adeb81  cmp     [rsp+150h+var_D4], 1
0x140adeb86  jnz     loc_140ADEA8D
0x140adeb8c  mov     [rbp+50h+var_44], si
0x140adeb90  lea     rsi, [rbp+50h+var_90]
0x140adeb94  mov     edx, [rdi+0Ch]
0x140adeb97  lea     rax, [rsp+150h+Handle]
0x140adeb9c  mov     r9d, 20019h
0x140adeba2  mov     [rsp+150h+var_130], rax
0x140adeba7  call    _PnpCtxOpenContextBaseKey
0x140adebac  xor     edi, edi
0x140adebae  mov     ebx, eax
0x140adebb0  test    eax, eax
0x140adebb2  js      loc_140ADEE97
0x140adebb8  test    rsi, rsi
0x140adebbb  jz      loc_140ADECA1
0x140adebc1  mov     rdx, rsi; SourceString
0x140adebc4  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x140adebc9  call    RtlInitUnicodeString
0x140adebce  mov     rdx, [rsp+150h+Handle]
0x140adebd3  lea     r8, [rsp+150h+DestinationString]
0x140adebd8  mov     r9d, 20019h
0x140adebde  lea     rcx, [rbp+50h+var_C8]
0x140adebe2  call    IopOpenRegistryKeyEx
0x140adebe7  mov     ebx, eax
0x140adebe9  test    eax, eax
0x140adebeb  js      loc_140ADEE97
0x140adebf1  mov     rcx, [rsp+150h+Handle]; Handle
0x140adebf6  call    ZwClose
0x140adebfb  mov     rax, [rbp+50h+var_C8]
0x140adebff  mov     [rsp+150h+Handle], rax
0x140adec04  jmp     loc_140ADECA1
0x140adec09  mov     ebx, 0C00000E5h
0x140adec0e  jmp     loc_140ADEE97
0x140adec13  lea     rdx, aSystem; "SYSTEM"
0x140adec1a  mov     rcx, rbx; Str1
0x140adec1d  call    _wcsicmp
0x140adec22  xor     edi, edi
0x140adec24  test    eax, eax
0x140adec26  jnz     short loc_140ADEC39
0x140adec28  mov     dword ptr [rsp+150h+DestinationString.Length], 320030h
0x140adec30  lea     rax, aRegistryMachin_68; "\\Registry\\Machine\\SYSTEM"
0x140adec37  jmp     short loc_140ADEC7B
0x140adec39  lea     rdx, aSoftware; "SOFTWARE"
0x140adec40  mov     rcx, rbx; Str1
0x140adec43  call    _wcsicmp
0x140adec48  test    eax, eax
0x140adec4a  jnz     short loc_140ADEC55
0x140adec4c  lea     rax, aRegistryMachin_125; "\\Registry\\Machine\\SOFTWARE"
0x140adec53  jmp     short loc_140ADEC73
0x140adec55  lea     rdx, aHardware_0; "HARDWARE"
0x140adec5c  mov     rcx, rbx; Str1
0x140adec5f  call    _wcsicmp
0x140adec64  test    eax, eax
0x140adec66  jnz     loc_140ADF0F8
0x140adec6c  lea     rax, aRegistryMachin_1; "\\Registry\\Machine\\HARDWARE"
0x140adec73  mov     dword ptr [rsp+150h+DestinationString.Length], 360034h
0x140adec7b  mov     r9d, 20019h
0x140adec81  mov     [rsp+150h+DestinationString.Buffer], rax
0x140adec86  lea     r8, [rsp+150h+DestinationString]
0x140adec8b  xor     edx, edx
0x140adec8d  lea     rcx, [rsp+150h+Handle]
0x140adec92  call    IopOpenRegistryKeyEx
0x140adec97  mov     ebx, eax
0x140adec99  test    eax, eax
0x140adec9b  js      loc_140ADEE97
0x140adeca1  xor     edx, edx; Tag
0x140adeca3  mov     rcx, r14; P
0x140adeca6  call    ExFreePoolWithTag
0x140adecab  lea     r9, [rsp+150h+P]
0x140adecb0  mov     [rsp+150h+P], rdi
0x140adecb5  xor     r8d, r8d
0x140adecb8  lea     rdx, aKeypath; "KeyPath"
0x140adecbf  mov     rcx, r15; KeyHandle
0x140adecc2  call    IopGetRegistryValue
0x140adecc7  mov     r14, [rsp+150h+P]
0x140adeccc  mov     ebx, eax
0x140adecce  test    eax, eax
0x140adecd0  js      loc_140ADF0D4
0x140adecd6  mov     rcx, r14
0x140adecd9  call    PnpValidateRegistryString
0x140adecde  test    al, al
0x140adece0  jz      loc_140ADEA8D
0x140adece6  mov     esi, [r14+8]
0x140adecea  mov     r15d, 24h ; '$'
0x140adecf0  add     rsi, r14
0x140adecf3  mov     edx, r15d; Ch
0x140adecf6  mov     rcx, rsi; Str
0x140adecf9  mov     [rbp+50h+Str], rsi
0x140adecfd  call    wcschr
0x140aded02  test    rax, rax
0x140aded05  jz      loc_140ADF074
0x140aded0b  mov     edx, r15d; Ch
0x140aded0e  lea     rcx, [rax+2]; Str
0x140aded12  inc     edi
0x140aded14  call    wcschr
0x140aded19  test    rax, rax
0x140aded1c  jnz     short loc_140ADED0B
0x140aded1e  mov     r14, [rsp+150h+P]
0x140aded23  mov     [rsp+150h+var_F8], edi
0x140aded27  test    edi, edi
0x140aded29  jz      loc_140ADF074
0x140aded2f  mov     edx, edi
0x140aded31  mov     ecx, 100h
0x140aded36  shl     rdx, 3
0x140aded3a  mov     r8d, 63647050h
0x140aded40  call    ExAllocatePool2
0x140aded45  mov     [rsp+150h+var_E0], rax
0x140aded4a  test    rax, rax
0x140aded4d  jnz     short loc_140ADED59
0x140aded4f  mov     ebx, 0C000009Ah
0x140aded54  jmp     loc_140ADEE97
0x140aded59  mov     r15d, [rsp+150h+var_110]
0x140aded5e  xor     edx, edx
0x140aded60  mov     r13d, edx
0x140aded63  lea     eax, [rdx+5Ch]
0x140aded66  lea     r8d, [rdx+2]
0x140aded6a  mov     r12, rsi
0x140aded6d  cmp     [rsi], dx
0x140aded70  jz      loc_140ADEEDF
0x140aded76  cmp     r13d, edi
0x140aded79  jnb     loc_140ADEEDF
0x140aded7f  mov     edx, eax; Ch
0x140aded81  mov     rcx, rsi; Str
0x140aded84  call    wcschr
0x140aded89  xor     edx, edx
0x140aded8b  mov     rsi, rax
0x140aded8e  test    rax, rax
0x140aded91  jz      short loc_140ADEDA1
0x140aded93  mov     rdi, rax
0x140aded96  mov     [rax], dx
0x140aded99  sub     rdi, r12
0x140aded9c  sar     rdi, 1
0x140aded9f  jmp     short loc_140ADEDAF
0x140adeda1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140adeda5  inc     rdi
0x140adeda8  cmp     [r12+rdi*2], dx
0x140adedad  jnz     short loc_140ADEDA5
0x140adedaf  add     edi, edi
0x140adedb1  mov     eax, 24h ; '$'
0x140adedb6  cmp     [r12], ax
0x140adedbb  jnz     short loc_140ADEE2B
0x140adedbd  mov     rcx, [rsp+150h+var_E0]
0x140adedc2  lea     rdx, [r12+2]
0x140adedc7  mov     eax, r13d
0x140adedca  lea     r15, [rcx+rax*8]
0x140adedce  mov     rcx, [rbp+50h+var_A0]
0x140adedd2  mov     r8, r15
0x140adedd5  call    PiDevCfgResolveVariable
0x140adedda  xor     edx, edx
0x140adeddc  mov     ebx, eax
0x140adedde  test    eax, eax
0x140adede0  js      short loc_140ADEE1A
0x140adede2  mov     rdx, [r15]
0x140adede5  mov     ecx, [rdx+20h]
0x140adede8  sub     ecx, 1
0x140adedeb  jz      short loc_140ADEE12
0x140adeded  sub     ecx, 1
0x140adedf0  jz      short loc_140ADEE12
0x140adedf2  cmp     ecx, 5
0x140adedf5  jz      short loc_140ADEDFB
0x140adedf7  xor     edx, edx
0x140adedf9  jmp     short loc_140ADEE23
0x140adedfb  mov     rax, [rdx+28h]
0x140adedff  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140adee03  xor     edx, edx
0x140adee05  inc     rdi
0x140adee08  cmp     [rax+rdi*2], dx
0x140adee0c  jnz     short loc_140ADEE05
0x140adee0e  add     edi, edi
0x140adee10  jmp     short loc_140ADEE23
0x140adee12  mov     edi, [rdx+24h]
0x140adee15  sub     edi, 2
0x140adee18  jmp     short loc_140ADEDF7
0x140adee1a  cmp     eax, 0C0000034h
0x140adee1f  jnz     short loc_140ADEE8B
0x140adee21  mov     ebx, edx
0x140adee23  mov     r15d, [rsp+150h+var_110]
0x140adee28  inc     r13d
0x140adee2b  movzx   ecx, r15w
0x140adee2f  mov     r8d, 2
0x140adee35  add     ecx, edi
0x140adee37  add     rcx, r8
0x140adee3a  cmp     rcx, 0FFFEh
0x140adee41  jnb     short loc_140ADEE86
0x140adee43  add     di, r8w
0x140adee47  add     r15w, di
0x140adee4b  mov     [rsp+150h+var_110], r15d
0x140adee50  mov     word ptr [rbp+50h+var_B0+2], r15w
0x140adee55  test    rsi, rsi
0x140adee58  jz      short loc_140ADEE66
0x140adee5a  lea     eax, [r8+5Ah]
0x140adee5e  mov     [rsi], ax
0x140adee61  add     rsi, r8
0x140adee64  jmp     short loc_140ADEE7D
0x140adee66  or      rax, 0FFFFFFFFFFFFFFFFh
  ... truncated ...
```
