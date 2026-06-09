# CAccountData::_OpenRegRoot(void)

- ea: `0x180008408`
- end: `0x180008495`
- name: `?_OpenRegRoot@CAccountData@@AEAAHXZ`
- size: `141`
- prototype: `__int64 __fastcall(CAccountData *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008184`

## callees

- `0x180008408`
- `0x180025d38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000846e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000846e`

## pseudocode

```c
__int64 __fastcall CAccountData::_OpenRegRoot(CAccountData *this)
{
  unsigned int v2; // ecx
  int v3; // edx
  int v4; // edx
  HKEY NtUserHive; // rax

  v2 = 0;
  v3 = *((_DWORD *)this + 150);
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 == 1 )
      {
        NtUserHive = Intl_LoadNtUserHive(0, &LocaleName, (char *)this + 608);
        *((_QWORD *)this + 77) = NtUserHive;
        return NtUserHive != 0;
      }
    }
    else
    {
      return RegOpenKeyExW(HKEY_USERS, L".DEFAULT", 0, 0x20019u, (PHKEY)this + 77) == 0;
    }
  }
  else
  {
    *((_QWORD *)this + 77) = -2147483647;
    return 1;
  }
  return v2;
}

```

## disassembly

```asm
0x180008408  push    rbx
0x18000840a  sub     rsp, 30h
0x18000840e  mov     rbx, rcx
0x180008411  xor     ecx, ecx; unsigned __int16 *
0x180008413  mov     edx, [rbx+258h]
0x180008419  test    edx, edx
0x18000841b  jz      short loc_18000847D
0x18000841d  sub     edx, 1
0x180008420  jz      short loc_18000844B
0x180008422  cmp     edx, 1
0x180008425  jnz     short loc_18000848D
0x180008427  lea     r8, [rbx+260h]; unsigned __int8 *
0x18000842e  lea     rdx, LocaleName; unsigned __int16 *
0x180008435  call    ?Intl_LoadNtUserHive@@YAPEAUHKEY__@@PEBG0PEAE@Z; Intl_LoadNtUserHive(ushort const *,ushort const *,uchar *)
0x18000843a  xor     ecx, ecx
0x18000843c  mov     [rbx+268h], rax
0x180008443  test    rax, rax
0x180008446  setnz   cl
0x180008449  jmp     short loc_18000848D
0x18000844b  lea     rax, [rbx+268h]
0x180008452  mov     r9d, 20019h; samDesired
0x180008458  xor     r8d, r8d; ulOptions
0x18000845b  mov     [rsp+38h+phkResult], rax; phkResult
0x180008460  lea     rdx, aDefault; ".DEFAULT"
0x180008467  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18000846e  call    cs:__imp_RegOpenKeyExW
0x180008474  xor     ecx, ecx
0x180008476  test    eax, eax
0x180008478  setz    cl
0x18000847b  jmp     short loc_18000848D
0x18000847d  mov     qword ptr [rbx+268h], 0FFFFFFFF80000001h
0x180008488  mov     ecx, 1
0x18000848d  mov     eax, ecx
0x18000848f  add     rsp, 30h
0x180008493  pop     rbx
0x180008494  retn
```
