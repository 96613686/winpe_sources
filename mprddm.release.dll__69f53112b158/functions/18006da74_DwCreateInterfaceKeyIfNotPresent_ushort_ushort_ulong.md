# DwCreateInterfaceKeyIfNotPresent(ushort *,ushort *,ulong)

- ea: `0x18006da74`
- end: `0x18006dc49`
- name: `?DwCreateInterfaceKeyIfNotPresent@@YAKPEAG0K@Z`
- size: `469`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18006c404`

## callees

- `0x180028058`
- `0x18006da74`
- `0x18006e34c`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18006db49`
- `ADVAPI32!RegOpenKeyExW` at `0x18006db49`
- `ADVAPI32!RegCloseKey` at `0x18006dc13`
- `ADVAPI32!RegCloseKey` at `0x18006dc13`
- `ADVAPI32!RegCreateKeyExW` at `0x18006db9b`
- `ADVAPI32!RegCreateKeyExW` at `0x18006db9b`

## string_xrefs

- `0x18006dbb0`: `DwCreateInterfaceIfNotPresent: Failed to add %ws, 0x%x`
- `0x18006dbd8`: `DwCreateInterfaceIfNotPresent: Failed to add %ws, 0x%x`

## pseudocode

```c
__int64 __fastcall DwCreateInterfaceKeyIfNotPresent(unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3)
{
  WCHAR *v6; // rcx
  __int64 v7; // r8
  WCHAR v8; // ax
  WCHAR *v9; // rax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  int v16; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v17[2044]; // [rsp+274h] [rbp+174h] BYREF

  dwDisposition = 0;
  hKey = 0;
  v16 = 0;
  memset_0(v17, 0, sizeof(v17));
  v6 = SubKey;
  v7 = 260;
  do
  {
    if ( v7 == -2147483386 )
      break;
    v8 = *(WCHAR *)((char *)v6 + (char *)a2 - (char *)SubKey);
    if ( !v8 )
      break;
    *v6++ = v8;
    --v7;
  }
  while ( v7 );
  v9 = v6 - 1;
  if ( v7 )
    v9 = v6;
  *v9 = 0;
  StringCchCatW(SubKey, 0x104u, a1);
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20006u, &hKey);
  if ( v10
    && (v11 = RegCreateKeyExW(
                HKEY_LOCAL_MACHINE,
                SubKey,
                0,
                (LPWSTR)&SourceString,
                0,
                0xF003Fu,
                0,
                &hKey,
                &dwDisposition),
        (v10 = v11) != 0) )
  {
    TraceIt(a3, "DwCreateInterfaceIfNotPresent: Failed to add %ws, 0x%x", a2, v11);
    if ( (_QWORD)xmmword_1800D1020 )
    {
      LOWORD(v16) = 0;
      FormatRRASErrorString(&v16, L"DwCreateInterfaceIfNotPresent: Failed to add %ws, 0x%x", a2, v10);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRegHelpTemplateFunc)(gRegHelpEtwContext, xmmword_1800D1020, &v16);
    }
  }
  else
  {
    RegCloseKey(hKey);
  }
  return v10;
}

```

## disassembly

