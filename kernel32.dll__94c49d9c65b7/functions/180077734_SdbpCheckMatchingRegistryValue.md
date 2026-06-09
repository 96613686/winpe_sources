# SdbpCheckMatchingRegistryValue

- ea: `0x180077734`
- end: `0x180077ab3`
- name: `SdbpCheckMatchingRegistryValue`
- size: `895`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, wchar_t *String1@<rdx>, int, __int64, void *Buf1, size_t Size, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18007754c`
- `0x18007851c`

## callees

- `0x180021144`
- `0x1800212e4`
- `0x1800214b4`
- `0x180058f2c`
- `0x18005c390`
- `0x18005c3a8`
- `0x180077734`
- `0x18007a7c5`

## import_xrefs

- `ntdll!ZwQueryValueKey` at `0x1800777de`
- `ntdll!ZwQueryValueKey` at `0x180077860`
- `ntdll!ZwQueryValueKey` at `0x1800777de`
- `ntdll!ZwQueryValueKey` at `0x180077860`
- `ntdll!RtlInitUnicodeString` at `0x1800777ba`
- `ntdll!RtlInitUnicodeString` at `0x1800777ba`
- `ntdll!RtlAllocateHeap` at `0x180077814`
- `ntdll!RtlAllocateHeap` at `0x18007791a`
- `ntdll!RtlAllocateHeap` at `0x180077a56`
- `ntdll!RtlAllocateHeap` at `0x180077814`
- `ntdll!RtlAllocateHeap` at `0x18007791a`
- `ntdll!RtlAllocateHeap` at `0x180077a56`

## string_xrefs

- `0x180077782`: `dbRegistryDefaultName`
- `0x18007786d`: `Failed to read value`
- `0x1800778e2`: `Unknown registry value data type`
- `0x18007782f`: `SdbpCheckMatchingRegistryValue`
- `0x18007787d`: `SdbpCheckMatchingRegistryValue`

## pseudocode

```c
__int64 __fastcall SdbpCheckMatchingRegistryValue(
        HANDLE KeyHandle,
        wchar_t *String1,
        int a3,
        __int64 a4,
        int a5,
        __int64 a6,
        void *Buf1,
        size_t Size,
        _DWORD *a9)
{
  PCWSTR v12; // r15
  _WORD *v13; // rsi
  _DWORD *v14; // rdi
  unsigned int v15; // ebx
  const WCHAR *v16; // rdx
  int v17; // eax
  NTSTATUS v18; // eax
  _DWORD *Heap; // rax
  const char *v20; // r9
  int v21; // r8d
  int v22; // ecx
  _DWORD *v23; // r14
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  bool v29; // zf
  _WORD *v30; // rax
  _WORD *i; // rcx
  _WORD *v33; // rax
  PCWSTR SourceString; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+98h] [rbp+48h] BYREF
  __int64 v37; // [rsp+A8h] [rbp+58h]

  v37 = a4;
  SourceString = 0;
  ResultLength = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  DestinationString = 0;
  if ( !String1 || !*String1 )
    goto LABEL_38;
  v15 = 0;
  if ( wcsicmp_0(String1, L"dbRegistryDefaultName") )
  {
    v17 = AslStringDuplicate(&SourceString, String1);
    v12 = SourceString;
    if ( v17 < 0 )
      goto LABEL_42;
    v16 = SourceString;
  }
  else
  {
    v16 = 0;
  }
  RtlInitUnicodeString(&DestinationString, v16);
  v18 = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, 0, 0, &ResultLength);
  if ( v18 < 0 && v18 != -2147483643 && v18 != -1073741789 )
  {
    v15 = 1;
    goto LABEL_42;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, ResultLength);
  v14 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, (unsigned int)"SdbpCheckMatchingRegistryValue", 1249, (unsigned int)"Failed to allocate memory");
    goto LABEL_42;
  }
  if ( ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, Heap, ResultLength, &ResultLength) >= 0 )
  {
    if ( !a3 )
    {
      *a9 = 1;
LABEL_18:
      v15 = 1;
      goto LABEL_39;
    }
    v22 = v14[1];
    if ( v22 != a3 )
      goto LABEL_18;
    v23 = (_DWORD *)((char *)v14 + (unsigned int)v14[2]);
    v24 = v22 - 1;
    if ( v24 && (v25 = v24 - 1) != 0 )
    {
      v26 = v25 - 1;
      if ( !v26 )
      {
        if ( Size != v14[3] )
          goto LABEL_52;
        v29 = memcmp_0(Buf1, (char *)v14 + (unsigned int)v14[2], Size) == 0;
LABEL_37:
        if ( v29 )
          goto LABEL_38;
LABEL_52:
        v15 = 1;
        goto LABEL_39;
      }
      v27 = v26 - 1;
      if ( !v27 )
      {
        v29 = a5 == *v23;
        goto LABEL_37;
      }
      v28 = v27 - 3;
      if ( v28 )
      {
        if ( v28 != 4 )
        {
          v20 = "Unknown registry value data type";
          v21 = 1396;
          goto LABEL_15;
        }
        v29 = a6 == *(_QWORD *)v23;
        goto LABEL_37;
      }
      v30 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v14[3] + 2LL);
      v13 = v30;
      if ( !v30 )
      {
        v21 = 1321;
LABEL_49:
        v20 = "Failed to allocate memory";
        goto LABEL_15;
      }
      memmove_0(v30, v23, (unsigned int)v14[3]);
      v13[(unsigned __int64)(unsigned int)v14[3] >> 1] = 0;
      for ( i = v13; i < (_WORD *)((char *)v13 + (v14[3] & 0xFFFFFFFE)); ++i )
      {
        if ( !*i )
        {
          if ( !i[1] )
            break;
          *i = 59;
        }
      }
    }
    else
    {
      v33 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v14[3] + 2LL);
      v13 = v33;
      if ( !v33 )
      {
        v21 = 1297;
        goto LABEL_49;
      }
      memmove_0(v33, v23, (unsigned int)v14[3]);
      v13[(unsigned __int64)(unsigned int)v14[3] >> 1] = 0;
    }
    if ( !(unsigned int)AslStringPatternMatchExW(v37, v13) )
      goto LABEL_52;
