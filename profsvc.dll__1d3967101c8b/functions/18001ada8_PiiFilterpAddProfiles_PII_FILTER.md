# PiiFilterpAddProfiles(_PII_FILTER *)

- ea: `0x18001ada8`
- end: `0x18001b12a`
- name: `?PiiFilterpAddProfiles@@YAJPEAU_PII_FILTER@@@Z`
- size: `898`
- prototype: `__int64 __fastcall(struct _PII_FILTER *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001abb4`

## callees

- `0x18001a93c`
- `0x18001a9e0`
- `0x18001ada8`
- `0x18001b3f0`
- `0x18001ce60`
- `0x180035ea4`
- `0x18003b274`
- `0x18003b280`
- `0x18003b310`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001b05b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001b05b`
- `ntdll!RtlAllocateHeap` at `0x18001adef`
- `ntdll!RtlAllocateHeap` at `0x18001ae19`
- `ntdll!RtlAllocateHeap` at `0x18001adef`
- `ntdll!RtlAllocateHeap` at `0x18001ae19`
- `ntdll!RtlFreeHeap` at `0x18001ae7b`
- `ntdll!RtlFreeHeap` at `0x18001b0af`
- `ntdll!RtlFreeHeap` at `0x18001b0cc`
- `ntdll!RtlFreeHeap` at `0x18001b0e9`
- `ntdll!RtlFreeHeap` at `0x18001ae7b`
- `ntdll!RtlFreeHeap` at `0x18001b0af`
- `ntdll!RtlFreeHeap` at `0x18001b0cc`
- `ntdll!RtlFreeHeap` at `0x18001b0e9`
- `ntdll!ZwEnumerateKey` at `0x18001aec5`
- `ntdll!ZwEnumerateKey` at `0x18001aec5`
- `ntdll!ZwClose` at `0x18001ae5a`
- `ntdll!ZwClose` at `0x18001b0f8`
- `ntdll!ZwClose` at `0x18001b107`
- `ntdll!ZwClose` at `0x18001ae5a`
- `ntdll!ZwClose` at `0x18001b0f8`
- `ntdll!ZwClose` at `0x18001b107`
- `ntdll!ZwOpenKey` at `0x18001af8c`
- `ntdll!ZwOpenKey` at `0x18001af8c`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001af2c`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001af2c`

## string_xrefs

- `0x18001af9e`: `ProfileImagePath`
- `0x18001ae34`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`
- `0x18001af49`: `AslRegistryOpenSubKey`
- `0x18001af38`: `AslRegistryOpenSubKey passed bad Path [%x]`

## pseudocode

