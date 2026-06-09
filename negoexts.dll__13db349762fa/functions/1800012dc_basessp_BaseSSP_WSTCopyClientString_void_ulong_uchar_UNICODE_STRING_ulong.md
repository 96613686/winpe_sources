# basessp::BaseSSP::WSTCopyClientString(void *,ulong,uchar,_UNICODE_STRING *,ulong)

- ea: `0x1800012dc`
- end: `0x1800013f5`
- name: `?WSTCopyClientString@BaseSSP@basessp@@AEAAJPEAXKEPEAU_UNICODE_STRING@@K@Z`
- size: `281`
- prototype: `__int64 __usercall@<rax>(basessp::BaseSSP *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned __int8@<r9b>, struct _UNICODE_STRING *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180004404`

## callees

- `0x1800012dc`
- `0x1800027e4`
- `0x180005960`
- `0x180006650`
- `0x180020010`

## import_xrefs

- `ntdll!RtlAnsiStringToUnicodeString` at `0x180001386`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x180001386`
- `ntdll!RtlFreeUnicodeString` at `0x1800013d0`
- `ntdll!RtlFreeUnicodeString` at `0x1800013d0`

## pseudocode

```c
__int64 __fastcall basessp::BaseSSP::WSTCopyClientString(
        basessp::BaseSSP *this,
        void *a2,
        unsigned int a3,
        char a4,
        struct _UNICODE_STRING *a5,
        unsigned int a6)
{
  USHORT v6; // di
  NTSTATUS v10; // esi
  unsigned __int64 v11; // rsi
  WCHAR *v12; // rax
  WCHAR *v13; // rbx
  unsigned __int8 v14; // r9
  USHORT v15; // di
  _STRING SourceString; // [rsp+30h] [rbp-58h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF

  v6 = a3;
  DestinationString = 0;
  if ( a3 > a6 )
  {
    v10 = -1073741811;
LABEL_10:
    v13 = 0;
    goto LABEL_11;
  }
  v11 = a3 * (2 - (a4 != 0));
  v12 = (WCHAR *)basessp::BaseSSP::WSTAllocate(this, v11);
  v13 = v12;
  if ( !v12 )
  {
    v10 = -1073741670;
    goto LABEL_11;
  }
  v10 = ((__int64 (__fastcall *)(_QWORD, _QWORD, WCHAR *, void *))basessp::WSTGlobalLsaFunctions->CopyFromClientBuffer)(
          0,
          (unsigned int)v11,
          v12,
          a2);
  if ( v10 >= 0 )
  {
    if ( !a4 )
    {
      v15 = 2 * v6;
      a5->Buffer = v13;
      a5->Length = v15;
      a5->MaximumLength = v15;
      goto LABEL_10;
    }
    *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
    SourceString.Buffer = (PCHAR)v13;
    SourceString.Length = v6;
    SourceString.MaximumLength = v6;
    v10 = RtlAnsiStringToUnicodeString(&DestinationString, &SourceString, 1u);
    if ( v10 >= 0 )
      v10 = basessp::BaseSSP::WSTDuplicateStringEx(this, a5, &DestinationString, v14);
  }
LABEL_11:
  if ( DestinationString.Buffer )
    RtlFreeUnicodeString(&DestinationString);
  if ( v13 )
    basessp::BaseSSP::WSTFree(this, v13);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800012dc  push    rbx
0x1800012de  push    rbp
0x1800012df  push    rsi
0x1800012e0  push    rdi
0x1800012e1  push    r14
0x1800012e3  push    r15
0x1800012e5  sub     rsp, 58h
0x1800012e9  mov     edi, r8d
0x1800012ec  mov     al, r9b
0x1800012ef  neg     al
0x1800012f1  xorps   xmm0, xmm0
0x1800012f4  mov     r14b, r9b
0x1800012f7  mov     r15, rdx
0x1800012fa  sbb     r8d, r8d
0x1800012fd  mov     rbp, rcx
0x180001300  add     r8d, 2
0x180001304  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x180001309  cmp     edi, [rsp+88h+arg_28]
0x180001310  jbe     short loc_18000131C
0x180001312  mov     esi, 0C000000Dh
0x180001317  jmp     loc_1800013C1
0x18000131c  imul    r8d, edi
0x180001320  mov     edx, r8d; unsigned __int64
0x180001323  mov     esi, r8d
0x180001326  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18000132b  mov     rbx, rax
0x18000132e  test    rax, rax
0x180001331  jnz     short loc_18000133D
0x180001333  mov     esi, 0C000009Ah
0x180001338  jmp     loc_1800013C3
0x18000133d  mov     rax, cs:?WSTGlobalLsaFunctions@basessp@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * basessp::WSTGlobalLsaFunctions
0x180001344  mov     r9, r15
0x180001347  mov     r8, rbx
0x18000134a  mov     edx, esi
0x18000134c  xor     ecx, ecx
0x18000134e  mov     rax, [rax+50h]
0x180001352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001357  mov     esi, eax
0x180001359  test    eax, eax
0x18000135b  js      short loc_1800013C3
0x18000135d  test    r14b, r14b
0x180001360  jz      short loc_1800013AB
0x180001362  xorps   xmm0, xmm0
0x180001365  lea     rdx, [rsp+88h+SourceString]; SourceString
0x18000136a  movups  xmmword ptr [rsp+88h+SourceString.Length], xmm0
0x18000136f  mov     r8b, 1; AllocateDestinationString
0x180001372  mov     [rsp+88h+SourceString.Buffer], rbx
0x180001377  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x18000137c  mov     [rsp+88h+SourceString.Length], di
0x180001381  mov     [rsp+88h+SourceString.MaximumLength], di
0x180001386  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18000138c  mov     esi, eax
0x18000138e  test    eax, eax
0x180001390  js      short loc_1800013C3
0x180001392  mov     rdx, [rsp+88h+arg_20]; struct _UNICODE_STRING *
0x18000139a  lea     r8, [rsp+88h+DestinationString]; struct _UNICODE_STRING *
0x18000139f  mov     rcx, rbp; this
0x1800013a2  call    ?WSTDuplicateStringEx@BaseSSP@basessp@@QEAAJPEAU_UNICODE_STRING@@0E@Z; basessp::BaseSSP::WSTDuplicateStringEx(_UNICODE_STRING *,_UNICODE_STRING *,uchar)
0x1800013a7  mov     esi, eax
0x1800013a9  jmp     short loc_1800013C3
0x1800013ab  mov     rax, [rsp+88h+arg_20]
0x1800013b3  add     di, di
0x1800013b6  mov     [rax+8], rbx
0x1800013ba  mov     [rax], di
0x1800013bd  mov     [rax+2], di
0x1800013c1  xor     ebx, ebx
0x1800013c3  cmp     [rsp+88h+DestinationString.Buffer], 0
0x1800013c9  jz      short loc_1800013D6
0x1800013cb  lea     rcx, [rsp+88h+DestinationString]; UnicodeString
0x1800013d0  call    cs:__imp_RtlFreeUnicodeString
0x1800013d6  test    rbx, rbx
0x1800013d9  jz      short loc_1800013E6
0x1800013db  mov     rdx, rbx; void *
0x1800013de  mov     rcx, rbp; this
0x1800013e1  call    ?WSTFree@BaseSSP@basessp@@QEAAXPEAX@Z; basessp::BaseSSP::WSTFree(void *)
0x1800013e6  mov     eax, esi
0x1800013e8  add     rsp, 58h
0x1800013ec  pop     r15
0x1800013ee  pop     r14
0x1800013f0  pop     rdi
0x1800013f1  pop     rsi
0x1800013f2  pop     rbp
0x1800013f3  pop     rbx
0x1800013f4  retn
```
