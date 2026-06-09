# FwHashtableDestroy

- ea: `0x180014130`
- end: `0x1800141f8`
- name: `FwHashtableDestroy`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180013050`
- `0x180014130`
- `0x18001e1d0`
- `0x18002f43c`
- `0x180030010`

## import_xrefs

- `ntdll!RtlEnumerateEntryHashTable` at `0x18001418c`
- `ntdll!RtlEnumerateEntryHashTable` at `0x18001418c`
- `ntdll!RtlEndEnumerationHashTable` at `0x1800141c1`
- `ntdll!RtlEndEnumerationHashTable` at `0x1800141c1`
- `ntdll!RtlInitEnumerationHashTable` at `0x180014171`
- `ntdll!RtlInitEnumerationHashTable` at `0x180014171`
- `ntdll!RtlDeleteHashTable` at `0x1800141d4`
- `ntdll!RtlDeleteHashTable` at `0x1800141d4`

## pseudocode

```c
__int64 __fastcall FwHashtableDestroy(_BYTE *a1, void (__fastcall *a2)(_QWORD *))
{
  __int64 v4; // rax
  __int64 v5; // rcx
  _QWORD v7[7]; // [rsp+20h] [rbp-40h] BYREF

  memset(v7, 0, sizeof(v7));
  if ( !(unsigned __int8)RtlInitEnumerationHashTable(a1, &v7[2]) )
    ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
  v7[1] = a1;
  while ( 1 )
  {
    v4 = RtlEnumerateEntryHashTable(v7[1], &v7[2]);
    v7[0] = v4;
    if ( !v4 )
      break;
    FwHashtableRemove((__int64)a1, v4);
    if ( a2 )
      a2(v7);
  }
  RtlEndEnumerationHashTable(v7[1], &v7[2]);
  if ( (*a1 & 1) != 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5);
  return RtlDeleteHashTable(a1);
}

```

## disassembly

```asm
0x180014130  mov     [rsp-8+arg_10], rbx
0x180014135  mov     [rsp-8+arg_18], rdi
0x18001413a  push    rbp
0x18001413b  mov     rbp, rsp
0x18001413e  sub     rsp, 60h
0x180014142  mov     rax, cs:__security_cookie
0x180014149  xor     rax, rsp
0x18001414c  mov     [rbp+var_8], rax
0x180014150  xorps   xmm0, xmm0
0x180014153  mov     [rbp+var_40], 0
0x18001415b  mov     rdi, rdx
0x18001415e  mov     rbx, rcx
0x180014161  lea     rdx, [rbp+var_38+8]
0x180014165  movups  [rbp+var_38], xmm0
0x180014169  movups  [rbp+var_28], xmm0
0x18001416d  movups  [rbp+var_18], xmm0
0x180014171  call    cs:__imp_RtlInitEnumerationHashTable
0x180014177  test    al, al
0x180014179  jnz     short loc_180014180
0x18001417b  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "success")
0x180014180  mov     qword ptr [rbp+var_38], rbx
0x180014184  mov     rcx, qword ptr [rbp+var_38]
0x180014188  lea     rdx, [rbp+var_38+8]
0x18001418c  call    cs:__imp_RtlEnumerateEntryHashTable
0x180014192  mov     [rbp+var_40], rax
0x180014196  test    rax, rax
0x180014199  jz      short loc_1800141B9
0x18001419b  mov     rdx, rax
0x18001419e  mov     rcx, rbx
0x1800141a1  call    FwHashtableRemove
0x1800141a6  test    rdi, rdi
0x1800141a9  jz      short loc_180014184
0x1800141ab  lea     rcx, [rbp+var_40]
0x1800141af  mov     rax, rdi
0x1800141b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141b7  jmp     short loc_180014184
0x1800141b9  mov     rcx, qword ptr [rbp+var_38]
0x1800141bd  lea     rdx, [rbp+var_38+8]
0x1800141c1  call    cs:__imp_RtlEndEnumerationHashTable
0x1800141c7  test    byte ptr [rbx], 1
0x1800141ca  jz      short loc_1800141D1
0x1800141cc  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "(hashTable->Flags & RTL_HASH_ALLOCATED_HEADER) == 0")
0x1800141d1  mov     rcx, rbx
0x1800141d4  call    cs:__imp_RtlDeleteHashTable
0x1800141da  mov     rcx, [rbp+var_8]
0x1800141de  xor     rcx, rsp; StackCookie
0x1800141e1  call    __security_check_cookie
0x1800141e6  lea     r11, [rsp+60h+var_s0]
0x1800141eb  mov     rbx, [r11+20h]
0x1800141ef  mov     rdi, [r11+28h]
0x1800141f3  mov     rsp, r11
0x1800141f6  pop     rbp
0x1800141f7  retn
```
