# _OpenMuiStringCache

- ea: `0x1800747f0`
- end: `0x180074abf`
- name: `_OpenMuiStringCache`
- size: `719`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020f20`

## callees

- `0x18002a790`
- `0x18002b38c`
- `0x1800747f0`
- `0x180074ac8`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800749ac`
- `ntdll!RtlInitUnicodeString` at `0x1800749ac`
- `ntdll!NtOpenKey` at `0x1800749f6`
- `ntdll!NtOpenKey` at `0x1800749f6`
- `ntdll!RtlNtStatusToDosError` at `0x180074aa7`
- `ntdll!RtlNtStatusToDosError` at `0x180074aa7`
- `ntdll!NtCreateKey` at `0x180074a2c`
- `ntdll!NtCreateKey` at `0x180074a2c`
- `ntdll!RtlOpenCurrentUser` at `0x1800748c3`
- `ntdll!RtlOpenCurrentUser` at `0x1800748c3`
- `ntdll!NtClose` at `0x180074966`
- `ntdll!NtClose` at `0x180074a44`
- `ntdll!NtClose` at `0x180074966`
- `ntdll!NtClose` at `0x180074a44`

## pseudocode

```c
__int64 __fastcall OpenMuiStringCache(PHANDLE KeyHandle, WCHAR *a2, __int64 a3, __int64 a4)
{
  ULONG refreshed; // r14d
  int v9; // ebx
  __int64 v10; // rcx
  WCHAR *v11; // rax
  __int64 v12; // r8
  WCHAR *v13; // rdx
  WCHAR *v14; // r9
  __int64 v15; // rcx
  WCHAR *v16; // rcx
  bool v17; // zf
  ULONG Disposition; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE KeyHandlea; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SourceString[512]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR v24[552]; // [rsp+490h] [rbp+390h] BYREF

  memset_0(v24, 0, sizeof(v24));
  if ( KeyHandle && a2 && a3 )
  {
    refreshed = 0;
    v9 = RtlStringCchPrintfW(v24, 552, L"%s\\%s\\%s", a2, a3, a4);
    if ( v9 >= 0 )
    {
      KeyHandlea = 0;
      Disposition = 0;
      memset(&ObjectAttributes, 0, 44);
      DestinationString = 0;
      if ( RtlOpenCurrentUser(0x2000000u, &KeyHandlea) >= 0 )
      {
        SourceString[0] = 0;
        v10 = 512;
        v11 = SourceString;
        do
        {
          if ( !*v11 )
            break;
          ++v11;
          --v10;
        }
        while ( v10 );
        if ( !v10 )
          goto LABEL_17;
        v12 = v10;
        v13 = v24;
        v14 = &SourceString[512 - v10];
        v15 = 2147483646;
        do
        {
          if ( !v15 )
            break;
          if ( !*v13 )
            break;
          *v14++ = *v13++;
          --v15;
          --v12;
        }
        while ( v12 );
        v16 = v14 - 1;
        if ( v12 )
          v16 = v14;
        *v16 = 0;
        if ( v12 )
        {
          RtlInitUnicodeString(&DestinationString, SourceString);
          ObjectAttributes.RootDirectory = KeyHandlea;
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          Disposition = 0;
          v9 = NtOpenKey(KeyHandle, 0x2001Fu, &ObjectAttributes);
          if ( v9 < 0 )
            v9 = NtCreateKey(KeyHandle, 0x2001Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
          if ( KeyHandlea )
            NtClose(KeyHandlea);
          v17 = v9 == 0;
          if ( v9 >= 0 )
            goto LABEL_29;
          *KeyHandle = 0;
        }
        else
        {
LABEL_17:
          if ( KeyHandlea )
            NtClose(KeyHandlea);
        }
      }
      refreshed = RefreshCacheForUser(a3, a2);
      if ( refreshed )
        return refreshed;
      v9 = OpenRegKeyForUser(KeyHandle, (WCHAR *)&word_18029DECC, v24, 0x2001Fu, 2);
    }
    v17 = v9 == 0;
LABEL_29:
    if ( !v17 )
      return RtlNtStatusToDosError(v9);
    return refreshed;
  }
  return 87;
}

```

## disassembly

