# PsmpDereferenceHostContext

- ea: `0x18000a750`
- end: `0x18000a8c5`
- name: `PsmpDereferenceHostContext`
- size: `373`
- prototype: `unsigned __int8 __fastcall(__int64 *, unsigned int)`
- caller_count: `37`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800049a0`
- `0x180004ff0`
- `0x180005c74`
- `0x180006f5c`
- `0x180007214`
- `0x18000772c`
- `0x1800078e0`
- `0x180007d40`
- `0x180007fd0`
- `0x180008360`
- `0x180008840`
- `0x180008f10`
- `0x180009630`
- `0x180009b40`
- `0x18000aab0`
- `0x18000abf0`
- `0x18000bc20`
- `0x18000c61c`
- `0x18000c7b0`
- `0x18000cb34`
- `0x18000f7dc`
- `0x1800103ac`
- `0x180013b40`
- `0x180014710`
- `0x180014800`
- `0x1800149b0`
- `0x180014bb4`
- `0x1800188f8`
- `0x180019100`
- `0x18001a444`
- `0x18001adc8`
- `0x18001d6dc`
- `0x18001dc40`
- `0x18001deb0`
- `0x18002a7d0`
- `0x18002c640`
- `0x18002c7f0`

## callees

- `0x1800017b0`
- `0x18000a750`
- `0x18000d07c`
- `0x180013610`
- `0x1800137a4`
- `0x1800192fc`
- `0x18001b7e0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a863`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000a863`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a889`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000a889`

## pseudocode

```c
unsigned __int8 __fastcall PsmpDereferenceHostContext(__int64 *a1, unsigned int a2)
{
  __int64 v2; // rsi
  unsigned __int8 result; // al
  int v6; // edi
  char *v7; // rdx
  __int64 v8; // r8
  __int64 **v9; // rdx
  int v10; // [rsp+30h] [rbp-59h] BYREF
  int v11; // [rsp+34h] [rbp-55h] BYREF
  int v12; // [rsp+38h] [rbp-51h] BYREF
  __int64 v13; // [rsp+40h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+50h] [rbp-39h] BYREF
  int *v15; // [rsp+70h] [rbp-19h]
  __int64 v16; // [rsp+78h] [rbp-11h]
  _BYTE v17[16]; // [rsp+80h] [rbp-9h] BYREF
  int *v18; // [rsp+90h] [rbp+7h]
  __int64 v19; // [rsp+98h] [rbp+Fh]
  int *v20; // [rsp+A0h] [rbp+17h]
  __int64 v21; // [rsp+A8h] [rbp+1Fh]
  __int64 *v22; // [rsp+B0h] [rbp+27h]
  __int64 v23; // [rsp+B8h] [rbp+2Fh]

  v2 = *a1;
  v10 = 0;
  result = PsmpDereferenceObjectEx(a1 + 9, &v10);
  v6 = result;
  if ( (unsigned int)dword_18003F048 > 5 )
  {
    result = tlgKeywordOn((__int64)&dword_18003F048, 1);
    if ( result )
    {
      v7 = (char *)(*a1 + 7040);
      v16 = 4;
      v15 = &v10;
      tlgCreate1Sz_wchar_t((__int64)v17, v7);
      v11 = v6;
      v18 = &v11;
      v12 = *((_DWORD *)a1 + 4);
      v19 = 4;
      v20 = &v12;
      v13 = a1[5];
      v22 = &v13;
      v21 = 4;
      v23 = 8;
      result = tlgWriteTransfer_EventWriteTransfer(
                 (__int64)&dword_18003F048,
                 (unsigned __int8 *)&word_180037E06,
                 0,
                 0,
                 7u,
                 &v14);
    }
  }
  if ( (_BYTE)v6 )
  {
    RtlAcquireSRWLockExclusive(v2 + 328);
    v8 = a1[7];
    if ( *(__int64 **)(v8 + 8) != a1 + 7 || (v9 = (__int64 **)a1[8], *v9 != a1 + 7) )
      __fastfail(3u);
    *v9 = (__int64 *)v8;
    *(_QWORD *)(v8 + 8) = v9;
    RtlReleaseSRWLockExclusive(v2 + 328);
    return PsmpRundownHostContext(a1, a2);
  }
  return result;
}

```

## disassembly

