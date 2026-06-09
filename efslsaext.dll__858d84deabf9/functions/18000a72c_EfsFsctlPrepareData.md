# EfsFsctlPrepareData

- ea: `0x18000a72c`
- end: `0x18000a865`
- name: `EfsFsctlPrepareData`
- size: `313`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008bd0`
- `0x180008f88`
- `0x180009200`

## callees

- `0x180007e6c`
- `0x18000a72c`
- `0x180012002`
- `0x18001200e`

## pseudocode

```c
char __fastcall EfsFsctlPrepareData(int a1, int a2, int a3, __int64 a4, _DWORD *a5, _DWORD *a6)
{
  char v6; // bl
  unsigned int v10; // esi
  unsigned int *v11; // rdx
  unsigned int v12; // ebx
  char *v13; // r15
  unsigned int *v14; // rdi
  __int64 v15; // rcx
  char *v16; // rcx
  unsigned int v17; // edi

  v6 = 0;
  if ( *a6 < 0x10u )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( *a6 >= 0x10u )
  {
    v10 = *a6 - 16;
    if ( *(_DWORD *)a4 != 1 )
    {
      if ( *(_DWORD *)a4 == 2 )
      {
        if ( !*(_QWORD *)(a4 + 8) )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( !*(_QWORD *)(a4 + 16) )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v13 = *(char **)(a4 + 16);
        v14 = *(unsigned int **)(a4 + 8);
        v15 = *v14;
        if ( v10 < *(_DWORD *)v13 + (int)v15 + 56 )
          goto LABEL_17;
        v10 = *(_DWORD *)v13 + v15 + 56;
        memcpy_0(a5 + 4, v14, v15 + 56);
        v16 = (char *)a5 + *v14 + 72;
        if ( v16 != v13 )
          memcpy_0(v16, v13, *(unsigned int *)v13);
      }
      else
      {
        if ( *(_DWORD *)a4 != 3 )
        {
LABEL_17:
          MicrosoftTelemetryAssertTriggeredNoArgs();
          MicrosoftTelemetryAssertTriggeredNoArgs();
          return v6;
        }
        if ( !*(_QWORD *)(a4 + 8) )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v11 = *(unsigned int **)(a4 + 8);
        v12 = *v11;
        if ( v10 < *v11 )
        {
          v6 = 0;
          goto LABEL_17;
        }
        memcpy_0(a5 + 4, v11, *v11);
        v10 = v12;
      }
    }
    v17 = (v10 + 15) & 0xFFFFFFF0;
    *a5 = a2;
    a5[1] = a1;
    v6 = 1;
    a5[2] = a3;
    a5[3] = v17;
    if ( v10 )
      memset_0((char *)a5 + v10 + 16, 0, v17 - v10);
    *a6 = v17 + 16;
  }
  return v6;
}

```

## disassembly

```asm
0x18000a72c  mov     [rsp+arg_0], ecx
0x18000a730  push    rbx
0x18000a731  push    rbp
0x18000a732  push    rsi
0x18000a733  push    rdi
0x18000a734  push    r12
0x18000a736  push    r13
0x18000a738  push    r14
0x18000a73a  push    r15
0x18000a73c  sub     rsp, 28h
0x18000a740  mov     rbp, [rsp+68h+arg_28]
0x18000a748  xor     bl, bl
0x18000a74a  mov     rdi, r9
0x18000a74d  mov     r12d, r8d
0x18000a750  mov     r13d, edx
0x18000a753  cmp     dword ptr [rbp+0], 10h
0x18000a757  jnb     short loc_18000A75E
0x18000a759  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a75e  mov     esi, [rbp+0]
0x18000a761  cmp     esi, 10h
0x18000a764  jb      loc_18000A852
0x18000a76a  mov     ecx, [rdi]
0x18000a76c  add     esi, 0FFFFFFF0h
0x18000a76f  mov     r14, [rsp+68h+arg_20]
0x18000a777  sub     ecx, 1
0x18000a77a  jz      loc_18000A817
0x18000a780  sub     ecx, 1
0x18000a783  jz      short loc_18000A7B4
0x18000a785  cmp     ecx, 1
0x18000a788  jnz     short loc_18000A7E0
0x18000a78a  cmp     qword ptr [rdi+8], 0
0x18000a78f  jnz     short loc_18000A796
0x18000a791  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a796  mov     rdx, [rdi+8]; Src
0x18000a79a  mov     ebx, [rdx]
0x18000a79c  cmp     esi, ebx
0x18000a79e  jnb     short loc_18000A7A4
0x18000a7a0  xor     bl, bl
0x18000a7a2  jmp     short loc_18000A7E0
0x18000a7a4  mov     r8, rbx; Size
0x18000a7a7  lea     rcx, [r14+10h]; void *
0x18000a7ab  call    memcpy_0
0x18000a7b0  mov     esi, ebx
0x18000a7b2  jmp     short loc_18000A817
0x18000a7b4  cmp     qword ptr [rdi+8], 0
0x18000a7b9  jnz     short loc_18000A7C0
0x18000a7bb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a7c0  cmp     qword ptr [rdi+10h], 0
0x18000a7c5  jnz     short loc_18000A7CC
0x18000a7c7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a7cc  mov     r15, [rdi+10h]
0x18000a7d0  mov     rdi, [rdi+8]
0x18000a7d4  mov     ecx, [rdi]
0x18000a7d6  lea     edx, [rcx+38h]
0x18000a7d9  add     edx, [r15]
0x18000a7dc  cmp     esi, edx
0x18000a7de  jnb     short loc_18000A7EC
0x18000a7e0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a7e5  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000a7ea  jmp     short loc_18000A852
0x18000a7ec  mov     esi, edx
0x18000a7ee  lea     r8, [rcx+38h]; Size
0x18000a7f2  mov     rdx, rdi; Src
0x18000a7f5  lea     rcx, [r14+10h]; void *
0x18000a7f9  call    memcpy_0
0x18000a7fe  mov     eax, [rdi]
0x18000a800  lea     rcx, [r14+48h]
0x18000a804  add     rcx, rax; void *
0x18000a807  cmp     rcx, r15
0x18000a80a  jz      short loc_18000A817
0x18000a80c  mov     r8d, [r15]; Size
0x18000a80f  mov     rdx, r15; Src
0x18000a812  call    memcpy_0
0x18000a817  mov     eax, [rsp+68h+arg_0]
0x18000a81b  lea     edi, [rsi+0Fh]
0x18000a81e  and     edi, 0FFFFFFF0h
0x18000a821  mov     [r14], r13d
0x18000a824  mov     [r14+4], eax
0x18000a828  mov     bl, 1
0x18000a82a  mov     [r14+8], r12d
0x18000a82e  mov     [r14+0Ch], edi
0x18000a832  test    esi, esi
0x18000a834  jz      short loc_18000A84C
0x18000a836  mov     r8d, edi
0x18000a839  mov     ecx, esi
0x18000a83b  add     rcx, 10h
0x18000a83f  sub     r8d, esi; Size
0x18000a842  add     rcx, r14; void *
0x18000a845  xor     edx, edx; Val
0x18000a847  call    memset_0
0x18000a84c  lea     ecx, [rdi+10h]
0x18000a84f  mov     [rbp+0], ecx
0x18000a852  mov     al, bl
0x18000a854  add     rsp, 28h
0x18000a858  pop     r15
0x18000a85a  pop     r14
0x18000a85c  pop     r13
0x18000a85e  pop     r12
0x18000a860  pop     rdi
0x18000a861  pop     rsi
0x18000a862  pop     rbp
0x18000a863  pop     rbx
0x18000a864  retn
```
