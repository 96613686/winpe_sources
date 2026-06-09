# RegSetValueExA

- ea: `0x18002e7d0`
- end: `0x18002e9e5`
- name: `RegSetValueExA`
- size: `533`
- prototype: `LSTATUS __stdcall(HKEY hKey, LPCSTR lpValueName, DWORD Reserved, DWORD dwType, const BYTE *lpData, DWORD cbData)`
- caller_count: `5`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18002e140`
- `0x18002e1cc`
- `0x18002e360`
- `0x18011fa40`
- `0x180149090`

## callees

- `0x18002e7d0`
- `0x18005e7e0`
- `0x18005feb0`
- `0x1800a7d00`
- `0x180136e28`
- `0x180194eb9`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18002e938`
- `ntdll!RtlFreeUnicodeString` at `0x18002e938`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18019a1fc`
- `ntdll!RtlMultiByteToUnicodeN` at `0x18019a1fc`
- `ntdll!RtlNtStatusToDosError` at `0x18002e86a`
- `ntdll!RtlNtStatusToDosError` at `0x18019a20e`
- `ntdll!RtlNtStatusToDosError` at `0x18002e86a`
- `ntdll!RtlNtStatusToDosError` at `0x18019a20e`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18002e855`
- `ntdll!RtlCreateUnicodeStringFromAsciiz` at `0x18002e855`
- `ntdll!RtlFreeHeap` at `0x18002e9b1`
- `ntdll!RtlFreeHeap` at `0x18002e9d4`
- `ntdll!RtlFreeHeap` at `0x18002e9b1`
- `ntdll!RtlFreeHeap` at `0x18002e9d4`
- `ntdll!RtlAllocateHeap` at `0x18019a17f`
- `ntdll!RtlAllocateHeap` at `0x18019a1ca`
- `ntdll!RtlAllocateHeap` at `0x18019a17f`
- `ntdll!RtlAllocateHeap` at `0x18019a1ca`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegSetValue` at `0x18019a24d`
- `ext-ms-win-advapi32-registry-l1-1-0!BaseRegSetValue` at `0x18019a24d`

## pseudocode

```c
LSTATUS __stdcall RegSetValueExA(
        HKEY hKey,
        LPCSTR lpValueName,
        DWORD Reserved,
        DWORD dwType,
        const BYTE *lpData,
        DWORD cbData)
{
  ULONG v8; // edi
  struct _UNICODE_STRING *p_Destination; // rax
  BYTE *v11; // r12
  BYTE *v12; // r14
  WCHAR *v13; // r15
  ULONG BytesInMultiByteString; // esi
  BYTE *v15; // rax
  size_t v16; // rdi
  BYTE *Heap; // rax
  WCHAR *v18; // rax
  int v19; // eax
  char v20; // [rsp+30h] [rbp-98h] BYREF
  ULONG BytesInUnicodeString[3]; // [rsp+34h] [rbp-94h] BYREF
  PUNICODE_STRING ValueName; // [rsp+40h] [rbp-88h]
  BYTE *v23; // [rsp+48h] [rbp-80h]
  WCHAR *v24; // [rsp+50h] [rbp-78h]
  __int64 v25; // [rsp+58h] [rbp-70h] BYREF
  __int64 v26; // [rsp+60h] [rbp-68h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+68h] [rbp-60h] BYREF
  __int128 v28; // [rsp+78h] [rbp-50h] BYREF
  HANDLE KeyHandle; // [rsp+D0h] [rbp+8h] BYREF
  LPCSTR v30; // [rsp+D8h] [rbp+10h]
  ULONG Type; // [rsp+E8h] [rbp+20h]

  Type = dwType;
  v30 = lpValueName;
  KeyHandle = hKey;
  Destination = 0;
  v28 = 0;
  BytesInUnicodeString[0] = 0;
  v26 = 0;
  v25 = 0;
  v20 = 0;
  if ( hKey == HKEY_PERFORMANCE_DATA )
    return 6;
  if ( !Reserved )
  {
    v8 = MapPredefinedHandleInternal(hKey, &KeyHandle, &v26, &v25);
    if ( v8 )
    {
LABEL_7:
      CLOSE_LOCAL_HANDLE_INTERNAL(v26, v25);
      return v8;
    }
    if ( lpValueName )
    {
      if ( !RtlCreateUnicodeStringFromAsciiz(&Destination, lpValueName) )
      {
        v8 = RtlNtStatusToDosError(-1073741801);
        goto LABEL_7;
      }
      Destination.Length += 2;
      if ( !Destination.Length )
      {
        v8 = 87;
        goto LABEL_22;
      }
      p_Destination = &Destination;
    }
    else
    {
      p_Destination = (struct _UNICODE_STRING *)&v28;
      LODWORD(v28) = 0;
      *((_QWORD *)&v28 + 1) = 0;
    }
    ValueName = p_Destination;
    v11 = 0;
    v23 = 0;
    v12 = (BYTE *)lpData;
    if ( !lpData || dwType - 1 > 1 && dwType != 7 )
    {
      v13 = 0;
      v24 = 0;
      BytesInMultiByteString = cbData;
      goto LABEL_14;
    }
    BytesInMultiByteString = cbData;
    if ( cbData )
    {
      if ( lpData[cbData - 1] )
      {
        v16 = cbData;
        if ( (((unsigned __int64)&lpData[cbData] ^ (unsigned __int64)&lpData[cbData - 1]) & 0xFFFFFFFFFFFFF000uLL) == 0
          && !lpData[cbData] )
        {
          BytesInMultiByteString = cbData + 1;
          Heap = (BYTE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, cbData + 1);
          v11 = Heap;
          v23 = Heap;
          if ( !Heap )
          {
            v8 = 8;
LABEL_22:
            if ( lpValueName )
              RtlFreeUnicodeString(&Destination);
            goto LABEL_7;
          }
          memcpy_0(Heap, v12, v16);
          v11[v16] = 0;
          v12 = v11;
        }
      }
    }
    v18 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * BytesInMultiByteString);
    v13 = v18;
    v24 = v18;
    if ( !v18 )
    {
      v8 = 8;
LABEL_18:
      if ( v11 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
      if ( v13 )
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
      goto LABEL_22;
    }
    v19 = RtlMultiByteToUnicodeN(
            v18,
            2 * BytesInMultiByteString,
            BytesInUnicodeString,
            (const CHAR *)v12,
            BytesInMultiByteString);
    if ( v19 < 0 )
    {
      v8 = RtlNtStatusToDosError(v19);
LABEL_15:
      if ( !v8 )
      {
        if ( ((unsigned __int8)KeyHandle & 1) != 0 )
        {
          if ( (unsigned __int8)IsBaseRegCloseKeyPresent() )
          {
            if ( !v12 )
            {
              v15 = (BYTE *)&v20;
              if ( BytesInMultiByteString )
                v15 = 0;
              v12 = v15;
            }
            v8 = BaseRegSetValue(
                   (unsigned __int64)KeyHandle & 0xFFFFFFFFFFFFFFFEuLL,
                   ValueName,
                   Type,
                   v12,
                   BytesInMultiByteString);
            BytesInUnicodeString[2] = v8;
          }
        }
        else
        {
          v8 = BaseRegSetValueInternal(KeyHandle, ValueName, Type, v12, BytesInMultiByteString);
        }
      }
      goto LABEL_18;
    }
    v12 = (BYTE *)v13;
    BytesInMultiByteString = BytesInUnicodeString[0];
LABEL_14:
    v8 = 0;
    goto LABEL_15;
  }
  return 87;
}

