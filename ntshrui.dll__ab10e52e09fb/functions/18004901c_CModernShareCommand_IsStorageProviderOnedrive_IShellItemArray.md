# CModernShareCommand::IsStorageProviderOnedrive(IShellItemArray *)

- ea: `0x18004901c`
- end: `0x18004914c`
- name: `?IsStorageProviderOnedrive@CModernShareCommand@@AEAA_NPEAUIShellItemArray@@@Z`
- size: `304`
- prototype: `bool __fastcall(CModernShareCommand *__hidden this, struct IShellItemArray *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180047af0`

## callees

- `0x18001d18c`
- `0x18002cdd0`
- `0x18004901c`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800490df`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800490df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800490f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004911e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800490f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004911e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall CModernShareCommand::IsStorageProviderOnedrive(CModernShareCommand *this, struct IShellItemArray *a2)
{
  struct IShellItemArrayVtbl *lpVtbl; // rax
  int (*GetItemAt)(void); // rax
  int (__fastcall **v4)(_QWORD, GUID *, CModernShareCommand **); // rax
  CModernShareCommand *v5; // rdi
  int (__fastcall *v6)(CModernShareCommand *, const PROPERTYKEY *, __int64); // rbx
  __int64 v7; // r8
  unsigned int v8; // r8d
  const char *v9; // r9
  char result; // al
  wil *v11; // rcx
  DWORD v12; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  CModernShareCommand *v14; // [rsp+40h] [rbp+8h] BYREF
  LPCWCH lpString1; // [rsp+48h] [rbp+10h] BYREF
  int (__fastcall ***v16)(_QWORD, GUID *, CModernShareCommand **); // [rsp+50h] [rbp+18h] BYREF

  v14 = this;
  lpVtbl = a2->lpVtbl;
  v16 = 0;
  GetItemAt = (int (*)(void))lpVtbl->GetItemAt;
  try
  {
    if ( GetItemAt() >= 0 )
    {
      v14 = 0;
      v4 = *v16;
      v14 = 0;
      if ( (*v4)(v16, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &v14) >= 0 )
      {
        lpString1 = 0;
        v5 = v14;
        v6 = *(int (__fastcall **)(CModernShareCommand *, const PROPERTYKEY *, __int64))(*(_QWORD *)v14 + 136LL);
        v7 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&lpString1);
        if ( v6(v5, &PKEY_StorageProviderId, v7) >= 0 && CompareStringOrdinal(lpString1, -1, L"OneDrive", -1, 1) == 2 )
        {
          if ( lpString1 )
            CoTaskMemFree((LPVOID)lpString1);
          wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v14);
          wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v16);
          return 1;
        }
        if ( lpString1 )
          CoTaskMemFree((LPVOID)lpString1);
      }
      wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v14);
    }
    wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v16);
    result = 0;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(retaddr, (void *)0x8E8, v8, v9);
    v12 = wil::ResultFromCaughtException(v11);
    SetLastError(v12);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18004901c  mov     r11, rsp
0x18004901f  mov     [r11+20h], rbx
0x180049023  mov     [r11+8], rcx
0x180049027  push    rdi
0x180049028  sub     rsp, 30h
0x18004902c  mov     r9, rdx
0x18004902f  mov     rax, [rdx]
0x180049032  mov     qword ptr [r11+18h], 0
0x18004903a  lea     r8, [r11+18h]
0x18004903e  xor     edx, edx
0x180049040  mov     rcx, r9
0x180049043  mov     rax, [rax+40h]
0x180049047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004904c  test    eax, eax
0x18004904e  js      loc_180049130
0x180049054  mov     [rsp+38h+arg_0], 0
0x18004905d  mov     rcx, [rsp+38h+arg_10]
0x180049062  mov     rax, [rcx]
0x180049065  mov     [rsp+38h+arg_0], 0
0x18004906e  lea     r8, [rsp+38h+arg_0]
0x180049073  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x18004907a  mov     rax, [rax]
0x18004907d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049082  test    eax, eax
0x180049084  js      loc_180049125
0x18004908a  mov     [rsp+38h+lpString1], 0
0x180049093  mov     rdi, [rsp+38h+arg_0]
0x180049098  mov     rax, [rdi]
0x18004909b  mov     rbx, [rax+88h]
0x1800490a2  lea     rcx, [rsp+38h+lpString1]
0x1800490a7  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x1800490ac  mov     r8, rax
0x1800490af  lea     rdx, PKEY_StorageProviderId
0x1800490b6  mov     rcx, rdi
0x1800490b9  mov     rax, rbx
0x1800490bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800490c1  test    eax, eax
0x1800490c3  js      short loc_180049114
0x1800490c5  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800490cd  or      edx, 0FFFFFFFFh; cchCount1
0x1800490d0  mov     r9d, edx; cchCount2
0x1800490d3  lea     r8, aOnedrive_2; "OneDrive"
0x1800490da  mov     rcx, [rsp+38h+lpString1]; lpString1
0x1800490df  call    cs:__imp_CompareStringOrdinal
0x1800490e5  cmp     eax, 2
0x1800490e8  jnz     short loc_180049114
0x1800490ea  mov     rcx, [rsp+38h+lpString1]; pv
0x1800490ef  test    rcx, rcx
0x1800490f2  jz      short loc_1800490FB
0x1800490f4  call    cs:__imp_CoTaskMemFree
0x1800490fa  nop
0x1800490fb  lea     rcx, [rsp+38h+arg_0]
0x180049100  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180049105  nop
0x180049106  lea     rcx, [rsp+38h+arg_10]
0x18004910b  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x180049110  mov     al, 1
0x180049112  jmp     short loc_180049140
0x180049114  mov     rcx, [rsp+38h+lpString1]; pv
0x180049119  test    rcx, rcx
0x18004911c  jz      short loc_180049125
0x18004911e  call    cs:__imp_CoTaskMemFree
0x180049124  nop
0x180049125  lea     rcx, [rsp+38h+arg_0]
0x18004912a  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004912f  nop
0x180049130  lea     rcx, [rsp+38h+arg_10]
0x180049135  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18004913a  xor     al, al
0x18004913c  jmp     short loc_180049140
0x18004913e  xor     al, al
0x180049140  mov     rbx, [rsp+38h+arg_18]
0x180049145  add     rsp, 30h
0x180049149  pop     rdi
0x18004914a  retn
```
