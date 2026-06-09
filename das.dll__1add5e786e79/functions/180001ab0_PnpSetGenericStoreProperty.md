# _PnpSetGenericStoreProperty

- ea: `0x180001ab0`
- end: `0x180001d14`
- name: `_PnpSetGenericStoreProperty`
- size: `612`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180001924`
- `0x180005c5c`
- `0x180006440`
- `0x1800068a0`

## callees

- `0x180001ab0`
- `0x180001f50`
- `0x1800037f0`
- `0x180003bf0`
- `0x18001df70`
- `0x18003bc80`

## import_xrefs

- `ntdll!NtClose` at `0x180001ca2`
- `ntdll!NtClose` at `0x180001ca2`
- `ntdll!NtDeleteValueKey` at `0x180001c92`
- `ntdll!NtDeleteValueKey` at `0x180001c92`
- `ntdll!RtlInitUnicodeStringEx` at `0x180001c7b`
- `ntdll!RtlInitUnicodeStringEx` at `0x180001c7b`

## pseudocode

```c
__int64 __fastcall PnpSetGenericStoreProperty(
        __int64 a1,
        char *a2,
        PCWSTR SourceString,
        _DWORD *a4,
        int a5,
        void *a6,
        ULONG a7)
{
  int v12; // eax
  unsigned int v13; // edi
  HANDLE v14; // rsi
  NTSTATUS inited; // ebx
  int v16; // [rsp+28h] [rbp-140h]
  HANDLE KeyHandle; // [rsp+90h] [rbp-D8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-D0h] BYREF
  _WORD v19[48]; // [rsp+B0h] [rbp-B8h] BYREF

  if ( a5 )
    return PnpSetPropertyWorker(a1, (int)a2, SourceString, a4, a5, a6, a7);
  KeyHandle = 0;
  if ( a7 )
    return (unsigned int)-1073741811;
  if ( SourceString )
  {
    v13 = RtlUnalignedStringCchLengthW(SourceString, 85, &DestinationString);
    if ( (v13 & 0x80000000) != 0 )
      return v13;
  }
  if ( (int)RtlStringCchPrintfExW(
              (int)v19,
              48,
              0,
              0,
              2048,
              (__int64)L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}\\%04lX",
              *a4) < 0 )
    return (unsigned int)-1073741595;
  v12 = PnpOpenPropertiesKey(a1, a2, v19, 6u, 0, v16, &KeyHandle);
  v13 = v12;
  if ( v12 == -1073741772 )
    return (unsigned int)-1073741275;
  if ( v12 >= 0 )
  {
    v14 = KeyHandle;
    DestinationString = 0;
    inited = RtlInitUnicodeStringEx(&DestinationString, SourceString);
    if ( inited >= 0 )
      inited = NtDeleteValueKey(v14, &DestinationString);
    NtClose(KeyHandle);
    if ( inited != -1073741772 && inited != -1073741444 )
    {
      if ( inited < 0 )
        return (unsigned int)inited;
      return v13;
    }
    return (unsigned int)-1073741275;
  }
  return v13;
}

