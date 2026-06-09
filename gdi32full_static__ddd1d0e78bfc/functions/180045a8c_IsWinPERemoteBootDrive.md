# IsWinPERemoteBootDrive

- ea: `0x180045a8c`
- end: `0x180045c22`
- name: `IsWinPERemoteBootDrive`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, registry_config, loader_planting`

## callers

- `0x180045a00`

## callees

- `0x180045a8c`
- `0x18007f800`
- `0x180080604`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180045b11`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180045b11`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180045b37`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180045b37`
- `ntdll!RtlInitUnicodeString` at `0x180045b81`
- `ntdll!RtlInitUnicodeString` at `0x180045b81`
- `ntdll!NtOpenKey` at `0x180045bc4`
- `ntdll!NtOpenKey` at `0x180045bc4`
- `ntdll!NtClose` at `0x180045bdf`
- `ntdll!NtClose` at `0x180045bdf`

## string_xrefs

- `0x180045b66`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control\MiniNT`

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
  if ( !dword_1800FD7A8 )
  {
    memset_0(Buffer, 0, 0x208u);
    dword_1800FD7A8 = 1;
    if ( GetWindowsDirectoryW(Buffer, 0x104u) )
    {
      word_1800FD7A4 = Buffer[0];
      Buffer[3] = 0;
      DriveTypeW = GetDriveTypeW(Buffer);
      dword_1800FD7A0 = DriveTypeW == 4;
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
          dword_1800FD7A0 = 1;
          NtClose(KeyHandle);
          goto LABEL_2;
        }
        dword_1800FD7A0 = 0;
      }
      return 0;
    }
  }
LABEL_2:
  if ( !dword_1800FD7A0 || !a1 || !*a1 || word_1800FD7A4 != *a1 )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x180045a8c  push    rbp
0x180045a8e  push    rbx
0x180045a8f  push    rsi
0x180045a90  push    rdi
0x180045a91  lea     rbp, [rsp-198h]
0x180045a99  sub     rsp, 298h
0x180045aa0  mov     rax, cs:__security_cookie
0x180045aa7  xor     rax, rsp
0x180045aaa  mov     [rbp+1B0h+var_30], rax
0x180045ab1  xor     esi, esi
0x180045ab3  mov     rdi, rcx
0x180045ab6  cmp     cs:dword_1800FD7A8, esi
0x180045abc  mov     ebx, 1
0x180045ac1  jz      short loc_180045AEF
0x180045ac3  cmp     cs:dword_1800FD7A0, esi
0x180045ac9  jnz     loc_180045BFB
0x180045acf  mov     ebx, esi
0x180045ad1  mov     eax, ebx
0x180045ad3  mov     rcx, [rbp+1B0h+var_30]
0x180045ada  xor     rcx, rsp; StackCookie
0x180045add  call    __security_check_cookie
0x180045ae2  add     rsp, 298h
0x180045ae9  pop     rdi
0x180045aea  pop     rsi
0x180045aeb  pop     rbx
0x180045aec  pop     rbp
0x180045aed  retn
0x180045aef  xor     edx, edx; Val
0x180045af1  lea     rcx, [rsp+2B0h+Buffer]; void *
0x180045af6  mov     r8d, 208h; Size
0x180045afc  call    memset_0
0x180045b01  mov     edx, 104h; uSize
0x180045b06  mov     cs:dword_1800FD7A8, ebx
0x180045b0c  lea     rcx, [rsp+2B0h+Buffer]; lpBuffer
0x180045b11  call    cs:__imp_GetWindowsDirectoryW
0x180045b18  nop     dword ptr [rax+rax+00h]
0x180045b1d  test    eax, eax
0x180045b1f  jz      short loc_180045AC3
0x180045b21  movzx   eax, [rsp+2B0h+Buffer]
0x180045b26  lea     rcx, [rsp+2B0h+Buffer]; lpRootPathName
0x180045b2b  mov     cs:word_1800FD7A4, ax
0x180045b32  mov     [rsp+2B0h+var_23A], si
0x180045b37  call    cs:__imp_GetDriveTypeW
0x180045b3e  nop     dword ptr [rax+rax+00h]
0x180045b43  mov     ecx, esi
0x180045b45  cmp     eax, 4
0x180045b48  setz    cl
0x180045b4b  mov     cs:dword_1800FD7A0, ecx
0x180045b51  jnz     loc_180045ACF
0x180045b57  xorps   xmm0, xmm0
0x180045b5a  mov     [rsp+2B0h+KeyHandle], rsi
0x180045b5f  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.ObjectName], xmm0
0x180045b64  xor     eax, eax
0x180045b66  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x180045b6d  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x180045b72  movups  xmmword ptr [rsp+2B0h+ObjectAttributes+1Ch], xmm0
0x180045b77  movups  xmmword ptr [rsp+2B0h+ObjectAttributes.Length], xmm0
0x180045b7c  movups  xmmword ptr [rsp+2B0h+DestinationString.Length], xmm0
0x180045b81  call    cs:__imp_RtlInitUnicodeString
0x180045b88  nop     dword ptr [rax+rax+00h]
0x180045b8d  lea     rax, [rsp+2B0h+DestinationString]
0x180045b92  mov     [rsp+2B0h+ObjectAttributes.Length], 30h ; '0'
0x180045b9a  xorps   xmm0, xmm0
0x180045b9d  mov     [rsp+2B0h+ObjectAttributes.ObjectName], rax
0x180045ba2  lea     r8, [rsp+2B0h+ObjectAttributes]; ObjectAttributes
0x180045ba7  mov     [rsp+2B0h+ObjectAttributes.RootDirectory], rsi
0x180045bac  mov     edx, 20019h; DesiredAccess
0x180045bb1  mov     [rsp+2B0h+ObjectAttributes.Attributes], 40h ; '@'
0x180045bb9  lea     rcx, [rsp+2B0h+KeyHandle]; KeyHandle
0x180045bbe  movdqu  xmmword ptr [rsp+2B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180045bc4  call    cs:__imp_NtOpenKey
0x180045bcb  nop     dword ptr [rax+rax+00h]
0x180045bd0  test    eax, eax
0x180045bd2  js      short loc_180045BF0
0x180045bd4  mov     rcx, [rsp+2B0h+KeyHandle]; Handle
0x180045bd9  mov     cs:dword_1800FD7A0, ebx
0x180045bdf  call    cs:__imp_NtClose
0x180045be6  nop     dword ptr [rax+rax+00h]
0x180045beb  jmp     loc_180045AC3
0x180045bf0  mov     cs:dword_1800FD7A0, esi
0x180045bf6  jmp     loc_180045ACF
0x180045bfb  test    rdi, rdi
0x180045bfe  jz      loc_180045ACF
0x180045c04  movzx   eax, word ptr [rdi]
0x180045c07  test    ax, ax
0x180045c0a  jz      loc_180045ACF
0x180045c10  cmp     cs:word_1800FD7A4, ax
0x180045c17  jz      loc_180045AD1
0x180045c1d  jmp     loc_180045ACF
```
