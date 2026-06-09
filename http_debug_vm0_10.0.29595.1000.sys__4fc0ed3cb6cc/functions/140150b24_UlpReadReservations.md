# UlpReadReservations

- ea: `0x140150b24`
- end: `0x140150e07`
- name: `UlpReadReservations`
- size: `739`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1401502e0`

## callees

- `0x140042490`
- `0x14009fd68`
- `0x1401503f0`
- `0x1401508b0`
- `0x140150b24`
- `0x140151260`
- `0x140167810`
- `0x140167c40`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x140150bfd`
- `ntoskrnl!ZwCreateKey` at `0x140150bfd`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140150c84`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140150c84`
- `ntoskrnl!ExAllocatePool3` at `0x140150d7f`
- `ntoskrnl!ExAllocatePool3` at `0x140150d7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150cfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150d53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150dda`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150cfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150d53`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150dda`

## string_xrefs

- `0x140150b4d`: `\Registry\Machine\System\CurrentControlSet\Services\Http\Parameters\UrlAclInfo`

## pseudocode

```c
void __fastcall UlpReadReservations(__int64 a1)
{
  int inited; // eax
  int v3; // edx
  HANDLE *v4; // r15
  NTSTATUS v5; // eax
  int v6; // edx
  int v7; // r14d
  unsigned int *p_KeyValueInformation; // rbx
  ULONG v9; // esi
  ULONG v10; // r12d
  NTSTATUS v11; // eax
  int v12; // edx
  __int64 v13; // r9
  int v14; // edi
  ULONG v15; // eax
  PUNICODE_STRING Class; // [rsp+20h] [rbp-E0h]
  PUNICODE_STRING Classa; // [rsp+20h] [rbp-E0h]
  PUNICODE_STRING Classb; // [rsp+20h] [rbp-E0h]
  PVOID P; // [rsp+50h] [rbp-B0h] BYREF
  ULONG ResultLength; // [rsp+58h] [rbp-A8h] BYREF
  ULONG Disposition; // [rsp+5Ch] [rbp-A4h] BYREF
  __int128 v22; // [rsp+60h] [rbp-A0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v24[144]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 KeyValueInformation; // [rsp+130h] [rbp+30h] BYREF
  __int64 v26; // [rsp+140h] [rbp+40h]

  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v26 = 0;
  Disposition = 0;
  KeyValueInformation = 0;
  ResultLength = 0;
  v22 = 0;
  inited = UlInitUnicodeStringEx(
             &v22,
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\Http\\Parameters\\UrlAclInfo");
  if ( inited < 0 )
  {
    LODWORD(P) = inited;
    LODWORD(Class) = 4;
    UlWriteEventLogEntry(-1073726815, v3, 0, 0, (size_t)Class, &P);
    return;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v22;
  v4 = (HANDLE *)(a1 + 1400);
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = ZwCreateKey((PHANDLE)(a1 + 1400), 0x2001Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
  if ( v5 < 0 )
  {
    LODWORD(P) = v5;
    LODWORD(Classa) = 4;
    UlWriteEventLogEntry(-1073726815, v6, 0, 0, (size_t)Classa, &P);
    *v4 = 0;
    return;
  }
  if ( Disposition != 1 )
  {
    v7 = 1;
    ResultLength = 0;
    p_KeyValueInformation = (unsigned int *)&KeyValueInformation;
    v9 = 0;
    KeyValueInformation = 0;
    v10 = 24;
    v26 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        v11 = ZwEnumerateValueKey(*v4, v9, KeyValueFullInformation, p_KeyValueInformation, v10, &ResultLength);
        if ( !v11 )
          break;
        if ( v11 == -2147483622 )
          goto LABEL_23;
        if ( v11 != -2147483643 )
        {
          LODWORD(P) = v11;
LABEL_22:
          LODWORD(Classb) = 4;
          UlWriteEventLogEntry(-1073726815, v12, 0, 0, (size_t)Classb, &P);
LABEL_23:
          if ( p_KeyValueInformation != (unsigned int *)&KeyValueInformation && p_KeyValueInformation )
            ExFreePoolWithTag(p_KeyValueInformation, 0);
          return;
        }
        v15 = ResultLength;
        v10 = ResultLength;
        if ( p_KeyValueInformation != (unsigned int *)&KeyValueInformation )
        {
          ExFreePoolWithTag(p_KeyValueInformation, 0);
          v15 = ResultLength;
        }
        p_KeyValueInformation = (unsigned int *)ExAllocatePool3(256, v15, 1146252373, UxLowPriorityPool, 1);
        if ( !p_KeyValueInformation )
        {
          LODWORD(P) = -1073741670;
          goto LABEL_22;
        }
      }
      P = 0;
      memset(v24, 0, 0x88u);
      if ( (int)UlpValidateUrlSdPair(a1, p_KeyValueInformation, &P, v24) < 0 )
      {
        v14 = -1073741492;
      }
      else
      {
        v14 = UlpAddReservationEntry(
                a1,
                (__int64)v24,
                (__int64)p_KeyValueInformation + p_KeyValueInformation[2],
                v13,
                0,
                0,
                0,
                0,
                0);
        ExFreePoolWithTag(P, 0);
        if ( v14 >= 0 )
          goto LABEL_14;
      }
      if ( v7 )
      {
        v7 = 0;
        UlpLogSpecificInitFailure(p_KeyValueInformation, (unsigned int)v14);
      }
LABEL_14:
      ++v9;
    }
  }
}

```

