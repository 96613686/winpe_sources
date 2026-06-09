# LPA::Lui::ValidateClient(LPALUICLIENTMODE,void *,void *)

- ea: `0x1800ce810`
- end: `0x1800cea16`
- name: `?ValidateClient@Lui@LPA@@SAJW4LPALUICLIENTMODE@@PEAX1@Z`
- size: `518`
- prototype: `static int __high(enum LPALUICLIENTMODE, void *, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800eff70`

## callees

- `0x18000df90`
- `0x18000ebf4`
- `0x18006ba8c`
- `0x1800974e0`
- `0x1800ce378`
- `0x1800ce410`
- `0x1800ce810`
- `0x1800cea1c`
- `0x1800cead0`
- `0x1800cebf8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800ce8d5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800ce962`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800ce8d5`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800ce962`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ce905`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ce98c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ce905`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800ce98c`

## pseudocode

```c
__int64 __fastcall LPA::Lui::ValidateClient(int a1, void *a2, void *a3)
{
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  __int64 result; // rax
  const unsigned __int16 *v10; // rdx
  CommonUtil *v11; // rcx
  CommonUtil *v12; // rcx
  CommonUtil *v13; // rcx
  CommonUtil *v14; // rcx
  WINBOOL IsMember; // [rsp+20h] [rbp-79h] BYREF
  DWORD cbSid[3]; // [rsp+24h] [rbp-75h] BYREF
  _BYTE pSid[80]; // [rsp+30h] [rbp-69h] BYREF
  _BYTE SidToCheck[80]; // [rsp+80h] [rbp-19h] BYREF

  if ( !a1 )
  {
    result = LPA::Lui::ValidateAppContainerSid(
               a2,
               L"S-1-15-2-155514346-2573954481-755741238-1654018636-1233331829-3075935687-2861478708");
    if ( (int)result >= 0 )
      return result;
    result = LPA::Lui::ValidateAppContainerSid(
               a2,
               L"S-1-15-2-3083765670-2301828090-3288705196-2597965991-2057664196-4044987863-2761340229");
    if ( (int)result >= 0 )
      return result;
    return LPA::Lui::ValidateClientSignedByMicrosoft(a3);
  }
  v5 = a1 - 1;
  if ( !v5 )
  {
LABEL_13:
    memset_0(pSid, 0, 0x44u);
    cbSid[0] = 68;
    if ( CreateWellKnownSid(WinLocalSystemSid, 0, pSid, cbSid)
      || (result = CommonUtil::GetLastErrorToHResultAndForceFailure(v11), (int)result >= 0) )
    {
      if ( a2 )
      {
        IsMember = 0;
        if ( CheckTokenMembership(a2, pSid, &IsMember) )
        {
          result = 0;
          if ( !IsMember )
            result = 2147942405LL;
        }
        else
        {
          result = CommonUtil::GetLastErrorToHResultAndForceFailure(v12);
        }
        if ( (int)result >= 0 )
        {
          result = LPA::Lui::ValidateClientSignedByMicrosoft(a3);
          if ( (int)result < 0 )
            result = LPA::Lui::ValidateEmbeddedModeEnabled();
        }
      }
      else
      {
        result = 2147942405LL;
      }
    }
    if ( (_DWORD)result == -2147024891 )
    {
      memset_0(SidToCheck, 0, 0x44u);
      cbSid[0] = 68;
      if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, SidToCheck, cbSid)
        || (result = CommonUtil::GetLastErrorToHResultAndForceFailure(v13), (int)result >= 0) )
      {
        if ( a2 )
        {
          IsMember = 0;
          if ( CheckTokenMembership(a2, SidToCheck, &IsMember) )
          {
            result = 0;
            if ( !IsMember )
              result = 2147942405LL;
          }
          else
          {
            result = CommonUtil::GetLastErrorToHResultAndForceFailure(v14);
          }
          if ( (int)result >= 0 )
          {
            result = LPA::Lui::ValidateClientSignedByMicrosoft(a3);
            if ( (int)result < 0 )
              return LPA::Lui::ValidateEmbeddedModeEnabled();
          }
        }
        else
        {
          return 2147942405LL;
        }
      }
    }
    return result;
  }
  v6 = v5 - 1;
  if ( !v6 )
    return LPA::Lui::ValidateAppContainerSid(
             a2,
             L"S-1-15-2-3784866113-3187381476-3433752343-3391928953-3760210436-1684329488-1912184601");
  v7 = v6 - 1;
  if ( !v7 )
    return LPA::Lui::ValidateAppContainerCapability(a2, (const unsigned __int16 *)a2);
  v8 = v7 - 1;
  if ( v8 )
  {
    if ( v8 != 1 )
      return 2147942487LL;
    goto LABEL_13;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_ECMC>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NetworkUX_ECMC>::GetImpl'::`2'::impl) )
    return 2147942487LL;
  result = LPA::Lui::ValidateOwnerUserSid(a2, v10);
  if ( (int)result >= 0 )
    return LPA::Lui::ValidateClientSignedByMicrosoft(a3);
  return result;
}

