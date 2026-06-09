# CMvExtensionKey::ReadKeys(void)

- ea: `0x180015474`
- end: `0x180015764`
- name: `?ReadKeys@CMvExtensionKey@@QEAAJXZ`
- size: `752`
- prototype: `__int64 __fastcall(CMvExtensionKey *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800143f0`

## callees

- `0x180015474`
- `0x180015934`
- `0x18003b96a`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015569`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015569`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001555b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001555b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015658`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015658`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180015522`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180015522`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800155ea`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800155ea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001568d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001568d`

## pseudocode

```c
__int64 __fastcall CMvExtensionKey::ReadKeys(CMvExtensionKey *this)
{
  struct IMVKey **v2; // rcx
  LSTATUS ValueW; // eax
  int v4; // ebx
  bool v5; // cc
  SIZE_T v6; // rbx
  HANDLE ProcessHeap; // rax
  void *v8; // rax
  DWORD v9; // esi
  struct IMVKey **v10; // rcx
  DWORD cValues; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchValueName; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD pcbData; // [rsp+68h] [rbp-98h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-90h] BYREF
  DWORD Type; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ValueName[264]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pvData[528]; // [rsp+290h] [rbp+190h] BYREF

  v2 = (struct IMVKey **)*((_QWORD *)this + 76);
  cchValueName = 0;
  pcbData = 0;
  cValues = 0;
  ppv = 0;
  Type = 0;
  if ( v2 )
  {
    ReleaseKeyArray(v2, *((_DWORD *)this + 154));
    *((_QWORD *)this + 76) = 0;
    *((_DWORD *)this + 154) = 0;
  }
  ValueW = RegQueryInfoKeyW(*((HKEY *)this + 78), 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
  v4 = ValueW;
  v5 = ValueW <= 0;
  if ( !ValueW )
  {
    if ( !cValues )
    {
      v4 = -2147024809;
      goto LABEL_21;
    }
    v6 = 8LL * cValues;
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 0, v6);
    *((_QWORD *)this + 76) = v8;
    if ( !v8 )
    {
      v4 = -2147024882;
      goto LABEL_21;
    }
    memset_0(v8, 0, 8LL * cValues);
    v9 = 0;
    if ( !cValues )
    {
LABEL_20:
      v4 = 0;
      goto LABEL_21;
    }
    while ( 1 )
    {
      cchValueName = 261;
      memset_0(ValueName, 0, 0x20Au);
      ValueW = RegEnumValueW(*((HKEY *)this + 78), v9, ValueName, &cchValueName, 0, &Type, 0, 0);
      v4 = ValueW;
      v5 = ValueW <= 0;
      if ( ValueW )
        break;
      if ( Type == 1 && cchValueName )
      {
        pcbData = 522;
        memset_0(pvData, 0, 0x20Au);
        ValueW = RegGetValueW(*((HKEY *)this + 78), 0, ValueName, v4 + 2, 0, pvData, &pcbData);
        v4 = ValueW;
        v5 = ValueW <= 0;
        if ( ValueW )
          break;
        if ( pcbData )
        {
          v4 = CoCreateInstance(
                 &GUID_38be0989_9830_49a8_985b_7741219fd0fb,
                 0,
                 ValueW + 1,
                 &GUID_401e2463_465f_4bc9_9dc9_c6daf36894b0,
                 &ppv);
          if ( v4 < 0 )
            goto LABEL_21;
          v4 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, ValueName, 0);
          if ( v4 < 0 )
          {
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
            goto LABEL_21;
          }
          *(_QWORD *)(*((_QWORD *)this + 76) + 8LL * (unsigned int)(*((_DWORD *)this + 154))++) = ppv;
          ppv = 0;
        }
      }
      if ( ++v9 >= cValues )
        goto LABEL_20;
    }
  }
  if ( !v5 )
    v4 = (unsigned __int16)ValueW | 0x80070000;
LABEL_21:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v4 < 0 )
  {
    v10 = (struct IMVKey **)*((_QWORD *)this + 76);
    if ( v10 )
    {
      ReleaseKeyArray(v10, cValues);
      *((_QWORD *)this + 76) = 0;
      *((_DWORD *)this + 154) = 0;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180015474  mov     [rsp-8+arg_8], rbx
0x180015479  mov     [rsp-8+arg_10], rsi
0x18001547e  push    rbp
0x18001547f  push    rdi
0x180015480  push    r14
0x180015482  lea     rbp, [rsp-3B0h]
0x18001548a  sub     rsp, 4B0h
0x180015491  mov     rax, cs:__security_cookie
0x180015498  xor     rax, rsp
0x18001549b  mov     [rbp+3C0h+var_20], rax
0x1800154a2  xor     r14d, r14d
0x1800154a5  mov     rdi, rcx
0x1800154a8  mov     rcx, [rcx+260h]; struct IMVKey **
0x1800154af  mov     [rsp+4C0h+cchValueName], r14d
0x1800154b4  mov     [rsp+4C0h+pcbData], r14d
0x1800154b9  mov     [rsp+4C0h+cValues], r14d
0x1800154be  mov     [rsp+4C0h+ppv], r14
0x1800154c3  mov     [rsp+4C0h+Type], r14d
0x1800154c8  test    rcx, rcx
0x1800154cb  jz      short loc_1800154E6
0x1800154cd  mov     edx, [rdi+268h]; unsigned int
0x1800154d3  call    ?ReleaseKeyArray@@YAXPEAPEAUIMVKey@@K@Z; ReleaseKeyArray(IMVKey * *,ulong)
0x1800154d8  mov     [rdi+260h], r14
0x1800154df  mov     [rdi+268h], r14d
0x1800154e6  mov     rcx, [rdi+270h]; hKey
0x1800154ed  lea     rax, [rsp+4C0h+cValues]
0x1800154f2  mov     [rsp+4C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800154f7  xor     r9d, r9d; lpReserved
0x1800154fa  mov     [rsp+4C0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800154ff  xor     r8d, r8d; lpcchClass
0x180015502  mov     [rsp+4C0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180015507  xor     edx, edx; lpClass
0x180015509  mov     [rsp+4C0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18001550e  mov     [rsp+4C0h+lpcValues], rax; lpcValues
0x180015513  mov     [rsp+4C0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180015518  mov     [rsp+4C0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18001551d  mov     [rsp+4C0h+lpcSubKeys], r14; lpcSubKeys
0x180015522  call    cs:__imp_RegQueryInfoKeyW
0x180015528  mov     ebx, eax
0x18001552a  test    eax, eax
0x18001552c  jz      short loc_180015542
0x18001552e  jle     loc_1800156EB
0x180015534  movzx   ebx, ax
0x180015537  or      ebx, 80070000h
0x18001553d  jmp     loc_1800156EB
0x180015542  cmp     [rsp+4C0h+cValues], r14d
0x180015547  jnz     short loc_180015553
0x180015549  mov     ebx, 80070057h
0x18001554e  jmp     loc_1800156EB
0x180015553  mov     ebx, [rsp+4C0h+cValues]
0x180015557  shl     rbx, 3
0x18001555b  call    cs:__imp_GetProcessHeap
0x180015561  mov     r8, rbx; dwBytes
0x180015564  xor     edx, edx; dwFlags
0x180015566  mov     rcx, rax; hHeap
0x180015569  call    cs:__imp_HeapAlloc
0x18001556f  mov     [rdi+260h], rax
0x180015576  test    rax, rax
0x180015579  jnz     short loc_180015585
0x18001557b  mov     ebx, 8007000Eh
0x180015580  jmp     loc_1800156EB
0x180015585  mov     r8d, [rsp+4C0h+cValues]
0x18001558a  xor     edx, edx; Val
0x18001558c  shl     r8, 3; Size
0x180015590  mov     rcx, rax; void *
0x180015593  call    memset_0
0x180015598  mov     esi, r14d
0x18001559b  cmp     [rsp+4C0h+cValues], r14d
0x1800155a0  jbe     loc_1800156E8
0x1800155a6  xor     edx, edx; Val
0x1800155a8  mov     [rsp+4C0h+cchValueName], 105h
0x1800155b0  mov     r8d, 20Ah; Size
0x1800155b6  lea     rcx, [rbp+3C0h+ValueName]; void *
0x1800155ba  call    memset_0
0x1800155bf  mov     rcx, [rdi+270h]; hKey
0x1800155c6  lea     rax, [rsp+4C0h+Type]
0x1800155cb  mov     [rsp+4C0h+lpcValues], r14; lpcbData
0x1800155d0  lea     r9, [rsp+4C0h+cchValueName]; lpcchValueName
0x1800155d5  mov     [rsp+4C0h+lpcbMaxClassLen], r14; lpData
0x1800155da  lea     r8, [rbp+3C0h+ValueName]; lpValueName
0x1800155de  mov     [rsp+4C0h+lpcbMaxSubKeyLen], rax; lpType
0x1800155e3  mov     edx, esi; dwIndex
0x1800155e5  mov     [rsp+4C0h+lpcSubKeys], r14; lpReserved
0x1800155ea  call    cs:__imp_RegEnumValueW
0x1800155f0  mov     ebx, eax
0x1800155f2  test    eax, eax
0x1800155f4  jnz     loc_18001552E
0x1800155fa  cmp     [rsp+4C0h+Type], 1
0x1800155ff  jnz     loc_1800156DC
0x180015605  cmp     [rsp+4C0h+cchValueName], r14d
0x18001560a  jz      loc_1800156DC
0x180015610  xor     edx, edx; Val
0x180015612  mov     [rsp+4C0h+pcbData], 20Ah
0x18001561a  mov     r8d, 20Ah; Size
0x180015620  lea     rcx, [rbp+3C0h+pvData]; void *
0x180015627  call    memset_0
0x18001562c  mov     rcx, [rdi+270h]; hkey
0x180015633  lea     rax, [rsp+4C0h+pcbData]
0x180015638  mov     [rsp+4C0h+lpcbMaxClassLen], rax; pcbData
0x18001563d  lea     r9d, [rbx+2]; dwFlags
0x180015641  lea     rax, [rbp+3C0h+pvData]
0x180015648  xor     edx, edx; lpSubKey
0x18001564a  mov     [rsp+4C0h+lpcbMaxSubKeyLen], rax; pvData
0x18001564f  lea     r8, [rbp+3C0h+ValueName]; lpValue
0x180015653  mov     [rsp+4C0h+lpcSubKeys], r14; pdwType
0x180015658  call    cs:__imp_RegGetValueW
0x18001565e  mov     ebx, eax
0x180015660  test    eax, eax
0x180015662  jnz     loc_18001552E
0x180015668  cmp     [rsp+4C0h+pcbData], r14d
0x18001566d  jz      short loc_1800156DC
0x18001566f  lea     rax, [rsp+4C0h+ppv]
0x180015674  xor     edx, edx; pUnkOuter
0x180015676  lea     r9, _GUID_401e2463_465f_4bc9_9dc9_c6daf36894b0; riid
0x18001567d  mov     [rsp+4C0h+lpcSubKeys], rax; ppv
0x180015682  lea     r8d, [rbx+1]; dwClsContext
0x180015686  lea     rcx, _GUID_38be0989_9830_49a8_985b_7741219fd0fb; rclsid
0x18001568d  call    cs:__imp_CoCreateInstance
0x180015693  mov     ebx, eax
0x180015695  test    eax, eax
0x180015697  js      short loc_1800156EB
0x180015699  mov     rcx, [rsp+4C0h+ppv]
0x18001569e  lea     rdx, [rbp+3C0h+ValueName]
0x1800156a2  xor     r8d, r8d
0x1800156a5  mov     rax, [rcx]
0x1800156a8  mov     rax, [rax+18h]
0x1800156ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156b1  mov     ebx, eax
0x1800156b3  test    eax, eax
0x1800156b5  js      loc_180015751
0x1800156bb  mov     edx, [rdi+268h]
0x1800156c1  mov     rax, [rsp+4C0h+ppv]
0x1800156c6  mov     rcx, [rdi+260h]
0x1800156cd  mov     [rcx+rdx*8], rax
0x1800156d1  inc     dword ptr [rdi+268h]
0x1800156d7  mov     [rsp+4C0h+ppv], r14
0x1800156dc  inc     esi
0x1800156de  cmp     esi, [rsp+4C0h+cValues]
0x1800156e2  jb      loc_1800155A6
0x1800156e8  mov     ebx, r14d
0x1800156eb  mov     rcx, [rsp+4C0h+ppv]
0x1800156f0  test    rcx, rcx
0x1800156f3  jz      short loc_180015701
0x1800156f5  mov     rax, [rcx]
0x1800156f8  mov     rax, [rax+10h]
0x1800156fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015701  test    ebx, ebx
0x180015703  jns     short loc_180015728
0x180015705  mov     rcx, [rdi+260h]; struct IMVKey **
0x18001570c  test    rcx, rcx
0x18001570f  jz      short loc_180015728
0x180015711  mov     edx, [rsp+4C0h+cValues]; unsigned int
0x180015715  call    ?ReleaseKeyArray@@YAXPEAPEAUIMVKey@@K@Z; ReleaseKeyArray(IMVKey * *,ulong)
0x18001571a  mov     [rdi+260h], r14
0x180015721  mov     [rdi+268h], r14d
0x180015728  mov     eax, ebx
0x18001572a  mov     rcx, [rbp+3C0h+var_20]
0x180015731  xor     rcx, rsp; StackCookie
0x180015734  call    __security_check_cookie
0x180015739  lea     r11, [rsp+4C0h+var_10]
0x180015741  mov     rbx, [r11+28h]
0x180015745  mov     rsi, [r11+30h]
0x180015749  mov     rsp, r11
0x18001574c  pop     r14
0x18001574e  pop     rdi
0x18001574f  pop     rbp
0x180015750  retn
0x180015751  mov     rcx, [rsp+4C0h+ppv]
0x180015756  mov     rax, [rcx]
0x180015759  mov     rax, [rax+10h]
0x18001575d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015762  jmp     short loc_1800156EB
```
