# CCsrMgr::CCsrMgr(long *)

- ea: `0x18006fa1c`
- end: `0x18006fc52`
- name: `??0CCsrMgr@@QEAA@PEAJ@Z`
- size: `566`
- prototype: `CCsrMgr *__fastcall(CCsrMgr *this, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a2c0`

## callees

- `0x1800074c0`
- `0x18001288c`
- `0x180025070`
- `0x18006f984`
- `0x18006fa1c`
- `0x18006fefc`

## import_xrefs

- `ntdll!RtlConnectToSm` at `0x18006faf8`
- `ntdll!RtlConnectToSm` at `0x18006faf8`
- `ntdll!TpAllocAlpcCompletion` at `0x18006fb80`
- `ntdll!TpAllocAlpcCompletion` at `0x18006fb80`
- `ntdll!NtAlpcQueryInformation` at `0x18006fb4b`
- `ntdll!NtAlpcQueryInformation` at `0x18006fb4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006fbb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006fbb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006fc2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006fc2d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006fc0f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006fc0f`

## string_xrefs

- `0x18006fb23`: `CreateLpcPort failed: 0x%x in %s`
- `0x18006fbc7`: `RegOpenKeyEx on session manager control failed. Cannot determine initial command override.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
CCsrMgr *__fastcall CCsrMgr::CCsrMgr(CCsrMgr *this, unsigned int *a2)
{
  int LpcPort; // eax
  unsigned int v5; // ebx
  const char *v6; // rdx
  int v7; // eax
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int128 v13; // [rsp+40h] [rbp-10h] BYREF
  const char *v14; // [rsp+90h] [rbp+40h] BYREF
  DWORD pcbData; // [rsp+98h] [rbp+48h] BYREF
  HKEY hkey; // [rsp+A0h] [rbp+50h] BYREF

  v14 = (const char *)this;
  CTSPrivateObject<ICsrMgr>::CTSPrivateObject<ICsrMgr>();
  *(_QWORD *)this = &CCsrMgr::`vftable';
  *((_DWORD *)this + 422) = 0;
  *((_QWORD *)this + 212) = &DynArray<SmartArray<CCsrPipe,long>::CCleanType,long>::`vftable';
  *((_QWORD *)this + 213) = 0;
  *((_QWORD *)this + 214) = 0;
  *((_DWORD *)this + 454) = 0;
  *((_QWORD *)this + 228) = 0;
  *((_QWORD *)this + 229) = 0;
  *((_DWORD *)this + 460) = 0;
  *((_QWORD *)this + 231) = 0;
  v13 = 0;
  LpcPort = CResource::Initialize((CCsrMgr *)((char *)this + 1592));
  v5 = LpcPort;
  if ( LpcPort < 0 )
  {
    v6 = "Lock.Initialize failed: 0x%x in %s";
LABEL_3:
    _DbgPrintMessage(8, v6, (unsigned int)LpcPort, "CCsrMgr::CCsrMgr");
    goto LABEL_21;
  }
  LpcPort = CResource::Initialize((CCsrMgr *)((char *)this + 1720));
  v5 = LpcPort;
  if ( LpcPort < 0 )
  {
    v6 = "CsrPipesLock.Initialize failed: 0x%x in %s";
    goto LABEL_3;
  }
  v7 = RtlConnectToSm(0, 0, 0, (char *)this + 1832);
  v5 = v7 | 0x10000000;
  if ( v7 >= 0 )
  {
    LpcPort = CCsrMgr::CreateLpcPort(this);
    v5 = LpcPort;
    if ( LpcPort < 0 )
    {
      v6 = "CreateLpcPort failed: 0x%x in %s";
      goto LABEL_3;
    }
    *((_DWORD *)this + 464) = 0;
    v8 = NtAlpcQueryInformation(*((_QWORD *)this + 228), 0, &v13, 16, 0);
    if ( v8 < 0
      || (*((_DWORD *)this + 464) = DWORD1(v13),
          v8 = TpAllocAlpcCompletion((char *)this + 1848, *((_QWORD *)this + 228), CCsrMgr::staticLpcWorker, this, 0),
          v8 < 0) )
    {
      v5 = v8 | 0x10000000;
    }
    else
    {
      hkey = 0;
      pcbData = 0;
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Session Manager", 0, 0x20019u, &hkey) )
      {
        if ( (unsigned int)dword_1800DA020 > 2 )
        {
          v14 = "RegOpenKeyEx on session manager control failed. Cannot determine initial command override.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v9,
            (unsigned __int8 *)byte_1800C6121,
            v10,
            v11,
            (const unsigned __int16 **)&v14);
        }
      }
      else
      {
        if ( !RegGetValueW(hkey, 0, L"Execute", 0x20u, 0, 0, &pcbData) && pcbData > 6 )
          *((_DWORD *)this + 465) = 1;
        RegCloseKey(hkey);
      }
    }
  }
  else
  {
    _DbgPrintMessage(8, "SmConnectToSm failed: 0x%x in %s", v5, "CCsrMgr::CCsrMgr");
  }
LABEL_21:
  *a2 = v5;
  return this;
}

```

