# CTSSecurityDescriptor::AddUserAce(void *,ulong)

- ea: `0x180009ad4`
- end: `0x180009bec`
- name: `?AddUserAce@CTSSecurityDescriptor@@QEAAJPEAXK@Z`
- size: `280`
- prototype: `int(CTSSecurityDescriptor *__hidden this, void *, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009a34`
- `0x18000ab80`

## callees

- `0x1800077a0`
- `0x180009ad4`
- `0x180009bf4`
- `0x18000a4a0`
- `0x18000acec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b7b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180009b06`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180009b06`

## string_xrefs

- `0x180009bd6`: `CTSSecurityDescriptor::AddUserAce`
- `0x180009b72`: `GetSecurityDescriptorControl failed: 0x%x in %s`
- `0x180009bcf`: `CUtils::AddAceToSecurityDescriptor failed: 0x%x in %s`

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
0x180009ad4  mov     r11, rsp
0x180009ad7  mov     [r11+10h], rbx
0x180009adb  push    rbp
0x180009adc  push    rsi
0x180009add  push    rdi
0x180009ade  sub     rsp, 30h
0x180009ae2  xor     eax, eax
0x180009ae4  lea     rdi, [rcx+8]
0x180009ae8  mov     rcx, [rdi]; pSecurityDescriptor
0x180009aeb  mov     esi, r8d
0x180009aee  mov     rbp, rdx
0x180009af1  mov     [rsp+48h+arg_0], ax
0x180009af6  lea     r8, [r11+20h]; lpdwRevision
0x180009afa  mov     [rsp+48h+arg_18], eax
0x180009afe  lea     rdx, [r11+8]; pControl
0x180009b02  mov     [r11-28h], rax
0x180009b06  call    cs:__imp_GetSecurityDescriptorControl
0x180009b0d  nop     dword ptr [rax+rax+00h]
0x180009b12  test    eax, eax
0x180009b14  jz      short loc_180009B50
0x180009b16  mov     eax, 8000h
0x180009b1b  test    [rsp+48h+arg_0], ax
0x180009b20  jz      loc_180009BA6
0x180009b26  xor     r9d, r9d; unsigned __int8
0x180009b29  mov     r8, rbp; void *
0x180009b2c  mov     edx, esi; unsigned int
0x180009b2e  mov     rcx, rdi; void **
0x180009b31  call    ?AddAceToSecurityDescriptor@CUtils@@SAJPEAPEAXKPEAXE@Z; CUtils::AddAceToSecurityDescriptor(void * *,ulong,void *,uchar)
0x180009b36  mov     ebx, eax
0x180009b38  test    eax, eax
0x180009b3a  js      loc_180009BCC
0x180009b40  mov     eax, ebx
0x180009b42  mov     rbx, [rsp+48h+arg_8]
0x180009b47  add     rsp, 30h
0x180009b4b  pop     rdi
0x180009b4c  pop     rsi
0x180009b4d  pop     rbp
0x180009b4e  retn
0x180009b50  call    cs:__imp_GetLastError
0x180009b57  nop     dword ptr [rax+rax+00h]
0x180009b5c  mov     ebx, eax
0x180009b5e  test    eax, eax
0x180009b60  jle     short loc_180009B6B
0x180009b62  movzx   ebx, ax
0x180009b65  or      ebx, 80070000h
0x180009b6b  test    ebx, ebx
0x180009b6d  jns     short loc_180009B16
0x180009b6f  mov     r8d, ebx
0x180009b72  lea     rdx, aGetsecuritydes_2; "GetSecurityDescriptorControl failed: 0x"...
0x180009b79  jmp     short loc_180009BD6
0x180009b7b  call    cs:__imp_GetLastError
0x180009b82  nop     dword ptr [rax+rax+00h]
0x180009b87  mov     ebx, eax
0x180009b89  test    eax, eax
0x180009b8b  jle     short loc_180009B96
0x180009b8d  movzx   ebx, ax
0x180009b90  or      ebx, 80070000h
0x180009b96  test    ebx, ebx
0x180009b98  jns     short loc_180009BB7
0x180009b9a  mov     r8d, ebx
0x180009b9d  lea     rdx, aCutilsAbsolute; "CUtils::AbsoluteToSelfRelativeSD failed"...
0x180009ba4  jmp     short loc_180009BD6
0x180009ba6  mov     rcx, [rdi]; pAbsoluteSecurityDescriptor
0x180009ba9  lea     rdx, [rsp+48h+var_28]; void **
0x180009bae  call    ?AbsoluteToSelfRelativeSD@CUtils@@SAHPEAXPEAPEAXPEAK@Z; CUtils::AbsoluteToSelfRelativeSD(void *,void * *,ulong *)
0x180009bb3  test    eax, eax
0x180009bb5  jz      short loc_180009B7B
0x180009bb7  mov     rcx, [rdi]; hMem
0x180009bba  call    ?CleanupSD@CUtils@@SAXPEAX@Z; CUtils::CleanupSD(void *)
0x180009bbf  mov     rax, [rsp+48h+var_28]
0x180009bc4  mov     [rdi], rax
0x180009bc7  jmp     loc_180009B26
0x180009bcc  mov     r8d, eax
0x180009bcf  lea     rdx, aCutilsAddaceto; "CUtils::AddAceToSecurityDescriptor fail"...
0x180009bd6  lea     r9, aCtssecuritydes; "CTSSecurityDescriptor::AddUserAce"
0x180009bdd  mov     ecx, 8; int
0x180009be2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180009be7  jmp     loc_180009B40
```
