# CNameResolver::_ResolveOnlineId(ushort const *,CDPA<CUserObject,CTContainer_PolicyUnOwned<CUserObject>> &)

- ea: `0x18006fd64`
- end: `0x18006ff16`
- name: `?_ResolveOnlineId@CNameResolver@@AEAAJPEBGAEAV?$CDPA@VCUserObject@@V?$CTContainer_PolicyUnOwned@VCUserObject@@@@@@@Z`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18006f048`

## callees

- `0x1800120e0`
- `0x1800259bc`
- `0x180053fd4`
- `0x18006f608`
- `0x18006fd64`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006fda8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006fda8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fed2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fee9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fed2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006fee9`

## pseudocode

```c
__int64 __fastcall CNameResolver::_ResolveOnlineId(void *a1, const unsigned __int16 *a2, __int64 a3)
{
  HRESULT appended; // edi
  _QWORD *v6; // rbx
  int v7; // eax
  unsigned int v8; // edx
  CSidResolver *v9; // rcx
  LPVOID pv[2]; // [rsp+40h] [rbp-10h] BYREF
  LPVOID v12; // [rsp+70h] [rbp+20h] BYREF
  LPVOID v13; // [rsp+88h] [rbp+38h] BYREF

  v12 = a1;
  v13 = 0;
  appended = CoCreateInstance(&CLSID_OnlineIdFilter, 0, 1u, &GUID_e6496873_6ddc_4709_8785_1a5b3267843b, &v13);
  if ( appended >= 0 )
  {
    v12 = 0;
    appended = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, LPVOID *))(*(_QWORD *)v13 + 48LL))(
                 v13,
                 a2,
                 &v12);
    if ( appended >= 0 )
    {
      appended = -2147024882;
      pv[0] = operator new(0x40u, (const struct std::nothrow_t *)std::nothrow);
      v6 = pv[0];
      if ( pv[0] )
      {
        *(_QWORD *)pv[0] = v12;
        v6[1] = 0;
        v6[2] = 0;
        v6[3] = 0;
        v6[4] = 0;
        v6[5] = 8;
        *((_DWORD *)v6 + 13) = 1;
        v6[7] = 0;
        *((_DWORD *)v6 + 12) = -1;
        pv[0] = 0;
        v7 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, LPVOID *))(*(_QWORD *)v13 + 56LL))(v13, v12, pv);
        v12 = 0;
        appended = v7;
        if ( v7 < 0 )
          goto LABEL_9;
        appended = CSidResolver::_FillObjectDetails(
                     v9,
                     (struct CUserObject *)v6,
                     a2,
                     a2,
                     0,
                     (const unsigned __int16 *)pv[0],
                     SidTypeUser,
                     1);
        if ( appended >= 0 )
        {
          appended = CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(a3, v6);
          if ( appended >= 0 )
            v6 = 0;
        }
        CoTaskMemFree(pv[0]);
        if ( v6 )
LABEL_9:
          CUserObject::`scalar deleting destructor'((CUserObject *)v6, v8);
      }
    }
    CoTaskMemFree(v12);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18006fd64  mov     r11, rsp