```

## disassembly

```asm
0x180001ab0  push    r12
0x180001ab2  push    r13
0x180001ab4  push    r14
0x180001ab6  push    r15
0x180001ab8  sub     rsp, 148h
0x180001abf  mov     rax, cs:__security_cookie
0x180001ac6  xor     rax, rsp
0x180001ac9  mov     [rsp+168h+var_58], rax
0x180001ad1  mov     eax, [rsp+168h+arg_20]
0x180001ad8  mov     r13, rdx
0x180001adb  mov     rdx, [rsp+168h+arg_28]
0x180001ae3  mov     r14, r9
0x180001ae6  mov     r15, r8
0x180001ae9  mov     r12, rcx
0x180001aec  test    eax, eax
0x180001aee  jz      short loc_180001B2F
0x180001af0  mov     ecx, [rsp+168h+arg_30]
0x180001af7  mov     dword ptr [rsp+168h+Args], ecx; ULONG
0x180001afb  mov     rcx, r12; int
0x180001afe  mov     [rsp+168h+var_140], rdx; __int64
0x180001b03  mov     rdx, r13; int
0x180001b06  mov     [rsp+168h+var_148], eax; int
0x180001b0a  call    _PnpSetPropertyWorker
0x180001b0f  mov     rcx, [rsp+168h+var_58]
0x180001b17  xor     rcx, rsp; StackCookie
0x180001b1a  call    __security_check_cookie
0x180001b1f  add     rsp, 148h
0x180001b26  pop     r15
0x180001b28  pop     r14
0x180001b2a  pop     r13
0x180001b2c  pop     r12
0x180001b2e  retn
0x180001b2f  cmp     [rsp+168h+arg_30], 0
0x180001b37  mov     [rsp+168h+var_40], rdi
0x180001b3f  mov     [rsp+168h+var_28], rbx
0x180001b47  mov     [rsp+168h+var_38], rsi
0x180001b4f  mov     [rsp+168h+KeyHandle], 0
0x180001b5b  jnz     loc_180001D0D
0x180001b61  test    r15, r15
0x180001b64  jnz     loc_180001CE2
0x180001b6a  movzx   ecx, byte ptr [r9+0Fh]
0x180001b6f  movzx   edx, byte ptr [r9+0Eh]
0x180001b74  movzx   r8d, byte ptr [r9+0Dh]
0x180001b79  mov     eax, [r14+10h]
0x180001b7d  movzx   r9d, byte ptr [r9+0Ch]
0x180001b82  movzx   r10d, byte ptr [r14+0Bh]
0x180001b87  movzx   r11d, byte ptr [r14+0Ah]
0x180001b8c  movzx   ebx, byte ptr [r14+9]
0x180001b91  movzx   edi, byte ptr [r14+8]
0x180001b96  movzx   esi, word ptr [r14+6]
0x180001b9b  mov     [rsp+168h+var_E0], eax
0x180001ba2  mov     eax, [r14]
0x180001ba5  mov     [rsp+168h+var_E8], ecx
0x180001bac  lea     rcx, [rsp+168h+var_B8]; int
0x180001bb4  mov     [rsp+168h+var_F0], edx
0x180001bb8  mov     edx, 30h ; '0'; int
0x180001bbd  mov     [rsp+168h+var_F8], r8d
0x180001bc2  xor     r8d, r8d; int
0x180001bc5  mov     [rsp+168h+var_100], r9d
0x180001bca  xor     r9d, r9d; int
0x180001bcd  mov     [rsp+168h+var_108], r10d
0x180001bd2  mov     [rsp+168h+var_110], r11d
0x180001bd7  mov     [rsp+168h+var_118], ebx
0x180001bdb  mov     [rsp+168h+var_120], edi
0x180001bdf  mov     [rsp+168h+var_128], esi
0x180001be3  mov     [rsp+168h+var_30], rbp
0x180001beb  movzx   ebp, word ptr [r14+4]
0x180001bf0  mov     [rsp+168h+var_130], ebp
0x180001bf4  mov     dword ptr [rsp+168h+Args], eax; Args
0x180001bf8  lea     rax, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x180001bff  mov     [rsp+168h+var_140], rax; __int64
0x180001c04  mov     [rsp+168h+var_148], 800h; int
0x180001c0c  call    RtlStringCchPrintfExW
0x180001c11  mov     rbp, [rsp+168h+var_30]
0x180001c19  test    eax, eax
0x180001c1b  js      loc_180001D02
0x180001c21  lea     rax, [rsp+168h+KeyHandle]
0x180001c29  mov     r9d, 6
0x180001c2f  mov     qword ptr [rsp+168h+Args], rax
0x180001c34  lea     r8, [rsp+168h+var_B8]
0x180001c3c  mov     rdx, r13
0x180001c3f  mov     byte ptr [rsp+168h+var_148], 0
0x180001c44  mov     rcx, r12
0x180001c47  call    _PnpOpenPropertiesKey
0x180001c4c  mov     edi, eax
0x180001c4e  cmp     eax, 0C0000034h
0x180001c53  jz      loc_180001CDB
0x180001c59  test    eax, eax
0x180001c5b  js      short loc_180001CBC
0x180001c5d  mov     rsi, [rsp+168h+KeyHandle]
0x180001c65  lea     rcx, [rsp+168h+DestinationString]; DestinationString
0x180001c6d  xorps   xmm0, xmm0
0x180001c70  mov     rdx, r15; SourceString
0x180001c73  movups  xmmword ptr [rsp+168h+DestinationString.Length], xmm0
0x180001c7b  call    cs:__imp_RtlInitUnicodeStringEx
0x180001c81  mov     ebx, eax
0x180001c83  test    eax, eax
0x180001c85  js      short loc_180001C9A
0x180001c87  lea     rdx, [rsp+168h+DestinationString]; ValueName
0x180001c8f  mov     rcx, rsi; KeyHandle
0x180001c92  call    cs:__imp_NtDeleteValueKey
0x180001c98  mov     ebx, eax
0x180001c9a  mov     rcx, [rsp+168h+KeyHandle]; Handle
0x180001ca2  call    cs:__imp_NtClose
0x180001ca8  cmp     ebx, 0C0000034h
0x180001cae  jz      short loc_180001CDB
0x180001cb0  cmp     ebx, 0C000017Ch
0x180001cb6  jz      short loc_180001CDB
0x180001cb8  test    ebx, ebx
0x180001cba  js      short loc_180001D09
0x180001cbc  mov     rsi, [rsp+168h+var_38]
0x180001cc4  mov     eax, edi
0x180001cc6  mov     rdi, [rsp+168h+var_40]
0x180001cce  mov     rbx, [rsp+168h+var_28]
0x180001cd6  jmp     loc_180001B0F
0x180001cdb  mov     edi, 0C0000225h
0x180001ce0  jmp     short loc_180001CBC
0x180001ce2  lea     r8, [rsp+168h+DestinationString]
0x180001cea  mov     edx, 55h ; 'U'
0x180001cef  mov     rcx, r15
0x180001cf2  call    RtlUnalignedStringCchLengthW
0x180001cf7  mov     edi, eax
0x180001cf9  test    eax, eax
0x180001cfb  js      short loc_180001CBC
0x180001cfd  jmp     loc_180001B6A
0x180001d02  mov     edi, 0C00000E5h
0x180001d07  jmp     short loc_180001CBC
0x180001d09  mov     edi, ebx
0x180001d0b  jmp     short loc_180001CBC
0x180001d0d  mov     edi, 0C000000Dh
0x180001d12  jmp     short loc_180001CBC
```
