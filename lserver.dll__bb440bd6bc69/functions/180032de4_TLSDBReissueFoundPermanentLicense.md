# TLSDBReissueFoundPermanentLicense

- ea: `0x180032de4`
- end: `0x18003301f`
- name: `TLSDBReissueFoundPermanentLicense`
- size: `571`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x180028ab4`
- `0x18002a3b4`

## callees

- `0x180005665`
- `0x18000cff0`
- `0x18001fdac`
- `0x180027d40`
- `0x180032de4`
- `0x180034c3c`
- `0x180035b38`
- `0x180035c74`
- `0x180035cd0`
- `0x180036604`
- `0x1800662a0`
- `0x1800a0fb0`
- `0x1800a1070`

## import_xrefs

- `msvcrt!time` at `0x180032ee1`
- `msvcrt!time` at `0x180032f01`
- `msvcrt!time` at `0x180032ee1`
- `msvcrt!time` at `0x180032f01`
- `KERNEL32!GetCurrentThreadId` at `0x180032ec2`
- `KERNEL32!GetCurrentThreadId` at `0x180032ec2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TLSDBReissueFoundPermanentLicense(
        __int64 *a1,
        const unsigned __int16 *a2,
        struct _DbLicensedProduct *a3,
        __int64 a4)
{
  unsigned int v8; // eax
  int v9; // edx
  unsigned int updated; // ebx
  DWORD CurrentThreadId; // eax
  unsigned int v12; // ebx
  unsigned __int16 *v13; // rax
  int v14; // edx
  int v15; // ecx
  __int64 v16; // rdx
  __int64 v17; // rdx
  char v19[8]; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+38h] [rbp-C8h]
  unsigned __int16 v21[290]; // [rsp+48h] [rbp-B8h] BYREF
  signed int v22; // [rsp+28Ch] [rbp+18Ch]
  char v23; // [rsp+290h] [rbp+190h]
  char v24[8]; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int64 v25; // [rsp+2C8h] [rbp+1C8h]
  unsigned int v26; // [rsp+2DCh] [rbp+1DCh]
  __int64 v27; // [rsp+2E8h] [rbp+1E8h]
  int v28; // [rsp+2F0h] [rbp+1F0h]
  _BYTE v29[4]; // [rsp+1110h] [rbp+1010h] BYREF
  int v30; // [rsp+1114h] [rbp+1014h]
  __int64 v31; // [rsp+1118h] [rbp+1018h]
  __int64 v32; // [rsp+1138h] [rbp+1038h]
  int v33; // [rsp+1140h] [rbp+1040h]

  memset_0(v19, 0, 0x288u);
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v25 = 0;
  v27 = 0;
  v28 = 0;
  v8 = TLSFindDbLicensedProduct(a1, a3, v19);
  updated = v8;
  if ( v23 == 7 )
  {
    updated = -1072693245;
  }
  else if ( !v8 )
  {
    v30 = v20;
    updated = TLSDBKeyPackFind(a1, v9, 0x10000, (__int64)v29, (__int64)v24);
    if ( !updated )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = GenerateRandomNumber(CurrentThreadId) % *(_DWORD *)&g_dwReissueLeaseRange;
      if ( v12 + *(_DWORD *)&g_dwReissueLeaseMinimum + (unsigned int)time(0) >= v26 )
        v22 = v26;
      else
        v22 = v12 + *(_DWORD *)&g_dwReissueLeaseMinimum + time(0);
      TLSDBLockLicenseTable(a1);
      v13 = v21;
      do
      {
        v14 = *(unsigned __int16 *)((char *)v13 + (char *)a2 - (char *)v21);
        v15 = *v13 - v14;
        if ( v15 )
          break;
        ++v13;
      }
      while ( v14 );
      if ( v15 )
      {
        memset_0(v21, 0, 0x40u);
        v16 = -1;
        do
          ++v16;
        while ( a2[v16] );
        StringCchCopyW(v21, v16 + 1, a2);
        v17 = 264;
      }
      else
      {
        v17 = 256;
      }
      updated = TLSDBLicenseUpdateEntry(a1, v17, v19, 0);
      TLSDBUnlockLicenseTable(a1);
      if ( !updated )
      {
        CopyDbLicensedProduct(a3, (struct _DbLicensedProduct *)a4);
        *(_QWORD *)(a4 + 60) = 10000000 * (v22 + 0x2B6109100LL);
        *(_QWORD *)(a4 + 2664) = 0;
      }
    }
  }
  __LicensePack::~__LicensePack((__LicensePack *)v24);
  __LicensePack::~__LicensePack((__LicensePack *)v29);
  return updated;
}

