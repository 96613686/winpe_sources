# ndisAllocateConfigurationString

- ea: `0x14002b500`
- end: `0x14002b6ca`
- name: `ndisAllocateConfigurationString`
- size: `458`
- prototype: `__int64 __fastcall(char, char, char, PUNICODE_STRING Destination)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140048d20`

## callees

- `0x14002b500`
- `0x14002b980`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14002b66f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14002b66f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002b685`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002b69c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002b6ae`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002b685`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002b69c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002b6ae`
- `ntoskrnl!ExAllocatePool2` at `0x14002b602`
- `ntoskrnl!ExAllocatePool2` at `0x14002b602`

## pseudocode

```c
__int64 __fastcall ndisAllocateConfigurationString(
        const UNICODE_STRING *a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        PUNICODE_STRING Destination)
{
  const UNICODE_STRING *v6; // rdi
  unsigned __int16 Length; // cx
  __int16 v9; // r8
  unsigned __int16 v10; // r10
  unsigned int v11; // r9d
  unsigned __int16 v12; // ax
  unsigned int v13; // ecx
  unsigned __int16 v14; // ax
  unsigned __int16 v15; // r8
  wchar_t *Pool2; // rax
  unsigned int v17; // ebx
  char v19; // [rsp+30h] [rbp-48h]

  v6 = a2;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v19 = (char)a2;
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)a2,
      8,
      17,
      (struct _GUID *)&WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids,
      (char)a1,
      v19,
      (char)a3);
  }
  Length = a1->Length;
  v9 = -1;
  v10 = -1;
  if ( (unsigned __int16)(ndisParameterStr.Length + Length) >= Length )
    v10 = ndisParameterStr.Length + Length;
  v11 = (unsigned __int16)(ndisParameterStr.Length + Length) < Length ? 0xC0000095 : 0;
  Destination->MaximumLength = v10;
  if ( v6 )
  {
    LODWORD(a2) = 0xFFFF;
    v12 = a3->Length + v10;
    if ( v12 >= v10 )
      LOWORD(a2) = a3->Length + v10;
    Destination->MaximumLength = (unsigned __int16)a2;
    v13 = v11 | (v12 < v10 ? 0xC0000095 : 0);
    v14 = v6->Length + (_WORD)a2;
    if ( v14 >= (unsigned __int16)a2 )
      v9 = v6->Length + (_WORD)a2;
    v11 = v13 | (v14 < (unsigned __int16)a2 ? 0xC0000095 : 0);
  }
  else
  {
    v9 = v10;
  }
  v15 = v9 + 2;
  Destination->Buffer = 0;
  Destination->MaximumLength = v15;
  Destination->Length = 0;
  if ( !v11 && (Pool2 = (wchar_t *)ExAllocatePool2(64, v15, 538985550), (Destination->Buffer = Pool2) != 0) )
  {
    RtlCopyUnicodeString(Destination, a1);
    RtlAppendUnicodeStringToString(Destination, &ndisParameterStr);
    if ( v6 )
    {
      RtlAppendUnicodeStringToString(Destination, a3);
      RtlAppendUnicodeStringToString(Destination, v6);
    }
    v17 = 0;
  }
  else
  {
    v17 = -1073741670;
  }
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)a2,
      1,
      18,
      (struct _GUID *)&WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids,
      (char)a1,
      (char)v6,
      (char)a3);
  }
  return v17;
}

```

## disassembly

