# AVrfpParseVerifierDllsString

- ea: `0x1800c3cd8`
- end: `0x1800c3e43`
- name: `AVrfpParseVerifierDllsString`
- size: `363`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180113878`

## callees

- `0x18001b984`
- `0x1800c3cd8`
- `0x1800c4700`
- `0x180128800`
- `0x18016f030`

## string_xrefs

- `0x1800c3db8`: `verifier.dll`

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
0x1800c3cd8  push    rbx
0x1800c3cda  push    rbp
0x1800c3cdb  push    rsi
0x1800c3cdc  push    rdi
0x1800c3cdd  push    r12
0x1800c3cdf  push    r14
0x1800c3ce1  push    r15
0x1800c3ce3  sub     rsp, 20h
0x1800c3ce7  mov     rax, gs:60h
0x1800c3cf0  mov     r12d, 48h ; 'H'
0x1800c3cf6  mov     r8d, r12d
0x1800c3cf9  xor     edx, edx
0x1800c3cfb  mov     rbp, [rax+30h]
0x1800c3cff  mov     rcx, rbp
0x1800c3d02  call    RtlAllocateHeap_0
0x1800c3d07  xor     r14d, r14d
0x1800c3d0a  mov     rbx, rax
0x1800c3d0d  test    rax, rax
0x1800c3d10  jz      loc_1800C3E2E
0x1800c3d16  mov     r8d, r12d; Size
0x1800c3d19  xor     edx, edx; Val
0x1800c3d1b  mov     rcx, rax; void *
0x1800c3d1e  call    memset$thunk$772440563353939046
0x1800c3d23  movups  xmm0, xmmword ptr cs:VerifierDllString
0x1800c3d2a  lea     r15, AVrfpVerifierProvidersList
0x1800c3d31  movdqu  xmmword ptr [rbx+10h], xmm0
0x1800c3d36  mov     rax, cs:qword_1801CC638
0x1800c3d3d  cmp     [rax], r15
0x1800c3d40  jnz     loc_1800C3E27
0x1800c3d46  cmp     cs:UseWOW64, r14d
0x1800c3d4d  mov     [rbx], r15
0x1800c3d50  mov     [rbx+8], rax
0x1800c3d54  mov     [rax], rbx
0x1800c3d57  mov     cs:qword_1801CC638, rbx
0x1800c3d5e  jnz     loc_1800C3E23
0x1800c3d64  lea     rbx, AVrfpVerifierDllsString
0x1800c3d6b  movzx   eax, word ptr [rbx]
0x1800c3d6e  test    ax, ax
0x1800c3d71  jz      loc_1800C3E23
0x1800c3d77  cmp     ax, 20h ; ' '
0x1800c3d7b  jz      short loc_1800C3D83
0x1800c3d7d  cmp     ax, 9
0x1800c3d81  jnz     short loc_1800C3D8C
0x1800c3d83  add     rbx, 2
0x1800c3d87  movzx   eax, word ptr [rbx]
0x1800c3d8a  jmp     short loc_1800C3D77
0x1800c3d8c  movzx   eax, word ptr [rbx]
0x1800c3d8f  test    ax, ax
0x1800c3d92  jz      loc_1800C3E23
0x1800c3d98  mov     rsi, rbx
0x1800c3d9b  cmp     ax, 20h ; ' '
0x1800c3d9f  jz      short loc_1800C3DB3
0x1800c3da1  cmp     ax, 9
0x1800c3da5  jz      short loc_1800C3DB3
0x1800c3da7  add     rbx, 2
0x1800c3dab  movzx   eax, word ptr [rbx]
0x1800c3dae  test    ax, ax
0x1800c3db1  jnz     short loc_1800C3D9B
0x1800c3db3  cmp     rsi, rbx
0x1800c3db6  jz      short loc_1800C3E23
0x1800c3db8  lea     rdx, aVerifierDll; "verifier.dll"
0x1800c3dbf  mov     [rbx], r14w
0x1800c3dc3  mov     rcx, rsi; String1
0x1800c3dc6  call    _wcsicmp
0x1800c3dcb  test    eax, eax
0x1800c3dcd  jz      short loc_1800C3E1A
0x1800c3dcf  mov     r8, r12
0x1800c3dd2  xor     edx, edx
0x1800c3dd4  mov     rcx, rbp
0x1800c3dd7  call    RtlAllocateHeap_0
0x1800c3ddc  mov     rdi, rax
0x1800c3ddf  test    rax, rax
0x1800c3de2  jz      short loc_1800C3E2E
0x1800c3de4  mov     r8, r12; Size
0x1800c3de7  xor     edx, edx; Val
0x1800c3de9  mov     rcx, rax; void *
0x1800c3dec  call    memset$thunk$772440563353939046
0x1800c3df1  lea     rcx, [rdi+10h]; DestinationString
0x1800c3df5  mov     rdx, rsi; SourceString
0x1800c3df8  call    RtlInitUnicodeString
0x1800c3dfd  mov     rax, cs:qword_1801CC638
0x1800c3e04  cmp     [rax], r15
0x1800c3e07  jnz     short loc_1800C3E27
0x1800c3e09  mov     [rdi], r15
0x1800c3e0c  mov     [rdi+8], rax
0x1800c3e10  mov     [rax], rdi
0x1800c3e13  mov     cs:qword_1801CC638, rdi
0x1800c3e1a  add     rbx, 2
0x1800c3e1e  jmp     loc_1800C3D6B
0x1800c3e23  xor     eax, eax
0x1800c3e25  jmp     short loc_1800C3E33
0x1800c3e27  mov     ecx, 3
0x1800c3e2c  int     29h; Win8: RtlFailFast(ecx)
0x1800c3e2e  mov     eax, 0C0000017h
0x1800c3e33  add     rsp, 20h
0x1800c3e37  pop     r15
0x1800c3e39  pop     r14
0x1800c3e3b  pop     r12
0x1800c3e3d  pop     rdi
0x1800c3e3e  pop     rsi
0x1800c3e3f  pop     rbp
0x1800c3e40  pop     rbx
0x1800c3e41  retn
```
