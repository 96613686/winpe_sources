# CSNOCplCore::OnNavTaskLinkClicked(int)

- ea: `0x18000de90`
- end: `0x18000df91`
- name: `?OnNavTaskLinkClicked@CSNOCplCore@@QEAAXH@Z`
- size: `257`
- prototype: `void __fastcall(LPARAM lParam, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180014f80`

## callees

- `0x180007e50`
- `0x18000de90`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000df7b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000df00`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000df00`
- `SHLWAPI!SHStrDupW` at `0x18000df45`
- `SHLWAPI!SHStrDupW` at `0x18000df45`
- `USER32!PostMessageW` at `0x18000df63`
- `USER32!PostMessageW` at `0x18000df63`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSNOCplCore::OnNavTaskLinkClicked(LPARAM lParam, int a2)
{
  unsigned __int64 v3; // rbx
  __int64 v4; // rbx
  LPWSTR v5; // rcx
  LPWSTR ppwsz; // [rsp+50h] [rbp+18h] BYREF

  if ( a2 - 1 >= 0 )
  {
    v3 = a2 - 1LL;
    if ( v3 < 3 )
    {
      v4 = 32 * v3;
      (*(void (**)(void))((char *)&unk_180024360 + v4 + 8))();
      ppwsz = 0;
      if ( *(_DWORD *)((char *)&unk_180024360 + v4 + 16) )
      {
        if ( CoCreateInstance(
               &CLSID_OpenControlPanel,
               0,
               0x17u,
               &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1,
               (LPVOID *)&ppwsz) >= 0 )
          (*(void (__fastcall **)(LPWSTR, const unsigned __int16 *, _QWORD, _QWORD))(*(_QWORD *)ppwsz + 24LL))(
            ppwsz,
            L"Microsoft.NetworkAndSharingCenter",
            *(_QWORD *)((char *)&unk_180024360 + v4 + 24),
            *(_QWORD *)(lParam + 344));
        ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>(&ppwsz);
      }
      else if ( SHStrDupW(*(LPCWSTR *)((char *)&unk_180024360 + v4 + 24), &ppwsz) >= 0 )
      {
        if ( PostMessageW(*(HWND *)(lParam + 256), 0x800Fu, (WPARAM)ppwsz, lParam) )
        {
          v5 = 0;
          ppwsz = 0;
        }
        else
        {
          v5 = ppwsz;
        }
        CoTaskMemFree(v5);
      }
    }
  }
}

```

## disassembly

```asm
0x18000de90  mov     [rsp+arg_0], rbx
0x18000de95  mov     [rsp+arg_8], rbp
0x18000de9a  push    rdi
0x18000de9b  sub     rsp, 30h
0x18000de9f  mov     rdi, rcx
0x18000dea2  lea     eax, [rdx-1]
0x18000dea5  test    eax, eax
0x18000dea7  js      loc_18000DF81
0x18000dead  movsxd  rbx, edx
0x18000deb0  dec     rbx
0x18000deb3  cmp     rbx, 3
0x18000deb7  jnb     loc_18000DF81
0x18000debd  shl     rbx, 5
0x18000dec1  lea     rbp, unk_180024360
0x18000dec8  mov     rax, [rbx+rbp+8]
0x18000decd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ded2  mov     [rsp+38h+ppwsz], 0
0x18000dedb  cmp     dword ptr [rbx+rbp+10h], 0
0x18000dee0  jz      short loc_18000DF3B
0x18000dee2  lea     rax, [rsp+38h+ppwsz]
0x18000dee7  mov     [rsp+38h+ppv], rax; ppv
0x18000deec  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x18000def3  xor     edx, edx; pUnkOuter
0x18000def5  lea     r8d, [rdx+17h]; dwClsContext
0x18000def9  lea     rcx, CLSID_OpenControlPanel; rclsid
0x18000df00  call    cs:__imp_CoCreateInstance
0x18000df06  test    eax, eax
0x18000df08  js      short loc_18000DF2F
0x18000df0a  mov     rcx, [rsp+38h+ppwsz]
0x18000df0f  mov     rax, [rcx]
0x18000df12  mov     r9, [rdi+158h]
0x18000df19  mov     r8, [rbx+rbp+18h]
0x18000df1e  lea     rdx, aMicrosoftNetwo; "Microsoft.NetworkAndSharingCenter"
0x18000df25  mov     rax, [rax+18h]
0x18000df29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df2e  nop
0x18000df2f  lea     rcx, [rsp+38h+ppwsz]
0x18000df34  call    ??1?$CComPtrBase@UIShellFolder2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IShellFolder2>::~CComPtrBase<IShellFolder2>(void)
0x18000df39  jmp     short loc_18000DF81
0x18000df3b  lea     rdx, [rsp+38h+ppwsz]; ppwsz
0x18000df40  mov     rcx, [rbx+rbp+18h]; psz
0x18000df45  call    cs:__imp_SHStrDupW
0x18000df4b  test    eax, eax
0x18000df4d  js      short loc_18000DF81
0x18000df4f  mov     r9, rdi; lParam
0x18000df52  mov     r8, [rsp+38h+ppwsz]; wParam
0x18000df57  mov     edx, 800Fh; Msg
0x18000df5c  mov     rcx, [rdi+100h]; hWnd
0x18000df63  call    cs:__imp_PostMessageW
0x18000df69  test    eax, eax
0x18000df6b  jz      short loc_18000DF76
0x18000df6d  xor     ecx, ecx
0x18000df6f  mov     [rsp+38h+ppwsz], rcx
0x18000df74  jmp     short loc_18000DF7B
0x18000df76  mov     rcx, [rsp+38h+ppwsz]; pv
0x18000df7b  call    cs:__imp_CoTaskMemFree
0x18000df81  mov     rbx, [rsp+38h+arg_0]
0x18000df86  mov     rbp, [rsp+38h+arg_8]
0x18000df8b  add     rsp, 30h
0x18000df8f  pop     rdi
0x18000df90  retn
```
