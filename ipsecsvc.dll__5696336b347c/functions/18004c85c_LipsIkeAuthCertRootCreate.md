# LipsIkeAuthCertRootCreate

- ea: `0x18004c85c`
- end: `0x18004ca12`
- name: `LipsIkeAuthCertRootCreate`
- size: `438`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18004c6f0`

## callees

- `0x180006f00`
- `0x18000c4d0`
- `0x18000e510`
- `0x180042ef8`
- `0x18004a188`
- `0x18004c85c`
- `0x18004ca18`

## string_xrefs

- `0x18004c9f3`: `LipsIkeAuthCertRootCreate`

## pseudocode

```c
__int64 __fastcall LipsIkeAuthCertRootCreate(__int64 a1, unsigned int a2, int a3, _QWORD *a4, unsigned int *a5)
{
  unsigned int *v5; // r15
  unsigned int v10; // ebx
  int v11; // r10d
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r8
  _DWORD *v15; // rdi
  __int64 i; // rsi
  int v17; // edx
  int v18; // eax
  unsigned int v19; // eax
  SIZE_T v21[11]; // [rsp+20h] [rbp-58h] BYREF
  _DWORD *v22; // [rsp+98h] [rbp+20h] BYREF

  v5 = a5;
  *a4 = 0;
  v21[0] = 0;
  v22 = 0;
  *v5 = 0;
  v10 = NsuSizeTMultiply(a2, 24, v21);
  if ( v10 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_27;
    v13 = (unsigned int)(v11 + 18);
    goto LABEL_5;
  }
  v22 = IpsecAllocMem(v21[0]);
  v15 = v22;
  if ( !v22 )
  {
    v10 = 8;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_27;
    v13 = 19;
LABEL_5:
    WPP_SF_d(v12[2], v13, WPP_69ea531b64ef3d8c6a1fb42055cd62ac_Traceguids, v10);
    goto LABEL_27;
  }
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= a2 )
    {
      *v5 = a2;
      *a4 = v15;
      v22 = 0;
      goto LABEL_27;
    }
    v17 = *(_DWORD *)(a1 + 24 * i + 16);
    v15[6 * i + 4] = 0;
    if ( (v17 & 1) != 0 )
    {
      v15[6 * i + 4] = 1;
      v18 = 1;
    }
    else
    {
      v18 = 0;
    }
    if ( (v17 & 2) != 0 )
    {
      v18 |= 2u;
      v15[6 * i + 4] = v18;
    }
    if ( gcNapFlag == 1 )
    {
      v18 |= 4u;
      v15[6 * i + 4] = v18;
    }
    if ( a3 )
      v15[6 * i + 4] = v18 | 0x20;
    v19 = *(_DWORD *)(a1 + 24 * i + 4);
    v15[6 * i] = v19;
    v10 = LipsBufferCopy(*(void **)(a1 + 24 * i + 8), v19, v14, &v15[6 * i + 2]);
    if ( v10 )
      break;
  }
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v13 = 20;
    goto LABEL_5;
  }
LABEL_27:
  LipsIkeAuthCertRootDestroy(a2, &v22);
  if ( v10 )
    return LipsReportError(v10, "LipsIkeAuthCertRootCreate");
  else
    return 0;
}

