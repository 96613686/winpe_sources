# CRegNode::CopyKeyAndDescendants(HKEY__ *,HKEY__ *)

- ea: `0x180033cd0`
- end: `0x180033ead`
- name: `?CopyKeyAndDescendants@CRegNode@@AEAAJPEAUHKEY__@@0@Z`
- size: `477`
- prototype: `__int64 __fastcall(CRegNode *__hidden this, HKEY, HKEY)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180033ba0`
- `0x180033cd0`

## callees

- `0x180033cd0`
- `0x180033eb4`
- `0x180034f88`
- `0x180034fa8`
- `0x180034ff4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033e8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033e8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033d15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033d15`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180033d7b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180033d7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180033cd0  mov     [rsp-28h+arg_0], rbx
0x180033cd5  mov     [rsp-28h+arg_8], rsi
0x180033cda  push    rbp
0x180033cdb  push    rdi
0x180033cdc  push    r12
0x180033cde  push    r14
0x180033ce0  push    r15
0x180033ce2  mov     rbp, rsp
0x180033ce5  sub     rsp, 70h
0x180033ce9  mov     r15, r8
0x180033cec  mov     r14, rdx
0x180033cef  mov     r12, rcx
0x180033cf2  mov     [rbp+cchName], 7D0h
0x180033cf9  mov     [rbp+hKey], 0
0x180033d01  mov     [rbp+var_10], 0
0x180033d09  mov     [rbp+var_20], 0
0x180033d10  mov     ecx, 0FA0h; cb
0x180033d15  call    cs:__imp_CoTaskMemAlloc
0x180033d1b  mov     rdi, rax
0x180033d1e  test    rax, rax
0x180033d21  jnz     short loc_180033D2D
0x180033d23  mov     eax, 8007000Eh
0x180033d28  jmp     loc_180033E94
0x180033d2d  mov     r8, r15; HKEY
0x180033d30  mov     rdx, r14; HKEY
0x180033d33  call    ?CopyKeyValues@CRegNode@@AEAAJPEAUHKEY__@@0@Z; CRegNode::CopyKeyValues(HKEY__ *,HKEY__ *)
0x180033d38  mov     ebx, eax
0x180033d3a  test    eax, eax
0x180033d3c  js      loc_180033E5C
0x180033d42  xor     esi, esi
0x180033d44  mov     [rbp+cchName], 7D0h
0x180033d4b  mov     [rsp+70h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180033d54  mov     [rsp+70h+lpcchClass], 0; struct _SECURITY_ATTRIBUTES *
0x180033d5d  mov     [rsp+70h+lpClass], 0; lpClass
0x180033d66  mov     [rsp+70h+lpReserved], 0; lpReserved
0x180033d6f  lea     r9, [rbp+cchName]; lpcchName
0x180033d73  mov     r8, rdi; lpName
0x180033d76  mov     edx, esi; dwIndex
0x180033d78  mov     rcx, r14; hKey
0x180033d7b  call    cs:__imp_RegEnumKeyExW
0x180033d81  cmp     eax, 103h
0x180033d86  jz      loc_180033E5A
0x180033d8c  test    eax, eax
0x180033d8e  jnz     loc_180033E40
0x180033d94  lea     rax, [rbp+hKey]
0x180033d98  mov     [rsp+70h+lpReserved], rax; unsigned int
0x180033d9d  mov     r9d, 2001Fh; unsigned int
0x180033da3  mov     rdx, rdi; unsigned __int16 *
0x180033da6  mov     rcx, r14; HKEY
0x180033da9  call    ?RegSafeOpenKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; RegSafeOpenKeyEx(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180033dae  test    eax, eax
0x180033db0  jnz     short loc_180033E2D
0x180033db2  lea     rax, [rbp+var_20]
0x180033db6  mov     [rsp+70h+var_30], rax; unsigned int *
0x180033dbb  lea     rax, [rbp+var_10]
0x180033dbf  mov     [rsp+70h+lpftLastWriteTime], rax; HKEY *
0x180033dc4  mov     dword ptr [rsp+70h+lpClass], 2001Fh; unsigned int
0x180033dcc  mov     rdx, rdi; unsigned __int16 *
0x180033dcf  mov     rcx, r15; HKEY
0x180033dd2  call    ?RegSafeCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; RegSafeCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180033dd7  test    eax, eax
0x180033dd9  jnz     short loc_180033E1A
0x180033ddb  mov     r8, [rbp+var_10]; HKEY
0x180033ddf  mov     rdx, [rbp+hKey]; HKEY
0x180033de3  mov     rcx, r12; this
0x180033de6  call    ?CopyKeyAndDescendants@CRegNode@@AEAAJPEAUHKEY__@@0@Z; CRegNode::CopyKeyAndDescendants(HKEY__ *,HKEY__ *)
0x180033deb  mov     ebx, eax
0x180033ded  test    eax, eax
0x180033def  js      short loc_180033E5C
0x180033df1  mov     rcx, [rbp+hKey]; HKEY
0x180033df5  call    ?RegSafeCloseKey@@YAJPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x180033dfa  mov     [rbp+hKey], 0
0x180033e02  mov     rcx, [rbp+var_10]; HKEY
0x180033e06  call    ?RegSafeCloseKey@@YAJPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x180033e0b  mov     [rbp+var_10], 0
0x180033e13  inc     esi
0x180033e15  jmp     loc_180033D44
0x180033e1a  cmp     eax, 522h
0x180033e1f  jz      short loc_180033E53
0x180033e21  cmp     eax, 5
0x180033e24  jz      short loc_180033E53
0x180033e26  mov     ebx, 80110021h
0x180033e2b  jmp     short loc_180033E5C
0x180033e2d  cmp     eax, 522h
0x180033e32  jz      short loc_180033E53
0x180033e34  cmp     eax, 5
0x180033e37  jz      short loc_180033E53
0x180033e39  mov     ebx, 80110031h
0x180033e3e  jmp     short loc_180033E5C
0x180033e40  cmp     eax, 522h
0x180033e45  jz      short loc_180033E53
0x180033e47  cmp     eax, 5
0x180033e4a  jz      short loc_180033E53
0x180033e4c  mov     ebx, 8011002Bh
0x180033e51  jmp     short loc_180033E5C
0x180033e53  mov     ebx, 80110823h
0x180033e58  jmp     short loc_180033E5C
0x180033e5a  xor     ebx, ebx
0x180033e5c  mov     rcx, [rbp+hKey]; HKEY
0x180033e60  test    rcx, rcx
0x180033e63  jz      short loc_180033E72
0x180033e65  call    ?RegSafeCloseKey@@YAJPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x180033e6a  mov     [rbp+hKey], 0
0x180033e72  mov     rcx, [rbp+var_10]; HKEY
0x180033e76  test    rcx, rcx
0x180033e79  jz      short loc_180033E88
0x180033e7b  call    ?RegSafeCloseKey@@YAJPEAUHKEY__@@@Z; RegSafeCloseKey(HKEY__ *)
0x180033e80  mov     [rbp+var_10], 0
0x180033e88  mov     rcx, rdi; pv
0x180033e8b  call    cs:__imp_CoTaskMemFree
0x180033e91  nop
0x180033e92  mov     eax, ebx
0x180033e94  lea     r11, [rsp+70h+var_s0]
0x180033e99  mov     rbx, [r11+30h]
0x180033e9d  mov     rsi, [r11+38h]
0x180033ea1  mov     rsp, r11
0x180033ea4  pop     r15
0x180033ea6  pop     r14
0x180033ea8  pop     r12
0x180033eaa  pop     rdi
0x180033eab  pop     rbp
0x180033eac  retn
```
