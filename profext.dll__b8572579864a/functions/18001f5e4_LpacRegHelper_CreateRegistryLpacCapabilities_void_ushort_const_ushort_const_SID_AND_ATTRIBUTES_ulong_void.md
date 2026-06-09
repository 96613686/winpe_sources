# LpacRegHelper::CreateRegistryLpacCapabilities(void *,ushort const *,ushort const *,_SID_AND_ATTRIBUTES *,ulong,void *)

- ea: `0x18001f5e4`
- end: `0x18001f7a7`
- name: `?CreateRegistryLpacCapabilities@LpacRegHelper@@CAJPEAXPEBG1PEAU_SID_AND_ATTRIBUTES@@K0@Z`
- size: `451`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, const unsigned __int16 *, struct _SID_AND_ATTRIBUTES *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f390`

## callees

- `0x180004594`
- `0x18000a4d8`
- `0x18000a740`
- `0x18000aacc`
- `0x18000c7d4`
- `0x18000f864`
- `0x18001f5e4`
- `0x18001f7b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001f714`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001f714`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001f6dd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001f6dd`

## string_xrefs

- `0x18001f613`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001f686`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001f771`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`
- `0x18001f788`: `onecore\ds\security\gina\profile\profext\lpacreghelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LpacRegHelper::CreateRegistryLpacCapabilities(
        void *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _SID_AND_ATTRIBUTES *a4,
        unsigned int a5,
        void *a6)
{
  __int64 v9; // rdx
  unsigned int LastError; // ebx
  unsigned __int64 v11; // rdi
  void *v12; // rbx
  HKEY *v13; // rax
  void *v14; // rcx
  int RegistryLpacFlex; // eax
  __int64 v16; // rsi
  const char *v17; // r9
  LSTATUS v18; // eax
  const unsigned __int16 *lpData; // [rsp+20h] [rbp-20h]
  int lpDataa; // [rsp+20h] [rbp-20h]
  int lpDatab; // [rsp+20h] [rbp-20h]
  HKEY hKey[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  void *Data; // [rsp+70h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+78h] [rbp+38h] BYREF

  Data = a1;
  if ( !a2 )
  {
    v9 = 71;
LABEL_3:
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)0x80070057LL,
      (int)lpData);
    return LastError;
  }
  if ( !a3 )
  {
    v9 = 72;
    goto LABEL_3;
  }
  v11 = a5;
  if ( a5 && !a4 )
  {
    v9 = 73;
    goto LABEL_3;
  }
  v12 = a6;
  if ( !a6 )
  {
    v9 = 74;
    goto LABEL_3;
  }
  hKey[0] = 0;
  v13 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKey);
  RegistryLpacFlex = LpacRegHelper::CreateRegistryLpacFlex(v14, a2, a3, v12, lpData, v13);
  LastError = RegistryLpacFlex;
  if ( RegistryLpacFlex >= 0 )
  {
    if ( a4 && (_DWORD)v11 )
    {
      v16 = 0;
      while ( 1 )
      {
        StringSid = 0;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &StringSid,
          0);
        if ( !ConvertSidToStringSidW(a4[v16].Sid, &StringSid) )
          break;
        LODWORD(Data) = a4[v16].Attributes;
        v18 = RegSetKeyValueW(hKey[0], 0, StringSid, 4u, &Data, 4u);
        LastError = v18;
        if ( v18 > 0 )
          LastError = (unsigned __int16)v18 | 0x80070000;
        if ( (LastError & 0x80000000) != 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x67,
            (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
            (const char *)LastError,
            lpDatab);
          goto LABEL_26;
        }
        wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&StringSid);
        if ( ++v16 >= v11 )
          goto LABEL_21;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x62,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
                    v17);
LABEL_26:
      wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(&StringSid);
    }
    else
    {
LABEL_21:
      LastError = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\lpacreghelper.cpp",
      (const char *)(unsigned int)RegistryLpacFlex,
      lpDataa);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return LastError;
}

```

## disassembly

