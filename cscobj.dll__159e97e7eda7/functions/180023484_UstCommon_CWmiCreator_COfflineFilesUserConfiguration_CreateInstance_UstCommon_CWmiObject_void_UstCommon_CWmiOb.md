# UstCommon::CWmiCreator<COfflineFilesUserConfiguration>::CreateInstance<UstCommon::CWmiObject>(void *,UstCommon::CWmiObject * *)

- ea: `0x180023484`
- end: `0x180023586`
- name: `??$CreateInstance@VCWmiObject@UstCommon@@@?$CWmiCreator@VCOfflineFilesUserConfiguration@@@UstCommon@@SAJPEAXPEAPEAVCWmiObject@1@@Z`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180025de0`

## callees

- `0x18000bb9c`
- `0x180023484`
- `0x18002c010`

## string_xrefs

- `0x18002351d`: `Win32_OfflineFilesUserConfiguration`

## pseudocode

```c
__int64 __fastcall UstCommon::CWmiCreator<COfflineFilesUserConfiguration>::CreateInstance<UstCommon::CWmiObject>(
        __int64 a1,
        _QWORD *a2)
{
  int v3; // edi
  _DWORD *v4; // rax
  _DWORD *v5; // rbx

  v3 = -2147024882;
  v4 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    *(_QWORD *)v4 = &CRefCounted::`vftable';
    v4[2] = 0;
    *((_QWORD *)v4 + 2) = &UstCommon::CWmiLanternObject::`vftable';
    v4[6] = 0;
    *((_QWORD *)v4 + 4) = 0;
    v4[10] = 0;
    *((_QWORD *)v4 + 6) = 0;
    v4[14] = 0;
    *((_QWORD *)v4 + 8) = 0;
    v4[11] = 16;
    *(_QWORD *)v4 = &UstCommon::CWmiObject::`vftable'{for `UstCommon::CRefCounted'};
    *((_QWORD *)v4 + 2) = &UstCommon::CWmiLanternObject::`vftable';
    *((_QWORD *)v4 + 9) = L"Win32_OfflineFilesUserConfiguration";
    _InterlockedIncrement(&g_cUstRefDll);
    *(_QWORD *)v4 = &COfflineFilesUserConfiguration::`vftable'{for `UstCommon::CRefCounted'};
    *((_QWORD *)v4 + 2) = &UstCommon::CWmiLanternObject::`vftable';
    v3 = ((__int64 (__fastcall *)(_DWORD *, _QWORD))CWmiQueryCancel_Never::QueryCancel)(v4, 0);
    if ( v3 < 0 )
    {
      (**(void (__fastcall ***)(_DWORD *, __int64))v5)(v5, 1);
    }
    else
    {
      _InterlockedIncrement(v5 + 2);
      *a2 = v5;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180023484  mov     [rsp+arg_0], rbx
0x180023489  mov     [rsp+arg_8], rsi
0x18002348e  push    rdi
0x18002348f  sub     rsp, 20h
0x180023493  mov     rsi, rdx
0x180023496  mov     edi, 8007000Eh
0x18002349b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800234a2  mov     ecx, 50h ; 'P'; unsigned __int64
0x1800234a7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800234ac  mov     rbx, rax
0x1800234af  test    rax, rax
0x1800234b2  jz      loc_180023574
0x1800234b8  lea     rax, ??_7CRefCounted@@6B@; const CRefCounted::`vftable'
0x1800234bf  mov     [rbx], rax
0x1800234c2  mov     dword ptr [rbx+8], 0
0x1800234c9  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x1800234d0  mov     [rbx+10h], rax
0x1800234d4  mov     dword ptr [rbx+18h], 0
0x1800234db  mov     qword ptr [rbx+20h], 0
0x1800234e3  mov     dword ptr [rbx+28h], 0
0x1800234ea  mov     qword ptr [rbx+30h], 0
0x1800234f2  mov     dword ptr [rbx+38h], 0
0x1800234f9  mov     qword ptr [rbx+40h], 0
0x180023501  mov     dword ptr [rbx+2Ch], 10h
0x180023508  lea     rax, ??_7CWmiObject@UstCommon@@6BCRefCounted@1@@; const UstCommon::CWmiObject::`vftable'{for `UstCommon::CRefCounted'}
0x18002350f  mov     [rbx], rax
0x180023512  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x180023519  mov     [rbx+10h], rax
0x18002351d  lea     rax, CSCWMI_STR_OFFLINEFILESUSERCONFIGURATION; "Win32_OfflineFilesUserConfiguration"
0x180023524  mov     [rbx+48h], rax
0x180023528  lock inc cs:?g_cUstRefDll@@3JA; long g_cUstRefDll
0x18002352f  lea     r8, ??_7COfflineFilesUserConfiguration@@6BCRefCounted@UstCommon@@@; const COfflineFilesUserConfiguration::`vftable'{for `UstCommon::CRefCounted'}
0x180023536  mov     [rbx], r8
0x180023539  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x180023540  mov     [rbx+10h], rax
0x180023544  xor     edx, edx
0x180023546  mov     rcx, rbx
0x180023549  mov     rax, [r8+8]
0x18002354d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023552  mov     edi, eax
0x180023554  test    eax, eax
0x180023556  js      short loc_180023561
0x180023558  lock inc dword ptr [rbx+8]
0x18002355c  mov     [rsi], rbx
0x18002355f  jmp     short loc_180023574
0x180023561  mov     rax, [rbx]
0x180023564  mov     edx, 1
0x180023569  mov     rcx, rbx
0x18002356c  mov     rax, [rax]
0x18002356f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023574  mov     eax, edi
0x180023576  mov     rbx, [rsp+28h+arg_0]
0x18002357b  mov     rsi, [rsp+28h+arg_8]
0x180023580  add     rsp, 20h
0x180023584  pop     rdi
0x180023585  retn
```
