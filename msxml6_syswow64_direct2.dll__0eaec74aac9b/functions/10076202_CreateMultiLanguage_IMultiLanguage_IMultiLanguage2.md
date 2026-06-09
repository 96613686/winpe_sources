# CreateMultiLanguage(IMultiLanguage * *,IMultiLanguage2 * *)

- ea: `0x10076202`
- end: `0x100762cc`
- name: `?CreateMultiLanguage@@YGJPAPAUIMultiLanguage@@PAPAUIMultiLanguage2@@@Z`
- size: `202`
- prototype: `HRESULT __userpurge@<eax>(IMultiLanguage **ppMLang@<ecx>, IMultiLanguage2 **ppMLang2@<edx>)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1013efc9`
- `0x1016b130`

## callees

- `0x1003fc4a`
- `0x1003fc8f`
- `0x10040bb4`
- `0x10067b20`
- `0x10076202`
- `0x10076346`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x10076243`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x10076243`

## pseudocode

```c
HRESULT __fastcall CreateMultiLanguage(LPVOID *ppMLang, IUnknown **ppMLang2)
{
  HRESULT Instance; // eax
  int v5; // esi
  MutexLock lock; // [esp+Ch] [ebp-4h] BYREF

  if ( !*ppMLang || !*ppMLang2 )
  {
    MutexLock::MutexLock(&lock, g_pMutexSR);
    if ( !*ppMLang )
    {
      if ( *ppMLang2 )
        Instance = ((int (__thiscall *)(HRESULT (__stdcall *)(IUnknown *, const _GUID *, void **), IUnknown *, GUID *, LPVOID *))(*ppMLang2)->QueryInterface)(
                     (*ppMLang2)->QueryInterface,
                     *ppMLang2,
                     &IID_IMultiLanguage,
                     ppMLang);
      else
        Instance = CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage, ppMLang);
      v5 = Instance;
      if ( Instance < 0 )
        goto error;
      v5 = RegisterStaticUnknown((IUnknown **)ppMLang, "MLANG");
      if ( v5 < 0 )
      {
        release((IUnknown **)ppMLang);
error:
        MutexLock::Release(&lock);
        return v5;
      }
    }
    if ( !*ppMLang2
      && (**(int (__thiscall ***)(_DWORD, LPVOID, GUID *, IUnknown **))*ppMLang)(
           **(_DWORD **)*ppMLang,
           *ppMLang,
           &IID_IMultiLanguage2,
           ppMLang2) >= 0
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
0x10076202  mov     edi, edi
0x10076204  push    ebp; HRESULT
0x10076205  mov     ebp, esp
0x10076207  push    ppMLang; wchar_t *
0x10076208  push    ebx; ISAXLocator *
0x10076209  mov     ebx, ppMLang
0x1007620b  push    esi; this
0x1007620c  xor     esi, esi
0x1007620e  push    edi
0x1007620f  mov     edi, ppMLang2
0x10076211  cmp     [ebx], esi
0x10076213  jz      short loc_1007621D
0x10076215  cmp     [edi], esi
0x10076217  jnz     loc_100762C5
0x1007621d  push    ?g_pMutexSR@@3PAVCSMutex@@A; pMutex
0x10076223  lea     ppMLang, [ebp+lock]; this
0x10076226  call    ??0MutexLock@@QAE@PAVMutex@@@Z; MutexLock::MutexLock(Mutex *)
0x1007622b  cmp     [ebx], esi
0x1007622d  jnz     short loc_10076287
0x1007622f  mov     ppMLang, [edi]
0x10076231  push    ebx; ppv
0x10076232  push    offset _IID_IMultiLanguage; riid
0x10076237  test    ppMLang, ppMLang
0x10076239  jnz     short loc_1007624B
0x1007623b  push    1; dwClsContext
0x1007623d  push    esi; pUnkOuter
0x1007623e  push    offset _CLSID_CMultiLanguage; rclsid
0x10076243  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x10076249  jmp     short loc_1007625A
0x1007624b  mov     eax, [ppMLang]
0x1007624d  push    ppMLang
0x1007624e  mov     esi, [eax]
0x10076250  mov     ppMLang, esi; this
0x10076252  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10076258  call    esi
0x1007625a  mov     esi, eax
0x1007625c  test    esi, esi
0x1007625e  js      short error
0x10076260  mov     ppMLang2, offset aMlang; "MLANG"
0x10076265  mov     ppMLang, ebx; ppUnk
0x10076267  call    ?RegisterStaticUnknown@@YGJPAPAUIUnknown@@PBD@Z; RegisterStaticUnknown(IUnknown * *,char const *)
0x1007626c  mov     esi, eax
0x1007626e  test    esi, esi
0x10076270  jns     short loc_10076285
0x10076272  mov     ppMLang, ebx; ppref
0x10076274  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10076279  lea     ppMLang, [ebp+lock]; this
0x1007627c  call    ?Release@MutexLock@@QAEXXZ; MutexLock::Release(void)
0x10076281  mov     eax, esi
0x10076283  jmp     short loc_100762C7
0x10076285  xor     esi, esi
0x10076287  cmp     [edi], esi
0x10076289  jnz     short loc_100762BD
0x1007628b  mov     ppMLang, [ebx]
0x1007628d  push    edi
0x1007628e  push    offset _IID_IMultiLanguage2
0x10076293  push    ppMLang
0x10076294  mov     eax, [ppMLang]
0x10076296  mov     esi, [eax]
0x10076298  mov     ppMLang, esi; this
0x1007629a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100762a0  call    esi
0x100762a2  test    eax, eax
0x100762a4  js      short loc_100762BD
0x100762a6  mov     ppMLang2, offset aMlang2; "MLANG2"
0x100762ab  mov     ppMLang, edi; ppUnk
0x100762ad  call    ?RegisterStaticUnknown@@YGJPAPAUIUnknown@@PBD@Z; RegisterStaticUnknown(IUnknown * *,char const *)
0x100762b2  test    eax, eax
0x100762b4  jns     short loc_100762BD
0x100762b6  mov     ppMLang, edi; ppref
0x100762b8  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x100762bd  lea     ppMLang, [ebp+lock]; this
0x100762c0  call    ?Release@MutexLock@@QAEXXZ; MutexLock::Release(void)
0x100762c5  xor     eax, eax
0x100762c7  pop     edi
0x100762c8  pop     esi
0x100762c9  pop     ebx
0x100762ca  leave
0x100762cb  retn
```
