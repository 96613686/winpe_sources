# BthQueryAllocateKeyValue

- ea: `0x140034168`
- end: `0x140034287`
- name: `BthQueryAllocateKeyValue`
- size: `287`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000916c`

## callees

- `0x140034168`
- `0x140034290`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14003421c`
- `ntoskrnl!ExAllocatePool2` at `0x14003421c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034257`
- `ntoskrnl!ExFreePoolWithTag` at `0x140034257`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400341ca`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400341ca`

## string_xrefs

- `0x1400341be`: `SecurityDescriptor`

## pseudocode

```c
__int64 __fastcall BthQueryAllocateKeyValue(
        HANDLE KeyHandle,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        unsigned int *a6)
{
  _QWORD *v6; // r14
  unsigned int *v7; // r15
  int v10; // eax
  unsigned int v11; // esi
  void *v12; // rdi
  int v13; // ebx
  void *Pool2; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v16; // [rsp+78h] [rbp+20h] BYREF
  int v17; // [rsp+7Ch] [rbp+24h]

  v17 = HIDWORD(a4);
  v6 = a5;
  v7 = a6;
  v16 = 0;
  DestinationString = 0;
  *a5 = 0;
  *v7 = 0;
  if ( !KeyHandle )
    return 3221225485LL;
  RtlInitUnicodeString(&DestinationString, L"SecurityDescriptor");
  v10 = BthQueryKeyValueEx(KeyHandle, &DestinationString, 0, (__int64)&v16);
  v11 = v16;
  if ( v10 != -1073741789 && v10 != -2147483643 )
  {
    v12 = 0;
    v13 = -1073741823;
    goto LABEL_10;
  }
  Pool2 = (void *)ExAllocatePool2(256, v16, 1818784834);
  v12 = Pool2;
  if ( !Pool2 )
  {
    v13 = -1073741670;
    goto LABEL_10;
  }
  v13 = BthQueryKeyValueEx(KeyHandle, &DestinationString, Pool2, 0);
  if ( v13 >= 0 )
  {
LABEL_10:
    *v6 = v12;
    *v7 = v11;
    return (unsigned int)v13;
  }
  ExFreePoolWithTag(v12, 0);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140034168  mov     rax, rsp
0x14003416b  mov     [rax+8], rbx
0x14003416f  mov     [rax+10h], rsi
0x140034173  mov     [rax+20h], r9
0x140034177  push    rdi
0x140034178  push    r14
0x14003417a  push    r15
0x14003417c  sub     rsp, 40h
0x140034180  mov     r14, [rsp+58h+arg_20]
0x140034188  xorps   xmm0, xmm0
0x14003418b  mov     r15, [rsp+58h+arg_28]
0x140034193  mov     rbx, rcx
0x140034196  mov     dword ptr [rax+20h], 0
0x14003419d  movups  xmmword ptr [rax-28h], xmm0
0x1400341a1  mov     qword ptr [r14], 0
0x1400341a8  mov     dword ptr [r15], 0
0x1400341af  test    rcx, rcx
0x1400341b2  jnz     short loc_1400341BE
0x1400341b4  mov     eax, 0C000000Dh
0x1400341b9  jmp     loc_140034272
0x1400341be  lea     rdx, aSecuritydescri; "SecurityDescriptor"
0x1400341c5  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x1400341ca  call    cs:__imp_RtlInitUnicodeString
0x1400341d1  nop     dword ptr [rax+rax+00h]
0x1400341d6  lea     rax, [rsp+58h+arg_18]
0x1400341db  xor     r9d, r9d
0x1400341de  xor     r8d, r8d; void *
0x1400341e1  mov     [rsp+58h+var_38], rax; __int64
0x1400341e6  lea     rdx, [rsp+58h+DestinationString]; ValueName
0x1400341eb  mov     rcx, rbx; KeyHandle
0x1400341ee  call    BthQueryKeyValueEx
0x1400341f3  mov     esi, dword ptr [rsp+58h+arg_18]
0x1400341f7  cmp     eax, 0C0000023h
0x1400341fc  jz      short loc_14003420E
0x1400341fe  cmp     eax, 80000005h
0x140034203  jz      short loc_14003420E
0x140034205  xor     edi, edi
0x140034207  mov     ebx, 0C0000001h
0x14003420c  jmp     short loc_14003426A
0x14003420e  mov     rdx, rsi
0x140034211  mov     ecx, 100h
0x140034216  mov     r8d, 6C687442h
0x14003421c  call    cs:__imp_ExAllocatePool2
0x140034223  nop     dword ptr [rax+rax+00h]
0x140034228  mov     rdi, rax
0x14003422b  test    rax, rax
0x14003422e  jz      short loc_140034265
0x140034230  mov     r9d, esi
0x140034233  mov     [rsp+58h+var_38], 0; __int64
0x14003423c  mov     r8, rax; void *
0x14003423f  lea     rdx, [rsp+58h+DestinationString]; ValueName
0x140034244  mov     rcx, rbx; KeyHandle
0x140034247  call    BthQueryKeyValueEx
0x14003424c  mov     ebx, eax
0x14003424e  test    eax, eax
0x140034250  jns     short loc_14003426A
0x140034252  xor     edx, edx; Tag
0x140034254  mov     rcx, rdi; P
0x140034257  call    cs:__imp_ExFreePoolWithTag
0x14003425e  nop     dword ptr [rax+rax+00h]
0x140034263  jmp     short loc_140034270
0x140034265  mov     ebx, 0C000009Ah
0x14003426a  mov     [r14], rdi
0x14003426d  mov     [r15], esi
0x140034270  mov     eax, ebx
0x140034272  mov     rbx, [rsp+58h+arg_0]
0x140034277  mov     rsi, [rsp+58h+arg_8]
0x14003427c  add     rsp, 40h
0x140034280  pop     r15
0x140034282  pop     r14
0x140034284  pop     rdi
0x140034285  retn
```
