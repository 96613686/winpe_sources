# _GetAppContainerPath(ushort const *,ushort const *,ushort * *)

- ea: `0x180016250`
- end: `0x1800163f5`
- name: `?_GetAppContainerPath@@YAJPEBG0PEAPEAG@Z`
- size: `421`
- prototype: `__int64 __fastcall(char *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cf24`
- `0x1800165d0`

## callees

- `0x1800017e4`
- `0x180002484`
- `0x180004c10`
- `0x180005b60`
- `0x180005b90`
- `0x180008910`
- `0x180016250`

## string_xrefs

- `0x1800162d3`: `GetBasicProfileFolderPathAlloc %ws`

## pseudocode

```c
__int64 __fastcall _GetAppContainerPath(char *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  int BasicProfileFolderPathAlloc; // eax
  unsigned int v7; // ebx
  unsigned int v8; // edi
  int AppContainerSpecificSubPath; // eax
  int v10; // eax
  int v12; // [rsp+20h] [rbp-40h]
  unsigned __int16 *v13; // [rsp+30h] [rbp-30h] BYREF
  __int64 v14; // [rsp+38h] [rbp-28h]
  __int64 v15; // [rsp+40h] [rbp-20h]
  unsigned __int16 *v16; // [rsp+48h] [rbp-18h] BYREF
  __int64 v17; // [rsp+50h] [rbp-10h]
  __int64 v18; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  *a3 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v13);
  v14 = -1;
  v15 = -1;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(8, (const unsigned __int16 *)a1, &v13);
  v7 = -2147024877;
  v8 = BasicProfileFolderPathAlloc;
  if ( BasicProfileFolderPathAlloc != -2147024877 )
  {
    v7 = -2147024891;
    if ( BasicProfileFolderPathAlloc != -2147024891 )
    {
      if ( BasicProfileFolderPathAlloc < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xBB,
          (unsigned int)"minio\\profapi\\appcontainer.cpp",
          (const char *)(unsigned int)BasicProfileFolderPathAlloc,
          (int)"GetBasicProfileFolderPathAlloc %ws",
          a1);
LABEL_5:
        v7 = v8;
        goto LABEL_13;
      }
      v16 = 0;
      v17 = 0;
      v18 = 0;
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v16);
      v17 = -1;
      v18 = -1;
      AppContainerSpecificSubPath = _GetAppContainerSpecificSubPath((const unsigned __int16 *)a1, a2, 0, &v16);
      v7 = -2147024894;
      v8 = AppContainerSpecificSubPath;
      if ( AppContainerSpecificSubPath != -2147024894 )
      {
        if ( AppContainerSpecificSubPath < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC0,
            (unsigned int)"minio\\profapi\\appcontainer.cpp",
            (const char *)(unsigned int)AppContainerSpecificSubPath,
            v12);
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v16);
          goto LABEL_5;
        }
        v10 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
                &v13,
                L"\\Packages\\%s",
                v16);
        v7 = v10;
        if ( v10 >= 0 )
        {
          *a3 = v13;
          v13 = 0;
          v15 = 0;
          v14 = 0;
          Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v16);
          v7 = 0;
          goto LABEL_13;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC3,
          (unsigned int)"minio\\profapi\\appcontainer.cpp",
          (const char *)(unsigned int)v10,
          v12);
      }
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v16);
    }
  }
LABEL_13:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v13);
  return v7;
}

```

## disassembly

