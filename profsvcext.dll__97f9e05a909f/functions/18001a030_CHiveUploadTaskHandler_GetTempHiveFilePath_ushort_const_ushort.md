# CHiveUploadTaskHandler::_GetTempHiveFilePath(ushort const *,ushort * *)

- ea: `0x18001a030`
- end: `0x18001a146`
- name: `?_GetTempHiveFilePath@CHiveUploadTaskHandler@@AEAAJPEBGPEAPEAG@Z`
- size: `278`
- prototype: `__int64 __fastcall(CHiveUploadTaskHandler *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180018a3c`

## callees

- `0x180005424`
- `0x180006a9c`
- `0x180012f28`
- `0x1800160d4`
- `0x18001a030`

## import_xrefs

- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18001a086`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x18001a086`

## string_xrefs

- `0x18001a0be`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
__int64 __fastcall CHiveUploadTaskHandler::_GetTempHiveFilePath(
        CHiveUploadTaskHandler *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int BasicProfileFolderPathAlloc; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  unsigned __int16 *v9; // [rsp+20h] [rbp-20h] BYREF
  __int64 v10; // [rsp+28h] [rbp-18h]
  __int64 v11; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]

  *a3 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v9);
  v10 = -1;
  v11 = -1;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(6, a2, &v9);
  v6 = BasicProfileFolderPathAlloc;
  if ( BasicProfileFolderPathAlloc >= 0 )
  {
    BasicProfileFolderPathAlloc = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Concat(
                                    &v9,
                                    L"\\Microsoft\\Windows\\HiveUpload",
                                    29);
    v6 = BasicProfileFolderPathAlloc;
    if ( BasicProfileFolderPathAlloc >= 0 )
    {
      BasicProfileFolderPathAlloc = CreateNestedDirectory(v9, 0);
      v6 = BasicProfileFolderPathAlloc;
      if ( BasicProfileFolderPathAlloc >= 0 )
      {
        BasicProfileFolderPathAlloc = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Concat(
                                        &v9,
                                        L"\\ntuser.dat",
                                        11);
        v6 = BasicProfileFolderPathAlloc;
        if ( BasicProfileFolderPathAlloc >= 0 )
        {
          v6 = 0;
          *a3 = v9;
          v9 = 0;
          v11 = 0;
          v10 = 0;
          goto LABEL_11;
        }
        v7 = 510;
      }
      else
      {
        v7 = 509;
      }
    }
    else
    {
      v7 = 508;
    }
  }
  else
  {
    v7 = 507;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
    (const char *)(unsigned int)BasicProfileFolderPathAlloc,
    (int)v9);
LABEL_11:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v9);
  return v6;
}

```

## disassembly

```asm
0x18001a030  mov     [rsp-8+arg_0], rbx
0x18001a035  mov     [rsp-8+arg_8], rdi
0x18001a03a  push    rbp
0x18001a03b  mov     rbp, rsp
0x18001a03e  sub     rsp, 40h
0x18001a042  lea     rcx, [rbp+var_20]
0x18001a046  mov     qword ptr [r8], 0
0x18001a04d  mov     rdi, r8
0x18001a050  mov     [rbp+var_20], 0
0x18001a058  mov     rbx, rdx
0x18001a05b  mov     [rbp+var_18], 0
0x18001a063  mov     [rbp+var_10], 0
0x18001a06b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001a070  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a074  lea     r8, [rbp+var_20]
0x18001a078  mov     rdx, rbx
0x18001a07b  mov     [rbp+var_18], rax
0x18001a07f  mov     [rbp+var_10], rax
0x18001a083  lea     ecx, [rax+7]
0x18001a086  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x18001a08c  mov     ebx, eax
0x18001a08e  test    eax, eax
0x18001a090  jns     short loc_18001A099
0x18001a092  mov     edx, 1FBh
0x18001a097  jmp     short loc_18001A0BA
0x18001a099  mov     r8d, 1Dh
0x18001a09f  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\HiveUpload"
0x18001a0a6  lea     rcx, [rbp+var_20]
0x18001a0aa  call    ?_Concat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18001a0af  mov     ebx, eax
0x18001a0b1  test    eax, eax
0x18001a0b3  jns     short loc_18001A0CF
0x18001a0b5  mov     edx, 1FCh; void *
0x18001a0ba  mov     rcx, [rbp+8]; this
0x18001a0be  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x18001a0c5  mov     r9d, eax; char *
0x18001a0c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a0cd  jmp     short loc_18001A12B
0x18001a0cf  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x18001a0d3  xor     edx, edx; lpSecurityAttributes
0x18001a0d5  call    ?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x18001a0da  mov     ebx, eax
0x18001a0dc  test    eax, eax
0x18001a0de  jns     short loc_18001A0E7
0x18001a0e0  mov     edx, 1FDh
0x18001a0e5  jmp     short loc_18001A0BA
0x18001a0e7  mov     r8d, 0Bh
0x18001a0ed  lea     rdx, aNtuserDat; "\\ntuser.dat"
0x18001a0f4  lea     rcx, [rbp+var_20]
0x18001a0f8  call    ?_Concat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x18001a0fd  mov     ebx, eax
0x18001a0ff  test    eax, eax
0x18001a101  jns     short loc_18001A10A
0x18001a103  mov     edx, 1FEh
0x18001a108  jmp     short loc_18001A0BA
0x18001a10a  mov     rax, [rbp+var_20]
0x18001a10e  xor     ebx, ebx
0x18001a110  mov     [rdi], rax
0x18001a113  mov     [rbp+var_20], 0
0x18001a11b  mov     [rbp+var_10], 0
0x18001a123  mov     [rbp+var_18], 0
0x18001a12b  lea     rcx, [rbp+var_20]
0x18001a12f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001a134  mov     rdi, [rsp+40h+arg_8]
0x18001a139  mov     eax, ebx
0x18001a13b  mov     rbx, [rsp+40h+arg_0]
0x18001a140  add     rsp, 40h
0x18001a144  pop     rbp
0x18001a145  retn
```
