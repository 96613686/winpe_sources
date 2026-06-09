# CGlobalConfigManager::SetUsagePolicy(UsagePolicy const *)

- ea: `0x1800d82e4`
- end: `0x1800d842c`
- name: `?SetUsagePolicy@CGlobalConfigManager@@QEAAJPEBUUsagePolicy@@@Z`
- size: `328`
- prototype: `__int64 __fastcall(CGlobalConfigManager *this, const struct UsagePolicy *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18007de68`

## callees

- `0x18000cea4`
- `0x18009b290`
- `0x1800d82e4`
- `0x1800e7fc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d837e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800d837e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d8301`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800d8301`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d8340`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800d8340`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d8352`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800d8352`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueA` at `0x1800d83d3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueA` at `0x1800d83d3`

## string_xrefs

- `0x1800d8419`: `C:\__w\1\s\src\DeliveryOptimization\ConfigManagement\win10\UsagePolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CGlobalConfigManager::SetUsagePolicy(CGlobalConfigManager *this, const struct UsagePolicy *a2)
{
  RTL_SRWLOCK *v4; // rsi
  bool v5; // r14
  struct CPersistenceLocation *v6; // rax
  const CHAR *v7; // rbx
  struct CPersistenceLocation *v8; // rax
  LSTATUS v9; // eax
  unsigned __int64 v10; // r9
  int lpData; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = (RTL_SRWLOCK *)((char *)this + 544);
  AcquireSRWLockShared((PSRWLOCK)this + 68);
  v5 = !*((_BYTE *)this + 540)
    || *(_QWORD *)a2 != *((_QWORD *)this + 65)
    || *((_QWORD *)a2 + 1) != *((_QWORD *)this + 66)
    || *((_DWORD *)a2 + 4) != *((_DWORD *)this + 134);
  ReleaseSRWLockShared(v4);
  if ( v5 )
  {
    AcquireSRWLockExclusive(v4);
    *(_OWORD *)((char *)this + 520) = *(_OWORD *)a2;
    *((_DWORD *)this + 134) = *((_DWORD *)a2 + 4);
    if ( !*((_BYTE *)this + 540) )
      *((_BYTE *)this + 540) = 1;
    ReleaseSRWLockExclusive(v4);
    try
    {
      g_LogUsagePolicy(a2);
      v6 = CPersistenceLocation::Instance();
      v7 = (char *)v6 + 32;
      if ( *((_QWORD *)v6 + 7) > 0xFu )
        v7 = *(const CHAR **)v7;
      v8 = CPersistenceLocation::Instance();
      v9 = RegSetKeyValueA((HKEY)(-(__int64)(*((_BYTE *)v8 + 160) != 0) - 2147483645), v7, "UsagePolicy", 3u, a2, 0x14u);
      v10 = (unsigned __int16)v9 | 0x80070000;
      if ( v9 <= 0 )
        v10 = (unsigned int)v9;
      if ( (v10 & 0x80000000) != 0LL )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x35,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\win10\\UsagePolicy.cpp",
          (const char *)v10,
          lpData);
    }
    catch ( std::bad_alloc )
    {
      return 2147942414LL;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x632,
                             (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\ConfigManagement\\GlobalConfigManager.cpp",
                             (const char *)v10);
    }
  }
  return !v5;
}

```

## disassembly

