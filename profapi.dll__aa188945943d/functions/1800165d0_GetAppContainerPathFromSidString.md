# GetAppContainerPathFromSidString

- ea: `0x1800165d0`
- end: `0x1800166be`
- name: `GetAppContainerPathFromSidString`
- size: `238`
- prototype: `__int64 __fastcall(char *, unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180002484`
- `0x180005b60`
- `0x180005b90`
- `0x18000a540`
- `0x180016250`
- `0x1800165d0`

## string_xrefs

- `0x180016641`: `_GetAppContainerPath %ws %ws`

## pseudocode

```c
__int64 __fastcall GetAppContainerPathFromSidString(
        char *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int64 a4)
{
  int AppContainerPath; // eax
  unsigned int v9; // ebx
  unsigned int v10; // edi
  int v11; // eax
  int v13; // [rsp+20h] [rbp-78h]
  unsigned __int16 *v14; // [rsp+40h] [rbp-58h] BYREF
  __int64 v15; // [rsp+48h] [rbp-50h]
  __int64 v16; // [rsp+50h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v14 = 0;
  v15 = 0;
  v16 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v14);
  v15 = -1;
  v16 = -1;
  AppContainerPath = _GetAppContainerPath(a1, a2, &v14);
  v9 = -2147024877;
  v10 = AppContainerPath;
  if ( AppContainerPath != -2147024877 )
  {
    if ( AppContainerPath >= 0 )
    {
      v11 = StringCchCopyW(a3, a4, v14);
      v9 = v11;
      if ( v11 >= 0 )
        v9 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14E,
          (unsigned int)"minio\\profapi\\appcontainer.cpp",
          (const char *)(unsigned int)v11,
          v13);
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x14D,
        (unsigned int)"minio\\profapi\\appcontainer.cpp",
        (const char *)(unsigned int)AppContainerPath,
        (int)"_GetAppContainerPath %ws %ws",
        a1,
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
0x1800165d0  mov     rax, rsp
0x1800165d3  push    rbx
0x1800165d4  push    rbp
0x1800165d5  push    rsi
0x1800165d6  push    rdi
0x1800165d7  push    r14
0x1800165d9  push    r15
0x1800165db  sub     rsp, 68h
0x1800165df  mov     rbp, rcx
0x1800165e2  mov     qword ptr [rax-58h], 0
0x1800165ea  lea     rcx, [rax-58h]
0x1800165ee  mov     qword ptr [rax-50h], 0
0x1800165f6  mov     r14, r9
0x1800165f9  mov     qword ptr [rax-48h], 0
0x180016601  mov     r15, r8
0x180016604  mov     rsi, rdx
0x180016607  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001660c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016610  lea     r8, [rsp+98h+var_58]; unsigned __int16 **
0x180016615  mov     rdx, rsi; unsigned __int16 *
0x180016618  mov     [rsp+98h+var_50], rax
0x18001661d  mov     rcx, rbp; char *
0x180016620  mov     [rsp+98h+var_48], rax
0x180016625  call    ?_GetAppContainerPath@@YAJPEBG0PEAPEAG@Z; _GetAppContainerPath(ushort const *,ushort const *,ushort * *)
0x18001662a  mov     ebx, 80070013h
0x18001662f  mov     edi, eax
0x180016631  cmp     eax, ebx
0x180016633  jz      short loc_1800166A5
0x180016635  test    eax, eax
0x180016637  jns     short loc_18001666F
0x180016639  mov     rcx, [rsp+98h]; this
0x180016641  lea     rax, aGetappcontaine_1; "_GetAppContainerPath %ws %ws"
0x180016648  mov     [rsp+98h+var_68], rsi
0x18001664d  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180016654  mov     [rsp+98h+var_70], rbp; char *
0x180016659  mov     r9d, edi; char *
0x18001665c  mov     edx, 14Dh; void *
0x180016661  mov     qword ptr [rsp+98h+var_78], rax; int
0x180016666  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001666b  mov     ebx, edi
0x18001666d  jmp     short loc_1800166A5
0x18001666f  mov     r8, [rsp+98h+var_58]; unsigned __int16 *
0x180016674  mov     rdx, r14; unsigned __int64
0x180016677  mov     rcx, r15; unsigned __int16 *
0x18001667a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001667f  mov     ebx, eax
0x180016681  test    eax, eax
0x180016683  jns     short loc_1800166A3
0x180016685  mov     rcx, [rsp+98h]; this
0x18001668d  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x180016694  mov     r9d, eax; char *
0x180016697  mov     edx, 14Eh; void *
0x18001669c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800166a1  jmp     short loc_1800166A5
0x1800166a3  xor     ebx, ebx
0x1800166a5  lea     rcx, [rsp+98h+var_58]
0x1800166aa  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x1800166af  mov     eax, ebx
0x1800166b1  add     rsp, 68h
0x1800166b5  pop     r15
0x1800166b7  pop     r14
0x1800166b9  pop     rdi
0x1800166ba  pop     rsi
0x1800166bb  pop     rbp
0x1800166bc  pop     rbx
0x1800166bd  retn
```
