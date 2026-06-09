# wil::is_default_system_managed_account(ushort const *)

- ea: `0x14001d09c`
- end: `0x14001d1bb`
- name: `?is_default_system_managed_account@wil@@YA_NPEBG@Z`
- size: `287`
- prototype: `bool __fastcall(wil *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001c748`

## callees

- `0x140002de3`
- `0x14001d09c`
- `0x140025d70`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x14001d157`
- `ADVAPI32!RegGetValueW` at `0x14001d157`
- `KERNEL32!CompareStringOrdinal` at `0x14001d189`
- `KERNEL32!CompareStringOrdinal` at `0x14001d189`
- `msvcrt!wcschr` at `0x14001d115`
- `msvcrt!wcschr` at `0x14001d115`
- `Secur32!GetUserNameExW` at `0x14001d100`
- `Secur32!GetUserNameExW` at `0x14001d100`

## pseudocode

```c
char __fastcall wil::is_default_system_managed_account(wil *this, const unsigned __int16 *a2)
{
  const WCHAR *v2; // rbx
  LSTATUS ValueW; // eax
  bool v4; // sf
  char v5; // di
  ULONG nSize; // [rsp+40h] [rbp-468h] BYREF
  DWORD pcbData[3]; // [rsp+44h] [rbp-464h] BYREF
  WCHAR String2[264]; // [rsp+50h] [rbp-458h] BYREF
  WCHAR NameBuffer[280]; // [rsp+260h] [rbp-248h] BYREF

  v2 = 0;
  memset_0(String2, 0, 0x202u);
  pcbData[0] = 514;
  memset_0(NameBuffer, 0, 0x222u);
  nSize = 273;
  if ( GetUserNameExW(NameSamCompatible, NameBuffer, &nSize) )
    v2 = wcschr(NameBuffer, 0x5Cu) + 1;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
             L"DefaultAccountSAMName",
             2u,
             0,
             String2,
             pcbData);
  v4 = ValueW < 0;
  if ( ValueW > 0 )
    v4 = 1;
  if ( v4 )
    return 0;
  if ( !v2 )
    return 0;
  v5 = 1;
  if ( CompareStringOrdinal(v2, -1, String2, -1, 1) != 2 )
    return 0;
  return v5;
}

```

## disassembly

```asm
0x14001d09c  mov     [rsp+arg_0], rbx
0x14001d0a1  push    rdi
0x14001d0a2  sub     rsp, 4A0h
0x14001d0a9  mov     rax, cs:__security_cookie
0x14001d0b0  xor     rax, rsp
0x14001d0b3  mov     [rsp+4A8h+var_18], rax
0x14001d0bb  mov     edi, 202h
0x14001d0c0  lea     rcx, [rsp+4A8h+String2]; void *
0x14001d0c5  mov     r8d, edi; Size
0x14001d0c8  xor     edx, edx; Val
0x14001d0ca  xor     ebx, ebx
0x14001d0cc  call    memset_0
0x14001d0d1  xor     edx, edx; Val
0x14001d0d3  mov     [rsp+4A8h+var_464], edi
0x14001d0d7  lea     r8d, [rdi+20h]; Size
0x14001d0db  lea     rcx, [rsp+4A8h+NameBuffer]; void *
0x14001d0e3  call    memset_0
0x14001d0e8  lea     r8, [rsp+4A8h+nSize]; nSize
0x14001d0ed  mov     [rsp+4A8h+nSize], 111h
0x14001d0f5  lea     rdx, [rsp+4A8h+NameBuffer]; lpNameBuffer
0x14001d0fd  lea     ecx, [rbx+2]; NameFormat
0x14001d100  call    cs:__imp_GetUserNameExW
0x14001d106  test    al, al
0x14001d108  jz      short loc_14001D11F
0x14001d10a  lea     edx, [rbx+5Ch]; Ch
0x14001d10d  lea     rcx, [rsp+4A8h+NameBuffer]; Str
0x14001d115  call    cs:__imp_wcschr
0x14001d11b  lea     rbx, [rax+2]
0x14001d11f  lea     rax, [rsp+4A8h+var_464]
0x14001d124  mov     r9d, 2; dwFlags
0x14001d12a  mov     [rsp+4A8h+pcbData], rax; pcbData
0x14001d12f  lea     r8, aDefaultaccount; "DefaultAccountSAMName"
0x14001d136  lea     rax, [rsp+4A8h+String2]
0x14001d13b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x14001d142  mov     [rsp+4A8h+pvData], rax; pvData
0x14001d147  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14001d14e  mov     [rsp+4A8h+pdwType], 0; pdwType
0x14001d157  call    cs:__imp_RegGetValueW
0x14001d15d  test    eax, eax
0x14001d15f  jle     short loc_14001D16B
0x14001d161  movzx   eax, ax
0x14001d164  or      eax, 80070000h
0x14001d169  test    eax, eax
0x14001d16b  js      short loc_14001D194
0x14001d16d  test    rbx, rbx
0x14001d170  jz      short loc_14001D194
0x14001d172  or      edx, 0FFFFFFFFh; cchCount1
0x14001d175  lea     r8, [rsp+4A8h+String2]; lpString2
0x14001d17a  mov     edi, 1
0x14001d17f  mov     r9d, edx; cchCount2
0x14001d182  mov     rcx, rbx; lpString1
0x14001d185  mov     dword ptr [rsp+4A8h+pdwType], edi; bIgnoreCase
0x14001d189  call    cs:__imp_CompareStringOrdinal
0x14001d18f  cmp     eax, 2
0x14001d192  jz      short loc_14001D197
0x14001d194  xor     dil, dil
0x14001d197  mov     al, dil
0x14001d19a  mov     rcx, [rsp+4A8h+var_18]
0x14001d1a2  xor     rcx, rsp; StackCookie
0x14001d1a5  call    __security_check_cookie
0x14001d1aa  mov     rbx, [rsp+4A8h+arg_0]
0x14001d1b2  add     rsp, 4A0h
0x14001d1b9  pop     rdi
0x14001d1ba  retn
```
