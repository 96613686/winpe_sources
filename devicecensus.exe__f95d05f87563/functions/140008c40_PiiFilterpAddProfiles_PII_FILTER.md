# PiiFilterpAddProfiles(_PII_FILTER *)

- ea: `0x140008c40`
- end: `0x140008ec9`
- name: `?PiiFilterpAddProfiles@@YAJPEAU_PII_FILTER@@@Z`
- size: `649`
- prototype: `__int64 __fastcall(struct _PII_FILTER *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140005b3c`

## callees

- `0x140001e94`
- `0x14000233f`
- `0x140007448`
- `0x1400079ac`
- `0x140007a44`
- `0x1400088d4`
- `0x140008b9c`
- `0x140008c40`

## import_xrefs

- `msvcrt!wcsrchr` at `0x140008dfb`
- `msvcrt!wcsrchr` at `0x140008dfb`
- `msvcrt!_wcslwr` at `0x140008dd6`
- `msvcrt!_wcslwr` at `0x140008dd6`
- `ntdll!ZwEnumerateKey` at `0x140008d5e`
- `ntdll!ZwEnumerateKey` at `0x140008d5e`
- `ntdll!ZwClose` at `0x140008cf3`
- `ntdll!ZwClose` at `0x140008e9a`
- `ntdll!ZwClose` at `0x140008ea9`
- `ntdll!ZwClose` at `0x140008cf3`
- `ntdll!ZwClose` at `0x140008e9a`
- `ntdll!ZwClose` at `0x140008ea9`
- `ntdll!RtlFreeHeap` at `0x140008d14`
- `ntdll!RtlFreeHeap` at `0x140008e51`
- `ntdll!RtlFreeHeap` at `0x140008e6e`
- `ntdll!RtlFreeHeap` at `0x140008e8b`
- `ntdll!RtlFreeHeap` at `0x140008d14`
- `ntdll!RtlFreeHeap` at `0x140008e51`
- `ntdll!RtlFreeHeap` at `0x140008e6e`
- `ntdll!RtlFreeHeap` at `0x140008e8b`
- `ntdll!RtlAllocateHeap` at `0x140008c88`
- `ntdll!RtlAllocateHeap` at `0x140008cb2`
- `ntdll!RtlAllocateHeap` at `0x140008c88`
- `ntdll!RtlAllocateHeap` at `0x140008cb2`

## string_xrefs

