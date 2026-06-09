# CFveApi::IdentificationFieldMatch(void)

- ea: `0x180041d24`
- end: `0x18004203c`
- name: `?IdentificationFieldMatch@CFveApi@@AEAAHXZ`
- size: `792`
- prototype: `__int64 __fastcall(CFveApi *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800403f0`

## callees

- `0x1800090c0`
- `0x180037f50`
- `0x18003d000`
- `0x180041d24`
- `0x180045ea0`
- `0x180084840`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041d9c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041df2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041e5b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041d9c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041df2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180041e5b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180041fc1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180041fc1`

## pseudocode

```c
__int64 __fastcall CFveApi::IdentificationFieldMatch(CFveApi *this)
{
  unsigned int v1; // r15d
  LSTATUS ValueW; // eax
  bool v4; // sf
  LSTATUS v5; // eax
  bool v6; // sf
  void *v7; // rsi
  unsigned __int64 v8; // r12
  LSTATUS v9; // eax
  bool v10; // sf
  unsigned int v11; // eax
  int v12; // ebx
  unsigned __int16 *v13; // rax
  WCHAR *v14; // rdi
  unsigned int IdentificationField; // eax
  int v16; // ebx
  PVOID *v17; // rcx
  int cchCount1[2]; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int64 v20; // [rsp+48h] [rbp-28h] BYREF
  DWORD v21; // [rsp+50h] [rbp-20h] BYREF
  int pvData; // [rsp+54h] [rbp-1Ch] BYREF
  DWORD pcbData; // [rsp+58h] [rbp-18h] BYREF

  v1 = 0;
  pcbData = 4;
  pvData = 0;
  v20 = 0;
  *(_QWORD *)cchCount1 = 0;
  v21 = 0;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Policies\\Microsoft\\FVE",
             L"IdentificationField",
             0x18u,
             0,
             &pvData,
             &pcbData);
  v4 = ValueW < 0;
  if ( ValueW > 0 )
    v4 = 1;
  if ( !v4 && pvData )
  {
    pcbData = 0;
    v5 = RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Policies\\Microsoft\\FVE",
           L"IdentificationFieldString",
           2u,
           0,
           0,
           &v21);
    v6 = v5 < 0;
    if ( v5 > 0 )
      v6 = 1;
    if ( !v6 )
    {
      if ( v21 )
      {
        v7 = CFveApiBase::ZeroAlloc(v21);
        if ( v7 )
        {
          v8 = v21;
          v9 = RegGetValueW(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Policies\\Microsoft\\FVE",
                 L"IdentificationFieldString",
                 2u,
                 0,
                 v7,
                 &v21);
          v10 = v9 < 0;
          if ( v9 > 0 )
            v10 = 1;
          if ( v10
            || (unsigned int)CFveApiBase::GetIdentificationField(this, 0, 0, (unsigned __int64 *)cchCount1) != -2147024774 )
          {
            goto LABEL_36;
          }
          v11 = ULongLongMult(*(unsigned __int64 *)cchCount1, 2u, &v20);
          v12 = v11;
          if ( v11 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_dac461a5a0973d62c81039952891528d_Traceguids, v11);
            if ( v12 < 0 )
              goto LABEL_36;
          }
          v13 = (unsigned __int16 *)CFveApiBase::ZeroAlloc(v20);
          v14 = v13;
          if ( !v13 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                11,
                WPP_dac461a5a0973d62c81039952891528d_Traceguids,
                2147942414LL);
            goto LABEL_36;
          }
          IdentificationField = CFveApiBase::GetIdentificationField(
                                  this,
                                  v13,
                                  *(unsigned __int64 *)cchCount1,
                                  (unsigned __int64 *)cchCount1);
          v16 = IdentificationField;
          if ( IdentificationField )
          {
            v17 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                12,
                WPP_dac461a5a0973d62c81039952891528d_Traceguids,
                IdentificationField);
              v17 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v16 < 0 )
              goto LABEL_35;
          }
          else
          {
            v17 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( *(_QWORD *)cchCount1 > 0xFFFFFFFF )
          {
            if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 0x40) != 0 )
              WPP_SF_d(v17[2], 13, WPP_dac461a5a0973d62c81039952891528d_Traceguids, 2147942934LL);
          }
          else
          {
            LOBYTE(v1) = CompareStringW(0x7Fu, 1u, v14, cchCount1[0], (PCNZWCH)v7, v21 >> 1) == 2;
          }
