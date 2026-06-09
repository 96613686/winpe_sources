# CreateMultiLanguage(IMultiLanguage * *,IMultiLanguage2 * *)

- ea: `0x100761d2`
- end: `0x1007629c`
- name: `?CreateMultiLanguage@@YGJPAPAUIMultiLanguage@@PAPAUIMultiLanguage2@@@Z`
- size: `202`
- prototype: `HRESULT __userpurge@<eax>(IMultiLanguage **ppMLang@<ecx>, IMultiLanguage2 **ppMLang2@<edx>)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1013eeb9`
- `0x1016b040`

## callees

- `0x1003fcda`
- `0x1003fd1f`
- `0x10040c44`
- `0x10067bc0`
- `0x100761d2`
- `0x10076316`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x10076213`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x10076213`

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
0x100761d2  mov     edi, edi
0x100761d4  push    ebp; HRESULT
0x100761d5  mov     ebp, esp
0x100761d7  push    ppMLang; wchar_t *
0x100761d8  push    ebx; ISAXLocator *
0x100761d9  mov     ebx, ppMLang
0x100761db  push    esi; this
0x100761dc  xor     esi, esi
0x100761de  push    edi
0x100761df  mov     edi, ppMLang2
0x100761e1  cmp     [ebx], esi
0x100761e3  jz      short loc_100761ED
0x100761e5  cmp     [edi], esi
0x100761e7  jnz     loc_10076295
0x100761ed  push    ?g_pMutexSR@@3PAVCSMutex@@A; pMutex
0x100761f3  lea     ppMLang, [ebp+lock]; this
0x100761f6  call    ??0MutexLock@@QAE@PAVMutex@@@Z; MutexLock::MutexLock(Mutex *)
0x100761fb  cmp     [ebx], esi
0x100761fd  jnz     short loc_10076257
0x100761ff  mov     ppMLang, [edi]
0x10076201  push    ebx; ppv
0x10076202  push    offset _IID_IMultiLanguage; riid
0x10076207  test    ppMLang, ppMLang
0x10076209  jnz     short loc_1007621B
0x1007620b  push    1; dwClsContext
0x1007620d  push    esi; pUnkOuter
0x1007620e  push    offset _CLSID_CMultiLanguage; rclsid
0x10076213  call    ds:__imp__CoCreateInstance@20; CoCreateInstance(x,x,x,x,x)
0x10076219  jmp     short loc_1007622A
0x1007621b  mov     eax, [ppMLang]
0x1007621d  push    ppMLang
0x1007621e  mov     esi, [eax]
0x10076220  mov     ppMLang, esi; this
0x10076222  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10076228  call    esi
0x1007622a  mov     esi, eax
0x1007622c  test    esi, esi
0x1007622e  js      short error
0x10076230  mov     ppMLang2, offset aMlang; "MLANG"
0x10076235  mov     ppMLang, ebx; ppUnk
0x10076237  call    ?RegisterStaticUnknown@@YGJPAPAUIUnknown@@PBD@Z; RegisterStaticUnknown(IUnknown * *,char const *)
0x1007623c  mov     esi, eax
0x1007623e  test    esi, esi
0x10076240  jns     short loc_10076255
0x10076242  mov     ppMLang, ebx; ppref
0x10076244  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x10076249  lea     ppMLang, [ebp+lock]; this
0x1007624c  call    ?Release@MutexLock@@QAEXXZ; MutexLock::Release(void)
0x10076251  mov     eax, esi
0x10076253  jmp     short loc_10076297
0x10076255  xor     esi, esi
0x10076257  cmp     [edi], esi
0x10076259  jnz     short loc_1007628D
0x1007625b  mov     ppMLang, [ebx]
0x1007625d  push    edi
0x1007625e  push    offset _IID_IMultiLanguage2
0x10076263  push    ppMLang
0x10076264  mov     eax, [ppMLang]
0x10076266  mov     esi, [eax]
0x10076268  mov     ppMLang, esi; this
0x1007626a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10076270  call    esi
0x10076272  test    eax, eax
0x10076274  js      short loc_1007628D
0x10076276  mov     ppMLang2, offset aMlang2; "MLANG2"
0x1007627b  mov     ppMLang, edi; ppUnk
0x1007627d  call    ?RegisterStaticUnknown@@YGJPAPAUIUnknown@@PBD@Z; RegisterStaticUnknown(IUnknown * *,char const *)
0x10076282  test    eax, eax
0x10076284  jns     short loc_1007628D
0x10076286  mov     ppMLang, edi; ppref
0x10076288  call    ?release@@YGXPAPAUIUnknown@@@Z; release(IUnknown * *)
0x1007628d  lea     ppMLang, [ebp+lock]; this
0x10076290  call    ?Release@MutexLock@@QAEXXZ; MutexLock::Release(void)
0x10076295  xor     eax, eax
0x10076297  pop     edi
0x10076298  pop     esi
0x10076299  pop     ebx
0x1007629a  leave
0x1007629b  retn
```
