# CExtensionsEnumRegKeyBase<IEnumString,&_GUID const IID_IEnumString,ushort *>::_Next(ushort * *)

- ea: `0x180068f40`
- end: `0x180069072`
- name: `?_Next@?$CExtensionsEnumRegKeyBase@UIEnumString@@$1?IID_IEnumString@@3U_GUID@@BPEAG@@EEAAJPEAPEAG@Z`
- size: `306`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180031670`
- `0x18003fb80`
- `0x180068f40`
- `0x180083c10`
- `0x180083cd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180068fc0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180068fc0`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180068fb8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180068fb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180069014`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180069014`

## pseudocode

```c
__int64 __fastcall CExtensionsEnumRegKeyBase<IEnumString,&_GUID const IID_IEnumString,unsigned short *>::_Next(
        __int64 a1,
        _QWORD *a2)
{
  unsigned int v4; // ebx
  DWORD v5; // edx
  HKEY v6; // rcx
  LSTATUS v7; // eax
  unsigned __int64 v8; // rsi
  unsigned __int16 *v9; // rax
  __int64 v10; // r11
  DWORD cchValueName[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR ValueName[2048]; // [rsp+50h] [rbp-B0h] BYREF

  v4 = 1;
  do
  {
    v5 = *(_DWORD *)(a1 + 28);
    v6 = *(HKEY *)(a1 + 16);
    cchValueName[0] = 2048;
    ValueName[0] = 0;
    if ( *(_DWORD *)(a1 + 24) )
      v7 = RegEnumKeyExW(v6, v5, ValueName, cchValueName, 0, 0, 0, 0);
    else
      v7 = RegEnumValueW(v6, v5, ValueName, cchValueName, 0, 0, 0, 0);
    if ( v7 == 259 )
      break;
    if ( (*(unsigned __int8 (__fastcall **)(__int64, WCHAR *))(*(_QWORD *)a1 + 72LL))(a1, ValueName) )
    {
      *(_QWORD *)cchValueName = 0;
      v4 = StringCchLengthW(ValueName, 0x800u, (unsigned __int64 *)cchValueName);
      if ( !v4 )
      {
        v8 = *(_QWORD *)cchValueName + 1LL;
        v9 = (unsigned __int16 *)CoTaskMemAlloc(2 * (*(_QWORD *)cchValueName + 1LL));
        if ( v9 )
        {
          v4 = StringCchCopyW(v9, v8, ValueName);
          *a2 = v10;
        }
      }
    }
    else
    {
      v4 = -2147467259;
    }
    ++*(_DWORD *)(a1 + 28);
  }
  while ( v4 );
  return v4;
}

```

## disassembly

```asm
0x180068f40  mov     [rsp-8+arg_10], rbx
0x180068f45  mov     [rsp-8+arg_18], rsi
0x180068f4a  push    rbp
0x180068f4b  push    rdi
0x180068f4c  push    r14
0x180068f4e  lea     rbp, [rsp-0F60h]
0x180068f56  mov     eax, 1060h
0x180068f5b  call    _alloca_probe
0x180068f60  sub     rsp, rax
0x180068f63  mov     rax, cs:__security_cookie
0x180068f6a  xor     rax, rsp
0x180068f6d  mov     [rbp+0F70h+var_20], rax
0x180068f74  mov     r14, rdx
0x180068f77  mov     rdi, rcx
0x180068f7a  mov     ebx, 1
0x180068f7f  mov     edx, [rdi+1Ch]; dwIndex
0x180068f82  lea     r9, [rsp+1070h+cchValueName]; lpcchName
0x180068f87  mov     rcx, [rdi+10h]; hKey
0x180068f8b  lea     r8, [rsp+1070h+ValueName]; lpName
0x180068f90  xor     eax, eax
0x180068f92  mov     [rsp+1070h+cchValueName], 800h
0x180068f9a  mov     [rsp+1070h+lpcbData], rax; lpftLastWriteTime
0x180068f9f  mov     [rsp+1070h+lpData], rax; lpcchClass
0x180068fa4  mov     [rsp+1070h+lpType], rax; lpClass
0x180068fa9  mov     [rsp+1070h+lpReserved], rax; lpReserved
0x180068fae  mov     [rsp+1070h+ValueName], ax
0x180068fb3  cmp     [rdi+18h], eax
0x180068fb6  jnz     short loc_180068FC0
0x180068fb8  call    cs:__imp_RegEnumValueW
0x180068fbe  jmp     short loc_180068FC6
0x180068fc0  call    cs:__imp_RegEnumKeyExW
0x180068fc6  cmp     eax, 103h
0x180068fcb  jz      short loc_180069049
0x180068fcd  mov     rax, [rdi]
0x180068fd0  lea     rdx, [rsp+1070h+ValueName]
0x180068fd5  mov     rcx, rdi
0x180068fd8  mov     rax, [rax+48h]
0x180068fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068fe1  test    al, al
0x180068fe3  jz      short loc_180069039
0x180068fe5  lea     r8, [rsp+1070h+cchValueName]; unsigned __int64 *
0x180068fea  mov     qword ptr [rsp+1070h+cchValueName], 0
0x180068ff3  mov     edx, 800h; unsigned __int64
0x180068ff8  lea     rcx, [rsp+1070h+ValueName]; unsigned __int16 *
0x180068ffd  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180069002  mov     ebx, eax
0x180069004  test    eax, eax
0x180069006  jnz     short loc_18006903E
0x180069008  mov     rsi, qword ptr [rsp+1070h+cchValueName]
0x18006900d  inc     rsi
0x180069010  lea     rcx, [rsi+rsi]; cb
0x180069014  call    cs:__imp_CoTaskMemAlloc
0x18006901a  mov     r11, rax
0x18006901d  test    rax, rax
0x180069020  jz      short loc_18006903E
0x180069022  lea     r8, [rsp+1070h+ValueName]; unsigned __int16 *
0x180069027  mov     rdx, rsi; unsigned __int64
0x18006902a  mov     rcx, rax; unsigned __int16 *
0x18006902d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180069032  mov     ebx, eax
0x180069034  mov     [r14], r11
0x180069037  jmp     short loc_18006903E
0x180069039  mov     ebx, 80004005h
0x18006903e  inc     dword ptr [rdi+1Ch]
0x180069041  test    ebx, ebx
0x180069043  jnz     loc_180068F7F
0x180069049  mov     eax, ebx
0x18006904b  mov     rcx, [rbp+0F70h+var_20]
0x180069052  xor     rcx, rsp; StackCookie
0x180069055  call    __security_check_cookie
0x18006905a  lea     r11, [rsp+1070h+var_10]
0x180069062  mov     rbx, [r11+30h]
0x180069066  mov     rsi, [r11+38h]
0x18006906a  mov     rsp, r11
0x18006906d  pop     r14
0x18006906f  pop     rdi
0x180069070  pop     rbp
0x180069071  retn
```
