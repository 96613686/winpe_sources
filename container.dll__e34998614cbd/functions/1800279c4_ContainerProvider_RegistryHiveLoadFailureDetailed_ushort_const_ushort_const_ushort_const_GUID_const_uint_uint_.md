# ContainerProvider::RegistryHiveLoadFailureDetailed<ushort const *,ushort const *,ushort const *,_GUID const &,uint,uint,long,ushort const (&)[57],ulong &>(ushort const * &&,ushort const * &&,ushort const * &&,_GUID const &,uint &&,uint &&,long &&,ushort const (&)[57],ulong &)

- ea: `0x1800279c4`
- end: `0x180027b8c`
- name: `??$RegistryHiveLoadFailureDetailed@PEBGPEBGPEBGAEBU_GUID@@IIJAEAY0DJ@$$CBGAEAK@ContainerProvider@@SAX$$QEAPEBG00AEBU_GUID@@$$QEAI2$$QEAJAEAY0DJ@$$CBGAEAK@Z`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029bc0`

## callees

- `0x180001e10`
- `0x180002ad0`
- `0x18000895c`
- `0x1800279c4`

## pseudocode

```c
int __fastcall ContainerProvider::RegistryHiveLoadFailureDetailed<unsigned short const *,unsigned short const *,unsigned short const *,_GUID const &,unsigned int,unsigned int,long,unsigned short const (&)[57],unsigned long &>(
        const WCHAR **a1,
        const WCHAR **a2,
        const WCHAR **a3,
        __int128 *a4,
        int *a5,
        int *a6,
        int *a7,
        int a8,
        int *a9)
{
  const struct _tlgProvider_t *v13; // rax
  int v14; // r11d
  __int64 v15; // rbx
  __int128 v16; // xmm0
  const WCHAR *v17; // r8
  int v18; // r9d
  const WCHAR *v19; // r9
  int v20; // edx
  int v21; // ecx
  __int64 v22; // rax
  const WCHAR *v23; // rdx
  __int64 v24; // rcx
  int v25; // ecx
  __int64 v26; // rcx
  int v27; // ecx
  int v29; // [rsp+30h] [rbp-D0h] BYREF
  int v30; // [rsp+34h] [rbp-CCh] BYREF
  int v31; // [rsp+38h] [rbp-C8h] BYREF
  int v32; // [rsp+3Ch] [rbp-C4h] BYREF
  __int128 v33; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v34; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v35; // [rsp+70h] [rbp-90h]
  int v36; // [rsp+78h] [rbp-88h]
  int v37; // [rsp+7Ch] [rbp-84h]
  const WCHAR *v38; // [rsp+80h] [rbp-80h]
  int v39; // [rsp+88h] [rbp-78h]
  int v40; // [rsp+8Ch] [rbp-74h]
  const WCHAR *v41; // [rsp+90h] [rbp-70h]
  int v42; // [rsp+98h] [rbp-68h]
  int v43; // [rsp+9Ch] [rbp-64h]
  __int128 *v44; // [rsp+A0h] [rbp-60h]
  __int64 v45; // [rsp+A8h] [rbp-58h]
  int *v46; // [rsp+B0h] [rbp-50h]
  __int64 v47; // [rsp+B8h] [rbp-48h]
  int *v48; // [rsp+C0h] [rbp-40h]
  __int64 v49; // [rsp+C8h] [rbp-38h]
  int *v50; // [rsp+D0h] [rbp-30h]
  __int64 v51; // [rsp+D8h] [rbp-28h]
  const wchar_t *v52; // [rsp+E0h] [rbp-20h]
  __int64 v53; // [rsp+E8h] [rbp-18h]
  int *v54; // [rsp+F0h] [rbp-10h]
  __int64 v55; // [rsp+F8h] [rbp-8h]

  v13 = ContainerProvider::Provider();
  v14 = 2;
  v15 = (__int64)v13;
  if ( *(_DWORD *)v13 > 2u )
  {
    v16 = *a4;
    v17 = *a1;
    v18 = *a9;
    v30 = *a7;
    v29 = v18;
    v19 = *a3;
    v33 = v16;
    v20 = *a6;
    v21 = *a5;
    v54 = &v29;
    v52 = L"DeviceIoControl IOCTL_VREG_LOAD_DIFFERENCING_HIVE failed";
    v50 = &v30;
    v48 = &v31;
    v46 = &v32;
    v44 = &v33;
    v22 = -1;
    v31 = v20;
    v23 = *a2;
    v32 = v21;
    v55 = 4;
    v53 = 114;
    v51 = 4;
    v49 = 4;
    v47 = 4;
    v45 = 16;
    if ( v19 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v19[v24] );
      v25 = 2 * v24 + 2;
    }
    else
    {
      v19 = &pwszBaseUri;
      v25 = 2;
    }
    v41 = v19;
    v42 = v25;
    v43 = 0;
    if ( v23 )
    {
      v26 = -1;
      do
        ++v26;
      while ( v23[v26] );
      v27 = 2 * v26 + 2;
    }
    else
    {
      v23 = &pwszBaseUri;
      v27 = 2;
    }
    v38 = v23;
    v39 = v27;
    v40 = 0;
    if ( v17 )
    {
      do
        ++v22;
      while ( v17[v22] );
      v14 = 2 * v22 + 2;
    }
    else
    {
      v17 = &pwszBaseUri;
    }
    v35 = v17;
    v36 = v14;
    v37 = 0;
    LODWORD(v13) = tlgWriteTransfer_EventWriteTransfer(v15, (unsigned __int8 *)&unk_18003CD20, 0, 0, 0xBu, &v34);
  }
  return (int)v13;
}

