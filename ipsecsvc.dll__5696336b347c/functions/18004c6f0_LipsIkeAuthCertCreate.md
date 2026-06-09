# LipsIkeAuthCertCreate

- ea: `0x18004c6f0`
- end: `0x18004c828`
- name: `LipsIkeAuthCertCreate`
- size: `312`
- prototype: `__int64 __fastcall(__int64, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18004cb0c`

## callees

- `0x18000c4d0`
- `0x18000e510`
- `0x18004c6f0`
- `0x18004c830`
- `0x18004c85c`

## string_xrefs

- `0x18004c80d`: `LipsIkeAuthCertCreate`

## pseudocode

```c
__int64 __fastcall LipsIkeAuthCertCreate(__int64 a1, unsigned int *a2, __int64 a3)
{
  __int64 v4; // rdx
  _DWORD *v5; // rdi
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v9; // ecx
  __int64 v10; // rax
  int v11; // ebp

  v4 = a1;
  v5 = (_DWORD *)(*(_QWORD *)a3 + ((unsigned __int64)a2[2] << 6));
  if ( a2[2] >= *(_DWORD *)(a3 + 8) )
  {
    v6 = 13;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_18;
    v8 = 15;
LABEL_17:
    WPP_SF_d(v7[2], v8, WPP_69ea531b64ef3d8c6a1fb42055cd62ac_Traceguids, v6);
LABEL_18:
    LipsIkeAuthCertDestroy(v5, v4);
    return (unsigned int)LipsReportError(v6, "LipsIkeAuthCertCreate");
  }
  v9 = 3 * a2[4];
  v10 = *(_QWORD *)(v4 + 32);
  *v5 = 1;
  v11 = v10 + 8 * v9;
  if ( gcCrlCheck )
  {
    if ( gcCrlCheck == 2 )
      v5[14] |= 4u;
  }
  else
  {
    v5[14] |= 2u;
  }
  v6 = LipsIkeAuthCertRootCreate(v11, a2[5], 0, (int)v5 + 24, (__int64)(v5 + 4));
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_18;
    v8 = 16;
    goto LABEL_17;
  }
  v6 = LipsIkeAuthCertRootCreate(v11, a2[5], 1, (int)v5 + 48, (__int64)(v5 + 10));
  if ( v6 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_18;
    v8 = 17;
    goto LABEL_17;
  }
  return v6;
}

```

## disassembly

```asm
0x18004c6f0  push    rbx
0x18004c6f2  push    rbp
0x18004c6f3  push    rsi
0x18004c6f4  push    rdi
0x18004c6f5  sub     rsp, 38h
0x18004c6f9  mov     rsi, rdx
0x18004c6fc  mov     rdx, rcx
0x18004c6ff  mov     r10d, [rsi+8]
0x18004c703  mov     edi, r10d
0x18004c706  shl     rdi, 6
0x18004c70a  add     rdi, [r8]
0x18004c70d  cmp     r10d, [r8+8]
0x18004c711  jb      short loc_18004C741
0x18004c713  mov     ebx, 0Dh
0x18004c718  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c71f  lea     rax, WPP_GLOBAL_Control
0x18004c726  cmp     rcx, rax
0x18004c729  jz      loc_18004C805
0x18004c72f  test    byte ptr [rcx+1Ch], 10h
0x18004c733  jz      loc_18004C805
0x18004c739  lea     edx, [rbx+2]
0x18004c73c  jmp     loc_18004C7F2
0x18004c741  mov     eax, [rsi+10h]
0x18004c744  lea     rcx, [rax+rax*2]
0x18004c748  mov     rax, [rdx+20h]
0x18004c74c  mov     dword ptr [rdi], 1
0x18004c752  lea     rbp, [rax+rcx*8]
0x18004c756  mov     eax, cs:gcCrlCheck
0x18004c75c  test    eax, eax
0x18004c75e  jnz     short loc_18004C766
0x18004c760  or      dword ptr [rdi+38h], 2
0x18004c764  jmp     short loc_18004C76F
0x18004c766  cmp     eax, 2
0x18004c769  jnz     short loc_18004C76F
0x18004c76b  or      dword ptr [rdi+38h], 4
0x18004c76f  mov     edx, [rsi+14h]
0x18004c772  lea     rax, [rdi+10h]
0x18004c776  lea     r9, [rdi+18h]
0x18004c77a  mov     [rsp+58h+var_38], rax
0x18004c77f  xor     r8d, r8d
0x18004c782  mov     rcx, rbp
0x18004c785  call    LipsIkeAuthCertRootCreate
0x18004c78a  mov     ebx, eax
0x18004c78c  test    eax, eax
0x18004c78e  jz      short loc_18004C7B0
0x18004c790  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c797  lea     rax, WPP_GLOBAL_Control
0x18004c79e  cmp     rcx, rax
0x18004c7a1  jz      short loc_18004C805
0x18004c7a3  test    byte ptr [rcx+1Ch], 10h
0x18004c7a7  jz      short loc_18004C805
0x18004c7a9  mov     edx, 10h
0x18004c7ae  jmp     short loc_18004C7F2
0x18004c7b0  mov     edx, [rsi+14h]
0x18004c7b3  lea     rax, [rdi+28h]
0x18004c7b7  lea     r9, [rdi+30h]
0x18004c7bb  mov     [rsp+58h+var_38], rax
0x18004c7c0  mov     r8d, 1
0x18004c7c6  mov     rcx, rbp
0x18004c7c9  call    LipsIkeAuthCertRootCreate
0x18004c7ce  mov     ebx, eax
0x18004c7d0  test    eax, eax
0x18004c7d2  jz      short loc_18004C81D
0x18004c7d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c7db  lea     rax, WPP_GLOBAL_Control
0x18004c7e2  cmp     rcx, rax
0x18004c7e5  jz      short loc_18004C805
0x18004c7e7  test    byte ptr [rcx+1Ch], 10h
0x18004c7eb  jz      short loc_18004C805
0x18004c7ed  mov     edx, 11h
0x18004c7f2  mov     rcx, [rcx+10h]
0x18004c7f6  lea     r8, WPP_69ea531b64ef3d8c6a1fb42055cd62ac_Traceguids
0x18004c7fd  mov     r9d, ebx
0x18004c800  call    WPP_SF_d
0x18004c805  mov     rcx, rdi
0x18004c808  call    LipsIkeAuthCertDestroy
0x18004c80d  lea     rdx, aLipsikeauthcer; "LipsIkeAuthCertCreate"
0x18004c814  mov     ecx, ebx
0x18004c816  call    LipsReportError
0x18004c81b  mov     ebx, eax
0x18004c81d  mov     eax, ebx
0x18004c81f  add     rsp, 38h
0x18004c823  pop     rdi
0x18004c824  pop     rsi
0x18004c825  pop     rbp
0x18004c826  pop     rbx
0x18004c827  retn
```
