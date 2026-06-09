# CKSThunkDevice::DispatchCreate(_IRP *,_IRP_STATUS,long *)

- ea: `0x140001e80`
- end: `0x1400021d0`
- name: `?DispatchCreate@CKSThunkDevice@@UEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z`
- size: `848`
- prototype: `__int64 __fastcall(__int64, IRP *, int, _DWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x140001e80`
- `0x140004240`
- `0x140004540`
- `0x14000b400`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400020c1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400020c1`
- `ntoskrnl!_wcsnicmp` at `0x140001f38`
- `ntoskrnl!_wcsnicmp` at `0x140001fa6`
- `ntoskrnl!_wcsnicmp` at `0x140001f38`
- `ntoskrnl!_wcsnicmp` at `0x140001fa6`
- `ntoskrnl!IoIs32bitProcess` at `0x140001ed8`
- `ntoskrnl!IoIs32bitProcess` at `0x140001ed8`
- `ntoskrnl!ExFreePool` at `0x140002158`
- `ntoskrnl!ExFreePool` at `0x140002158`
- `ntoskrnl!IoIsInitiator32bitProcess` at `0x140001eeb`
- `ntoskrnl!IoIsInitiator32bitProcess` at `0x140001eeb`

## pseudocode

```c
__int64 __fastcall CKSThunkDevice::DispatchCreate(__int64 a1, IRP *a2, int a3, _DWORD *a4)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  PFILE_OBJECT FileObject; // r9
  __int64 v9; // r8
  PFILE_OBJECT v10; // r13
  __int64 v11; // r8
  unsigned int v12; // esi
  __int64 v13; // r15
  PWSTR Buffer; // r9
  size_t v15; // r12
  __int128 v16; // xmm1
  __int64 v17; // rcx
  __int128 v18; // xmm0
  WCHAR *v19; // r11
  __int128 v20; // xmm6
  unsigned int v21; // r15d
  unsigned __int64 Length; // r10
  __int64 v23; // r8
  __int64 v24; // rax
  unsigned int v25; // eax
  unsigned int v26; // ecx
  char *PoolWithTag; // rax
  char *v28; // rsi
  size_t Size; // [rsp+28h] [rbp-99h]
  __int64 v30; // [rsp+30h] [rbp-91h]
  WCHAR *Src; // [rsp+38h] [rbp-89h]
  __m256i v32; // [rsp+58h] [rbp-69h]
  __int128 v33; // [rsp+78h] [rbp-49h]
  __int64 v34; // [rsp+88h] [rbp-39h]
  __int128 v35; // [rsp+B0h] [rbp-11h]
  int v36; // [rsp+138h] [rbp+77h]
  USHORT v37; // [rsp+138h] [rbp+77h]

  if ( a3 )
    return CKernelFilterDevice::DispatchCreate();
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->FileObject->RelatedFileObject )
  {
    if ( !IoIs32bitProcess(a2) && !(unsigned __int8)IoIsInitiator32bitProcess(a2) )
    {
      FileObject = CurrentStackLocation->FileObject;
      v9 = -1;
      do
        ++v9;
      while ( a146f1a80479111[v9] );
      if ( FileObject->FileName.Length >= (unsigned __int64)(unsigned int)(2 * v9 + 74) + 64
        && !_wcsnicmp(FileObject->FileName.Buffer, L"{146F1A80-4791-11D0-A5D6-28DB04C10000}", (unsigned int)v9) )
      {
        return CKernelFilterDevice::DispatchCreate();
      }
      return 1;
    }
    v10 = CurrentStackLocation->FileObject;
    v11 = -1;
    do
      ++v11;
    while ( a146f1a80479111[v11] );
    v12 = 2 * v11 + 66;
    v36 = 2 * v11;
    if ( v10->FileName.Length >= (unsigned __int64)v12 + 64 )
    {
      v13 = (unsigned int)v11;
      v30 = (unsigned int)v11;
      if ( !_wcsnicmp(v10->FileName.Buffer, L"{146F1A80-4791-11D0-A5D6-28DB04C10000}", (unsigned int)v11) )
      {
        Buffer = v10->FileName.Buffer;
        v15 = 2 * v13;
        v16 = *(_OWORD *)&Buffer[v13 + 9];
        v17 = *(_QWORD *)&Buffer[v13 + 29];
        v18 = *(_OWORD *)&Buffer[v13 + 17];
        v19 = &Buffer[v13 + 33];
        v20 = *(_OWORD *)&Buffer[v13 + 1];
        Src = v19;
        *(_QWORD *)&v35 = *((_QWORD *)&v16 + 1);
        v21 = *(_DWORD *)v19;
        *((_QWORD *)&v35 + 1) = v18;
        if ( (unsigned int)(*(_DWORD *)v19 - 64) <= 0x3A58 )
        {
          Length = v10->FileName.Length;
          if ( (unsigned int)Length < v21 + v12 )
            goto LABEL_30;
          if ( (*((_DWORD *)v19 + 1) & 2) != 0 )
          {
            v23 = (v21 + 7) & 0xFFFFFFF8;
            if ( Length < (unsigned __int64)((unsigned int)v23 + v12) + 8 )
              goto LABEL_30;
            v24 = *(_QWORD *)((char *)v19 + v23);
            if ( (unsigned int)v24 < 8 )
              goto LABEL_30;
            v21 = v23 + v24;
            if ( (int)v23 + (int)v24 < (unsigned int)v23 )
              goto LABEL_31;
            if ( (unsigned int)Length - v12 < v21 )
            {
LABEL_30:
              *a4 = -1073741823;
              return 0;
            }
          }
          *(_QWORD *)&v33 = *(unsigned int *)&Buffer[v15 / 2 + 25];
          *((_QWORD *)&v33 + 1) = *(unsigned int *)&Buffer[v15 / 2 + 27];
          v25 = v36 + 74;
          v34 = v17;
          v32.m256i_i64[0] = v16;
          v26 = v36 + 74 + v21;
          v32.m256i_i64[3] = *((_QWORD *)&v18 + 1);
          v37 = v36 + 74 + v21;
          *(_OWORD *)&v32.m256i_u64[1] = v35;
          if ( v26 >= v25 && v26 <= 0xFFFF )
          {
            Size = v26;
            PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1536, v26, 0x6474534Bu);
            v28 = PoolWithTag;
            if ( ExPoolZeroingNativelySupported )
            {
              if ( PoolWithTag )
                goto LABEL_27;
            }
            else if ( PoolWithTag )
            {
              memset(PoolWithTag, 0, Size);
LABEL_27:
              memmove(v28, L"{146F1A80-4791-11D0-A5D6-28DB04C10000}", v15);
              *(_OWORD *)&v28[v15 + 2] = v20;
              *(_OWORD *)&v28[v15 + 18] = *(_OWORD *)v32.m256i_i8;
              *(_WORD *)&v28[v15] = 92;
              *(_OWORD *)&v28[v15 + 34] = *(_OWORD *)&v32.m256i_u64[2];
              *(_OWORD *)&v28[v15 + 50] = v33;
              *(_QWORD *)&v28[v15 + 66] = v34;
              memmove(&v28[2 * v30 + 74], Src, v21);
              ExFreePool(v10->FileName.Buffer);
              v10->FileName.MaximumLength = v37;
              v10->FileName.Length = v37;
              v10->FileName.Buffer = (PWSTR)v28;
              return CKernelFilterDevice::DispatchCreate();
            }
            *a4 = -1073741670;
            return 0;
          }
        }
LABEL_31:
        *a4 = -1073741811;
        return 0;
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x140001e80  mov     rax, rsp
0x140001e83  mov     [rax+10h], rbx
0x140001e87  mov     [rax+8], rcx
0x140001e8b  push    rbp
0x140001e8c  push    rsi
0x140001e8d  push    rdi
0x140001e8e  push    r12
0x140001e90  push    r13
0x140001e92  push    r14
0x140001e94  push    r15
0x140001e96  lea     rbp, [rax-5Fh]
0x140001e9a  sub     rsp, 0E0h
0x140001ea1  xor     r12d, r12d
0x140001ea4  movaps  xmmword ptr [rax-48h], xmm6
0x140001ea8  mov     rbx, r9
0x140001eab  mov     rdi, rdx
0x140001eae  mov     r15, rcx
0x140001eb1  test    r8d, r8d
0x140001eb4  jz      short loc_140001EC0
0x140001eb6  call    ?DispatchCreate@CKernelFilterDevice@@MEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z; CKernelFilterDevice::DispatchCreate(_IRP *,_IRP_STATUS,long *)
0x140001ebb  jmp     loc_1400021AF
0x140001ec0  mov     rsi, [rdx+0B8h]
0x140001ec7  mov     rax, [rsi+30h]
0x140001ecb  cmp     [rax+40h], r12
0x140001ecf  jz      loc_1400021AA
0x140001ed5  mov     rcx, rdi; Irp
0x140001ed8  call    cs:__imp_IoIs32bitProcess
0x140001edf  nop     dword ptr [rax+rax+00h]
0x140001ee4  test    al, al
0x140001ee6  jnz     short loc_140001F5D
0x140001ee8  mov     rcx, rdi
0x140001eeb  call    cs:__imp_IoIsInitiator32bitProcess
0x140001ef2  nop     dword ptr [rax+rax+00h]
0x140001ef7  test    al, al
0x140001ef9  jnz     short loc_140001F5D
0x140001efb  mov     r9, [rsi+30h]
0x140001eff  lea     r14, a146f1a80479111; "{146F1A80-4791-11D0-A5D6-28DB04C10000}"
0x140001f06  or      r8, 0FFFFFFFFFFFFFFFFh
0x140001f0a  inc     r8
0x140001f0d  cmp     [r14+r8*2], r12w
0x140001f12  jnz     short loc_140001F0A
0x140001f14  movzx   eax, word ptr [r9+58h]
0x140001f19  lea     ecx, ds:4Ah[r8*2]
0x140001f21  add     rcx, 40h ; '@'
0x140001f25  cmp     rax, rcx
0x140001f28  jb      loc_1400021AA
0x140001f2e  mov     rcx, [r9+60h]; Str1
0x140001f32  mov     rdx, r14; Str2
0x140001f35  mov     r8d, r8d; MaxCount
0x140001f38  call    cs:__imp__wcsnicmp
0x140001f3f  nop     dword ptr [rax+rax+00h]
0x140001f44  test    eax, eax
0x140001f46  jnz     loc_1400021AA
0x140001f4c  mov     r9, rbx
0x140001f4f  xor     r8d, r8d
0x140001f52  mov     rdx, rdi
0x140001f55  mov     rcx, r15
0x140001f58  jmp     loc_140001EB6
0x140001f5d  mov     r13, [rsi+30h]
0x140001f61  lea     r14, a146f1a80479111; "{146F1A80-4791-11D0-A5D6-28DB04C10000}"
0x140001f68  or      r8, 0FFFFFFFFFFFFFFFFh
0x140001f6c  inc     r8
0x140001f6f  cmp     [r14+r8*2], r12w
0x140001f74  jnz     short loc_140001F6C
0x140001f76  lea     eax, [r8+r8]
0x140001f7a  lea     esi, [rax+42h]
0x140001f7d  mov     [rbp+57h+arg_10], eax
0x140001f80  movzx   eax, word ptr [r13+58h]
0x140001f85  mov     ecx, esi
0x140001f87  add     rcx, 40h ; '@'
0x140001f8b  cmp     rax, rcx
0x140001f8e  jb      loc_1400021AA
0x140001f94  mov     rcx, [r13+60h]; Str1
0x140001f98  mov     rdx, r14; Str2
0x140001f9b  mov     r15d, r8d
0x140001f9e  mov     r8d, r8d; MaxCount
0x140001fa1  mov     [rsp+110h+var_E8], r15
0x140001fa6  call    cs:__imp__wcsnicmp
0x140001fad  nop     dword ptr [rax+rax+00h]
0x140001fb2  test    eax, eax
0x140001fb4  jnz     loc_1400021AA
0x140001fba  mov     r9, [r13+60h]
0x140001fbe  lea     r12, [r15+r15]
0x140001fc2  movups  xmm1, xmmword ptr [r12+r9+12h]
0x140001fc8  mov     rcx, [r12+r9+3Ah]
0x140001fcd  lea     r11, [r9+42h]
0x140001fd1  movups  xmm0, xmmword ptr [r12+r9+22h]
0x140001fd7  add     r11, r12
0x140001fda  movups  xmm6, xmmword ptr [r12+r9+2]
0x140001fe0  mov     [rsp+110h+Src], r11
0x140001fe5  movaps  [rbp+57h+var_70], xmm1
0x140001fe9  mov     r15d, [r11]
0x140001fec  movaps  [rbp+57h+var_60], xmm0
0x140001ff0  lea     eax, [r15-40h]
0x140001ff4  cmp     eax, 3A58h
0x140001ff9  ja      loc_1400021A0
0x140001fff  movzx   r10d, word ptr [r13+58h]
0x140002004  lea     eax, [r15+rsi]
0x140002008  mov     edx, [r11+4]
0x14000200c  cmp     r10d, eax
0x14000200f  jb      loc_140002198
0x140002015  test    dl, 2
0x140002018  jz      short loc_140002059
0x14000201a  lea     r8d, [r15+7]
0x14000201e  and     r8d, 0FFFFFFF8h
0x140002022  lea     edx, [r8+rsi]
0x140002026  add     rdx, 8
0x14000202a  cmp     r10, rdx
0x14000202d  jb      loc_140002198
0x140002033  mov     rax, [r8+r11]
0x140002037  cmp     eax, 8
0x14000203a  jb      loc_140002198
0x140002040  lea     r15d, [r8+rax]
0x140002044  cmp     r15d, r8d
0x140002047  jb      loc_1400021A0
0x14000204d  sub     r10d, esi
0x140002050  cmp     r10d, r15d
0x140002053  jb      loc_140002198
0x140002059  mov     eax, [r12+r9+32h]
0x14000205e  movups  xmm0, [rbp+57h+var_70+8]
0x140002062  mov     dword ptr [rbp+57h+var_A0], eax
0x140002065  mov     eax, [r12+r9+36h]
0x14000206a  mov     qword ptr [rbp+57h+var_A0+8], rax
0x14000206e  mov     eax, [rbp+57h+arg_10]
0x140002071  add     eax, 4Ah ; 'J'
0x140002074  mov     [rbp+57h+var_90], rcx
0x140002078  movsd   qword ptr [rbp+57h+var_C0], xmm1
0x14000207d  movsd   xmm1, qword ptr [rbp+57h+var_60+8]
0x140002082  mov     dword ptr [rbp+57h+var_A0+4], 0
0x140002089  lea     ecx, [rax+r15]
0x14000208d  movsd   [rbp+57h+var_A8], xmm1
0x140002092  mov     [rbp+57h+arg_10], ecx
0x140002095  movups  [rbp+57h+var_C0+8], xmm0
0x140002099  cmp     ecx, eax
0x14000209b  jb      loc_1400021A0
0x1400020a1  cmp     ecx, 0FFFFh
0x1400020a7  ja      loc_1400021A0
0x1400020ad  mov     eax, ecx
0x1400020af  mov     r8d, 6474534Bh; Tag
0x1400020b5  mov     edx, ecx; NumberOfBytes
0x1400020b7  mov     ecx, 600h; PoolType
0x1400020bc  mov     [rsp+110h+Size], rax
0x1400020c1  call    cs:__imp_ExAllocatePoolWithTag
0x1400020c8  nop     dword ptr [rax+rax+00h]
0x1400020cd  cmp     cs:ExPoolZeroingNativelySupported, 0
0x1400020d4  mov     rsi, rax
0x1400020d7  jnz     loc_140002187
0x1400020dd  test    rax, rax
0x1400020e0  jz      loc_140002190
0x1400020e6  mov     r8, [rsp+110h+Size]; Size
0x1400020eb  xor     edx, edx; Val
0x1400020ed  mov     rcx, rax; void *
0x1400020f0  call    memset
0x1400020f5  mov     r8, r12; Size
0x1400020f8  mov     rdx, r14; Src
0x1400020fb  mov     rcx, rsi; void *
0x1400020fe  call    memmove
0x140002103  movaps  xmm0, [rbp+57h+var_C0]
0x140002107  movaps  xmm1, xmmword ptr [rbp-59h]
0x14000210b  mov     rax, [rsp+110h+var_E8]
0x140002110  mov     rdx, [rsp+110h+Src]; Src
0x140002115  add     rax, 25h ; '%'
0x140002119  movups  xmmword ptr [r12+rsi+2], xmm6
0x14000211f  mov     r8d, r15d; Size
0x140002122  movups  xmmword ptr [r12+rsi+12h], xmm0
0x140002128  lea     rcx, [rsi+rax*2]; void *
0x14000212c  mov     word ptr [r12+rsi], 5Ch ; '\'
0x140002133  movaps  xmm0, [rbp+57h+var_A0]
0x140002137  movups  xmmword ptr [r12+rsi+22h], xmm1
0x14000213d  movsd   xmm1, [rbp+57h+var_90]
0x140002142  movups  xmmword ptr [r12+rsi+32h], xmm0
0x140002148  movsd   qword ptr [r12+rsi+42h], xmm1
0x14000214f  call    memmove
0x140002154  mov     rcx, [r13+60h]; P
0x140002158  call    cs:__imp_ExFreePool
0x14000215f  nop     dword ptr [rax+rax+00h]
0x140002164  mov     eax, [rbp+57h+arg_10]
0x140002167  mov     r9, rbx
0x14000216a  mov     rcx, [rbp+57h+arg_0]
0x14000216e  xor     r8d, r8d
0x140002171  mov     [r13+5Ah], ax
0x140002176  mov     rdx, rdi
0x140002179  mov     [r13+58h], ax
0x14000217e  mov     [r13+60h], rsi
0x140002182  jmp     loc_140001EB6
0x140002187  test    rsi, rsi
0x14000218a  jnz     loc_1400020F5
0x140002190  mov     dword ptr [rbx], 0C000009Ah
0x140002196  jmp     short loc_1400021A6
0x140002198  mov     dword ptr [rbx], 0C0000001h
0x14000219e  jmp     short loc_1400021A6
0x1400021a0  mov     dword ptr [rbx], 0C000000Dh
0x1400021a6  xor     eax, eax
0x1400021a8  jmp     short loc_1400021AF
0x1400021aa  mov     eax, 1
0x1400021af  lea     r11, [rsp+110h+var_30]
0x1400021b7  mov     rbx, [r11+48h]
0x1400021bb  movaps  xmm6, xmmword ptr [r11-10h]
0x1400021c0  mov     rsp, r11
0x1400021c3  pop     r15
0x1400021c5  pop     r14
0x1400021c7  pop     r13
0x1400021c9  pop     r12
0x1400021cb  pop     rdi
0x1400021cc  pop     rsi
0x1400021cd  pop     rbp
0x1400021ce  retn
```
