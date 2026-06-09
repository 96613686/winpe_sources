# IsWinPERemoteBootDrive

- ea: `0x180039fd8`
- end: `0x18003a14b`
- name: `IsWinPERemoteBootDrive`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x180039f54`

## callees

- `0x180039fd8`
- `0x18007ac50`
- `0x18007ba24`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18003a05c`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18003a05c`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18003a07c`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18003a07c`
- `ntdll!RtlInitUnicodeString` at `0x18003a0bc`
- `ntdll!RtlInitUnicodeString` at `0x18003a0bc`
- `ntdll!NtOpenKey` at `0x18003a0f9`
- `ntdll!NtOpenKey` at `0x18003a0f9`
- `ntdll!NtClose` at `0x18003a10e`
- `ntdll!NtClose` at `0x18003a10e`

## string_xrefs

- `0x18003a0a1`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\MiniNT`

## pseudocode

```c
__int64 __fastcall IsWinPERemoteBootDrive(_WORD *a1)
{
  unsigned int v2; // ebx
  UINT DriveTypeW; // eax
  void *KeyHandle; // [rsp+20h] [rbp-E0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+28h] [rbp-D8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF

  v2 = 1;
  if ( !dword_1800FA6B0 )
  {
    memset_0(Buffer, 0, 0x208u);
    dword_1800FA6B0 = 1;
    if ( GetWindowsDirectoryW(Buffer, 0x104u) )
    {
      word_1800FA6AC = Buffer[0];
      Buffer[3] = 0;
      DriveTypeW = GetDriveTypeW(Buffer);
      dword_1800FA6A8 = DriveTypeW == 4;
      if ( DriveTypeW == 4 )
      {
        KeyHandle = 0;
        memset(&ObjectAttributes.Attributes + 1, 0, 20);
        *(&ObjectAttributes.Length + 1) = 0;
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Control\\MiniNT");
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 64;
        if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
        {
          dword_1800FA6A8 = 1;
          NtClose(KeyHandle);
          goto LABEL_2;
        }
        dword_1800FA6A8 = 0;
      }
      return 0;
    }
  }
LABEL_2:
  if ( !dword_1800FA6A8 || !a1 || !*a1 || word_1800FA6AC != *a1 )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x180039fd8  push    rbp
0x180039fda  push    rbx
0x180039fdb  push    rsi
0x180039fdc  push    rdi
0x180039fdd  lea     rbp, [rsp-198h]
0x180039fe5  sub     rsp, 298h
0x180039fec  mov     rax, cs:__security_cookie
0x180039ff3  xor     rax, rsp
0x180039ff6  mov     [rbp+1B0h+var_30], rax
0x180039ffd  xor     esi, esi
0x180039fff  mov     rdi, rcx
0x18003a002  cmp     cs:dword_1800FA6B0, esi
0x18003a008  mov     ebx, 1
0x18003a00d  jz      short loc_18003A03A
0x18003a00f  cmp     cs:dword_1800FA6A8, esi
0x18003a015  jnz     loc_18003A124
0x18003a01b  mov     ebx, esi
0x18003a01d  mov     eax, ebx
0x18003a01f  mov     rcx, [rbp+1B0h+var_30]
0x18003a026  xor     rcx, rsp; StackCookie
0x18003a029  call    __security_check_cookie
0x18003a02e  add     rsp, 298h
0x18003a035  pop     rdi
0x18003a036  pop     rsi
0x18003a037  pop     rbx
0x18003a038  pop     rbp
0x18003a039  retn
0x18003a03a  xor     edx, edx; Val
0x18003a03c  lea     rcx, [rsp+2B0h+Buffer]; void *
0x18003a041  mov     r8d, 208h; Size
0x18003a047  call    memset_0
0x18003a04c  mov     edx, 104h; uSize
0x18003a051  mov     cs:dword_1800FA6B0, ebx
0x18003a057  lea     rcx, [rsp+2B0h+Buffer]; lpBuffer
0x18003a05c  call    cs:__imp_GetWindowsDirectoryW
0x18003a062  test    eax, eax
0x18003a064  jz      short loc_18003A00F
0x18003a066  movzx   eax, [rsp+2B0h+Buffer]
0x18003a06b  lea     rcx, [rsp+2B0h+Buffer]; lpRootPathName
0x18003a070  mov     cs:word_1800FA6AC, ax
0x18003a077  mov     [rsp+2B0h+var_23A], si
0x18003a07c  call    cs:__imp_GetDriveTypeW
0x18003a082  mov     ecx, esi
0x18003a084  cmp     eax, 4
0x18003a087  setz    cl
0x18003a08a  mov     cs:dword_1800FA6A8, ecx
0x18003a090  jnz     short loc_18003A01B
0x18003a092  xorps   xmm0, xmm0
0x18003a095  mov     [rsp+2B0h+KeyHandle], rsi
0x18003a09a  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.ObjectName], xmm0
0x18003a09f  xor     eax, eax
0x18003a0a1  lea     rdx, SourceString; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x18003a0a8  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x18003a0ad  movups  xmmword ptr [rsp+2B0h+ObjectAttributes+1Ch], xmm0
0x18003a0b2  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.Length], xmm0
0x18003a0b7  movups  xmmword ptr [rsp+2B0h+DestinationString.Length], xmm0
0x18003a0bc  call    cs:__imp_RtlInitUnicodeString
0x18003a0c2  lea     rax, [rsp+2B0h+DestinationString]
0x18003a0c7  mov     [rsp+2B0h+ObjectAttributes.Length], 30h ; '0'
0x18003a0cf  xorps   xmm0, xmm0
0x18003a0d2  mov     [rsp+2B0h+ObjectAttributes.ObjectName], rax
0x18003a0d7  lea     r8, [rsp+2B0h+ObjectAttributes]; ObjectAttributes
0x18003a0dc  mov     [rsp+2B0h+ObjectAttributes.RootDirectory], rsi
0x18003a0e1  mov     edx, 20019h; DesiredAccess
0x18003a0e6  mov     [rsp+2B0h+ObjectAttributes.Attributes], 40h ; '@'
0x18003a0ee  lea     rcx, [rsp+2B0h+KeyHandle]; KeyHandle
0x18003a0f3  movdqu  xmmword ptr [rsp+2B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003a0f9  call    cs:__imp_NtOpenKey
0x18003a0ff  test    eax, eax
0x18003a101  js      short loc_18003A119
0x18003a103  mov     rcx, [rsp+2B0h+KeyHandle]; Handle
0x18003a108  mov     cs:dword_1800FA6A8, ebx
0x18003a10e  call    cs:__imp_NtClose
0x18003a114  jmp     loc_18003A00F
0x18003a119  mov     cs:dword_1800FA6A8, esi
0x18003a11f  jmp     loc_18003A01B
0x18003a124  test    rdi, rdi
0x18003a127  jz      loc_18003A01B
0x18003a12d  movzx   eax, word ptr [rdi]
0x18003a130  test    ax, ax
0x18003a133  jz      loc_18003A01B
0x18003a139  cmp     cs:word_1800FA6AC, ax
0x18003a140  jz      loc_18003A01D
0x18003a146  jmp     loc_18003A01B
```
