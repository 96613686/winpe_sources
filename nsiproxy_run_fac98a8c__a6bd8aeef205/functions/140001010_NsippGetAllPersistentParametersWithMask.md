# NsippGetAllPersistentParametersWithMask

- ea: `0x140001010`
- end: `0x1400013e1`
- name: `NsippGetAllPersistentParametersWithMask`
- size: `977`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x140001dd0`
- `0x140002090`

## callees

- `0x140001010`
- `0x1400043d0`
- `0x1400056e8`
- `0x140006560`
- `0x140006980`
- `0x14000d08c`

## import_xrefs

- `ntoskrnl!IoIs32bitProcess` at `0x140001082`
- `ntoskrnl!IoIs32bitProcess` at `0x140001082`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400013ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400013ba`
- `NETIO!NsiGetAllPersistentParametersWithMask` at `0x140001303`
- `NETIO!NsiGetAllPersistentParametersWithMask` at `0x140001303`

## pseudocode

```c
__int64 __fastcall NsippGetAllPersistentParametersWithMask(void *Src, unsigned int a2, unsigned __int8 a3, _QWORD *a4)
{
  BOOLEAN v8; // al
  int AllPersistentParametersWithMask; // esi
  _DWORD *v10; // rbx
  int v11; // eax
  void *v12; // rdx
  unsigned int v13; // eax
  void *v14; // rdx
  unsigned int v15; // eax
  void *v16; // rdx
  unsigned int v17; // eax
  PVOID P; // [rsp+D0h] [rbp-F8h] BYREF
  __int128 v20; // [rsp+D8h] [rbp-F0h] BYREF
  __int128 v21; // [rsp+E8h] [rbp-E0h]
  __int32 v22; // [rsp+F8h] [rbp-D0h]
  __int64 v23; // [rsp+100h] [rbp-C8h] BYREF
  char *v24; // [rsp+108h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+110h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+118h] [rbp-B0h] BYREF
  void *v27[2]; // [rsp+120h] [rbp-A8h] BYREF
  void *v28[2]; // [rsp+130h] [rbp-98h] BYREF
  __int64 v29; // [rsp+140h] [rbp-88h]
  __m128i v30[7]; // [rsp+150h] [rbp-78h] BYREF

  P = 0;
  *(_OWORD *)v27 = 0;
  v26 = 0;
  v25 = 0;
  v23 = 0;
  *(_OWORD *)v28 = 0;
  v29 = 0;
  v24 = 0;
  memset(v30, 0, 0x48u);
  v8 = IoIs32bitProcess(0);
  if ( !Src )
    return 3221225485LL;
  if ( v8 )
  {
    if ( a2 >= 0x24 )
    {
      v20 = 0;
      v21 = 0;
      v22 = 0;
      if ( a3 )
        RtlCopyFromUser(&v20, Src, 0x24u);
      else
        RtlCopyVolatileMemory(&v20, Src, 0x24u);
      v30[2].m128i_i64[0] = (unsigned int)v21;
      v30[2].m128i_i32[2] = DWORD1(v21);
      v30[1].m128i_i64[0] = DWORD2(v20);
      v30[0].m128i_i32[2] = DWORD1(v20);
      v30[1].m128i_i32[2] = HIDWORD(v20);
      v30[3].m128i_i64[1] = HIDWORD(v21);
      v30[3].m128i_i64[0] = DWORD2(v21);
      v30[4].m128i_i32[0] = v22;
      v30[0].m128i_i64[0] = (int)v20;
      goto LABEL_12;
    }
    return 3221225485LL;
  }
  if ( a2 < 0x48 )
    return 3221225485LL;
  if ( a3 )
    RtlCopyFromUser(v30, Src, 0x48u);
  else
    RtlCopyVolatileMemory(v30, Src, 0x48u);
LABEL_12:
  AllPersistentParametersWithMask = NsippProbeAndAllocateParameters(
                                      v30,
                                      0x48u,
                                      (__int64)&v30[0].m128i_i64[1],
                                      &v30[2],
                                      0,
                                      0,
                                      0,
                                      &v30[3],
                                      a3,
                                      1u,
                                      0,
                                      (__m128i *)v27,
                                      &v23,
                                      0,
                                      0,
                                      0,
                                      0,
                                      0,
                                      (__m128i *)v28,
                                      &v26,
                                      &v25,
                                      0,
                                      0,
                                      &v24,
                                      &P);
  v10 = P;
  if ( AllPersistentParametersWithMask >= 0 )
  {
    *((_QWORD *)P + 4) = v23;
    v10[10] = v27[1];
    *((_QWORD *)v10 + 2) = v24;
    *((_QWORD *)v10 + 7) = v25;
    *((_QWORD *)v10 + 6) = v26;
    v11 = v29;
    v10[16] = v29;
    AllPersistentParametersWithMask = NsiGetAllPersistentParametersWithMask(
                                        *((_QWORD *)v10 + 2),
                                        (unsigned int)v10[6],
                                        *((_QWORD *)v10 + 4),
                                        (unsigned int)v10[10],
                                        *((_QWORD *)v10 + 6),
                                        *((_QWORD *)v10 + 7),
                                        v11);
    if ( AllPersistentParametersWithMask >= 0 )
    {
      *a4 = 72;
      v12 = (void *)*((_QWORD *)v10 + 4);
      if ( v12 )
      {
        v13 = v10[10];
        if ( v13 )
        {
          if ( a3 )
            RtlCopyToUser(v27[0], v12, v13);
          else
            RtlCopyVolatileMemory(v27[0], v12, v13);
        }
      }
      v14 = (void *)*((_QWORD *)v10 + 6);
      if ( v14 )
      {
        v15 = v10[16];
        if ( v15 )
        {
          if ( a3 )
            RtlCopyToUser(v28[0], v14, v15);
          else
            RtlCopyVolatileMemory(v28[0], v14, v15);
        }
      }
      v16 = (void *)*((_QWORD *)v10 + 7);
      if ( v16 )
      {
        v17 = v10[16];
        if ( v17 )
        {
          if ( a3 )
            RtlCopyToUser(v28[1], v16, v17);
          else
            RtlCopyVolatileMemory(v28[1], v16, v17);
        }
      }
    }
  }
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  return (unsigned int)AllPersistentParametersWithMask;
}

```