```asm
0x14002b500  push    rbx
0x14002b502  push    rbp
0x14002b503  push    rsi
0x14002b504  push    rdi
0x14002b505  push    r14
0x14002b507  push    r15
0x14002b509  sub     rsp, 48h
0x14002b50d  mov     rbx, r9
0x14002b510  mov     rbp, r8
0x14002b513  mov     rdi, rdx
0x14002b516  mov     rsi, rcx
0x14002b519  lea     r14, WPP_RECORDER_INITIALIZED
0x14002b520  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14002b527  lea     r15, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x14002b52e  jz      short loc_14002B562
0x14002b530  mov     qword ptr [rsp+78h+var_40], r8; char
0x14002b535  mov     r9d, 11h; int
0x14002b53b  mov     qword ptr [rsp+78h+var_48], rdx; char
0x14002b540  mov     r8d, 8; int
0x14002b546  mov     qword ptr [rsp+78h+var_50], rcx; char
0x14002b54b  mov     dl, 4; int
0x14002b54d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b554  mov     [rsp+78h+var_58], r15; struct _GUID *
0x14002b559  mov     rcx, [rcx+40h]; int
0x14002b55d  call    WPP_RECORDER_SF_qqq
0x14002b562  movzx   ecx, word ptr [rsi]
0x14002b565  mov     r8d, 0FFFFh
0x14002b56b  movzx   eax, cx
0x14002b56e  movzx   r10d, r8w
0x14002b572  add     ax, cs:?ndisParameterStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisParameterStr ...
0x14002b579  cmp     ax, cx
0x14002b57c  cmovnb  r10w, ax
0x14002b581  sbb     r9d, r9d
0x14002b584  and     r9d, 0C0000095h
0x14002b58b  mov     [rbx+2], r10w
0x14002b590  test    rdi, rdi
0x14002b593  jz      loc_14002B6C1
0x14002b599  movzx   edx, r8w
0x14002b59d  movzx   eax, r10w
0x14002b5a1  add     ax, [rbp+0]
0x14002b5a5  cmp     ax, r10w
0x14002b5a9  cmovnb  dx, ax
0x14002b5ad  sbb     ecx, ecx
0x14002b5af  and     ecx, 0C0000095h
0x14002b5b5  mov     [rbx+2], dx
0x14002b5b9  or      ecx, r9d
0x14002b5bc  movzx   eax, dx
0x14002b5bf  add     ax, [rdi]
0x14002b5c2  cmp     ax, dx
0x14002b5c5  cmovnb  r8w, ax
0x14002b5ca  sbb     r9d, r9d
0x14002b5cd  and     r9d, 0C0000095h
0x14002b5d4  or      r9d, ecx
0x14002b5d7  add     r8w, 2
0x14002b5dc  mov     qword ptr [rbx+8], 0
0x14002b5e4  xor     eax, eax
0x14002b5e6  mov     [rbx+2], r8w
0x14002b5eb  mov     [rbx], ax
0x14002b5ee  test    r9d, r9d
0x14002b5f1  jnz     short loc_14002B617
0x14002b5f3  movzx   edx, r8w
0x14002b5f7  mov     ecx, 40h ; '@'
0x14002b5fc  mov     r8d, 2020444Eh
0x14002b602  call    cs:__imp_ExAllocatePool2
0x14002b609  nop     dword ptr [rax+rax+00h]
0x14002b60e  mov     [rbx+8], rax
0x14002b612  test    rax, rax
0x14002b615  jnz     short loc_14002B669
0x14002b617  mov     ebx, 0C000009Ah
0x14002b61c  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14002b623  jnz     short loc_14002B635
0x14002b625  mov     eax, ebx
0x14002b627  add     rsp, 48h
0x14002b62b  pop     r15
0x14002b62d  pop     r14
0x14002b62f  pop     rdi
0x14002b630  pop     rsi
0x14002b631  pop     rbp
0x14002b632  pop     rbx
0x14002b633  retn
0x14002b635  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b63c  mov     r9d, 12h; int
0x14002b642  mov     qword ptr [rsp+78h+var_40], rbp; char
0x14002b647  mov     r8d, 1; int
0x14002b64d  mov     qword ptr [rsp+78h+var_48], rdi; char
0x14002b652  mov     dl, 4; int
0x14002b654  mov     qword ptr [rsp+78h+var_50], rsi; char
0x14002b659  mov     rcx, [rcx+40h]; int
0x14002b65d  mov     [rsp+78h+var_58], r15; struct _GUID *
0x14002b662  call    WPP_RECORDER_SF_qqq
0x14002b667  jmp     short loc_14002B625
0x14002b669  mov     rdx, rsi; SourceString
0x14002b66c  mov     rcx, rbx; DestinationString
0x14002b66f  call    cs:__imp_RtlCopyUnicodeString
0x14002b676  nop     dword ptr [rax+rax+00h]
0x14002b67b  lea     rdx, ?ndisParameterStr@@3U_UNICODE_STRING@@A; Source
0x14002b682  mov     rcx, rbx; Destination
0x14002b685  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002b68c  nop     dword ptr [rax+rax+00h]
0x14002b691  test    rdi, rdi
0x14002b694  jz      short loc_14002B6BA
0x14002b696  mov     rdx, rbp; Source
0x14002b699  mov     rcx, rbx; Destination
0x14002b69c  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002b6a3  nop     dword ptr [rax+rax+00h]
0x14002b6a8  mov     rdx, rdi; Source
0x14002b6ab  mov     rcx, rbx; Destination
0x14002b6ae  call    cs:__imp_RtlAppendUnicodeStringToString
0x14002b6b5  nop     dword ptr [rax+rax+00h]
0x14002b6ba  xor     ebx, ebx
0x14002b6bc  jmp     loc_14002B61C
0x14002b6c1  movzx   r8d, r10w
0x14002b6c5  jmp     loc_14002B5D7
```
