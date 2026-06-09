# CreateMultiLanguage(IMultiLanguage * *)

- ea: `0x18000bb50`
- end: `0x18000bbf8`
- name: `?CreateMultiLanguage@@YAJPEAPEAUIMultiLanguage@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bc00`
- `0x18000be30`

## callees

- `0x18000bb50`

## import_xrefs

- `KERNEL32!Sleep` at `0x18000bbed`
- `KERNEL32!Sleep` at `0x18000bbed`
- `ole32!CoCreateInstance` at `0x18000bb9c`
- `ole32!CoCreateInstance` at `0x18000bbc5`
- `ole32!CoCreateInstance` at `0x18000bb9c`
- `ole32!CoCreateInstance` at `0x18000bbc5`

## pseudocode

```c
__int64 __fastcall CreateMultiLanguage(LPVOID *ppv)
{
  unsigned int v2; // ebx
  HRESULT Instance; // [rsp+40h] [rbp+8h]

  v2 = 0;
  Instance = 0;
  if ( !*ppv )
  {
    while ( _InterlockedCompareExchange(&g_fMultiLanguageInitLock, 1, 0) )
      Sleep(0);
    if ( !*ppv )
    {
      Instance = CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage2, ppv);
      if ( Instance < 0 )
      {
        _mm_lfence();
        Instance = CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage, ppv);
      }
    }
    _InterlockedExchange(&g_fMultiLanguageInitLock, 0);
    return (unsigned int)Instance;
  }
  return v2;
}

```

## disassembly

```asm
0x18000bb50  mov     [rsp+arg_10], rbx
0x18000bb55  mov     [rsp+arg_18], rsi
0x18000bb5a  push    rdi
0x18000bb5b  sub     rsp, 30h
0x18000bb5f  mov     rdi, rcx
0x18000bb62  xor     ebx, ebx
0x18000bb64  mov     [rsp+38h+arg_0], ebx
0x18000bb68  cmp     [rcx], rbx
0x18000bb6b  jnz     short loc_18000BBD9
0x18000bb6d  mov     esi, 1
0x18000bb72  xor     eax, eax
0x18000bb74  lock cmpxchg cs:?g_fMultiLanguageInitLock@@3JC, esi; long volatile g_fMultiLanguageInitLock
0x18000bb7c  jnz     short loc_18000BBEB
0x18000bb7e  cmp     qword ptr [rdi], 0
0x18000bb82  jnz     short loc_18000BBCF
0x18000bb84  mov     [rsp+38h+ppv], rdi; ppv
0x18000bb89  lea     r9, IID_IMultiLanguage2; riid
0x18000bb90  mov     r8d, esi; dwClsContext
0x18000bb93  xor     edx, edx; pUnkOuter
0x18000bb95  lea     rcx, CLSID_CMultiLanguage; rclsid
0x18000bb9c  call    cs:__imp_CoCreateInstance
0x18000bba2  mov     [rsp+38h+arg_0], eax
0x18000bba6  test    eax, eax
0x18000bba8  jns     short loc_18000BBCF
0x18000bbaa  lfence
0x18000bbad  mov     [rsp+38h+ppv], rdi; ppv
0x18000bbb2  lea     r9, IID_IMultiLanguage; riid
0x18000bbb9  mov     r8d, esi; dwClsContext
0x18000bbbc  xor     edx, edx; pUnkOuter
0x18000bbbe  lea     rcx, CLSID_CMultiLanguage; rclsid
0x18000bbc5  call    cs:__imp_CoCreateInstance
0x18000bbcb  mov     [rsp+38h+arg_0], eax
0x18000bbcf  xchg    ebx, cs:?g_fMultiLanguageInitLock@@3JC; long volatile g_fMultiLanguageInitLock
0x18000bbd5  mov     ebx, [rsp+38h+arg_0]
0x18000bbd9  mov     eax, ebx
0x18000bbdb  mov     rbx, [rsp+38h+arg_10]
0x18000bbe0  mov     rsi, [rsp+38h+arg_18]
0x18000bbe5  add     rsp, 30h
0x18000bbe9  pop     rdi
0x18000bbea  retn
0x18000bbeb  xor     ecx, ecx; dwMilliseconds
0x18000bbed  call    cs:__imp_Sleep
0x18000bbf3  jmp     loc_18000BB72
0x1801ada10  push    rbp
0x1801ada12  sub     rsp, 30h
0x1801ada16  mov     rbp, rdx
0x1801ada19  xor     eax, eax
0x1801ada1b  xchg    eax, cs:?g_fMultiLanguageInitLock@@3JC; long volatile g_fMultiLanguageInitLock
0x1801ada21  add     rsp, 30h
0x1801ada25  pop     rbp
0x1801ada26  retn
```
