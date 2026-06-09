# WriteMemoryFromProcess(_MINIDUMP_STATE *,_MINIDUMP_STREAM_INFO *,_INTERNAL_PROCESS *,unsigned __int64,ulong,MEMBLOCK_FILTER_TYPE,ulong,_VA_RANGE_REF *,MEMBLOCK_TYPE,uchar,ulong *)

- ea: `0x18000dc78`
- end: `0x18000df2b`
- name: `?WriteMemoryFromProcess@@YAJPEAU_MINIDUMP_STATE@@PEAU_MINIDUMP_STREAM_INFO@@PEAU_INTERNAL_PROCESS@@_KKW4MEMBLOCK_FILTER_TYPE@@KPEAU_VA_RANGE_REF@@W4MEMBLOCK_TYPE@@EPEAK@Z`
- size: `691`
- prototype: `__int64 __fastcall(struct _MINIDUMP_STATE *, _DWORD *, __int64, void *, int, int, int, __int64, int, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18000d608`
- `0x18000ec70`

## callees

- `0x180001710`
- `0x180003424`
- `0x18000a020`
- `0x18000bcbc`
- `0x18000dc78`
- `0x1800197d4`
- `0x18002c010`

## string_xrefs

- `0x18000dea6`: `WriteMemoryFromProcess.Read(0x%I64x, 0x%x) failed, 0x%08x`

## pseudocode

