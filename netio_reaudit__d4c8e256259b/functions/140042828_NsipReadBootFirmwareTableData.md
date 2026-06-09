# NsipReadBootFirmwareTableData

- ea: `0x140042828`
- end: `0x1400428ee`
- name: `NsipReadBootFirmwareTableData`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140023160`

## callees

- `0x140042828`
- `0x1400428f4`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140042883`
- `ntoskrnl!KeSetEvent` at `0x1400428ab`
- `ntoskrnl!KeSetEvent` at `0x140042883`
- `ntoskrnl!KeSetEvent` at `0x1400428ab`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004285b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004285b`
- `ntoskrnl!RtlCompareMemory` at `0x14007d7e9`
- `ntoskrnl!RtlCompareMemory` at `0x14007d8b2`
- `ntoskrnl!RtlCompareMemory` at `0x14007d7e9`
- `ntoskrnl!RtlCompareMemory` at `0x14007d8b2`

## pseudocode

```c
__int64 __fastcall NsipReadBootFirmwareTableData(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int v6; // ebx
  unsigned int v8; // ebp
  __int64 i; // rdi
  bool v10; // zf
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdi
  unsigned int v14; // r13d
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rcx

  v6 = 0;
  KeWaitForSingleObject(&NsiBootNicTable, Executive, 0, 0, 0);
  if ( !SystemInformation )
  {
    v6 = NsipInitializeBootFirmwareTableData();
    if ( (v6 & 0x80000000) != 0 )
    {
      KeSetEvent(&NsiBootNicTable, 0, 0);
      return v6;
    }
  }
  KeSetEvent(&NsiBootNicTable, 0, 0);
  if ( !*a3 )
    return v6;
  if ( !a2 || !a1 || *(_DWORD *)(a1 + 8) != 6 )
    return 3221225485LL;
  v8 = 102;
  if ( *a3 < 0x66 )
    return 3221225990LL;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    v10 = (_DWORD)i == dword_14009ACD8;
    if ( (unsigned int)i >= dword_14009ACD8 )
      break;
    v11 = *((_QWORD *)qword_14009ACC8 + i);
    if ( v11 && RtlCompareMemory((const void *)(v11 + 90), *(const void **)a1, 6u) == 6 )
    {
      _mm_lfence();
      v12 = *((_QWORD *)qword_14009ACC8 + i);
      *(_OWORD *)a2 = *(_OWORD *)v12;
      *(_OWORD *)(a2 + 16) = *(_OWORD *)(v12 + 16);
      *(_OWORD *)(a2 + 32) = *(_OWORD *)(v12 + 32);
      *(_OWORD *)(a2 + 48) = *(_OWORD *)(v12 + 48);
      *(_OWORD *)(a2 + 64) = *(_OWORD *)(v12 + 64);
      *(_OWORD *)(a2 + 80) = *(_OWORD *)(v12 + 80);
      *(_QWORD *)(a2 + 94) = *(_QWORD *)(v12 + 94);
      v10 = (_DWORD)i == dword_14009ACD8;
      break;
    }
  }
  if ( !v10 )
  {
    v13 = 0;
    v14 = 0;
    while ( (unsigned int)v13 < dword_14009ACDC )
    {
      if ( *(unsigned __int8 *)(*((_QWORD *)qword_14009ACD0 + v13) + 33LL) < (unsigned int)dword_14009ACD8 )
      {
        v15 = *((_QWORD *)qword_14009ACC8 + *(unsigned __int8 *)(*((_QWORD *)qword_14009ACD0 + v13) + 33LL));
        if ( v15 )
        {
          if ( RtlCompareMemory((const void *)(v15 + 90), *(const void **)a1, 6u) == 6 )
          {
            if ( (unsigned __int64)v8 + 54 > *a3 )
              return 261;
            v16 = *((_QWORD *)qword_14009ACD0 + v13);
            v17 = v14++;
            v18 = 54 * v17;
            v8 += 54;
            *(_OWORD *)(v18 + a2 + 102) = *(_OWORD *)v16;
            *(_OWORD *)(v18 + a2 + 118) = *(_OWORD *)(v16 + 16);
            *(_OWORD *)(v18 + a2 + 134) = *(_OWORD *)(v16 + 32);
            *(_QWORD *)(v18 + a2 + 148) = *(_QWORD *)(v16 + 46);
          }
        }
      }
      v13 = (unsigned int)(v13 + 1);
    }
    if ( !v6 && *a3 > v8 )
      *a3 = v8;
    return v6;
  }
  *a3 = 0;
  return 3221226021LL;
}

