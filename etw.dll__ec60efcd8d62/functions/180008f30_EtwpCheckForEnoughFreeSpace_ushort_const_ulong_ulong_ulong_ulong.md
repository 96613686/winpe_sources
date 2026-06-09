# EtwpCheckForEnoughFreeSpace(ushort const *,ulong,ulong,ulong,ulong)

- ea: `0x180008f30`
- end: `0x180009221`
- name: `?EtwpCheckForEnoughFreeSpace@@YAKPEBGKKKK@Z`
- size: `753`
- prototype: `unsigned int __usercall@<eax>(const unsigned __int16 *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000c4a0`
- `0x18000cca0`

## callees

- `0x180001560`
- `0x180001e8e`
- `0x180001eb2`
- `0x180002020`
- `0x18000202c`
- `0x180006180`
- `0x180008f30`

## import_xrefs

- `ntdll!NtOpenKey` at `0x180008fd7`
- `ntdll!NtOpenKey` at `0x180008fd7`
- `ntdll!RtlInitUnicodeString` at `0x180008f94`
- `ntdll!RtlInitUnicodeString` at `0x180008f94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009050`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009050`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009085`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000907b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000907b`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18000918e`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x18000918e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180009018`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x180009018`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fe6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008fe6`

## string_xrefs

- `0x180008f6e`: `\Registry\Machine\System\CurrentControlSet\Control\MiniNT`

## pseudocode

```c
int __fastcall EtwpCheckForEnoughFreeSpace(
        const unsigned __int16 *a1,
        unsigned int a2,
        unsigned int a3,
        int a4,
        unsigned int a5)
{
  int result; // eax
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rdx
  UINT SystemDirectoryW; // eax
  unsigned __int64 v13; // rax
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rsi
  __int64 v16; // r11
  ULONGLONG v17; // rbx
  ULONGLONG v18; // r14
  void *KeyHandle; // [rsp+20h] [rbp-E0h] BYREF
  _ULARGE_INTEGER FreeBytesAvailableToCaller; // [rsp+28h] [rbp-D8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-D0h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\MiniNT");
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    CloseHandle(KeyHandle);
    return 0;
  }
  if ( a3 && a4 )
  {
    memset(&ObjectAttributes, 0, 36);
    if ( GetFileAttributesExW(a1, GetFileExInfoStandard, &ObjectAttributes) )
    {
      v10 = LODWORD(ObjectAttributes.SecurityDescriptor) + ((unsigned __int64)*(&ObjectAttributes.Attributes + 1) << 32);
      if ( a5 )
        v11 = v10 >> 10;
      else
        v11 = v10 >> 20;
      if ( (unsigned int)v11 >= a3 )
        return 112;
      a3 -= v11;
    }
    else
    {
      result = GetLastError();
      if ( result != 2 )
        return result;
    }
  }
  memset_0(Buffer, 0, 0x208u);
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( !SystemDirectoryW )
    return GetLastError();
  if ( SystemDirectoryW < 2 || a2 < 2 )
    return 87;
  if ( a1[1] == 58 && Buffer[1] == 58 && !wcsnicmp(a1, Buffer, 1u) )
  {
    if ( a5 )
    {
      if ( a3 <= 0xFFFCDFFF )
      {
        a3 += 204800;
        goto LABEL_25;
      }
    }
    else if ( a3 <= 0xFFFFFF37 )
    {
      a3 += 200;
      goto LABEL_25;
    }
    return 112;
  }
LABEL_25:
  if ( !a3 )
    return 0;
  FreeBytesAvailableToCaller.QuadPart = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  v13 = 2LL * (a2 + 1);
  if ( !is_mul_ok(a2 + 1, 2u) )
    v13 = -1;
  v14 = (unsigned __int16 *)operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v14;
  if ( !v14 )
    return 8;
  StringCchCopyW(v14, a2 + 1, a1);
  v16 = a2 - 1;
  if ( (int)v16 < 0 )
  {
LABEL_34:
    operator delete(v15);
    v15 = 0;
  }
  else
  {
    while ( v15[v16] != 92 && v15[v16] != 47 )
    {
      v16 = (unsigned int)(v16 - 1);
      if ( (int)v16 < 0 )
        goto LABEL_34;
    }
    v15[v16] = 0;
  }
  if ( !GetDiskFreeSpaceExW(v15, &FreeBytesAvailableToCaller, (PULARGE_INTEGER)&DestinationString, 0) )
  {
    if ( v15 )
      operator delete(v15);
    return GetLastError();
  }
  v17 = FreeBytesAvailableToCaller.QuadPart >> 10;
  v18 = FreeBytesAvailableToCaller.QuadPart >> 20;
  if ( v15 )
    operator delete(v15);
  if ( !a5 )
  {
    if ( (unsigned int)v18 >= a3 )
      return 0;
    return 112;
  }
  return (unsigned int)v17 < a3 ? 0x70 : 0;
}

