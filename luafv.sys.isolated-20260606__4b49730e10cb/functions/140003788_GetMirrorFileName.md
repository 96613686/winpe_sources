# GetMirrorFileName

- ea: `0x140003788`
- end: `0x140003933`
- name: `GetMirrorFileName`
- size: `427`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140003fb8`
- `0x140004390`

## callees

- `0x140003788`
- `0x14001b6a0`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400037c6`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400037c6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003868`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003868`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003854`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400038ff`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140003854`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400038ff`

## pseudocode

```c
__int64 __fastcall GetMirrorFileName(_QWORD *a1, __int64 a2, const UNICODE_STRING *a3, struct _UNICODE_STRING *a4)
{
  UNICODE_STRING v6; // xmm0
  __int64 v8; // r14
  USHORT v9; // dx
  __int64 v10; // rax
  unsigned int v11; // edx
  WCHAR *Pool; // rax
  NTSTATUS appended; // ebx
  UNICODE_STRING *p_Source; // rdx
  unsigned int v15; // edx
  __int64 v17; // rdx
  PWSTR Buffer; // rax
  __int64 v19; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-30h] BYREF
  UNICODE_STRING Source; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING v22; // [rsp+40h] [rbp-10h] BYREF

  v22 = 0;
  v6 = *a3;
  DestinationString = 0;
  v8 = *a1;
  Source = v6;
  if ( RtlPrefixUnicodeString((PCUNICODE_STRING)(v8 + 152), a3, 1u) )
  {
    Source.Buffer += (unsigned __int64)*(unsigned __int16 *)(v8 + 152) >> 1;
    Source.Length -= *(_WORD *)(v8 + 152);
    v9 = Source.MaximumLength - *(_WORD *)(v8 + 152);
    DestinationString.Length = 0;
    v10 = a1[1];
    Source.MaximumLength = v9;
    v11 = (unsigned __int16)(*(_WORD *)(v10 + 152) + v9);
    DestinationString.MaximumLength = v11;
    Pool = (WCHAR *)LuafvAllocatePool(1, v11, 2);
    DestinationString.Buffer = Pool;
    if ( !Pool )
    {
      appended = -1073741670;
      goto LABEL_11;
    }
    RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(a1[1] + 152LL));
    p_Source = &Source;
  }
  else
  {
    v15 = (unsigned __int16)(a3->MaximumLength + *(_WORD *)(a1[1] + 122LL) - *(_WORD *)(*a1 + 122LL));
    DestinationString.Length = 0;
    DestinationString.MaximumLength = v15;
    DestinationString.Buffer = (PWSTR)LuafvAllocatePool(1, v15, 2);
    if ( !DestinationString.Buffer )
      return 3221225626LL;
    v17 = *a1;
    Buffer = a3->Buffer;
    v22 = *a3;
    v22.Buffer = &Buffer[(unsigned __int64)*(unsigned __int16 *)(v17 + 120) >> 1];
    v22.Length -= *(_WORD *)(v17 + 120);
    LOWORD(Buffer) = *(_WORD *)(v17 + 120);
    v19 = a1[1];
    v22.MaximumLength -= (unsigned __int16)Buffer;
    RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(v19 + 120));
    p_Source = &v22;
  }
  appended = RtlAppendUnicodeStringToString(&DestinationString, p_Source);
  if ( appended < 0 )
  {
    Pool = DestinationString.Buffer;
LABEL_11:
    if ( Pool )
      LuafvFreePool(Pool);
    return (unsigned int)appended;
  }
  *a4 = DestinationString;
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140003788  push    rbp
0x14000378a  push    rbx
0x14000378b  push    rsi
0x14000378c  push    rdi
0x14000378d  push    r14
0x14000378f  mov     rbp, rsp
0x140003792  sub     rsp, 50h
0x140003796  xorps   xmm0, xmm0
0x140003799  mov     rsi, r8
0x14000379c  movups  [rbp+var_10], xmm0
0x1400037a0  mov     rbx, rcx
0x1400037a3  mov     rdx, rsi; String2
0x1400037a6  movups  xmm0, xmmword ptr [r8]
0x1400037aa  mov     r8b, 1; CaseInSensitive
0x1400037ad  mov     rdi, r9
0x1400037b0  xorps   xmm1, xmm1
0x1400037b3  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x1400037b7  mov     r14, [rcx]
0x1400037ba  movdqu  xmmword ptr [rbp+Source.Length], xmm0
0x1400037bf  lea     rcx, [r14+98h]; String1
0x1400037c6  call    cs:__imp_RtlPrefixUnicodeString
0x1400037cd  nop     dword ptr [rax+rax+00h]
0x1400037d2  mov     r8b, 2
0x1400037d5  test    al, al
0x1400037d7  jz      loc_14000388B
0x1400037dd  movzx   ecx, word ptr [r14+98h]
0x1400037e5  mov     rax, [rbp+Source.Buffer]
0x1400037e9  movzx   edx, [rbp+Source.MaximumLength]
0x1400037ed  shr     rcx, 1
0x1400037f0  lea     rcx, [rax+rcx*2]
0x1400037f4  mov     [rbp+Source.Buffer], rcx
0x1400037f8  mov     ecx, 1
0x1400037fd  movzx   eax, word ptr [r14+98h]
0x140003805  sub     [rbp+Source.Length], ax
0x140003809  xor     eax, eax
0x14000380b  sub     dx, [r14+98h]
0x140003813  mov     [rbp+DestinationString.Length], ax
0x140003817  mov     rax, [rbx+8]
0x14000381b  mov     [rbp+Source.MaximumLength], dx
0x14000381f  add     dx, [rax+98h]
0x140003826  movzx   edx, dx
0x140003829  mov     [rbp+DestinationString.MaximumLength], dx
0x14000382d  call    LuafvAllocatePool
0x140003832  mov     [rbp+DestinationString.Buffer], rax
0x140003836  test    rax, rax
0x140003839  jnz     short loc_140003845
0x14000383b  mov     ebx, 0C000009Ah
0x140003840  jmp     loc_140003918
0x140003845  mov     rdx, [rbx+8]
0x140003849  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000384d  add     rdx, 98h; SourceString
0x140003854  call    cs:__imp_RtlCopyUnicodeString
0x14000385b  nop     dword ptr [rax+rax+00h]
0x140003860  lea     rdx, [rbp+Source]; Source
0x140003864  lea     rcx, [rbp+DestinationString]; Destination
0x140003868  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000386f  nop     dword ptr [rax+rax+00h]
0x140003874  mov     ebx, eax
0x140003876  test    eax, eax
0x140003878  js      loc_140003914
0x14000387e  movups  xmm0, xmmword ptr [rbp+DestinationString.Length]
0x140003882  movdqu  xmmword ptr [rdi], xmm0
0x140003886  jmp     loc_140003925
0x14000388b  mov     rax, [rbx]
0x14000388e  mov     rdx, [rbx+8]
0x140003892  movzx   ecx, word ptr [rax+7Ah]
0x140003896  movzx   eax, word ptr [rdx+7Ah]
0x14000389a  sub     ax, cx
0x14000389d  add     ax, [rsi+2]
0x1400038a1  movzx   edx, ax
0x1400038a4  xor     eax, eax
0x1400038a6  mov     [rbp+DestinationString.Length], ax
0x1400038aa  mov     [rbp+DestinationString.MaximumLength], dx
0x1400038ae  lea     ecx, [rax+1]
0x1400038b1  call    LuafvAllocatePool
0x1400038b6  mov     [rbp+DestinationString.Buffer], rax
0x1400038ba  test    rax, rax
0x1400038bd  jnz     short loc_1400038C6
0x1400038bf  mov     eax, 0C000009Ah
0x1400038c4  jmp     short loc_140003927
0x1400038c6  mov     rdx, [rbx]
0x1400038c9  mov     rax, [rsi+8]
0x1400038cd  movups  xmm0, xmmword ptr [rsi]
0x1400038d0  movups  [rbp+var_10], xmm0
0x1400038d4  movzx   ecx, word ptr [rdx+78h]
0x1400038d8  shr     rcx, 1
0x1400038db  lea     rcx, [rax+rcx*2]
0x1400038df  mov     qword ptr [rbp+var_10+8], rcx
0x1400038e3  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400038e7  movzx   eax, word ptr [rdx+78h]
0x1400038eb  sub     word ptr [rbp+var_10], ax
0x1400038ef  movzx   eax, word ptr [rdx+78h]
0x1400038f3  mov     rdx, [rbx+8]
0x1400038f7  sub     word ptr [rbp+var_10+2], ax
0x1400038fb  add     rdx, 78h ; 'x'; SourceString
0x1400038ff  call    cs:__imp_RtlCopyUnicodeString
0x140003906  nop     dword ptr [rax+rax+00h]
0x14000390b  lea     rdx, [rbp+var_10]
0x14000390f  jmp     loc_140003864
0x140003914  mov     rax, [rbp+DestinationString.Buffer]
0x140003918  test    rax, rax
0x14000391b  jz      short loc_140003925
0x14000391d  mov     rcx, rax
0x140003920  call    LuafvFreePool
0x140003925  mov     eax, ebx
0x140003927  add     rsp, 50h
0x14000392b  pop     r14
0x14000392d  pop     rdi
0x14000392e  pop     rsi
0x14000392f  pop     rbx
0x140003930  pop     rbp
0x140003931  retn
```
