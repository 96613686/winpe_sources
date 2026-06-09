# CSyncContext::_Initialize(void)

- ea: `0x180003dd4`
- end: `0x180003e5d`
- name: `?_Initialize@CSyncContext@@AEAAJXZ`
- size: `137`
- prototype: `__int64 __fastcall(CSyncContext *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800077f4`

## callees

- `0x180003dd4`
- `0x180003f80`
- `0x1800041f0`
- `0x180004470`
- `0x18003e260`
- `0x18004c670`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003e12`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180003e12`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180003df9`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180003df9`

## pseudocode

```c
HRESULT __fastcall CSyncContext::_Initialize(CSyncContext *this)
{
  HRESULT result; // eax
  GUID pguid; // [rsp+20h] [rbp-28h] BYREF

  pguid = 0;
  result = CoCreateGuid(&pguid);
  if ( result >= 0 )
  {
    result = StringFromGUID2(&pguid, (LPOLESTR)this + 32, 39);
    if ( result >= 0 )
    {
      result = CSyncItemDescriptors::CreateInstance((struct CSyncItemDescriptors **)this + 5);
      if ( result >= 0 )
      {
        result = CSyncItemLog::CreateInstance((struct CSyncItemLog **)this + 6);
        if ( result >= 0 )
        {
          result = CSyncContext::_CollectItems(this);
          if ( result >= 0 )
            return CSyncContext::_SelectItems(this);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003dd4  push    rbx
0x180003dd6  sub     rsp, 40h
0x180003dda  mov     rax, cs:__security_cookie
0x180003de1  xor     rax, rsp
0x180003de4  mov     [rsp+48h+var_18], rax
0x180003de9  mov     rbx, rcx
0x180003dec  xorps   xmm0, xmm0
0x180003def  lea     rcx, [rsp+48h+pguid]; pguid
0x180003df4  movups  xmmword ptr [rsp+48h+pguid.Data1], xmm0
0x180003df9  call    cs:__imp_CoCreateGuid
0x180003dff  test    eax, eax
0x180003e01  js      short loc_180003E4A
0x180003e03  lea     rdx, [rbx+40h]; lpsz
0x180003e07  mov     r8d, 27h ; '''; cchMax
0x180003e0d  lea     rcx, [rsp+48h+pguid]; rguid
0x180003e12  call    cs:__imp_StringFromGUID2
0x180003e18  test    eax, eax
0x180003e1a  js      short loc_180003E4A
0x180003e1c  lea     rcx, [rbx+28h]; struct CSyncItemDescriptors **
0x180003e20  call    ?CreateInstance@CSyncItemDescriptors@@SAJPEAPEAV1@@Z; CSyncItemDescriptors::CreateInstance(CSyncItemDescriptors * *)
0x180003e25  test    eax, eax
0x180003e27  js      short loc_180003E4A
0x180003e29  lea     rcx, [rbx+30h]; struct CSyncItemLog **
0x180003e2d  call    ?CreateInstance@CSyncItemLog@@SAJPEAPEAV1@@Z; CSyncItemLog::CreateInstance(CSyncItemLog * *)
0x180003e32  test    eax, eax
0x180003e34  js      short loc_180003E4A
0x180003e36  mov     rcx, rbx; this
0x180003e39  call    ?_CollectItems@CSyncContext@@AEAAJXZ; CSyncContext::_CollectItems(void)
0x180003e3e  test    eax, eax
0x180003e40  js      short loc_180003E4A
0x180003e42  mov     rcx, rbx; this
0x180003e45  call    ?_SelectItems@CSyncContext@@AEAAJXZ; CSyncContext::_SelectItems(void)
0x180003e4a  mov     rcx, [rsp+48h+var_18]
0x180003e4f  xor     rcx, rsp; StackCookie
0x180003e52  call    __security_check_cookie
0x180003e57  add     rsp, 40h
0x180003e5b  pop     rbx
0x180003e5c  retn
```
