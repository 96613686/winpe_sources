# FveRegistryGetValue

- ea: `0x180045108`
- end: `0x18004528a`
- name: `FveRegistryGetValue`
- size: `386`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d830`
- `0x18011d388`

## callees

- `0x18002fd50`
- `0x180030060`
- `0x180045108`
- `0x180060196`

## import_xrefs

- `ntdll!NtClose` at `0x18004517f`
- `ntdll!NtClose` at `0x18004517f`
- `ntdll!NtQueryValueKey` at `0x1800451c6`
- `ntdll!NtQueryValueKey` at `0x180045221`
- `ntdll!NtQueryValueKey` at `0x1800451c6`
- `ntdll!NtQueryValueKey` at `0x180045221`
- `ntdll!NtOpenKey` at `0x180045164`
- `ntdll!NtOpenKey` at `0x180045164`

## pseudocode

```c
__int64 __fastcall FveRegistryGetValue(
        struct _UNICODE_STRING *a1,
        struct _UNICODE_STRING *a2,
        int a3,
        void *a4,
        unsigned int *a5)
{
  NTSTATUS v8; // ebx
  ULONG v10; // esi
  int v11; // eax
  _DWORD *v12; // rdi
  unsigned int v13; // eax
  void *KeyHandle; // [rsp+30h] [rbp-40h] BYREF
  PVOID KeyValueInformation; // [rsp+38h] [rbp-38h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+30h] BYREF

  ObjectAttributes.ObjectName = a1;
  ResultLength = 0;
  KeyHandle = 0;
  KeyValueInformation = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v8 >= 0 )
  {
    v8 = NtQueryValueKey(KeyHandle, a2, KeyValuePartialInformation, 0, 0, &ResultLength);
    if ( (int)(v8 + 0x80000000) < 0 || v8 == -1073741789 )
    {
      v10 = 0;
      v11 = FveLibAllocWithTagZero(ResultLength);
      v12 = KeyValueInformation;
      v8 = v11;
      if ( v11 >= 0 )
      {
        v10 = ResultLength;
        v8 = NtQueryValueKey(
               KeyHandle,
               a2,
               KeyValuePartialInformation,
               KeyValueInformation,
               ResultLength,
               &ResultLength);
        if ( v8 >= 0 )
        {
          if ( v12[1] == a3 )
          {
            if ( a4 && (v13 = v12[2], *a5 >= v13) )
            {
              *a5 = v13;
              memcpy_0(a4, v12 + 3, v13);
              v8 = 0;
            }
            else
            {
              v8 = -1073741789;
              *a5 = v12[2];
            }
          }
          else
          {
            v8 = -1073741438;
          }
        }
      }
      if ( v12 )
        FveLibFreeWithTag(v12, v10, 0);
    }
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180045108  mov     [rsp-28h+arg_8], rbx
0x18004510d  mov     [rsp-28h+arg_10], rsi
0x180045112  push    rbp
0x180045113  push    rdi
0x180045114  push    r12
0x180045116  push    r14
0x180045118  push    r15
0x18004511a  mov     rbp, rsp
0x18004511d  sub     rsp, 70h
0x180045121  xor     eax, eax
0x180045123  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x180045127  mov     r15d, r8d
0x18004512a  mov     [rbp+arg_0], eax
0x18004512d  mov     r12, rdx
0x180045130  mov     [rbp+KeyHandle], rax
0x180045134  xorps   xmm0, xmm0
0x180045137  mov     [rbp+KeyValueInformation], rax
0x18004513b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18004513f  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180045143  mov     edx, 20019h; DesiredAccess
0x180045148  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180045150  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180045154  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18004515c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180045161  mov     r14, r9
0x180045164  call    cs:__imp_NtOpenKey
0x18004516b  nop     dword ptr [rax+rax+00h]
0x180045170  mov     ebx, eax
0x180045172  test    eax, eax
0x180045174  jns     short loc_1800451A7
0x180045176  mov     rcx, [rbp+KeyHandle]; Handle
0x18004517a  test    rcx, rcx
0x18004517d  jz      short loc_18004518B
0x18004517f  call    cs:__imp_NtClose
0x180045186  nop     dword ptr [rax+rax+00h]
0x18004518b  lea     r11, [rsp+70h+var_s0]
0x180045190  mov     eax, ebx
0x180045192  mov     rbx, [r11+38h]
0x180045196  mov     rsi, [r11+40h]
0x18004519a  mov     rsp, r11
0x18004519d  pop     r15
0x18004519f  pop     r14
0x1800451a1  pop     r12
0x1800451a3  pop     rdi
0x1800451a4  pop     rbp
0x1800451a5  retn
0x1800451a7  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800451ab  lea     rax, [rbp+arg_0]
0x1800451af  xor     r9d, r9d; KeyValueInformation
0x1800451b2  mov     [rsp+70h+ResultLength], rax; ResultLength
0x1800451b7  mov     rdx, r12; ValueName
0x1800451ba  mov     [rsp+70h+Length], 0; Length
0x1800451c2  lea     r8d, [r9+2]; KeyValueInformationClass
0x1800451c6  call    cs:__imp_NtQueryValueKey
0x1800451cd  nop     dword ptr [rax+rax+00h]
0x1800451d2  mov     ecx, 80000000h
0x1800451d7  mov     ebx, eax
0x1800451d9  add     eax, ecx
0x1800451db  test    ecx, eax
0x1800451dd  jnz     short loc_1800451E7
0x1800451df  cmp     ebx, 0C0000023h
0x1800451e5  jnz     short loc_180045176
0x1800451e7  mov     ecx, [rbp+arg_0]; Size
0x1800451ea  lea     r8, [rbp+KeyValueInformation]
0x1800451ee  xor     edx, edx
0x1800451f0  xor     esi, esi
0x1800451f2  call    FveLibAllocWithTagZero
0x1800451f7  mov     rdi, [rbp+KeyValueInformation]
0x1800451fb  mov     ebx, eax
0x1800451fd  test    eax, eax
0x1800451ff  js      short loc_18004526F
0x180045201  mov     esi, [rbp+arg_0]
0x180045204  lea     rax, [rbp+arg_0]
0x180045208  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18004520c  mov     r9, rdi; KeyValueInformation
0x18004520f  mov     [rsp+70h+ResultLength], rax; ResultLength
0x180045214  mov     r8d, 2; KeyValueInformationClass
0x18004521a  mov     rdx, r12; ValueName
0x18004521d  mov     [rsp+70h+Length], esi; Length
0x180045221  call    cs:__imp_NtQueryValueKey
0x180045228  nop     dword ptr [rax+rax+00h]
0x18004522d  mov     ebx, eax
0x18004522f  test    eax, eax
0x180045231  js      short loc_18004526F
0x180045233  cmp     [rdi+4], r15d
0x180045237  jz      short loc_180045240
0x180045239  mov     ebx, 0C0000182h
0x18004523e  jmp     short loc_18004526F
0x180045240  mov     rcx, [rbp+arg_20]
0x180045244  test    r14, r14
0x180045247  jz      short loc_180045265
0x180045249  mov     eax, [rdi+8]
0x18004524c  cmp     [rcx], eax
0x18004524e  jb      short loc_180045265
0x180045250  mov     [rcx], eax
0x180045252  lea     rdx, [rdi+0Ch]; Src
0x180045256  mov     rcx, r14; void *
0x180045259  mov     r8d, eax; Size
0x18004525c  call    memcpy_0
0x180045261  xor     ebx, ebx
0x180045263  jmp     short loc_18004526F
0x180045265  mov     eax, [rdi+8]
0x180045268  mov     ebx, 0C0000023h
0x18004526d  mov     [rcx], eax
0x18004526f  test    rdi, rdi
0x180045272  jz      loc_180045176
0x180045278  mov     edx, esi
0x18004527a  xor     r8d, r8d
0x18004527d  mov     rcx, rdi
0x180045280  call    FveLibFreeWithTag
0x180045285  jmp     loc_180045176
```
