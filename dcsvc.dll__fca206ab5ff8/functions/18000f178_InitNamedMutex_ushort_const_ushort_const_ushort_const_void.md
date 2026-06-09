# InitNamedMutex(ushort const *,ushort const *,ushort const *,void * *)

- ea: `0x18000f178`
- end: `0x18000f231`
- name: `?InitNamedMutex@@YAJPEBG00PEAPEAX@Z`
- size: `185`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f00c`

## callees

- `0x18000f178`
- `0x1800106c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f1eb`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000f1e0`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000f1e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f211`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f211`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000f219`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18000f219`

## string_xrefs

- `0x18000f1be`: `ConfigManagerMutexUAP`

## pseudocode

```c
__int64 __fastcall InitNamedMutex(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void **a4)
{
  int MergedSecurityDescriptorForTransientObject; // ebx
  HANDLE v7; // rax
  signed int LastError; // eax
  _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+30h] [rbp-28h] BYREF
  int v11; // [rsp+60h] [rbp+8h] BYREF
  int v12; // [rsp+64h] [rbp+Ch]

  v12 = HIDWORD(a1);
  *(_OWORD *)&MutexAttributes.nLength = 0;
  *(&MutexAttributes.bInheritHandle + 1) = 0;
  *a4 = 0;
  MutexAttributes.bInheritHandle = 0;
  v11 = 0;
  MutexAttributes.nLength = 24;
  MergedSecurityDescriptorForTransientObject = DmGetMergedSecurityDescriptorForTransientObject(
                                                 0,
                                                 (__int64)L"ConfigManagerMutexUAP",
                                                 (__int64)a2,
                                                 &MutexAttributes.lpSecurityDescriptor,
                                                 &v11);
  if ( MergedSecurityDescriptorForTransientObject >= 0 )
  {
    v7 = CreateMutexW(&MutexAttributes, 0, a3);
    if ( v7 )
    {
      *a4 = v7;
    }
    else
    {
      LastError = GetLastError();
      MergedSecurityDescriptorForTransientObject = LastError;
      if ( LastError > 0 )
        MergedSecurityDescriptorForTransientObject = (unsigned __int16)LastError | 0x80070000;
    }
  }
  if ( v11 )
    FreeTransientObjectSecurityDescriptor(MutexAttributes.lpSecurityDescriptor);
  else
    LocalFree(MutexAttributes.lpSecurityDescriptor);
  return (unsigned int)MergedSecurityDescriptorForTransientObject;
}

```

## disassembly

```asm
0x18000f178  mov     r11, rsp
0x18000f17b  mov     [r11+10h], rbx
0x18000f17f  mov     [r11+18h], rsi
0x18000f183  mov     [r11+8], rcx
0x18000f187  push    rdi
0x18000f188  sub     rsp, 50h
0x18000f18c  xor     eax, eax
0x18000f18e  xorps   xmm0, xmm0
0x18000f191  movups  xmmword ptr [rsp+58h+MutexAttributes.nLength], xmm0
0x18000f196  mov     [r11-18h], rax
0x18000f19a  mov     rsi, r8
0x18000f19d  mov     [r9], rax
0x18000f1a0  mov     rdi, r9
0x18000f1a3  mov     [rsp+58h+MutexAttributes.bInheritHandle], eax
0x18000f1a7  lea     r9, [r11-20h]
0x18000f1ab  mov     [rsp+58h+arg_0], eax
0x18000f1af  mov     r8, rdx
0x18000f1b2  lea     rax, [r11+8]
0x18000f1b6  mov     [rsp+58h+MutexAttributes.nLength], 18h
0x18000f1be  lea     rdx, aConfigmanagerm_0; "ConfigManagerMutexUAP"
0x18000f1c5  mov     [r11-38h], rax
0x18000f1c9  xor     ecx, ecx
0x18000f1cb  call    ?DmGetMergedSecurityDescriptorForTransientObject@@YAJW4TransientObject_Type@@PEBG1PEAPEAXPEAH@Z; DmGetMergedSecurityDescriptorForTransientObject(TransientObject_Type,ushort const *,ushort const *,void * *,int *)
0x18000f1d0  mov     ebx, eax
0x18000f1d2  test    eax, eax
0x18000f1d4  js      short loc_18000F205
0x18000f1d6  mov     r8, rsi; lpName
0x18000f1d9  lea     rcx, [rsp+58h+MutexAttributes]; lpMutexAttributes
0x18000f1de  xor     edx, edx; bInitialOwner
0x18000f1e0  call    cs:__imp_CreateMutexW
0x18000f1e6  test    rax, rax
0x18000f1e9  jnz     short loc_18000F202
0x18000f1eb  call    cs:__imp_GetLastError
0x18000f1f1  mov     ebx, eax
0x18000f1f3  test    eax, eax
0x18000f1f5  jle     short loc_18000F205
0x18000f1f7  movzx   ebx, ax
0x18000f1fa  or      ebx, 80070000h
0x18000f200  jmp     short loc_18000F205
0x18000f202  mov     [rdi], rax
0x18000f205  cmp     [rsp+58h+arg_0], 0
0x18000f20a  mov     rcx, [rsp+58h+MutexAttributes.lpSecurityDescriptor]; hMem
0x18000f20f  jnz     short loc_18000F219
0x18000f211  call    cs:__imp_LocalFree
0x18000f217  jmp     short loc_18000F21F
0x18000f219  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000f21f  mov     rsi, [rsp+58h+arg_10]
0x18000f224  mov     eax, ebx
0x18000f226  mov     rbx, [rsp+58h+arg_8]
0x18000f22b  add     rsp, 50h
0x18000f22f  pop     rdi
0x18000f230  retn
```
