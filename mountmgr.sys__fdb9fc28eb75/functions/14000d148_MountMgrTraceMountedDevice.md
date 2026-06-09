# MountMgrTraceMountedDevice

- ea: `0x14000d148`
- end: `0x14000d3a5`
- name: `MountMgrTraceMountedDevice`
- size: `605`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14000d3ac`

## callees

- `0x140001b30`
- `0x140002490`
- `0x140002520`
- `0x14000263c`
- `0x14000d148`

## pseudocode

```c
__int64 __fastcall MountMgrTraceMountedDevice(int a1, __int64 a2)
{
  char v3; // r15
  const char *v4; // r8
  const char *v5; // rdx
  const char *v6; // rbp
  const char *v7; // rsi
  const char *v8; // rdi
  const char *v9; // rbx
  const char *v10; // r11
  const char *v11; // r10
  const wchar_t *v12; // r8
  __int64 *v13; // rbx
  const wchar_t *v14; // r9
  __int64 *i; // rbx
  const wchar_t *v16; // r9
  char v18; // [rsp+D0h] [rbp+8h]

  v18 = a1;
  v3 = a1;
  v4 = "FALSE";
  v5 = "TRUE";
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v6 = "TRUE";
    v7 = "TRUE";
    v8 = "TRUE";
    v9 = "TRUE";
    v10 = "TRUE";
    v11 = "TRUE";
    if ( !*(_BYTE *)(a2 + 134) )
      v6 = "FALSE";
    if ( !*(_BYTE *)(a2 + 133) )
      v7 = "FALSE";
    if ( !*(_BYTE *)(a2 + 132) )
      v8 = "FALSE";
    if ( !*(_BYTE *)(a2 + 131) )
      v9 = "FALSE";
    if ( !*(_BYTE *)(a2 + 124) )
      v10 = "FALSE";
    if ( !*(_BYTE *)(a2 + 130) )
      v11 = "FALSE";
    v12 = L"NULL";
    if ( *(_QWORD *)(a2 + 88) )
      v12 = *(const wchar_t **)(a2 + 88);
    WPP_SF_iSsdsssssdiDDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      *(unsigned __int8 *)(a2 + 128),
      (_DWORD)v12,
      a2 ^ a1,
      (__int64)v12,
      (__int64)v11,
      *(_BYTE *)(a2 + 128),
      (__int64)v10,
      (__int64)v9,
      (__int64)v8,
      (__int64)v7,
      (__int64)v6,
      *(_DWORD *)(a2 + 136),
      *(_QWORD *)(a2 + 176),
      *(_DWORD *)(a2 + 160),
      *(_DWORD *)(a2 + 164),
      *(_DWORD *)(a2 + 168),
      *(_DWORD *)(a2 + 172));
    v5 = "TRUE";
  }
  v13 = *(__int64 **)(a2 + 16);
  if ( v13 != (__int64 *)(a2 + 16) )
  {
    do
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v14 = L"NONE";
        if ( !*((_BYTE *)v13 + 16) )
          v5 = "FALSE";
        if ( v13[4] )
          LODWORD(v14) = v13[4];
        WPP_SF_Ss(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)v5, (_DWORD)v4, (_DWORD)v14, (__int64)v5);
      }
      v13 = (__int64 *)*v13;
      v5 = "TRUE";
    }
    while ( v13 != (__int64 *)(a2 + 16) );
    v3 = v18;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 335);
  }
  for ( i = *(__int64 **)(a2 + 48); i != (__int64 *)(a2 + 48); i = (__int64 *)*i )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v16 = L"NONE";
      if ( i[4] )
        v16 = (const wchar_t *)i[4];
      WPP_SF_Si(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)v5, (_DWORD)v4, (_DWORD)v16, *((_BYTE *)i + 16) ^ v3);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000d148  mov     [rsp+arg_0], rcx
