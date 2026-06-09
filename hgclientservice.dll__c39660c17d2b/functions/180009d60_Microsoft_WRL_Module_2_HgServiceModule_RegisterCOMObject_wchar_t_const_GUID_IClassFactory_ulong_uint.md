# Microsoft::WRL::Module<2,HgServiceModule>::RegisterCOMObject(wchar_t const *,_GUID *,IClassFactory * *,ulong *,uint)

- ea: `0x180009d60`
- end: `0x180009df9`
- name: `?RegisterCOMObject@?$Module@$01VHgServiceModule@@@WRL@Microsoft@@UEAAJPEB_WPEAU_GUID@@PEAPEAUIClassFactory@@PEAKI@Z`
- size: `153`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009d60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x180009dc0`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x180009dc0`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180009dae`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180009dae`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180009dd6`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180009dd6`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Module<2,HgServiceModule>::RegisterCOMObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6)
{
  HRESULT v6; // edi
  __int64 v7; // rbp
  HRESULT v10; // eax
  __int64 i; // rsi

  v6 = 0;
  v7 = 0;
  if ( a6 )
  {
    while ( v6 >= 0 )
    {
      v10 = CoRegisterClassObject(
              (const IID *const)(a3 + 16LL * (unsigned int)v7),
              *(LPUNKNOWN *)(a4 + 8 * v7),
              4u,
              5u,
              (LPDWORD)(a5 + 4 * v7));
      v7 = (unsigned int)(v7 + 1);
      v6 = v10;
      if ( (unsigned int)v7 >= a6 )
      {
        if ( v10 < 0 )
          break;
        goto LABEL_5;
      }
    }
  }
  else
  {
LABEL_5:
    v6 = CoResumeClassObjects();
    if ( v6 >= 0 )
      return (unsigned int)v6;
  }
  for ( i = 0; (unsigned int)i < (unsigned int)v7; i = (unsigned int)(i + 1) )
  {
    CoRevokeClassObject(*(_DWORD *)(a5 + 4 * i));
    *(_DWORD *)(a5 + 4 * i) = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009d60  push    rbx
0x180009d62  push    rbp
0x180009d63  push    rsi
0x180009d64  push    rdi
0x180009d65  push    r14
0x180009d67  push    r15
0x180009d69  sub     rsp, 38h
0x180009d6d  mov     ebx, [rsp+68h+arg_28]
0x180009d74  xor     edi, edi
0x180009d76  mov     r14, [rsp+68h+arg_20]
0x180009d7e  xor     ebp, ebp
0x180009d80  mov     rsi, r9
0x180009d83  mov     r15, r8
0x180009d86  test    ebx, ebx
0x180009d88  jz      short loc_180009DC0
0x180009d8a  test    edi, edi
0x180009d8c  js      short loc_180009DCC
0x180009d8e  mov     rdx, [rsi+rbp*8]; pUnk
0x180009d92  lea     rax, [r14+rbp*4]
0x180009d96  mov     r9d, 5; flags
0x180009d9c  mov     ecx, ebp
0x180009d9e  shl     rcx, 4
0x180009da2  add     rcx, r15; rclsid
0x180009da5  mov     [rsp+68h+lpdwRegister], rax; lpdwRegister
0x180009daa  lea     r8d, [r9-1]; dwClsContext
0x180009dae  call    cs:__imp_CoRegisterClassObject
0x180009db4  inc     ebp
0x180009db6  mov     edi, eax
0x180009db8  cmp     ebp, ebx
0x180009dba  jb      short loc_180009D8A
0x180009dbc  test    eax, eax
0x180009dbe  js      short loc_180009DCC
0x180009dc0  call    cs:__imp_CoResumeClassObjects
0x180009dc6  mov     edi, eax
0x180009dc8  test    eax, eax
0x180009dca  jns     short loc_180009DEA
0x180009dcc  xor     esi, esi
0x180009dce  test    ebp, ebp
0x180009dd0  jz      short loc_180009DEA
0x180009dd2  mov     ecx, [r14+rsi*4]; dwRegister
0x180009dd6  call    cs:__imp_CoRevokeClassObject
0x180009ddc  mov     dword ptr [r14+rsi*4], 0
0x180009de4  inc     esi
0x180009de6  cmp     esi, ebp
0x180009de8  jb      short loc_180009DD2
0x180009dea  mov     eax, edi
0x180009dec  add     rsp, 38h
0x180009df0  pop     r15
0x180009df2  pop     r14
0x180009df4  pop     rdi
0x180009df5  pop     rsi
0x180009df6  pop     rbp
0x180009df7  pop     rbx
0x180009df8  retn
```
