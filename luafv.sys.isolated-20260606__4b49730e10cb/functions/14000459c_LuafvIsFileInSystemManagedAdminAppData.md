# LuafvIsFileInSystemManagedAdminAppData

- ea: `0x14000459c`
- end: `0x1400046bc`
- name: `LuafvIsFileInSystemManagedAdminAppData`
- size: `288`
- prototype: `__int64 __fastcall(__int64, const UNICODE_STRING *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400258a0`

## callees

- `0x14000459c`
- `0x140005798`
- `0x14001b6a0`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000466d`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x14000466d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140004653`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140004653`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000463c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000463c`

## pseudocode

```c
__int64 __fastcall LuafvIsFileInSystemManagedAdminAppData(__int64 a1, const UNICODE_STRING *a2, __int64 a3)
{
  unsigned int v4; // esi
  const UNICODE_STRING *v5; // rdi
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF
  __int128 v8; // [rsp+30h] [rbp-28h] BYREF
  __int128 v9; // [rsp+40h] [rbp-18h] BYREF

  v4 = 0;
  DestinationString = 0;
  v9 = 0;
  v8 = 0;
  if ( a2 && a2->Length && a2->Buffer )
  {
    if ( *(_QWORD *)(a1 + 128) )
    {
      v5 = (const UNICODE_STRING *)(a1 + 120);
    }
    else
    {
      if ( (int)GetUserProfilePaths((struct _UNICODE_STRING *)(a1 + 88), (__int64)&v9, (__int64)&v8) < 0 )
        goto LABEL_12;
      v5 = (const UNICODE_STRING *)&v8;
    }
    LOBYTE(a3) = 1;
    DestinationString.MaximumLength = v5->MaximumLength + 18;
    DestinationString.Buffer = (PWSTR)LuafvAllocatePool(1, DestinationString.MaximumLength, a3);
    if ( !DestinationString.Buffer )
      goto LABEL_14;
    RtlCopyUnicodeString(&DestinationString, v5);
    if ( RtlAppendUnicodeStringToString(&DestinationString, &AppData) >= 0
      && RtlPrefixUnicodeString(&DestinationString, a2, 1u) )
    {
      v4 = 1;
    }
  }
LABEL_12:
  if ( DestinationString.Buffer )
    LuafvFreePool(DestinationString.Buffer);
LABEL_14:
  if ( *((_QWORD *)&v9 + 1) )
    LuafvFreePool(*((_QWORD *)&v9 + 1));
  if ( *((_QWORD *)&v8 + 1) )
    LuafvFreePool(*((_QWORD *)&v8 + 1));
  return v4;
}

```

## disassembly

```asm
0x14000459c  push    rbp
0x14000459e  push    rbx
0x14000459f  push    rsi
0x1400045a0  push    rdi
0x1400045a1  push    r14
0x1400045a3  push    r15
0x1400045a5  mov     rbp, rsp
0x1400045a8  sub     rsp, 58h
0x1400045ac  xor     r14d, r14d
0x1400045af  xorps   xmm0, xmm0
0x1400045b2  xorps   xmm1, xmm1
0x1400045b5  mov     rbx, rdx
0x1400045b8  mov     esi, r14d
0x1400045bb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400045bf  movups  [rbp+var_18], xmm1
0x1400045c3  movups  [rbp+var_28], xmm0
0x1400045c7  test    rdx, rdx
0x1400045ca  jz      loc_14000467F
0x1400045d0  cmp     [rdx], r14w
0x1400045d4  jbe     loc_14000467F
0x1400045da  cmp     [rdx+8], r14
0x1400045de  jz      loc_14000467F
0x1400045e4  cmp     [rcx+80h], r14
0x1400045eb  jz      short loc_1400045F3
0x1400045ed  lea     rdi, [rcx+78h]
0x1400045f1  jmp     short loc_14000460C
0x1400045f3  add     rcx, 58h ; 'X'
0x1400045f7  lea     r8, [rbp+var_28]
0x1400045fb  lea     rdx, [rbp+var_18]
0x1400045ff  call    GetUserProfilePaths
0x140004604  test    eax, eax
0x140004606  js      short loc_14000467F
0x140004608  lea     rdi, [rbp+var_28]
0x14000460c  movzx   eax, word ptr [rdi+2]
0x140004610  mov     r15d, 1
0x140004616  add     ax, 12h
0x14000461a  mov     r8b, r15b
0x14000461d  movzx   edx, ax
0x140004620  mov     ecx, r15d
0x140004623  mov     [rbp+DestinationString.MaximumLength], dx
0x140004627  call    LuafvAllocatePool
0x14000462c  mov     [rbp+DestinationString.Buffer], rax
0x140004630  test    rax, rax
0x140004633  jz      short loc_140004690
0x140004635  mov     rdx, rdi; SourceString
0x140004638  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000463c  call    cs:__imp_RtlCopyUnicodeString
0x140004643  nop     dword ptr [rax+rax+00h]
0x140004648  lea     rdx, AppData; Source
0x14000464f  lea     rcx, [rbp+DestinationString]; Destination
0x140004653  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000465a  nop     dword ptr [rax+rax+00h]
0x14000465f  test    eax, eax
0x140004661  js      short loc_14000467F
0x140004663  mov     r8b, r15b; CaseInSensitive
0x140004666  lea     rcx, [rbp+DestinationString]; String1
0x14000466a  mov     rdx, rbx; String2
0x14000466d  call    cs:__imp_RtlPrefixUnicodeString
0x140004674  nop     dword ptr [rax+rax+00h]
0x140004679  test    al, al
0x14000467b  cmovnz  esi, r15d
0x14000467f  mov     rax, [rbp+DestinationString.Buffer]
0x140004683  test    rax, rax
0x140004686  jz      short loc_140004690
0x140004688  mov     rcx, rax
0x14000468b  call    LuafvFreePool
0x140004690  mov     rcx, qword ptr [rbp+var_18+8]
0x140004694  test    rcx, rcx
0x140004697  jz      short loc_14000469E
0x140004699  call    LuafvFreePool
0x14000469e  mov     rcx, qword ptr [rbp+var_28+8]
0x1400046a2  test    rcx, rcx
0x1400046a5  jz      short loc_1400046AC
0x1400046a7  call    LuafvFreePool
0x1400046ac  mov     eax, esi
0x1400046ae  add     rsp, 58h
0x1400046b2  pop     r15
0x1400046b4  pop     r14
0x1400046b6  pop     rdi
0x1400046b7  pop     rsi
0x1400046b8  pop     rbx
0x1400046b9  pop     rbp
0x1400046ba  retn
```
