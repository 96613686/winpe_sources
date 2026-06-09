# CSyncContext::CreateInstance(ulong,IDataObject *,_GUID const &,void * *)

- ea: `0x180003e70`
- end: `0x180003f77`
- name: `?CreateInstance@CSyncContext@@SAJKPEAUIDataObject@@AEBU_GUID@@PEAPEAX@Z`
- size: `263`
- prototype: `__int64 __fastcall(unsigned int, struct IDataObject *, const struct _GUID *, void **)`
- caller_count: `6`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180015b8c`
- `0x1800160a8`
- `0x1800161d0`
- `0x180019850`
- `0x18001f57c`
- `0x180023a20`

## callees

- `0x180003e70`
- `0x180003f80`
- `0x1800041f0`
- `0x180004470`
- `0x18000793c`
- `0x18000c1e8`
- `0x18003e260`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003eea`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003eea`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180003ecf`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180003ecf`

## pseudocode

```c
__int64 __fastcall CSyncContext::CreateInstance(
        unsigned int a1,
        struct IDataObject *a2,
        const struct _GUID *a3,
        void **a4)
{
  CSyncContext *v7; // rax
  CSyncContext *v8; // rdi
  HRESULT Instance; // ebx
  GUID pguid; // [rsp+20h] [rbp-38h] BYREF

  *a4 = 0;
  v7 = (CSyncContext *)operator new(0x90u);
  if ( !v7 )
    return 2147942414LL;
  v8 = CSyncContext::CSyncContext(v7, a1, a2);
  if ( !v8 )
    return 2147942414LL;
  pguid = 0;
  Instance = CoCreateGuid(&pguid);
  if ( Instance >= 0 )
  {
    Instance = StringFromGUID2(&pguid, (LPOLESTR)v8 + 32, 39);
    if ( Instance >= 0 )
    {
      Instance = CSyncItemDescriptors::CreateInstance((struct CSyncItemDescriptors **)v8 + 5);
      if ( Instance >= 0 )
      {
        Instance = CSyncItemLog::CreateInstance((struct CSyncItemLog **)v8 + 6);
        if ( Instance >= 0 )
        {
          Instance = CSyncContext::_CollectItems(v8);
          if ( Instance >= 0 )
          {
            Instance = CSyncContext::_SelectItems(v8);
            if ( Instance >= 0 )
              Instance = (**(__int64 (__fastcall ***)(CSyncContext *, GUID *, void **))v8)(
                           v8,
                           &GUID_b464955c_9277_4657_a3dc_99a32c76c6f3,
                           a4);
          }
        }
      }
    }
  }
  (*(void (__fastcall **)(CSyncContext *))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180003e70  push    rbx
0x180003e72  push    rsi
0x180003e73  push    rdi
0x180003e74  sub     rsp, 40h
0x180003e78  mov     rax, cs:__security_cookie
0x180003e7f  xor     rax, rsp
0x180003e82  mov     [rsp+58h+var_28], rax
0x180003e87  mov     ebx, ecx
0x180003e89  mov     qword ptr [r9], 0
0x180003e90  mov     ecx, 90h; Size
0x180003e95  mov     rsi, r9
0x180003e98  mov     rdi, rdx
0x180003e9b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003ea0  test    rax, rax
0x180003ea3  jz      loc_180003F5D
0x180003ea9  mov     r8, rdi; struct IDataObject *
0x180003eac  mov     edx, ebx; unsigned int
0x180003eae  mov     rcx, rax; this
0x180003eb1  call    ??0CSyncContext@@AEAA@KPEAUIDataObject@@@Z; CSyncContext::CSyncContext(ulong,IDataObject *)
0x180003eb6  mov     rdi, rax
0x180003eb9  test    rax, rax
0x180003ebc  jz      loc_180003F5D
0x180003ec2  xorps   xmm0, xmm0
0x180003ec5  lea     rcx, [rsp+58h+pguid]; pguid
0x180003eca  movups  xmmword ptr [rsp+58h+pguid.Data1], xmm0
0x180003ecf  call    cs:__imp_CoCreateGuid
0x180003ed5  mov     ebx, eax
0x180003ed7  test    eax, eax
0x180003ed9  js      short loc_180003F4A
0x180003edb  lea     rdx, [rdi+40h]; lpsz
0x180003edf  mov     r8d, 27h ; '''; cchMax
0x180003ee5  lea     rcx, [rsp+58h+pguid]; rguid
0x180003eea  call    cs:__imp_StringFromGUID2
0x180003ef0  mov     ebx, eax
0x180003ef2  test    eax, eax
0x180003ef4  js      short loc_180003F4A
0x180003ef6  lea     rcx, [rdi+28h]; struct CSyncItemDescriptors **
0x180003efa  call    ?CreateInstance@CSyncItemDescriptors@@SAJPEAPEAV1@@Z; CSyncItemDescriptors::CreateInstance(CSyncItemDescriptors * *)
0x180003eff  mov     ebx, eax
0x180003f01  test    eax, eax
0x180003f03  js      short loc_180003F4A
0x180003f05  lea     rcx, [rdi+30h]; struct CSyncItemLog **
0x180003f09  call    ?CreateInstance@CSyncItemLog@@SAJPEAPEAV1@@Z; CSyncItemLog::CreateInstance(CSyncItemLog * *)
0x180003f0e  mov     ebx, eax
0x180003f10  test    eax, eax
0x180003f12  js      short loc_180003F4A
0x180003f14  mov     rcx, rdi; this
0x180003f17  call    ?_CollectItems@CSyncContext@@AEAAJXZ; CSyncContext::_CollectItems(void)
0x180003f1c  mov     ebx, eax
0x180003f1e  test    eax, eax
0x180003f20  js      short loc_180003F4A
0x180003f22  mov     rcx, rdi; this
0x180003f25  call    ?_SelectItems@CSyncContext@@AEAAJXZ; CSyncContext::_SelectItems(void)
0x180003f2a  mov     ebx, eax
0x180003f2c  test    eax, eax
0x180003f2e  js      short loc_180003F4A
0x180003f30  mov     rax, [rdi]
0x180003f33  lea     rdx, _GUID_b464955c_9277_4657_a3dc_99a32c76c6f3
0x180003f3a  mov     r8, rsi
0x180003f3d  mov     rcx, rdi
0x180003f40  mov     rax, [rax]
0x180003f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f48  mov     ebx, eax
0x180003f4a  mov     rax, [rdi]
0x180003f4d  mov     rcx, rdi
0x180003f50  mov     rax, [rax+10h]
0x180003f54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f59  mov     eax, ebx
0x180003f5b  jmp     short loc_180003F62
0x180003f5d  mov     eax, 8007000Eh
0x180003f62  mov     rcx, [rsp+58h+var_28]
0x180003f67  xor     rcx, rsp; StackCookie
0x180003f6a  call    __security_check_cookie
0x180003f6f  add     rsp, 40h
0x180003f73  pop     rdi
0x180003f74  pop     rsi
0x180003f75  pop     rbx
0x180003f76  retn
```
