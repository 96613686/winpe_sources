# RegistryPropertyBag::EncryptedDwordProperty::Write(HKEY__ *)

- ea: `0x180056c28`
- end: `0x180056dd4`
- name: `?Write@EncryptedDwordProperty@RegistryPropertyBag@@MEAAJPEAUHKEY__@@@Z`
- size: `428`
- prototype: `int(RegistryPropertyBag::EncryptedDwordProperty *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180055db0`

## callees

- `0x1800024e0`
- `0x180002efc`
- `0x180055448`
- `0x180055470`
- `0x180056c28`
- `0x1800573a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180056d5d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180056d5d`
- `ntdll!NtQueryKey` at `0x180056cdc`
- `ntdll!NtQueryKey` at `0x180056cdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056d7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180056d7a`

## pseudocode

```c
__int64 __fastcall RegistryPropertyBag::EncryptedDwordProperty::Write(
        RegistryPropertyBag::EncryptedDwordProperty *this,
        HKEY a2)
{
  _QWORD *v4; // rcx
  unsigned __int64 cbData; // rsi
  unsigned __int8 *v6; // rdi
  int v7; // eax
  RegistryPropertyBag::EncryptedDwordProperty *v8; // rcx
  int v9; // eax
  int v10; // eax
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int8 *v13; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  DWORD KeyInformation; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v16[540]; // [rsp+54h] [rbp-ACh] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( *((_BYTE *)this + 9) )
  {
    cbData = 0;
    v6 = 0;
    v14 = 0;
    v13 = 0;
    ResultLength = 0;
    KeyInformation = 0;
    memset_0(v16, 0, 0x210u);
    v7 = NtQueryKey(a2, KeyNameInformation, &KeyInformation, 0x214u, &ResultLength) | 0x10000000;
    *((_DWORD *)this + 5) = v7;
    if ( v7 >= 0 )
    {
      if ( KeyInformation > 0x20A )
        goto LABEL_9;
      v9 = RegistryPropertyBag::EncryptedDwordProperty::_Encrypt(v8, (BYTE *)this + 12, KeyInformation, v16, &v14, &v13);
      v6 = v13;
      *((_DWORD *)this + 5) = v9;
      if ( v9 >= 0 )
      {
        cbData = v14;
LABEL_9:
        if ( cbData <= 0x1000 )
        {
          v10 = RegSetValueExW(a2, *((LPCWSTR *)this + 3), 0, 3u, v6, cbData);
          if ( v10 > 0 )
            v10 = (unsigned __int16)v10 | 0x80070000;
          *((_DWORD *)this + 5) = v10;
        }
        else
        {
          *((_DWORD *)this + 5) = -2147024883;
        }
      }
    }
    if ( v6 )
      LocalFree(v6);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x10) != 0 )
    WPP_SF_d(v4[2], 46, &WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids, *((unsigned int *)this + 5));
  return *((unsigned int *)this + 5);
}

```

## disassembly

