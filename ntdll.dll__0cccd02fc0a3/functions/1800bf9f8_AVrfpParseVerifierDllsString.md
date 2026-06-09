# AVrfpParseVerifierDllsString

- ea: `0x1800bf9f8`
- end: `0x1800bfb63`
- name: `AVrfpParseVerifierDllsString`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180112488`

## callees

- `0x18001b984`
- `0x1800bf9f8`
- `0x1800c0420`
- `0x180127d10`
- `0x18016f030`

## string_xrefs

- `0x1800bfad8`: `verifier.dll`

## pseudocode

```c
__int64 AVrfpParseVerifierDllsString()
{
  void *ProcessHeap; // rbp
  void *Heap_0; // rax
  __int64 v2; // rbx
  __int64 *v3; // rax
  bool v4; // zf
  wchar_t *i; // rbx
  wchar_t v6; // ax
  wchar_t v7; // ax
  const WCHAR *v8; // rsi
  void *v9; // rax
  __int64 v10; // rdi
  __int64 *v11; // rax

  ProcessHeap = NtCurrentPeb()->ProcessHeap;
  Heap_0 = (void *)RtlAllocateHeap_0(ProcessHeap, 0, 72);
  v2 = (__int64)Heap_0;
  if ( !Heap_0 )
    return 3221225495LL;
  memset_thunk_772440563353939046(Heap_0, 0, 0x48u);
  *(_OWORD *)(v2 + 16) = *(_OWORD *)VerifierDllString;
  v3 = (__int64 *)qword_1801CC638;
  if ( *(__int64 **)qword_1801CC638 != &AVrfpVerifierProvidersList )
LABEL_21:
    __fastfail(3u);
  v4 = UseWOW64 == 0;
  *(_QWORD *)v2 = &AVrfpVerifierProvidersList;
  *(_QWORD *)(v2 + 8) = v3;
  *v3 = v2;
  qword_1801CC638 = v2;
  if ( v4 )
  {
    for ( i = &AVrfpVerifierDllsString; ; ++i )
    {
      v6 = *i;
      if ( !*i )
        break;
      while ( v6 == 32 || v6 == 9 )
        v6 = *++i;
      v7 = *i;
      if ( !*i )
        break;
      v8 = i;
      do
      {
        if ( v7 == 32 )
          break;
        if ( v7 == 9 )
          break;
        v7 = *++i;
      }
      while ( *i );
      if ( v8 == i )
        break;
      *i = 0;
      if ( wcsicmp(v8, L"verifier.dll") )
      {
        v9 = (void *)RtlAllocateHeap_0(ProcessHeap, 0, 72);
        v10 = (__int64)v9;
        if ( !v9 )
          return 3221225495LL;
        memset_thunk_772440563353939046(v9, 0, 0x48u);
        RtlInitUnicodeString((PUNICODE_STRING)(v10 + 16), v8);
        v11 = (__int64 *)qword_1801CC638;
        if ( *(__int64 **)qword_1801CC638 != &AVrfpVerifierProvidersList )
          goto LABEL_21;
        *(_QWORD *)v10 = &AVrfpVerifierProvidersList;
        *(_QWORD *)(v10 + 8) = v11;
        *v11 = v10;
        qword_1801CC638 = v10;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800bf9f8  push    rbx
0x1800bf9fa  push    rbp
0x1800bf9fb  push    rsi
0x1800bf9fc  push    rdi
0x1800bf9fd  push    r12
0x1800bf9ff  push    r14
0x1800bfa01  push    r15
0x1800bfa03  sub     rsp, 20h
0x1800bfa07  mov     rax, gs:60h
0x1800bfa10  mov     r12d, 48h ; 'H'
0x1800bfa16  mov     r8d, r12d
0x1800bfa19  xor     edx, edx
0x1800bfa1b  mov     rbp, [rax+30h]
0x1800bfa1f  mov     rcx, rbp
0x1800bfa22  call    RtlAllocateHeap_0
0x1800bfa27  xor     r14d, r14d
0x1800bfa2a  mov     rbx, rax
0x1800bfa2d  test    rax, rax
0x1800bfa30  jz      loc_1800BFB4E
0x1800bfa36  mov     r8d, r12d; Size
0x1800bfa39  xor     edx, edx; Val
0x1800bfa3b  mov     rcx, rax; void *
0x1800bfa3e  call    memset$thunk$772440563353939046
0x1800bfa43  movups  xmm0, xmmword ptr cs:VerifierDllString
0x1800bfa4a  lea     r15, AVrfpVerifierProvidersList
0x1800bfa51  movdqu  xmmword ptr [rbx+10h], xmm0
0x1800bfa56  mov     rax, cs:qword_1801CC638
0x1800bfa5d  cmp     [rax], r15
0x1800bfa60  jnz     loc_1800BFB47
0x1800bfa66  cmp     cs:UseWOW64, r14d
0x1800bfa6d  mov     [rbx], r15
0x1800bfa70  mov     [rbx+8], rax
0x1800bfa74  mov     [rax], rbx
0x1800bfa77  mov     cs:qword_1801CC638, rbx
0x1800bfa7e  jnz     loc_1800BFB43
0x1800bfa84  lea     rbx, AVrfpVerifierDllsString
0x1800bfa8b  movzx   eax, word ptr [rbx]
0x1800bfa8e  test    ax, ax
0x1800bfa91  jz      loc_1800BFB43
0x1800bfa97  cmp     ax, 20h ; ' '
0x1800bfa9b  jz      short loc_1800BFAA3
0x1800bfa9d  cmp     ax, 9
0x1800bfaa1  jnz     short loc_1800BFAAC
0x1800bfaa3  add     rbx, 2
0x1800bfaa7  movzx   eax, word ptr [rbx]
0x1800bfaaa  jmp     short loc_1800BFA97
0x1800bfaac  movzx   eax, word ptr [rbx]
0x1800bfaaf  test    ax, ax
0x1800bfab2  jz      loc_1800BFB43
0x1800bfab8  mov     rsi, rbx
0x1800bfabb  cmp     ax, 20h ; ' '
0x1800bfabf  jz      short loc_1800BFAD3
0x1800bfac1  cmp     ax, 9
0x1800bfac5  jz      short loc_1800BFAD3
0x1800bfac7  add     rbx, 2
0x1800bfacb  movzx   eax, word ptr [rbx]
0x1800bface  test    ax, ax
0x1800bfad1  jnz     short loc_1800BFABB
0x1800bfad3  cmp     rsi, rbx
0x1800bfad6  jz      short loc_1800BFB43
0x1800bfad8  lea     rdx, aVerifierDll; "verifier.dll"
0x1800bfadf  mov     [rbx], r14w
0x1800bfae3  mov     rcx, rsi; String1
0x1800bfae6  call    _wcsicmp
0x1800bfaeb  test    eax, eax
0x1800bfaed  jz      short loc_1800BFB3A
0x1800bfaef  mov     r8, r12
0x1800bfaf2  xor     edx, edx
0x1800bfaf4  mov     rcx, rbp
0x1800bfaf7  call    RtlAllocateHeap_0
0x1800bfafc  mov     rdi, rax
0x1800bfaff  test    rax, rax
0x1800bfb02  jz      short loc_1800BFB4E
0x1800bfb04  mov     r8, r12; Size
0x1800bfb07  xor     edx, edx; Val
0x1800bfb09  mov     rcx, rax; void *
0x1800bfb0c  call    memset$thunk$772440563353939046
0x1800bfb11  lea     rcx, [rdi+10h]; DestinationString
0x1800bfb15  mov     rdx, rsi; SourceString
0x1800bfb18  call    RtlInitUnicodeString
0x1800bfb1d  mov     rax, cs:qword_1801CC638
0x1800bfb24  cmp     [rax], r15
0x1800bfb27  jnz     short loc_1800BFB47
0x1800bfb29  mov     [rdi], r15
0x1800bfb2c  mov     [rdi+8], rax
0x1800bfb30  mov     [rax], rdi
0x1800bfb33  mov     cs:qword_1801CC638, rdi
0x1800bfb3a  add     rbx, 2
0x1800bfb3e  jmp     loc_1800BFA8B
0x1800bfb43  xor     eax, eax
0x1800bfb45  jmp     short loc_1800BFB53
0x1800bfb47  mov     ecx, 3
0x1800bfb4c  int     29h; Win8: RtlFailFast(ecx)
0x1800bfb4e  mov     eax, 0C0000017h
0x1800bfb53  add     rsp, 20h
0x1800bfb57  pop     r15
0x1800bfb59  pop     r14
0x1800bfb5b  pop     r12
0x1800bfb5d  pop     rdi
0x1800bfb5e  pop     rsi
0x1800bfb5f  pop     rbp
0x1800bfb60  pop     rbx
0x1800bfb61  retn
```
