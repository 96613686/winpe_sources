# LookupIPv6ZoneMapEntry

- ea: `0x1400896fc`
- end: `0x1400898db`
- name: `LookupIPv6ZoneMapEntry`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400898e4`

## callees

- `0x140039fa8`
- `0x140059f00`
- `0x1400896fc`
- `0x14008a73c`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14008985e`
- `ntoskrnl!ZwOpenKey` at `0x14008985e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008981f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14008981f`
- `ntoskrnl!ExAllocatePool2` at `0x14008978e`
- `ntoskrnl!ExAllocatePool2` at `0x14008978e`
- `ntoskrnl!ZwClose` at `0x1400898b4`
- `ntoskrnl!ZwClose` at `0x1400898b4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008989f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008989f`

## pseudocode

```c
__int64 __fastcall LookupIPv6ZoneMapEntry(unsigned __int16 *a1, const WCHAR *a2, int *a3)
{
  _WORD *v4; // rcx
  void *v7; // rbx
  unsigned int v8; // r14d
  _WORD *Pool2; // rax
  unsigned int v10; // edi
  __int128 v12; // [rsp+20h] [rbp-50h] BYREF
  UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  int v15; // [rsp+B0h] [rbp+40h] BYREF
  void *KeyHandle; // [rsp+C0h] [rbp+50h] BYREF

  KeyHandle = 0;
  v4 = (_WORD *)*((_QWORD *)a1 + 1);
  v15 = 3;
  *a3 = 3;
  v12 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( *v4 == 91 && v4[((unsigned __int64)*a1 >> 1) - 1] == 93 )
  {
    v7 = 0;
    v12 = *(_OWORD *)a1;
LABEL_10:
    RtlInitUnicodeString(&DestinationString, a2);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) < 0 || (int)RegQueryZoneFromKey(KeyHandle, &v12, &v15) < 0 )
    {
      v10 = -1073741772;
    }
    else
    {
      v10 = 0;
      *a3 = v15;
    }
    if ( v7 )
      ExFreePoolWithTag(v7, 0x7A4D6D53u);
    goto LABEL_16;
  }
  v8 = *a1 + 4;
  Pool2 = (_WORD *)ExAllocatePool2(258, v8, 2051894611);
  v7 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = 91;
    memmove(Pool2 + 1, *((const void **)a1 + 1), *a1);
    *((_WORD *)v7 + ((unsigned __int64)v8 >> 1) - 1) = 93;
    *((_QWORD *)&v12 + 1) = v7;
    LOWORD(v12) = v8;
    WORD1(v12) = v8;
    goto LABEL_10;
  }
  v10 = -1073741670;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids);
  }
LABEL_16:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return v10;
}

```

## disassembly

