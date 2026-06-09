# VerifyMultipleProtocolLists(uchar *,ulong,ulong)

- ea: `0x1400352d4`
- end: `0x1400353c5`
- name: `?VerifyMultipleProtocolLists@@YAJPEAEKK@Z`
- size: `241`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400351f0`
- `0x140035490`

## callees

- `0x1400352d4`
- `0x1400353cc`
- `0x14003573c`
- `0x140036444`

## pseudocode

```c
__int64 __fastcall VerifyMultipleProtocolLists(unsigned __int8 *a1, unsigned int a2, int a3)
{
  int v5; // r14d
  __int64 result; // rax
  int v7; // r8d
  int v8; // r8d
  int v9; // ebx
  int v10; // [rsp+40h] [rbp-20h] BYREF
  int v11; // [rsp+48h] [rbp-18h] BYREF
  int v12; // [rsp+4Ch] [rbp-14h]
  _BYTE *v13; // [rsp+50h] [rbp-10h] BYREF
  int v14; // [rsp+98h] [rbp+38h] BYREF

  v5 = (int)a1;
  result = VerifyOnlySizedElement(a1, a2);
  if ( (int)result >= 0 )
  {
    v13 = 0;
    v7 = 0;
    v14 = 0;
    while ( 1 )
    {
      v12 = 1;
      v11 = a3;
      SdpGetNextElement(v5, a2, v7, (unsigned int)&v13, (__int64)&v14);
      v9 = (int)v13;
      if ( !v13 )
        return 0;
      if ( (*v13 & 0xF8) != 0x30 )
        break;
      v10 = 0;
      LOBYTE(v8) = 6;
      result = SdpVerifySequenceOf((_DWORD)v13, v14, v8, 0, (__int64)&v10, (__int64)WalkProtocolSequence, (__int64)&v11);
      if ( (int)result < 0 )
        return result;
      if ( !v10 || !BYTE2(v12) && (a3 & 2) != 0 )
        break;
      v7 = v9;
    }
    return 3221225485LL;
  }
  return result;
}

```

## disassembly

```asm
0x1400352d4  mov     [rsp-18h+arg_0], rbx
0x1400352d9  mov     [rsp-18h+arg_8], rsi
0x1400352de  push    rbp
0x1400352df  push    rdi
0x1400352e0  push    r14
0x1400352e2  mov     rbp, rsp
0x1400352e5  sub     rsp, 60h
0x1400352e9  mov     edi, r8d
0x1400352ec  mov     esi, edx
0x1400352ee  mov     r14, rcx
0x1400352f1  call    ?VerifyOnlySizedElement@@YAJPEAEK@Z; VerifyOnlySizedElement(uchar *,ulong)
0x1400352f6  test    eax, eax
0x1400352f8  js      loc_1400353A8
0x1400352fe  mov     [rbp+var_10], 0
0x140035306  xor     r8d, r8d
0x140035309  mov     [rbp+arg_18], 0
0x140035310  jmp     short loc_14003536D
0x140035312  mov     al, [rbx]
0x140035314  and     al, 0F8h
0x140035316  cmp     al, 30h ; '0'
0x140035318  jnz     loc_1400353BE
0x14003531e  mov     edx, [rbp+arg_18]
0x140035321  lea     rax, [rbp+var_18]
0x140035325  mov     [rsp+60h+var_30], rax
0x14003532a  xor     r9d, r9d
0x14003532d  lea     rax, ?WalkProtocolSequence@@YAJPEAU_PROTOCOL_LIST_INFO@@EKPEAE@Z; WalkProtocolSequence(_PROTOCOL_LIST_INFO *,uchar,ulong,uchar *)
0x140035334  mov     [rbp+var_20], 0
0x14003533b  mov     [rsp+60h+var_38], rax
0x140035340  mov     r8b, 6
0x140035343  lea     rax, [rbp+var_20]
0x140035347  mov     rcx, rbx
0x14003534a  mov     [rsp+60h+var_40], rax
0x14003534f  call    SdpVerifySequenceOf
0x140035354  test    eax, eax
0x140035356  js      short loc_1400353A8
0x140035358  cmp     [rbp+var_20], 0
0x14003535c  jz      short loc_1400353BE
0x14003535e  cmp     byte ptr [rbp+var_18+6], 0
0x140035362  jnz     short loc_14003536A
0x140035364  test    dil, 2
0x140035368  jnz     short loc_1400353BE
0x14003536a  mov     r8, rbx
0x14003536d  mov     [rbp+var_18], 0
0x140035375  lea     rax, [rbp+arg_18]
0x140035379  lea     r9, [rbp+var_10]
0x14003537d  mov     [rsp+60h+var_40], rax
0x140035382  mov     edx, esi
0x140035384  mov     word ptr [rbp+var_18+4], 1
0x14003538a  mov     rcx, r14
0x14003538d  mov     byte ptr [rbp+var_18+6], 0
0x140035391  mov     dword ptr [rbp+var_18], edi
0x140035394  call    SdpGetNextElement
0x140035399  mov     rbx, [rbp+var_10]
0x14003539d  test    rbx, rbx
0x1400353a0  jnz     loc_140035312
0x1400353a6  xor     eax, eax
0x1400353a8  lea     r11, [rsp+60h+var_s0]
0x1400353ad  mov     rbx, [r11+20h]
0x1400353b1  mov     rsi, [r11+28h]
0x1400353b5  mov     rsp, r11
0x1400353b8  pop     r14
0x1400353ba  pop     rdi
0x1400353bb  pop     rbp
0x1400353bc  retn
0x1400353be  mov     eax, 0C000000Dh
0x1400353c3  jmp     short loc_1400353A8
```
