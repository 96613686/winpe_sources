# _CopyFromDefaultProfile(ushort const *,void *)

- ea: `0x180016bec`
- end: `0x180016ceb`
- name: `?_CopyFromDefaultProfile@@YAJPEBGPEAX@Z`
- size: `255`
- prototype: `__int64 __fastcall(const unsigned __int16 *, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000caa0`

## callees

- `0x180005b60`
- `0x1800087f0`
- `0x18000a540`
- `0x18000d620`
- `0x18000fa10`
- `0x180016bec`
- `0x180016d14`

## pseudocode

```c
__int64 __fastcall _CopyFromDefaultProfile(const unsigned __int16 *a1, PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  unsigned __int64 v4; // rdx
  int BasicProfileFolderPath; // ebx
  __int64 v6; // rdx
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // r9
  int pSecurityDescriptora; // [rsp+20h] [rbp-458h]
  unsigned __int16 v11[264]; // [rsp+30h] [rbp-448h] BYREF
  unsigned __int16 v12[264]; // [rsp+240h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+478h] [rbp+0h]

  BasicProfileFolderPath = StringCchCopyW(v11, 0x104u, a1);
  if ( BasicProfileFolderPath < 0 )
  {
    v6 = 334;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"minio\\profapi\\load.cpp",
      (const char *)(unsigned int)BasicProfileFolderPath,
      pSecurityDescriptora);
    return (unsigned int)BasicProfileFolderPath;
  }
  _SetSecurityOnTree(v11, v4, pSecurityDescriptor);
  BasicProfileFolderPath = StringCchCopyW(v11, 0x104u, a1);
  if ( BasicProfileFolderPath < 0 )
  {
    v6 = 339;
    goto LABEL_3;
  }
  pSecurityDescriptora = 0;
  BasicProfileFolderPath = GetBasicProfileFolderPathEx(2, 0, v12, 0x104u);
  if ( BasicProfileFolderPath < 0 )
  {
    v6 = 342;
    goto LABEL_3;
  }
  BasicProfileFolderPath = _CopyTree(v12, v8, v11, v9, pSecurityDescriptor);
  if ( BasicProfileFolderPath < 0 )
  {
    v6 = 343;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180016bec  mov     [rsp+arg_10], rbx
0x180016bf1  push    rbp
0x180016bf2  push    rsi
0x180016bf3  push    rdi
0x180016bf4  sub     rsp, 460h
0x180016bfb  mov     rax, cs:__security_cookie
0x180016c02  xor     rax, rsp
0x180016c05  mov     [rsp+478h+var_28], rax
0x180016c0d  mov     rdi, rdx
0x180016c10  mov     rsi, rcx
0x180016c13  mov     r8, rcx; unsigned __int16 *
0x180016c16  mov     ebp, 104h
0x180016c1b  mov     edx, ebp; unsigned __int64
0x180016c1d  lea     rcx, [rsp+478h+var_448]; unsigned __int16 *
0x180016c22  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016c27  mov     ebx, eax
0x180016c29  test    eax, eax
0x180016c2b  jns     short loc_180016C4B
0x180016c2d  lea     edx, [rbp+4Ah]; void *
0x180016c30  mov     rcx, [rsp+478h]; this
0x180016c38  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x180016c3f  mov     r9d, ebx; char *
0x180016c42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c47  mov     eax, ebx
0x180016c49  jmp     short loc_180016CC8
0x180016c4b  mov     r8, rdi; void *
0x180016c4e  lea     rcx, [rsp+478h+var_448]; unsigned __int16 *
0x180016c53  call    ?_SetSecurityOnTree@@YAJPEAG_KPEAX@Z; _SetSecurityOnTree(ushort *,unsigned __int64,void *)
0x180016c58  mov     r8, rsi; unsigned __int16 *
0x180016c5b  lea     rcx, [rsp+478h+var_448]; unsigned __int16 *
0x180016c60  mov     rdx, rbp; unsigned __int64
0x180016c63  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016c68  mov     ebx, eax
0x180016c6a  test    eax, eax
0x180016c6c  jns     short loc_180016C75
0x180016c6e  mov     edx, 153h
0x180016c73  jmp     short loc_180016C30
0x180016c75  xor     edx, edx
0x180016c77  mov     [rsp+478h+pSecurityDescriptor], 0
0x180016c7f  mov     r9, rbp
0x180016c82  lea     r8, [rsp+478h+var_238]
0x180016c8a  lea     ecx, [rdx+2]
0x180016c8d  call    GetBasicProfileFolderPathEx
0x180016c92  mov     ebx, eax
0x180016c94  test    eax, eax
0x180016c96  jns     short loc_180016C9F
0x180016c98  mov     edx, 156h
0x180016c9d  jmp     short loc_180016C30
0x180016c9f  lea     r8, [rsp+478h+var_448]; unsigned __int16 *
0x180016ca4  mov     qword ptr [rsp+478h+pSecurityDescriptor], rdi; pSecurityDescriptor
0x180016ca9  lea     rcx, [rsp+478h+var_238]; unsigned __int16 *
0x180016cb1  call    ?_CopyTree@@YAJPEAG_K01PEAX@Z; _CopyTree(ushort *,unsigned __int64,ushort *,unsigned __int64,void *)
0x180016cb6  mov     ebx, eax
0x180016cb8  test    eax, eax
0x180016cba  jns     short loc_180016CC6
0x180016cbc  mov     edx, 157h
0x180016cc1  jmp     loc_180016C30
0x180016cc6  xor     eax, eax
0x180016cc8  mov     rcx, [rsp+478h+var_28]
0x180016cd0  xor     rcx, rsp; StackCookie
0x180016cd3  call    __security_check_cookie
0x180016cd8  mov     rbx, [rsp+478h+arg_10]
0x180016ce0  add     rsp, 460h
0x180016ce7  pop     rdi
0x180016ce8  pop     rsi
0x180016ce9  pop     rbp
0x180016cea  retn
```
