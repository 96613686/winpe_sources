# DevAuthUtcTimeToFileTime

- ea: `0x180003370`
- end: `0x1800035b4`
- name: `DevAuthUtcTimeToFileTime`
- size: `580`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001700`

## callees

- `0x180003370`
- `0x1800066f6`
- `0x1800067e0`

## import_xrefs

- `ntoskrnl!atoi` at `0x180003444`
- `ntoskrnl!atoi` at `0x180003481`
- `ntoskrnl!atoi` at `0x1800034ac`
- `ntoskrnl!atoi` at `0x1800034d7`
- `ntoskrnl!atoi` at `0x180003501`
- `ntoskrnl!atoi` at `0x180003523`
- `ntoskrnl!atoi` at `0x180003444`
- `ntoskrnl!atoi` at `0x180003481`
- `ntoskrnl!atoi` at `0x1800034ac`
- `ntoskrnl!atoi` at `0x1800034d7`
- `ntoskrnl!atoi` at `0x180003501`
- `ntoskrnl!atoi` at `0x180003523`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x180003574`
- `ntoskrnl!RtlTimeFieldsToTime` at `0x180003574`

## pseudocode

```c
__int64 __fastcall DevAuthUtcTimeToFileTime(__int64 a1, unsigned int a2, _LARGE_INTEGER *a3)
{
  unsigned int v5; // eax
  __int16 v6; // r12
  int v7; // ebx
  int v8; // eax
  CSHORT v9; // r15
  int v10; // eax
  CSHORT v11; // r14
  int v12; // eax
  CSHORT v13; // si
  int v14; // eax
  CSHORT v15; // di
  int v16; // eax
  __int64 result; // rax
  char Dest[4]; // [rsp+20h] [rbp-40h] BYREF
  char Str[4]; // [rsp+24h] [rbp-3Ch] BYREF
  char v20[4]; // [rsp+28h] [rbp-38h] BYREF
  char v21[4]; // [rsp+2Ch] [rbp-34h] BYREF
  char v22[4]; // [rsp+30h] [rbp-30h] BYREF
  char v23[4]; // [rsp+34h] [rbp-2Ch] BYREF
  _LARGE_INTEGER Time; // [rsp+38h] [rbp-28h] BYREF
  _TIME_FIELDS TimeFields; // [rsp+40h] [rbp-20h] BYREF

  if ( a2 < 0xF )
    return 0;
  if ( *(_BYTE *)(a1 + 14) != 90 )
    return 0;
  if ( *(_BYTE *)a1 != 23 )
    return 0;
  if ( *(_BYTE *)(a1 + 1) != 13 )
    return 0;
  strncpy_0(Dest, (const char *)(a1 + 2), 2u);
  Dest[2] = 0;
  strncpy_0(Str, (const char *)(a1 + 4), 2u);
  Str[2] = 0;
  strncpy_0(v20, (const char *)(a1 + 6), 2u);
  v20[2] = 0;
  strncpy_0(v21, (const char *)(a1 + 8), 2u);
  v21[2] = 0;
  strncpy_0(v22, (const char *)(a1 + 10), 2u);
  v22[2] = 0;
  strncpy_0(v23, (const char *)(a1 + 12), 2u);
  v23[2] = 0;
  v5 = atoi(Dest);
  v6 = v5;
  if ( !v5 && (Dest[0] != 48 || Dest[1] != 48) )
    return 0;
  v7 = v5 < 0x32 ? 2000 : 1900;
  v8 = atoi(Str);
  v9 = v8;
  if ( !v8 && (Str[0] != 48 || Str[1] != 48) )
    return 0;
  v10 = atoi(v20);
  v11 = v10;
  if ( !v10 && (v20[0] != 48 || v20[1] != 48) )
    return 0;
  v12 = atoi(v21);
  v13 = v12;
  if ( !v12 && (v21[0] != 48 || v21[1] != 48) )
    return 0;
  v14 = atoi(v22);
  v15 = v14;
  if ( !v14 && (v22[0] != 48 || v22[1] != 48) )
    return 0;
  v16 = atoi(v23);
  if ( !v16 && (v23[0] != 48 || v23[1] != 48) )
    return 0;
  *(_DWORD *)&TimeFields.Milliseconds = 0;
  TimeFields.Year = v6 + v7;
  TimeFields.Month = v9;
  TimeFields.Day = v11;
  TimeFields.Hour = v13;
  TimeFields.Minute = v15;
  TimeFields.Second = v16;
  Time.QuadPart = 0;
  LOBYTE(result) = RtlTimeFieldsToTime(&TimeFields, &Time);
  *a3 = Time;
  return (unsigned __int8)result;
}

```