LABEL_38:
    *a9 = 1;
    v15 = 1;
    if ( !v14 )
      goto LABEL_40;
    goto LABEL_39;
  }
  v20 = "Failed to read value";
  v21 = 1260;
LABEL_15:
  AslLogCallPrintf(1, (unsigned int)"SdbpCheckMatchingRegistryValue", v21, (_DWORD)v20);
LABEL_39:
  AslFree(NtCurrentPeb()->ProcessHeap, v14);
LABEL_40:
  if ( v13 )
    AslFree(NtCurrentPeb()->ProcessHeap, v13);
LABEL_42:
  if ( v12 )
    AslFree(NtCurrentPeb()->ProcessHeap, v12);
  return v15;
}

```

## disassembly

```asm
0x180077734  mov     [rsp-38h+arg_0], rbx
0x180077739  mov     [rsp-38h+arg_18], r9
0x18007773e  push    rbp
0x18007773f  push    rsi
0x180077740  push    rdi
0x180077741  push    r12
0x180077743  push    r13
0x180077745  push    r14
0x180077747  push    r15
0x180077749  mov     rbp, rsp
0x18007774c  sub     rsp, 50h
0x180077750  xor     eax, eax
0x180077752  xorps   xmm0, xmm0
0x180077755  mov     [rbp+SourceString], rax
0x180077759  mov     r12d, r8d
0x18007775c  mov     [rbp+arg_8], eax
0x18007775f  mov     r14, rdx
0x180077762  mov     r13, rcx
0x180077765  mov     r15d, eax
0x180077768  mov     esi, eax
0x18007776a  mov     edi, eax
0x18007776c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180077770  test    rdx, rdx
0x180077773  jz      loc_18007799F
0x180077779  cmp     [rdx], ax
0x18007777c  jz      loc_18007799F
0x180077782  lea     rdx, aDbregistrydefa; "dbRegistryDefaultName"
0x180077789  mov     rcx, r14; String1
0x18007778c  mov     ebx, eax
0x18007778e  call    _wcsicmp_0
0x180077793  test    eax, eax
0x180077795  jnz     short loc_18007779B
0x180077797  xor     edx, edx
0x180077799  jmp     short loc_1800777B6
0x18007779b  mov     rdx, r14
0x18007779e  lea     rcx, [rbp+SourceString]
0x1800777a2  call    AslStringDuplicate
0x1800777a7  mov     r15, [rbp+SourceString]
0x1800777ab  test    eax, eax
0x1800777ad  js      loc_1800779E5
0x1800777b3  mov     rdx, r15; SourceString
0x1800777b6  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800777ba  call    cs:__imp_RtlInitUnicodeString
0x1800777c0  xor     r9d, r9d; KeyValueInformation
0x1800777c3  lea     rax, [rbp+arg_8]
0x1800777c7  mov     [rsp+50h+ResultLength], rax; ResultLength
0x1800777cc  lea     rdx, [rbp+DestinationString]; ValueName
0x1800777d0  mov     rcx, r13; KeyHandle
0x1800777d3  mov     [rsp+50h+Length], ebx; Length
0x1800777d7  lea     r14d, [r9+1]
0x1800777db  mov     r8d, r14d; KeyValueInformationClass
0x1800777de  call    cs:__imp_ZwQueryValueKey
0x1800777e4  test    eax, eax
0x1800777e6  jns     short loc_1800777FE
0x1800777e8  cmp     eax, 80000005h
0x1800777ed  jz      short loc_1800777FE
0x1800777ef  cmp     eax, 0C0000023h
0x1800777f4  jz      short loc_1800777FE
0x1800777f6  mov     ebx, r14d
0x1800777f9  jmp     loc_1800779E5
0x1800777fe  mov     rcx, gs:60h
0x180077807  mov     edx, 8; Flags
0x18007780c  mov     r8d, [rbp+arg_8]; Size
0x180077810  mov     rcx, [rcx+30h]; HeapHandle
0x180077814  call    cs:__imp_RtlAllocateHeap
0x18007781a  mov     rdi, rax
0x18007781d  test    rax, rax
0x180077820  jnz     short loc_180077843
0x180077822  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x180077829  mov     r8d, 4E1h
0x18007782f  lea     rdx, aSdbpcheckmatch_7; "SdbpCheckMatchingRegistryValue"
0x180077836  mov     ecx, r14d
0x180077839  call    AslLogCallPrintf
0x18007783e  jmp     loc_1800779E5
0x180077843  lea     rax, [rbp+arg_8]
0x180077847  mov     r9, rdi; KeyValueInformation
0x18007784a  mov     [rsp+50h+ResultLength], rax; ResultLength
0x18007784f  lea     rdx, [rbp+DestinationString]; ValueName
0x180077853  mov     eax, [rbp+arg_8]
0x180077856  mov     r8d, r14d; KeyValueInformationClass
0x180077859  mov     rcx, r13; KeyHandle
0x18007785c  mov     [rsp+50h+Length], eax; Length
0x180077860  call    cs:__imp_ZwQueryValueKey
0x180077866  xor     r13d, r13d
0x180077869  test    eax, eax
0x18007786b  jns     short loc_18007788E
0x18007786d  lea     r9, aFailedToReadVa_0; "Failed to read value"
0x180077874  mov     r8d, 4ECh
0x18007787a  mov     ecx, r14d
0x18007787d  lea     rdx, aSdbpcheckmatch_7; "SdbpCheckMatchingRegistryValue"
0x180077884  call    AslLogCallPrintf
0x180077889  jmp     loc_1800779B6
0x18007788e  test    r12d, r12d
0x180077891  jnz     short loc_1800778A5
0x180077893  mov     rax, [rbp+arg_40]
0x18007789a  mov     [rax], r14d
0x18007789d  mov     ebx, r14d
0x1800778a0  jmp     loc_1800779B6
0x1800778a5  mov     ecx, [rdi+4]
0x1800778a8  cmp     ecx, r12d
0x1800778ab  jnz     short loc_18007789D
0x1800778ad  mov     r14d, [rdi+8]
0x1800778b1  add     r14, rdi
0x1800778b4  sub     ecx, 1
0x1800778b7  jz      loc_180077A3C
0x1800778bd  sub     ecx, 1
0x1800778c0  jz      loc_180077A3C
0x1800778c6  sub     ecx, 1
0x1800778c9  jz      loc_180077A19
0x1800778cf  sub     ecx, 1
0x1800778d2  jz      loc_180077993
0x1800778d8  sub     ecx, 3
0x1800778db  jz      short loc_180077900
0x1800778dd  cmp     ecx, 4
0x1800778e0  jz      short loc_1800778F4
0x1800778e2  lea     r9, aUnknownRegistr; "Unknown registry value data type"
0x1800778e9  mov     r8d, 574h
0x1800778ef  jmp     loc_180077A71
0x1800778f4  mov     rax, [r14]
0x1800778f7  cmp     [rbp+arg_28], rax
0x1800778fb  jmp     loc_180077999
0x180077900  mov     rcx, gs:60h
0x180077909  mov     edx, 8; Flags
0x18007790e  mov     r8d, [rdi+0Ch]
0x180077912  add     r8, 2; Size
0x180077916  mov     rcx, [rcx+30h]; HeapHandle
0x18007791a  call    cs:__imp_RtlAllocateHeap
0x180077920  mov     rsi, rax
0x180077923  test    rax, rax
0x180077926  jnz     short loc_180077933
0x180077928  mov     r8d, 529h
0x18007792e  jmp     loc_180077A6A
0x180077933  mov     r8d, [rdi+0Ch]; Size
0x180077937  mov     rdx, r14; Src
0x18007793a  mov     rcx, rsi; void *
0x18007793d  call    memmove_0
0x180077942  mov     ecx, [rdi+0Ch]
0x180077945  shr     rcx, 1
0x180077948  mov     [rsi+rcx*2], r13w
0x18007794d  mov     rcx, rsi
0x180077950  mov     eax, [rdi+0Ch]
0x180077953  and     rax, 0FFFFFFFFFFFFFFFEh
0x180077957  add     rax, rsi
0x18007795a  cmp     rsi, rax
0x18007795d  jnb     loc_180077A95
0x180077963  lea     rax, [rcx+2]
0x180077967  cmp     [rcx], r13w
0x18007796b  jnz     short loc_18007797C
0x18007796d  cmp     [rax], r13w
0x180077971  jz      loc_180077A95
0x180077977  mov     word ptr [rcx], 3Bh ; ';'
0x18007797c  mov     rcx, rax
0x18007797f  mov     eax, [rdi+0Ch]
0x180077982  and     rax, 0FFFFFFFFFFFFFFFEh
0x180077986  add     rax, rsi
0x180077989  cmp     rcx, rax
0x18007798c  jb      short loc_180077963
0x18007798e  jmp     loc_180077A95
0x180077993  mov     eax, [r14]
0x180077996  cmp     [rbp+arg_20], eax
0x180077999  jnz     loc_180077AA9
0x18007799f  mov     rax, [rbp+arg_40]
0x1800779a6  mov     dword ptr [rax], 1
0x1800779ac  mov     ebx, 1
0x1800779b1  test    rdi, rdi
0x1800779b4  jz      short loc_1800779CB
0x1800779b6  mov     rcx, gs:60h
0x1800779bf  mov     rdx, rdi
0x1800779c2  mov     rcx, [rcx+30h]
0x1800779c6  call    AslFree
0x1800779cb  test    rsi, rsi
0x1800779ce  jz      short loc_1800779E5
0x1800779d0  mov     rcx, gs:60h
0x1800779d9  mov     rdx, rsi
0x1800779dc  mov     rcx, [rcx+30h]
0x1800779e0  call    AslFree
0x1800779e5  test    r15, r15
0x1800779e8  jz      short loc_1800779FF
0x1800779ea  mov     rcx, gs:60h
0x1800779f3  mov     rdx, r15
0x1800779f6  mov     rcx, [rcx+30h]
0x1800779fa  call    AslFree
0x1800779ff  mov     eax, ebx
0x180077a01  mov     rbx, [rsp+50h+arg_0]
0x180077a09  add     rsp, 50h
0x180077a0d  pop     r15
0x180077a0f  pop     r14
0x180077a11  pop     r13
0x180077a13  pop     r12
0x180077a15  pop     rdi
0x180077a16  pop     rsi
0x180077a17  pop     rbp
0x180077a18  retn
0x180077a19  mov     eax, [rdi+0Ch]
0x180077a1c  mov     r8, [rbp+Size]; Size
0x180077a20  cmp     r8, rax
0x180077a23  jnz     loc_180077AA9
0x180077a29  mov     rcx, [rbp+Buf1]; Buf1
0x180077a2d  mov     rdx, r14; Buf2
0x180077a30  call    memcmp_0
0x180077a35  test    eax, eax
0x180077a37  jmp     loc_180077999
0x180077a3c  mov     rcx, gs:60h
0x180077a45  mov     edx, 8; Flags
0x180077a4a  mov     r8d, [rdi+0Ch]
0x180077a4e  add     r8, 2; Size
0x180077a52  mov     rcx, [rcx+30h]; HeapHandle
0x180077a56  call    cs:__imp_RtlAllocateHeap
0x180077a5c  mov     rsi, rax
0x180077a5f  test    rax, rax
0x180077a62  jnz     short loc_180077A7B
0x180077a64  mov     r8d, 511h
0x180077a6a  lea     r9, aFailedToAlloca_0; "Failed to allocate memory"
0x180077a71  mov     ecx, 1
0x180077a76  jmp     loc_18007787D
0x180077a7b  mov     r8d, [rdi+0Ch]; Size
0x180077a7f  mov     rdx, r14; Src
0x180077a82  mov     rcx, rsi; void *
0x180077a85  call    memmove_0
0x180077a8a  mov     ecx, [rdi+0Ch]
0x180077a8d  shr     rcx, 1
0x180077a90  mov     [rsi+rcx*2], r13w
0x180077a95  mov     rcx, [rbp+arg_18]
0x180077a99  mov     rdx, rsi
0x180077a9c  call    AslStringPatternMatchExW
0x180077aa1  test    eax, eax
0x180077aa3  jnz     loc_18007799F
0x180077aa9  mov     ebx, 1
0x180077aae  jmp     loc_1800779B6
```