```asm
0x180016250  push    rbp
0x180016252  push    rbx
0x180016253  push    rsi
0x180016254  push    rdi
0x180016255  push    r13
0x180016257  push    r14
0x180016259  push    r15
0x18001625b  mov     rbp, rsp
0x18001625e  sub     rsp, 60h
0x180016262  mov     rsi, rcx
0x180016265  mov     qword ptr [r8], 0
0x18001626c  lea     rcx, [rbp+var_30]
0x180016270  mov     [rbp+var_30], 0
0x180016278  mov     r14, r8
0x18001627b  mov     [rbp+var_28], 0
0x180016283  mov     r15, rdx
0x180016286  mov     [rbp+var_20], 0
0x18001628e  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180016293  or      r13, 0FFFFFFFFFFFFFFFFh
0x180016297  lea     r8, [rbp+var_30]
0x18001629b  mov     rdx, rsi
0x18001629e  mov     [rbp+var_28], r13
0x1800162a2  mov     [rbp+var_20], r13
0x1800162a6  lea     ecx, [r13+9]
0x1800162aa  call    GetBasicProfileFolderPathAlloc
0x1800162af  mov     ebx, 80070013h
0x1800162b4  mov     edi, eax
0x1800162b6  cmp     eax, ebx
0x1800162b8  jz      loc_1800163DB
0x1800162be  mov     ebx, 80070005h
0x1800162c3  cmp     eax, ebx
0x1800162c5  jz      loc_1800163DB
0x1800162cb  test    eax, eax
0x1800162cd  jns     short loc_1800162FF
0x1800162cf  mov     rcx, [rbp+38h]; this
0x1800162d3  lea     rax, aGetbasicprofil; "GetBasicProfileFolderPathAlloc %ws"
0x1800162da  mov     [rsp+60h+var_38], rsi; char *
0x1800162df  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x1800162e6  mov     r9d, edi; char *
0x1800162e9  mov     qword ptr [rsp+60h+var_40], rax; int
0x1800162ee  mov     edx, 0BBh; void *
0x1800162f3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800162f8  mov     ebx, edi
0x1800162fa  jmp     loc_1800163DB
0x1800162ff  lea     rcx, [rbp+var_18]
0x180016303  mov     [rbp+var_18], 0
0x18001630b  mov     [rbp+var_10], 0
0x180016313  mov     [rbp+var_8], 0
0x18001631b  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180016320  lea     r9, [rbp+var_18]; unsigned __int16 **
0x180016324  mov     [rbp+var_10], r13
0x180016328  xor     r8d, r8d; int
0x18001632b  mov     [rbp+var_8], r13
0x18001632f  mov     rdx, r15; unsigned __int16 *
0x180016332  mov     rcx, rsi; unsigned __int16 *
0x180016335  call    ?_GetAppContainerSpecificSubPath@@YAJPEBG0HPEAPEAG@Z; _GetAppContainerSpecificSubPath(ushort const *,ushort const *,int,ushort * *)
0x18001633a  mov     ebx, 80070002h
0x18001633f  mov     edi, eax
0x180016341  cmp     eax, ebx
0x180016343  jnz     short loc_180016353
0x180016345  lea     rcx, [rbp+var_18]
0x180016349  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001634e  jmp     loc_1800163DB
0x180016353  test    edi, edi
0x180016355  jns     short loc_18001637D
0x180016357  mov     rcx, [rbp+38h]; this
0x18001635b  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180016362  mov     r9d, edi; char *
0x180016365  mov     edx, 0C0h; void *
0x18001636a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001636f  lea     rcx, [rbp+var_18]
0x180016373  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180016378  jmp     loc_1800162F8
0x18001637d  mov     r8, [rbp+var_18]
0x180016381  lea     rdx, aPackagesS; "\\Packages\\%s"
0x180016388  lea     rcx, [rbp+var_30]
0x18001638c  call    ?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x180016391  mov     ebx, eax
0x180016393  test    eax, eax
0x180016395  jns     short loc_1800163B1
0x180016397  mov     rcx, [rbp+38h]; this
0x18001639b  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x1800163a2  mov     r9d, eax; char *
0x1800163a5  mov     edx, 0C3h; void *
0x1800163aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800163af  jmp     short loc_180016345
0x1800163b1  mov     rax, [rbp+var_30]
0x1800163b5  lea     rcx, [rbp+var_18]
0x1800163b9  mov     [r14], rax
0x1800163bc  mov     [rbp+var_30], 0
0x1800163c4  mov     [rbp+var_20], 0
0x1800163cc  mov     [rbp+var_28], 0
0x1800163d4  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800163d9  xor     ebx, ebx
0x1800163db  lea     rcx, [rbp+var_30]
0x1800163df  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800163e4  mov     eax, ebx
0x1800163e6  add     rsp, 60h
0x1800163ea  pop     r15
0x1800163ec  pop     r14
0x1800163ee  pop     r13
0x1800163f0  pop     rdi
0x1800163f1  pop     rsi
0x1800163f2  pop     rbx
0x1800163f3  pop     rbp
0x1800163f4  retn
```
