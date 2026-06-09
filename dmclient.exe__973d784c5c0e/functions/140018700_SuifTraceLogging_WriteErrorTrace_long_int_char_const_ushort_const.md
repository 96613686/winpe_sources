# SuifTraceLogging::WriteErrorTrace(long,int,char const *,ushort const *)

- ea: `0x140018700`
- end: `0x140018847`
- name: `?WriteErrorTrace@SuifTraceLogging@@CAXJHPEBDPEBG@Z`
- size: `327`
- prototype: `void __fastcall(int, int, const char *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140018850`

## callees

- `0x140001840`
- `0x140018700`
- `0x140019610`

## pseudocode

```c
void __fastcall SuifTraceLogging::WriteErrorTrace(int a1, int a2, const char *a3, const unsigned __int16 *a4)
{
  int v4; // r11d
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // ecx
  int v8; // [rsp+30h] [rbp-39h] BYREF
  int v9; // [rsp+34h] [rbp-35h] BYREF
  __int64 v10; // [rsp+38h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+40h] [rbp-29h] BYREF
  const unsigned __int16 *v12; // [rsp+60h] [rbp-9h]
  int v13; // [rsp+68h] [rbp-1h]
  int v14; // [rsp+6Ch] [rbp+3h]
  int *v15; // [rsp+70h] [rbp+7h]
  __int64 v16; // [rsp+78h] [rbp+Fh]
  const char *v17; // [rsp+80h] [rbp+17h]
  int v18; // [rsp+88h] [rbp+1Fh]
  int v19; // [rsp+8Ch] [rbp+23h]
  int *v20; // [rsp+90h] [rbp+27h]
  __int64 v21; // [rsp+98h] [rbp+2Fh]
  __int64 *v22; // [rsp+A0h] [rbp+37h]
  __int64 v23; // [rsp+A8h] [rbp+3Fh]

  v4 = 2;
  if ( (unsigned int)dword_140028000 > 2
    && (qword_140028010 & 0x400000000000LL) != 0
    && (qword_140028018 & 0x400000000000LL) == qword_140028018 )
  {
    v8 = a2;
    v22 = &v10;
    v10 = 0x1000000;
    v20 = &v8;
    v5 = -1;
    v9 = a1;
    v23 = 8;
    v21 = 4;
    if ( a3 )
    {
      v6 = -1;
      do
        ++v6;
      while ( a3[v6] );
      v7 = v6 + 1;
    }
    else
    {
      a3 = (const char *)&word_14001D5D2;
      v7 = 1;
    }
    v18 = v7;
    v15 = &v9;
    v17 = a3;
    v19 = 0;
    v16 = 4;
    if ( a4 )
    {
      do
        ++v5;
      while ( a4[v5] );
      v4 = 2 * v5 + 2;
    }
    else
    {
      a4 = (const unsigned __int16 *)&dword_14001D5D4;
    }
    v12 = a4;
    v14 = 0;
    v13 = v4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_140028000, (unsigned __int8 *)byte_140023FC9, 0, 0, 7u, &v11);
  }
}

```

## disassembly

```asm
0x140018700  mov     [rsp-8+arg_0], rbx
0x140018705  push    rbp
0x140018706  lea     rbp, [rsp-57h]
0x14001870b  sub     rsp, 0C0h
0x140018712  mov     rax, cs:__security_cookie
0x140018719  xor     rax, rsp
0x14001871c  mov     [rbp+57h+var_10], rax
0x140018720  mov     eax, cs:dword_140028000
0x140018726  mov     r11d, 2
0x14001872c  cmp     eax, r11d
0x14001872f  jbe     loc_140018829
0x140018735  mov     r10, cs:qword_140028018
0x14001873c  mov     rbx, 400000000000h
0x140018746  mov     rax, cs:qword_140028010
0x14001874d  test    rbx, rax
0x140018750  jz      loc_140018829
0x140018756  mov     rax, r10
0x140018759  and     rax, rbx
0x14001875c  cmp     rax, r10
0x14001875f  jnz     loc_140018829
0x140018765  lea     rax, [rbp+57h+var_88]
0x140018769  mov     [rbp+57h+var_90], edx
0x14001876c  mov     [rbp+57h+var_20], rax
0x140018770  xor     edx, edx
0x140018772  lea     rax, [rbp+57h+var_90]
0x140018776  mov     [rbp+57h+var_88], 1000000h
0x14001877e  mov     [rbp+57h+var_30], rax
0x140018782  or      rax, 0FFFFFFFFFFFFFFFFh
0x140018786  mov     [rbp+57h+var_8C], ecx
0x140018789  mov     [rbp+57h+var_18], 8
0x140018791  mov     [rbp+57h+var_28], 4
0x140018799  test    r8, r8
0x14001879c  jz      short loc_1400187AE
0x14001879e  mov     rcx, rax
0x1400187a1  inc     rcx
0x1400187a4  cmp     [r8+rcx], dl
0x1400187a8  jnz     short loc_1400187A1
0x1400187aa  inc     ecx
0x1400187ac  jmp     short loc_1400187BA
0x1400187ae  lea     r8, word_14001D5D2
0x1400187b5  mov     ecx, 1
0x1400187ba  mov     [rbp+57h+var_38], ecx
0x1400187bd  lea     rcx, [rbp+57h+var_8C]
0x1400187c1  mov     [rbp+57h+var_50], rcx
0x1400187c5  mov     [rbp+57h+var_40], r8
0x1400187c9  mov     [rbp+57h+var_34], edx
0x1400187cc  mov     [rbp+57h+var_48], 4
0x1400187d4  test    r9, r9
0x1400187d7  jz      short loc_1400187ED
0x1400187d9  inc     rax
0x1400187dc  cmp     [r9+rax*2], dx
0x1400187e1  jnz     short loc_1400187D9
0x1400187e3  lea     r11d, ds:2[rax*2]
0x1400187eb  jmp     short loc_1400187F4
0x1400187ed  lea     r9, dword_14001D5D4
0x1400187f4  lea     rax, [rbp+57h+var_80]
0x1400187f8  mov     [rbp+57h+var_60], r9
0x1400187fc  mov     [rbp+57h+var_54], edx
0x1400187ff  lea     rcx, dword_140028000
0x140018806  mov     [rsp+0C0h+var_98], rax
0x14001880b  lea     rdx, byte_140023FC9
0x140018812  xor     r9d, r9d
0x140018815  mov     [rsp+0C0h+var_A0], 7
0x14001881d  xor     r8d, r8d
0x140018820  mov     [rbp+57h+var_58], r11d
0x140018824  call    _tlgWriteTransfer_EventWriteTransfer
0x140018829  mov     rcx, [rbp+57h+var_10]
0x14001882d  xor     rcx, rsp; StackCookie
0x140018830  call    __security_check_cookie
0x140018835  mov     rbx, [rsp+0C0h+arg_0]
0x14001883d  add     rsp, 0C0h
0x140018844  pop     rbp
0x140018845  retn
```