- `0x140008ccd`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`
- `0x140008dbb`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall PiiFilterpAddProfiles(struct _PII_FILTER *this)
{
  wchar_t *v2; // rdi
  wchar_t *Heap; // rsi
  int v4; // ebx
  PVOID v5; // r14
  ULONG i; // r12d
  NTSTATUS v7; // eax
  int v8; // ebx
  int v9; // eax
  wchar_t *v10; // rax
  const unsigned __int16 *v11; // rdx
  wchar_t *String; // [rsp+30h] [rbp-10h] BYREF
  ULONG ResultLength; // [rsp+88h] [rbp+48h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp+50h] BYREF
  HANDLE KeyHandle; // [rsp+98h] [rbp+58h] BYREF

  ResultLength = 0;
  Handle = 0;
  KeyHandle = 0;
  v2 = 0;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x218u);
  if ( Heap )
  {
    v5 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x218u);
    if ( v5 )
    {
      v4 = AslRegistryOpenKey(&KeyHandle);
      if ( v4 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          if ( Handle )
          {
            ZwClose(Handle);
            Handle = 0;
          }
          if ( v2 )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
          String = 0;
          v2 = 0;
          memset_0(v5, 0, 0x218u);
          memset_0(Heap, 0, 0x218u);
          v7 = ZwEnumerateKey(KeyHandle, i, KeyBasicInformation, Heap, 0x217u, &ResultLength);
          if ( v7 == -2147483622 )
            break;
          if ( v7 >= 0 )
          {
            v8 = 0;
            while ( wcsicmp_0(Heap + 8, off_140013B10[v8]) )
            {
              if ( (unsigned int)++v8 >= 3 )
              {
                if ( (int)AslRegistryOpenSubKey(&Handle) >= 0 )
                {
                  v9 = AslRegistryGetString(&String, Handle, L"ProfileImagePath");
                  v2 = String;
                  if ( v9 >= 0 )
                  {
                    _wcslwr(String);
                    v4 = PiiFilterpAddItemSorted(this, v2, L"%USERPROFILE%");
                    if ( v4 < 0 )
                      goto LABEL_24;
                    v10 = wcsrchr(v2, 0x5Cu);
                    if ( v10 )
                    {
                      if ( v10[1] )
                      {
                        v4 = RtlNameValueArray::Insert(
                               (PVOID *)this + 6,
                               v11,
                               v10 + 1,
                               L"%USERNAME%",
                               *((_QWORD *)this + 8));
                        if ( v4 < 0 )
                          goto LABEL_24;
                      }
                    }
                  }
                }
                break;
              }
            }
          }
        }
        v4 = 0;
      }
    }
    else
    {
      v4 = -1073741801;
    }
LABEL_24:
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
    if ( v5 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  }
  else
  {
    v4 = -1073741801;
  }
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140008c40  mov     [rsp-38h+arg_0], rbx
0x140008c45  push    rbp
0x140008c46  push    rsi
0x140008c47  push    rdi
0x140008c48  push    r12
0x140008c4a  push    r13
0x140008c4c  push    r14
0x140008c4e  push    r15
0x140008c50  mov     rbp, rsp
0x140008c53  sub     rsp, 40h
0x140008c57  xor     r15d, r15d
0x140008c5a  mov     r13, rcx
0x140008c5d  mov     [rbp+arg_8], r15d
0x140008c61  mov     r14d, 218h
0x140008c67  mov     [rbp+Handle], r15
0x140008c6b  mov     r8d, r14d; Size
0x140008c6e  mov     [rbp+KeyHandle], r15
0x140008c72  mov     edi, r15d
0x140008c75  mov     rcx, gs:60h
0x140008c7e  lea     ebx, [r15+8]
0x140008c82  mov     edx, ebx; Flags
0x140008c84  mov     rcx, [rcx+30h]; HeapHandle
0x140008c88  call    cs:__imp_RtlAllocateHeap
0x140008c8e  mov     rsi, rax
0x140008c91  test    rax, rax
0x140008c94  jnz     short loc_140008CA0
0x140008c96  mov     ebx, 0C0000017h
0x140008c9b  jmp     loc_140008E74
0x140008ca0  mov     rcx, gs:60h
0x140008ca9  mov     r8, r14; Size
0x140008cac  mov     edx, ebx; Flags
0x140008cae  mov     rcx, [rcx+30h]; HeapHandle
0x140008cb2  call    cs:__imp_RtlAllocateHeap
0x140008cb8  mov     r14, rax
0x140008cbb  test    rax, rax
0x140008cbe  jnz     short loc_140008CCA
0x140008cc0  mov     ebx, 0C0000017h
0x140008cc5  jmp     loc_140008E3F
0x140008cca  mov     r8d, ebx
0x140008ccd  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x140008cd4  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140008cd8  call    AslRegistryOpenKey
0x140008cdd  mov     ebx, eax
0x140008cdf  test    eax, eax
0x140008ce1  js      loc_140008E3F
0x140008ce7  mov     r12d, r15d
0x140008cea  mov     rcx, [rbp+Handle]; Handle
0x140008cee  test    rcx, rcx
0x140008cf1  jz      short loc_140008CFD
0x140008cf3  call    cs:__imp_ZwClose
0x140008cf9  mov     [rbp+Handle], r15
0x140008cfd  test    rdi, rdi
0x140008d00  jz      short loc_140008D1A
0x140008d02  mov     rcx, gs:60h
0x140008d0b  mov     r8, rdi; P
0x140008d0e  xor     edx, edx; Flags
0x140008d10  mov     rcx, [rcx+30h]; HeapHandle
0x140008d14  call    cs:__imp_RtlFreeHeap
0x140008d1a  mov     ebx, 218h
0x140008d1f  mov     [rbp+String], r15
0x140008d23  mov     r8d, ebx; Size
0x140008d26  xor     edx, edx; Val
0x140008d28  mov     rcx, r14; void *
0x140008d2b  mov     rdi, r15
0x140008d2e  call    memset_0
0x140008d33  mov     r8d, ebx; Size
0x140008d36  xor     edx, edx; Val
0x140008d38  mov     rcx, rsi; void *
0x140008d3b  call    memset_0
0x140008d40  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140008d44  lea     rax, [rbp+arg_8]
0x140008d48  mov     [rsp+40h+ResultLength], rax; ResultLength
0x140008d4d  mov     r9, rsi; KeyInformation
0x140008d50  xor     r8d, r8d; KeyInformationClass
0x140008d53  mov     [rsp+40h+Length], 217h; Length
0x140008d5b  mov     edx, r12d; Index
0x140008d5e  call    cs:__imp_ZwEnumerateKey
0x140008d64  cmp     eax, 8000001Ah
0x140008d69  jz      loc_140008E3C
0x140008d6f  test    eax, eax
0x140008d71  js      loc_140008E34
0x140008d77  mov     ebx, r15d
0x140008d7a  lea     rax, off_140013B10; "s-1-5-18"
0x140008d81  mov     edx, ebx
0x140008d83  lea     rcx, [rsi+10h]; String1
0x140008d87  mov     rdx, [rax+rdx*8]; String2
0x140008d8b  call    _wcsicmp_0
0x140008d90  test    eax, eax
0x140008d92  jz      loc_140008E31
0x140008d98  inc     ebx
0x140008d9a  cmp     ebx, 3
0x140008d9d  jb      short loc_140008D7A
0x140008d9f  mov     rdx, [rbp+KeyHandle]
0x140008da3  lea     r8, [rsi+10h]
0x140008da7  lea     rcx, [rbp+Handle]; KeyHandle
0x140008dab  call    AslRegistryOpenSubKey
0x140008db0  xor     r15d, r15d
0x140008db3  test    eax, eax
0x140008db5  js      short loc_140008E34
0x140008db7  mov     rdx, [rbp+Handle]
0x140008dbb  lea     r8, aProfileimagepa; "ProfileImagePath"
0x140008dc2  lea     rcx, [rbp+String]
0x140008dc6  call    AslRegistryGetString
0x140008dcb  mov     rdi, [rbp+String]
0x140008dcf  test    eax, eax
0x140008dd1  js      short loc_140008E34
0x140008dd3  mov     rcx, rdi; String
0x140008dd6  call    cs:__imp__wcslwr
0x140008ddc  lea     r8, aUserprofile; "%USERPROFILE%"
0x140008de3  mov     rdx, rdi; unsigned __int16 *
0x140008de6  mov     rcx, r13; this
0x140008de9  call    ?PiiFilterpAddItemSorted@@YAJPEAU_PII_FILTER@@PEBG1@Z; PiiFilterpAddItemSorted(_PII_FILTER *,ushort const *,ushort const *)
0x140008dee  mov     ebx, eax
0x140008df0  test    eax, eax
0x140008df2  js      short loc_140008E3F
0x140008df4  lea     edx, [r15+5Ch]; Ch
0x140008df8  mov     rcx, rdi; Str
0x140008dfb  call    cs:__imp_wcsrchr
0x140008e01  test    rax, rax
0x140008e04  jz      short loc_140008E34
0x140008e06  lea     r8, [rax+2]; unsigned __int16 *
0x140008e0a  cmp     [r8], r15w
0x140008e0e  jz      short loc_140008E34
0x140008e10  lea     rcx, [r13+30h]; this
0x140008e14  mov     rax, [rcx+10h]
0x140008e18  lea     r9, aUsername; "%USERNAME%"
0x140008e1f  mov     qword ptr [rsp+40h+Length], rax; unsigned __int64
0x140008e24  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x140008e29  mov     ebx, eax
0x140008e2b  test    eax, eax
0x140008e2d  js      short loc_140008E3F
0x140008e2f  jmp     short loc_140008E34
0x140008e31  xor     r15d, r15d
0x140008e34  inc     r12d
0x140008e37  jmp     loc_140008CEA
0x140008e3c  mov     ebx, r15d
0x140008e3f  mov     rcx, gs:60h
0x140008e48  mov     r8, rsi; P
0x140008e4b  xor     edx, edx; Flags
0x140008e4d  mov     rcx, [rcx+30h]; HeapHandle
0x140008e51  call    cs:__imp_RtlFreeHeap
0x140008e57  test    r14, r14
0x140008e5a  jz      short loc_140008E74
0x140008e5c  mov     rcx, gs:60h
0x140008e65  mov     r8, r14; P
0x140008e68  xor     edx, edx; Flags
0x140008e6a  mov     rcx, [rcx+30h]; HeapHandle
0x140008e6e  call    cs:__imp_RtlFreeHeap
0x140008e74  test    rdi, rdi
0x140008e77  jz      short loc_140008E91
0x140008e79  mov     rcx, gs:60h
0x140008e82  mov     r8, rdi; P
0x140008e85  xor     edx, edx; Flags
0x140008e87  mov     rcx, [rcx+30h]; HeapHandle
0x140008e8b  call    cs:__imp_RtlFreeHeap
0x140008e91  mov     rcx, [rbp+KeyHandle]; Handle
0x140008e95  test    rcx, rcx
0x140008e98  jz      short loc_140008EA0
0x140008e9a  call    cs:__imp_ZwClose
0x140008ea0  mov     rcx, [rbp+Handle]; Handle
0x140008ea4  test    rcx, rcx
0x140008ea7  jz      short loc_140008EAF
0x140008ea9  call    cs:__imp_ZwClose
0x140008eaf  mov     eax, ebx
0x140008eb1  mov     rbx, [rsp+40h+arg_0]
0x140008eb9  add     rsp, 40h
0x140008ebd  pop     r15
0x140008ebf  pop     r14
0x140008ec1  pop     r13
0x140008ec3  pop     r12
0x140008ec5  pop     rdi
0x140008ec6  pop     rsi
0x140008ec7  pop     rbp
0x140008ec8  retn
```
