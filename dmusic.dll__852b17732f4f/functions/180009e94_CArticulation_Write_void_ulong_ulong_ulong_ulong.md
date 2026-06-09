# CArticulation::Write(void *,ulong *,ulong *,ulong *,ulong)

- ea: `0x180009e94`
- end: `0x18000a0a4`
- name: `?Write@CArticulation@@QEAAJPEAXPEAK11K@Z`
- size: `528`
- prototype: `__int64 __fastcall(CArticulation *this, char *, unsigned int *, unsigned int *, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e7e0`
- `0x180010c28`

## callees

- `0x180009874`
- `0x180009e94`
- `0x1800217bc`

## pseudocode

```c
__int64 __fastcall CArticulation::Write(
        CArticulation *this,
        char *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int a6)
{
  unsigned int v10; // ebx
  unsigned int v11; // eax
  unsigned int v12; // edi
  __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  unsigned int v15; // ecx
  int v16; // eax
  unsigned int v17; // r13d
  unsigned int v18; // ebp
  unsigned int v19; // ebp
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 *v22; // r13
  int v23; // ecx
  int v24; // esi
  int v25; // edx
  unsigned int v26; // edi
  int v27; // eax
  unsigned int v28; // ecx
  int v29; // [rsp+20h] [rbp-48h]
  int v30; // [rsp+70h] [rbp+8h]

  if ( !*((_DWORD *)this + 12) )
    return 0;
  v10 = 0;
  v11 = *a3;
  if ( !*((_DWORD *)this + 18) )
  {
    v20 = v11 + 8;
    *a3 = v20;
    if ( *((_QWORD *)this + 3) )
    {
      v21 = *a5;
      a4[v21] = v20;
      *(_DWORD *)a2 = v21;
      *a5 = v21 + 1;
      CArticData::GenerateLevel1((CArticulation *)((char *)this + 16), (struct _DMUS_ARTICPARAMS *)(a2 + 8));
      *a3 += 80;
      v19 = 88;
      goto LABEL_24;
    }
    v19 = 8;
LABEL_23:
    *(_DWORD *)a2 = 0;
LABEL_24:
    v22 = (__int64 *)*((_QWORD *)this + 4);
    if ( v22 )
    {
      v23 = *((_DWORD *)this + 10);
      v24 = *a5;
      *((_DWORD *)a2 + 1) = *a5;
      v30 = v23;
      if ( (v10 & 0x80000000) == 0 )
      {
        v25 = v24;
        do
        {
          if ( !v23 )
            break;
          v26 = *a3;
          v27 = v24 + 1;
          v24 = 0;
          if ( v23 != 1 )
            v24 = v27;
          v29 = v25 + 1;
          *a5 = v25 + 1;
          a4[v25] = v26;
          memcpy_0(&a2[v19], (const void *)v22[1], (*((_DWORD *)v22 + 4) + 23) & 0xFFFFFFF8);
          v25 = v29;
          v28 = (*((_DWORD *)v22 + 4) + 23) & 0xFFFFFFF8;
          *(_DWORD *)&a2[v19 + 4] = v24;
          v22 = (__int64 *)*v22;
          v19 += v28;
          v10 = 0;
          *a3 = v28 + v26;
          v23 = --v30;
        }
        while ( v22 );
      }
    }
    else
    {
      *((_DWORD *)a2 + 1) = 0;
    }
    return v10;
  }
  v12 = v11 + 16;
  *((_DWORD *)a2 + 2) = a6;
  *a3 = v11 + 16;
  if ( !*((_QWORD *)this + 3) )
  {
    v19 = 16;
    goto LABEL_23;
  }
  v13 = *a5;
  a4[v13] = v12;
  *(_DWORD *)a2 = v13;
  *a5 = v13 + 1;
  if ( !*((_QWORD *)this + 3) )
  {
    v18 = v11 + 16;
    goto LABEL_18;
  }
  *((_QWORD *)a2 + 2) = *((_QWORD *)this + 2);
  if ( !*((_QWORD *)this + 3) )
  {
    v17 = 0;
LABEL_16:
    memcpy_0(a2 + 24, *((const void **)this + 3), v17 - 8LL);
    v18 = v12 + v17;
    *a3 = v12 + v17;
LABEL_18:
    v19 = v18 - v12 + 16;
    goto LABEL_24;
  }
  v14 = 12LL * *((unsigned int *)this + 5);
  if ( v14 <= 0xFFFFFFFF )
  {
    v15 = v14 + 8;
    v16 = -1;
    if ( (int)v14 + 8 >= (unsigned int)v14 )
      v16 = v14 + 8;
    v17 = 0;
    if ( v15 >= (unsigned int)v14 )
      v17 = v16;
    v10 = v15 < (unsigned int)v14 ? 0x80070216 : 0;
    if ( v15 < (unsigned int)v14 )
      return v10;
    goto LABEL_16;
  }
  return (unsigned int)-2147024362;
}

```

