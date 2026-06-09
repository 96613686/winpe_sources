# CxPlatStorageOpen

- ea: `0x140033bfc`
- end: `0x140033e2a`
- name: `CxPlatStorageOpen`
- size: `558`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140023f20`
- `0x1400258c0`

## callees

- `0x140033a6c`
- `0x140033bfc`
- `0x14003ce00`
- `0x14003e928`
- `0x14003ed00`

## import_xrefs

- `ntoskrnl!ExInitializePushLock` at `0x140033cf9`
- `ntoskrnl!ExInitializePushLock` at `0x140033cf9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033dd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033dff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033dd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033dff`
- `ntoskrnl!ZwClose` at `0x140033deb`
- `ntoskrnl!ZwClose` at `0x140033deb`
- `ntoskrnl!ZwNotifyChangeKey` at `0x140033d98`
- `ntoskrnl!ZwNotifyChangeKey` at `0x140033d98`
- `ntoskrnl!ZwOpenKey` at `0x140033d32`
- `ntoskrnl!ZwOpenKey` at `0x140033d32`
- `ntoskrnl!ExAllocatePool2` at `0x140033cb2`
- `ntoskrnl!ExAllocatePool2` at `0x140033cb2`

## string_xrefs

- `0x140033c57`: `CxPlatStorageCreateAppKey failed`
- `0x140033d4d`: `ZwOpenKey failed`

## pseudocode

```c
__int64 __fastcall CxPlatStorageOpen(const CHAR *a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  __int128 v5; // xmm0
  char *v6; // rbx
  int AppKey; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // edi
  char *Pool2; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  NTSTATUS v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  const char *v19; // r9
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF

  v5 = 0;
  v6 = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( a1 )
  {
    AppKey = CxPlatStorageCreateAppKey(a1);
    v12 = AppKey;
    if ( AppKey < 0 )
    {
      if ( (Microsoft_QuicEnableBits & 4) != 0 )
        McTemplateU0qs_EtwWriteTransfer(v11, v10, (unsigned int)AppKey, "CxPlatStorageCreateAppKey failed");
      goto LABEL_23;
    }
    v5 = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = 0;
  }
  else
  {
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&BaseKeyPath;
  }
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = v5;
  Pool2 = (char *)ExAllocatePool2(66, 88, 1144152913);
  v6 = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 0x58u);
    ExInitializePushLock((PULONG_PTR)v6 + 1);
    if ( a2 )
    {
      *((_QWORD *)v6 + 3) = 0;
      *((_QWORD *)v6 + 5) = CxPlatStorageRegKeyChangeCallback;
      *((_QWORD *)v6 + 9) = a2;
      *((_QWORD *)v6 + 10) = a3;
      *((_QWORD *)v6 + 6) = v6;
    }
    v16 = ZwOpenKey((PHANDLE)v6, 0x20019u, &ObjectAttributes);
    v12 = v16;
    if ( v16 >= 0 )
    {
      if ( !a2
        || (v16 = ZwNotifyChangeKey(
                    *(HANDLE *)v6,
                    0,
                    (PIO_APC_ROUTINE)(v6 + 24),
                    (PVOID)1,
                    (PIO_STATUS_BLOCK)(v6 + 56),
                    4u,
                    0,
                    0,
                    0,
                    1u),
            v12 = v16,
            v16 >= 0) )
      {
        *a5 = v6;
        v6 = 0;
        goto LABEL_23;
      }
      if ( (Microsoft_QuicEnableBits & 4) == 0 )
        goto LABEL_23;
      v19 = "ZwNotifyChangeKey failed";
    }
    else
    {
      if ( (Microsoft_QuicEnableBits & 4) == 0 )
        goto LABEL_23;
      v19 = "ZwOpenKey failed";
    }
    McTemplateU0qs_EtwWriteTransfer(v18, v17, (unsigned int)v16, v19);
    goto LABEL_23;
  }
  if ( (Microsoft_QuicEnableBits & 2) != 0 )
    McTemplateU0sx_EtwWriteTransfer(v15, v14, "CXPLAT_STORAGE", 88);
  v12 = -1073741801;
