# PolicyManager::ReadGroupPolicy

- ea: `0x180023e1c`
- end: `0x18002400c`
- name: `PolicyManager::ReadGroupPolicy`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020320`

## callees

- `0x1800158e0`
- `0x180016538`
- `0x18001a36c`
- `0x180023e1c`
- `0x18003e878`
- `0x18003e9a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023e71`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023e71`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PolicyManager::ReadGroupPolicy(__int64 a1, __int64 a2, _OWORD *a3)
{
  LSTATUS v4; // eax
  __int64 v5; // rcx
  signed int v6; // ebx
  int v7; // ebx
  int IsKeyEmpty; // eax
  unsigned __int8 *v9; // rdx
  void **v11; // [rsp+30h] [rbp-19h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-11h] BYREF
  __int128 v13; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v14[44]; // [rsp+50h] [rbp+7h]
  __int64 v15; // [rsp+B8h] [rbp+6Fh] BYREF

  v15 = a2;
  v11 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  phkResult = 0;
  Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(&v11);
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Policies\\Microsoft\\PassportForWork", 0, 0x20019u, &phkResult);
  v6 = v4;
  if ( v4 )
  {
    if ( v4 == 2 )
      goto LABEL_6;
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      LODWORD(v15) = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)byte_1800621A5,
        0,
        0,
        (__int64)&v15);
    }
    if ( v6 > 0 )
LABEL_6:
      v6 = (unsigned __int16)v6 | 0x80070000;
    v7 = HResultToSecurityStatus(v6);
    goto LABEL_20;
  }
  LOBYTE(v15) = 1;
  IsKeyEmpty = PolicyManager::IsKeyEmpty(v5, phkResult, &v15);
  v7 = IsKeyEmpty;
  if ( IsKeyEmpty < 0 )
  {
    if ( (unsigned int)dword_18006E000 <= 2 )
      goto LABEL_20;
    LODWORD(v15) = IsKeyEmpty;
    v9 = (unsigned __int8 *)byte_180062183;
LABEL_11:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18006E000,
      v9,
      0,
      0,
      (__int64)&v15);
    goto LABEL_20;
  }
  if ( (_BYTE)v15 )
  {
    if ( (unsigned int)dword_18006E000 > 4 )
    {
      LODWORD(v15) = -2146893807;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18006E000,
        (unsigned __int8 *)byte_180062161,
        0,
        0,
        (__int64)&v15);
    }
    v7 = -2146893807;
  }
  else
  {
    LOBYTE(v13) = 0;
    DWORD1(v13) = 1;
    *((_QWORD *)&v13 + 1) = 1;
    v14[0] = 0;
    *(_QWORD *)&v14[4] = 0x7F00000008LL;
    *(_OWORD *)&v14[12] = 0;
    *(_DWORD *)&v14[28] = 2;
    *(_QWORD *)&v14[32] = 1;
    *(_DWORD *)&v14[40] = 0;
    v7 = PolicyManager::ReadProPolicyValuesFromRegistry((int)&v11, &v13);
    if ( v7 >= 0 )
    {
      *a3 = v13;
      a3[1] = *(_OWORD *)v14;
      a3[2] = *(_OWORD *)&v14[16];
      *(_OWORD *)((char *)a3 + 44) = *(_OWORD *)&v14[28];
      goto LABEL_20;
    }
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      LODWORD(v15) = v7;
      v9 = (unsigned __int8 *)&word_180062126;
      goto LABEL_11;
    }
  }
LABEL_20:
  v11 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(&v11);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180023e1c  mov     [rsp-8+arg_8], rdx
