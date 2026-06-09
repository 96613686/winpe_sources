# ContainerProvider::RegistrySymlinkCreationFailure<ushort const *,ushort const *,long,int,ushort const (&)[43]>(ushort const * &&,ushort const * &&,long &&,int &&,ushort const (&)[43])

- ea: `0x180027f20`
- end: `0x180028053`
- name: `??$RegistrySymlinkCreationFailure@PEBGPEBGJHAEAY0CL@$$CBG@ContainerProvider@@SAX$$QEAPEBG0$$QEAJ$$QEAHAEAY0CL@$$CBG@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18002abc0`

## callees

- `0x180001e10`
- `0x180002ad0`
- `0x18000895c`
- `0x180027f20`

## string_xrefs

- `0x180027f6c`: `NtCreateKey failed during symlink creation`

## pseudocode

```c
int __fastcall ContainerProvider::RegistrySymlinkCreationFailure<unsigned short const *,unsigned short const *,long,int,unsigned short const (&)[43]>(
        const WCHAR **a1,
        const WCHAR **a2,
        int *a3,
        int *a4)
{
  const struct _tlgProvider_t *v8; // rax
  int v9; // r11d
  __int64 v10; // rbx
  int v11; // r9d
  int v12; // r8d
  const WCHAR *v13; // rdx
  __int64 v14; // rax
  const WCHAR *v15; // r8
  __int64 v16; // rcx
  int v17; // ecx
  int v19; // [rsp+30h] [rbp-71h] BYREF
  int v20; // [rsp+34h] [rbp-6Dh] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+40h] [rbp-61h] BYREF
  const WCHAR *v22; // [rsp+60h] [rbp-41h]
  int v23; // [rsp+68h] [rbp-39h]
  int v24; // [rsp+6Ch] [rbp-35h]
  const WCHAR *v25; // [rsp+70h] [rbp-31h]
  int v26; // [rsp+78h] [rbp-29h]
  int v27; // [rsp+7Ch] [rbp-25h]
  int *v28; // [rsp+80h] [rbp-21h]
  __int64 v29; // [rsp+88h] [rbp-19h]
  int *v30; // [rsp+90h] [rbp-11h]
  __int64 v31; // [rsp+98h] [rbp-9h]
  const wchar_t *v32; // [rsp+A0h] [rbp-1h]
  __int64 v33; // [rsp+A8h] [rbp+7h]

  v8 = ContainerProvider::Provider();
  v9 = 2;
  v10 = (__int64)v8;
  if ( *(_DWORD *)v8 > 2u )
  {
    v11 = *a4;
    v12 = *a3;
    v13 = *a1;
    v32 = L"NtCreateKey failed during symlink creation";
    v30 = &v19;
    v28 = &v20;
    v14 = -1;
    v19 = v11;
    v20 = v12;
    v15 = *a2;
    v33 = 86;
    v31 = 4;
    v29 = 4;
    if ( v15 )
    {
      v16 = -1;
      do
        ++v16;
      while ( v15[v16] );
      v17 = 2 * v16 + 2;
    }
    else
    {
      v15 = &pwszBaseUri;
      v17 = 2;
    }
    v25 = v15;
    v26 = v17;
    v27 = 0;
    if ( v13 )
    {
      do
        ++v14;
      while ( v13[v14] );
      v9 = 2 * v14 + 2;
    }
    else
    {
      v13 = &pwszBaseUri;
    }
    v22 = v13;
    v23 = v9;
    v24 = 0;
    LODWORD(v8) = tlgWriteTransfer_EventWriteTransfer(v10, (unsigned __int8 *)&word_18003CB36, 0, 0, 7u, &v21);
  }
  return (int)v8;
}

```

## disassembly