```asm
0x1400896fc  mov     [rsp-38h+arg_8], rbx
0x140089701  push    rbp
0x140089702  push    rsi
0x140089703  push    rdi
0x140089704  push    r12
0x140089706  push    r13
0x140089708  push    r14
0x14008970a  push    r15
0x14008970c  mov     rbp, rsp
0x14008970f  sub     rsp, 70h
0x140089713  xorps   xmm0, xmm0
0x140089716  mov     [rbp+KeyHandle], 0
0x14008971e  mov     eax, 3
0x140089723  mov     rdi, rcx
0x140089726  mov     rcx, [rcx+8]
0x14008972a  mov     r15, r8
0x14008972d  mov     [rbp+arg_0], eax
0x140089730  mov     r12, rdx
0x140089733  mov     [r8], eax
0x140089736  mov     eax, 5Bh ; '['
0x14008973b  movups  [rbp+var_50], xmm0
0x14008973f  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140089743  lea     r13d, [rax+2]
0x140089747  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14008974b  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14008974f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140089753  cmp     [rcx], ax
0x140089756  jnz     short loc_140089775
0x140089758  movzx   eax, word ptr [rdi]
0x14008975b  shr     rax, 1
0x14008975e  cmp     [rcx+rax*2-2], r13w
0x140089764  jnz     short loc_140089775
0x140089766  movups  xmm0, xmmword ptr [rdi]
0x140089769  xor     ebx, ebx
0x14008976b  movdqu  [rbp+var_50], xmm0
0x140089770  jmp     loc_140089818
0x140089775  movzx   r14d, word ptr [rdi]
0x140089779  mov     r8d, 7A4D6D53h
0x14008977f  add     r14d, 4
0x140089783  mov     ecx, 102h
0x140089788  mov     edx, r14d
0x14008978b  mov     esi, r14d
0x14008978e  call    cs:__imp_ExAllocatePool2
0x140089795  nop     dword ptr [rax+rax+00h]
0x14008979a  mov     rbx, rax
0x14008979d  test    rax, rax
0x1400897a0  jnz     short loc_1400897EB
0x1400897a2  mov     edi, 0C000009Ah
0x1400897a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400897ae  lea     rax, WPP_GLOBAL_Control
0x1400897b5  cmp     rcx, rax
0x1400897b8  jz      loc_1400898AB
0x1400897be  mov     eax, [rcx+2Ch]
0x1400897c1  test    al, 1
0x1400897c3  jz      loc_1400898AB
0x1400897c9  cmp     byte ptr [rcx+29h], 1
0x1400897cd  jb      loc_1400898AB
0x1400897d3  mov     rcx, [rcx+18h]
0x1400897d7  lea     edx, [rbx+45h]
0x1400897da  lea     r8, WPP_318b97441ad5316ed29d4021e7d37a6e_Traceguids
0x1400897e1  call    WPP_SF_
0x1400897e6  jmp     loc_1400898AB
0x1400897eb  mov     word ptr [rax], 5Bh ; '['
0x1400897f0  lea     rcx, [rax+2]; void *
0x1400897f4  movzx   r8d, word ptr [rdi]; Size
0x1400897f8  mov     rdx, [rdi+8]; Src
0x1400897fc  call    memmove
0x140089801  shr     rsi, 1
0x140089804  mov     [rbx+rsi*2-2], r13w
0x14008980a  mov     qword ptr [rbp+var_50+8], rbx
0x14008980e  mov     word ptr [rbp+var_50], r14w
0x140089813  mov     word ptr [rbp+var_50+2], r14w
0x140089818  mov     rdx, r12; SourceString
0x14008981b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14008981f  call    cs:__imp_RtlInitUnicodeString
0x140089826  nop     dword ptr [rax+rax+00h]
0x14008982b  lea     rax, [rbp+DestinationString]
0x14008982f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140089836  xorps   xmm0, xmm0
0x140089839  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14008983d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140089841  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140089849  mov     edx, 20019h; DesiredAccess
0x14008984e  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140089855  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140089859  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14008985e  call    cs:__imp_ZwOpenKey
0x140089865  nop     dword ptr [rax+rax+00h]
0x14008986a  test    eax, eax
0x14008986c  js      short loc_14008988D
0x14008986e  mov     rcx, [rbp+KeyHandle]
0x140089872  lea     r8, [rbp+arg_0]
0x140089876  lea     rdx, [rbp+var_50]
0x14008987a  call    RegQueryZoneFromKey
0x14008987f  test    eax, eax
0x140089881  js      short loc_14008988D
0x140089883  xor     edi, edi
0x140089885  mov     eax, [rbp+arg_0]
0x140089888  mov     [r15], eax
0x14008988b  jmp     short loc_140089892
0x14008988d  mov     edi, 0C0000034h
0x140089892  test    rbx, rbx
0x140089895  jz      short loc_1400898AB
0x140089897  mov     edx, 7A4D6D53h; Tag
0x14008989c  mov     rcx, rbx; P
0x14008989f  call    cs:__imp_ExFreePoolWithTag
0x1400898a6  nop     dword ptr [rax+rax+00h]
0x1400898ab  mov     rcx, [rbp+KeyHandle]; Handle
0x1400898af  test    rcx, rcx
0x1400898b2  jz      short loc_1400898C0
0x1400898b4  call    cs:__imp_ZwClose
0x1400898bb  nop     dword ptr [rax+rax+00h]
0x1400898c0  mov     rbx, [rsp+70h+arg_8]
0x1400898c8  mov     eax, edi
0x1400898ca  add     rsp, 70h
0x1400898ce  pop     r15
0x1400898d0  pop     r14
0x1400898d2  pop     r13
0x1400898d4  pop     r12
0x1400898d6  pop     rdi
0x1400898d7  pop     rsi
0x1400898d8  pop     rbp
0x1400898d9  retn
```