0x180023e21  push    rbp
0x180023e22  push    rbx
0x180023e23  push    rdi
0x180023e24  push    r15
0x180023e26  lea     rbp, [rsp-3Fh]
0x180023e2b  sub     rsp, 88h
0x180023e32  mov     rdi, r8
0x180023e35  lea     r15, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x180023e3c  mov     [rbp+57h+var_70], r15
0x180023e40  mov     [rbp+57h+var_68], 0
0x180023e48  lea     rcx, [rbp+57h+var_70]
0x180023e4c  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x180023e51  lea     rax, [rbp+57h+var_68]
0x180023e55  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180023e5a  mov     r9d, 20019h; samDesired
0x180023e60  xor     r8d, r8d; ulOptions
0x180023e63  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Passport"...
0x180023e6a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180023e71  call    cs:__imp_RegOpenKeyExW
0x180023e77  mov     ebx, eax
0x180023e79  test    eax, eax
0x180023e7b  jz      short loc_180023ECD
0x180023e7d  cmp     eax, 2
0x180023e80  jz      short loc_180023EB6
0x180023e82  mov     eax, cs:dword_18006E000
0x180023e88  cmp     eax, 2
0x180023e8b  jbe     short loc_180023EB2
0x180023e8d  mov     dword ptr [rbp+57h+arg_8], ebx
0x180023e90  lea     rax, [rbp+57h+arg_8]
0x180023e94  mov     [rsp+0A0h+phkResult], rax
0x180023e99  xor     r9d, r9d
0x180023e9c  xor     r8d, r8d
0x180023e9f  lea     rdx, byte_1800621A5
0x180023ea6  lea     rcx, dword_18006E000
0x180023ead  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180023eb2  test    ebx, ebx
0x180023eb4  jle     short loc_180023EBF
0x180023eb6  movzx   ebx, bx
0x180023eb9  or      ebx, 80070000h
0x180023ebf  mov     ecx, ebx; int
0x180023ec1  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x180023ec6  mov     ebx, eax
0x180023ec8  jmp     loc_180023FF0
0x180023ecd  mov     byte ptr [rbp+57h+arg_8], 1
0x180023ed1  lea     r8, [rbp+57h+arg_8]
0x180023ed5  mov     rdx, [rbp+57h+var_68]
0x180023ed9  call    PolicyManager__IsKeyEmpty
0x180023ede  mov     ebx, eax
0x180023ee0  test    eax, eax
0x180023ee2  jns     short loc_180023F1D
0x180023ee4  mov     ecx, cs:dword_18006E000
0x180023eea  cmp     ecx, 2
0x180023eed  jbe     loc_180023FF0
0x180023ef3  mov     dword ptr [rbp+57h+arg_8], eax
0x180023ef6  lea     rdx, byte_180062183
0x180023efd  xor     r9d, r9d
0x180023f00  lea     rax, [rbp+57h+arg_8]
0x180023f04  xor     r8d, r8d
0x180023f07  mov     [rsp+0A0h+phkResult], rax
0x180023f0c  lea     rcx, dword_18006E000
0x180023f13  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180023f18  jmp     loc_180023FF0
0x180023f1d  cmp     byte ptr [rbp+57h+arg_8], 0
0x180023f21  jz      short loc_180023F61
0x180023f23  mov     eax, cs:dword_18006E000
0x180023f29  cmp     eax, 4
0x180023f2c  jbe     short loc_180023F57
0x180023f2e  mov     dword ptr [rbp+57h+arg_8], 80090011h
0x180023f35  lea     rax, [rbp+57h+arg_8]
0x180023f39  mov     [rsp+0A0h+phkResult], rax
0x180023f3e  xor     r9d, r9d
0x180023f41  xor     r8d, r8d
0x180023f44  lea     rdx, byte_180062161
0x180023f4b  lea     rcx, dword_18006E000
0x180023f52  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180023f57  mov     ebx, 80090011h
0x180023f5c  jmp     loc_180023FF0
0x180023f61  mov     byte ptr [rbp+57h+var_60], 0
0x180023f65  mov     dword ptr [rbp+57h+var_60+4], 1
0x180023f6c  mov     qword ptr [rbp+57h+var_60+8], 1
0x180023f74  mov     byte ptr [rbp+57h+var_50], 0
0x180023f78  mov     dword ptr [rbp+57h+var_50+4], 8
0x180023f7f  mov     dword ptr [rbp+57h+var_50+8], 7Fh
0x180023f86  xorps   xmm0, xmm0
0x180023f89  movdqu  [rbp+57h+var_50+0Ch], xmm0
0x180023f8e  mov     dword ptr [rbp+57h+var_34], 2
0x180023f95  mov     qword ptr [rbp+57h+var_34+4], 1
0x180023f9d  mov     dword ptr [rbp+57h+var_34+0Ch], 0
0x180023fa4  lea     rdx, [rbp+57h+var_60]
0x180023fa8  lea     rcx, [rbp+57h+var_70]
0x180023fac  call    PolicyManager__ReadProPolicyValuesFromRegistry
0x180023fb1  mov     ebx, eax
0x180023fb3  test    eax, eax
0x180023fb5  jns     short loc_180023FD1
0x180023fb7  mov     eax, cs:dword_18006E000
0x180023fbd  cmp     eax, 2
0x180023fc0  jbe     short loc_180023FF0
0x180023fc2  mov     dword ptr [rbp+57h+arg_8], ebx
0x180023fc5  lea     rdx, word_180062126
0x180023fcc  jmp     loc_180023EFD
0x180023fd1  movups  xmm0, [rbp+57h+var_60]
0x180023fd5  movups  xmmword ptr [rdi], xmm0
0x180023fd8  movups  xmm1, [rbp+57h+var_50]
0x180023fdc  movups  xmmword ptr [rdi+10h], xmm1
0x180023fe0  movups  xmm0, xmmword ptr [rbp+17h]
0x180023fe4  movups  xmmword ptr [rdi+20h], xmm0
0x180023fe8  movups  xmm1, [rbp+57h+var_34]
0x180023fec  movups  xmmword ptr [rdi+2Ch], xmm1
0x180023ff0  mov     [rbp+57h+var_70], r15
0x180023ff4  lea     rcx, [rbp+57h+var_70]
0x180023ff8  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x180023ffd  mov     eax, ebx
0x180023fff  add     rsp, 88h
0x180024006  pop     r15
0x180024008  pop     rdi
0x180024009  pop     rbx
0x18002400a  pop     rbp
0x18002400b  retn
```