```

## disassembly

```asm
0x1800279c4  push    rbp
0x1800279c6  push    rbx
0x1800279c7  push    rsi
0x1800279c8  push    rdi
0x1800279c9  push    r14
0x1800279cb  push    r15
0x1800279cd  lea     rbp, [rsp-18h]
0x1800279d2  sub     rsp, 118h
0x1800279d9  mov     rax, cs:__security_cookie
0x1800279e0  xor     rax, rsp
0x1800279e3  mov     [rbp+40h+var_40], rax
0x1800279e7  mov     rdi, r9
0x1800279ea  mov     rsi, r8
0x1800279ed  mov     r14, rdx
0x1800279f0  mov     r15, rcx
0x1800279f3  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x1800279f8  mov     r11d, 2
0x1800279fe  mov     rbx, rax
0x180027a01  mov     r10d, [rax]
0x180027a04  cmp     r10d, r11d
0x180027a07  jbe     loc_180027B6F
0x180027a0d  mov     rdx, [rbp+40h+arg_30]
0x180027a14  mov     rax, [rbp+40h+arg_20]
0x180027a18  mov     r10, [rbp+40h+arg_40]
0x180027a1f  movups  xmm0, xmmword ptr [rdi]
0x180027a22  mov     ecx, [rdx]
0x180027a24  lea     rdi, pwszBaseUri
0x180027a2b  mov     r8, [r15]
0x180027a2e  mov     r9d, [r10]
0x180027a31  xor     r10d, r10d
0x180027a34  mov     [rsp+140h+var_10C], ecx
0x180027a38  mov     rcx, [rbp+40h+arg_28]
0x180027a3c  mov     [rsp+140h+var_110], r9d
0x180027a41  mov     r9, [rsi]
0x180027a44  movdqu  [rsp+140h+var_100], xmm0
0x180027a4a  mov     edx, [rcx]
0x180027a4c  mov     ecx, [rax]
0x180027a4e  lea     rax, [rsp+140h+var_110]
0x180027a53  mov     [rbp+40h+var_50], rax
0x180027a57  lea     rax, aDeviceiocontro; "DeviceIoControl IOCTL_VREG_LOAD_DIFFERE"...
0x180027a5e  mov     [rbp+40h+var_60], rax
0x180027a62  lea     rax, [rsp+140h+var_10C]
0x180027a67  mov     [rbp+40h+var_70], rax
0x180027a6b  lea     rax, [rsp+140h+var_108]
0x180027a70  mov     [rbp+40h+var_80], rax
0x180027a74  lea     rax, [rsp+140h+var_104]
0x180027a79  mov     [rbp+40h+var_90], rax
0x180027a7d  lea     rax, [rsp+140h+var_100]
0x180027a82  mov     [rbp+40h+var_A0], rax
0x180027a86  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027a8a  mov     [rsp+140h+var_108], edx
0x180027a8e  mov     rdx, [r14]
0x180027a91  mov     [rsp+140h+var_104], ecx
0x180027a95  mov     [rbp+40h+var_48], 4
0x180027a9d  mov     [rbp+40h+var_58], 72h ; 'r'
0x180027aa5  mov     [rbp+40h+var_68], 4
0x180027aad  mov     [rbp+40h+var_78], 4
0x180027ab5  mov     [rbp+40h+var_88], 4
0x180027abd  mov     [rbp+40h+var_98], 10h
0x180027ac5  test    r9, r9
0x180027ac8  jz      short loc_180027AE0
0x180027aca  mov     rcx, rax
0x180027acd  inc     rcx
0x180027ad0  cmp     [r9+rcx*2], r10w
0x180027ad5  jnz     short loc_180027ACD
0x180027ad7  lea     ecx, ds:2[rcx*2]
0x180027ade  jmp     short loc_180027AE6
0x180027ae0  mov     r9, rdi
0x180027ae3  mov     ecx, r11d
0x180027ae6  mov     [rbp+40h+var_B0], r9
0x180027aea  mov     [rbp+40h+var_A8], ecx
0x180027aed  mov     [rbp+40h+var_A4], r10d
0x180027af1  test    rdx, rdx
0x180027af4  jz      short loc_180027B0C
0x180027af6  mov     rcx, rax
0x180027af9  inc     rcx
0x180027afc  cmp     [rdx+rcx*2], r10w
0x180027b01  jnz     short loc_180027AF9
0x180027b03  lea     ecx, ds:2[rcx*2]
0x180027b0a  jmp     short loc_180027B12
0x180027b0c  mov     rdx, rdi
0x180027b0f  mov     ecx, r11d
0x180027b12  mov     [rbp+40h+var_C0], rdx
0x180027b16  mov     [rbp+40h+var_B8], ecx
0x180027b19  mov     [rbp+40h+var_B4], r10d
0x180027b1d  test    r8, r8
0x180027b20  jz      short loc_180027B36
0x180027b22  inc     rax
0x180027b25  cmp     [r8+rax*2], r10w
0x180027b2a  jnz     short loc_180027B22
0x180027b2c  lea     r11d, ds:2[rax*2]
0x180027b34  jmp     short loc_180027B39
0x180027b36  mov     r8, rdi
0x180027b39  lea     rax, [rsp+140h+var_F0]
0x180027b3e  mov     [rsp+140h+var_D0], r8
0x180027b43  mov     [rsp+140h+var_118], rax
0x180027b48  lea     rdx, unk_18003CD20
0x180027b4f  xor     r9d, r9d
0x180027b52  mov     [rsp+140h+var_120], 0Bh
0x180027b5a  xor     r8d, r8d
0x180027b5d  mov     [rsp+140h+var_C8], r11d
0x180027b62  mov     rcx, rbx
0x180027b65  mov     [rsp+140h+var_C4], r10d
0x180027b6a  call    _tlgWriteTransfer_EventWriteTransfer
0x180027b6f  mov     rcx, [rbp+40h+var_40]
0x180027b73  xor     rcx, rsp; StackCookie
0x180027b76  call    __security_check_cookie
0x180027b7b  add     rsp, 118h
0x180027b82  pop     r15
0x180027b84  pop     r14
0x180027b86  pop     rdi
0x180027b87  pop     rsi
0x180027b88  pop     rbx
0x180027b89  pop     rbp
0x180027b8a  retn
```
