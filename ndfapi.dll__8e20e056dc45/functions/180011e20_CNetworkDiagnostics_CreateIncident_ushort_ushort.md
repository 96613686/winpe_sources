# CNetworkDiagnostics::CreateIncident(ushort *,ushort *)

- ea: `0x180011e20`
- end: `0x180011f53`
- name: `?CreateIncident@CNetworkDiagnostics@@UEAAJPEAG0@Z`
- size: `307`
- prototype: `__int64 __fastcall(NDFHANDLE *this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000a9e0`
- `0x180011c20`
- `0x180011e20`
- `0x180021010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180011e4c`
- `KERNEL32!EnterCriticalSection` at `0x180011e4c`
- `KERNEL32!LeaveCriticalSection` at `0x180011f32`
- `KERNEL32!LeaveCriticalSection` at `0x180011f32`
- `ole32!CoCreateInstance` at `0x180011e8e`
- `ole32!CoCreateInstance` at `0x180011e8e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNetworkDiagnostics::CreateIncident(NDFHANDLE *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  HRESULT Instance; // ebx
  struct IXMLDOMDocument *ppv; // [rsp+30h] [rbp-10h] BYREF
  HELPER_ATTRIBUTE *attributes; // [rsp+38h] [rbp-8h] BYREF
  __int16 v11; // [rsp+70h] [rbp+30h] BYREF
  ULONG celt; // [rsp+88h] [rbp+48h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)(this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 16));
  if ( *((_DWORD *)this + 30) )
  {
    Instance = -2147024120;
  }
  else
  {
    attributes = 0;
    celt = 0;
    ppv = 0;
    Instance = CoCreateInstance(
                 &CLSID_DOMDocument60,
                 0,
                 0x17u,
                 &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60,
                 (LPVOID *)&ppv);
    if ( Instance >= 0 )
    {
      ((void (__fastcall *)(struct IXMLDOMDocument *, _QWORD))ppv->lpVtbl->put_validateOnParse)(ppv, 0);
      v11 = 0;
      Instance = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, unsigned __int16 *, __int16 *))ppv->lpVtbl->loadXML)(
                   ppv,
                   a3,
                   &v11);
      if ( Instance >= 0 )
      {
        if ( v11 )
        {
          Instance = CreateHelperAttributesFromXML(ppv, &attributes, &celt);
          if ( Instance >= 0 )
          {
            Instance = NdfCreateIncident(a2, celt, attributes, this + 2);
            if ( Instance >= 0 )
              *((_DWORD *)this + 30) = 1;
          }
        }
        else
        {
          Instance = -2147024809;
        }
      }
    }
    if ( ppv )
      ((void (__fastcall *)(struct IXMLDOMDocument *))ppv->lpVtbl->Release)(ppv);
  }
  LeaveCriticalSection(v6);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180011e20  mov     [rsp-28h+arg_8], rbx
0x180011e25  mov     [rsp-28h+arg_10], rsi
0x180011e2a  push    rbp
0x180011e2b  push    rdi
0x180011e2c  push    r12
0x180011e2e  push    r14
0x180011e30  push    r15
0x180011e32  mov     rbp, rsp
0x180011e35  sub     rsp, 40h
0x180011e39  mov     r15, r8
0x180011e3c  mov     r14, rdx
0x180011e3f  mov     rdi, rcx
0x180011e42  lea     rsi, [rcx+80h]
0x180011e49  mov     rcx, rsi; lpCriticalSection
0x180011e4c  call    cs:__imp_EnterCriticalSection
0x180011e52  xor     r12d, r12d
0x180011e55  cmp     [rdi+78h], r12d
0x180011e59  jz      short loc_180011E65
0x180011e5b  mov     ebx, 80070308h
0x180011e60  jmp     loc_180011F2F
0x180011e65  mov     [rbp+attributes], r12
0x180011e69  mov     [rbp+celt], r12d
0x180011e6d  mov     [rbp+var_10], r12
0x180011e71  lea     rax, [rbp+var_10]
0x180011e75  mov     [rsp+40h+ppv], rax; ppv
0x180011e7a  lea     r9, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; riid
0x180011e81  xor     edx, edx; pUnkOuter
0x180011e83  lea     r8d, [rdx+17h]; dwClsContext
0x180011e87  lea     rcx, CLSID_DOMDocument60; rclsid
0x180011e8e  call    cs:__imp_CoCreateInstance
0x180011e94  mov     ebx, eax
0x180011e96  test    eax, eax
0x180011e98  js      short loc_180011F19
0x180011e9a  mov     rcx, [rbp+var_10]
0x180011e9e  mov     rax, [rcx]
0x180011ea1  xor     edx, edx
0x180011ea3  mov     rax, [rax+220h]
0x180011eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011eaf  mov     [rbp+arg_0], r12w
0x180011eb4  mov     rcx, [rbp+var_10]
0x180011eb8  mov     rax, [rcx]
0x180011ebb  lea     r8, [rbp+arg_0]
0x180011ebf  mov     rdx, r15
0x180011ec2  mov     rax, [rax+208h]
0x180011ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ece  mov     ebx, eax
0x180011ed0  test    eax, eax
0x180011ed2  js      short loc_180011F19
0x180011ed4  cmp     [rbp+arg_0], r12w
0x180011ed9  jz      short loc_180011F14
0x180011edb  lea     r8, [rbp+celt]; unsigned int *
0x180011edf  lea     rdx, [rbp+attributes]; struct tagHELPER_ATTRIBUTE **
0x180011ee3  mov     rcx, [rbp+var_10]; struct IXMLDOMDocument *
0x180011ee7  call    ?CreateHelperAttributesFromXML@@YAJPEAUIXMLDOMDocument@@PEAPEAUtagHELPER_ATTRIBUTE@@PEAK@Z; CreateHelperAttributesFromXML(IXMLDOMDocument *,tagHELPER_ATTRIBUTE * *,ulong *)
0x180011eec  mov     ebx, eax
0x180011eee  test    eax, eax
0x180011ef0  js      short loc_180011F19
0x180011ef2  lea     r9, [rdi+10h]; handle
0x180011ef6  mov     r8, [rbp+attributes]; attributes
0x180011efa  mov     edx, [rbp+celt]; celt
0x180011efd  mov     rcx, r14; helperClassName
0x180011f00  call    NdfCreateIncident
0x180011f05  mov     ebx, eax
0x180011f07  test    eax, eax
0x180011f09  js      short loc_180011F19
0x180011f0b  mov     dword ptr [rdi+78h], 1
0x180011f12  jmp     short loc_180011F19
0x180011f14  mov     ebx, 80070057h
0x180011f19  mov     rcx, [rbp+var_10]
0x180011f1d  test    rcx, rcx
0x180011f20  jz      short loc_180011F2F
0x180011f22  mov     rax, [rcx]
0x180011f25  mov     rax, [rax+10h]
0x180011f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f2e  nop
0x180011f2f  mov     rcx, rsi; lpCriticalSection
0x180011f32  call    cs:__imp_LeaveCriticalSection
0x180011f38  mov     eax, ebx
0x180011f3a  lea     r11, [rsp+40h+var_s0]
0x180011f3f  mov     rbx, [r11+38h]
0x180011f43  mov     rsi, [r11+40h]
0x180011f47  mov     rsp, r11
0x180011f4a  pop     r15
0x180011f4c  pop     r14
0x180011f4e  pop     r12
0x180011f50  pop     rdi
0x180011f51  pop     rbp
0x180011f52  retn
```
