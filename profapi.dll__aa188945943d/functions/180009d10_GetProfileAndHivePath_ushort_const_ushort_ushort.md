# _GetProfileAndHivePath(ushort const *,ushort * *,ushort * *)

- ea: `0x180009d10`
- end: `0x180009e5d`
- name: `?_GetProfileAndHivePath@@YAJPEBGPEAPEAG1@Z`
- size: `333`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d23c`

## callees

- `0x180004990`
- `0x180005b60`
- `0x180005b90`
- `0x1800091f0`
- `0x180009d10`
- `0x18000a1c0`
- `0x18000a3e0`

## string_xrefs

- `0x180009d64`: `ProfileImagePath`
- `0x180009d85`: `%SystemRoot%\ServiceProfiles\LocalService`
- `0x180009d9a`: `%SystemRoot%\ServiceProfiles\NetworkService`

## pseudocode

```c
__int64 __fastcall _GetProfileAndHivePath(const unsigned __int16 *a1, unsigned __int16 **a2, unsigned __int16 **a3)
{
  int IsEqual; // ebx
  const WCHAR *v6; // r8
  const unsigned __int16 *v7; // rdx
  int v8; // eax
  unsigned int v9; // ebx
  unsigned __int16 *v10; // rdi
  int v11; // eax
  unsigned __int16 *v12; // rax
  unsigned __int16 *v14; // [rsp+20h] [rbp-38h] BYREF
  __int64 v15; // [rsp+28h] [rbp-30h]
  __int64 v16; // [rsp+30h] [rbp-28h]
  unsigned __int16 *v17; // [rsp+38h] [rbp-20h] BYREF
  __int64 v18; // [rsp+40h] [rbp-18h]
  __int64 v19; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]

  *a2 = 0;
  *a3 = 0;
  IsEqual = StringIsEqual(a1, L"S-1-5-19");
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v6 = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList\\S-1-5-19";
  if ( !IsEqual )
    v6 = L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList\\S-1-5-20";
  if ( Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
         (__int64)&v14,
         HKEY_LOCAL_MACHINE,
         v6,
         L"ProfileImagePath") >= 0 )
    goto LABEL_8;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v14);
  v7 = L"%SystemRoot%\\ServiceProfiles\\LocalService";
  v15 = -1;
  v16 = -1;
  if ( !IsEqual )
    v7 = L"%SystemRoot%\\ServiceProfiles\\NetworkService";
  v8 = ExpandEnvStringAlloc(0, v7, &v14);
  v9 = v8;
  if ( v8 >= 0 )
  {
LABEL_8:
    v10 = v14;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v11 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
            &v17,
            L"%s\\NTUSER.DAT",
            v14);
    v9 = v11;
    if ( v11 >= 0 )
    {
      v12 = v17;
      *a2 = v10;
      *a3 = v12;
      v14 = 0;
      v16 = 0;
      v15 = 0;
      v17 = 0;
      v19 = 0;
      v18 = 0;
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v17);
      v9 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"minio\\profapi\\load.cpp",
        (const char *)(unsigned int)v11,
        (int)v14);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v17);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"minio\\profapi\\load.cpp",
      (const char *)(unsigned int)v8,
      (int)v14);
  }
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)&v14);
  return v9;
}

