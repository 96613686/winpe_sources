# DockingProviders::ForAllProviders(ProviderOperation &)

- ea: `0x180015460`
- end: `0x1800156dd`
- name: `?ForAllProviders@DockingProviders@@AEAAJAEAVProviderOperation@@@Z`
- size: `637`
- prototype: `__int64 __fastcall(DockingProviders *__hidden this, struct ProviderOperation *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800160c0`

## callees

- `0x180001dc8`
- `0x18000c348`
- `0x180015460`
- `0x18001a580`
- `0x18001ca3e`
- `0x18001ca70`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800154c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800154c5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180015557`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180015557`

## string_xrefs

- `0x1800154b7`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\WirelessDocking\DockingProviderDLLs`

## pseudocode

```c
__int64 __fastcall DockingProviders::ForAllProviders(DockingProviders *this, struct ProviderOperation *a2)
{
  HKEY v4; // rbx
  LSTATUS v5; // eax
  signed int v6; // edi
  DWORD v7; // esi
  LSTATUS v8; // eax
  __int64 v9; // rcx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  unsigned __int64 v12; // rcx
  int v13; // eax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v18[2]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[528]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ValueName[264]; // [rsp+270h] [rbp+170h] BYREF

  v4 = 0;
  v18[0] = 0;
  hKey = 0;
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WirelessDocking\\DockingProviderDLLs",
         0,
         0x20019u,
         &hKey);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( v6 < 0 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v11 = 67;
LABEL_32:
        WPP_SF_qD(v10[2], v11, &WPP_664df381f3e33d6bde707323c6216c8b_Traceguids, this, v6);
      }
      goto LABEL_25;
    }
  }
  else
  {
    v4 = hKey;
    v18[0] = hKey;
  }
  v7 = 0;
  memset_0(ValueName, 0, 0x208u);
  memset_0(Data, 0, 0x208u);
  while ( 1 )
  {
    cbData = 518;
    Type = 0;
    LODWORD(hKey) = 259;
    v8 = RegEnumValueW(v4, v7, ValueName, (LPDWORD)&hKey, 0, &Type, Data, &cbData);
    v6 = v8;
    if ( v8 )
    {
      v9 = 0;
      if ( v8 > 0 )
        v6 = (unsigned __int16)v8 | 0x80070000;
      if ( v6 == -2147023267 )
        goto LABEL_27;
    }
    else
    {
      if ( Type != 1 )
        goto LABEL_27;
      v9 = cbData >> 1;
      if ( !(cbData >> 1) )
        goto LABEL_27;
    }
    if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147024637 )
      break;
    if ( (unsigned int)v9 >= 0x104 )
    {
      RegKey::~RegKey((RegKey *)v18);
      return 2147942511LL;
    }
    if ( (_DWORD)v9 )
    {
      ValueName[259] = 0;
      v12 = 2 * v9;
      if ( v12 >= 0x208 )
        _report_rangecheckfailure();
      *(_WORD *)&Data[v12] = 0;
      v13 = (**(__int64 (__fastcall ***)(struct ProviderOperation *, WCHAR *, BYTE *))a2)(a2, ValueName, Data);
      if ( v13 < 0 )
      {
        v6 = v13;
        goto LABEL_25;
      }
    }
    else if ( v6 == -2147024637 )
    {
      RegKey::~RegKey((RegKey *)v18);
      return 0;
    }
LABEL_27:
    ++v7;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v11 = 68;
    goto LABEL_32;
  }
LABEL_25:
  RegKey::~RegKey((RegKey *)v18);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180015460  mov     [rsp-8+arg_10], rbx