## disassembly

```asm
0x180009e94  mov     [rsp+arg_8], rbx
0x180009e99  mov     [rsp+arg_18], r9
0x180009e9e  push    rbp
0x180009e9f  push    rsi
0x180009ea0  push    rdi
0x180009ea1  push    r12
0x180009ea3  push    r13
0x180009ea5  push    r14
0x180009ea7  push    r15
0x180009ea9  sub     rsp, 30h
0x180009ead  xor     r10d, r10d
0x180009eb0  mov     r15, r8
0x180009eb3  mov     r14, rdx
0x180009eb6  mov     rsi, rcx
0x180009eb9  cmp     [rcx+30h], r10d
0x180009ebd  jnz     short loc_180009EC6
0x180009ebf  xor     eax, eax
0x180009ec1  jmp     loc_18000A08F
0x180009ec6  mov     ebx, r10d
0x180009ec9  mov     eax, [r8]
0x180009ecc  mov     r11d, 0FFFFFFFFh
0x180009ed2  mov     r12, [rsp+68h+arg_20]
0x180009eda  cmp     [rcx+48h], r10d
0x180009ede  jz      loc_180009F93
0x180009ee4  lea     edi, [rax+10h]
0x180009ee7  mov     eax, [rsp+68h+arg_28]
0x180009eee  mov     [rdx+8], eax
0x180009ef1  mov     [r8], edi
0x180009ef4  cmp     [rcx+18h], r10
0x180009ef8  jz      loc_180009F8C
0x180009efe  mov     ecx, [r12]
0x180009f02  mov     [r9+rcx*4], edi
0x180009f06  lea     eax, [rcx+1]
0x180009f09  mov     [rdx], ecx
0x180009f0b  mov     [r12], eax
0x180009f0f  cmp     [rsi+18h], r10
0x180009f13  jz      short loc_180009F83
0x180009f15  mov     rax, [rsi+10h]
0x180009f19  mov     [rdx+10h], rax
0x180009f1d  mov     r9, [rsi+18h]
0x180009f21  test    r9, r9
0x180009f24  jz      short loc_180009F64
0x180009f26  mov     eax, [rsi+14h]
0x180009f29  lea     rdx, [rax+rax*2]
0x180009f2d  shl     rdx, 2
0x180009f31  cmp     rdx, r11
0x180009f34  ja      short loc_180009F5A
0x180009f36  lea     ecx, [rdx+8]
0x180009f39  mov     eax, r11d
0x180009f3c  cmp     ecx, edx
0x180009f3e  cmovnb  eax, ecx
0x180009f41  mov     r13d, r10d
0x180009f44  cmovnb  r13d, eax
0x180009f48  sbb     ebx, ebx
0x180009f4a  and     ebx, 80070216h
0x180009f50  cmp     ecx, edx
0x180009f52  jb      loc_18000A08D
0x180009f58  jmp     short loc_180009F67
0x180009f5a  mov     ebx, 80070216h
0x180009f5f  jmp     loc_18000A08D
0x180009f64  mov     r13d, r10d
0x180009f67  mov     r8d, r13d
0x180009f6a  lea     rcx, [r14+18h]; void *
0x180009f6e  sub     r8, 8; Size
0x180009f72  mov     rdx, r9; Src
0x180009f75  call    memcpy_0
0x180009f7a  lea     ebp, [rdi+r13]
0x180009f7e  mov     [r15], ebp
0x180009f81  jmp     short loc_180009F85
0x180009f83  mov     ebp, edi
0x180009f85  sub     ebp, edi
0x180009f87  add     ebp, 10h
0x180009f8a  jmp     short loc_180009FD1
0x180009f8c  mov     ebp, 10h
0x180009f91  jmp     short loc_180009FCE
0x180009f93  add     eax, 8
0x180009f96  mov     [r8], eax
0x180009f99  cmp     [rcx+18h], r10
0x180009f9d  jz      short loc_180009FC9
0x180009f9f  mov     edx, [r12]
0x180009fa3  add     rcx, 10h; this
0x180009fa7  mov     [r9+rdx*4], eax
0x180009fab  lea     eax, [rdx+1]
0x180009fae  mov     [r14], edx
0x180009fb1  lea     rdx, [r14+8]; struct _DMUS_ARTICPARAMS *
0x180009fb5  mov     [r12], eax
0x180009fb9  call    ?GenerateLevel1@CArticData@@QEAAJPEAU_DMUS_ARTICPARAMS@@@Z; CArticData::GenerateLevel1(_DMUS_ARTICPARAMS *)
0x180009fbe  add     dword ptr [r15], 50h ; 'P'
0x180009fc2  mov     ebp, 58h ; 'X'
0x180009fc7  jmp     short loc_180009FD1
0x180009fc9  mov     ebp, 8
0x180009fce  mov     [rdx], r10d
0x180009fd1  mov     r13, [rsi+20h]
0x180009fd5  test    r13, r13
0x180009fd8  jz      loc_18000A085
0x180009fde  mov     ecx, [rsi+28h]
0x180009fe1  mov     esi, [r12]
0x180009fe5  mov     [r14+4], esi
0x180009fe9  mov     [rsp+68h+arg_0], ecx
0x180009fed  test    ebx, ebx
0x180009fef  js      loc_18000A08D
0x180009ff5  mov     edx, esi
0x180009ff7  mov     r9d, 0FFFFFFF8h
0x180009ffd  test    ecx, ecx
0x180009fff  jz      loc_18000A08D
0x18000a005  mov     edi, [r15]
0x18000a008  lea     eax, [rsi+1]
0x18000a00b  xor     esi, esi
0x18000a00d  mov     ebx, ebp
0x18000a00f  cmp     ecx, 1
0x18000a012  mov     rcx, [rsp+68h+arg_18]
0x18000a01a  cmovnz  esi, eax
0x18000a01d  mov     eax, edx
0x18000a01f  inc     edx
0x18000a021  add     rbx, r14
0x18000a024  mov     [rsp+68h+var_48], edx
0x18000a028  mov     [r12], edx
0x18000a02c  mov     [rcx+rax*4], edi
0x18000a02f  mov     rcx, rbx; void *
0x18000a032  mov     r8d, [r13+10h]
0x18000a036  mov     rdx, [r13+8]; Src
0x18000a03a  add     r8d, 17h
0x18000a03e  and     r8, r9; Size
0x18000a041  call    memcpy_0
0x18000a046  mov     ecx, [r13+10h]
0x18000a04a  mov     r9d, 0FFFFFFF8h
0x18000a050  mov     edx, [rsp+68h+var_48]
0x18000a054  add     ecx, 17h
0x18000a057  and     ecx, r9d
0x18000a05a  mov     [rbx+4], esi
0x18000a05d  mov     r13, [r13+0]
0x18000a061  add     ebp, ecx
0x18000a063  xor     ebx, ebx
0x18000a065  lea     eax, [rcx+rdi]
0x18000a068  mov     ecx, [rsp+68h+arg_0]
0x18000a06c  mov     [r15], eax
0x18000a06f  mov     eax, 0FFFFFFFFh
0x18000a074  add     ecx, eax
0x18000a076  mov     [rsp+68h+arg_0], ecx
0x18000a07a  test    r13, r13
0x18000a07d  jnz     loc_180009FFD
0x18000a083  jmp     short loc_18000A08D
0x18000a085  mov     dword ptr [r14+4], 0
0x18000a08d  mov     eax, ebx
0x18000a08f  mov     rbx, [rsp+68h+arg_8]
0x18000a094  add     rsp, 30h
0x18000a098  pop     r15
0x18000a09a  pop     r14
0x18000a09c  pop     r13
0x18000a09e  pop     r12
0x18000a0a0  pop     rdi
0x18000a0a1  pop     rsi
0x18000a0a2  pop     rbp
0x18000a0a3  retn
```