```asm
0x18001f5e4  mov     [rsp-28h+arg_10], rbx
0x18001f5e9  mov     [rsp-28h+Data], rcx
0x18001f5ee  push    rbp
0x18001f5ef  push    rsi
0x18001f5f0  push    rdi
0x18001f5f1  push    r14
0x18001f5f3  push    r15
0x18001f5f5  mov     rbp, rsp
0x18001f5f8  sub     rsp, 40h
0x18001f5fc  mov     r14, r9
0x18001f5ff  mov     rsi, r8
0x18001f602  mov     r15, rdx
0x18001f605  test    rdx, rdx
0x18001f608  jnz     short loc_18001F62B
0x18001f60a  lea     edx, [r15+47h]; void *
0x18001f60e  mov     ebx, 80070057h
0x18001f613  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001f61a  mov     r9d, ebx; char *
0x18001f61d  mov     rcx, [rbp+28h]; this
0x18001f621  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f626  jmp     loc_18001F753
0x18001f62b  test    rsi, rsi
0x18001f62e  jnz     short loc_18001F635
0x18001f630  lea     edx, [rsi+48h]
0x18001f633  jmp     short loc_18001F60E
0x18001f635  mov     edi, [rbp+arg_20]
0x18001f638  test    edi, edi
0x18001f63a  jz      short loc_18001F647
0x18001f63c  test    r14, r14
0x18001f63f  jnz     short loc_18001F647
0x18001f641  lea     edx, [r14+49h]
0x18001f645  jmp     short loc_18001F60E
0x18001f647  mov     rbx, [rbp+arg_28]
0x18001f64b  test    rbx, rbx
0x18001f64e  jnz     short loc_18001F655
0x18001f650  lea     edx, [rbx+4Ah]
0x18001f653  jmp     short loc_18001F60E
0x18001f655  mov     [rbp+hKey], 0
0x18001f65d  lea     rcx, [rbp+hKey]
0x18001f661  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18001f666  mov     qword ptr [rsp+40h+cbData], rax; HKEY *
0x18001f66b  mov     r9, rbx; void *
0x18001f66e  mov     r8, rsi; unsigned __int16 *
0x18001f671  mov     rdx, r15; unsigned __int16 *
0x18001f674  call    ?CreateRegistryLpacFlex@LpacRegHelper@@CAJPEAXPEBG101PEAPEAUHKEY__@@@Z; LpacRegHelper::CreateRegistryLpacFlex(void *,ushort const *,ushort const *,void *,ushort const *,HKEY__ * *)
0x18001f679  mov     ebx, eax
0x18001f67b  test    eax, eax
0x18001f67d  jns     short loc_18001F69C
0x18001f67f  mov     rcx, [rbp+28h]; this
0x18001f683  mov     r9d, eax; char *
0x18001f686  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001f68d  mov     edx, 54h ; 'T'; void *
0x18001f692  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f697  jmp     loc_18001F74A
0x18001f69c  test    r14, r14
0x18001f69f  jz      loc_18001F748
0x18001f6a5  test    edi, edi
0x18001f6a7  jz      loc_18001F748
0x18001f6ad  xor     esi, esi
0x18001f6af  test    rdi, rdi
0x18001f6b2  jz      loc_18001F748
0x18001f6b8  lea     r15d, [rsi+4]
0x18001f6bc  mov     [rbp+StringSid], 0
0x18001f6c4  xor     edx, edx
0x18001f6c6  lea     rcx, [rbp+StringSid]
0x18001f6ca  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001f6cf  mov     rbx, rsi
0x18001f6d2  add     rbx, rbx
0x18001f6d5  lea     rdx, [rbp+StringSid]; StringSid
0x18001f6d9  mov     rcx, [r14+rbx*8]; Sid
0x18001f6dd  call    cs:__imp_ConvertSidToStringSidW
0x18001f6e4  nop     dword ptr [rax+rax+00h]
0x18001f6e9  test    eax, eax
0x18001f6eb  jz      loc_18001F784
0x18001f6f1  mov     eax, [r14+rbx*8+8]
0x18001f6f6  mov     dword ptr [rbp+Data], eax
0x18001f6f9  mov     [rsp+40h+cbData], r15d; cbData
0x18001f6fe  lea     rax, [rbp+Data]
0x18001f702  mov     [rsp+40h+lpData], rax; int
0x18001f707  mov     r9d, r15d; dwType
0x18001f70a  mov     r8, [rbp+StringSid]; lpValueName
0x18001f70e  xor     edx, edx; lpSubKey
0x18001f710  mov     rcx, [rbp+hKey]; hKey
0x18001f714  call    cs:__imp_RegSetKeyValueW
0x18001f71b  nop     dword ptr [rax+rax+00h]
0x18001f720  mov     ebx, eax
0x18001f722  test    eax, eax
0x18001f724  jle     short loc_18001F72F
0x18001f726  movzx   ebx, ax
0x18001f729  or      ebx, 80070000h
0x18001f72f  test    ebx, ebx
0x18001f731  js      short loc_18001F76A
0x18001f733  lea     rcx, [rbp+StringSid]
0x18001f737  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001f73c  inc     rsi
0x18001f73f  cmp     rsi, rdi
0x18001f742  jb      loc_18001F6BC
0x18001f748  xor     ebx, ebx
0x18001f74a  lea     rcx, [rbp+hKey]
0x18001f74e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001f753  mov     eax, ebx
0x18001f755  mov     rbx, [rsp+40h+arg_10]
0x18001f75d  add     rsp, 40h
0x18001f761  pop     r15
0x18001f763  pop     r14
0x18001f765  pop     rdi
0x18001f766  pop     rsi
0x18001f767  pop     rbp
0x18001f768  retn
0x18001f76a  mov     rcx, [rbp+28h]; this
0x18001f76e  mov     r9d, ebx; char *
0x18001f771  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001f778  mov     edx, 67h ; 'g'; void *
0x18001f77d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f782  jmp     short loc_18001F79B
0x18001f784  mov     rcx, [rbp+28h]; this
0x18001f788  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001f78f  mov     edx, 62h ; 'b'; void *
0x18001f794  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f799  mov     ebx, eax
0x18001f79b  lea     rcx, [rbp+StringSid]
0x18001f79f  call    ??1?$unique_storage@U?$resource_policy@PEAU_PROC_THREAD_ATTRIBUTE_LIST@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_PROC_THREAD_ATTRIBUTE_LIST *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_PROC_THREAD_ATTRIBUTE_LIST *,_PROC_THREAD_ATTRIBUTE_LIST *,0,std::nullptr_t>>(void)
0x18001f7a4  jmp     short loc_18001F74A
```
