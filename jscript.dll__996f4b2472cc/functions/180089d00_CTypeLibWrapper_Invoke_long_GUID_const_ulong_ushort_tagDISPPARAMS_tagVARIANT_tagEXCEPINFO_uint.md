# CTypeLibWrapper::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180089d00`
- end: `0x180089d83`
- name: `?Invoke@CTypeLibWrapper@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `131`
- prototype: `__int64 __fastcall(CTypeLibWrapper *__hidden this, int, const struct _GUID *, unsigned int, char, struct tagDISPPARAMS *, VARIANTARG *pvargDest, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180089d00`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180089d61`
- `OLEAUT32!__imp_VariantCopy` at `0x180089d61`

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
0x180089d00  sub     rsp, 28h
0x180089d04  test    [rsp+28h+arg_20], 2
0x180089d09  mov     r9, rcx
0x180089d0c  jz      short loc_180089D78
0x180089d0e  cmp     dword ptr [rcx+0Ch], 0
0x180089d12  jz      short loc_180089D78
0x180089d14  cmp     edx, [rcx+0Ch]
0x180089d17  ja      short loc_180089D78
0x180089d19  mov     rax, [rsp+28h+arg_28]
0x180089d1e  test    rax, rax
0x180089d21  jz      short loc_180089D3D
0x180089d23  cmp     dword ptr [rax+10h], 0
0x180089d27  jz      short loc_180089D30
0x180089d29  mov     eax, 8002000Eh
0x180089d2e  jmp     short loc_180089D7D
0x180089d30  cmp     dword ptr [rax+14h], 0
0x180089d34  jz      short loc_180089D3D
0x180089d36  mov     eax, 80020007h
0x180089d3b  jmp     short loc_180089D7D
0x180089d3d  mov     rcx, [rsp+28h+pvargDest]; pvargDest
0x180089d42  test    rcx, rcx
0x180089d45  jnz     short loc_180089D4B
0x180089d47  xor     eax, eax
0x180089d49  jmp     short loc_180089D7D
0x180089d4b  lea     eax, [rdx-1]
0x180089d4e  movsxd  rdx, eax
0x180089d51  mov     rax, [r9+18h]
0x180089d55  lea     r8, [rdx+rdx*2]
0x180089d59  mov     rdx, [rax+10h]
0x180089d5d  lea     rdx, [rdx+r8*8]; pvargSrc
0x180089d61  call    cs:__imp_VariantCopy
0x180089d68  nop     dword ptr [rax+rax+00h]
0x180089d6d  xor     ecx, ecx
0x180089d6f  test    eax, eax
0x180089d71  cmovs   ecx, eax
0x180089d74  mov     eax, ecx
0x180089d76  jmp     short loc_180089D7D
0x180089d78  mov     eax, 80020003h
0x180089d7d  add     rsp, 28h
0x180089d81  retn
```
