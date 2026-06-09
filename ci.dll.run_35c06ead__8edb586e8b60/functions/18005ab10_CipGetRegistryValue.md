# CipGetRegistryValue

- ea: `0x18005ab10`
- end: `0x18005aef2`
- name: `CipGetRegistryValue`
- size: `994`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180065344`
- `0x180073cb0`
- `0x180073dac`
- `0x180074118`
- `0x18007434c`
- `0x1800747d8`
- `0x1800749d0`
- `0x180075fcc`
- `0x1800e2bb0`

## callees

- `0x18002c0d0`
- `0x18002c500`
- `0x18005ab10`
- `0x180072d94`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18005abfa`
- `ntoskrnl!ExAllocatePool2` at `0x18005abfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005aeb9`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005aeb9`
- `ntoskrnl!ZwClose` at `0x18005add5`
- `ntoskrnl!ZwClose` at `0x18005aea0`
- `ntoskrnl!ZwClose` at `0x18005add5`
- `ntoskrnl!ZwClose` at `0x18005aea0`
- `ntoskrnl!ZwOpenKey` at `0x18005aceb`
- `ntoskrnl!ZwOpenKey` at `0x18005ae57`
- `ntoskrnl!ZwOpenKey` at `0x18005aceb`
- `ntoskrnl!ZwOpenKey` at `0x18005ae57`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18005abd8`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18005ac3a`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18005abd8`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18005ac3a`

## pseudocode

```c
__int64 __fastcall CipGetRegistryValue(__int64 a1, _WORD *a2, __int64 a3, int a4, __int64 a5, int a6, __int64 a7)
{
  _BYTE *Pool2; // r12
  __int64 v11; // r15
  NTSTATUS RegistryValueInternal; // ebx
  _BYTE *v13; // rdx
  __int64 v14; // rcx
  _WORD *v15; // rax
  __int64 v16; // rcx
  _WORD *v17; // rax
  unsigned __int16 *v18; // rax
  int v19; // ecx
  int v20; // edx
  _WORD *v21; // rax
  __int16 v22; // r15
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h]
  __int64 v28; // [rsp+68h] [rbp-98h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v30[528]; // [rsp+A0h] [rbp-60h] BYREF

  v28 = a5;
  v27 = a7;
  v24 = 0;
  KeyHandle = 0;
  Pool2 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v26 = 0;
  memset(v30, 0, 0x20Au);
  v11 = 0x7FFF;
  if ( !a1 )
  {
    if ( a2 )
    {
      v16 = 0x7FFF;
      v17 = a2;
      while ( *v17 )
      {
        ++v17;
        if ( !--v16 )
          goto LABEL_14;
      }
      *((_QWORD *)&v26 + 1) = a2;
      LOWORD(v26) = -2 - 2 * v16;
      WORD1(v26) = -2 * v16;
    }
LABEL_14:
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v26;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    RegistryValueInternal = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( RegistryValueInternal >= 0 )
    {
      if ( a4 && (unsigned int)(a4 - 1) >= 2 )
      {
        RegistryValueInternal = -1073741822;
      }
      else
      {
        RegistryValueInternal = CipGetRegistryValueInternal(KeyHandle, v28, v27);
        if ( RegistryValueInternal == -1073741772 && a2 )
        {
          v18 = (unsigned __int16 *)*((_QWORD *)&v26 + 1);
          do
          {
            v19 = *(unsigned __int16 *)((char *)a2 + (_QWORD)v18 - *((_QWORD *)&v26 + 1));
            v20 = *v18 - v19;
            if ( v20 )
              break;
            ++v18;
          }
          while ( v19 );
          if ( v20 )
          {
            ZwClose(KeyHandle);
            KeyHandle = 0;
            v21 = a2;
            v26 = 0;
            while ( *v21 )
            {
              ++v21;
              if ( !--v11 )
                goto LABEL_35;
            }
            v22 = 2 * v11;
            *((_QWORD *)&v26 + 1) = a2;
            LOWORD(v26) = -2 - v22;
            WORD1(v26) = -v22;
LABEL_35:
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.ObjectName = (PUNICODE_STRING)&v26;
            ObjectAttributes.Length = 48;
            ObjectAttributes.Attributes = 576;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            RegistryValueInternal = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
            if ( RegistryValueInternal >= 0 )
              RegistryValueInternal = CipGetRegistryValueInternal(KeyHandle, v28, v27);
          }
        }
      }
    }
    goto LABEL_37;
  }
  if ( (unsigned int)RtlGetPersistedStateLocation(a1, 0, a2, 0, v30, 522, &v24) != -2147483643 )
  {
    v13 = v30;
LABEL_8:
    v26 = 0;
    if ( v13 )
    {
      v14 = 0x7FFF;
      v15 = v13;
      do
      {
        if ( !*v15 )
          break;
        ++v15;
        --v14;
      }
      while ( v14 );
      RegistryValueInternal = v14 == 0 ? 0xC000000D : 0;
      if ( !v14 )
        goto LABEL_37;
      *((_QWORD *)&v26 + 1) = v13;
      LOWORD(v26) = -2 - 2 * v14;
      WORD1(v26) = -2 * v14;
    }
    goto LABEL_14;
  }
  Pool2 = (_BYTE *)ExAllocatePool2(258, v24, 1668499779);
  if ( !Pool2 )
  {
    RegistryValueInternal = -1073741801;
    goto LABEL_37;
  }
  RegistryValueInternal = RtlGetPersistedStateLocation(a1, 0, a2, 0, Pool2, v24, &v24);
  if ( RegistryValueInternal >= 0 )
  {
    v13 = Pool2;
    goto LABEL_8;
  }