## disassembly

```asm
0x18006fa1c  mov     [rsp-38h+arg_18], rbx
0x18006fa21  mov     [rsp-38h+arg_0], rcx
0x18006fa26  push    rbp
0x18006fa27  push    rsi
0x18006fa28  push    rdi
0x18006fa29  push    r12
0x18006fa2b  push    r13
0x18006fa2d  push    r14
0x18006fa2f  push    r15
0x18006fa31  mov     rbp, rsp
0x18006fa34  sub     rsp, 50h
0x18006fa38  mov     r12, rdx
0x18006fa3b  mov     rdi, rcx
0x18006fa3e  call    ??0?$CTSPrivateObject@VICsrMgr@@@@QEAA@PEBD@Z; CTSPrivateObject<ICsrMgr>::CTSPrivateObject<ICsrMgr>(char const *)
0x18006fa43  nop
0x18006fa44  lea     rax, ??_7CCsrMgr@@6B@; const CCsrMgr::`vftable'
0x18006fa4b  mov     [rdi], rax
0x18006fa4e  lea     rcx, [rdi+638h]; this
0x18006fa55  xor     r13d, r13d
0x18006fa58  mov     [rcx+60h], r13d
0x18006fa5c  lea     rax, ??_7?$DynArray@VCCleanType@?$SmartArray@VCCsrPipe@@J@@J@@6B@; const DynArray<SmartArray<CCsrPipe,long>::CCleanType,long>::`vftable'
0x18006fa63  mov     [rdi+6A0h], rax
0x18006fa6a  mov     [rdi+6A8h], r13
0x18006fa71  mov     [rdi+6B0h], r13
0x18006fa78  lea     rsi, [rdi+6B8h]
0x18006fa7f  mov     [rsi+60h], r13d
0x18006fa83  mov     [rdi+720h], r13
0x18006fa8a  lea     r14, [rdi+728h]
0x18006fa91  mov     [r14], r13
0x18006fa94  mov     [rdi+730h], r13d
0x18006fa9b  lea     r15, [rdi+738h]
0x18006faa2  mov     [r15], r13
0x18006faa5  xorps   xmm0, xmm0
0x18006faa8  movups  [rbp+var_10], xmm0
0x18006faac  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x18006fab1  mov     ebx, eax
0x18006fab3  test    eax, eax
0x18006fab5  jns     short loc_18006FAD7
0x18006fab7  lea     rdx, aLockInitialize; "Lock.Initialize failed: 0x%x in %s"
0x18006fabe  mov     r8d, eax
0x18006fac1  lea     r9, aCcsrmgrCcsrmgr; "CCsrMgr::CCsrMgr"
0x18006fac8  mov     ecx, 8; int
0x18006facd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006fad2  jmp     loc_18006FC33
0x18006fad7  mov     rcx, rsi; this
0x18006fada  call    ?Initialize@CResource@@QEAAJXZ; CResource::Initialize(void)
0x18006fadf  mov     ebx, eax
0x18006fae1  test    eax, eax
0x18006fae3  jns     short loc_18006FAEE
0x18006fae5  lea     rdx, aCsrpipeslockIn; "CsrPipesLock.Initialize failed: 0x%x in"...
0x18006faec  jmp     short loc_18006FABE
0x18006faee  mov     r9, r14
0x18006faf1  xor     r8d, r8d
0x18006faf4  xor     edx, edx
0x18006faf6  xor     ecx, ecx
0x18006faf8  call    cs:__imp_RtlConnectToSm
0x18006fafe  mov     ebx, eax
0x18006fb00  mov     esi, 10000000h
0x18006fb05  or      ebx, esi
0x18006fb07  jge     short loc_18006FB15
0x18006fb09  mov     r8d, ebx
0x18006fb0c  lea     rdx, aSmconnecttosmF; "SmConnectToSm failed: 0x%x in %s"
0x18006fb13  jmp     short loc_18006FAC1
0x18006fb15  mov     rcx, rdi; this
0x18006fb18  call    ?CreateLpcPort@CCsrMgr@@AEAAJXZ; CCsrMgr::CreateLpcPort(void)
0x18006fb1d  mov     ebx, eax
0x18006fb1f  test    eax, eax
0x18006fb21  jns     short loc_18006FB2C
0x18006fb23  lea     rdx, aCreatelpcportF; "CreateLpcPort failed: 0x%x in %s"
0x18006fb2a  jmp     short loc_18006FABE
0x18006fb2c  mov     [rdi+740h], r13d
0x18006fb33  mov     [rsp+50h+phkResult], r13
0x18006fb38  mov     r9d, 10h
0x18006fb3e  lea     r8, [rbp+var_10]
0x18006fb42  xor     edx, edx
0x18006fb44  mov     rcx, [rdi+720h]
0x18006fb4b  call    cs:__imp_NtAlpcQueryInformation
0x18006fb51  test    eax, eax
0x18006fb53  jns     short loc_18006FB5E
0x18006fb55  mov     ebx, eax
0x18006fb57  or      ebx, esi
0x18006fb59  jmp     loc_18006FC33
0x18006fb5e  mov     eax, dword ptr [rbp+var_10+4]
0x18006fb61  mov     [rdi+740h], eax
0x18006fb67  mov     [rsp+50h+phkResult], r13
0x18006fb6c  mov     r9, rdi
0x18006fb6f  lea     r8, ?staticLpcWorker@CCsrMgr@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_ALPC@@@Z; CCsrMgr::staticLpcWorker(_TP_CALLBACK_INSTANCE *,void *,_TP_ALPC *)
0x18006fb76  mov     rdx, [rdi+720h]
0x18006fb7d  mov     rcx, r15
0x18006fb80  call    cs:__imp_TpAllocAlpcCompletion
0x18006fb86  test    eax, eax
0x18006fb88  js      short loc_18006FB55
0x18006fb8a  mov     [rbp+hkey], r13
0x18006fb8e  mov     [rbp+arg_8], r13d
0x18006fb92  lea     rax, [rbp+hkey]
0x18006fb96  mov     [rsp+50h+phkResult], rax; phkResult
0x18006fb9b  mov     r9d, 20019h; samDesired
0x18006fba1  xor     r8d, r8d; ulOptions
0x18006fba4  lea     rdx, aSystemCurrentc_12; "SYSTEM\\CurrentControlSet\\Control\\Ses"...
0x18006fbab  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006fbb2  call    cs:__imp_RegOpenKeyExW
0x18006fbb8  test    eax, eax
0x18006fbba  jz      short loc_18006FBE9
0x18006fbbc  mov     eax, cs:dword_1800DA020
0x18006fbc2  cmp     eax, 2
0x18006fbc5  jbe     short loc_18006FC33
0x18006fbc7  lea     rax, aRegopenkeyexOn; "RegOpenKeyEx on session manager control"...
0x18006fbce  mov     [rbp+arg_0], rax
0x18006fbd2  lea     rax, [rbp+arg_0]
0x18006fbd6  mov     [rsp+50h+phkResult], rax
0x18006fbdb  lea     rdx, byte_1800C6121
0x18006fbe2  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006fbe7  jmp     short loc_18006FC33
0x18006fbe9  lea     rax, [rbp+arg_8]
0x18006fbed  mov     [rsp+50h+pcbData], rax; pcbData
0x18006fbf2  mov     [rsp+50h+pvData], r13; pvData
0x18006fbf7  mov     [rsp+50h+phkResult], r13; pdwType
0x18006fbfc  mov     r9d, 20h ; ' '; dwFlags
0x18006fc02  lea     r8, aExecute; "Execute"
0x18006fc09  xor     edx, edx; lpSubKey
0x18006fc0b  mov     rcx, [rbp+hkey]; hkey
0x18006fc0f  call    cs:__imp_RegGetValueW
0x18006fc15  test    eax, eax
0x18006fc17  jnz     short loc_18006FC29
0x18006fc19  cmp     [rbp+arg_8], 6
0x18006fc1d  jbe     short loc_18006FC29
0x18006fc1f  mov     dword ptr [rdi+744h], 1
0x18006fc29  mov     rcx, [rbp+hkey]; hKey
0x18006fc2d  call    cs:__imp_RegCloseKey
0x18006fc33  mov     [r12], ebx
0x18006fc37  mov     rax, rdi
0x18006fc3a  mov     rbx, [rsp+50h+arg_18]
0x18006fc42  add     rsp, 50h
0x18006fc46  pop     r15
0x18006fc48  pop     r14
0x18006fc4a  pop     r13
0x18006fc4c  pop     r12
0x18006fc4e  pop     rdi
0x18006fc4f  pop     rsi
0x18006fc50  pop     rbp
0x18006fc51  retn
```