```

## disassembly

```asm
0x1800ce810  mov     [rsp-8+arg_0], rbx
0x1800ce815  mov     [rsp-8+arg_18], rdi
0x1800ce81a  push    rbp
0x1800ce81b  push    r14
0x1800ce81d  push    r15
0x1800ce81f  lea     rbp, [rsp-47h]
0x1800ce824  sub     rsp, 0E0h
0x1800ce82b  mov     rax, cs:__security_cookie
0x1800ce832  xor     rax, rsp
0x1800ce835  mov     [rbp+57h+var_20], rax
0x1800ce839  mov     rdi, r8
0x1800ce83c  mov     rbx, rdx
0x1800ce83f  test    ecx, ecx
0x1800ce841  jz      loc_1800CE9C3
0x1800ce847  sub     ecx, 1
0x1800ce84a  jz      short loc_1800CE8B0
0x1800ce84c  sub     ecx, 1
0x1800ce84f  jz      short loc_1800CE89C
0x1800ce851  sub     ecx, 1
0x1800ce854  jz      short loc_1800CE88F
0x1800ce856  sub     ecx, 1
0x1800ce859  jz      short loc_1800CE86A
0x1800ce85b  cmp     ecx, 1
0x1800ce85e  jz      short loc_1800CE8B0
0x1800ce860  mov     eax, 80070057h
0x1800ce865  jmp     loc_1800CE9F1
0x1800ce86a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NetworkUX_ECMC@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_ECMC@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_ECMC> `wil::Feature<__WilFeatureTraits_Feature_NetworkUX_ECMC>::GetImpl(void)'::`2'::impl
0x1800ce871  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_ECMC@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_ECMC>::__private_IsEnabled(void)
0x1800ce876  test    al, al
0x1800ce878  jz      short loc_1800CE860
0x1800ce87a  mov     rcx, rbx; TokenHandle
0x1800ce87d  call    ?ValidateOwnerUserSid@Lui@LPA@@CAJPEAXPEBG@Z; LPA::Lui::ValidateOwnerUserSid(void *,ushort const *)
0x1800ce882  test    eax, eax
0x1800ce884  js      loc_1800CE9F1
0x1800ce88a  jmp     loc_1800CE9E9
0x1800ce88f  mov     rcx, rbx; void *
0x1800ce892  call    ?ValidateAppContainerCapability@Lui@LPA@@CAJPEAXPEBG@Z; LPA::Lui::ValidateAppContainerCapability(void *,ushort const *)
0x1800ce897  jmp     loc_1800CE9F1
0x1800ce89c  lea     rdx, aS1152378486611; "S-1-15-2-3784866113-3187381476-34337523"...
0x1800ce8a3  mov     rcx, rbx; TokenHandle
0x1800ce8a6  call    ?ValidateAppContainerSid@Lui@LPA@@CAJPEAXPEBG@Z; LPA::Lui::ValidateAppContainerSid(void *,ushort const *)
0x1800ce8ab  jmp     loc_1800CE9F1
0x1800ce8b0  mov     r15d, 44h ; 'D'
0x1800ce8b6  lea     rcx, [rbp+57h+pSid]; void *
0x1800ce8ba  mov     r8d, r15d; Size
0x1800ce8bd  xor     edx, edx; Val
0x1800ce8bf  call    memset_0
0x1800ce8c4  xor     edx, edx; DomainSid
0x1800ce8c6  mov     [rbp+57h+cbSid], r15d
0x1800ce8ca  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800ce8ce  lea     r8, [rbp+57h+pSid]; pSid
0x1800ce8d2  lea     ecx, [rdx+16h]; WellKnownSidType
0x1800ce8d5  call    cs:__imp_CreateWellKnownSid
0x1800ce8db  mov     r14d, 80070005h
0x1800ce8e1  test    eax, eax
0x1800ce8e3  jnz     short loc_1800CE8EE
0x1800ce8e5  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ce8ea  test    eax, eax
0x1800ce8ec  js      short loc_1800CE93A
0x1800ce8ee  test    rbx, rbx
0x1800ce8f1  jz      short loc_1800CE937
0x1800ce8f3  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800ce8f7  mov     [rbp+57h+IsMember], 0
0x1800ce8fe  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x1800ce902  mov     rcx, rbx; TokenHandle
0x1800ce905  call    cs:__imp_CheckTokenMembership
0x1800ce90b  test    eax, eax
0x1800ce90d  jnz     short loc_1800CE916
0x1800ce90f  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ce914  jmp     short loc_1800CE920
0x1800ce916  xor     eax, eax
0x1800ce918  cmp     [rbp+57h+IsMember], eax
0x1800ce91b  jnz     short loc_1800CE920
0x1800ce91d  mov     eax, r14d
0x1800ce920  test    eax, eax
0x1800ce922  js      short loc_1800CE93A
0x1800ce924  mov     rcx, rdi; hProcess
0x1800ce927  call    ?ValidateClientSignedByMicrosoft@Lui@LPA@@CAJPEAX@Z; LPA::Lui::ValidateClientSignedByMicrosoft(void *)
0x1800ce92c  test    eax, eax
0x1800ce92e  jns     short loc_1800CE93A
0x1800ce930  call    ?ValidateEmbeddedModeEnabled@Lui@LPA@@CAJXZ; LPA::Lui::ValidateEmbeddedModeEnabled(void)
0x1800ce935  jmp     short loc_1800CE93A
0x1800ce937  mov     eax, r14d
0x1800ce93a  cmp     eax, r14d
0x1800ce93d  jnz     loc_1800CE9F1
0x1800ce943  mov     r8, r15; Size
0x1800ce946  lea     rcx, [rbp+57h+SidToCheck]; void *
0x1800ce94a  xor     edx, edx; Val
0x1800ce94c  call    memset_0
0x1800ce951  xor     edx, edx; DomainSid
0x1800ce953  mov     [rbp+57h+cbSid], r15d
0x1800ce957  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800ce95b  lea     r8, [rbp+57h+SidToCheck]; pSid
0x1800ce95f  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800ce962  call    cs:__imp_CreateWellKnownSid
0x1800ce968  test    eax, eax
0x1800ce96a  jnz     short loc_1800CE975
0x1800ce96c  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ce971  test    eax, eax
0x1800ce973  js      short loc_1800CE9F1
0x1800ce975  test    rbx, rbx
0x1800ce978  jz      short loc_1800CE9BE
0x1800ce97a  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800ce97e  mov     [rbp+57h+IsMember], 0
0x1800ce985  lea     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1800ce989  mov     rcx, rbx; TokenHandle
0x1800ce98c  call    cs:__imp_CheckTokenMembership
0x1800ce992  test    eax, eax
0x1800ce994  jnz     short loc_1800CE99D
0x1800ce996  call    ?GetLastErrorToHResultAndForceFailure@CommonUtil@@YAJXZ; CommonUtil::GetLastErrorToHResultAndForceFailure(void)
0x1800ce99b  jmp     short loc_1800CE9A7
0x1800ce99d  xor     eax, eax
0x1800ce99f  cmp     [rbp+57h+IsMember], eax
0x1800ce9a2  jnz     short loc_1800CE9A7
0x1800ce9a4  mov     eax, r14d
0x1800ce9a7  test    eax, eax
0x1800ce9a9  js      short loc_1800CE9F1
0x1800ce9ab  mov     rcx, rdi; hProcess
0x1800ce9ae  call    ?ValidateClientSignedByMicrosoft@Lui@LPA@@CAJPEAX@Z; LPA::Lui::ValidateClientSignedByMicrosoft(void *)
0x1800ce9b3  test    eax, eax
0x1800ce9b5  jns     short loc_1800CE9F1
0x1800ce9b7  call    ?ValidateEmbeddedModeEnabled@Lui@LPA@@CAJXZ; LPA::Lui::ValidateEmbeddedModeEnabled(void)
0x1800ce9bc  jmp     short loc_1800CE9F1
0x1800ce9be  mov     eax, r14d
0x1800ce9c1  jmp     short loc_1800CE9F1
0x1800ce9c3  lea     rdx, aS1152155514346; "S-1-15-2-155514346-2573954481-755741238"...
0x1800ce9ca  mov     rcx, rbx; TokenHandle
0x1800ce9cd  call    ?ValidateAppContainerSid@Lui@LPA@@CAJPEAXPEBG@Z; LPA::Lui::ValidateAppContainerSid(void *,ushort const *)
0x1800ce9d2  test    eax, eax
0x1800ce9d4  jns     short loc_1800CE9F1
0x1800ce9d6  lea     rdx, aS1152308376567; "S-1-15-2-3083765670-2301828090-32887051"...
0x1800ce9dd  mov     rcx, rbx; TokenHandle
0x1800ce9e0  call    ?ValidateAppContainerSid@Lui@LPA@@CAJPEAXPEBG@Z; LPA::Lui::ValidateAppContainerSid(void *,ushort const *)
0x1800ce9e5  test    eax, eax
0x1800ce9e7  jns     short loc_1800CE9F1
0x1800ce9e9  mov     rcx, rdi; hProcess
0x1800ce9ec  call    ?ValidateClientSignedByMicrosoft@Lui@LPA@@CAJPEAX@Z; LPA::Lui::ValidateClientSignedByMicrosoft(void *)
0x1800ce9f1  mov     rcx, [rbp+57h+var_20]
0x1800ce9f5  xor     rcx, rsp; StackCookie
0x1800ce9f8  call    __security_check_cookie
0x1800ce9fd  lea     r11, [rsp+0F0h+var_10]
0x1800cea05  mov     rbx, [r11+20h]
0x1800cea09  mov     rdi, [r11+38h]
0x1800cea0d  mov     rsp, r11
0x1800cea10  pop     r15
0x1800cea12  pop     r14
0x1800cea14  pop     rbp
0x1800cea15  retn
```
