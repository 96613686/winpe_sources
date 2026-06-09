# NgcUtils::GetWindowsAikAlternateLocation(ushort * *)

- ea: `0x18001d85c`
- end: `0x18001d94e`
- name: `?GetWindowsAikAlternateLocation@NgcUtils@@YAJPEAPEAG@Z`
- size: `242`
- prototype: `__int64 __fastcall(unsigned __int16 ***this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d954`

## callees

- `0x180006330`
- `0x18000cc34`
- `0x180010310`
- `0x180014bcc`
- `0x18001c754`
- `0x18001d85c`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPath` at `0x18001d88e`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18001d88e`

## string_xrefs

- `0x18001d8a2`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`
- `0x18001d8f8`: `onecore\ds\security\ngc\utils\common\lib\cryptutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
           &qword_180024840,
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
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)v7);
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
0x18001d85c  mov     [rsp+arg_8], rbx
0x18001d861  push    rdi
0x18001d862  sub     rsp, 250h
0x18001d869  mov     rax, cs:__security_cookie
0x18001d870  xor     rax, rsp
0x18001d873  mov     [rsp+258h+var_18], rax
0x18001d87b  xor     edx, edx
0x18001d87d  lea     r8, [rsp+258h+var_228]
0x18001d882  mov     rdi, rcx
0x18001d885  mov     r9d, 104h
0x18001d88b  lea     ecx, [rdx+4]
0x18001d88e  call    cs:__imp_GetBasicProfileFolderPath
0x18001d894  mov     ebx, eax
0x18001d896  test    eax, eax
0x18001d898  jns     short loc_18001D8B8
0x18001d89a  mov     rcx, [rsp+258h]; this
0x18001d8a2  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d8a9  mov     r9d, eax; char *
0x18001d8ac  mov     edx, 16h; void *
0x18001d8b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d8b6  jmp     short loc_18001D92B
0x18001d8b8  xor     edx, edx
0x18001d8ba  mov     [rsp+258h+var_238], 0; int
0x18001d8c3  lea     rcx, [rsp+258h+var_238]
0x18001d8c8  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001d8cd  lea     r9, [rsp+258h+var_238]; unsigned __int16 *
0x18001d8d2  lea     r8, aMicrosoftCrypt; "\\Microsoft\\Crypto\\PCPKSP\\WindowsAIK"
0x18001d8d9  lea     rdx, qword_180024840; unsigned __int16 *
0x18001d8e0  lea     rcx, [rsp+258h+var_228]; this
0x18001d8e5  call    ?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001d8ea  mov     ebx, eax
0x18001d8ec  test    eax, eax
0x18001d8ee  jns     short loc_18001D90E
0x18001d8f0  mov     rcx, [rsp+258h]; this
0x18001d8f8  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001d8ff  mov     r9d, eax; char *
0x18001d902  mov     edx, 1Dh; void *
0x18001d907  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d90c  jmp     short loc_18001D921
0x18001d90e  mov     rax, [rsp+258h+var_238]
0x18001d913  xor     ebx, ebx
0x18001d915  mov     [rdi], rax
0x18001d918  mov     [rsp+258h+var_238], 0
0x18001d921  lea     rcx, [rsp+258h+var_238]
0x18001d926  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001d92b  mov     eax, ebx
0x18001d92d  mov     rcx, [rsp+258h+var_18]
0x18001d935  xor     rcx, rsp; StackCookie
0x18001d938  call    __security_check_cookie
0x18001d93d  mov     rbx, [rsp+258h+arg_8]
0x18001d945  add     rsp, 250h
0x18001d94c  pop     rdi
0x18001d94d  retn
```
