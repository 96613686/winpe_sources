# RtlFormatCurrentUserKeyPath

- ea: `0x1800152b0`
- end: `0x180015485`
- name: `RtlFormatCurrentUserKeyPath`
- size: `469`
- prototype: `__int64 __fastcall(PUNICODE_STRING UnicodeString)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180010770`
- `0x18001d4b0`
- `0x180038ed4`

## callees

- `0x1800152b0`
- `0x180015710`
- `0x180015af0`
- `0x180021fd0`
- `0x180035fd0`
- `0x18012d320`
- `0x18015ef00`
- `0x180162810`
- `0x180164280`

## string_xrefs

- `0x180015373`: `\REGISTRY\USER\`
- `0x1800153a9`: `\REGISTRY\USER\`

## pseudocode

```c
__int64 __fastcall RtlFormatCurrentUserKeyPath(PUNICODE_STRING UnicodeString)
{
  __int64 result; // rax
  unsigned __int8 *v3; // rbx
  __int16 v4; // dx
  __int16 v5; // si
  unsigned __int16 v6; // si
  __int64 v7; // rcx
  wchar_t *Atom; // rax
  size_t v9; // rax
  unsigned int v10; // ebp
  wchar_t *v11; // r14
  wchar_t *Buffer; // rax
  unsigned __int64 v13; // rdx
  NTSTATUS v14; // ebx
  int v15; // [rsp+30h] [rbp-A8h] BYREF
  UNICODE_STRING UnicodeStringa; // [rsp+38h] [rbp-A0h] BYREF
  PSID Sid[12]; // [rsp+50h] [rbp-88h] BYREF

  v15 = 0;
  *(_DWORD *)(&UnicodeStringa.MaximumLength + 1) = 0;
  result = NtQueryInformationToken(-6, 1, Sid, 88, &v15);
  if ( (int)result >= 0 )
  {
    v3 = (unsigned __int8 *)Sid[0];
    if ( (unsigned __int8)RtlValidSid(Sid[0]) == 1 )
    {
      if ( v3[2] || v3[3] )
        v4 = 36;
      else
        v4 = 28;
      v5 = 22 * v3[1];
      UnicodeString->Length = 0;
      v6 = v4 + v5;
      v7 = (unsigned __int16)(v6 + 34);
      UnicodeString->MaximumLength = v7;
      Atom = (wchar_t *)RtlpAllocateAtom(v7);
      UnicodeString->Buffer = Atom;
      if ( Atom )
      {
        v9 = wcslen(L"\\REGISTRY\\USER\\");
        if ( v9 <= 0x7FFE )
        {
          v10 = (unsigned __int16)(2 * v9);
          if ( UnicodeString->Length + v10 <= UnicodeString->MaximumLength )
          {
            v11 = &UnicodeString->Buffer[(unsigned __int64)UnicodeString->Length >> 1];
            memmove(v11, L"\\REGISTRY\\USER\\", (unsigned __int16)(2 * v9));
            UnicodeString->Length += v10;
            if ( (unsigned int)UnicodeString->Length + 1 < UnicodeString->MaximumLength )
              v11[(unsigned __int64)v10 >> 1] = 0;
          }
        }
        Buffer = UnicodeString->Buffer;
        v13 = (unsigned __int64)UnicodeString->Length >> 1;
        UnicodeStringa.MaximumLength = v6;
        UnicodeStringa.Length = 0;
        UnicodeStringa.Buffer = &Buffer[v13];
        v14 = RtlConvertSidToUnicodeString(&UnicodeStringa, Sid[0], 0);
        if ( v14 < 0 )
          RtlFreeAnsiString(UnicodeString);
        else
          UnicodeString->Length += UnicodeStringa.Length;
        return (unsigned int)v14;
      }
      else
      {
        return 3221225495LL;
      }
    }
    else
    {
      return 3221225592LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800152b0  push    rdi
0x1800152b2  push    r15
0x1800152b4  sub     rsp, 0C8h
0x1800152bb  mov     rax, cs:__security_cookie
0x1800152c2  xor     rax, rsp
0x1800152c5  mov     [rsp+0D8h+var_28], rax
0x1800152cd  mov     rdi, rcx
0x1800152d0  lea     rax, [rsp+0D8h+var_A8]
0x1800152d5  xor     r15d, r15d
0x1800152d8  mov     [rsp+0D8h+var_B8], rax
0x1800152dd  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x1800152e4  mov     [rsp+0D8h+var_A8], r15d
0x1800152e9  mov     r9d, 58h ; 'X'
0x1800152ef  mov     dword ptr [rsp+0D8h+UnicodeString+4], r15d
0x1800152f4  lea     r8, [rsp+0D8h+Sid]
0x1800152f9  mov     edx, 1
0x1800152fe  call    NtQueryInformationToken
0x180015303  test    eax, eax
0x180015305  js      loc_180015447
0x18001530b  mov     [rsp+0D8h+arg_8], rbx
0x180015313  mov     rbx, [rsp+0D8h+Sid]
0x180015318  mov     rcx, rbx
0x18001531b  call    RtlValidSid
0x180015320  cmp     al, 1
0x180015322  jnz     loc_180015474
0x180015328  mov     [rsp+0D8h+arg_18], rsi
0x180015330  cmp     [rbx+2], r15b
0x180015334  jnz     loc_180015463
0x18001533a  cmp     [rbx+3], r15b
0x18001533e  jnz     loc_180015463
0x180015344  mov     edx, 1Ch
0x180015349  movzx   eax, byte ptr [rbx+1]
0x18001534d  imul    esi, eax, 16h
0x180015350  mov     [rdi], r15w
0x180015354  add     si, dx
0x180015357  lea     eax, [rsi+22h]
0x18001535a  movzx   ecx, ax
0x18001535d  mov     [rdi+2], cx
0x180015361  call    RtlpAllocateAtom
0x180015366  mov     [rdi+8], rax
0x18001536a  test    rax, rax
0x18001536d  jz      loc_18001546D
0x180015373  lea     rcx, aRegistryUser; "\\REGISTRY\\USER\\"
0x18001537a  call    wcslen
0x18001537f  cmp     rax, 7FFEh
0x180015385  ja      short loc_1800153F7
0x180015387  movzx   r8d, word ptr [rdi]
0x18001538b  add     ax, ax
0x18001538e  mov     [rsp+0D8h+arg_10], rbp
0x180015396  movzx   ebp, ax
0x180015399  movzx   eax, word ptr [rdi+2]
0x18001539d  lea     ecx, [r8+rbp]
0x1800153a1  cmp     ecx, eax
0x1800153a3  ja      short loc_1800153EF
0x1800153a5  mov     rax, [rdi+8]
0x1800153a9  lea     rdx, aRegistryUser; "\\REGISTRY\\USER\\"
0x1800153b0  mov     ecx, r8d
0x1800153b3  mov     [rsp+0D8h+var_18], r14
0x1800153bb  shr     rcx, 1
0x1800153be  mov     r8d, ebp; Size
0x1800153c1  mov     ebx, ebp
0x1800153c3  lea     r14, [rax+rcx*2]
0x1800153c7  mov     rcx, r14; void *
0x1800153ca  call    memmove
0x1800153cf  add     [rdi], bp
0x1800153d2  movzx   ecx, word ptr [rdi]
0x1800153d5  movzx   eax, word ptr [rdi+2]
0x1800153d9  inc     ecx
0x1800153db  cmp     ecx, eax
0x1800153dd  jnb     short loc_1800153E7
0x1800153df  shr     rbx, 1
0x1800153e2  mov     [r14+rbx*2], r15w
0x1800153e7  mov     r14, [rsp+0D8h+var_18]
0x1800153ef  mov     rbp, [rsp+0D8h+arg_10]
0x1800153f7  movzx   edx, word ptr [rdi]
0x1800153fa  lea     rcx, [rsp+0D8h+UnicodeString]; UnicodeString
0x1800153ff  mov     rax, [rdi+8]
0x180015403  xor     r8d, r8d; AllocateDestinationString
0x180015406  shr     rdx, 1
0x180015409  mov     [rsp+0D8h+UnicodeString.MaximumLength], si
0x18001540e  mov     [rsp+0D8h+UnicodeString.Length], r15w
0x180015414  lea     rdx, [rax+rdx*2]
0x180015418  mov     [rsp+0D8h+UnicodeString.Buffer], rdx
0x18001541d  mov     rdx, [rsp+0D8h+Sid]; Sid
0x180015422  call    RtlConvertSidToUnicodeString
0x180015427  mov     ebx, eax
0x180015429  test    eax, eax
0x18001542b  js      short loc_18001547B
0x18001542d  movzx   eax, [rsp+0D8h+UnicodeString.Length]
0x180015432  add     [rdi], ax
0x180015435  mov     eax, ebx
0x180015437  mov     rsi, [rsp+0D8h+arg_18]
0x18001543f  mov     rbx, [rsp+0D8h+arg_8]
0x180015447  mov     rcx, [rsp+0D8h+var_28]
0x18001544f  xor     rcx, rsp; StackCookie
0x180015452  call    __security_check_cookie
0x180015457  add     rsp, 0C8h
0x18001545e  pop     r15
0x180015460  pop     rdi
0x180015461  retn
0x180015463  mov     edx, 24h ; '$'
0x180015468  jmp     loc_180015349
0x18001546d  mov     eax, 0C0000017h
0x180015472  jmp     short loc_180015437
0x180015474  mov     eax, 0C0000078h
0x180015479  jmp     short loc_18001543F
0x18001547b  mov     rcx, rdi; UnicodeString
0x18001547e  call    RtlFreeAnsiString
0x180015483  jmp     short loc_180015435
```
