# DhcpNotifyConfigChangeEx

- ea: `0x18000dbe0`
- end: `0x18000dd20`
- name: `DhcpNotifyConfigChangeEx`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000db10`

## callees

- `0x180002620`
- `0x18000bcc0`
- `0x18000dbe0`
- `0x18000f090`
- `0x18000f2a0`
- `0x180011260`
- `0x1800121e0`
- `0x180012230`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000dc2a`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000dc2a`

## pseudocode

```c
__int64 __fastcall DhcpNotifyConfigChangeEx(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        int a7,
        char a8)
{
  int v9; // r15d
  int v12; // r12d
  int v13; // ebp
  int v14; // esi
  LPWSTR CommandLineW; // rax
  int v16; // edx
  int v17; // ecx
  int v18; // r8d
  unsigned int refreshed; // ebx
  __int64 v21; // [rsp+90h] [rbp+8h] BYREF

  v21 = 0;
  v9 = a3;
  v12 = a7;
  v13 = a6;
  v14 = a5;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SSldDDLLS(v17, v16, v18, a1, a2, v9, a4, v14, v13, v12, a8, (__int64)CommandLineW);
  }
  if ( a1 || !a2 )
    goto LABEL_15;
  if ( v12 || v9 )
  {
    refreshed = 50;
    goto LABEL_16;
  }
  if ( a4 != 0xFFFF || v13 && v14 )
  {
    refreshed = DhcpAdapterNameToIfId(a2, &v21);
    if ( !refreshed )
    {
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
        WPP_SF_J(a1, 13, WPP_bced608cee43397007671a721f646035_Traceguids, v21);
      refreshed = DhcpStaticRefreshParams(a2);
      ForceNetbtRegistryRead(a2);
      NetBTNotifyRegChanges(a2);
    }
  }
  else
  {
LABEL_15:
    refreshed = 87;
  }
LABEL_16:
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_DJ(a1, a2, a3, refreshed, v21);
  return refreshed;
}

```

## disassembly

```asm
0x18000dbe0  mov     rax, rsp
0x18000dbe3  mov     [rax+10h], rbx
0x18000dbe7  mov     [rax+18h], rbp
0x18000dbeb  push    rsi
0x18000dbec  push    rdi
0x18000dbed  push    r12
0x18000dbef  push    r14
0x18000dbf1  push    r15
0x18000dbf3  sub     rsp, 60h
0x18000dbf7  mov     r14d, r9d
0x18000dbfa  mov     qword ptr [rax+8], 0
0x18000dc02  mov     r15d, r8d
0x18000dc05  mov     rdi, rdx
0x18000dc08  mov     rbx, rcx
0x18000dc0b  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000dc12  mov     r12d, [rsp+88h+arg_30]
0x18000dc1a  mov     ebp, [rsp+88h+arg_28]
0x18000dc21  mov     esi, [rsp+88h+arg_20]
0x18000dc28  jz      short loc_18000DC64
0x18000dc2a  call    cs:__imp_GetCommandLineW
0x18000dc30  mov     [rsp+88h+var_30], rax
0x18000dc35  mov     r9, rbx
0x18000dc38  mov     eax, [rsp+88h+arg_38]
0x18000dc3f  mov     [rsp+88h+var_38], eax
0x18000dc43  mov     [rsp+88h+var_40], r12d
0x18000dc48  mov     [rsp+88h+var_48], ebp
0x18000dc4c  mov     [rsp+88h+var_50], esi
0x18000dc50  mov     [rsp+88h+var_58], r14d
0x18000dc55  mov     [rsp+88h+var_60], r15d
0x18000dc5a  mov     [rsp+88h+var_68], rdi
0x18000dc5f  call    WPP_SF_SSldDDLLS
0x18000dc64  test    rbx, rbx
0x18000dc67  jnz     short loc_18000DCE2
0x18000dc69  test    rdi, rdi
0x18000dc6c  jz      short loc_18000DCE2
0x18000dc6e  test    r12d, r12d
0x18000dc71  jnz     short loc_18000DCDB
0x18000dc73  test    r15d, r15d
0x18000dc76  jnz     short loc_18000DCDB
0x18000dc78  cmp     r14d, 0FFFFh
0x18000dc7f  jnz     short loc_18000DC89
0x18000dc81  test    ebp, ebp
0x18000dc83  jz      short loc_18000DCE2
0x18000dc85  test    esi, esi
0x18000dc87  jz      short loc_18000DCE2
0x18000dc89  lea     rdx, [rsp+88h+arg_0]
0x18000dc91  mov     rcx, rdi
0x18000dc94  call    DhcpAdapterNameToIfId
0x18000dc99  mov     ebx, eax
0x18000dc9b  test    eax, eax
0x18000dc9d  jnz     short loc_18000DCE7
0x18000dc9f  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000dca6  jz      short loc_18000DCBF
0x18000dca8  mov     r9, [rsp+88h+arg_0]
0x18000dcb0  lea     edx, [rax+0Dh]
0x18000dcb3  lea     r8, WPP_bced608cee43397007671a721f646035_Traceguids
0x18000dcba  call    WPP_SF_J
0x18000dcbf  mov     rcx, rdi
0x18000dcc2  call    DhcpStaticRefreshParams
0x18000dcc7  mov     rcx, rdi
0x18000dcca  mov     ebx, eax
0x18000dccc  call    ForceNetbtRegistryRead
0x18000dcd1  mov     rcx, rdi
0x18000dcd4  call    NetBTNotifyRegChanges
0x18000dcd9  jmp     short loc_18000DCE7
0x18000dcdb  mov     ebx, 32h ; '2'
0x18000dce0  jmp     short loc_18000DCE7
0x18000dce2  mov     ebx, 57h ; 'W'
0x18000dce7  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000dcee  jz      short loc_18000DD05
0x18000dcf0  mov     rax, [rsp+88h+arg_0]
0x18000dcf8  mov     r9d, ebx
0x18000dcfb  mov     [rsp+88h+var_68], rax
0x18000dd00  call    WPP_SF_DJ
0x18000dd05  lea     r11, [rsp+88h+var_28]
0x18000dd0a  mov     eax, ebx
0x18000dd0c  mov     rbx, [r11+38h]
0x18000dd10  mov     rbp, [r11+40h]
0x18000dd14  mov     rsp, r11
0x18000dd17  pop     r15
0x18000dd19  pop     r14
0x18000dd1b  pop     r12
0x18000dd1d  pop     rdi
0x18000dd1e  pop     rsi
0x18000dd1f  retn
```
