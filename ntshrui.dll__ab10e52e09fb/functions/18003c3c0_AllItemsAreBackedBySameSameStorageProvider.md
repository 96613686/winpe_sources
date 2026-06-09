# AllItemsAreBackedBySameSameStorageProvider

- ea: `0x18003c3c0`
- end: `0x18003c56b`
- name: `AllItemsAreBackedBySameSameStorageProvider`
- size: `427`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001f880`
- `0x18004f758`

## callees

- `0x18001d18c`
- `0x18002cdd0`
- `0x180036bd8`
- `0x18003c3c0`
- `0x180045fc8`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c4f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c517`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c53d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c557`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c4f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c517`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c53d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c557`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
bool __fastcall AllItemsAreBackedBySameSameStorageProvider(__int64 *a1, char a2)
{
  bool v4; // bl
  __int64 v5; // rax
  unsigned __int16 **v6; // rax
  unsigned int v7; // edi
  unsigned int v8; // esi
  __int64 v9; // rax
  unsigned __int16 **v10; // rax
  unsigned __int16 *v11; // rax
  int v12; // r8d
  int v13; // r9d
  struct IShellItem *v15; // [rsp+20h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-8h] BYREF
  unsigned int v17; // [rsp+60h] [rbp+30h] BYREF
  char v18; // [rsp+68h] [rbp+38h] BYREF
  struct IShellItem *v19; // [rsp+70h] [rbp+40h] BYREF
  LPVOID v20; // [rsp+78h] [rbp+48h] BYREF

  v18 = a2;
  ShareVerbTelemetry::ShareVerb_CheckedStorageProviderNames<bool &>(&v18);
  v17 = 0;
  v4 = 0;
  if ( (*(int (__fastcall **)(__int64 *, unsigned int *))(*a1 + 56))(a1, &v17) >= 0 && v17 )
  {
    v20 = 0;
    v5 = *a1;
    v15 = 0;
    v4 = 0;
    if ( (*(int (__fastcall **)(__int64 *, _QWORD, struct IShellItem **))(v5 + 64))(a1, 0, &v15) >= 0 )
    {
      v6 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v20);
      if ( (int)GetStorageProviderNameForFolder(v15, v6) >= 0 )
        v4 = 1;
    }
    if ( !a2 )
    {
      v7 = 16;
      if ( v17 > 0x10 )
      {
        v8 = 1;
        goto LABEL_11;
      }
    }
    v7 = v17;
    v8 = 1;
    if ( v17 > 1 )
    {
LABEL_11:
      while ( v4 )
      {
        v9 = *a1;
        v19 = 0;
        if ( (*(int (__fastcall **)(__int64 *, _QWORD, struct IShellItem **))(v9 + 64))(a1, v8, &v19) >= 0 )
        {
          pv = 0;
          v10 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pv);
          if ( (int)GetStorageProviderNameForFolder(v19, v10) < 0 )
          {
            if ( pv )
              CoTaskMemFree(pv);
            wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v19);
            if ( v20 )
              CoTaskMemFree(v20);
            wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v15);
            return 0;
          }
          v11 = (unsigned __int16 *)v20;
          do
          {
            v12 = *(unsigned __int16 *)((char *)v11 + (_BYTE *)pv - (_BYTE *)v20);
            v13 = *v11 - v12;
            if ( v13 )
              break;
            ++v11;
          }
          while ( v12 );
          v4 = v13 == 0;
          if ( pv )
            CoTaskMemFree(pv);
        }
        wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v19);
        if ( ++v8 >= v7 )
          break;
      }
    }
    if ( v20 )
      CoTaskMemFree(v20);
    wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(&v15);
  }
  return v4;
}

```

## disassembly

