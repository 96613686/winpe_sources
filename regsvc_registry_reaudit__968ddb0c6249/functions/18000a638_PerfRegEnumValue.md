# PerfRegEnumValue

- ea: `0x18000a638`
- end: `0x18000a7b1`
- name: `PerfRegEnumValue`
- size: `377`
- prototype: `__int64 __usercall@<rax>(HKEY@<rcx>, unsigned int *, unsigned __int8 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001c734`

## callees

- `0x180008b58`
- `0x1800093a8`
- `0x18000a638`

## import_xrefs

- `ntdll!RtlRunOnceExecuteOnce` at `0x18000a663`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18000a663`
- `ntdll!RtlCopyUnicodeString` at `0x18000a6fd`
- `ntdll!RtlCopyUnicodeString` at `0x18000a6fd`

## pseudocode

```c
__int64 __fastcall PerfRegEnumValue(
        HKEY a1,
        unsigned int a2,
        struct _UNICODE_STRING *a3,
        __int64 a4,
        unsigned int *a5,
        unsigned __int8 *a6,
        unsigned int *a7,
        unsigned int *a8)
{
  __int64 v9; // rdi
  const UNICODE_STRING *v12; // rdx
  _DWORD v13[2]; // [rsp+40h] [rbp-28h] BYREF
  const wchar_t *v14; // [rsp+48h] [rbp-20h]
  int v15; // [rsp+50h] [rbp-18h]
  const wchar_t *v16; // [rsp+58h] [rbp-10h]

  v9 = a2;
  RtlRunOnceExecuteOnce(qword_18002B570, PerfpInitializeCallback, 0, 0);
  v13[0] = 917516;
  v14 = L"Global";
  v16 = L"Costly";
  v15 = 917516;
  if ( !a3 || !a3->Buffer )
    return 87;
  if ( ((unsigned __int64)(a1 + 536870892) & 0xFFFFFFFFFFFFFFEFuLL) == 0 )
    return PerfEnumTextValue(a1, a5, a6, a7, a8);
  if ( (unsigned int)v9 < 2 )
  {
    v12 = (const UNICODE_STRING *)&v13[4 * v9];
    if ( a3->MaximumLength >= v12->Length )
    {
      a3->Length = v12->Length;
      RtlCopyUnicodeString(a3, v12);
      if ( a5 )
        *a5 = 3;
      return PerfRegQueryValueEx(a1, &stru_1800206B8, a3, 0, a5, a6, a7, a8);
    }
    else
    {
      return 234;
    }
  }
  else
  {
    *a7 = 0;
    return 259;
  }
}

