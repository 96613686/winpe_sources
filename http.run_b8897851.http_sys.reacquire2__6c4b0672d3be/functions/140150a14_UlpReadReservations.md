# UlpReadReservations

- ea: `0x140150a14`
- end: `0x140150cf7`
- name: `UlpReadReservations`
- size: `739`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1401501d0`

## callees

- `0x1400424b0`
- `0x14009fd88`
- `0x1401502e0`
- `0x1401507a0`
- `0x140150a14`
- `0x140151150`
- `0x140167700`
- `0x140167b40`

## import_xrefs

- `ntoskrnl!ZwCreateKey` at `0x140150aed`
- `ntoskrnl!ZwCreateKey` at `0x140150aed`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140150b74`
- `ntoskrnl!ZwEnumerateValueKey` at `0x140150b74`
- `ntoskrnl!ExAllocatePool3` at `0x140150c6f`
- `ntoskrnl!ExAllocatePool3` at `0x140150c6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150bea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150c43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150cca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150bea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150c43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140150cca`

## string_xrefs

- `0x140150a3d`: `\Registry\Machine\System\CurrentControlSet\Services\Http\Parameters\UrlAclInfo`

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
0x140150a14  push    rbp
0x140150a16  push    rbx
0x140150a17  push    rsi
0x140150a18  push    rdi
0x140150a19  push    r12
0x140150a1b  push    r13
0x140150a1d  push    r14
0x140150a1f  push    r15
0x140150a21  lea     rbp, [rsp-58h]
0x140150a26  sub     rsp, 158h
0x140150a2d  mov     rax, cs:__security_cookie
0x140150a34  xor     rax, rsp
0x140150a37  mov     [rbp+90h+var_48], rax
0x140150a3b  xor     edi, edi
0x140150a3d  lea     rdx, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x140150a44  xorps   xmm0, xmm0
0x140150a47  mov     dword ptr [rsp+190h+ObjectAttributes+4], edi
0x140150a4b  xor     eax, eax
0x140150a4d  mov     dword ptr [rbp+90h+ObjectAttributes+1Ch], edi
0x140150a50  mov     r13, rcx
0x140150a53  mov     [rbp+90h+var_50], rax
0x140150a57  lea     rcx, [rsp+190h+var_130]
0x140150a5c  mov     [rsp+190h+var_134], edi
0x140150a60  movups  [rbp+90h+KeyValueInformation], xmm0
0x140150a64  mov     [rsp+190h+ResultLength], edi
0x140150a68  movups  [rsp+190h+var_130], xmm0
0x140150a6d  call    UlInitUnicodeStringEx
0x140150a72  test    eax, eax
0x140150a74  jns     short loc_140150AA1
0x140150a76  mov     dword ptr [rsp+190h+P], eax
0x140150a7a  xor     r8d, r8d; int
0x140150a7d  lea     rax, [rsp+190h+P]
0x140150a82  xor     r9d, r9d; int
0x140150a85  mov     qword ptr [rsp+190h+CreateOptions], rax; Src
0x140150a8a  mov     ecx, 0C0003AA1h; int
0x140150a8f  mov     dword ptr [rsp+190h+Class], 4; Size
0x140150a97  call    UlWriteEventLogEntry
0x140150a9c  jmp     loc_140150CD6
0x140150aa1  lea     rax, [rsp+190h+var_130]
0x140150aa6  mov     [rsp+190h+ObjectAttributes.Length], 30h ; '0'
0x140150aae  mov     [rbp+90h+ObjectAttributes.ObjectName], rax
0x140150ab2  lea     r15, [r13+578h]
0x140150ab9  lea     rax, [rsp+190h+var_134]
0x140150abe  mov     [rsp+190h+ObjectAttributes.RootDirectory], rdi
0x140150ac3  mov     [rsp+190h+Disposition], rax; Disposition
0x140150ac8  lea     r8, [rsp+190h+ObjectAttributes]; ObjectAttributes
0x140150acd  mov     [rsp+190h+CreateOptions], edi; CreateOptions
0x140150ad1  xor     r9d, r9d; TitleIndex
0x140150ad4  mov     edx, 2001Fh; DesiredAccess
0x140150ad9  mov     [rsp+190h+Class], rdi; Class
0x140150ade  mov     rcx, r15; KeyHandle
0x140150ae1  mov     [rbp+90h+ObjectAttributes.Attributes], 240h
0x140150ae8  movdqu  xmmword ptr [rbp+90h+ObjectAttributes.SecurityDescriptor], xmm0
0x140150aed  call    cs:__imp_ZwCreateKey
0x140150af4  nop     dword ptr [rax+rax+00h]
0x140150af9  test    eax, eax
0x140150afb  jns     short loc_140150B2B
0x140150afd  mov     dword ptr [rsp+190h+P], eax
0x140150b01  xor     r8d, r8d; int
0x140150b04  lea     rax, [rsp+190h+P]
0x140150b09  xor     r9d, r9d; int
0x140150b0c  mov     qword ptr [rsp+190h+CreateOptions], rax; Src
0x140150b11  mov     ecx, 0C0003AA1h; int
0x140150b16  mov     dword ptr [rsp+190h+Class], 4; Size
0x140150b1e  call    UlWriteEventLogEntry
0x140150b23  mov     [r15], rdi
0x140150b26  jmp     loc_140150CD6
0x140150b2b  cmp     [rsp+190h+var_134], 1
0x140150b30  jz      loc_140150CD6
0x140150b36  mov     r14d, 1
0x140150b3c  mov     [rsp+190h+ResultLength], edi
0x140150b40  xorps   xmm0, xmm0
0x140150b43  lea     rbx, [rbp+90h+KeyValueInformation]
0x140150b47  xor     eax, eax
0x140150b49  mov     esi, edi
0x140150b4b  movups  [rbp+90h+KeyValueInformation], xmm0
0x140150b4f  lea     r12d, [r14+17h]
0x140150b53  mov     [rbp+90h+var_50], rax
0x140150b57  mov     rcx, [r15]; KeyHandle
0x140150b5a  lea     rax, [rsp+190h+ResultLength]
0x140150b5f  mov     qword ptr [rsp+190h+CreateOptions], rax; ResultLength
0x140150b64  mov     r9, rbx; KeyValueInformation
0x140150b67  mov     r8d, 1; KeyValueInformationClass
0x140150b6d  mov     dword ptr [rsp+190h+Class], r12d; Length
0x140150b72  mov     edx, esi; Index
0x140150b74  call    cs:__imp_ZwEnumerateValueKey
0x140150b7b  nop     dword ptr [rax+rax+00h]
0x140150b80  test    eax, eax
0x140150b82  jnz     loc_140150C1C
0x140150b88  xor     edx, edx; Val
0x140150b8a  mov     [rsp+190h+P], rdi
0x140150b8f  mov     r8d, 88h; Size
0x140150b95  lea     rcx, [rbp+90h+var_F0]; void *
0x140150b99  call    memset
0x140150b9e  lea     r9, [rbp+90h+var_F0]
0x140150ba2  mov     rdx, rbx
0x140150ba5  lea     r8, [rsp+190h+P]
0x140150baa  mov     rcx, r13
0x140150bad  call    UlpValidateUrlSdPair
0x140150bb2  test    eax, eax
0x140150bb4  js      short loc_140150BFC
0x140150bb6  mov     r8d, [rbx+8]
0x140150bba  lea     rdx, [rbp+90h+var_F0]
0x140150bbe  mov     [rsp+190h+var_150], dil
0x140150bc3  add     r8, rbx
0x140150bc6  mov     [rsp+190h+var_158], rdi
0x140150bcb  mov     rcx, r13
0x140150bce  mov     byte ptr [rsp+190h+Disposition], dil
0x140150bd3  mov     [rsp+190h+CreateOptions], edi
0x140150bd7  mov     [rsp+190h+Class], rdi
0x140150bdc  call    UlpAddReservationEntry
0x140150be1  mov     rcx, [rsp+190h+P]; P
0x140150be6  xor     edx, edx; Tag
0x140150be8  mov     edi, eax
0x140150bea  call    cs:__imp_ExFreePoolWithTag
0x140150bf1  nop     dword ptr [rax+rax+00h]
0x140150bf6  test    edi, edi
0x140150bf8  jns     short loc_140150C13
0x140150bfa  jmp     short loc_140150C01
0x140150bfc  mov     edi, 0C000014Ch
0x140150c01  test    r14d, r14d
0x140150c04  jz      short loc_140150C13
0x140150c06  xor     r14d, r14d
0x140150c09  mov     edx, edi
0x140150c0b  mov     rcx, rbx
0x140150c0e  call    UlpLogSpecificInitFailure
0x140150c13  inc     esi
0x140150c15  xor     edi, edi
0x140150c17  jmp     loc_140150B57
0x140150c1c  cmp     eax, 8000001Ah
0x140150c21  jz      loc_140150CB7
0x140150c27  cmp     eax, 80000005h
0x140150c2c  jnz     short loc_140150C91
0x140150c2e  mov     eax, [rsp+190h+ResultLength]
0x140150c32  lea     rcx, [rbp+90h+KeyValueInformation]
0x140150c36  mov     r12d, eax
0x140150c39  cmp     rbx, rcx
0x140150c3c  jz      short loc_140150C53
0x140150c3e  xor     edx, edx; Tag
0x140150c40  mov     rcx, rbx; P
0x140150c43  call    cs:__imp_ExFreePoolWithTag
0x140150c4a  nop     dword ptr [rax+rax+00h]
0x140150c4f  mov     eax, [rsp+190h+ResultLength]
0x140150c53  mov     edx, eax
0x140150c55  lea     r9, UxLowPriorityPool
0x140150c5c  mov     ecx, 100h
0x140150c61  mov     dword ptr [rsp+190h+Class], 1
0x140150c69  mov     r8d, 44526C55h
0x140150c6f  call    cs:__imp_ExAllocatePool3
0x140150c76  nop     dword ptr [rax+rax+00h]
0x140150c7b  mov     rbx, rax
0x140150c7e  test    rax, rax
0x140150c81  jnz     loc_140150B57
0x140150c87  mov     dword ptr [rsp+190h+P], 0C000009Ah
0x140150c8f  jmp     short loc_140150C95
0x140150c91  mov     dword ptr [rsp+190h+P], eax
0x140150c95  lea     rax, [rsp+190h+P]
0x140150c9a  xor     r9d, r9d; int
0x140150c9d  mov     qword ptr [rsp+190h+CreateOptions], rax; Src
0x140150ca2  xor     r8d, r8d; int
0x140150ca5  mov     ecx, 0C0003AA1h; int
0x140150caa  mov     dword ptr [rsp+190h+Class], 4; Size
0x140150cb2  call    UlWriteEventLogEntry
0x140150cb7  lea     rax, [rbp+90h+KeyValueInformation]
0x140150cbb  cmp     rbx, rax
0x140150cbe  jz      short loc_140150CD6
0x140150cc0  test    rbx, rbx
0x140150cc3  jz      short loc_140150CD6
0x140150cc5  xor     edx, edx; Tag
0x140150cc7  mov     rcx, rbx; P
0x140150cca  call    cs:__imp_ExFreePoolWithTag
0x140150cd1  nop     dword ptr [rax+rax+00h]
0x140150cd6  mov     rcx, [rbp+90h+var_48]
0x140150cda  xor     rcx, rsp; StackCookie
0x140150cdd  call    __security_check_cookie
0x140150ce2  add     rsp, 158h
0x140150ce9  pop     r15
0x140150ceb  pop     r14
0x140150ced  pop     r13
0x140150cef  pop     r12
0x140150cf1  pop     rdi
0x140150cf2  pop     rsi
0x140150cf3  pop     rbx
0x140150cf4  pop     rbp
0x140150cf5  retn
```
