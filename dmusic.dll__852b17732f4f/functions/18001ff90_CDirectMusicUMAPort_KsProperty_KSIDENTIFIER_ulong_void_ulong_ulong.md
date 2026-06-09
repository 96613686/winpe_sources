# CDirectMusicUMAPort::KsProperty(KSIDENTIFIER *,ulong,void *,ulong,ulong *)

- ea: `0x18001ff90`
- end: `0x18002013f`
- name: `?KsProperty@CDirectMusicUMAPort@@UEAAJPEAUKSIDENTIFIER@@KPEAXKPEAK@Z`
- size: `431`
- prototype: `__int64 __fastcall(CDirectMusicUMAPort *__hidden this, struct KSIDENTIFIER *, unsigned int, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callees

- `0x1800012c4`
- `0x1800012d0`
- `0x18001ff90`
- `0x1800212e4`

## pseudocode

```c
__int64 __fastcall CDirectMusicUMAPort::KsProperty(
        CDirectMusicUMAPort *this,
        struct KSIDENTIFIER *a2,
        unsigned int a3,
        int *a4,
        DWORD a5,
        unsigned int *lpNumberOfBytesTransferred)
{
  __int64 v6; // rsi
  int *v7; // rdi
  DWORD *v10; // r15
  DWORD v12; // r12d
  int v13; // eax
  int v14; // ecx
  int v15; // r14d
  GUID *v16; // rax
  GUID *v17; // rbp
  int v18; // [rsp+A0h] [rbp+18h] BYREF

  v6 = a3;
  v18 = 0;
  v7 = a4;
  if ( a3 && !a2 )
    return 2147500035LL;
  v10 = lpNumberOfBytesTransferred;
  if ( !lpNumberOfBytesTransferred )
    return 2147500035LL;
  if ( !*((_QWORD *)this + 2) )
    return 2289570100LL;
  if ( a3 < 0x18 )
    return 2147942487LL;
  if ( !a4 )
    return 2147500035LL;
  v12 = a5;
  if ( a2->Alignment == *(_QWORD *)&GUID_fedfae25_e46e_11d1_aace_0000f875ac12.Data1
    && *(&a2->Alignment + 1) == *(_QWORD *)GUID_fedfae25_e46e_11d1_aace_0000f875ac12.Data4 )
  {
    if ( !a2->Id )
    {
      if ( a5 == 4 )
      {
        if ( (*((_BYTE *)&a2->Alignment + 20) & 2) != 0 )
        {
          v13 = *a4;
          v14 = -20000;
          v18 = v13;
          if ( v13 < -20000 || (v14 = 2000, v13 > 2000) )
          {
            v18 = v14;
            v7 = &v18;
          }
        }
        goto LABEL_16;
      }
      return 2147942487LL;
    }
    return 2289570082LL;
  }
  if ( a2->Alignment == *(_QWORD *)&GUID_d523fa2c_dee3_11d1_a789_0000f875ac12.Data1
    && *(&a2->Alignment + 1) == *(_QWORD *)GUID_d523fa2c_dee3_11d1_a789_0000f875ac12.Data4 )
  {
    return 2289570082LL;
  }
LABEL_16:
  v15 = SyncIoctl(*((void **)this + 114), 0x2F0003u, a2, a3, v7, a5, lpNumberOfBytesTransferred);
  if ( v15 < 0 )
  {
    v16 = (GUID *)operator new[](v6 + 8);
    v17 = v16;
    if ( !v16 )
      return 2147942414LL;
    *v16 = a2->Set;
    *(_QWORD *)&v16[1].Data1 = *(&a2->Alignment + 2);
    *(_DWORD *)&v16[1].Data2 |= 0x10000000u;
    *(_QWORD *)v16[1].Data4 = 0;
    v15 = SyncIoctl(*((void **)this + 114), 0x2F0003u, v16, (int)v6 + 8, v7, v12, v10);
    operator delete(v17);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001ff90  mov     rax, rsp
0x18001ff93  push    rbx
0x18001ff94  push    rbp
0x18001ff95  push    rsi
0x18001ff96  push    rdi
0x18001ff97  push    r12
0x18001ff99  push    r13
0x18001ff9b  push    r14
0x18001ff9d  push    r15
0x18001ff9f  sub     rsp, 48h
0x18001ffa3  xor     ebp, ebp
0x18001ffa5  mov     esi, r8d
0x18001ffa8  mov     [rax+18h], ebp
0x18001ffab  mov     rdi, r9
0x18001ffae  mov     rbx, rdx
0x18001ffb1  mov     r13, rcx
0x18001ffb4  test    r8d, r8d
0x18001ffb7  jz      short loc_18001FFC2
0x18001ffb9  test    rdx, rdx
0x18001ffbc  jz      loc_180020129
0x18001ffc2  mov     r15, [rsp+88h+arg_28]
0x18001ffca  test    r15, r15
0x18001ffcd  jz      loc_180020129
0x18001ffd3  cmp     [rcx+10h], rbp
0x18001ffd7  jnz     short loc_18001FFE3
0x18001ffd9  mov     eax, 88781134h
0x18001ffde  jmp     loc_18002012E
0x18001ffe3  cmp     esi, 18h
0x18001ffe6  jb      loc_180020122
0x18001ffec  test    r9, r9
0x18001ffef  jz      loc_180020129
0x18001fff5  mov     rax, [rdx]
0x18001fff8  cmp     rax, qword ptr cs:_GUID_fedfae25_e46e_11d1_aace_0000f875ac12.Data1
0x18001ffff  mov     r12d, [rsp+88h+arg_20]
0x180020007  jnz     loc_1800200AE
0x18002000d  mov     rax, [rdx+8]
0x180020011  cmp     rax, qword ptr cs:_GUID_fedfae25_e46e_11d1_aace_0000f875ac12.Data4
0x180020018  jnz     loc_1800200AE
0x18002001e  cmp     [rdx+10h], ebp
0x180020021  jnz     loc_1800200C7
0x180020027  cmp     r12d, 4
0x18002002b  jnz     loc_180020122
0x180020031  test    byte ptr [rdx+14h], 2
0x180020035  jz      short loc_180020062
0x180020037  mov     eax, [r9]
0x18002003a  mov     ecx, 0FFFFB1E0h
0x18002003f  mov     [rsp+88h+arg_10], eax
0x180020046  cmp     eax, ecx
0x180020048  jl      short loc_180020053
0x18002004a  mov     ecx, 7D0h
0x18002004f  cmp     eax, ecx
0x180020051  jle     short loc_180020062
0x180020053  mov     [rsp+88h+arg_10], ecx
0x18002005a  lea     rdi, [rsp+88h+arg_10]
0x180020062  mov     rcx, [r13+390h]; void *
0x180020069  mov     r9d, esi; unsigned int
0x18002006c  mov     [rsp+88h+lpNumberOfBytesTransferred], r15; lpNumberOfBytesTransferred
0x180020071  mov     r8, rbx; void *
0x180020074  mov     [rsp+88h+var_60], r12d; DWORD
0x180020079  mov     edx, 2F0003h; unsigned int
0x18002007e  mov     [rsp+88h+var_68], rdi; void *
0x180020083  call    ?SyncIoctl@@YAJPEAXK0K0KPEAK@Z; SyncIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x180020088  mov     r14d, eax
0x18002008b  test    eax, eax
0x18002008d  jns     loc_18002011D
0x180020093  lea     rcx, [rsi+8]; unsigned __int64
0x180020097  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002009c  mov     rbp, rax
0x18002009f  test    rax, rax
0x1800200a2  jnz     short loc_1800200CE
0x1800200a4  mov     eax, 8007000Eh
0x1800200a9  jmp     loc_18002012E
0x1800200ae  mov     rax, [rdx]
0x1800200b1  cmp     rax, qword ptr cs:_GUID_d523fa2c_dee3_11d1_a789_0000f875ac12.Data1
0x1800200b8  jnz     short loc_180020062
0x1800200ba  mov     rax, [rdx+8]
0x1800200be  cmp     rax, qword ptr cs:_GUID_d523fa2c_dee3_11d1_a789_0000f875ac12.Data4
0x1800200c5  jnz     short loc_180020062
0x1800200c7  mov     eax, 88781122h
0x1800200cc  jmp     short loc_18002012E
0x1800200ce  movups  xmm0, xmmword ptr [rbx]
0x1800200d1  mov     [rsp+88h+lpNumberOfBytesTransferred], r15; lpNumberOfBytesTransferred
0x1800200d6  lea     r9d, [rsi+8]; unsigned int
0x1800200da  mov     [rsp+88h+var_60], r12d; DWORD
0x1800200df  mov     r8, rbp; void *
0x1800200e2  movups  xmmword ptr [rax], xmm0
0x1800200e5  mov     edx, 2F0003h; unsigned int
0x1800200ea  mov     [rsp+88h+var_68], rdi; void *
0x1800200ef  movsd   xmm1, qword ptr [rbx+10h]
0x1800200f4  movsd   qword ptr [rax+10h], xmm1
0x1800200f9  bts     dword ptr [rax+14h], 1Ch
0x1800200fe  mov     qword ptr [rax+18h], 0
0x180020106  mov     rcx, [r13+390h]; void *
0x18002010d  call    ?SyncIoctl@@YAJPEAXK0K0KPEAK@Z; SyncIoctl(void *,ulong,void *,ulong,void *,ulong,ulong *)
0x180020112  mov     rcx, rbp; void *
0x180020115  mov     r14d, eax
0x180020118  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002011d  mov     eax, r14d
0x180020120  jmp     short loc_18002012E
0x180020122  mov     eax, 80070057h
0x180020127  jmp     short loc_18002012E
0x180020129  mov     eax, 80004003h
0x18002012e  add     rsp, 48h
0x180020132  pop     r15
0x180020134  pop     r14
0x180020136  pop     r13
0x180020138  pop     r12
0x18002013a  pop     rdi
0x18002013b  pop     rsi
0x18002013c  pop     rbp
0x18002013d  pop     rbx
0x18002013e  retn
```