## disassembly

```asm
0x140150b24  push    rbp
0x140150b26  push    rbx
0x140150b27  push    rsi
0x140150b28  push    rdi
0x140150b29  push    r12
0x140150b2b  push    r13
0x140150b2d  push    r14
0x140150b2f  push    r15
0x140150b31  lea     rbp, [rsp-58h]
0x140150b36  sub     rsp, 158h
0x140150b3d  mov     rax, cs:__security_cookie
0x140150b44  xor     rax, rsp
0x140150b47  mov     [rbp+90h+var_48], rax
0x140150b4b  xor     edi, edi
0x140150b4d  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x140150b54  xorps   xmm0, xmm0
0x140150b57  mov     dword ptr [rsp+190h+ObjectAttributes+4], edi
0x140150b5b  xor     eax, eax
0x140150b5d  mov     dword ptr [rbp+90h+ObjectAttributes+1Ch], edi
0x140150b60  mov     r13, rcx
0x140150b63  mov     [rbp+90h+var_50], rax
0x140150b67  lea     rcx, [rsp+190h+var_130]
0x140150b6c  mov     [rsp+190h+var_134], edi
0x140150b70  movups  [rbp+90h+KeyValueInformation], xmm0
0x140150b74  mov     [rsp+190h+ResultLength], edi
0x140150b78  movups  [rsp+190h+var_130], xmm0
0x140150b7d  call    UlInitUnicodeStringEx
0x140150b82  test    eax, eax
0x140150b84  jns     short loc_140150BB1
0x140150b86  mov     dword ptr [rsp+190h+P], eax
0x140150b8a  xor     r8d, r8d; int
0x140150b8d  lea     rax, [rsp+190h+P]
0x140150b92  xor     r9d, r9d; int
0x140150b95  mov     qword ptr [rsp+190h+CreateOptions], rax; Src
0x140150b9a  mov     ecx, 0C0003AA1h; int
0x140150b9f  mov     dword ptr [rsp+190h+Class], 4; Size
0x140150ba7  call    UlWriteEventLogEntry
0x140150bac  jmp     loc_140150DE6
0x140150bb1  lea     rax, [rsp+190h+var_130]
0x140150bb6  mov     [rsp+190h+ObjectAttributes.Length], 30h ; '0'
0x140150bbe  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x140150bc2  lea     r15, [r13+578h]
0x140150bc9  lea     rax, [rsp+190h+var_134]
0x140150bce  mov     [rsp+190h+ObjectAttributes.RootDirectory], rdi
0x140150bd3  mov     [rsp+190h+Disposition], rax; Disposition
0x140150bd8  lea     r8, [rsp+190h+ObjectAttributes]; ObjectAttributes
0x140150bdd  mov     [rsp+190h+CreateOptions], edi; CreateOptions
0x140150be1  xor     r9d, r9d; TitleIndex
0x140150be4  mov     edx, 2001Fh; DesiredAccess
0x140150be9  mov     [rsp+190h+Class], rdi; Class
0x140150bee  mov     rcx, r15; KeyHandle
0x140150bf1  mov     [rbp+90h+ObjectAttributes.Attributes], 240h
0x140150bf8  movdqu  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x140150bfd  call    cs:__imp_ZwCreateKey
0x140150c04  nop     dword ptr [rax+rax+00h]
0x140150c09  test    eax, eax
0x140150c0b  jns     short loc_140150C3B
0x140150c0d  mov     dword ptr [rsp+190h+P], eax
0x140150c11  xor     r8d, r8d; int
0x140150c14  lea     rax, [rsp+190h+P]
0x140150c19  xor     r9d, r9d; int
0x140150c1c  mov     qword ptr [rsp+190h+CreateOptions], rax; Src
0x140150c21  mov     ecx, 0C0003AA1h; int
0x140150c26  mov     dword ptr [rsp+190h+Class], 4; Size
0x140150c2e  call    UlWriteEventLogEntry
0x140150c33  mov     [r15], rdi
0x140150c36  jmp     loc_140150DE6
0x140150c3b  cmp     [rsp+190h+var_134], 1
0x140150c40  jz      loc_140150DE6
0x140150c46  mov     r14d, 1
0x140150c4c  mov     [rsp+190h+ResultLength], edi
0x140150c50  xorps   xmm0, xmm0
0x140150c53  lea     rbx, [rbp+90h+KeyValueInformation]
0x140150c57  xor     eax, eax
0x140150c59  mov     esi, edi
0x140150c5b  movups  [rbp+90h+KeyValueInformation], xmm0
0x140150c5f  lea     r12d, [r14+17h]
0x140150c63  mov     [rbp+90h+var_50], rax
0x140150c67  mov     rcx, [r15]; KeyHandle
0x140150c6a  lea     rax, [rsp+190h+ResultLength]
0x140150c6f  mov     qword ptr [rsp+190h+CreateOptions], rax; ResultLength
0x140150c74  mov     r9, rbx; KeyValueInformation
0x140150c77  mov     r8d, 1; KeyValueInformationClass
0x140150c7d  mov     dword ptr [rsp+190h+Class], r12d; Length
0x140150c82  mov     edx, esi; Index
0x140150c84  call    cs:__imp_ZwEnumerateValueKey
0x140150c8b  nop     dword ptr [rax+rax+00h]
0x140150c90  test    eax, eax
0x140150c92  jnz     loc_140150D2C
0x140150c98  xor     edx, edx; Val
0x140150c9a  mov     [rsp+190h+P], rdi
0x140150c9f  mov     r8d, 88h; Size
0x140150ca5  lea     rcx, [rbp+90h+var_F0]; void *
0x140150ca9  call    memset
0x140150cae  lea     r9, [rbp+90h+var_F0]
0x140150cb2  mov     rdx, rbx
0x140150cb5  lea     r8, [rsp+190h+P]
0x140150cba  mov     rcx, r13
0x140150cbd  call    UlpValidateUrlSdPair
0x140150cc2  test    eax, eax
0x140150cc4  js      short loc_140150D0C
0x140150cc6  mov     r8d, [rbx+8]
0x140150cca  lea     rdx, [rbp+90h+var_F0]
0x140150cce  mov     [rsp+190h+var_150], dil
0x140150cd3  add     r8, rbx
0x140150cd6  mov     [rsp+190h+var_158], rdi
0x140150cdb  mov     rcx, r13
0x140150cde  mov     byte ptr [rsp+190h+Disposition], dil
0x140150ce3  mov     [rsp+190h+CreateOptions], edi
0x140150ce7  mov     [rsp+190h+Class], rdi
0x140150cec  call    UlpAddReservationEntry
0x140150cf1  mov     rcx, [rsp+190h+P]; P
0x140150cf6  xor     edx, edx; Tag
0x140150cf8  mov     edi, eax
0x140150cfa  call    cs:__imp_ExFreePoolWithTag
0x140150d01  nop     dword ptr [rax+rax+00h]
0x140150d06  test    edi, edi
0x140150d08  jns     short loc_140150D23
0x140150d0a  jmp     short loc_140150D11
0x140150d0c  mov     edi, 0C000014Ch
0x140150d11  test    r14d, r14d
0x140150d14  jz      short loc_140150D23
0x140150d16  xor     r14d, r14d
0x140150d19  mov     edx, edi
0x140150d1b  mov     rcx, rbx
0x140150d1e  call    UlpLogSpecificInitFailure
0x140150d23  inc     esi
0x140150d25  xor     edi, edi
0x140150d27  jmp     loc_140150C67
0x140150d2c  cmp     eax, 8000001Ah
0x140150d31  jz      loc_140150DC7
0x140150d37  cmp     eax, 80000005h
0x140150d3c  jnz     short loc_140150DA1
0x140150d3e  mov     eax, [rsp+190h+ResultLength]
0x140150d42  lea     rcx, [rbp+90h+KeyValueInformation]
0x140150d46  mov     r12d, eax
0x140150d49  cmp     rbx, rcx
0x140150d4c  jz      short loc_140150D63
0x140150d4e  xor     edx, edx; Tag
0x140150d50  mov     rcx, rbx; P
0x140150d53  call    cs:__imp_ExFreePoolWithTag
0x140150d5a  nop     dword ptr [rax+rax+00h]
0x140150d5f  mov     eax, [rsp+190h+ResultLength]
0x140150d63  mov     edx, eax
0x140150d65  lea     r9, UxLowPriorityPool
0x140150d6c  mov     ecx, 100h
0x140150d71  mov     dword ptr [rsp+190h+Class], 1
0x140150d79  mov     r8d, 44526C55h
0x140150d7f  call    cs:__imp_ExAllocatePool3
0x140150d86  nop     dword ptr [rax+rax+00h]
0x140150d8b  mov     rbx, rax
0x140150d8e  test    rax, rax
0x140150d91  jnz     loc_140150C67
0x140150d97  mov     dword ptr [rsp+190h+P], 0C000009Ah
0x140150d9f  jmp     short loc_140150DA5
0x140150da1  mov     dword ptr [rsp+190h+P], eax
0x140150da5  lea     rax, [rsp+190h+P]
0x140150daa  xor     r9d, r9d; int
0x140150dad  mov     qword ptr [rsp+190h+CreateOptions], rax; Src
0x140150db2  xor     r8d, r8d; int
0x140150db5  mov     ecx, 0C0003AA1h; int
0x140150dba  mov     dword ptr [rsp+190h+Class], 4; Size
0x140150dc2  call    UlWriteEventLogEntry
0x140150dc7  lea     rax, [rbp+90h+KeyValueInformation]
0x140150dcb  cmp     rbx, rax
0x140150dce  jz      short loc_140150DE6
0x140150dd0  test    rbx, rbx
0x140150dd3  jz      short loc_140150DE6
0x140150dd5  xor     edx, edx; Tag
0x140150dd7  mov     rcx, rbx; P
0x140150dda  call    cs:__imp_ExFreePoolWithTag
0x140150de1  nop     dword ptr [rax+rax+00h]
0x140150de6  mov     rcx, [rbp+90h+var_48]
0x140150dea  xor     rcx, rsp; StackCookie
0x140150ded  call    __security_check_cookie
0x140150df2  add     rsp, 158h
0x140150df9  pop     r15
0x140150dfb  pop     r14
0x140150dfd  pop     r13
0x140150dff  pop     r12
0x140150e01  pop     rdi
0x140150e02  pop     rsi
0x140150e03  pop     rbx
0x140150e04  pop     rbp
0x140150e05  retn
```
