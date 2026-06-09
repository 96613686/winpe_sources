# KSecLocatePackageEx

- ea: `0x1800018f8`
- end: `0x180001a5f`
- name: `KSecLocatePackageEx`
- size: `359`
- prototype: `__int64 __fastcall(PCUNICODE_STRING String1)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800219f0`
- `0x180027738`
- `0x1800279a0`

## callees

- `0x1800018f8`
- `0x180001c00`
- `0x180001cf0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x180001959`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180001a1d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180001959`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180001a1d`

## pseudocode

```c
__int64 __fastcall KSecLocatePackageEx(PCUNICODE_STRING String1, int a2, _QWORD *a3, _QWORD *a4)
{
  __int64 v8; // rbx
  __int64 i; // rsi
  __int64 v10; // rax
  __int64 j; // rsi
  PKDEFERRED_ROUTINE DeferredRoutine; // rcx
  __int64 v14; // [rsp+60h] [rbp+18h] BYREF

  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v14);
  v8 = v14;
  *a3 = 0;
  if ( v8 )
  {
    for ( i = 0; ; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= *(_DWORD *)(v8 + 480) )
      {
        for ( j = 0; (unsigned int)j < KsecDeferredPackageCount; j = (unsigned int)(j + 1) )
        {
          if ( RtlEqualUnicodeString(String1, *((PCUNICODE_STRING *)WPP_MAIN_CB.Dpc.DeferredRoutine + 5 * j + 1), 1u) )
          {
            if ( !a2 || (*(_DWORD *)(*(_QWORD *)(v8 + 472) + 40 * j + 24) & 0x200000) == 0 )
            {
              DeferredRoutine = WPP_MAIN_CB.Dpc.DeferredRoutine;
              *a3 = *((_QWORD *)WPP_MAIN_CB.Dpc.DeferredRoutine + 5 * j);
              v10 = *((_QWORD *)DeferredRoutine + 5 * j + 2);
              goto LABEL_8;
            }
            goto LABEL_14;
          }
        }
        goto LABEL_12;
      }
      if ( RtlEqualUnicodeString(String1, *(PCUNICODE_STRING *)(*(_QWORD *)(v8 + 472) + 40 * i + 8), 1u) )
        break;
    }
    if ( !a2 || (*(_DWORD *)(*(_QWORD *)(v8 + 472) + 40 * i + 24) & 0x200000) == 0 )
    {
      *a3 = *(_QWORD *)(*(_QWORD *)(v8 + 472) + 40 * i);
      v10 = *(_QWORD *)(*(_QWORD *)(v8 + 472) + 40 * i + 16);
LABEL_8:
      *a4 = v10;
      KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v14);
      return 0;
    }
LABEL_14:
    if ( KsecddGlobalExtenderPackage )
    {
      *a3 = KsecddGlobalExtenderPackage;
      v10 = (unsigned int)KsecddGlobalExtenderPackageId;
      goto LABEL_8;
    }
LABEL_12:
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v14);
    return 2148074245LL;
  }
  else
  {
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v14);
    return 3221226238LL;
  }
}

```

## disassembly