```

## disassembly

```asm
0x18000a638  mov     [rsp+arg_0], rbx
0x18000a63d  mov     [rsp+arg_8], rsi
0x18000a642  push    rdi
0x18000a643  sub     rsp, 60h
0x18000a647  mov     rbx, r8
0x18000a64a  mov     edi, edx
0x18000a64c  mov     rsi, rcx
0x18000a64f  lea     rdx, PerfpInitializeCallback
0x18000a656  xor     r8d, r8d
0x18000a659  lea     rcx, qword_18002B570
0x18000a660  xor     r9d, r9d
0x18000a663  call    cs:__imp_RtlRunOnceExecuteOnce
0x18000a669  mov     [rsp+68h+var_28], 0E000Ch
0x18000a671  lea     rax, ?GLOBAL_STRING@@3QBGB; "Global"
0x18000a678  mov     [rsp+68h+var_20], rax
0x18000a67d  lea     rax, ?COSTLY_STRING@@3QBGB; "Costly"
0x18000a684  mov     [rsp+68h+var_10], rax
0x18000a689  mov     [rsp+68h+var_18], 0E000Ch
0x18000a691  test    rbx, rbx
0x18000a694  jz      loc_18000A79C
0x18000a69a  cmp     qword ptr [rbx+8], 0
0x18000a69f  jz      loc_18000A79C
0x18000a6a5  lea     rax, [rsi+7FFFFFB0h]
0x18000a6ac  test    rax, 0FFFFFFFFFFFFFFEFh
0x18000a6b2  jz      loc_18000A759
0x18000a6b8  cmp     edi, 2
0x18000a6bb  jb      short loc_18000A6D5
0x18000a6bd  mov     rax, [rsp+68h+arg_30]
0x18000a6c5  mov     dword ptr [rax], 0
0x18000a6cb  mov     eax, 103h
0x18000a6d0  jmp     loc_18000A7A1
0x18000a6d5  mov     rax, rdi
0x18000a6d8  lea     rdx, [rsp+68h+var_28]
0x18000a6dd  shl     rax, 4
0x18000a6e1  add     rdx, rax; SourceString
0x18000a6e4  movzx   eax, word ptr [rdx]
0x18000a6e7  cmp     [rbx+2], ax
0x18000a6eb  jnb     short loc_18000A6F7
0x18000a6ed  mov     eax, 0EAh
0x18000a6f2  jmp     loc_18000A7A1
0x18000a6f7  mov     rcx, rbx; DestinationString
0x18000a6fa  mov     [rbx], ax
0x18000a6fd  call    cs:__imp_RtlCopyUnicodeString
0x18000a703  mov     rcx, [rsp+68h+arg_20]
0x18000a70b  test    rcx, rcx
0x18000a70e  jz      short loc_18000A716
0x18000a710  mov     dword ptr [rcx], 3
0x18000a716  mov     rax, [rsp+68h+arg_38]
0x18000a71e  lea     rdx, stru_1800206B8; struct _UNICODE_STRING *
0x18000a725  mov     [rsp+68h+var_30], rax; unsigned int *
0x18000a72a  xor     r9d, r9d; unsigned int *
0x18000a72d  mov     rax, [rsp+68h+arg_30]
0x18000a735  mov     r8, rbx; struct _UNICODE_STRING *
0x18000a738  mov     [rsp+68h+var_38], rax; unsigned int *
0x18000a73d  mov     rax, [rsp+68h+arg_28]
0x18000a745  mov     [rsp+68h+var_40], rax; unsigned __int8 *
0x18000a74a  mov     [rsp+68h+var_48], rcx; unsigned int *
0x18000a74f  mov     rcx, rsi; HKEY
0x18000a752  call    ?PerfRegQueryValueEx@@YAJPEAUHKEY__@@PEBU_UNICODE_STRING@@1PEAK2PEAE22@Z; PerfRegQueryValueEx(HKEY__ *,_UNICODE_STRING const *,_UNICODE_STRING const *,ulong *,ulong *,uchar *,ulong *,ulong *)
0x18000a757  jmp     short loc_18000A7A1
0x18000a759  mov     rax, [rsp+68h+arg_38]
0x18000a761  mov     r8, rbx
0x18000a764  mov     [rsp+68h+var_30], rax; unsigned int *
0x18000a769  mov     edx, edi
0x18000a76b  mov     rax, [rsp+68h+arg_30]
0x18000a773  mov     rcx, rsi; HKEY
0x18000a776  mov     [rsp+68h+var_38], rax; unsigned int *
0x18000a77b  mov     rax, [rsp+68h+arg_28]
0x18000a783  mov     [rsp+68h+var_40], rax; unsigned __int8 *
0x18000a788  mov     rax, [rsp+68h+arg_20]
0x18000a790  mov     [rsp+68h+var_48], rax; unsigned int *
0x18000a795  call    PerfEnumTextValue
0x18000a79a  jmp     short loc_18000A7A1
0x18000a79c  mov     eax, 57h ; 'W'
0x18000a7a1  mov     rbx, [rsp+68h+arg_0]
0x18000a7a6  mov     rsi, [rsp+68h+arg_8]
0x18000a7ab  add     rsp, 60h
0x18000a7af  pop     rdi
0x18000a7b0  retn
```
