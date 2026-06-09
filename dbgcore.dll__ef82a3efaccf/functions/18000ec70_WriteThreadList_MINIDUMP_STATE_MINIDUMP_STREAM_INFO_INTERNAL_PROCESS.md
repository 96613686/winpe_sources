# WriteThreadList(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *)

- ea: `0x18000ec70`
- end: `0x18000eef3`
- name: `?WriteThreadList@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@@Z`
- size: `643`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, struct _MINIDUMP_STREAM_INFO *, struct _INTERNAL_PROCESS *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000c19c`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x18000bcbc`
- `0x18000dc78`
- `0x18000e660`
- `0x18000e798`
- `0x18000ec70`
- `0x18001951c`
- `0x18001fe48`

## pseudocode

```c
__int64 __fastcall WriteThreadList(
        struct _MINIDUMP_STATE *a1,
        struct _MINIDUMP_STREAM_INFO *a2,
        struct _INTERNAL_PROCESS *a3)
{
  struct _INTERNAL_PROCESS *v4; // r15
  unsigned int v6; // edx
  __int64 result; // rax
  _QWORD *v8; // r13
  _QWORD *v9; // r14
  _QWORD *v10; // rbx
  int v11; // eax
  unsigned int v12; // r12d
  unsigned __int16 *v13; // r8
  int v14; // edx
  int v15; // ecx
  unsigned int v16; // r15d
  struct _VA_RANGE *MemoryBlock; // rax
  unsigned int v18; // edx
  unsigned int v19; // ecx
  int v20; // eax
  unsigned int v21; // ebx
  __int64 v22; // [rsp+48h] [rbp-61h]
  unsigned int v23; // [rsp+60h] [rbp-49h] BYREF
  unsigned int v24; // [rsp+64h] [rbp-45h] BYREF
  int v25; // [rsp+68h] [rbp-41h] BYREF
  struct _INTERNAL_PROCESS *v26; // [rsp+70h] [rbp-39h]
  _DWORD v27[4]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v28; // [rsp+90h] [rbp-19h]
  __int64 v29; // [rsp+98h] [rbp-11h]
  unsigned int v30; // [rsp+A0h] [rbp-9h]
  int v31; // [rsp+A4h] [rbp-5h]
  int v32; // [rsp+A8h] [rbp-1h]
  unsigned int v33; // [rsp+ACh] [rbp+3h]
  __int64 v34; // [rsp+B0h] [rbp+7h]
  int v35; // [rsp+B8h] [rbp+Fh]
  unsigned int v36; // [rsp+BCh] [rbp+13h]

  v26 = a3;
  v24 = 0;
  v4 = a3;
  v23 = 0;
  memset_0(v27, 0, 0x40u);
  v6 = *((_DWORD *)a2 + 11);
  v25 = *((_DWORD *)v4 + 19);
  result = WriteAtOffset(a1, v6, &v25, 4u);
  if ( !(_DWORD)result )
  {
    *((_DWORD *)a2 + 13) += 4;
    v8 = (_QWORD *)((char *)v4 + 104);
    v9 = (_QWORD *)*((_QWORD *)v4 + 13);
    while ( 1 )
    {
      if ( v9 == v8 )
        return 0;
      if ( (unsigned int)GenCheckCancel(a1) )
        break;
      v10 = v9 - 23;
      v9 = (_QWORD *)*v9;
      v11 = *((_DWORD *)v10 + 44);
      if ( (v11 & 1) != 0 )
      {
        if ( (v11 & 4) != 0 )
        {
          result = WriteOther(a1, a2, (void *)v10[14], *((_DWORD *)a1 + 35), &v23);
          if ( (_DWORD)result )
            return result;
          v12 = v23;
        }
        else
        {
          v12 = 0;
          v23 = 0;
        }
        v13 = (unsigned __int16 *)v10[26];
        if ( v13 )
        {
          result = WriteStringToPool(a1, a2, v13, (unsigned int *)v10 + 54);
          if ( (_DWORD)result )
            return result;
        }
        if ( (v10[22] & 8) != 0 && (v14 = *((_DWORD *)v10 + 40)) != 0 )
        {
          if ( (*((_DWORD *)a1 + 14) & 0x100000) != 0 )
            v15 = 0x100000;
          else
            v15 = *((_BYTE *)a1 + 56) & 8;
          result = WriteMemoryFromProcess(a1, a2, (__int64)v4, (void *)v10[19], v14, v15 != 0, v15, 0, 3, v22, &v24);
          if ( (_DWORD)result )
            return result;
          v16 = v24;
        }
        else
        {
          v16 = 0;
          v24 = 0;
        }
        v27[0] = *(_DWORD *)v10;
        v27[1] = *((_DWORD *)v10 + 6);
        v27[2] = *((_DWORD *)v10 + 9);
        v27[3] = *((_DWORD *)v10 + 10);
        v28 = v10[12];
        v29 = v10[17];
        v30 = *((_DWORD *)v10 + 32) - *((_DWORD *)v10 + 34);
        MemoryBlock = GenFindMemoryBlock(a1, v26, v10[17], v30);
        if ( MemoryBlock )
          v31 = *((_DWORD *)MemoryBlock + 3);
        else
          v31 = 0;
        v18 = *((_DWORD *)a2 + 13);
        v19 = *((_DWORD *)a2 + 11) + *((_DWORD *)a2 + 12);
        v34 = v10[19];
        v20 = *((_DWORD *)v10 + 40);
        v21 = *((_DWORD *)a2 + 14);
        v35 = v20;
        v32 = *((_DWORD *)a1 + 35);
        v36 = v16;
        v33 = v12;
        if ( v21 + v18 > v19 )
          return 2147942487LL;
        result = WriteAtOffset(a1, v18, v27, v21);
        if ( (_DWORD)result )
          return result;
        *((_DWORD *)a2 + 13) += v21;
        v4 = v26;
      }
    }
    return 2147943623LL;
  }
  return result;
}

```

