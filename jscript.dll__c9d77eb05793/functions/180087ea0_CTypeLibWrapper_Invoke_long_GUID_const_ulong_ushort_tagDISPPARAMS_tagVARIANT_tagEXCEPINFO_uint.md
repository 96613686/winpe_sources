# CTypeLibWrapper::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180087ea0`
- end: `0x180087f1c`
- name: `?Invoke@CTypeLibWrapper@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `124`
- prototype: `__int64 __fastcall(CTypeLibWrapper *__hidden this, int, const struct _GUID *, unsigned int, char, struct tagDISPPARAMS *, VARIANTARG *pvargDest, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180087ea0`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180087f01`
- `OLEAUT32!__imp_VariantCopy` at `0x180087f01`

## pseudocode

```c
__int64 __fastcall CTypeLibWrapper::Invoke(
        CTypeLibWrapper *this,
        unsigned int a2,
        const struct _GUID *a3,
        __int64 a4,
        char a5,
        struct tagDISPPARAMS *a6,
        VARIANTARG *pvargDest)
{
  HRESULT v8; // eax
  unsigned int v9; // ecx

  if ( (a5 & 2) == 0 || !*((_DWORD *)this + 3) || a2 > *((_DWORD *)this + 3) )
    return 2147614723LL;
  if ( !a6 )
    goto LABEL_9;
  if ( a6->cArgs )
    return 2147614734LL;
  if ( a6->cNamedArgs )
    return 2147614727LL;
LABEL_9:
  if ( !pvargDest )
    return 0;
  v8 = VariantCopy(pvargDest, (const VARIANTARG *)(*(_QWORD *)(*((_QWORD *)this + 3) + 16LL) + 24LL * (int)(a2 - 1)));
  v9 = 0;
  if ( v8 < 0 )
    return (unsigned int)v8;
  return v9;
}

```

## disassembly

```asm
0x180087ea0  sub     rsp, 28h
0x180087ea4  test    [rsp+28h+arg_20], 2
0x180087ea9  mov     r9, rcx
0x180087eac  jz      short loc_180087F12
0x180087eae  cmp     dword ptr [rcx+0Ch], 0
0x180087eb2  jz      short loc_180087F12
0x180087eb4  cmp     edx, [rcx+0Ch]
0x180087eb7  ja      short loc_180087F12
0x180087eb9  mov     rax, [rsp+28h+arg_28]
0x180087ebe  test    rax, rax
0x180087ec1  jz      short loc_180087EDD
0x180087ec3  cmp     dword ptr [rax+10h], 0
0x180087ec7  jz      short loc_180087ED0
0x180087ec9  mov     eax, 8002000Eh
0x180087ece  jmp     short loc_180087F17
0x180087ed0  cmp     dword ptr [rax+14h], 0
0x180087ed4  jz      short loc_180087EDD
0x180087ed6  mov     eax, 80020007h
0x180087edb  jmp     short loc_180087F17
0x180087edd  mov     rcx, [rsp+28h+pvargDest]; pvargDest
0x180087ee2  test    rcx, rcx
0x180087ee5  jnz     short loc_180087EEB
0x180087ee7  xor     eax, eax
0x180087ee9  jmp     short loc_180087F17
0x180087eeb  lea     eax, [rdx-1]
0x180087eee  movsxd  rdx, eax
0x180087ef1  mov     rax, [r9+18h]
0x180087ef5  lea     r8, [rdx+rdx*2]
0x180087ef9  mov     rdx, [rax+10h]
0x180087efd  lea     rdx, [rdx+r8*8]; pvargSrc
0x180087f01  call    cs:__imp_VariantCopy
0x180087f07  xor     ecx, ecx
0x180087f09  test    eax, eax
0x180087f0b  cmovs   ecx, eax
0x180087f0e  mov     eax, ecx
0x180087f10  jmp     short loc_180087F17
0x180087f12  mov     eax, 80020003h
0x180087f17  add     rsp, 28h
0x180087f1b  retn
```