```c
__int64 __fastcall WriteMemoryFromProcess(
        struct _MINIDUMP_STATE *a1,
        _DWORD *a2,
        __int64 a3,
        void *a4,
        int a5,
        int a6,
        int a7,
        __int64 a8,
        int a9,
        __int64 a10,
        unsigned int *a11)
{
  unsigned int v12; // edx
  unsigned __int64 v14; // rsi
  unsigned int v16; // r15d
  int v17; // r14d
  __int64 result; // rax
  unsigned int v19; // r12d
  void *v20; // rdx
  unsigned int v21; // ebp
  unsigned int v22; // eax
  unsigned int v23; // edi
  __int64 *v24; // rdi
  unsigned __int64 v25; // r12
  unsigned __int64 v26; // rcx
  __int64 v27; // rax
  unsigned __int64 v28; // rdx
  unsigned int v29; // r9d
  unsigned int v30; // ecx
  __int64 v31; // [rsp+20h] [rbp-A8h]
  __int64 v32; // [rsp+28h] [rbp-A0h]
  unsigned int v33; // [rsp+50h] [rbp-78h]
  void *v35; // [rsp+68h] [rbp-60h] BYREF
  int v36; // [rsp+70h] [rbp-58h]
  unsigned int v37; // [rsp+74h] [rbp-54h]

  v12 = a2[28];
  v14 = (unsigned __int64)a4;
  if ( v12 + 16 > a2[27] + a2[26] )
    return 2147942487LL;
  v16 = a2[31];
  v17 = a5;
  if ( v16 + a5 > a2[29] + a2[30] )
    return 2147942487LL;
  v35 = a4;
  v36 = a5;
  v37 = v16;
  result = WriteAtOffset(a1, v12, &v35, 0x10u);
  if ( !(_DWORD)result )
  {
    a2[28] += 16;
    a2[31] += a5;
    if ( a11 )
      *a11 = v16;
    v33 = a5;
    v19 = a5;
    if ( a5 )
    {
      v20 = (void *)(a3 + 7608);
      v35 = (void *)(a3 + 7608);
      while ( 1 )
      {
        v21 = v19;
        if ( v19 > 0x10000 )
          v21 = 0x10000;
        v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int64, void *, unsigned int))(**((_QWORD **)a1 + 2)
                                                                                                + 240LL))(
                *((_QWORD *)a1 + 2),
                *(_QWORD *)a1,
                v14,
                v20,
                v21);
        v23 = v22;
        if ( v22 )
          break;
        if ( (a7 & 0x100008) != 0 )
          ScanMemoryForModuleRefs(a1, a3, 0, v14, v21, v35, a9, a6, a7, a8);
        v24 = *(__int64 **)(a3 + 73184);
        if ( v24 )
        {
          v25 = v14 + v21;
          while ( 1 )
          {
            v26 = v24[2];
            if ( v25 < v26 )
            {
LABEL_27:
              v17 = a5;
              v19 = v33;
              goto LABEL_28;
            }
            v27 = *((unsigned int *)v24 + 6);
            v28 = v27 + v26;
            if ( v14 <= v26 )
              break;
            if ( v28 >= v14 )
            {
              v29 = 0;
              v30 = v14 - *((_DWORD *)v24 + 4);
              if ( v28 < v25 )
                LODWORD(v27) = v27 - v30;
              else
                LODWORD(v27) = v21;
LABEL_24:
              if ( (_DWORD)v27 )
                memcpy_0((void *)(a3 + v29 + 7608LL), (const void *)(v24[1] + v30), (unsigned int)v27);
            }
            v24 = (__int64 *)*v24;
            if ( !v24 )
              goto LABEL_27;
          }
          v29 = v26 - v14;
          if ( v28 > v25 )
            LODWORD(v27) = v21 - v29;
          v30 = 0;
          goto LABEL_24;
        }
LABEL_28:
        result = WriteAtOffset(a1, v16, v35, v21);
        if ( (_DWORD)result )
          return result;
        v20 = v35;
        v16 += v21;
        v14 += v21;
        v19 -= v21;
        v33 = v19;
        if ( !v19 )
          return 0;
      }
      LODWORD(v32) = v22;
      LODWORD(v31) = v21;
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)a1 + 5) + 8LL))(
        *((_QWORD *)a1 + 5),
        4,
        "WriteMemoryFromProcess.Read(0x%I64x, 0x%x) failed, 0x%08x",
        v14,
        v31,
        v32);
      if ( (unsigned int)(a9 - 2) > 1 && (unsigned int)GenExecuteReadMemoryFailureCallback(a1, v14, v21, v23) )
      {
        v23 = 1;
        a2[28] -= 16;
        a2[27] -= 16;
        a2[31] -= v17;
      }
      return v23;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000dc78  mov     r11, rsp
0x18000dc7b  push    rbx
0x18000dc7c  push    rbp
0x18000dc7d  push    rsi
0x18000dc7e  push    rdi
0x18000dc7f  push    r12
0x18000dc81  push    r13
0x18000dc83  push    r14
0x18000dc85  push    r15
0x18000dc87  sub     rsp, 88h
0x18000dc8e  mov     rax, cs:__security_cookie
0x18000dc95  xor     rax, rsp
0x18000dc98  mov     [rsp+0C8h+var_50], rax
0x18000dc9d  mov     rax, [rsp+0C8h+arg_38]
0x18000dca5  mov     rbx, rdx
0x18000dca8  mov     edx, [rdx+70h]; unsigned int
0x18000dcab  mov     r13, rcx
0x18000dcae  mov     rdi, [rsp+0C8h+arg_50]
0x18000dcb6  mov     rsi, r9
0x18000dcb9  mov     [rsp+0C8h+var_68], rax
0x18000dcbe  mov     rbp, r8
0x18000dcc1  mov     ecx, [rbx+68h]
0x18000dcc4  add     ecx, [rbx+6Ch]
0x18000dcc7  lea     eax, [rdx+10h]
0x18000dcca  mov     [rsp+0C8h+var_70], r8
0x18000dccf  cmp     eax, ecx
0x18000dcd1  ja      loc_18000DF05
0x18000dcd7  mov     r15d, [rbx+7Ch]
0x18000dcdb  mov     r14d, [rsp+0C8h+arg_20]
0x18000dce3  mov     ecx, [rbx+78h]
0x18000dce6  add     ecx, [rbx+74h]
0x18000dce9  lea     eax, [r15+r14]
0x18000dced  cmp     eax, ecx
0x18000dcef  ja      loc_18000DF05
0x18000dcf5  mov     [r11-60h], r9
0x18000dcf9  lea     r8, [r11-60h]; void *
0x18000dcfd  mov     r9d, 10h; unsigned int
0x18000dd03  mov     [r11-58h], r14d
0x18000dd07  mov     rcx, r13; struct _MINIDUMP_STATE *
0x18000dd0a  mov     [r11-54h], r15d
0x18000dd0e  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000dd13  test    eax, eax
0x18000dd15  jnz     loc_18000DF0A
0x18000dd1b  add     dword ptr [rbx+70h], 10h
0x18000dd1f  add     [rbx+7Ch], r14d
0x18000dd23  test    rdi, rdi
0x18000dd26  jz      short loc_18000DD2B
0x18000dd28  mov     [rdi], r15d
0x18000dd2b  mov     [rsp+0C8h+var_78], r14d
0x18000dd30  mov     r12d, r14d
0x18000dd33  test    r14d, r14d
0x18000dd36  jz      loc_18000DE9E
0x18000dd3c  lea     rdx, [rbp+1DB8h]
0x18000dd43  mov     eax, 10000h
0x18000dd48  mov     [rsp+0C8h+var_60], rdx
0x18000dd4d  mov     rcx, [r13+10h]
0x18000dd51  cmp     r12d, eax
0x18000dd54  mov     r9, rdx
0x18000dd57  mov     ebp, r12d
0x18000dd5a  mov     rdx, [r13+0]
0x18000dd5e  cmova   ebp, eax
0x18000dd61  mov     r8, rsi
0x18000dd64  mov     dword ptr [rsp+0C8h+var_A8], ebp
0x18000dd68  mov     rax, [rcx]
0x18000dd6b  mov     rax, [rax+0F0h]
0x18000dd72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd77  mov     edi, eax
0x18000dd79  test    eax, eax
0x18000dd7b  jnz     loc_18000DEA2
0x18000dd81  mov     eax, [rsp+0C8h+arg_30]
0x18000dd88  test    eax, 100008h
0x18000dd8d  jz      short loc_18000DDD4
0x18000dd8f  mov     rcx, [rsp+0C8h+var_68]
0x18000dd94  mov     r9, rsi
0x18000dd97  mov     rdx, [rsp+0C8h+var_70]
0x18000dd9c  xor     r8d, r8d
0x18000dd9f  mov     [rsp+0C8h+var_80], rcx
0x18000dda4  mov     rcx, r13
0x18000dda7  mov     [rsp+0C8h+var_88], eax
0x18000ddab  mov     eax, [rsp+0C8h+arg_28]
0x18000ddb2  mov     [rsp+0C8h+var_90], eax
0x18000ddb6  mov     eax, [rsp+0C8h+arg_40]
0x18000ddbd  mov     [rsp+0C8h+var_98], eax
0x18000ddc1  mov     rax, [rsp+0C8h+var_60]
0x18000ddc6  mov     [rsp+0C8h+var_A0], rax
0x18000ddcb  mov     dword ptr [rsp+0C8h+var_A8], ebp
0x18000ddcf  call    ?ScanMemoryForModuleRefs@@YAKPEAU_MINIDUMP_STATE@@PEAU_INTERNAL_PROCESS@@H_KKPEAXW4MEMBLOCK_TYPE@@W4MEMBLOCK_FILTER_TYPE@@KPEAU_VA_RANGE_REF@@@Z; ScanMemoryForModuleRefs(_MINIDUMP_STATE *,_INTERNAL_PROCESS *,int,unsigned __int64,ulong,void *,MEMBLOCK_TYPE,MEMBLOCK_FILTER_TYPE,ulong,_VA_RANGE_REF *)
0x18000ddd4  mov     rax, [rsp+0C8h+var_70]
0x18000ddd9  mov     rdi, [rax+11DE0h]
0x18000dde0  test    rdi, rdi
0x18000dde3  jz      short loc_18000DE63
0x18000dde5  mov     r12d, ebp
0x18000dde8  mov     r14, rax
0x18000ddeb  add     r12, rsi
0x18000ddee  mov     rcx, [rdi+10h]
0x18000ddf2  cmp     r12, rcx
0x18000ddf5  jb      short loc_18000DE56
0x18000ddf7  mov     eax, [rdi+18h]
0x18000ddfa  lea     rdx, [rax+rcx]
0x18000ddfe  cmp     rsi, rcx
0x18000de01  ja      short loc_18000DE17
0x18000de03  mov     r9d, ecx
0x18000de06  sub     r9d, esi
0x18000de09  cmp     rdx, r12
0x18000de0c  jbe     short loc_18000DE13
0x18000de0e  mov     eax, ebp
0x18000de10  sub     eax, r9d
0x18000de13  xor     ecx, ecx
0x18000de15  jmp     short loc_18000DE2F
0x18000de17  cmp     rdx, rsi
0x18000de1a  jb      short loc_18000DE4E
0x18000de1c  mov     ecx, esi
0x18000de1e  xor     r9d, r9d
0x18000de21  sub     ecx, [rdi+10h]
0x18000de24  cmp     rdx, r12
0x18000de27  jb      short loc_18000DE2D
0x18000de29  mov     eax, ebp
0x18000de2b  jmp     short loc_18000DE2F
0x18000de2d  sub     eax, ecx
0x18000de2f  test    eax, eax
0x18000de31  jz      short loc_18000DE4E
0x18000de33  mov     edx, ecx
0x18000de35  add     rdx, [rdi+8]; Src
0x18000de39  mov     ecx, r9d
0x18000de3c  add     rcx, 1DB8h
0x18000de43  mov     r8d, eax; Size
0x18000de46  add     rcx, r14; void *
0x18000de49  call    memcpy_0
0x18000de4e  mov     rdi, [rdi]
0x18000de51  test    rdi, rdi
0x18000de54  jnz     short loc_18000DDEE
0x18000de56  mov     r14d, [rsp+0C8h+arg_20]
0x18000de5e  mov     r12d, [rsp+0C8h+var_78]
0x18000de63  mov     r8, [rsp+0C8h+var_60]; void *
0x18000de68  mov     r9d, ebp; unsigned int
0x18000de6b  mov     edx, r15d; unsigned int
0x18000de6e  mov     rcx, r13; struct _MINIDUMP_STATE *
0x18000de71  call    ?WriteAtOffset@@YAJPEAU_MINIDUMP_STATE@@KPEAXK@Z; WriteAtOffset(_MINIDUMP_STATE *,ulong,void *,ulong)
0x18000de76  test    eax, eax
0x18000de78  jnz     loc_18000DF0A
0x18000de7e  mov     rdx, [rsp+0C8h+var_60]
0x18000de83  add     r15d, ebp
0x18000de86  mov     eax, ebp
0x18000de88  add     rsi, rax
0x18000de8b  mov     eax, 10000h
0x18000de90  sub     r12d, ebp
0x18000de93  mov     [rsp+0C8h+var_78], r12d
0x18000de98  jnz     loc_18000DD4D
0x18000de9e  xor     eax, eax
0x18000dea0  jmp     short loc_18000DF0A
0x18000dea2  mov     rcx, [r13+28h]
0x18000dea6  lea     r8, aWritememoryfro; "WriteMemoryFromProcess.Read(0x%I64x, 0x"...
0x18000dead  mov     dword ptr [rsp+0C8h+var_A0], edi
0x18000deb1  mov     r9, rsi
0x18000deb4  mov     edx, 4
0x18000deb9  mov     dword ptr [rsp+0C8h+var_A8], ebp
0x18000debd  mov     rax, [rcx]
0x18000dec0  mov     rax, [rax+8]
0x18000dec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dec9  mov     eax, [rsp+0C8h+arg_40]
0x18000ded0  add     eax, 0FFFFFFFEh
0x18000ded3  cmp     eax, 1
0x18000ded6  jbe     short loc_18000DF01
0x18000ded8  mov     r9d, edi; int
0x18000dedb  mov     r8d, ebp; unsigned int
0x18000dede  mov     rdx, rsi; unsigned __int64
0x18000dee1  mov     rcx, r13; struct _MINIDUMP_STATE *
0x18000dee4  call    ?GenExecuteReadMemoryFailureCallback@@YAHPEAU_MINIDUMP_STATE@@_KKJ@Z; GenExecuteReadMemoryFailureCallback(_MINIDUMP_STATE *,unsigned __int64,ulong,long)
0x18000dee9  test    eax, eax
0x18000deeb  jz      short loc_18000DF01
0x18000deed  mov     eax, 0FFFFFFF0h
0x18000def2  mov     edi, 1
0x18000def7  add     [rbx+70h], eax
0x18000defa  add     [rbx+6Ch], eax
0x18000defd  sub     [rbx+7Ch], r14d
0x18000df01  mov     eax, edi
0x18000df03  jmp     short loc_18000DF0A
0x18000df05  mov     eax, 80070057h
0x18000df0a  mov     rcx, [rsp+0C8h+var_50]
0x18000df0f  xor     rcx, rsp; StackCookie
0x18000df12  call    __security_check_cookie
0x18000df17  add     rsp, 88h
0x18000df1e  pop     r15
0x18000df20  pop     r14
0x18000df22  pop     r13
0x18000df24  pop     r12
0x18000df26  pop     rdi
0x18000df27  pop     rsi
0x18000df28  pop     rbp
0x18000df29  pop     rbx
0x18000df2a  retn
```
