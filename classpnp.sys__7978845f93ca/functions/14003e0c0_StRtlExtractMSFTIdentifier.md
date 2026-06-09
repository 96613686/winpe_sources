# StRtlExtractMSFTIdentifier

- ea: `0x14003e0c0`
- end: `0x14003e161`
- name: `StRtlExtractMSFTIdentifier`
- size: `161`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140059500`

## callees

- `0x14003e0c0`
- `0x14003e430`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14003e125`
- `ntoskrnl!RtlCompareMemory` at `0x14003e125`

## pseudocode

```c
char __fastcall StRtlExtractMSFTIdentifier(__int64 a1, _OWORD *a2)
{
  char v2; // bl
  bool v3; // zf
  __int64 v5; // rdi
  _QWORD Source2[2]; // [rsp+20h] [rbp-28h] BYREF

  v2 = 0;
  v3 = *(_DWORD *)a1 == 1;
  strcpy((char *)Source2, "MSFT    ");
  if ( v3 && *(_DWORD *)(a1 + 4) == 1 && !*(_DWORD *)(a1 + 12) && *(_WORD *)(a1 + 8) == 24 )
  {
    v5 = a1 + 16;
    if ( RtlCompareMemory((const void *)(a1 + 16), Source2, 8u) == 8 )
    {
      v2 = 1;
      *a2 = *(_OWORD *)(v5 + 8);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x14003e0c0  mov     [rsp+arg_10], rbx
0x14003e0c5  mov     [rsp+arg_18], rsi
0x14003e0ca  push    rdi
0x14003e0cb  sub     rsp, 40h
0x14003e0cf  mov     rax, cs:__security_cookie
0x14003e0d6  xor     rax, rsp
0x14003e0d9  mov     [rsp+48h+var_18], rax
0x14003e0de  movsd   xmm0, qword ptr cs:aMsft; "MSFT    "
0x14003e0e6  xor     bl, bl
0x14003e0e8  cmp     dword ptr [rcx], 1
0x14003e0eb  mov     rsi, rdx
0x14003e0ee  mov     al, byte ptr cs:aMsft+8; ""
0x14003e0f4  movsd   [rsp+48h+Source2], xmm0
0x14003e0fa  mov     [rsp+48h+var_20], al
0x14003e0fe  jnz     short loc_14003E141
0x14003e100  cmp     dword ptr [rcx+4], 1
0x14003e104  jnz     short loc_14003E141
0x14003e106  cmp     dword ptr [rcx+0Ch], 0
0x14003e10a  jnz     short loc_14003E141
0x14003e10c  cmp     word ptr [rcx+8], 18h
0x14003e111  jnz     short loc_14003E141
0x14003e113  lea     rdi, [rcx+10h]
0x14003e117  mov     r8d, 8; Length
0x14003e11d  mov     rcx, rdi; Source1
0x14003e120  lea     rdx, [rsp+48h+Source2]; Source2
0x14003e125  call    cs:__imp_RtlCompareMemory
0x14003e12c  nop     dword ptr [rax+rax+00h]
0x14003e131  cmp     rax, 8
0x14003e135  jnz     short loc_14003E141
0x14003e137  movups  xmm0, xmmword ptr [rdi+8]
0x14003e13b  mov     bl, 1
0x14003e13d  movdqu  xmmword ptr [rsi], xmm0
0x14003e141  mov     al, bl
0x14003e143  mov     rcx, [rsp+48h+var_18]
0x14003e148  xor     rcx, rsp; StackCookie
0x14003e14b  call    __security_check_cookie
0x14003e150  mov     rbx, [rsp+48h+arg_10]
0x14003e155  mov     rsi, [rsp+48h+arg_18]
0x14003e15a  add     rsp, 40h
0x14003e15e  pop     rdi
0x14003e15f  retn
```
