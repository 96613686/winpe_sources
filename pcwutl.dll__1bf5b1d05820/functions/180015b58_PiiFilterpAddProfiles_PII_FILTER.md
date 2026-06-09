# PiiFilterpAddProfiles(_PII_FILTER *)

- ea: `0x180015b58`
- end: `0x180015de0`
- name: `?PiiFilterpAddProfiles@@YAJPEAU_PII_FILTER@@@Z`
- size: `648`
- prototype: `__int64 __fastcall(struct _PII_FILTER *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008948`

## callees

- `0x180002664`
- `0x180002694`
- `0x18000e71c`
- `0x18000ec80`
- `0x18000ed18`
- `0x1800157f0`
- `0x180015ab4`
- `0x180015b58`
- `0x1800191a2`

## import_xrefs

- `msvcrt!_wcslwr` at `0x180015cee`
- `msvcrt!_wcslwr` at `0x180015cee`
- `ntdll!ZwClose` at `0x180015c0b`
- `ntdll!ZwClose` at `0x180015db1`
- `ntdll!ZwClose` at `0x180015dc0`
- `ntdll!ZwClose` at `0x180015c0b`
- `ntdll!ZwClose` at `0x180015db1`
- `ntdll!ZwClose` at `0x180015dc0`
- `ntdll!ZwEnumerateKey` at `0x180015c76`
- `ntdll!ZwEnumerateKey` at `0x180015c76`
- `ntdll!RtlFreeHeap` at `0x180015c2c`
- `ntdll!RtlFreeHeap` at `0x180015d68`
- `ntdll!RtlFreeHeap` at `0x180015d85`
- `ntdll!RtlFreeHeap` at `0x180015da2`
- `ntdll!RtlFreeHeap` at `0x180015c2c`
- `ntdll!RtlFreeHeap` at `0x180015d68`
- `ntdll!RtlFreeHeap` at `0x180015d85`
- `ntdll!RtlFreeHeap` at `0x180015da2`
- `ntdll!RtlAllocateHeap` at `0x180015ba0`
- `ntdll!RtlAllocateHeap` at `0x180015bca`
- `ntdll!RtlAllocateHeap` at `0x180015ba0`
- `ntdll!RtlAllocateHeap` at `0x180015bca`

## string_xrefs