LABEL_35:
          CFveApiBase::ZeroFree(v14, v20);
LABEL_36:
          CFveApiBase::ZeroFree(v7, v8);
        }
      }
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180041d24  mov     r11, rsp
0x180041d27  mov     [r11+10h], rbx
0x180041d2b  mov     [r11+18h], rsi
0x180041d2f  push    rbp
0x180041d30  push    rdi
0x180041d31  push    r12
0x180041d33  push    r14
0x180041d35  push    r15
0x180041d37  mov     rbp, rsp
0x180041d3a  sub     rsp, 70h
0x180041d3e  mov     rax, cs:__security_cookie
0x180041d45  xor     rax, rsp
0x180041d48  mov     [rbp+var_10], rax
0x180041d4c  xor     r15d, r15d
0x180041d4f  mov     [rbp+var_18], 4
0x180041d56  lea     rax, [rbp+var_18]
0x180041d5a  mov     [rbp+var_1C], r15d
0x180041d5e  mov     [r11-68h], rax
0x180041d62  lea     rdi, aSoftwarePolici; "Software\\Policies\\Microsoft\\FVE"
0x180041d69  lea     rax, [rbp+var_1C]
0x180041d6d  mov     [rbp+var_28], r15
0x180041d71  mov     r14, rcx
0x180041d74  mov     [r11-70h], rax
0x180041d78  mov     rsi, 0FFFFFFFF80000002h
0x180041d7f  mov     [r11-78h], r15
0x180041d83  lea     r9d, [r15+18h]; dwFlags
0x180041d87  mov     qword ptr [rbp+cchCount1], r15
0x180041d8b  lea     r8, aIdentification_0; "IdentificationField"
0x180041d92  mov     [rbp+var_20], r15d
0x180041d96  mov     rdx, rdi; lpSubKey
0x180041d99  mov     rcx, rsi; hkey
0x180041d9c  call    cs:__imp_RegGetValueW
0x180041da3  nop     dword ptr [rax+rax+00h]
0x180041da8  mov     ebx, 80070000h
0x180041dad  test    eax, eax
0x180041daf  jle     short loc_180041DB8
0x180041db1  movzx   eax, ax
0x180041db4  or      eax, ebx
0x180041db6  test    eax, eax
0x180041db8  js      loc_180042013
0x180041dbe  cmp     [rbp+var_1C], r15d
0x180041dc2  jz      loc_180042013
0x180041dc8  lea     rax, [rbp+var_20]
0x180041dcc  mov     [rbp+var_18], r15d
0x180041dd0  mov     [rsp+70h+pcbData], rax; pcbData
0x180041dd5  lea     r8, aIdentification; "IdentificationFieldString"
0x180041ddc  mov     [rsp+70h+pvData], r15; pvData
0x180041de1  mov     r9d, 2; dwFlags
0x180041de7  mov     rdx, rdi; lpSubKey
0x180041dea  mov     [rsp+70h+pdwType], r15; pdwType
0x180041def  mov     rcx, rsi; hkey
0x180041df2  call    cs:__imp_RegGetValueW
0x180041df9  nop     dword ptr [rax+rax+00h]
0x180041dfe  test    eax, eax
0x180041e00  jle     short loc_180041E09
0x180041e02  movzx   eax, ax
0x180041e05  or      eax, ebx
0x180041e07  test    eax, eax
0x180041e09  js      loc_180042013
0x180041e0f  mov     eax, [rbp+var_20]
0x180041e12  test    eax, eax
0x180041e14  jz      loc_180042013
0x180041e1a  mov     ecx, eax; unsigned __int64
0x180041e1c  call    ?ZeroAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::ZeroAlloc(unsigned __int64)
0x180041e21  mov     rsi, rax
0x180041e24  test    rax, rax
0x180041e27  jz      loc_180042013
0x180041e2d  mov     r12d, [rbp+var_20]
0x180041e31  lea     rax, [rbp+var_20]
0x180041e35  mov     [rsp+70h+pcbData], rax; pcbData
0x180041e3a  lea     r8, aIdentification; "IdentificationFieldString"
0x180041e41  mov     [rsp+70h+pvData], rsi; pvData
0x180041e46  mov     r9d, 2; dwFlags
0x180041e4c  mov     rdx, rdi; lpSubKey
0x180041e4f  mov     [rsp+70h+pdwType], r15; pdwType
0x180041e54  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180041e5b  call    cs:__imp_RegGetValueW
0x180041e62  nop     dword ptr [rax+rax+00h]
0x180041e67  test    eax, eax
0x180041e69  jle     short loc_180041E72
0x180041e6b  movzx   eax, ax
0x180041e6e  or      eax, ebx
0x180041e70  test    eax, eax
0x180041e72  js      loc_180042008
0x180041e78  lea     r9, [rbp+cchCount1]; unsigned __int64 *
0x180041e7c  xor     r8d, r8d; unsigned __int64
0x180041e7f  xor     edx, edx; unsigned __int16 *
0x180041e81  mov     rcx, r14; this
0x180041e84  call    ?GetIdentificationField@CFveApiBase@@QEAAJPEAG_KPEA_K@Z; CFveApiBase::GetIdentificationField(ushort *,unsigned __int64,unsigned __int64 *)
0x180041e89  cmp     eax, 8007007Ah
0x180041e8e  jnz     loc_180042008
0x180041e94  mov     rcx, qword ptr [rbp+cchCount1]; unsigned __int64
0x180041e98  lea     r8, [rbp+var_28]; unsigned __int64 *
0x180041e9c  mov     edx, 2; unsigned __int64
0x180041ea1  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180041ea6  lea     rdx, WPP_GLOBAL_Control
0x180041ead  mov     ebx, eax
0x180041eaf  test    eax, eax
0x180041eb1  jz      short loc_180041EE5
0x180041eb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180041eba  cmp     rcx, rdx
0x180041ebd  jz      short loc_180041EDD
0x180041ebf  test    byte ptr [rcx+1Ch], 40h
0x180041ec3  jz      short loc_180041EDD
0x180041ec5  mov     rcx, [rcx+10h]
0x180041ec9  lea     r8, WPP_dac461a5a0973d62c81039952891528d_Traceguids
0x180041ed0  mov     edx, 0Ah
0x180041ed5  mov     r9d, eax
0x180041ed8  call    WPP_SF_d
0x180041edd  test    ebx, ebx
0x180041edf  js      loc_180042008
0x180041ee5  mov     rcx, [rbp+var_28]; unsigned __int64
0x180041ee9  call    ?ZeroAlloc@CFveApiBase@@SAPEAX_K@Z; CFveApiBase::ZeroAlloc(unsigned __int64)
0x180041eee  mov     rdi, rax
0x180041ef1  test    rax, rax
0x180041ef4  jnz     short loc_180041F35
0x180041ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x180041efd  lea     r14, WPP_GLOBAL_Control
0x180041f04  cmp     rcx, r14
0x180041f07  jz      loc_180042008
0x180041f0d  test    byte ptr [rcx+1Ch], 40h
0x180041f11  jz      loc_180042008
0x180041f17  mov     rcx, [rcx+10h]
0x180041f1b  lea     edx, [rax+0Bh]
0x180041f1e  mov     r9d, 8007000Eh
0x180041f24  lea     r8, WPP_dac461a5a0973d62c81039952891528d_Traceguids
0x180041f2b  call    WPP_SF_d
0x180041f30  jmp     loc_180042008
0x180041f35  mov     r8, qword ptr [rbp+cchCount1]; unsigned __int64
0x180041f39  lea     r9, [rbp+cchCount1]; unsigned __int64 *
0x180041f3d  mov     rdx, rdi; unsigned __int16 *
0x180041f40  mov     rcx, r14; this
0x180041f43  call    ?GetIdentificationField@CFveApiBase@@QEAAJPEAG_KPEA_K@Z; CFveApiBase::GetIdentificationField(ushort *,unsigned __int64,unsigned __int64 *)
0x180041f48  mov     ebx, eax
0x180041f4a  test    eax, eax
0x180041f4c  jz      short loc_180041F8C
0x180041f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180041f55  lea     r14, WPP_GLOBAL_Control
0x180041f5c  cmp     rcx, r14
0x180041f5f  jz      short loc_180041F86
0x180041f61  test    byte ptr [rcx+1Ch], 40h
0x180041f65  jz      short loc_180041F86
0x180041f67  mov     rcx, [rcx+10h]
0x180041f6b  lea     r8, WPP_dac461a5a0973d62c81039952891528d_Traceguids
0x180041f72  mov     edx, 0Ch
0x180041f77  mov     r9d, eax
0x180041f7a  call    WPP_SF_d
0x180041f7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180041f86  test    ebx, ebx
0x180041f88  jns     short loc_180041F9A
0x180041f8a  jmp     short loc_180041FFC
0x180041f8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180041f93  lea     r14, WPP_GLOBAL_Control
0x180041f9a  mov     r9, qword ptr [rbp+cchCount1]; cchCount1
0x180041f9e  mov     eax, 0FFFFFFFFh
0x180041fa3  cmp     r9, rax
0x180041fa6  ja      short loc_180041FD6
0x180041fa8  mov     eax, [rbp+var_20]
0x180041fab  mov     edx, 1; dwCmpFlags
0x180041fb0  shr     eax, 1
0x180041fb2  mov     r8, rdi; lpString1
0x180041fb5  mov     dword ptr [rsp+70h+pvData], eax; cchCount2
0x180041fb9  mov     [rsp+70h+pdwType], rsi; lpString2
0x180041fbe  lea     ecx, [rdx+7Eh]; Locale
0x180041fc1  call    cs:__imp_CompareStringW
0x180041fc8  nop     dword ptr [rax+rax+00h]
0x180041fcd  cmp     eax, 2
0x180041fd0  setz    r15b
0x180041fd4  jmp     short loc_180041FFC
0x180041fd6  cmp     rcx, r14
0x180041fd9  jz      short loc_180041FFC
0x180041fdb  test    byte ptr [rcx+1Ch], 40h
0x180041fdf  jz      short loc_180041FFC
0x180041fe1  mov     rcx, [rcx+10h]
0x180041fe5  lea     r8, WPP_dac461a5a0973d62c81039952891528d_Traceguids
0x180041fec  mov     edx, 0Dh
0x180041ff1  mov     r9d, 80070216h
0x180041ff7  call    WPP_SF_d
0x180041ffc  mov     rdx, [rbp+var_28]; unsigned __int64
0x180042000  mov     rcx, rdi; lpMem
0x180042003  call    ?ZeroFree@CFveApiBase@@SAJPEAX_K@Z; CFveApiBase::ZeroFree(void *,unsigned __int64)
0x180042008  mov     rdx, r12; unsigned __int64
0x18004200b  mov     rcx, rsi; lpMem
0x18004200e  call    ?ZeroFree@CFveApiBase@@SAJPEAX_K@Z; CFveApiBase::ZeroFree(void *,unsigned __int64)
0x180042013  mov     eax, r15d
0x180042016  mov     rcx, [rbp+var_10]
0x18004201a  xor     rcx, rsp; StackCookie
0x18004201d  call    __security_check_cookie
0x180042022  lea     r11, [rsp+70h+var_s0]
0x180042027  mov     rbx, [r11+38h]
0x18004202b  mov     rsi, [r11+40h]
0x18004202f  mov     rsp, r11
0x180042032  pop     r15
0x180042034  pop     r14
0x180042036  pop     r12
0x180042038  pop     rdi
0x180042039  pop     rbp
0x18004203a  retn
```
