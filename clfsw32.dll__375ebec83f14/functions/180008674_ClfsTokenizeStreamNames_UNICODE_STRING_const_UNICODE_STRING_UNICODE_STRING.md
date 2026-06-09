# ClfsTokenizeStreamNames(_UNICODE_STRING const &,_UNICODE_STRING &,_UNICODE_STRING &)

- ea: `0x180008674`
- end: `0x1800089b3`
- name: `?ClfsTokenizeStreamNames@@YAEAEBU_UNICODE_STRING@@AEAU1@1@Z`
- size: `831`
- prototype: `unsigned __int8 __fastcall(const struct _UNICODE_STRING *, PUNICODE_STRING DestinationString, PUNICODE_STRING)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180009fe0`

## callees

- `0x180008574`
- `0x180008674`

## import_xrefs

- `ntdll!RtlPrefixUnicodeString` at `0x1800087ad`
- `ntdll!RtlPrefixUnicodeString` at `0x1800087cb`
- `ntdll!RtlPrefixUnicodeString` at `0x1800087e9`
- `ntdll!RtlPrefixUnicodeString` at `0x180008807`
- `ntdll!RtlPrefixUnicodeString` at `0x180008821`
- `ntdll!RtlPrefixUnicodeString` at `0x180008863`
- `ntdll!RtlPrefixUnicodeString` at `0x1800087ad`
- `ntdll!RtlPrefixUnicodeString` at `0x1800087cb`
- `ntdll!RtlPrefixUnicodeString` at `0x1800087e9`
- `ntdll!RtlPrefixUnicodeString` at `0x180008807`
- `ntdll!RtlPrefixUnicodeString` at `0x180008821`
- `ntdll!RtlPrefixUnicodeString` at `0x180008863`
- `ntdll!RtlInitUnicodeString` at `0x1800086e5`
- `ntdll!RtlInitUnicodeString` at `0x1800086f6`
- `ntdll!RtlInitUnicodeString` at `0x18000870d`
- `ntdll!RtlInitUnicodeString` at `0x180008724`
- `ntdll!RtlInitUnicodeString` at `0x18000873b`
- `ntdll!RtlInitUnicodeString` at `0x180008752`
- `ntdll!RtlInitUnicodeString` at `0x180008769`
- `ntdll!RtlInitUnicodeString` at `0x180008780`
- `ntdll!RtlInitUnicodeString` at `0x180008797`
- `ntdll!RtlInitUnicodeString` at `0x1800086e5`
- `ntdll!RtlInitUnicodeString` at `0x1800086f6`
- `ntdll!RtlInitUnicodeString` at `0x18000870d`
- `ntdll!RtlInitUnicodeString` at `0x180008724`
- `ntdll!RtlInitUnicodeString` at `0x18000873b`
- `ntdll!RtlInitUnicodeString` at `0x180008752`
- `ntdll!RtlInitUnicodeString` at `0x180008769`
- `ntdll!RtlInitUnicodeString` at `0x180008780`
- `ntdll!RtlInitUnicodeString` at `0x180008797`

## pseudocode

