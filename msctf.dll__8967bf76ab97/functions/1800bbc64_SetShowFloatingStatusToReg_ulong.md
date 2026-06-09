# SetShowFloatingStatusToReg(ulong)

- ea: `0x1800bbc64`
- end: `0x1800bbdf9`
- name: `?SetShowFloatingStatusToReg@@YAJK@Z`
- size: `405`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180063310`

## callees

- `0x180053824`
- `0x1800539d8`
- `0x1800bbc64`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbd06`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbd51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbd8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbdcd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbd06`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbd51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbd8e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800bbdcd`

## pseudocode

```c
__int64 __fastcall SetShowFloatingStatusToReg(__int16 a1, __int64 a2, __int64 a3, unsigned __int16 *a4)
{
  unsigned int v5; // ebx
  HKEY v6; // rdi
  DWORD lpData; // [rsp+20h] [rbp-30h]
  struct _SECURITY_ATTRIBUTES *v9; // [rsp+30h] [rbp-20h]
  unsigned int *v10; // [rsp+38h] [rbp-18h]
  void **v11; // [rsp+40h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-8h]
  int Data; // [rsp+78h] [rbp+28h] BYREF

  hKey = 0;
  v11 = &CPreloadRegKey::`vftable';
  if ( !(unsigned int)CMyRegKey::Create(
                        (CMyRegKey *)&v11,
                        HKEY_CURRENT_USER,
                        L"SOFTWARE\\Microsoft\\CTF\\LangBar\\",
                        a4,
                        lpData,
                        0x2001Fu,
                        v9,
                        v10) )
  {
    v6 = hKey;
    if ( (a1 & 1) != 0 )
    {
      Data = 0;
    }
    else if ( (a1 & 8) != 0 )
    {
      Data = 3;
    }
    else
    {
      if ( (a1 & 0x800) == 0 )
        goto LABEL_10;
      Data = 4;
    }
    RegSetValueExW(hKey, L"ShowStatus", 0, 4u, (const BYTE *)&Data, 4u);
LABEL_10:
    if ( (a1 & 0x10) != 0 )
    {
      Data = 255;
    }
    else if ( (a1 & 0x20) != 0 )
    {
      Data = 128;
    }
    else
    {
      if ( (a1 & 0x40) == 0 )
        goto LABEL_17;
      Data = 64;
    }
    RegSetValueExW(v6, L"Transparency", 0, 4u, (const BYTE *)&Data, 4u);
LABEL_17:
    if ( (a1 & 0x80u) == 0 )
    {
      if ( (a1 & 0x100) == 0 )
        goto LABEL_22;
      Data = 0;
    }
    else
    {
      Data = 1;
    }
    RegSetValueExW(v6, L"Label", 0, 4u, (const BYTE *)&Data, 4u);
LABEL_22:
    if ( (a1 & 0x200) != 0 )
    {
      Data = 1;
    }
    else
    {
      if ( (a1 & 0x400) == 0 )
      {
LABEL_27:
        v5 = 0;
        goto LABEL_28;
      }
      Data = 0;
    }
    RegSetValueExW(v6, L"ExtraIconsOnMinimized", 0, 4u, (const BYTE *)&Data, 4u);
    goto LABEL_27;
  }
  v5 = -2147467259;
LABEL_28:
  v11 = &CPreloadRegKey::`vftable';
  CInputDllRegKey::Close((CInputDllRegKey *)&v11);
  return v5;
}

```

## disassembly