- `0x180015be5`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`
- `0x180015cd3`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall PiiFilterpAddProfiles(struct _PII_FILTER *this)
{
  wchar_t *v2; // rdi
  WCHAR *Heap; // rsi
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
  Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x218u);
  if ( Heap )
  {
    v5 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x218u);
    if ( v5 )
    {
      v4 = AslRegistryOpenKey(
             &KeyHandle,
             L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
             8u);
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
            while ( wcsicmp_0(Heap + 8, off_18001BC50[v8]) )
            {
              if ( (unsigned int)++v8 >= 3 )
              {
                if ( AslRegistryOpenSubKey(&Handle, KeyHandle, Heap + 8) >= 0 )
                {
                  v9 = AslRegistryGetString(&String, Handle, L"ProfileImagePath");
                  v2 = String;
                  if ( v9 >= 0 )
                  {
                    _wcslwr(String);
                    v4 = PiiFilterpAddItemSorted(this, v2, L"%USERPROFILE%");
                    if ( v4 < 0 )
                      goto LABEL_24;
                    v10 = wcsrchr_0(v2, 0x5Cu);
                    if ( v10 )
                    {
                      if ( v10[1] )
                      {
                        v4 = RtlNameValueArray::Insert(
                               (struct _PII_FILTER *)((char *)this + 48),
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
0x180015b58  mov     [rsp-38h+arg_0], rbx
0x180015b5d  push    rbp
0x180015b5e  push    rsi
0x180015b5f  push    rdi
0x180015b60  push    r12
0x180015b62  push    r13
0x180015b64  push    r14
0x180015b66  push    r15
0x180015b68  mov     rbp, rsp
0x180015b6b  sub     rsp, 40h
0x180015b6f  xor     r15d, r15d
0x180015b72  mov     r13, rcx
0x180015b75  mov     [rbp+arg_8], r15d
0x180015b79  mov     r14d, 218h
0x180015b7f  mov     [rbp+Handle], r15
0x180015b83  mov     r8d, r14d; Size
0x180015b86  mov     [rbp+KeyHandle], r15
0x180015b8a  mov     edi, r15d
0x180015b8d  mov     rcx, gs:60h
0x180015b96  lea     ebx, [r15+8]
0x180015b9a  mov     edx, ebx; Flags
0x180015b9c  mov     rcx, [rcx+30h]; HeapHandle
0x180015ba0  call    cs:__imp_RtlAllocateHeap
0x180015ba6  mov     rsi, rax
0x180015ba9  test    rax, rax
0x180015bac  jnz     short loc_180015BB8
0x180015bae  mov     ebx, 0C0000017h
0x180015bb3  jmp     loc_180015D8B
0x180015bb8  mov     rcx, gs:60h
0x180015bc1  mov     r8, r14; Size
0x180015bc4  mov     edx, ebx; Flags
0x180015bc6  mov     rcx, [rcx+30h]; HeapHandle
0x180015bca  call    cs:__imp_RtlAllocateHeap
0x180015bd0  mov     r14, rax
0x180015bd3  test    rax, rax
0x180015bd6  jnz     short loc_180015BE2
0x180015bd8  mov     ebx, 0C0000017h
0x180015bdd  jmp     loc_180015D56
0x180015be2  mov     r8d, ebx
0x180015be5  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x180015bec  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x180015bf0  call    AslRegistryOpenKey
0x180015bf5  mov     ebx, eax
0x180015bf7  test    eax, eax
0x180015bf9  js      loc_180015D56
0x180015bff  mov     r12d, r15d
0x180015c02  mov     rcx, [rbp+Handle]; Handle
0x180015c06  test    rcx, rcx
0x180015c09  jz      short loc_180015C15
0x180015c0b  call    cs:__imp_ZwClose
0x180015c11  mov     [rbp+Handle], r15
0x180015c15  test    rdi, rdi
0x180015c18  jz      short loc_180015C32
0x180015c1a  mov     rcx, gs:60h
0x180015c23  mov     r8, rdi; P
0x180015c26  xor     edx, edx; Flags
0x180015c28  mov     rcx, [rcx+30h]; HeapHandle
0x180015c2c  call    cs:__imp_RtlFreeHeap
0x180015c32  mov     ebx, 218h
0x180015c37  mov     [rbp+String], r15
0x180015c3b  mov     r8d, ebx; Size
0x180015c3e  xor     edx, edx; Val
0x180015c40  mov     rcx, r14; void *
0x180015c43  mov     rdi, r15
0x180015c46  call    memset_0
0x180015c4b  mov     r8d, ebx; Size
0x180015c4e  xor     edx, edx; Val
0x180015c50  mov     rcx, rsi; void *
0x180015c53  call    memset_0
0x180015c58  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180015c5c  lea     rax, [rbp+arg_8]
0x180015c60  mov     [rsp+40h+ResultLength], rax; ResultLength
0x180015c65  mov     r9, rsi; KeyInformation
0x180015c68  xor     r8d, r8d; KeyInformationClass
0x180015c6b  mov     [rsp+40h+Length], 217h; Length
0x180015c73  mov     edx, r12d; Index
0x180015c76  call    cs:__imp_ZwEnumerateKey
0x180015c7c  cmp     eax, 8000001Ah
0x180015c81  jz      loc_180015D53
0x180015c87  test    eax, eax
0x180015c89  js      loc_180015D4B
0x180015c8f  mov     ebx, r15d
0x180015c92  lea     rax, off_18001BC50; "s-1-5-18"
0x180015c99  mov     edx, ebx
0x180015c9b  lea     rcx, [rsi+10h]; String1
0x180015c9f  mov     rdx, [rax+rdx*8]; String2
0x180015ca3  call    _wcsicmp_0
0x180015ca8  test    eax, eax
0x180015caa  jz      loc_180015D48
0x180015cb0  inc     ebx
0x180015cb2  cmp     ebx, 3
0x180015cb5  jb      short loc_180015C92
0x180015cb7  mov     rdx, [rbp+KeyHandle]
0x180015cbb  lea     r8, [rsi+10h]
0x180015cbf  lea     rcx, [rbp+Handle]; KeyHandle
0x180015cc3  call    AslRegistryOpenSubKey
0x180015cc8  xor     r15d, r15d
0x180015ccb  test    eax, eax
0x180015ccd  js      short loc_180015D4B
0x180015ccf  mov     rdx, [rbp+Handle]
0x180015cd3  lea     r8, aProfileimagepa; "ProfileImagePath"
0x180015cda  lea     rcx, [rbp+String]
0x180015cde  call    AslRegistryGetString
0x180015ce3  mov     rdi, [rbp+String]
0x180015ce7  test    eax, eax
0x180015ce9  js      short loc_180015D4B
0x180015ceb  mov     rcx, rdi; String
0x180015cee  call    cs:__imp__wcslwr
0x180015cf4  lea     r8, aUserprofile; "%USERPROFILE%"
0x180015cfb  mov     rdx, rdi; unsigned __int16 *
0x180015cfe  mov     rcx, r13; this
0x180015d01  call    ?PiiFilterpAddItemSorted@@YAJPEAU_PII_FILTER@@PEBG1@Z; PiiFilterpAddItemSorted(_PII_FILTER *,ushort const *,ushort const *)
0x180015d06  mov     ebx, eax
0x180015d08  test    eax, eax
0x180015d0a  js      short loc_180015D56
0x180015d0c  lea     edx, [r15+5Ch]; Ch
0x180015d10  mov     rcx, rdi; Str
0x180015d13  call    wcsrchr_0
0x180015d18  test    rax, rax
0x180015d1b  jz      short loc_180015D4B
0x180015d1d  lea     r8, [rax+2]; unsigned __int16 *
0x180015d21  cmp     [r8], r15w
0x180015d25  jz      short loc_180015D4B
0x180015d27  lea     rcx, [r13+30h]; this
0x180015d2b  mov     rax, [rcx+10h]
0x180015d2f  lea     r9, aUsername; "%USERNAME%"
0x180015d36  mov     qword ptr [rsp+40h+Length], rax; unsigned __int64
0x180015d3b  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x180015d40  mov     ebx, eax
0x180015d42  test    eax, eax
0x180015d44  js      short loc_180015D56
0x180015d46  jmp     short loc_180015D4B
0x180015d48  xor     r15d, r15d
0x180015d4b  inc     r12d
0x180015d4e  jmp     loc_180015C02
0x180015d53  mov     ebx, r15d
0x180015d56  mov     rcx, gs:60h
0x180015d5f  mov     r8, rsi; P
0x180015d62  xor     edx, edx; Flags
0x180015d64  mov     rcx, [rcx+30h]; HeapHandle
0x180015d68  call    cs:__imp_RtlFreeHeap
0x180015d6e  test    r14, r14
0x180015d71  jz      short loc_180015D8B
0x180015d73  mov     rcx, gs:60h
0x180015d7c  mov     r8, r14; P
0x180015d7f  xor     edx, edx; Flags
0x180015d81  mov     rcx, [rcx+30h]; HeapHandle
0x180015d85  call    cs:__imp_RtlFreeHeap
0x180015d8b  test    rdi, rdi
0x180015d8e  jz      short loc_180015DA8
0x180015d90  mov     rcx, gs:60h
0x180015d99  mov     r8, rdi; P
0x180015d9c  xor     edx, edx; Flags
0x180015d9e  mov     rcx, [rcx+30h]; HeapHandle
0x180015da2  call    cs:__imp_RtlFreeHeap
0x180015da8  mov     rcx, [rbp+KeyHandle]; Handle
0x180015dac  test    rcx, rcx
0x180015daf  jz      short loc_180015DB7
0x180015db1  call    cs:__imp_ZwClose
0x180015db7  mov     rcx, [rbp+Handle]; Handle
0x180015dbb  test    rcx, rcx
0x180015dbe  jz      short loc_180015DC6
0x180015dc0  call    cs:__imp_ZwClose
0x180015dc6  mov     eax, ebx
0x180015dc8  mov     rbx, [rsp+40h+arg_0]
0x180015dd0  add     rsp, 40h
0x180015dd4  pop     r15
0x180015dd6  pop     r14
0x180015dd8  pop     r13
0x180015dda  pop     r12
0x180015ddc  pop     rdi
0x180015ddd  pop     rsi
0x180015dde  pop     rbp
0x180015ddf  retn
```
