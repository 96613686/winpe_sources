# SmbExtSecuritySessionSetupExchangeReceive

- ea: `0x14000e320`
- end: `0x14000e3d2`
- name: `SmbExtSecuritySessionSetupExchangeReceive`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000e0d8`
- `0x14000e320`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14000e362`
- `ntoskrnl!RtlCompareMemory` at `0x14000e362`

## pseudocode

```c
__int64 __fastcall SmbExtSecuritySessionSetupExchangeReceive(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        unsigned int *a4,
        __int64 a5,
        _QWORD *a6,
        _DWORD *a7)
{
  unsigned int v11; // edx

  if ( (*(_BYTE *)(*(_QWORD *)(a1 + 80) + 672LL) & 0x18) == 0x10
    && RtlCompareMemory((const void *)(a5 + 14), InitialSecuritySignature, 8u) != 8 )
  {
    *(_BYTE *)(*(_QWORD *)(a1 + 440) + 40LL) = 1;
  }
  v11 = ParseExtSecuritySessionSetupResponse(a1, a2, a3, a5);
  if ( v11 == -1073741802 )
  {
    *a4 = 0;
    *a6 = *(_QWORD *)(a1 + 384);
    *a7 = *(_DWORD *)(a1 + 396);
  }
  else
  {
    *a4 = a3;
    return 0;
  }
  return v11;
}

```

## disassembly

```asm
0x14000e320  push    rbx
0x14000e322  push    rbp
0x14000e323  push    rsi
0x14000e324  push    rdi
0x14000e325  push    r14
0x14000e327  sub     rsp, 20h
0x14000e32b  mov     rax, [rcx+50h]
0x14000e32f  mov     rdi, r9
0x14000e332  mov     rbp, [rsp+48h+arg_20]
0x14000e337  mov     esi, r8d
0x14000e33a  mov     r14d, edx
0x14000e33d  mov     rbx, rcx
0x14000e340  mov     r10b, [rax+2A0h]
0x14000e347  and     r10b, 18h
0x14000e34b  cmp     r10b, 10h
0x14000e34f  jnz     short loc_14000E37F
0x14000e351  lea     rcx, [rbp+0Eh]; Source1
0x14000e355  mov     r8d, 8; Length
0x14000e35b  lea     rdx, InitialSecuritySignature; "BSRSPYL "
0x14000e362  call    cs:__imp_RtlCompareMemory
0x14000e369  nop     dword ptr [rax+rax+00h]
0x14000e36e  cmp     rax, 8
0x14000e372  jz      short loc_14000E37F
0x14000e374  mov     rax, [rbx+1B8h]
0x14000e37b  mov     byte ptr [rax+28h], 1
0x14000e37f  mov     r9, rbp
0x14000e382  mov     r8d, esi
0x14000e385  mov     edx, r14d
0x14000e388  mov     rcx, rbx
0x14000e38b  call    ParseExtSecuritySessionSetupResponse
0x14000e390  mov     edx, eax
0x14000e392  cmp     eax, 0C0000016h
0x14000e397  jz      short loc_14000E39F
0x14000e399  mov     [rdi], esi
0x14000e39b  xor     edx, edx
0x14000e39d  jmp     short loc_14000E3C4
0x14000e39f  mov     rax, [rsp+48h+arg_28]
0x14000e3a4  mov     dword ptr [rdi], 0
0x14000e3aa  mov     rcx, [rbx+180h]
0x14000e3b1  mov     [rax], rcx
0x14000e3b4  mov     rax, [rsp+48h+arg_30]
0x14000e3bc  mov     ecx, [rbx+18Ch]
0x14000e3c2  mov     [rax], ecx
0x14000e3c4  mov     eax, edx
0x14000e3c6  add     rsp, 20h
0x14000e3ca  pop     r14
0x14000e3cc  pop     rdi
0x14000e3cd  pop     rsi
0x14000e3ce  pop     rbp
0x14000e3cf  pop     rbx
0x14000e3d0  retn
```
