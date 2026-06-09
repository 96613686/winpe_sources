# CipGetRegistryValue

- ea: `0x18005abe8`
- end: `0x18005afca`
- name: `CipGetRegistryValue`
- size: `994`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800651d4`
- `0x1800739d0`
- `0x180073acc`
- `0x180073e38`
- `0x18007406c`
- `0x1800744f8`
- `0x1800746f0`
- `0x180075cec`
- `0x1800e2be0`

## callees

- `0x18002bf20`
- `0x18002c380`
- `0x18005abe8`
- `0x180072ab4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18005acd2`
- `ntoskrnl!ExAllocatePool2` at `0x18005acd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005af91`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005af91`
- `ntoskrnl!ZwClose` at `0x18005aead`
- `ntoskrnl!ZwClose` at `0x18005af78`
- `ntoskrnl!ZwClose` at `0x18005aead`
- `ntoskrnl!ZwClose` at `0x18005af78`
- `ntoskrnl!ZwOpenKey` at `0x18005adc3`
- `ntoskrnl!ZwOpenKey` at `0x18005af2f`
- `ntoskrnl!ZwOpenKey` at `0x18005adc3`
- `ntoskrnl!ZwOpenKey` at `0x18005af2f`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18005acb0`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18005ad12`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18005acb0`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x18005ad12`

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
0x18005abe8  mov     [rsp-8+arg_18], rbx
0x18005abed  push    rbp
0x18005abee  push    rsi
0x18005abef  push    rdi
0x18005abf0  push    r12
0x18005abf2  push    r13
0x18005abf4  push    r14
0x18005abf6  push    r15
0x18005abf8  lea     rbp, [rsp-1C0h]
0x18005ac00  sub     rsp, 2C0h
0x18005ac07  mov     rax, cs:__security_cookie
0x18005ac0e  xor     rax, rsp
0x18005ac11  mov     [rbp+1F0h+var_40], rax
0x18005ac18  mov     rax, [rbp+1F0h+arg_20]
0x18005ac1f  xorps   xmm0, xmm0
0x18005ac22  mov     [rsp+2F0h+var_288], rax
0x18005ac27  mov     r13, r8
0x18005ac2a  mov     rax, [rbp+1F0h+arg_30]
0x18005ac31  mov     rsi, rdx
0x18005ac34  mov     [rsp+2F0h+var_290], rax
0x18005ac39  mov     rbx, rcx
0x18005ac3c  xor     eax, eax
0x18005ac3e  lea     rcx, [rbp+1F0h+var_250]; void *
0x18005ac42  xor     edx, edx; Val
0x18005ac44  mov     [rsp+2F0h+var_2B0], eax
0x18005ac48  mov     r8d, 20Ah; Size
0x18005ac4e  mov     [rsp+2F0h+KeyHandle], rax
0x18005ac53  mov     r12d, eax
0x18005ac56  mov     edi, r9d
0x18005ac59  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm0
0x18005ac5e  movups  xmmword ptr [rbp+1F0h+ObjectAttributes.ObjectName], xmm0
0x18005ac62  movups  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005ac66  movups  [rsp+2F0h+var_2A0], xmm0
0x18005ac6b  call    memset
0x18005ac70  xor     edx, edx
0x18005ac72  lea     r8d, [r12+2]
0x18005ac77  mov     r15d, 7FFFh
0x18005ac7d  mov     r14d, 0FFFEh
0x18005ac83  test    rbx, rbx
0x18005ac86  jz      loc_18005ADF1
0x18005ac8c  lea     rax, [rsp+2F0h+var_2B0]
0x18005ac91  xor     r9d, r9d
0x18005ac94  mov     [rsp+2F0h+var_2C0], rax
0x18005ac99  mov     r8, rsi
0x18005ac9c  lea     rax, [rbp+1F0h+var_250]
0x18005aca0  mov     dword ptr [rsp+2F0h+var_2C8], 20Ah
0x18005aca8  mov     rcx, rbx
0x18005acab  mov     [rsp+2F0h+var_2D0], rax
0x18005acb0  call    cs:__imp_RtlGetPersistedStateLocation
0x18005acb7  nop     dword ptr [rax+rax+00h]
0x18005acbc  cmp     eax, 80000005h
0x18005acc1  jnz     short loc_18005AD2D
0x18005acc3  mov     edx, [rsp+2F0h+var_2B0]
0x18005acc7  mov     ecx, 102h
0x18005accc  mov     r8d, 63734943h
0x18005acd2  call    cs:__imp_ExAllocatePool2
0x18005acd9  nop     dword ptr [rax+rax+00h]
0x18005acde  mov     r12, rax
0x18005ace1  test    rax, rax
0x18005ace4  jnz     short loc_18005ACF0
0x18005ace6  mov     ebx, 0C0000017h
0x18005aceb  jmp     loc_18005AF6E
0x18005acf0  mov     eax, [rsp+2F0h+var_2B0]
0x18005acf4  lea     rcx, [rsp+2F0h+var_2B0]
0x18005acf9  mov     [rsp+2F0h+var_2C0], rcx
0x18005acfe  xor     r9d, r9d
0x18005ad01  mov     dword ptr [rsp+2F0h+var_2C8], eax
0x18005ad05  mov     rcx, rbx
0x18005ad08  mov     r8, rsi
0x18005ad0b  mov     [rsp+2F0h+var_2D0], r12
0x18005ad10  xor     edx, edx
0x18005ad12  call    cs:__imp_RtlGetPersistedStateLocation
0x18005ad19  nop     dword ptr [rax+rax+00h]
0x18005ad1e  mov     ebx, eax
0x18005ad20  test    eax, eax
0x18005ad22  js      loc_18005AF6E
0x18005ad28  mov     rdx, r12
0x18005ad2b  jmp     short loc_18005AD31
0x18005ad2d  lea     rdx, [rbp+1F0h+var_250]
0x18005ad31  xor     ebx, ebx
0x18005ad33  xorps   xmm0, xmm0
0x18005ad36  movups  [rsp+2F0h+var_2A0], xmm0
0x18005ad3b  test    rdx, rdx
0x18005ad3e  jz      short loc_18005AD8D
0x18005ad40  mov     rcx, r15
0x18005ad43  lea     r8d, [rbx+2]
0x18005ad47  mov     rax, rdx
0x18005ad4a  cmp     [rax], bx
0x18005ad4d  jz      short loc_18005AD58
0x18005ad4f  add     rax, r8
0x18005ad52  sub     rcx, 1
0x18005ad56  jnz     short loc_18005AD4A
0x18005ad58  mov     rax, rcx
0x18005ad5b  neg     rax
0x18005ad5e  sbb     ebx, ebx
0x18005ad60  not     ebx
0x18005ad62  and     ebx, 0C000000Dh
0x18005ad68  test    rcx, rcx
0x18005ad6b  jz      loc_18005AF6E
0x18005ad71  add     cx, cx
0x18005ad74  mov     qword ptr [rsp+2F0h+var_2A0+8], rdx
0x18005ad79  mov     eax, r14d
0x18005ad7c  sub     ax, cx
0x18005ad7f  mov     word ptr [rsp+2F0h+var_2A0], ax
0x18005ad84  add     ax, r8w
0x18005ad88  mov     word ptr [rsp+2F0h+var_2A0+2], ax
0x18005ad8d  xor     edx, edx
0x18005ad8f  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rdx
0x18005ad94  lea     rax, [rsp+2F0h+var_2A0]
0x18005ad99  xorps   xmm0, xmm0
0x18005ad9c  mov     [rbp+1F0h+ObjectAttributes.ObjectName], rax
0x18005ada0  mov     edx, 20019h; DesiredAccess
0x18005ada5  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x18005adad  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x18005adb2  mov     [rbp+1F0h+ObjectAttributes.Attributes], 240h
0x18005adb9  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18005adbe  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005adc3  call    cs:__imp_ZwOpenKey
0x18005adca  nop     dword ptr [rax+rax+00h]
0x18005adcf  mov     ebx, eax
0x18005add1  test    eax, eax
0x18005add3  js      loc_18005AF6E
0x18005add9  test    edi, edi
0x18005addb  jz      short loc_18005AE3B
0x18005addd  sub     edi, 1
0x18005ade0  jz      short loc_18005AE34
0x18005ade2  cmp     edi, 1
0x18005ade5  jz      short loc_18005AE2D
0x18005ade7  mov     ebx, 0C0000002h
0x18005adec  jmp     loc_18005AF6E
0x18005adf1  test    rsi, rsi
0x18005adf4  jz      short loc_18005AD8F
0x18005adf6  mov     rcx, r15
0x18005adf9  mov     rax, rsi
0x18005adfc  cmp     [rax], dx
0x18005adff  jz      short loc_18005AE0C
0x18005ae01  add     rax, r8
0x18005ae04  sub     rcx, 1
0x18005ae08  jnz     short loc_18005ADFC
0x18005ae0a  jmp     short loc_18005AD8F
0x18005ae0c  add     cx, cx
0x18005ae0f  mov     qword ptr [rsp+2F0h+var_2A0+8], rsi
0x18005ae14  mov     eax, r14d
0x18005ae17  sub     ax, cx
0x18005ae1a  mov     word ptr [rsp+2F0h+var_2A0], ax
0x18005ae1f  add     ax, r8w
0x18005ae23  mov     word ptr [rsp+2F0h+var_2A0+2], ax
0x18005ae28  jmp     loc_18005AD8F
0x18005ae2d  mov     edi, 1
0x18005ae32  jmp     short loc_18005AE40
0x18005ae34  mov     edi, 3
0x18005ae39  jmp     short loc_18005AE40
0x18005ae3b  mov     edi, 4
0x18005ae40  mov     rax, [rsp+2F0h+var_290]
0x18005ae45  mov     r8d, edi
0x18005ae48  mov     r9d, [rbp+1F0h+arg_28]
0x18005ae4f  mov     rdx, r13
0x18005ae52  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18005ae57  mov     [rsp+2F0h+var_2C8], rax; __int64
0x18005ae5c  mov     rax, [rsp+2F0h+var_288]
0x18005ae61  mov     [rsp+2F0h+var_2D0], rax; __int64
0x18005ae66  call    CipGetRegistryValueInternal
0x18005ae6b  mov     ebx, eax
0x18005ae6d  cmp     eax, 0C0000034h
0x18005ae72  jnz     loc_18005AF6E
0x18005ae78  test    rsi, rsi
0x18005ae7b  jz      loc_18005AF6E
0x18005ae81  mov     rax, qword ptr [rsp+2F0h+var_2A0+8]
0x18005ae86  mov     r8, rsi
0x18005ae89  sub     r8, rax
0x18005ae8c  movzx   edx, word ptr [rax]
0x18005ae8f  movzx   ecx, word ptr [rax+r8]
0x18005ae94  sub     edx, ecx
0x18005ae96  jnz     short loc_18005AEA0
0x18005ae98  add     rax, 2
0x18005ae9c  test    ecx, ecx
0x18005ae9e  jnz     short loc_18005AE8C
0x18005aea0  test    edx, edx
0x18005aea2  jz      loc_18005AF6E
0x18005aea8  mov     rcx, [rsp+2F0h+KeyHandle]; Handle
0x18005aead  call    cs:__imp_ZwClose
0x18005aeb4  nop     dword ptr [rax+rax+00h]
0x18005aeb9  xor     ecx, ecx
0x18005aebb  xorps   xmm0, xmm0
0x18005aebe  mov     [rsp+2F0h+KeyHandle], rcx
0x18005aec3  mov     rax, rsi
0x18005aec6  movups  [rsp+2F0h+var_2A0], xmm0
0x18005aecb  lea     edx, [rcx+2]
0x18005aece  cmp     [rax], cx
0x18005aed1  jz      short loc_18005AEDE
0x18005aed3  add     rax, rdx
0x18005aed6  sub     r15, 1
0x18005aeda  jnz     short loc_18005AECE
0x18005aedc  jmp     short loc_18005AEFB
0x18005aede  add     r15w, r15w
0x18005aee2  mov     qword ptr [rsp+2F0h+var_2A0+8], rsi
0x18005aee7  sub     r14w, r15w
0x18005aeeb  mov     word ptr [rsp+2F0h+var_2A0], r14w
0x18005aef1  add     r14w, dx
0x18005aef5  mov     word ptr [rsp+2F0h+var_2A0+2], r14w
0x18005aefb  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rcx
0x18005af00  lea     rax, [rsp+2F0h+var_2A0]
0x18005af05  xorps   xmm0, xmm0
0x18005af08  mov     [rbp+1F0h+ObjectAttributes.ObjectName], rax
0x18005af0c  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18005af11  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x18005af19  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x18005af1e  mov     [rbp+1F0h+ObjectAttributes.Attributes], 240h
0x18005af25  mov     edx, 20019h; DesiredAccess
0x18005af2a  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005af2f  call    cs:__imp_ZwOpenKey
0x18005af36  nop     dword ptr [rax+rax+00h]
0x18005af3b  mov     ebx, eax
0x18005af3d  test    eax, eax
0x18005af3f  js      short loc_18005AF6E
0x18005af41  mov     rax, [rsp+2F0h+var_290]
0x18005af46  mov     r8d, edi
0x18005af49  mov     r9d, [rbp+1F0h+arg_28]
0x18005af50  mov     rdx, r13
0x18005af53  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18005af58  mov     [rsp+2F0h+var_2C8], rax; __int64
0x18005af5d  mov     rax, [rsp+2F0h+var_288]
0x18005af62  mov     [rsp+2F0h+var_2D0], rax; __int64
0x18005af67  call    CipGetRegistryValueInternal
0x18005af6c  mov     ebx, eax
0x18005af6e  mov     rcx, [rsp+2F0h+KeyHandle]; Handle
0x18005af73  test    rcx, rcx
0x18005af76  jz      short loc_18005AF84
0x18005af78  call    cs:__imp_ZwClose
0x18005af7f  nop     dword ptr [rax+rax+00h]
0x18005af84  test    r12, r12
0x18005af87  jz      short loc_18005AF9D
0x18005af89  mov     edx, 63734943h; Tag
0x18005af8e  mov     rcx, r12; P
0x18005af91  call    cs:__imp_ExFreePoolWithTag
0x18005af98  nop     dword ptr [rax+rax+00h]
0x18005af9d  mov     eax, ebx
0x18005af9f  mov     rcx, [rbp+1F0h+var_40]
0x18005afa6  xor     rcx, rsp; StackCookie
0x18005afa9  call    __security_check_cookie
0x18005afae  mov     rbx, [rsp+2F0h+arg_18]
0x18005afb6  add     rsp, 2C0h
0x18005afbd  pop     r15
0x18005afbf  pop     r14
0x18005afc1  pop     r13
0x18005afc3  pop     r12
0x18005afc5  pop     rdi
0x18005afc6  pop     rsi
0x18005afc7  pop     rbp
0x18005afc8  retn
```
