# AggregateSets(void *,HKEY__ *,CGenericList<CAggregateMarshaler> *,IUnknown *)

- ea: `0x18000aaac`
- end: `0x18000ae21`
- name: `?AggregateSets@@YAJPEAXPEAUHKEY__@@PEAV?$CGenericList@VCAggregateMarshaler@@@@PEAUIUnknown@@@Z`
- size: `885`
- prototype: `__int64 __fastcall(HANDLE hFile, HKEY hKey, CBaseList *this, IUnknown *)`
- caller_count: `8`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x1800196f0`
- `0x18001aaf0`
- `0x180026de0`
- `0x1800275c0`
- `0x180028584`
- `0x180029ad0`
- `0x18002b6e0`
- `0x180030890`

## callees

- `0x180003d60`
- `0x18000aaac`
- `0x18000ae28`
- `0x18000b290`
- `0x18000b2e4`
- `0x18001f1c4`
- `0x18001f1d0`
- `0x18001f620`
- `0x180045010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000ac83`
- `ADVAPI32!RegQueryValueExW` at `0x18000ad48`
- `ADVAPI32!RegQueryValueExW` at `0x18000ac83`
- `ADVAPI32!RegQueryValueExW` at `0x18000ad48`
- `ADVAPI32!RegCloseKey` at `0x18000abf5`
- `ADVAPI32!RegCloseKey` at `0x18000ac95`
- `ADVAPI32!RegCloseKey` at `0x18000ad93`
- `ADVAPI32!RegCloseKey` at `0x18000addc`
- `ADVAPI32!RegCloseKey` at `0x18000abf5`
- `ADVAPI32!RegCloseKey` at `0x18000ac95`
- `ADVAPI32!RegCloseKey` at `0x18000ad93`
- `ADVAPI32!RegCloseKey` at `0x18000addc`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ab29`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ab66`
- `ADVAPI32!RegOpenKeyExW` at `0x18000abda`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ab29`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ab66`
- `ADVAPI32!RegOpenKeyExW` at `0x18000abda`
- `ole32!StringFromGUID2` at `0x18000aba7`
- `ole32!StringFromGUID2` at `0x18000ad71`
- `ole32!StringFromGUID2` at `0x18000aba7`
- `ole32!StringFromGUID2` at `0x18000ad71`

## pseudocode

```c
__int64 __fastcall AggregateSets(HANDLE hFile, HKEY hKey, CBaseList *this, IUnknown *a4)
{
  unsigned __int64 v7; // rdx
  HKEY v8; // r15
  DWORD v9; // edi
  GUID *v10; // r12
  unsigned __int64 v11; // rdx
  CBaseList::CNode *v12; // rdx
  _QWORD **v13; // rbx
  CBaseList::CNode *v14; // rdi
  LSTATUS v16; // ebx
  _OWORD *v17; // rax
  IUnknown *v18; // r8
  CBaseList::CNode *m_pFirst; // rdx
  _QWORD **m_pObject; // rbx
  CBaseList::CNode *m_pNext; // rdi
  DWORD cbData; // [rsp+30h] [rbp-79h] BYREF
  HKEY v23; // [rsp+38h] [rbp-71h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-69h] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-61h] BYREF
  LPUNKNOWN pUnkOuter; // [rsp+50h] [rbp-59h]
  BYTE Data[16]; // [rsp+58h] [rbp-51h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-39h] BYREF

  pUnkOuter = a4;
  cbData = 0;
  v23 = 0;
  hKeya = 0;
  phkResult = 0;
  NotifyStaticAggregates(this);
  CollectAllSets(hFile, (struct _GUID **)&v23, &cbData);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\MediaInterfaces", 0, 0x20019u, &hKeya) )
  {
    if ( v23 )
      operator delete(v23, v7);
    goto LABEL_22;
  }
  v8 = v23;
  if ( !v23 )
  {
    RegCloseKey(hKeya);
LABEL_22:
    m_pFirst = this->m_pFirst;
    if ( this->m_pFirst )
    {
      do
      {
        m_pObject = (_QWORD **)m_pFirst->m_pObject;
        m_pNext = m_pFirst->m_pNext;
        if ( *((_DWORD *)m_pObject + 12) && !*((_DWORD *)m_pObject + 13) )
        {
          CBaseList::RemoveI(this, m_pFirst);
          (*(void (__fastcall **)(_QWORD *))(*m_pObject[4] + 16LL))(m_pObject[4]);
          operator delete(m_pObject, 0x38u);
        }
        m_pFirst = m_pNext;
      }
      while ( m_pNext );
    }
    return 0;
  }
  if ( RegOpenKeyExW(hKey, L"SetAliases", 0, 0x20019u, &phkResult) )
    phkResult = 0;
  v9 = cbData;
  while ( v9 )
  {
    cbData = 0;
    v23 = 0;
    v10 = (GUID *)(v8 + 4 * --v9);
    *(_OWORD *)Data = 0;
    StringFromGUID2(v10, sz, 39);
    if ( phkResult )
    {
      cbData = 16;
      if ( !RegQueryValueExW(phkResult, sz, 0, 0, Data, &cbData) )
      {
        *v10 = *(GUID *)Data;
        StringFromGUID2(v10, sz, 39);
      }
    }
    if ( !RegOpenKeyExW(hKeya, sz, 0, 0x20019u, &v23) )
    {
      cbData = 16;
      v16 = RegQueryValueExW(v23, L"iid", 0, 0, Data, &cbData);
      RegCloseKey(v23);
      if ( v16 )
        *(GUID *)Data = GUID_00000000_0000_0000_0000_000000000000;
      v17 = operator new(0x38u);
      if ( !v17 )
        break;
      v18 = pUnkOuter;
      *v17 = *(_OWORD *)Data;
      v17[1] = *v10;
      AddAggregateObject(this, v17, v18);
    }
  }
  RegCloseKey(hKeya);
  if ( phkResult )
    RegCloseKey(phkResult);
  operator delete(v8, v11);
  v12 = this->m_pFirst;
  if ( this->m_pFirst )
  {
    do
    {
      v13 = (_QWORD **)v12->m_pObject;
      v14 = v12->m_pNext;
      if ( *((_DWORD *)v13 + 12) && !*((_DWORD *)v13 + 13) )
      {
        CBaseList::RemoveI(this, v12);
        (*(void (__fastcall **)(_QWORD *))(*v13[4] + 16LL))(v13[4]);
        operator delete(v13, 0x38u);
      }
      v12 = v14;
    }
    while ( v14 );
  }
  return 0;
}

