# FwGetServiceTypes

- ea: `0x18002c310`
- end: `0x18002c3ee`
- name: `FwGetServiceTypes`
- size: `222`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180004750`
- `0x1800047e0`
- `0x180004870`
- `0x180006ac0`
- `0x18001f990`
- `0x18002c310`

## string_xrefs

- `0x18002c34f`: `FwGetServiceTypes`
- `0x18002c39f`: `FwGetServiceTypes`
- `0x18002c3d3`: `FwGetServiceTypes`

## pseudocode

```c
__int64 __fastcall FwGetServiceTypes(_OWORD *a1, __int64 a2)
{
  __int64 v3; // rsi
  int v4; // ebx
  unsigned int i; // edi
  __int64 v6; // rcx
  int v7; // eax
  __int128 v9; // [rsp+20h] [rbp-38h] BYREF

  *(_QWORD *)&v9 = 0;
  *a1 = 0;
  *((_QWORD *)&v9 + 1) = FwAlloc(192, a2);
  v3 = *((_QWORD *)&v9 + 1);
  if ( *((_QWORD *)&v9 + 1) )
  {
    v4 = 0;
    for ( i = 0; i < 3; LODWORD(v9) = i )
    {
      v6 = 4LL * i;
      *(_DWORD *)(v3 + ((unsigned __int64)i << 6) + 8) = qword_180031250[v6];
      v7 = FwBuildIndirectString(HIDWORD(qword_180031250[v6]));
      v4 = v7;
      if ( v7 < 0 )
      {
        FwReportReturnError("FwGetServiceTypes", (unsigned int)v7);
        goto LABEL_10;
      }
      ++i;
    }
    *a1 = v9;
  }
  else
  {
    v4 = FwReportErrorAsWinError("FwGetServiceTypes", "FwAlloc", 8);
  }
  if ( v4 < 0 )
  {
LABEL_10:
    FwArrayDestroy(64, FwIcfAuthBypassServiceDestroy, &v9);
    return (unsigned int)FwReportReturnError("FwGetServiceTypes", (unsigned int)v4);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002c310  push    rbx
0x18002c312  push    rbp
0x18002c313  push    rsi
0x18002c314  push    rdi
0x18002c315  push    r15
0x18002c317  sub     rsp, 30h
0x18002c31b  xorps   xmm0, xmm0
0x18002c31e  mov     qword ptr [rsp+58h+var_38], 0
0x18002c327  movups  xmmword ptr [rcx], xmm0
0x18002c32a  mov     rbp, rcx
0x18002c32d  mov     ecx, 0C0h
0x18002c332  call    FwAlloc
0x18002c337  mov     qword ptr [rsp+58h+var_38+8], rax
0x18002c33c  mov     rsi, rax
0x18002c33f  test    rax, rax
0x18002c342  jnz     short loc_18002C35F
0x18002c344  lea     r8d, [rax+8]
0x18002c348  lea     rdx, aFwalloc_0; "FwAlloc"
0x18002c34f  lea     rcx, aFwgetservicety_0; "FwGetServiceTypes"
0x18002c356  call    FwReportErrorAsWinError
0x18002c35b  mov     ebx, eax
0x18002c35d  jmp     short loc_18002C3B7
0x18002c35f  xor     ebx, ebx
0x18002c361  lea     r15, qword_180031250
0x18002c368  xor     edi, edi
0x18002c36a  cmp     edi, 3
0x18002c36d  jnb     short loc_18002C3AD
0x18002c36f  mov     edx, edi
0x18002c371  shl     rdx, 6
0x18002c375  add     rdx, rsi
0x18002c378  mov     ecx, edi
0x18002c37a  shl     rcx, 5
0x18002c37e  mov     eax, [rcx+r15]
0x18002c382  mov     [rdx+8], eax
0x18002c385  mov     ecx, [rcx+r15+4]
0x18002c38a  call    FwBuildIndirectString
0x18002c38f  mov     ebx, eax
0x18002c391  test    eax, eax
0x18002c393  js      short loc_18002C39D
0x18002c395  inc     edi
0x18002c397  mov     dword ptr [rsp+58h+var_38], edi
0x18002c39b  jmp     short loc_18002C36A
0x18002c39d  mov     edx, eax
0x18002c39f  lea     rcx, aFwgetservicety_0; "FwGetServiceTypes"
0x18002c3a6  call    FwReportReturnError
0x18002c3ab  jmp     short loc_18002C3BB
0x18002c3ad  movups  xmm0, [rsp+58h+var_38]
0x18002c3b2  movdqu  xmmword ptr [rbp+0], xmm0
0x18002c3b7  test    ebx, ebx
0x18002c3b9  jns     short loc_18002C3E1
0x18002c3bb  lea     r8, [rsp+58h+var_38]
0x18002c3c0  mov     ecx, 40h ; '@'
0x18002c3c5  lea     rdx, FwIcfAuthBypassServiceDestroy
0x18002c3cc  call    FwArrayDestroy
0x18002c3d1  mov     edx, ebx
0x18002c3d3  lea     rcx, aFwgetservicety_0; "FwGetServiceTypes"
0x18002c3da  call    FwReportReturnError
0x18002c3df  mov     ebx, eax
0x18002c3e1  mov     eax, ebx
0x18002c3e3  add     rsp, 30h
0x18002c3e7  pop     r15
0x18002c3e9  pop     rdi
0x18002c3ea  pop     rsi
0x18002c3eb  pop     rbp
0x18002c3ec  pop     rbx
0x18002c3ed  retn
```