## disassembly

```asm
0x180003370  mov     [rsp-38h+arg_8], rbx
0x180003375  push    rbp
0x180003376  push    rsi
0x180003377  push    rdi
0x180003378  push    r12
0x18000337a  push    r13
0x18000337c  push    r14
0x18000337e  push    r15
0x180003380  mov     rbp, rsp
0x180003383  sub     rsp, 60h
0x180003387  mov     rax, cs:__security_cookie
0x18000338e  xor     rax, rsp
0x180003391  mov     [rbp+var_10], rax
0x180003395  mov     r13, r8
0x180003398  mov     rbx, rcx
0x18000339b  cmp     edx, 0Fh
0x18000339e  jb      loc_18000358D
0x1800033a4  cmp     byte ptr [rcx+0Eh], 5Ah ; 'Z'
0x1800033a8  jnz     loc_18000358D
0x1800033ae  cmp     byte ptr [rcx], 17h
0x1800033b1  jnz     loc_18000358D
0x1800033b7  cmp     byte ptr [rcx+1], 0Dh
0x1800033bb  jnz     loc_18000358D
0x1800033c1  lea     rdx, [rcx+2]; Source
0x1800033c5  mov     edi, 2
0x1800033ca  mov     r8d, edi; Count
0x1800033cd  lea     rcx, [rbp+Dest]; Dest
0x1800033d1  call    strncpy_0
0x1800033d6  xor     esi, esi
0x1800033d8  lea     rdx, [rbx+4]; Source
0x1800033dc  mov     r8d, edi; Count
0x1800033df  mov     [rbp+var_3E], sil
0x1800033e3  lea     rcx, [rbp+Str]; Dest
0x1800033e7  call    strncpy_0
0x1800033ec  lea     rdx, [rbx+6]; Source
0x1800033f0  mov     [rbp+var_3A], sil
0x1800033f4  mov     r8d, edi; Count
0x1800033f7  lea     rcx, [rbp+var_38]; Dest
0x1800033fb  call    strncpy_0
0x180003400  lea     rdx, [rbx+8]; Source
0x180003404  mov     [rbp+var_36], sil
0x180003408  mov     r8d, edi; Count
0x18000340b  lea     rcx, [rbp+var_34]; Dest
0x18000340f  call    strncpy_0
0x180003414  lea     rdx, [rbx+0Ah]; Source
0x180003418  mov     [rbp+var_32], sil
0x18000341c  mov     r8d, edi; Count
0x18000341f  lea     rcx, [rbp+var_30]; Dest
0x180003423  call    strncpy_0
0x180003428  lea     rdx, [rbx+0Ch]; Source
0x18000342c  mov     [rbp+var_2E], sil
0x180003430  mov     r8d, edi; Count
0x180003433  lea     rcx, [rbp+var_2C]; Dest
0x180003437  call    strncpy_0
0x18000343c  lea     rcx, [rbp+Dest]; Str
0x180003440  mov     [rbp+var_2A], sil
0x180003444  call    cs:__imp_atoi
0x18000344b  nop     dword ptr [rax+rax+00h]
0x180003450  mov     r12d, eax
0x180003453  mov     dil, 30h ; '0'
0x180003456  test    eax, eax
0x180003458  jnz     short loc_18000346E
0x18000345a  cmp     [rbp+Dest], dil
0x18000345e  jnz     loc_18000358D
0x180003464  cmp     [rbp+var_3F], dil
0x180003468  jnz     loc_18000358D
0x18000346e  cmp     r12d, 32h ; '2'
0x180003472  lea     rcx, [rbp+Str]; Str
0x180003476  sbb     ebx, ebx
0x180003478  and     ebx, 64h
0x18000347b  add     ebx, 76Ch
0x180003481  call    cs:__imp_atoi
0x180003488  nop     dword ptr [rax+rax+00h]
0x18000348d  mov     r15d, eax
0x180003490  test    eax, eax
0x180003492  jnz     short loc_1800034A8
0x180003494  cmp     [rbp+Str], dil
0x180003498  jnz     loc_18000358D
0x18000349e  cmp     [rbp+var_3B], dil
0x1800034a2  jnz     loc_18000358D
0x1800034a8  lea     rcx, [rbp+var_38]; Str
0x1800034ac  call    cs:__imp_atoi
0x1800034b3  nop     dword ptr [rax+rax+00h]
0x1800034b8  mov     r14d, eax
0x1800034bb  test    eax, eax
0x1800034bd  jnz     short loc_1800034D3
0x1800034bf  cmp     [rbp+var_38], dil
0x1800034c3  jnz     loc_18000358D
0x1800034c9  cmp     [rbp+var_37], dil
0x1800034cd  jnz     loc_18000358D
0x1800034d3  lea     rcx, [rbp+var_34]; Str
0x1800034d7  call    cs:__imp_atoi
0x1800034de  nop     dword ptr [rax+rax+00h]
0x1800034e3  mov     esi, eax
0x1800034e5  test    eax, eax
0x1800034e7  jnz     short loc_1800034FD
0x1800034e9  cmp     [rbp+var_34], dil
0x1800034ed  jnz     loc_18000358D
0x1800034f3  cmp     [rbp+var_33], dil
0x1800034f7  jnz     loc_18000358D
0x1800034fd  lea     rcx, [rbp+var_30]; Str
0x180003501  call    cs:__imp_atoi
0x180003508  nop     dword ptr [rax+rax+00h]
0x18000350d  mov     edi, eax
0x18000350f  test    eax, eax
0x180003511  jnz     short loc_18000351F
0x180003513  cmp     [rbp+var_30], 30h ; '0'
0x180003517  jnz     short loc_18000358D
0x180003519  cmp     [rbp+var_2F], 30h ; '0'
0x18000351d  jnz     short loc_18000358D
0x18000351f  lea     rcx, [rbp+var_2C]; Str
0x180003523  call    cs:__imp_atoi
0x18000352a  nop     dword ptr [rax+rax+00h]
0x18000352f  test    eax, eax
0x180003531  jnz     short loc_18000353F
0x180003533  cmp     [rbp+var_2C], 30h ; '0'
0x180003537  jnz     short loc_18000358D
0x180003539  cmp     [rbp+var_2B], 30h ; '0'
0x18000353d  jnz     short loc_18000358D
0x18000353f  add     bx, r12w
0x180003543  mov     dword ptr [rbp+TimeFields.Milliseconds], 0
0x18000354a  lea     rdx, [rbp+Time]; Time
0x18000354e  mov     [rbp+TimeFields.Year], bx
0x180003552  lea     rcx, [rbp+TimeFields]; TimeFields
0x180003556  mov     [rbp+TimeFields.Month], r15w
0x18000355b  mov     [rbp+TimeFields.Day], r14w
0x180003560  mov     [rbp+TimeFields.Hour], si
0x180003564  mov     [rbp+TimeFields.Minute], di
0x180003568  mov     [rbp+TimeFields.Second], ax
0x18000356c  mov     qword ptr [rbp+Time], 0
0x180003574  call    cs:__imp_RtlTimeFieldsToTime
0x18000357b  nop     dword ptr [rax+rax+00h]
0x180003580  mov     rcx, qword ptr [rbp+Time]
0x180003584  mov     [r13+0], rcx
0x180003588  movzx   eax, al
0x18000358b  jmp     short loc_18000358F
0x18000358d  xor     eax, eax
0x18000358f  mov     rcx, [rbp+var_10]
0x180003593  xor     rcx, rsp; StackCookie
0x180003596  call    __security_check_cookie
0x18000359b  mov     rbx, [rsp+60h+arg_8]
0x1800035a3  add     rsp, 60h
0x1800035a7  pop     r15
0x1800035a9  pop     r14
0x1800035ab  pop     r13
0x1800035ad  pop     r12
0x1800035af  pop     rdi
0x1800035b0  pop     rsi
0x1800035b1  pop     rbp
0x1800035b2  retn
```