## disassembly

```asm
0x140001010  mov     r11, rsp
0x140001013  push    rbx
0x140001014  push    rsi
0x140001015  push    rdi
0x140001016  push    r14
0x140001018  push    r15
0x14000101a  sub     rsp, 1A0h
0x140001021  mov     r14, r9
0x140001024  movzx   edi, r8b
0x140001028  mov     esi, edx
0x14000102a  mov     rbx, rcx
0x14000102d  xor     r15d, r15d
0x140001030  mov     [r11-0F8h], r15
0x140001037  xorps   xmm0, xmm0
0x14000103a  movups  xmmword ptr [rsp+1C8h+var_A8], xmm0
0x140001042  mov     [r11-0B0h], r15
0x140001049  mov     [r11-0B8h], r15
0x140001050  mov     [r11-0C8h], r15
0x140001057  xor     eax, eax
0x140001059  movups  xmmword ptr [rsp+1C8h+var_98], xmm0
0x140001061  mov     [r11-88h], rax
0x140001068  mov     [r11-0C0h], r15
0x14000106f  xor     edx, edx; Val
0x140001071  mov     r8d, 48h ; 'H'; Size
0x140001077  lea     rcx, [r11-78h]; void *
0x14000107b  call    memset
0x140001080  xor     ecx, ecx; Irp
0x140001082  call    cs:__imp_IoIs32bitProcess
0x140001089  nop     dword ptr [rax+rax+00h]
0x14000108e  test    rbx, rbx
0x140001091  jz      loc_1400013CC
0x140001097  test    al, al
0x140001099  jz      loc_140001172
0x14000109f  cmp     esi, 24h ; '$'
0x1400010a2  jb      loc_1400013CC
0x1400010a8  xorps   xmm0, xmm0
0x1400010ab  xor     eax, eax
0x1400010ad  movups  [rsp+1C8h+var_F0], xmm0
0x1400010b5  movups  [rsp+1C8h+var_E0], xmm0
0x1400010bd  mov     [rsp+1C8h+var_D0], eax
0x1400010c4  mov     r8d, 24h ; '$'; Size
0x1400010ca  mov     rdx, rbx; Src
0x1400010cd  lea     rcx, [rsp+1C8h+var_F0]; void *
0x1400010d5  test    dil, dil
0x1400010d8  jz      short loc_1400010E1
0x1400010da  call    RtlCopyFromUser
0x1400010df  jmp     short loc_1400010E7
0x1400010e1  call    RtlCopyVolatileMemory
0x1400010e6  nop
0x1400010e7  mov     eax, dword ptr [rsp+1C8h+var_E0]
0x1400010ee  mov     [rsp+1C8h+var_58], rax
0x1400010f6  mov     eax, dword ptr [rsp+1C8h+var_E0+4]
0x1400010fd  mov     [rsp+1C8h+var_50], eax
0x140001104  mov     eax, dword ptr [rsp+1C8h+var_F0+8]
0x14000110b  mov     [rsp+1C8h+var_68], rax
0x140001113  mov     eax, dword ptr [rsp+1C8h+var_F0+4]
0x14000111a  mov     [rsp+1C8h+var_70], eax
0x140001121  mov     eax, dword ptr [rsp+1C8h+var_F0+0Ch]
0x140001128  mov     [rsp+1C8h+var_60], eax
0x14000112f  mov     eax, dword ptr [rsp+1C8h+var_E0+0Ch]
0x140001136  mov     [rsp+1C8h+var_40], rax
0x14000113e  mov     eax, dword ptr [rsp+1C8h+var_E0+8]
0x140001145  mov     [rsp+1C8h+var_48], rax
0x14000114d  mov     eax, [rsp+1C8h+var_D0]
0x140001154  mov     [rsp+1C8h+var_38], eax
0x14000115b  movsxd  rax, dword ptr [rsp+1C8h+var_F0]
0x140001163  mov     [rsp+1C8h+var_78], rax
0x14000116b  jmp     short loc_14000119E
0x14000116d  jmp     loc_1400013D1
0x140001172  cmp     esi, 48h ; 'H'
0x140001175  jb      loc_1400013CC
0x14000117b  mov     r8d, 48h ; 'H'; Size
0x140001181  mov     rdx, rbx; Src
0x140001184  lea     rcx, [rsp+1C8h+var_78]; void *
0x14000118c  test    dil, dil
0x14000118f  jz      short loc_140001198
0x140001191  call    RtlCopyFromUser
0x140001196  jmp     short loc_14000119E
0x140001198  call    RtlCopyVolatileMemory
0x14000119d  nop
0x14000119e  lea     rax, [rsp+1C8h+P]
0x1400011a6  mov     [rsp+1C8h+var_108], rax
0x1400011ae  lea     rax, [rsp+1C8h+var_C0]
0x1400011b6  mov     [rsp+1C8h+var_110], rax
0x1400011be  mov     [rsp+1C8h+var_118], r15
0x1400011c6  mov     [rsp+1C8h+var_120], r15
0x1400011ce  lea     rax, [rsp+1C8h+var_B8]
0x1400011d6  mov     [rsp+1C8h+var_128], rax
0x1400011de  lea     rax, [rsp+1C8h+var_B0]
0x1400011e6  mov     [rsp+1C8h+var_130], rax
0x1400011ee  lea     rax, [rsp+1C8h+var_98]
0x1400011f6  mov     [rsp+1C8h+var_138], rax
0x1400011fe  mov     [rsp+1C8h+var_140], r15
0x140001206  mov     [rsp+1C8h+var_148], r15
0x14000120e  mov     [rsp+1C8h+var_150], r15
0x140001213  mov     [rsp+1C8h+var_158], r15
0x140001218  mov     [rsp+1C8h+var_160], r15
0x14000121d  lea     rax, [rsp+1C8h+var_C8]
0x140001225  mov     [rsp+1C8h+var_168], rax
0x14000122a  lea     rax, [rsp+1C8h+var_A8]
0x140001232  mov     [rsp+1C8h+var_170], rax
0x140001237  mov     [rsp+1C8h+var_178], 0
0x14000123c  mov     [rsp+1C8h+var_180], 1
0x140001244  mov     [rsp+1C8h+var_188], dil
0x140001249  lea     rax, [rsp+1C8h+var_48]
0x140001251  mov     [rsp+1C8h+var_190], rax
0x140001256  mov     [rsp+1C8h+var_198], r15
0x14000125b  mov     [rsp+1C8h+var_1A0], r15
0x140001260  mov     [rsp+1C8h+var_1A8], r15
0x140001265  lea     r9, [rsp+1C8h+var_58]
0x14000126d  lea     r8, [rsp+1C8h+var_70]
0x140001275  mov     edx, 48h ; 'H'
0x14000127a  lea     rcx, [rsp+1C8h+var_78]
0x140001282  call    NsippProbeAndAllocateParameters
0x140001287  mov     esi, eax
0x140001289  mov     rbx, [rsp+1C8h+P]
0x140001291  test    eax, eax
0x140001293  js      loc_1400013B0
0x140001299  mov     rax, [rsp+1C8h+var_C8]
0x1400012a1  mov     [rbx+20h], rax
0x1400012a5  mov     eax, dword ptr [rsp+1C8h+var_A8+8]
0x1400012ac  mov     [rbx+28h], eax
0x1400012af  mov     rax, [rsp+1C8h+var_C0]
0x1400012b7  mov     [rbx+10h], rax
0x1400012bb  mov     rax, [rsp+1C8h+var_B8]
0x1400012c3  mov     [rbx+38h], rax
0x1400012c7  mov     rax, [rsp+1C8h+var_B0]
0x1400012cf  mov     [rbx+30h], rax
0x1400012d3  mov     rax, [rsp+1C8h+var_88]
0x1400012db  mov     [rbx+40h], eax
0x1400012de  mov     dword ptr [rsp+1C8h+var_198], eax
0x1400012e2  mov     rax, [rbx+38h]
0x1400012e6  mov     [rsp+1C8h+var_1A0], rax
0x1400012eb  mov     rax, [rbx+30h]
0x1400012ef  mov     [rsp+1C8h+var_1A8], rax
0x1400012f4  mov     r9d, [rbx+28h]
0x1400012f8  mov     r8, [rbx+20h]
0x1400012fc  mov     edx, [rbx+18h]
0x1400012ff  mov     rcx, [rbx+10h]
0x140001303  call    cs:__imp_NsiGetAllPersistentParametersWithMask
0x14000130a  nop     dword ptr [rax+rax+00h]
0x14000130f  mov     esi, eax
0x140001311  test    eax, eax
0x140001313  js      loc_1400013B0
0x140001319  mov     qword ptr [r14], 48h ; 'H'
0x140001320  mov     rdx, [rbx+20h]; Src
0x140001324  test    rdx, rdx
0x140001327  jz      short loc_14000134C
0x140001329  mov     eax, [rbx+28h]
0x14000132c  test    eax, eax
0x14000132e  jz      short loc_14000134C
0x140001330  mov     rcx, [rsp+1C8h+var_A8]; void *
0x140001338  mov     r8d, eax; Size
0x14000133b  test    dil, dil
0x14000133e  jz      short loc_140001347
0x140001340  call    RtlCopyToUser
0x140001345  jmp     short loc_14000134C
0x140001347  call    RtlCopyVolatileMemory
0x14000134c  mov     rdx, [rbx+30h]; Src
0x140001350  test    rdx, rdx
0x140001353  jz      short loc_140001378
0x140001355  mov     eax, [rbx+40h]
0x140001358  test    eax, eax
0x14000135a  jz      short loc_140001378
0x14000135c  mov     rcx, [rsp+1C8h+var_98]; void *
0x140001364  mov     r8d, eax; Size
0x140001367  test    dil, dil
0x14000136a  jz      short loc_140001373
0x14000136c  call    RtlCopyToUser
0x140001371  jmp     short loc_140001378
0x140001373  call    RtlCopyVolatileMemory
0x140001378  mov     rdx, [rbx+38h]; Src
0x14000137c  test    rdx, rdx
0x14000137f  jz      short loc_1400013A4
0x140001381  mov     eax, [rbx+40h]
0x140001384  test    eax, eax
0x140001386  jz      short loc_1400013A4
0x140001388  mov     rcx, [rsp+1C8h+var_98+8]; void *
0x140001390  mov     r8d, eax; Size
0x140001393  test    dil, dil
0x140001396  jz      short loc_14000139F
0x140001398  call    RtlCopyToUser
0x14000139d  jmp     short loc_1400013A4
0x14000139f  call    RtlCopyVolatileMemory
0x1400013a4  jmp     short loc_1400013B0
0x1400013a6  mov     esi, eax
0x1400013a8  mov     rbx, [rsp+1C8h+P]
0x1400013b0  test    rbx, rbx
0x1400013b3  jz      short loc_1400013C6
0x1400013b5  xor     edx, edx; Tag
0x1400013b7  mov     rcx, rbx; P
0x1400013ba  call    cs:__imp_ExFreePoolWithTag
0x1400013c1  nop     dword ptr [rax+rax+00h]
0x1400013c6  mov     eax, esi
0x1400013c8  jmp     short loc_1400013D1
0x1400013ca  jmp     short loc_1400013D1
0x1400013cc  mov     eax, 0C000000Dh
0x1400013d1  add     rsp, 1A0h
0x1400013d8  pop     r15
0x1400013da  pop     r14
0x1400013dc  pop     rdi
0x1400013dd  pop     rsi
0x1400013de  pop     rbx
0x1400013df  retn
```
