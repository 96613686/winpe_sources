# CRegistry::RecurseDeleteKey(ushort const *)

- ea: `0x180017040`
- end: `0x180017149`
- name: `?RecurseDeleteKey@CRegistry@@QEAAKPEBG@Z`
- size: `265`
- prototype: `unsigned int __fastcall(CRegistry *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180017040`
- `0x1800468a4`

## callees

- `0x180017040`
- `0x180017da0`
- `0x180018640`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180017100`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180017100`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017093`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017093`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001712d`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18001712d`

## pseudocode

```c
__int64 __fastcall CRegistry::RecurseDeleteKey(CRegistry *this, const unsigned __int16 *a2)
{
  HKEY v3; // rcx
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  void **v8; // [rsp+40h] [rbp-38h] BYREF
  LPWSTR lpName; // [rsp+48h] [rbp-30h]
  int v10; // [rsp+50h] [rbp-28h]
  HKEY hKey; // [rsp+58h] [rbp-20h] BYREF
  DWORD dwIndex; // [rsp+60h] [rbp-18h]
  int v13; // [rsp+64h] [rbp-14h]
  DWORD cchName; // [rsp+A0h] [rbp+28h] BYREF

  lpName = 0;
  v8 = &CRegistry::`vftable';
  v3 = (HKEY)*((_QWORD *)this + 3);
  dwIndex = -1;
  v13 = -1;
  v10 = 0;
  hKey = 0;
  v5 = RegOpenKeyExW(v3, a2, 0, 0xF003Fu, &hKey);
  if ( v5 )
  {
    hKey = 0;
  }
  else
  {
    while ( 1 )
    {
      dwIndex = 0;
      cchName = 1024;
      if ( !CRegistry::Allocate((CRegistry *)&v8, 0x800u) )
        break;
      v6 = RegEnumKeyExW(hKey, dwIndex, lpName, &cchName, 0, 0, 0, 0);
      ++cchName;
      if ( v6 == 259 )
        break;
      ++dwIndex;
      if ( v6 )
        break;
      CRegistry::RecurseDeleteKey((CRegistry *)&v8, lpName);
    }
    v5 = RegDeleteKeyW(*((HKEY *)this + 3), a2);
  }
  CRegistry::~CRegistry((CRegistry *)&v8);
  return v5;
}

```

## disassembly

```asm
0x180017040  push    rbp
0x180017042  push    rbx
0x180017043  push    rsi
0x180017044  push    rdi
0x180017045  mov     rbp, rsp
0x180017048  sub     rsp, 78h
0x18001704c  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x180017053  mov     [rbp+lpName], 0
0x18001705b  mov     [rbp+var_38], rax
0x18001705f  mov     rsi, rcx
0x180017062  mov     rcx, [rcx+18h]; hKey
0x180017066  or      eax, 0FFFFFFFFh
0x180017069  mov     [rbp+dwIndex], eax
0x18001706c  mov     r9d, 0F003Fh; samDesired
0x180017072  mov     [rbp+var_14], eax
0x180017075  xor     r8d, r8d; ulOptions
0x180017078  lea     rax, [rbp+hKey]
0x18001707c  mov     [rbp+var_28], 0
0x180017083  mov     [rsp+78h+phkResult], rax; phkResult
0x180017088  mov     rdi, rdx
0x18001708b  mov     [rbp+hKey], 0
0x180017093  call    cs:__imp_RegOpenKeyExW
0x180017099  mov     ebx, eax
0x18001709b  test    eax, eax
0x18001709d  jz      short loc_1800170AC
0x18001709f  mov     [rbp+hKey], 0
0x1800170a7  jmp     loc_180017135
0x1800170ac  mov     edx, 800h; unsigned int
0x1800170b1  mov     [rbp+dwIndex], 0
0x1800170b8  lea     rcx, [rbp+var_38]; this
0x1800170bc  mov     [rbp+cchName], 400h
0x1800170c3  call    ?Allocate@CRegistry@@AEAAPEAXK@Z; CRegistry::Allocate(ulong)
0x1800170c8  test    rax, rax
0x1800170cb  jz      short loc_180017126
0x1800170cd  mov     r8, [rbp+lpName]; lpName
0x1800170d1  lea     r9, [rbp+cchName]; lpcchName
0x1800170d5  mov     edx, [rbp+dwIndex]; dwIndex
0x1800170d8  mov     rcx, [rbp+hKey]; hKey
0x1800170dc  mov     [rsp+78h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800170e5  mov     [rsp+78h+lpcchClass], 0; lpcchClass
0x1800170ee  mov     [rsp+78h+lpClass], 0; lpClass
0x1800170f7  mov     [rsp+78h+phkResult], 0; lpReserved
0x180017100  call    cs:__imp_RegEnumKeyExW
0x180017106  inc     [rbp+cchName]
0x180017109  cmp     eax, 103h
0x18001710e  jz      short loc_180017126
0x180017110  inc     [rbp+dwIndex]
0x180017113  test    eax, eax
0x180017115  jnz     short loc_180017126
0x180017117  mov     rdx, [rbp+lpName]; unsigned __int16 *
0x18001711b  lea     rcx, [rbp+var_38]; this
0x18001711f  call    ?RecurseDeleteKey@CRegistry@@QEAAKPEBG@Z; CRegistry::RecurseDeleteKey(ushort const *)
0x180017124  jmp     short loc_1800170AC
0x180017126  mov     rcx, [rsi+18h]; hKey
0x18001712a  mov     rdx, rdi; lpSubKey
0x18001712d  call    cs:__imp_RegDeleteKeyW
0x180017133  mov     ebx, eax
0x180017135  lea     rcx, [rbp+var_38]; this
0x180017139  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18001713e  mov     eax, ebx
0x180017140  add     rsp, 78h
0x180017144  pop     rdi
0x180017145  pop     rsi
0x180017146  pop     rbx
0x180017147  pop     rbp
0x180017148  retn
```