```

## disassembly

```asm
0x18004c85c  mov     rax, rsp
0x18004c85f  push    rbx
0x18004c860  push    rbp
0x18004c861  push    rsi
0x18004c862  push    rdi
0x18004c863  push    r12
0x18004c865  push    r13
0x18004c867  push    r14
0x18004c869  push    r15
0x18004c86b  sub     rsp, 38h
0x18004c86f  mov     r15, [rsp+78h+arg_20]
0x18004c877  xor     r10d, r10d
0x18004c87a  mov     ebp, edx
0x18004c87c  mov     r12, rcx
0x18004c87f  mov     ecx, edx
0x18004c881  mov     r13d, r8d
0x18004c884  mov     [r9], r10
0x18004c887  lea     r8, [rax-58h]
0x18004c88b  lea     edx, [r10+18h]
0x18004c88f  mov     [rax-58h], r10
0x18004c893  mov     r14, r9
0x18004c896  mov     [rax+20h], r10
0x18004c89a  mov     [r15], r10d
0x18004c89d  call    NsuSizeTMultiply
0x18004c8a2  mov     ebx, eax
0x18004c8a4  test    eax, eax
0x18004c8a6  jz      short loc_18004C8E5
0x18004c8a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c8af  lea     rax, WPP_GLOBAL_Control
0x18004c8b6  cmp     rcx, rax
0x18004c8b9  jz      loc_18004C9DC
0x18004c8bf  test    byte ptr [rcx+1Ch], 10h
0x18004c8c3  jz      loc_18004C9DC
0x18004c8c9  lea     edx, [r10+12h]
0x18004c8cd  mov     rcx, [rcx+10h]
0x18004c8d1  lea     r8, WPP_69ea531b64ef3d8c6a1fb42055cd62ac_Traceguids
0x18004c8d8  mov     r9d, ebx
0x18004c8db  call    WPP_SF_d
0x18004c8e0  jmp     loc_18004C9DC
0x18004c8e5  mov     rcx, [rsp+78h+var_58]
0x18004c8ea  call    IpsecAllocMem
0x18004c8ef  mov     [rsp+78h+arg_18], rax
0x18004c8f7  mov     rdi, rax
0x18004c8fa  test    rax, rax
0x18004c8fd  jnz     short loc_18004C928
0x18004c8ff  lea     ebx, [rax+8]
0x18004c902  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c909  lea     rax, WPP_GLOBAL_Control
0x18004c910  cmp     rcx, rax
0x18004c913  jz      loc_18004C9DC
0x18004c919  test    byte ptr [rcx+1Ch], 10h
0x18004c91d  jz      loc_18004C9DC
0x18004c923  lea     edx, [rdi+13h]
0x18004c926  jmp     short loc_18004C8CD
0x18004c928  xor     esi, esi
0x18004c92a  cmp     esi, ebp
0x18004c92c  jnb     loc_18004C9CA
0x18004c932  lea     rcx, [rsi+rsi*2]
0x18004c936  mov     edx, [r12+rcx*8+10h]
0x18004c93b  mov     dword ptr [rdi+rcx*8+10h], 0
0x18004c943  test    dl, 1
0x18004c946  jz      short loc_18004C957
0x18004c948  mov     dword ptr [rdi+rcx*8+10h], 1
0x18004c950  mov     eax, 1
0x18004c955  jmp     short loc_18004C959
0x18004c957  xor     eax, eax
0x18004c959  test    dl, 2
0x18004c95c  jz      short loc_18004C965
0x18004c95e  or      eax, 2
0x18004c961  mov     [rdi+rcx*8+10h], eax
0x18004c965  cmp     cs:gcNapFlag, 1
0x18004c96c  jnz     short loc_18004C975
0x18004c96e  or      eax, 4
0x18004c971  mov     [rdi+rcx*8+10h], eax
0x18004c975  test    r13d, r13d
0x18004c978  jz      short loc_18004C981
0x18004c97a  or      eax, 20h
0x18004c97d  mov     [rdi+rcx*8+10h], eax
0x18004c981  mov     eax, [r12+rcx*8+4]
0x18004c986  lea     r9, [rdi+8]
0x18004c98a  mov     [rdi+rcx*8], eax
0x18004c98d  lea     r9, [r9+rcx*8]
0x18004c991  mov     rcx, [r12+rcx*8+8]; Src
0x18004c996  mov     edx, eax; Size
0x18004c998  call    LipsBufferCopy
0x18004c99d  mov     ebx, eax
0x18004c99f  test    eax, eax
0x18004c9a1  jnz     short loc_18004C9A7
0x18004c9a3  inc     esi
0x18004c9a5  jmp     short loc_18004C92A
0x18004c9a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c9ae  lea     rax, WPP_GLOBAL_Control
0x18004c9b5  cmp     rcx, rax
0x18004c9b8  jz      short loc_18004C9DC
0x18004c9ba  test    byte ptr [rcx+1Ch], 10h
0x18004c9be  jz      short loc_18004C9DC
0x18004c9c0  mov     edx, 14h
0x18004c9c5  jmp     loc_18004C8CD
0x18004c9ca  mov     [r15], ebp
0x18004c9cd  mov     [r14], rdi
0x18004c9d0  mov     [rsp+78h+arg_18], 0
0x18004c9dc  lea     rdx, [rsp+78h+arg_18]
0x18004c9e4  mov     ecx, ebp
0x18004c9e6  call    LipsIkeAuthCertRootDestroy
0x18004c9eb  test    ebx, ebx
0x18004c9ed  jnz     short loc_18004C9F3
0x18004c9ef  xor     eax, eax
0x18004c9f1  jmp     short loc_18004CA01
0x18004c9f3  lea     rdx, aLipsikeauthcer_0; "LipsIkeAuthCertRootCreate"
0x18004c9fa  mov     ecx, ebx
0x18004c9fc  call    LipsReportError
0x18004ca01  add     rsp, 38h
0x18004ca05  pop     r15
0x18004ca07  pop     r14
0x18004ca09  pop     r13
0x18004ca0b  pop     r12
0x18004ca0d  pop     rdi
0x18004ca0e  pop     rsi
0x18004ca0f  pop     rbp
0x18004ca10  pop     rbx
0x18004ca11  retn
```