0x180015465  mov     [rsp-8+arg_18], rsi
0x18001546a  push    rbp
0x18001546b  push    rdi
0x18001546c  push    r13
0x18001546e  push    r14
0x180015470  push    r15
0x180015472  lea     rbp, [rsp-390h]
0x18001547a  sub     rsp, 490h
0x180015481  mov     rax, cs:__security_cookie
0x180015488  xor     rax, rsp
0x18001548b  mov     [rbp+3B0h+var_30], rax
0x180015492  mov     r15, rdx
0x180015495  mov     r14, rcx
0x180015498  xor     ebx, ebx
0x18001549a  mov     [rsp+4B0h+var_460], rbx
0x18001549f  mov     [rsp+4B0h+hKey], rbx
0x1800154a4  lea     rax, [rsp+4B0h+hKey]
0x1800154a9  mov     [rsp+4B0h+phkResult], rax; phkResult
0x1800154ae  mov     r9d, 20019h; samDesired
0x1800154b4  xor     r8d, r8d; ulOptions
0x1800154b7  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800154be  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800154c5  call    cs:__imp_RegOpenKeyExW
0x1800154cb  mov     edi, eax
0x1800154cd  test    eax, eax
0x1800154cf  jnz     loc_18001557C
0x1800154d5  mov     rbx, [rsp+4B0h+hKey]
0x1800154da  mov     [rsp+4B0h+var_460], rbx
0x1800154df  xor     esi, esi
0x1800154e1  mov     r13d, 208h
0x1800154e7  mov     r8d, r13d; Size
0x1800154ea  xor     edx, edx; Val
0x1800154ec  lea     rcx, [rbp+3B0h+ValueName]; void *
0x1800154f3  call    memset_0
0x1800154f8  mov     r8d, r13d; Size
0x1800154fb  xor     edx, edx; Val
0x1800154fd  lea     rcx, [rsp+4B0h+Data]; void *
0x180015502  call    memset_0
0x180015507  mov     [rsp+4B0h+cbData], 206h
0x18001550f  mov     [rsp+4B0h+Type], 0
0x180015517  mov     dword ptr [rsp+4B0h+hKey], 103h
0x18001551f  lea     rax, [rsp+4B0h+cbData]
0x180015524  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x180015529  lea     rax, [rsp+4B0h+Data]
0x18001552e  mov     [rsp+4B0h+lpData], rax; lpData
0x180015533  lea     rax, [rsp+4B0h+Type]
0x180015538  mov     [rsp+4B0h+lpType], rax; lpType
0x18001553d  mov     [rsp+4B0h+phkResult], 0; lpReserved
0x180015546  lea     r9, [rsp+4B0h+hKey]; lpcchValueName
0x18001554b  lea     r8, [rbp+3B0h+ValueName]; lpValueName
0x180015552  mov     edx, esi; dwIndex
0x180015554  mov     rcx, rbx; hKey
0x180015557  call    cs:__imp_RegEnumValueW
0x18001555d  mov     edi, eax
0x18001555f  test    eax, eax
0x180015561  jnz     short loc_1800155C0
0x180015563  cmp     [rsp+4B0h+Type], 1
0x180015568  jnz     loc_18001564B
0x18001556e  mov     ecx, [rsp+4B0h+cbData]
0x180015572  shr     ecx, 1
0x180015574  jz      loc_18001564B
0x18001557a  jmp     short loc_1800155D7
0x18001557c  jle     short loc_180015587
0x18001557e  movzx   edi, ax
0x180015581  or      edi, 80070000h
0x180015587  test    edi, edi
0x180015589  jns     loc_1800154DF
0x18001558f  lea     rax, WPP_GLOBAL_Control
0x180015596  mov     rcx, cs:WPP_GLOBAL_Control
0x18001559d  cmp     rcx, rax
0x1800155a0  jz      loc_180015635
0x1800155a6  cmp     byte ptr [rcx+19h], 1
0x1800155aa  jb      loc_180015635
0x1800155b0  test    byte ptr [rcx+1Ch], 1
0x1800155b4  jz      short loc_180015635
0x1800155b6  mov     edx, 43h ; 'C'
0x1800155bb  jmp     loc_180015676
0x1800155c0  xor     ecx, ecx
0x1800155c2  test    eax, eax
0x1800155c4  jle     short loc_1800155CF
0x1800155c6  movzx   edi, ax
0x1800155c9  or      edi, 80070000h
0x1800155cf  cmp     edi, 8007065Dh
0x1800155d5  jz      short loc_18001564B
0x1800155d7  mov     edx, 80000000h
0x1800155dc  lea     eax, [rdi+rdx]
0x1800155df  test    edx, eax
0x1800155e1  jnz     short loc_1800155EB
0x1800155e3  cmp     edi, 80070103h
0x1800155e9  jnz     short loc_180015652
0x1800155eb  cmp     ecx, 104h
0x1800155f1  jnb     loc_18001569D
0x1800155f7  test    ecx, ecx
0x1800155f9  jz      short loc_180015643
0x1800155fb  xor     eax, eax
0x1800155fd  mov     [rbp+3B0h+var_3A], ax
0x180015604  add     rcx, rcx
0x180015607  cmp     rcx, r13
0x18001560a  jnb     loc_1800156D7
0x180015610  mov     word ptr [rsp+rcx+4B0h+Data], ax
0x180015615  mov     rax, [r15]
0x180015618  lea     r8, [rsp+4B0h+Data]
0x18001561d  lea     rdx, [rbp+3B0h+ValueName]
0x180015624  mov     rcx, r15
0x180015627  mov     rax, [rax]
0x18001562a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001562f  test    eax, eax
0x180015631  jns     short loc_18001564B
0x180015633  mov     edi, eax
0x180015635  lea     rcx, [rsp+4B0h+var_460]; this
0x18001563a  call    ??1RegKey@@QEAA@XZ; RegKey::~RegKey(void)
0x18001563f  mov     eax, edi
0x180015641  jmp     short loc_1800156AC
0x180015643  cmp     edi, 80070103h
0x180015649  jz      short loc_18001568F
0x18001564b  inc     esi
0x18001564d  jmp     loc_180015507
0x180015652  lea     rax, WPP_GLOBAL_Control
0x180015659  mov     rcx, cs:WPP_GLOBAL_Control
0x180015660  cmp     rcx, rax
0x180015663  jz      short loc_180015635
0x180015665  cmp     byte ptr [rcx+19h], 1
0x180015669  jb      short loc_180015635
0x18001566b  test    byte ptr [rcx+1Ch], 1
0x18001566f  jz      short loc_180015635
0x180015671  mov     edx, 44h ; 'D'
0x180015676  mov     dword ptr [rsp+4B0h+phkResult], edi
0x18001567a  mov     r9, r14
0x18001567d  lea     r8, WPP_664df381f3e33d6bde707323c6216c8b_Traceguids
0x180015684  mov     rcx, [rcx+10h]
0x180015688  call    WPP_SF_qD
0x18001568d  jmp     short loc_180015635
0x18001568f  lea     rcx, [rsp+4B0h+var_460]; this
0x180015694  call    ??1RegKey@@QEAA@XZ; RegKey::~RegKey(void)
0x180015699  xor     eax, eax
0x18001569b  jmp     short loc_1800156AC
0x18001569d  lea     rcx, [rsp+4B0h+var_460]; this
0x1800156a2  call    ??1RegKey@@QEAA@XZ; RegKey::~RegKey(void)
0x1800156a7  mov     eax, 8007006Fh
0x1800156ac  mov     rcx, [rbp+3B0h+var_30]
0x1800156b3  xor     rcx, rsp; StackCookie
0x1800156b6  call    __security_check_cookie
0x1800156bb  lea     r11, [rsp+4B0h+var_20]
0x1800156c3  mov     rbx, [r11+40h]
0x1800156c7  mov     rsi, [r11+48h]
0x1800156cb  mov     rsp, r11
0x1800156ce  pop     r15
0x1800156d0  pop     r14
0x1800156d2  pop     r13
0x1800156d4  pop     rdi
0x1800156d5  pop     rbp
0x1800156d6  retn
0x1800156d7  call    __report_rangecheckfailure
```
