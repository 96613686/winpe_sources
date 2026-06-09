# LuafvMergeStoreDirectory

- ea: `0x1400220ac`
- end: `0x14002239b`
- name: `LuafvMergeStoreDirectory`
- size: `751`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *, __int64, unsigned int, char, int, char, PUNICODE_STRING, BOOLEAN, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140014df0`

## callees

- `0x140001b34`
- `0x140014c8c`
- `0x1400220ac`
- `0x1400223a4`
- `0x1400240a0`

## pseudocode

```c
__int64 __fastcall LuafvMergeStoreDirectory(
        struct _FLT_INSTANCE *a1,
        __int64 a2,
        unsigned int a3,
        char a4,
        int a5,
        char a6,
        PUNICODE_STRING a7,
        BOOLEAN a8,
        __int64 a9,
        _DWORD *a10)
{
  __int64 v10; // r15
  unsigned __int64 v11; // rdi
  _DWORD *v12; // r14
  unsigned __int64 v13; // r12
  int DirectoryIfNeeded; // esi
  bool v15; // sf
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // r8
  int v18; // edx
  int v19; // r8d
  int v20; // eax
  char v22; // [rsp+40h] [rbp-78h]
  _QWORD v23[12]; // [rsp+58h] [rbp-60h] BYREF
  struct _FLT_INSTANCE *Instance; // [rsp+C0h] [rbp+8h]

  Instance = a1;
  v10 = *(_QWORD *)(a2 + 96);
  v23[1] = v10;
  v23[2] = v10 + 32;
  v11 = (unsigned __int64)a10;
  v12 = a10;
  v13 = (unsigned __int64)a10 + a3;
  v23[3] = v13;
  LOBYTE(a10) = 0;
  v22 = 0;
  while ( 1 )
  {
    DirectoryIfNeeded = LuafvQueryDirectoryIfNeeded(a1, a7, a8);
    if ( DirectoryIfNeeded >= 0 )
    {
      DirectoryIfNeeded = LuafvQueryDirectoryIfNeeded(Instance, a7, a8);
      if ( DirectoryIfNeeded >= 0 )
      {
        v23[0] = 0;
        if ( LuafvCopyNextDirectoryEntry(a2, a5, a4, v11, v13, a6, (__int64)v23, (__int64)&a10) )
        {
          if ( (_BYTE)a10 )
          {
            v11 = v13;
          }
          else
          {
            v12 = (_DWORD *)v11;
            v11 = v23[0];
            v22 = 1;
          }
        }
      }
    }
    if ( a6 && v22 )
      break;
    v15 = DirectoryIfNeeded < 0;
    if ( DirectoryIfNeeded )
      goto LABEL_21;
    if ( v11 >= v13 )
      break;
    a8 = 0;
    v16 = *(_QWORD *)(v10 + 24);
    if ( v16 )
    {
      a1 = Instance;
      if ( v16 < (unsigned __int64)*(unsigned int *)(v10 + 12) + *(_QWORD *)(v10 + 16) )
        continue;
    }
    v17 = *(_QWORD *)(v10 + 56);
    if ( v17 )
    {
      a1 = Instance;
      if ( v17 < (unsigned __int64)*(unsigned int *)(v10 + 44) + *(_QWORD *)(v10 + 48) )
        continue;
    }
    a1 = Instance;
    if ( v16 )
    {
      if ( *(_DWORD *)(v10 + 8) && v17 && *(_DWORD *)(v10 + 40) )
        break;
    }
  }
  v15 = DirectoryIfNeeded < 0;
LABEL_21:
  if ( !v15 )
  {
    if ( v22 )
    {
      if ( (unsigned int)Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline() && a4 )
        RtlWriteULongToUser(v12, 0);
      else
        *v12 = 0;
      *(_QWORD *)(a9 + 8) = a3 + (_DWORD)v11 - (_DWORD)v13;
      *(_DWORD *)a9 = 0;
    }
    else
    {
      *(_QWORD *)(a9 + 8) = 0;
      v18 = *(_DWORD *)(v10 + 8);
      v19 = -2147483643;
      if ( v18 != -2147483643 )
      {
        v20 = *(_DWORD *)(v10 + 40);
        if ( v20 != -2147483643 )
        {
          if ( (_BYTE)a10 )
          {
            *(_QWORD *)(a9 + 8) = a3 + (_DWORD)v11 - (_DWORD)v13;
          }
          else
          {
            v19 = -2147483642;
            if ( v18 != -2147483642 && v20 != -2147483642 )
            {
              *(_DWORD *)a9 = -1073741809;
              return (unsigned int)DirectoryIfNeeded;
            }
          }
        }
      }
      *(_DWORD *)a9 = v19;
    }
  }
  return (unsigned int)DirectoryIfNeeded;
}

