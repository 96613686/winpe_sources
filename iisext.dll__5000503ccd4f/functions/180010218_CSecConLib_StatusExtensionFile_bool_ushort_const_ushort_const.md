# CSecConLib::StatusExtensionFile(bool,ushort const *,ushort const *)

- ea: `0x180010218`
- end: `0x1800103a3`
- name: `?StatusExtensionFile@CSecConLib@@AEAAJ_NPEBG1@Z`
- size: `395`
- prototype: `__int64 __fastcall(CSecConLib *this, char, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x180009260`
- `0x1800093c0`

## callees

- `0x180001048`
- `0x18000f02c`
- `0x18001011c`
- `0x180010218`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800102ee`
- `msvcrt!_wcsnicmp` at `0x1800102ee`

## pseudocode

```c
__int64 __fastcall CSecConLib::StatusExtensionFile(
        CSecConLib *this,
        char a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v4; // rsi
  int MultiSZPropVal; // ebx
  unsigned __int16 *v6; // rbx
  void *v7; // rdi
  char v8; // r15
  unsigned __int16 *v9; // r14
  unsigned __int16 *v10; // r12
  unsigned __int16 *v11; // rcx
  __int64 v12; // rbp
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v16; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int16 *v17; // [rsp+38h] [rbp-60h] BYREF
  unsigned __int16 *v18; // [rsp+40h] [rbp-58h]
  void *Block; // [rsp+48h] [rbp-50h]

  v17 = 0;
  v4 = -1;
  v16 = 0;
  do
    ++v4;
  while ( a3[v4] );
  MultiSZPropVal = CSecConLib::GetMultiSZPropVal(this, a4, 0x878u, &v17, &v16);
  if ( MultiSZPropVal >= 0 )
  {
    v6 = v17;
    if ( v17 )
    {
      v7 = v17;
      Block = v17;
      if ( !*v17 )
        goto LABEL_20;
      v8 = 0;
      v9 = v17;
      v10 = v17;
      v11 = &v17[v16 - 1];
      v18 = v11;
      do
      {
        v12 = -1;
        do
          ++v12;
        while ( v9[v12] );
        if ( &v9[(unsigned int)v4 + 2] > v11 )
          break;
        if ( !_wcsnicmp(a3, v9 + 2, (unsigned int)v4) )
        {
          v13 = (unsigned int)(v4 + 2);
          if ( v10[v13] == 44 || !v10[v13] )
          {
            v8 = 1;
            if ( a2 )
              *v6 = 49;
            else
              *v6 = 48;
          }
        }
        v11 = v18;
        v14 = (unsigned int)(v12 + 1);
        v6 = &v9[v14];
        if ( v6 > v18 )
          break;
        v9 += v14;
        v10 = v6;
      }
      while ( *v6 );
      v7 = Block;
      if ( v8 )
        MultiSZPropVal = CSecConLib::SetMultiSZPropVal(this, a4, 0x878u, (unsigned __int16 *)Block, v16);
      else
LABEL_20:
        MultiSZPropVal = -2146646015;
      if ( v7 )
        operator delete(v7);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)MultiSZPropVal;
}

```

## disassembly

```asm
0x180010218  mov     r11, rsp
0x18001021b  mov     [r11+20h], r9
0x18001021f  mov     [r11+18h], r8
0x180010223  mov     [rsp+arg_8], dl
0x180010227  mov     [r11+8], rcx
0x18001022b  push    rbx
0x18001022c  push    rbp
0x18001022d  push    rsi
0x18001022e  push    rdi
0x18001022f  push    r12
0x180010231  push    r13
0x180010233  push    r14
0x180010235  push    r15
0x180010237  sub     rsp, 58h
0x18001023b  xor     r14d, r14d
0x18001023e  mov     r13, r9
0x180010241  mov     [r11-60h], r14
0x180010245  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180010249  mov     [r11-68h], r14d
0x18001024d  mov     rax, rcx
0x180010250  inc     rsi
0x180010253  cmp     [r8+rsi*2], r14w
0x180010258  jnz     short loc_180010250
0x18001025a  lea     rcx, [rsp+98h+var_68]
0x18001025f  mov     r8d, 878h; unsigned int
0x180010265  mov     [rsp+98h+var_78], rcx; unsigned int *
0x18001026a  lea     r9, [rsp+98h+var_60]; unsigned __int16 **
0x18001026f  mov     rcx, rax; this
0x180010272  mov     rdx, r13; unsigned __int16 *
0x180010275  call    ?GetMultiSZPropVal@CSecConLib@@AEAAJPEBGKPEAPEAGPEAK@Z; CSecConLib::GetMultiSZPropVal(ushort const *,ulong,ushort * *,ulong *)
0x18001027a  mov     ebx, eax
0x18001027c  test    eax, eax
0x18001027e  js      loc_180010390
0x180010284  mov     rbx, [rsp+98h+var_60]
0x180010289  test    rbx, rbx
0x18001028c  jz      loc_18001038B
0x180010292  mov     rdi, rbx
0x180010295  mov     [rsp+98h+Block], rbx
0x18001029a  cmp     [rbx], r14w
0x18001029e  jz      loc_180010377
0x1800102a4  mov     eax, [rsp+98h+var_68]
0x1800102a8  mov     r15b, r14b
0x1800102ab  mov     r13, [rsp+98h+String1]
0x1800102b3  dec     rax
0x1800102b6  mov     r14, rbx
0x1800102b9  mov     edi, esi
0x1800102bb  mov     r12, rbx
0x1800102be  xor     edx, edx
0x1800102c0  lea     rcx, [rbx+rax*2]
0x1800102c4  mov     [rsp+98h+var_58], rcx
0x1800102c9  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800102cd  inc     rbp
0x1800102d0  cmp     [r14+rbp*2], dx
0x1800102d5  jnz     short loc_1800102CD
0x1800102d7  lea     rax, [rdi+2]
0x1800102db  lea     rax, [r14+rax*2]
0x1800102df  cmp     rax, rcx
0x1800102e2  ja      short loc_180010340
0x1800102e4  lea     rdx, [r14+4]; String2
0x1800102e8  mov     r8, rdi; MaxCount
0x1800102eb  mov     rcx, r13; String1
0x1800102ee  call    cs:__imp__wcsnicmp
0x1800102f4  xor     edx, edx
0x1800102f6  test    eax, eax
0x1800102f8  jnz     short loc_180010324
0x1800102fa  lea     eax, [rsi+2]
0x1800102fd  cmp     word ptr [r12+rax*2], 2Ch ; ','
0x180010303  jz      short loc_18001030C
0x180010305  cmp     [r12+rax*2], dx
0x18001030a  jnz     short loc_180010324
0x18001030c  mov     r15b, 1
0x18001030f  cmp     [rsp+98h+arg_8], dl
0x180010316  jz      short loc_18001031F
0x180010318  mov     word ptr [rbx], 31h ; '1'
0x18001031d  jmp     short loc_180010324
0x18001031f  mov     word ptr [rbx], 30h ; '0'
0x180010324  mov     rcx, [rsp+98h+var_58]
0x180010329  lea     eax, [rbp+1]
0x18001032c  lea     rbx, [r14+rax*2]
0x180010330  cmp     rbx, rcx
0x180010333  ja      short loc_180010340
0x180010335  mov     r14, rbx
0x180010338  mov     r12, rbx
0x18001033b  cmp     [rbx], dx
0x18001033e  jnz     short loc_1800102C9
0x180010340  mov     rdi, [rsp+98h+Block]
0x180010345  mov     r13, [rsp+98h+arg_18]
0x18001034d  test    r15b, r15b
0x180010350  jz      short loc_180010377
0x180010352  mov     eax, [rsp+98h+var_68]
0x180010356  mov     r9, rdi; unsigned __int16 *
0x180010359  mov     rcx, [rsp+98h+arg_0]; this
0x180010361  mov     r8d, 878h; unsigned int
0x180010367  mov     rdx, r13; unsigned __int16 *
0x18001036a  mov     dword ptr [rsp+98h+var_78], eax; unsigned int
0x18001036e  call    ?SetMultiSZPropVal@CSecConLib@@AEAAJPEBGKPEAGK@Z; CSecConLib::SetMultiSZPropVal(ushort const *,ulong,ushort *,ulong)
0x180010373  mov     ebx, eax
0x180010375  jmp     short loc_18001037C
0x180010377  mov     ebx, 800CC801h
0x18001037c  test    rdi, rdi
0x18001037f  jz      short loc_180010390
0x180010381  mov     rcx, rdi; Block
0x180010384  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010389  jmp     short loc_180010390
0x18001038b  mov     ebx, 8007000Eh
0x180010390  mov     eax, ebx
0x180010392  add     rsp, 58h
0x180010396  pop     r15
0x180010398  pop     r14
0x18001039a  pop     r13
0x18001039c  pop     r12
0x18001039e  pop     rdi
0x18001039f  pop     rsi
0x1800103a0  pop     rbp
0x1800103a1  pop     rbx
0x1800103a2  retn
```
