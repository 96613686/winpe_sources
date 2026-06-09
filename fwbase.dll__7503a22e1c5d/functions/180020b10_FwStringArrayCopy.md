# FwStringArrayCopy

- ea: `0x180020b10`
- end: `0x180020c47`
- name: `FwStringArrayCopy`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800045f0`
- `0x180004750`
- `0x1800047e0`
- `0x180004840`
- `0x180004870`
- `0x18000c060`
- `0x18001eb54`
- `0x180020b10`
- `0x18002f43c`

## string_xrefs

- `0x180020b6e`: `FwStringArrayCopy`
- `0x180020b9e`: `FwStringArrayCopy`
- `0x180020be2`: `FwStringArrayCopy`
- `0x180020c20`: `FwStringArrayCopy`

## pseudocode

```c
__int64 __fastcall FwStringArrayCopy(__int64 a1, unsigned int a2, _QWORD *a3, _DWORD *a4)
{
  __int64 v4; // rsi
  int v8; // eax
  __int64 v9; // rdx
  unsigned int v10; // ebx
  _QWORD *v11; // rdi
  _QWORD *v12; // r14
  _QWORD *v13; // rax
  __int64 j; // rbp
  int v15; // eax
  __int64 i; // rbp
  __int64 v18; // [rsp+60h] [rbp+18h] BYREF

  v4 = a2;
  v18 = 0;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  *a3 = 0;
  *a4 = 0;
  v8 = FwSizeTMultiply(v4, 8, &v18);
  v10 = v8;
  if ( v8 < 0 )
  {
    v11 = 0;
    FwReportReturnError("FwStringArrayCopy", (unsigned int)v8);
    v12 = 0;
LABEL_17:
    for ( i = 0; (unsigned int)i < (unsigned int)v4; i = (unsigned int)(i + 1) )
      FwFree(v12[i]);
    FwFree(v11);
    if ( (v10 & 0x80000000) != 0 )
      return (unsigned int)FwReportReturnError("FwStringArrayCopy", v10);
    return v10;
  }
  v13 = (_QWORD *)FwAlloc(v18, v9);
  v11 = v13;
  if ( v13 )
  {
    if ( (_DWORD)v4 )
      memset_0(v13, 0, 8 * v4);
    for ( j = 0; (unsigned int)j < (unsigned int)v4; j = (unsigned int)(j + 1) )
    {
      v15 = FwStringCopy(*(void **)(a1 + 8 * j));
      v10 = v15;
      if ( v15 < 0 )
      {
        FwReportReturnError("FwStringArrayCopy", (unsigned int)v15);
        goto LABEL_16;
      }
    }
    *a3 = v11;
    *a4 = v4;
  }
  else
  {
    v10 = FwReportErrorAsWinError("FwStringArrayCopy", "FwAlloc", 8);
  }
  if ( v10 )
  {
LABEL_16:
    v12 = v11;
    goto LABEL_17;
  }
  return v10;
}

```

## disassembly

```asm
0x180020b10  mov     [rsp+arg_0], rbx
0x180020b15  mov     [rsp+arg_8], rbp
0x180020b1a  push    rsi
0x180020b1b  push    rdi
0x180020b1c  push    r12
0x180020b1e  push    r14
0x180020b20  push    r15
0x180020b22  sub     rsp, 20h
0x180020b26  mov     esi, edx
0x180020b28  mov     r14, r9
0x180020b2b  mov     [rsp+48h+arg_10], 0
0x180020b34  mov     r15, r8
0x180020b37  mov     r12, rcx
0x180020b3a  test    edx, edx
0x180020b3c  jnz     short loc_180020B43
0x180020b3e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "size != 0")
0x180020b43  mov     qword ptr [r15], 0
0x180020b4a  lea     r8, [rsp+48h+arg_10]
0x180020b4f  mov     edx, 8
0x180020b54  mov     dword ptr [r14], 0
0x180020b5b  mov     rcx, rsi
0x180020b5e  mov     rbp, rsi
0x180020b61  call    FwSizeTMultiply
0x180020b66  mov     ebx, eax
0x180020b68  test    eax, eax
0x180020b6a  jns     short loc_180020B81
0x180020b6c  mov     edx, eax
0x180020b6e  lea     rcx, aFwstringarrayc_0; "FwStringArrayCopy"
0x180020b75  xor     edi, edi
0x180020b77  call    FwReportReturnError
0x180020b7c  xor     r14d, r14d
0x180020b7f  jmp     short loc_180020BFD
0x180020b81  mov     rcx, [rsp+48h+arg_10]
0x180020b86  call    FwAlloc
0x180020b8b  mov     rdi, rax
0x180020b8e  test    rax, rax
0x180020b91  jnz     short loc_180020BAE
0x180020b93  lea     r8d, [rax+8]
0x180020b97  lea     rdx, aFwalloc_0; "FwAlloc"
0x180020b9e  lea     rcx, aFwstringarrayc_0; "FwStringArrayCopy"
0x180020ba5  call    FwReportErrorAsWinError
0x180020baa  mov     ebx, eax
0x180020bac  jmp     short loc_180020BF6
0x180020bae  test    esi, esi
0x180020bb0  jz      short loc_180020BC3
0x180020bb2  shl     rbp, 3
0x180020bb6  xor     edx, edx; Val
0x180020bb8  mov     r8, rbp; Size
0x180020bbb  mov     rcx, rdi; void *
0x180020bbe  call    memset_0
0x180020bc3  xor     ebp, ebp
0x180020bc5  cmp     ebp, esi
0x180020bc7  jnb     short loc_180020BF0
0x180020bc9  mov     rcx, [r12+rbp*8]; Src
0x180020bcd  lea     rdx, [rdi+rbp*8]
0x180020bd1  call    FwStringCopy
0x180020bd6  mov     ebx, eax
0x180020bd8  test    eax, eax
0x180020bda  js      short loc_180020BE0
0x180020bdc  inc     ebp
0x180020bde  jmp     short loc_180020BC5
0x180020be0  mov     edx, eax
0x180020be2  lea     rcx, aFwstringarrayc_0; "FwStringArrayCopy"
0x180020be9  call    FwReportReturnError
0x180020bee  jmp     short loc_180020BFA
0x180020bf0  mov     [r15], rdi
0x180020bf3  mov     [r14], esi
0x180020bf6  test    ebx, ebx
0x180020bf8  jz      short loc_180020C2E
0x180020bfa  mov     r14, rdi
0x180020bfd  xor     ebp, ebp
0x180020bff  test    esi, esi
0x180020c01  jz      short loc_180020C12
0x180020c03  mov     rcx, [r14+rbp*8]
0x180020c07  call    FwFree
0x180020c0c  inc     ebp
0x180020c0e  cmp     ebp, esi
0x180020c10  jb      short loc_180020C03
0x180020c12  mov     rcx, rdi
0x180020c15  call    FwFree
0x180020c1a  test    ebx, ebx
0x180020c1c  jns     short loc_180020C2E
0x180020c1e  mov     edx, ebx
0x180020c20  lea     rcx, aFwstringarrayc_0; "FwStringArrayCopy"
0x180020c27  call    FwReportReturnError
0x180020c2c  mov     ebx, eax
0x180020c2e  mov     rbp, [rsp+48h+arg_8]
0x180020c33  mov     eax, ebx
0x180020c35  mov     rbx, [rsp+48h+arg_0]
0x180020c3a  add     rsp, 20h
0x180020c3e  pop     r15
0x180020c40  pop     r14
0x180020c42  pop     r12
0x180020c44  pop     rdi
0x180020c45  pop     rsi
0x180020c46  retn
```
