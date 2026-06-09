# CClfsRequest::StartArchival(void)

- ea: `0x140043370`
- end: `0x1400434d6`
- name: `?StartArchival@CClfsRequest@@AEAAJXZ`
- size: `358`
- prototype: `__int64 __fastcall(CClfsRequest *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14006c874`

## callees

- `0x140001b30`
- `0x14000c2f0`
- `0x140043370`
- `0x140059e80`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140043487`
- `ntoskrnl!KeSetEvent` at `0x14007f363`
- `ntoskrnl!KeSetEvent` at `0x140043487`
- `ntoskrnl!KeSetEvent` at `0x14007f363`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004342b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004342b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400433cf`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400433cf`

## pseudocode

```c
__int64 __fastcall CClfsRequest::StartArchival(CClfsRequest *this)
{
  CClfsLogCcb *v2; // rsi
  __int64 v3; // rax
  __int64 v4; // rdi
  unsigned int v5; // edi
  const union _CLS_LSN *v6; // r14
  __int64 v7; // rcx
  wchar_t *v8; // rax
  struct _KEVENT *v9; // rcx
  unsigned int *Priority; // [rsp+28h] [rbp-40h]
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v13; // [rsp+78h] [rbp+10h] BYREF

  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  v13 = 0;
  v2 = 0;
  v3 = *((_QWORD *)this + 6);
  v4 = *(_QWORD *)(v3 + 184);
  if ( *(_DWORD *)(v4 + 16) >= 0x10u )
  {
    v6 = *(const union _CLS_LSN **)(v3 + 24);
    RtlInitUnicodeString(&DestinationString, 0);
    DestinationString.MaximumLength = *(_WORD *)(v4 + 8);
    v2 = *(CClfsLogCcb **)(*(_QWORD *)(v4 + 48) + 32LL);
    CClfsLogCcb::AddRef(v2);
    if ( !DestinationString.MaximumLength
      || ((v7 = *(_QWORD *)(*((_QWORD *)this + 6) + 8LL), (*(_BYTE *)(v7 + 10) & 5) == 0)
        ? (v8 = (wchar_t *)MmMapLockedPagesSpecifyCache((PMDL)v7, 0, MmCached, 0, 0, 0x40000010u))
        : (v8 = *(wchar_t **)(v7 + 24)),
          (DestinationString.Buffer = v8) != 0) )
    {
      v5 = CClfsLogCcb::AddArchiveRef((ULONG_PTR)v2, &DestinationString, v6, v6 + 1, &v13, Priority);
    }
    else
    {
      v5 = -1073741670;
    }
  }
  else
  {
    v5 = -1073741306;
  }
  if ( (*((_BYTE *)this + 16) & 1) != 0 )
  {
    v9 = *(struct _KEVENT **)(*((_QWORD *)this + 6) + 80LL);
    if ( v9 )
      KeSetEvent(v9, 0, 0);
  }
  if ( (*((_DWORD *)this + 4) & 4) == 0 )
  {
    *(_DWORD *)(*((_QWORD *)this + 6) + 48LL) = v5;
    *(_QWORD *)(*((_QWORD *)this + 6) + 56LL) = 2LL * v13;
  }
  if ( v2 )
    CClfsLogCcb::Release((volatile signed __int32 *)v2);
  return v5;
}

