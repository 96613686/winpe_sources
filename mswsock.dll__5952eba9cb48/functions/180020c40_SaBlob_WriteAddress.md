# SaBlob_WriteAddress

- ea: `0x180020c40`
- end: `0x180020d2a`
- name: `SaBlob_WriteAddress`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180015310`
- `0x18001571c`

## callees

- `0x180020c40`
- `0x180029a14`

## import_xrefs

- `DNSAPI!DnsAddrArrayCreate` at `0x180020cdf`
- `DNSAPI!DnsAddrArrayCreate` at `0x180020cdf`
- `DNSAPI!DnsApiAlloc` at `0x180020c74`
- `DNSAPI!DnsApiAlloc` at `0x180020c74`
- `DNSAPI!DnsAddrArrayAddAddr` at `0x180020d07`
- `DNSAPI!DnsAddrArrayAddAddr` at `0x180020d07`

## pseudocode

```c
__int64 __fastcall SaBlob_WriteAddress(__int64 a1, _OWORD *a2)
{
  int IsEnabledDeviceUsageNoInline; // eax
  _DWORD *v5; // rax
  _DWORD *v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v10; // rax

  if ( (Feature_5977_1413__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_5977_1413__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_5977_1413__private_IsEnabledDeviceUsageNoInline();
  if ( !IsEnabledDeviceUsageNoInline )
  {
    v10 = *(_QWORD *)(a1 + 8);
    if ( !v10 )
    {
      v10 = DnsAddrArrayCreate(1);
      if ( !v10 )
        return 14;
      *(_QWORD *)(a1 + 8) = v10;
    }
    return (unsigned int)DnsAddrArrayAddAddr(v10, a2, 0, 0) == 0 ? 0xEA : 0;
  }
  if ( *(_QWORD *)(a1 + 8) )
    goto LABEL_8;
  v5 = (_DWORD *)DnsApiAlloc(96);
  *(_QWORD *)(a1 + 8) = v5;
  if ( !v5 )
    return 14;
  *v5 = 1;
LABEL_8:
  v6 = *(_DWORD **)(a1 + 8);
  v7 = (unsigned int)v6[1];
  if ( (unsigned int)v7 >= *v6 )
    return 234;
  v8 = v7 << 6;
  *(_OWORD *)((char *)v6 + v8 + 32) = *a2;
  *(_OWORD *)((char *)v6 + v8 + 48) = a2[1];
  *(_OWORD *)((char *)v6 + v8 + 64) = a2[2];
  *(_OWORD *)((char *)v6 + v8 + 80) = a2[3];
  ++*(_DWORD *)(*(_QWORD *)(a1 + 8) + 4LL);
  return 0;
}

```

## disassembly

```asm
0x180020c40  mov     [rsp+arg_0], rbx
0x180020c45  push    rdi
0x180020c46  sub     rsp, 20h
0x180020c4a  mov     rdi, rdx
0x180020c4d  mov     rbx, rcx
0x180020c50  mov     eax, cs:Feature_5977_1413__private_featureState
0x180020c56  test    al, 10h
0x180020c58  jz      short loc_180020C5F
0x180020c5a  and     eax, 1
0x180020c5d  jmp     short loc_180020C64
0x180020c5f  call    Feature_5977_1413__private_IsEnabledDeviceUsageNoInline
0x180020c64  test    eax, eax
0x180020c66  jz      short loc_180020CD3
0x180020c68  cmp     qword ptr [rbx+8], 0
0x180020c6d  jnz     short loc_180020C8F
0x180020c6f  mov     ecx, 60h ; '`'
0x180020c74  call    cs:__imp_DnsApiAlloc
0x180020c7b  nop     dword ptr [rax+rax+00h]
0x180020c80  mov     [rbx+8], rax
0x180020c84  test    rax, rax
0x180020c87  jz      short loc_180020CF0
0x180020c89  mov     dword ptr [rax], 1
0x180020c8f  mov     rcx, [rbx+8]
0x180020c93  mov     eax, [rcx+4]
0x180020c96  cmp     eax, [rcx]
0x180020c98  jnb     short loc_180020CCC
0x180020c9a  movaps  xmm0, xmmword ptr [rdi]
0x180020c9d  shl     rax, 6
0x180020ca1  movups  xmmword ptr [rax+rcx+20h], xmm0
0x180020ca6  movaps  xmm1, xmmword ptr [rdi+10h]
0x180020caa  movups  xmmword ptr [rax+rcx+30h], xmm1
0x180020caf  movaps  xmm0, xmmword ptr [rdi+20h]
0x180020cb3  movups  xmmword ptr [rax+rcx+40h], xmm0
0x180020cb8  movaps  xmm1, xmmword ptr [rdi+30h]
0x180020cbc  movups  xmmword ptr [rax+rcx+50h], xmm1
0x180020cc1  mov     rax, [rbx+8]
0x180020cc5  inc     dword ptr [rax+4]
0x180020cc8  xor     eax, eax
0x180020cca  jmp     short loc_180020D1E
0x180020ccc  mov     eax, 0EAh
0x180020cd1  jmp     short loc_180020D1E
0x180020cd3  mov     rax, [rbx+8]
0x180020cd7  test    rax, rax
0x180020cda  jnz     short loc_180020CFB
0x180020cdc  lea     ecx, [rax+1]
0x180020cdf  call    cs:__imp_DnsAddrArrayCreate
0x180020ce6  nop     dword ptr [rax+rax+00h]
0x180020ceb  test    rax, rax
0x180020cee  jnz     short loc_180020CF7
0x180020cf0  mov     eax, 0Eh
0x180020cf5  jmp     short loc_180020D1E
0x180020cf7  mov     [rbx+8], rax
0x180020cfb  xor     r9d, r9d
0x180020cfe  xor     r8d, r8d
0x180020d01  mov     rdx, rdi
0x180020d04  mov     rcx, rax
0x180020d07  call    cs:__imp_DnsAddrArrayAddAddr
0x180020d0e  nop     dword ptr [rax+rax+00h]
0x180020d13  neg     eax
0x180020d15  sbb     eax, eax
0x180020d17  not     eax
0x180020d19  and     eax, 0EAh
0x180020d1e  mov     rbx, [rsp+28h+arg_0]
0x180020d23  add     rsp, 20h
0x180020d27  pop     rdi
0x180020d28  retn
```