```

## disassembly

```asm
0x180008f30  mov     [rsp-8+arg_10], rbx
0x180008f35  push    rbp
0x180008f36  push    rsi
0x180008f37  push    rdi
0x180008f38  push    r13
0x180008f3a  push    r14
0x180008f3c  lea     rbp, [rsp-190h]
0x180008f44  sub     rsp, 290h
0x180008f4b  mov     rax, cs:__security_cookie
0x180008f52  xor     rax, rsp
0x180008f55  mov     [rbp+1B0h+var_30], rax
0x180008f5c  xorps   xmm0, xmm0
0x180008f5f  mov     [rsp+2B0h+KeyHandle], 0
0x180008f68  mov     r13d, edx
0x180008f6b  mov     rbx, rcx
0x180008f6e  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x180008f75  mov     esi, r9d
0x180008f78  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x180008f7d  mov     edi, r8d
0x180008f80  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.Length], xmm0
0x180008f85  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.ObjectName], xmm0
0x180008f8a  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180008f8f  movups  xmmword ptr [rsp+2B0h+DestinationString.Length], xmm0
0x180008f94  call    cs:__imp_RtlInitUnicodeString
0x180008f9a  lea     rax, [rsp+2B0h+DestinationString]
0x180008f9f  mov     qword ptr [rsp+2B0h+ObjectAttributes.Length], 30h ; '0'
0x180008fa8  xorps   xmm0, xmm0
0x180008fab  mov     [rsp+2B0h+ObjectAttributes.ObjectName], rax
0x180008fb0  lea     r8, [rsp+2B0h+ObjectAttributes]; ObjectAttributes
0x180008fb5  mov     qword ptr [rsp+2B0h+ObjectAttributes.Attributes], 40h ; '@'
0x180008fbe  mov     edx, 20019h; DesiredAccess
0x180008fc3  mov     [rsp+2B0h+ObjectAttributes.RootDirectory], 0
0x180008fcc  lea     rcx, [rsp+2B0h+KeyHandle]; KeyHandle
0x180008fd1  movdqu  xmmword ptr [rsp+2B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180008fd7  call    cs:__imp_NtOpenKey
0x180008fdd  test    eax, eax
0x180008fdf  js      short loc_180008FF3
0x180008fe1  mov     rcx, [rsp+2B0h+KeyHandle]; hObject
0x180008fe6  call    cs:__imp_CloseHandle
0x180008fec  xor     eax, eax
0x180008fee  jmp     loc_1800091FB
0x180008ff3  test    edi, edi
0x180008ff5  jz      short loc_18000905F
0x180008ff7  test    esi, esi
0x180008ff9  jz      short loc_18000905F
0x180008ffb  xorps   xmm0, xmm0
0x180008ffe  lea     r8, [rsp+2B0h+ObjectAttributes]; lpFileInformation
0x180009003  xor     eax, eax
0x180009005  xor     edx, edx; fInfoLevelId
0x180009007  mov     rcx, rbx; lpFileName
0x18000900a  mov     dword ptr [rsp+2B0h+ObjectAttributes.SecurityDescriptor], eax
0x18000900e  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.Length], xmm0
0x180009013  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.ObjectName], xmm0
0x180009018  call    cs:__imp_GetFileAttributesExW
0x18000901e  test    eax, eax
0x180009020  jz      short loc_180009050
0x180009022  mov     edx, dword ptr [rsp+2B0h+ObjectAttributes+1Ch]
0x180009026  mov     eax, dword ptr [rsp+2B0h+ObjectAttributes.SecurityDescriptor]
0x18000902a  shl     rdx, 20h
0x18000902e  add     rdx, rax
0x180009031  cmp     [rbp+1B0h+arg_20], 0
0x180009038  jnz     short loc_180009040
0x18000903a  shr     rdx, 14h
0x18000903e  jmp     short loc_180009044
0x180009040  shr     rdx, 0Ah
0x180009044  cmp     edx, edi
0x180009046  jnb     loc_1800091C7
0x18000904c  sub     edi, edx
0x18000904e  jmp     short loc_18000905F
0x180009050  call    cs:__imp_GetLastError
0x180009056  cmp     eax, 2
0x180009059  jnz     loc_1800091FB
0x18000905f  xor     edx, edx; Val
0x180009061  lea     rcx, [rsp+2B0h+Buffer]; void *
0x180009066  mov     r8d, 208h; Size
0x18000906c  call    memset_0
0x180009071  mov     edx, 104h; uSize
0x180009076  lea     rcx, [rsp+2B0h+Buffer]; lpBuffer
0x18000907b  call    cs:__imp_GetSystemDirectoryW
0x180009081  test    eax, eax
0x180009083  jnz     short loc_180009090
0x180009085  call    cs:__imp_GetLastError
0x18000908b  jmp     loc_1800091FB
0x180009090  cmp     eax, 2
0x180009093  jb      loc_1800091F6
0x180009099  cmp     r13d, 2
0x18000909d  jb      loc_1800091F6
0x1800090a3  cmp     word ptr [rbx+2], 3Ah ; ':'
0x1800090a8  jnz     short loc_1800090F7
0x1800090aa  cmp     [rsp+2B0h+var_23E], 3Ah ; ':'
0x1800090b0  jnz     short loc_1800090F7
0x1800090b2  mov     r8d, 1; MaxCount
0x1800090b8  lea     rdx, [rsp+2B0h+Buffer]; String2
0x1800090bd  mov     rcx, rbx; String1
0x1800090c0  call    _wcsnicmp
0x1800090c5  test    eax, eax
0x1800090c7  jnz     short loc_1800090F7
0x1800090c9  cmp     [rbp+1B0h+arg_20], eax
0x1800090cf  jnz     short loc_1800090E5
0x1800090d1  cmp     edi, 0FFFFFF37h
0x1800090d7  ja      loc_1800091C7
0x1800090dd  add     edi, 0C8h
0x1800090e3  jmp     short loc_1800090F7
0x1800090e5  cmp     edi, 0FFFCDFFFh
0x1800090eb  ja      loc_1800091C7
0x1800090f1  add     edi, 32000h
0x1800090f7  test    edi, edi
0x1800090f9  jz      loc_180008FEC
0x1800090ff  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180009106  mov     qword ptr [rsp+2B0h+FreeBytesAvailableToCaller], 0
0x18000910f  lea     r14d, [r13+1]
0x180009113  mov     qword ptr [rsp+2B0h+DestinationString.Length], 0
0x18000911c  mov     eax, 2
0x180009121  mul     r14
0x180009124  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000912b  cmovb   rax, rcx
0x18000912f  mov     rcx, rax; unsigned __int64
0x180009132  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180009137  mov     rsi, rax
0x18000913a  test    rax, rax
0x18000913d  jnz     short loc_180009147
0x18000913f  lea     eax, [rsi+8]
0x180009142  jmp     loc_1800091FB
0x180009147  mov     r8, rbx; unsigned __int16 *
0x18000914a  mov     rdx, r14; unsigned __int64
0x18000914d  mov     rcx, rsi; unsigned __int16 *
0x180009150  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009155  lea     r11d, [r13-1]
0x180009159  test    r11d, r11d
0x18000915c  js      short loc_180009174
0x18000915e  cmp     word ptr [rsi+r11*2], 5Ch ; '\'
0x180009164  jz      short loc_1800091CE
0x180009166  cmp     word ptr [rsi+r11*2], 2Fh ; '/'
0x18000916c  jz      short loc_1800091CE
0x18000916e  sub     r11d, 1
0x180009172  jns     short loc_18000915E
0x180009174  mov     rcx, rsi; Block
0x180009177  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000917c  xor     esi, esi
0x18000917e  xor     r9d, r9d; lpTotalNumberOfFreeBytes
0x180009181  lea     r8, [rsp+2B0h+DestinationString]; lpTotalNumberOfBytes
0x180009186  lea     rdx, [rsp+2B0h+FreeBytesAvailableToCaller]; lpFreeBytesAvailableToCaller
0x18000918b  mov     rcx, rsi; lpDirectoryName
0x18000918e  call    cs:__imp_GetDiskFreeSpaceExW
0x180009194  test    eax, eax
0x180009196  jz      short loc_1800091E0
0x180009198  mov     rbx, qword ptr [rsp+2B0h+FreeBytesAvailableToCaller]
0x18000919d  mov     r14, rbx
0x1800091a0  shr     rbx, 0Ah
0x1800091a4  shr     r14, 14h
0x1800091a8  test    rsi, rsi
0x1800091ab  jz      short loc_1800091B5
0x1800091ad  mov     rcx, rsi; Block
0x1800091b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800091b5  cmp     [rbp+1B0h+arg_20], 0
0x1800091bc  jnz     short loc_1800091D7
0x1800091be  cmp     r14d, edi
0x1800091c1  jnb     loc_180008FEC
0x1800091c7  mov     eax, 70h ; 'p'
0x1800091cc  jmp     short loc_1800091FB
0x1800091ce  xor     eax, eax
0x1800091d0  mov     [rsi+r11*2], ax
0x1800091d5  jmp     short loc_18000917E
0x1800091d7  cmp     ebx, edi
0x1800091d9  sbb     eax, eax
0x1800091db  and     eax, 70h
0x1800091de  jmp     short loc_1800091FB
0x1800091e0  test    rsi, rsi
0x1800091e3  jz      loc_180009085
0x1800091e9  mov     rcx, rsi; Block
0x1800091ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800091f1  jmp     loc_180009085
0x1800091f6  mov     eax, 57h ; 'W'
0x1800091fb  mov     rcx, [rbp+1B0h+var_30]
0x180009202  xor     rcx, rsp; StackCookie
0x180009205  call    __security_check_cookie
0x18000920a  mov     rbx, [rsp+2B0h+arg_10]
0x180009212  add     rsp, 290h
0x180009219  pop     r14
0x18000921b  pop     r13
0x18000921d  pop     rdi
0x18000921e  pop     rsi
0x18000921f  pop     rbp
0x180009220  retn
```
