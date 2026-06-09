# _GetServicePathFromDevice

- ea: `0x18006a408`
- end: `0x18006a5d5`
- name: `_GetServicePathFromDevice`
- size: `461`
- prototype: `__int64 __fastcall(__int64, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006a378`

## callees

- `0x180003f70`
- `0x180006470`
- `0x18000743c`
- `0x18006a408`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18006a55f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18006a55f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18006a54c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18006a54c`

## string_xrefs

- `0x18006a599`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18006a429`: `\Registry\Machine\System\CurrentControlSet\Services\`

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
  unsigned __int16 v9; // r8
  __int16 v10; // ax
  unsigned __int16 v11; // r14
  int v12; // esi
  unsigned __int16 v13; // r10
  __int16 v14; // bx
  __int64 v15; // r8
  unsigned __int16 v16; // r10
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned int appended; // ebx
  __int64 v20; // r9
  PWSTR Buffer; // rcx
  UNICODE_STRING Source; // [rsp+20h] [rbp-20h] BYREF
  UNICODE_STRING SourceString; // [rsp+30h] [rbp-10h] BYREF

  *(_QWORD *)&SourceString.Length = 6946920;
  *(_QWORD *)&Source.Length = 0;
  SourceString.Buffer = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\";
  Source.Buffer = 0;
  if ( !a2 || !a1 )
  {
    v20 = 923;
    goto LABEL_22;
  }
  v3 = *(_QWORD *)(a1 + 8);
  if ( !v3 || (v4 = *(_QWORD *)(v3 + 64)) == 0 || (v5 = *(_WORD *)(v3 + 56)) == 0 )
  {
    appended = -1073741808;
    v20 = 939;
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
  v15 = (unsigned int)(v12 + 1);
  if ( v14 == 92 )
    LOWORD(v15) = v12;
  v16 = v13 + 1;
  if ( v14 == 92 )
    v16 = v11;
  if ( !(_WORD)v15 )
  {
LABEL_19:
    v20 = 971;
LABEL_22:
    appended = -1073741811;
    goto LABEL_23;
  }
  Source.Length = 2 * v15;
  Source.MaximumLength = 2 * v15;
  v17 = *(_QWORD *)(v3 + 64);
  a2->Length = 0;
  LOWORD(v15) = (2 * v15 + 111) & 0xFFF8;
  Source.Buffer = (PWSTR)(v17 + 2 * (v7 - v16));
  a2->MaximumLength = v15;
  v18 = MSCryptAlloc((unsigned __int16)v15, v3, v15, v4);
  a2->Buffer = (PWSTR)v18;
  if ( v18 )
  {
    RtlCopyUnicodeString(a2, &SourceString);
    appended = RtlAppendUnicodeStringToString(a2, &Source);
    if ( (appended & 0x80000000) == 0 )
      return appended;
    v20 = 1004;
  }
  else
  {
    appended = -1073741801;
    v20 = 996;
  }
LABEL_23:
  DebugTraceError(appended, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c", v20);
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
0x18006a408  push    rbp
0x18006a40a  push    rbx
0x18006a40b  push    rsi
0x18006a40c  push    rdi
0x18006a40d  push    r12
0x18006a40f  push    r14
0x18006a411  push    r15
0x18006a413  mov     rbp, rsp
0x18006a416  sub     rsp, 40h
0x18006a41a  xor     r15d, r15d
0x18006a41d  mov     qword ptr [rbp+SourceString.Length], 6A0068h
0x18006a425  mov     qword ptr [rbp+Source.Length], r15
0x18006a429  lea     rax, aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x18006a430  mov     [rbp+SourceString.Buffer], rax
0x18006a434  mov     rdi, rdx
0x18006a437  mov     [rbp+Source.Buffer], r15
0x18006a43b  mov     r12d, 68h ; 'h'
0x18006a441  test    rdx, rdx
0x18006a444  jz      loc_18006A58E
0x18006a44a  test    rcx, rcx
0x18006a44d  jz      loc_18006A58E
0x18006a453  mov     rdx, [rcx+8]
0x18006a457  test    rdx, rdx
0x18006a45a  jz      loc_18006A581
0x18006a460  mov     r9, [rdx+40h]
0x18006a464  test    r9, r9
0x18006a467  jz      loc_18006A581
0x18006a46d  movzx   eax, word ptr [rdx+38h]
0x18006a471  test    ax, ax
0x18006a474  jz      loc_18006A581
0x18006a47a  shr     ax, 1
0x18006a47d  movzx   r11d, ax
0x18006a481  movzx   ecx, r11w
0x18006a485  test    r11w, r11w
0x18006a489  jz      loc_18006A579
0x18006a48f  mov     r8d, r15d
0x18006a492  mov     eax, r15d
0x18006a495  movzx   r14d, ax
0x18006a499  movzx   esi, r8w
0x18006a49d  mov     eax, 0FFFFh
0x18006a4a2  movzx   r10d, r8w
0x18006a4a6  add     cx, ax
0x18006a4a9  movzx   eax, cx
0x18006a4ac  movzx   ebx, word ptr [r9+rax*2]
0x18006a4b1  cmp     bx, 5Ch ; '\'
0x18006a4b5  jz      short loc_18006A4C4
0x18006a4b7  inc     r8w
0x18006a4bb  movzx   eax, r8w
0x18006a4bf  test    cx, cx
0x18006a4c2  jnz     short loc_18006A495
0x18006a4c4  cmp     bx, 5Ch ; '\'
0x18006a4c8  lea     r8d, [rsi+1]
0x18006a4cc  cmovz   r8w, si
0x18006a4d1  inc     r10w
0x18006a4d5  cmp     bx, 5Ch ; '\'
0x18006a4d9  cmovz   r10w, r14w
0x18006a4de  test    r8w, r8w
0x18006a4e2  jz      loc_18006A579
0x18006a4e8  add     r8w, r8w
0x18006a4ec  movzx   eax, r10w
0x18006a4f0  mov     [rbp+Source.Length], r8w
0x18006a4f5  mov     rcx, r11
0x18006a4f8  mov     [rbp+Source.MaximumLength], r8w
0x18006a4fd  sub     rcx, rax
0x18006a500  mov     rax, [rdx+40h]
0x18006a504  add     r8w, 7
0x18006a509  add     r8w, r12w
0x18006a50d  mov     [rdi], r15w
0x18006a511  lea     rcx, [rax+rcx*2]
0x18006a515  mov     eax, 0FFF8h
0x18006a51a  and     r8w, ax
0x18006a51e  mov     [rbp+Source.Buffer], rcx
0x18006a522  movzx   ecx, r8w
0x18006a526  mov     [rdi+2], cx
0x18006a52a  call    MSCryptAlloc
0x18006a52f  mov     [rdi+8], rax
0x18006a533  test    rax, rax
0x18006a536  jnz     short loc_18006A545
0x18006a538  mov     ebx, 0C0000017h
0x18006a53d  mov     r9d, 3E4h
0x18006a543  jmp     short loc_18006A599
0x18006a545  lea     rdx, [rbp+SourceString]; SourceString
0x18006a549  mov     rcx, rdi; DestinationString
0x18006a54c  call    cs:__imp_RtlCopyUnicodeString
0x18006a553  nop     dword ptr [rax+rax+00h]
0x18006a558  lea     rdx, [rbp+Source]; Source
0x18006a55c  mov     rcx, rdi; Destination
0x18006a55f  call    cs:__imp_RtlAppendUnicodeStringToString
0x18006a566  nop     dword ptr [rax+rax+00h]
0x18006a56b  mov     ebx, eax
0x18006a56d  test    eax, eax
0x18006a56f  jns     short loc_18006A5C3
0x18006a571  mov     r9d, 3ECh
0x18006a577  jmp     short loc_18006A599
0x18006a579  mov     r9d, 3CBh
0x18006a57f  jmp     short loc_18006A594
0x18006a581  mov     ebx, 0C0000010h
0x18006a586  mov     r9d, 3ABh
0x18006a58c  jmp     short loc_18006A599
0x18006a58e  mov     r9d, 39Bh
0x18006a594  mov     ebx, 0C000000Dh
0x18006a599  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006a5a0  mov     ecx, ebx
0x18006a5a2  lea     rdx, aSresult; "sResult"
0x18006a5a9  call    DebugTraceError
0x18006a5ae  mov     rcx, [rdi+8]; P
0x18006a5b2  test    rcx, rcx
0x18006a5b5  jz      short loc_18006A5C3
0x18006a5b7  call    MSCryptFree
0x18006a5bc  mov     [rdi], r15d
0x18006a5bf  mov     [rdi+8], r15
0x18006a5c3  mov     eax, ebx
0x18006a5c5  add     rsp, 40h
0x18006a5c9  pop     r15
0x18006a5cb  pop     r14
0x18006a5cd  pop     r12
0x18006a5cf  pop     rdi
0x18006a5d0  pop     rsi
0x18006a5d1  pop     rbx
0x18006a5d2  pop     rbp
0x18006a5d3  retn
```