```asm
0x1800747f0  push    rbp
0x1800747f2  push    rbx
0x1800747f3  push    rsi
0x1800747f4  push    rdi
0x1800747f5  push    r15
0x1800747f7  lea     rbp, [rsp-800h]
0x1800747ff  sub     rsp, 900h
0x180074806  mov     rax, cs:__security_cookie
0x18007480d  xor     rax, rsp
0x180074810  mov     [rbp+820h+var_40], rax
0x180074817  mov     rsi, r8
0x18007481a  mov     rdi, rdx
0x18007481d  mov     r15, rcx
0x180074820  xor     edx, edx; Val
0x180074822  mov     r8d, 450h; Size
0x180074828  lea     rcx, [rbp+820h+var_490]; void *
0x18007482f  mov     rbx, r9
0x180074832  call    memset_0
0x180074837  test    r15, r15
0x18007483a  jz      loc_180074AB8
0x180074840  test    rdi, rdi
0x180074843  jz      loc_180074AB8
0x180074849  test    rsi, rsi
0x18007484c  jz      loc_180074AB8
0x180074852  mov     [rsp+920h+var_28], r12
0x18007485a  lea     r8, aSSS; "%s\\%s\\%s"
0x180074861  xor     r12d, r12d
0x180074864  mov     [rsp+920h+var_30], r14
0x18007486c  mov     qword ptr [rsp+920h+CreateOptions], rbx
0x180074871  lea     rcx, [rbp+820h+var_490]
0x180074878  mov     r9, rdi
0x18007487b  mov     [rsp+920h+Class], rsi
0x180074880  mov     edx, 228h
0x180074885  mov     r14d, r12d
0x180074888  call    RtlStringCchPrintfW
0x18007488d  mov     ebx, eax
0x18007488f  test    eax, eax
0x180074891  js      loc_18007499D
0x180074897  xorps   xmm0, xmm0
0x18007489a  mov     [rsp+920h+KeyHandle], r12
0x18007489f  movups  xmmword ptr [rsp+920h+ObjectAttributes.ObjectName], xmm0
0x1800748a4  xor     eax, eax
0x1800748a6  mov     [rsp+920h+var_8E0], r12d
0x1800748ab  lea     rdx, [rsp+920h+KeyHandle]; KeyHandle
0x1800748b0  mov     ecx, 2000000h; DesiredAccess
0x1800748b5  movups  xmmword ptr [rsp+920h+ObjectAttributes+1Ch], xmm0
0x1800748ba  movups  xmmword ptr [rsp+920h+ObjectAttributes.Length], xmm0
0x1800748bf  movups  xmmword ptr [rbp+820h+DestinationString.Length], xmm0
0x1800748c3  call    cs:__imp_RtlOpenCurrentUser
0x1800748ca  nop     dword ptr [rax+rax+00h]
0x1800748cf  mov     ebx, eax
0x1800748d1  test    eax, eax
0x1800748d3  js      loc_180074A6E
0x1800748d9  mov     r8d, 200h
0x1800748df  mov     [rbp+820h+SourceString], r12w
0x1800748e4  mov     ecx, r8d
0x1800748e7  lea     rax, [rbp+820h+SourceString]
0x1800748eb  nop     dword ptr [rax+rax+00h]
0x1800748f0  cmp     [rax], r12w
0x1800748f4  jz      short loc_180074900
0x1800748f6  add     rax, 2
0x1800748fa  sub     rcx, 1
0x1800748fe  jnz     short loc_1800748F0
0x180074900  mov     r9, r8
0x180074903  sub     r9, rcx
0x180074906  test    rcx, rcx
0x180074909  cmovz   r9, r12
0x18007490d  jz      short loc_180074958
0x18007490f  sub     r8, r9
0x180074912  lea     rdx, [rbp+820h+var_490]
0x180074919  lea     r9, [rbp+r9*2+820h+SourceString]
0x18007491e  mov     ecx, 7FFFFFFEh
0x180074923  jz      short loc_180074947
0x180074925  test    rcx, rcx
0x180074928  jz      short loc_180074947
0x18007492a  movzx   eax, word ptr [rdx]
0x18007492d  test    ax, ax
0x180074930  jz      short loc_180074947
0x180074932  mov     [r9], ax
0x180074936  add     rdx, 2
0x18007493a  add     r9, 2
0x18007493e  dec     rcx
0x180074941  sub     r8, 1
0x180074945  jnz     short loc_180074925
0x180074947  test    r8, r8
0x18007494a  lea     rcx, [r9-2]
0x18007494e  cmovnz  rcx, r9
0x180074952  mov     [rcx], r12w
0x180074956  jnz     short loc_1800749A4
0x180074958  mov     rcx, [rsp+920h+KeyHandle]; Handle
0x18007495d  test    rcx, rcx
0x180074960  jz      loc_180074A57
0x180074966  call    cs:__imp_NtClose
0x18007496d  nop     dword ptr [rax+rax+00h]
0x180074972  jmp     loc_180074A57
0x180074977  mov     r9d, 2001Fh
0x18007497d  mov     dword ptr [rsp+920h+Class], 2; char
0x180074985  lea     r8, [rbp+820h+var_490]
0x18007498c  mov     rcx, r15; KeyHandle
0x18007498f  lea     rdx, word_18029DECC
0x180074996  call    OpenRegKeyForUser
0x18007499b  mov     ebx, eax
0x18007499d  test    ebx, ebx
0x18007499f  jmp     loc_180074A72
0x1800749a4  lea     rdx, [rbp+820h+SourceString]; SourceString
0x1800749a8  lea     rcx, [rbp+820h+DestinationString]; DestinationString
0x1800749ac  call    cs:__imp_RtlInitUnicodeString
0x1800749b3  nop     dword ptr [rax+rax+00h]
0x1800749b8  mov     rax, [rsp+920h+KeyHandle]
0x1800749bd  lea     r8, [rsp+920h+ObjectAttributes]; ObjectAttributes
0x1800749c2  mov     [rsp+920h+ObjectAttributes.RootDirectory], rax
0x1800749c7  xorps   xmm0, xmm0
0x1800749ca  lea     rax, [rbp+820h+DestinationString]
0x1800749ce  mov     [rsp+920h+ObjectAttributes.Length], 30h ; '0'
0x1800749d6  mov     edx, 2001Fh; DesiredAccess
0x1800749db  mov     [rsp+920h+ObjectAttributes.ObjectName], rax
0x1800749e0  mov     rcx, r15; KeyHandle
0x1800749e3  mov     [rsp+920h+ObjectAttributes.Attributes], 40h ; '@'
0x1800749eb  movdqu  xmmword ptr [rsp+920h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800749f1  mov     [rsp+920h+var_8E0], r12d
0x1800749f6  call    cs:__imp_NtOpenKey
0x1800749fd  nop     dword ptr [rax+rax+00h]
0x180074a02  mov     ebx, eax
0x180074a04  test    eax, eax
0x180074a06  jns     short loc_180074A3A
0x180074a08  lea     rax, [rsp+920h+var_8E0]
0x180074a0d  xor     r9d, r9d; TitleIndex
0x180074a10  mov     [rsp+920h+Disposition], rax; Disposition
0x180074a15  lea     r8, [rsp+920h+ObjectAttributes]; ObjectAttributes
0x180074a1a  mov     [rsp+920h+CreateOptions], r12d; CreateOptions
0x180074a1f  mov     edx, 2001Fh; DesiredAccess
0x180074a24  mov     rcx, r15; KeyHandle
0x180074a27  mov     [rsp+920h+Class], r12; Class
0x180074a2c  call    cs:__imp_NtCreateKey
0x180074a33  nop     dword ptr [rax+rax+00h]
0x180074a38  mov     ebx, eax
0x180074a3a  mov     rcx, [rsp+920h+KeyHandle]; Handle
0x180074a3f  test    rcx, rcx
0x180074a42  jz      short loc_180074A50
0x180074a44  call    cs:__imp_NtClose
0x180074a4b  nop     dword ptr [rax+rax+00h]
0x180074a50  test    ebx, ebx
0x180074a52  jns     short loc_180074A72
0x180074a54  mov     [r15], r12
0x180074a57  mov     rdx, rdi
0x180074a5a  mov     rcx, rsi
0x180074a5d  call    _RefreshCacheForUser
0x180074a62  mov     r14d, eax
0x180074a65  test    eax, eax
0x180074a67  jnz     short loc_180074A74
0x180074a69  jmp     loc_180074977
0x180074a6e  test    ebx, ebx
0x180074a70  js      short loc_180074A57
0x180074a72  jnz     short loc_180074AA5
0x180074a74  mov     r12, [rsp+920h+var_28]
0x180074a7c  mov     eax, r14d
0x180074a7f  mov     r14, [rsp+920h+var_30]
0x180074a87  mov     rcx, [rbp+820h+var_40]
0x180074a8e  xor     rcx, rsp; StackCookie
0x180074a91  call    __security_check_cookie
0x180074a96  add     rsp, 900h
0x180074a9d  pop     r15
0x180074a9f  pop     rdi
0x180074aa0  pop     rsi
0x180074aa1  pop     rbx
0x180074aa2  pop     rbp
0x180074aa3  retn
0x180074aa5  mov     ecx, ebx; Status
0x180074aa7  call    cs:__imp_RtlNtStatusToDosError
0x180074aae  nop     dword ptr [rax+rax+00h]
0x180074ab3  mov     r14d, eax
0x180074ab6  jmp     short loc_180074A74
0x180074ab8  mov     eax, 57h ; 'W'
0x180074abd  jmp     short loc_180074A87
```
