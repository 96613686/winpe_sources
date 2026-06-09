# IsExcludedExtension

- ea: `0x14001cbd0`
- end: `0x14001cd0c`
- name: `IsExcludedExtension`
- size: `316`
- prototype: `char __fastcall(WCHAR *, unsigned int, _BYTE *, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001cb30`
- `0x140028f98`

## callees

- `0x14001cbd0`

## import_xrefs

- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14001cc15`
- `ntoskrnl!RtlUpcaseUnicodeChar` at `0x14001cc15`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001ccb7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001ccb7`

## pseudocode

```c
char __fastcall IsExcludedExtension(WCHAR *a1, unsigned int a2, _BYTE *a3, int *a4)
{
  int v4; // ebx
  unsigned int v7; // edi
  WCHAR *v8; // rsi
  WCHAR *v9; // r14
  unsigned __int64 v10; // r10
  int v11; // r9d
  int v12; // eax
  int v13; // edi
  __int64 v14; // rsi
  LONG v15; // eax
  int v17; // ecx
  unsigned __int64 v18; // [rsp+20h] [rbp-38h] BYREF
  UNICODE_STRING String2; // [rsp+28h] [rbp-30h] BYREF

  v4 = 0;
  v7 = a2;
  v8 = a1;
  String2 = 0;
  if ( a2 > 4 )
  {
    String2.Buffer = a1;
    String2.Length = 2 * a2;
    String2.MaximumLength = 2 * a2;
    v13 = HIDWORD(qword_14000ECB0) - 1;
    while ( v13 >= v4 )
    {
      v14 = (v13 + v4) / 2;
      v15 = RtlCompareUnicodeString((PCUNICODE_STRING)(qword_14000ECA8 + 16 * v14), &String2, 1u);
      if ( !v15 )
      {
        if ( a3 )
        {
          *a3 = 0;
          *a4 = v14;
        }
        return 1;
      }
      v17 = v14 + 1;
      if ( v15 >= 0 )
        v17 = v4;
      v4 = v17;
      if ( v15 >= 0 )
        v13 = v14 - 1;
    }
  }
  else
  {
    v9 = (WCHAR *)&v18;
    v18 = 0;
    v10 = 0;
    if ( a2 )
    {
      do
      {
        *v9++ = RtlUpcaseUnicodeChar(*v8++);
        --v7;
      }
      while ( v7 );
      v10 = v18;
    }
    v11 = qword_14000ECB0 - 1;
    while ( v11 >= v4 )
    {
      v12 = (v11 + v4) / 2;
      if ( *(_QWORD *)(qword_14000ECA0 + 8LL * v12) == v10 )
      {
        if ( a3 )
        {
          *a3 = 1;
          *a4 = v12;
        }
        return 1;
      }
      if ( *(_QWORD *)(qword_14000ECA0 + 8LL * v12) >= v10 )
        v11 = v12 - 1;
      else
        v4 = v12 + 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14001cbd0  mov     [rsp+arg_8], rbx
0x14001cbd5  mov     [rsp+arg_10], rbp
0x14001cbda  push    rsi
0x14001cbdb  push    rdi
0x14001cbdc  push    r15
0x14001cbde  sub     rsp, 40h
0x14001cbe2  xor     ebx, ebx
0x14001cbe4  xorps   xmm0, xmm0
0x14001cbe7  mov     rbp, r9
0x14001cbea  mov     r15, r8
0x14001cbed  mov     edi, edx
0x14001cbef  mov     rsi, rcx
0x14001cbf2  movups  xmmword ptr [rsp+58h+String2.Length], xmm0
0x14001cbf7  cmp     edx, 4
0x14001cbfa  ja      short loc_14001CC78
0x14001cbfc  mov     [rsp+58h+arg_0], r14
0x14001cc01  lea     r14, [rsp+58h+var_38]
0x14001cc06  mov     [rsp+58h+var_38], rbx
0x14001cc0b  mov     r10d, ebx
0x14001cc0e  test    edx, edx
0x14001cc10  jz      short loc_14001CC37
0x14001cc12  movzx   ecx, word ptr [rsi]; SourceCharacter
0x14001cc15  call    cs:__imp_RtlUpcaseUnicodeChar
0x14001cc1c  nop     dword ptr [rax+rax+00h]
0x14001cc21  mov     [r14], ax
0x14001cc25  lea     r14, [r14+2]
0x14001cc29  lea     rsi, [rsi+2]
0x14001cc2d  add     edi, 0FFFFFFFFh
0x14001cc30  jnz     short loc_14001CC12
0x14001cc32  mov     r10, [rsp+58h+var_38]
0x14001cc37  mov     r9d, dword ptr cs:qword_14000ECB0
0x14001cc3e  mov     r14, [rsp+58h+arg_0]
0x14001cc43  dec     r9d
0x14001cc46  cmp     r9d, ebx
0x14001cc49  jl      loc_14001CCEF
0x14001cc4f  lea     eax, [r9+rbx]
0x14001cc53  test    eax, eax
0x14001cc55  jns     short loc_14001CC59
0x14001cc57  inc     eax
0x14001cc59  mov     rcx, cs:qword_14000ECA0
0x14001cc60  sar     eax, 1
0x14001cc62  movsxd  rdx, eax
0x14001cc65  cmp     [rcx+rdx*8], r10
0x14001cc69  jz      short loc_14001CCD4
0x14001cc6b  jnb     short loc_14001CC72
0x14001cc6d  lea     ebx, [rax+1]
0x14001cc70  jmp     short loc_14001CC46
0x14001cc72  lea     r9d, [rax-1]
0x14001cc76  jmp     short loc_14001CC46
0x14001cc78  add     di, di
0x14001cc7b  mov     [rsp+58h+String2.Buffer], rcx
0x14001cc80  mov     [rsp+58h+String2.Length], di
0x14001cc85  mov     [rsp+58h+String2.MaximumLength], di
0x14001cc8a  mov     edi, dword ptr cs:qword_14000ECB0+4
0x14001cc90  dec     edi
0x14001cc92  cmp     edi, ebx
0x14001cc94  jl      short loc_14001CCEF
0x14001cc96  lea     eax, [rdi+rbx]
0x14001cc99  mov     r8b, 1; CaseInSensitive
0x14001cc9c  cdq
0x14001cc9d  sub     eax, edx
0x14001cc9f  lea     rdx, [rsp+58h+String2]; String2
0x14001cca4  sar     eax, 1
0x14001cca6  movsxd  rsi, eax
0x14001cca9  mov     rcx, rsi
0x14001ccac  shl     rcx, 4
0x14001ccb0  add     rcx, cs:qword_14000ECA8; String1
0x14001ccb7  call    cs:__imp_RtlCompareUnicodeString
0x14001ccbe  nop     dword ptr [rax+rax+00h]
0x14001ccc3  test    eax, eax
0x14001ccc5  jnz     short loc_14001CCF3
0x14001ccc7  test    r15, r15
0x14001ccca  jz      short loc_14001CCD9
0x14001cccc  mov     [r15], al
0x14001cccf  mov     [rbp+0], esi
0x14001ccd2  jmp     short loc_14001CCD9
0x14001ccd4  test    r15, r15
0x14001ccd7  jnz     short loc_14001CD03
0x14001ccd9  mov     al, 1
0x14001ccdb  mov     rbx, [rsp+58h+arg_8]
0x14001cce0  mov     rbp, [rsp+58h+arg_10]
0x14001cce5  add     rsp, 40h
0x14001cce9  pop     r15
0x14001cceb  pop     rdi
0x14001ccec  pop     rsi
0x14001cced  retn
0x14001ccef  xor     al, al
0x14001ccf1  jmp     short loc_14001CCDB
0x14001ccf3  lea     ecx, [rsi+1]
0x14001ccf6  cmovns  ecx, ebx
0x14001ccf9  mov     ebx, ecx
0x14001ccfb  lea     ecx, [rsi-1]
0x14001ccfe  cmovns  edi, ecx
0x14001cd01  jmp     short loc_14001CC92
0x14001cd03  mov     byte ptr [r15], 1
0x14001cd07  mov     [rbp+0], eax
0x14001cd0a  jmp     short loc_14001CCD9
```