```

## disassembly

```asm
0x18000aaac  push    rbp
0x18000aaae  push    rbx
0x18000aaaf  push    rsi
0x18000aab0  push    rdi
0x18000aab1  push    r12
0x18000aab3  push    r13
0x18000aab5  push    r15
0x18000aab7  lea     rbp, [rsp-27h]
0x18000aabc  sub     rsp, 0D0h
0x18000aac3  mov     rax, cs:__security_cookie
0x18000aaca  xor     rax, rsp
0x18000aacd  mov     [rbp+57h+var_40], rax
0x18000aad1  xor     r12d, r12d
0x18000aad4  mov     [rbp+57h+pUnkOuter], r9
0x18000aad8  mov     rbx, rcx
0x18000aadb  mov     [rbp+57h+cbData], r12d
0x18000aadf  mov     rcx, r8
0x18000aae2  mov     [rbp+57h+var_C8], r12
0x18000aae6  mov     [rbp+57h+hKey], r12
0x18000aaea  mov     rsi, r8
0x18000aaed  mov     [rbp+57h+var_C0], r12
0x18000aaf1  mov     rdi, rdx
0x18000aaf4  call    ?NotifyStaticAggregates@@YAXPEAV?$CGenericList@VCAggregateMarshaler@@@@@Z; NotifyStaticAggregates(CGenericList<CAggregateMarshaler> *)
0x18000aaf9  lea     r8, [rbp+57h+cbData]; unsigned int *
0x18000aafd  mov     rcx, rbx; hFile
0x18000ab00  lea     rdx, [rbp+57h+var_C8]; struct _GUID **
0x18000ab04  call    ?CollectAllSets@@YAJPEAXPEAPEAU_GUID@@PEAK@Z; CollectAllSets(void *,_GUID * *,ulong *)
0x18000ab09  lea     rax, [rbp+57h+hKey]
0x18000ab0d  mov     r9d, 20019h; samDesired
0x18000ab13  xor     r8d, r8d; ulOptions
0x18000ab16  mov     [rsp+100h+phkResult], rax; phkResult
0x18000ab1b  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Med"...
0x18000ab22  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ab29  call    cs:__imp_RegOpenKeyExW
0x18000ab30  nop     dword ptr [rax+rax+00h]
0x18000ab35  test    eax, eax
0x18000ab37  jnz     loc_18000ACEC
0x18000ab3d  mov     r15, [rbp+57h+var_C8]
0x18000ab41  test    r15, r15
0x18000ab44  jz      loc_18000ADD8
0x18000ab4a  lea     rax, [rbp+57h+var_C0]
0x18000ab4e  mov     r9d, 20019h; samDesired
0x18000ab54  xor     r8d, r8d; ulOptions
0x18000ab57  mov     [rsp+100h+phkResult], rax; phkResult
0x18000ab5c  lea     rdx, aSetaliases; "SetAliases"
0x18000ab63  mov     rcx, rdi; hKey
0x18000ab66  call    cs:__imp_RegOpenKeyExW
0x18000ab6d  nop     dword ptr [rax+rax+00h]
0x18000ab72  test    eax, eax
0x18000ab74  jz      short loc_18000AB7A
0x18000ab76  mov     [rbp+57h+var_C0], r12
0x18000ab7a  mov     edi, [rbp+57h+cbData]
0x18000ab7d  jmp     short loc_18000ABED
0x18000ab7f  mov     [rbp+57h+cbData], r12d
0x18000ab83  lea     rdx, [rbp+57h+sz]; lpsz
0x18000ab87  mov     [rbp+57h+var_C8], r12
0x18000ab8b  xorps   xmm0, xmm0
0x18000ab8e  dec     edi
0x18000ab90  mov     r8d, 27h ; '''; cchMax
0x18000ab96  mov     r12d, edi
0x18000ab99  shl     r12, 4
0x18000ab9d  add     r12, r15
0x18000aba0  mov     rcx, r12; rguid
0x18000aba3  movups  xmmword ptr [rbp+57h+Data], xmm0
0x18000aba7  call    cs:__imp_StringFromGUID2
0x18000abae  nop     dword ptr [rax+rax+00h]
0x18000abb3  mov     rcx, [rbp+57h+var_C0]; hKey
0x18000abb7  test    rcx, rcx
0x18000abba  jnz     loc_18000AD25
0x18000abc0  mov     rcx, [rbp+57h+hKey]; hKey
0x18000abc4  lea     rax, [rbp+57h+var_C8]
0x18000abc8  mov     r9d, 20019h; samDesired
0x18000abce  mov     [rsp+100h+phkResult], rax; phkResult
0x18000abd3  xor     r8d, r8d; ulOptions
0x18000abd6  lea     rdx, [rbp+57h+sz]; lpSubKey
0x18000abda  call    cs:__imp_RegOpenKeyExW
0x18000abe1  nop     dword ptr [rax+rax+00h]
0x18000abe6  test    eax, eax
0x18000abe8  jz      short loc_18000AC59
0x18000abea  xor     r12d, r12d
0x18000abed  test    edi, edi
0x18000abef  jnz     short loc_18000AB7F
0x18000abf1  mov     rcx, [rbp+57h+hKey]; hKey
0x18000abf5  call    cs:__imp_RegCloseKey
0x18000abfc  nop     dword ptr [rax+rax+00h]
0x18000ac01  mov     rcx, [rbp+57h+var_C0]; hKey
0x18000ac05  test    rcx, rcx
0x18000ac08  jnz     loc_18000AD93
0x18000ac0e  mov     rcx, r15; void *
0x18000ac11  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ac16  mov     rdx, [rsi]; struct __POSITION *
0x18000ac19  test    rdx, rdx
0x18000ac1c  jz      short loc_18000AC38
0x18000ac1e  mov     rbx, [rdx+10h]
0x18000ac22  mov     rdi, [rdx+8]
0x18000ac26  cmp     [rbx+30h], r12d
0x18000ac2a  jnz     loc_18000ADA4
0x18000ac30  mov     rdx, rdi
0x18000ac33  test    rdi, rdi
0x18000ac36  jnz     short loc_18000AC1E
0x18000ac38  xor     eax, eax
0x18000ac3a  mov     rcx, [rbp+57h+var_40]
0x18000ac3e  xor     rcx, rsp; StackCookie
0x18000ac41  call    __security_check_cookie
0x18000ac46  add     rsp, 0D0h
0x18000ac4d  pop     r15
0x18000ac4f  pop     r13
0x18000ac51  pop     r12
0x18000ac53  pop     rdi
0x18000ac54  pop     rsi
0x18000ac55  pop     rbx
0x18000ac56  pop     rbp
0x18000ac57  retn
0x18000ac59  mov     rcx, [rbp+57h+var_C8]; hKey
0x18000ac5d  lea     rax, [rbp+57h+cbData]
0x18000ac61  mov     [rsp+100h+lpcbData], rax; lpcbData
0x18000ac66  lea     rdx, ValueName; "iid"
0x18000ac6d  lea     rax, [rbp+57h+Data]
0x18000ac71  mov     [rbp+57h+cbData], 10h
0x18000ac78  xor     r9d, r9d; lpType
0x18000ac7b  mov     [rsp+100h+phkResult], rax; lpData
0x18000ac80  xor     r8d, r8d; lpReserved
0x18000ac83  call    cs:__imp_RegQueryValueExW
0x18000ac8a  nop     dword ptr [rax+rax+00h]
0x18000ac8f  mov     rcx, [rbp+57h+var_C8]; hKey
0x18000ac93  mov     ebx, eax
0x18000ac95  call    cs:__imp_RegCloseKey
0x18000ac9c  nop     dword ptr [rax+rax+00h]
0x18000aca1  test    ebx, ebx
0x18000aca3  jnz     loc_18000AD82
0x18000aca9  mov     ecx, 38h ; '8'; Size
0x18000acae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000acb3  test    rax, rax
0x18000acb6  jz      short loc_18000ACE4
0x18000acb8  movups  xmm0, xmmword ptr [rbp+57h+Data]
0x18000acbc  mov     r8, [rbp+57h+pUnkOuter]; pUnkOuter
0x18000acc0  mov     r9d, 1
0x18000acc6  mov     rdx, rax; void *
0x18000acc9  mov     rcx, rsi; this
0x18000accc  movdqu  xmmword ptr [rax], xmm0
0x18000acd0  movups  xmm1, xmmword ptr [r12]
0x18000acd5  movdqu  xmmword ptr [rax+10h], xmm1
0x18000acda  call    ?AddAggregateObject@@YAJPEAV?$CGenericList@VCAggregateMarshaler@@@@PEAVCAggregateMarshaler@@PEAUIUnknown@@H@Z; AddAggregateObject(CGenericList<CAggregateMarshaler> *,CAggregateMarshaler *,IUnknown *,int)
0x18000acdf  jmp     loc_18000ABEA
0x18000ace4  xor     r12d, r12d
0x18000ace7  jmp     loc_18000ABF1
0x18000acec  mov     rcx, [rbp+57h+var_C8]; void *
0x18000acf0  test    rcx, rcx
0x18000acf3  jz      short loc_18000ACFA
0x18000acf5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000acfa  mov     rdx, [rsi]; struct __POSITION *
0x18000acfd  test    rdx, rdx
0x18000ad00  jz      loc_18000AC38
0x18000ad06  mov     rbx, [rdx+10h]
0x18000ad0a  mov     rdi, [rdx+8]
0x18000ad0e  cmp     [rbx+30h], r12d
0x18000ad12  jnz     loc_18000ADED
0x18000ad18  mov     rdx, rdi
0x18000ad1b  test    rdi, rdi
0x18000ad1e  jnz     short loc_18000AD06
0x18000ad20  jmp     loc_18000AC38
0x18000ad25  lea     rax, [rbp+57h+cbData]
0x18000ad29  mov     [rbp+57h+cbData], 10h
0x18000ad30  mov     [rsp+100h+lpcbData], rax; lpcbData
0x18000ad35  lea     rdx, [rbp+57h+sz]; lpValueName
0x18000ad39  lea     rax, [rbp+57h+Data]
0x18000ad3d  xor     r9d, r9d; lpType
0x18000ad40  xor     r8d, r8d; lpReserved
0x18000ad43  mov     [rsp+100h+phkResult], rax; lpData
0x18000ad48  call    cs:__imp_RegQueryValueExW
0x18000ad4f  nop     dword ptr [rax+rax+00h]
0x18000ad54  test    eax, eax
0x18000ad56  jnz     loc_18000ABC0
0x18000ad5c  movups  xmm0, xmmword ptr [rbp+57h+Data]
0x18000ad60  lea     r8d, [rax+27h]; cchMax
0x18000ad64  mov     rcx, r12; rguid
0x18000ad67  lea     rdx, [rbp+57h+sz]; lpsz
0x18000ad6b  movdqu  xmmword ptr [r12], xmm0
0x18000ad71  call    cs:__imp_StringFromGUID2
0x18000ad78  nop     dword ptr [rax+rax+00h]
0x18000ad7d  jmp     loc_18000ABC0
0x18000ad82  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000ad89  movdqu  xmmword ptr [rbp+57h+Data], xmm0
0x18000ad8e  jmp     loc_18000ACA9
0x18000ad93  call    cs:__imp_RegCloseKey
0x18000ad9a  nop     dword ptr [rax+rax+00h]
0x18000ad9f  jmp     loc_18000AC0E
0x18000ada4  cmp     [rbx+34h], r12d
0x18000ada8  jnz     loc_18000AC30
0x18000adae  mov     rcx, rsi; this
0x18000adb1  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x18000adb6  mov     rcx, [rbx+20h]
0x18000adba  mov     rax, [rcx]
0x18000adbd  mov     rax, [rax+10h]
0x18000adc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adc6  mov     edx, 38h ; '8'; unsigned __int64
0x18000adcb  mov     rcx, rbx; void *
0x18000adce  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000add3  jmp     loc_18000AC30
0x18000add8  mov     rcx, [rbp+57h+hKey]; hKey
0x18000addc  call    cs:__imp_RegCloseKey
0x18000ade3  nop     dword ptr [rax+rax+00h]
0x18000ade8  jmp     loc_18000ACFA
0x18000aded  cmp     [rbx+34h], r12d
0x18000adf1  jnz     loc_18000AD18
0x18000adf7  mov     rcx, rsi; this
0x18000adfa  call    ?RemoveI@CBaseList@@IEAAPEAXPEAU__POSITION@@@Z; CBaseList::RemoveI(__POSITION *)
0x18000adff  mov     rcx, [rbx+20h]
0x18000ae03  mov     rax, [rcx]
0x18000ae06  mov     rax, [rax+10h]
0x18000ae0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae0f  mov     edx, 38h ; '8'; unsigned __int64
0x18000ae14  mov     rcx, rbx; void *
0x18000ae17  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ae1c  jmp     loc_18000AD18
```
