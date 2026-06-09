# CHNetPortMappingProtocol::GetGuid(_GUID * *)

- ea: `0x180023940`
- end: `0x180023a32`
- name: `?GetGuid@CHNetPortMappingProtocol@@UEAAJPEAPEAU_GUID@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(CHNetPortMappingProtocol *__hidden this, struct _GUID **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180023940`
- `0x180029a3c`
- `0x18002f010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800239ee`
- `OLEAUT32!__imp_VariantClear` at `0x1800239ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023974`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180023974`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023a11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180023a11`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800239e1`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800239e1`

## pseudocode

```c
__int64 __fastcall CHNetPortMappingProtocol::GetGuid(CHNetPortMappingProtocol *this, struct _GUID **a2)
{
  struct _GUID *v4; // rax
  HRESULT WmiObjectFromPath; // ebx
  bool v6; // sf
  VARIANTARG lpsz; // [rsp+40h] [rbp-28h] BYREF
  struct IWbemClassObject *v9; // [rsp+78h] [rbp+10h] BYREF

  v9 = 0;
  memset(&lpsz, 0, sizeof(lpsz));
  if ( a2 )
  {
    v4 = (struct _GUID *)CoTaskMemAlloc(0x10u);
    *a2 = v4;
    if ( v4 )
      WmiObjectFromPath = GetWmiObjectFromPath(
                            *((struct IWbemServices **)this + 9),
                            *((unsigned __int16 **)this + 10),
                            &v9);
    else
      WmiObjectFromPath = -2147024882;
    v6 = WmiObjectFromPath < 0;
    if ( !WmiObjectFromPath )
    {
      WmiObjectFromPath = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))v9->lpVtbl->Get)(
                            v9,
                            L"Id",
                            0,
                            &lpsz,
                            0,
                            0);
      if ( !WmiObjectFromPath )
      {
        WmiObjectFromPath = CLSIDFromString(lpsz.bstrVal, *a2);
        VariantClear(&lpsz);
      }
      ((void (__fastcall *)(struct IWbemClassObject *))v9->lpVtbl->Release)(v9);
      v6 = WmiObjectFromPath < 0;
    }
    if ( v6 && *a2 )
    {
      CoTaskMemFree(*a2);
      *a2 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)WmiObjectFromPath;
}

```

## disassembly

```asm
0x180023940  mov     [rsp+arg_0], rbx
0x180023945  push    rdi
0x180023946  sub     rsp, 60h
0x18002394a  xor     eax, eax
0x18002394c  mov     [rsp+68h+arg_8], 0
0x180023955  mov     [rsp+68h+var_18], rax
0x18002395a  xorps   xmm0, xmm0
0x18002395d  mov     rdi, rdx
0x180023960  mov     rbx, rcx
0x180023963  movups  xmmword ptr [rsp+68h+lpsz], xmm0
0x180023968  test    rdx, rdx
0x18002396b  jz      loc_180023A20
0x180023971  lea     ecx, [rax+10h]; cb
0x180023974  call    cs:__imp_CoTaskMemAlloc
0x18002397a  mov     [rdi], rax
0x18002397d  test    rax, rax
0x180023980  jz      short loc_180023998
0x180023982  mov     rdx, [rbx+50h]; unsigned __int16 *
0x180023986  lea     r8, [rsp+68h+arg_8]; struct IWbemClassObject **
0x18002398b  mov     rcx, [rbx+48h]; struct IWbemServices *
0x18002398f  call    ?GetWmiObjectFromPath@@YAJPEAUIWbemServices@@PEAGPEAPEAUIWbemClassObject@@@Z; GetWmiObjectFromPath(IWbemServices *,ushort *,IWbemClassObject * *)
0x180023994  mov     ebx, eax
0x180023996  jmp     short loc_18002399D
0x180023998  mov     ebx, 8007000Eh
0x18002399d  test    ebx, ebx
0x18002399f  jnz     short loc_180023A07
0x1800239a1  mov     rcx, [rsp+68h+arg_8]
0x1800239a6  lea     r9, [rsp+68h+lpsz]
0x1800239ab  mov     [rsp+68h+var_40], 0
0x1800239b4  lea     rdx, ?c_wszId@@3QBGB; "Id"
0x1800239bb  xor     r8d, r8d
0x1800239be  mov     [rsp+68h+var_48], 0
0x1800239c7  mov     rax, [rcx]
0x1800239ca  mov     rax, [rax+20h]
0x1800239ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239d3  mov     ebx, eax
0x1800239d5  test    eax, eax
0x1800239d7  jnz     short loc_1800239F4
0x1800239d9  mov     rdx, [rdi]; pclsid
0x1800239dc  mov     rcx, [rsp+68h+lpsz+8]; lpsz
0x1800239e1  call    cs:__imp_CLSIDFromString
0x1800239e7  lea     rcx, [rsp+68h+lpsz]; pvarg
0x1800239ec  mov     ebx, eax
0x1800239ee  call    cs:__imp_VariantClear
0x1800239f4  mov     rcx, [rsp+68h+arg_8]
0x1800239f9  mov     rax, [rcx]
0x1800239fc  mov     rax, [rax+10h]
0x180023a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a05  test    ebx, ebx
0x180023a07  jns     short loc_180023A25
0x180023a09  mov     rcx, [rdi]; pv
0x180023a0c  test    rcx, rcx
0x180023a0f  jz      short loc_180023A25
0x180023a11  call    cs:__imp_CoTaskMemFree
0x180023a17  mov     qword ptr [rdi], 0
0x180023a1e  jmp     short loc_180023A25
0x180023a20  mov     ebx, 80004003h
0x180023a25  mov     eax, ebx
0x180023a27  mov     rbx, [rsp+68h+arg_0]
0x180023a2c  add     rsp, 60h
0x180023a30  pop     rdi
0x180023a31  retn
```
