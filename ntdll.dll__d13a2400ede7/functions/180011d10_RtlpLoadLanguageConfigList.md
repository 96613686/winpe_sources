# RtlpLoadLanguageConfigList

- ea: `0x180011d10`
- end: `0x180012283`
- name: `RtlpLoadLanguageConfigList`
- size: `1395`
- prototype: ``
- caller_count: `4`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e160`
- `0x180010320`
- `0x180071960`
- `0x1800da9a0`

## callees

- `0x180010770`
- `0x180010870`
- `0x180010b80`
- `0x180011d10`
- `0x18001228c`
- `0x1800122d0`
- `0x1800125e4`
- `0x180012664`
- `0x180012c34`
- `0x18001861c`
- `0x18001b984`
- `0x18012d320`
- `0x18015ecc0`
- `0x18015ed20`
- `0x18015edc0`
- `0x180164280`

## string_xrefs

- `0x180011d5f`: `\Registry\Machine\Software\Policies\Microsoft\MUI\Settings`
- `0x180011ff8`: `Control Panel\Desktop\LanguageConfiguration`
- `0x18001212a`: `Control Panel\Desktop\MuiCached\MachineLanguageConfiguration`
- `0x18001219d`: `\Registry\Machine\System\CurrentControlSet\Control\MUI\Settings\LanguageConfiguration`

## pseudocode

```c
__int64 __fastcall RtlpLoadLanguageConfigList(unsigned int a1, __int64 *a2, __int64 a3)
{
  int v3; // ebx
  __int64 v7; // r15
  size_t v8; // rax
  int v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  int v12; // eax
  HANDLE v13; // rbx
  int v14; // r12d
  size_t v15; // rax
  __int64 Heap_0; // r13
  int v17; // ebx
  char v18; // al
  size_t v19; // rax
  size_t v20; // rax
  int v21; // eax
  __int64 LanguageConfigList; // rax
  size_t v24; // rax
  size_t v25; // rax
  int v26; // eax
  unsigned int v27; // eax
  HANDLE Handle; // [rsp+30h] [rbp-59h] BYREF
  __int128 v29; // [rsp+38h] [rbp-51h] BYREF
  HANDLE v30; // [rsp+48h] [rbp-41h] BYREF
  int v31; // [rsp+50h] [rbp-39h] BYREF
  __int64 v32; // [rsp+58h] [rbp-31h] BYREF
  HANDLE v33; // [rsp+60h] [rbp-29h]
  __int128 *v34; // [rsp+68h] [rbp-21h]
  __int64 v35; // [rsp+70h] [rbp-19h]
  __int128 v36; // [rsp+78h] [rbp-11h]
  int v37; // [rsp+88h] [rbp-1h] BYREF
  HANDLE v38; // [rsp+90h] [rbp+7h] BYREF
  _QWORD v39[3]; // [rsp+98h] [rbp+Fh] BYREF
  char v40; // [rsp+F8h] [rbp+6Fh] BYREF
  __int16 v41; // [rsp+108h] [rbp+7Fh] BYREF

  v3 = 0;
  v40 = 0;
  v41 = 0;
  Handle = 0;
  v38 = 0;
  v30 = 0;
  v29 = 0;
  if ( !a2 || !a3 )
  {
    v7 = 0;
    v3 = -1073741811;
LABEL_48:
    if ( a2 && *a2 != v7 )
    {
      if ( *a2 )
        RtlpMuiRegFreeLanguageConfigList();
      *a2 = v7;
    }
    return (unsigned int)v3;
  }
  v7 = *a2;
  *((_QWORD *)&v29 + 1) = L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\MUI\\Settings";
  v8 = 2 * wcslen(L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\MUI\\Settings");
  v32 = 48;
  v35 = 64;
  Handle = 0;
  v33 = 0;
  if ( v8 >= 0xFFFE )
    LOWORD(v8) = -4;
  LOWORD(v29) = v8;
  WORD1(v29) = v8 + 2;
  v34 = &v29;
  v36 = 0;
  if ( (int)NtOpenKey(&Handle, 131097, &v32) >= 0 )
  {
    v3 = RtlpLoadPolicyLanguageSpec(Handle, a3, &v40, &v41);
    if ( v3 >= 0 )
      goto LABEL_38;
    if ( a1 != 8 )
      goto LABEL_23;
    v13 = Handle;
    v14 = -1;
    v37 = -1;
    if ( !Handle )
      goto LABEL_23;
    v39[0] = 0;
    v39[1] = L"MachineUILock";
    v15 = 2 * wcslen(L"MachineUILock");
    v31 = 0;
    if ( v15 >= 0xFFFE )
      LOWORD(v15) = -4;
    LOWORD(v39[0]) = v15;
    WORD1(v39[0]) = v15 + 2;
    Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, a1, 16);
    if ( !Heap_0 )
      goto LABEL_23;
    v17 = NtQueryValueKey(v13, v39, 2, Heap_0, 16, &v31);
    if ( v17 >= 0 )
    {
      v27 = *(_DWORD *)(Heap_0 + 8);
      if ( v27 > 4 )
      {
        v17 = -2147483643;
      }
      else
      {
        memmove(&v37, (const void *)(Heap_0 + 12), v27);
        v14 = v37;
      }
    }
    RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, Heap_0);
    if ( v17 >= 0 )
    {
      if ( v14 == 1 )
      {
        v18 = 1;
LABEL_20:
        if ( !v17 && v18 == 1 )
          a1 = 4;
        goto LABEL_23;
      }
      if ( v14 )
      {
LABEL_23:
        NtClose(Handle);
        v3 = 0;
        Handle = 0;
        goto LABEL_6;
      }
    }
    v18 = 0;
    goto LABEL_20;
  }