```c
unsigned __int8 __fastcall ClfsTokenizeStreamNames(
        const struct _UNICODE_STRING *a1,
        PUNICODE_STRING DestinationString,
        PUNICODE_STRING a3)
{
  const unsigned __int16 *v6; // rdx
  unsigned __int64 v7; // rdx
  USHORT Length; // di
  USHORT v9; // si
  unsigned __int64 v10; // rcx
  USHORT v11; // r14
  __int16 v12; // di
  WCHAR *Buffer; // r15
  __int16 v14; // r8
  struct _UNICODE_STRING v15; // xmm0
  unsigned __int16 v16; // ax
  unsigned int v17; // r8d
  int v19; // edx
  __int64 v20; // rcx
  USHORT v21; // cx
  struct _UNICODE_STRING v22; // [rsp+20h] [rbp-79h] BYREF
  UNICODE_STRING v23; // [rsp+30h] [rbp-69h] BYREF
  UNICODE_STRING v24; // [rsp+40h] [rbp-59h] BYREF
  struct _UNICODE_STRING v25; // [rsp+50h] [rbp-49h] BYREF
  UNICODE_STRING String1; // [rsp+60h] [rbp-39h] BYREF
  UNICODE_STRING v27; // [rsp+70h] [rbp-29h] BYREF
  UNICODE_STRING v28; // [rsp+80h] [rbp-19h] BYREF
  UNICODE_STRING v29; // [rsp+90h] [rbp-9h] BYREF
  _UNICODE_STRING DestinationStringa; // [rsp+A0h] [rbp+7h] BYREF

  *(_QWORD *)&v23.Length = 0;
  v23.Buffer = 0;
  *(_QWORD *)&String1.Length = 0;
  String1.Buffer = 0;
  *(_QWORD *)&v27.Length = 0;
  v27.Buffer = 0;
  *(_QWORD *)&v24.Length = 0;
  v24.Buffer = 0;
  *(_QWORD *)&v28.Length = 0;
  v28.Buffer = 0;
  *(_QWORD *)&v29.Length = 0;
  v29.Buffer = 0;
  *(_QWORD *)&v25.Length = 0;
  v25.Buffer = 0;
  *(_QWORD *)&v22.Length = 0;
  v22.Buffer = 0;
  *(_QWORD *)&DestinationStringa.Length = 0;
  DestinationStringa.Buffer = 0;
  RtlInitUnicodeString(DestinationString, 0);
  RtlInitUnicodeString(a3, 0);
  RtlInitUnicodeString(&DestinationStringa, L"::");
  RtlInitUnicodeString(&v23, L"\\CLFS");
  RtlInitUnicodeString(&String1, L"\\??\\LOG:");
  RtlInitUnicodeString(&v27, L"LOG:");
  RtlInitUnicodeString(&v24, L"\\CLFSAPI");
  RtlInitUnicodeString(&v28, L"\\??\\LOGAPI:");
  RtlInitUnicodeString(&v29, L"LOGAPI:");
  if ( RtlPrefixUnicodeString(&String1, a1, 1u)
    || RtlPrefixUnicodeString(&v27, a1, 1u)
    || RtlPrefixUnicodeString(&v28, a1, 1u)
    || RtlPrefixUnicodeString(&v29, a1, 1u) )
  {
    v12 = ClfsStrTok(a1, v6, &v25);
    v7 = v12 + 1;
    v14 = 2 * (v12 + 1);
    v9 = a1->Length - v14;
    v11 = a1->MaximumLength - v14;
    Buffer = &a1->Buffer[v7];
  }
  else
  {
    if ( RtlPrefixUnicodeString(&v23, a1, 1u) )
    {
      Length = v23.Length;
      v9 = a1->Length - v23.Length;
      v10 = (unsigned __int64)v23.Length >> 1;
      v11 = a1->MaximumLength - v23.Length;
    }
    else
    {
      if ( !RtlPrefixUnicodeString(&v24, a1, 1u) )
        return 0;
      v7 = v24.Length;
      v9 = a1->Length - v24.Length;
      Length = v23.Length;
      v10 = (unsigned __int64)v24.Length >> 1;
      v11 = a1->MaximumLength - v24.Length;
    }
    v12 = (Length >> 1) - 1;
    Buffer = &a1->Buffer[v10];
  }
  v15 = *a1;
  v22.Buffer = Buffer;
  *DestinationString = v15;
  while ( 1 )
  {
    v22.Length = v9;
    v22.MaximumLength = v11;
    v16 = ClfsStrTok(&v22, (const unsigned __int16 *const)v7, &v25);
    v7 = v16;
    if ( (__int16)v16 <= 0 )
      break;
    if ( Buffer[v16] == 58 )
    {
      v17 = v9 >> 1;
      if ( (unsigned int)v16 + 1 < v17 && Buffer[v16 + 1] == 58 )
      {
        if ( (unsigned int)v16 + 2 > v17 )
          return 0;
        v19 = v16 + 3 + v12;
        v20 = v19;
        LOWORD(v19) = 2 * v19;
        a3->Buffer = &a1->Buffer[v20];
        a3->Length = a1->Length - v19;
        a3->MaximumLength = a1->MaximumLength - v19;
        break;
      }
    }
    v22.Buffer = &Buffer[v16];
    Buffer = v22.Buffer;
    v9 -= 2 * v16;
    v11 -= 2 * v16;
    v12 += v16;
  }
  if ( a3->Length )
  {
    v21 = DestinationStringa.Length;
    DestinationString->Length -= DestinationStringa.Length + a3->Length;
    DestinationString->MaximumLength -= a3->MaximumLength + v21;
  }
  return 1;
}

```

