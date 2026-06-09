# CRegNode::MoveToChildKeyOrValueByPosition(ulong,ulong)

- ea: `0x1800347c0`
- end: `0x18003490e`
- name: `?MoveToChildKeyOrValueByPosition@CRegNode@@AEAAJKK@Z`
- size: `334`
- prototype: `__int64 __fastcall(CRegNode *__hidden this, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800347b0`
- `0x180034920`

## callees

- `0x180001e60`
- `0x1800347c0`
- `0x180034934`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800348fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800348fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800347ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800347ef`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180034888`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180034888`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003484e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003484e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRegNode::MoveToChildKeyOrValueByPosition(CRegNode *this, int a2, DWORD a3)
{
  WCHAR *v7; // rdi
  int v8; // ebx
  LSTATUS v9; // eax
  unsigned __int16 *v10; // r9
  const unsigned __int16 *v11; // r8
  DWORD cchValueName; // [rsp+70h] [rbp+8h] BYREF

  cchValueName = 2000;
  if ( (*((_DWORD *)this + 2) & 3) != 0 )
    return 2148597829LL;
  v7 = (WCHAR *)CoTaskMemAlloc(0xFA0u);
  if ( !v7 )
    return 2147942414LL;
  if ( a2 )
  {
    if ( a2 != 1 )
    {
      v8 = -2147418113;
      goto LABEL_21;
    }
    v9 = RegEnumValueW(*((HKEY *)this + 3), a3, v7, &cchValueName, 0, 0, 0, 0);
  }
  else
  {
    v9 = RegEnumKeyExW(*((HKEY *)this + 3), a3, v7, &cchValueName, 0, 0, 0, 0);
  }
  if ( v9 )
  {
    if ( v9 == 1314 || v9 == 5 )
      v8 = -2146367453;
    else
      v8 = -2146369493;
    goto LABEL_21;
  }
  if ( a2 )
  {
    if ( !cchValueName )
    {
      v8 = StringCchCopyW(v7, 0x7D0u, L"\\");
      if ( v8 < 0 )
        goto LABEL_21;
    }
    v10 = v7;
    v11 = L"\\";
  }
  else
  {
    v10 = L"\\";
    v11 = v7;
  }
  v8 = CRegNode::MoveToDescendantOr(this, 0, v11, v10);
LABEL_21:
  CoTaskMemFree(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800347c0  push    rbx
0x1800347c2  push    rbp
0x1800347c3  push    rsi
0x1800347c4  push    rdi
0x1800347c5  sub     rsp, 48h
0x1800347c9  mov     ebx, r8d
0x1800347cc  mov     esi, edx
0x1800347ce  mov     rbp, rcx
0x1800347d1  mov     [rsp+68h+cchValueName], 7D0h
0x1800347d9  mov     eax, [rcx+8]
0x1800347dc  test    al, 3
0x1800347de  jz      short loc_1800347EA
0x1800347e0  mov     eax, 80110045h
0x1800347e5  jmp     loc_180034905
0x1800347ea  mov     ecx, 0FA0h; cb
0x1800347ef  call    cs:__imp_CoTaskMemAlloc
0x1800347f5  mov     rdi, rax
0x1800347f8  test    rax, rax
0x1800347fb  jnz     short loc_180034807
0x1800347fd  mov     eax, 8007000Eh
0x180034802  jmp     loc_180034905
0x180034807  mov     eax, esi
0x180034809  test    esi, esi
0x18003480b  jz      short loc_180034856
0x18003480d  cmp     eax, 1
0x180034810  jz      short loc_18003481C
0x180034812  mov     ebx, 8000FFFFh
0x180034817  jmp     loc_1800348F9
0x18003481c  mov     [rsp+68h+lpcbData], 0; lpcbData
0x180034825  mov     [rsp+68h+lpData], 0; lpData
0x18003482e  mov     [rsp+68h+lpType], 0; lpType
0x180034837  mov     [rsp+68h+lpReserved], 0; lpReserved
0x180034840  lea     r9, [rsp+68h+cchValueName]; lpcchValueName
0x180034845  mov     r8, rdi; lpValueName
0x180034848  mov     edx, ebx; dwIndex
0x18003484a  mov     rcx, [rbp+18h]; hKey
0x18003484e  call    cs:__imp_RegEnumValueW
0x180034854  jmp     short loc_18003488E
0x180034856  mov     [rsp+68h+lpcbData], 0; lpftLastWriteTime
0x18003485f  mov     [rsp+68h+lpData], 0; lpcchClass
0x180034868  mov     [rsp+68h+lpType], 0; lpClass
0x180034871  mov     [rsp+68h+lpReserved], 0; lpReserved
0x18003487a  lea     r9, [rsp+68h+cchValueName]; lpcchName
0x18003487f  mov     r8, rdi; lpName
0x180034882  mov     edx, ebx; dwIndex
0x180034884  mov     rcx, [rbp+18h]; hKey
0x180034888  call    cs:__imp_RegEnumKeyExW
0x18003488e  test    eax, eax
0x180034890  jz      short loc_1800348AC
0x180034892  cmp     eax, 522h
0x180034897  jz      short loc_1800348A5
0x180034899  cmp     eax, 5
0x18003489c  jz      short loc_1800348A5
0x18003489e  mov     ebx, 8011002Bh
0x1800348a3  jmp     short loc_1800348F9
0x1800348a5  mov     ebx, 80110823h
0x1800348aa  jmp     short loc_1800348F9
0x1800348ac  xor     ebx, ebx
0x1800348ae  test    esi, esi
0x1800348b0  jz      short loc_1800348E3
0x1800348b2  cmp     esi, 1
0x1800348b5  jnz     short loc_1800348F9
0x1800348b7  cmp     [rsp+68h+cchValueName], ebx
0x1800348bb  jnz     short loc_1800348D7
0x1800348bd  lea     r8, asc_180061B34; "\\"
0x1800348c4  mov     edx, 7D0h; unsigned __int64
0x1800348c9  mov     rcx, rdi; unsigned __int16 *
0x1800348cc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800348d1  mov     ebx, eax
0x1800348d3  test    eax, eax
0x1800348d5  js      short loc_1800348F9
0x1800348d7  mov     r9, rdi
0x1800348da  lea     r8, asc_180061B34; "\\"
0x1800348e1  jmp     short loc_1800348ED
0x1800348e3  lea     r9, asc_180061B34; "\\"
0x1800348ea  mov     r8, rdi; unsigned __int16 *
0x1800348ed  xor     edx, edx; unsigned int
0x1800348ef  mov     rcx, rbp; this
0x1800348f2  call    ?MoveToDescendantOr@CRegNode@@AEAAJKPEBG0@Z; CRegNode::MoveToDescendantOr(ulong,ushort const *,ushort const *)
0x1800348f7  mov     ebx, eax
0x1800348f9  mov     rcx, rdi; pv
0x1800348fc  call    cs:__imp_CoTaskMemFree
0x180034902  nop
0x180034903  mov     eax, ebx
0x180034905  add     rsp, 48h
0x180034909  pop     rdi
0x18003490a  pop     rsi
0x18003490b  pop     rbp
0x18003490c  pop     rbx
0x18003490d  retn
```
