# LdrpInitializeDllPath

- ea: `0x1800bcba0`
- end: `0x1800bcd68`
- name: `LdrpInitializeDllPath`
- size: `456`
- prototype: ``
- caller_count: `12`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180053390`
- `0x1800bbb90`
- `0x1800bbda8`
- `0x1800bc71c`
- `0x1800bc9c0`
- `0x1800bd6e0`
- `0x1800be2e0`
- `0x1800d6508`
- `0x180105288`
- `0x180106c24`
- `0x1801253a0`
- `0x18015b538`

## callees

- `0x1800165d0`
- `0x18001d490`
- `0x18001eb80`
- `0x18004cef8`
- `0x1800526f0`
- `0x1800bcba0`

## string_xrefs

- `0x1800bcbfe`: `DLL search path passed in externally: %ws\n`
- `0x1800bcc0a`: `LdrpInitializeDllPath`

## pseudocode

```c
void __fastcall LdrpInitializeDllPath(int *a1, __int64 ArgList, __int64 *a3)
{
  int *v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  _DWORD *SharedData; // rcx
  __int64 v9; // rcx
  char *v10; // rcx
  __int64 v11; // rdi
  char v12; // bl
  char v13; // al
  __int128 v14; // [rsp+30h] [rbp-28h] BYREF
  __int128 v15; // [rsp+40h] [rbp-18h] BYREF

  v4 = a1;
  *(_OWORD *)a3 = 0;
  *((_OWORD *)a3 + 1) = 0;
  *((_OWORD *)a3 + 2) = 0;
  *((_OWORD *)a3 + 3) = 0;
  *((_OWORD *)a3 + 4) = 0;
  *((_OWORD *)a3 + 5) = 0;
  *((_OWORD *)a3 + 6) = 0;
  *((_OWORD *)a3 + 7) = 0;
  if ( (ArgList & 1) != 0 || !ArgList )
  {
    a3[4] = (__int64)a1;
    *((_DWORD *)a3 + 6) = ArgList & 0xFFFFFFFE;
  }
  else
  {
    *a3 = ArgList;
    LdrpLogInternal(
      (int)"minkernel\\ldr\\ldrutil.c",
      1552,
      (int)"LdrpInitializeDllPath",
      2,
      "DLL search path passed in externally: %ws\n",
      ArgList);
    v15 = 0;
    SharedData = NtCurrentPeb()->SharedData;
    v14 = 0;
    if ( SharedData && *SharedData )
      v9 = (__int64)NtCurrentPeb()->SharedData + 554;
    else
      v9 = 2147353476;
    if ( *(_BYTE *)v9 && (NtCurrentPeb()->TracingFlags & 4) != 0 )
    {
      v10 = (unsigned int)RtlGetCurrentServiceSessionId(v9, v5, v6, v7)
          ? (char *)NtCurrentPeb()->SharedData + 555
          : (char *)2147353477;
      if ( (*v10 & 0x20) != 0 )
      {
        v11 = *a3;
        if ( !v4 )
          v4 = &dword_1801764CC;
        v12 = RtlCreateUnicodeString(&v15, v4);
        v13 = RtlCreateUnicodeString(&v14, v11);
        if ( v12 )
        {
          if ( v13 )
          {
            LdrpLogEtwEvent(5312, 0, 0, 0, (__int64)&v14, (__int64)&v15);
            if ( *((_QWORD *)&v14 + 1) )
              RtlpSysVolFree(*((_QWORD *)&v14 + 1));
          }
          if ( *((_QWORD *)&v15 + 1) )
            RtlpSysVolFree(*((_QWORD *)&v15 + 1));
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800bcba0  mov     [rsp+arg_8], rbx
0x1800bcba5  push    rsi
0x1800bcba6  sub     rsp, 50h
0x1800bcbaa  xorps   xmm0, xmm0
0x1800bcbad  mov     rbx, r8
0x1800bcbb0  mov     rsi, rcx
0x1800bcbb3  movups  xmmword ptr [r8], xmm0
0x1800bcbb7  movups  xmmword ptr [r8+10h], xmm0
0x1800bcbbc  movups  xmmword ptr [r8+20h], xmm0
0x1800bcbc1  movups  xmmword ptr [r8+30h], xmm0
0x1800bcbc6  movups  xmmword ptr [r8+40h], xmm0
0x1800bcbcb  movups  xmmword ptr [r8+50h], xmm0
0x1800bcbd0  movups  xmmword ptr [r8+60h], xmm0
0x1800bcbd5  movups  xmmword ptr [r8+70h], xmm0
0x1800bcbda  test    dl, 1
0x1800bcbdd  jz      short loc_1800BCBF6
0x1800bcbdf  and     edx, 0FFFFFFFEh
0x1800bcbe2  mov     [r8+20h], rsi
0x1800bcbe6  mov     [r8+18h], edx
0x1800bcbea  mov     rbx, [rsp+58h+arg_8]
0x1800bcbef  add     rsp, 50h
0x1800bcbf3  pop     rsi
0x1800bcbf4  retn
0x1800bcbf6  test    rdx, rdx
0x1800bcbf9  jz      short loc_1800BCBDF
0x1800bcbfb  mov     [r8], rdx
0x1800bcbfe  lea     rax, aDllSearchPathP; "DLL search path passed in externally: %"...
0x1800bcc05  mov     qword ptr [rsp+58h+ArgList], rdx; ArgList
0x1800bcc0a  lea     r8, aLdrpinitialize_12; "LdrpInitializeDllPath"
0x1800bcc11  mov     edx, 610h; int
0x1800bcc16  mov     [rsp+58h+Format], rax; Format
0x1800bcc1b  mov     r9d, 2; int
0x1800bcc21  lea     rcx, aMinkernelLdrLd_2; "minkernel\\ldr\\ldrutil.c"
0x1800bcc28  call    LdrpLogInternal
0x1800bcc2d  mov     rax, gs:60h
0x1800bcc36  xorps   xmm0, xmm0
0x1800bcc39  xorps   xmm1, xmm1
0x1800bcc3c  movups  [rsp+58h+var_18], xmm0
0x1800bcc41  mov     rcx, [rax+90h]
0x1800bcc48  movups  [rsp+58h+var_28], xmm1
0x1800bcc4d  test    rcx, rcx
0x1800bcc50  jnz     loc_1800BCD39
0x1800bcc56  mov     ecx, 7FFE0384h
0x1800bcc5b  cmp     byte ptr [rcx], 0
0x1800bcc5e  jz      short loc_1800BCBEA
0x1800bcc60  mov     rax, gs:60h
0x1800bcc69  test    byte ptr [rax+378h], 4
0x1800bcc70  jz      loc_1800BCBEA
0x1800bcc76  call    RtlGetCurrentServiceSessionId
0x1800bcc7b  test    eax, eax
0x1800bcc7d  jz      loc_1800BCD5E
0x1800bcc83  mov     rax, gs:60h
0x1800bcc8c  mov     rcx, [rax+90h]
0x1800bcc93  add     rcx, 22Bh
0x1800bcc9a  test    byte ptr [rcx], 20h
0x1800bcc9d  jz      loc_1800BCBEA
0x1800bcca3  lea     rax, dword_1801764CC
0x1800bccaa  mov     [rsp+58h+arg_0], rdi
0x1800bccaf  mov     rdi, [rbx]
0x1800bccb2  lea     rcx, [rsp+58h+var_18]
0x1800bccb7  test    rsi, rsi
0x1800bccba  cmovz   rsi, rax
0x1800bccbe  mov     rdx, rsi
0x1800bccc1  call    RtlCreateUnicodeString
0x1800bccc6  mov     rdx, rdi
0x1800bccc9  lea     rcx, [rsp+58h+var_28]
0x1800bccce  movzx   ebx, al
0x1800bccd1  call    RtlCreateUnicodeString
0x1800bccd6  mov     rdi, [rsp+58h+arg_0]
0x1800bccdb  test    bl, bl
0x1800bccdd  jz      loc_1800BCBEA
0x1800bcce3  test    al, al
0x1800bcce5  jz      short loc_1800BCD1C
0x1800bcce7  lea     rax, [rsp+58h+var_18]
0x1800bccec  mov     ecx, 14C0h
0x1800bccf1  mov     qword ptr [rsp+58h+ArgList], rax
0x1800bccf6  xor     r9d, r9d
0x1800bccf9  lea     rax, [rsp+58h+var_28]
0x1800bccfe  xor     r8d, r8d
0x1800bcd01  xor     edx, edx
0x1800bcd03  mov     [rsp+58h+Format], rax
0x1800bcd08  call    LdrpLogEtwEvent
0x1800bcd0d  mov     rcx, qword ptr [rsp+58h+var_28+8]
0x1800bcd12  test    rcx, rcx
0x1800bcd15  jz      short loc_1800BCD1C
0x1800bcd17  call    RtlpSysVolFree
0x1800bcd1c  mov     rcx, qword ptr [rsp+58h+var_18+8]
0x1800bcd21  test    rcx, rcx
0x1800bcd24  jz      loc_1800BCBEA
0x1800bcd2a  mov     rbx, [rsp+58h+arg_8]
0x1800bcd2f  add     rsp, 50h
0x1800bcd33  pop     rsi
0x1800bcd34  jmp     RtlpSysVolFree
0x1800bcd39  cmp     dword ptr [rcx], 0
0x1800bcd3c  jz      loc_1800BCC56
0x1800bcd42  mov     rax, gs:60h
0x1800bcd4b  mov     rcx, [rax+90h]
0x1800bcd52  add     rcx, 22Ah
0x1800bcd59  jmp     loc_1800BCC5B
0x1800bcd5e  mov     ecx, 7FFE0385h
0x1800bcd63  jmp     loc_1800BCC9A
```
