# SockGetSingleValue

- ea: `0x1800013c8`
- end: `0x1800015f8`
- name: `SockGetSingleValue`
- size: `560`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, ULONG)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800011d8`

## callees

- `0x1800013c8`
- `0x180022bd2`

## import_xrefs

- `ntdll!RtlUnicodeStringToAnsiString` at `0x18000154a`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18000154a`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180001496`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180001496`
- `ntdll!RtlAllocateHeap` at `0x180001416`
- `ntdll!RtlAllocateHeap` at `0x18000145a`
- `ntdll!RtlAllocateHeap` at `0x180001416`
- `ntdll!RtlAllocateHeap` at `0x18000145a`
- `ntdll!RtlFreeHeap` at `0x180001510`
- `ntdll!RtlFreeHeap` at `0x1800015be`
- `ntdll!RtlFreeHeap` at `0x1800015dc`
- `ntdll!RtlFreeHeap` at `0x180001510`
- `ntdll!RtlFreeHeap` at `0x1800015be`
- `ntdll!RtlFreeHeap` at `0x1800015dc`
- `ntdll!NtQueryValueKey` at `0x1800014c0`
- `ntdll!NtQueryValueKey` at `0x1800014c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001579`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180001566`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180001566`

## string_xrefs

- `0x180001479`: `DatabasePath`

## pseudocode

