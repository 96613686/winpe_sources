# CreateDXGIFactoryImpl(uint,IDXGIFactory1 * *)

- ea: `0x18004eb18`
- end: `0x18004ec78`
- name: `?CreateDXGIFactoryImpl@@YAJIPEAPEAUIDXGIFactory1@@@Z`
- size: `352`
- prototype: `__int64 __fastcall(unsigned int, struct IDXGIFactory1 **)`
- caller_count: `5`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004e700`
- `0x18004e8f0`
- `0x18004ea20`
- `0x18004eaa0`
- `0x18004ed14`

## callees

- `0x180006770`
- `0x18000c6b0`
- `0x18000cb1c`
- `0x18001c258`
- `0x18004eb18`
- `0x18004ef4c`
- `0x18004f008`
- `0x18004f320`
- `0x1800cb010`

## import_xrefs

- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x18004eb3c`
- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x18004eb3c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18004ebfb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x18004ebfb`

## string_xrefs

- `0x18004ebf4`: `CreateDXGIFactory2 failed because DXGI_CREATE_FACTORY_DEBUG was specified, but DXGIDebug.dll is not present on the system. This flag must be removed, or the Windows SDK must be installed.\n`

## pseudocode

```c
__int64 __fastcall CreateDXGIFactoryImpl(int a1, struct IDXGIFactory1 **a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  int v6; // edi
  unsigned int v7; // edx
  CDXGIFactory *v8; // rbx
  CModule *v10; // rcx
  int v11; // eax
  CDXGIFactory *v12; // [rsp+40h] [rbp+18h] BYREF

  if ( RtlIsCriticalSectionLockedByThread(NtCurrentPeb()->LoaderLock) )
  {
    DXGI_SDK_MSG(0, DXGI_MSG_IDXGIFactory_Creation_CalledFromDllMain);
    return 2289696769LL;
  }
  if ( HIDWORD(qword_180109A08) || (v11 = IsModernApp(), LODWORD(qword_180109A08) = 1, !v11) )
    LODWORD(qword_180109A08) = 0;
  if ( (a1 & 1) != 0 )
  {
    CheckDxgiDebugDll();
    if ( !g_pDebugPrivate )
    {
      if ( a1 >= 0 )
      {
        OutputDebugStringA(
          "CreateDXGIFactory2 failed because DXGI_CREATE_FACTORY_DEBUG was specified, but DXGIDebug.dll is not present on"
          " the system. This flag must be removed, or the Windows SDK must be installed.\n");
        CModule::RecordJournalImpl(v10, -2005270483, "Factory creation failed: DXGIDebug required and not present.");
        return 2289696769LL;
      }
      a1 &= ~1u;
    }
  }
  v12 = 0;
  if ( (Microsoft_Windows_DXGIEnableBits & 2) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(v4, "(", 0);
  v6 = ATL::CComObject<CDXGIFactory>::CreateInstance(&v12);
  if ( v6 >= 0 )
  {
    v7 = a1;
    v8 = v12;
    v6 = CDXGIFactory::Initialize(v12, v7);
    (*(void (__fastcall **)(CDXGIFactory *))(*(_QWORD *)v8 + 8LL))(v8);
    if ( v6 >= 0 )
      *a2 = (struct IDXGIFactory1 *)v8;
    else
      (*(void (__fastcall **)(CDXGIFactory *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  if ( (Microsoft_Windows_DXGIEnableBits & 2) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(v5, EventProfileStop, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004eb18  mov     [rsp+arg_0], rbx
0x18004eb1d  mov     [rsp+arg_8], rsi
0x18004eb22  push    rdi
0x18004eb23  sub     rsp, 20h
0x18004eb27  mov     ebx, ecx
0x18004eb29  mov     rsi, rdx
0x18004eb2c  mov     rcx, gs:60h
0x18004eb35  mov     rcx, [rcx+110h]; CriticalSection
0x18004eb3c  call    cs:__imp_RtlIsCriticalSectionLockedByThread
0x18004eb42  test    eax, eax
0x18004eb44  jnz     loc_18004EC3A
0x18004eb4a  cmp     dword ptr cs:qword_180109A08+4, eax
0x18004eb50  jz      loc_18004EC1E
0x18004eb56  mov     dword ptr cs:qword_180109A08, 0
0x18004eb60  test    bl, 1
0x18004eb63  jnz     short loc_18004EBDD
0x18004eb65  test    byte ptr cs:Microsoft_Windows_DXGIEnableBits, 2
0x18004eb6c  mov     [rsp+28h+arg_10], 0
0x18004eb75  jnz     loc_18004EC50
0x18004eb7b  lea     rcx, [rsp+28h+arg_10]
0x18004eb80  call    ?CreateInstance@?$CComObject@VCDXGIFactory@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CDXGIFactory>::CreateInstance(ATL::CComObject<CDXGIFactory> * *)
0x18004eb85  mov     edi, eax
0x18004eb87  test    eax, eax
0x18004eb89  js      short loc_18004EBBE
0x18004eb8b  mov     edx, ebx; unsigned int
0x18004eb8d  mov     rbx, [rsp+28h+arg_10]
0x18004eb92  mov     rcx, rbx; this
0x18004eb95  call    ?Initialize@CDXGIFactory@@QEAAJI@Z; CDXGIFactory::Initialize(uint)
0x18004eb9a  mov     edi, eax
0x18004eb9c  mov     rcx, rbx
0x18004eb9f  mov     rax, [rbx]
0x18004eba2  mov     rax, [rax+8]
0x18004eba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ebab  test    edi, edi
0x18004ebad  jns     short loc_18004EC19
0x18004ebaf  mov     rax, [rbx]
0x18004ebb2  mov     rcx, rbx
0x18004ebb5  mov     rax, [rax+10h]
0x18004ebb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ebbe  test    byte ptr cs:Microsoft_Windows_DXGIEnableBits, 2
0x18004ebc5  jnz     loc_18004EC64
0x18004ebcb  mov     eax, edi
0x18004ebcd  mov     rbx, [rsp+28h+arg_0]
0x18004ebd2  mov     rsi, [rsp+28h+arg_8]
0x18004ebd7  add     rsp, 20h
0x18004ebdb  pop     rdi
0x18004ebdc  retn
0x18004ebdd  call    ?CheckDxgiDebugDll@@YAXXZ; CheckDxgiDebugDll(void)
0x18004ebe2  cmp     cs:?g_pDebugPrivate@@3PEAUIDXGIDebugPrivate@@EA, 0; IDXGIDebugPrivate * g_pDebugPrivate
0x18004ebea  jnz     loc_18004EB65
0x18004ebf0  test    ebx, ebx
0x18004ebf2  js      short loc_18004EC48
0x18004ebf4  lea     rcx, aCreatedxgifact_2; "CreateDXGIFactory2 failed because DXGI_"...
0x18004ebfb  call    cs:__imp_OutputDebugStringA
0x18004ec01  lea     r8, aFactoryCreatio; "Factory creation failed: DXGIDebug requ"...
0x18004ec08  mov     edx, 887A002Dh; unsigned int
0x18004ec0d  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18004ec12  mov     eax, 887A0001h
0x18004ec17  jmp     short loc_18004EBCD
0x18004ec19  mov     [rsi], rbx
0x18004ec1c  jmp     short loc_18004EBBE
0x18004ec1e  call    ?IsModernApp@@YAHXZ; IsModernApp(void)
0x18004ec23  mov     dword ptr cs:qword_180109A08, 1
0x18004ec2d  test    eax, eax
0x18004ec2f  jz      loc_18004EB56
0x18004ec35  jmp     loc_18004EB60
0x18004ec3a  mov     edx, 4Ch ; 'L'; enum DXGI_Message_Id
0x18004ec3f  xor     ecx, ecx; struct CDXGIFactory *
0x18004ec41  call    ?DXGI_SDK_MSG@@YAXPEAVCDXGIFactory@@W4DXGI_Message_Id@@ZZ; DXGI_SDK_MSG(CDXGIFactory *,DXGI_Message_Id,...)
0x18004ec46  jmp     short loc_18004EC12
0x18004ec48  and     ebx, 0FFFFFFFEh
0x18004ec4b  jmp     loc_18004EB65
0x18004ec50  xor     r8d, r8d
0x18004ec53  lea     rdx, EventProfileStart; "("
0x18004ec5a  call    McTemplateU0q_EtwEventWriteTransfer
0x18004ec5f  jmp     loc_18004EB7B
0x18004ec64  xor     r8d, r8d
0x18004ec67  lea     rdx, EventProfileStop
0x18004ec6e  call    McTemplateU0q_EtwEventWriteTransfer
0x18004ec73  jmp     loc_18004EBCB
```
