# WebRuntimeDiagnostics::LCIEWebruntimeDiagnostics_ThreadProc(void *)

- ea: `0x18006f0a0`
- end: `0x18006f14a`
- name: `?LCIEWebruntimeDiagnostics_ThreadProc@WebRuntimeDiagnostics@@YAKPEAX@Z`
- size: `170`
- prototype: `unsigned int __fastcall(WebRuntimeDiagnostics *__hidden this, void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180037b5c`
- `0x18006932c`
- `0x18006ea64`
- `0x18006f0a0`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18006f123`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PostMessageW` at `0x18006f123`
- `edgeIso!__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x18006f0c1`
- `edgeIso!__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z` at `0x18006f0c1`
- `edgeIso!__imp_?IsoReferenceThread@@YAKK@Z` at `0x18006f10f`
- `edgeIso!__imp_?IsoReferenceThread@@YAKK@Z` at `0x18006f10f`

## pseudocode

```c
__int64 __fastcall WebRuntimeDiagnostics::LCIEWebruntimeDiagnostics_ThreadProc(WebRuntimeDiagnostics *this, void *a2)
{
  __int64 v2; // rcx
  HWND *v3; // rbx
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  _IsoComponent *v7; // [rsp+30h] [rbp+8h] BYREF

  v2 = *((unsigned int *)this + 102);
  v7 = 0;
  if ( !(unsigned int)IsoGetArtifactAddress(v2, 1, &v7) )
  {
    v3 = (HWND *)((char *)v7 + 56);
    _IsoComponent::SetAppObj(v7, (char *)v7 + 56);
    *((_DWORD *)v7 + 12) = 4;
    *((_WORD *)v7 + 1) = 526;
    _IsoComponent::SetFromSHAREDMEM_64BITVALUE(
      v7,
      *((unsigned int *)v7 + 12),
      WebRuntimeDiagnostics::LCIEDiagnosticsTarget::LCIEProcessMessage);
    IsoReferenceThread(*((_DWORD *)v7 + 10));
    if ( !PostMessageW(*v3, 0x400u, 0, 0) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticstarget.cpp",
        v4);
  }
  return 0;
}

```

## disassembly

```asm
0x18006f0a0  push    rbx
0x18006f0a2  sub     rsp, 20h
0x18006f0a6  mov     ecx, [rcx+198h]
0x18006f0ac  lea     r8, [rsp+28h+arg_0]
0x18006f0b1  xor     r9d, r9d
0x18006f0b4  mov     [rsp+28h+arg_0], 0
0x18006f0bd  lea     edx, [r9+1]
0x18006f0c1  call    cs:__imp_?IsoGetArtifactAddress@@YAJKW4IsoArtifactType@@PEAPEAU_IsoArtifact@@PEAK@Z; IsoGetArtifactAddress(ulong,IsoArtifactType,_IsoArtifact * *,ulong *)
0x18006f0c7  test    eax, eax
0x18006f0c9  jnz     short loc_18006F142
0x18006f0cb  mov     rcx, [rsp+28h+arg_0]; this
0x18006f0d0  lea     rbx, [rcx+38h]
0x18006f0d4  mov     rdx, rbx; void *
0x18006f0d7  call    ?SetAppObj@_IsoComponent@@QEAAXQEAX@Z; _IsoComponent::SetAppObj(void * const)
0x18006f0dc  mov     rax, [rsp+28h+arg_0]
0x18006f0e1  lea     r8, ?LCIEProcessMessage@LCIEDiagnosticsTarget@WebRuntimeDiagnostics@@SA_JPEAUHWND__@@I_K_J@Z; WebRuntimeDiagnostics::LCIEDiagnosticsTarget::LCIEProcessMessage(HWND__ *,uint,unsigned __int64,__int64)
0x18006f0e8  mov     dword ptr [rax+30h], 4
0x18006f0ef  mov     rax, [rsp+28h+arg_0]
0x18006f0f4  mov     word ptr [rax+2], 20Eh
0x18006f0fa  mov     rcx, [rsp+28h+arg_0]
0x18006f0ff  mov     edx, [rcx+30h]
0x18006f102  call    ?SetFromSHAREDMEM_64BITVALUE@_IsoComponent@@QEAAXW4_IsoComponentDispatchType@@USHAREDMEM_64BITVALUE@@@Z; _IsoComponent::SetFromSHAREDMEM_64BITVALUE(_IsoComponentDispatchType,SHAREDMEM_64BITVALUE)
0x18006f107  mov     rcx, [rsp+28h+arg_0]
0x18006f10c  mov     ecx, [rcx+28h]
0x18006f10f  call    cs:__imp_?IsoReferenceThread@@YAKK@Z; IsoReferenceThread(ulong)
0x18006f115  mov     rcx, [rbx]; hWnd
0x18006f118  xor     r9d, r9d; lParam
0x18006f11b  xor     r8d, r8d; wParam
0x18006f11e  mov     edx, 400h; Msg
0x18006f123  call    cs:__imp_PostMessageW
0x18006f129  test    eax, eax
0x18006f12b  jnz     short loc_18006F142
0x18006f12d  mov     rcx, [rsp+28h]; this
0x18006f132  lea     r8, aOnecoreuapInet_16; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18006f139  lea     edx, [rax+2Dh]; void *
0x18006f13c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18006f142  xor     eax, eax
0x18006f144  add     rsp, 20h
0x18006f148  pop     rbx
0x18006f149  retn
```
