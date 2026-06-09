# GetAppContainerSpecificSubPath

- ea: `0x18000c0f0`
- end: `0x18000c1d2`
- name: `GetAppContainerSpecificSubPath`
- size: `226`
- prototype: `__int64 __fastcall(void *, char *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002484`
- `0x180005b60`
- `0x180005b90`
- `0x18000a540`
- `0x18000c0f0`
- `0x18000ce3c`

## string_xrefs

- `0x18000c15f`: `_GetAppContainerSpecificSubPath %ws`

## pseudocode

```c
__int64 __fastcall GetAppContainerSpecificSubPath(void *a1, char *a2, unsigned __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // rbp
  int AppContainerSpecificSubPath; // eax
  unsigned int v9; // ebx
  unsigned int v10; // edi
  int v11; // eax
  int v13; // [rsp+20h] [rbp-58h]
  unsigned __int16 *v14; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+38h] [rbp-40h]
  __int64 v16; // [rsp+40h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v5 = a4;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v14);
  v15 = -1;
  v16 = -1;
  AppContainerSpecificSubPath = _GetAppContainerSpecificSubPath(a1, (const unsigned __int16 *)a2, 0, &v14);
  v9 = -2147024877;
  v10 = AppContainerSpecificSubPath;
  if ( AppContainerSpecificSubPath != -2147024877 )
  {
    if ( AppContainerSpecificSubPath >= 0 )
    {
      v11 = StringCchCopyW(a3, v5, v14);
      v9 = v11;
      if ( v11 >= 0 )
        v9 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x179,
          (unsigned int)"minio\\profapi\\appcontainer.cpp",
          (const char *)(unsigned int)v11,
          v13);
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x178,
        (unsigned int)"minio\\profapi\\appcontainer.cpp",
        (const char *)(unsigned int)AppContainerSpecificSubPath,
        (int)"_GetAppContainerSpecificSubPath %ws",
        a2);
      v9 = v10;
    }
  }
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v14);
  return v9;
}

```

## disassembly

```asm
0x18000c0f0  mov     rax, rsp
0x18000c0f3  push    rbx
0x18000c0f4  push    rbp
0x18000c0f5  push    rsi
0x18000c0f6  push    rdi
0x18000c0f7  push    r14
0x18000c0f9  sub     rsp, 50h
0x18000c0fd  mov     rbx, rcx
0x18000c100  mov     ebp, r9d
0x18000c103  lea     rcx, [rax-48h]
0x18000c107  mov     qword ptr [rax-48h], 0
0x18000c10f  mov     r14, r8
0x18000c112  mov     qword ptr [rax-40h], 0
0x18000c11a  mov     rsi, rdx
0x18000c11d  mov     qword ptr [rax-38h], 0
0x18000c125  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000c12a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c12e  lea     r9, [rsp+78h+var_48]; unsigned __int16 **
0x18000c133  xor     r8d, r8d; int
0x18000c136  mov     [rsp+78h+var_40], rax
0x18000c13b  mov     rdx, rsi; unsigned __int16 *
0x18000c13e  mov     [rsp+78h+var_38], rax
0x18000c143  mov     rcx, rbx; void *
0x18000c146  call    ?_GetAppContainerSpecificSubPath@@YAJPEAXPEBGHPEAPEAG@Z; _GetAppContainerSpecificSubPath(void *,ushort const *,int,ushort * *)
0x18000c14b  mov     ebx, 80070013h
0x18000c150  mov     edi, eax
0x18000c152  cmp     eax, ebx
0x18000c154  jz      short loc_18000C1BB
0x18000c156  test    eax, eax
0x18000c158  jns     short loc_18000C188
0x18000c15a  mov     rcx, [rsp+78h]; this
0x18000c15f  lea     rax, aGetappcontaine; "_GetAppContainerSpecificSubPath %ws"
0x18000c166  mov     [rsp+78h+var_50], rsi; char *
0x18000c16b  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x18000c172  mov     r9d, edi; char *
0x18000c175  mov     qword ptr [rsp+78h+var_58], rax; int
0x18000c17a  mov     edx, 178h; void *
0x18000c17f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000c184  mov     ebx, edi
0x18000c186  jmp     short loc_18000C1BB
0x18000c188  mov     r8, [rsp+78h+var_48]; unsigned __int16 *
0x18000c18d  mov     rdx, rbp; unsigned __int64
0x18000c190  mov     rcx, r14; unsigned __int16 *
0x18000c193  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c198  mov     ebx, eax
0x18000c19a  test    eax, eax
0x18000c19c  jns     short loc_18000C1B9
0x18000c19e  mov     rcx, [rsp+78h]; this
0x18000c1a3  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x18000c1aa  mov     r9d, eax; char *
0x18000c1ad  mov     edx, 179h; void *
0x18000c1b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c1b7  jmp     short loc_18000C1BB
0x18000c1b9  xor     ebx, ebx
0x18000c1bb  lea     rcx, [rsp+78h+var_48]
0x18000c1c0  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18000c1c5  mov     eax, ebx
0x18000c1c7  add     rsp, 50h
0x18000c1cb  pop     r14
0x18000c1cd  pop     rdi
0x18000c1ce  pop     rsi
0x18000c1cf  pop     rbp
0x18000c1d0  pop     rbx
0x18000c1d1  retn
```
