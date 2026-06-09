# UstCommon::CWmiCreator<COfflineFilesMachineConfiguration>::CreateInstance<UstCommon::CWmiObject>(void *,UstCommon::CWmiObject * *)

- ea: `0x18002337c`
- end: `0x18002347e`
- name: `??$CreateInstance@VCWmiObject@UstCommon@@@?$CWmiCreator@VCOfflineFilesMachineConfiguration@@@UstCommon@@SAJPEAXPEAPEAVCWmiObject@1@@Z`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180025de0`

## callees

- `0x18000bb9c`
- `0x18002337c`
- `0x18002c010`

## string_xrefs

- `0x180023415`: `Win32_OfflineFilesMachineConfiguration`

## pseudocode

```c
__int64 __fastcall UstCommon::CWmiCreator<COfflineFilesMachineConfiguration>::CreateInstance<UstCommon::CWmiObject>(
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
    *((_QWORD *)v4 + 9) = L"Win32_OfflineFilesMachineConfiguration";
    _InterlockedIncrement(&g_cUstRefDll);
    *(_QWORD *)v4 = &COfflineFilesMachineConfiguration::`vftable'{for `UstCommon::CRefCounted'};
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
0x18002337c  mov     [rsp+arg_0], rbx
0x180023381  mov     [rsp+arg_8], rsi
0x180023386  push    rdi
0x180023387  sub     rsp, 20h
0x18002338b  mov     rsi, rdx
0x18002338e  mov     edi, 8007000Eh
0x180023393  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002339a  mov     ecx, 50h ; 'P'; unsigned __int64
0x18002339f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800233a4  mov     rbx, rax
0x1800233a7  test    rax, rax
0x1800233aa  jz      loc_18002346C
0x1800233b0  lea     rax, ??_7CRefCounted@@6B@; const CRefCounted::`vftable'
0x1800233b7  mov     [rbx], rax
0x1800233ba  mov     dword ptr [rbx+8], 0
0x1800233c1  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x1800233c8  mov     [rbx+10h], rax
0x1800233cc  mov     dword ptr [rbx+18h], 0
0x1800233d3  mov     qword ptr [rbx+20h], 0
0x1800233db  mov     dword ptr [rbx+28h], 0
0x1800233e2  mov     qword ptr [rbx+30h], 0
0x1800233ea  mov     dword ptr [rbx+38h], 0
0x1800233f1  mov     qword ptr [rbx+40h], 0
0x1800233f9  mov     dword ptr [rbx+2Ch], 10h
0x180023400  lea     rax, ??_7CWmiObject@UstCommon@@6BCRefCounted@1@@; const UstCommon::CWmiObject::`vftable'{for `UstCommon::CRefCounted'}
0x180023407  mov     [rbx], rax
0x18002340a  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x180023411  mov     [rbx+10h], rax
0x180023415  lea     rax, CSCWMI_STR__OFFLINEFILESMACHINECONFIGURATION; "Win32_OfflineFilesMachineConfiguration"
0x18002341c  mov     [rbx+48h], rax
0x180023420  lock inc cs:?g_cUstRefDll@@3JA; long g_cUstRefDll
0x180023427  lea     r8, ??_7COfflineFilesMachineConfiguration@@6BCRefCounted@UstCommon@@@; const COfflineFilesMachineConfiguration::`vftable'{for `UstCommon::CRefCounted'}
0x18002342e  mov     [rbx], r8
0x180023431  lea     rax, ??_7CWmiLanternObject@UstCommon@@6B@; const UstCommon::CWmiLanternObject::`vftable'
0x180023438  mov     [rbx+10h], rax
0x18002343c  xor     edx, edx
0x18002343e  mov     rcx, rbx
0x180023441  mov     rax, [r8+8]
0x180023445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002344a  mov     edi, eax
0x18002344c  test    eax, eax
0x18002344e  js      short loc_180023459
0x180023450  lock inc dword ptr [rbx+8]
0x180023454  mov     [rsi], rbx
0x180023457  jmp     short loc_18002346C
0x180023459  mov     rax, [rbx]
0x18002345c  mov     edx, 1
0x180023461  mov     rcx, rbx
0x180023464  mov     rax, [rax]
0x180023467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002346c  mov     eax, edi
0x18002346e  mov     rbx, [rsp+28h+arg_0]
0x180023473  mov     rsi, [rsp+28h+arg_8]
0x180023478  add     rsp, 20h
0x18002347c  pop     rdi
0x18002347d  retn
```
