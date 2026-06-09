# UlpPrepareSecurityDescriptor

- ea: `0x1c00da658`
- end: `0x1c00da79a`
- name: `UlpPrepareSecurityDescriptor`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c00da2b8`

## callees

- `0x1c00da658`
- `0x1c00da7a0`

## import_xrefs

- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1c00da6af`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1c00da723`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1c00da6af`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1c00da723`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x1c00da6c9`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x1c00da6c9`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1c00da6e1`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1c00da6e1`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1c00da6f9`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1c00da6f9`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1c00fe666`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1c00fe681`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1c00fe666`
- `ntoskrnl!SeReleaseSecurityDescriptor` at `0x1c00fe681`

## pseudocode

```c
__int64 __fastcall UlpPrepareSecurityDescriptor(__int64 a1, __int64 a2, _QWORD *a3, _QWORD *a4, ULONG *a5)
{
  ULONG *v5; // r14
  _QWORD *v6; // rdi
  char v8; // r12
  int v9; // ebx
  __int64 v10; // r8
  __int64 v11; // rdx
  ULONG v12; // r15d
  __int64 v13; // r9
  __int64 v14; // rax
  PSECURITY_DESCRIPTOR v15; // rax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp+30h] BYREF
  __int64 v18; // [rsp+70h] [rbp+40h] BYREF

  v5 = a5;
  v6 = a4;
  SecurityDescriptor = 0;
  v18 = 0;
  v8 = a2;
  *a3 = 0;
  *v5 = 0;
  *a4 = 0;
  if ( !a1 )
    return (unsigned int)-1073741811;
  LOBYTE(a4) = 1;
  v9 = SeCaptureSecurityDescriptor(a1, a2, 1, a4, &SecurityDescriptor);
  if ( v9 >= 0 )
  {
    if ( RtlValidSecurityDescriptor(SecurityDescriptor)
      && (v12 = RtlLengthSecurityDescriptor(SecurityDescriptor),
          RtlValidRelativeSecurityDescriptor(SecurityDescriptor, v12, 0)) )
    {
      LOBYTE(v13) = 1;
      v9 = SeCaptureSecurityDescriptor(SecurityDescriptor, 0, 1, v13, &v18);
      if ( v9 < 0 )
      {
        v18 = 0;
      }
      else
      {
        v9 = UlMapGenericMask(v18);
        if ( v9 >= 0 )
        {
          v14 = v18;
          v18 = 0;
          *a3 = v14;
          v15 = SecurityDescriptor;
          SecurityDescriptor = 0;
          *v6 = v15;
          *v5 = v12;
        }
      }
    }
    else
    {
      v9 = -1073741811;
    }
    if ( !SecurityDescriptor )
      goto LABEL_9;
    LOBYTE(v10) = 1;
    LOBYTE(v11) = v8;
    SeReleaseSecurityDescriptor(SecurityDescriptor, v11, v10);
  }
  SecurityDescriptor = 0;
LABEL_9:
  if ( v18 )
  {
    LOBYTE(v10) = 1;
    SeReleaseSecurityDescriptor(v18, 0, v10);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1c00da658  mov     [rsp-28h+arg_8], rbx
0x1c00da65d  mov     [rsp-28h+arg_18], rsi
0x1c00da662  push    rbp
0x1c00da663  push    rdi
0x1c00da664  push    r12
0x1c00da666  push    r14
0x1c00da668  push    r15
0x1c00da66a  mov     rbp, rsp
0x1c00da66d  sub     rsp, 30h
0x1c00da671  mov     r14, [rbp+arg_20]
0x1c00da675  mov     rdi, r9
0x1c00da678  and     [rbp+SecurityDescriptor], 0
0x1c00da67d  mov     rsi, r8
0x1c00da680  and     [rbp+arg_10], 0
0x1c00da685  mov     r12b, dl
0x1c00da688  and     qword ptr [r8], 0
0x1c00da68c  and     dword ptr [r14], 0
0x1c00da690  and     qword ptr [r9], 0
0x1c00da694  test    rcx, rcx
0x1c00da697  jz      loc_1C00FE64C
0x1c00da69d  lea     rax, [rbp+SecurityDescriptor]
0x1c00da6a1  mov     r9b, 1
0x1c00da6a4  mov     r8d, 1
0x1c00da6aa  mov     [rsp+30h+var_10], rax
0x1c00da6af  call    cs:__imp_SeCaptureSecurityDescriptor
0x1c00da6b6  nop     dword ptr [rax+rax+00h]
0x1c00da6bb  mov     ebx, eax
0x1c00da6bd  test    eax, eax
0x1c00da6bf  js      loc_1C00FE672
0x1c00da6c5  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1c00da6c9  call    cs:__imp_RtlValidSecurityDescriptor
0x1c00da6d0  nop     dword ptr [rax+rax+00h]
0x1c00da6d5  test    al, al
0x1c00da6d7  jz      loc_1C00FE656
0x1c00da6dd  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1c00da6e1  call    cs:__imp_RtlLengthSecurityDescriptor
0x1c00da6e8  nop     dword ptr [rax+rax+00h]
0x1c00da6ed  mov     rcx, [rbp+SecurityDescriptor]; SecurityDescriptorInput
0x1c00da6f1  xor     r8d, r8d; RequiredInformation
0x1c00da6f4  mov     edx, eax; SecurityDescriptorLength
0x1c00da6f6  mov     r15d, eax
0x1c00da6f9  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1c00da700  nop     dword ptr [rax+rax+00h]
0x1c00da705  test    al, al
0x1c00da707  jz      loc_1C00FE656
0x1c00da70d  mov     rcx, [rbp+SecurityDescriptor]
0x1c00da711  lea     rax, [rbp+arg_10]
0x1c00da715  xor     edx, edx
0x1c00da717  mov     [rsp+30h+var_10], rax
0x1c00da71c  mov     r9b, 1
0x1c00da71f  lea     r8d, [rdx+1]
0x1c00da723  call    cs:__imp_SeCaptureSecurityDescriptor
0x1c00da72a  nop     dword ptr [rax+rax+00h]
0x1c00da72f  mov     ebx, eax
0x1c00da731  test    eax, eax
0x1c00da733  js      short loc_1C00DA793
0x1c00da735  mov     rcx, [rbp+arg_10]
0x1c00da739  call    UlMapGenericMask
0x1c00da73e  mov     ebx, eax
0x1c00da740  test    eax, eax
0x1c00da742  js      short loc_1C00DA75F
0x1c00da744  mov     rax, [rbp+arg_10]
0x1c00da748  and     [rbp+arg_10], 0
0x1c00da74d  mov     [rsi], rax
0x1c00da750  mov     rax, [rbp+SecurityDescriptor]
0x1c00da754  and     [rbp+SecurityDescriptor], 0
0x1c00da759  mov     [rdi], rax
0x1c00da75c  mov     [r14], r15d
0x1c00da75f  mov     rcx, [rbp+SecurityDescriptor]
0x1c00da763  test    rcx, rcx
0x1c00da766  jnz     loc_1C00FE660
0x1c00da76c  mov     rcx, [rbp+arg_10]
0x1c00da770  test    rcx, rcx
0x1c00da773  jnz     loc_1C00FE67C
0x1c00da779  mov     rsi, [rsp+30h+arg_18]
0x1c00da77e  mov     eax, ebx
0x1c00da780  mov     rbx, [rsp+30h+arg_8]
0x1c00da785  add     rsp, 30h
0x1c00da789  pop     r15
0x1c00da78b  pop     r14
0x1c00da78d  pop     r12
0x1c00da78f  pop     rdi
0x1c00da790  pop     rbp
0x1c00da791  retn
0x1c00da793  and     [rbp+arg_10], 0
0x1c00da798  jmp     short loc_1C00DA75F
0x1c00fe64c  mov     ebx, 0C000000Dh
0x1c00fe651  jmp     loc_1C00DA779
0x1c00fe656  mov     ebx, 0C000000Dh
0x1c00fe65b  jmp     loc_1C00DA75F
0x1c00fe660  mov     r8b, 1
0x1c00fe663  mov     dl, r12b
0x1c00fe666  call    cs:__imp_SeReleaseSecurityDescriptor
0x1c00fe66d  nop     dword ptr [rax+rax+00h]
0x1c00fe672  and     [rbp+SecurityDescriptor], 0
0x1c00fe677  jmp     loc_1C00DA76C
0x1c00fe67c  mov     r8b, 1
0x1c00fe67f  xor     edx, edx
0x1c00fe681  call    cs:__imp_SeReleaseSecurityDescriptor
0x1c00fe688  nop     dword ptr [rax+rax+00h]
0x1c00fe68d  nop
0x1c00fe68e  jmp     loc_1C00DA779
```
