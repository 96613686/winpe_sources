# CRegionPlugin::_CommitPendingRegion(void)

- ea: `0x18004a6c4`
- end: `0x18004a7cc`
- name: `?_CommitPendingRegion@CRegionPlugin@@AEAAJXZ`
- size: `264`
- prototype: `__int64 __fastcall(CRegionPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18004a110`

## callees

- `0x1800098cc`
- `0x180026b68`
- `0x18004a6c4`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!SetUserGeoID` at `0x18004a729`
- `api-ms-win-core-localization-l1-2-0!SetUserGeoID` at `0x18004a729`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a78f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a78f`

## string_xrefs

- `0x18004a7b1`: `Skipping commit region - no pending region to set.`
- `0x18004a79c`: `Failed to commit region with hr=0x%08X`
- `0x18004a754`: `Successfully committed region [%s]`
- `0x18004a771`: `Failed to commit region [%s] with hr=0x%08X`

## pseudocode

```c
__int64 __fastcall CRegionPlugin::_CommitPendingRegion(CRegionPlugin *this)
{
  _QWORD *v1; // rdi
  __int64 v2; // rcx
  int v3; // ebx
  __int64 v4; // rcx
  GEOID GeoId; // [rsp+30h] [rbp+8h] BYREF
  LPVOID pv; // [rsp+38h] [rbp+10h] BYREF

  v1 = (_QWORD *)((char *)this + 64);
  v2 = *((_QWORD *)this + 8);
  if ( v2 )
  {
    GeoId = 0;
    pv = 0;
    v3 = -2147418113;
    if ( (*(int (__fastcall **)(__int64, GEOID *))(*(_QWORD *)v2 + 40LL))(v2, &GeoId) < 0
      || (*(int (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*v1 + 24LL))(*v1, &pv) < 0 )
    {
      goto LABEL_10;
    }
    if ( SetUserGeoID(GeoId) )
    {
      v3 = 0;
      if ( (Microsoft_Windows_OOBE_Machine_PluginsEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer(v4, RegionSelection_Info, (unsigned int)GeoId);
      UnattendLogW(0, L"Successfully committed region [%s]", pv);
      SafeRelease<IOOBETimeZoneItem>(v1);
    }
    else
    {
      v3 = -2147467259;
      UnattendLogW(1, L"Failed to commit region [%s] with hr=0x%08X", pv, 2147500037LL);
    }
    CoTaskMemFree(pv);
    if ( v3 < 0 )
LABEL_10:
      UnattendLogW(1, L"Failed to commit region with hr=0x%08X", (unsigned int)v3);
  }
  else
  {
    v3 = 0;
    UnattendLogW(0, L"Skipping commit region - no pending region to set.");
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004a6c4  mov     [rsp+arg_10], rbx
0x18004a6c9  push    rdi
0x18004a6ca  sub     rsp, 20h
0x18004a6ce  lea     rdi, [rcx+40h]
0x18004a6d2  mov     rcx, [rdi]
0x18004a6d5  test    rcx, rcx
0x18004a6d8  jz      loc_18004A7AF
0x18004a6de  mov     [rsp+28h+GeoId], 0
0x18004a6e6  lea     rdx, [rsp+28h+GeoId]
0x18004a6eb  mov     [rsp+28h+pv], 0
0x18004a6f4  mov     ebx, 8000FFFFh
0x18004a6f9  mov     rax, [rcx]
0x18004a6fc  mov     rax, [rax+28h]
0x18004a700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a705  test    eax, eax
0x18004a707  js      loc_18004A799
0x18004a70d  mov     rcx, [rdi]
0x18004a710  lea     rdx, [rsp+28h+pv]
0x18004a715  mov     rax, [rcx]
0x18004a718  mov     rax, [rax+18h]
0x18004a71c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a721  test    eax, eax
0x18004a723  js      short loc_18004A799
0x18004a725  mov     ecx, [rsp+28h+GeoId]; GeoId
0x18004a729  call    cs:__imp_SetUserGeoID
0x18004a72f  test    eax, eax
0x18004a731  jz      short loc_18004A76C
0x18004a733  xor     ebx, ebx
0x18004a735  test    byte ptr cs:Microsoft_Windows_OOBE_Machine_PluginsEnableBits, 1
0x18004a73c  jz      short loc_18004A74F
0x18004a73e  mov     r8d, [rsp+28h+GeoId]
0x18004a743  lea     rdx, RegionSelection_Info
0x18004a74a  call    McTemplateU0q_EventWriteTransfer
0x18004a74f  mov     r8, [rsp+28h+pv]
0x18004a754  lea     rdx, aSuccessfullyCo_1; "Successfully committed region [%s]"
0x18004a75b  xor     ecx, ecx
0x18004a75d  call    UnattendLogW
0x18004a762  mov     rcx, rdi
0x18004a765  call    ??$SafeRelease@UIOOBETimeZoneItem@@@@YAXPEAPEAUIOOBETimeZoneItem@@@Z; SafeRelease<IOOBETimeZoneItem>(IOOBETimeZoneItem * *)
0x18004a76a  jmp     short loc_18004A78A
0x18004a76c  mov     r8, [rsp+28h+pv]
0x18004a771  lea     rdx, aFailedToCommit; "Failed to commit region [%s] with hr=0x"...
0x18004a778  mov     ebx, 80004005h
0x18004a77d  mov     ecx, 1
0x18004a782  mov     r9d, ebx
0x18004a785  call    UnattendLogW
0x18004a78a  mov     rcx, [rsp+28h+pv]; pv
0x18004a78f  call    cs:__imp_CoTaskMemFree
0x18004a795  test    ebx, ebx
0x18004a797  jns     short loc_18004A7BF
0x18004a799  mov     r8d, ebx
0x18004a79c  lea     rdx, aFailedToCommit_6; "Failed to commit region with hr=0x%08X"
0x18004a7a3  mov     ecx, 1
0x18004a7a8  call    UnattendLogW
0x18004a7ad  jmp     short loc_18004A7BF
0x18004a7af  xor     ebx, ebx
0x18004a7b1  lea     rdx, aSkippingCommit_1; "Skipping commit region - no pending reg"...
0x18004a7b8  xor     ecx, ecx
0x18004a7ba  call    UnattendLogW
0x18004a7bf  mov     eax, ebx
0x18004a7c1  mov     rbx, [rsp+28h+arg_10]
0x18004a7c6  add     rsp, 20h
0x18004a7ca  pop     rdi
0x18004a7cb  retn
```