```

## disassembly

```asm
0x140043370  mov     rax, rsp
0x140043373  mov     [rax+18h], rbx
0x140043377  mov     [rax+20h], rsi
0x14004337b  mov     [rax+8], rcx
0x14004337f  push    rdi
0x140043380  push    r14
0x140043382  push    r15
0x140043384  sub     rsp, 50h
0x140043388  mov     rbx, rcx
0x14004338b  xor     r15d, r15d
0x14004338e  mov     [rax-28h], r15
0x140043392  mov     [rax-20h], r15
0x140043396  mov     [rax-38h], r15d
0x14004339a  mov     [rax+10h], r15d
0x14004339e  mov     esi, r15d
0x1400433a1  mov     [rax-30h], r15
0x1400433a5  mov     rax, [rcx+30h]
0x1400433a9  mov     rdi, [rax+0B8h]
0x1400433b0  cmp     dword ptr [rdi+10h], 10h
0x1400433b4  jnb     short loc_1400433C4
0x1400433b6  mov     edi, 0C0000206h
0x1400433bb  mov     [rsp+68h+var_38], edi
0x1400433bf  jmp     loc_14004346F
0x1400433c4  mov     r14, [rax+18h]
0x1400433c8  xor     edx, edx; SourceString
0x1400433ca  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1400433cf  call    cs:__imp_RtlInitUnicodeString
0x1400433d6  nop     dword ptr [rax+rax+00h]
0x1400433db  movzx   eax, word ptr [rdi+8]
0x1400433df  mov     [rsp+68h+DestinationString.MaximumLength], ax
0x1400433e4  mov     rax, [rdi+30h]
0x1400433e8  mov     rsi, [rax+20h]
0x1400433ec  mov     [rsp+68h+var_30], rsi
0x1400433f1  mov     rcx, rsi; this
0x1400433f4  call    ?AddRef@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::AddRef(void)
0x1400433f9  cmp     [rsp+68h+DestinationString.MaximumLength], r15w
0x1400433ff  jbe     short loc_14004344B
0x140043401  mov     rax, [rbx+30h]
0x140043405  mov     rcx, [rax+8]; MemoryDescriptorList
0x140043409  test    byte ptr [rcx+0Ah], 5
0x14004340d  jz      short loc_140043415
0x14004340f  mov     rax, [rcx+18h]
0x140043413  jmp     short loc_140043437
0x140043415  mov     dword ptr [rsp+68h+Priority], 40000010h; Priority
0x14004341d  mov     [rsp+68h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x140043422  xor     r9d, r9d; RequestedAddress
0x140043425  xor     edx, edx; AccessMode
0x140043427  lea     r8d, [r9+1]; CacheType
0x14004342b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140043432  nop     dword ptr [rax+rax+00h]
0x140043437  mov     [rsp+68h+DestinationString.Buffer], rax
0x14004343c  test    rax, rax
0x14004343f  jnz     short loc_14004344B
0x140043441  mov     edi, 0C000009Ah
0x140043446  jmp     loc_1400433BB
0x14004344b  lea     r9, [r14+8]; union _CLS_LSN *
0x14004344f  lea     rax, [rsp+68h+arg_8]
0x140043454  mov     qword ptr [rsp+68h+BugCheckOnFailure], rax; unsigned int *
0x140043459  mov     r8, r14; union _CLS_LSN *
0x14004345c  lea     rdx, [rsp+68h+DestinationString]; struct _UNICODE_STRING *
0x140043461  mov     rcx, rsi; BugCheckParameter3
0x140043464  call    ?AddArchiveRef@CClfsLogCcb@@QEAAJAEAU_UNICODE_STRING@@AEBT_CLS_LSN@@1AEAK2@Z; CClfsLogCcb::AddArchiveRef(_UNICODE_STRING &,_CLS_LSN const &,_CLS_LSN const &,ulong &,ulong &)
0x140043469  mov     edi, eax
0x14004346b  mov     [rsp+68h+var_38], eax
0x14004346f  test    byte ptr [rbx+10h], 1
0x140043473  jz      short loc_140043493
0x140043475  mov     rax, [rbx+30h]
0x140043479  mov     rcx, [rax+50h]; Event
0x14004347d  test    rcx, rcx
0x140043480  jz      short loc_140043493
0x140043482  xor     r8d, r8d; Wait
0x140043485  xor     edx, edx; Increment
0x140043487  call    cs:__imp_KeSetEvent
0x14004348e  nop     dword ptr [rax+rax+00h]
0x140043493  mov     eax, [rbx+10h]
0x140043496  test    al, 4
0x140043498  jnz     short loc_1400434B0
0x14004349a  mov     rax, [rbx+30h]
0x14004349e  mov     [rax+30h], edi
0x1400434a1  mov     edx, [rsp+68h+arg_8]
0x1400434a5  add     rdx, rdx
0x1400434a8  mov     rax, [rbx+30h]
0x1400434ac  mov     [rax+38h], rdx
0x1400434b0  test    rsi, rsi
0x1400434b3  jz      short loc_1400434BD
0x1400434b5  mov     rcx, rsi; Entry
0x1400434b8  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x1400434bd  mov     eax, edi
0x1400434bf  lea     r11, [rsp+68h+var_18]
0x1400434c4  mov     rbx, [r11+30h]
0x1400434c8  mov     rsi, [r11+38h]
0x1400434cc  mov     rsp, r11
0x1400434cf  pop     r15
0x1400434d1  pop     r14
0x1400434d3  pop     rdi
0x1400434d4  retn
0x14007f32c  push    rbx
0x14007f32e  push    rbp
0x14007f32f  sub     rsp, 38h
0x14007f333  mov     rbp, rdx
0x14007f336  xor     cl, cl
0x14007f338  mov     rbx, [rbp+70h]
0x14007f33c  test    byte ptr [rbx+10h], 1
0x14007f340  movzx   eax, cl
0x14007f343  mov     ecx, 1
0x14007f348  cmovnz  eax, ecx
0x14007f34b  test    al, al
0x14007f34d  jz      short loc_14007F370
0x14007f34f  mov     rax, [rbx+30h]
0x14007f353  cmp     qword ptr [rax+50h], 0
0x14007f358  jz      short loc_14007F370
0x14007f35a  xor     r8d, r8d; Wait
0x14007f35d  xor     edx, edx; Increment
0x14007f35f  mov     rcx, [rax+50h]; Event
0x14007f363  call    cs:__imp_KeSetEvent
0x14007f36a  nop     dword ptr [rax+rax+00h]
0x14007f36f  nop
0x14007f370  xor     cl, cl
0x14007f372  test    byte ptr [rbx+10h], 4
0x14007f376  movzx   eax, cl
0x14007f379  mov     ecx, 1
0x14007f37e  cmovnz  eax, ecx
0x14007f381  test    al, al
0x14007f383  jnz     short loc_14007F39D
0x14007f385  mov     rcx, [rbx+30h]
0x14007f389  mov     eax, [rbp+30h]
0x14007f38c  mov     [rcx+30h], eax
0x14007f38f  mov     ecx, [rbp+78h]
0x14007f392  add     rcx, rcx
0x14007f395  mov     rax, [rbx+30h]
0x14007f399  mov     [rax+38h], rcx
0x14007f39d  mov     rcx, [rbp+38h]; Entry
0x14007f3a1  test    rcx, rcx
0x14007f3a4  jz      short loc_14007F3B3
0x14007f3a6  call    ?Release@CClfsLogCcb@@QEAAKXZ; CClfsLogCcb::Release(void)
0x14007f3ab  mov     qword ptr [rbp+38h], 0
0x14007f3b3  add     rsp, 38h
0x14007f3b7  pop     rbp
0x14007f3b8  pop     rbx
0x14007f3b9  retn
```