## disassembly

```asm
0x18000ec70  mov     [rsp-8+arg_18], rbx
0x18000ec75  push    rbp
0x18000ec76  push    rsi
0x18000ec77  push    rdi
0x18000ec78  push    r12
0x18000ec7a  push    r13
0x18000ec7c  push    r14
0x18000ec7e  push    r15
0x18000ec80  lea     rbp, [rsp-27h]
0x18000ec85  sub     rsp, 0D0h
0x18000ec8c  mov     rax, cs:__security_cookie
0x18000ec93  xor     rax, rsp
0x18000ec96  mov     [rbp+57h+var_40], rax
0x18000ec9a  mov     rdi, rdx
0x18000ec9d  mov     [rbp+57h+var_90], r8
0x18000eca1  xor     edx, edx; Val
0x18000eca3  mov     [rbp+57h+var_9C], 0
0x18000ecaa  mov     r15, r8
0x18000ecad  mov     [rbp+57h+var_A0], 0
0x18000ecb4  mov     rsi, rcx
0x18000ecb7  lea     rcx, [rbp+57h+var_80]; void *
0x18000ecbb  lea     r8d, [rdx+40h]; Size
0x18000ecbf  call    memset_0
0x18000ecc4  mov     eax, [r15+4Ch]
0x18000ecc8  lea     r8, [rbp+57h+var_98]; void *
0x18000eccc  mov     edx, [rdi+2Ch]; unsigned int
0x18000eccf  mov     r9d, 4; unsigned int
0x18000ecd5  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x18000ecd8  mov     [rbp+57h+var_98], eax
0x18000ecdb  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000ece0  test    eax, eax
0x18000ece2  jnz     loc_18000EEBE
0x18000ece8  add     dword ptr [rdi+34h], 4
0x18000ecec  lea     r13, [r15+68h]
0x18000ecf0  mov     r14, [r13+0]
0x18000ecf4  jmp     loc_18000EEB3
0x18000ecf9  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x18000ecfc  call    ?GenCheckCancel@@YAHPEAU_MINIDUMP_STATE@@@Z; GenCheckCancel(_MINIDUMP_STATE *)
0x18000ed01  test    eax, eax
0x18000ed03  jnz     loc_18000EEEC
0x18000ed09  lea     rbx, [r14-0B8h]
0x18000ed10  mov     r14, [r14]
0x18000ed13  mov     eax, [rbx+0B0h]
0x18000ed19  test    al, 1
0x18000ed1b  jz      loc_18000EEB3
0x18000ed21  test    al, 4
0x18000ed23  jz      short loc_18000ED52
0x18000ed25  mov     r9d, [rsi+8Ch]; unsigned int
0x18000ed2c  lea     rax, [rbp+57h+var_A0]
0x18000ed30  mov     r8, [rbx+70h]; void *
0x18000ed34  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000ed37  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x18000ed3a  mov     [rsp+100h+var_E0], rax; unsigned int *
0x18000ed3f  call    ?WriteOther@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAXKPEAK@Z; WriteOther(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,void *,ulong,ulong *)
0x18000ed44  test    eax, eax
0x18000ed46  jnz     loc_18000EEBE
0x18000ed4c  mov     r12d, [rbp+57h+var_A0]
0x18000ed50  jmp     short loc_18000ED59
0x18000ed52  xor     r12d, r12d
0x18000ed55  mov     [rbp+57h+var_A0], r12d
0x18000ed59  mov     r8, [rbx+0D0h]; unsigned __int16 *
0x18000ed60  test    r8, r8
0x18000ed63  jz      short loc_18000ED7F
0x18000ed65  lea     r9, [rbx+0D8h]; unsigned int *
0x18000ed6c  mov     rdx, rdi; struct _MINIDUMP_STREAM_INFO *
0x18000ed6f  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x18000ed72  call    ?WriteStringToPool@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAGPEAK@Z; WriteStringToPool(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,ushort *,ulong *)
0x18000ed77  test    eax, eax
0x18000ed79  jnz     loc_18000EEBE
0x18000ed7f  test    byte ptr [rbx+0B0h], 8
0x18000ed86  jz      short loc_18000EDF7
0x18000ed88  mov     edx, [rbx+0A0h]
0x18000ed8e  test    edx, edx
0x18000ed90  jz      short loc_18000EDF7
0x18000ed92  mov     eax, 100000h
0x18000ed97  test    [rsi+38h], eax
0x18000ed9a  jz      short loc_18000EDA0
0x18000ed9c  mov     ecx, eax
0x18000ed9e  jmp     short loc_18000EDA7
0x18000eda0  movzx   ecx, byte ptr [rsi+38h]
0x18000eda4  and     ecx, 8
0x18000eda7  mov     r9, [rbx+98h]
0x18000edae  lea     r8, [rbp+57h+var_9C]
0x18000edb2  mov     [rsp+100h+var_B0], r8
0x18000edb7  xor     eax, eax
0x18000edb9  mov     [rsp+100h+var_C0], 3
0x18000edc1  test    ecx, ecx
0x18000edc3  mov     [rsp+100h+var_C8], 0
0x18000edcc  mov     r8, r15
0x18000edcf  mov     [rsp+100h+var_D0], ecx
0x18000edd3  setnz   al
0x18000edd6  mov     [rsp+100h+var_D8], eax
0x18000edda  mov     rcx, rsi
0x18000eddd  mov     dword ptr [rsp+100h+var_E0], edx
0x18000ede1  mov     rdx, rdi
0x18000ede4  call    ?WriteMemoryFromProcess@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@_KKW4MEMBLOCK_FILTER_TYPE@@KPEAU_VA_RANGE_REF@@W4MEMBLOCK_TYPE@@EPEAK@Z; WriteMemoryFromProcess(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *,unsigned __int64,ulong,MEMBLOCK_FILTER_TYPE,ulong,_VA_RANGE_REF *,MEMBLOCK_TYPE,uchar,ulong *)
0x18000ede9  test    eax, eax
0x18000edeb  jnz     loc_18000EEBE
0x18000edf1  mov     r15d, [rbp+57h+var_9C]
0x18000edf5  jmp     short loc_18000EDFE
0x18000edf7  xor     r15d, r15d
0x18000edfa  mov     [rbp+57h+var_9C], r15d
0x18000edfe  mov     eax, [rbx]
0x18000ee00  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x18000ee03  mov     rdx, [rbp+57h+var_90]; struct _INTERNAL_PROCESS *
0x18000ee07  mov     [rbp+57h+var_80], eax
0x18000ee0a  mov     eax, [rbx+18h]
0x18000ee0d  mov     [rbp+57h+var_7C], eax
0x18000ee10  mov     eax, [rbx+24h]
0x18000ee13  mov     [rbp+57h+var_78], eax
0x18000ee16  mov     eax, [rbx+28h]
0x18000ee19  mov     [rbp+57h+var_74], eax
0x18000ee1c  mov     rax, [rbx+60h]
0x18000ee20  mov     [rbp+57h+var_70], rax
0x18000ee24  mov     rax, [rbx+88h]
0x18000ee2b  mov     [rbp+57h+var_68], rax
0x18000ee2f  mov     r9d, [rbx+80h]
0x18000ee36  sub     r9d, [rbx+88h]; unsigned int
0x18000ee3d  mov     [rbp+57h+var_60], r9d
0x18000ee41  mov     r8, [rbx+88h]; unsigned __int64
0x18000ee48  call    ?GenFindMemoryBlock@@YAPEAU_VA_RANGE@@PEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@_KK@Z; GenFindMemoryBlock(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,unsigned __int64,ulong)
0x18000ee4d  test    rax, rax
0x18000ee50  jz      short loc_18000EE5A
0x18000ee52  mov     eax, [rax+0Ch]
0x18000ee55  mov     [rbp+57h+var_5C], eax
0x18000ee58  jmp     short loc_18000EE61
0x18000ee5a  mov     [rbp+57h+var_5C], 0
0x18000ee61  mov     rax, [rbx+98h]
0x18000ee68  mov     edx, [rdi+34h]; unsigned int
0x18000ee6b  mov     ecx, [rdi+30h]
0x18000ee6e  add     ecx, [rdi+2Ch]
0x18000ee71  mov     [rbp+57h+var_50], rax
0x18000ee75  mov     eax, [rbx+0A0h]
0x18000ee7b  mov     ebx, [rdi+38h]
0x18000ee7e  mov     [rbp+57h+var_48], eax
0x18000ee81  mov     eax, [rsi+8Ch]
0x18000ee87  mov     [rbp+57h+var_58], eax
0x18000ee8a  lea     eax, [rbx+rdx]
0x18000ee8d  mov     [rbp+57h+var_44], r15d
0x18000ee91  mov     [rbp+57h+var_54], r12d
0x18000ee95  cmp     eax, ecx
0x18000ee97  ja      short loc_18000EEE5
0x18000ee99  mov     r9d, ebx; unsigned int
0x18000ee9c  lea     r8, [rbp+57h+var_80]; void *
0x18000eea0  mov     rcx, rsi; struct _MINIDUMP_STATE *
0x18000eea3  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000eea8  test    eax, eax
0x18000eeaa  jnz     short loc_18000EEBE
0x18000eeac  add     [rdi+34h], ebx
0x18000eeaf  mov     r15, [rbp+57h+var_90]
0x18000eeb3  cmp     r14, r13
0x18000eeb6  jnz     loc_18000ECF9
0x18000eebc  xor     eax, eax
0x18000eebe  mov     rcx, [rbp+57h+var_40]
0x18000eec2  xor     rcx, rsp; StackCookie
0x18000eec5  call    __security_check_cookie
0x18000eeca  mov     rbx, [rsp+100h+arg_18]
0x18000eed2  add     rsp, 0D0h
0x18000eed9  pop     r15
0x18000eedb  pop     r14
0x18000eedd  pop     r13
0x18000eedf  pop     r12
0x18000eee1  pop     rdi
0x18000eee2  pop     rsi
0x18000eee3  pop     rbp
0x18000eee4  retn
0x18000eee5  mov     eax, 80070057h
0x18000eeea  jmp     short loc_18000EEBE
0x18000eeec  mov     eax, 800704C7h
0x18000eef1  jmp     short loc_18000EEBE
```
