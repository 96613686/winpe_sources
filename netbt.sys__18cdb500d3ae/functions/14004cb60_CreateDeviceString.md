# CreateDeviceString

- ea: `0x14004cb60`
- end: `0x14004cc40`
- name: `CreateDeviceString`
- size: `224`
- prototype: `__int64 __fastcall(PCWSTR Source, PUNICODE_STRING Destination)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14004bf14`
- `0x14004c4a8`

## callees

- `0x14004cb60`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004cbe5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004cbfd`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004cbe5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14004cbfd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004cc32`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004cc32`
- `ntoskrnl!ExAllocatePool2` at `0x14004cbbe`
- `ntoskrnl!ExAllocatePool2` at `0x14004cbbe`

## pseudocode

```c
NTSTATUS __fastcall CreateDeviceString(PCWSTR Source, PUNICODE_STRING Destination)
{
  const WCHAR *v2; // rbx
  __int64 v5; // rax
  __int64 v6; // rdx
  unsigned __int16 v7; // r14
  wchar_t *Pool2; // rax
  wchar_t *v9; // rsi
  NTSTATUS appended; // ebx
  NTSTATUS result; // eax

  v2 = L"\\Device\\Streams\\";
  if ( qword_1400394E0 )
    v2 = (const WCHAR *)qword_1400394E0;
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( Source[v6] );
  do
    ++v5;
  while ( v2[v5] );
  v7 = 2 * (v6 + v5) + 2;
  Pool2 = (wchar_t *)ExAllocatePool2(64, (unsigned int)(2 * (v6 + v5) + 2), 1853121102);
  v9 = Pool2;
  if ( !Pool2 )
  {
    appended = -1073741670;
LABEL_11:
    *(_DWORD *)&Destination->Length = 0;
    result = appended;
    Destination->Buffer = 0;
    return result;
  }
  Destination->MaximumLength = v7;
  Destination->Length = 0;
  Destination->Buffer = Pool2;
  appended = RtlAppendUnicodeToString(Destination, v2);
  if ( appended < 0 || (result = RtlAppendUnicodeToString(Destination, Source), appended = result, result < 0) )
  {
    ExFreePoolWithTag(v9, 0);
    goto LABEL_11;
  }
  return result;
}

```

## disassembly

```asm
0x14004cb60  push    rbx
0x14004cb62  push    rbp
0x14004cb63  push    rsi
0x14004cb64  push    rdi
0x14004cb65  push    r14
0x14004cb67  push    r15
0x14004cb69  sub     rsp, 28h
0x14004cb6d  mov     rax, cs:qword_1400394E0
0x14004cb74  lea     rbx, aDeviceStreams; "\\Device\\Streams\\"
0x14004cb7b  xor     r15d, r15d
0x14004cb7e  mov     rdi, rdx
0x14004cb81  test    rax, rax
0x14004cb84  mov     rbp, rcx
0x14004cb87  cmovnz  rbx, rax
0x14004cb8b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14004cb8f  mov     rdx, rax
0x14004cb92  inc     rdx
0x14004cb95  cmp     [rcx+rdx*2], r15w
0x14004cb9a  jnz     short loc_14004CB92
0x14004cb9c  inc     rax
0x14004cb9f  cmp     [rbx+rax*2], r15w
0x14004cba4  jnz     short loc_14004CB9C
0x14004cba6  add     eax, edx
0x14004cba8  mov     ecx, 40h ; '@'
0x14004cbad  mov     r8d, 6E74624Eh
0x14004cbb3  lea     r14d, ds:2[rax*2]
0x14004cbbb  mov     edx, r14d
0x14004cbbe  call    cs:__imp_ExAllocatePool2
0x14004cbc5  nop     dword ptr [rax+rax+00h]
0x14004cbca  mov     rsi, rax
0x14004cbcd  test    rax, rax
0x14004cbd0  jz      short loc_14004CC1D
0x14004cbd2  mov     rdx, rbx; Source
0x14004cbd5  mov     [rdi+2], r14w
0x14004cbda  mov     rcx, rdi; Destination
0x14004cbdd  mov     [rdi], r15w
0x14004cbe1  mov     [rdi+8], rax
0x14004cbe5  call    cs:__imp_RtlAppendUnicodeToString
0x14004cbec  nop     dword ptr [rax+rax+00h]
0x14004cbf1  mov     ebx, eax
0x14004cbf3  test    eax, eax
0x14004cbf5  js      short loc_14004CC2D
0x14004cbf7  mov     rdx, rbp; Source
0x14004cbfa  mov     rcx, rdi; Destination
0x14004cbfd  call    cs:__imp_RtlAppendUnicodeToString
0x14004cc04  nop     dword ptr [rax+rax+00h]
0x14004cc09  mov     ebx, eax
0x14004cc0b  test    eax, eax
0x14004cc0d  js      short loc_14004CC2D
0x14004cc0f  add     rsp, 28h
0x14004cc13  pop     r15
0x14004cc15  pop     r14
0x14004cc17  pop     rdi
0x14004cc18  pop     rsi
0x14004cc19  pop     rbp
0x14004cc1a  pop     rbx
0x14004cc1b  retn
0x14004cc1d  mov     ebx, 0C000009Ah
0x14004cc22  mov     [rdi], r15d
0x14004cc25  mov     eax, ebx
0x14004cc27  mov     [rdi+8], r15
0x14004cc2b  jmp     short loc_14004CC0F
0x14004cc2d  xor     edx, edx; Tag
0x14004cc2f  mov     rcx, rsi; P
0x14004cc32  call    cs:__imp_ExFreePoolWithTag
0x14004cc39  nop     dword ptr [rax+rax+00h]
0x14004cc3e  jmp     short loc_14004CC22
```
