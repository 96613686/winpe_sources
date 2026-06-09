# CDimRouterManager::DoStartRouter(void *)

- ea: `0x18002de10`
- end: `0x18002df80`
- name: `?DoStartRouter@CDimRouterManager@@CAKPEAX@Z`
- size: `368`
- prototype: `__int64 __fastcall(RTL_SRWLOCK **Parameter)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000def0`
- `0x1800182a0`
- `0x1800239f8`
- `0x18002da7c`
- `0x18002de10`
- `0x18002e15c`
- `0x18002f7c8`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002defa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002defa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002df1c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002df1c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002de62`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002de62`
- `MPRDDM!DDMTransportCreate` at `0x18002df3f`
- `MPRDDM!DDMTransportCreate` at `0x18002df3f`

## pseudocode

```c
__int64 __fastcall CDimRouterManager::DoStartRouter(RTL_SRWLOCK **Parameter)
{
  unsigned int v2; // ebp
  unsigned int started; // eax
  unsigned __int16 *v4; // rdx
  CDimInterfaceTable *v5; // rcx
  RTL_SRWLOCK *v6; // rdi
  unsigned int v7; // ebx
  void (*v8)(void); // rax
  int v10; // [rsp+40h] [rbp-828h] BYREF
  _BYTE v11[2044]; // [rsp+44h] [rbp-824h] BYREF

  v10 = 0;
  v2 = 0;
  memset_0(v11, 0, sizeof(v11));
  if ( Parameter )
  {
    Sleep(0x3A98u);
    started = CDimRouterManager::StartRouter(
                (unsigned int)*Parameter,
                *((_DWORD *)Parameter + 2),
                (int)Parameter + 16,
                (int)Parameter + 24,
                *((_DWORD *)Parameter + 8),
                (__int64)(Parameter + 5),
                *((_DWORD *)Parameter + 12));
    v2 = started;
    if ( started )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v10) = 0;
        FormatRRASErrorString(&v10, L"DoStartRouter: StartRouter failed %d", started);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v10);
      }
    }
    else
    {
      CDimInterfaceTable::AddTransportFromRegistry(v5, v4, *((_DWORD *)Parameter + 2));
      v6 = *Parameter;
      v7 = *((_DWORD *)Parameter + 2);
      AcquireSRWLockShared(*Parameter + 1);
      v8 = (void (*)(void))*((_QWORD *)CDimRouterManager::GetRouter((CDimRouterManager *)v6, v7) + 2);
      if ( v8 )
        v8();
      ReleaseSRWLockShared(v6 + 1);
      if ( (gblDIMConfigInfo & 0x12) != gblDIMConfigInfo && (gbldwDIMComponentsLoaded & 4) != 0 )
        DDMTransportCreate(*((unsigned int *)Parameter + 2));
      RouterIdentityObjectUpdateAttributes(0, 0);
    }
    CDimRouterManager::_ROUTER_START_DATA::`scalar deleting destructor'(
      (CDimRouterManager::_ROUTER_START_DATA *)Parameter,
      (unsigned int)v4);
  }
  return v2;
}