0x14000d14d  push    rbx
0x14000d14e  push    rbp
0x14000d14f  push    rsi
0x14000d150  push    rdi
0x14000d151  push    r14
0x14000d153  push    r15
0x14000d155  sub     rsp, 98h
0x14000d15c  mov     r14, rdx
0x14000d15f  mov     r15, rcx
0x14000d162  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d169  lea     rax, WPP_GLOBAL_Control
0x14000d170  lea     r8, aFalse; "FALSE"
0x14000d177  lea     rdx, aTrue; "TRUE"
0x14000d17e  cmp     rcx, rax
0x14000d181  jz      loc_14000D29A
0x14000d187  mov     eax, [rcx+2Ch]
0x14000d18a  test    al, 8
0x14000d18c  jz      loc_14000D293
0x14000d192  cmp     byte ptr [rcx+29h], 2
0x14000d196  jb      loc_14000D293
0x14000d19c  mov     rax, [r14+58h]
0x14000d1a0  mov     rbp, rdx
0x14000d1a3  mov     rcx, [rcx+18h]
0x14000d1a7  mov     rsi, rdx
0x14000d1aa  mov     rdi, rdx
0x14000d1ad  mov     rbx, rdx
0x14000d1b0  mov     r11, rdx
0x14000d1b3  mov     r10, rdx
0x14000d1b6  movzx   edx, byte ptr [r14+80h]
0x14000d1be  mov     r9, r15
0x14000d1c1  xor     r9, r14
0x14000d1c4  cmp     byte ptr [r14+86h], 0
0x14000d1cc  cmovz   rbp, r8
0x14000d1d0  cmp     byte ptr [r14+85h], 0
0x14000d1d8  cmovz   rsi, r8
0x14000d1dc  cmp     byte ptr [r14+84h], 0
0x14000d1e4  cmovz   rdi, r8
0x14000d1e8  cmp     byte ptr [r14+83h], 0
0x14000d1f0  cmovz   rbx, r8
0x14000d1f4  cmp     byte ptr [r14+7Ch], 0
0x14000d1f9  cmovz   r11, r8
0x14000d1fd  cmp     byte ptr [r14+82h], 0
0x14000d205  cmovz   r10, r8
0x14000d209  test    rax, rax
0x14000d20c  lea     r8, aNull_0; "NULL"
0x14000d213  cmovnz  r8, rax
0x14000d217  mov     eax, [r14+0ACh]
0x14000d21e  mov     [rsp+0C8h+var_40], eax
0x14000d225  mov     eax, [r14+0A8h]
0x14000d22c  mov     [rsp+0C8h+var_48], eax
0x14000d233  mov     eax, [r14+0A4h]
0x14000d23a  mov     [rsp+0C8h+var_50], eax
0x14000d23e  mov     eax, [r14+0A0h]
0x14000d245  mov     [rsp+0C8h+var_58], eax
0x14000d249  mov     rax, [r14+0B0h]
0x14000d250  mov     [rsp+0C8h+var_60], rax
0x14000d255  mov     eax, [r14+88h]
0x14000d25c  mov     [rsp+0C8h+var_68], eax
0x14000d260  mov     [rsp+0C8h+var_70], rbp
0x14000d265  mov     [rsp+0C8h+var_78], rsi
0x14000d26a  mov     [rsp+0C8h+var_80], rdi
0x14000d26f  mov     [rsp+0C8h+var_88], rbx
0x14000d274  mov     [rsp+0C8h+var_90], r11
0x14000d279  mov     [rsp+0C8h+var_98], edx
0x14000d27d  mov     [rsp+0C8h+var_A0], r10
0x14000d282  mov     [rsp+0C8h+var_A8], r8
0x14000d287  call    WPP_SF_iSsdsssssdiDDDD
0x14000d28c  lea     rdx, aTrue; "TRUE"
0x14000d293  lea     rax, WPP_GLOBAL_Control
0x14000d29a  lea     rdi, [r14+10h]
0x14000d29e  mov     rbx, [rdi]
0x14000d2a1  cmp     rbx, rdi
0x14000d2a4  jz      short loc_14000D30C
0x14000d2a6  lea     r15, aFalse; "FALSE"
0x14000d2ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d2b4  cmp     rcx, rax
0x14000d2b7  jz      short loc_14000D2F5
0x14000d2b9  mov     eax, [rcx+2Ch]
0x14000d2bc  test    al, 8
0x14000d2be  jz      short loc_14000D2EE
0x14000d2c0  cmp     byte ptr [rcx+29h], 2
0x14000d2c4  jb      short loc_14000D2EE
0x14000d2c6  cmp     byte ptr [rbx+10h], 0
0x14000d2ca  lea     r9, aNone; "NONE"
0x14000d2d1  mov     rax, [rbx+20h]
0x14000d2d5  mov     rcx, [rcx+18h]
0x14000d2d9  cmovz   rdx, r15
0x14000d2dd  test    rax, rax
0x14000d2e0  mov     [rsp+0C8h+var_A8], rdx
0x14000d2e5  cmovnz  r9, rax
0x14000d2e9  call    WPP_SF_Ss
0x14000d2ee  lea     rax, WPP_GLOBAL_Control
0x14000d2f5  mov     rbx, [rbx]
0x14000d2f8  lea     rdx, aTrue; "TRUE"
0x14000d2ff  cmp     rbx, rdi
0x14000d302  jnz     short loc_14000D2AD
0x14000d304  mov     r15, [rsp+0C8h+arg_0]
0x14000d30c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d313  cmp     rcx, rax
0x14000d316  jz      short loc_14000D33A
0x14000d318  mov     eax, [rcx+2Ch]
0x14000d31b  test    al, 8
0x14000d31d  jz      short loc_14000D333
0x14000d31f  cmp     byte ptr [rcx+29h], 2
0x14000d323  jb      short loc_14000D333
0x14000d325  mov     rcx, [rcx+18h]
0x14000d329  mov     edx, 14Fh
0x14000d32e  call    WPP_SF_
0x14000d333  lea     rax, WPP_GLOBAL_Control
0x14000d33a  lea     rdi, [r14+30h]
0x14000d33e  mov     rbx, [rdi]
0x14000d341  jmp     short loc_14000D38D
0x14000d343  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d34a  cmp     rcx, rax
0x14000d34d  jz      short loc_14000D38A
0x14000d34f  mov     eax, [rcx+2Ch]
0x14000d352  test    al, 8
0x14000d354  jz      short loc_14000D383
0x14000d356  cmp     byte ptr [rcx+29h], 2
0x14000d35a  jb      short loc_14000D383
0x14000d35c  mov     rax, [rbx+20h]
0x14000d360  lea     r9, aNone; "NONE"
0x14000d367  mov     rcx, [rcx+18h]
0x14000d36b  test    rax, rax
0x14000d36e  cmovnz  r9, rax
0x14000d372  mov     rax, r15
0x14000d375  xor     rax, [rbx+10h]
0x14000d379  mov     [rsp+0C8h+var_A8], rax
0x14000d37e  call    WPP_SF_Si
0x14000d383  lea     rax, WPP_GLOBAL_Control
0x14000d38a  mov     rbx, [rbx]
0x14000d38d  cmp     rbx, rdi
0x14000d390  jnz     short loc_14000D343
0x14000d392  xor     eax, eax
0x14000d394  add     rsp, 98h
0x14000d39b  pop     r15
0x14000d39d  pop     r14
0x14000d39f  pop     rdi
0x14000d3a0  pop     rsi
0x14000d3a1  pop     rbp
0x14000d3a2  pop     rbx
0x14000d3a3  retn
```
