# DwCreateInterfaceKeyIfNotPresent(ushort *,ushort *,ulong)

- ea: `0x18006afc8`
- end: `0x18006b179`
- name: `?DwCreateInterfaceKeyIfNotPresent@@YAKPEAG0K@Z`
- size: `433`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800699c4`

## callees

- `0x180025e2c`
- `0x18006afc8`
- `0x18006b82c`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18006b096`
- `ADVAPI32!RegOpenKeyExW` at `0x18006b096`
- `ADVAPI32!RegCloseKey` at `0x18006b154`
- `ADVAPI32!RegCloseKey` at `0x18006b154`
- `ADVAPI32!RegCreateKeyExW` at `0x18006b0e2`
- `ADVAPI32!RegCreateKeyExW` at `0x18006b0e2`

## string_xrefs

- `0x18006b0f1`: `DwCreateInterfaceIfNotPresent: Failed to add %ws, 0x%x`
- `0x18006b119`: `DwCreateInterfaceIfNotPresent: Failed to add %ws, 0x%x`

## pseudocode

```c
__int64 __fastcall DwCreateInterfaceKeyIfNotPresent(unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3)
{
  WCHAR *v6; // rax
  __int64 v7; // r9
  __int64 v8; // rcx
  unsigned __int16 *v9; // r10
  WCHAR *v10; // rcx
  unsigned int v11; // ebx
  unsigned int v12; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF
  int v17; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v18[2044]; // [rsp+274h] [rbp+174h] BYREF

  dwDisposition = 0;
  hKey = 0;
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  v6 = SubKey;
  v7 = 260;
  v8 = 2147483646;
  v9 = a2;
  do
  {
    if ( !v8 )
      break;
    if ( !*v9 )
      break;
    *v6++ = *v9++;
    --v8;
    --v7;
  }
  while ( v7 );
  v10 = v6 - 1;
  if ( v7 )
    v10 = v6;
  *v10 = 0;
  StringCchCatW(SubKey, 0x104u, a1);
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20006u, &hKey);
  if ( v11
    && (v12 = RegCreateKeyExW(
                HKEY_LOCAL_MACHINE,
                SubKey,
                0,
                (LPWSTR)&SourceString,
                0,
                0xF003Fu,
                0,
                &hKey,
                &dwDisposition),
        (v11 = v12) != 0) )
  {
    TraceIt(a3, "DwCreateInterfaceIfNotPresent: Failed to add %ws, 0x%x", a2, v12);
    if ( (_QWORD)xmmword_1800CA020 )
    {
      LOWORD(v17) = 0;
      FormatRRASErrorString(&v17, L"DwCreateInterfaceIfNotPresent: Failed to add %ws, 0x%x", a2, v11);
      ((void (__fastcall *)(__int64, _QWORD, int *))gRegHelpTemplateFunc)(gRegHelpEtwContext, xmmword_1800CA020, &v17);
    }
  }
  else
  {
    RegCloseKey(hKey);
  }
  return v11;
}

```

## disassembly

