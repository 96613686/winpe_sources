# _GetServicePathFromDevice

- ea: `0x180073ba8`
- end: `0x180073d75`
- name: `_GetServicePathFromDevice`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180073b18`

## callees

- `0x18000e090`
- `0x180010590`
- `0x18001155c`
- `0x180073ba8`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180073cff`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180073cff`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180073cec`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180073cec`

## string_xrefs

- `0x180073d39`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x180073bc9`: `\Registry\Machine\System\CurrentControlSet\Services\`

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
0x180073ba8  push    rbp
0x180073baa  push    rbx
0x180073bab  push    rsi
0x180073bac  push    rdi
0x180073bad  push    r12
0x180073baf  push    r14
0x180073bb1  push    r15
0x180073bb3  mov     rbp, rsp
0x180073bb6  sub     rsp, 40h
0x180073bba  xor     r15d, r15d
0x180073bbd  mov     qword ptr [rbp+SourceString.Length], 6A0068h
0x180073bc5  mov     qword ptr [rbp+Source.Length], r15
0x180073bc9  lea     rax, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x180073bd0  mov     [rbp+SourceString.Buffer], rax
0x180073bd4  mov     rdi, rdx
0x180073bd7  mov     [rbp+Source.Buffer], r15
0x180073bdb  mov     r12d, 68h ; 'h'
0x180073be1  test    rdx, rdx
0x180073be4  jz      loc_180073D2E
0x180073bea  test    rcx, rcx
0x180073bed  jz      loc_180073D2E
0x180073bf3  mov     rdx, [rcx+8]
0x180073bf7  test    rdx, rdx
0x180073bfa  jz      loc_180073D21
0x180073c00  mov     r9, [rdx+40h]
0x180073c04  test    r9, r9
0x180073c07  jz      loc_180073D21
0x180073c0d  movzx   eax, word ptr [rdx+38h]
0x180073c11  test    ax, ax
0x180073c14  jz      loc_180073D21
0x180073c1a  shr     ax, 1
0x180073c1d  movzx   r11d, ax
0x180073c21  movzx   ecx, r11w
0x180073c25  test    r11w, r11w
0x180073c29  jz      loc_180073D19
0x180073c2f  mov     r8d, r15d
0x180073c32  mov     eax, r15d
0x180073c35  movzx   r14d, ax
0x180073c39  movzx   esi, r8w
0x180073c3d  mov     eax, 0FFFFh
0x180073c42  movzx   r10d, r8w
0x180073c46  add     cx, ax
0x180073c49  movzx   eax, cx
0x180073c4c  movzx   ebx, word ptr [r9+rax*2]
0x180073c51  cmp     bx, 5Ch ; '\'
0x180073c55  jz      short loc_180073C64
0x180073c57  inc     r8w
0x180073c5b  movzx   eax, r8w
0x180073c5f  test    cx, cx
0x180073c62  jnz     short loc_180073C35
0x180073c64  cmp     bx, 5Ch ; '\'
0x180073c68  lea     r8d, [rsi+1]
0x180073c6c  cmovz   r8w, si
0x180073c71  inc     r10w
0x180073c75  cmp     bx, 5Ch ; '\'
0x180073c79  cmovz   r10w, r14w
0x180073c7e  test    r8w, r8w
0x180073c82  jz      loc_180073D19
0x180073c88  add     r8w, r8w
0x180073c8c  movzx   eax, r10w
0x180073c90  mov     [rbp+Source.Length], r8w
0x180073c95  mov     rcx, r11
0x180073c98  mov     [rbp+Source.MaximumLength], r8w
0x180073c9d  sub     rcx, rax
0x180073ca0  mov     rax, [rdx+40h]
0x180073ca4  add     r8w, 7
0x180073ca9  add     r8w, r12w
0x180073cad  mov     [rdi], r15w
0x180073cb1  lea     rcx, [rax+rcx*2]
0x180073cb5  mov     eax, 0FFF8h
0x180073cba  and     r8w, ax
0x180073cbe  mov     [rbp+Source.Buffer], rcx
0x180073cc2  movzx   ecx, r8w
0x180073cc6  mov     [rdi+2], cx
0x180073cca  call    MSCryptAlloc
0x180073ccf  mov     [rdi+8], rax
0x180073cd3  test    rax, rax
0x180073cd6  jnz     short loc_180073CE5
0x180073cd8  mov     ebx, 0C0000017h
0x180073cdd  mov     r9d, 3E4h
0x180073ce3  jmp     short loc_180073D39
0x180073ce5  lea     rdx, [rbp+SourceString]; SourceString
0x180073ce9  mov     rcx, rdi; DestinationString
0x180073cec  call    cs:__imp_RtlCopyUnicodeString
0x180073cf3  nop     dword ptr [rax+rax+00h]
0x180073cf8  lea     rdx, [rbp+Source]; Source
0x180073cfc  mov     rcx, rdi; Destination
0x180073cff  call    cs:__imp_RtlAppendUnicodeStringToString
0x180073d06  nop     dword ptr [rax+rax+00h]
0x180073d0b  mov     ebx, eax
0x180073d0d  test    eax, eax
0x180073d0f  jns     short loc_180073D63
0x180073d11  mov     r9d, 3ECh
0x180073d17  jmp     short loc_180073D39
0x180073d19  mov     r9d, 3CBh
0x180073d1f  jmp     short loc_180073D34
0x180073d21  mov     ebx, 0C0000010h
0x180073d26  mov     r9d, 3ABh
0x180073d2c  jmp     short loc_180073D39
0x180073d2e  mov     r9d, 39Bh
0x180073d34  mov     ebx, 0C000000Dh
0x180073d39  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180073d40  mov     ecx, ebx
0x180073d42  lea     rdx, aSresult; "sResult"
0x180073d49  call    DebugTraceError
0x180073d4e  mov     rcx, [rdi+8]; P
0x180073d52  test    rcx, rcx
0x180073d55  jz      short loc_180073D63
0x180073d57  call    MSCryptFree
0x180073d5c  mov     [rdi], r15d
0x180073d5f  mov     [rdi+8], r15
0x180073d63  mov     eax, ebx
0x180073d65  add     rsp, 40h
0x180073d69  pop     r15
0x180073d6b  pop     r14
0x180073d6d  pop     r12
0x180073d6f  pop     rdi
0x180073d70  pop     rsi
0x180073d71  pop     rbx
0x180073d72  pop     rbp
0x180073d73  retn
```
