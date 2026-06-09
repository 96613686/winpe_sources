# CRegNode::CopyKeyAndDescendants(HKEY__ *,HKEY__ *)

- ea: `0x180053450`
- end: `0x18005362c`
- name: `?CopyKeyAndDescendants@CRegNode@@AEAAJPEAUHKEY__@@0@Z`
- size: `476`
- prototype: `__int64 __fastcall(CRegNode *__hidden this, HKEY, HKEY)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180053320`
- `0x180053450`

## callees

- `0x180053450`
- `0x180053634`
- `0x1800546f8`
- `0x180054718`
- `0x180054764`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800534fb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800534fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005360b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005360b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053495`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053495`

## pseudocode

```c
__int64 __fastcall CRegNode::CopyKeyAndDescendants(CRegNode *this, HKEY a2, HKEY a3)
{
  CRegNode *v6; // rcx
  WCHAR *v7; // rdi
  int v9; // ebx
  DWORD i; // esi
  LSTATUS v11; // eax
  unsigned int v12; // r8d
  int v13; // eax
  unsigned int v14; // r8d
  unsigned __int16 *v15; // r9
  int v16; // eax
  unsigned int lpReserved; // [rsp+20h] [rbp-50h]
  struct _SECURITY_ATTRIBUTES *lpcchClass; // [rsp+30h] [rbp-40h]
  unsigned int v19; // [rsp+50h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-18h] BYREF
  HKEY v21; // [rsp+60h] [rbp-10h] BYREF
  DWORD cchName; // [rsp+B8h] [rbp+48h] BYREF

  cchName = 2000;
  hKey = 0;
  v21 = 0;
  v19 = 0;
  v7 = (WCHAR *)CoTaskMemAlloc(0xFA0u);
  if ( !v7 )
    return 2147942414LL;
  v9 = CRegNode::CopyKeyValues(v6, a2, a3);
  if ( v9 >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      cchName = 2000;
      v11 = RegEnumKeyExW(a2, i, v7, &cchName, 0, 0, 0, 0);
      if ( v11 == 259 )
        break;
      if ( v11 )
      {
        if ( v11 != 1314 && v11 != 5 )
        {
          v9 = -2146369493;
          goto LABEL_22;
        }
        goto LABEL_20;
      }
      v13 = RegSafeOpenKeyEx(a2, v7, v12, 0x2001Fu, &hKey);
      if ( v13 )
      {
        if ( v13 != 1314 && v13 != 5 )
        {
          v9 = -2146369487;
          goto LABEL_22;
        }
        goto LABEL_20;
      }
      v16 = RegSafeCreateKeyEx(a3, v7, v14, v15, lpReserved, 0x2001Fu, lpcchClass, &v21, &v19);
      if ( v16 )
      {
        if ( v16 != 1314 && v16 != 5 )
        {
          v9 = -2146369503;
          goto LABEL_22;
        }
LABEL_20:
        v9 = -2146367453;
        goto LABEL_22;
      }
      v9 = CRegNode::CopyKeyAndDescendants(this, hKey, v21);
      if ( v9 < 0 )
        goto LABEL_22;
      RegSafeCloseKey(hKey);
      hKey = 0;
      RegSafeCloseKey(v21);
      v21 = 0;
    }
    v9 = 0;
  }
LABEL_22:
  if ( hKey )
  {
    RegSafeCloseKey(hKey);
    hKey = 0;
  }
  if ( v21 )
  {
    RegSafeCloseKey(v21);
    v21 = 0;
  }
  CoTaskMemFree(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180053450  mov     [rsp-28h+arg_0], rbx
0x180053455  mov     [rsp-28h+arg_8], rsi
0x18005345a  push    rbp
0x18005345b  push    rdi
0x18005345c  push    r12
0x18005345e  push    r14
0x180053460  push    r15
0x180053462  mov     rbp, rsp
0x180053465  sub     rsp, 70h
0x180053469  mov     r12, rcx
0x18005346c  mov     [rbp+cchName], 7D0h
0x180053473  mov     ecx, 0FA0h; cb
0x180053478  mov     [rbp+hKey], 0
0x180053480  mov     r15, r8
0x180053483  mov     [rbp+var_10], 0
0x18005348b  mov     r14, rdx
0x18005348e  mov     [rbp+var_20], 0
0x180053495  call    cs:__imp_CoTaskMemAlloc
0x18005349b  mov     rdi, rax
0x18005349e  test    rax, rax
0x1800534a1  jnz     short loc_1800534AD
0x1800534a3  mov     eax, 8007000Eh
0x1800534a8  jmp     loc_180053613
0x1800534ad  mov     r8, r15; HKEY
0x1800534b0  mov     rdx, r14; HKEY
0x1800534b3  call    ?CopyKeyValues@CRegNode@@AEAAJPEAUHKEY__@@0@Z; CRegNode::CopyKeyValues(HKEY__ *,HKEY__ *)
0x1800534b8  mov     ebx, eax
0x1800534ba  test    eax, eax
0x1800534bc  js      loc_1800535DC
0x1800534c2  xor     esi, esi
0x1800534c4  mov     [rsp+70h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800534cd  lea     r9, [rbp+cchName]; lpcchName
0x1800534d1  mov     [rsp+70h+lpcchClass], 0; struct _SECURITY_ATTRIBUTES *
0x1800534da  mov     r8, rdi; lpName
0x1800534dd  mov     [rsp+70h+lpClass], 0; lpClass
0x1800534e6  mov     edx, esi; dwIndex
0x1800534e8  mov     rcx, r14; hKey
0x1800534eb  mov     [rsp+70h+lpReserved], 0; lpReserved
0x1800534f4  mov     [rbp+cchName], 7D0h
0x1800534fb  call    cs:__imp_RegEnumKeyExW
0x180053501  cmp     eax, 103h
0x180053506  jz      loc_1800535DA
0x18005350c  test    eax, eax
0x18005350e  jnz     loc_1800535C0
0x180053514  lea     rax, [rbp+hKey]
0x180053518  mov     r9d, 2001Fh; unsigned int
0x18005351e  mov     rdx, rdi; unsigned __int16 *
0x180053521  mov     [rsp+70h+lpReserved], rax; unsigned int
0x180053526  mov     rcx, r14; HKEY
0x180053529  call    ?RegSafeOpenKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; RegSafeOpenKeyEx(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18005352e  test    eax, eax
0x180053530  jnz     short loc_1800535AD
0x180053532  lea     rax, [rbp+var_20]
0x180053536  mov     rdx, rdi; unsigned __int16 *
0x180053539  mov     [rsp+70h+var_30], rax; unsigned int *
0x18005353e  mov     rcx, r15; HKEY
0x180053541  lea     rax, [rbp+var_10]
0x180053545  mov     [rsp+70h+lpftLastWriteTime], rax; HKEY *
0x18005354a  mov     dword ptr [rsp+70h+lpClass], 2001Fh; unsigned int
0x180053552  call    ?RegSafeCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; RegSafeCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180053557  test    eax, eax
0x180053559  jnz     short loc_18005359A
0x18005355b  mov     r8, [rbp+var_10]; HKEY
0x18005355f  mov     rcx, r12; this
0x180053562  mov     rdx, [rbp+hKey]; HKEY
0x180053566  call    ?CopyKeyAndDescendants@CRegNode@@AEAAJPEAUHKEY__@@0@Z; CRegNode::CopyKeyAndDescendants(HKEY__ *,HKEY__ *)
0x18005356b  mov     ebx, eax
0x18005356d  test    eax, eax
0x18005356f  js      short loc_1800535DC
0x180053571  mov     rcx, [rbp+hKey]; HKEY
0x180053575  call    ?RegSafeCloseKey@@YAJPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x18005357a  mov     rcx, [rbp+var_10]; HKEY
0x18005357e  mov     [rbp+hKey], 0
0x180053586  call    ?RegSafeCloseKey@@YAJPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x18005358b  inc     esi
0x18005358d  mov     [rbp+var_10], 0
0x180053595  jmp     loc_1800534C4
0x18005359a  cmp     eax, 522h
0x18005359f  jz      short loc_1800535D3
0x1800535a1  cmp     eax, 5
0x1800535a4  jz      short loc_1800535D3
0x1800535a6  mov     ebx, 80110021h
0x1800535ab  jmp     short loc_1800535DC
0x1800535ad  cmp     eax, 522h
0x1800535b2  jz      short loc_1800535D3
0x1800535b4  cmp     eax, 5
0x1800535b7  jz      short loc_1800535D3
0x1800535b9  mov     ebx, 80110031h
0x1800535be  jmp     short loc_1800535DC
0x1800535c0  cmp     eax, 522h
0x1800535c5  jz      short loc_1800535D3
0x1800535c7  cmp     eax, 5
0x1800535ca  jz      short loc_1800535D3
0x1800535cc  mov     ebx, 8011002Bh
0x1800535d1  jmp     short loc_1800535DC
0x1800535d3  mov     ebx, 80110823h
0x1800535d8  jmp     short loc_1800535DC
0x1800535da  xor     ebx, ebx
0x1800535dc  mov     rcx, [rbp+hKey]; HKEY
0x1800535e0  test    rcx, rcx
0x1800535e3  jz      short loc_1800535F2
0x1800535e5  call    ?RegSafeCloseKey@@YAJPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x1800535ea  mov     [rbp+hKey], 0
0x1800535f2  mov     rcx, [rbp+var_10]; HKEY
0x1800535f6  test    rcx, rcx
0x1800535f9  jz      short loc_180053608
0x1800535fb  call    ?RegSafeCloseKey@@YAJPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x180053600  mov     [rbp+var_10], 0
0x180053608  mov     rcx, rdi; pv
0x18005360b  call    cs:__imp_CoTaskMemFree
0x180053611  mov     eax, ebx
0x180053613  lea     r11, [rsp+70h+var_s0]
0x180053618  mov     rbx, [r11+30h]
0x18005361c  mov     rsi, [r11+38h]
0x180053620  mov     rsp, r11
0x180053623  pop     r15
0x180053625  pop     r14
0x180053627  pop     r12
0x180053629  pop     rdi
0x18005362a  pop     rbp
0x18005362b  retn
```
