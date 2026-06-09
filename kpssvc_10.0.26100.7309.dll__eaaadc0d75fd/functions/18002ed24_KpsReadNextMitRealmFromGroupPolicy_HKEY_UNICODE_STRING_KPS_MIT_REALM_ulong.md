# KpsReadNextMitRealmFromGroupPolicy(HKEY__ *,_UNICODE_STRING *,_KPS_MIT_REALM *,ulong *)

- ea: `0x18002ed24`
- end: `0x18002f18d`
- name: `?KpsReadNextMitRealmFromGroupPolicy@@YAKPEAUHKEY__@@PEAU_UNICODE_STRING@@PEAU_KPS_MIT_REALM@@PEAK@Z`
- size: `1129`
- prototype: `unsigned int __fastcall(HKEY hKey, struct _UNICODE_STRING *, struct _KPS_MIT_REALM *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x18002eb50`

## callees

- `0x18001ae0c`
- `0x18001ae38`
- `0x18001ae7c`
- `0x18002dbb8`
- `0x18002e330`
- `0x18002ed24`
- `0x18002f738`
- `0x1800300f4`
- `0x18003012c`
- `0x18003100e`
- `0x180031040`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002ee2c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002efbe`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002ee2c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002efbe`
- `ntdll!RtlDuplicateUnicodeString` at `0x18002eefb`
- `ntdll!RtlDuplicateUnicodeString` at `0x18002eefb`
- `ntdll!RtlInitUnicodeString` at `0x18002eee1`
- `ntdll!RtlInitUnicodeString` at `0x18002f02c`
- `ntdll!RtlInitUnicodeString` at `0x18002eee1`
- `ntdll!RtlInitUnicodeString` at `0x18002f02c`
- `ntdll!RtlFreeUnicodeString` at `0x18002ee5f`
- `ntdll!RtlFreeUnicodeString` at `0x18002ee5f`

## pseudocode

