# NgcUtils::GetWindowsAikAlternateLocation(ushort * *)

- ea: `0x180014380`
- end: `0x180014472`
- name: `?GetWindowsAikAlternateLocation@NgcUtils@@YAJPEAPEAG@Z`
- size: `242`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014588`

## callees

- `0x180004de0`
- `0x18000b0fc`
- `0x18000db5c`
- `0x180010730`
- `0x180014380`
- `0x180015030`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800143b2`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800143b2`

## string_xrefs

- `0x1800143c6`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18001441c`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::GetWindowsAikAlternateLocation(unsigned __int16 ***this, unsigned __int16 **a2)
{
  int BasicProfileFolderPath; // eax
  unsigned int v4; // ebx
  int v5; // eax
  unsigned __int16 **v7[2]; // [rsp+20h] [rbp-238h] BYREF
  _BYTE v8[528]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  BasicProfileFolderPath = GetBasicProfileFolderPath(4, 0, v8, 260);
  v4 = BasicProfileFolderPath;
  if ( BasicProfileFolderPath >= 0 )
  {
    v7[0] = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      v7,
      0);
    v5 = NgcUtils::CombineSeparateStrings(
           (NgcUtils *)v8,
           &qword_18002A2C0,
           L"\\Microsoft\\Crypto\\PCPKSP\\WindowsAIK",
           (unsigned __int16 *)v7);
    v4 = v5;
    if ( v5 >= 0 )
    {
      v4 = 0;
      *this = v7[0];
      v7[0] = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
        (const char *)(unsigned int)v5,
        (int)v7[0]);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v7);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\cryptutils.cpp",
      (const char *)(unsigned int)BasicProfileFolderPath,
      (int)v7[0]);
  }
  return v4;
}

```

## disassembly

```asm
0x180014380  mov     [rsp+arg_8], rbx
0x180014385  push    rdi
0x180014386  sub     rsp, 250h
0x18001438d  mov     rax, cs:__security_cookie
0x180014394  xor     rax, rsp
0x180014397  mov     [rsp+258h+var_18], rax
0x18001439f  xor     edx, edx
0x1800143a1  lea     r8, [rsp+258h+var_228]
0x1800143a6  mov     rdi, rcx
0x1800143a9  mov     r9d, 104h
0x1800143af  lea     ecx, [rdx+4]
0x1800143b2  call    cs:__imp_GetBasicProfileFolderPath
0x1800143b8  mov     ebx, eax
0x1800143ba  test    eax, eax
0x1800143bc  jns     short loc_1800143DC
0x1800143be  mov     rcx, [rsp+258h]; this
0x1800143c6  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800143cd  mov     r9d, eax; char *
0x1800143d0  mov     edx, 16h; void *
0x1800143d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800143da  jmp     short loc_18001444F
0x1800143dc  xor     edx, edx
0x1800143de  mov     [rsp+258h+var_238], 0; int
0x1800143e7  lea     rcx, [rsp+258h+var_238]
0x1800143ec  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800143f1  lea     r9, [rsp+258h+var_238]; unsigned __int16 *
0x1800143f6  lea     r8, aMicrosoftCrypt; "\\Microsoft\\Crypto\\PCPKSP\\WindowsAIK"
0x1800143fd  lea     rdx, qword_18002A2C0; unsigned __int16 *
0x180014404  lea     rcx, [rsp+258h+var_228]; this
0x180014409  call    ?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001440e  mov     ebx, eax
0x180014410  test    eax, eax
0x180014412  jns     short loc_180014432
0x180014414  mov     rcx, [rsp+258h]; this
0x18001441c  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180014423  mov     r9d, eax; char *
0x180014426  mov     edx, 1Dh; void *
0x18001442b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014430  jmp     short loc_180014445
0x180014432  mov     rax, [rsp+258h+var_238]
0x180014437  xor     ebx, ebx
0x180014439  mov     [rdi], rax
0x18001443c  mov     [rsp+258h+var_238], 0
0x180014445  lea     rcx, [rsp+258h+var_238]
0x18001444a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001444f  mov     eax, ebx
0x180014451  mov     rcx, [rsp+258h+var_18]
0x180014459  xor     rcx, rsp; StackCookie
0x18001445c  call    __security_check_cookie
0x180014461  mov     rbx, [rsp+258h+arg_8]
0x180014469  add     rsp, 250h
0x180014470  pop     rdi
0x180014471  retn
```
