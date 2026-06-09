# CScrub::_ScrubAlternativeDataStreams(_SCRUB_THREAD_CONTEXT *,void *,ulong,_SCRUB_DIRECTORY_ENTRY_FLAGS)

- ea: `0x180028fe4`
- end: `0x18002920a`
- name: `?_ScrubAlternativeDataStreams@CScrub@@AEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXKW4_SCRUB_DIRECTORY_ENTRY_FLAGS@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(__int64, struct _SCRUB_THREAD_CONTEXT *, void *)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180023a44`
- `0x180024280`
- `0x1800293d4`

## callees

- `0x1800032f8`
- `0x180006688`
- `0x1800129b0`
- `0x1800247c4`
- `0x180028fe4`

## import_xrefs

- `msvcrt!realloc` at `0x1800290ea`
- `msvcrt!realloc` at `0x1800290ea`
- `ntdll!RtlEqualUnicodeString` at `0x180029199`
- `ntdll!RtlEqualUnicodeString` at `0x180029199`
- `ntdll!NtQueryInformationFile` at `0x1800290c1`
- `ntdll!NtQueryInformationFile` at `0x1800290c1`

## pseudocode

```c
__int64 __fastcall CScrub::_ScrubAlternativeDataStreams(__int64 a1, struct _SCRUB_THREAD_CONTEXT *a2, void *a3)
{
  __int64 v6; // rdx
  USHORT v7; // dx
  USHORT Length; // cx
  USHORT v9; // ax
  NTSTATUS v10; // eax
  NTSTATUS v11; // ebx
  unsigned int v12; // ebx
  void *v13; // rax
  unsigned int v14; // ebx
  unsigned int *i; // rbx
  const char *v17; // [rsp+30h] [rbp-38h] BYREF
  int v18; // [rsp+38h] [rbp-30h]
  UNICODE_STRING String1; // [rsp+40h] [rbp-28h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF

  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v6 + 16) = "CScrub::_ScrubAlternativeDataStreams";
  v17 = "CScrub::_ScrubAlternativeDataStreams";
  v18 = 0;
  v7 = ++*(_WORD *)(v6 + 8);
  Length = GlobalIndentString.Length;
  v9 = GlobalIndentString.Length;
  if ( v7 < GlobalIndentString.Length )
    v9 = v7;
  String1.Length = v9;
  if ( v7 < GlobalIndentString.Length )
    Length = v7;
  String1.MaximumLength = Length;
  *(_DWORD *)(&String1.MaximumLength + 1) = 0;
  String1.Buffer = (PWSTR)off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrub::_ScrubAlternativeDataStreams");
  }
  IoStatusBlock = 0;
  while ( 1 )
  {
    v10 = NtQueryInformationFile(
            a3,
            &IoStatusBlock,
            *(PVOID *)(a1 + 1248),
            *(_DWORD *)(a1 + 1256),
            FileStreamInformation);
    v11 = v10;
    if ( v10 != -2147483643 && v10 != -1073741789 )
      break;
    v12 = 2 * *(_DWORD *)(a1 + 1256);
    v13 = realloc(*(void **)(a1 + 1248), v12);
    if ( !v13 )
    {
      v14 = -2147024882;
      goto LABEL_30;
    }
    *(_QWORD *)(a1 + 1248) = v13;
    *(_DWORD *)(a1 + 1256) = v12;
  }
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        171,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        (_DWORD)a2 + 88,
        v10);
    }
    v14 = v11 | 0x10000000;
LABEL_30:
    v18 = v14;
LABEL_31:
    CHResultImp::~CHResultImp((CHResultImp *)&v17);
    return v14;
  }
  if ( !IoStatusBlock.Information )
  {
    v18 = 0;
    v14 = 0;
    goto LABEL_31;
  }
  for ( i = *(unsigned int **)(a1 + 1248); ; i = (unsigned int *)((char *)i + *i) )
  {
    String1 = 0;
    String1.Length = *((_WORD *)i + 2);
    String1.MaximumLength = *((_WORD *)i + 2);
    String1.Buffer = (PWSTR)(i + 6);
    if ( !RtlEqualUnicodeString(&String1, &DefaultStreamName, 1u) )
    {
      v18 = CScrub::ScrubStream((CScrub *)a1, a2, a3, &String1, 0);
      if ( v18 == -805306102 )
      {
        v14 = -805306102;
        goto LABEL_31;
      }
    }
    if ( !*i )
      break;
  }
  v18 = 0;
  CHResultImp::~CHResultImp((CHResultImp *)&v17);
  return 0;
}

```