```asm
0x1800018f8  mov     [rsp+arg_0], rbx
0x1800018fd  mov     [rsp+arg_8], rbp
0x180001902  push    rsi
0x180001903  push    rdi
0x180001904  push    r12
0x180001906  push    r14
0x180001908  push    r15
0x18000190a  sub     rsp, 20h
0x18000190e  mov     r12, rcx
0x180001911  mov     r15, r9
0x180001914  lea     rcx, [rsp+48h+arg_10]; this
0x180001919  mov     rdi, r8
0x18000191c  mov     r14d, edx
0x18000191f  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180001924  mov     rbx, [rsp+48h+arg_10]
0x180001929  mov     qword ptr [rdi], 0
0x180001930  test    rbx, rbx
0x180001933  jz      short loc_1800019B3
0x180001935  xor     esi, esi
0x180001937  cmp     esi, [rbx+1E0h]
0x18000193d  jnb     loc_1800019C4
0x180001943  mov     rdx, [rbx+1D8h]
0x18000194a  lea     rbp, [rsi+rsi*4]
0x18000194e  mov     r8b, 1; CaseInSensitive
0x180001951  mov     rcx, r12; String1
0x180001954  mov     rdx, [rdx+rbp*8+8]; String2
0x180001959  call    cs:__imp_RtlEqualUnicodeString
0x180001960  nop     dword ptr [rax+rax+00h]
0x180001965  test    al, al
0x180001967  jnz     short loc_18000196D
0x180001969  inc     esi
0x18000196b  jmp     short loc_180001937
0x18000196d  test    r14d, r14d
0x180001970  jnz     short loc_1800019DF
0x180001972  mov     rax, [rbx+1D8h]
0x180001979  mov     rcx, [rax+rbp*8]
0x18000197d  mov     [rdi], rcx
0x180001980  mov     rax, [rbx+1D8h]
0x180001987  mov     rax, [rax+rbp*8+10h]
0x18000198c  lea     rcx, [rsp+48h+arg_10]; this
0x180001991  mov     [r15], rax
0x180001994  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180001999  xor     eax, eax
0x18000199b  mov     rbx, [rsp+48h+arg_0]
0x1800019a0  mov     rbp, [rsp+48h+arg_8]
0x1800019a5  add     rsp, 20h
0x1800019a9  pop     r15
0x1800019ab  pop     r14
0x1800019ad  pop     r12
0x1800019af  pop     rdi
0x1800019b0  pop     rsi
0x1800019b1  retn
0x1800019b3  lea     rcx, [rsp+48h+arg_10]; this
0x1800019b8  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x1800019bd  mov     eax, 0C00002FEh
0x1800019c2  jmp     short loc_18000199B
0x1800019c4  xor     esi, esi
0x1800019c6  cmp     esi, cs:?KsecDeferredPackageCount@@3KA; ulong KsecDeferredPackageCount
0x1800019cc  jb      short loc_180001A07
0x1800019ce  lea     rcx, [rsp+48h+arg_10]; this
0x1800019d3  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x1800019d8  mov     eax, 80090305h
0x1800019dd  jmp     short loc_18000199B
0x1800019df  mov     rax, [rbx+1D8h]
0x1800019e6  test    dword ptr [rax+rbp*8+18h], 200000h
0x1800019ee  jz      short loc_180001972
0x1800019f0  mov     rax, cs:KsecddGlobalExtenderPackage
0x1800019f7  test    rax, rax
0x1800019fa  jz      short loc_1800019CE
0x1800019fc  mov     [rdi], rax
0x1800019ff  mov     eax, cs:KsecddGlobalExtenderPackageId
0x180001a05  jmp     short loc_18000198C
0x180001a07  mov     rdx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x180001a0e  lea     rbp, [rsi+rsi*4]
0x180001a12  mov     r8b, 1; CaseInSensitive
0x180001a15  mov     rcx, r12; String1
0x180001a18  mov     rdx, [rdx+rbp*8+8]; String2
0x180001a1d  call    cs:__imp_RtlEqualUnicodeString
0x180001a24  nop     dword ptr [rax+rax+00h]
0x180001a29  test    al, al
0x180001a2b  jnz     short loc_180001A31
0x180001a2d  inc     esi
0x180001a2f  jmp     short loc_1800019C6
0x180001a31  test    r14d, r14d
0x180001a34  jz      short loc_180001A47
0x180001a36  mov     rax, [rbx+1D8h]
0x180001a3d  test    dword ptr [rax+rbp*8+18h], 200000h
0x180001a45  jnz     short loc_1800019F0
0x180001a47  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x180001a4e  mov     rax, [rcx+rbp*8]
0x180001a52  mov     [rdi], rax
0x180001a55  mov     rax, [rcx+rbp*8+10h]
0x180001a5a  jmp     loc_18000198C
```