```

## disassembly

```asm
0x180032de4  push    rbp
0x180032de6  push    rbx
0x180032de7  push    rsi
0x180032de8  push    rdi
0x180032de9  push    r12
0x180032deb  push    r14
0x180032ded  push    r15
0x180032def  lea     rbp, [rsp-1E70h]
0x180032df7  mov     eax, 1F70h
0x180032dfc  call    _alloca_probe
0x180032e01  sub     rsp, rax
0x180032e04  mov     rax, cs:__security_cookie
0x180032e0b  xor     rax, rsp
0x180032e0e  mov     [rbp+1EA0h+var_40], rax
0x180032e15  mov     rsi, r9
0x180032e18  mov     r15, r8
0x180032e1b  mov     r14, rdx
0x180032e1e  mov     rdi, rcx
0x180032e21  xor     edx, edx; Val
0x180032e23  mov     r8d, 288h; Size
0x180032e29  lea     rcx, [rsp+1FA0h+var_1F70]; void *
0x180032e2e  call    memset_0
0x180032e33  xor     r12d, r12d
0x180032e36  mov     [rbp+1EA0h+var_E88], r12
0x180032e3d  mov     [rbp+1EA0h+var_E68], r12
0x180032e44  mov     [rbp+1EA0h+var_E60], r12d
0x180032e4b  mov     [rbp+1EA0h+var_1CD8], r12
0x180032e52  mov     [rbp+1EA0h+var_1CB8], r12
0x180032e59  mov     [rbp+1EA0h+var_1CB0], r12d
0x180032e60  lea     r8, [rsp+1FA0h+var_1F70]
0x180032e65  mov     rdx, r15
0x180032e68  mov     rcx, rdi
0x180032e6b  call    TLSFindDbLicensedProduct
0x180032e70  mov     ebx, eax
0x180032e72  cmp     [rbp+1EA0h+var_1D10], 7
0x180032e79  jnz     short loc_180032E85
0x180032e7b  mov     ebx, 0C0100003h
0x180032e80  jmp     loc_180032FE2
0x180032e85  test    eax, eax
0x180032e87  jnz     loc_180032FE2
0x180032e8d  mov     eax, [rsp+1FA0h+var_1F68]
0x180032e91  mov     [rbp+1EA0h+var_E8C], eax
0x180032e97  lea     rax, [rbp+1EA0h+var_1CE0]
0x180032e9e  mov     [rsp+1FA0h+var_1F80], rax
0x180032ea3  lea     r9, [rbp+1EA0h+var_E90]
0x180032eaa  mov     r8d, 10000h
0x180032eb0  mov     rcx, rdi
0x180032eb3  call    TLSDBKeyPackFind
0x180032eb8  mov     ebx, eax
0x180032eba  test    eax, eax
0x180032ebc  jnz     loc_180032FE2
0x180032ec2  call    cs:__imp_GetCurrentThreadId
0x180032ec9  nop     dword ptr [rax+rax+00h]
0x180032ece  mov     ecx, eax; unsigned int
0x180032ed0  call    ?GenerateRandomNumber@@YAKK@Z; GenerateRandomNumber(ulong)
0x180032ed5  xor     edx, edx
0x180032ed7  div     cs:?g_dwReissueLeaseRange@@3KA; ulong g_dwReissueLeaseRange
0x180032edd  mov     ebx, edx
0x180032edf  xor     ecx, ecx; Time
0x180032ee1  call    cs:__imp_time
0x180032ee8  nop     dword ptr [rax+rax+00h]
0x180032eed  add     eax, cs:?g_dwReissueLeaseMinimum@@3KA; ulong g_dwReissueLeaseMinimum
0x180032ef3  add     eax, ebx
0x180032ef5  mov     ecx, [rbp+1EA0h+var_1CC4]
0x180032efb  cmp     eax, ecx
0x180032efd  jnb     short loc_180032F1D
0x180032eff  xor     ecx, ecx; Time
0x180032f01  call    cs:__imp_time
0x180032f08  nop     dword ptr [rax+rax+00h]
0x180032f0d  add     eax, cs:?g_dwReissueLeaseMinimum@@3KA; ulong g_dwReissueLeaseMinimum
0x180032f13  add     eax, ebx
0x180032f15  mov     [rbp+1EA0h+var_1D14], eax
0x180032f1b  jmp     short loc_180032F23
0x180032f1d  mov     [rbp+1EA0h+var_1D14], ecx
0x180032f23  mov     rcx, rdi
0x180032f26  call    TLSDBLockLicenseTable
0x180032f2b  lea     rax, [rsp+1FA0h+var_1F58]
0x180032f30  mov     r8, r14
0x180032f33  sub     r8, rax
0x180032f36  movzx   ecx, word ptr [rax]
0x180032f39  movzx   edx, word ptr [rax+r8]
0x180032f3e  sub     ecx, edx
0x180032f40  jnz     short loc_180032F4A
0x180032f42  add     rax, 2
0x180032f46  test    edx, edx
0x180032f48  jnz     short loc_180032F36
0x180032f4a  test    ecx, ecx
0x180032f4c  jz      short loc_180032F83
0x180032f4e  xor     edx, edx; Val
0x180032f50  lea     r8d, [rdx+40h]; Size
0x180032f54  lea     rcx, [rsp+1FA0h+var_1F58]; void *
0x180032f59  call    memset_0
0x180032f5e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180032f62  inc     rdx
0x180032f65  cmp     [r14+rdx*2], r12w
0x180032f6a  jnz     short loc_180032F62
0x180032f6c  inc     rdx; unsigned __int64
0x180032f6f  mov     r8, r14; unsigned __int16 *
0x180032f72  lea     rcx, [rsp+1FA0h+var_1F58]; unsigned __int16 *
0x180032f77  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180032f7c  mov     edx, 108h
0x180032f81  jmp     short loc_180032F88
0x180032f83  mov     edx, 100h
0x180032f88  xor     r9d, r9d
0x180032f8b  lea     r8, [rsp+1FA0h+var_1F70]
0x180032f90  mov     rcx, rdi
0x180032f93  call    TLSDBLicenseUpdateEntry
0x180032f98  mov     ebx, eax
0x180032f9a  mov     rcx, rdi
0x180032f9d  call    TLSDBUnlockLicenseTable
0x180032fa2  test    ebx, ebx
0x180032fa4  jnz     short loc_180032FE2
0x180032fa6  mov     rdx, rsi; struct _DbLicensedProduct *
0x180032fa9  mov     rcx, r15; struct _DbLicensedProduct *
0x180032fac  call    ?CopyDbLicensedProduct@@YAXPEAU_DbLicensedProduct@@0@Z; CopyDbLicensedProduct(_DbLicensedProduct *,_DbLicensedProduct *)
0x180032fb1  mov     eax, [rbp+1EA0h+var_1D14]
0x180032fb7  movsxd  rcx, eax
0x180032fba  mov     rax, 2B6109100h
0x180032fc4  add     rcx, rax
0x180032fc7  imul    rax, rcx, 989680h
0x180032fce  mov     rcx, rax
0x180032fd1  shr     rcx, 20h
0x180032fd5  mov     [rsi+40h], ecx
0x180032fd8  mov     [rsi+3Ch], eax
0x180032fdb  mov     [rsi+0A68h], r12
0x180032fe2  lea     rcx, [rbp+1EA0h+var_1CE0]; this
0x180032fe9  call    ??1__LicensePack@@QEAA@XZ; __LicensePack::~__LicensePack(void)
0x180032fee  nop
0x180032fef  lea     rcx, [rbp+1EA0h+var_E90]; this
0x180032ff6  call    ??1__LicensePack@@QEAA@XZ; __LicensePack::~__LicensePack(void)
0x180032ffb  mov     eax, ebx
0x180032ffd  mov     rcx, [rbp+1EA0h+var_40]
0x180033004  xor     rcx, rsp; StackCookie
0x180033007  call    __security_check_cookie
0x18003300c  add     rsp, 1F70h
0x180033013  pop     r15
0x180033015  pop     r14
0x180033017  pop     r12
0x180033019  pop     rdi
0x18003301a  pop     rsi
0x18003301b  pop     rbx
0x18003301c  pop     rbp
0x18003301d  retn
```
