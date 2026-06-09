# ContainerProvider::RegistrySymlinkDeletionFailure<ushort const *,long,ushort const (&)[40]>(ushort const * &&,long &&,ushort const (&)[40])

- ea: `0x180028100`
- end: `0x1800281e1`
- name: `??$RegistrySymlinkDeletionFailure@PEBGJAEAY0CI@$$CBG@ContainerProvider@@SAX$$QEAPEBG$$QEAJAEAY0CI@$$CBG@Z`
- size: `225`
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
- `0x180028100`

## string_xrefs

- `0x18002814b`: `NtDeleteKey failed during symlink retry`

## pseudocode

```c
ULONG __fastcall ContainerProvider::RegistrySymlinkDeletionFailure<unsigned short const *,long,unsigned short const (&)[40]>(
        const WCHAR **a1,
        int *a2)
{
  const struct _tlgProvider_t *v4; // r10
  ULONG result; // eax
  const WCHAR *v6; // rcx
  __int64 v7; // rax
  int v8; // [rsp+30h] [rbp-19h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+40h] [rbp-9h] BYREF
  const WCHAR *v10; // [rsp+60h] [rbp+17h]
  ULONG v11; // [rsp+68h] [rbp+1Fh]
  int v12; // [rsp+6Ch] [rbp+23h]
  int *v13; // [rsp+70h] [rbp+27h]
  __int64 v14; // [rsp+78h] [rbp+2Fh]
  const wchar_t *v15; // [rsp+80h] [rbp+37h]
  __int64 v16; // [rsp+88h] [rbp+3Fh]

  v4 = ContainerProvider::Provider();
  result = 2;
  if ( *(_DWORD *)v4 > 2u )
  {
    v6 = *a1;
    v8 = *a2;
    v15 = L"NtDeleteKey failed during symlink retry";
    v13 = &v8;
    v16 = 80;
    v14 = 4;
    if ( v6 )
    {
      v7 = -1;
      do
        ++v7;
      while ( v6[v7] );
      result = 2 * v7 + 2;
    }
    else
    {
      v6 = &pwszBaseUri;
    }
    v11 = result;
    v10 = v6;
    v12 = 0;
    return tlgWriteTransfer_EventWriteTransfer((__int64)v4, (unsigned __int8 *)&dword_18003CFBC, 0, 0, 5u, &v9);
  }
  return result;
}

```

## disassembly

```asm
0x180028100  mov     [rsp-8+arg_0], rbx
0x180028105  mov     [rsp-8+arg_8], rdi
0x18002810a  push    rbp
0x18002810b  lea     rbp, [rsp-57h]
0x180028110  sub     rsp, 0A0h
0x180028117  mov     rax, cs:__security_cookie
0x18002811e  xor     rax, rsp
0x180028121  mov     [rbp+57h+var_10], rax
0x180028125  mov     rbx, rdx
0x180028128  mov     rdi, rcx
0x18002812b  call    ?Provider@ContainerProvider@@SAPEBU_tlgProvider_t@@XZ; ContainerProvider::Provider(void)
0x180028130  mov     r10, rax
0x180028133  mov     r8d, [rax]
0x180028136  mov     eax, 2
0x18002813b  cmp     r8d, eax
0x18002813e  jbe     short loc_1800281BF
0x180028140  mov     edx, [rbx]
0x180028142  xor     r8d, r8d
0x180028145  mov     rcx, [rdi]
0x180028148  mov     [rbp+57h+var_70], edx
0x18002814b  lea     rdx, aNtdeletekeyFai; "NtDeleteKey failed during symlink retry"
0x180028152  mov     [rbp+57h+var_20], rdx
0x180028156  lea     rdx, [rbp+57h+var_70]
0x18002815a  mov     [rbp+57h+var_30], rdx
0x18002815e  mov     [rbp+57h+var_18], 50h ; 'P'
0x180028166  mov     [rbp+57h+var_28], 4
0x18002816e  test    rcx, rcx
0x180028171  jz      short loc_18002818A
0x180028173  or      rax, 0FFFFFFFFFFFFFFFFh
0x180028177  inc     rax
0x18002817a  cmp     [rcx+rax*2], r8w
0x18002817f  jnz     short loc_180028177
0x180028181  lea     eax, ds:2[rax*2]
0x180028188  jmp     short loc_180028191
0x18002818a  lea     rcx, pwszBaseUri
0x180028191  mov     [rbp+57h+var_38], eax
0x180028194  lea     rdx, dword_18003CFBC
0x18002819b  lea     rax, [rbp+57h+var_60]
0x18002819f  mov     [rbp+57h+var_40], rcx
0x1800281a3  mov     [rsp+0A0h+var_78], rax
0x1800281a8  xor     r9d, r9d
0x1800281ab  mov     rcx, r10
0x1800281ae  mov     [rsp+0A0h+var_80], 5
0x1800281b6  mov     [rbp+57h+var_34], r8d
0x1800281ba  call    _tlgWriteTransfer_EventWriteTransfer
0x1800281bf  mov     rcx, [rbp+57h+var_10]
0x1800281c3  xor     rcx, rsp; StackCookie
0x1800281c6  call    __security_check_cookie
0x1800281cb  lea     r11, [rsp+0A0h+var_s0]
0x1800281d3  mov     rbx, [r11+10h]
0x1800281d7  mov     rdi, [r11+18h]
0x1800281db  mov     rsp, r11
0x1800281de  pop     rbp
0x1800281df  retn
```
