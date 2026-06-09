# CInstrObj::Write(void *)

- ea: `0x18000e7e0`
- end: `0x18000ebd3`
- name: `?Write@CInstrObj@@AEAAJPEAX@Z`
- size: `1011`
- prototype: `__int64 __fastcall(CRegion **this, char *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000f6a4`

## callees

- `0x1800021a8`
- `0x180009e94`
- `0x18000e508`
- `0x18000e7e0`
- `0x1800108c8`
- `0x180010c28`
- `0x1800217bc`

## pseudocode

```c
__int64 __fastcall CInstrObj::Write(CRegion **this, char *a2)
{
  __int64 *v4; // r11
  unsigned __int64 v5; // r8
  signed int v6; // ebx
  int v7; // ecx
  unsigned int v8; // edx
  unsigned int v9; // ecx
  unsigned int v10; // eax
  __int64 v11; // rcx
  char *v12; // r8
  __int64 v13; // r12
  unsigned int v14; // esi
  CRegion *v15; // rdx
  unsigned int v16; // r15d
  CRegion *v17; // r10
  CRegion *v18; // r10
  CRegion *i; // r14
  int v20; // eax
  CRegion *v21; // rcx
  int v22; // r14d
  __int64 v23; // rax
  char *v24; // rbx
  CRegion **v25; // rcx
  CRegion *v26; // rax
  CRegion *v27; // rbx
  int v28; // eax
  __int64 v29; // rcx
  CRegion *v30; // rcx
  int v31; // eax
  unsigned int v32; // r8d
  CRegion *v33; // r14
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // eax
  unsigned int v39; // [rsp+80h] [rbp+48h] BYREF
  unsigned int v40; // [rsp+88h] [rbp+50h] BYREF
  size_t Size; // [rsp+90h] [rbp+58h] BYREF
  CRegion *v42; // [rsp+98h] [rbp+60h]

  LODWORD(Size) = 0;
  CInstrObj::Size((CInstrObj *)this, (unsigned int *)&Size);
  v4 = 0;
  *(_DWORD *)a2 = *((_DWORD *)this + 22) != 0 ? 3 : 1;
  *((_DWORD *)a2 + 1) = *((_DWORD *)this + 13);
  *((_DWORD *)a2 + 2) = *((_DWORD *)this + 18);
  *((_DWORD *)a2 + 3) = Size;
  v5 = 4LL * *((unsigned int *)this + 18);
  v6 = -2147024362;
  if ( v5 > 0xFFFFFFFF )
    goto LABEL_72;
  v7 = -1;
  v8 = v5 + 7;
  if ( (int)v5 + 7 >= (unsigned int)v5 )
    v7 = v5 + 7;
  v9 = v7 & 0xFFFFFFF8;
  if ( v8 < (unsigned int)v5 )
  {
    v6 = v8 < (unsigned int)v5 ? 0x80070216 : 0;
    goto LABEL_72;
  }
  v10 = v9;
  v11 = v9 + 16;
  if ( v10 >= 0xFFFFFFF0 )
    goto LABEL_72;
  v12 = a2 + 16;
  v13 = (unsigned int)v11;
  *((_DWORD *)a2 + 4) = v11;
  v14 = 1;
  *(_DWORD *)&a2[v11] = *((_DWORD *)this + 3);
  *(_DWORD *)&a2[v11 + 20] = 0;
  v15 = this[7];
  if ( *((_QWORD *)v15 + 28) == *(_QWORD *)&GUID_DefaultGMCollection.Data1
    && *((_QWORD *)v15 + 29) == *(_QWORD *)GUID_DefaultGMCollection.Data4 )
  {
    *(_DWORD *)&a2[v11 + 20] = 1;
  }
  v16 = v11 + 24;
  if ( (int)v11 + 24 < (unsigned int)v11 )
    goto LABEL_72;
  *(_DWORD *)&a2[v11 + 4] = 0;
  v6 = 0;
  v17 = this[2];
  v39 = v10 + 40;
  if ( v17 )
  {
    while ( !CRegion::Count(v17) )
    {
      v17 = *(CRegion **)v18;
      if ( !v17 )
      {
LABEL_24:
        v12 = a2 + 16;
        goto LABEL_25;
      }
    }
    while ( 1 )
    {
      for ( i = *(CRegion **)v18; i; i = *(CRegion **)i )
      {
        if ( CRegion::Count(i) )
        {
          LODWORD(v4) = v14 + CRegion::Count(v18);
          break;
        }
      }
      if ( !*(_DWORD *)&a2[v13 + 4] )
        *(_DWORD *)&a2[v13 + 4] = v14;
      *(_DWORD *)&a2[4 * v14 + 16] = v16;
      v40 = v14 + 1;
      v20 = CRegion::Write(v18, &a2[v16], &v39, (unsigned int *)a2 + 4, &v40, (unsigned int)v4);
      v4 = 0;
      v6 = v20;
      if ( v20 < 0 )
        goto LABEL_72;
      v14 = v40;
      v18 = i;
      v16 = v39;
      if ( !i )
        goto LABEL_24;
    }
  }
LABEL_25:
  v21 = this[5];
  v42 = v21;
  if ( v21 )
  {
    v22 = *((_DWORD *)this + 12);
    *(_DWORD *)&a2[v13 + 12] = v14;
    if ( v6 < 0 )
      goto LABEL_72;
    do
    {
      if ( !v22 )
        break;
      v40 = v22 == 1 ? (unsigned int)v4 : v14 + 1;
      v23 = v14++;
      v24 = &a2[v16];
      *(_DWORD *)&v12[4 * v23] = v16;
      memcpy_0(v24, *((const void **)v21 + 1), (*((_DWORD *)v21 + 4) + 23) & 0xFFFFFFF8);
      v25 = (CRegion **)v42;
      v12 = a2 + 16;
      v4 = 0;
      v16 += (*((_DWORD *)v42 + 4) + 23) & 0xFFFFFFF8;
      *((_DWORD *)v24 + 1) = v40;
      v6 = 0;
      v21 = *v25;
      --v22;
      v39 = v16;
      v42 = v21;
    }
    while ( v21 );
  }
  else
  {
    *(_DWORD *)&a2[v13 + 12] = (_DWORD)v4;
  }
  v26 = this[4];
  if ( !v26 || *((__int64 **)v26 + 2) == v4 )
  {
    v29 = *((_QWORD *)this[7] + 10);
    if ( !v29 || *(__int64 **)(v29 + 16) == v4 )
    {
      *(_DWORD *)&a2[v13 + 16] = (_DWORD)v4;
      goto LABEL_42;
    }
    *(_DWORD *)&a2[4 * v14 + 16] = v16;
    *(_DWORD *)&a2[v13 + 16] = v14;
    v27 = (CRegion *)*((_QWORD *)this[7] + 10);
  }
  else
  {
    *(_DWORD *)&a2[4 * v14 + 16] = v16;
    *(_DWORD *)&a2[v13 + 16] = v14;
    v27 = this[4];
  }
  memcpy_0(&a2[v16], *((const void **)v27 + 2), (*((_DWORD *)v27 + 6) + 15) & 0xFFFFFFF8);
  v4 = 0;
  v28 = *((_DWORD *)v27 + 6) + 15;
  v6 = 0;
  v16 += v28 & 0xFFFFFFF8;
  v39 = v16;
  ++v14;
LABEL_42:
  *(_DWORD *)&a2[v13 + 8] = (_DWORD)v4;
  v30 = this[3];
  if ( v30 )
  {
    do
    {
      if ( *((_DWORD *)v30 + 12) != (_DWORD)v4 )
      {
        v31 = *((_DWORD *)v30 + 10);
        if ( *((__int64 **)v30 + 3) != v4 )
          ++v31;
        if ( v31 != -1 )
          break;
      }
      v30 = *(CRegion **)v30;
    }
    while ( v30 );
    if ( v30 )
    {
      while ( 1 )
      {
        v32 = (unsigned int)v4;
        if ( *((_DWORD *)this + 22) == (_DWORD)v4 )
        {
          v33 = (CRegion *)v4;
        }
        else
        {
          v33 = *(CRegion **)v30;
          if ( *(_QWORD *)v30 )
          {
            do
            {
              if ( *((_DWORD *)v33 + 12) != (_DWORD)v4 )
              {
                v34 = *((_DWORD *)v33 + 10);
                if ( *((__int64 **)v33 + 3) != v4 )
                  ++v34;
                if ( v34 != -1 )
                  break;
              }
              v33 = *(CRegion **)v33;
            }
            while ( v33 );
            if ( v33 )
            {
              if ( *((_DWORD *)v30 + 12) == (_DWORD)v4 )
              {
                v36 = (int)v4;
              }
              else
              {
                v35 = *((_DWORD *)v30 + 10);
                if ( *((__int64 **)v30 + 3) != v4 )
                  ++v35;
                v36 = v35 + 1;
              }
              v32 = v36 + v14;
            }
          }
        }
        if ( *(_DWORD *)&a2[v13 + 8] == (_DWORD)v4 )
          *(_DWORD *)&a2[v13 + 8] = v14;
        v40 = v14 + 1;
        *(_DWORD *)&a2[4 * v14 + 16] = v16;
        v37 = CArticulation::Write(v30, &a2[v16], &v39, (unsigned int *)a2 + 4, &v40, v32);
        v4 = 0;
        v6 = v37;
        if ( v37 < 0 )
          break;
        v30 = v33;
        if ( !v33 )
          return (unsigned int)v6;
        v14 = v40;
        v16 = v39;
      }
      goto LABEL_72;
    }
  }
  if ( v6 < 0 )
LABEL_72:
    memset_0(a2, 0, (unsigned int)Size);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000e7e0  push    rbp
0x18000e7e2  push    rbx
0x18000e7e3  push    rsi
0x18000e7e4  push    rdi
0x18000e7e5  push    r12
0x18000e7e7  push    r13
0x18000e7e9  push    r14
0x18000e7eb  push    r15
0x18000e7ed  mov     rbp, rsp
0x18000e7f0  sub     rsp, 38h
0x18000e7f4  mov     rdi, rdx
0x18000e7f7  mov     dword ptr [rbp+Size], 0
0x18000e7fe  lea     rdx, [rbp+Size]; unsigned int *
0x18000e802  mov     r13, rcx
0x18000e805  call    ?Size@CInstrObj@@AEAAJPEAK@Z; CInstrObj::Size(ulong *)
0x18000e80a  mov     eax, [r13+58h]
0x18000e80e  xor     r11d, r11d
0x18000e811  neg     eax
0x18000e813  mov     esi, r11d
0x18000e816  sbb     r8d, r8d
0x18000e819  and     r8d, 2
0x18000e81d  inc     r8d
0x18000e820  mov     [rdi], r8d
0x18000e823  mov     eax, [r13+34h]
0x18000e827  mov     [rdi+4], eax
0x18000e82a  mov     eax, [r13+48h]
0x18000e82e  mov     [rdi+8], eax
0x18000e831  mov     eax, dword ptr [rbp+Size]
0x18000e834  mov     [rdi+0Ch], eax
0x18000e837  mov     r8d, [r13+48h]
0x18000e83b  mov     eax, 0FFFFFFFFh
0x18000e840  shl     r8, 2
0x18000e844  mov     ebx, 80070216h
0x18000e849  cmp     r8, rax
0x18000e84c  ja      loc_18000EBB2
0x18000e852  mov     ecx, eax
0x18000e854  lea     edx, [r8+7]
0x18000e858  cmp     edx, r8d
0x18000e85b  cmovnb  ecx, edx
0x18000e85e  sbb     eax, eax
0x18000e860  and     eax, ebx
0x18000e862  cmp     edx, r8d
0x18000e865  sbb     r9d, r9d
0x18000e868  and     r9d, eax
0x18000e86b  mov     eax, 0FFFFFFF8h
0x18000e870  and     ecx, eax
0x18000e872  mov     eax, r11d
0x18000e875  cmp     edx, r8d
0x18000e878  cmovnb  eax, ecx
0x18000e87b  test    r9d, r9d
0x18000e87e  js      loc_18000EBAF
0x18000e884  lea     ecx, [rax+10h]
0x18000e887  cmp     ecx, 10h
0x18000e88a  jb      loc_18000EBB2
0x18000e890  lea     r8, [rdi+10h]
0x18000e894  mov     r12d, ecx
0x18000e897  mov     [r8+rsi*4], ecx
0x18000e89b  inc     esi
0x18000e89d  mov     eax, [r13+0Ch]
0x18000e8a1  mov     [rcx+rdi], eax
0x18000e8a4  mov     [rcx+rdi+14h], r11d
0x18000e8a9  mov     rdx, [r13+38h]
0x18000e8ad  mov     rax, [rdx+0E0h]
0x18000e8b4  cmp     rax, qword ptr cs:GUID_DefaultGMCollection.Data1
0x18000e8bb  jnz     short loc_18000E8D5
0x18000e8bd  mov     rax, [rdx+0E8h]
0x18000e8c4  cmp     rax, qword ptr cs:GUID_DefaultGMCollection.Data4
0x18000e8cb  jnz     short loc_18000E8D5
0x18000e8cd  mov     dword ptr [rcx+rdi+14h], 1
0x18000e8d5  lea     r15d, [rcx+18h]
0x18000e8d9  cmp     r15d, ecx
0x18000e8dc  jb      loc_18000EBB2
0x18000e8e2  mov     [rcx+rdi+4], r11d
0x18000e8e7  mov     ebx, r11d
0x18000e8ea  mov     r10, [r13+10h]
0x18000e8ee  mov     [rbp+arg_0], r15d
0x18000e8f2  test    r10, r10
0x18000e8f5  jz      loc_18000E998
0x18000e8fb  mov     rcx, r10; this
0x18000e8fe  call    ?Count@CRegion@@QEAAKXZ; CRegion::Count(void)
0x18000e903  test    eax, eax
0x18000e905  jnz     short loc_18000E914
0x18000e907  mov     r10, [r10]
0x18000e90a  test    r10, r10
0x18000e90d  jnz     short loc_18000E8FB
0x18000e90f  jmp     loc_18000E994
0x18000e914  mov     r14, [r10]
0x18000e917  jmp     short loc_18000E928
0x18000e919  mov     rcx, r14; this
0x18000e91c  call    ?Count@CRegion@@QEAAKXZ; CRegion::Count(void)
0x18000e921  test    eax, eax
0x18000e923  jnz     short loc_18000E92F
0x18000e925  mov     r14, [r14]
0x18000e928  test    r14, r14
0x18000e92b  jnz     short loc_18000E919
0x18000e92d  jmp     short loc_18000E93B
0x18000e92f  mov     rcx, r10; this
0x18000e932  call    ?Count@CRegion@@QEAAKXZ; CRegion::Count(void)
0x18000e937  lea     r11d, [rsi+rax]
0x18000e93b  cmp     dword ptr [r12+rdi+4], 0
0x18000e941  jnz     short loc_18000E948
0x18000e943  mov     [r12+rdi+4], esi
0x18000e948  mov     edx, esi
0x18000e94a  lea     rcx, [rbp+arg_8]
0x18000e94e  mov     [rsp+38h+var_10], r11d; unsigned int
0x18000e953  lea     r9, [rdi+10h]; unsigned int *
0x18000e957  mov     [rsp+38h+var_18], rcx; unsigned int *
0x18000e95c  lea     r8, [rbp+arg_0]; unsigned int *
0x18000e960  inc     esi
0x18000e962  mov     rcx, r10; this
0x18000e965  mov     [rdi+rdx*4+10h], r15d
0x18000e96a  mov     edx, r15d
0x18000e96d  add     rdx, rdi; void *
0x18000e970  mov     [rbp+arg_8], esi
0x18000e973  call    ?Write@CRegion@@QEAAJPEAXPEAK11K@Z; CRegion::Write(void *,ulong *,ulong *,ulong *,ulong)
0x18000e978  xor     r11d, r11d
0x18000e97b  mov     ebx, eax
0x18000e97d  test    eax, eax
0x18000e97f  js      loc_18000EBB2
0x18000e985  mov     esi, [rbp+arg_8]
0x18000e988  mov     r10, r14
0x18000e98b  mov     r15d, [rbp+arg_0]
0x18000e98f  test    r14, r14
0x18000e992  jnz     short loc_18000E914
0x18000e994  lea     r8, [rdi+10h]
0x18000e998  mov     rcx, [r13+28h]
0x18000e99c  mov     [rbp+arg_18], rcx
0x18000e9a0  test    rcx, rcx
0x18000e9a3  jz      loc_18000EA39
0x18000e9a9  mov     r14d, [r13+30h]
0x18000e9ad  mov     [r12+rdi+0Ch], esi
0x18000e9b2  test    ebx, ebx
0x18000e9b4  js      loc_18000EBB2
0x18000e9ba  test    r14d, r14d
0x18000e9bd  jz      short loc_18000EA3E
0x18000e9bf  cmp     r14d, 1
0x18000e9c3  jnz     short loc_18000E9CB
0x18000e9c5  mov     [rbp+arg_8], r11d
0x18000e9c9  jmp     short loc_18000E9D1
0x18000e9cb  lea     eax, [rsi+1]
0x18000e9ce  mov     [rbp+arg_8], eax
0x18000e9d1  mov     eax, esi
0x18000e9d3  inc     esi
0x18000e9d5  mov     ebx, r15d
0x18000e9d8  add     rbx, rdi
0x18000e9db  mov     [r8+rax*4], r15d
0x18000e9df  mov     eax, 0FFFFFFF8h
0x18000e9e4  mov     r8d, [rcx+10h]
0x18000e9e8  mov     rdx, [rcx+8]; Src
0x18000e9ec  add     r8d, 17h
0x18000e9f0  and     r8, rax; Size
0x18000e9f3  mov     rcx, rbx; void *
0x18000e9f6  call    memcpy_0
0x18000e9fb  mov     rcx, [rbp+arg_18]
0x18000e9ff  lea     r8, [rdi+10h]
0x18000ea03  xor     r11d, r11d
0x18000ea06  mov     edx, 0FFFFFFF8h
0x18000ea0b  mov     eax, [rcx+10h]
0x18000ea0e  add     eax, 17h
0x18000ea11  and     eax, edx
0x18000ea13  add     r15d, eax
0x18000ea16  mov     eax, [rbp+arg_8]
0x18000ea19  mov     [rbx+4], eax
0x18000ea1c  mov     ebx, r11d
0x18000ea1f  mov     rcx, [rcx]
0x18000ea22  mov     eax, 0FFFFFFFFh
0x18000ea27  add     r14d, eax
0x18000ea2a  mov     [rbp+arg_0], r15d
0x18000ea2e  mov     [rbp+arg_18], rcx
0x18000ea32  test    rcx, rcx
0x18000ea35  jnz     short loc_18000E9BA
0x18000ea37  jmp     short loc_18000EA3E
0x18000ea39  mov     [r12+rdi+0Ch], r11d
0x18000ea3e  mov     rax, [r13+20h]
0x18000ea42  test    rax, rax
0x18000ea45  jz      short loc_18000EA97
0x18000ea47  cmp     [rax+10h], r11
0x18000ea4b  jz      short loc_18000EA97
0x18000ea4d  mov     eax, esi
0x18000ea4f  mov     [rdi+rax*4+10h], r15d
0x18000ea54  mov     [r12+rdi+10h], esi
0x18000ea59  mov     rbx, [r13+20h]
0x18000ea5d  mov     r8d, [rbx+18h]
0x18000ea61  mov     r14d, 0FFFFFFF8h
0x18000ea67  mov     rdx, [rbx+10h]; Src
0x18000ea6b  add     r8d, 0Fh
0x18000ea6f  mov     ecx, r15d
0x18000ea72  and     r8, r14; Size
0x18000ea75  add     rcx, rdi; void *
0x18000ea78  call    memcpy_0
0x18000ea7d  mov     eax, [rbx+18h]
0x18000ea80  xor     r11d, r11d
0x18000ea83  add     eax, 0Fh
0x18000ea86  mov     ebx, r11d
0x18000ea89  and     eax, r14d
0x18000ea8c  add     r15d, eax
0x18000ea8f  mov     [rbp+arg_0], r15d
0x18000ea93  inc     esi
0x18000ea95  jmp     short loc_18000EAC5
0x18000ea97  mov     rax, [r13+38h]
0x18000ea9b  mov     rcx, [rax+50h]
0x18000ea9f  test    rcx, rcx
0x18000eaa2  jz      short loc_18000EAC0
0x18000eaa4  cmp     [rcx+10h], r11
0x18000eaa8  jz      short loc_18000EAC0
0x18000eaaa  mov     eax, esi
0x18000eaac  mov     [rdi+rax*4+10h], r15d
0x18000eab1  mov     [r12+rdi+10h], esi
0x18000eab6  mov     rax, [r13+38h]
0x18000eaba  mov     rbx, [rax+50h]
0x18000eabe  jmp     short loc_18000EA5D
0x18000eac0  mov     [r12+rdi+10h], r11d
0x18000eac5  mov     [r12+rdi+8], r11d
0x18000eaca  mov     rcx, [r13+18h]
0x18000eace  test    rcx, rcx
0x18000ead1  jz      loc_18000EBA9
0x18000ead7  cmp     [rcx+30h], r11d
0x18000eadb  jz      short loc_18000EAED
0x18000eadd  mov     eax, [rcx+28h]
0x18000eae0  cmp     [rcx+18h], r11
0x18000eae4  jz      short loc_18000EAE8
0x18000eae6  inc     eax
0x18000eae8  add     eax, 1
0x18000eaeb  jnz     short loc_18000EAF5
0x18000eaed  mov     rcx, [rcx]; this
0x18000eaf0  test    rcx, rcx
0x18000eaf3  jnz     short loc_18000EAD7
0x18000eaf5  test    rcx, rcx
0x18000eaf8  jz      loc_18000EBA9
0x18000eafe  mov     r8d, r11d
0x18000eb01  cmp     [r13+58h], r11d
0x18000eb05  jz      short loc_18000EB51
0x18000eb07  mov     r14, [rcx]
0x18000eb0a  test    r14, r14
0x18000eb0d  jz      short loc_18000EB54
0x18000eb0f  cmp     [r14+30h], r11d
0x18000eb13  jz      short loc_18000EB26
0x18000eb15  mov     eax, [r14+28h]
0x18000eb19  cmp     [r14+18h], r11
0x18000eb1d  jz      short loc_18000EB21
0x18000eb1f  inc     eax
0x18000eb21  add     eax, 1
0x18000eb24  jnz     short loc_18000EB2E
0x18000eb26  mov     r14, [r14]
0x18000eb29  test    r14, r14
0x18000eb2c  jnz     short loc_18000EB0F
0x18000eb2e  test    r14, r14
0x18000eb31  jz      short loc_18000EB54
0x18000eb33  cmp     [rcx+30h], r11d
0x18000eb37  jz      short loc_18000EB48
0x18000eb39  mov     eax, [rcx+28h]
0x18000eb3c  cmp     [rcx+18h], r11
0x18000eb40  jz      short loc_18000EB44
0x18000eb42  inc     eax
0x18000eb44  inc     eax
0x18000eb46  jmp     short loc_18000EB4B
0x18000eb48  mov     eax, r11d
0x18000eb4b  lea     r8d, [rax+rsi]
0x18000eb4f  jmp     short loc_18000EB54
0x18000eb51  mov     r14, r11
0x18000eb54  cmp     [r12+rdi+8], r11d
0x18000eb59  jnz     short loc_18000EB60
0x18000eb5b  mov     [r12+rdi+8], esi
0x18000eb60  mov     eax, esi
0x18000eb62  lea     r9, [rdi+10h]; unsigned int *
0x18000eb66  mov     [rsp+38h+var_10], r8d; unsigned int
0x18000eb6b  inc     esi
0x18000eb6d  mov     edx, r15d
0x18000eb70  lea     r8, [rbp+arg_0]; unsigned int *
0x18000eb74  add     rdx, rdi; void *
0x18000eb77  mov     [rbp+arg_8], esi
0x18000eb7a  mov     [r9+rax*4], r15d
0x18000eb7e  lea     rax, [rbp+arg_8]
0x18000eb82  mov     [rsp+38h+var_18], rax; unsigned int *
0x18000eb87  call    ?Write@CArticulation@@QEAAJPEAXPEAK11K@Z; CArticulation::Write(void *,ulong *,ulong *,ulong *,ulong)
0x18000eb8c  xor     r11d, r11d
0x18000eb8f  mov     ebx, eax
0x18000eb91  test    eax, eax
0x18000eb93  js      short loc_18000EBB2
0x18000eb95  mov     rcx, r14
0x18000eb98  test    r14, r14
0x18000eb9b  jz      short loc_18000EBC0
0x18000eb9d  mov     esi, [rbp+arg_8]
0x18000eba0  mov     r15d, [rbp+arg_0]
0x18000eba4  jmp     loc_18000EAFE
0x18000eba9  test    ebx, ebx
0x18000ebab  jns     short loc_18000EBC0
0x18000ebad  jmp     short loc_18000EBB2
0x18000ebaf  mov     ebx, r9d
0x18000ebb2  mov     r8d, dword ptr [rbp+Size]; Size
0x18000ebb6  xor     edx, edx; Val
0x18000ebb8  mov     rcx, rdi; void *
0x18000ebbb  call    memset_0
0x18000ebc0  mov     eax, ebx
0x18000ebc2  add     rsp, 38h
0x18000ebc6  pop     r15
0x18000ebc8  pop     r14
0x18000ebca  pop     r13
0x18000ebcc  pop     r12
0x18000ebce  pop     rdi
  ... truncated ...
```
