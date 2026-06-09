# ContainerProvider::RegistryRedirectionNodeFailure<ushort const *,ushort const *,ushort const *,long,ushort const (&)[56],uint const &>(ushort const * &&,ushort const * &&,ushort const * &&,long &&,ushort const (&)[56],uint const &)

- ea: `0x180027db0`
- end: `0x180027f1a`
- name: `??$RegistryRedirectionNodeFailure@PEBGPEBGPEBGJAEAY0DI@$$CBGAEBI@ContainerProvider@@SAX$$QEAPEBG00$$QEAJAEAY0DI@$$CBGAEBI@Z`
- size: `362`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002a78c`

## callees

- `0x180001e10`
- `0x180002ad0`
- `0x18000895c`
- `0x180027db0`

## string_xrefs

- `0x180027e12`: `DeviceIoControl IOCTL_VREG_CREATE_NAMESPACE_NODE failed`

## pseudocode

```c
int __fastcall ContainerProvider::RegistryRedirectionNodeFailure<unsigned short const *,unsigned short const *,unsigned short const *,long,unsigned short const (&)[56],unsigned int const &>(
        const WCHAR **a1,
        const WCHAR **a2,
        const WCHAR **a3,
        int *a4,
        int a5,
        int *a6)
{
  const struct _tlgProvider_t *v10; // rax
  int v11; // r11d
  __int64 v12; // r15
  int v13; // edx
  const WCHAR *v14; // r8
  int v15; // r9d
  __int64 v16; // rax
  const WCHAR *v17; // r9
  const WCHAR *v18; // rdx
  __int64 v19; // rcx
  int v20; // ecx
  __int64 v21; // rcx
  int v22; // ecx
  int v24; // [rsp+30h] [rbp-89h] BYREF
  int v25; // [rsp+34h] [rbp-85h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+40h] [rbp-79h] BYREF
  const WCHAR *v27; // [rsp+60h] [rbp-59h]
  int v28; // [rsp+68h] [rbp-51h]
  int v29; // [rsp+6Ch] [rbp-4Dh]
  const WCHAR *v30; // [rsp+70h] [rbp-49h]
  int v31; // [rsp+78h] [rbp-41h]
  int v32; // [rsp+7Ch] [rbp-3Dh]
  const WCHAR *v33; // [rsp+80h] [rbp-39h]
  int v34; // [rsp+88h] [rbp-31h]
  int v35; // [rsp+8Ch] [rbp-2Dh]
  int *v36; // [rsp+90h] [rbp-29h]
  __int64 v37; // [rsp+98h] [rbp-21h]
  const wchar_t *v38; // [rsp+A0h] [rbp-19h]
  __int64 v39; // [rsp+A8h] [rbp-11h]
  int *v40; // [rsp+B0h] [rbp-9h]
  __int64 v41; // [rsp+B8h] [rbp-1h]

  v10 = ContainerProvider::Provider();
  v11 = 2;
  v12 = (__int64)v10;
  if ( *(_DWORD *)v10 > 2u )
  {
    v13 = *a4;
    v14 = *a1;
    v40 = &v24;
    v38 = L"DeviceIoControl IOCTL_VREG_CREATE_NAMESPACE_NODE failed";
    v15 = *a6;
    v36 = &v25;
    v16 = -1;
    v24 = v15;
    v17 = *a3;
    v25 = v13;
    v18 = *a2;
    v41 = 4;
    v39 = 112;
    v37 = 4;
    if ( v17 )
    {
      v19 = -1;
      do
        ++v19;
      while ( v17[v19] );
      v20 = 2 * v19 + 2;
    }
    else
    {
      v17 = &pwszBaseUri;
      v20 = 2;
    }
    v33 = v17;
    v34 = v20;
    v35 = 0;
    if ( v18 )
    {
      v21 = -1;
      do
        ++v21;
      while ( v18[v21] );
      v22 = 2 * v21 + 2;
    }
    else
    {
      v18 = &pwszBaseUri;
      v22 = 2;
    }
    v30 = v18;
    v31 = v22;
    v32 = 0;
    if ( v14 )
    {
      do
        ++v16;
      while ( v14[v16] );
      v11 = 2 * v16 + 2;
    }
    else
    {
      v14 = &pwszBaseUri;
    }
    v27 = v14;
    v28 = v11;
    v29 = 0;
    LODWORD(v10) = tlgWriteTransfer_EventWriteTransfer(v12, (unsigned __int8 *)&unk_18003CED0, 0, 0, 8u, &v26);
  }
  return (int)v10;
}

