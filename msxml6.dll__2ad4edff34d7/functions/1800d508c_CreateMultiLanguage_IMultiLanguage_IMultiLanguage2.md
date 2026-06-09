# CreateMultiLanguage(IMultiLanguage * *,IMultiLanguage2 * *)

- ea: `0x1800d508c`
- end: `0x1800d5190`
- name: `?CreateMultiLanguage@@YAJPEAPEAUIMultiLanguage@@PEAPEAUIMultiLanguage2@@@Z`
- size: `260`
- prototype: `HRESULT __fastcall(IMultiLanguage **ppMLang, IMultiLanguage2 **ppMLang2)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18015d88c`
- `0x1801754e0`

## callees

- `0x18000d7d0`
- `0x18005f3dc`
- `0x18005fbe0`
- `0x1800d508c`
- `0x1800d5198`
- `0x180188010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d50e9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d50e9`

## pseudocode

```c
__int64 __fastcall CreateMultiLanguage(IMultiLanguage **ppMLang, IUnknown **ppMLang2)
{
  HRESULT Instance; // eax
  int v5; // esi
  MutexLock lock; // [rsp+40h] [rbp+8h] BYREF

  if ( !*ppMLang || !*ppMLang2 )
  {
    MutexLock::MutexLock(&lock, g_pMutexSR);
    if ( !*ppMLang )
    {
      if ( *ppMLang2 )
        Instance = (*ppMLang2)->QueryInterface(*ppMLang2, &IID_IMultiLanguage, (void **)ppMLang);
      else
        Instance = CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage, (LPVOID *)ppMLang);
      v5 = Instance;
      if ( Instance < 0 )
        goto $error_3;
      v5 = RegisterStaticUnknown(ppMLang, "MLANG");
      if ( v5 < 0 )
      {
        release(ppMLang);
$error_3:
        MutexLock::Release(&lock);
        return (unsigned int)v5;
      }
    }
    if ( !*ppMLang2
      && (*ppMLang)->QueryInterface(*ppMLang, &IID_IMultiLanguage2, (void **)ppMLang2) >= 0
      && RegisterStaticUnknown(ppMLang2, "MLANG2") < 0 )
    {
      release(ppMLang2);
    }
    MutexLock::Release(&lock);
  }
  return 0;
}

```

## disassembly

```asm
0x1800d508c  mov     [rsp+arg_8], rbx
0x1800d5091  mov     [rsp+arg_10], rsi
0x1800d5096  push    rdi
0x1800d5097  sub     rsp, 30h
0x1800d509b  cmp     qword ptr [ppMLang], 0
0x1800d509f  mov     rbx, ppMLang2
0x1800d50a2  mov     rdi, ppMLang
0x1800d50a5  jz      short loc_1800D50B1
0x1800d50a7  cmp     qword ptr [ppMLang2], 0
0x1800d50ab  jnz     loc_1800D517E
0x1800d50b1  mov     ppMLang2, cs:?g_pMutexSR@@3PEAVCSMutex@@EA; pMutex
0x1800d50b8  lea     ppMLang, [rsp+38h+lock]; this
0x1800d50bd  call    ??0MutexLock@@QEAA@PEAVMutex@@@Z; MutexLock::MutexLock(Mutex *)
0x1800d50c2  cmp     qword ptr [rdi], 0
0x1800d50c6  jnz     short loc_1800D5137
0x1800d50c8  mov     ppMLang, [rbx]
0x1800d50cb  test    ppMLang, ppMLang
0x1800d50ce  jnz     short loc_1800D50F1
0x1800d50d0  lea     r8d, [ppMLang+1]; dwClsContext
0x1800d50d4  mov     [rsp+38h+ppv], rdi; ppv
0x1800d50d9  lea     ppMLang, CLSID_CMultiLanguage; rclsid
0x1800d50e0  xor     edx, edx; pUnkOuter
0x1800d50e2  lea     r9, IID_IMultiLanguage; riid
0x1800d50e9  call    cs:__imp_CoCreateInstance
0x1800d50ef  jmp     short loc_1800D5106
0x1800d50f1  mov     rax, [ppMLang]
0x1800d50f4  lea     ppMLang2, IID_IMultiLanguage
0x1800d50fb  mov     r8, rdi
0x1800d50fe  mov     rax, [rax]
0x1800d5101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5106  mov     esi, eax
0x1800d5108  test    eax, eax
0x1800d510a  js      short $error_3
0x1800d510c  lea     ppMLang2, aMlang; "MLANG"
0x1800d5113  mov     ppMLang, rdi; ppUnk
0x1800d5116  call    ?RegisterStaticUnknown@@YAJPEAPEAUIUnknown@@PEBD@Z; RegisterStaticUnknown(IUnknown * *,char const *)
0x1800d511b  mov     esi, eax
0x1800d511d  test    eax, eax
0x1800d511f  jns     short loc_1800D5137
0x1800d5121  mov     ppMLang, rdi; ppref
0x1800d5124  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800d5129  lea     ppMLang, [rsp+38h+lock]; this
0x1800d512e  call    ?Release@MutexLock@@QEAAXXZ; MutexLock::Release(void)
0x1800d5133  mov     eax, esi
0x1800d5135  jmp     short loc_1800D5180
0x1800d5137  cmp     qword ptr [rbx], 0
0x1800d513b  jnz     short loc_1800D5174
0x1800d513d  mov     ppMLang, [rdi]
0x1800d5140  lea     ppMLang2, IID_IMultiLanguage2
0x1800d5147  mov     r8, rbx
0x1800d514a  mov     rax, [ppMLang]
0x1800d514d  mov     rax, [rax]
0x1800d5150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5155  test    eax, eax
0x1800d5157  js      short loc_1800D5174
0x1800d5159  lea     ppMLang2, aMlang2; "MLANG2"
0x1800d5160  mov     ppMLang, rbx; ppUnk
0x1800d5163  call    ?RegisterStaticUnknown@@YAJPEAPEAUIUnknown@@PEBD@Z; RegisterStaticUnknown(IUnknown * *,char const *)
0x1800d5168  test    eax, eax
0x1800d516a  jns     short loc_1800D5174
0x1800d516c  mov     ppMLang, rbx; ppref
0x1800d516f  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800d5174  lea     ppMLang, [rsp+38h+lock]; this
0x1800d5179  call    ?Release@MutexLock@@QEAAXXZ; MutexLock::Release(void)
0x1800d517e  xor     eax, eax
0x1800d5180  mov     rbx, [rsp+38h+arg_8]
0x1800d5185  mov     rsi, [rsp+38h+arg_10]
0x1800d518a  add     rsp, 30h
0x1800d518e  pop     rdi
0x1800d518f  retn
```
