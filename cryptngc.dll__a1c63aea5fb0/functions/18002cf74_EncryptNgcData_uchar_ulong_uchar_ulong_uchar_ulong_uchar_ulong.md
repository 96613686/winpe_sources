# EncryptNgcData(uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18002cf74`
- end: `0x18002d085`
- name: `?EncryptNgcData@@YAJPEAEK0K0KPEAPEAEPEAK@Z`
- size: `273`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, PUCHAR pbInput, ULONG cbInput, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003c2ec`

## callees

- `0x180006538`
- `0x180018430`
- `0x180019ef4`
- `0x180027824`
- `0x18002cf74`
- `0x18002d08c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d046`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d046`

## string_xrefs

- `0x18002cfaf`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`
- `0x18002d021`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkeyencrypt.cpp`

## pseudocode

```c
__int64 __fastcall EncryptNgcData(
        NgcUtils *a1,
        __int64 a2,
        unsigned __int8 *a3,
        int a4,
        PUCHAR pbInput,
        ULONG cbInput,
        unsigned __int8 **a7,
        unsigned int *a8)
{
  int AesCbcKeyHandle; // eax
  UCHAR *v9; // r9
  int v10; // ebx
  HLOCAL v11; // rcx
  unsigned __int8 *v12; // rax
  ULONG v14; // [rsp+20h] [rbp-50h]
  int v15; // [rsp+20h] [rbp-50h]
  void **v16; // [rsp+28h] [rbp-48h]
  HLOCAL hMem; // [rsp+40h] [rbp-30h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+48h] [rbp-28h] BYREF
  HLOCAL *p_hMem; // [rsp+50h] [rbp-20h] BYREF
  unsigned int v20[2]; // [rsp+58h] [rbp-18h] BYREF
  char v21; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  unsigned __int8 *v23; // [rsp+98h] [rbp+28h] BYREF

  LODWORD(v23) = a4;
  hKey = 0;
  AesCbcKeyHandle = NgcUtils::GetAesCbcKeyHandle(
                      a1,
                      (unsigned __int8 *)0x20,
                      (unsigned int)a3,
                      (unsigned __int8 *)0x10,
                      (unsigned int)&hKey,
                      v16);
  v10 = AesCbcKeyHandle;
  if ( AesCbcKeyHandle >= 0 )
  {
    p_hMem = &hMem;
    LODWORD(v23) = 0;
    hMem = 0;
    *(_QWORD *)v20 = 0;
    v21 = 1;
    v10 = NgcUtils::EncryptData(hKey, pbInput, cbInput, v9, v14, (PUCHAR *)v20, &v23);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
    if ( v10 >= 0 )
    {
      v12 = (unsigned __int8 *)hMem;
      v10 = 0;
      hMem = 0;
      *a7 = v12;
      *a8 = (unsigned int)v23;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
        (const char *)(unsigned int)v10,
        v15);
      v11 = hMem;
      hMem = 0;
      if ( v11 )
        LocalFree(v11);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE5,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkeyencrypt.cpp",
      (const char *)(unsigned int)AesCbcKeyHandle,
      v14);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002cf74  mov     [rsp-8+arg_0], rbx
0x18002cf79  mov     dword ptr [rsp-8+arg_18], r9d
0x18002cf7e  push    rbp
0x18002cf7f  mov     rbp, rsp
0x18002cf82  sub     rsp, 70h
0x18002cf86  mov     edx, 20h ; ' '; unsigned __int8 *
0x18002cf8b  mov     [rbp+hKey], 0
0x18002cf93  lea     rax, [rbp+hKey]
0x18002cf97  mov     qword ptr [rsp+70h+var_50], rax; int
0x18002cf9c  lea     r9d, [rdx-10h]; unsigned __int8 *
0x18002cfa0  call    ?GetAesCbcKeyHandle@NgcUtils@@YAJPEAEK0KPEAPEAX@Z; NgcUtils::GetAesCbcKeyHandle(uchar *,ulong,uchar *,ulong,void * *)
0x18002cfa5  mov     ebx, eax
0x18002cfa7  test    eax, eax
0x18002cfa9  jns     short loc_18002CFC8
0x18002cfab  mov     rcx, [rbp+8]; this
0x18002cfaf  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18002cfb6  mov     r9d, eax; char *
0x18002cfb9  mov     edx, 0E5h; void *
0x18002cfbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002cfc3  jmp     loc_18002D06C
0x18002cfc8  mov     r8d, [rbp+cbInput]; cbInput
0x18002cfcc  lea     rax, [rbp+hMem]
0x18002cfd0  mov     rdx, [rbp+pbInput]; pbInput
0x18002cfd4  mov     rcx, [rbp+hKey]; hKey
0x18002cfd8  mov     [rbp+var_20], rax
0x18002cfdc  lea     rax, [rbp+arg_18]
0x18002cfe0  mov     [rsp+70h+var_40], rax; unsigned __int8 **
0x18002cfe5  lea     rax, [rbp+var_18]
0x18002cfe9  mov     qword ptr [rsp+70h+var_48], rax; unsigned int
0x18002cfee  mov     dword ptr [rbp+arg_18], 0
0x18002cff5  mov     [rbp+hMem], 0
0x18002cffd  mov     qword ptr [rbp+var_18], 0
0x18002d005  mov     [rbp+var_10], 1
0x18002d009  call    ?EncryptData@NgcUtils@@YAJPEAXPEAEK1KPEAPEAEPEAK@Z; NgcUtils::EncryptData(void *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x18002d00e  lea     rcx, [rbp+var_20]
0x18002d012  mov     ebx, eax
0x18002d014  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18002d019  test    ebx, ebx
0x18002d01b  jns     short loc_18002D04E
0x18002d01d  mov     rcx, [rbp+8]; this
0x18002d021  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18002d028  mov     r9d, ebx; char *
0x18002d02b  mov     edx, 0F0h; void *
0x18002d030  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d035  mov     rcx, [rbp+hMem]; hMem
0x18002d039  mov     [rbp+hMem], 0
0x18002d041  test    rcx, rcx
0x18002d044  jz      short loc_18002D06C
0x18002d046  call    cs:__imp_LocalFree
0x18002d04c  jmp     short loc_18002D06C
0x18002d04e  mov     rax, [rbp+hMem]
0x18002d052  xor     ebx, ebx
0x18002d054  mov     rcx, [rbp+arg_30]
0x18002d058  mov     [rbp+hMem], 0
0x18002d060  mov     [rcx], rax
0x18002d063  mov     rcx, [rbp+arg_38]
0x18002d067  mov     eax, dword ptr [rbp+arg_18]
0x18002d06a  mov     [rcx], eax
0x18002d06c  lea     rcx, [rbp+hKey]
0x18002d070  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002d075  mov     eax, ebx
0x18002d077  mov     rbx, [rsp+70h+arg_0]
0x18002d07f  add     rsp, 70h
0x18002d083  pop     rbp
0x18002d084  retn
```
