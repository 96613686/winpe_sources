# PiiFilterpAddProfiles(_PII_FILTER *)

- ea: `0x18001ec90`
- end: `0x18001f061`
- name: `?PiiFilterpAddProfiles@@YAJPEAU_PII_FILTER@@@Z`
- size: `977`
- prototype: `__int64 __fastcall(struct _PII_FILTER *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ea7c`

## callees

- `0x18001e7d4`
- `0x18001e880`
- `0x18001ec90`
- `0x18001f340`
- `0x180020db0`
- `0x180036388`
- `0x18003c7d4`
- `0x18003c7e0`
- `0x18003c870`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001ef6d`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001ef6d`
- `ntdll!RtlAllocateHeap` at `0x18001ecd7`
- `ntdll!RtlAllocateHeap` at `0x18001ed07`
- `ntdll!RtlAllocateHeap` at `0x18001ecd7`
- `ntdll!RtlAllocateHeap` at `0x18001ed07`
- `ntdll!RtlFreeHeap` at `0x18001ed75`
- `ntdll!RtlFreeHeap` at `0x18001efc7`
- `ntdll!RtlFreeHeap` at `0x18001efea`
- `ntdll!RtlFreeHeap` at `0x18001f00d`
- `ntdll!RtlFreeHeap` at `0x18001ed75`
- `ntdll!RtlFreeHeap` at `0x18001efc7`
- `ntdll!RtlFreeHeap` at `0x18001efea`
- `ntdll!RtlFreeHeap` at `0x18001f00d`
- `ntdll!ZwEnumerateKey` at `0x18001edc5`
- `ntdll!ZwEnumerateKey` at `0x18001edc5`
- `ntdll!ZwClose` at `0x18001ed4e`
- `ntdll!ZwClose` at `0x18001f022`
- `ntdll!ZwClose` at `0x18001f037`
- `ntdll!ZwClose` at `0x18001ed4e`
- `ntdll!ZwClose` at `0x18001f022`
- `ntdll!ZwClose` at `0x18001f037`
- `ntdll!ZwOpenKey` at `0x18001ee98`
- `ntdll!ZwOpenKey` at `0x18001ee98`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001ee32`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001ee32`

## string_xrefs

