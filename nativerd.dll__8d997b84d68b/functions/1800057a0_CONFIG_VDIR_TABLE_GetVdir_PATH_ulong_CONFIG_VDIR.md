# CONFIG_VDIR_TABLE::GetVdir(PATH *,ulong,CONFIG_VDIR * *)

- ea: `0x1800057a0`
- end: `0x180005a25`
- name: `?GetVdir@CONFIG_VDIR_TABLE@@QEAAJPEAVPATH@@KPEAPEAVCONFIG_VDIR@@@Z`
- size: `645`
- prototype: `__int64 __fastcall(CONFIG_VDIR_TABLE *__hidden this, struct PATH *, unsigned int, struct CONFIG_VDIR **)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003970`
- `0x180004a70`
- `0x180005b80`
- `0x180006a20`
- `0x180008d00`

## callees

- `0x1800057a0`

## import_xrefs

- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x1800059b4`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x1800059b4`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180005996`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180005996`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005a1a`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005a1a`

## pseudocode

```c
__int64 __fastcall CONFIG_VDIR_TABLE::GetVdir(
        CONFIG_VDIR_TABLE *this,
        struct PATH *a2,
        unsigned int a3,
        struct CONFIG_VDIR **a4)
{
  unsigned int v4; // eax
  unsigned int v6; // ebx
  _QWORD *v8; // r9
  const unsigned __int16 *v9; // r8
  unsigned __int16 v10; // ax
  __int64 v11; // r9
  struct CONFIG_VDIR *v12; // r14
  CReaderWriterLock3 *v13; // r15
  int v14; // ebp
  __int64 *v15; // rsi
  int v16; // edi
  __int64 v17; // rdx
  char *v19; // [rsp+20h] [rbp-58h]
  char v20; // [rsp+28h] [rbp-50h] BYREF
  const unsigned __int16 *v21; // [rsp+88h] [rbp+10h]

  v4 = *((_DWORD *)a2 + 6);
  v6 = 0;
  if ( a3 >= v4 )
  {
    v16 = -2147024809;
    goto LABEL_32;
  }
  if ( *((_DWORD *)a2 + 7) != -1 || v4 == -1 )
  {
    v16 = -2147024846;
LABEL_32:
    v8 = (_QWORD *)((char *)a2 + 8);
    goto LABEL_26;
  }
  v8 = (_QWORD *)((char *)a2 + 8);
  *(_WORD *)(*((_QWORD *)a2 + 1) + 2LL * *(unsigned int *)(*(_QWORD *)a2 + 8LL * a3)) = 0;
  *((_DWORD *)a2 + 7) = a3;
  v9 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
  v21 = v9;
  if ( v9 )
  {
    v10 = *v9;
    v19 = (char *)a2 + 8;
    if ( *v9 )
    {
      v11 = *((_QWORD *)a2 + 1);
      do
      {
        if ( (v10 & 0xFF80) != 0 )
        {
          if ( LOWORD((&mapping_values)[64
                                      * (unsigned __int64)*((unsigned __int8 *)&mapping_indexes
                                                          + ((unsigned __int64)v10 >> 8))
                                      + (unsigned __int8)v10]) )
            v10 = (unsigned __int16)(&mapping_values)[64
                                                    * (unsigned __int64)*((unsigned __int8 *)&mapping_indexes
                                                                        + ((unsigned __int64)v10 >> 8))
                                                    + (unsigned __int8)v10];
          v6 = 65599 * v6 + v10;
        }
        else
        {
          v6 = (v10 & 0xDF) + 65599 * v6;
        }
        v10 = *(_WORD *)(v11 + 2);
        v11 += 2;
      }
      while ( v10 );
    }
    v12 = 0;
    v13 = (CONFIG_VDIR_TABLE *)((char *)this + 144);
    if ( *((_DWORD *)this + 39) )
    {
      v14 = 0;
    }
    else
    {
      CReaderWriterLock3::ReadLock((CONFIG_VDIR_TABLE *)((char *)this + 144));
      v9 = v21;
      v14 = 1;
    }
    v15 = *(__int64 **)(*((_QWORD *)this + 15) + 8LL * (v6 % *((_DWORD *)this + 34)));
    while ( 1 )
    {
      if ( !v15 )
      {
LABEL_19:
        v16 = -2147024893;
        goto LABEL_20;
      }
      if ( &v20 == (char *)(v15 + 1) )
      {
        v16 = 0;
LABEL_34:
        v12 = (struct CONFIG_VDIR *)v15[4];
        goto LABEL_20;
      }
      if ( *((_DWORD *)v15 + 7) )
        break;
      v16 = 0;
      if ( v6 == *((_DWORD *)v15 + 6) && IsStringEqualOrdinalIgnoreCase(v9, (const unsigned __int16 *)v15[1]) )
        goto LABEL_34;
      if ( *((_DWORD *)v15 + 6) > v6 )
        goto LABEL_19;
      v15 = (__int64 *)*v15;
      v9 = v21;
    }
    v16 = -2147024846;
LABEL_20:
    if ( v14 )
      CReaderWriterLock3::ReadUnlock(v13);
    if ( v16 == -2147024893 )
    {
      v16 = 0;
    }
    else if ( v16 < 0 )
    {
      goto LABEL_25;
    }
    *a4 = v12;
LABEL_25:
    v8 = v19;
    goto LABEL_26;
  }
  v16 = -2147024809;
LABEL_26:
  v17 = *((unsigned int *)a2 + 7);
  if ( (_DWORD)v17 != -1 )
  {
    if ( (_DWORD)v17 != *((_DWORD *)a2 + 6) - 1 )
      *(_WORD *)(*v8 + 2LL * *(unsigned int *)(*(_QWORD *)a2 + 8 * v17)) = 47;
    *((_DWORD *)a2 + 7) = -1;
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800057a0  mov     r11, rsp
0x1800057a3  mov     [r11+20h], r9
0x1800057a7  push    rdi
0x1800057a8  push    r12
0x1800057aa  push    r13
0x1800057ac  sub     rsp, 60h
0x1800057b0  mov     eax, [rdx+18h]
0x1800057b3  mov     r12, rdx
0x1800057b6  mov     [r11+8], rbx
0x1800057ba  xor     ebx, ebx
0x1800057bc  mov     [r11-28h], rsi
0x1800057c0  mov     rsi, rcx
0x1800057c3  mov     [r11-30h], r14
0x1800057c7  cmp     r8d, eax
0x1800057ca  jnb     loc_1800059C4
0x1800057d0  cmp     dword ptr [rdx+1Ch], 0FFFFFFFFh
0x1800057d4  jnz     loc_180005969
0x1800057da  cmp     eax, 0FFFFFFFFh
0x1800057dd  jz      loc_180005969
0x1800057e3  mov     rax, [rdx]
0x1800057e6  lea     r9, [rdx+8]
0x1800057ea  mov     ecx, r8d
0x1800057ed  mov     edx, [rax+rcx*8]
0x1800057f0  xor     eax, eax
0x1800057f2  mov     rcx, [r9]
0x1800057f5  mov     [rcx+rdx*2], ax
0x1800057f9  mov     [r12+1Ch], r8d
0x1800057fe  mov     r8, [r9]
0x180005801  mov     [rsp+78h+arg_8], r8
0x180005809  test    r8, r8
0x18000580c  jz      loc_1800059CB
0x180005812  movzx   eax, word ptr [r8]
0x180005816  mov     [r11-20h], rbp
0x18000581a  mov     [r11-38h], r15
0x18000581e  mov     [rsp+78h+var_58], r9
0x180005823  test    ax, ax
0x180005826  jz      short loc_18000586D
0x180005828  mov     r9, r8
0x18000582b  lea     r11, __ImageBase
0x180005832  mov     r10d, 0FF80h
0x180005838  nop     dword ptr [rax+rax+00000000h]
0x180005840  test    r10w, ax
0x180005844  jnz     loc_1800059D5
0x18000584a  imul    ebx, 1003Fh
0x180005850  and     eax, 0DFh
0x180005855  add     ebx, eax
0x180005857  movzx   eax, word ptr [r9+2]
0x18000585c  add     r9, 2
0x180005860  test    ax, ax
0x180005863  jnz     short loc_180005840
0x180005865  mov     r8, [rsp+78h+arg_8]
0x18000586d  xor     r14d, r14d
0x180005870  lea     r15, [rsi+90h]
0x180005877  cmp     [rsi+9Ch], r14d
0x18000587e  jz      loc_180005993
0x180005884  xor     ebp, ebp
0x180005886  xor     edx, edx
0x180005888  mov     eax, ebx
0x18000588a  xor     edi, edi
0x18000588c  div     dword ptr [rsi+88h]
0x180005892  mov     rax, [rsi+78h]
0x180005896  mov     rsi, [rax+rdx*8]
0x18000589a  nop     word ptr [rax+rax+00h]
0x1800058a0  test    rsi, rsi
0x1800058a3  jz      short loc_1800058DE
0x1800058a5  lea     rdx, [rsi+8]
0x1800058a9  lea     rax, [rsp+78h+var_50]
0x1800058ae  cmp     rax, rdx
0x1800058b1  jz      loc_180005974
0x1800058b7  cmp     [rdx+14h], r14d
0x1800058bb  jnz     loc_18000597F
0x1800058c1  xor     edi, edi
0x1800058c3  cmp     ebx, [rdx+10h]
0x1800058c6  jz      loc_1800059AE
0x1800058cc  cmp     [rsi+18h], ebx
0x1800058cf  ja      short loc_1800058DE
0x1800058d1  mov     rsi, [rsi]
0x1800058d4  mov     r8, [rsp+78h+arg_8]
0x1800058dc  jmp     short loc_1800058A0
0x1800058de  test    edi, edi
0x1800058e0  jnz     loc_180005A12
0x1800058e6  mov     edi, 80070003h
0x1800058eb  test    ebp, ebp
0x1800058ed  mov     rbp, [rsp+78h+var_20]
0x1800058f2  jnz     loc_180005A17
0x1800058f8  mov     r15, [rsp+78h+var_38]
0x1800058fd  cmp     edi, 80070003h
0x180005903  jnz     loc_180005989
0x180005909  xor     edi, edi
0x18000590b  mov     rax, [rsp+78h+arg_18]
0x180005913  mov     [rax], r14
0x180005916  mov     r9, [rsp+78h+var_58]
0x18000591b  mov     edx, [r12+1Ch]
0x180005920  mov     r14, [rsp+78h+var_30]
0x180005925  mov     rsi, [rsp+78h+var_28]
0x18000592a  mov     rbx, [rsp+78h+arg_0]
0x180005932  cmp     edx, 0FFFFFFFFh
0x180005935  jz      short loc_18000595D
0x180005937  mov     ecx, [r12+18h]
0x18000593c  dec     ecx
0x18000593e  cmp     edx, ecx
0x180005940  jz      short loc_180005954
0x180005942  mov     rcx, [r12]
0x180005946  mov     r8d, [rcx+rdx*8]
0x18000594a  mov     rcx, [r9]
0x18000594d  mov     word ptr [rcx+r8*2], 2Fh ; '/'
0x180005954  mov     dword ptr [r12+1Ch], 0FFFFFFFFh
0x18000595d  mov     eax, edi
0x18000595f  add     rsp, 60h
0x180005963  pop     r13
0x180005965  pop     r12
0x180005967  pop     rdi
0x180005968  retn
0x180005969  mov     edi, 80070032h
0x18000596e  lea     r9, [rdx+8]
0x180005972  jmp     short loc_18000591B
0x180005974  xor     edi, edi
0x180005976  mov     r14, [rsi+20h]
0x18000597a  jmp     loc_1800058EB
0x18000597f  mov     edi, 80070032h
0x180005984  jmp     loc_1800058EB
0x180005989  test    edi, edi
0x18000598b  jns     loc_18000590B
0x180005991  jmp     short loc_180005916
0x180005993  mov     rcx, r15
0x180005996  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000599c  mov     r8, [rsp+78h+arg_8]
0x1800059a4  mov     ebp, 1
0x1800059a9  jmp     loc_180005886
0x1800059ae  mov     rdx, [rdx]
0x1800059b1  mov     rcx, r8
0x1800059b4  call    cs:__imp_?IsStringEqualOrdinalIgnoreCase@@YA_NPEBG0@Z; IsStringEqualOrdinalIgnoreCase(ushort const *,ushort const *)
0x1800059ba  test    al, al
0x1800059bc  jz      loc_1800058CC
0x1800059c2  jmp     short loc_180005976
0x1800059c4  mov     edi, 80070057h
0x1800059c9  jmp     short loc_18000596E
0x1800059cb  mov     edi, 80070057h
0x1800059d0  jmp     loc_18000591B
0x1800059d5  movzx   edx, ax
0x1800059d8  mov     ecx, edx
0x1800059da  shr     rcx, 8
0x1800059de  movzx   r8d, byte ptr [rcx+r11+65250h]
0x1800059e7  movzx   ecx, dl
0x1800059ea  shl     r8, 8
0x1800059ee  add     r8, rcx
0x1800059f1  movzx   ecx, ds:rva ?mapping_values@@3QAY0BAA@$$CBGA[r11+r8*2]; ushort const (near * mapping_values)[256] ...
0x1800059fa  test    cx, cx
0x1800059fd  cmovnz  ax, cx
0x180005a01  movzx   ecx, ax
0x180005a04  imul    eax, ebx, 1003Fh
0x180005a0a  lea     ebx, [rax+rcx]
0x180005a0d  jmp     loc_180005857
0x180005a12  jmp     loc_1800058EB
0x180005a17  mov     rcx, r15
0x180005a1a  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180005a20  jmp     loc_1800058F8
```
