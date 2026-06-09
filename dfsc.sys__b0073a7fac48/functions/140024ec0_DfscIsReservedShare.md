# DfscIsReservedShare

- ea: `0x140024ec0`
- end: `0x140024fe6`
- name: `DfscIsReservedShare`
- size: `294`
- prototype: `char __fastcall(UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140029160`

## callees

- `0x140024ec0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x140024f9c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140024f9c`

## pseudocode

```c
char __fastcall DfscIsReservedShare(UNICODE_STRING *a1)
{
  unsigned int i; // ebx
  unsigned __int16 v3; // ax
  unsigned __int16 v4; // dx
  __int16 v5; // r8
  WCHAR v6; // r8
  UNICODE_STRING String2; // [rsp+20h] [rbp-48h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-38h] BYREF

  for ( i = 0; i < 4; ++i )
  {
    v3 = a1->Length >> 1;
    v4 = asc_14000C080[8 * i] >> 1;
    String1 = 0;
    for ( String2 = 0; v4; --v4 )
    {
      v5 = *(_WORD *)(*(_QWORD *)&asc_14000C080[8 * i + 4] + 2LL * v4 - 2);
      if ( v5 != 92 && v5 )
        break;
    }
    if ( v3 )
    {
      while ( 1 )
      {
        v6 = a1->Buffer[v3 - 1];
        if ( v6 != 92 )
        {
          if ( v6 )
            break;
        }
        if ( !--v3 )
          goto LABEL_16;
      }
      if ( v3 == v4 )
      {
        if ( v4 )
        {
          String1 = *(UNICODE_STRING *)&asc_14000C080[8 * i];
          String1.Length = 2 * v4;
          String2 = *a1;
          String2.Length = 2 * v3;
          if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
            return 1;
        }
      }
    }
    else
    {
LABEL_16:
      if ( !v4 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140024ec0  push    rbx
0x140024ec2  push    rbp
0x140024ec3  push    rsi
0x140024ec4  push    rdi
0x140024ec5  sub     rsp, 48h
0x140024ec9  mov     rdi, rcx
0x140024ecc  lea     rsi, asc_14000C080; "\b\b"
0x140024ed3  xor     ebx, ebx
0x140024ed5  mov     ebp, 0FFFFh
0x140024eda  nop     word ptr [rax+rax+00h]
0x140024ee0  cmp     ebx, 4
0x140024ee3  jnb     loc_140024FD7
0x140024ee9  movzx   eax, word ptr [rdi]
0x140024eec  xorps   xmm0, xmm0
0x140024eef  mov     r8d, ebx
0x140024ef2  xorps   xmm1, xmm1
0x140024ef5  add     r8, r8
0x140024ef8  shr     ax, 1
0x140024efb  movzx   edx, word ptr [rsi+r8*8]
0x140024f00  lea     r10, [rsi+r8*8]
0x140024f04  shr     dx, 1
0x140024f07  movups  xmmword ptr [rsp+68h+String1.Length], xmm0
0x140024f0c  movups  xmmword ptr [rsp+68h+String2.Length], xmm1
0x140024f11  jz      short loc_140024F36
0x140024f13  mov     r9, [rsi+r8*8+8]
0x140024f18  movzx   ecx, dx
0x140024f1b  movzx   r8d, word ptr [r9+rcx*2-2]
0x140024f21  cmp     r8w, 5Ch ; '\'
0x140024f26  jz      loc_140024FB8
0x140024f2c  test    r8w, r8w
0x140024f30  jz      loc_140024FB8
0x140024f36  test    ax, ax
0x140024f39  jz      loc_140024FC6
0x140024f3f  mov     r9, [rdi+8]
0x140024f43  movzx   ecx, ax
0x140024f46  movzx   r8d, word ptr [r9+rcx*2-2]
0x140024f4c  cmp     r8w, 5Ch ; '\'
0x140024f51  jz      loc_140024FDB
0x140024f57  test    r8w, r8w
0x140024f5b  jz      short loc_140024FDB
0x140024f5d  cmp     ax, dx
0x140024f60  jz      short loc_140024F69
0x140024f62  inc     ebx
0x140024f64  jmp     loc_140024EE0
0x140024f69  test    dx, dx
0x140024f6c  jz      short loc_140024F62
0x140024f6e  movups  xmm0, xmmword ptr [r10]
0x140024f72  add     dx, dx
0x140024f75  lea     rcx, [rsp+68h+String1]; String1
0x140024f7a  add     ax, ax
0x140024f7d  mov     r8b, 1; CaseInSensitive
0x140024f80  movups  xmmword ptr [rsp+68h+String1.Length], xmm0
0x140024f85  mov     [rsp+68h+String1.Length], dx
0x140024f8a  lea     rdx, [rsp+68h+String2]; String2
0x140024f8f  movups  xmm0, xmmword ptr [rdi]
0x140024f92  movups  xmmword ptr [rsp+68h+String2.Length], xmm0
0x140024f97  mov     [rsp+68h+String2.Length], ax
0x140024f9c  call    cs:__imp_RtlCompareUnicodeString
0x140024fa3  nop     dword ptr [rax+rax+00h]
0x140024fa8  test    eax, eax
0x140024faa  jnz     short loc_140024F62
0x140024fac  mov     al, 1
0x140024fae  add     rsp, 48h
0x140024fb2  pop     rdi
0x140024fb3  pop     rsi
0x140024fb4  pop     rbp
0x140024fb5  pop     rbx
0x140024fb6  retn
0x140024fb8  add     dx, bp
0x140024fbb  jnz     loc_140024F18
0x140024fc1  jmp     loc_140024F36
0x140024fc6  test    dx, dx
0x140024fc9  jnz     short loc_140024F62
0x140024fcb  mov     al, 1
0x140024fcd  add     rsp, 48h
0x140024fd1  pop     rdi
0x140024fd2  pop     rsi
0x140024fd3  pop     rbp
0x140024fd4  pop     rbx
0x140024fd5  retn
0x140024fd7  xor     al, al
0x140024fd9  jmp     short loc_140024FCD
0x140024fdb  add     ax, bp
0x140024fde  jnz     loc_140024F43
0x140024fe4  jmp     short loc_140024FC6
```