0x18006fd67  mov     [r11+10h], rbx
0x18006fd6b  mov     [r11+18h], rsi
0x18006fd6f  mov     [r11+8], rcx
0x18006fd73  push    rbp
0x18006fd74  push    rdi
0x18006fd75  push    r14
0x18006fd77  mov     rbp, rsp
0x18006fd7a  sub     rsp, 50h
0x18006fd7e  mov     rsi, rdx
0x18006fd81  mov     [rbp+arg_18], 0
0x18006fd89  xor     edx, edx; pUnkOuter
0x18006fd8b  lea     rax, [rbp+arg_18]
0x18006fd8f  mov     r14, r8
0x18006fd92  mov     [r11-48h], rax
0x18006fd96  lea     r9, _GUID_e6496873_6ddc_4709_8785_1a5b3267843b; riid
0x18006fd9d  lea     rcx, CLSID_OnlineIdFilter; rclsid
0x18006fda4  lea     r8d, [rdx+1]; dwClsContext
0x18006fda8  call    cs:__imp_CoCreateInstance
0x18006fdae  mov     edi, eax
0x18006fdb0  test    eax, eax
0x18006fdb2  js      loc_18006FEFF
0x18006fdb8  mov     rcx, [rbp+arg_18]
0x18006fdbc  lea     r8, [rbp+arg_0]
0x18006fdc0  mov     [rbp+arg_0], 0
0x18006fdc8  mov     rdx, rsi
0x18006fdcb  mov     rax, [rcx]
0x18006fdce  mov     rax, [rax+30h]
0x18006fdd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fdd7  mov     edi, eax
0x18006fdd9  test    eax, eax
0x18006fddb  js      loc_18006FEE5
0x18006fde1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18006fde8  mov     ecx, 40h ; '@'; unsigned __int64
0x18006fded  mov     edi, 8007000Eh
0x18006fdf2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18006fdf7  mov     [rbp+pv], rax
0x18006fdfb  mov     rbx, rax
0x18006fdfe  test    rax, rax
0x18006fe01  jz      loc_18006FEE5
0x18006fe07  mov     rax, [rbp+arg_0]
0x18006fe0b  mov     [rbx], rax
0x18006fe0e  mov     qword ptr [rbx+8], 0
0x18006fe16  mov     qword ptr [rbx+10h], 0
0x18006fe1e  mov     qword ptr [rbx+18h], 0
0x18006fe26  mov     qword ptr [rbx+20h], 0
0x18006fe2e  mov     qword ptr [rbx+28h], 8
0x18006fe36  mov     dword ptr [rbx+34h], 1
0x18006fe3d  mov     qword ptr [rbx+38h], 0
0x18006fe45  mov     dword ptr [rbx+30h], 0FFFFFFFFh
0x18006fe4c  test    rbx, rbx
0x18006fe4f  jz      loc_18006FEE5
0x18006fe55  mov     rcx, [rbp+arg_18]
0x18006fe59  lea     r8, [rbp+pv]
0x18006fe5d  mov     rdx, [rbp+arg_0]
0x18006fe61  mov     [rbp+pv], 0
0x18006fe69  mov     rax, [rcx]
0x18006fe6c  mov     rax, [rax+38h]
0x18006fe70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fe75  mov     [rbp+arg_0], 0
0x18006fe7d  mov     edi, eax
0x18006fe7f  test    eax, eax
0x18006fe81  js      short loc_18006FEDD
0x18006fe83  mov     rax, [rbp+pv]
0x18006fe87  mov     r9, rsi; unsigned __int16 *
0x18006fe8a  mov     [rsp+50h+var_18], 1; int
0x18006fe92  mov     r8, rsi; unsigned __int16 *
0x18006fe95  mov     [rsp+50h+var_20], 1; enum _SID_NAME_USE
0x18006fe9d  mov     rdx, rbx; struct CUserObject *
0x18006fea0  mov     [rsp+50h+var_28], rax; unsigned __int16 *
0x18006fea5  mov     [rsp+50h+var_30], 0; unsigned __int16 *
0x18006feae  call    ?_FillObjectDetails@CSidResolver@@IEAAJPEAVCUserObject@@PEBG111W4_SID_NAME_USE@@H@Z; CSidResolver::_FillObjectDetails(CUserObject *,ushort const *,ushort const *,ushort const *,ushort const *,_SID_NAME_USE,int)
0x18006feb3  mov     edi, eax
0x18006feb5  test    eax, eax
0x18006feb7  js      short loc_18006FECE
0x18006feb9  mov     rdx, rbx
0x18006febc  mov     rcx, r14
0x18006febf  call    ?AppendPtr@?$CDPA_Base@VCShareUserInfo@@VCTContainer_PolicyNewMem@@@@QEAAJPEAVCShareUserInfo@@PEAH@Z; CDPA_Base<CShareUserInfo,CTContainer_PolicyNewMem>::AppendPtr(CShareUserInfo *,int *)
0x18006fec4  mov     edi, eax
0x18006fec6  xor     eax, eax
0x18006fec8  test    edi, edi
0x18006feca  cmovns  rbx, rax
0x18006fece  mov     rcx, [rbp+pv]; pv
0x18006fed2  call    cs:__imp_CoTaskMemFree
0x18006fed8  test    rbx, rbx
0x18006fedb  jz      short loc_18006FEE5
0x18006fedd  mov     rcx, rbx; this
0x18006fee0  call    ??_GCUserObject@@QEAAPEAXI@Z; CUserObject::`scalar deleting destructor'(uint)
0x18006fee5  mov     rcx, [rbp+arg_0]; pv
0x18006fee9  call    cs:__imp_CoTaskMemFree
0x18006feef  mov     rcx, [rbp+arg_18]
0x18006fef3  mov     rax, [rcx]
0x18006fef6  mov     rax, [rax+10h]
0x18006fefa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006feff  lea     r11, [rsp+50h+var_s0]
0x18006ff04  mov     eax, edi
0x18006ff06  mov     rbx, [r11+28h]
0x18006ff0a  mov     rsi, [r11+30h]
0x18006ff0e  mov     rsp, r11
0x18006ff11  pop     r14
0x18006ff13  pop     rdi
0x18006ff14  pop     rbp
0x18006ff15  retn
```
