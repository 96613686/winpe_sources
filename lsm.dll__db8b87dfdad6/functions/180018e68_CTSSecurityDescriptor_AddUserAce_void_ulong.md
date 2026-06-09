# CTSSecurityDescriptor::AddUserAce(void *,ulong)

- ea: `0x180018e68`
- end: `0x180018f65`
- name: `?AddUserAce@CTSSecurityDescriptor@@QEAAJPEAXK@Z`
- size: `253`
- prototype: `int(CTSSecurityDescriptor *__hidden this, void *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018dd0`
- `0x180019dc8`

## callees

- `0x1800074c0`
- `0x180018e68`
- `0x180018f6c`
- `0x180019734`
- `0x180019f28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018efa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018efa`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180018e9a`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180018e9a`

## string_xrefs

- `0x180018f4f`: `CTSSecurityDescriptor::AddUserAce`
- `0x180018ef1`: `GetSecurityDescriptorControl failed: 0x%x in %s`
- `0x180018f48`: `CUtils::AddAceToSecurityDescriptor failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSecurityDescriptor::AddUserAce(CTSSecurityDescriptor *this, void *a2, int a3)
{
  PSECURITY_DESCRIPTOR *v3; // rdi
  void *v4; // rcx
  unsigned int *v7; // r8
  int v8; // eax
  unsigned int v9; // ebx
  signed int LastError; // eax
  signed int v12; // eax
  void *v13; // [rsp+20h] [rbp-28h] BYREF
  __int16 v14; // [rsp+50h] [rbp+8h] BYREF
  DWORD v15; // [rsp+68h] [rbp+20h] BYREF

  v3 = (PSECURITY_DESCRIPTOR *)((char *)this + 8);
  v4 = (void *)*((_QWORD *)this + 1);
  v14 = 0;
  v15 = 0;
  v13 = 0;
  if ( GetSecurityDescriptorControl(v4, (PSECURITY_DESCRIPTOR_CONTROL)&v14, &v15) )
    goto LABEL_2;
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( (v9 & 0x80000000) == 0 )
  {
LABEL_2:
    if ( v14 >= 0 )
    {
      if ( !(unsigned int)CUtils::AbsoluteToSelfRelativeSD(*v3, &v13, v7) )
      {
        v12 = GetLastError();
        v9 = v12;
        if ( v12 > 0 )
          v9 = (unsigned __int16)v12 | 0x80070000;
        if ( (v9 & 0x80000000) != 0 )
        {
          _DbgPrintMessage(
            8,
            "CUtils::AbsoluteToSelfRelativeSD failed: 0x%x in %s",
            v9,
            "CTSSecurityDescriptor::AddUserAce");
          return v9;
        }
      }
      CUtils::CleanupSD(*v3);
      *v3 = v13;
    }
    v8 = CUtils::AddAceToSecurityDescriptor(v3, a3, a2, 0);
    v9 = v8;
    if ( v8 < 0 )
      _DbgPrintMessage(
        8,
        "CUtils::AddAceToSecurityDescriptor failed: 0x%x in %s",
        (unsigned int)v8,
        "CTSSecurityDescriptor::AddUserAce");
  }
  else
  {
    _DbgPrintMessage(8, "GetSecurityDescriptorControl failed: 0x%x in %s", v9, "CTSSecurityDescriptor::AddUserAce");
  }
  return v9;
}

```

## disassembly