```c
__int64 __fastcall PiiFilterpAddProfiles(struct _PII_FILTER *this)
{
  wchar_t *v2; // rdi
  wchar_t *Heap; // r15
  int v4; // ebx
  PVOID v5; // r12
  ULONG i; // r13d
  NTSTATUS v7; // eax
  unsigned int j; // ebx
  HANDLE v9; // rbx
  NTSTATUS inited; // eax
  int v11; // eax
  unsigned __int64 v12; // rdx
  __int64 v13; // r11
  unsigned __int64 v14; // r9
  unsigned __int64 v15; // rcx
  unsigned int v16; // r10d
  __int64 *v17; // rax
  unsigned __int64 v18; // rcx
  __int64 v19; // rcx
  unsigned __int64 v20; // rax
  wchar_t *v21; // rax
  const unsigned __int16 *v22; // rdx
  wchar_t *String; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+C8h] [rbp+48h] BYREF
  HANDLE Handle; // [rsp+D0h] [rbp+50h] BYREF
  HANDLE KeyHandle; // [rsp+D8h] [rbp+58h] BYREF

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
            for ( j = 0; j < 3; ++j )
            {
              if ( !wcsicmp(Heap + 8, off_1800541B0[j]) )
                goto LABEL_37;
            }
            v9 = KeyHandle;
            Handle = 0;
            DestinationString = 0;
            memset(&ObjectAttributes, 0, 44);
            inited = RtlInitUnicodeStringEx(&DestinationString, Heap + 8);
            if ( inited >= 0 )
            {
              ObjectAttributes.Length = 48;
              ObjectAttributes.ObjectName = &DestinationString;
              ObjectAttributes.RootDirectory = v9;
              ObjectAttributes.Attributes = 64;
              *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
              if ( ZwOpenKey(&Handle, 0x20019u, &ObjectAttributes) >= 0 )
              {
                v11 = AslRegistryGetString(&String, Handle, L"ProfileImagePath");
                v2 = String;
                if ( v11 >= 0 )
                {
                  wcslwr(String);
                  v13 = -1;
                  v14 = -1;
                  do
                    ++v14;
                  while ( v2[v14] );
                  v15 = *((_QWORD *)this + 2);
                  v16 = 0;
                  if ( v15 )
                  {
                    v12 = 0;
                    do
                    {
                      v17 = 0;
                      if ( v12 < v15 )
                      {
                        v18 = *((_QWORD *)this + 1);
                        String = 0;
                        if ( (int)ULongLongMult(v18, v12, (unsigned __int64 *)&String) < 0
                          || (v17 = (__int64 *)((char *)String + *((_QWORD *)this + 5)),
                              (unsigned __int64)v17 < *((_QWORD *)this + 5)) )
                        {
                          v17 = 0;
                        }
                      }
                      v19 = *v17;
                      v20 = v13;
                      do
                        ++v20;
                      while ( *(_WORD *)(v19 + 2 * v20) );
                      if ( v14 > v20 )
                        break;
                      v15 = *((_QWORD *)this + 2);
                      v12 = ++v16;
                    }
                    while ( v16 < v15 );
                  }
                  v4 = RtlNameValueArray::Insert(this, (const unsigned __int16 *)v12, v2, L"%USERPROFILE%", v16);
                  if ( v4 < 0 )
                    goto LABEL_39;
                  v21 = wcsrchr(v2, 0x5Cu);
                  if ( v21 )
                  {
                    if ( v21[1] )
                    {
                      v4 = RtlNameValueArray::Insert(
                             (struct _PII_FILTER *)((char *)this + 48),
                             v22,
                             v21 + 1,
                             L"%USERNAME%",
                             *((_QWORD *)this + 8));
                      if ( v4 < 0 )
                        goto LABEL_39;
                    }
                  }
                }
              }
            }
            else
            {
              AslLogCallPrintf(1, "AslRegistryOpenSubKey", 958, "AslRegistryOpenSubKey passed bad Path [%x]", inited);
            }
          }
LABEL_37:
          ;
        }
        v4 = 0;
      }
    }
    else
    {
      v4 = -1073741801;
    }
LABEL_39:
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
0x18001ada8  mov     [rsp-38h+arg_0], rbx
0x18001adad  push    rbp
0x18001adae  push    rsi
0x18001adaf  push    rdi
0x18001adb0  push    r12
0x18001adb2  push    r13
0x18001adb4  push    r14
0x18001adb6  push    r15
0x18001adb8  mov     rbp, rsp
0x18001adbb  sub     rsp, 80h
0x18001adc2  xor     esi, esi
0x18001adc4  mov     r14, rcx
0x18001adc7  mov     [rbp+arg_8], esi
0x18001adca  mov     r12d, 218h
0x18001add0  mov     [rbp+Handle], rsi
0x18001add4  mov     r8d, r12d; Size
0x18001add7  mov     [rbp+KeyHandle], rsi
0x18001addb  mov     edi, esi
0x18001addd  mov     rcx, gs:60h
0x18001ade6  lea     ebx, [rsi+8]
0x18001ade9  mov     edx, ebx; Flags
0x18001adeb  mov     rcx, [rcx+30h]; HeapHandle
0x18001adef  call    cs:__imp_RtlAllocateHeap
0x18001adf5  mov     r15, rax
0x18001adf8  test    rax, rax
0x18001adfb  jnz     short loc_18001AE07
0x18001adfd  mov     ebx, 0C0000017h
0x18001ae02  jmp     loc_18001B0D2
0x18001ae07  mov     rcx, gs:60h
0x18001ae10  mov     r8, r12; Size
0x18001ae13  mov     edx, ebx; Flags
0x18001ae15  mov     rcx, [rcx+30h]; HeapHandle
0x18001ae19  call    cs:__imp_RtlAllocateHeap
0x18001ae1f  mov     r12, rax
0x18001ae22  test    rax, rax
0x18001ae25  jnz     short loc_18001AE31
0x18001ae27  mov     ebx, 0C0000017h
0x18001ae2c  jmp     loc_18001B09D
0x18001ae31  mov     r8d, ebx
0x18001ae34  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x18001ae3b  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18001ae3f  call    AslRegistryOpenKey
0x18001ae44  mov     ebx, eax
0x18001ae46  test    eax, eax
0x18001ae48  js      loc_18001B09D
0x18001ae4e  mov     r13d, esi
0x18001ae51  mov     rcx, [rbp+Handle]; Handle
0x18001ae55  test    rcx, rcx
0x18001ae58  jz      short loc_18001AE64
0x18001ae5a  call    cs:__imp_ZwClose
0x18001ae60  mov     [rbp+Handle], rsi
0x18001ae64  test    rdi, rdi
0x18001ae67  jz      short loc_18001AE81
0x18001ae69  mov     rcx, gs:60h
0x18001ae72  mov     r8, rdi; P
0x18001ae75  xor     edx, edx; Flags
0x18001ae77  mov     rcx, [rcx+30h]; HeapHandle
0x18001ae7b  call    cs:__imp_RtlFreeHeap
0x18001ae81  mov     ebx, 218h
0x18001ae86  mov     [rbp+String], rsi
0x18001ae8a  mov     r8d, ebx; Size
0x18001ae8d  xor     edx, edx; Val
0x18001ae8f  mov     rcx, r12; void *
0x18001ae92  mov     rdi, rsi
0x18001ae95  call    memset_0
0x18001ae9a  mov     r8d, ebx; Size
0x18001ae9d  xor     edx, edx; Val
0x18001ae9f  mov     rcx, r15; void *
0x18001aea2  call    memset_0
0x18001aea7  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18001aeab  lea     rax, [rbp+arg_8]
0x18001aeaf  mov     [rsp+80h+ResultLength], rax; ResultLength
0x18001aeb4  mov     r9, r15; KeyInformation
0x18001aeb7  xor     r8d, r8d; KeyInformationClass
0x18001aeba  mov     [rsp+80h+Length], 217h; Length
0x18001aec2  mov     edx, r13d; Index
0x18001aec5  call    cs:__imp_ZwEnumerateKey
0x18001aecb  cmp     eax, 8000001Ah
0x18001aed0  jz      loc_18001B09B
0x18001aed6  test    eax, eax
0x18001aed8  js      loc_18001B093
0x18001aede  mov     ebx, esi
0x18001aee0  cmp     ebx, 3
0x18001aee3  jnb     short loc_18001AF07
0x18001aee5  lea     rax, off_1800541B0; "s-1-5-18"
0x18001aeec  mov     edx, ebx
0x18001aeee  lea     rcx, [r15+10h]; String1
0x18001aef2  mov     rdx, [rax+rdx*8]; String2
0x18001aef6  call    _wcsicmp
0x18001aefb  test    eax, eax
0x18001aefd  jz      loc_18001B091
0x18001af03  inc     ebx
0x18001af05  jmp     short loc_18001AEE0
0x18001af07  mov     rbx, [rbp+KeyHandle]
0x18001af0b  lea     rdx, [r15+10h]; SourceString
0x18001af0f  xorps   xmm0, xmm0
0x18001af12  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001af16  xor     eax, eax
0x18001af18  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18001af1c  mov     [rbp+Handle], rax
0x18001af20  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18001af24  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001af28  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18001af2c  call    cs:__imp_RtlInitUnicodeStringEx
0x18001af32  xor     esi, esi
0x18001af34  test    eax, eax
0x18001af36  jns     short loc_18001AF5D
0x18001af38  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x18001af3f  mov     [rsp+80h+Length], eax
0x18001af43  mov     r8d, 3BEh
0x18001af49  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x18001af50  lea     ecx, [rsi+1]
0x18001af53  call    AslLogCallPrintf
0x18001af58  jmp     loc_18001B093
0x18001af5d  lea     rax, [rbp+DestinationString]
0x18001af61  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001af68  xorps   xmm0, xmm0
0x18001af6b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18001af6f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18001af73  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x18001af77  mov     edx, 20019h; DesiredAccess
0x18001af7c  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18001af83  lea     rcx, [rbp+Handle]; KeyHandle
0x18001af87  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001af8c  call    cs:__imp_ZwOpenKey
0x18001af92  test    eax, eax
0x18001af94  js      loc_18001B093
0x18001af9a  mov     rdx, [rbp+Handle]
0x18001af9e  lea     r8, aProfileimagepa; "ProfileImagePath"
0x18001afa5  lea     rcx, [rbp+String]
0x18001afa9  call    AslRegistryGetString
0x18001afae  mov     rdi, [rbp+String]
0x18001afb2  test    eax, eax
0x18001afb4  js      loc_18001B093
0x18001afba  mov     rcx, rdi; String
0x18001afbd  call    _wcslwr
0x18001afc2  or      r11, 0FFFFFFFFFFFFFFFFh
0x18001afc6  mov     r9, r11
0x18001afc9  inc     r9
0x18001afcc  cmp     [rdi+r9*2], si
0x18001afd1  jnz     short loc_18001AFC9
0x18001afd3  mov     rcx, [r14+10h]
0x18001afd7  mov     r10d, esi
0x18001afda  test    rcx, rcx
0x18001afdd  jz      short loc_18001B033
0x18001afdf  mov     rdx, rsi; unsigned __int64
0x18001afe2  mov     rax, rsi
0x18001afe5  cmp     rdx, rcx
0x18001afe8  jnb     short loc_18001B010
0x18001afea  mov     rcx, [r14+8]; unsigned __int64
0x18001afee  lea     r8, [rbp+String]; unsigned __int64 *
0x18001aff2  mov     [rbp+String], rsi
0x18001aff6  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001affb  test    eax, eax
0x18001affd  js      short loc_18001B00D
0x18001afff  mov     rax, [rbp+String]
0x18001b003  add     rax, [r14+28h]
0x18001b007  cmp     rax, [r14+28h]
0x18001b00b  jnb     short loc_18001B010
0x18001b00d  mov     rax, rsi
0x18001b010  mov     rcx, [rax]
0x18001b013  mov     rax, r11
0x18001b016  inc     rax
0x18001b019  cmp     [rcx+rax*2], si
0x18001b01d  jnz     short loc_18001B016
0x18001b01f  cmp     r9, rax
0x18001b022  ja      short loc_18001B033
0x18001b024  mov     rcx, [r14+10h]
0x18001b028  inc     r10d
0x18001b02b  mov     edx, r10d; unsigned __int16 *
0x18001b02e  cmp     rdx, rcx
0x18001b031  jb      short loc_18001AFE2
0x18001b033  mov     eax, r10d
0x18001b036  lea     r9, aUserprofile_0; "%USERPROFILE%"
0x18001b03d  mov     r8, rdi; unsigned __int16 *
0x18001b040  mov     qword ptr [rsp+80h+Length], rax; unsigned __int64
0x18001b045  mov     rcx, r14; this
0x18001b048  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x18001b04d  mov     ebx, eax
0x18001b04f  test    eax, eax
0x18001b051  js      short loc_18001B09D
0x18001b053  mov     edx, 5Ch ; '\'; Ch
0x18001b058  mov     rcx, rdi; Str
0x18001b05b  call    cs:__imp_wcsrchr
0x18001b061  test    rax, rax
0x18001b064  jz      short loc_18001B093
0x18001b066  lea     r8, [rax+2]; unsigned __int16 *
0x18001b06a  cmp     [r8], si
0x18001b06e  jz      short loc_18001B093
0x18001b070  lea     rcx, [r14+30h]; this
0x18001b074  mov     rax, [rcx+10h]
0x18001b078  lea     r9, aUsername; "%USERNAME%"
0x18001b07f  mov     qword ptr [rsp+80h+Length], rax; unsigned __int64
0x18001b084  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x18001b089  mov     ebx, eax
0x18001b08b  test    eax, eax
0x18001b08d  js      short loc_18001B09D
0x18001b08f  jmp     short loc_18001B093
0x18001b091  xor     esi, esi
0x18001b093  inc     r13d
0x18001b096  jmp     loc_18001AE51
0x18001b09b  mov     ebx, esi
0x18001b09d  mov     rcx, gs:60h
0x18001b0a6  mov     r8, r15; P
0x18001b0a9  xor     edx, edx; Flags
0x18001b0ab  mov     rcx, [rcx+30h]; HeapHandle
0x18001b0af  call    cs:__imp_RtlFreeHeap
0x18001b0b5  test    r12, r12
0x18001b0b8  jz      short loc_18001B0D2
0x18001b0ba  mov     rcx, gs:60h
0x18001b0c3  mov     r8, r12; P
0x18001b0c6  xor     edx, edx; Flags
0x18001b0c8  mov     rcx, [rcx+30h]; HeapHandle
0x18001b0cc  call    cs:__imp_RtlFreeHeap
0x18001b0d2  test    rdi, rdi
0x18001b0d5  jz      short loc_18001B0EF
0x18001b0d7  mov     rcx, gs:60h
0x18001b0e0  mov     r8, rdi; P
0x18001b0e3  xor     edx, edx; Flags
0x18001b0e5  mov     rcx, [rcx+30h]; HeapHandle
0x18001b0e9  call    cs:__imp_RtlFreeHeap
0x18001b0ef  mov     rcx, [rbp+KeyHandle]; Handle
0x18001b0f3  test    rcx, rcx
0x18001b0f6  jz      short loc_18001B0FE
0x18001b0f8  call    cs:__imp_ZwClose
0x18001b0fe  mov     rcx, [rbp+Handle]; Handle
0x18001b102  test    rcx, rcx
0x18001b105  jz      short loc_18001B10D
0x18001b107  call    cs:__imp_ZwClose
0x18001b10d  mov     eax, ebx
0x18001b10f  mov     rbx, [rsp+80h+arg_0]
0x18001b117  add     rsp, 80h
0x18001b11e  pop     r15
0x18001b120  pop     r14
0x18001b122  pop     r13
0x18001b124  pop     r12
0x18001b126  pop     rdi
0x18001b127  pop     rsi
0x18001b128  pop     rbp
0x18001b129  retn
```