## disassembly

```asm
0x180028fe4  push    rbp
0x180028fe6  push    rbx
0x180028fe7  push    rsi
0x180028fe8  push    rdi
0x180028fe9  push    r12
0x180028feb  push    r14
0x180028fed  mov     rbp, rsp
0x180028ff0  sub     rsp, 68h
0x180028ff4  mov     r14, r8
0x180028ff7  mov     rsi, rdx
0x180028ffa  mov     rdi, rcx
0x180028ffd  mov     r9d, cs:_tls_index
0x180029004  mov     rax, gs:58h
0x18002900d  mov     rdx, [rax+r9*8]
0x180029011  mov     eax, 10h
0x180029016  lea     r8, aCscrubScrubalt; "CScrub::_ScrubAlternativeDataStreams"
0x18002901d  mov     [rax+rdx], r8
0x180029021  mov     [rbp+var_38], r8
0x180029025  mov     [rbp+var_30], 0
0x18002902c  mov     eax, 8
0x180029031  inc     word ptr [rax+rdx]
0x180029035  movzx   edx, word ptr [rax+rdx]
0x180029039  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180029040  movzx   eax, cx
0x180029043  cmp     dx, cx
0x180029046  cmovb   ax, dx
0x18002904a  mov     [rbp+String1.Length], ax
0x18002904e  cmovb   cx, dx
0x180029052  mov     [rbp+String1.MaximumLength], cx
0x180029056  xor     eax, eax
0x180029058  mov     dword ptr [rbp+String1+4], eax
0x18002905b  mov     rax, cs:off_180047060; "                                       "...
0x180029062  mov     [rbp+String1.Buffer], rax
0x180029066  lea     r12, WPP_GLOBAL_Control
0x18002906d  mov     rcx, cs:WPP_GLOBAL_Control
0x180029074  cmp     rcx, r12
0x180029077  jz      short loc_18002909D
0x180029079  test    byte ptr [rcx+1Ch], 1
0x18002907d  jz      short loc_18002909D
0x18002907f  cmp     byte ptr [rcx+19h], 5
0x180029083  jb      short loc_18002909D
0x180029085  mov     edx, 0Dh
0x18002908a  mov     qword ptr [rsp+68h+FileInformationClass], r8; __int64
0x18002908f  lea     r9, [rbp+String1]
0x180029093  mov     rcx, [rcx+10h]; LoggerHandle
0x180029097  call    WPP_SF_aZs
0x18002909c  nop
0x18002909d  xorps   xmm0, xmm0
0x1800290a0  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x1800290a4  mov     [rsp+68h+FileInformationClass], 16h; FileInformationClass
0x1800290ac  mov     r9d, [rdi+4E8h]; Length
0x1800290b3  mov     r8, [rdi+4E0h]; FileInformation
0x1800290ba  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x1800290be  mov     rcx, r14; FileHandle
0x1800290c1  call    cs:__imp_NtQueryInformationFile
0x1800290c7  mov     ebx, eax
0x1800290c9  cmp     eax, 80000005h
0x1800290ce  jz      short loc_1800290D7
0x1800290d0  cmp     eax, 0C0000023h
0x1800290d5  jnz     short loc_180029108
0x1800290d7  mov     eax, [rdi+4E8h]
0x1800290dd  add     eax, eax
0x1800290df  mov     ebx, eax
0x1800290e1  mov     edx, eax; Size
0x1800290e3  mov     rcx, [rdi+4E0h]; Block
0x1800290ea  call    cs:__imp_realloc
0x1800290f0  test    rax, rax
0x1800290f3  jz      loc_1800291EA
0x1800290f9  mov     [rdi+4E0h], rax
0x180029100  mov     [rdi+4E8h], ebx
0x180029106  jmp     short loc_1800290A4
0x180029108  test    ebx, ebx
0x18002910a  jns     short loc_18002914A
0x18002910c  mov     rcx, cs:WPP_GLOBAL_Control
0x180029113  cmp     rcx, r12
0x180029116  jz      short loc_180029141
0x180029118  test    byte ptr [rcx+1Ch], 1
0x18002911c  jz      short loc_180029141
0x18002911e  cmp     byte ptr [rcx+19h], 2
0x180029122  jb      short loc_180029141
0x180029124  lea     r9, [rsi+58h]
0x180029128  mov     edx, 0ABh
0x18002912d  mov     [rsp+68h+FileInformationClass], ebx
0x180029131  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180029138  mov     rcx, [rcx+10h]
0x18002913c  call    WPP_SF_Zd
0x180029141  bts     ebx, 1Ch
0x180029145  jmp     loc_1800291EF
0x18002914a  cmp     [rbp+IoStatusBlock.Information], 0
0x18002914f  jnz     short loc_18002915F
0x180029151  mov     [rbp+var_30], 0
0x180029158  xor     ebx, ebx
0x18002915a  jmp     loc_1800291F2
0x18002915f  mov     rbx, [rdi+4E0h]
0x180029166  mov     r12d, 0D000010Ah
0x18002916c  xorps   xmm0, xmm0
0x18002916f  movups  xmmword ptr [rbp+String1.Length], xmm0
0x180029173  movzx   eax, word ptr [rbx+4]
0x180029177  mov     [rbp+String1.Length], ax
0x18002917b  movzx   eax, word ptr [rbx+4]
0x18002917f  mov     [rbp+String1.MaximumLength], ax
0x180029183  lea     rax, [rbx+18h]
0x180029187  mov     [rbp+String1.Buffer], rax
0x18002918b  mov     r8b, 1; CaseInsensitive
0x18002918e  lea     rdx, ?DefaultStreamName@@3U_UNICODE_STRING@@B; String2
0x180029195  lea     rcx, [rbp+String1]; String1
0x180029199  call    cs:__imp_RtlEqualUnicodeString
0x18002919f  test    al, al
0x1800291a1  jnz     short loc_1800291C5
0x1800291a3  mov     [rsp+68h+FileInformationClass], 0; unsigned int
0x1800291ab  lea     r9, [rbp+String1]; struct _UNICODE_STRING *
0x1800291af  mov     r8, r14; void *
0x1800291b2  mov     rdx, rsi; struct _SCRUB_THREAD_CONTEXT *
0x1800291b5  mov     rcx, rdi; this
0x1800291b8  call    ?ScrubStream@CScrub@@QEAAJPEAU_SCRUB_THREAD_CONTEXT@@PEAXPEBU_UNICODE_STRING@@K@Z; CScrub::ScrubStream(_SCRUB_THREAD_CONTEXT *,void *,_UNICODE_STRING const *,ulong)
0x1800291bd  mov     [rbp+var_30], eax
0x1800291c0  cmp     eax, r12d
0x1800291c3  jz      short loc_1800291D1
0x1800291c5  cmp     dword ptr [rbx], 0
0x1800291c8  jz      short loc_1800291D6
0x1800291ca  mov     eax, [rbx]
0x1800291cc  add     rbx, rax
0x1800291cf  jmp     short loc_18002916C
0x1800291d1  mov     ebx, r12d
0x1800291d4  jmp     short loc_1800291F2
0x1800291d6  mov     [rbp+var_30], 0
0x1800291dd  lea     rcx, [rbp+var_38]; this
0x1800291e1  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1800291e6  xor     eax, eax
0x1800291e8  jmp     short loc_1800291FD
0x1800291ea  mov     ebx, 8007000Eh
0x1800291ef  mov     [rbp+var_30], ebx
0x1800291f2  lea     rcx, [rbp+var_38]; this
0x1800291f6  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1800291fb  mov     eax, ebx
0x1800291fd  add     rsp, 68h
0x180029201  pop     r14
0x180029203  pop     r12
0x180029205  pop     rdi
0x180029206  pop     rsi
0x180029207  pop     rbx
0x180029208  pop     rbp
0x180029209  retn
```