```

## disassembly

```asm
0x180027db0  push    rbp
0x180027db2  push    rbx
0x180027db3  push    rsi
0x180027db4  push    rdi
0x180027db5  push    r14
0x180027db7  push    r15
0x180027db9  lea     rbp, [rsp-1Fh]
0x180027dbe  sub     rsp, 0D8h
0x180027dc5  mov     rax, cs:__security_cookie
0x180027dcc  xor     rax, rsp
0x180027dcf  mov     [rbp+47h+var_40], rax
0x180027dd3  mov     rbx, r9
0x180027dd6  mov     rdi, r8
0x180027dd9  mov     rsi, rdx
0x180027ddc  mov     r14, rcx
0x180027ddf  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180027de4  mov     r11d, 2
0x180027dea  mov     r15, rax
0x180027ded  mov     r10d, [rax]
0x180027df0  cmp     r10d, r11d
0x180027df3  jbe     loc_180027EFD
0x180027df9  mov     edx, [rbx]
0x180027dfb  lea     rax, [rsp+100h+var_D0]
0x180027e00  mov     r10, [rbp+47h+arg_28]
0x180027e04  lea     rbx, pwszBaseUri
0x180027e0b  mov     r8, [r14]
0x180027e0e  mov     [rbp+47h+var_50], rax
0x180027e12  lea     rax, aDeviceiocontro_0; "DeviceIoControl IOCTL_VREG_CREATE_NAMES"...
0x180027e19  mov     [rbp+47h+var_60], rax
0x180027e1d  lea     rax, [rsp+100h+var_CC]
0x180027e22  mov     r9d, [r10]
0x180027e25  xor     r10d, r10d
0x180027e28  mov     [rbp+47h+var_70], rax
0x180027e2c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027e30  mov     [rsp+100h+var_D0], r9d
0x180027e35  mov     r9, [rdi]
0x180027e38  mov     [rsp+100h+var_CC], edx
0x180027e3c  mov     rdx, [rsi]
0x180027e3f  mov     [rbp+47h+var_48], 4
0x180027e47  mov     [rbp+47h+var_58], 70h ; 'p'
0x180027e4f  mov     [rbp+47h+var_68], 4
0x180027e57  test    r9, r9
0x180027e5a  jz      short loc_180027E72
0x180027e5c  mov     rcx, rax
0x180027e5f  inc     rcx
0x180027e62  cmp     [r9+rcx*2], r10w
0x180027e67  jnz     short loc_180027E5F
0x180027e69  lea     ecx, ds:2[rcx*2]
0x180027e70  jmp     short loc_180027E78
0x180027e72  mov     r9, rbx
0x180027e75  mov     ecx, r11d
0x180027e78  mov     [rbp+47h+var_80], r9
0x180027e7c  mov     [rbp+47h+var_78], ecx
0x180027e7f  mov     [rbp+47h+var_74], r10d
0x180027e83  test    rdx, rdx
0x180027e86  jz      short loc_180027E9E
0x180027e88  mov     rcx, rax
0x180027e8b  inc     rcx
0x180027e8e  cmp     [rdx+rcx*2], r10w
0x180027e93  jnz     short loc_180027E8B
0x180027e95  lea     ecx, ds:2[rcx*2]
0x180027e9c  jmp     short loc_180027EA4
0x180027e9e  mov     rdx, rbx
0x180027ea1  mov     ecx, r11d
0x180027ea4  mov     [rbp+47h+var_90], rdx
0x180027ea8  mov     [rbp+47h+var_88], ecx
0x180027eab  mov     [rbp+47h+var_84], r10d
0x180027eaf  test    r8, r8
0x180027eb2  jz      short loc_180027EC8
0x180027eb4  inc     rax
0x180027eb7  cmp     [r8+rax*2], r10w
0x180027ebc  jnz     short loc_180027EB4
0x180027ebe  lea     r11d, ds:2[rax*2]
0x180027ec6  jmp     short loc_180027ECB
0x180027ec8  mov     r8, rbx
0x180027ecb  lea     rax, [rbp+47h+var_C0]
0x180027ecf  mov     [rbp+47h+var_A0], r8
0x180027ed3  mov     [rsp+100h+var_D8], rax
0x180027ed8  lea     rdx, unk_18003CED0
0x180027edf  xor     r9d, r9d
0x180027ee2  mov     [rsp+100h+var_E0], 8
0x180027eea  xor     r8d, r8d
0x180027eed  mov     [rbp+47h+var_98], r11d
0x180027ef1  mov     rcx, r15
0x180027ef4  mov     [rbp+47h+var_94], r10d
0x180027ef8  call    _tlgWriteTransfer_EventWriteTransfer
0x180027efd  mov     rcx, [rbp+47h+var_40]
0x180027f01  xor     rcx, rsp; StackCookie
0x180027f04  call    __security_check_cookie
0x180027f09  add     rsp, 0D8h
0x180027f10  pop     r15
0x180027f12  pop     r14
0x180027f14  pop     rdi
0x180027f15  pop     rsi
0x180027f16  pop     rbx
0x180027f17  pop     rbp
0x180027f18  retn
```