```c
__int64 __fastcall KpsReadNextMitRealmFromGroupPolicy(
        HKEY hKey,
        struct _UNICODE_STRING *a2,
        struct _KPS_MIT_REALM *a3,
        unsigned int *a4)
{
  WCHAR *v8; // r14
  DWORD v9; // edx
  unsigned int v10; // ebx
  unsigned __int16 v12; // di
  unsigned int v13; // eax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  BYTE *lpData; // rax
  DWORD v18; // edx
  int v19; // r8d
  __int128 v20; // xmm1
  __int64 v21; // xmm0_8
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v26; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v27; // [rsp+70h] [rbp-90h]
  __int64 v28; // [rsp+80h] [rbp-80h]
  struct _UNICODE_STRING v29; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-68h] BYREF
  WCHAR ValueName[264]; // [rsp+B0h] [rbp-50h] BYREF

  Type = 0;
  cbData = 0;
  v28 = 0;
  v8 = 0;
  DestinationString = 0;
  UnicodeString = 0;
  v29 = 0;
  v26 = 0;
  v27 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids);
  *(_OWORD *)a3 = 0;
  *((_OWORD *)a3 + 1) = 0;
  *((_QWORD *)a3 + 4) = 0;
  *a2 = 0;
  while ( 1 )
  {
    memset_0(ValueName, 0, 0x20Au);
    v9 = *a4;
    cchValueName = 261;
    v10 = RegEnumValueW(hKey, v9, ValueName, &cchValueName, 0, &Type, 0, &cbData);
    if ( v10 == 259 )
      goto LABEL_9;
    if ( v10 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_9;
      v15 = 35;
      goto LABEL_25;
    }
    if ( Type == 1 )
      break;
    ++*a4;
  }
  if ( (cbData & 1) != 0 || cbData > 0xFFFD )
  {
    v10 = 87;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids, cbData, 87);
    goto LABEL_9;
  }
  v12 = cbData + 2;
  RtlInitUnicodeString(&DestinationString, ValueName);
  v13 = RtlDuplicateUnicodeString(1u, &DestinationString, &UnicodeString);
  v10 = v13;
  if ( !v13 )
  {
    lpData = (BYTE *)KpsAllocMem(v12);
    v8 = (WCHAR *)lpData;
    if ( lpData )
    {
      v18 = *a4;
      cchValueName = 261;
      v13 = RegEnumValueW(hKey, v18, ValueName, &cchValueName, 0, &Type, lpData, &cbData);
      v10 = v13;
      if ( !v13 )
      {
        if ( (cbData & 1) != 0 || cbData > (unsigned __int64)v12 - 2 )
        {
          v10 = 87;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_dD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              40,
              &WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids,
              cbData,
              87);
        }
        else
        {
          v8[(unsigned __int64)cbData >> 1] = 0;
          RtlInitUnicodeString(&v29, v8);
          v10 = KpsParseMitRealmSettings(&v29, (struct _KPS_MIT_REALM *)&v26);
          if ( v10 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_DZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, v19, v10, (__int64)&v29);
          }
          else
          {
            *a2 = UnicodeString;
            UnicodeString = 0;
            v20 = v27;
            *(_OWORD *)a3 = v26;
            v21 = v28;
            *((_OWORD *)a3 + 1) = v20;
            v28 = 0;
            *((_QWORD *)a3 + 4) = v21;
            ++*a4;
            v26 = 0;
            v27 = 0;
          }
        }
        goto LABEL_9;
      }
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_9;
      v15 = 39;
LABEL_19:
      v16 = v13;
LABEL_20:
      WPP_SF_D(v14[2], v15, &WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids, v16);
      goto LABEL_9;
    }
    v10 = 8;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_9;
    v15 = 38;
LABEL_25:
    v16 = v10;
    goto LABEL_20;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v15 = 37;
    goto LABEL_19;
  }
LABEL_9:
  KpsFreeMem(v8);
  KpsFreeMitRealm((struct _KPS_MIT_REALM *)&v26);
  RtlFreeUnicodeString(&UnicodeString);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18002ed24  push    rbp
0x18002ed26  push    rbx
0x18002ed27  push    rsi
0x18002ed28  push    rdi
0x18002ed29  push    r12
0x18002ed2b  push    r13
0x18002ed2d  push    r14
0x18002ed2f  push    r15
0x18002ed31  lea     rbp, [rsp-1D8h]
0x18002ed39  sub     rsp, 2D8h
0x18002ed40  mov     rax, cs:__security_cookie
0x18002ed47  xor     rax, rsp
0x18002ed4a  mov     [rbp+210h+var_50], rax
0x18002ed51  xor     edi, edi
0x18002ed53  xorps   xmm1, xmm1
0x18002ed56  xorps   xmm0, xmm0
0x18002ed59  mov     [rsp+310h+Type], edi
0x18002ed5d  xor     eax, eax
0x18002ed5f  mov     [rsp+310h+cbData], edi
0x18002ed63  mov     [rbp+210h+var_290], rax
0x18002ed67  mov     rsi, r9
0x18002ed6a  mov     r15, r8
0x18002ed6d  mov     r13, rdx
0x18002ed70  mov     r12, rcx
0x18002ed73  mov     r14d, edi
0x18002ed76  movups  xmmword ptr [rbp+210h+DestinationString.Length], xmm0
0x18002ed7a  movups  xmmword ptr [rsp+310h+UnicodeString.Length], xmm1
0x18002ed7f  movups  xmmword ptr [rbp+210h+var_288.Length], xmm0
0x18002ed83  movups  [rsp+310h+var_2B0], xmm1
0x18002ed88  movups  [rsp+310h+var_2A0], xmm1
0x18002ed8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed94  lea     rax, WPP_GLOBAL_Control
0x18002ed9b  cmp     rcx, rax
0x18002ed9e  jz      short loc_18002EDB9
0x18002eda0  test    byte ptr [rcx+1Ch], 20h
0x18002eda4  jz      short loc_18002EDB9
0x18002eda6  mov     rcx, [rcx+10h]
0x18002edaa  lea     edx, [rdi+22h]
0x18002edad  lea     r8, WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids
0x18002edb4  call    WPP_SF_
0x18002edb9  xorps   xmm0, xmm0
0x18002edbc  xor     eax, eax
0x18002edbe  movups  xmmword ptr [r15], xmm0
0x18002edc2  movups  xmmword ptr [r15+10h], xmm0
0x18002edc7  mov     [r15+20h], rax
0x18002edcb  movups  xmmword ptr [r13+0], xmm0
0x18002edd0  jmp     short loc_18002EDE7
0x18002edd2  test    ebx, ebx
0x18002edd4  jnz     loc_18002F162
0x18002edda  cmp     [rsp+310h+Type], 1
0x18002eddf  jz      loc_18002EEBB
0x18002ede5  inc     dword ptr [rsi]
0x18002ede7  mov     r8d, 20Ah; Size
0x18002eded  lea     rcx, [rbp+210h+ValueName]; void *
0x18002edf1  xor     edx, edx; Val
0x18002edf3  call    memset_0
0x18002edf8  mov     edx, [rsi]; dwIndex
0x18002edfa  lea     rax, [rsp+310h+cbData]
0x18002edff  mov     [rsp+310h+lpcbData], rax; lpcbData
0x18002ee04  lea     r9, [rsp+310h+cchValueName]; lpcchValueName
0x18002ee09  lea     rax, [rsp+310h+Type]
0x18002ee0e  mov     [rsp+310h+lpData], rdi; lpData
0x18002ee13  mov     [rsp+310h+lpType], rax; lpType
0x18002ee18  lea     r8, [rbp+210h+ValueName]; lpValueName
0x18002ee1c  mov     rcx, r12; hKey
0x18002ee1f  mov     [rsp+310h+lpReserved], rdi; lpReserved
0x18002ee24  mov     [rsp+310h+cchValueName], 105h
0x18002ee2c  call    cs:__imp_RegEnumValueW
0x18002ee33  nop     dword ptr [rax+rax+00h]
0x18002ee38  mov     ebx, eax
0x18002ee3a  cmp     eax, 103h
0x18002ee3f  jnz     short loc_18002EDD2
0x18002ee41  lea     rsi, WPP_GLOBAL_Control
0x18002ee48  mov     rcx, r14; lpMem
0x18002ee4b  call    ?KpsFreeMem@@YAXPEAX@Z; KpsFreeMem(void *)
0x18002ee50  lea     rcx, [rsp+310h+var_2B0]; struct _KPS_MIT_REALM *
0x18002ee55  call    ?KpsFreeMitRealm@@YAXPEAU_KPS_MIT_REALM@@@Z; KpsFreeMitRealm(_KPS_MIT_REALM *)
0x18002ee5a  lea     rcx, [rsp+310h+UnicodeString]; UnicodeString
0x18002ee5f  call    cs:__imp_RtlFreeUnicodeString
0x18002ee66  nop     dword ptr [rax+rax+00h]
0x18002ee6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee72  cmp     rcx, rsi
0x18002ee75  jz      short loc_18002EE95
0x18002ee77  test    byte ptr [rcx+1Ch], 20h
0x18002ee7b  jz      short loc_18002EE95
0x18002ee7d  mov     rcx, [rcx+10h]
0x18002ee81  lea     r8, WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids
0x18002ee88  mov     edx, 2Ah ; '*'
0x18002ee8d  mov     r9d, ebx
0x18002ee90  call    WPP_SF_D
0x18002ee95  mov     eax, ebx
0x18002ee97  mov     rcx, [rbp+210h+var_50]
0x18002ee9e  xor     rcx, rsp; StackCookie
0x18002eea1  call    __security_check_cookie
0x18002eea6  add     rsp, 2D8h
0x18002eead  pop     r15
0x18002eeaf  pop     r14
0x18002eeb1  pop     r13
0x18002eeb3  pop     r12
0x18002eeb5  pop     rdi
0x18002eeb6  pop     rsi
0x18002eeb7  pop     rbx
0x18002eeb8  pop     rbp
0x18002eeb9  retn
0x18002eebb  mov     edi, [rsp+310h+cbData]
0x18002eebf  test    dil, 1
0x18002eec3  jnz     loc_18002F11B
0x18002eec9  cmp     edi, 0FFFDh
0x18002eecf  ja      loc_18002F11B
0x18002eed5  lea     rdx, [rbp+210h+ValueName]; SourceString
0x18002eed9  add     di, 2
0x18002eedd  lea     rcx, [rbp+210h+DestinationString]; DestinationString
0x18002eee1  call    cs:__imp_RtlInitUnicodeString
0x18002eee8  nop     dword ptr [rax+rax+00h]
0x18002eeed  lea     r8, [rsp+310h+UnicodeString]; DestinationString
0x18002eef2  mov     ecx, 1; Flags
0x18002eef7  lea     rdx, [rbp+210h+DestinationString]; SourceString
0x18002eefb  call    cs:__imp_RtlDuplicateUnicodeString
0x18002ef02  nop     dword ptr [rax+rax+00h]
0x18002ef07  mov     ebx, eax
0x18002ef09  test    eax, eax
0x18002ef0b  jz      short loc_18002EF4B
0x18002ef0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef14  lea     rsi, WPP_GLOBAL_Control
0x18002ef1b  cmp     rcx, rsi
0x18002ef1e  jz      loc_18002EE48
0x18002ef24  test    byte ptr [rcx+1Ch], 1
0x18002ef28  jz      loc_18002EE48
0x18002ef2e  mov     edx, 25h ; '%'
0x18002ef33  mov     r9d, eax
0x18002ef36  mov     rcx, [rcx+10h]
0x18002ef3a  lea     r8, WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids
0x18002ef41  call    WPP_SF_D
0x18002ef46  jmp     loc_18002EE48
0x18002ef4b  movzx   edi, di
0x18002ef4e  mov     ecx, edi; unsigned __int64
0x18002ef50  call    ?KpsAllocMem@@YAPEAX_K@Z; KpsAllocMem(unsigned __int64)
0x18002ef55  mov     r14, rax
0x18002ef58  test    rax, rax
0x18002ef5b  jnz     short loc_18002EF89
0x18002ef5d  lea     ebx, [rax+8]
0x18002ef60  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef67  lea     rsi, WPP_GLOBAL_Control
0x18002ef6e  cmp     rcx, rsi
0x18002ef71  jz      loc_18002EE48
0x18002ef77  test    byte ptr [rcx+1Ch], 1
0x18002ef7b  jz      loc_18002EE48
0x18002ef81  lea     edx, [rax+26h]
0x18002ef84  mov     r9d, ebx
0x18002ef87  jmp     short loc_18002EF36
0x18002ef89  mov     edx, [rsi]; dwIndex
0x18002ef8b  lea     rax, [rsp+310h+cbData]
0x18002ef90  mov     [rsp+310h+lpcbData], rax; lpcbData
0x18002ef95  lea     r9, [rsp+310h+cchValueName]; lpcchValueName
0x18002ef9a  lea     rax, [rsp+310h+Type]
0x18002ef9f  mov     [rsp+310h+lpData], r14; lpData
0x18002efa4  mov     [rsp+310h+lpType], rax; lpType
0x18002efa9  lea     r8, [rbp+210h+ValueName]; lpValueName
0x18002efad  and     [rsp+310h+lpReserved], 0
0x18002efb3  mov     rcx, r12; hKey
0x18002efb6  mov     [rsp+310h+cchValueName], 105h
0x18002efbe  call    cs:__imp_RegEnumValueW
0x18002efc5  nop     dword ptr [rax+rax+00h]
0x18002efca  xor     r12d, r12d
0x18002efcd  mov     ebx, eax
0x18002efcf  test    eax, eax
0x18002efd1  jz      short loc_18002EFFE
0x18002efd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002efda  lea     rsi, WPP_GLOBAL_Control
0x18002efe1  cmp     rcx, rsi
0x18002efe4  jz      loc_18002EE48
0x18002efea  test    byte ptr [rcx+1Ch], 1
0x18002efee  jz      loc_18002EE48
0x18002eff4  lea     edx, [r12+27h]
0x18002eff9  jmp     loc_18002EF33
0x18002effe  mov     r9d, [rsp+310h+cbData]
0x18002f003  test    r9b, 1
0x18002f007  jnz     loc_18002F0D7
0x18002f00d  lea     rax, [rdi-2]
0x18002f011  mov     ecx, r9d
0x18002f014  cmp     r9, rax
0x18002f017  ja      loc_18002F0D7
0x18002f01d  shr     rcx, 1
0x18002f020  mov     rdx, r14; SourceString
0x18002f023  mov     [r14+rcx*2], r12w
0x18002f028  lea     rcx, [rbp+210h+var_288]; DestinationString
0x18002f02c  call    cs:__imp_RtlInitUnicodeString
0x18002f033  nop     dword ptr [rax+rax+00h]
0x18002f038  lea     rdx, [rsp+310h+var_2B0]; struct _KPS_MIT_REALM *
0x18002f03d  lea     rcx, [rbp+210h+var_288]; struct _UNICODE_STRING *
0x18002f041  call    ?KpsParseMitRealmSettings@@YAKPEAU_UNICODE_STRING@@PEAU_KPS_MIT_REALM@@@Z; KpsParseMitRealmSettings(_UNICODE_STRING *,_KPS_MIT_REALM *)
0x18002f046  mov     ebx, eax
0x18002f048  test    eax, eax
0x18002f04a  jz      short loc_18002F08C
0x18002f04c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f053  lea     rsi, WPP_GLOBAL_Control
0x18002f05a  cmp     rcx, rsi
0x18002f05d  jz      loc_18002EE48
0x18002f063  test    byte ptr [rcx+1Ch], 1
0x18002f067  jz      loc_18002EE48
0x18002f06d  mov     rcx, [rcx+10h]
0x18002f071  lea     rax, [rbp+210h+var_288]
0x18002f075  mov     edx, 29h ; ')'
0x18002f07a  mov     [rsp+310h+lpReserved], rax
0x18002f07f  mov     r9d, ebx
0x18002f082  call    WPP_SF_DZ
0x18002f087  jmp     loc_18002EE48
0x18002f08c  movups  xmm0, xmmword ptr [rsp+310h+UnicodeString.Length]
0x18002f091  xor     eax, eax
0x18002f093  xorps   xmm1, xmm1
0x18002f096  movdqu  xmmword ptr [r13+0], xmm0
0x18002f09c  movups  xmm0, [rsp+310h+var_2B0]
0x18002f0a1  movups  xmmword ptr [rsp+310h+UnicodeString.Length], xmm1
0x18002f0a6  movups  xmm1, [rsp+310h+var_2A0]
0x18002f0ab  movups  xmmword ptr [r15], xmm0
0x18002f0af  movsd   xmm0, [rbp+210h+var_290]
0x18002f0b4  movups  xmmword ptr [r15+10h], xmm1
0x18002f0b9  mov     [rbp+210h+var_290], rax
0x18002f0bd  xorps   xmm1, xmm1
0x18002f0c0  movsd   qword ptr [r15+20h], xmm0
0x18002f0c6  inc     dword ptr [rsi]
0x18002f0c8  movups  [rsp+310h+var_2B0], xmm1
0x18002f0cd  movups  [rsp+310h+var_2A0], xmm1
0x18002f0d2  jmp     loc_18002EE41
0x18002f0d7  mov     eax, 57h ; 'W'
0x18002f0dc  mov     ebx, eax
0x18002f0de  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f0e5  lea     rsi, WPP_GLOBAL_Control
0x18002f0ec  cmp     rcx, rsi
0x18002f0ef  jz      loc_18002EE48
0x18002f0f5  test    byte ptr [rcx+1Ch], 1
0x18002f0f9  jz      loc_18002EE48
0x18002f0ff  mov     rcx, [rcx+10h]
0x18002f103  lea     edx, [rax-2Fh]
0x18002f106  lea     r8, WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids
0x18002f10d  mov     dword ptr [rsp+310h+lpReserved], eax
0x18002f111  call    WPP_SF_dD
0x18002f116  jmp     loc_18002EE48
0x18002f11b  mov     eax, 57h ; 'W'
0x18002f120  mov     ebx, eax
0x18002f122  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f129  lea     rsi, WPP_GLOBAL_Control
0x18002f130  cmp     rcx, rsi
0x18002f133  jz      loc_18002EE48
0x18002f139  test    byte ptr [rcx+1Ch], 1
0x18002f13d  jz      loc_18002EE48
0x18002f143  mov     rcx, [rcx+10h]
0x18002f147  lea     edx, [rax-33h]
0x18002f14a  mov     r9d, edi
0x18002f14d  mov     dword ptr [rsp+310h+lpReserved], eax
0x18002f151  lea     r8, WPP_7f8013e68bb4352abd7d18e77413a56c_Traceguids
0x18002f158  call    WPP_SF_dD
0x18002f15d  jmp     loc_18002EE48
0x18002f162  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f169  lea     rsi, WPP_GLOBAL_Control
0x18002f170  cmp     rcx, rsi
0x18002f173  jz      loc_18002EE48
0x18002f179  test    byte ptr [rcx+1Ch], 1
0x18002f17d  jz      loc_18002EE48
0x18002f183  mov     edx, 23h ; '#'
0x18002f188  jmp     loc_18002EF84
```