```asm
0x18003c3c0  mov     [rsp-28h+arg_8], dl
0x18003c3c4  push    rbp
0x18003c3c5  push    rbx
0x18003c3c6  push    rsi
0x18003c3c7  push    rdi
0x18003c3c8  push    r14
0x18003c3ca  mov     rbp, rsp
0x18003c3cd  sub     rsp, 30h
0x18003c3d1  mov     dil, dl
0x18003c3d4  mov     r14, rcx
0x18003c3d7  lea     rcx, [rbp+arg_8]
0x18003c3db  call    ??$ShareVerb_CheckedStorageProviderNames@AEA_N@ShareVerbTelemetry@@SAXAEA_N@Z; ShareVerbTelemetry::ShareVerb_CheckedStorageProviderNames<bool &>(bool &)
0x18003c3e0  mov     [rbp+arg_0], 0
0x18003c3e7  xor     bl, bl
0x18003c3e9  mov     rax, [r14]
0x18003c3ec  lea     rdx, [rbp+arg_0]
0x18003c3f0  mov     rcx, r14
0x18003c3f3  mov     rax, [rax+38h]
0x18003c3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3fc  test    eax, eax
0x18003c3fe  js      loc_18003C527
0x18003c404  cmp     [rbp+arg_0], 0
0x18003c408  jbe     loc_18003C527
0x18003c40e  mov     [rbp+arg_18], 0
0x18003c416  mov     rax, [r14]
0x18003c419  mov     [rbp+var_10], 0
0x18003c421  lea     r8, [rbp+var_10]
0x18003c425  xor     edx, edx
0x18003c427  mov     rcx, r14
0x18003c42a  mov     rax, [rax+40h]
0x18003c42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c433  test    eax, eax
0x18003c435  js      short loc_18003C454
0x18003c437  lea     rcx, [rbp+arg_18]
0x18003c43b  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18003c440  mov     rdx, rax; unsigned __int16 **
0x18003c443  mov     rcx, [rbp+var_10]; struct IShellItem *
0x18003c447  call    ?GetStorageProviderNameForFolder@@YAJPEAUIShellItem@@PEAPEAG@Z; GetStorageProviderNameForFolder(IShellItem *,ushort * *)
0x18003c44c  test    eax, eax
0x18003c44e  js      short loc_18003C454
0x18003c450  mov     bl, 1
0x18003c452  jmp     short loc_18003C456
0x18003c454  xor     bl, bl
0x18003c456  test    dil, dil
0x18003c459  jnz     short loc_18003C46A
0x18003c45b  mov     edi, 10h
0x18003c460  cmp     [rbp+arg_0], edi
0x18003c463  jbe     short loc_18003C46A
0x18003c465  lea     esi, [rdi-0Fh]
0x18003c468  jmp     short loc_18003C47A
0x18003c46a  mov     edi, [rbp+arg_0]
0x18003c46d  mov     esi, 1
0x18003c472  cmp     edi, esi
0x18003c474  jbe     loc_18003C50E
0x18003c47a  test    bl, bl
0x18003c47c  jz      loc_18003C50E
0x18003c482  mov     rax, [r14]
0x18003c485  mov     [rbp+arg_10], 0
0x18003c48d  lea     r8, [rbp+arg_10]
0x18003c491  mov     edx, esi
0x18003c493  mov     rcx, r14
0x18003c496  mov     rax, [rax+40h]
0x18003c49a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c49f  test    eax, eax
0x18003c4a1  js      short loc_18003C4FB
0x18003c4a3  mov     [rbp+pv], 0
0x18003c4ab  lea     rcx, [rbp+pv]
0x18003c4af  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18003c4b4  mov     rdx, rax; unsigned __int16 **
0x18003c4b7  mov     rcx, [rbp+arg_10]; struct IShellItem *
0x18003c4bb  call    ?GetStorageProviderNameForFolder@@YAJPEAUIShellItem@@PEAPEAG@Z; GetStorageProviderNameForFolder(IShellItem *,ushort * *)
0x18003c4c0  test    eax, eax
0x18003c4c2  js      short loc_18003C534
0x18003c4c4  mov     rax, [rbp+arg_18]
0x18003c4c8  mov     rcx, [rbp+pv]; pv
0x18003c4cc  mov     rdx, rcx
0x18003c4cf  sub     rdx, rax
0x18003c4d2  movzx   r9d, word ptr [rax]
0x18003c4d6  movzx   r8d, word ptr [rax+rdx]
0x18003c4db  sub     r9d, r8d
0x18003c4de  jnz     short loc_18003C4E9
0x18003c4e0  add     rax, 2
0x18003c4e4  test    r8d, r8d
0x18003c4e7  jnz     short loc_18003C4D2
0x18003c4e9  test    r9d, r9d
0x18003c4ec  setz    bl
0x18003c4ef  test    rcx, rcx
0x18003c4f2  jz      short loc_18003C4FB
0x18003c4f4  call    cs:__imp_CoTaskMemFree
0x18003c4fa  nop
0x18003c4fb  lea     rcx, [rbp+arg_10]
0x18003c4ff  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18003c504  inc     esi
0x18003c506  cmp     esi, edi
0x18003c508  jb      loc_18003C47A
0x18003c50e  mov     rcx, [rbp+arg_18]; pv
0x18003c512  test    rcx, rcx
0x18003c515  jz      short loc_18003C51E
0x18003c517  call    cs:__imp_CoTaskMemFree
0x18003c51d  nop
0x18003c51e  lea     rcx, [rbp+var_10]
0x18003c522  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18003c527  mov     al, bl
0x18003c529  add     rsp, 30h
0x18003c52d  pop     r14
0x18003c52f  pop     rdi
0x18003c530  pop     rsi
0x18003c531  pop     rbx
0x18003c532  pop     rbp
0x18003c533  retn
0x18003c534  mov     rcx, [rbp+pv]; pv
0x18003c538  test    rcx, rcx
0x18003c53b  jz      short loc_18003C544
0x18003c53d  call    cs:__imp_CoTaskMemFree
0x18003c543  nop
0x18003c544  lea     rcx, [rbp+arg_10]
0x18003c548  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18003c54d  nop
0x18003c54e  mov     rcx, [rbp+arg_18]; pv
0x18003c552  test    rcx, rcx
0x18003c555  jz      short loc_18003C55E
0x18003c557  call    cs:__imp_CoTaskMemFree
0x18003c55d  nop
0x18003c55e  lea     rcx, [rbp+var_10]
0x18003c562  call    ??1?$com_ptr_t@UISyncRootManager@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ISyncRootManager,wil::err_returncode_policy>::~com_ptr_t<ISyncRootManager,wil::err_returncode_policy>(void)
0x18003c567  xor     al, al
0x18003c569  jmp     short loc_18003C529
```
