# PiiFilterpAddProfiles(_PII_FILTER *)

- ea: `0x18000adf8`
- end: `0x18000b060`
- name: `?PiiFilterpAddProfiles@@YAJPEAU_PII_FILTER@@@Z`
- size: `616`
- prototype: `__int64 __fastcall(struct _PII_FILTER *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003560`

## callees

- `0x180006880`
- `0x180006c80`
- `0x180008232`
- `0x18000823e`
- `0x180008262`
- `0x18000a5b8`
- `0x18000a67c`
- `0x18000aa1c`
- `0x18000ad40`
- `0x18000adf8`
- `0x18000bffe`

## import_xrefs

- `ntdll!ZwClose` at `0x18000aea4`
- `ntdll!ZwClose` at `0x18000b031`
- `ntdll!ZwClose` at `0x18000b040`
- `ntdll!ZwClose` at `0x18000aea4`
- `ntdll!ZwClose` at `0x18000b031`
- `ntdll!ZwClose` at `0x18000b040`
- `ntdll!ZwEnumerateKey` at `0x18000af07`
- `ntdll!ZwEnumerateKey` at `0x18000af07`
- `ntdll!RtlAllocateHeap` at `0x18000ae40`
- `ntdll!RtlAllocateHeap` at `0x18000ae6d`
- `ntdll!RtlAllocateHeap` at `0x18000ae40`
- `ntdll!RtlAllocateHeap` at `0x18000ae6d`

## string_xrefs

