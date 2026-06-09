# CSecConLib::DeleteExtensionFileRecord(ushort const *,ushort const *)

- ea: `0x18000ec68`
- end: `0x18000ee38`
- name: `?DeleteExtensionFileRecord@CSecConLib@@QEAAJPEBG0@Z`
- size: `464`
- prototype: `__int64 __fastcall(CSecConLib *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x180009200`

## callees

- `0x180001048`
- `0x180001054`
- `0x18000ec68`
- `0x18000f02c`
- `0x18000f1c0`
- `0x18001011c`
- `0x1800111a2`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000ed67`
- `msvcrt!_wcsnicmp` at `0x18000ed67`
- `msvcrt!wcscpy_s` at `0x18000ed9c`
- `msvcrt!wcscpy_s` at `0x18000ed9c`

## pseudocode

```c
__int64 __fastcall CSecConLib::DeleteExtensionFileRecord(
        CSecConLib *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v4; // rsi
  int inited; // ebx
  __int64 v7; // r14
  wchar_t *v8; // rax
  const wchar_t *v9; // rbx
  unsigned int v10; // r14d
  wchar_t *v11; // r12
  __int64 v12; // r15
  char v13; // bp
  size_t v14; // rcx
  __int64 v15; // rax
  __int64 v16; // r13
  int v17; // eax
  unsigned int v19; // [rsp+30h] [rbp-58h] BYREF
  void *Src; // [rsp+38h] [rbp-50h] BYREF
  size_t v21; // [rsp+40h] [rbp-48h]
  void *Block; // [rsp+48h] [rbp-40h]

  Src = 0;
  v4 = -1;
  v19 = 0;
  do
    ++v4;
  while ( a2[v4] );
  inited = CSecConLib::InternalInitIfNecessary(this);
  if ( inited >= 0 )
  {
    inited = CSecConLib::GetMultiSZPropVal(this, a3, 0x878u, (unsigned __int16 **)&Src, &v19);
    if ( inited >= 0 )
    {
      v7 = v19;
      v8 = (wchar_t *)operator new[](saturated_mul(v19, 2u));
      v9 = v8;
      if ( v8 )
      {
        Block = v8;
        memcpy_0(v8, Src, 2 * v7);
        v10 = 1;
        v11 = (wchar_t *)Src;
        if ( !*v9 )
          goto LABEL_22;
        v12 = v19;
        v13 = 0;
        v14 = (unsigned int)v4;
        v21 = (unsigned int)v4;
        do
        {
          v15 = -1;
          do
            ++v15;
          while ( v9[v15] );
          v16 = (unsigned int)(v15 + 1);
          if ( _wcsnicmp(a2, v9 + 2, v14) || v9[(unsigned int)(v4 + 2)] != 44 )
          {
            if ( v11 )
            {
              wcscpy_s(v11, v12 - (((char *)v11 - (_BYTE *)Src) >> 1), v9);
              v11 += v16;
              *v11 = 0;
              v10 += v16;
            }
          }
          else
          {
            v13 = 1;
          }
          v14 = v21;
          v9 += v16;
        }
        while ( *v9 );
        if ( v13 )
        {
          if ( v10 >= 3 )
            v17 = CSecConLib::SetMultiSZPropVal(this, a3, 0x878u, (unsigned __int16 *)Src, v10);
          else
            v17 = CSecConLib::SetMultiSZPropVal(this, a3, 0x878u, 0, 0);
          inited = v17;
        }
        else
        {
LABEL_22:
          inited = -2146646015;
        }
        operator delete(Block);
      }
      else
      {
        inited = -2147024882;
      }
    }
    if ( Src )
      operator delete(Src);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000ec68  mov     rax, rsp
0x18000ec6b  mov     [rax+18h], r8
0x18000ec6f  mov     [rax+10h], rdx
0x18000ec73  mov     [rax+8], rcx
0x18000ec77  push    rbx
0x18000ec78  push    rbp
0x18000ec79  push    rsi
0x18000ec7a  push    r12
0x18000ec7c  push    r13
0x18000ec7e  push    r14
0x18000ec80  push    r15
0x18000ec82  sub     rsp, 50h
0x18000ec86  xor     r13d, r13d
0x18000ec89  mov     r15, r8
0x18000ec8c  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000ec90  mov     [rax-50h], r13
0x18000ec94  mov     rsi, r12
0x18000ec97  mov     [rax-58h], r13d
0x18000ec9b  mov     rbp, rcx
0x18000ec9e  inc     rsi
0x18000eca1  cmp     [rdx+rsi*2], r13w
0x18000eca6  jnz     short loc_18000EC9E
0x18000eca8  call    ?InternalInitIfNecessary@CSecConLib@@AEAAJXZ; CSecConLib::InternalInitIfNecessary(void)
0x18000ecad  mov     ebx, eax
0x18000ecaf  test    eax, eax
0x18000ecb1  js      loc_18000EE26
0x18000ecb7  lea     rax, [rsp+88h+var_58]
0x18000ecbc  mov     r8d, 878h; unsigned int
0x18000ecc2  lea     r9, [rsp+88h+Src]; unsigned __int16 **
0x18000ecc7  mov     [rsp+88h+var_68], rax; unsigned int *
0x18000eccc  mov     rdx, r15; unsigned __int16 *
0x18000eccf  mov     rcx, rbp; this
0x18000ecd2  call    ?GetMultiSZPropVal@CSecConLib@@AEAAJPEBGKPEAPEAGPEAK@Z; CSecConLib::GetMultiSZPropVal(ushort const *,ulong,ushort * *,ulong *)
0x18000ecd7  mov     ebx, eax
0x18000ecd9  test    eax, eax
0x18000ecdb  js      loc_18000EE15
0x18000ece1  mov     r14d, [rsp+88h+var_58]
0x18000ece6  mov     eax, 2
0x18000eceb  mul     r14
0x18000ecee  cmovb   rax, r12
0x18000ecf2  mov     rcx, rax; unsigned __int64
0x18000ecf5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ecfa  mov     rbx, rax
0x18000ecfd  test    rax, rax
0x18000ed00  jnz     short loc_18000ED0C
0x18000ed02  mov     ebx, 8007000Eh
0x18000ed07  jmp     loc_18000EE15
0x18000ed0c  mov     rdx, [rsp+88h+Src]; Src
0x18000ed11  lea     r8, [r14+r14]; Size
0x18000ed15  mov     rcx, rbx; void *
0x18000ed18  mov     [rsp+88h+Block], rbx
0x18000ed1d  call    memcpy_0
0x18000ed22  mov     r14d, 1
0x18000ed28  mov     r12, [rsp+88h+Src]
0x18000ed2d  cmp     [rbx], r13w
0x18000ed31  jz      loc_18000EE06
0x18000ed37  mov     r15d, [rsp+88h+var_58]
0x18000ed3c  mov     bpl, r13b
0x18000ed3f  mov     ecx, esi
0x18000ed41  mov     [rsp+88h+var_48], rcx
0x18000ed46  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ed4a  inc     rax
0x18000ed4d  cmp     [rbx+rax*2], r13w
0x18000ed52  jnz     short loc_18000ED4A
0x18000ed54  mov     r8, rcx; MaxCount
0x18000ed57  lea     rdx, [rbx+4]; String2
0x18000ed5b  mov     rcx, [rsp+88h+String1]; String1
0x18000ed63  lea     r13d, [rax+1]
0x18000ed67  call    cs:__imp__wcsnicmp
0x18000ed6d  test    eax, eax
0x18000ed6f  jnz     short loc_18000ED80
0x18000ed71  lea     eax, [rsi+2]
0x18000ed74  cmp     word ptr [rbx+rax*2], 2Ch ; ','
0x18000ed79  jnz     short loc_18000ED80
0x18000ed7b  mov     bpl, 1
0x18000ed7e  jmp     short loc_18000EDB0
0x18000ed80  test    r12, r12
0x18000ed83  jz      short loc_18000EDB0
0x18000ed85  mov     rax, r12
0x18000ed88  mov     rdx, r15
0x18000ed8b  sub     rax, [rsp+88h+Src]
0x18000ed90  mov     r8, rbx; Source
0x18000ed93  sar     rax, 1
0x18000ed96  mov     rcx, r12; Destination
0x18000ed99  sub     rdx, rax; SizeInWords
0x18000ed9c  call    cs:__imp_wcscpy_s
0x18000eda2  xor     eax, eax
0x18000eda4  lea     r12, [r12+r13*2]
0x18000eda8  mov     [r12], ax
0x18000edad  add     r14d, r13d
0x18000edb0  mov     rcx, [rsp+88h+var_48]
0x18000edb5  lea     rbx, [rbx+r13*2]
0x18000edb9  xor     r13d, r13d
0x18000edbc  cmp     [rbx], r13w
0x18000edc0  jnz     short loc_18000ED46
0x18000edc2  mov     r15, [rsp+88h+arg_10]
0x18000edca  test    bpl, bpl
0x18000edcd  mov     rbp, [rsp+88h+arg_0]
0x18000edd5  jz      short loc_18000EE06
0x18000edd7  mov     r8d, 878h; unsigned int
0x18000eddd  mov     rdx, r15; unsigned __int16 *
0x18000ede0  mov     rcx, rbp; this
0x18000ede3  cmp     r14d, 3
0x18000ede7  jnb     short loc_18000EDFA
0x18000ede9  mov     dword ptr [rsp+88h+var_68], r13d; unsigned int
0x18000edee  xor     r9d, r9d; unsigned __int16 *
0x18000edf1  call    ?SetMultiSZPropVal@CSecConLib@@AEAAJPEBGKPEAGK@Z; CSecConLib::SetMultiSZPropVal(ushort const *,ulong,ushort *,ulong)
0x18000edf6  mov     ebx, eax
0x18000edf8  jmp     short loc_18000EE0B
0x18000edfa  mov     r9, [rsp+88h+Src]
0x18000edff  mov     dword ptr [rsp+88h+var_68], r14d
0x18000ee04  jmp     short loc_18000EDF1
0x18000ee06  mov     ebx, 800CC801h
0x18000ee0b  mov     rcx, [rsp+88h+Block]; Block
0x18000ee10  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ee15  cmp     [rsp+88h+Src], r13
0x18000ee1a  jz      short loc_18000EE26
0x18000ee1c  mov     rcx, [rsp+88h+Src]; Block
0x18000ee21  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ee26  mov     eax, ebx
0x18000ee28  add     rsp, 50h
0x18000ee2c  pop     r15
0x18000ee2e  pop     r14
0x18000ee30  pop     r13
0x18000ee32  pop     r12
0x18000ee34  pop     rsi
0x18000ee35  pop     rbp
0x18000ee36  pop     rbx
0x18000ee37  retn
```