```asm
0x180027f20  push    rbp
0x180027f22  push    rbx
0x180027f23  push    rsi
0x180027f24  push    rdi
0x180027f25  push    r14
0x180027f27  push    r15
0x180027f29  lea     rbp, [rsp-27h]
0x180027f2e  sub     rsp, 0C8h
0x180027f35  mov     rax, cs:__security_cookie
0x180027f3c  xor     rax, rsp
0x180027f3f  mov     [rbp+4Fh+var_40], rax
0x180027f43  mov     rdi, r9
0x180027f46  mov     rsi, r8
0x180027f49  mov     r14, rdx
0x180027f4c  mov     r15, rcx
0x180027f4f  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180027f54  mov     r11d, 2
0x180027f5a  mov     rbx, rax
0x180027f5d  mov     r10d, [rax]
0x180027f60  cmp     r10d, r11d
0x180027f63  jbe     loc_180028036
0x180027f69  mov     r9d, [rdi]
0x180027f6c  lea     rax, aNtcreatekeyFai; "NtCreateKey failed during symlink creat"...
0x180027f73  mov     r8d, [rsi]
0x180027f76  mov     rdx, [r15]
0x180027f79  mov     [rbp+4Fh+var_50], rax
0x180027f7d  lea     rax, [rbp+4Fh+var_C0]
0x180027f81  mov     [rbp+4Fh+var_60], rax
0x180027f85  lea     rax, [rbp+4Fh+var_BC]
0x180027f89  mov     [rbp+4Fh+var_70], rax
0x180027f8d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027f91  mov     [rbp+4Fh+var_C0], r9d
0x180027f95  xor     r9d, r9d
0x180027f98  mov     [rbp+4Fh+var_BC], r8d
0x180027f9c  mov     r8, [r14]
0x180027f9f  mov     [rbp+4Fh+var_48], 56h ; 'V'
0x180027fa7  mov     [rbp+4Fh+var_58], 4
0x180027faf  mov     [rbp+4Fh+var_68], 4
0x180027fb7  test    r8, r8
0x180027fba  jz      short loc_180027FD2
0x180027fbc  mov     rcx, rax
0x180027fbf  inc     rcx
0x180027fc2  cmp     [r8+rcx*2], r9w
0x180027fc7  jnz     short loc_180027FBF
0x180027fc9  lea     ecx, ds:2[rcx*2]
0x180027fd0  jmp     short loc_180027FDC
0x180027fd2  lea     r8, pwszBaseUri
0x180027fd9  mov     ecx, r11d
0x180027fdc  mov     [rbp+4Fh+var_80], r8
0x180027fe0  mov     [rbp+4Fh+var_78], ecx
0x180027fe3  mov     [rbp+4Fh+var_74], r9d
0x180027fe7  test    rdx, rdx
0x180027fea  jz      short loc_180028000
0x180027fec  inc     rax
0x180027fef  cmp     [rdx+rax*2], r9w
0x180027ff4  jnz     short loc_180027FEC
0x180027ff6  lea     r11d, ds:2[rax*2]
0x180027ffe  jmp     short loc_180028007
0x180028000  lea     rdx, pwszBaseUri
0x180028007  lea     rax, [rbp+4Fh+var_B0]
0x18002800b  mov     [rbp+4Fh+var_90], rdx
0x18002800f  mov     [rsp+0F0h+var_C8], rax
0x180028014  lea     rdx, word_18003CB36
0x18002801b  xor     r8d, r8d
0x18002801e  mov     [rsp+0F0h+var_D0], 7
0x180028026  mov     rcx, rbx
0x180028029  mov     [rbp+4Fh+var_88], r11d
0x18002802d  mov     [rbp+4Fh+var_84], r9d
0x180028031  call    _tlgWriteTransfer_EventWriteTransfer
0x180028036  mov     rcx, [rbp+4Fh+var_40]
0x18002803a  xor     rcx, rsp; StackCookie
0x18002803d  call    __security_check_cookie
0x180028042  add     rsp, 0C8h
0x180028049  pop     r15
0x18002804b  pop     r14
0x18002804d  pop     rdi
0x18002804e  pop     rsi
0x18002804f  pop     rbx
0x180028050  pop     rbp
0x180028051  retn
```