```

## disassembly

```asm
0x18002de10  mov     [rsp+arg_8], rbx
0x18002de15  mov     [rsp+arg_10], rbp
0x18002de1a  push    rsi
0x18002de1b  push    rdi
0x18002de1c  push    r14
0x18002de1e  sub     rsp, 850h
0x18002de25  mov     rax, cs:__security_cookie
0x18002de2c  xor     rax, rsp
0x18002de2f  mov     [rsp+868h+var_28], rax
0x18002de37  mov     rsi, rcx
0x18002de3a  xor     eax, eax
0x18002de3c  lea     rcx, [rsp+868h+var_824]; void *
0x18002de41  mov     [rsp+868h+var_828], eax
0x18002de45  xor     edx, edx; Val
0x18002de47  mov     r8d, 7FCh; Size
0x18002de4d  xor     ebp, ebp
0x18002de4f  call    memset_0
0x18002de54  test    rsi, rsi
0x18002de57  jz      loc_18002DF56
0x18002de5d  mov     ecx, 3A98h; dwMilliseconds
0x18002de62  call    cs:__imp_Sleep
0x18002de68  mov     eax, [rsi+30h]
0x18002de6b  lea     rcx, [rsi+28h]
0x18002de6f  mov     edx, [rsi+8]
0x18002de72  lea     r9, [rsi+18h]
0x18002de76  mov     [rsp+868h+var_838], eax
0x18002de7a  lea     r8, [rsi+10h]
0x18002de7e  mov     eax, [rsi+20h]
0x18002de81  mov     [rsp+868h+var_840], rcx
0x18002de86  mov     rcx, [rsi]
0x18002de89  mov     [rsp+868h+var_848], eax
0x18002de8d  call    ?StartRouter@CDimRouterManager@@AEAAKKAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@AEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@3@K1K@Z; CDimRouterManager::StartRouter(ulong,std::unique_ptr<ushort [0]> &,std::unique_ptr<uchar [0]> &,ulong,std::unique_ptr<uchar [0]> &,ulong)
0x18002de92  mov     ebp, eax
0x18002de94  test    eax, eax
0x18002de96  jz      short loc_18002DEE7
0x18002de98  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18002de9f  jz      loc_18002DF4E
0x18002dea5  xor     ecx, ecx
0x18002dea7  lea     rdx, aDostartrouterS; "DoStartRouter: StartRouter failed %d"
0x18002deae  mov     word ptr [rsp+868h+var_828], cx
0x18002deb3  mov     r8d, eax
0x18002deb6  lea     rcx, [rsp+868h+var_828]
0x18002debb  call    FormatRRASErrorString
0x18002dec0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x18002dec7  jz      loc_18002DF4E
0x18002decd  lea     r8, [rsp+868h+var_828]
0x18002ded2  lea     rdx, RasDimTraceError
0x18002ded9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002dee0  call    McTemplateU0z_EventWriteTransfer
0x18002dee5  jmp     short loc_18002DF4E
0x18002dee7  mov     r8d, [rsi+8]; unsigned int
0x18002deeb  call    ?AddTransportFromRegistry@CDimInterfaceTable@@QEAAKPEAGK@Z; CDimInterfaceTable::AddTransportFromRegistry(ushort *,ulong)
0x18002def0  mov     rdi, [rsi]
0x18002def3  mov     ebx, [rsi+8]
0x18002def6  lea     rcx, [rdi+8]; SRWLock
0x18002defa  call    cs:__imp_AcquireSRWLockShared
0x18002df00  mov     edx, ebx; unsigned int
0x18002df02  mov     rcx, rdi; this
0x18002df05  call    ?GetRouter@CDimRouterManager@@AEAAPEAU_ROUTER@1@K@Z; CDimRouterManager::GetRouter(ulong)
0x18002df0a  mov     rax, [rax+10h]
0x18002df0e  test    rax, rax
0x18002df11  jz      short loc_18002DF18
0x18002df13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df18  lea     rcx, [rdi+8]; SRWLock
0x18002df1c  call    cs:__imp_ReleaseSRWLockShared
0x18002df22  mov     eax, cs:?gblDIMConfigInfo@@3U_DIM_CONFIG_INFO@@A; _DIM_CONFIG_INFO gblDIMConfigInfo
0x18002df28  and     eax, 12h
0x18002df2b  cmp     eax, cs:?gblDIMConfigInfo@@3U_DIM_CONFIG_INFO@@A; _DIM_CONFIG_INFO gblDIMConfigInfo
0x18002df31  jz      short loc_18002DF45
0x18002df33  test    byte ptr cs:?gbldwDIMComponentsLoaded@@3KA, 4; ulong gbldwDIMComponentsLoaded
0x18002df3a  jz      short loc_18002DF45
0x18002df3c  mov     ecx, [rsi+8]
0x18002df3f  call    cs:__imp_DDMTransportCreate
0x18002df45  xor     edx, edx; BOOLEAN
0x18002df47  xor     ecx, ecx; PVOID
0x18002df49  call    ?RouterIdentityObjectUpdateAttributes@@YAXPEAXE@Z; RouterIdentityObjectUpdateAttributes(void *,uchar)
0x18002df4e  mov     rcx, rsi; this
0x18002df51  call    ??_G_ROUTER_START_DATA@CDimRouterManager@@QEAAPEAXI@Z; CDimRouterManager::_ROUTER_START_DATA::`scalar deleting destructor'(uint)
0x18002df56  mov     eax, ebp
0x18002df58  mov     rcx, [rsp+868h+var_28]
0x18002df60  xor     rcx, rsp; StackCookie
0x18002df63  call    __security_check_cookie
0x18002df68  lea     r11, [rsp+868h+var_18]
0x18002df70  mov     rbx, [r11+28h]
0x18002df74  mov     rbp, [r11+30h]
0x18002df78  mov     rsp, r11
0x18002df7b  pop     r14
0x18002df7d  pop     rdi
0x18002df7e  pop     rsi
0x18002df7f  retn
```