```

## disassembly

```asm
0x180009d10  push    rbp
0x180009d12  push    rbx
0x180009d13  push    rsi
0x180009d14  push    rdi
0x180009d15  push    r14
0x180009d17  push    r15
0x180009d19  mov     rbp, rsp
0x180009d1c  sub     rsp, 58h
0x180009d20  xor     r15d, r15d
0x180009d23  mov     r14, rdx
0x180009d26  mov     [rdx], r15
0x180009d29  mov     rsi, r8
0x180009d2c  lea     rdx, aS1519; "S-1-5-19"
0x180009d33  mov     [r8], r15
0x180009d36  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x180009d3b  mov     ebx, eax
0x180009d3d  mov     [rbp+var_38], r15
0x180009d41  lea     rax, aSoftwareMicros_23; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180009d48  mov     [rbp+var_30], r15
0x180009d4c  test    ebx, ebx
0x180009d4e  mov     [rbp+var_28], r15
0x180009d52  lea     r8, aSoftwareMicros_27; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180009d59  mov     rdx, 0FFFFFFFF80000002h
0x180009d60  cmovz   r8, rax
0x180009d64  lea     r9, aProfileimagepa; "ProfileImagePath"
0x180009d6b  lea     rcx, [rbp+var_38]
0x180009d6f  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x180009d74  test    eax, eax
0x180009d76  jns     short loc_180009DCB
0x180009d78  lea     rcx, [rbp+var_38]
0x180009d7c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009d81  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009d85  lea     rdx, aSystemrootServ; "%SystemRoot%\\ServiceProfiles\\LocalSer"...
0x180009d8c  mov     [rbp+var_30], rax
0x180009d90  lea     r8, [rbp+var_38]; unsigned __int16 **
0x180009d94  mov     [rbp+var_28], rax
0x180009d98  test    ebx, ebx
0x180009d9a  lea     rax, aSystemrootServ_0; "%SystemRoot%\\ServiceProfiles\\NetworkS"...
0x180009da1  cmovz   rdx, rax; unsigned __int16 *
0x180009da5  xor     ecx, ecx; void *
0x180009da7  call    ?ExpandEnvStringAlloc@@YAJQEAXPEBGPEAPEAG@Z; ExpandEnvStringAlloc(void * const,ushort const *,ushort * *)
0x180009dac  mov     ebx, eax
0x180009dae  test    eax, eax
0x180009db0  jns     short loc_180009DCB
0x180009db2  mov     rcx, [rbp+30h]; this
0x180009db6  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x180009dbd  mov     r9d, eax; char *
0x180009dc0  lea     edx, [r15+3Ah]; void *
0x180009dc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009dc9  jmp     short loc_180009E45
0x180009dcb  mov     rdi, [rbp+var_38]
0x180009dcf  lea     rdx, aSNtuserDat; "%s\\NTUSER.DAT"
0x180009dd6  mov     r8, rdi
0x180009dd9  mov     [rbp+var_20], r15
0x180009ddd  lea     rcx, [rbp+var_20]
0x180009de1  mov     [rbp+var_18], r15
0x180009de5  mov     [rbp+var_10], r15
0x180009de9  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180009dee  mov     ebx, eax
0x180009df0  test    eax, eax
0x180009df2  jns     short loc_180009E17
0x180009df4  mov     rcx, [rbp+30h]; this
0x180009df8  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x180009dff  mov     r9d, eax; char *
0x180009e02  mov     edx, 3Eh ; '>'; void *
0x180009e07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e0c  lea     rcx, [rbp+var_20]
0x180009e10  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009e15  jmp     short loc_180009E45
0x180009e17  mov     rax, [rbp+var_20]
0x180009e1b  lea     rcx, [rbp+var_20]
0x180009e1f  mov     [r14], rdi
0x180009e22  mov     [rsi], rax
0x180009e25  mov     [rbp+var_38], r15
0x180009e29  mov     [rbp+var_28], r15
0x180009e2d  mov     [rbp+var_30], r15
0x180009e31  mov     [rbp+var_20], r15
0x180009e35  mov     [rbp+var_10], r15
0x180009e39  mov     [rbp+var_18], r15
0x180009e3d  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009e42  mov     ebx, r15d
0x180009e45  lea     rcx, [rbp+var_38]
0x180009e49  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180009e4e  mov     eax, ebx
0x180009e50  add     rsp, 58h
0x180009e54  pop     r15
0x180009e56  pop     r14
0x180009e58  pop     rdi
0x180009e59  pop     rsi
0x180009e5a  pop     rbx
0x180009e5b  pop     rbp
0x180009e5c  retn
```