```asm
0x18000a750  mov     [rsp-8+arg_8], rbx
0x18000a755  mov     [rsp-8+arg_10], rsi
0x18000a75a  push    rbp
0x18000a75b  push    rdi
0x18000a75c  push    r14
0x18000a75e  lea     rbp, [rsp-47h]
0x18000a763  sub     rsp, 0D0h
0x18000a76a  mov     rax, cs:__security_cookie
0x18000a771  xor     rax, rsp
0x18000a774  mov     [rbp+57h+var_20], rax
0x18000a778  mov     rsi, [rcx]
0x18000a77b  mov     r14d, edx
0x18000a77e  mov     rbx, rcx
0x18000a781  mov     [rbp+57h+var_B0], 0
0x18000a788  add     rcx, 48h ; 'H'
0x18000a78c  lea     rdx, [rbp+57h+var_B0]
0x18000a790  call    PsmpDereferenceObjectEx
0x18000a795  mov     ecx, cs:dword_18003F048
0x18000a79b  movzx   edi, al
0x18000a79e  cmp     ecx, 5
0x18000a7a1  jbe     loc_18000A854
0x18000a7a7  mov     edx, 1
0x18000a7ac  lea     rcx, dword_18003F048
0x18000a7b3  call    _tlgKeywordOn
0x18000a7b8  test    al, al
0x18000a7ba  jz      loc_18000A854
0x18000a7c0  mov     eax, [rbp+57h+var_B0]
0x18000a7c3  lea     rcx, [rbp+57h+var_60]
0x18000a7c7  mov     rdx, [rbx]
0x18000a7ca  mov     [rbp+57h+var_B0], eax
0x18000a7cd  add     rdx, 1B80h
0x18000a7d4  lea     rax, [rbp+57h+var_B0]
0x18000a7d8  mov     [rbp+57h+var_68], 4
0x18000a7e0  mov     [rbp+57h+var_70], rax
0x18000a7e4  call    _tlgCreate1Sz_wchar_t
0x18000a7e9  lea     rax, [rbp+57h+var_AC]
0x18000a7ed  mov     [rbp+57h+var_AC], edi
0x18000a7f0  mov     [rbp+57h+var_50], rax
0x18000a7f4  lea     rdx, word_180037E06
0x18000a7fb  mov     eax, [rbx+10h]
0x18000a7fe  lea     rcx, dword_18003F048
0x18000a805  mov     [rbp+57h+var_A8], eax
0x18000a808  xor     r9d, r9d
0x18000a80b  lea     rax, [rbp+57h+var_A8]
0x18000a80f  mov     [rbp+57h+var_48], 4
0x18000a817  mov     [rbp+57h+var_40], rax
0x18000a81b  xor     r8d, r8d
0x18000a81e  mov     rax, [rbx+28h]
0x18000a822  mov     [rbp+57h+var_A0], rax
0x18000a826  lea     rax, [rbp+57h+var_A0]
0x18000a82a  mov     [rbp+57h+var_30], rax
0x18000a82e  lea     rax, [rbp+57h+var_90]
0x18000a832  mov     [rsp+0E0h+var_B8], rax
0x18000a837  mov     [rsp+0E0h+var_C0], 7
0x18000a83f  mov     [rbp+57h+var_38], 4
0x18000a847  mov     [rbp+57h+var_28], 8
0x18000a84f  call    _tlgWriteTransfer_EventWriteTransfer
0x18000a854  test    dil, dil
0x18000a857  jz      short loc_18000A89A
0x18000a859  lea     rdi, [rsi+148h]
0x18000a860  mov     rcx, rdi
0x18000a863  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000a869  lea     rax, [rbx+38h]
0x18000a86d  mov     r8, [rax]
0x18000a870  cmp     [r8+8], rax
0x18000a874  jnz     short loc_18000A8BE
0x18000a876  mov     rdx, [rax+8]
0x18000a87a  cmp     [rdx], rax
0x18000a87d  jnz     short loc_18000A8BE
0x18000a87f  mov     [rdx], r8
0x18000a882  mov     rcx, rdi
0x18000a885  mov     [r8+8], rdx
0x18000a889  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000a88f  mov     edx, r14d
0x18000a892  mov     rcx, rbx
0x18000a895  call    PsmpRundownHostContext
0x18000a89a  mov     rcx, [rbp+57h+var_20]
0x18000a89e  xor     rcx, rsp; StackCookie
0x18000a8a1  call    __security_check_cookie
0x18000a8a6  lea     r11, [rsp+0E0h+var_10]
0x18000a8ae  mov     rbx, [r11+28h]
0x18000a8b2  mov     rsi, [r11+30h]
0x18000a8b6  mov     rsp, r11
0x18000a8b9  pop     r14
0x18000a8bb  pop     rdi
0x18000a8bc  pop     rbp
0x18000a8bd  retn
0x18000a8be  mov     ecx, 3
0x18000a8c3  int     29h; Win8: RtlFailFast(ecx)
```