```asm
0x18006da74  mov     [rsp-8+arg_0], rbx
0x18006da79  mov     [rsp-8+arg_18], rsi
0x18006da7e  push    rbp
0x18006da7f  push    rdi
0x18006da80  push    r14
0x18006da82  lea     rbp, [rsp-980h]
0x18006da8a  sub     rsp, 0A80h
0x18006da91  mov     rax, cs:__security_cookie
0x18006da98  xor     rax, rsp
0x18006da9b  mov     [rbp+990h+var_20], rax
0x18006daa2  xor     r14d, r14d
0x18006daa5  mov     esi, r8d
0x18006daa8  mov     rdi, rdx
0x18006daab  mov     [rsp+0A90h+dwDisposition], r14d
0x18006dab0  mov     rbx, rcx
0x18006dab3  mov     [rsp+0A90h+hKey], r14
0x18006dab8  xor     edx, edx; Val
0x18006daba  mov     [rbp+990h+var_820], r14d
0x18006dac1  mov     r8d, 7FCh; Size
0x18006dac7  lea     rcx, [rbp+990h+var_81C]; void *
0x18006dace  call    memset_0
0x18006dad3  mov     edx, 104h; unsigned __int64
0x18006dad8  lea     rax, [rsp+0A90h+SubKey]
0x18006dadd  mov     r9, rdi
0x18006dae0  lea     rcx, [rsp+0A90h+SubKey]
0x18006dae5  mov     r8d, edx
0x18006dae8  sub     r9, rax
0x18006daeb  lea     rax, [r8+7FFFFEFAh]
0x18006daf2  test    rax, rax
0x18006daf5  jz      short loc_18006DB0E
0x18006daf7  movzx   eax, word ptr [r9+rcx]
0x18006dafc  test    ax, ax
0x18006daff  jz      short loc_18006DB0E
0x18006db01  mov     [rcx], ax
0x18006db04  add     rcx, 2
0x18006db08  sub     r8, 1
0x18006db0c  jnz     short loc_18006DAEB
0x18006db0e  test    r8, r8
0x18006db11  lea     rax, [rcx-2]
0x18006db15  mov     r8, rbx; unsigned __int16 *
0x18006db18  cmovnz  rax, rcx
0x18006db1c  lea     rcx, [rsp+0A90h+SubKey]; unsigned __int16 *
0x18006db21  mov     [rax], r14w
0x18006db25  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006db2a  lea     rax, [rsp+0A90h+hKey]
0x18006db2f  mov     r9d, 20006h; samDesired
0x18006db35  xor     r8d, r8d; ulOptions
0x18006db38  mov     [rsp+0A90h+phkResult], rax; phkResult
0x18006db3d  lea     rdx, [rsp+0A90h+SubKey]; lpSubKey
0x18006db42  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006db49  call    cs:__imp_RegOpenKeyExW
0x18006db50  nop     dword ptr [rax+rax+00h]
0x18006db55  mov     ebx, eax
0x18006db57  test    eax, eax
0x18006db59  jz      loc_18006DC0E
0x18006db5f  lea     rax, [rsp+0A90h+dwDisposition]
0x18006db64  xor     r8d, r8d; Reserved
0x18006db67  mov     [rsp+0A90h+lpdwDisposition], rax; lpdwDisposition
0x18006db6c  lea     r9, SourceString; lpClass
0x18006db73  lea     rax, [rsp+0A90h+hKey]
0x18006db78  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006db7f  mov     [rsp+0A90h+var_A58], rax; phkResult
0x18006db84  lea     rdx, [rsp+0A90h+SubKey]; lpSubKey
0x18006db89  mov     [rsp+0A90h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18006db8e  mov     [rsp+0A90h+samDesired], 0F003Fh; samDesired
0x18006db96  mov     dword ptr [rsp+0A90h+phkResult], r14d; dwOptions
0x18006db9b  call    cs:__imp_RegCreateKeyExW
0x18006dba2  nop     dword ptr [rax+rax+00h]
0x18006dba7  mov     ebx, eax
0x18006dba9  test    eax, eax
0x18006dbab  jz      short loc_18006DC0E
0x18006dbad  mov     r9d, eax
0x18006dbb0  lea     rdx, aDwcreateinterf; "DwCreateInterfaceIfNotPresent: Failed t"...
0x18006dbb7  mov     r8, rdi
0x18006dbba  mov     ecx, esi; unsigned int
0x18006dbbc  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006dbc1  cmp     qword ptr cs:xmmword_1800D1020, r14
0x18006dbc8  jz      short loc_18006DC1F
0x18006dbca  mov     r9d, ebx
0x18006dbcd  mov     word ptr [rbp+990h+var_820], r14w
0x18006dbd5  mov     r8, rdi
0x18006dbd8  lea     rdx, aDwcreateinterf_0; "DwCreateInterfaceIfNotPresent: Failed t"...
0x18006dbdf  lea     rcx, [rbp+990h+var_820]
0x18006dbe6  call    FormatRRASErrorString
0x18006dbeb  mov     rdx, qword ptr cs:xmmword_1800D1020
0x18006dbf2  lea     r8, [rbp+990h+var_820]
0x18006dbf9  mov     rcx, cs:gRegHelpEtwContext
0x18006dc00  mov     rax, cs:gRegHelpTemplateFunc
0x18006dc07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dc0c  jmp     short loc_18006DC1F
0x18006dc0e  mov     rcx, [rsp+0A90h+hKey]; hKey
0x18006dc13  call    cs:__imp_RegCloseKey
0x18006dc1a  nop     dword ptr [rax+rax+00h]
0x18006dc1f  mov     eax, ebx
0x18006dc21  mov     rcx, [rbp+990h+var_20]
0x18006dc28  xor     rcx, rsp; StackCookie
0x18006dc2b  call    __security_check_cookie
0x18006dc30  lea     r11, [rsp+0A90h+var_10]
0x18006dc38  mov     rbx, [r11+20h]
0x18006dc3c  mov     rsi, [r11+38h]
0x18006dc40  mov     rsp, r11
0x18006dc43  pop     r14
0x18006dc45  pop     rdi
0x18006dc46  pop     rbp
0x18006dc47  retn
```
