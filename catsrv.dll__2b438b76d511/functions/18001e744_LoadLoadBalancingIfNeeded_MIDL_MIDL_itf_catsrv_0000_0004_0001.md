# LoadLoadBalancingIfNeeded(__MIDL___MIDL_itf_catsrv_0000_0004_0001)

- ea: `0x18001e744`
- end: `0x18001e863`
- name: `?LoadLoadBalancingIfNeeded@@YAJW4__MIDL___MIDL_itf_catsrv_0000_0004_0001@@@Z`
- size: `287`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001dfc0`
- `0x18001e550`
- `0x18001e5d0`
- `0x18001e870`
- `0x18001e9d0`
- `0x18001eae0`
- `0x18001ed90`
- `0x18001f0b4`

## callees

- `0x18000a01c`
- `0x18001dd1c`
- `0x18001e744`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e76d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e7c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e813`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e76d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e7c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e813`

## string_xrefs

- `0x18001e7d9`: `ServiceExe`
- `0x18001e829`: `ServiceDesc`
- `0x18001e789`: `ServiceName`
- `0x18001e7a3`: `Service Name not in Registry`
- `0x18001e7f3`: `Service Exe not in Registry`
- `0x18001e843`: `Service desc not in registry`

## pseudocode

```c
__int64 __fastcall LoadLoadBalancingIfNeeded(int a1)
{
  unsigned __int16 *v1; // rax
  unsigned int v2; // edx
  __int64 result; // rax
  unsigned __int16 *v4; // rax
  unsigned int v5; // edx
  unsigned __int16 *v6; // rax
  unsigned int v7; // edx

  if ( a1 != 1 )
    return 0;
  if ( csServices )
    goto LABEL_18;
  v1 = (unsigned __int16 *)CoTaskMemAlloc(0x208u);
  csServices = v1;
  if ( !v1 )
    return 2147942414LL;
  if ( !(unsigned int)GetCLBSKeyInfo(v1, v2, L"ServiceName")
    || (result = StringCchCopyW(csServices, 0x104u, L"Service Name not in Registry"), (int)result >= 0) )
  {
LABEL_18:
    if ( qword_180072278 )
      goto LABEL_19;
    v4 = (unsigned __int16 *)CoTaskMemAlloc(0x208u);
    qword_180072278 = v4;
    if ( !v4 )
      return 2147942414LL;
    if ( !(unsigned int)GetCLBSKeyInfo(v4, v5, L"ServiceExe")
      || (result = StringCchCopyW(qword_180072278, 0x104u, L"Service Exe not in Registry"), (int)result >= 0) )
    {
LABEL_19:
      if ( qword_180072270 )
        return 0;
      v6 = (unsigned __int16 *)CoTaskMemAlloc(0x208u);
      qword_180072270 = v6;
      if ( !v6 )
        return 2147942414LL;
      if ( !(unsigned int)GetCLBSKeyInfo(v6, v7, L"ServiceDesc") )
        return 0;
      result = StringCchCopyW(qword_180072270, 0x104u, L"Service desc not in registry");
      if ( (int)result >= 0 )
        return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001e744  mov     [rsp+arg_0], rsi
0x18001e749  push    rdi
0x18001e74a  sub     rsp, 20h
0x18001e74e  cmp     ecx, 1
0x18001e751  jnz     loc_18001E856
0x18001e757  cmp     cs:?csServices@@3PAUcsServiceInfo@@A, 0; csServiceInfo near * csServices
0x18001e75f  mov     esi, 104h
0x18001e764  mov     edi, 208h
0x18001e769  jnz     short loc_18001E7BA
0x18001e76b  mov     ecx, edi; cb
0x18001e76d  call    cs:__imp_CoTaskMemAlloc
0x18001e773  mov     cs:?csServices@@3PAUcsServiceInfo@@A, rax; csServiceInfo near * csServices
0x18001e77a  test    rax, rax
0x18001e77d  jnz     short loc_18001E789
0x18001e77f  mov     eax, 8007000Eh
0x18001e784  jmp     loc_18001E858
0x18001e789  lea     r8, aServicename; "ServiceName"
0x18001e790  mov     rcx, rax; unsigned __int16 *
0x18001e793  call    ?GetCLBSKeyInfo@@YAJPEAGK0@Z; GetCLBSKeyInfo(ushort *,ulong,ushort *)
0x18001e798  test    eax, eax
0x18001e79a  jz      short loc_18001E7BA
0x18001e79c  mov     rcx, cs:?csServices@@3PAUcsServiceInfo@@A; unsigned __int16 *
0x18001e7a3  lea     r8, aServiceNameNot; "Service Name not in Registry"
0x18001e7aa  mov     rdx, rsi; unsigned __int64
0x18001e7ad  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e7b2  test    eax, eax
0x18001e7b4  js      loc_18001E858
0x18001e7ba  cmp     cs:qword_180072278, 0
0x18001e7c2  jnz     short loc_18001E806
0x18001e7c4  mov     rcx, rdi; cb
0x18001e7c7  call    cs:__imp_CoTaskMemAlloc
0x18001e7cd  mov     cs:qword_180072278, rax
0x18001e7d4  test    rax, rax
0x18001e7d7  jz      short loc_18001E77F
0x18001e7d9  lea     r8, aServiceexe; "ServiceExe"
0x18001e7e0  mov     rcx, rax; unsigned __int16 *
0x18001e7e3  call    ?GetCLBSKeyInfo@@YAJPEAGK0@Z; GetCLBSKeyInfo(ushort *,ulong,ushort *)
0x18001e7e8  test    eax, eax
0x18001e7ea  jz      short loc_18001E806
0x18001e7ec  mov     rcx, cs:qword_180072278; unsigned __int16 *
0x18001e7f3  lea     r8, aServiceExeNotI; "Service Exe not in Registry"
0x18001e7fa  mov     rdx, rsi; unsigned __int64
0x18001e7fd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e802  test    eax, eax
0x18001e804  js      short loc_18001E858
0x18001e806  cmp     cs:qword_180072270, 0
0x18001e80e  jnz     short loc_18001E856
0x18001e810  mov     rcx, rdi; cb
0x18001e813  call    cs:__imp_CoTaskMemAlloc
0x18001e819  mov     cs:qword_180072270, rax
0x18001e820  test    rax, rax
0x18001e823  jz      loc_18001E77F
0x18001e829  lea     r8, aServicedesc; "ServiceDesc"
0x18001e830  mov     rcx, rax; unsigned __int16 *
0x18001e833  call    ?GetCLBSKeyInfo@@YAJPEAGK0@Z; GetCLBSKeyInfo(ushort *,ulong,ushort *)
0x18001e838  test    eax, eax
0x18001e83a  jz      short loc_18001E856
0x18001e83c  mov     rcx, cs:qword_180072270; unsigned __int16 *
0x18001e843  lea     r8, aServiceDescNot; "Service desc not in registry"
0x18001e84a  mov     rdx, rsi; unsigned __int64
0x18001e84d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e852  test    eax, eax
0x18001e854  js      short loc_18001E858
0x18001e856  xor     eax, eax
0x18001e858  mov     rsi, [rsp+28h+arg_0]
0x18001e85d  add     rsp, 20h
0x18001e861  pop     rdi
0x18001e862  retn
```