LABEL_37:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x63734943u);
  return (unsigned int)RegistryValueInternal;
}

```

## disassembly

```asm
0x18005ab10  mov     [rsp-8+arg_18], rbx
0x18005ab15  push    rbp
0x18005ab16  push    rsi
0x18005ab17  push    rdi
0x18005ab18  push    r12
0x18005ab1a  push    r13
0x18005ab1c  push    r14
0x18005ab1e  push    r15
0x18005ab20  lea     rbp, [rsp-1C0h]
0x18005ab28  sub     rsp, 2C0h
0x18005ab2f  mov     rax, cs:__security_cookie
0x18005ab36  xor     rax, rsp
0x18005ab39  mov     [rbp+1F0h+var_40], rax
0x18005ab40  mov     rax, [rbp+1F0h+arg_20]
0x18005ab47  xorps   xmm0, xmm0
0x18005ab4a  mov     [rsp+2F0h+var_288], rax
0x18005ab4f  mov     r13, r8
0x18005ab52  mov     rax, [rbp+1F0h+arg_30]
0x18005ab59  mov     rsi, rdx
0x18005ab5c  mov     [rsp+2F0h+var_290], rax
0x18005ab61  mov     rbx, rcx
0x18005ab64  xor     eax, eax
0x18005ab66  lea     rcx, [rbp+1F0h+var_250]; void *
0x18005ab6a  xor     edx, edx; Val
0x18005ab6c  mov     [rsp+2F0h+var_2B0], eax
0x18005ab70  mov     r8d, 20Ah; Size
0x18005ab76  mov     [rsp+2F0h+KeyHandle], rax
0x18005ab7b  mov     r12d, eax
0x18005ab7e  mov     edi, r9d
0x18005ab81  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm0
0x18005ab86  movups  xmmword ptr [rbp+1F0h+ObjectAttributes.ObjectName], xmm0
0x18005ab8a  movups  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005ab8e  movups  [rsp+2F0h+var_2A0], xmm0
0x18005ab93  call    memset
0x18005ab98  xor     edx, edx
0x18005ab9a  lea     r8d, [r12+2]
0x18005ab9f  mov     r15d, 7FFFh
0x18005aba5  mov     r14d, 0FFFEh
0x18005abab  test    rbx, rbx
0x18005abae  jz      loc_18005AD19
0x18005abb4  lea     rax, [rsp+2F0h+var_2B0]
0x18005abb9  xor     r9d, r9d
0x18005abbc  mov     [rsp+2F0h+var_2C0], rax
0x18005abc1  mov     r8, rsi
0x18005abc4  lea     rax, [rbp+1F0h+var_250]
0x18005abc8  mov     dword ptr [rsp+2F0h+var_2C8], 20Ah
0x18005abd0  mov     rcx, rbx
0x18005abd3  mov     [rsp+2F0h+var_2D0], rax
0x18005abd8  call    cs:__imp_RtlGetPersistedStateLocation
0x18005abdf  nop     dword ptr [rax+rax+00h]
0x18005abe4  cmp     eax, 80000005h
0x18005abe9  jnz     short loc_18005AC55
0x18005abeb  mov     edx, [rsp+2F0h+var_2B0]
0x18005abef  mov     ecx, 102h
0x18005abf4  mov     r8d, 63734943h
0x18005abfa  call    cs:__imp_ExAllocatePool2
0x18005ac01  nop     dword ptr [rax+rax+00h]
0x18005ac06  mov     r12, rax
0x18005ac09  test    rax, rax
0x18005ac0c  jnz     short loc_18005AC18
0x18005ac0e  mov     ebx, 0C0000017h
0x18005ac13  jmp     loc_18005AE96
0x18005ac18  mov     eax, [rsp+2F0h+var_2B0]
0x18005ac1c  lea     rcx, [rsp+2F0h+var_2B0]
0x18005ac21  mov     [rsp+2F0h+var_2C0], rcx
0x18005ac26  xor     r9d, r9d
0x18005ac29  mov     dword ptr [rsp+2F0h+var_2C8], eax
0x18005ac2d  mov     rcx, rbx
0x18005ac30  mov     r8, rsi
0x18005ac33  mov     [rsp+2F0h+var_2D0], r12
0x18005ac38  xor     edx, edx
0x18005ac3a  call    cs:__imp_RtlGetPersistedStateLocation
0x18005ac41  nop     dword ptr [rax+rax+00h]
0x18005ac46  mov     ebx, eax
0x18005ac48  test    eax, eax
0x18005ac4a  js      loc_18005AE96
0x18005ac50  mov     rdx, r12
0x18005ac53  jmp     short loc_18005AC59
0x18005ac55  lea     rdx, [rbp+1F0h+var_250]
0x18005ac59  xor     ebx, ebx
0x18005ac5b  xorps   xmm0, xmm0
0x18005ac5e  movups  [rsp+2F0h+var_2A0], xmm0
0x18005ac63  test    rdx, rdx
0x18005ac66  jz      short loc_18005ACB5
0x18005ac68  mov     rcx, r15
0x18005ac6b  lea     r8d, [rbx+2]
0x18005ac6f  mov     rax, rdx
0x18005ac72  cmp     [rax], bx
0x18005ac75  jz      short loc_18005AC80
0x18005ac77  add     rax, r8
0x18005ac7a  sub     rcx, 1
0x18005ac7e  jnz     short loc_18005AC72
0x18005ac80  mov     rax, rcx
0x18005ac83  neg     rax
0x18005ac86  sbb     ebx, ebx
0x18005ac88  not     ebx
0x18005ac8a  and     ebx, 0C000000Dh
0x18005ac90  test    rcx, rcx
0x18005ac93  jz      loc_18005AE96
0x18005ac99  add     cx, cx
0x18005ac9c  mov     qword ptr [rsp+2F0h+var_2A0+8], rdx
0x18005aca1  mov     eax, r14d
0x18005aca4  sub     ax, cx
0x18005aca7  mov     word ptr [rsp+2F0h+var_2A0], ax
0x18005acac  add     ax, r8w
0x18005acb0  mov     word ptr [rsp+2F0h+var_2A0+2], ax
0x18005acb5  xor     edx, edx
0x18005acb7  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rdx
0x18005acbc  lea     rax, [rsp+2F0h+var_2A0]
0x18005acc1  xorps   xmm0, xmm0
0x18005acc4  mov     [rbp+1F0h+ObjectAttributes.ObjectName], rax
0x18005acc8  mov     edx, 20019h; DesiredAccess
0x18005accd  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x18005acd5  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x18005acda  mov     [rbp+1F0h+ObjectAttributes.Attributes], 240h
0x18005ace1  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18005ace6  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005aceb  call    cs:__imp_ZwOpenKey
0x18005acf2  nop     dword ptr [rax+rax+00h]
0x18005acf7  mov     ebx, eax
0x18005acf9  test    eax, eax
0x18005acfb  js      loc_18005AE96
0x18005ad01  test    edi, edi
0x18005ad03  jz      short loc_18005AD63
0x18005ad05  sub     edi, 1
0x18005ad08  jz      short loc_18005AD5C
0x18005ad0a  cmp     edi, 1
0x18005ad0d  jz      short loc_18005AD55
0x18005ad0f  mov     ebx, 0C0000002h
0x18005ad14  jmp     loc_18005AE96
0x18005ad19  test    rsi, rsi
0x18005ad1c  jz      short loc_18005ACB7
0x18005ad1e  mov     rcx, r15
0x18005ad21  mov     rax, rsi
0x18005ad24  cmp     [rax], dx
0x18005ad27  jz      short loc_18005AD34
0x18005ad29  add     rax, r8
0x18005ad2c  sub     rcx, 1
0x18005ad30  jnz     short loc_18005AD24
0x18005ad32  jmp     short loc_18005ACB7
0x18005ad34  add     cx, cx
0x18005ad37  mov     qword ptr [rsp+2F0h+var_2A0+8], rsi
0x18005ad3c  mov     eax, r14d
0x18005ad3f  sub     ax, cx
0x18005ad42  mov     word ptr [rsp+2F0h+var_2A0], ax
0x18005ad47  add     ax, r8w
0x18005ad4b  mov     word ptr [rsp+2F0h+var_2A0+2], ax
0x18005ad50  jmp     loc_18005ACB7
0x18005ad55  mov     edi, 1
0x18005ad5a  jmp     short loc_18005AD68
0x18005ad5c  mov     edi, 3
0x18005ad61  jmp     short loc_18005AD68
0x18005ad63  mov     edi, 4
0x18005ad68  mov     rax, [rsp+2F0h+var_290]
0x18005ad6d  mov     r8d, edi
0x18005ad70  mov     r9d, [rbp+1F0h+arg_28]
0x18005ad77  mov     rdx, r13
0x18005ad7a  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18005ad7f  mov     [rsp+2F0h+var_2C8], rax; __int64
0x18005ad84  mov     rax, [rsp+2F0h+var_288]
0x18005ad89  mov     [rsp+2F0h+var_2D0], rax; __int64
0x18005ad8e  call    CipGetRegistryValueInternal
0x18005ad93  mov     ebx, eax
0x18005ad95  cmp     eax, 0C0000034h
0x18005ad9a  jnz     loc_18005AE96
0x18005ada0  test    rsi, rsi
0x18005ada3  jz      loc_18005AE96
0x18005ada9  mov     rax, qword ptr [rsp+2F0h+var_2A0+8]
0x18005adae  mov     r8, rsi
0x18005adb1  sub     r8, rax
0x18005adb4  movzx   edx, word ptr [rax]
0x18005adb7  movzx   ecx, word ptr [rax+r8]
0x18005adbc  sub     edx, ecx
0x18005adbe  jnz     short loc_18005ADC8
0x18005adc0  add     rax, 2
0x18005adc4  test    ecx, ecx
0x18005adc6  jnz     short loc_18005ADB4
0x18005adc8  test    edx, edx
0x18005adca  jz      loc_18005AE96
0x18005add0  mov     rcx, [rsp+2F0h+KeyHandle]; Handle
0x18005add5  call    cs:__imp_ZwClose
0x18005addc  nop     dword ptr [rax+rax+00h]
0x18005ade1  xor     ecx, ecx
0x18005ade3  xorps   xmm0, xmm0
0x18005ade6  mov     [rsp+2F0h+KeyHandle], rcx
0x18005adeb  mov     rax, rsi
0x18005adee  movups  [rsp+2F0h+var_2A0], xmm0
0x18005adf3  lea     edx, [rcx+2]
0x18005adf6  cmp     [rax], cx
0x18005adf9  jz      short loc_18005AE06
0x18005adfb  add     rax, rdx
0x18005adfe  sub     r15, 1
0x18005ae02  jnz     short loc_18005ADF6
0x18005ae04  jmp     short loc_18005AE23
0x18005ae06  add     r15w, r15w
0x18005ae0a  mov     qword ptr [rsp+2F0h+var_2A0+8], rsi
0x18005ae0f  sub     r14w, r15w
0x18005ae13  mov     word ptr [rsp+2F0h+var_2A0], r14w
0x18005ae19  add     r14w, dx
0x18005ae1d  mov     word ptr [rsp+2F0h+var_2A0+2], r14w
0x18005ae23  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rcx
0x18005ae28  lea     rax, [rsp+2F0h+var_2A0]
0x18005ae2d  xorps   xmm0, xmm0
0x18005ae30  mov     [rbp+1F0h+ObjectAttributes.ObjectName], rax
0x18005ae34  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18005ae39  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x18005ae41  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x18005ae46  mov     [rbp+1F0h+ObjectAttributes.Attributes], 240h
0x18005ae4d  mov     edx, 20019h; DesiredAccess
0x18005ae52  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005ae57  call    cs:__imp_ZwOpenKey
0x18005ae5e  nop     dword ptr [rax+rax+00h]
0x18005ae63  mov     ebx, eax
0x18005ae65  test    eax, eax
0x18005ae67  js      short loc_18005AE96
0x18005ae69  mov     rax, [rsp+2F0h+var_290]
0x18005ae6e  mov     r8d, edi
0x18005ae71  mov     r9d, [rbp+1F0h+arg_28]
0x18005ae78  mov     rdx, r13
0x18005ae7b  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18005ae80  mov     [rsp+2F0h+var_2C8], rax; __int64
0x18005ae85  mov     rax, [rsp+2F0h+var_288]
0x18005ae8a  mov     [rsp+2F0h+var_2D0], rax; __int64
0x18005ae8f  call    CipGetRegistryValueInternal
0x18005ae94  mov     ebx, eax
0x18005ae96  mov     rcx, [rsp+2F0h+KeyHandle]; Handle
0x18005ae9b  test    rcx, rcx
0x18005ae9e  jz      short loc_18005AEAC
0x18005aea0  call    cs:__imp_ZwClose
0x18005aea7  nop     dword ptr [rax+rax+00h]
0x18005aeac  test    r12, r12
0x18005aeaf  jz      short loc_18005AEC5
0x18005aeb1  mov     edx, 63734943h; Tag
0x18005aeb6  mov     rcx, r12; P
0x18005aeb9  call    cs:__imp_ExFreePoolWithTag
0x18005aec0  nop     dword ptr [rax+rax+00h]
0x18005aec5  mov     eax, ebx
0x18005aec7  mov     rcx, [rbp+1F0h+var_40]
0x18005aece  xor     rcx, rsp; StackCookie
0x18005aed1  call    __security_check_cookie
0x18005aed6  mov     rbx, [rsp+2F0h+arg_18]
0x18005aede  add     rsp, 2C0h
0x18005aee5  pop     r15
0x18005aee7  pop     r14
0x18005aee9  pop     r13
0x18005aeeb  pop     r12
0x18005aeed  pop     rdi
0x18005aeee  pop     rsi
0x18005aeef  pop     rbp
0x18005aef0  retn
```