```

## disassembly

```asm
0x140042828  push    rbx
0x14004282a  push    rbp
0x14004282b  push    rsi
0x14004282c  push    rdi
0x14004282d  push    r12
0x14004282f  push    r13
0x140042831  push    r14
0x140042833  push    r15
0x140042835  sub     rsp, 38h
0x140042839  mov     rsi, r8
0x14004283c  lea     rdi, NsiBootNicTable
0x140042843  mov     r14, rdx
0x140042846  mov     r15, rcx
0x140042849  xor     ebx, ebx
0x14004284b  mov     rcx, rdi; Object
0x14004284e  xor     r9d, r9d; Alertable
0x140042851  mov     [rsp+78h+Timeout], rbx; Timeout
0x140042856  xor     r8d, r8d; WaitMode
0x140042859  xor     edx, edx; WaitReason
0x14004285b  call    cs:__imp_KeWaitForSingleObject
0x140042862  nop     dword ptr [rax+rax+00h]
0x140042867  cmp     cs:SystemInformation, rbx
0x14004286e  jnz     short loc_1400428A3
0x140042870  call    NsipInitializeBootFirmwareTableData
0x140042875  mov     ebx, eax
0x140042877  test    eax, eax
0x140042879  jns     short loc_1400428A3
0x14004287b  xor     r8d, r8d; Wait
0x14004287e  xor     edx, edx; Increment
0x140042880  mov     rcx, rdi; Event
0x140042883  call    cs:__imp_KeSetEvent
0x14004288a  nop     dword ptr [rax+rax+00h]
0x14004288f  mov     eax, ebx
0x140042891  add     rsp, 38h
0x140042895  pop     r15
0x140042897  pop     r14
0x140042899  pop     r13
0x14004289b  pop     r12
0x14004289d  pop     rdi
0x14004289e  pop     rsi
0x14004289f  pop     rbp
0x1400428a0  pop     rbx
0x1400428a1  retn
0x1400428a3  xor     r8d, r8d; Wait
0x1400428a6  xor     edx, edx; Increment
0x1400428a8  mov     rcx, rdi; Event
0x1400428ab  call    cs:__imp_KeSetEvent
0x1400428b2  nop     dword ptr [rax+rax+00h]
0x1400428b7  mov     eax, [rsi]
0x1400428b9  test    eax, eax
0x1400428bb  jz      short loc_14004288F
0x1400428bd  test    r14, r14
0x1400428c0  jz      loc_14007D940
0x1400428c6  test    r15, r15
0x1400428c9  jz      loc_14007D940
0x1400428cf  cmp     dword ptr [r15+8], 6
0x1400428d4  jnz     loc_14007D940
0x1400428da  mov     ebp, 66h ; 'f'
0x1400428df  cmp     eax, ebp
0x1400428e1  jnb     loc_14007D7BA
0x1400428e7  mov     eax, 0C0000206h
0x1400428ec  jmp     short loc_140042891
0x14007d7ba  xor     edi, edi
0x14007d7bc  cmp     edi, cs:dword_14009ACD8
0x14007d7c2  jnb     loc_14007D84E
0x14007d7c8  mov     rax, cs:qword_14009ACC8
0x14007d7cf  mov     rcx, [rax+rdi*8]
0x14007d7d3  test    rcx, rcx
0x14007d7d6  jz      loc_14007D860
0x14007d7dc  mov     rdx, [r15]; Source2
0x14007d7df  add     rcx, 5Ah ; 'Z'; Source1
0x14007d7e3  mov     r8d, 6; Length
0x14007d7e9  call    cs:__imp_RtlCompareMemory
0x14007d7f0  nop     dword ptr [rax+rax+00h]
0x14007d7f5  cmp     rax, 6
0x14007d7f9  jnz     short loc_14007D860
0x14007d7fb  lfence
0x14007d7fe  mov     rax, cs:qword_14009ACC8
0x14007d805  mov     rcx, [rax+rdi*8]
0x14007d809  movups  xmm0, xmmword ptr [rcx]
0x14007d80c  movups  xmmword ptr [r14], xmm0
0x14007d810  movups  xmm1, xmmword ptr [rcx+10h]
0x14007d814  movups  xmmword ptr [r14+10h], xmm1
0x14007d819  movups  xmm0, xmmword ptr [rcx+20h]
0x14007d81d  movups  xmmword ptr [r14+20h], xmm0
0x14007d822  movups  xmm1, xmmword ptr [rcx+30h]
0x14007d826  movups  xmmword ptr [r14+30h], xmm1
0x14007d82b  movups  xmm0, xmmword ptr [rcx+40h]
0x14007d82f  movups  xmmword ptr [r14+40h], xmm0
0x14007d834  movups  xmm1, xmmword ptr [rcx+50h]
0x14007d838  movups  xmmword ptr [r14+50h], xmm1
0x14007d83d  movsd   xmm0, qword ptr [rcx+5Eh]
0x14007d842  movsd   qword ptr [r14+5Eh], xmm0
0x14007d848  cmp     edi, cs:dword_14009ACD8
0x14007d84e  jnz     short loc_14007D867
0x14007d850  mov     dword ptr [rsi], 0
0x14007d856  mov     eax, 0C0000225h
0x14007d85b  jmp     loc_140042891
0x14007d860  inc     edi
0x14007d862  jmp     loc_14007D7BC
0x14007d867  xor     edi, edi
0x14007d869  xor     r13d, r13d
0x14007d86c  cmp     edi, cs:dword_14009ACDC
0x14007d872  jnb     loc_14007D929
0x14007d878  mov     rax, cs:qword_14009ACD0
0x14007d87f  mov     rcx, [rax+rdi*8]
0x14007d883  movzx   eax, byte ptr [rcx+21h]
0x14007d887  cmp     eax, cs:dword_14009ACD8
0x14007d88d  jnb     loc_14007D918
0x14007d893  mov     ecx, eax
0x14007d895  mov     rax, cs:qword_14009ACC8
0x14007d89c  mov     rcx, [rax+rcx*8]
0x14007d8a0  test    rcx, rcx
0x14007d8a3  jz      short loc_14007D918
0x14007d8a5  mov     rdx, [r15]; Source2
0x14007d8a8  add     rcx, 5Ah ; 'Z'; Source1
0x14007d8ac  mov     r8d, 6; Length
0x14007d8b2  call    cs:__imp_RtlCompareMemory
0x14007d8b9  nop     dword ptr [rax+rax+00h]
0x14007d8be  cmp     rax, 6
0x14007d8c2  jnz     short loc_14007D918
0x14007d8c4  mov     eax, [rsi]
0x14007d8c6  mov     ecx, ebp
0x14007d8c8  add     rcx, 36h ; '6'
0x14007d8cc  cmp     rcx, rax
0x14007d8cf  ja      short loc_14007D91F
0x14007d8d1  mov     rax, cs:qword_14009ACD0
0x14007d8d8  mov     rdx, [rax+rdi*8]
0x14007d8dc  mov     eax, r13d
0x14007d8df  inc     r13d
0x14007d8e2  imul    rcx, rax, 36h ; '6'
0x14007d8e6  movups  xmm0, xmmword ptr [rdx]
0x14007d8e9  add     ebp, 36h ; '6'
0x14007d8ec  movups  xmmword ptr [rcx+r14+66h], xmm0
0x14007d8f2  movups  xmm1, xmmword ptr [rdx+10h]
0x14007d8f6  movups  xmmword ptr [rcx+r14+76h], xmm1
0x14007d8fc  movups  xmm0, xmmword ptr [rdx+20h]
0x14007d900  movups  xmmword ptr [rcx+r14+86h], xmm0
0x14007d909  movsd   xmm1, qword ptr [rdx+2Eh]
0x14007d90e  movsd   qword ptr [rcx+r14+94h], xmm1
0x14007d918  inc     edi
0x14007d91a  jmp     loc_14007D86C
0x14007d91f  mov     ebx, 105h
0x14007d924  jmp     loc_14004288F
0x14007d929  test    ebx, ebx
0x14007d92b  jnz     loc_14004288F
0x14007d931  cmp     [rsi], ebp
0x14007d933  jbe     loc_14004288F
0x14007d939  mov     [rsi], ebp
0x14007d93b  jmp     loc_14004288F
0x14007d940  mov     eax, 0C000000Dh
0x14007d945  jmp     loc_140042891
```