- `0x18001eeb0`: `ProfileImagePath`
- `0x18001ed28`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`
- `0x18001ee55`: `AslRegistryOpenSubKey`
- `0x18001ee44`: `AslRegistryOpenSubKey passed bad Path [%x]`

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
              if ( !wcsicmp(Heap + 8, off_1800571D8[j]) )
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
0x18001ec90  mov     [rsp-38h+arg_0], rbx
0x18001ec95  push    rbp
0x18001ec96  push    rsi
0x18001ec97  push    rdi
0x18001ec98  push    r12
0x18001ec9a  push    r13
0x18001ec9c  push    r14
0x18001ec9e  push    r15
0x18001eca0  mov     rbp, rsp
0x18001eca3  sub     rsp, 80h
0x18001ecaa  xor     esi, esi
0x18001ecac  mov     r14, rcx
0x18001ecaf  mov     [rbp+arg_8], esi
0x18001ecb2  mov     r12d, 218h
0x18001ecb8  mov     [rbp+Handle], rsi
0x18001ecbc  mov     r8d, r12d; Size
0x18001ecbf  mov     [rbp+KeyHandle], rsi
0x18001ecc3  mov     edi, esi
0x18001ecc5  mov     rcx, gs:60h
0x18001ecce  lea     ebx, [rsi+8]
0x18001ecd1  mov     edx, ebx; Flags
0x18001ecd3  mov     rcx, [rcx+30h]; HeapHandle
0x18001ecd7  call    cs:__imp_RtlAllocateHeap
0x18001ecde  nop     dword ptr [rax+rax+00h]
0x18001ece3  mov     r15, rax
0x18001ece6  test    rax, rax
0x18001ece9  jnz     short loc_18001ECF5
0x18001eceb  mov     ebx, 0C0000017h
0x18001ecf0  jmp     loc_18001EFF6
0x18001ecf5  mov     rcx, gs:60h
0x18001ecfe  mov     r8, r12; Size
0x18001ed01  mov     edx, ebx; Flags
0x18001ed03  mov     rcx, [rcx+30h]; HeapHandle
0x18001ed07  call    cs:__imp_RtlAllocateHeap
0x18001ed0e  nop     dword ptr [rax+rax+00h]
0x18001ed13  mov     r12, rax
0x18001ed16  test    rax, rax
0x18001ed19  jnz     short loc_18001ED25
0x18001ed1b  mov     ebx, 0C0000017h
0x18001ed20  jmp     loc_18001EFB5
0x18001ed25  mov     r8d, ebx
0x18001ed28  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x18001ed2f  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18001ed33  call    AslRegistryOpenKey
0x18001ed38  mov     ebx, eax
0x18001ed3a  test    eax, eax
0x18001ed3c  js      loc_18001EFB5
0x18001ed42  mov     r13d, esi
0x18001ed45  mov     rcx, [rbp+Handle]; Handle
0x18001ed49  test    rcx, rcx
0x18001ed4c  jz      short loc_18001ED5E
0x18001ed4e  call    cs:__imp_ZwClose
0x18001ed55  nop     dword ptr [rax+rax+00h]
0x18001ed5a  mov     [rbp+Handle], rsi
0x18001ed5e  test    rdi, rdi
0x18001ed61  jz      short loc_18001ED81
0x18001ed63  mov     rcx, gs:60h
0x18001ed6c  mov     r8, rdi; P
0x18001ed6f  xor     edx, edx; Flags
0x18001ed71  mov     rcx, [rcx+30h]; HeapHandle
0x18001ed75  call    cs:__imp_RtlFreeHeap
0x18001ed7c  nop     dword ptr [rax+rax+00h]
0x18001ed81  mov     ebx, 218h
0x18001ed86  mov     [rbp+String], rsi
0x18001ed8a  mov     r8d, ebx; Size
0x18001ed8d  xor     edx, edx; Val
0x18001ed8f  mov     rcx, r12; void *
0x18001ed92  mov     rdi, rsi
0x18001ed95  call    memset_0
0x18001ed9a  mov     r8d, ebx; Size
0x18001ed9d  xor     edx, edx; Val
0x18001ed9f  mov     rcx, r15; void *
0x18001eda2  call    memset_0
0x18001eda7  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18001edab  lea     rax, [rbp+arg_8]
0x18001edaf  mov     [rsp+80h+ResultLength], rax; ResultLength
0x18001edb4  mov     r9, r15; KeyInformation
0x18001edb7  xor     r8d, r8d; KeyInformationClass
0x18001edba  mov     [rsp+80h+Length], 217h; Length
0x18001edc2  mov     edx, r13d; Index
0x18001edc5  call    cs:__imp_ZwEnumerateKey
0x18001edcc  nop     dword ptr [rax+rax+00h]
0x18001edd1  cmp     eax, 8000001Ah
0x18001edd6  jz      loc_18001EFB3
0x18001eddc  test    eax, eax
0x18001edde  js      loc_18001EFAB
0x18001ede4  mov     ebx, esi
0x18001ede6  cmp     ebx, 3
0x18001ede9  jnb     short loc_18001EE0D
0x18001edeb  lea     rax, off_1800571D8; "s-1-5-18"
0x18001edf2  mov     edx, ebx
0x18001edf4  lea     rcx, [r15+10h]; String1
0x18001edf8  mov     rdx, [rax+rdx*8]; String2
0x18001edfc  call    _wcsicmp
0x18001ee01  test    eax, eax
0x18001ee03  jz      loc_18001EFA9
0x18001ee09  inc     ebx
0x18001ee0b  jmp     short loc_18001EDE6
0x18001ee0d  mov     rbx, [rbp+KeyHandle]
0x18001ee11  lea     rdx, [r15+10h]; SourceString
0x18001ee15  xorps   xmm0, xmm0
0x18001ee18  lea     rcx, [rbp+DestinationString]; DestinationString
0x18001ee1c  xor     eax, eax
0x18001ee1e  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18001ee22  mov     [rbp+Handle], rax
0x18001ee26  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18001ee2a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18001ee2e  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18001ee32  call    cs:__imp_RtlInitUnicodeStringEx
0x18001ee39  nop     dword ptr [rax+rax+00h]
0x18001ee3e  xor     esi, esi
0x18001ee40  test    eax, eax
0x18001ee42  jns     short loc_18001EE69
0x18001ee44  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x18001ee4b  mov     [rsp+80h+Length], eax
0x18001ee4f  mov     r8d, 3BEh
0x18001ee55  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x18001ee5c  lea     ecx, [rsi+1]
0x18001ee5f  call    AslLogCallPrintf
0x18001ee64  jmp     loc_18001EFAB
0x18001ee69  lea     rax, [rbp+DestinationString]
0x18001ee6d  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001ee74  xorps   xmm0, xmm0
0x18001ee77  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18001ee7b  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18001ee7f  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x18001ee83  mov     edx, 20019h; DesiredAccess
0x18001ee88  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18001ee8f  lea     rcx, [rbp+Handle]; KeyHandle
0x18001ee93  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001ee98  call    cs:__imp_ZwOpenKey
0x18001ee9f  nop     dword ptr [rax+rax+00h]
0x18001eea4  test    eax, eax
0x18001eea6  js      loc_18001EFAB
0x18001eeac  mov     rdx, [rbp+Handle]
0x18001eeb0  lea     r8, aProfileimagepa; "ProfileImagePath"
0x18001eeb7  lea     rcx, [rbp+String]
0x18001eebb  call    AslRegistryGetString
0x18001eec0  mov     rdi, [rbp+String]
0x18001eec4  test    eax, eax
0x18001eec6  js      loc_18001EFAB
0x18001eecc  mov     rcx, rdi; String
0x18001eecf  call    _wcslwr
0x18001eed4  or      r11, 0FFFFFFFFFFFFFFFFh
0x18001eed8  mov     r9, r11
0x18001eedb  inc     r9
0x18001eede  cmp     [rdi+r9*2], si
0x18001eee3  jnz     short loc_18001EEDB
0x18001eee5  mov     rcx, [r14+10h]
0x18001eee9  mov     r10d, esi
0x18001eeec  test    rcx, rcx
0x18001eeef  jz      short loc_18001EF45
0x18001eef1  mov     rdx, rsi; unsigned __int64
0x18001eef4  mov     rax, rsi
0x18001eef7  cmp     rdx, rcx
0x18001eefa  jnb     short loc_18001EF22
0x18001eefc  mov     rcx, [r14+8]; unsigned __int64
0x18001ef00  lea     r8, [rbp+String]; unsigned __int64 *
0x18001ef04  mov     [rbp+String], rsi
0x18001ef08  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001ef0d  test    eax, eax
0x18001ef0f  js      short loc_18001EF1F
0x18001ef11  mov     rax, [rbp+String]
0x18001ef15  add     rax, [r14+28h]
0x18001ef19  cmp     rax, [r14+28h]
0x18001ef1d  jnb     short loc_18001EF22
0x18001ef1f  mov     rax, rsi
0x18001ef22  mov     rcx, [rax]
0x18001ef25  mov     rax, r11
0x18001ef28  inc     rax
0x18001ef2b  cmp     [rcx+rax*2], si
0x18001ef2f  jnz     short loc_18001EF28
0x18001ef31  cmp     r9, rax
0x18001ef34  ja      short loc_18001EF45
0x18001ef36  mov     rcx, [r14+10h]
0x18001ef3a  inc     r10d
0x18001ef3d  mov     edx, r10d; unsigned __int16 *
0x18001ef40  cmp     rdx, rcx
0x18001ef43  jb      short loc_18001EEF4
0x18001ef45  mov     eax, r10d
0x18001ef48  lea     r9, aUserprofile_0; "%USERPROFILE%"
0x18001ef4f  mov     r8, rdi; unsigned __int16 *
0x18001ef52  mov     qword ptr [rsp+80h+Length], rax; unsigned __int64
0x18001ef57  mov     rcx, r14; this
0x18001ef5a  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x18001ef5f  mov     ebx, eax
0x18001ef61  test    eax, eax
0x18001ef63  js      short loc_18001EFB5
0x18001ef65  mov     edx, 5Ch ; '\'; Ch
0x18001ef6a  mov     rcx, rdi; Str
0x18001ef6d  call    cs:__imp_wcsrchr
0x18001ef74  nop     dword ptr [rax+rax+00h]
0x18001ef79  test    rax, rax
0x18001ef7c  jz      short loc_18001EFAB
0x18001ef7e  lea     r8, [rax+2]; unsigned __int16 *
0x18001ef82  cmp     [r8], si
0x18001ef86  jz      short loc_18001EFAB
0x18001ef88  lea     rcx, [r14+30h]; this
0x18001ef8c  mov     rax, [rcx+10h]
0x18001ef90  lea     r9, aUsername; "%USERNAME%"
0x18001ef97  mov     qword ptr [rsp+80h+Length], rax; unsigned __int64
0x18001ef9c  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x18001efa1  mov     ebx, eax
0x18001efa3  test    eax, eax
0x18001efa5  js      short loc_18001EFB5
0x18001efa7  jmp     short loc_18001EFAB
0x18001efa9  xor     esi, esi
0x18001efab  inc     r13d
0x18001efae  jmp     loc_18001ED45
0x18001efb3  mov     ebx, esi
0x18001efb5  mov     rcx, gs:60h
0x18001efbe  mov     r8, r15; P
0x18001efc1  xor     edx, edx; Flags
0x18001efc3  mov     rcx, [rcx+30h]; HeapHandle
0x18001efc7  call    cs:__imp_RtlFreeHeap
0x18001efce  nop     dword ptr [rax+rax+00h]
0x18001efd3  test    r12, r12
0x18001efd6  jz      short loc_18001EFF6
0x18001efd8  mov     rcx, gs:60h
0x18001efe1  mov     r8, r12; P
0x18001efe4  xor     edx, edx; Flags
0x18001efe6  mov     rcx, [rcx+30h]; HeapHandle
0x18001efea  call    cs:__imp_RtlFreeHeap
0x18001eff1  nop     dword ptr [rax+rax+00h]
0x18001eff6  test    rdi, rdi
0x18001eff9  jz      short loc_18001F019
0x18001effb  mov     rcx, gs:60h
0x18001f004  mov     r8, rdi; P
0x18001f007  xor     edx, edx; Flags
0x18001f009  mov     rcx, [rcx+30h]; HeapHandle
0x18001f00d  call    cs:__imp_RtlFreeHeap
0x18001f014  nop     dword ptr [rax+rax+00h]
0x18001f019  mov     rcx, [rbp+KeyHandle]; Handle
0x18001f01d  test    rcx, rcx
0x18001f020  jz      short loc_18001F02E
0x18001f022  call    cs:__imp_ZwClose
0x18001f029  nop     dword ptr [rax+rax+00h]
0x18001f02e  mov     rcx, [rbp+Handle]; Handle
0x18001f032  test    rcx, rcx
0x18001f035  jz      short loc_18001F043
0x18001f037  call    cs:__imp_ZwClose
0x18001f03e  nop     dword ptr [rax+rax+00h]
0x18001f043  mov     eax, ebx
0x18001f045  mov     rbx, [rsp+80h+arg_0]
0x18001f04d  add     rsp, 80h
0x18001f054  pop     r15
0x18001f056  pop     r14
0x18001f058  pop     r13
0x18001f05a  pop     r12
0x18001f05c  pop     rdi
0x18001f05d  pop     rsi
0x18001f05e  pop     rbp
0x18001f05f  retn
```
