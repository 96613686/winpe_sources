# ndisAllocateConfigurationString

- ea: `0x14001f5b0`
- end: `0x14001f77a`
- name: `ndisAllocateConfigurationString`
- size: `458`
- prototype: `__int64 __fastcall(char, char, char, PUNICODE_STRING Destination)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14004d6a0`

## callees

- `0x14001f5b0`
- `0x14001fa30`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14001f71f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001f71f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001f735`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001f74c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001f75e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001f735`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001f74c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001f75e`
- `ntoskrnl!ExAllocatePool2` at `0x14001f6b2`
- `ntoskrnl!ExAllocatePool2` at `0x14001f6b2`

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
0x14001f5b0  push    rbx
0x14001f5b2  push    rbp
0x14001f5b3  push    rsi
0x14001f5b4  push    rdi
0x14001f5b5  push    r14
0x14001f5b7  push    r15
0x14001f5b9  sub     rsp, 48h
0x14001f5bd  mov     rbx, r9
0x14001f5c0  mov     rbp, r8
0x14001f5c3  mov     rdi, rdx
0x14001f5c6  mov     rsi, rcx
0x14001f5c9  lea     r14, WPP_RECORDER_INITIALIZED
0x14001f5d0  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001f5d7  lea     r15, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x14001f5de  jz      short loc_14001F612
0x14001f5e0  mov     qword ptr [rsp+78h+var_40], r8; char
0x14001f5e5  mov     r9d, 11h; int
0x14001f5eb  mov     qword ptr [rsp+78h+var_48], rdx; char
0x14001f5f0  mov     r8d, 8; int
0x14001f5f6  mov     qword ptr [rsp+78h+var_50], rcx; char
0x14001f5fb  mov     dl, 4; int
0x14001f5fd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f604  mov     [rsp+78h+var_58], r15; struct _GUID *
0x14001f609  mov     rcx, [rcx+40h]; int
0x14001f60d  call    WPP_RECORDER_SF_qqq
0x14001f612  movzx   ecx, word ptr [rsi]
0x14001f615  mov     r8d, 0FFFFh
0x14001f61b  movzx   eax, cx
0x14001f61e  movzx   r10d, r8w
0x14001f622  add     ax, cs:?ndisParameterStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisParameterStr ...
0x14001f629  cmp     ax, cx
0x14001f62c  cmovnb  r10w, ax
0x14001f631  sbb     r9d, r9d
0x14001f634  and     r9d, 0C0000095h
0x14001f63b  mov     [rbx+2], r10w
0x14001f640  test    rdi, rdi
0x14001f643  jz      loc_14001F771
0x14001f649  movzx   edx, r8w
0x14001f64d  movzx   eax, r10w
0x14001f651  add     ax, [rbp+0]
0x14001f655  cmp     ax, r10w
0x14001f659  cmovnb  dx, ax
0x14001f65d  sbb     ecx, ecx
0x14001f65f  and     ecx, 0C0000095h
0x14001f665  mov     [rbx+2], dx
0x14001f669  or      ecx, r9d
0x14001f66c  movzx   eax, dx
0x14001f66f  add     ax, [rdi]
0x14001f672  cmp     ax, dx
0x14001f675  cmovnb  r8w, ax
0x14001f67a  sbb     r9d, r9d
0x14001f67d  and     r9d, 0C0000095h
0x14001f684  or      r9d, ecx
0x14001f687  add     r8w, 2
0x14001f68c  mov     qword ptr [rbx+8], 0
0x14001f694  xor     eax, eax
0x14001f696  mov     [rbx+2], r8w
0x14001f69b  mov     [rbx], ax
0x14001f69e  test    r9d, r9d
0x14001f6a1  jnz     short loc_14001F6C7
0x14001f6a3  movzx   edx, r8w
0x14001f6a7  mov     ecx, 40h ; '@'
0x14001f6ac  mov     r8d, 2020444Eh
0x14001f6b2  call    cs:__imp_ExAllocatePool2
0x14001f6b9  nop     dword ptr [rax+rax+00h]
0x14001f6be  mov     [rbx+8], rax
0x14001f6c2  test    rax, rax
0x14001f6c5  jnz     short loc_14001F719
0x14001f6c7  mov     ebx, 0C000009Ah
0x14001f6cc  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14001f6d3  jnz     short loc_14001F6E5
0x14001f6d5  mov     eax, ebx
0x14001f6d7  add     rsp, 48h
0x14001f6db  pop     r15
0x14001f6dd  pop     r14
0x14001f6df  pop     rdi
0x14001f6e0  pop     rsi
0x14001f6e1  pop     rbp
0x14001f6e2  pop     rbx
0x14001f6e3  retn
0x14001f6e5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f6ec  mov     r9d, 12h; int
0x14001f6f2  mov     qword ptr [rsp+78h+var_40], rbp; char
0x14001f6f7  mov     r8d, 1; int
0x14001f6fd  mov     qword ptr [rsp+78h+var_48], rdi; char
0x14001f702  mov     dl, 4; int
0x14001f704  mov     qword ptr [rsp+78h+var_50], rsi; char
0x14001f709  mov     rcx, [rcx+40h]; int
0x14001f70d  mov     [rsp+78h+var_58], r15; struct _GUID *
0x14001f712  call    WPP_RECORDER_SF_qqq
0x14001f717  jmp     short loc_14001F6D5
0x14001f719  mov     rdx, rsi; SourceString
0x14001f71c  mov     rcx, rbx; DestinationString
0x14001f71f  call    cs:__imp_RtlCopyUnicodeString
0x14001f726  nop     dword ptr [rax+rax+00h]
0x14001f72b  lea     rdx, ?ndisParameterStr@@3U_UNICODE_STRING@@A; Source
0x14001f732  mov     rcx, rbx; Destination
0x14001f735  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001f73c  nop     dword ptr [rax+rax+00h]
0x14001f741  test    rdi, rdi
0x14001f744  jz      short loc_14001F76A
0x14001f746  mov     rdx, rbp; Source
0x14001f749  mov     rcx, rbx; Destination
0x14001f74c  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001f753  nop     dword ptr [rax+rax+00h]
0x14001f758  mov     rdx, rdi; Source
0x14001f75b  mov     rcx, rbx; Destination
0x14001f75e  call    cs:__imp_RtlAppendUnicodeStringToString
0x14001f765  nop     dword ptr [rax+rax+00h]
0x14001f76a  xor     ebx, ebx
0x14001f76c  jmp     loc_14001F6CC
0x14001f771  movzx   r8d, r10w
0x14001f775  jmp     loc_14001F687
```
