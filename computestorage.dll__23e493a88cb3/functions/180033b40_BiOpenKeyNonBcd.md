# BiOpenKeyNonBcd

- ea: `0x180033b40`
- end: `0x180033c61`
- name: `BiOpenKeyNonBcd`
- size: `289`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180032b00`
- `0x1800334d4`

## callees

- `0x180033b40`

## import_xrefs

- `ntdll!ZwClose` at `0x180033c04`
- `ntdll!ZwClose` at `0x180033c04`
- `ntdll!RtlInitUnicodeString` at `0x180033b97`
- `ntdll!RtlInitUnicodeString` at `0x180033b97`
- `ntdll!ZwOpenKey` at `0x180033bd8`
- `ntdll!ZwOpenKey` at `0x180033bd8`

## pseudocode

```c
__int64 __fastcall BiOpenKeyNonBcd(void *a1, const WCHAR *a2, ACCESS_MASK a3, void **a4)
{
  unsigned int i; // edi
  NTSTATUS v9; // ebx
  void *KeyHandle; // [rsp+28h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-68h] BYREF

  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  for ( i = 0; ; ++i )
  {
    KeyHandle = 0;
    RtlInitUnicodeString(&DestinationString, a2);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = a1;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v9 = ZwOpenKey(&KeyHandle, a3, &ObjectAttributes);
    if ( v9 < 0 )
    {
      if ( KeyHandle )
        ZwClose(KeyHandle);
    }
    else
    {
      *a4 = KeyHandle;
    }
    if ( v9 != -1073741443 )
      break;
    __debugbreak();
    if ( i >= 5 )
      break;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180033b40  mov     rax, rsp
0x180033b43  mov     [rax+20h], r9
0x180033b47  mov     [rax+18h], r8d
0x180033b4b  mov     [rax+10h], rdx
0x180033b4f  mov     [rax+8], rcx
0x180033b53  push    rbx
0x180033b54  push    rsi
0x180033b55  push    rdi
0x180033b56  push    r12
0x180033b58  push    r14
0x180033b5a  push    r15
0x180033b5c  sub     rsp, 78h
0x180033b60  mov     rsi, r9
0x180033b63  mov     r14d, r8d
0x180033b66  mov     r15, rdx
0x180033b69  mov     r12, rcx
0x180033b6c  xorps   xmm0, xmm0
0x180033b6f  movups  xmmword ptr [rax-78h], xmm0
0x180033b73  xor     eax, eax
0x180033b75  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x180033b7a  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x180033b7f  movups  xmmword ptr [rsp+0A8h+ObjectAttributes+1Ch], xmm0
0x180033b84  xor     edi, edi
0x180033b86  mov     [rsp+0A8h+KeyHandle], 0
0x180033b8f  mov     rdx, r15; SourceString
0x180033b92  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x180033b97  call    cs:__imp_RtlInitUnicodeString
0x180033b9e  nop     dword ptr [rax+rax+00h]
0x180033ba3  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x180033bab  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], r12
0x180033bb0  mov     [rsp+0A8h+ObjectAttributes.Attributes], 40h ; '@'
0x180033bb8  lea     rax, [rsp+0A8h+DestinationString]
0x180033bbd  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x180033bc2  xorps   xmm0, xmm0
0x180033bc5  movdqu  xmmword ptr [rsp+0A8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180033bcb  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x180033bd0  mov     edx, r14d; DesiredAccess
0x180033bd3  lea     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x180033bd8  call    cs:__imp_ZwOpenKey
0x180033bdf  nop     dword ptr [rax+rax+00h]
0x180033be4  mov     ebx, eax
0x180033be6  mov     [rsp+0A8h+var_88], eax
0x180033bea  test    eax, eax
0x180033bec  js      short loc_180033BF6
0x180033bee  mov     rcx, [rsp+0A8h+KeyHandle]
0x180033bf3  mov     [rsi], rcx
0x180033bf6  test    ebx, ebx
0x180033bf8  jns     short loc_180033C10
0x180033bfa  mov     rcx, [rsp+0A8h+KeyHandle]; Handle
0x180033bff  test    rcx, rcx
0x180033c02  jz      short loc_180033C10
0x180033c04  call    cs:__imp_ZwClose
0x180033c0b  nop     dword ptr [rax+rax+00h]
0x180033c10  cmp     ebx, 0C000017Dh
0x180033c16  jnz     short loc_180033C50
0x180033c18  int     3; Trap to Debugger
0x180033c19  jmp     short loc_180033C44
0x180033c1b  mov     edi, 5
0x180033c20  mov     rsi, [rsp+0A8h+arg_18]
0x180033c28  mov     r14d, [rsp+0A8h+arg_10]
0x180033c30  mov     r15, [rsp+0A8h+arg_8]
0x180033c38  mov     r12, [rsp+0A8h+arg_0]
0x180033c40  mov     ebx, [rsp+0A8h+var_88]
0x180033c44  cmp     edi, 5
0x180033c47  jnb     short loc_180033C50
0x180033c49  inc     edi
0x180033c4b  jmp     loc_180033B86
0x180033c50  mov     eax, ebx
0x180033c52  add     rsp, 78h
0x180033c56  pop     r15
0x180033c58  pop     r14
0x180033c5a  pop     r12
0x180033c5c  pop     rdi
0x180033c5d  pop     rsi
0x180033c5e  pop     rbx
0x180033c5f  retn
```
