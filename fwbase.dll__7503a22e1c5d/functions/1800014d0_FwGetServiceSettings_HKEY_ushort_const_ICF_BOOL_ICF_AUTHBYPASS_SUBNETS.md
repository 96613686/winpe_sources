# FwGetServiceSettings(HKEY__ *,ushort const *,ICF_BOOL_ *,ICF_AUTHBYPASS_SUBNETS_ *)

- ea: `0x1800014d0`
- end: `0x1800015ef`
- name: `?FwGetServiceSettings@@YAJPEAUHKEY__@@PEBGPEAW4ICF_BOOL_@@PEAUICF_AUTHBYPASS_SUBNETS_@@@Z`
- size: `287`
- prototype: `int(HKEY, const unsigned __int16 *, enum ICF_BOOL_ *, struct ICF_AUTHBYPASS_SUBNETS_ *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180001400`
- `0x18002bc90`

## callees

- `0x180001344`
- `0x1800014d0`
- `0x180001720`
- `0x1800028e0`
- `0x180002910`
- `0x1800047e0`
- `0x180004840`
- `0x18001262c`

## string_xrefs

- `0x180001534`: `FwGetServiceSettings`

## pseudocode

```c
__int64 __fastcall FwGetServiceSettings(
        HKEY a1,
        const unsigned __int16 *a2,
        enum ICF_BOOL_ *a3,
        struct ICF_AUTHBYPASS_SUBNETS_ *a4)
{
  int IcfBool; // eax
  const unsigned __int16 *v6; // rdx
  int v7; // ebx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *Src; // [rsp+38h] [rbp-8h]
  __int64 v11; // [rsp+70h] [rbp+30h] BYREF

  *(_DWORD *)a3 = 0;
  *(_OWORD *)a4 = 0;
  hKey = 0;
  *((_OWORD *)a4 + 1) = 0;
  *((_QWORD *)a4 + 4) = 0;
  LODWORD(v11) = 0;
  Src = 0;
  IcfBool = FwRegOpenKey(a1, a2, 1u, &hKey, (int *)&v11);
  v7 = IcfBool;
  if ( IcfBool < 0 )
    goto LABEL_7;
  if ( !(_DWORD)v11 )
    goto LABEL_10;
  IcfBool = FwRegQueryIcfBool(hKey, v6, L"Enabled", a3);
  v7 = IcfBool;
  if ( IcfBool < 0 )
    goto LABEL_7;
  IcfBool = FwRegQueryString(hKey, 0, L"RemoteAddresses", (__int64)&v11);
  v7 = IcfBool;
  if ( IcfBool < 0 )
    goto LABEL_7;
  if ( !(_DWORD)v11 )
    goto LABEL_10;
  IcfBool = FwSubNetsDecode(Src);
  v7 = IcfBool;
  if ( IcfBool < 0 )
LABEL_7:
    FwReportReturnError("FwGetServiceSettings", (unsigned int)IcfBool);
  if ( v7 == -2147024883 )
  {
    *(_DWORD *)a3 = 1;
    v7 = 0;
  }
LABEL_10:
  FwFree(Src);
  FwRegCloseKey(hKey);
  if ( v7 < 0 )
    return (unsigned int)FwReportReturnError("FwGetServiceSettings", (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800014d0  mov     [rsp-18h+arg_0], rbx
0x1800014d5  mov     [rsp-18h+arg_8], rsi
0x1800014da  push    rbp
0x1800014db  push    r12
0x1800014dd  push    r14
0x1800014df  mov     rbp, rsp
0x1800014e2  sub     rsp, 40h
0x1800014e6  mov     dword ptr [r8], 0
0x1800014ed  xorps   xmm0, xmm0
0x1800014f0  movups  xmmword ptr [r9], xmm0
0x1800014f4  xor     eax, eax
0x1800014f6  mov     [rbp+hKey], 0
0x1800014fe  movups  xmmword ptr [r9+10h], xmm0
0x180001503  mov     [r9+20h], rax
0x180001507  mov     r14, r9
0x18000150a  lea     rax, [rbp+arg_10]
0x18000150e  mov     dword ptr [rbp+arg_10], 0
0x180001515  mov     rsi, r8
0x180001518  mov     [rsp+40h+var_20], rax; __int64
0x18000151d  lea     r9, [rbp+hKey]
0x180001521  mov     [rbp+Src], 0
0x180001529  mov     r8d, 1; samDesired
0x18000152f  call    FwRegOpenKey
0x180001534  lea     r12, aFwgetservicese; "FwGetServiceSettings"
0x18000153b  mov     ebx, eax
0x18000153d  test    eax, eax
0x18000153f  js      short loc_18000159D
0x180001541  cmp     dword ptr [rbp+arg_10], 0
0x180001545  jz      short loc_1800015B7
0x180001547  mov     rcx, [rbp+hKey]; HKEY
0x18000154b  lea     r8, aEnabled; "Enabled"
0x180001552  mov     r9, rsi; enum ICF_BOOL_ *
0x180001555  call    ?FwRegQueryIcfBool@@YAJPEAUHKEY__@@PEBG1PEAW4ICF_BOOL_@@@Z; FwRegQueryIcfBool(HKEY__ *,ushort const *,ushort const *,ICF_BOOL_ *)
0x18000155a  mov     ebx, eax
0x18000155c  test    eax, eax
0x18000155e  js      short loc_18000159D
0x180001560  mov     rcx, [rbp+hKey]; hKey
0x180001564  lea     rax, [rbp+arg_10]
0x180001568  lea     r9, [rbp+Src]
0x18000156c  mov     [rsp+40h+var_20], rax; __int64
0x180001571  lea     r8, aRemoteaddresse; "RemoteAddresses"
0x180001578  xor     edx, edx; lpSubKey
0x18000157a  call    FwRegQueryString
0x18000157f  mov     ebx, eax
0x180001581  test    eax, eax
0x180001583  js      short loc_18000159D
0x180001585  cmp     dword ptr [rbp+arg_10], 0
0x180001589  jz      short loc_1800015B7
0x18000158b  mov     rcx, [rbp+Src]; Src
0x18000158f  mov     rdx, r14
0x180001592  call    FwSubNetsDecode
0x180001597  mov     ebx, eax
0x180001599  test    eax, eax
0x18000159b  jns     short loc_1800015A7
0x18000159d  mov     edx, eax
0x18000159f  mov     rcx, r12
0x1800015a2  call    FwReportReturnError
0x1800015a7  cmp     ebx, 8007000Dh
0x1800015ad  jnz     short loc_1800015B7
0x1800015af  mov     dword ptr [rsi], 1
0x1800015b5  xor     ebx, ebx
0x1800015b7  mov     rcx, [rbp+Src]
0x1800015bb  call    FwFree
0x1800015c0  mov     rcx, [rbp+hKey]
0x1800015c4  call    FwRegCloseKey
0x1800015c9  test    ebx, ebx
0x1800015cb  jns     short loc_1800015D9
0x1800015cd  mov     edx, ebx
0x1800015cf  mov     rcx, r12
0x1800015d2  call    FwReportReturnError
0x1800015d7  mov     ebx, eax
0x1800015d9  mov     rsi, [rsp+40h+arg_8]
0x1800015de  mov     eax, ebx
0x1800015e0  mov     rbx, [rsp+40h+arg_0]
0x1800015e5  add     rsp, 40h
0x1800015e9  pop     r14
0x1800015eb  pop     r12
0x1800015ed  pop     rbp
0x1800015ee  retn
```
