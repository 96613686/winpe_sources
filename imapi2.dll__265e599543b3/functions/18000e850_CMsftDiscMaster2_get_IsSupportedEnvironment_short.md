# CMsftDiscMaster2::get_IsSupportedEnvironment(short *)

- ea: `0x18000e850`
- end: `0x18000e991`
- name: `?get_IsSupportedEnvironment@CMsftDiscMaster2@@UEAAJPEAF@Z`
- size: `321`
- prototype: `__int64 __fastcall(CMsftDiscMaster2 *__hidden this, __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002fc8`
- `0x18000e850`
- `0x18004a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000e8fd`
- `ole32!CoCreateInstance` at `0x18000e8fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e943`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e943`

## pseudocode

```c
__int64 __fastcall CMsftDiscMaster2::get_IsSupportedEnvironment(CMsftDiscMaster2 *this, __int16 *a2)
{
  HRESULT v5; // ebx
  const struct _GUID *v6; // r8
  char v7; // di
  int v8; // esi
  __int64 v9; // rax
  int v10; // [rsp+68h] [rbp+38h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+48h] BYREF

  v10 = 0;
  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  v5 = (*(__int64 (__fastcall **)(CMsftDiscMaster2 *, int *))(*(_QWORD *)this + 72LL))(this, &v10);
  if ( v5 >= 0 )
  {
    v7 = 0;
    v8 = 0;
    if ( v10 <= 0 )
      goto LABEL_15;
    do
    {
      if ( v7 )
        break;
      v9 = *(_QWORD *)this;
      bstrString = 0;
      v5 = (*(__int64 (__fastcall **)(CMsftDiscMaster2 *, _QWORD, BSTR *))(v9 + 64))(
             this,
             (unsigned int)v8,
             &bstrString);
      if ( v5 >= 0 )
      {
        ppv = 0;
        v5 = CoCreateInstance(&CLSID_MsftDiscRecorder2, 0, 0x17u, &GUID_27354133_7f64_5b0f_8f00_5d77afbe261e, &ppv);
        if ( v5 >= 0 )
        {
          v5 = (*(__int64 (__fastcall **)(LPVOID, BSTR))(*(_QWORD *)ppv + 104LL))(ppv, bstrString);
          if ( v5 < 0 )
            v5 = 0;
          else
            v7 = 1;
        }
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      SysFreeString(bstrString);
      ++v8;
    }
    while ( v8 < v10 );
    if ( v5 >= 0 )
LABEL_15:
      *a2 = -(v7 != 0);
  }
  if ( (v5 & 0x80FF0000) == 0x80AA0000 )
    Imapi2Utility::SetErrorDescription(v5, (__int64)&CLSID_MsftDiscMaster2, v6);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000e850  mov     [rsp-28h+arg_0], rbx
0x18000e855  push    rbp
0x18000e856  push    rsi
0x18000e857  push    rdi
0x18000e858  push    r14
0x18000e85a  push    r15
0x18000e85c  mov     rbp, rsp
0x18000e85f  sub     rsp, 30h
0x18000e863  mov     [rbp+arg_8], 0
0x18000e86a  mov     r14, rdx
0x18000e86d  mov     r15, rcx
0x18000e870  test    rdx, rdx
0x18000e873  jnz     short loc_18000E87F
0x18000e875  mov     eax, 80004003h
0x18000e87a  jmp     loc_18000E980
0x18000e87f  xor     eax, eax
0x18000e881  mov     [rdx], ax
0x18000e884  lea     rdx, [rbp+arg_8]
0x18000e888  mov     rax, [rcx]
0x18000e88b  mov     rax, [rax+48h]
0x18000e88f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e894  mov     ebx, eax
0x18000e896  test    eax, eax
0x18000e898  js      loc_18000E962
0x18000e89e  xor     dil, dil
0x18000e8a1  xor     esi, esi
0x18000e8a3  cmp     [rbp+arg_8], esi
0x18000e8a6  jle     loc_18000E958
0x18000e8ac  test    dil, dil
0x18000e8af  jnz     loc_18000E954
0x18000e8b5  mov     rax, [r15]
0x18000e8b8  lea     r8, [rbp+bstrString]
0x18000e8bc  mov     edx, esi
0x18000e8be  mov     [rbp+bstrString], 0
0x18000e8c6  mov     rcx, r15
0x18000e8c9  mov     rax, [rax+40h]
0x18000e8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8d2  mov     ebx, eax
0x18000e8d4  test    eax, eax
0x18000e8d6  js      short loc_18000E93F
0x18000e8d8  xor     edx, edx; pUnkOuter
0x18000e8da  mov     [rbp+arg_10], 0
0x18000e8e2  lea     rax, [rbp+arg_10]
0x18000e8e6  lea     r9, _GUID_27354133_7f64_5b0f_8f00_5d77afbe261e; riid
0x18000e8ed  mov     [rsp+30h+ppv], rax; ppv
0x18000e8f2  lea     rcx, CLSID_MsftDiscRecorder2; rclsid
0x18000e8f9  lea     r8d, [rdx+17h]; dwClsContext
0x18000e8fd  call    cs:__imp_CoCreateInstance
0x18000e903  mov     ebx, eax
0x18000e905  test    eax, eax
0x18000e907  js      short loc_18000E92A
0x18000e909  mov     rcx, [rbp+arg_10]
0x18000e90d  mov     rdx, [rbp+bstrString]
0x18000e911  mov     rax, [rcx]
0x18000e914  mov     rax, [rax+68h]
0x18000e918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e91d  mov     ebx, eax
0x18000e91f  test    eax, eax
0x18000e921  js      short loc_18000E928
0x18000e923  mov     dil, 1
0x18000e926  jmp     short loc_18000E92A
0x18000e928  xor     ebx, ebx
0x18000e92a  mov     rcx, [rbp+arg_10]
0x18000e92e  test    rcx, rcx
0x18000e931  jz      short loc_18000E93F
0x18000e933  mov     rax, [rcx]
0x18000e936  mov     rax, [rax+10h]
0x18000e93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e93f  mov     rcx, [rbp+bstrString]; bstrString
0x18000e943  call    cs:__imp_SysFreeString
0x18000e949  inc     esi
0x18000e94b  cmp     esi, [rbp+arg_8]
0x18000e94e  jl      loc_18000E8AC
0x18000e954  test    ebx, ebx
0x18000e956  js      short loc_18000E962
0x18000e958  neg     dil
0x18000e95b  sbb     ax, ax
0x18000e95e  mov     [r14], ax
0x18000e962  mov     eax, ebx
0x18000e964  and     eax, 80FF0000h
0x18000e969  cmp     eax, 80AA0000h
0x18000e96e  jnz     short loc_18000E97E
0x18000e970  lea     rdx, CLSID_MsftDiscMaster2; int
0x18000e977  mov     ecx, ebx; dwMessageId
0x18000e979  call    ?SetErrorDescription@Imapi2Utility@@YAXJAEBU_GUID@@@Z; Imapi2Utility::SetErrorDescription(long,_GUID const &)
0x18000e97e  mov     eax, ebx
0x18000e980  mov     rbx, [rsp+30h+arg_0]
0x18000e985  add     rsp, 30h
0x18000e989  pop     r15
0x18000e98b  pop     r14
0x18000e98d  pop     rdi
0x18000e98e  pop     rsi
0x18000e98f  pop     rbp
0x18000e990  retn
```