## disassembly

```asm
0x180008674  push    rbp
0x180008676  push    rbx
0x180008677  push    rsi
0x180008678  push    rdi
0x180008679  push    r12
0x18000867b  push    r13
0x18000867d  push    r14
0x18000867f  push    r15
0x180008681  lea     rbp, [rsp-1Fh]
0x180008686  sub     rsp, 0B8h
0x18000868d  xor     edi, edi
0x18000868f  mov     r12, rdx
0x180008692  mov     rbx, rcx
0x180008695  mov     qword ptr [rbp+57h+var_C0.Length], rdi
0x180008699  mov     rcx, r12; DestinationString
0x18000869c  mov     [rbp+57h+var_C0.Buffer], rdi
0x1800086a0  xor     edx, edx; SourceString
0x1800086a2  mov     qword ptr [rbp+57h+String1.Length], rdi
0x1800086a6  mov     r13, r8
0x1800086a9  mov     [rbp+57h+String1.Buffer], rdi
0x1800086ad  mov     qword ptr [rbp+57h+var_80.Length], rdi
0x1800086b1  mov     [rbp+57h+var_80.Buffer], rdi
0x1800086b5  mov     qword ptr [rbp+57h+var_B0.Length], rdi
0x1800086b9  mov     [rbp+57h+var_B0.Buffer], rdi
0x1800086bd  mov     qword ptr [rbp+57h+var_70.Length], rdi
0x1800086c1  mov     [rbp+57h+var_70.Buffer], rdi
0x1800086c5  mov     qword ptr [rbp+57h+var_60.Length], rdi
0x1800086c9  mov     [rbp+57h+var_60.Buffer], rdi
0x1800086cd  mov     qword ptr [rbp+57h+var_A0.Length], rdi
0x1800086d1  mov     [rbp+57h+var_A0.Buffer], rdi
0x1800086d5  mov     qword ptr [rbp+57h+var_D0.Length], rdi
0x1800086d9  mov     [rbp+57h+var_D0.Buffer], rdi
0x1800086dd  mov     qword ptr [rbp+57h+DestinationString.Length], rdi
0x1800086e1  mov     [rbp+57h+DestinationString.Buffer], rdi
0x1800086e5  call    cs:__imp_RtlInitUnicodeString
0x1800086ec  nop     dword ptr [rax+rax+00h]
0x1800086f1  xor     edx, edx; SourceString
0x1800086f3  mov     rcx, r13; DestinationString
0x1800086f6  call    cs:__imp_RtlInitUnicodeString
0x1800086fd  nop     dword ptr [rax+rax+00h]
0x180008702  lea     rdx, SourceString; "::"
0x180008709  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000870d  call    cs:__imp_RtlInitUnicodeString
0x180008714  nop     dword ptr [rax+rax+00h]
0x180008719  lea     rdx, aClfs; "\\CLFS"
0x180008720  lea     rcx, [rbp+57h+var_C0]; DestinationString
0x180008724  call    cs:__imp_RtlInitUnicodeString
0x18000872b  nop     dword ptr [rax+rax+00h]
0x180008730  lea     rdx, aLog; "\\??\\LOG:"
0x180008737  lea     rcx, [rbp+57h+String1]; DestinationString
0x18000873b  call    cs:__imp_RtlInitUnicodeString
0x180008742  nop     dword ptr [rax+rax+00h]
0x180008747  lea     rdx, aLog_0; "LOG:"
0x18000874e  lea     rcx, [rbp+57h+var_80]; DestinationString
0x180008752  call    cs:__imp_RtlInitUnicodeString
0x180008759  nop     dword ptr [rax+rax+00h]
0x18000875e  lea     rdx, aClfsapi; "\\CLFSAPI"
0x180008765  lea     rcx, [rbp+57h+var_B0]; DestinationString
0x180008769  call    cs:__imp_RtlInitUnicodeString
0x180008770  nop     dword ptr [rax+rax+00h]
0x180008775  lea     rdx, aLogapi; "\\??\\LOGAPI:"
0x18000877c  lea     rcx, [rbp+57h+var_70]; DestinationString
0x180008780  call    cs:__imp_RtlInitUnicodeString
0x180008787  nop     dword ptr [rax+rax+00h]
0x18000878c  lea     rdx, aLogapi_0; "LOGAPI:"
0x180008793  lea     rcx, [rbp+57h+var_60]; DestinationString
0x180008797  call    cs:__imp_RtlInitUnicodeString
0x18000879e  nop     dword ptr [rax+rax+00h]
0x1800087a3  mov     r8b, 1; CaseInsensitive
0x1800087a6  lea     rcx, [rbp+57h+String1]; String1
0x1800087aa  mov     rdx, rbx; String2
0x1800087ad  call    cs:__imp_RtlPrefixUnicodeString
0x1800087b4  nop     dword ptr [rax+rax+00h]
0x1800087b9  test    al, al
0x1800087bb  jnz     loc_180008895
0x1800087c1  mov     r8b, 1; CaseInsensitive
0x1800087c4  lea     rcx, [rbp+57h+var_80]; String1
0x1800087c8  mov     rdx, rbx; String2
0x1800087cb  call    cs:__imp_RtlPrefixUnicodeString
0x1800087d2  nop     dword ptr [rax+rax+00h]
0x1800087d7  test    al, al
0x1800087d9  jnz     loc_180008895
0x1800087df  mov     r8b, 1; CaseInsensitive
0x1800087e2  lea     rcx, [rbp+57h+var_70]; String1
0x1800087e6  mov     rdx, rbx; String2
0x1800087e9  call    cs:__imp_RtlPrefixUnicodeString
0x1800087f0  nop     dword ptr [rax+rax+00h]
0x1800087f5  test    al, al
0x1800087f7  jnz     loc_180008895
0x1800087fd  mov     r8b, 1; CaseInsensitive
0x180008800  lea     rcx, [rbp+57h+var_60]; String1
0x180008804  mov     rdx, rbx; String2
0x180008807  call    cs:__imp_RtlPrefixUnicodeString
0x18000880e  nop     dword ptr [rax+rax+00h]
0x180008813  test    al, al
0x180008815  jnz     short loc_180008895
0x180008817  mov     r8b, 1; CaseInsensitive
0x18000881a  lea     rcx, [rbp+57h+var_C0]; String1
0x18000881e  mov     rdx, rbx; String2
0x180008821  call    cs:__imp_RtlPrefixUnicodeString
0x180008828  nop     dword ptr [rax+rax+00h]
0x18000882d  test    al, al
0x18000882f  jz      short loc_180008859
0x180008831  movzx   edi, [rbp+57h+var_C0.Length]
0x180008835  movzx   esi, word ptr [rbx]
0x180008838  mov     ecx, edi
0x18000883a  movzx   r14d, word ptr [rbx+2]
0x18000883f  sub     si, di
0x180008842  shr     rcx, 1
0x180008845  sub     r14w, di
0x180008849  mov     rax, [rbx+8]
0x18000884d  shr     di, 1
0x180008850  dec     di
0x180008853  lea     r15, [rax+rcx*2]
0x180008857  jmp     short loc_1800088C7
0x180008859  mov     r8b, 1; CaseInsensitive
0x18000885c  lea     rcx, [rbp+57h+var_B0]; String1
0x180008860  mov     rdx, rbx; String2
0x180008863  call    cs:__imp_RtlPrefixUnicodeString
0x18000886a  nop     dword ptr [rax+rax+00h]
0x18000886f  test    al, al
0x180008871  jz      loc_180008946
0x180008877  movzx   edx, [rbp+57h+var_B0.Length]
0x18000887b  movzx   esi, word ptr [rbx]
0x18000887e  mov     ecx, edx
0x180008880  movzx   r14d, word ptr [rbx+2]
0x180008885  sub     si, dx
0x180008888  movzx   edi, [rbp+57h+var_C0.Length]
0x18000888c  shr     rcx, 1
0x18000888f  sub     r14w, dx
0x180008893  jmp     short loc_180008849
0x180008895  lea     r8, [rbp+57h+var_A0]; struct _UNICODE_STRING *
0x180008899  mov     rcx, rbx; struct _UNICODE_STRING *
0x18000889c  call    ?ClfsStrTok@@YAFAEBU_UNICODE_STRING@@QEBGAEAU1@@Z; ClfsStrTok(_UNICODE_STRING const &,ushort const * const,_UNICODE_STRING &)
0x1800088a1  mov     rcx, [rbx+8]
0x1800088a5  movzx   esi, word ptr [rbx]
0x1800088a8  movzx   r14d, word ptr [rbx+2]
0x1800088ad  movsx   edi, ax
0x1800088b0  lea     r8d, [rdi+1]
0x1800088b4  movsxd  rdx, r8d; unsigned __int16 *
0x1800088b7  add     r8w, r8w
0x1800088bb  sub     si, r8w
0x1800088bf  sub     r14w, r8w
0x1800088c3  lea     r15, [rcx+rdx*2]
0x1800088c7  movups  xmm0, xmmword ptr [rbx]
0x1800088ca  mov     [rbp+57h+var_D0.Buffer], r15
0x1800088ce  movdqu  xmmword ptr [r12], xmm0
0x1800088d4  lea     r8, [rbp+57h+var_A0]; struct _UNICODE_STRING *
0x1800088d8  mov     [rbp+57h+var_D0.Length], si
0x1800088dc  lea     rcx, [rbp+57h+var_D0]; struct _UNICODE_STRING *
0x1800088e0  mov     [rbp+57h+var_D0.MaximumLength], r14w
0x1800088e5  call    ?ClfsStrTok@@YAFAEBU_UNICODE_STRING@@QEBGAEAU1@@Z; ClfsStrTok(_UNICODE_STRING const &,ushort const * const,_UNICODE_STRING &)
0x1800088ea  xor     r10d, r10d
0x1800088ed  movzx   edx, ax
0x1800088f0  cmp     r10w, ax
0x1800088f4  jge     loc_18000897B
0x1800088fa  movzx   ecx, ax
0x1800088fd  lea     r11d, [r10+3Ah]
0x180008901  lea     r9, [r15+rcx*2]
0x180008905  cmp     r11w, [r9]
0x180008909  jnz     short loc_180008925
0x18000890b  movzx   ecx, ax
0x18000890e  movzx   r8d, si
0x180008912  shr     r8d, 1
0x180008915  lea     eax, [rcx+1]
0x180008918  cmp     eax, r8d
0x18000891b  jnb     short loc_180008925
0x18000891d  cmp     [r15+rcx*2+2], r11w
0x180008923  jz      short loc_18000893E
0x180008925  movzx   eax, dx
0x180008928  mov     [rbp+57h+var_D0.Buffer], r9
0x18000892c  add     ax, ax
0x18000892f  mov     r15, r9
0x180008932  sub     si, ax
0x180008935  sub     r14w, ax
0x180008939  add     di, dx
0x18000893c  jmp     short loc_1800088D4
0x18000893e  lea     eax, [rcx+2]
0x180008941  cmp     eax, r8d
0x180008944  jbe     short loc_18000894A
0x180008946  xor     al, al
0x180008948  jmp     short loc_18000899E
0x18000894a  mov     rax, [rbx+8]
0x18000894e  add     ecx, 3
0x180008951  movsx   edx, di
0x180008954  add     edx, ecx
0x180008956  movsxd  rcx, edx
0x180008959  add     dx, dx
0x18000895c  lea     rcx, [rax+rcx*2]
0x180008960  mov     [r13+8], rcx
0x180008964  movzx   eax, word ptr [rbx]
0x180008967  sub     ax, dx
0x18000896a  mov     [r13+0], ax
0x18000896f  movzx   eax, word ptr [rbx+2]
0x180008973  sub     ax, dx
0x180008976  mov     [r13+2], ax
0x18000897b  movzx   edx, word ptr [r13+0]
0x180008980  test    dx, dx
0x180008983  jz      short loc_18000899C
0x180008985  movzx   ecx, [rbp+57h+DestinationString.Length]
0x180008989  add     dx, cx
0x18000898c  sub     [r12], dx
0x180008991  add     cx, [r13+2]
0x180008996  sub     [r12+2], cx
0x18000899c  mov     al, 1
0x18000899e  add     rsp, 0B8h
0x1800089a5  pop     r15
0x1800089a7  pop     r14
0x1800089a9  pop     r13
0x1800089ab  pop     r12
0x1800089ad  pop     rdi
0x1800089ae  pop     rsi
0x1800089af  pop     rbx
0x1800089b0  pop     rbp
0x1800089b1  retn
```
