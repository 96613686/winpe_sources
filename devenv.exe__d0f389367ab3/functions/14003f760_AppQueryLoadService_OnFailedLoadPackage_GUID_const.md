# AppQueryLoadService::OnFailedLoadPackage(_GUID const &)

- ea: `0x14003f760`
- end: `0x14003f8e4`
- name: `?OnFailedLoadPackage@AppQueryLoadService@@UEAAJAEBU_GUID@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(AppQueryLoadService *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x140001020`
- `0x14003f760`
- `0x14003f9c8`
- `0x14003fba4`
- `0x14003fc7c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14003f787`
- `KERNEL32!GetCurrentThreadId` at `0x14003f787`
- `OLEAUT32!__imp_SysFreeString` at `0x14003f8ba`
- `OLEAUT32!__imp_SysFreeString` at `0x14003f8ba`
- `OLEAUT32!__imp_SysStringLen` at `0x14003f7d4`
- `OLEAUT32!__imp_SysStringLen` at `0x14003f7d4`

## pseudocode

```c
__int64 __fastcall AppQueryLoadService::OnFailedLoadPackage(AppQueryLoadService *this, const struct _GUID *a2)
{
  __int64 v5; // rdx
  unsigned int v6; // edx
  OLECHAR *v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rdx
  BSTR pbstr; // [rsp+60h] [rbp-28h] BYREF
  int v11; // [rsp+68h] [rbp-20h] BYREF

  if ( GetCurrentThreadId() != *((_DWORD *)this + 70) )
    return 2147549454LL;
  v5 = *((_QWORD *)this + 9);
  if ( !*(_QWORD *)v5 )
    return 2147549183LL;
  v6 = *(_DWORD *)(v5 + 12);
  pbstr = 0;
  AppQueryLoadService::FormatPackageString_WithActivityLogPath(this, v6, a2, &pbstr);
  v7 = pbstr;
  if ( SysStringLen(pbstr) )
  {
    pbstr = 0;
    v8 = *(_QWORD *)(*((_QWORD *)this + 9) + 128LL);
    if ( v8 )
    {
      if ( (*(int (__fastcall **)(__int64, GUID *, GUID *, BSTR *))(*(_QWORD *)v8 + 24LL))(
             v8,
             &IID_IVsUIShell,
             &GUID_b61fc35b_eebf_4dec_bff1_28a2dd43c38f,
             &pbstr) < 0 )
      {
LABEL_11:
        if ( pbstr )
          (*(void (__fastcall **)(BSTR))(*(_QWORD *)pbstr + 16LL))(pbstr);
        goto LABEL_13;
      }
      if ( pbstr )
      {
        v11 = 0;
        (*(void (__fastcall **)(BSTR, _QWORD, GUID *, _QWORD, OLECHAR *, _QWORD, int, int, _DWORD, int, _DWORD, int *))(*(_QWORD *)pbstr + 176LL))(
          pbstr,
          0,
          &GUID_NULL,
          0,
          v7,
          0,
          -1,
          4,
          0,
          3,
          0,
          &v11);
        if ( v11 == 7 )
          AppQueryLoadService::WriteSkipLoading((__int64)this, a2, 1);
        goto LABEL_11;
      }
    }
  }
LABEL_13:
  v9 = *((_QWORD *)this + 9);
  if ( !*(_BYTE *)(v9 + 122) )
  {
    if ( *(_BYTE *)(v9 + 121) )
      AppQueryLoadService::OutputFormattedPackageString_WithPackageGuid(this, *(_DWORD *)(v9 + 16), a2);
  }
  SysFreeString(v7);
  return 0;
}

```

## disassembly