```

## disassembly

```asm
0x18002e7d0  mov     rax, rsp
0x18002e7d3  mov     [rax+20h], r9d
0x18002e7d7  mov     [rax+10h], rdx
0x18002e7db  mov     [rax+8], rcx
0x18002e7df  push    rbx
0x18002e7e0  push    rsi
0x18002e7e1  push    rdi
0x18002e7e2  push    r12
0x18002e7e4  push    r13
0x18002e7e6  push    r14
0x18002e7e8  push    r15
0x18002e7ea  sub     rsp, 90h
0x18002e7f1  mov     esi, r9d
0x18002e7f4  mov     r13, rdx
0x18002e7f7  xorps   xmm0, xmm0
0x18002e7fa  movups  xmmword ptr [rax-60h], xmm0
0x18002e7fe  xorps   xmm1, xmm1
0x18002e801  movups  xmmword ptr [rax-50h], xmm1
0x18002e805  xor     ebx, ebx
0x18002e807  mov     [rsp+0C8h+BytesInUnicodeString], ebx
0x18002e80b  mov     [rax-68h], rbx
0x18002e80f  mov     [rax-70h], rbx
0x18002e813  mov     [rsp+0C8h+var_98], bl
0x18002e817  cmp     rcx, 0FFFFFFFF80000004h
0x18002e81e  jz      loc_18002E966
0x18002e824  test    r8d, r8d
0x18002e827  jnz     loc_18002E970
0x18002e82d  lea     r9, [rax-70h]
0x18002e831  lea     r8, [rax-68h]
0x18002e835  lea     rdx, [rax+8]
0x18002e839  call    MapPredefinedHandleInternal
0x18002e83e  mov     edi, eax
0x18002e840  test    eax, eax
0x18002e842  jnz     short loc_18002E878
0x18002e844  test    r13, r13
0x18002e847  jz      loc_18002E949
0x18002e84d  mov     rdx, r13; Source
0x18002e850  lea     rcx, [rsp+0C8h+Destination]; Destination
0x18002e855  call    cs:__imp_RtlCreateUnicodeStringFromAsciiz
0x18002e85c  nop     dword ptr [rax+rax+00h]
0x18002e861  test    al, al
0x18002e863  jnz     short loc_18002E89D
0x18002e865  mov     ecx, 0C0000017h; Status
0x18002e86a  call    cs:__imp_RtlNtStatusToDosError
0x18002e871  nop     dword ptr [rax+rax+00h]
0x18002e876  mov     edi, eax
0x18002e878  mov     rdx, [rsp+0C8h+var_70]
0x18002e87d  mov     rcx, [rsp+0C8h+var_68]
0x18002e882  call    CLOSE_LOCAL_HANDLE_INTERNAL
0x18002e887  mov     eax, edi
0x18002e889  add     rsp, 90h
0x18002e890  pop     r15
0x18002e892  pop     r14
0x18002e894  pop     r13
0x18002e896  pop     r12
0x18002e898  pop     rdi
0x18002e899  pop     rsi
0x18002e89a  pop     rbx
0x18002e89b  retn
0x18002e89d  add     [rsp+0C8h+Destination.Length], 2
0x18002e8a3  jz      loc_18002E95F
0x18002e8a9  lea     rax, [rsp+0C8h+Destination]
0x18002e8ae  mov     [rsp+0C8h+ValueName], rax
0x18002e8b3  mov     r12, rbx
0x18002e8b6  mov     [rsp+0C8h+var_80], rbx
0x18002e8bb  mov     r14, [rsp+0C8h+lpData]
0x18002e8c3  test    r14, r14
0x18002e8c6  jz      short loc_18002E8DD
0x18002e8c8  lea     eax, [rsi-1]
0x18002e8cb  cmp     eax, 1
0x18002e8ce  jbe     loc_18019A13E
0x18002e8d4  cmp     esi, 7
0x18002e8d7  jz      loc_18019A13E
0x18002e8dd  mov     r15, rbx
0x18002e8e0  mov     [rsp+0C8h+var_78], rbx
0x18002e8e5  mov     esi, [rsp+0C8h+cbData]
0x18002e8ec  mov     edi, ebx
0x18002e8ee  test    edi, edi
0x18002e8f0  jnz     short loc_18002E91C
0x18002e8f2  mov     rax, [rsp+0C8h+KeyHandle]
0x18002e8fa  test    al, 1
0x18002e8fc  jnz     short loc_18002E97A
0x18002e8fe  mov     [rsp+0C8h+BytesInMultiByteString], esi; ULONG
0x18002e902  mov     r9, r14; Data
0x18002e905  mov     r8d, [rsp+0C8h+Type]; Type
0x18002e90d  mov     rdx, [rsp+0C8h+ValueName]; ValueName
0x18002e912  mov     rcx, rax; KeyHandle
0x18002e915  call    BaseRegSetValueInternal
0x18002e91a  mov     edi, eax
0x18002e91c  test    r12, r12
0x18002e91f  jnz     short loc_18002E99F
0x18002e921  test    r15, r15
0x18002e924  jnz     loc_18002E9C2
0x18002e92a  test    r13, r13
0x18002e92d  jz      loc_18002E878
0x18002e933  lea     rcx, [rsp+0C8h+Destination]; UnicodeString
0x18002e938  call    cs:__imp_RtlFreeUnicodeString
0x18002e93f  nop     dword ptr [rax+rax+00h]
0x18002e944  jmp     loc_18002E878
0x18002e949  lea     rax, [rsp+0C8h+var_50]
0x18002e94e  mov     [rsp+0C8h+var_50], ebx
0x18002e952  mov     [rsp+0C8h+var_48], rbx
0x18002e95a  jmp     loc_18002E8AE
0x18002e95f  mov     edi, 57h ; 'W'
0x18002e964  jmp     short loc_18002E92A
0x18002e966  mov     eax, 6
0x18002e96b  jmp     loc_18002E889
0x18002e970  mov     eax, 57h ; 'W'
0x18002e975  jmp     loc_18002E889
0x18002e97a  call    IsBaseRegCloseKeyPresent
0x18002e97f  test    al, al
0x18002e981  jz      short loc_18002E91C
0x18002e983  test    r14, r14
0x18002e986  jnz     loc_18019A22D
0x18002e98c  lea     rax, [rsp+0C8h+var_98]
0x18002e991  test    esi, esi
0x18002e993  cmovnz  rax, r14
0x18002e997  mov     r14, rax
0x18002e99a  jmp     loc_18019A22D
0x18002e99f  mov     rcx, gs:60h
0x18002e9a8  mov     r8, r12; P
0x18002e9ab  xor     edx, edx; Flags
0x18002e9ad  mov     rcx, [rcx+30h]; HeapHandle
0x18002e9b1  call    cs:__imp_RtlFreeHeap
0x18002e9b8  nop     dword ptr [rax+rax+00h]
0x18002e9bd  jmp     loc_18002E921
0x18002e9c2  mov     rcx, gs:60h
0x18002e9cb  mov     r8, r15; P
0x18002e9ce  xor     edx, edx; Flags
0x18002e9d0  mov     rcx, [rcx+30h]; HeapHandle
0x18002e9d4  call    cs:__imp_RtlFreeHeap
0x18002e9db  nop     dword ptr [rax+rax+00h]
0x18002e9e0  jmp     loc_18002E92A
0x18019a13e  mov     esi, [rsp+0C8h+cbData]
0x18019a145  test    esi, esi
0x18019a147  jz      short loc_18019A1B5
0x18019a149  lea     eax, [rsi-1]
0x18019a14c  cmp     [rax+r14], bl
0x18019a150  jz      short loc_18019A1B5
0x18019a152  mov     edi, esi
0x18019a154  lea     rcx, [rsi+r14]
0x18019a158  lea     rax, [rcx-1]
0x18019a15c  xor     rax, rcx
0x18019a15f  test    rax, 0FFFFFFFFFFFFF000h
0x18019a165  jnz     short loc_18019A1B5
0x18019a167  cmp     [rcx], bl
0x18019a169  jnz     short loc_18019A1B5
0x18019a16b  inc     esi
0x18019a16d  mov     r8d, esi; Size
0x18019a170  mov     rcx, gs:60h
0x18019a179  xor     edx, edx; Flags
0x18019a17b  mov     rcx, [rcx+30h]; HeapHandle
0x18019a17f  call    cs:__imp_RtlAllocateHeap
0x18019a186  nop     dword ptr [rax+rax+00h]
0x18019a18b  mov     r12, rax
0x18019a18e  mov     [rsp+0C8h+var_80], rax
0x18019a193  test    rax, rax
0x18019a196  jnz     short loc_18019A1A0
0x18019a198  lea     edi, [rax+8]
0x18019a19b  jmp     loc_18002E92A
0x18019a1a0  mov     r8, rdi; Size
0x18019a1a3  mov     rdx, r14; Src
0x18019a1a6  mov     rcx, r12; void *
0x18019a1a9  call    memcpy_0
0x18019a1ae  mov     [rdi+r12], bl
0x18019a1b2  mov     r14, r12
0x18019a1b5  lea     edi, [rsi+rsi]
0x18019a1b8  mov     r8d, edi; Size
0x18019a1bb  mov     rcx, gs:60h
0x18019a1c4  xor     edx, edx; Flags
0x18019a1c6  mov     rcx, [rcx+30h]; HeapHandle
0x18019a1ca  call    cs:__imp_RtlAllocateHeap
0x18019a1d1  nop     dword ptr [rax+rax+00h]
0x18019a1d6  mov     r15, rax
0x18019a1d9  mov     [rsp+0C8h+var_78], rax
0x18019a1de  test    rax, rax
0x18019a1e1  jnz     short loc_18019A1EB
0x18019a1e3  lea     edi, [rax+8]
0x18019a1e6  jmp     loc_18002E91C
0x18019a1eb  mov     [rsp+0C8h+BytesInMultiByteString], esi; BytesInMultiByteString
0x18019a1ef  mov     r9, r14; MultiByteString
0x18019a1f2  lea     r8, [rsp+0C8h+BytesInUnicodeString]; BytesInUnicodeString
0x18019a1f7  mov     edx, edi; MaxBytesInUnicodeString
0x18019a1f9  mov     rcx, r15; UnicodeString
0x18019a1fc  call    cs:__imp_RtlMultiByteToUnicodeN
0x18019a203  nop     dword ptr [rax+rax+00h]
0x18019a208  test    eax, eax
0x18019a20a  jns     short loc_18019A221
0x18019a20c  mov     ecx, eax; Status
0x18019a20e  call    cs:__imp_RtlNtStatusToDosError
0x18019a215  nop     dword ptr [rax+rax+00h]
0x18019a21a  mov     edi, eax
0x18019a21c  jmp     loc_18002E8EE
0x18019a221  mov     r14, r15
0x18019a224  mov     esi, [rsp+0C8h+BytesInUnicodeString]
0x18019a228  jmp     loc_18002E8EC
0x18019a22d  mov     rcx, [rsp+0C8h+KeyHandle]
0x18019a235  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18019a239  mov     [rsp+0C8h+BytesInMultiByteString], esi
0x18019a23d  mov     r9, r14
0x18019a240  mov     r8d, [rsp+0C8h+Type]
0x18019a248  mov     rdx, [rsp+0C8h+ValueName]
0x18019a24d  call    cs:__imp_BaseRegSetValue
0x18019a254  nop     dword ptr [rax+rax+00h]
0x18019a259  mov     edi, eax
0x18019a25b  mov     [rsp+0C8h+var_8C], eax
0x18019a25f  jmp     loc_18002E91C
0x18019a264  mov     edi, eax
0x18019a266  mov     [rsp+0C8h+var_8C], eax
0x18019a26a  mov     r13, [rsp+0C8h+arg_8]
0x18019a272  mov     r12, [rsp+0C8h+var_80]
0x18019a277  mov     r15, [rsp+0C8h+var_78]
0x18019a27c  jmp     loc_18002E91C
```
