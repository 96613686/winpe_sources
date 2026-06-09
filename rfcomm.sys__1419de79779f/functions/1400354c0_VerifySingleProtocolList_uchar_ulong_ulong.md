# VerifySingleProtocolList(uchar *,ulong,ulong)

- ea: `0x1400354c0`
- end: `0x140035567`
- name: `?VerifySingleProtocolList@@YAJPEAEKK@Z`
- size: `167`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400351f0`
- `0x140035490`

## callees

- `0x1400353cc`
- `0x1400354c0`
- `0x14003573c`

## pseudocode

```c
__int64 __fastcall VerifySingleProtocolList(unsigned __int8 *a1, unsigned int a2, int a3)
{
  int v5; // ebx
  __int64 result; // rax
  int v7; // r8d
  int v8; // [rsp+50h] [rbp+8h] BYREF
  __int64 v9; // [rsp+68h] [rbp+20h] BYREF

  v5 = (int)a1;
  if ( (*a1 & 0xF8) != 0x30 )
    return 3221225485LL;
  v9 = 0;
  result = VerifyOnlySizedElement(a1, a2);
  if ( (int)result >= 0 )
  {
    WORD2(v9) = 1;
    BYTE6(v9) = 0;
    LOBYTE(v7) = 6;
    LODWORD(v9) = a3;
    v8 = 0;
    result = SdpVerifySequenceOf(v5, a2, v7, 0, (__int64)&v8, (__int64)WalkProtocolSequence, (__int64)&v9);
    if ( (int)result >= 0 && (!v8 || !BYTE6(v9) && (a3 & 2) != 0) )
      return 3221225485LL;
  }
  return result;
}

```

## disassembly

```asm
0x1400354c0  mov     [rsp+arg_8], rbx
0x1400354c5  mov     [rsp+arg_10], rsi
0x1400354ca  push    rdi
0x1400354cb  sub     rsp, 40h
0x1400354cf  mov     al, [rcx]
0x1400354d1  mov     edi, r8d
0x1400354d4  and     al, 0F8h
0x1400354d6  mov     esi, edx
0x1400354d8  mov     rbx, rcx
0x1400354db  cmp     al, 30h ; '0'
0x1400354dd  jnz     short loc_140035551
0x1400354df  mov     [rsp+48h+arg_18], 0
0x1400354e8  call    ?VerifyOnlySizedElement@@YAJPEAEK@Z; VerifyOnlySizedElement(uchar *,ulong)
0x1400354ed  test    eax, eax
0x1400354ef  js      short loc_140035556
0x1400354f1  lea     rax, [rsp+48h+arg_18]
0x1400354f6  mov     word ptr [rsp+48h+arg_18+4], 1
0x1400354fd  mov     [rsp+48h+var_18], rax
0x140035502  xor     r9d, r9d
0x140035505  lea     rax, ?WalkProtocolSequence@@YAJPEAU_PROTOCOL_LIST_INFO@@EKPEAE@Z; WalkProtocolSequence(_PROTOCOL_LIST_INFO *,uchar,ulong,uchar *)
0x14003550c  mov     byte ptr [rsp+48h+arg_18+6], 0
0x140035511  mov     [rsp+48h+var_20], rax
0x140035516  mov     r8b, 6
0x140035519  lea     rax, [rsp+48h+arg_0]
0x14003551e  mov     dword ptr [rsp+48h+arg_18], edi
0x140035522  mov     edx, esi
0x140035524  mov     [rsp+48h+var_28], rax
0x140035529  mov     rcx, rbx
0x14003552c  mov     [rsp+48h+arg_0], 0
0x140035534  call    SdpVerifySequenceOf
0x140035539  test    eax, eax
0x14003553b  js      short loc_140035556
0x14003553d  cmp     [rsp+48h+arg_0], 0
0x140035542  jz      short loc_140035551
0x140035544  cmp     byte ptr [rsp+48h+arg_18+6], 0
0x140035549  jnz     short loc_140035556
0x14003554b  test    dil, 2
0x14003554f  jz      short loc_140035556
0x140035551  mov     eax, 0C000000Dh
0x140035556  mov     rbx, [rsp+48h+arg_8]
0x14003555b  mov     rsi, [rsp+48h+arg_10]
0x140035560  add     rsp, 40h
0x140035564  pop     rdi
0x140035565  retn
```