```asm
0x14003f760  mov     [rsp+arg_10], rbx
0x14003f765  mov     [rsp+arg_18], rsi
0x14003f76a  push    rdi
0x14003f76b  sub     rsp, 80h
0x14003f772  mov     rax, cs:__security_cookie
0x14003f779  xor     rax, rsp
0x14003f77c  mov     [rsp+88h+var_18], rax
0x14003f781  mov     rsi, rdx
0x14003f784  mov     rdi, rcx
0x14003f787  call    cs:__imp_GetCurrentThreadId
0x14003f78d  cmp     eax, [rdi+118h]
0x14003f793  jz      short loc_14003F79F
0x14003f795  mov     eax, 8001010Eh
0x14003f79a  jmp     loc_14003F8C2
0x14003f79f  mov     rdx, [rdi+48h]
0x14003f7a3  cmp     qword ptr [rdx], 0
0x14003f7a7  jnz     short loc_14003F7B3
0x14003f7a9  mov     eax, 8000FFFFh
0x14003f7ae  jmp     loc_14003F8C2
0x14003f7b3  mov     edx, [rdx+0Ch]; unsigned int
0x14003f7b6  lea     r9, [rsp+88h+pbstr]; unsigned __int16 **
0x14003f7bb  and     [rsp+88h+pbstr], 0
0x14003f7c1  mov     r8, rsi; struct _GUID *
0x14003f7c4  mov     rcx, rdi; this
0x14003f7c7  call    ?FormatPackageString_WithActivityLogPath@AppQueryLoadService@@IEAAHKAEBU_GUID@@PEAPEAG@Z; AppQueryLoadService::FormatPackageString_WithActivityLogPath(ulong,_GUID const &,ushort * *)
0x14003f7cc  mov     rbx, [rsp+88h+pbstr]
0x14003f7d1  mov     rcx, rbx; pbstr
0x14003f7d4  call    cs:__imp_SysStringLen
0x14003f7da  test    eax, eax
0x14003f7dc  jz      loc_14003F899
0x14003f7e2  and     [rsp+88h+pbstr], 0
0x14003f7e8  mov     rax, [rdi+48h]
0x14003f7ec  mov     rcx, [rax+80h]
0x14003f7f3  test    rcx, rcx
0x14003f7f6  jz      loc_14003F899
0x14003f7fc  mov     rax, [rcx]
0x14003f7ff  lea     r9, [rsp+88h+pbstr]
0x14003f804  lea     r8, _GUID_b61fc35b_eebf_4dec_bff1_28a2dd43c38f
0x14003f80b  lea     rdx, IID_IVsUIShell
0x14003f812  call    qword ptr [rax+18h]
0x14003f815  test    eax, eax
0x14003f817  js      short loc_14003F889
0x14003f819  mov     rcx, [rsp+88h+pbstr]
0x14003f81e  test    rcx, rcx
0x14003f821  jz      short loc_14003F899
0x14003f823  and     [rsp+88h+var_20], 0
0x14003f828  lea     rdx, [rsp+88h+var_20]
0x14003f82d  mov     rax, [rcx]
0x14003f830  lea     r8, GUID_NULL
0x14003f837  mov     [rsp+88h+var_30], rdx
0x14003f83c  xor     r9d, r9d
0x14003f83f  and     [rsp+88h+var_38], 0
0x14003f844  xor     edx, edx
0x14003f846  mov     [rsp+88h+var_40], 3
0x14003f84e  and     [rsp+88h+var_48], 0
0x14003f853  mov     [rsp+88h+var_50], 4
0x14003f85b  or      [rsp+88h+var_58], 0FFFFFFFFh
0x14003f860  and     [rsp+88h+var_60], 0
0x14003f866  mov     [rsp+88h+var_68], rbx
0x14003f86b  call    qword ptr [rax+0B0h]
0x14003f871  cmp     [rsp+88h+var_20], 7
0x14003f876  jnz     short loc_14003F889
0x14003f878  mov     r8d, 1
0x14003f87e  mov     rdx, rsi
0x14003f881  mov     rcx, rdi
0x14003f884  call    ?WriteSkipLoading@AppQueryLoadService@@AEAAJAEBU_GUID@@W4SkipLoadPackageType@@@Z; AppQueryLoadService::WriteSkipLoading(_GUID const &,SkipLoadPackageType)
0x14003f889  mov     rcx, [rsp+88h+pbstr]
0x14003f88e  test    rcx, rcx
0x14003f891  jz      short loc_14003F899
0x14003f893  mov     rax, [rcx]
0x14003f896  call    qword ptr [rax+10h]
0x14003f899  mov     rdx, [rdi+48h]
0x14003f89d  cmp     byte ptr [rdx+7Ah], 0
0x14003f8a1  jnz     short loc_14003F8B7
0x14003f8a3  cmp     byte ptr [rdx+79h], 0
0x14003f8a7  jz      short loc_14003F8B7
0x14003f8a9  mov     edx, [rdx+10h]; unsigned int
0x14003f8ac  mov     r8, rsi; struct _GUID *
0x14003f8af  mov     rcx, rdi; this
0x14003f8b2  call    ?OutputFormattedPackageString_WithPackageGuid@AppQueryLoadService@@IEAAXKAEBU_GUID@@@Z; AppQueryLoadService::OutputFormattedPackageString_WithPackageGuid(ulong,_GUID const &)
0x14003f8b7  mov     rcx, rbx; bstrString
0x14003f8ba  call    cs:__imp_SysFreeString
0x14003f8c0  xor     eax, eax
0x14003f8c2  mov     rcx, [rsp+88h+var_18]
0x14003f8c7  xor     rcx, rsp; StackCookie
0x14003f8ca  call    __security_check_cookie
0x14003f8cf  lea     r11, [rsp+88h+var_8]
0x14003f8d7  mov     rbx, [r11+20h]
0x14003f8db  mov     rsi, [r11+28h]
0x14003f8df  mov     rsp, r11
0x14003f8e2  pop     rdi
0x14003f8e3  retn
```
