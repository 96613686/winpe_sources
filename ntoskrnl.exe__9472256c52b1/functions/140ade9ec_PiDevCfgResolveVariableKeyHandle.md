# PiDevCfgResolveVariableKeyHandle

- ea: `0x140ade9ec`
- end: `0x140adf11d`
- name: `PiDevCfgResolveVariableKeyHandle`
- size: `1841`
- prototype: `__int64 __fastcall(_QWORD *, void *, _QWORD *)`
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
  PVOID v5; // r12
  NTSTATUS RegistryValue; // eax
  unsigned __int16 *v7; // r14
  int DeviceRegProp; // ebx
  unsigned int v9; // esi
  const wchar_t *v10; // rbx
  wchar_t **v11; // rdi
  int v12; // ecx
  int v13; // r8d
  __int64 v14; // rdx
  unsigned int v15; // edi
  int v16; // eax
  int v17; // eax
  const WCHAR *v18; // rsi
  int v19; // eax
  wchar_t *v20; // rax
  NTSTATUS v21; // eax
  wchar_t *v22; // rsi
  wchar_t *v23; // rax
  int v24; // r15d
  unsigned int v25; // r13d
  wchar_t *v26; // r12
  wchar_t *v27; // rax
  wchar_t *v28; // rsi
  __int64 v29; // rdi
  int v30; // edi
  char *v31; // r15
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rdi
  __int64 v35; // rax
  PVOID v36; // rcx
  void *v38; // rax
  unsigned int v39; // ebx
  wchar_t *v40; // rsi
  _WORD *v41; // r13
  unsigned int v42; // r12d
  wchar_t *v43; // rax
  wchar_t *v44; // r15
  __int64 v45; // rdi
  unsigned int v46; // edi
  wchar_t *v47; // r9
  __int64 v48; // rdx
  __int64 v49; // rdi
  wchar_t *v50; // r15
  __int64 v51; // rax
  bool v52; // zf
  UNICODE_STRING v53; // xmm0
  __int64 v54; // rdx
  char *v55; // rcx
  HANDLE v56; // rax
  int v57; // [rsp+40h] [rbp-C0h]
  unsigned int v58; // [rsp+40h] [rbp-C0h]
  PVOID P; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v61; // [rsp+58h] [rbp-A8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  PVOID Pool2; // [rsp+70h] [rbp-90h]
  int v64; // [rsp+78h] [rbp-88h] BYREF
  int v65; // [rsp+7Ch] [rbp-84h] BYREF
  HANDLE v66; // [rsp+80h] [rbp-80h] BYREF
  void *v67; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *Str; // [rsp+90h] [rbp-70h]
  UNICODE_STRING v69; // [rsp+A0h] [rbp-60h]
  _QWORD *v70; // [rsp+B0h] [rbp-50h]
  _QWORD *v71; // [rsp+B8h] [rbp-48h]
  _BYTE v72[76]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v73; // [rsp+10Ch] [rbp+Ch]

  v71 = a3;
  *a3 = 0;
  v70 = a1;
  v57 = 0;
  v69.MaximumLength = 0;
  *(_DWORD *)(&v69.MaximumLength + 1) = 0;
  P = 0;
  Handle = 0;
  v67 = 0;
  DestinationString = 0;
  v66 = 0;
  v5 = 0;
  v64 = 0;
  v65 = 0;
  RegistryValue = IopGetRegistryValue(a2, L"KeyRoot", 0, &P);
  v7 = (unsigned __int16 *)P;
  DeviceRegProp = RegistryValue;
  if ( RegistryValue >= 0 )
  {
    if ( !(unsigned __int8)PnpValidateRegistryString(P) )
    {
LABEL_3:
      DeviceRegProp = -1073741823;
      goto LABEL_67;
    }
    v9 = 0;
    v10 = (unsigned __int16 *)((char *)v7 + *((unsigned int *)v7 + 2));
    Pool2 = 0;
    while ( 1 )
    {
      if ( v9 >= 7 )
        goto LABEL_22;
      v11 = &(&off_140B7D7D0)[4 * v9];
      if ( !wcsicmp(*v11, v10) )
        break;
      ++v9;
    }
    if ( v11 )
    {
      v13 = *((_DWORD *)v11 + 4);
      v14 = *a1;
      if ( !v13 )
      {
        v17 = *((_DWORD *)v11 + 3);
        if ( !v17 )
        {
          DeviceRegProp = -1073741595;
          goto LABEL_67;
        }
        if ( v17 == 7 )
        {
          v64 = 78;
          DeviceRegProp = CmGetDeviceRegProp(
                            *(__int64 *)&PiPnpRtlCtx,
                            *(_QWORD *)(v14 + 48),
                            0,
                            9u,
                            (__int64)&v65,
                            (__int64)v72,
                            (__int64)&v64,
                            0);
          if ( DeviceRegProp < 0 )
            goto LABEL_67;
          if ( v65 != 1 )
            goto LABEL_3;
          v73 = 0;
          v18 = (const WCHAR *)v72;
        }
        else
        {
          v18 = v11[3];
        }
        v19 = PnpCtxOpenContextBaseKey(v12, *((_DWORD *)v11 + 3), v13, 131097, (__int64)&Handle);
        v15 = 0;
        DeviceRegProp = v19;
        if ( v19 < 0 )
          goto LABEL_67;
        if ( v18 )
        {
          RtlInitUnicodeString(&DestinationString, v18);
          DeviceRegProp = IopOpenRegistryKeyEx(&v67, Handle, &DestinationString, 131097);
          if ( DeviceRegProp < 0 )
            goto LABEL_67;
          ZwClose(Handle);
          Handle = v67;
        }
LABEL_31:
        ExFreePoolWithTag(v7, 0);
        P = 0;
        v21 = IopGetRegistryValue(a2, L"KeyPath", 0, &P);
        v7 = (unsigned __int16 *)P;
        DeviceRegProp = v21;
        if ( v21 < 0 )
        {
          if ( v21 != -1073741772 )
            goto LABEL_67;
          v56 = Handle;
          DeviceRegProp = 0;
          v66 = Handle;
          Handle = 0;
        }
        else
        {
          if ( !(unsigned __int8)PnpValidateRegistryString(P) )
            goto LABEL_3;
          Str = (unsigned __int16 *)((char *)v7 + *((unsigned int *)v7 + 2));
          v22 = Str;
          v23 = wcschr(Str, 0x24u);
          if ( !v23 )
            goto LABEL_106;
          do
          {
            ++v15;
            v23 = wcschr(v23 + 1, 0x24u);
          }
          while ( v23 );
          v7 = (unsigned __int16 *)P;
          v61 = v15;
          if ( v15 )
          {
            Pool2 = (PVOID)ExAllocatePool2(256, 8LL * v15, 1667526736);
            if ( !Pool2 )
            {
              DeviceRegProp = -1073741670;
              goto LABEL_67;
            }
            v24 = 0;
            v25 = 0;
            while ( 1 )
            {
              v26 = v22;
              if ( !*v22 || v25 >= v15 )
                break;
              v27 = wcschr(v22, 0x5Cu);
              v28 = v27;
              if ( v27 )
              {
                *v27 = 0;
                v29 = v27 - v26;
              }
              else
              {
                v29 = -1;
                do
                  ++v29;
                while ( v26[v29] );
              }
              v30 = 2 * v29;
              if ( *v26 == 36 )
              {
                v31 = (char *)Pool2 + 8 * v25;
                v32 = PiDevCfgResolveVariable(v70, v26 + 1, v31);
                DeviceRegProp = v32;
                if ( v32 < 0 )
                {
                  if ( v32 != -1073741772 )
                    goto LABEL_65;
                  DeviceRegProp = 0;
                }
                else
                {
                  v33 = *(_QWORD *)v31;
                  if ( *(_DWORD *)(*(_QWORD *)v31 + 32LL) == 1 || *(_DWORD *)(*(_QWORD *)v31 + 32LL) == 2 )
                  {
                    v30 = *(_DWORD *)(v33 + 36) - 2;
                  }
                  else if ( *(_DWORD *)(*(_QWORD *)v31 + 32LL) == 7 )
                  {
                    v34 = -1;
                    do
                      ++v34;
                    while ( *(_WORD *)(*(_QWORD *)(v33 + 40) + 2 * v34) );
                    v30 = 2 * v34;
                  }
                }
                v24 = v57;
                ++v25;
              }
              if ( (unsigned __int64)(v30 + (unsigned int)(unsigned __int16)v24) + 2 >= 0xFFFE )
              {
                DeviceRegProp = -2147483643;
LABEL_65:
                v36 = Pool2;
                goto LABEL_66;
              }
              LOWORD(v24) = v30 + 2 + v24;
              v57 = v24;
              v69.MaximumLength = v24;
              if ( v28 )
              {
                *v28 = 92;
                v22 = v28 + 1;
              }
              else
              {
                v35 = -1;
                do
                  ++v35;
                while ( v26[v35] );
                v22 = &v26[v35];
              }
              v15 = v61;
            }
            if ( DeviceRegProp < 0 )
              goto LABEL_65;
            v69.Length = v24 - 2;
            v38 = (void *)ExAllocatePool2(256, (unsigned __int16)v24, 1667526736);
            v39 = 0;
            P = v38;
            v69.Buffer = (wchar_t *)v38;
            if ( !v38 )
            {
              DeviceRegProp = -1073741670;
LABEL_75:
              v5 = P;
LABEL_113:
              if ( v5 )
                ExFreePool(v5);
              v36 = Pool2;
              if ( Pool2 )
LABEL_66:
                ExFreePoolWithTag(v36, 0);
              goto LABEL_67;
            }
            v40 = Str;
            v41 = v38;
            v42 = (unsigned __int16)v24;
            v58 = 0;
            while ( *v40 && v39 < v61 )
            {
              v43 = wcschr(v40, 0x5Cu);
              v44 = v43;
              if ( v43 )
              {
                *v43 = 0;
                v45 = v43 - v40;
              }
              else
              {
                v45 = -1;
                do
                  ++v45;
                while ( v40[v45] );
              }
              if ( v40 != Str )
              {
                if ( v42 <= 2 )
                  goto LABEL_102;
                *v41++ = 92;
                v42 -= 2;
              }
              v46 = 2 * v45;
              v47 = v40;
              if ( *v40 == 36 )
              {
                v58 = v39 + 1;
                v48 = *((_QWORD *)Pool2 + v39);
                if ( v48 )
                {
                  if ( *(_DWORD *)(v48 + 32) == 1 || *(_DWORD *)(v48 + 32) == 2 )
                  {
                    v47 = *(wchar_t **)(v48 + 40);
                    v46 = *(_DWORD *)(v48 + 36) - 2;
                  }
                  else if ( *(_DWORD *)(v48 + 32) == 7 )
                  {
                    v47 = *(wchar_t **)(v48 + 40);
                    v49 = -1;
                    do
                      ++v49;
                    while ( v47[v49] );
                    v46 = 2 * v49;
                  }
                }
              }
              if ( v42 <= v46 )
              {
LABEL_102:
                DeviceRegProp = -1073741823;
                goto LABEL_75;
              }
              memmove(v41, v47, v46);
              v42 -= v46;
              v41 += (unsigned __int64)v46 >> 1;
              if ( v44 )
              {
                *v44 = 92;
                v50 = v44 + 1;
              }
              else
              {
                v51 = -1;
                do
                  ++v51;
                while ( v40[v51] );
                v50 = &v40[v51];
              }
              v39 = v58;
              v40 = v50;
            }
            v52 = v42 == 2;
            v5 = P;
            if ( !v52 )
            {
              DeviceRegProp = -1073741823;
              goto LABEL_113;
            }
            v53 = v69;
            *v41 = 0;
            DestinationString = v53;
          }
          else
          {
LABEL_106:
            v54 = *((unsigned int *)v7 + 3);
            v55 = (char *)v7 + *((unsigned int *)v7 + 2);
            v61 = 0;
            PnpRegSzToString(v55, v54, &v61);
            DestinationString.Length = v61;
            DestinationString.MaximumLength = v7[6];
            DestinationString.Buffer = (unsigned __int16 *)((char *)v7 + *((unsigned int *)v7 + 2));
          }
          DeviceRegProp = IopOpenRegistryKeyEx(&v66, Handle, &DestinationString, 131097);
          if ( DeviceRegProp < 0 )
            goto LABEL_113;
          v56 = v66;
        }
        *v71 = v56;
        goto LABEL_113;
      }
      v15 = 0;
      v16 = CmOpenDeviceRegKey(*(__int64 *)&PiPnpRtlCtx, *(_QWORD *)(v14 + 48), v13, 0, 131097, 0, (__int64)&Handle, 0);
    }
    else
    {
LABEL_22:
      v15 = 0;
      if ( wcsicmp(v10, L"SYSTEM") )
      {
        if ( wcsicmp(v10, L"SOFTWARE") )
        {
          if ( wcsicmp(v10, L"HARDWARE") )
          {
            DeviceRegProp = -1073741772;
            goto LABEL_113;
          }
          v20 = L"\\Registry\\Machine\\HARDWARE";
        }
        else
        {
          v20 = L"\\Registry\\Machine\\SOFTWARE";
        }
        *(_DWORD *)&DestinationString.Length = 3538996;
      }
      else
      {
        *(_DWORD *)&DestinationString.Length = 3276848;
        v20 = L"\\Registry\\Machine\\SYSTEM";
      }
      DestinationString.Buffer = v20;
      v16 = IopOpenRegistryKeyEx(&Handle, 0, &DestinationString, 131097);
    }
    DeviceRegProp = v16;
    if ( v16 < 0 )
      goto LABEL_67;
    goto LABEL_31;
  }
LABEL_67:
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)DeviceRegProp;
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
