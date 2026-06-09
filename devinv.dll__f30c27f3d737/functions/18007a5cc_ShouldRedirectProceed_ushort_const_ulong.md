# ShouldRedirectProceed(ushort const *,ulong)

- ea: `0x18007a5cc`
- end: `0x18007a713`
- name: `?ShouldRedirectProceed@@YAJPEBGK@Z`
- size: `327`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180079de0`

## callees

- `0x180005e40`
- `0x180006ec4`
- `0x18000dcec`
- `0x180066c10`
- `0x18007a5cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007a69d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18007a69d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007a6dc`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18007a6dc`

## string_xrefs

- `0x18007a682`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x18007a6d5`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`

## pseudocode

```c
__int64 __fastcall ShouldRedirectProceed(const unsigned __int16 *a1, int a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  LSTATUS v5; // eax
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+44h] [rbp-BCh] BYREF
  int Data; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Value[264]; // [rsp+50h] [rbp-B0h] BYREF

  Data = a2;
  memset_0(Value, 0, 0x208u);
  pvData = 0;
  pcbData = 0;
  v3 = StringCchPrintfW(Value, 0x104u, L"GetInv_%ls", a1);
  v4 = v3;
  if ( v3 >= 0 )
  {
    pcbData = 4;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
           Value,
           0x18u,
           0,
           &pvData,
           &pcbData)
      || Data != pvData )
    {
      v5 = RegSetKeyValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
             Value,
             4u,
             &Data,
             4u);
      v4 = v5;
      if ( v5 > 0 )
        return (unsigned __int16)v5 | 0x80070000;
    }
    else
    {
      return 1;
    }
  }
  else
  {
    AslLogCallPrintf(1, "ShouldRedirectProceed", 63, "StringCchPrintfW failed %#x", v3);
  }
  return v4;
}

```

## disassembly

```asm
0x18007a5cc  mov     [rsp-8+arg_10], rbx
0x18007a5d1  push    rbp
0x18007a5d2  lea     rbp, [rsp-170h]
0x18007a5da  sub     rsp, 270h
0x18007a5e1  mov     rax, cs:__security_cookie
0x18007a5e8  xor     rax, rsp
0x18007a5eb  mov     [rbp+170h+var_10], rax
0x18007a5f2  mov     rbx, rcx
0x18007a5f5  mov     [rsp+270h+Data], edx
0x18007a5f9  xor     edx, edx; Val
0x18007a5fb  lea     rcx, [rsp+270h+Value]; void *
0x18007a600  mov     r8d, 208h; Size
0x18007a606  call    memset_0
0x18007a60b  mov     r9, rbx
0x18007a60e  mov     [rsp+270h+var_22C], 0
0x18007a616  lea     r8, aGetinvLs; "GetInv_%ls"
0x18007a61d  mov     [rsp+270h+var_230], 0
0x18007a625  mov     edx, 104h; unsigned __int64
0x18007a62a  lea     rcx, [rsp+270h+Value]; unsigned __int16 *
0x18007a62f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007a634  mov     ebx, eax
0x18007a636  test    eax, eax
0x18007a638  jns     short loc_18007A660
0x18007a63a  mov     r8d, 3Fh ; '?'
0x18007a640  mov     dword ptr [rsp+270h+pdwType], eax
0x18007a644  lea     r9, aStringcchprint_0; "StringCchPrintfW failed %#x"
0x18007a64b  lea     rdx, aShouldredirect; "ShouldRedirectProceed"
0x18007a652  lea     ecx, [r8-3Eh]
0x18007a656  call    AslLogCallPrintf
0x18007a65b  jmp     loc_18007A6F1
0x18007a660  mov     ebx, 4
0x18007a665  lea     rax, [rsp+270h+var_230]
0x18007a66a  mov     [rsp+270h+pcbData], rax; pcbData
0x18007a66f  lea     r8, [rsp+270h+Value]; lpValue
0x18007a674  lea     rax, [rsp+270h+var_22C]
0x18007a679  mov     [rsp+270h+var_230], ebx
0x18007a67d  mov     [rsp+270h+pvData], rax; pvData
0x18007a682  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18007a689  lea     r9d, [rbx+14h]; dwFlags
0x18007a68d  mov     [rsp+270h+pdwType], 0; pdwType
0x18007a696  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18007a69d  call    cs:__imp_RegGetValueW
0x18007a6a3  test    eax, eax
0x18007a6a5  jnz     short loc_18007A6B8
0x18007a6a7  mov     eax, [rsp+270h+var_22C]
0x18007a6ab  cmp     [rsp+270h+Data], eax
0x18007a6af  jnz     short loc_18007A6B8
0x18007a6b1  mov     ebx, 1
0x18007a6b6  jmp     short loc_18007A6F1
0x18007a6b8  lea     rax, [rsp+270h+Data]
0x18007a6bd  mov     dword ptr [rsp+270h+pvData], ebx; cbData
0x18007a6c1  mov     r9d, ebx; dwType
0x18007a6c4  mov     [rsp+270h+pdwType], rax; lpData
0x18007a6c9  lea     r8, [rsp+270h+Value]; lpValueName
0x18007a6ce  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007a6d5  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18007a6dc  call    cs:__imp_RegSetKeyValueW
0x18007a6e2  mov     ebx, eax
0x18007a6e4  test    eax, eax
0x18007a6e6  jle     short loc_18007A6F1
0x18007a6e8  movzx   ebx, ax
0x18007a6eb  or      ebx, 80070000h
0x18007a6f1  mov     eax, ebx
0x18007a6f3  mov     rcx, [rbp+170h+var_10]
0x18007a6fa  xor     rcx, rsp; StackCookie
0x18007a6fd  call    __security_check_cookie
0x18007a702  mov     rbx, [rsp+270h+arg_10]
0x18007a70a  add     rsp, 270h
0x18007a711  pop     rbp
0x18007a712  retn
```