LABEL_23:
  if ( v6 )
  {
    if ( *(_QWORD *)v6 )
      ZwClose(*(HANDLE *)v6);
    ExFreePoolWithTag(v6, 0x44326351u);
  }
  return v12;
}

```

## disassembly

```asm
0x140033bfc  mov     [rsp-28h+arg_8], rbx
0x140033c01  mov     [rsp-28h+arg_10], rsi
0x140033c06  push    rbp
0x140033c07  push    rdi
0x140033c08  push    r12
0x140033c0a  push    r14
0x140033c0c  push    r15
0x140033c0e  mov     rbp, rsp
0x140033c11  sub     rsp, 80h
0x140033c18  xor     eax, eax
0x140033c1a  xor     esi, esi
0x140033c1c  xorps   xmm0, xmm0
0x140033c1f  mov     [rbp+ObjectAttributes.SecurityDescriptor], rax
0x140033c23  xor     ebx, ebx
0x140033c25  mov     dword ptr [rbp+ObjectAttributes.SecurityQualityOfService], eax
0x140033c28  mov     [rbp+P], rsi
0x140033c2c  mov     r12, r8
0x140033c2f  mov     r15, rdx
0x140033c32  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140033c36  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140033c3a  test    rcx, rcx
0x140033c3d  jz      short loc_140033C80
0x140033c3f  lea     rdx, [rbp+P]
0x140033c43  call    CxPlatStorageCreateAppKey
0x140033c48  mov     edi, eax
0x140033c4a  test    eax, eax
0x140033c4c  jns     short loc_140033C6F
0x140033c4e  test    cs:Microsoft_QuicEnableBits, 4
0x140033c55  jz      short loc_140033C66
0x140033c57  lea     r9, aCxplatstoragec; "CxPlatStorageCreateAppKey failed"
0x140033c5e  mov     r8d, eax
0x140033c61  call    McTemplateU0qs_EtwWriteTransfer
0x140033c66  mov     rsi, [rbp+P]
0x140033c6a  jmp     loc_140033DC5
0x140033c6f  mov     rsi, [rbp+P]
0x140033c73  xorps   xmm0, xmm0
0x140033c76  and     [rbp+ObjectAttributes.RootDirectory], rbx
0x140033c7a  mov     [rbp+ObjectAttributes.ObjectName], rsi
0x140033c7e  jmp     short loc_140033C8F
0x140033c80  and     [rbp+ObjectAttributes.RootDirectory], rax
0x140033c84  lea     rax, BaseKeyPath
0x140033c8b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140033c8f  mov     edi, 58h ; 'X'
0x140033c94  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140033c9b  mov     r8d, 44326351h
0x140033ca1  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140033ca8  mov     edx, edi
0x140033caa  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140033caf  lea     ecx, [rdi-16h]
0x140033cb2  call    cs:__imp_ExAllocatePool2
0x140033cb9  nop     dword ptr [rax+rax+00h]
0x140033cbe  mov     rbx, rax
0x140033cc1  test    rax, rax
0x140033cc4  jnz     short loc_140033CE8
0x140033cc6  test    cs:Microsoft_QuicEnableBits, 2
0x140033ccd  jz      short loc_140033CDE
0x140033ccf  mov     r9d, edi
0x140033cd2  lea     r8, aCxplatStorage; "CXPLAT_STORAGE"
0x140033cd9  call    McTemplateU0sx_EtwWriteTransfer
0x140033cde  mov     edi, 0C0000017h
0x140033ce3  jmp     loc_140033DC5
0x140033ce8  mov     r8, rdi; Size
0x140033ceb  xor     edx, edx; Val
0x140033ced  mov     rcx, rbx; void *
0x140033cf0  call    memset
0x140033cf5  lea     rcx, [rbx+8]; PushLock
0x140033cf9  call    cs:__imp_ExInitializePushLock
0x140033d00  nop     dword ptr [rax+rax+00h]
0x140033d05  test    r15, r15
0x140033d08  jz      short loc_140033D26
0x140033d0a  and     qword ptr [rbx+18h], 0
0x140033d0f  lea     rax, CxPlatStorageRegKeyChangeCallback
0x140033d16  mov     [rbx+28h], rax
0x140033d1a  mov     [rbx+48h], r15
0x140033d1e  mov     [rbx+50h], r12
0x140033d22  mov     [rbx+30h], rbx
0x140033d26  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140033d2a  mov     edx, 20019h; DesiredAccess
0x140033d2f  mov     rcx, rbx; KeyHandle
0x140033d32  call    cs:__imp_ZwOpenKey
0x140033d39  nop     dword ptr [rax+rax+00h]
0x140033d3e  mov     edi, eax
0x140033d40  test    eax, eax
0x140033d42  jns     short loc_140033D5E
0x140033d44  test    cs:Microsoft_QuicEnableBits, 4
0x140033d4b  jz      short loc_140033DC5
0x140033d4d  lea     r9, aZwopenkeyFaile; "ZwOpenKey failed"
0x140033d54  mov     r8d, eax
0x140033d57  call    McTemplateU0qs_EtwWriteTransfer
0x140033d5c  jmp     short loc_140033DC5
0x140033d5e  test    r15, r15
0x140033d61  jz      short loc_140033DBC
0x140033d63  mov     rcx, [rbx]; KeyHandle
0x140033d66  lea     rax, [rbx+38h]
0x140033d6a  mov     [rsp+80h+Asynchronous], 1; Asynchronous
0x140033d6f  lea     r8, [rbx+18h]; ApcRoutine
0x140033d73  and     [rsp+80h+var_40], 0
0x140033d78  mov     r9d, 1; ApcContext
0x140033d7e  and     [rsp+80h+var_48], 0
0x140033d84  xor     edx, edx; Event
0x140033d86  mov     [rsp+80h+WatchTree], 0; WatchTree
0x140033d8b  mov     [rsp+80h+CompletionFilter], 4; CompletionFilter
0x140033d93  mov     [rsp+80h+IoStatusBlock], rax; IoStatusBlock
0x140033d98  call    cs:__imp_ZwNotifyChangeKey
0x140033d9f  nop     dword ptr [rax+rax+00h]
0x140033da4  mov     edi, eax
0x140033da6  test    eax, eax
0x140033da8  jns     short loc_140033DBC
0x140033daa  test    cs:Microsoft_QuicEnableBits, 4
0x140033db1  jz      short loc_140033DC5
0x140033db3  lea     r9, aZwnotifychange; "ZwNotifyChangeKey failed"
0x140033dba  jmp     short loc_140033D54
0x140033dbc  mov     rax, [rbp+arg_20]
0x140033dc0  mov     [rax], rbx
0x140033dc3  xor     ebx, ebx
0x140033dc5  test    rsi, rsi
0x140033dc8  jz      short loc_140033DDE
0x140033dca  mov     edx, 38326351h; Tag
0x140033dcf  mov     rcx, rsi; P
0x140033dd2  call    cs:__imp_ExFreePoolWithTag
0x140033dd9  nop     dword ptr [rax+rax+00h]
0x140033dde  test    rbx, rbx
0x140033de1  jz      short loc_140033E0B
0x140033de3  mov     rcx, [rbx]; Handle
0x140033de6  test    rcx, rcx
0x140033de9  jz      short loc_140033DF7
0x140033deb  call    cs:__imp_ZwClose
0x140033df2  nop     dword ptr [rax+rax+00h]
0x140033df7  mov     edx, 44326351h; Tag
0x140033dfc  mov     rcx, rbx; P
0x140033dff  call    cs:__imp_ExFreePoolWithTag
0x140033e06  nop     dword ptr [rax+rax+00h]
0x140033e0b  lea     r11, [rsp+80h+var_s0]
0x140033e13  mov     eax, edi
0x140033e15  mov     rbx, [r11+38h]
0x140033e19  mov     rsi, [r11+40h]
0x140033e1d  mov     rsp, r11
0x140033e20  pop     r15
0x140033e22  pop     r14
0x140033e24  pop     r12
0x140033e26  pop     rdi
0x140033e27  pop     rbp
0x140033e28  retn
```