```c
__int64 __fastcall SockGetSingleValue(HANDLE KeyHandle, __int64 a2, CHAR *a3, _DWORD *a4, ULONG ResultLength)
{
  USHORT *Heap; // rax
  USHORT *v9; // rdi
  int LastError; // ebx
  int v12; // ecx
  DWORD v13; // eax
  struct _PEB *v14; // rcx
  void *Buffer; // r8
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _STRING v17; // [rsp+40h] [rbp-38h] BYREF
  _STRING SourceString; // [rsp+50h] [rbp-28h] BYREF
  UNICODE_STRING v19; // [rsp+60h] [rbp-18h] BYREF

  ResultLength = 0;
  DestinationString = 0;
  SourceString = 0;
  v19 = 0;
  v17 = 0;
  Heap = (USHORT *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x400u);
  v9 = Heap;
  if ( !Heap )
    return 3221225495LL;
  memset_0(Heap, 0, 0x400u);
  *(_DWORD *)&DestinationString.Length = 0x4000000;
  DestinationString.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x400u);
  if ( DestinationString.Buffer )
  {
    *(_DWORD *)&SourceString.Length = 67108876;
    SourceString.Buffer = "DatabasePath";
    RtlAnsiStringToUnicodeString(&DestinationString, &SourceString, 0);
    LastError = NtQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, v9, 0x400u, &ResultLength);
    if ( LastError >= 0 )
    {
      v12 = *((_DWORD *)v9 + 1);
      *a4 = v12;
      if ( (unsigned int)(v12 - 3) > 1 )
      {
        v17.Length = 0;
        if ( v12 == 2 )
        {
          v17.Buffer = (PCHAR)DestinationString.Buffer;
        }
        else
        {
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
          v17.Buffer = a3;
        }
        v17.MaximumLength = 1024;
        v19.Length = v9[6];
        v19.MaximumLength = v9[6];
        v19.Buffer = (USHORT *)((char *)v9 + *((unsigned int *)v9 + 2));
        RtlUnicodeStringToAnsiString(&v17, &v19, 0);
        if ( *a4 != 2 )
          goto LABEL_19;
        v13 = ExpandEnvironmentStringsA(v17.Buffer, a3, 0x400u);
        ResultLength = v13;
        if ( v13 )
        {
          if ( v13 >= 0x400 )
            LastError = -1073741789;
        }
        else
        {
          LastError = GetLastError();
        }
        v14 = NtCurrentPeb();
        Buffer = v17.Buffer;
        goto LABEL_18;
      }
      *(_DWORD *)a3 = *(_DWORD *)((char *)v9 + *((unsigned int *)v9 + 2));
    }
    v14 = NtCurrentPeb();
    Buffer = DestinationString.Buffer;
LABEL_18:
    RtlFreeHeap(v14->ProcessHeap, 0, Buffer);
    goto LABEL_19;
  }
  LastError = -1073741801;
LABEL_19:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800013c8  push    rbp
0x1800013ca  push    rbx
0x1800013cb  push    rsi
0x1800013cc  push    rdi
0x1800013cd  push    r14
0x1800013cf  push    r15
0x1800013d1  mov     rbp, rsp
0x1800013d4  sub     rsp, 78h
0x1800013d8  xorps   xmm0, xmm0
0x1800013db  mov     [rbp+arg_20], 0
0x1800013e2  xorps   xmm1, xmm1
0x1800013e5  mov     rbx, rcx
0x1800013e8  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800013ec  mov     rsi, r8
0x1800013ef  mov     r15d, 400h
0x1800013f5  movups  xmmword ptr [rbp+SourceString.Length], xmm1
0x1800013f9  mov     r8d, r15d; Size
0x1800013fc  xor     edx, edx; Flags
0x1800013fe  movups  xmmword ptr [rbp+var_18.Length], xmm0
0x180001402  mov     r14, r9
0x180001405  movups  xmmword ptr [rbp+var_38.Length], xmm1
0x180001409  mov     rcx, gs:60h
0x180001412  mov     rcx, [rcx+30h]; HeapHandle
0x180001416  call    cs:__imp_RtlAllocateHeap
0x18000141d  nop     dword ptr [rax+rax+00h]
0x180001422  mov     rdi, rax
0x180001425  test    rax, rax
0x180001428  jnz     short loc_180001434
0x18000142a  mov     eax, 0C0000017h
0x18000142f  jmp     loc_1800015EA
0x180001434  mov     r8, r15; Size
0x180001437  xor     edx, edx; Val
0x180001439  mov     rcx, rdi; void *
0x18000143c  call    memset_0
0x180001441  mov     dword ptr [rbp+DestinationString.Length], 4000000h
0x180001448  mov     r8, r15; Size
0x18000144b  mov     rcx, gs:60h
0x180001454  xor     edx, edx; Flags
0x180001456  mov     rcx, [rcx+30h]; HeapHandle
0x18000145a  call    cs:__imp_RtlAllocateHeap
0x180001461  nop     dword ptr [rax+rax+00h]
0x180001466  mov     [rbp+DestinationString.Buffer], rax
0x18000146a  test    rax, rax
0x18000146d  jnz     short loc_180001479
0x18000146f  mov     ebx, 0C0000017h
0x180001474  jmp     loc_1800015CA
0x180001479  lea     rax, aDatabasepath; "DatabasePath"
0x180001480  mov     dword ptr [rbp+SourceString.Length], 400000Ch
0x180001487  xor     r8d, r8d; AllocateDestinationString
0x18000148a  mov     [rbp+SourceString.Buffer], rax
0x18000148e  lea     rdx, [rbp+SourceString]; SourceString
0x180001492  lea     rcx, [rbp+DestinationString]; DestinationString
0x180001496  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18000149d  nop     dword ptr [rax+rax+00h]
0x1800014a2  lea     rax, [rbp+arg_20]
0x1800014a6  mov     r9, rdi; KeyValueInformation
0x1800014a9  mov     [rsp+78h+ResultLength], rax; ResultLength
0x1800014ae  lea     rdx, [rbp+DestinationString]; ValueName
0x1800014b2  mov     r8d, 1; KeyValueInformationClass
0x1800014b8  mov     [rsp+78h+Length], r15d; Length
0x1800014bd  mov     rcx, rbx; KeyHandle
0x1800014c0  call    cs:__imp_NtQueryValueKey
0x1800014c7  nop     dword ptr [rax+rax+00h]
0x1800014cc  mov     ebx, eax
0x1800014ce  test    eax, eax
0x1800014d0  js      loc_1800015AB
0x1800014d6  mov     ecx, [rdi+4]
0x1800014d9  mov     [r14], ecx
0x1800014dc  lea     eax, [rcx-3]
0x1800014df  cmp     eax, 1
0x1800014e2  jbe     loc_1800015A3
0x1800014e8  xor     eax, eax
0x1800014ea  mov     [rbp+var_38.Length], ax
0x1800014ee  cmp     ecx, 2
0x1800014f1  jnz     short loc_1800014FD
0x1800014f3  mov     rax, [rbp+DestinationString.Buffer]
0x1800014f7  mov     [rbp+var_38.Buffer], rax
0x1800014fb  jmp     short loc_180001520
0x1800014fd  mov     rcx, gs:60h
0x180001506  xor     edx, edx; Flags
0x180001508  mov     r8, [rbp+DestinationString.Buffer]; P
0x18000150c  mov     rcx, [rcx+30h]; HeapHandle
0x180001510  call    cs:__imp_RtlFreeHeap
0x180001517  nop     dword ptr [rax+rax+00h]
0x18000151c  mov     [rbp+var_38.Buffer], rsi
0x180001520  mov     [rbp+var_38.MaximumLength], r15w
0x180001525  lea     rdx, [rbp+var_18]; SourceString
0x180001529  movzx   eax, word ptr [rdi+0Ch]
0x18000152d  lea     rcx, [rbp+var_38]; DestinationString
0x180001531  mov     [rbp+var_18.Length], ax
0x180001535  xor     r8d, r8d; AllocateDestinationString
0x180001538  movzx   eax, word ptr [rdi+0Ch]
0x18000153c  mov     [rbp+var_18.MaximumLength], ax
0x180001540  mov     eax, [rdi+8]
0x180001543  add     rax, rdi
0x180001546  mov     [rbp+var_18.Buffer], rax
0x18000154a  call    cs:__imp_RtlUnicodeStringToAnsiString
0x180001551  nop     dword ptr [rax+rax+00h]
0x180001556  cmp     dword ptr [r14], 2
0x18000155a  jnz     short loc_1800015CA
0x18000155c  mov     rcx, [rbp+var_38.Buffer]; lpSrc
0x180001560  mov     r8d, r15d; nSize
0x180001563  mov     rdx, rsi; lpDst
0x180001566  call    cs:__imp_ExpandEnvironmentStringsA
0x18000156d  nop     dword ptr [rax+rax+00h]
0x180001572  mov     [rbp+arg_20], eax
0x180001575  test    eax, eax
0x180001577  jnz     short loc_180001589
0x180001579  call    cs:__imp_GetLastError
0x180001580  nop     dword ptr [rax+rax+00h]
0x180001585  mov     ebx, eax
0x180001587  jmp     short loc_180001594
0x180001589  cmp     eax, r15d
0x18000158c  mov     ecx, 0C0000023h
0x180001591  cmovnb  ebx, ecx
0x180001594  mov     rcx, gs:60h
0x18000159d  mov     r8, [rbp+var_38.Buffer]
0x1800015a1  jmp     short loc_1800015B8
0x1800015a3  mov     eax, [rdi+8]
0x1800015a6  mov     ecx, [rax+rdi]
0x1800015a9  mov     [rsi], ecx
0x1800015ab  mov     rcx, gs:60h
0x1800015b4  mov     r8, [rbp+DestinationString.Buffer]; P
0x1800015b8  mov     rcx, [rcx+30h]; HeapHandle
0x1800015bc  xor     edx, edx; Flags
0x1800015be  call    cs:__imp_RtlFreeHeap
0x1800015c5  nop     dword ptr [rax+rax+00h]
0x1800015ca  mov     rcx, gs:60h
0x1800015d3  mov     r8, rdi; P
0x1800015d6  xor     edx, edx; Flags
0x1800015d8  mov     rcx, [rcx+30h]; HeapHandle
0x1800015dc  call    cs:__imp_RtlFreeHeap
0x1800015e3  nop     dword ptr [rax+rax+00h]
0x1800015e8  mov     eax, ebx
0x1800015ea  add     rsp, 78h
0x1800015ee  pop     r15
0x1800015f0  pop     r14
0x1800015f2  pop     rdi
0x1800015f3  pop     rsi
0x1800015f4  pop     rbx
0x1800015f5  pop     rbp
0x1800015f6  retn
```
