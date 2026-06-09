# _GetServicePathFromDevice

- ea: `0x180069a08`
- end: `0x180069bd5`
- name: `_GetServicePathFromDevice`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180069978`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x180069a08`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180069b5f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180069b5f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180069b4c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180069b4c`

## string_xrefs

- `0x180069b99`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180069a29`: `\Registry\Machine\System\CurrentControlSet\Services\`

## pseudocode

```c
__int64 __fastcall GetServicePathFromDevice(__int64 a1, struct _UNICODE_STRING *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r9
  unsigned __int16 v5; // ax
  unsigned __int16 v6; // ax
  __int64 v7; // r11
  unsigned __int16 v8; // cx
  __int16 v9; // r8
  __int16 v10; // ax
  unsigned __int16 v11; // r14
  __int16 v12; // si
  __int16 v13; // r10
  __int16 v14; // bx
  __int16 v15; // r8
  unsigned __int16 v16; // r10
  __int64 v17; // rax
  USHORT v18; // r8
  __int64 v19; // rax
  unsigned int appended; // ebx
  __int64 v21; // r9
  PWSTR Buffer; // rcx
  UNICODE_STRING Source; // [rsp+20h] [rbp-20h] BYREF
  UNICODE_STRING SourceString; // [rsp+30h] [rbp-10h] BYREF

  *(_QWORD *)&SourceString.Length = 6946920;
  *(_QWORD *)&Source.Length = 0;
  SourceString.Buffer = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\";
  Source.Buffer = 0;
  if ( !a2 || !a1 )
  {
    v21 = 923;
    goto LABEL_22;
  }
  v3 = *(_QWORD *)(a1 + 8);
  if ( !v3 || (v4 = *(_QWORD *)(v3 + 64)) == 0 || (v5 = *(_WORD *)(v3 + 56)) == 0 )
  {
    appended = -1073741808;
    v21 = 939;
    goto LABEL_23;
  }
  v6 = v5 >> 1;
  v7 = v6;
  v8 = v6;
  if ( !v6 )
    goto LABEL_19;
  v9 = 0;
  v10 = 0;
  do
  {
    v11 = v10;
    v12 = v9;
    v13 = v9;
    v14 = *(_WORD *)(v4 + 2LL * --v8);
    if ( v14 == 92 )
      break;
    v10 = ++v9;
  }
  while ( v8 );
  v15 = v12 + 1;
  if ( v14 == 92 )
    v15 = v12;
  v16 = v13 + 1;
  if ( v14 == 92 )
    v16 = v11;
  if ( !v15 )
  {
LABEL_19:
    v21 = 971;
LABEL_22:
    appended = -1073741811;
    goto LABEL_23;
  }
  Source.Length = 2 * v15;
  Source.MaximumLength = 2 * v15;
  v17 = *(_QWORD *)(v3 + 64);
  a2->Length = 0;
  v18 = (2 * v15 + 111) & 0xFFF8;
  Source.Buffer = (PWSTR)(v17 + 2 * (v7 - v16));
  a2->MaximumLength = v18;
  v19 = MSCryptAlloc(v18, v3);
  a2->Buffer = (PWSTR)v19;
  if ( v19 )
  {
    RtlCopyUnicodeString(a2, &SourceString);
    appended = RtlAppendUnicodeStringToString(a2, &Source);
    if ( (appended & 0x80000000) == 0 )
      return appended;
    v21 = 1004;
  }
  else
  {
    appended = -1073741801;
    v21 = 996;
  }
LABEL_23:
  DebugTraceError(appended, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v21);
  Buffer = a2->Buffer;
  if ( Buffer )
  {
    MSCryptFree(Buffer);
    *(_DWORD *)&a2->Length = 0;
    a2->Buffer = 0;
  }
  return appended;
}

