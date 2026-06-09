# CipGetRegistryValue

- ea: `0x180059ed0`
- end: `0x18005a2b2`
- name: `CipGetRegistryValue`
- size: `994`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800648e0`
- `0x180072720`
- `0x18007281c`
- `0x180072b88`
- `0x180072dbc`
- `0x180073248`
- `0x180073440`
- `0x180074730`
- `0x1800e1bf0`

## callees

- `0x18002bef0`
- `0x18002c340`
- `0x180059ed0`
- `0x180071804`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180059fba`
- `ntoskrnl!ExAllocatePool2` at `0x180059fba`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005a279`
- `ntoskrnl!ExFreePoolWithTag` at `0x18005a279`
- `ntoskrnl!ZwClose` at `0x18005a195`
- `ntoskrnl!ZwClose` at `0x18005a260`
- `ntoskrnl!ZwClose` at `0x18005a195`
- `ntoskrnl!ZwClose` at `0x18005a260`
- `ntoskrnl!ZwOpenKey` at `0x18005a0ab`
- `ntoskrnl!ZwOpenKey` at `0x18005a217`
- `ntoskrnl!ZwOpenKey` at `0x18005a0ab`
- `ntoskrnl!ZwOpenKey` at `0x18005a217`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180059f98`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180059ffa`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180059f98`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x180059ffa`

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
0x180059ed0  mov     [rsp-8+arg_18], rbx
0x180059ed5  push    rbp
0x180059ed6  push    rsi
0x180059ed7  push    rdi
0x180059ed8  push    r12
0x180059eda  push    r13
0x180059edc  push    r14
0x180059ede  push    r15
0x180059ee0  lea     rbp, [rsp-1C0h]
0x180059ee8  sub     rsp, 2C0h
0x180059eef  mov     rax, cs:__security_cookie
0x180059ef6  xor     rax, rsp
0x180059ef9  mov     [rbp+1F0h+var_40], rax
0x180059f00  mov     rax, [rbp+1F0h+arg_20]
0x180059f07  xorps   xmm0, xmm0
0x180059f0a  mov     [rsp+2F0h+var_288], rax
0x180059f0f  mov     r13, r8
0x180059f12  mov     rax, [rbp+1F0h+arg_30]
0x180059f19  mov     rsi, rdx
0x180059f1c  mov     [rsp+2F0h+var_290], rax
0x180059f21  mov     rbx, rcx
0x180059f24  xor     eax, eax
0x180059f26  lea     rcx, [rbp+1F0h+var_250]; void *
0x180059f2a  xor     edx, edx; Val
0x180059f2c  mov     [rsp+2F0h+var_2B0], eax
0x180059f30  mov     r8d, 20Ah; Size
0x180059f36  mov     [rsp+2F0h+KeyHandle], rax
0x180059f3b  mov     r12d, eax
0x180059f3e  mov     edi, r9d
0x180059f41  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm0
0x180059f46  movups  xmmword ptr [rbp+1F0h+ObjectAttributes.ObjectName], xmm0
0x180059f4a  movups  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180059f4e  movups  [rsp+2F0h+var_2A0], xmm0
0x180059f53  call    memset
0x180059f58  xor     edx, edx
0x180059f5a  lea     r8d, [r12+2]
0x180059f5f  mov     r15d, 7FFFh
0x180059f65  mov     r14d, 0FFFEh
0x180059f6b  test    rbx, rbx
0x180059f6e  jz      loc_18005A0D9
0x180059f74  lea     rax, [rsp+2F0h+var_2B0]
0x180059f79  xor     r9d, r9d
0x180059f7c  mov     [rsp+2F0h+var_2C0], rax
0x180059f81  mov     r8, rsi
0x180059f84  lea     rax, [rbp+1F0h+var_250]
0x180059f88  mov     dword ptr [rsp+2F0h+var_2C8], 20Ah
0x180059f90  mov     rcx, rbx
0x180059f93  mov     [rsp+2F0h+var_2D0], rax
0x180059f98  call    cs:__imp_RtlGetPersistedStateLocation
0x180059f9f  nop     dword ptr [rax+rax+00h]
0x180059fa4  cmp     eax, 80000005h
0x180059fa9  jnz     short loc_18005A015
0x180059fab  mov     edx, [rsp+2F0h+var_2B0]
0x180059faf  mov     ecx, 102h
0x180059fb4  mov     r8d, 63734943h
0x180059fba  call    cs:__imp_ExAllocatePool2
0x180059fc1  nop     dword ptr [rax+rax+00h]
0x180059fc6  mov     r12, rax
0x180059fc9  test    rax, rax
0x180059fcc  jnz     short loc_180059FD8
0x180059fce  mov     ebx, 0C0000017h
0x180059fd3  jmp     loc_18005A256
0x180059fd8  mov     eax, [rsp+2F0h+var_2B0]
0x180059fdc  lea     rcx, [rsp+2F0h+var_2B0]
0x180059fe1  mov     [rsp+2F0h+var_2C0], rcx
0x180059fe6  xor     r9d, r9d
0x180059fe9  mov     dword ptr [rsp+2F0h+var_2C8], eax
0x180059fed  mov     rcx, rbx
0x180059ff0  mov     r8, rsi
0x180059ff3  mov     [rsp+2F0h+var_2D0], r12
0x180059ff8  xor     edx, edx
0x180059ffa  call    cs:__imp_RtlGetPersistedStateLocation
0x18005a001  nop     dword ptr [rax+rax+00h]
0x18005a006  mov     ebx, eax
0x18005a008  test    eax, eax
0x18005a00a  js      loc_18005A256
0x18005a010  mov     rdx, r12
0x18005a013  jmp     short loc_18005A019
0x18005a015  lea     rdx, [rbp+1F0h+var_250]
0x18005a019  xor     ebx, ebx
0x18005a01b  xorps   xmm0, xmm0
0x18005a01e  movups  [rsp+2F0h+var_2A0], xmm0
0x18005a023  test    rdx, rdx
0x18005a026  jz      short loc_18005A075
0x18005a028  mov     rcx, r15
0x18005a02b  lea     r8d, [rbx+2]
0x18005a02f  mov     rax, rdx
0x18005a032  cmp     [rax], bx
0x18005a035  jz      short loc_18005A040
0x18005a037  add     rax, r8
0x18005a03a  sub     rcx, 1
0x18005a03e  jnz     short loc_18005A032
0x18005a040  mov     rax, rcx
0x18005a043  neg     rax
0x18005a046  sbb     ebx, ebx
0x18005a048  not     ebx
0x18005a04a  and     ebx, 0C000000Dh
0x18005a050  test    rcx, rcx
0x18005a053  jz      loc_18005A256
0x18005a059  add     cx, cx
0x18005a05c  mov     qword ptr [rsp+2F0h+var_2A0+8], rdx
0x18005a061  mov     eax, r14d
0x18005a064  sub     ax, cx
0x18005a067  mov     word ptr [rsp+2F0h+var_2A0], ax
0x18005a06c  add     ax, r8w
0x18005a070  mov     word ptr [rsp+2F0h+var_2A0+2], ax
0x18005a075  xor     edx, edx
0x18005a077  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rdx
0x18005a07c  lea     rax, [rsp+2F0h+var_2A0]
0x18005a081  xorps   xmm0, xmm0
0x18005a084  mov     [rbp+1F0h+ObjectAttributes.ObjectName], rax
0x18005a088  mov     edx, 20019h; DesiredAccess
0x18005a08d  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x18005a095  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x18005a09a  mov     [rbp+1F0h+ObjectAttributes.Attributes], 240h
0x18005a0a1  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18005a0a6  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005a0ab  call    cs:__imp_ZwOpenKey
0x18005a0b2  nop     dword ptr [rax+rax+00h]
0x18005a0b7  mov     ebx, eax
0x18005a0b9  test    eax, eax
0x18005a0bb  js      loc_18005A256
0x18005a0c1  test    edi, edi
0x18005a0c3  jz      short loc_18005A123
0x18005a0c5  sub     edi, 1
0x18005a0c8  jz      short loc_18005A11C
0x18005a0ca  cmp     edi, 1
0x18005a0cd  jz      short loc_18005A115
0x18005a0cf  mov     ebx, 0C0000002h
0x18005a0d4  jmp     loc_18005A256
0x18005a0d9  test    rsi, rsi
0x18005a0dc  jz      short loc_18005A077
0x18005a0de  mov     rcx, r15
0x18005a0e1  mov     rax, rsi
0x18005a0e4  cmp     [rax], dx
0x18005a0e7  jz      short loc_18005A0F4
0x18005a0e9  add     rax, r8
0x18005a0ec  sub     rcx, 1
0x18005a0f0  jnz     short loc_18005A0E4
0x18005a0f2  jmp     short loc_18005A077
0x18005a0f4  add     cx, cx
0x18005a0f7  mov     qword ptr [rsp+2F0h+var_2A0+8], rsi
0x18005a0fc  mov     eax, r14d
0x18005a0ff  sub     ax, cx
0x18005a102  mov     word ptr [rsp+2F0h+var_2A0], ax
0x18005a107  add     ax, r8w
0x18005a10b  mov     word ptr [rsp+2F0h+var_2A0+2], ax
0x18005a110  jmp     loc_18005A077
0x18005a115  mov     edi, 1
0x18005a11a  jmp     short loc_18005A128
0x18005a11c  mov     edi, 3
0x18005a121  jmp     short loc_18005A128
0x18005a123  mov     edi, 4
0x18005a128  mov     rax, [rsp+2F0h+var_290]
0x18005a12d  mov     r8d, edi
0x18005a130  mov     r9d, [rbp+1F0h+arg_28]
0x18005a137  mov     rdx, r13
0x18005a13a  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18005a13f  mov     [rsp+2F0h+var_2C8], rax; __int64
0x18005a144  mov     rax, [rsp+2F0h+var_288]
0x18005a149  mov     [rsp+2F0h+var_2D0], rax; __int64
0x18005a14e  call    CipGetRegistryValueInternal
0x18005a153  mov     ebx, eax
0x18005a155  cmp     eax, 0C0000034h
0x18005a15a  jnz     loc_18005A256
0x18005a160  test    rsi, rsi
0x18005a163  jz      loc_18005A256
0x18005a169  mov     rax, qword ptr [rsp+2F0h+var_2A0+8]
0x18005a16e  mov     r8, rsi
0x18005a171  sub     r8, rax
0x18005a174  movzx   edx, word ptr [rax]
0x18005a177  movzx   ecx, word ptr [rax+r8]
0x18005a17c  sub     edx, ecx
0x18005a17e  jnz     short loc_18005A188
0x18005a180  add     rax, 2
0x18005a184  test    ecx, ecx
0x18005a186  jnz     short loc_18005A174
0x18005a188  test    edx, edx
0x18005a18a  jz      loc_18005A256
0x18005a190  mov     rcx, [rsp+2F0h+KeyHandle]; Handle
0x18005a195  call    cs:__imp_ZwClose
0x18005a19c  nop     dword ptr [rax+rax+00h]
0x18005a1a1  xor     ecx, ecx
0x18005a1a3  xorps   xmm0, xmm0
0x18005a1a6  mov     [rsp+2F0h+KeyHandle], rcx
0x18005a1ab  mov     rax, rsi
0x18005a1ae  movups  [rsp+2F0h+var_2A0], xmm0
0x18005a1b3  lea     edx, [rcx+2]
0x18005a1b6  cmp     [rax], cx
0x18005a1b9  jz      short loc_18005A1C6
0x18005a1bb  add     rax, rdx
0x18005a1be  sub     r15, 1
0x18005a1c2  jnz     short loc_18005A1B6
0x18005a1c4  jmp     short loc_18005A1E3
0x18005a1c6  add     r15w, r15w
0x18005a1ca  mov     qword ptr [rsp+2F0h+var_2A0+8], rsi
0x18005a1cf  sub     r14w, r15w
0x18005a1d3  mov     word ptr [rsp+2F0h+var_2A0], r14w
0x18005a1d9  add     r14w, dx
0x18005a1dd  mov     word ptr [rsp+2F0h+var_2A0+2], r14w
0x18005a1e3  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rcx
0x18005a1e8  lea     rax, [rsp+2F0h+var_2A0]
0x18005a1ed  xorps   xmm0, xmm0
0x18005a1f0  mov     [rbp+1F0h+ObjectAttributes.ObjectName], rax
0x18005a1f4  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18005a1f9  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x18005a201  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x18005a206  mov     [rbp+1F0h+ObjectAttributes.Attributes], 240h
0x18005a20d  mov     edx, 20019h; DesiredAccess
0x18005a212  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005a217  call    cs:__imp_ZwOpenKey
0x18005a21e  nop     dword ptr [rax+rax+00h]
0x18005a223  mov     ebx, eax
0x18005a225  test    eax, eax
0x18005a227  js      short loc_18005A256
0x18005a229  mov     rax, [rsp+2F0h+var_290]
0x18005a22e  mov     r8d, edi
0x18005a231  mov     r9d, [rbp+1F0h+arg_28]
0x18005a238  mov     rdx, r13
0x18005a23b  mov     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x18005a240  mov     [rsp+2F0h+var_2C8], rax; __int64
0x18005a245  mov     rax, [rsp+2F0h+var_288]
0x18005a24a  mov     [rsp+2F0h+var_2D0], rax; __int64
0x18005a24f  call    CipGetRegistryValueInternal
0x18005a254  mov     ebx, eax
0x18005a256  mov     rcx, [rsp+2F0h+KeyHandle]; Handle
0x18005a25b  test    rcx, rcx
0x18005a25e  jz      short loc_18005A26C
0x18005a260  call    cs:__imp_ZwClose
0x18005a267  nop     dword ptr [rax+rax+00h]
0x18005a26c  test    r12, r12
0x18005a26f  jz      short loc_18005A285
0x18005a271  mov     edx, 63734943h; Tag
0x18005a276  mov     rcx, r12; P
0x18005a279  call    cs:__imp_ExFreePoolWithTag
0x18005a280  nop     dword ptr [rax+rax+00h]
0x18005a285  mov     eax, ebx
0x18005a287  mov     rcx, [rbp+1F0h+var_40]
0x18005a28e  xor     rcx, rsp; StackCookie
0x18005a291  call    __security_check_cookie
0x18005a296  mov     rbx, [rsp+2F0h+arg_18]
0x18005a29e  add     rsp, 2C0h
0x18005a2a5  pop     r15
0x18005a2a7  pop     r14
0x18005a2a9  pop     r13
0x18005a2ab  pop     r12
0x18005a2ad  pop     rdi
0x18005a2ae  pop     rsi
0x18005a2af  pop     rbp
0x18005a2b0  retn
```