```asm
0x1800bbc64  mov     [rsp-18h+arg_0], rbx
0x1800bbc69  mov     [rsp-18h+arg_10], rsi
0x1800bbc6e  push    rbp
0x1800bbc6f  push    rdi
0x1800bbc70  push    r12
0x1800bbc72  mov     rbp, rsp
0x1800bbc75  sub     rsp, 50h
0x1800bbc79  mov     ebx, ecx
0x1800bbc7b  mov     [rbp+hKey], 0
0x1800bbc83  lea     r12, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x1800bbc8a  mov     [rsp+50h+cbData], 2001Fh; unsigned int
0x1800bbc92  lea     rcx, [rbp+var_10]; this
0x1800bbc96  mov     [rbp+var_10], r12
0x1800bbc9a  lea     r8, ?c_szLangBarKey@@3QBGB; "SOFTWARE\\Microsoft\\CTF\\LangBar\\"
0x1800bbca1  mov     rdx, 0FFFFFFFF80000001h; hKey
0x1800bbca8  call    ?Create@CMyRegKey@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; CMyRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800bbcad  test    eax, eax
0x1800bbcaf  jz      short loc_1800BBCBB
0x1800bbcb1  mov     ebx, 80004005h
0x1800bbcb6  jmp     loc_1800BBDD5
0x1800bbcbb  mov     rdi, [rbp+hKey]
0x1800bbcbf  mov     esi, 4
0x1800bbcc4  test    bl, 1
0x1800bbcc7  jz      short loc_1800BBCD2
0x1800bbcc9  mov     [rbp+Data], 0
0x1800bbcd0  jmp     short loc_1800BBCE9
0x1800bbcd2  test    bl, 8
0x1800bbcd5  jz      short loc_1800BBCE0
0x1800bbcd7  mov     [rbp+Data], 3
0x1800bbcde  jmp     short loc_1800BBCE9
0x1800bbce0  bt      ebx, 0Bh
0x1800bbce4  jnb     short loc_1800BBD0C
0x1800bbce6  mov     [rbp+Data], esi
0x1800bbce9  lea     rax, [rbp+Data]
0x1800bbced  mov     [rsp+50h+cbData], esi; cbData
0x1800bbcf1  mov     r9d, esi; dwType
0x1800bbcf4  mov     [rsp+50h+lpData], rax; lpData
0x1800bbcf9  xor     r8d, r8d; Reserved
0x1800bbcfc  lea     rdx, ?c_szShowStatus@@3QBGB; "ShowStatus"
0x1800bbd03  mov     rcx, rdi; hKey
0x1800bbd06  call    cs:__imp_RegSetValueExW
0x1800bbd0c  test    bl, 10h
0x1800bbd0f  jz      short loc_1800BBD1A
0x1800bbd11  mov     [rbp+Data], 0FFh
0x1800bbd18  jmp     short loc_1800BBD34
0x1800bbd1a  test    bl, 20h
0x1800bbd1d  jz      short loc_1800BBD28
0x1800bbd1f  mov     [rbp+Data], 80h
0x1800bbd26  jmp     short loc_1800BBD34
0x1800bbd28  test    bl, 40h
0x1800bbd2b  jz      short loc_1800BBD57
0x1800bbd2d  mov     [rbp+Data], 40h ; '@'
0x1800bbd34  lea     rax, [rbp+Data]
0x1800bbd38  mov     [rsp+50h+cbData], esi; cbData
0x1800bbd3c  mov     r9d, esi; dwType
0x1800bbd3f  mov     [rsp+50h+lpData], rax; lpData
0x1800bbd44  xor     r8d, r8d; Reserved
0x1800bbd47  lea     rdx, ?c_szTransparency@@3QBGB; "Transparency"
0x1800bbd4e  mov     rcx, rdi; hKey
0x1800bbd51  call    cs:__imp_RegSetValueExW
0x1800bbd57  test    bl, bl
0x1800bbd59  jns     short loc_1800BBD64
0x1800bbd5b  mov     [rbp+Data], 1
0x1800bbd62  jmp     short loc_1800BBD71
0x1800bbd64  bt      ebx, 8
0x1800bbd68  jnb     short loc_1800BBD94
0x1800bbd6a  mov     [rbp+Data], 0
0x1800bbd71  lea     rax, [rbp+Data]
0x1800bbd75  mov     [rsp+50h+cbData], esi; cbData
0x1800bbd79  mov     r9d, esi; dwType
0x1800bbd7c  mov     [rsp+50h+lpData], rax; lpData
0x1800bbd81  xor     r8d, r8d; Reserved
0x1800bbd84  lea     rdx, ?c_szLabel@@3QBGB; "Label"
0x1800bbd8b  mov     rcx, rdi; hKey
0x1800bbd8e  call    cs:__imp_RegSetValueExW
0x1800bbd94  bt      ebx, 9
0x1800bbd98  jnb     short loc_1800BBDA3
0x1800bbd9a  mov     [rbp+Data], 1
0x1800bbda1  jmp     short loc_1800BBDB0
0x1800bbda3  bt      ebx, 0Ah
0x1800bbda7  jnb     short loc_1800BBDD3
0x1800bbda9  mov     [rbp+Data], 0
0x1800bbdb0  lea     rax, [rbp+Data]
0x1800bbdb4  mov     [rsp+50h+cbData], esi; cbData
0x1800bbdb8  mov     r9d, esi; dwType
0x1800bbdbb  mov     [rsp+50h+lpData], rax; lpData
0x1800bbdc0  xor     r8d, r8d; Reserved
0x1800bbdc3  lea     rdx, ?c_szExtraIconsOnMinimized@@3QBGB; "ExtraIconsOnMinimized"
0x1800bbdca  mov     rcx, rdi; hKey
0x1800bbdcd  call    cs:__imp_RegSetValueExW
0x1800bbdd3  xor     ebx, ebx
0x1800bbdd5  lea     rcx, [rbp+var_10]; this
0x1800bbdd9  mov     [rbp+var_10], r12
0x1800bbddd  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x1800bbde2  lea     r11, [rsp+50h+var_s0]
0x1800bbde7  mov     eax, ebx
0x1800bbde9  mov     rbx, [r11+20h]
0x1800bbded  mov     rsi, [r11+30h]
0x1800bbdf1  mov     rsp, r11
0x1800bbdf4  pop     r12
0x1800bbdf6  pop     rdi
0x1800bbdf7  pop     rbp
0x1800bbdf8  retn
```