```asm
0x1800d82e4  mov     [rsp+arg_10], rbx
0x1800d82e9  push    rsi
0x1800d82ea  push    rdi
0x1800d82eb  push    r14
0x1800d82ed  sub     rsp, 50h
0x1800d82f1  mov     rdi, rdx
0x1800d82f4  mov     rbx, rcx
0x1800d82f7  lea     rsi, [rcx+220h]
0x1800d82fe  mov     rcx, rsi; SRWLock
0x1800d8301  call    cs:__imp_AcquireSRWLockShared
0x1800d8307  nop
0x1800d8308  cmp     byte ptr [rbx+21Ch], 0
0x1800d830f  jz      short loc_1800D833A
0x1800d8311  mov     rax, [rdi]
0x1800d8314  cmp     rax, [rbx+208h]
0x1800d831b  jnz     short loc_1800D833A
0x1800d831d  mov     rax, [rdi+8]
0x1800d8321  cmp     rax, [rbx+210h]
0x1800d8328  jnz     short loc_1800D833A
0x1800d832a  mov     eax, [rdi+10h]
0x1800d832d  cmp     eax, [rbx+218h]
0x1800d8333  jnz     short loc_1800D833A
0x1800d8335  xor     r14b, r14b
0x1800d8338  jmp     short loc_1800D833D
0x1800d833a  mov     r14b, 1
0x1800d833d  mov     rcx, rsi; SRWLock
0x1800d8340  call    cs:__imp_ReleaseSRWLockShared
0x1800d8346  test    r14b, r14b
0x1800d8349  jz      loc_1800D83F4
0x1800d834f  mov     rcx, rsi; SRWLock
0x1800d8352  call    cs:__imp_AcquireSRWLockExclusive
0x1800d8358  movups  xmm0, xmmword ptr [rdi]
0x1800d835b  movups  xmmword ptr [rbx+208h], xmm0
0x1800d8362  mov     eax, [rdi+10h]
0x1800d8365  mov     [rbx+218h], eax
0x1800d836b  cmp     byte ptr [rbx+21Ch], 0
0x1800d8372  jnz     short loc_1800D837B
0x1800d8374  mov     byte ptr [rbx+21Ch], 1
0x1800d837b  mov     rcx, rsi; SRWLock
0x1800d837e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800d8384  mov     rcx, rdi
0x1800d8387  call    g_LogUsagePolicy
0x1800d838c  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x1800d8391  lea     rbx, [rax+20h]
0x1800d8395  cmp     qword ptr [rbx+18h], 0Fh
0x1800d839a  jbe     short loc_1800D839F
0x1800d839c  mov     rbx, [rbx]
0x1800d839f  call    ?Instance@CPersistenceLocation@@SAAEAV1@XZ; CPersistenceLocation::Instance(void)
0x1800d83a4  mov     al, [rax+0A0h]
0x1800d83aa  neg     al
0x1800d83ac  sbb     rcx, rcx
0x1800d83af  add     rcx, 0FFFFFFFF80000003h; hKey
0x1800d83b6  mov     [rsp+68h+cbData], 14h; cbData
0x1800d83be  mov     [rsp+68h+lpData], rdi; int
0x1800d83c3  mov     r9d, 3; dwType
0x1800d83c9  lea     r8, Value; "UsagePolicy"
0x1800d83d0  mov     rdx, rbx; lpSubKey
0x1800d83d3  call    cs:__imp_RegSetKeyValueA
0x1800d83d9  movzx   r9d, ax
0x1800d83dd  or      r9d, 80070000h
0x1800d83e4  test    eax, eax
0x1800d83e6  cmovle  r9d, eax; char *
0x1800d83ea  mov     rcx, [rsp+68h]; this
0x1800d83ef  test    r9d, r9d
0x1800d83f2  js      short loc_1800D8419
0x1800d83f4  movzx   eax, r14b
0x1800d83f8  xor     eax, 1
0x1800d83fb  jmp     short loc_1800D8408
0x1800d83fd  mov     eax, [rsp+68h+var_38]
0x1800d8401  jmp     short loc_1800D8408
0x1800d8403  mov     eax, 8007000Eh
0x1800d8408  mov     rbx, [rsp+68h+arg_10]
0x1800d8410  add     rsp, 50h
0x1800d8414  pop     r14
0x1800d8416  pop     rdi
0x1800d8417  pop     rsi
0x1800d8418  retn
0x1800d8419  lea     r8, aCW1SSrcDeliver_96; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800d8420  mov     edx, 35h ; '5'; void *
0x1800d8425  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
