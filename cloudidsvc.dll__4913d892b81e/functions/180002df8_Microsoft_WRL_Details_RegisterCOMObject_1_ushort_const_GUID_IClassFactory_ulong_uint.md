# Microsoft::WRL::Details::RegisterCOMObject<1>(ushort const *,_GUID *,IClassFactory * *,ulong *,uint)

- ea: `0x180002df8`
- end: `0x180002e8c`
- name: `??$RegisterCOMObject@$00@Details@WRL@Microsoft@@YAJPEBGPEAU_GUID@@PEAPEAUIClassFactory@@PEAKI@Z`
- size: `148`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800069e0`

## callees

- `0x180002df8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x180002e53`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x180002e53`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180002e41`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x180002e41`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180002e69`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x180002e69`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RegisterCOMObject<1>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5)
{
  HRESULT v5; // edi
  __int64 v6; // rbp
  HRESULT v10; // eax
  __int64 i; // rsi

  v5 = 0;
  v6 = 0;
  if ( a5 )
  {
    while ( v5 >= 0 )
    {
      v10 = CoRegisterClassObject(
              (const IID *const)(a2 + 16LL * (unsigned int)v6),
              *(LPUNKNOWN *)(a3 + 8 * v6),
              4u,
              5u,
              (LPDWORD)(a4 + 4 * v6));
      v6 = (unsigned int)(v6 + 1);
      v5 = v10;
      if ( (unsigned int)v6 >= a5 )
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
    v5 = CoResumeClassObjects();
    if ( v5 >= 0 )
      return (unsigned int)v5;
  }
  for ( i = 0; (unsigned int)i < (unsigned int)v6; i = (unsigned int)(i + 1) )
  {
    CoRevokeClassObject(*(_DWORD *)(a4 + 4 * i));
    *(_DWORD *)(a4 + 4 * i) = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002df8  push    rbx
0x180002dfa  push    rbp
0x180002dfb  push    rsi
0x180002dfc  push    rdi
0x180002dfd  push    r14
0x180002dff  push    r15
0x180002e01  sub     rsp, 38h
0x180002e05  mov     ebx, [rsp+68h+arg_20]
0x180002e0c  xor     edi, edi
0x180002e0e  xor     ebp, ebp
0x180002e10  mov     r14, r9
0x180002e13  mov     rsi, r8
0x180002e16  mov     r15, rdx
0x180002e19  test    ebx, ebx
0x180002e1b  jz      short loc_180002E53
0x180002e1d  test    edi, edi
0x180002e1f  js      short loc_180002E5F
0x180002e21  mov     rdx, [rsi+rbp*8]; pUnk
0x180002e25  lea     rax, [r14+rbp*4]
0x180002e29  mov     r9d, 5; flags
0x180002e2f  mov     ecx, ebp
0x180002e31  shl     rcx, 4
0x180002e35  add     rcx, r15; rclsid
0x180002e38  mov     [rsp+68h+lpdwRegister], rax; lpdwRegister
0x180002e3d  lea     r8d, [r9-1]; dwClsContext
0x180002e41  call    cs:__imp_CoRegisterClassObject
0x180002e47  inc     ebp
0x180002e49  mov     edi, eax
0x180002e4b  cmp     ebp, ebx
0x180002e4d  jb      short loc_180002E1D
0x180002e4f  test    eax, eax
0x180002e51  js      short loc_180002E5F
0x180002e53  call    cs:__imp_CoResumeClassObjects
0x180002e59  mov     edi, eax
0x180002e5b  test    eax, eax
0x180002e5d  jns     short loc_180002E7D
0x180002e5f  xor     esi, esi
0x180002e61  test    ebp, ebp
0x180002e63  jz      short loc_180002E7D
0x180002e65  mov     ecx, [r14+rsi*4]; dwRegister
0x180002e69  call    cs:__imp_CoRevokeClassObject
0x180002e6f  mov     dword ptr [r14+rsi*4], 0
0x180002e77  inc     esi
0x180002e79  cmp     esi, ebp
0x180002e7b  jb      short loc_180002E65
0x180002e7d  mov     eax, edi
0x180002e7f  add     rsp, 38h
0x180002e83  pop     r15
0x180002e85  pop     r14
0x180002e87  pop     rdi
0x180002e88  pop     rsi
0x180002e89  pop     rbp
0x180002e8a  pop     rbx
0x180002e8b  retn
```
