# RedirectSavedLink

- ea: `0x14000ff00`
- end: `0x14000ffb6`
- name: `RedirectSavedLink`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x140014fc0`

## callees

- `0x14000ff00`
- `0x140018cd0`
- `0x140018da0`
- `0x14001a2b0`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14000ff27`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14000ff27`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ff8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ff9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ff8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ff9e`

## pseudocode

```c
char __fastcall RedirectSavedLink(__int64 a1, UNICODE_STRING *a2, __int128 *a3)
{
  __int64 *v3; // rdi
  __int64 *v5; // rbx
  char v7; // si
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 *v11; // rax
  __int64 **v12; // rcx

  v3 = (__int64 *)(a1 + 16);
  v5 = *(__int64 **)(a1 + 16);
  v7 = 0;
  while ( v5 != v3 )
  {
    if ( RtlEqualUnicodeString(a2, (PCUNICODE_STRING)(v5 + 3), 1u) )
    {
      if ( v5 )
      {
        v11 = (__int64 *)*v5;
        if ( *(__int64 **)(*v5 + 8) != v5 || (v12 = (__int64 **)v5[1], *v12 != v5) )
          __fastfail(3u);
        *v12 = v11;
        v11[1] = (__int64)v12;
        MountmgrSetDLStringCase(a2, v8, v9);
        GlobalDeleteSymbolicLink((__int64)a2);
        GlobalCreateSymbolicLink(a2, a3);
        ExFreePoolWithTag((PVOID)v5[4], 0);
        ExFreePoolWithTag(v5, 0);
        return 1;
      }
      return v7;
    }
    v5 = (__int64 *)*v5;
  }
  return v7;
}

```

## disassembly

```asm
0x14000ff00  push    rbx
0x14000ff02  push    rbp
0x14000ff03  push    rsi
0x14000ff04  push    rdi
0x14000ff05  push    r14
0x14000ff07  sub     rsp, 20h
0x14000ff0b  lea     rdi, [rcx+10h]
0x14000ff0f  mov     r14, r8
0x14000ff12  mov     rbx, [rdi]
0x14000ff15  mov     rbp, rdx
0x14000ff18  xor     sil, sil
0x14000ff1b  jmp     short loc_14000FF3A
0x14000ff1d  lea     rdx, [rbx+18h]; String2
0x14000ff21  mov     r8b, 1; CaseInSensitive
0x14000ff24  mov     rcx, rbp; String1
0x14000ff27  call    cs:__imp_RtlEqualUnicodeString
0x14000ff2e  nop     dword ptr [rax+rax+00h]
0x14000ff33  test    al, al
0x14000ff35  jnz     short loc_14000FF4E
0x14000ff37  mov     rbx, [rbx]
0x14000ff3a  cmp     rbx, rdi
0x14000ff3d  jnz     short loc_14000FF1D
0x14000ff3f  mov     al, sil
0x14000ff42  add     rsp, 20h
0x14000ff46  pop     r14
0x14000ff48  pop     rdi
0x14000ff49  pop     rsi
0x14000ff4a  pop     rbp
0x14000ff4b  pop     rbx
0x14000ff4c  retn
0x14000ff4e  test    rbx, rbx
0x14000ff51  jz      short loc_14000FF3F
0x14000ff53  mov     rax, [rbx]
0x14000ff56  cmp     [rax+8], rbx
0x14000ff5a  jnz     short loc_14000FFAF
0x14000ff5c  mov     rcx, [rbx+8]
0x14000ff60  cmp     [rcx], rbx
0x14000ff63  jnz     short loc_14000FFAF
0x14000ff65  mov     [rcx], rax
0x14000ff68  mov     [rax+8], rcx
0x14000ff6c  mov     rcx, rbp
0x14000ff6f  call    MountmgrSetDLStringCase
0x14000ff74  mov     rcx, rbp
0x14000ff77  call    GlobalDeleteSymbolicLink
0x14000ff7c  mov     rdx, r14
0x14000ff7f  mov     rcx, rbp
0x14000ff82  call    GlobalCreateSymbolicLink
0x14000ff87  mov     rcx, [rbx+20h]; P
0x14000ff8b  xor     edx, edx; Tag
0x14000ff8d  call    cs:__imp_ExFreePoolWithTag
0x14000ff94  nop     dword ptr [rax+rax+00h]
0x14000ff99  xor     edx, edx; Tag
0x14000ff9b  mov     rcx, rbx; P
0x14000ff9e  call    cs:__imp_ExFreePoolWithTag
0x14000ffa5  nop     dword ptr [rax+rax+00h]
0x14000ffaa  mov     sil, 1
0x14000ffad  jmp     short loc_14000FF3F
0x14000ffaf  mov     ecx, 3
0x14000ffb4  int     29h; Win8: RtlFailFast(ecx)
```
