# CRegNode::MoveToChildKeyOrValueByPosition(ulong,ulong)

- ea: `0x180053f40`
- end: `0x18005408d`
- name: `?MoveToChildKeyOrValueByPosition@CRegNode@@AEAAJKK@Z`
- size: `333`
- prototype: `__int64 __fastcall(CRegNode *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180053f30`
- `0x1800540a0`

## callees

- `0x18000a01c`
- `0x180053f40`
- `0x1800540b4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180054008`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180054008`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180053fce`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180053fce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005407c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005407c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053f6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180053f6f`

## pseudocode

```c
__int64 __fastcall CRegNode::MoveToChildKeyOrValueByPosition(CRegNode *this, int a2, DWORD a3)
{
  int v3; // eax
  WCHAR *v8; // rdi
  int v9; // ebx
  LSTATUS v10; // eax
  unsigned __int16 *v11; // r9
  const unsigned __int16 *v12; // r8
  DWORD cchValueName; // [rsp+70h] [rbp+8h] BYREF

  v3 = *((_DWORD *)this + 2);
  cchValueName = 2000;
  if ( (v3 & 3) != 0 )
    return 2148597829LL;
  v8 = (WCHAR *)CoTaskMemAlloc(0xFA0u);
  if ( !v8 )
    return 2147942414LL;
  if ( a2 )
  {
    if ( a2 != 1 )
    {
      v9 = -2147418113;
      goto LABEL_21;
    }
    v10 = RegEnumValueW(*((HKEY *)this + 3), a3, v8, &cchValueName, 0, 0, 0, 0);
  }
  else
  {
    v10 = RegEnumKeyExW(*((HKEY *)this + 3), a3, v8, &cchValueName, 0, 0, 0, 0);
  }
  if ( v10 )
  {
    if ( v10 == 1314 || v10 == 5 )
      v9 = -2146367453;
    else
      v9 = -2146369493;
    goto LABEL_21;
  }
  if ( a2 )
  {
    if ( !cchValueName )
    {
      v9 = StringCchCopyW(v8, 0x7D0u, L"\\");
      if ( v9 < 0 )
        goto LABEL_21;
    }
    v11 = v8;
    v12 = L"\\";
  }
  else
  {
    v11 = L"\\";
    v12 = v8;
  }
  v9 = CRegNode::MoveToDescendantOr(this, 0, v12, v11);
LABEL_21:
  CoTaskMemFree(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180053f40  push    rbx
0x180053f42  push    rbp
0x180053f43  push    rsi
0x180053f44  push    rdi
0x180053f45  sub     rsp, 48h
0x180053f49  mov     eax, [rcx+8]
0x180053f4c  mov     ebx, r8d
0x180053f4f  mov     [rsp+68h+cchValueName], 7D0h
0x180053f57  mov     esi, edx
0x180053f59  mov     rbp, rcx
0x180053f5c  test    al, 3
0x180053f5e  jz      short loc_180053F6A
0x180053f60  mov     eax, 80110045h
0x180053f65  jmp     loc_180054084
0x180053f6a  mov     ecx, 0FA0h; cb
0x180053f6f  call    cs:__imp_CoTaskMemAlloc
0x180053f75  mov     rdi, rax
0x180053f78  test    rax, rax
0x180053f7b  jnz     short loc_180053F87
0x180053f7d  mov     eax, 8007000Eh
0x180053f82  jmp     loc_180054084
0x180053f87  mov     eax, esi
0x180053f89  test    esi, esi
0x180053f8b  jz      short loc_180053FD6
0x180053f8d  cmp     eax, 1
0x180053f90  jz      short loc_180053F9C
0x180053f92  mov     ebx, 8000FFFFh
0x180053f97  jmp     loc_180054079
0x180053f9c  mov     rcx, [rbp+18h]; hKey
0x180053fa0  lea     r9, [rsp+68h+cchValueName]; lpcchValueName
0x180053fa5  mov     [rsp+68h+lpcbData], 0; lpcbData
0x180053fae  mov     r8, rdi; lpValueName
0x180053fb1  mov     [rsp+68h+lpData], 0; lpData
0x180053fba  mov     edx, ebx; dwIndex
0x180053fbc  mov     [rsp+68h+lpType], 0; lpType
0x180053fc5  mov     [rsp+68h+lpReserved], 0; lpReserved
0x180053fce  call    cs:__imp_RegEnumValueW
0x180053fd4  jmp     short loc_18005400E
0x180053fd6  mov     rcx, [rbp+18h]; hKey
0x180053fda  lea     r9, [rsp+68h+cchValueName]; lpcchName
0x180053fdf  mov     [rsp+68h+lpcbData], 0; lpftLastWriteTime
0x180053fe8  mov     r8, rdi; lpName
0x180053feb  mov     [rsp+68h+lpData], 0; lpcchClass
0x180053ff4  mov     edx, ebx; dwIndex
0x180053ff6  mov     [rsp+68h+lpType], 0; lpClass
0x180053fff  mov     [rsp+68h+lpReserved], 0; lpReserved
0x180054008  call    cs:__imp_RegEnumKeyExW
0x18005400e  test    eax, eax
0x180054010  jz      short loc_18005402C
0x180054012  cmp     eax, 522h
0x180054017  jz      short loc_180054025
0x180054019  cmp     eax, 5
0x18005401c  jz      short loc_180054025
0x18005401e  mov     ebx, 8011002Bh
0x180054023  jmp     short loc_180054079
0x180054025  mov     ebx, 80110823h
0x18005402a  jmp     short loc_180054079
0x18005402c  xor     ebx, ebx
0x18005402e  test    esi, esi
0x180054030  jz      short loc_180054063
0x180054032  cmp     esi, 1
0x180054035  jnz     short loc_180054079
0x180054037  cmp     [rsp+68h+cchValueName], ebx
0x18005403b  jnz     short loc_180054057
0x18005403d  lea     r8, asc_18005D30C; "\\"
0x180054044  mov     edx, 7D0h; unsigned __int64
0x180054049  mov     rcx, rdi; unsigned __int16 *
0x18005404c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180054051  mov     ebx, eax
0x180054053  test    eax, eax
0x180054055  js      short loc_180054079
0x180054057  mov     r9, rdi
0x18005405a  lea     r8, asc_18005D30C; "\\"
0x180054061  jmp     short loc_18005406D
0x180054063  lea     r9, asc_18005D30C; "\\"
0x18005406a  mov     r8, rdi; unsigned __int16 *
0x18005406d  xor     edx, edx; unsigned int
0x18005406f  mov     rcx, rbp; this
0x180054072  call    ?MoveToDescendantOr@CRegNode@@AEAAJKPEBG0@Z; CRegNode::MoveToDescendantOr(ulong,ushort const *,ushort const *)
0x180054077  mov     ebx, eax
0x180054079  mov     rcx, rdi; pv
0x18005407c  call    cs:__imp_CoTaskMemFree
0x180054082  mov     eax, ebx
0x180054084  add     rsp, 48h
0x180054088  pop     rdi
0x180054089  pop     rsi
0x18005408a  pop     rbp
0x18005408b  pop     rbx
0x18005408c  retn
```
