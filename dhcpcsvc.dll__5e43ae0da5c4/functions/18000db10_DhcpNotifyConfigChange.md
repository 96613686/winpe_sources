# DhcpNotifyConfigChange

- ea: `0x18000db10`
- end: `0x18000dbd8`
- name: `DhcpNotifyConfigChange`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000db10`
- `0x18000dbe0`
- `0x1800123a4`
- `0x180012a00`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000db4c`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000db4c`

## pseudocode

```c
__int64 __fastcall DhcpNotifyConfigChange(__int64 a1, __int64 a2, unsigned int a3, int a4, int a5, int a6, int a7)
{
  LPWSTR CommandLineW; // rax
  int v12; // edx
  int v13; // ecx
  int v14; // r8d
  unsigned int v15; // eax
  unsigned int v16; // ebx

  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SSldDDLS(v13, v12, v14, a1, a2, a3, a4, a5, a6, a7, (__int64)CommandLineW);
  }
  v15 = DhcpNotifyConfigChangeEx(a1, a2, a3, a4, a5, a6, a7, 3);
  v16 = v15;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_d(1028, 16, WPP_bced608cee43397007671a721f646035_Traceguids, v15);
  return v16;
}

```

## disassembly

```asm
0x18000db10  push    rbx
0x18000db12  push    rbp
0x18000db13  push    rsi
0x18000db14  push    rdi
0x18000db15  push    r12
0x18000db17  push    r14
0x18000db19  push    r15
0x18000db1b  sub     rsp, 60h
0x18000db1f  mov     ebx, r9d
0x18000db22  mov     edi, r8d
0x18000db25  mov     rsi, rdx
0x18000db28  mov     rbp, rcx
0x18000db2b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000db32  mov     r14d, [rsp+98h+arg_30]
0x18000db3a  mov     r15d, [rsp+98h+arg_28]
0x18000db42  mov     r12d, [rsp+98h+arg_20]
0x18000db4a  jz      short loc_18000DB7B
0x18000db4c  call    cs:__imp_GetCommandLineW
0x18000db52  mov     [rsp+98h+var_48], rax
0x18000db57  mov     r9, rbp
0x18000db5a  mov     [rsp+98h+var_50], r14d
0x18000db5f  mov     [rsp+98h+var_58], r15d
0x18000db64  mov     [rsp+98h+var_60], r12d
0x18000db69  mov     [rsp+98h+var_68], ebx
0x18000db6d  mov     [rsp+98h+var_70], edi
0x18000db71  mov     [rsp+98h+var_78], rsi
0x18000db76  call    WPP_SF_SSldDDLS
0x18000db7b  mov     [rsp+98h+var_60], 3
0x18000db83  mov     r9d, ebx
0x18000db86  mov     [rsp+98h+var_68], r14d
0x18000db8b  mov     r8d, edi
0x18000db8e  mov     [rsp+98h+var_70], r15d
0x18000db93  mov     rdx, rsi
0x18000db96  mov     rcx, rbp
0x18000db99  mov     dword ptr [rsp+98h+var_78], r12d
0x18000db9e  call    DhcpNotifyConfigChangeEx
0x18000dba3  mov     ebx, eax
0x18000dba5  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000dbac  jz      short loc_18000DBC7
0x18000dbae  mov     edx, 10h
0x18000dbb3  lea     r8, WPP_bced608cee43397007671a721f646035_Traceguids
0x18000dbba  mov     ecx, 404h
0x18000dbbf  mov     r9d, eax
0x18000dbc2  call    WPP_SF_d
0x18000dbc7  mov     eax, ebx
0x18000dbc9  add     rsp, 60h
0x18000dbcd  pop     r15
0x18000dbcf  pop     r14
0x18000dbd1  pop     r12
0x18000dbd3  pop     rdi
0x18000dbd4  pop     rsi
0x18000dbd5  pop     rbp
0x18000dbd6  pop     rbx
0x18000dbd7  retn
```
