# PackageCollection::Verify(IPackage *)

- ea: `0x140055a60`
- end: `0x140055c71`
- name: `?Verify@PackageCollection@@UEAAJPEAVIPackage@@@Z`
- size: `529`
- prototype: `__int64 __fastcall(PackageCollection *this, struct IPackage *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x140020420`
- `0x140055a60`
- `0x140059278`
- `0x140063010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140055b35`
- `KERNEL32!GetLastError` at `0x140055b77`
- `KERNEL32!GetLastError` at `0x140055b35`
- `KERNEL32!GetLastError` at `0x140055b77`
- `KERNEL32!SetDllDirectoryW` at `0x140055b25`
- `KERNEL32!SetDllDirectoryW` at `0x140055b67`
- `KERNEL32!SetDllDirectoryW` at `0x140055b25`
- `KERNEL32!SetDllDirectoryW` at `0x140055b67`
- `OLEAUT32!__imp_SysFreeString` at `0x140055c1b`
- `OLEAUT32!__imp_SysFreeString` at `0x140055c38`
- `OLEAUT32!__imp_SysFreeString` at `0x140055c1b`
- `OLEAUT32!__imp_SysFreeString` at `0x140055c38`

## pseudocode

```c
__int64 __fastcall PackageCollection::Verify(PackageCollection *this, struct IPackage *a2)
{
  signed int v4; // ebx
  int updated; // eax
  int v6; // r9d
  signed int LastError; // eax
  signed int v8; // eax
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  int v11; // [rsp+68h] [rbp+28h] BYREF
  LPCWSTR lpPathName; // [rsp+70h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+38h] BYREF

  lpPathName = 0;
  bstrString = 0;
  v10 = 0;
  v11 = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::Verify", 731, -2147024809);
    goto LABEL_27;
  }
  updated = (*(__int64 (__fastcall **)(struct IPackage *, int *))(*(_QWORD *)a2 + 48LL))(a2, &v11);
  v4 = updated;
  if ( updated >= 0 )
  {
    if ( !v11 )
      goto LABEL_27;
    updated = (*(__int64 (__fastcall **)(struct IPackage *, __int64 *))(*(_QWORD *)a2 + 96LL))(a2, &v10);
    v4 = updated;
    if ( updated >= 0 )
    {
      updated = (*(__int64 (__fastcall **)(struct IPackage *, LPCWSTR *))(*(_QWORD *)a2 + 80LL))(a2, &lpPathName);
      v4 = updated;
      if ( updated >= 0 )
      {
        if ( !SetDllDirectoryW(0) )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          if ( v4 < 0 )
          {
            SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::Verify", 747, v4);
            goto LABEL_27;
          }
        }
        if ( !SetDllDirectoryW(lpPathName) )
        {
          v8 = GetLastError();
          v4 = v8;
          if ( v8 > 0 )
            v4 = (unsigned __int16)v8 | 0x80070000;
          if ( v4 < 0 )
          {
            SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::Verify", 750, v4);
            goto LABEL_27;
          }
        }
        if ( *((_DWORD *)this + 16) )
        {
          v4 = -2147467260;
          SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::Verify", 754, -2147467260);
          goto LABEL_27;
        }
        updated = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v10 + 160LL))(v10, &bstrString);
        v4 = updated;
        if ( updated >= 0 )
        {
          updated = Package::UpdateRootCausesWithVerifyXml(a2, bstrString);
          v4 = updated;
          if ( updated >= 0 )
            goto LABEL_27;
          v6 = 761;
        }
        else
        {
          v6 = 758;
        }
      }
      else
      {
        v6 = 744;
      }
    }
    else
    {
      v6 = 741;
    }
  }
  else
  {
    v6 = 737;
  }
  SdpDebugPrint(1u, "Met ERROR: %s:%d - hr = 0x%08X\n", "PackageCollection::Verify", v6, updated);
LABEL_27:
  if ( lpPathName )
  {
    SysFreeString((BSTR)lpPathName);
    lpPathName = 0;
  }
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140055a60  mov     [rsp-18h+arg_0], rbx
0x140055a65  push    rbp
0x140055a66  push    rsi
0x140055a67  push    rdi
0x140055a68  mov     rbp, rsp
0x140055a6b  sub     rsp, 40h
0x140055a6f  mov     [rbp+lpPathName], 0
0x140055a77  mov     rdi, rdx
0x140055a7a  mov     [rbp+bstrString], 0
0x140055a82  mov     rsi, rcx
0x140055a85  mov     [rbp+var_10], 0
0x140055a8d  mov     [rbp+arg_8], 0
0x140055a94  test    rdx, rdx
0x140055a97  jnz     short loc_140055AAD
0x140055a99  mov     ebx, 80070057h
0x140055a9e  mov     r9d, 2DBh
0x140055aa4  mov     [rsp+40h+var_20], ebx
0x140055aa8  jmp     loc_140055BFA
0x140055aad  mov     rax, [rdx]
0x140055ab0  mov     rcx, rdi
0x140055ab3  lea     rdx, [rbp+arg_8]
0x140055ab7  mov     rax, [rax+30h]
0x140055abb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055ac0  mov     ebx, eax
0x140055ac2  test    eax, eax
0x140055ac4  jns     short loc_140055AD1
0x140055ac6  mov     r9d, 2E1h
0x140055acc  jmp     loc_140055BF6
0x140055ad1  cmp     [rbp+arg_8], 0
0x140055ad5  jbe     loc_140055C12
0x140055adb  mov     rax, [rdi]
0x140055ade  lea     rdx, [rbp+var_10]
0x140055ae2  mov     rcx, rdi
0x140055ae5  mov     rax, [rax+60h]
0x140055ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055aee  mov     ebx, eax
0x140055af0  test    eax, eax
0x140055af2  jns     short loc_140055AFF
0x140055af4  mov     r9d, 2E5h
0x140055afa  jmp     loc_140055BF6
0x140055aff  mov     rax, [rdi]
0x140055b02  lea     rdx, [rbp+lpPathName]
0x140055b06  mov     rcx, rdi
0x140055b09  mov     rax, [rax+50h]
0x140055b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055b12  mov     ebx, eax
0x140055b14  test    eax, eax
0x140055b16  jns     short loc_140055B23
0x140055b18  mov     r9d, 2E8h
0x140055b1e  jmp     loc_140055BF6
0x140055b23  xor     ecx, ecx; lpPathName
0x140055b25  call    cs:__imp_SetDllDirectoryW
0x140055b2c  nop     dword ptr [rax+rax+00h]
0x140055b31  test    eax, eax
0x140055b33  jnz     short loc_140055B63
0x140055b35  call    cs:__imp_GetLastError
0x140055b3c  nop     dword ptr [rax+rax+00h]
0x140055b41  mov     ebx, eax
0x140055b43  test    eax, eax
0x140055b45  jle     short loc_140055B50
0x140055b47  movzx   ebx, ax
0x140055b4a  or      ebx, 80070000h
0x140055b50  test    ebx, ebx
0x140055b52  jns     short loc_140055B63
0x140055b54  mov     [rsp+40h+var_20], ebx
0x140055b58  mov     r9d, 2EBh
0x140055b5e  jmp     loc_140055BFA
0x140055b63  mov     rcx, [rbp+lpPathName]; lpPathName
0x140055b67  call    cs:__imp_SetDllDirectoryW
0x140055b6e  nop     dword ptr [rax+rax+00h]
0x140055b73  test    eax, eax
0x140055b75  jnz     short loc_140055BA2
0x140055b77  call    cs:__imp_GetLastError
0x140055b7e  nop     dword ptr [rax+rax+00h]
0x140055b83  mov     ebx, eax
0x140055b85  test    eax, eax
0x140055b87  jle     short loc_140055B92
0x140055b89  movzx   ebx, ax
0x140055b8c  or      ebx, 80070000h
0x140055b92  test    ebx, ebx
0x140055b94  jns     short loc_140055BA2
0x140055b96  mov     [rsp+40h+var_20], ebx
0x140055b9a  mov     r9d, 2EEh
0x140055ba0  jmp     short loc_140055BFA
0x140055ba2  cmp     dword ptr [rsi+40h], 0
0x140055ba6  jz      short loc_140055BB9
0x140055ba8  mov     ebx, 80004004h
0x140055bad  mov     r9d, 2F2h
0x140055bb3  mov     [rsp+40h+var_20], ebx
0x140055bb7  jmp     short loc_140055BFA
0x140055bb9  mov     rcx, [rbp+var_10]
0x140055bbd  lea     rdx, [rbp+bstrString]
0x140055bc1  mov     rax, [rcx]
0x140055bc4  mov     rax, [rax+0A0h]
0x140055bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055bd0  mov     ebx, eax
0x140055bd2  test    eax, eax
0x140055bd4  jns     short loc_140055BDE
0x140055bd6  mov     r9d, 2F6h
0x140055bdc  jmp     short loc_140055BF6
0x140055bde  mov     rdx, [rbp+bstrString]; unsigned __int16 *
0x140055be2  mov     rcx, rdi; this
0x140055be5  call    ?UpdateRootCausesWithVerifyXml@Package@@QEAAJPEAG@Z; Package::UpdateRootCausesWithVerifyXml(ushort *)
0x140055bea  mov     ebx, eax
0x140055bec  test    eax, eax
0x140055bee  jns     short loc_140055C12
0x140055bf0  mov     r9d, 2F9h
0x140055bf6  mov     [rsp+40h+var_20], eax
0x140055bfa  lea     r8, aPackagecollect_5; "PackageCollection::Verify"
0x140055c01  mov     ecx, 1; Level
0x140055c06  lea     rdx, aMetErrorSDHr0x; "Met ERROR: %s:%d - hr = 0x%08X\n"
0x140055c0d  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140055c12  mov     rcx, [rbp+lpPathName]; bstrString
0x140055c16  test    rcx, rcx
0x140055c19  jz      short loc_140055C2F
0x140055c1b  call    cs:__imp_SysFreeString
0x140055c22  nop     dword ptr [rax+rax+00h]
0x140055c27  mov     [rbp+lpPathName], 0
0x140055c2f  mov     rcx, [rbp+bstrString]; bstrString
0x140055c33  test    rcx, rcx
0x140055c36  jz      short loc_140055C4C
0x140055c38  call    cs:__imp_SysFreeString
0x140055c3f  nop     dword ptr [rax+rax+00h]
0x140055c44  mov     [rbp+bstrString], 0
0x140055c4c  mov     rcx, [rbp+var_10]
0x140055c50  test    rcx, rcx
0x140055c53  jz      short loc_140055C61
0x140055c55  mov     rax, [rcx]
0x140055c58  mov     rax, [rax+10h]
0x140055c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140055c61  mov     eax, ebx
0x140055c63  mov     rbx, [rsp+40h+arg_0]
0x140055c68  add     rsp, 40h
0x140055c6c  pop     rdi
0x140055c6d  pop     rsi
0x140055c6e  pop     rbp
0x140055c6f  retn
```
