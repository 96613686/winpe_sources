# UpdateAccountLockoutDB(_IASATTRIBUTE &,int,int *)

- ea: `0x180018f04`
- end: `0x180018fa9`
- name: `?UpdateAccountLockoutDB@@YAXAEAU_IASATTRIBUTE@@HPEAH@Z`
- size: `165`
- prototype: `void __fastcall(struct _IASATTRIBUTE *, int, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800194b8`

## callees

- `0x1800115f0`
- `0x180011664`
- `0x180011708`
- `0x18001193c`
- `0x180011a6c`
- `0x180018f04`

## import_xrefs

- `msvcrt!free` at `0x180018f89`
- `msvcrt!free` at `0x180018f89`

## pseudocode

```c
void __fastcall UpdateAccountLockoutDB(struct _IASATTRIBUTE *a1, int a2, int *a3)
{
  _WORD *v5; // rdi
  WCHAR *v6; // rdx
  unsigned __int16 *v7; // rcx
  unsigned __int16 *v8; // [rsp+20h] [rbp-18h] BYREF
  _WORD *v9; // [rsp+28h] [rbp-10h]

  SamExtractor::SamExtractor((SamExtractor *)&v8, a1);
  v5 = v9;
  v6 = (WCHAR *)&base;
  v7 = v8;
  if ( v9 )
  {
    v6 = v8;
    v7 = v9 + 1;
  }
  AccountLockoutOpenAndQuery(v7, v6);
  if ( a2 )
    AccountLockoutUpdatePass(0);
  else
    AccountLockoutUpdateFail(0, a3);
  if ( v5 )
    *v5 = 92;
}

```

## disassembly

```asm
0x180018f04  mov     [rsp+arg_0], rbx
0x180018f09  mov     [rsp+arg_8], rsi
0x180018f0e  push    rdi
0x180018f0f  sub     rsp, 30h
0x180018f13  mov     esi, edx
0x180018f15  mov     rbx, r8
0x180018f18  mov     rdx, rcx; struct _IASATTRIBUTE *
0x180018f1b  lea     rcx, [rsp+38h+var_18]; this
0x180018f20  call    ??0SamExtractor@@QEAA@AEBU_IASATTRIBUTE@@@Z; SamExtractor::SamExtractor(_IASATTRIBUTE const &)
0x180018f25  mov     rdi, [rsp+38h+var_10]
0x180018f2a  lea     rdx, base
0x180018f31  mov     rcx, [rsp+38h+var_18]
0x180018f36  test    rdi, rdi
0x180018f39  cmovnz  rdx, rcx; unsigned __int16 *
0x180018f3d  jz      short loc_180018F43
0x180018f3f  lea     rcx, [rdi+2]; unsigned __int16 *
0x180018f43  lea     r8, [rsp+38h+Block]
0x180018f48  mov     [rsp+38h+Block], 0
0x180018f51  call    AccountLockoutOpenAndQuery
0x180018f56  test    esi, esi
0x180018f58  jz      short loc_180018F69
0x180018f5a  mov     rbx, [rsp+38h+Block]
0x180018f5f  mov     rcx, rbx
0x180018f62  call    AccountLockoutUpdatePass
0x180018f67  jmp     short loc_180018F79
0x180018f69  mov     rdx, rbx
0x180018f6c  mov     rbx, [rsp+38h+Block]
0x180018f71  mov     rcx, rbx; this
0x180018f74  call    AccountLockoutUpdateFail
0x180018f79  test    rbx, rbx
0x180018f7c  jz      short loc_180018F8F
0x180018f7e  mov     rcx, rbx; this
0x180018f81  call    ??1AccountInfo@@IEAA@XZ; AccountInfo::~AccountInfo(void)
0x180018f86  mov     rcx, rbx; Block
0x180018f89  call    cs:__imp_free
0x180018f8f  test    rdi, rdi
0x180018f92  jz      short loc_180018F99
0x180018f94  mov     word ptr [rdi], 5Ch ; '\'
0x180018f99  mov     rbx, [rsp+38h+arg_0]
0x180018f9e  mov     rsi, [rsp+38h+arg_8]
0x180018fa3  add     rsp, 30h
0x180018fa7  pop     rdi
0x180018fa8  retn
```
