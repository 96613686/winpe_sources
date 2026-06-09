# CreateMultiLanguage(IMultiLanguage * *,IMultiLanguage2 * *)

- ea: `0x1800d6d34`
- end: `0x1800d6e3f`
- name: `?CreateMultiLanguage@@YAJPEAPEAUIMultiLanguage@@PEAPEAUIMultiLanguage2@@@Z`
- size: `267`
- prototype: `HRESULT __fastcall(IMultiLanguage **ppMLang, IMultiLanguage2 **ppMLang2)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801611c4`
- `0x180179110`

## callees

- `0x180019e20`
- `0x18005ed7c`
- `0x180060074`
- `0x1800d6d34`
- `0x1800d6e48`
- `0x18018c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d6d91`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800d6d91`

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
0x1800d6d34  mov     [rsp+arg_8], rbx
0x1800d6d39  mov     [rsp+arg_10], rsi
0x1800d6d3e  push    rdi
0x1800d6d3f  sub     rsp, 30h
0x1800d6d43  cmp     qword ptr [ppMLang], 0
0x1800d6d47  mov     rbx, ppMLang2
0x1800d6d4a  mov     rdi, ppMLang
0x1800d6d4d  jz      short loc_1800D6D59
0x1800d6d4f  cmp     qword ptr [ppMLang2], 0
0x1800d6d53  jnz     loc_1800D6E2C
0x1800d6d59  mov     ppMLang2, cs:?g_pMutexSR@@3PEAVCSMutex@@EA; pMutex
0x1800d6d60  lea     ppMLang, [rsp+38h+lock]; this
0x1800d6d65  call    ??0MutexLock@@QEAA@PEAVMutex@@@Z; MutexLock::MutexLock(Mutex *)
0x1800d6d6a  cmp     qword ptr [rdi], 0
0x1800d6d6e  jnz     short loc_1800D6DE5
0x1800d6d70  mov     ppMLang, [rbx]
0x1800d6d73  test    ppMLang, ppMLang
0x1800d6d76  jnz     short loc_1800D6D9F
0x1800d6d78  lea     r8d, [ppMLang+1]; dwClsContext
0x1800d6d7c  mov     [rsp+38h+ppv], rdi; ppv
0x1800d6d81  lea     ppMLang, CLSID_CMultiLanguage; rclsid
0x1800d6d88  xor     edx, edx; pUnkOuter
0x1800d6d8a  lea     r9, IID_IMultiLanguage; riid
0x1800d6d91  call    cs:__imp_CoCreateInstance
0x1800d6d98  nop     dword ptr [rax+rax+00h]
0x1800d6d9d  jmp     short loc_1800D6DB4
0x1800d6d9f  mov     rax, [ppMLang]
0x1800d6da2  lea     ppMLang2, IID_IMultiLanguage
0x1800d6da9  mov     r8, rdi
0x1800d6dac  mov     rax, [rax]
0x1800d6daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6db4  mov     esi, eax
0x1800d6db6  test    eax, eax
0x1800d6db8  js      short $error_3
0x1800d6dba  lea     ppMLang2, aMlang; "MLANG"
0x1800d6dc1  mov     ppMLang, rdi; ppUnk
0x1800d6dc4  call    ?RegisterStaticUnknown@@YAJPEAPEAUIUnknown@@PEBD@Z; RegisterStaticUnknown(IUnknown * *,char const *)
0x1800d6dc9  mov     esi, eax
0x1800d6dcb  test    eax, eax
0x1800d6dcd  jns     short loc_1800D6DE5
0x1800d6dcf  mov     ppMLang, rdi; ppref
0x1800d6dd2  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800d6dd7  lea     ppMLang, [rsp+38h+lock]; this
0x1800d6ddc  call    ?Release@MutexLock@@QEAAXXZ; MutexLock::Release(void)
0x1800d6de1  mov     eax, esi
0x1800d6de3  jmp     short loc_1800D6E2E
0x1800d6de5  cmp     qword ptr [rbx], 0
0x1800d6de9  jnz     short loc_1800D6E22
0x1800d6deb  mov     ppMLang, [rdi]
0x1800d6dee  lea     ppMLang2, IID_IMultiLanguage2
0x1800d6df5  mov     r8, rbx
0x1800d6df8  mov     rax, [ppMLang]
0x1800d6dfb  mov     rax, [rax]
0x1800d6dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d6e03  test    eax, eax
0x1800d6e05  js      short loc_1800D6E22
0x1800d6e07  lea     ppMLang2, aMlang2; "MLANG2"
0x1800d6e0e  mov     ppMLang, rbx; ppUnk
0x1800d6e11  call    ?RegisterStaticUnknown@@YAJPEAPEAUIUnknown@@PEBD@Z; RegisterStaticUnknown(IUnknown * *,char const *)
0x1800d6e16  test    eax, eax
0x1800d6e18  jns     short loc_1800D6E22
0x1800d6e1a  mov     ppMLang, rbx; ppref
0x1800d6e1d  call    ?release@@YAXPEAPEAUIUnknown@@@Z; release(IUnknown * *)
0x1800d6e22  lea     ppMLang, [rsp+38h+lock]; this
0x1800d6e27  call    ?Release@MutexLock@@QEAAXXZ; MutexLock::Release(void)
0x1800d6e2c  xor     eax, eax
0x1800d6e2e  mov     rbx, [rsp+38h+arg_8]
0x1800d6e33  mov     rsi, [rsp+38h+arg_10]
0x1800d6e38  add     rsp, 30h
0x1800d6e3c  pop     rdi
0x1800d6e3d  retn
```
