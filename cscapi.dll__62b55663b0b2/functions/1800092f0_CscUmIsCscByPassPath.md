# CscUmIsCscByPassPath

- ea: `0x1800092f0`
- end: `0x1800093bf`
- name: `CscUmIsCscByPassPath`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800091d4`

## callees

- `0x1800092f0`

## import_xrefs

- `ntdll!RtlEqualUnicodeString` at `0x18000939d`
- `ntdll!RtlEqualUnicodeString` at `0x18000939d`

## pseudocode

```c
__int64 __fastcall CscUmIsCscByPassPath(unsigned __int16 *a1, char *a2)
{
  char v2; // di
  unsigned __int64 v4; // r9
  __int64 v5; // r10
  unsigned __int16 v6; // cx
  unsigned __int16 v7; // dx
  char v8; // r8
  unsigned int v9; // ebx
  UNICODE_STRING String2; // [rsp+20h] [rbp-38h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-28h] BYREF
  __int64 v13; // [rsp+40h] [rbp-18h]

  v13 = 0;
  v2 = 0;
  *(_QWORD *)&String2.Length = 1048590;
  String2.Buffer = L"$NOCSC$";
  v4 = *a1;
  String1 = 0;
  if ( v4 < 4 )
  {
LABEL_11:
    v9 = -1073741585;
  }
  else
  {
    v5 = *((_QWORD *)a1 + 1);
    v6 = 2;
    v7 = v13;
    v8 = 0;
    do
    {
      if ( *(_WORD *)(v5 + 2LL * v6) == 92 )
      {
        if ( v8 )
          goto LABEL_8;
        v8 = 1;
        v7 = 2 * v6;
      }
      ++v6;
    }
    while ( v4 >= 2 * (unsigned __int64)v6 );
    if ( !v8 )
      goto LABEL_11;
LABEL_8:
    v9 = 0;
    if ( v7 >= 0xEu )
    {
      *(_DWORD *)&String1.Length = 917518;
      String1.Buffer = (PWSTR)(v5 + v7 - 14LL);
      if ( RtlEqualUnicodeString(&String1, &String2, 1u) )
        v2 = 1;
    }
  }
  *a2 = v2;
  return v9;
}

```

## disassembly

```asm
0x1800092f0  push    rbp
0x1800092f2  push    rbx
0x1800092f3  push    rsi
0x1800092f4  push    rdi
0x1800092f5  mov     rbp, rsp
0x1800092f8  sub     rsp, 58h
0x1800092fc  mov     rax, rcx
0x1800092ff  mov     [rbp+var_18], 0
0x180009307  xor     dil, dil
0x18000930a  mov     qword ptr [rbp+String2.Length], 10000Eh
0x180009312  lea     rcx, aNocsc; "$NOCSC$"
0x180009319  xorps   xmm0, xmm0
0x18000931c  mov     rsi, rdx
0x18000931f  mov     [rbp+String2.Buffer], rcx
0x180009323  movzx   r9d, word ptr [rax]
0x180009327  mov     r11d, 0Eh
0x18000932d  movups  xmmword ptr [rbp+String1.Length], xmm0
0x180009331  cmp     r9, 4
0x180009335  jb      short loc_1800093AC
0x180009337  mov     r10, [rax+8]
0x18000933b  lea     ecx, [r11-0Ch]
0x18000933f  movzx   edx, word ptr [rbp+var_18]
0x180009343  xor     r8b, r8b
0x180009346  movzx   eax, cx
0x180009349  cmp     word ptr [r10+rax*2], 5Ch ; '\'
0x18000934f  jnz     short loc_18000935F
0x180009351  test    r8b, r8b
0x180009354  jnz     short loc_180009372
0x180009356  movzx   edx, cx
0x180009359  mov     r8b, 1
0x18000935c  add     dx, dx
0x18000935f  inc     cx
0x180009362  movzx   eax, cx
0x180009365  add     rax, rax
0x180009368  cmp     r9, rax
0x18000936b  jnb     short loc_180009346
0x18000936d  test    r8b, r8b
0x180009370  jz      short loc_1800093AC
0x180009372  xor     ebx, ebx
0x180009374  cmp     dx, r11w
0x180009378  jb      short loc_1800093B1
0x18000937a  movzx   ecx, dx
0x18000937d  mov     r8b, 1; CaseInsensitive
0x180009380  movzx   eax, r11w
0x180009384  lea     rdx, [rbp+String2]; String2
0x180009388  sub     rcx, rax
0x18000938b  mov     dword ptr [rbp+String1.Length], 0E000Eh
0x180009392  add     rcx, r10
0x180009395  mov     [rbp+String1.Buffer], rcx
0x180009399  lea     rcx, [rbp+String1]; String1
0x18000939d  call    cs:__imp_RtlEqualUnicodeString
0x1800093a3  test    al, al
0x1800093a5  jz      short loc_1800093B1
0x1800093a7  mov     dil, 1
0x1800093aa  jmp     short loc_1800093B1
0x1800093ac  mov     ebx, 0C00000EFh
0x1800093b1  mov     [rsi], dil
0x1800093b4  mov     eax, ebx
0x1800093b6  add     rsp, 58h
0x1800093ba  pop     rdi
0x1800093bb  pop     rsi
0x1800093bc  pop     rbx
0x1800093bd  pop     rbp
0x1800093be  retn
```