- `0x18000ae7e`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`
- `0x18000af66`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall PiiFilterpAddProfiles(struct _PII_FILTER *this)
{
  wchar_t *v2; // rdi
  wchar_t *Heap; // r14
  PVOID v4; // rsi
  int v5; // ebx
  ULONG i; // r15d
  NTSTATUS v7; // eax
  unsigned int j; // ebx
  NTSTATUS v9; // eax
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
  if ( !Heap )
  {
    v4 = 0;
LABEL_3:
    v5 = -1073741801;
    goto LABEL_23;
  }
  v4 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x218u);
  if ( !v4 )
    goto LABEL_3;
  v5 = AslRegistryOpenKey(
         &KeyHandle,
         L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
         8u);
  if ( v5 >= 0 )
  {
    for ( i = 0; ; ++i )
    {
      if ( Handle )
      {
        ZwClose(Handle);
        Handle = 0;
      }
      AslFree(NtCurrentPeb()->ProcessHeap, v2);
      String = 0;
      v2 = 0;
      memset_0(v4, 0, 0x218u);
      memset_0(Heap, 0, 0x218u);
      v7 = ZwEnumerateKey(KeyHandle, i, KeyBasicInformation, Heap, 0x217u, &ResultLength);
      if ( v7 == -2147483622 )
        break;
      if ( v7 >= 0 )
      {
        for ( j = 0; j < 3; ++j )
        {
          if ( !wcsicmp_0(Heap + 8, off_18000E500[j]) )
            goto LABEL_21;
        }
        if ( AslRegistryOpenSubKey(&Handle, KeyHandle, Heap + 8) >= 0 )
        {
          v9 = AslRegistryGetString(&String, Handle, L"ProfileImagePath");
          v2 = String;
          if ( v9 >= 0 )
          {
            wcslwr_0(String);
            v5 = PiiFilterpAddItemSorted(this, v2, L"%USERPROFILE%");
            if ( v5 < 0 )
              goto LABEL_23;
            v10 = wcsrchr_0(v2, 0x5Cu);
            if ( v10 )
            {
              if ( v10[1] )
              {
                v5 = RtlNameValueArray::Insert(
                       (struct _PII_FILTER *)((char *)this + 48),
                       v11,
                       v10 + 1,
                       L"%USERNAME%",
                       *((_QWORD *)this + 8));
                if ( v5 < 0 )
                  goto LABEL_23;
              }
            }
          }
        }
      }
LABEL_21:
      ;
    }
    v5 = 0;
  }
LABEL_23:
  AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  AslFree(NtCurrentPeb()->ProcessHeap, v4);
  AslFree(NtCurrentPeb()->ProcessHeap, v2);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000adf8  mov     [rsp-38h+arg_0], rbx
0x18000adfd  push    rbp
0x18000adfe  push    rsi
0x18000adff  push    rdi
0x18000ae00  push    r12
0x18000ae02  push    r13
0x18000ae04  push    r14
0x18000ae06  push    r15
0x18000ae08  mov     rbp, rsp
0x18000ae0b  sub     rsp, 40h
0x18000ae0f  xor     r12d, r12d
0x18000ae12  mov     r13, rcx
0x18000ae15  mov     [rbp+arg_8], r12d
0x18000ae19  mov     esi, 218h
0x18000ae1e  mov     [rbp+Handle], r12
0x18000ae22  mov     r8d, esi; Size
0x18000ae25  mov     [rbp+KeyHandle], r12
0x18000ae29  mov     edi, r12d
0x18000ae2c  mov     rcx, gs:60h
0x18000ae35  lea     ebx, [r12+8]
0x18000ae3a  mov     edx, ebx; Flags
0x18000ae3c  mov     rcx, [rcx+30h]; HeapHandle
0x18000ae40  call    cs:__imp_RtlAllocateHeap
0x18000ae46  mov     r14, rax
0x18000ae49  test    rax, rax
0x18000ae4c  jnz     short loc_18000AE5B
0x18000ae4e  mov     esi, r12d
0x18000ae51  mov     ebx, 0C0000017h
0x18000ae56  jmp     loc_18000AFE9
0x18000ae5b  mov     rcx, gs:60h
0x18000ae64  mov     r8, rsi; Size
0x18000ae67  mov     edx, ebx; Flags
0x18000ae69  mov     rcx, [rcx+30h]; HeapHandle
0x18000ae6d  call    cs:__imp_RtlAllocateHeap
0x18000ae73  mov     rsi, rax
0x18000ae76  test    rax, rax
0x18000ae79  jz      short loc_18000AE51
0x18000ae7b  mov     r8d, ebx
0x18000ae7e  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x18000ae85  lea     rcx, [rbp+KeyHandle]
0x18000ae89  call    AslRegistryOpenKey
0x18000ae8e  mov     ebx, eax
0x18000ae90  test    eax, eax
0x18000ae92  js      loc_18000AFE9
0x18000ae98  mov     r15d, r12d
0x18000ae9b  mov     rcx, [rbp+Handle]; Handle
0x18000ae9f  test    rcx, rcx
0x18000aea2  jz      short loc_18000AEAE
0x18000aea4  call    cs:__imp_ZwClose
0x18000aeaa  mov     [rbp+Handle], r12
0x18000aeae  mov     rcx, gs:60h
0x18000aeb7  mov     rdx, rdi
0x18000aeba  mov     rcx, [rcx+30h]
0x18000aebe  call    AslFree
0x18000aec3  mov     ebx, 218h
0x18000aec8  mov     [rbp+String], r12
0x18000aecc  mov     r8d, ebx; Size
0x18000aecf  xor     edx, edx; Val
0x18000aed1  mov     rcx, rsi; void *
0x18000aed4  mov     rdi, r12
0x18000aed7  call    memset_0
0x18000aedc  mov     r8d, ebx; Size
0x18000aedf  xor     edx, edx; Val
0x18000aee1  mov     rcx, r14; void *
0x18000aee4  call    memset_0
0x18000aee9  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18000aeed  lea     rax, [rbp+arg_8]
0x18000aef1  mov     [rsp+40h+ResultLength], rax; ResultLength
0x18000aef6  mov     r9, r14; KeyInformation
0x18000aef9  xor     r8d, r8d; KeyInformationClass
0x18000aefc  mov     [rsp+40h+Length], 217h; Length
0x18000af04  mov     edx, r15d; Index
0x18000af07  call    cs:__imp_ZwEnumerateKey
0x18000af0d  cmp     eax, 8000001Ah
0x18000af12  jz      loc_18000AFE6
0x18000af18  test    eax, eax
0x18000af1a  js      loc_18000AFDE
0x18000af20  mov     ebx, r12d
0x18000af23  cmp     ebx, 3
0x18000af26  jnb     short loc_18000AF4A
0x18000af28  lea     rax, off_18000E500; "s-1-5-18"
0x18000af2f  mov     edx, ebx
0x18000af31  lea     rcx, [r14+10h]; String1
0x18000af35  mov     rdx, [rax+rdx*8]; String2
0x18000af39  call    _wcsicmp_0
0x18000af3e  test    eax, eax
0x18000af40  jz      loc_18000AFDB
0x18000af46  inc     ebx
0x18000af48  jmp     short loc_18000AF23
0x18000af4a  mov     rdx, [rbp+KeyHandle]
0x18000af4e  lea     r8, [r14+10h]
0x18000af52  lea     rcx, [rbp+Handle]; KeyHandle
0x18000af56  call    AslRegistryOpenSubKey
0x18000af5b  xor     r12d, r12d
0x18000af5e  test    eax, eax
0x18000af60  js      short loc_18000AFDE
0x18000af62  mov     rdx, [rbp+Handle]
0x18000af66  lea     r8, aProfileimagepa; "ProfileImagePath"
0x18000af6d  lea     rcx, [rbp+String]
0x18000af71  call    AslRegistryGetString
0x18000af76  mov     rdi, [rbp+String]
0x18000af7a  test    eax, eax
0x18000af7c  js      short loc_18000AFDE
0x18000af7e  mov     rcx, rdi; String
0x18000af81  call    _wcslwr_0
0x18000af86  lea     r8, aUserprofile; "%USERPROFILE%"
0x18000af8d  mov     rdx, rdi; unsigned __int16 *
0x18000af90  mov     rcx, r13; this
0x18000af93  call    ?PiiFilterpAddItemSorted@@YAJPEAU_PII_FILTER@@PEBG1@Z; PiiFilterpAddItemSorted(_PII_FILTER *,ushort const *,ushort const *)
0x18000af98  mov     ebx, eax
0x18000af9a  test    eax, eax
0x18000af9c  js      short loc_18000AFE9
0x18000af9e  lea     edx, [r12+5Ch]; Ch
0x18000afa3  mov     rcx, rdi; Str
0x18000afa6  call    wcsrchr_0
0x18000afab  test    rax, rax
0x18000afae  jz      short loc_18000AFDE
0x18000afb0  lea     r8, [rax+2]; unsigned __int16 *
0x18000afb4  cmp     [r8], r12w
0x18000afb8  jz      short loc_18000AFDE
0x18000afba  lea     rcx, [r13+30h]; this
0x18000afbe  mov     rax, [rcx+10h]
0x18000afc2  lea     r9, aUsername; "%USERNAME%"
0x18000afc9  mov     qword ptr [rsp+40h+Length], rax; unsigned __int64
0x18000afce  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x18000afd3  mov     ebx, eax
0x18000afd5  test    eax, eax
0x18000afd7  js      short loc_18000AFE9
0x18000afd9  jmp     short loc_18000AFDE
0x18000afdb  xor     r12d, r12d
0x18000afde  inc     r15d
0x18000afe1  jmp     loc_18000AE9B
0x18000afe6  mov     ebx, r12d
0x18000afe9  mov     rcx, gs:60h
0x18000aff2  mov     rdx, r14
0x18000aff5  mov     rcx, [rcx+30h]
0x18000aff9  call    AslFree
0x18000affe  mov     rcx, gs:60h
0x18000b007  mov     rdx, rsi
0x18000b00a  mov     rcx, [rcx+30h]
0x18000b00e  call    AslFree
0x18000b013  mov     rcx, gs:60h
0x18000b01c  mov     rdx, rdi
0x18000b01f  mov     rcx, [rcx+30h]
0x18000b023  call    AslFree
0x18000b028  mov     rcx, [rbp+KeyHandle]; Handle
0x18000b02c  test    rcx, rcx
0x18000b02f  jz      short loc_18000B037
0x18000b031  call    cs:__imp_ZwClose
0x18000b037  mov     rcx, [rbp+Handle]; Handle
0x18000b03b  test    rcx, rcx
0x18000b03e  jz      short loc_18000B046
0x18000b040  call    cs:__imp_ZwClose
0x18000b046  mov     eax, ebx
0x18000b048  mov     rbx, [rsp+40h+arg_0]
0x18000b050  add     rsp, 40h
0x18000b054  pop     r15
0x18000b056  pop     r14
0x18000b058  pop     r13
0x18000b05a  pop     r12
0x18000b05c  pop     rdi
0x18000b05d  pop     rsi
0x18000b05e  pop     rbp
0x18000b05f  retn
```
