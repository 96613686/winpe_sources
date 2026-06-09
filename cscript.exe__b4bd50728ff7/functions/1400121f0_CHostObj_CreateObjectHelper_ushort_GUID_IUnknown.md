# CHostObj::CreateObjectHelper(ushort *,_GUID *,IUnknown * *)

- ea: `0x1400121f0`
- end: `0x1400122ef`
- name: `?CreateObjectHelper@CHostObj@@IEAAJPEAGPEAU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `255`
- prototype: `int(CHostObj *__hidden this, unsigned __int16 *, struct _GUID *, struct IUnknown **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400120b0`
- `0x140012360`

## callees

- `0x140007d2c`
- `0x14000cd9c`
- `0x14000d178`
- `0x14000d2e0`
- `0x1400121f0`

## import_xrefs

- `ole32!CLSIDFromProgID` at `0x14001220d`
- `ole32!CLSIDFromProgID` at `0x14001220d`
- `ole32!CoCreateInstance` at `0x1400122ba`
- `ole32!CoCreateInstance` at `0x1400122ba`

## string_xrefs

- `0x140012223`: `WScript.CreateObject`
- `0x140012260`: `WScript.CreateObject`
- `0x1400122c9`: `WScript.CreateObject`

## pseudocode

```c
__int64 __fastcall CHostObj::CreateObjectHelper(CHostObj *this, unsigned __int16 *a2, struct _GUID *a3, LPVOID *a4)
{
  HRESULT v8; // eax
  HRESULT IsClassAllowed; // ebx
  CHost *v10; // rcx
  int v12; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 *v13; // [rsp+38h] [rbp-30h] BYREF

  v8 = CLSIDFromProgID(a2, a3);
  IsClassAllowed = v8;
  if ( v8 >= 0 )
  {
    v10 = (CHost *)*((_QWORD *)this + 16);
    v12 = 0;
    IsClassAllowed = CHost::WldpIsClassAllowed(v10, a3, &v12);
    if ( IsClassAllowed >= 0 )
    {
      if ( v12 )
      {
        IsClassAllowed = CoCreateInstance(a3, 0, 0x15u, &IID_IUnknown, a4);
        if ( IsClassAllowed >= 0 )
          return (unsigned int)IsClassAllowed;
      }
      else
      {
        IsClassAllowed = -2147024891;
      }
    }
    Signal_Exception(&IID_IHost, L"WScript.CreateObject", 0xC1Fu, a2);
    return (unsigned int)IsClassAllowed;
  }
  if ( v8 == -2147221005 )
  {
    Signal_Exception(&IID_IHost, L"WScript.CreateObject", 0xC1Du, a2);
    return (unsigned int)-2147352567;
  }
  else
  {
    v13 = 0;
    FormatHResult(v8, &v13);
    Signal_Exception(&IID_IHost, L"WScript.CreateObject", v13);
  }
  return (unsigned int)IsClassAllowed;
}

```

## disassembly

```asm
0x1400121f0  push    rbx
0x1400121f2  push    rbp
0x1400121f3  push    rsi
0x1400121f4  push    rdi
0x1400121f5  push    r14
0x1400121f7  sub     rsp, 40h
0x1400121fb  mov     rdi, rdx
0x1400121fe  mov     rbp, rcx
0x140012201  mov     rcx, rdi; lpszProgID
0x140012204  mov     rdx, r8; lpclsid
0x140012207  mov     r14, r9
0x14001220a  mov     rsi, r8
0x14001220d  call    cs:__imp_CLSIDFromProgID
0x140012213  mov     ebx, eax
0x140012215  test    eax, eax
0x140012217  jns     short loc_140012275
0x140012219  cmp     eax, 800401F3h
0x14001221e  jnz     short loc_140012246
0x140012220  mov     r9, rdi
0x140012223  lea     rdx, aWscriptCreateo; "WScript.CreateObject"
0x14001222a  mov     r8d, 0C1Dh; unsigned int
0x140012230  lea     rcx, IID_IHost; struct _GUID *
0x140012237  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x14001223c  mov     ebx, 80020009h
0x140012241  jmp     loc_1400122E2
0x140012246  lea     rdx, [rsp+68h+var_30]; unsigned __int16 **
0x14001224b  mov     [rsp+68h+var_30], 0
0x140012254  mov     ecx, eax; dwMessageId
0x140012256  call    ?FormatHResult@@YAJJPEAPEAG@Z; FormatHResult(long,ushort * *)
0x14001225b  mov     r8, [rsp+68h+var_30]; unsigned __int16 *
0x140012260  lea     rdx, aWscriptCreateo; "WScript.CreateObject"
0x140012267  lea     rcx, IID_IHost; struct _GUID *
0x14001226e  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBG1ZZ; Signal_Exception(_GUID const &,ushort const *,ushort const *,...)
0x140012273  jmp     short loc_1400122E2
0x140012275  mov     rcx, [rbp+80h]; this
0x14001227c  lea     r8, [rsp+68h+var_38]; int *
0x140012281  mov     rdx, rsi; struct _GUID *
0x140012284  mov     [rsp+68h+var_38], 0
0x14001228c  call    ?WldpIsClassAllowed@CHost@@QEAAJAEBU_GUID@@PEAH@Z; CHost::WldpIsClassAllowed(_GUID const &,int *)
0x140012291  mov     ebx, eax
0x140012293  test    eax, eax
0x140012295  js      short loc_1400122C6
0x140012297  cmp     [rsp+68h+var_38], 0
0x14001229c  jnz     short loc_1400122A5
0x14001229e  mov     ebx, 80070005h
0x1400122a3  jmp     short loc_1400122C6
0x1400122a5  xor     edx, edx; pUnkOuter
0x1400122a7  mov     [rsp+68h+ppv], r14; ppv
0x1400122ac  lea     r9, IID_IUnknown; riid
0x1400122b3  mov     rcx, rsi; rclsid
0x1400122b6  lea     r8d, [rdx+15h]; dwClsContext
0x1400122ba  call    cs:__imp_CoCreateInstance
0x1400122c0  mov     ebx, eax
0x1400122c2  test    eax, eax
0x1400122c4  jns     short loc_1400122E2
0x1400122c6  mov     r9, rdi
0x1400122c9  lea     rdx, aWscriptCreateo; "WScript.CreateObject"
0x1400122d0  mov     r8d, 0C1Fh; unsigned int
0x1400122d6  lea     rcx, IID_IHost; struct _GUID *
0x1400122dd  call    ?Signal_Exception@@YAJAEBU_GUID@@PEBGIZZ; Signal_Exception(_GUID const &,ushort const *,uint,...)
0x1400122e2  mov     eax, ebx
0x1400122e4  add     rsp, 40h
0x1400122e8  pop     r14
0x1400122ea  pop     rdi
0x1400122eb  pop     rsi
0x1400122ec  pop     rbp
0x1400122ed  pop     rbx
0x1400122ee  retn
```