```asm
0x18006afc8  push    rbp
0x18006afca  push    rbx
0x18006afcb  push    rsi
0x18006afcc  push    rdi
0x18006afcd  push    r14
0x18006afcf  lea     rbp, [rsp-980h]
0x18006afd7  sub     rsp, 0A80h
0x18006afde  mov     rax, cs:__security_cookie
0x18006afe5  xor     rax, rsp
0x18006afe8  mov     [rbp+9A0h+var_30], rax
0x18006afef  xor     r14d, r14d
0x18006aff2  mov     esi, r8d
0x18006aff5  mov     rdi, rdx
0x18006aff8  mov     [rsp+0AA0h+dwDisposition], r14d
0x18006affd  mov     rbx, rcx
0x18006b000  mov     [rsp+0AA0h+hKey], r14
0x18006b005  xor     edx, edx; Val
0x18006b007  mov     [rbp+9A0h+var_830], r14d
0x18006b00e  mov     r8d, 7FCh; Size
0x18006b014  lea     rcx, [rbp+9A0h+var_82C]; void *
0x18006b01b  call    memset_0
0x18006b020  mov     r11d, 104h
0x18006b026  lea     rax, [rsp+0AA0h+SubKey]
0x18006b02b  mov     r9d, r11d
0x18006b02e  mov     ecx, 7FFFFFFEh
0x18006b033  mov     r10, rdi
0x18006b036  test    rcx, rcx
0x18006b039  jz      short loc_18006B058
0x18006b03b  movzx   edx, word ptr [r10]
0x18006b03f  test    dx, dx
0x18006b042  jz      short loc_18006B058
0x18006b044  mov     [rax], dx
0x18006b047  add     r10, 2
0x18006b04b  add     rax, 2
0x18006b04f  dec     rcx
0x18006b052  sub     r9, 1
0x18006b056  jnz     short loc_18006B036
0x18006b058  test    r9, r9
0x18006b05b  lea     rcx, [rax-2]
0x18006b05f  mov     r8, rbx; unsigned __int16 *
0x18006b062  mov     rdx, r11; unsigned __int64
0x18006b065  cmovnz  rcx, rax
0x18006b069  mov     [rcx], r14w
0x18006b06d  lea     rcx, [rsp+0AA0h+SubKey]; unsigned __int16 *
0x18006b072  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006b077  lea     rax, [rsp+0AA0h+hKey]
0x18006b07c  mov     r9d, 20006h; samDesired
0x18006b082  xor     r8d, r8d; ulOptions
0x18006b085  mov     [rsp+0AA0h+phkResult], rax; phkResult
0x18006b08a  lea     rdx, [rsp+0AA0h+SubKey]; lpSubKey
0x18006b08f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006b096  call    cs:__imp_RegOpenKeyExW
0x18006b09c  mov     ebx, eax
0x18006b09e  test    eax, eax
0x18006b0a0  jz      loc_18006B14F
0x18006b0a6  lea     rax, [rsp+0AA0h+dwDisposition]
0x18006b0ab  xor     r8d, r8d; Reserved
0x18006b0ae  mov     [rsp+0AA0h+lpdwDisposition], rax; lpdwDisposition
0x18006b0b3  lea     r9, SourceString; lpClass
0x18006b0ba  lea     rax, [rsp+0AA0h+hKey]
0x18006b0bf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006b0c6  mov     [rsp+0AA0h+var_A68], rax; phkResult
0x18006b0cb  lea     rdx, [rsp+0AA0h+SubKey]; lpSubKey
0x18006b0d0  mov     [rsp+0AA0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18006b0d5  mov     [rsp+0AA0h+samDesired], 0F003Fh; samDesired
0x18006b0dd  mov     dword ptr [rsp+0AA0h+phkResult], r14d; dwOptions
0x18006b0e2  call    cs:__imp_RegCreateKeyExW
0x18006b0e8  mov     ebx, eax
0x18006b0ea  test    eax, eax
0x18006b0ec  jz      short loc_18006B14F
0x18006b0ee  mov     r9d, eax
0x18006b0f1  lea     rdx, aDwcreateinterf; "DwCreateInterfaceIfNotPresent: Failed t"...
0x18006b0f8  mov     r8, rdi
0x18006b0fb  mov     ecx, esi; unsigned int
0x18006b0fd  call    ?TraceIt@@YAXKPEADZZ; TraceIt(ulong,char *,...)
0x18006b102  cmp     qword ptr cs:xmmword_1800CA020, r14
0x18006b109  jz      short loc_18006B15A
0x18006b10b  mov     r9d, ebx
0x18006b10e  mov     word ptr [rbp+9A0h+var_830], r14w
0x18006b116  mov     r8, rdi
0x18006b119  lea     rdx, aDwcreateinterf_0; "DwCreateInterfaceIfNotPresent: Failed t"...
0x18006b120  lea     rcx, [rbp+9A0h+var_830]
0x18006b127  call    FormatRRASErrorString
0x18006b12c  mov     rdx, qword ptr cs:xmmword_1800CA020
0x18006b133  lea     r8, [rbp+9A0h+var_830]
0x18006b13a  mov     rcx, cs:gRegHelpEtwContext
0x18006b141  mov     rax, cs:gRegHelpTemplateFunc
0x18006b148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b14d  jmp     short loc_18006B15A
0x18006b14f  mov     rcx, [rsp+0AA0h+hKey]; hKey
0x18006b154  call    cs:__imp_RegCloseKey
0x18006b15a  mov     eax, ebx
0x18006b15c  mov     rcx, [rbp+9A0h+var_30]
0x18006b163  xor     rcx, rsp; StackCookie
0x18006b166  call    __security_check_cookie
0x18006b16b  add     rsp, 0A80h
0x18006b172  pop     r14
0x18006b174  pop     rdi
0x18006b175  pop     rsi
0x18006b176  pop     rbx
0x18006b177  pop     rbp
0x18006b178  retn
```
