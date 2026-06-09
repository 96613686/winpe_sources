# CGroupPolicyObject::OpenLocalMachineGpo(void)

- ea: `0x140004b20`
- end: `0x140004c38`
- name: `?OpenLocalMachineGpo@CGroupPolicyObject@@UEAAJXZ`
- size: `280`
- prototype: `__int64 __fastcall(CGroupPolicyObject *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140004b20`
- `0x140004f90`
- `0x140004fcc`
- `0x140005004`
- `0x140030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140004b5a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140004b91`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140004b5a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140004b91`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140004bbd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140004bbd`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140004b87`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140004b87`

## string_xrefs

- `0x140004b2c`: `CGroupPolicyObject::OpenLocalMachineGpo`
- `0x140004b7b`: `%s: CoInitializeEx(COINIT_APARTMENTTHREADED) failed with RPC_E_CHANGED_MODE. Trying to call CoUninitialize first then CoInitializeEx again.`
- `0x140004bcc`: `CoCreateInstance`
- `0x140004bf2`: `IGroupPolicyObject::OpenLocalMachineGPO`

## pseudocode

```c
__int64 __fastcall CGroupPolicyObject::OpenLocalMachineGpo(CGroupPolicyObject *this)
{
  int v2; // esi
  HRESULT v3; // eax
  unsigned int v4; // ebx
  LPVOID *ppv; // rdi
  HRESULT Instance; // eax
  __int64 v7; // r9
  const wchar_t *v8; // r8
  int v9; // eax

  Logger::TraceVerbose(L"%s started", L"CGroupPolicyObject::OpenLocalMachineGpo");
  (*(void (__fastcall **)(CGroupPolicyObject *))(*(_QWORD *)this + 32LL))(this);
  v2 = 2;
  v3 = CoInitializeEx(0, 2u);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v2 = 1;
    goto LABEL_5;
  }
  if ( v3 != -2147417850 )
  {
LABEL_10:
    v7 = v4;
    v8 = L"CoInitializeEx";
    goto LABEL_11;
  }
  Logger::TraceInformation(
    L"%s: CoInitializeEx(COINIT_APARTMENTTHREADED) failed with RPC_E_CHANGED_MODE. Trying to call CoUninitialize first the"
     "n CoInitializeEx again.",
    L"CGroupPolicyObject::OpenLocalMachineGpo");
  CoUninitialize();
  v4 = CoInitializeEx(0, 2u);
  if ( (v4 & 0x80000000) != 0 )
  {
    *((_DWORD *)this + 4) = 3;
    goto LABEL_10;
  }
LABEL_5:
  *((_DWORD *)this + 4) = v2;
  ppv = (LPVOID *)((char *)this + 8);
  Instance = CoCreateInstance(&CLSID_GroupPolicyObject, 0, 1u, &IID_IGroupPolicyObject, ppv);
  v4 = Instance;
  if ( Instance < 0 )
  {
    v7 = (unsigned int)Instance;
    v8 = L"CoCreateInstance";
LABEL_11:
    Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"CGroupPolicyObject::OpenLocalMachineGpo", v8, v7);
    goto LABEL_12;
  }
  v9 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)*ppv + 40LL))(*ppv, 1);
  v4 = v9;
  if ( v9 < 0 )
  {
    v7 = (unsigned int)v9;
    v8 = L"IGroupPolicyObject::OpenLocalMachineGPO";
    goto LABEL_11;
  }
LABEL_12:
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"CGroupPolicyObject::OpenLocalMachineGpo", v4);
  return v4;
}

```

## disassembly

```asm
0x140004b20  push    rbx
0x140004b22  push    rbp
0x140004b23  push    rsi
0x140004b24  push    rdi
0x140004b25  sub     rsp, 38h
0x140004b29  mov     rdi, rcx
0x140004b2c  lea     rbp, aCgrouppolicyob; "CGroupPolicyObject::OpenLocalMachineGpo"
0x140004b33  mov     rdx, rbp
0x140004b36  lea     rcx, aSStarted; "%s started"
0x140004b3d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x140004b42  mov     rax, [rdi]
0x140004b45  mov     rcx, rdi
0x140004b48  mov     rax, [rax+20h]
0x140004b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b51  mov     esi, 2
0x140004b56  xor     ecx, ecx; pvReserved
0x140004b58  mov     edx, esi; dwCoInit
0x140004b5a  call    cs:__imp_CoInitializeEx
0x140004b60  mov     ebx, eax
0x140004b62  test    eax, eax
0x140004b64  js      short loc_140004B6D
0x140004b66  mov     esi, 1
0x140004b6b  jmp     short loc_140004B9D
0x140004b6d  cmp     eax, 80010106h
0x140004b72  jnz     loc_140004C02
0x140004b78  mov     rdx, rbp
0x140004b7b  lea     rcx, aSCoinitializee; "%s: CoInitializeEx(COINIT_APARTMENTTHRE"...
0x140004b82  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x140004b87  call    cs:__imp_CoUninitialize
0x140004b8d  mov     edx, esi; dwCoInit
0x140004b8f  xor     ecx, ecx; pvReserved
0x140004b91  call    cs:__imp_CoInitializeEx
0x140004b97  mov     ebx, eax
0x140004b99  test    eax, eax
0x140004b9b  js      short loc_140004BFB
0x140004b9d  xor     edx, edx; pUnkOuter
0x140004b9f  mov     [rdi+10h], esi
0x140004ba2  add     rdi, 8
0x140004ba6  lea     r9, IID_IGroupPolicyObject; riid
0x140004bad  lea     rcx, CLSID_GroupPolicyObject; rclsid
0x140004bb4  mov     [rsp+58h+ppv], rdi; ppv
0x140004bb9  lea     r8d, [rdx+1]; dwClsContext
0x140004bbd  call    cs:__imp_CoCreateInstance
0x140004bc3  mov     ebx, eax
0x140004bc5  test    eax, eax
0x140004bc7  jns     short loc_140004BD5
0x140004bc9  mov     r9d, eax
0x140004bcc  lea     r8, aCocreateinstan; "CoCreateInstance"
0x140004bd3  jmp     short loc_140004C0C
0x140004bd5  mov     rcx, [rdi]
0x140004bd8  mov     edx, 1
0x140004bdd  mov     rax, [rcx]
0x140004be0  mov     rax, [rax+28h]
0x140004be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004be9  mov     ebx, eax
0x140004beb  test    eax, eax
0x140004bed  jns     short loc_140004C1B
0x140004bef  mov     r9d, eax
0x140004bf2  lea     r8, aIgrouppolicyob_0; "IGroupPolicyObject::OpenLocalMachineGPO"
0x140004bf9  jmp     short loc_140004C0C
0x140004bfb  mov     dword ptr [rdi+10h], 3
0x140004c02  mov     r9d, ebx
0x140004c05  lea     r8, aCoinitializeex; "CoInitializeEx"
0x140004c0c  mov     rdx, rbp
0x140004c0f  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x."
0x140004c16  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x140004c1b  mov     r8d, ebx
0x140004c1e  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x140004c25  mov     rdx, rbp
0x140004c28  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x140004c2d  mov     eax, ebx
0x140004c2f  add     rsp, 38h
0x140004c33  pop     rdi
0x140004c34  pop     rsi
0x140004c35  pop     rbp
0x140004c36  pop     rbx
0x140004c37  retn
```