```

## disassembly

```asm
0x1400220ac  mov     rax, rsp
0x1400220af  mov     [rax+20h], r9b
0x1400220b3  mov     [rax+18h], r8d
0x1400220b7  mov     [rax+10h], rdx
0x1400220bb  mov     [rax+8], rcx
0x1400220bf  push    rsi
0x1400220c0  push    rdi
0x1400220c1  push    r12
0x1400220c3  push    r13
0x1400220c5  push    r14
0x1400220c7  push    r15
0x1400220c9  sub     rsp, 88h
0x1400220d0  mov     r12d, r8d
0x1400220d3  mov     qword ptr [rax-68h], 0
0x1400220db  mov     r15, [rdx+60h]
0x1400220df  mov     [rsp+0B8h+var_58], r15
0x1400220e4  lea     r13, [r15+20h]
0x1400220e8  mov     [rsp+0B8h+var_50], r13
0x1400220ed  mov     rdi, [rsp+0B8h+arg_48]
0x1400220f5  mov     [rax-70h], rdi
0x1400220f9  mov     r14, rdi
0x1400220fc  mov     [rax-68h], rdi
0x140022100  add     r12, rdi
0x140022103  mov     [rsp+0B8h+var_48], r12
0x140022108  mov     byte ptr [rax+50h], 0
0x14002210c  mov     byte ptr [rax-78h], 0
0x140022110  mov     al, [rsp+0B8h+arg_38]
0x140022117  mov     [rsp+0B8h+var_90], al; BOOLEAN
0x14002211b  mov     rax, [rsp+0B8h+arg_30]
0x140022123  mov     [rsp+0B8h+var_98], rax; PUNICODE_STRING
0x140022128  mov     r9d, [rsp+0B8h+arg_20]
0x140022130  mov     r8b, [rsp+0B8h+arg_28]
0x140022138  mov     rdx, r15
0x14002213b  call    LuafvQueryDirectoryIfNeeded
0x140022140  mov     esi, eax
0x140022142  test    eax, eax
0x140022144  js      loc_140022227
0x14002214a  mov     al, [rsp+0B8h+arg_38]
0x140022151  mov     [rsp+0B8h+var_90], al; BOOLEAN
0x140022155  mov     rax, [rsp+0B8h+arg_30]
0x14002215d  mov     [rsp+0B8h+var_98], rax; PUNICODE_STRING
0x140022162  mov     r9d, [rsp+0B8h+arg_20]
0x14002216a  mov     r8b, [rsp+0B8h+arg_28]
0x140022172  mov     rdx, r13
0x140022175  mov     rcx, [rsp+0B8h+Instance]; Instance
0x14002217d  call    LuafvQueryDirectoryIfNeeded
0x140022182  mov     esi, eax
0x140022184  test    eax, eax
0x140022186  js      loc_140022227
0x14002218c  mov     [rsp+0B8h+var_60], 0
0x140022195  lea     rax, [rsp+0B8h+arg_48]
0x14002219d  mov     [rsp+0B8h+var_80], rax
0x1400221a2  lea     rax, [rsp+0B8h+var_60]
0x1400221a7  mov     [rsp+0B8h+var_88], rax
0x1400221ac  mov     al, [rsp+0B8h+arg_28]
0x1400221b3  mov     [rsp+0B8h+var_90], al
0x1400221b7  mov     [rsp+0B8h+var_98], r12
0x1400221bc  mov     r9, rdi
0x1400221bf  mov     r8b, [rsp+0B8h+arg_18]
0x1400221c7  mov     edx, [rsp+0B8h+arg_20]
0x1400221ce  mov     rcx, [rsp+0B8h+arg_8]
0x1400221d6  call    LuafvCopyNextDirectoryEntry
0x1400221db  test    al, al
0x1400221dd  jz      short loc_14002220A
0x1400221df  cmp     byte ptr [rsp+0B8h+arg_48], 0
0x1400221e7  jz      short loc_1400221F3
0x1400221e9  mov     rdi, r12
0x1400221ec  mov     [rsp+0B8h+var_70], r12
0x1400221f1  jmp     short loc_14002220A
0x1400221f3  mov     r14, rdi
0x1400221f6  mov     [rsp+0B8h+var_68], rdi
0x1400221fb  mov     rdi, [rsp+0B8h+var_60]
0x140022200  mov     [rsp+0B8h+var_70], rdi
0x140022205  mov     [rsp+0B8h+var_78], 1
0x14002220a  jmp     short loc_140022227
0x14002220c  mov     esi, eax
0x14002220e  mov     r15, [rsp+0B8h+var_58]
0x140022213  mov     r13, [rsp+0B8h+var_50]
0x140022218  mov     rdi, [rsp+0B8h+var_70]
0x14002221d  mov     r14, [rsp+0B8h+var_68]
0x140022222  mov     r12, [rsp+0B8h+var_48]
0x140022227  mov     r9b, [rsp+0B8h+var_78]
0x14002222c  cmp     [rsp+0B8h+arg_28], 0
0x140022234  jz      short loc_14002223F
0x140022236  test    r9b, r9b
0x140022239  jnz     loc_1400222D2
0x14002223f  test    esi, esi
0x140022241  jnz     loc_1400222D4
0x140022247  cmp     rdi, r12
0x14002224a  jnb     loc_1400222D2
0x140022250  mov     [rsp+0B8h+arg_38], sil
0x140022258  mov     rdx, [r15+18h]
0x14002225c  test    rdx, rdx
0x14002225f  jz      short loc_14002227D
0x140022261  mov     rcx, [r15+10h]
0x140022265  mov     eax, [r15+0Ch]
0x140022269  add     rcx, rax
0x14002226c  cmp     rdx, rcx
0x14002226f  mov     rcx, [rsp+0B8h+Instance]
0x140022277  jb      loc_140022110
0x14002227d  mov     r8, [r13+18h]
0x140022281  test    r8, r8
0x140022284  jz      short loc_1400222A2
0x140022286  mov     rcx, [r13+10h]
0x14002228a  mov     eax, [r13+0Ch]
0x14002228e  add     rcx, rax
0x140022291  cmp     r8, rcx
0x140022294  mov     rcx, [rsp+0B8h+Instance]
0x14002229c  jb      loc_140022110
0x1400222a2  test    rdx, rdx
0x1400222a5  mov     rcx, [rsp+0B8h+Instance]
0x1400222ad  jz      loc_140022110
0x1400222b3  cmp     dword ptr [r15+8], 0
0x1400222b8  jz      loc_140022110
0x1400222be  test    r8, r8
0x1400222c1  jz      loc_140022110
0x1400222c7  cmp     dword ptr [r13+8], 0
0x1400222cc  jz      loc_140022110
0x1400222d2  test    esi, esi
0x1400222d4  js      loc_14002236E
0x1400222da  test    r9b, r9b
0x1400222dd  jz      short loc_140022329
0x1400222df  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x1400222e4  test    eax, eax
0x1400222e6  jz      short loc_1400222FE
0x1400222e8  cmp     [rsp+0B8h+arg_18], 0
0x1400222f0  jz      short loc_1400222FE
0x1400222f2  xor     edx, edx
0x1400222f4  mov     rcx, r14
0x1400222f7  call    RtlWriteULongToUser
0x1400222fc  jmp     short loc_140022305
0x1400222fe  mov     dword ptr [r14], 0
0x140022305  sub     edi, r12d
0x140022308  add     edi, [rsp+0B8h+arg_10]
0x14002230f  mov     eax, edi
0x140022311  mov     rcx, [rsp+0B8h+arg_40]
0x140022319  mov     [rcx+8], rax
0x14002231d  mov     dword ptr [rcx], 0
0x140022323  jmp     short loc_14002236E
0x140022325  mov     esi, eax
0x140022327  jmp     short loc_14002236E
0x140022329  mov     rcx, [rsp+0B8h+arg_40]
0x140022331  mov     qword ptr [rcx+8], 0
0x140022339  mov     edx, [r15+8]
0x14002233d  mov     r8d, 80000005h
0x140022343  cmp     edx, r8d
0x140022346  jz      short loc_14002236B
0x140022348  mov     eax, [r13+8]
0x14002234c  cmp     eax, r8d
0x14002234f  jz      short loc_14002236B
0x140022351  cmp     byte ptr [rsp+0B8h+arg_48], 0
0x140022359  jz      short loc_140022383
0x14002235b  sub     edi, r12d
0x14002235e  add     edi, [rsp+0B8h+arg_10]
0x140022365  mov     eax, edi
0x140022367  mov     [rcx+8], rax
0x14002236b  mov     [rcx], r8d
0x14002236e  mov     eax, esi
0x140022370  add     rsp, 88h
0x140022377  pop     r15
0x140022379  pop     r14
0x14002237b  pop     r13
0x14002237d  pop     r12
0x14002237f  pop     rdi
0x140022380  pop     rsi
0x140022381  retn
0x140022383  mov     r8d, 80000006h
0x140022389  cmp     edx, r8d
0x14002238c  jz      short loc_14002236B
0x14002238e  cmp     eax, r8d
0x140022391  jz      short loc_14002236B
0x140022393  mov     dword ptr [rcx], 0C000000Fh
0x140022399  jmp     short loc_14002236E
```