```

## disassembly

```asm
0x180069a08  push    rbp
0x180069a0a  push    rbx
0x180069a0b  push    rsi
0x180069a0c  push    rdi
0x180069a0d  push    r12
0x180069a0f  push    r14
0x180069a11  push    r15
0x180069a13  mov     rbp, rsp
0x180069a16  sub     rsp, 40h
0x180069a1a  xor     r15d, r15d
0x180069a1d  mov     qword ptr [rbp+SourceString.Length], 6A0068h
0x180069a25  mov     qword ptr [rbp+Source.Length], r15
0x180069a29  lea     rax, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x180069a30  mov     [rbp+SourceString.Buffer], rax
0x180069a34  mov     rdi, rdx
0x180069a37  mov     [rbp+Source.Buffer], r15
0x180069a3b  mov     r12d, 68h ; 'h'
0x180069a41  test    rdx, rdx
0x180069a44  jz      loc_180069B8E
0x180069a4a  test    rcx, rcx
0x180069a4d  jz      loc_180069B8E
0x180069a53  mov     rdx, [rcx+8]
0x180069a57  test    rdx, rdx
0x180069a5a  jz      loc_180069B81
0x180069a60  mov     r9, [rdx+40h]
0x180069a64  test    r9, r9
0x180069a67  jz      loc_180069B81
0x180069a6d  movzx   eax, word ptr [rdx+38h]
0x180069a71  test    ax, ax
0x180069a74  jz      loc_180069B81
0x180069a7a  shr     ax, 1
0x180069a7d  movzx   r11d, ax
0x180069a81  movzx   ecx, r11w
0x180069a85  test    r11w, r11w
0x180069a89  jz      loc_180069B79
0x180069a8f  mov     r8d, r15d
0x180069a92  mov     eax, r15d
0x180069a95  movzx   r14d, ax
0x180069a99  movzx   esi, r8w
0x180069a9d  mov     eax, 0FFFFh
0x180069aa2  movzx   r10d, r8w
0x180069aa6  add     cx, ax
0x180069aa9  movzx   eax, cx
0x180069aac  movzx   ebx, word ptr [r9+rax*2]
0x180069ab1  cmp     bx, 5Ch ; '\'
0x180069ab5  jz      short loc_180069AC4
0x180069ab7  inc     r8w
0x180069abb  movzx   eax, r8w
0x180069abf  test    cx, cx
0x180069ac2  jnz     short loc_180069A95
0x180069ac4  cmp     bx, 5Ch ; '\'
0x180069ac8  lea     r8d, [rsi+1]
0x180069acc  cmovz   r8w, si
0x180069ad1  inc     r10w
0x180069ad5  cmp     bx, 5Ch ; '\'
0x180069ad9  cmovz   r10w, r14w
0x180069ade  test    r8w, r8w
0x180069ae2  jz      loc_180069B79
0x180069ae8  add     r8w, r8w
0x180069aec  movzx   eax, r10w
0x180069af0  mov     [rbp+Source.Length], r8w
0x180069af5  mov     rcx, r11
0x180069af8  mov     [rbp+Source.MaximumLength], r8w
0x180069afd  sub     rcx, rax
0x180069b00  mov     rax, [rdx+40h]
0x180069b04  add     r8w, 7
0x180069b09  add     r8w, r12w
0x180069b0d  mov     [rdi], r15w
0x180069b11  lea     rcx, [rax+rcx*2]
0x180069b15  mov     eax, 0FFF8h
0x180069b1a  and     r8w, ax
0x180069b1e  mov     [rbp+Source.Buffer], rcx
0x180069b22  movzx   ecx, r8w
0x180069b26  mov     [rdi+2], cx
0x180069b2a  call    MSCryptAlloc
0x180069b2f  mov     [rdi+8], rax
0x180069b33  test    rax, rax
0x180069b36  jnz     short loc_180069B45
0x180069b38  mov     ebx, 0C0000017h
0x180069b3d  mov     r9d, 3E4h
0x180069b43  jmp     short loc_180069B99
0x180069b45  lea     rdx, [rbp+SourceString]; SourceString
0x180069b49  mov     rcx, rdi; DestinationString
0x180069b4c  call    cs:__imp_RtlCopyUnicodeString
0x180069b53  nop     dword ptr [rax+rax+00h]
0x180069b58  lea     rdx, [rbp+Source]; Source
0x180069b5c  mov     rcx, rdi; Destination
0x180069b5f  call    cs:__imp_RtlAppendUnicodeStringToString
0x180069b66  nop     dword ptr [rax+rax+00h]
0x180069b6b  mov     ebx, eax
0x180069b6d  test    eax, eax
0x180069b6f  jns     short loc_180069BC3
0x180069b71  mov     r9d, 3ECh
0x180069b77  jmp     short loc_180069B99
0x180069b79  mov     r9d, 3CBh
0x180069b7f  jmp     short loc_180069B94
0x180069b81  mov     ebx, 0C0000010h
0x180069b86  mov     r9d, 3ABh
0x180069b8c  jmp     short loc_180069B99
0x180069b8e  mov     r9d, 39Bh
0x180069b94  mov     ebx, 0C000000Dh
0x180069b99  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180069ba0  mov     ecx, ebx
0x180069ba2  lea     rdx, aSresult; "sResult"
0x180069ba9  call    DebugTraceError
0x180069bae  mov     rcx, [rdi+8]; P
0x180069bb2  test    rcx, rcx
0x180069bb5  jz      short loc_180069BC3
0x180069bb7  call    MSCryptFree
0x180069bbc  mov     [rdi], r15d
0x180069bbf  mov     [rdi+8], r15
0x180069bc3  mov     eax, ebx
0x180069bc5  add     rsp, 40h
0x180069bc9  pop     r15
0x180069bcb  pop     r14
0x180069bcd  pop     r12
0x180069bcf  pop     rdi
0x180069bd0  pop     rsi
0x180069bd1  pop     rbx
0x180069bd2  pop     rbp
0x180069bd3  retn
```