```asm
0x180056c28  mov     [rsp-8+arg_10], rbx
0x180056c2d  push    rbp
0x180056c2e  push    rsi
0x180056c2f  push    rdi
0x180056c30  push    r12
0x180056c32  push    r14
0x180056c34  lea     rbp, [rsp-180h]
0x180056c3c  sub     rsp, 280h
0x180056c43  mov     rax, cs:__security_cookie
0x180056c4a  xor     rax, rsp
0x180056c4d  mov     [rbp+1A0h+var_30], rax
0x180056c54  mov     r14, rdx
0x180056c57  mov     rbx, rcx
0x180056c5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180056c61  lea     r12, WPP_GLOBAL_Control
0x180056c68  cmp     rcx, r12
0x180056c6b  jz      short loc_180056C8F
0x180056c6d  test    byte ptr [rcx+1Ch], 10h
0x180056c71  jz      short loc_180056C8F
0x180056c73  mov     rcx, [rcx+10h]
0x180056c77  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x180056c7e  mov     edx, 2Dh ; '-'
0x180056c83  call    WPP_SF_
0x180056c88  mov     rcx, cs:WPP_GLOBAL_Control
0x180056c8f  cmp     byte ptr [rbx+9], 0
0x180056c93  jz      loc_180056D87
0x180056c99  xor     esi, esi
0x180056c9b  lea     rcx, [rsp+2A0h+var_24C]; void *
0x180056ca0  xor     edi, edi
0x180056ca2  mov     [rsp+2A0h+var_260], rsi
0x180056ca7  xor     edx, edx; Val
0x180056ca9  mov     [rsp+2A0h+var_268], rdi
0x180056cae  mov     r8d, 210h; Size
0x180056cb4  mov     [rsp+2A0h+var_270], esi
0x180056cb8  mov     [rsp+2A0h+KeyInformation], esi
0x180056cbc  call    memset_0
0x180056cc1  lea     rax, [rsp+2A0h+var_270]
0x180056cc6  mov     r9d, 214h; Length
0x180056ccc  lea     r8, [rsp+2A0h+KeyInformation]; KeyInformation
0x180056cd1  mov     [rsp+2A0h+ResultLength], rax; ResultLength
0x180056cd6  lea     edx, [rsi+3]; KeyInformationClass
0x180056cd9  mov     rcx, r14; KeyHandle
0x180056cdc  call    cs:__imp_NtQueryKey
0x180056ce2  or      eax, 10000000h
0x180056ce7  mov     [rbx+14h], eax
0x180056cea  jl      loc_180056D72
0x180056cf0  cmp     [rsp+2A0h+KeyInformation], 20Ah
0x180056cf8  ja      short loc_180056D32
0x180056cfa  mov     r8d, [rsp+2A0h+KeyInformation]; unsigned __int64
0x180056cff  lea     rax, [rsp+2A0h+var_268]
0x180056d04  mov     qword ptr [rsp+2A0h+cbData], rax; unsigned __int8 **
0x180056d09  lea     rdx, [rbx+0Ch]; unsigned int *
0x180056d0d  lea     rax, [rsp+2A0h+var_260]
0x180056d12  lea     r9, [rsp+2A0h+var_24C]; unsigned __int8 *
0x180056d17  mov     [rsp+2A0h+ResultLength], rax; unsigned __int64 *
0x180056d1c  call    ?_Encrypt@EncryptedDwordProperty@RegistryPropertyBag@@AEAAJAEBK_KPEAEPEA_KPEAPEAE@Z; RegistryPropertyBag::EncryptedDwordProperty::_Encrypt(ulong const &,unsigned __int64,uchar *,unsigned __int64 *,uchar * *)
0x180056d21  mov     rdi, [rsp+2A0h+var_268]
0x180056d26  mov     [rbx+14h], eax
0x180056d29  test    eax, eax
0x180056d2b  js      short loc_180056D72
0x180056d2d  mov     rsi, [rsp+2A0h+var_260]
0x180056d32  cmp     rsi, 1000h
0x180056d39  jbe     short loc_180056D44
0x180056d3b  mov     dword ptr [rbx+14h], 8007000Dh
0x180056d42  jmp     short loc_180056D72
0x180056d44  mov     rdx, [rbx+18h]; lpValueName
0x180056d48  mov     r9d, 3; dwType
0x180056d4e  mov     [rsp+2A0h+cbData], esi; cbData
0x180056d52  xor     r8d, r8d; Reserved
0x180056d55  mov     rcx, r14; hKey
0x180056d58  mov     [rsp+2A0h+ResultLength], rdi; lpData
0x180056d5d  call    cs:__imp_RegSetValueExW
0x180056d63  test    eax, eax
0x180056d65  jle     short loc_180056D6F
0x180056d67  movzx   eax, ax
0x180056d6a  or      eax, 80070000h
0x180056d6f  mov     [rbx+14h], eax
0x180056d72  test    rdi, rdi
0x180056d75  jz      short loc_180056D80
0x180056d77  mov     rcx, rdi; hMem
0x180056d7a  call    cs:__imp_LocalFree
0x180056d80  mov     rcx, cs:WPP_GLOBAL_Control
0x180056d87  cmp     rcx, r12
0x180056d8a  jz      short loc_180056DAB
0x180056d8c  test    byte ptr [rcx+1Ch], 10h
0x180056d90  jz      short loc_180056DAB
0x180056d92  mov     r9d, [rbx+14h]
0x180056d96  lea     r8, WPP_ba44a63574e4389fb68e2aee6092cba5_Traceguids
0x180056d9d  mov     rcx, [rcx+10h]
0x180056da1  mov     edx, 2Eh ; '.'
0x180056da6  call    WPP_SF_d
0x180056dab  mov     eax, [rbx+14h]
0x180056dae  mov     rcx, [rbp+1A0h+var_30]
0x180056db5  xor     rcx, rsp; StackCookie
0x180056db8  call    __security_check_cookie
0x180056dbd  mov     rbx, [rsp+2A0h+arg_10]
0x180056dc5  add     rsp, 280h
0x180056dcc  pop     r14
0x180056dce  pop     r12
0x180056dd0  pop     rdi
0x180056dd1  pop     rsi
0x180056dd2  pop     rbp
0x180056dd3  retn
```