LABEL_6:
  v9 = GetGlobalizationUserModelType() - 1;
  if ( !v9 )
  {
    v12 = RtlOpenCurrentUser(0x2000000, &v30);
LABEL_25:
    if ( v12 >= 0 )
      goto LABEL_27;
    goto LABEL_26;
  }
  v11 = v9 - 1;
  if ( !v11 )
  {
    v12 = OpenGlobalizationUserSettingsKey_ForSingleUserModel(0x2000000, &v30);
    goto LABEL_25;
  }
  if ( v11 == 1 )
  {
    v31 = 0;
    v12 = OpenGlobalizationUserSettingsKey_ForMua(0x2000000, v10, &v30, &v31);
    goto LABEL_25;
  }
LABEL_26:
  v30 = 0;
LABEL_27:
  if ( a1 == 8 )
  {
    if ( !v30 )
      goto LABEL_38;
    *(_QWORD *)&v29 = 0;
    *((_QWORD *)&v29 + 1) = L"Software\\Policies\\Microsoft\\Control Panel\\Desktop";
    v19 = 2 * wcslen(L"Software\\Policies\\Microsoft\\Control Panel\\Desktop");
    v32 = 48;
    v35 = 64;
    v38 = 0;
    if ( v19 >= 0xFFFE )
      LOWORD(v19) = -4;
    LOWORD(v29) = v19;
    WORD1(v29) = v19 + 2;
    v33 = v30;
    v34 = &v29;
    v36 = 0;
    if ( (int)NtOpenKey(&v38, 131097, &v32) >= 0 )
    {
      v3 = RtlpLoadPolicyLanguageSpec(v38, a3, &v40, &v41);
      if ( v3 >= 0 )
        goto LABEL_38;
      v3 = 0;
    }
    *(_QWORD *)&v29 = 0;
    *((_QWORD *)&v29 + 1) = L"Control Panel\\Desktop\\LanguageConfiguration";
    v20 = 2 * wcslen(L"Control Panel\\Desktop\\LanguageConfiguration");
    v32 = 48;
    v35 = 64;
    Handle = 0;
    if ( v20 >= 0xFFFE )
      LOWORD(v20) = -4;
    LOWORD(v29) = v20;
    WORD1(v29) = v20 + 2;
    v33 = v30;
    v34 = &v29;
    v36 = 0;
    v21 = NtOpenKey(&Handle, 131097, &v32);
    if ( v21 >= 0 )
      goto LABEL_37;
    if ( v21 != -1073741772 )
      v3 = v21;
  }
  else
  {
    if ( a1 != 4 )
      goto LABEL_37;
    if ( v30 )
    {
      *(_QWORD *)&v29 = 0;
      *((_QWORD *)&v29 + 1) = L"Control Panel\\Desktop\\MuiCached\\MachineLanguageConfiguration";
      v24 = 2 * wcslen(L"Control Panel\\Desktop\\MuiCached\\MachineLanguageConfiguration");
      v32 = 48;
      v35 = 64;
      Handle = 0;
      if ( v24 >= 0xFFFE )
        LOWORD(v24) = -4;
      LOWORD(v29) = v24;
      WORD1(v29) = v24 + 2;
      v33 = v30;
      v34 = &v29;
      v36 = 0;
      if ( (int)NtOpenKey(&Handle, 131097, &v32) >= 0 )
        goto LABEL_37;
    }
    *(_QWORD *)&v29 = 0;
    *((_QWORD *)&v29 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MUI\\Settings\\LanguageConfiguration";
    v25 = 2 * wcslen(L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MUI\\Settings\\LanguageConfiguration");
    v32 = 48;
    v35 = 64;
    Handle = 0;
    if ( v25 >= 0xFFFE )
      LOWORD(v25) = -4;
    v33 = 0;
    LOWORD(v29) = v25;
    WORD1(v29) = v25 + 2;
    v34 = &v29;
    v36 = 0;
    v26 = NtOpenKey(&Handle, 131097, &v32);
    v3 = v26;
    if ( v26 >= 0 )
    {
LABEL_37:
      v3 = RtlpPopulateLanguageConfigList(Handle, a2, a3);
      goto LABEL_38;
    }
    if ( v26 == -1073741772 )
      v3 = 0;
  }
LABEL_38:
  if ( Handle )
    NtClose(Handle);
  if ( v38 )
    NtClose(v38);
  if ( v30 )
    NtClose(v30);
  if ( v3 < 0 )
    goto LABEL_48;
  if ( *a2 )
    return (unsigned int)v3;
  LanguageConfigList = RtlpMuiRegCreateLanguageConfigList(1);
  *a2 = LanguageConfigList;
  if ( LanguageConfigList )
    return (unsigned int)v3;
  *a2 = v7;
  return 3221225495LL;
}

```

## disassembly

```asm
0x180011d10  push    rbp
0x180011d12  push    rbx
0x180011d13  push    rsi
0x180011d14  push    rdi
0x180011d15  push    r14
0x180011d17  push    r15
0x180011d19  lea     rbp, [rsp-2Fh]
0x180011d1e  sub     rsp, 0B8h
0x180011d25  xor     ebx, ebx
0x180011d27  mov     [rbp+57h+arg_8], 0
0x180011d2b  mov     [rbp+57h+arg_18], bx
0x180011d2f  xorps   xmm0, xmm0
0x180011d32  mov     [rbp+57h+Handle], rbx
0x180011d36  mov     r14, r8
0x180011d39  mov     [rbp+57h+var_50], rbx
0x180011d3d  mov     rdi, rdx
0x180011d40  mov     [rbp+57h+var_98], rbx
0x180011d44  mov     esi, ecx
0x180011d46  movups  [rbp+57h+var_A8], xmm0
0x180011d4a  test    rdx, rdx
0x180011d4d  jz      loc_1800120CB
0x180011d53  test    r8, r8
0x180011d56  jz      loc_1800120CB
0x180011d5c  mov     r15, [rdx]
0x180011d5f  lea     rcx, aRegistryMachin_23; "\\Registry\\Machine\\Software\\Policies"...
0x180011d66  mov     qword ptr [rbp+57h+var_A8+8], rcx
0x180011d6a  mov     [rsp+0E0h+var_30], r13
0x180011d72  call    wcslen
0x180011d77  add     rax, rax
0x180011d7a  mov     [rbp+57h+var_88], 30h ; '0'
0x180011d82  cmp     rax, 0FFFEh
0x180011d88  mov     [rbp+57h+var_70], 40h ; '@'
0x180011d90  xorps   xmm0, xmm0
0x180011d93  mov     [rbp+57h+Handle], rbx
0x180011d97  mov     r13d, 0FFFCh
0x180011d9d  mov     [rbp+57h+var_80], rbx
0x180011da1  cmovnb  rax, r13
0x180011da5  lea     r8, [rbp+57h+var_88]
0x180011da9  mov     word ptr [rbp+57h+var_A8], ax
0x180011dad  lea     rcx, [rbp+57h+Handle]
0x180011db1  add     ax, 2
0x180011db5  mov     edx, 20019h
0x180011dba  mov     word ptr [rbp+57h+var_A8+2], ax
0x180011dbe  lea     rax, [rbp+57h+var_A8]
0x180011dc2  mov     [rbp+57h+var_78], rax
0x180011dc6  movdqu  [rbp+57h+var_68], xmm0
0x180011dcb  call    NtOpenKey
0x180011dd0  test    eax, eax
0x180011dd2  jns     short loc_180011E0E
0x180011dd4  call    GetGlobalizationUserModelType
0x180011dd9  sub     eax, 1
0x180011ddc  jz      loc_180012220
0x180011de2  sub     eax, 1
0x180011de5  jz      loc_180011F3F
0x180011deb  cmp     eax, 1
0x180011dee  jnz     loc_180011F51
0x180011df4  lea     r9, [rbp+57h+var_90]
0x180011df8  mov     [rbp+57h+var_90], ebx
0x180011dfb  lea     r8, [rbp+57h+var_98]
0x180011dff  mov     ecx, 2000000h
0x180011e04  call    OpenGlobalizationUserSettingsKey_ForMua
0x180011e09  jmp     loc_180011F4D
0x180011e0e  mov     rcx, [rbp+57h+Handle]
0x180011e12  lea     r9, [rbp+57h+arg_18]
0x180011e16  lea     r8, [rbp+57h+arg_8]
0x180011e1a  mov     rdx, r14
0x180011e1d  call    RtlpLoadPolicyLanguageSpec
0x180011e22  mov     ebx, eax
0x180011e24  test    eax, eax
0x180011e26  jns     loc_18001207C
0x180011e2c  cmp     esi, 8
0x180011e2f  jnz     loc_180011F2B
0x180011e35  mov     rbx, [rbp+57h+Handle]
0x180011e39  mov     [rsp+0E0h+arg_0], r12
0x180011e41  mov     r12d, 0FFFFFFFFh
0x180011e47  mov     [rbp+57h+var_58], r12d
0x180011e4b  test    rbx, rbx
0x180011e4e  jz      loc_180011F23
0x180011e54  lea     rcx, aMachineuilock; "MachineUILock"
0x180011e5b  mov     [rbp+57h+var_48], 0
0x180011e63  mov     [rbp+57h+var_40], rcx
0x180011e67  call    wcslen
0x180011e6c  add     rax, rax
0x180011e6f  mov     [rbp+57h+var_90], 0
0x180011e76  cmp     rax, 0FFFEh
0x180011e7c  mov     edx, esi
0x180011e7e  mov     r8d, 10h
0x180011e84  cmovnb  rax, r13
0x180011e88  mov     word ptr [rbp+57h+var_48], ax
0x180011e8c  add     ax, 2
0x180011e90  mov     word ptr [rbp+57h+var_48+2], ax
0x180011e94  mov     rcx, gs:60h
0x180011e9d  mov     rcx, [rcx+30h]
0x180011ea1  call    RtlAllocateHeap_0
0x180011ea6  mov     r13, rax
0x180011ea9  test    rax, rax
0x180011eac  jz      loc_18001226C
0x180011eb2  lea     rax, [rbp+57h+var_90]
0x180011eb6  mov     r9, r13
0x180011eb9  mov     [rsp+0E0h+var_B8], rax
0x180011ebe  lea     rdx, [rbp+57h+var_48]
0x180011ec2  mov     r8d, 2
0x180011ec8  mov     [rsp+0E0h+var_C0], 10h
0x180011ed0  mov     rcx, rbx
0x180011ed3  call    NtQueryValueKey
0x180011ed8  mov     ebx, eax
0x180011eda  test    eax, eax
0x180011edc  jns     loc_180012233
0x180011ee2  mov     rcx, gs:60h
0x180011eeb  mov     r8, r13
0x180011eee  xor     edx, edx
0x180011ef0  mov     rcx, [rcx+30h]
0x180011ef4  call    RtlFreeHeap_0
0x180011ef9  test    ebx, ebx
0x180011efb  js      loc_18001227C
0x180011f01  cmp     r12d, 1
0x180011f05  jnz     loc_180012277
0x180011f0b  movzx   eax, r12b
0x180011f0f  mov     r13d, 0FFFCh
0x180011f15  test    ebx, ebx
0x180011f17  jnz     short loc_180011F23
0x180011f19  cmp     al, 1
0x180011f1b  mov     ecx, 4
0x180011f20  cmovz   esi, ecx
0x180011f23  mov     r12, [rsp+0E0h+arg_0]
0x180011f2b  mov     rcx, [rbp+57h+Handle]; Handle
0x180011f2f  call    NtClose
0x180011f34  xor     ebx, ebx
0x180011f36  mov     [rbp+57h+Handle], rbx
0x180011f3a  jmp     loc_180011DD4
0x180011f3f  lea     rdx, [rbp+57h+var_98]
0x180011f43  mov     ecx, 2000000h
0x180011f48  call    OpenGlobalizationUserSettingsKey_ForSingleUserModel
0x180011f4d  test    eax, eax
0x180011f4f  jns     short loc_180011F55
0x180011f51  mov     [rbp+57h+var_98], rbx
0x180011f55  cmp     esi, 8
0x180011f58  jnz     loc_18001211A
0x180011f5e  cmp     [rbp+57h+var_98], 0
0x180011f63  jz      loc_18001207C
0x180011f69  lea     rcx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Control "...
0x180011f70  mov     qword ptr [rbp+57h+var_A8], rbx
0x180011f74  mov     qword ptr [rbp+57h+var_A8+8], rcx
0x180011f78  call    wcslen
0x180011f7d  add     rax, rax
0x180011f80  mov     [rbp+57h+var_88], 30h ; '0'
0x180011f88  cmp     rax, 0FFFEh
0x180011f8e  mov     [rbp+57h+var_70], 40h ; '@'
0x180011f96  xorps   xmm0, xmm0
0x180011f99  mov     [rbp+57h+var_50], rbx
0x180011f9d  cmovnb  rax, r13
0x180011fa1  lea     r8, [rbp+57h+var_88]
0x180011fa5  mov     word ptr [rbp+57h+var_A8], ax
0x180011fa9  lea     rcx, [rbp+57h+var_50]
0x180011fad  add     ax, 2
0x180011fb1  mov     edx, 20019h
0x180011fb6  mov     word ptr [rbp+57h+var_A8+2], ax
0x180011fba  mov     rax, [rbp+57h+var_98]
0x180011fbe  mov     [rbp+57h+var_80], rax
0x180011fc2  lea     rax, [rbp+57h+var_A8]
0x180011fc6  mov     [rbp+57h+var_78], rax
0x180011fca  movdqu  [rbp+57h+var_68], xmm0
0x180011fcf  call    NtOpenKey
0x180011fd4  test    eax, eax
0x180011fd6  js      short loc_180011FF8
0x180011fd8  mov     rcx, [rbp+57h+var_50]
0x180011fdc  lea     r9, [rbp+57h+arg_18]
0x180011fe0  lea     r8, [rbp+57h+arg_8]
0x180011fe4  mov     rdx, r14
0x180011fe7  call    RtlpLoadPolicyLanguageSpec
0x180011fec  mov     ebx, eax
0x180011fee  test    eax, eax
0x180011ff0  jns     loc_18001207C
0x180011ff6  xor     ebx, ebx
0x180011ff8  lea     rcx, aControlPanelDe_0; "Control Panel\\Desktop\\LanguageConfigu"...
0x180011fff  mov     qword ptr [rbp+57h+var_A8], rbx
0x180012003  mov     qword ptr [rbp+57h+var_A8+8], rcx
0x180012007  call    wcslen
0x18001200c  add     rax, rax
0x18001200f  mov     [rbp+57h+var_88], 30h ; '0'
0x180012017  cmp     rax, 0FFFEh
0x18001201d  mov     [rbp+57h+var_70], 40h ; '@'
0x180012025  xorps   xmm0, xmm0
0x180012028  mov     [rbp+57h+Handle], rbx
0x18001202c  cmovnb  rax, r13
0x180012030  lea     r8, [rbp+57h+var_88]
0x180012034  mov     word ptr [rbp+57h+var_A8], ax
0x180012038  lea     rcx, [rbp+57h+Handle]
0x18001203c  add     ax, 2
0x180012040  mov     edx, 20019h
0x180012045  mov     word ptr [rbp+57h+var_A8+2], ax
0x180012049  mov     rax, [rbp+57h+var_98]
0x18001204d  mov     [rbp+57h+var_80], rax
0x180012051  lea     rax, [rbp+57h+var_A8]
0x180012055  mov     [rbp+57h+var_78], rax
0x180012059  movdqu  [rbp+57h+var_68], xmm0
0x18001205e  call    NtOpenKey
0x180012063  test    eax, eax
0x180012065  js      loc_180012255
0x18001206b  mov     rcx, [rbp+57h+Handle]
0x18001206f  mov     r8, r14
0x180012072  mov     rdx, rdi
0x180012075  call    RtlpPopulateLanguageConfigList
0x18001207a  mov     ebx, eax
0x18001207c  mov     rcx, [rbp+57h+Handle]; Handle
0x180012080  mov     r13, [rsp+0E0h+var_30]
0x180012088  test    rcx, rcx
0x18001208b  jz      short loc_180012092
0x18001208d  call    NtClose
0x180012092  mov     rcx, [rbp+57h+var_50]; Handle
0x180012096  test    rcx, rcx
0x180012099  jz      short loc_1800120A0
0x18001209b  call    NtClose
0x1800120a0  mov     rcx, [rbp+57h+var_98]; Handle
0x1800120a4  test    rcx, rcx
0x1800120a7  jz      short loc_1800120AE
0x1800120a9  call    NtClose
0x1800120ae  test    ebx, ebx
0x1800120b0  js      short loc_1800120D3
0x1800120b2  cmp     qword ptr [rdi], 0
0x1800120b6  jz      short loc_1800120EF
0x1800120b8  mov     eax, ebx
0x1800120ba  add     rsp, 0B8h
0x1800120c1  pop     r15
0x1800120c3  pop     r14
0x1800120c5  pop     rdi
0x1800120c6  pop     rsi
0x1800120c7  pop     rbx
0x1800120c8  pop     rbp
0x1800120c9  retn
0x1800120cb  mov     r15, rbx
0x1800120ce  mov     ebx, 0C000000Dh
0x1800120d3  test    rdi, rdi
0x1800120d6  jz      short loc_1800120B8
0x1800120d8  mov     rcx, [rdi]
0x1800120db  cmp     rcx, r15
0x1800120de  jz      short loc_1800120B8
0x1800120e0  test    rcx, rcx
0x1800120e3  jz      short loc_1800120EA
0x1800120e5  call    RtlpMuiRegFreeLanguageConfigList
0x1800120ea  mov     [rdi], r15
0x1800120ed  jmp     short loc_1800120B8
0x1800120ef  mov     ecx, 1
0x1800120f4  call    RtlpMuiRegCreateLanguageConfigList
0x1800120f9  mov     [rdi], rax
0x1800120fc  test    rax, rax
0x1800120ff  jnz     short loc_1800120B8
0x180012101  mov     [rdi], r15
0x180012104  mov     eax, 0C0000017h
0x180012109  add     rsp, 0B8h
0x180012110  pop     r15
0x180012112  pop     r14
0x180012114  pop     rdi
0x180012115  pop     rsi
0x180012116  pop     rbx
0x180012117  pop     rbp
0x180012118  retn
0x18001211a  cmp     esi, 4
0x18001211d  jnz     loc_18001206B
0x180012123  cmp     [rbp+57h+var_98], 0
0x180012128  jz      short loc_18001219D
0x18001212a  lea     rcx, aControlPanelDe_1; "Control Panel\\Desktop\\MuiCached\\Mach"...
0x180012131  mov     qword ptr [rbp+57h+var_A8], rbx
0x180012135  mov     qword ptr [rbp+57h+var_A8+8], rcx
0x180012139  call    wcslen
0x18001213e  add     rax, rax
0x180012141  mov     [rbp+57h+var_88], 30h ; '0'
0x180012149  cmp     rax, 0FFFEh
0x18001214f  mov     [rbp+57h+var_70], 40h ; '@'
0x180012157  xorps   xmm0, xmm0
0x18001215a  mov     [rbp+57h+Handle], rbx
0x18001215e  cmovnb  rax, r13
0x180012162  lea     r8, [rbp+57h+var_88]
0x180012166  mov     word ptr [rbp+57h+var_A8], ax
0x18001216a  lea     rcx, [rbp+57h+Handle]
0x18001216e  add     ax, 2
0x180012172  mov     edx, 20019h
0x180012177  mov     word ptr [rbp+57h+var_A8+2], ax
0x18001217b  mov     rax, [rbp+57h+var_98]
0x18001217f  mov     [rbp+57h+var_80], rax
0x180012183  lea     rax, [rbp+57h+var_A8]
0x180012187  mov     [rbp+57h+var_78], rax
0x18001218b  movdqu  [rbp+57h+var_68], xmm0
0x180012190  call    NtOpenKey
0x180012195  test    eax, eax
0x180012197  jns     loc_18001206B
0x18001219d  lea     rcx, aRegistryMachin_32; "\\Registry\\Machine\\System\\CurrentCon"...
0x1800121a4  mov     qword ptr [rbp+57h+var_A8], rbx
0x1800121a8  mov     qword ptr [rbp+57h+var_A8+8], rcx
0x1800121ac  call    wcslen
0x1800121b1  add     rax, rax
0x1800121b4  mov     [rbp+57h+var_88], 30h ; '0'
0x1800121bc  cmp     rax, 0FFFEh
0x1800121c2  mov     [rbp+57h+var_70], 40h ; '@'
0x1800121ca  xorps   xmm0, xmm0
0x1800121cd  mov     [rbp+57h+Handle], rbx
0x1800121d1  cmovnb  rax, r13
0x1800121d5  mov     [rbp+57h+var_80], rbx
0x1800121d9  mov     word ptr [rbp+57h+var_A8], ax
0x1800121dd  lea     r8, [rbp+57h+var_88]
  ... truncated ...
```
