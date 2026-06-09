# Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::CreateAndInitSAXWriter(IMXWriter * *)

- ea: `0x14004dea4`
- end: `0x14004df8f`
- name: `?CreateAndInitSAXWriter@CMergeConfigFile@BindingRedirects@PkgDef@VisualStudio@Microsoft@@AEBAJPEAPEAUIMXWriter@@@Z`
- size: `235`
- prototype: `int(Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile *__hidden this, struct IMXWriter **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400222b0`

## callees

- `0x140001020`
- `0x140033ab0`
- `0x14004dea4`

## import_xrefs

- `ole32!CoCreateInstance` at `0x14004deed`
- `ole32!CoCreateInstance` at `0x14004deed`
- `OLEAUT32!__imp_SysAllocString` at `0x14004df18`
- `OLEAUT32!__imp_SysAllocString` at `0x14004df18`
- `OLEAUT32!__imp_SysFreeString` at `0x14004df51`
- `OLEAUT32!__imp_SysFreeString` at `0x14004df51`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile::CreateAndInitSAXWriter(
        Microsoft::VisualStudio::PkgDef::BindingRedirects::CMergeConfigFile *this,
        LPVOID *ppv)
{
  HRESULT result; // eax
  LPVOID v4; // rbx
  OLECHAR *v5; // rdi
  int v6; // esi

  if ( !ppv )
    return -2147467261;
  result = CoCreateInstance(
             &GUID_88d96a0f_f192_11d4_a65f_0040963251e5,
             0,
             1u,
             &GUID_4d7ff4ba_1565_4ea8_94e1_6e724a46f98d,
             ppv);
  _mm_lfence();
  if ( result >= 0 )
  {
    v4 = *ppv;
    if ( v4 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 8LL))(v4);
    v5 = SysAllocString(L"UTF-8");
    if ( !v5 )
      ATL::AtlThrowImpl(-2147024882);
    v6 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v4 + 104LL))(v4, 0xFFFFFFFFLL);
    if ( v6 >= 0 )
    {
      _mm_lfence();
      v6 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v4 + 72LL))(v4, v5);
    }
    SysFreeString(v5);
    if ( v4 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x14004dea4  mov     [rsp+arg_0], rbx
0x14004dea9  mov     [rsp+arg_10], rsi
0x14004deae  push    rdi
0x14004deaf  sub     rsp, 50h
0x14004deb3  mov     rax, cs:__security_cookie
0x14004deba  xor     rax, rsp
0x14004debd  mov     [rsp+58h+var_18], rax
0x14004dec2  mov     rbx, rdx
0x14004dec5  test    rdx, rdx
0x14004dec8  jnz     short loc_14004DED4
0x14004deca  mov     eax, 80004003h
0x14004decf  jmp     loc_14004DF67
0x14004ded4  mov     [rsp+58h+ppv], rbx; ppv
0x14004ded9  lea     r9, _GUID_4d7ff4ba_1565_4ea8_94e1_6e724a46f98d; riid
0x14004dee0  xor     edx, edx; pUnkOuter
0x14004dee2  lea     r8d, [rdx+1]; dwClsContext
0x14004dee6  lea     rcx, _GUID_88d96a0f_f192_11d4_a65f_0040963251e5; rclsid
0x14004deed  call    cs:__imp_CoCreateInstance
0x14004def3  lfence
0x14004def6  test    eax, eax
0x14004def8  js      short loc_14004DF67
0x14004defa  mov     rbx, [rbx]
0x14004defd  mov     [rsp+58h+var_20], rbx
0x14004df02  test    rbx, rbx
0x14004df05  jz      short loc_14004DF11
0x14004df07  mov     rax, [rbx]
0x14004df0a  mov     rcx, rbx
0x14004df0d  call    qword ptr [rax+8]
0x14004df10  nop
0x14004df11  lea     rcx, aUtf8; "UTF-8"
0x14004df18  call    cs:__imp_SysAllocString
0x14004df1e  mov     rdi, rax
0x14004df21  mov     [rsp+58h+var_28], rax
0x14004df26  test    rax, rax
0x14004df29  jz      short loc_14004DF84
0x14004df2b  mov     rax, [rbx]
0x14004df2e  or      edx, 0FFFFFFFFh
0x14004df31  mov     rcx, rbx
0x14004df34  call    qword ptr [rax+68h]
0x14004df37  mov     esi, eax
0x14004df39  test    eax, eax
0x14004df3b  js      short loc_14004DF4E
0x14004df3d  lfence
0x14004df40  mov     rax, [rbx]
0x14004df43  mov     rdx, rdi
0x14004df46  mov     rcx, rbx
0x14004df49  call    qword ptr [rax+48h]
0x14004df4c  mov     esi, eax
0x14004df4e  mov     rcx, rdi; bstrString
0x14004df51  call    cs:__imp_SysFreeString
0x14004df57  test    rbx, rbx
0x14004df5a  jz      short loc_14004DF65
0x14004df5c  mov     rax, [rbx]
0x14004df5f  mov     rcx, rbx
0x14004df62  call    qword ptr [rax+10h]
0x14004df65  mov     eax, esi
0x14004df67  mov     rcx, [rsp+58h+var_18]
0x14004df6c  xor     rcx, rsp; StackCookie
0x14004df6f  call    __security_check_cookie
0x14004df74  mov     rbx, [rsp+58h+arg_0]
0x14004df79  mov     rsi, [rsp+58h+arg_10]
0x14004df7e  add     rsp, 50h
0x14004df82  pop     rdi
0x14004df83  retn
0x14004df84  mov     ecx, 8007000Eh; int
0x14004df89  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