```asm
0x180018e68  mov     r11, rsp
0x180018e6b  mov     [r11+10h], rbx
0x180018e6f  push    rbp
0x180018e70  push    rsi
0x180018e71  push    rdi
0x180018e72  sub     rsp, 30h
0x180018e76  xor     eax, eax
0x180018e78  lea     rdi, [rcx+8]
0x180018e7c  mov     rcx, [rdi]; pSecurityDescriptor
0x180018e7f  mov     esi, r8d
0x180018e82  mov     rbp, rdx
0x180018e85  mov     [rsp+48h+arg_0], ax
0x180018e8a  lea     r8, [r11+20h]; lpdwRevision
0x180018e8e  mov     [rsp+48h+arg_18], eax
0x180018e92  lea     rdx, [r11+8]; pControl
0x180018e96  mov     [r11-28h], rax
0x180018e9a  call    cs:__imp_GetSecurityDescriptorControl
0x180018ea0  test    eax, eax
0x180018ea2  jz      short loc_180018ED5
0x180018ea4  mov     eax, 8000h
0x180018ea9  test    [rsp+48h+arg_0], ax
0x180018eae  jz      short loc_180018F1F
0x180018eb0  xor     r9d, r9d; unsigned __int8
0x180018eb3  mov     r8, rbp; void *
0x180018eb6  mov     edx, esi; unsigned int
0x180018eb8  mov     rcx, rdi; void **
0x180018ebb  call    ?AddAceToSecurityDescriptor@CUtils@@SAJPEAPEAXKPEAXE@Z; CUtils::AddAceToSecurityDescriptor(void * *,ulong,void *,uchar)
0x180018ec0  mov     ebx, eax
0x180018ec2  test    eax, eax
0x180018ec4  js      short loc_180018F45
0x180018ec6  mov     eax, ebx
0x180018ec8  mov     rbx, [rsp+48h+arg_8]
0x180018ecd  add     rsp, 30h
0x180018ed1  pop     rdi
0x180018ed2  pop     rsi
0x180018ed3  pop     rbp
0x180018ed4  retn
0x180018ed5  call    cs:__imp_GetLastError
0x180018edb  mov     ebx, eax
0x180018edd  test    eax, eax
0x180018edf  jle     short loc_180018EEA
0x180018ee1  movzx   ebx, ax
0x180018ee4  or      ebx, 80070000h
0x180018eea  test    ebx, ebx
0x180018eec  jns     short loc_180018EA4
0x180018eee  mov     r8d, ebx
0x180018ef1  lea     rdx, aGetsecuritydes_2; "GetSecurityDescriptorControl failed: 0x"...
0x180018ef8  jmp     short loc_180018F4F
0x180018efa  call    cs:__imp_GetLastError
0x180018f00  mov     ebx, eax
0x180018f02  test    eax, eax
0x180018f04  jle     short loc_180018F0F
0x180018f06  movzx   ebx, ax
0x180018f09  or      ebx, 80070000h
0x180018f0f  test    ebx, ebx
0x180018f11  jns     short loc_180018F30
0x180018f13  mov     r8d, ebx
0x180018f16  lea     rdx, aCutilsAbsolute; "CUtils::AbsoluteToSelfRelativeSD failed"...
0x180018f1d  jmp     short loc_180018F4F
0x180018f1f  mov     rcx, [rdi]; pAbsoluteSecurityDescriptor
0x180018f22  lea     rdx, [rsp+48h+var_28]; void **
0x180018f27  call    ?AbsoluteToSelfRelativeSD@CUtils@@SAHPEAXPEAPEAXPEAK@Z; CUtils::AbsoluteToSelfRelativeSD(void *,void * *,ulong *)
0x180018f2c  test    eax, eax
0x180018f2e  jz      short loc_180018EFA
0x180018f30  mov     rcx, [rdi]; hMem
0x180018f33  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x180018f38  mov     rax, [rsp+48h+var_28]
0x180018f3d  mov     [rdi], rax
0x180018f40  jmp     loc_180018EB0
0x180018f45  mov     r8d, eax
0x180018f48  lea     rdx, aCutilsAddaceto; "CUtils::AddAceToSecurityDescriptor fail"...
0x180018f4f  lea     r9, aCtssecuritydes; "CTSSecurityDescriptor::AddUserAce"
0x180018f56  mov     ecx, 8; int
0x180018f5b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180018f60  jmp     loc_180018EC6
```
