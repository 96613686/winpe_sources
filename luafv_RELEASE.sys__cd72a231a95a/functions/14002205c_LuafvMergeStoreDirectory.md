# LuafvMergeStoreDirectory

- ea: `0x14002205c`
- end: `0x14002234b`
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
- `0x14002205c`
- `0x140022354`
- `0x140024050`

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
0x14002205c  mov     rax, rsp
0x14002205f  mov     [rax+20h], r9b
0x140022063  mov     [rax+18h], r8d
0x140022067  mov     [rax+10h], rdx
0x14002206b  mov     [rax+8], rcx
0x14002206f  push    rsi
0x140022070  push    rdi
0x140022071  push    r12
0x140022073  push    r13
0x140022075  push    r14
0x140022077  push    r15
0x140022079  sub     rsp, 88h
0x140022080  mov     r12d, r8d
0x140022083  mov     qword ptr [rax-68h], 0
0x14002208b  mov     r15, [rdx+60h]
0x14002208f  mov     [rsp+0B8h+var_58], r15
0x140022094  lea     r13, [r15+20h]
0x140022098  mov     [rsp+0B8h+var_50], r13
0x14002209d  mov     rdi, [rsp+0B8h+arg_48]
0x1400220a5  mov     [rax-70h], rdi
0x1400220a9  mov     r14, rdi
0x1400220ac  mov     [rax-68h], rdi
0x1400220b0  add     r12, rdi
0x1400220b3  mov     [rsp+0B8h+var_48], r12
0x1400220b8  mov     byte ptr [rax+50h], 0
0x1400220bc  mov     byte ptr [rax-78h], 0
0x1400220c0  mov     al, [rsp+0B8h+arg_38]
0x1400220c7  mov     [rsp+0B8h+var_90], al; BOOLEAN
0x1400220cb  mov     rax, [rsp+0B8h+arg_30]
0x1400220d3  mov     [rsp+0B8h+var_98], rax; PUNICODE_STRING
0x1400220d8  mov     r9d, [rsp+0B8h+arg_20]
0x1400220e0  mov     r8b, [rsp+0B8h+arg_28]
0x1400220e8  mov     rdx, r15
0x1400220eb  call    LuafvQueryDirectoryIfNeeded
0x1400220f0  mov     esi, eax
0x1400220f2  test    eax, eax
0x1400220f4  js      loc_1400221D7
0x1400220fa  mov     al, [rsp+0B8h+arg_38]
0x140022101  mov     [rsp+0B8h+var_90], al; BOOLEAN
0x140022105  mov     rax, [rsp+0B8h+arg_30]
0x14002210d  mov     [rsp+0B8h+var_98], rax; PUNICODE_STRING
0x140022112  mov     r9d, [rsp+0B8h+arg_20]
0x14002211a  mov     r8b, [rsp+0B8h+arg_28]
0x140022122  mov     rdx, r13
0x140022125  mov     rcx, [rsp+0B8h+Instance]; Instance
0x14002212d  call    LuafvQueryDirectoryIfNeeded
0x140022132  mov     esi, eax
0x140022134  test    eax, eax
0x140022136  js      loc_1400221D7
0x14002213c  mov     [rsp+0B8h+var_60], 0
0x140022145  lea     rax, [rsp+0B8h+arg_48]
0x14002214d  mov     [rsp+0B8h+var_80], rax
0x140022152  lea     rax, [rsp+0B8h+var_60]
0x140022157  mov     [rsp+0B8h+var_88], rax
0x14002215c  mov     al, [rsp+0B8h+arg_28]
0x140022163  mov     [rsp+0B8h+var_90], al
0x140022167  mov     [rsp+0B8h+var_98], r12
0x14002216c  mov     r9, rdi
0x14002216f  mov     r8b, [rsp+0B8h+arg_18]
0x140022177  mov     edx, [rsp+0B8h+arg_20]
0x14002217e  mov     rcx, [rsp+0B8h+arg_8]
0x140022186  call    LuafvCopyNextDirectoryEntry
0x14002218b  test    al, al
0x14002218d  jz      short loc_1400221BA
0x14002218f  cmp     byte ptr [rsp+0B8h+arg_48], 0
0x140022197  jz      short loc_1400221A3
0x140022199  mov     rdi, r12
0x14002219c  mov     [rsp+0B8h+var_70], r12
0x1400221a1  jmp     short loc_1400221BA
0x1400221a3  mov     r14, rdi
0x1400221a6  mov     [rsp+0B8h+var_68], rdi
0x1400221ab  mov     rdi, [rsp+0B8h+var_60]
0x1400221b0  mov     [rsp+0B8h+var_70], rdi
0x1400221b5  mov     [rsp+0B8h+var_78], 1
0x1400221ba  jmp     short loc_1400221D7
0x1400221bc  mov     esi, eax
0x1400221be  mov     r15, [rsp+0B8h+var_58]
0x1400221c3  mov     r13, [rsp+0B8h+var_50]
0x1400221c8  mov     rdi, [rsp+0B8h+var_70]
0x1400221cd  mov     r14, [rsp+0B8h+var_68]
0x1400221d2  mov     r12, [rsp+0B8h+var_48]
0x1400221d7  mov     r9b, [rsp+0B8h+var_78]
0x1400221dc  cmp     [rsp+0B8h+arg_28], 0
0x1400221e4  jz      short loc_1400221EF
0x1400221e6  test    r9b, r9b
0x1400221e9  jnz     loc_140022282
0x1400221ef  test    esi, esi
0x1400221f1  jnz     loc_140022284
0x1400221f7  cmp     rdi, r12
0x1400221fa  jnb     loc_140022282
0x140022200  mov     [rsp+0B8h+arg_38], sil
0x140022208  mov     rdx, [r15+18h]
0x14002220c  test    rdx, rdx
0x14002220f  jz      short loc_14002222D
0x140022211  mov     rcx, [r15+10h]
0x140022215  mov     eax, [r15+0Ch]
0x140022219  add     rcx, rax
0x14002221c  cmp     rdx, rcx
0x14002221f  mov     rcx, [rsp+0B8h+Instance]
0x140022227  jb      loc_1400220C0
0x14002222d  mov     r8, [r13+18h]
0x140022231  test    r8, r8
0x140022234  jz      short loc_140022252
0x140022236  mov     rcx, [r13+10h]
0x14002223a  mov     eax, [r13+0Ch]
0x14002223e  add     rcx, rax
0x140022241  cmp     r8, rcx
0x140022244  mov     rcx, [rsp+0B8h+Instance]
0x14002224c  jb      loc_1400220C0
0x140022252  test    rdx, rdx
0x140022255  mov     rcx, [rsp+0B8h+Instance]
0x14002225d  jz      loc_1400220C0
0x140022263  cmp     dword ptr [r15+8], 0
0x140022268  jz      loc_1400220C0
0x14002226e  test    r8, r8
0x140022271  jz      loc_1400220C0
0x140022277  cmp     dword ptr [r13+8], 0
0x14002227c  jz      loc_1400220C0
0x140022282  test    esi, esi
0x140022284  js      loc_14002231E
0x14002228a  test    r9b, r9b
0x14002228d  jz      short loc_1400222D9
0x14002228f  call    Feature_Bugfix_LuafvUMA__private_IsEnabledDeviceUsageNoInline
0x140022294  test    eax, eax
0x140022296  jz      short loc_1400222AE
0x140022298  cmp     [rsp+0B8h+arg_18], 0
0x1400222a0  jz      short loc_1400222AE
0x1400222a2  xor     edx, edx
0x1400222a4  mov     rcx, r14
0x1400222a7  call    RtlWriteULongToUser
0x1400222ac  jmp     short loc_1400222B5
0x1400222ae  mov     dword ptr [r14], 0
0x1400222b5  sub     edi, r12d
0x1400222b8  add     edi, [rsp+0B8h+arg_10]
0x1400222bf  mov     eax, edi
0x1400222c1  mov     rcx, [rsp+0B8h+arg_40]
0x1400222c9  mov     [rcx+8], rax
0x1400222cd  mov     dword ptr [rcx], 0
0x1400222d3  jmp     short loc_14002231E
0x1400222d5  mov     esi, eax
0x1400222d7  jmp     short loc_14002231E
0x1400222d9  mov     rcx, [rsp+0B8h+arg_40]
0x1400222e1  mov     qword ptr [rcx+8], 0
0x1400222e9  mov     edx, [r15+8]
0x1400222ed  mov     r8d, 80000005h
0x1400222f3  cmp     edx, r8d
0x1400222f6  jz      short loc_14002231B
0x1400222f8  mov     eax, [r13+8]
0x1400222fc  cmp     eax, r8d
0x1400222ff  jz      short loc_14002231B
0x140022301  cmp     byte ptr [rsp+0B8h+arg_48], 0
0x140022309  jz      short loc_140022333
0x14002230b  sub     edi, r12d
0x14002230e  add     edi, [rsp+0B8h+arg_10]
0x140022315  mov     eax, edi
0x140022317  mov     [rcx+8], rax
0x14002231b  mov     [rcx], r8d
0x14002231e  mov     eax, esi
0x140022320  add     rsp, 88h
0x140022327  pop     r15
0x140022329  pop     r14
0x14002232b  pop     r13
0x14002232d  pop     r12
0x14002232f  pop     rdi
0x140022330  pop     rsi
0x140022331  retn
0x140022333  mov     r8d, 80000006h
0x140022339  cmp     edx, r8d
0x14002233c  jz      short loc_14002231B
0x14002233e  cmp     eax, r8d
0x140022341  jz      short loc_14002231B
0x140022343  mov     dword ptr [rcx], 0C000000Fh
0x140022349  jmp     short loc_14002231E
```
