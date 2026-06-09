# CKSThunkDevice::DispatchCreate(_IRP *,_IRP_STATUS,long *)

- ea: `0x140001e00`
- end: `0x140002150`
- name: `?DispatchCreate@CKSThunkDevice@@UEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z`
- size: `848`
- prototype: `__int64 __fastcall(__int64, IRP *, int, _DWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x140001e00`
- `0x1400037c0`
- `0x140003ac0`
- `0x14000a400`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140002041`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140002041`
- `ntoskrnl!_wcsnicmp` at `0x140001eb8`
- `ntoskrnl!_wcsnicmp` at `0x140001f26`
- `ntoskrnl!_wcsnicmp` at `0x140001eb8`
- `ntoskrnl!_wcsnicmp` at `0x140001f26`
- `ntoskrnl!IoIs32bitProcess` at `0x140001e58`
- `ntoskrnl!IoIs32bitProcess` at `0x140001e58`
- `ntoskrnl!ExFreePool` at `0x1400020d8`
- `ntoskrnl!ExFreePool` at `0x1400020d8`
- `ntoskrnl!IoIsInitiator32bitProcess` at `0x140001e6b`
- `ntoskrnl!IoIsInitiator32bitProcess` at `0x140001e6b`

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
0x140001e00  mov     rax, rsp
0x140001e03  mov     [rax+10h], rbx
0x140001e07  mov     [rax+8], rcx
0x140001e0b  push    rbp
0x140001e0c  push    rsi
0x140001e0d  push    rdi
0x140001e0e  push    r12
0x140001e10  push    r13
0x140001e12  push    r14
0x140001e14  push    r15
0x140001e16  lea     rbp, [rax-5Fh]
0x140001e1a  sub     rsp, 0E0h
0x140001e21  xor     r12d, r12d
0x140001e24  movaps  xmmword ptr [rax-48h], xmm6
0x140001e28  mov     rbx, r9
0x140001e2b  mov     rdi, rdx
0x140001e2e  mov     r15, rcx
0x140001e31  test    r8d, r8d
0x140001e34  jz      short loc_140001E40
0x140001e36  call    ?DispatchCreate@CKernelFilterDevice@@MEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z; CKernelFilterDevice::DispatchCreate(_IRP *,_IRP_STATUS,long *)
0x140001e3b  jmp     loc_14000212F
0x140001e40  mov     rsi, [rdx+0B8h]
0x140001e47  mov     rax, [rsi+30h]
0x140001e4b  cmp     [rax+40h], r12
0x140001e4f  jz      loc_14000212A
0x140001e55  mov     rcx, rdi; Irp
0x140001e58  call    cs:__imp_IoIs32bitProcess
0x140001e5f  nop     dword ptr [rax+rax+00h]
0x140001e64  test    al, al
0x140001e66  jnz     short loc_140001EDD
0x140001e68  mov     rcx, rdi
0x140001e6b  call    cs:__imp_IoIsInitiator32bitProcess
0x140001e72  nop     dword ptr [rax+rax+00h]
0x140001e77  test    al, al
0x140001e79  jnz     short loc_140001EDD
0x140001e7b  mov     r9, [rsi+30h]
0x140001e7f  lea     r14, a146f1a80479111; "{146F1A80-4791-11D0-A5D6-28DB04C10000}"
0x140001e86  or      r8, 0FFFFFFFFFFFFFFFFh
0x140001e8a  inc     r8
0x140001e8d  cmp     [r14+r8*2], r12w
0x140001e92  jnz     short loc_140001E8A
0x140001e94  movzx   eax, word ptr [r9+58h]
0x140001e99  lea     ecx, ds:4Ah[r8*2]
0x140001ea1  add     rcx, 40h ; '@'
0x140001ea5  cmp     rax, rcx
0x140001ea8  jb      loc_14000212A
0x140001eae  mov     rcx, [r9+60h]; Str1
0x140001eb2  mov     rdx, r14; Str2
0x140001eb5  mov     r8d, r8d; MaxCount
0x140001eb8  call    cs:__imp__wcsnicmp
0x140001ebf  nop     dword ptr [rax+rax+00h]
0x140001ec4  test    eax, eax
0x140001ec6  jnz     loc_14000212A
0x140001ecc  mov     r9, rbx
0x140001ecf  xor     r8d, r8d
0x140001ed2  mov     rdx, rdi
0x140001ed5  mov     rcx, r15
0x140001ed8  jmp     loc_140001E36
0x140001edd  mov     r13, [rsi+30h]
0x140001ee1  lea     r14, a146f1a80479111; "{146F1A80-4791-11D0-A5D6-28DB04C10000}"
0x140001ee8  or      r8, 0FFFFFFFFFFFFFFFFh
0x140001eec  inc     r8
0x140001eef  cmp     [r14+r8*2], r12w
0x140001ef4  jnz     short loc_140001EEC
0x140001ef6  lea     eax, [r8+r8]
0x140001efa  lea     esi, [rax+42h]
0x140001efd  mov     [rbp+57h+arg_10], eax
0x140001f00  movzx   eax, word ptr [r13+58h]
0x140001f05  mov     ecx, esi
0x140001f07  add     rcx, 40h ; '@'
0x140001f0b  cmp     rax, rcx
0x140001f0e  jb      loc_14000212A
0x140001f14  mov     rcx, [r13+60h]; Str1
0x140001f18  mov     rdx, r14; Str2
0x140001f1b  mov     r15d, r8d
0x140001f1e  mov     r8d, r8d; MaxCount
0x140001f21  mov     [rsp+110h+var_E8], r15
0x140001f26  call    cs:__imp__wcsnicmp
0x140001f2d  nop     dword ptr [rax+rax+00h]
0x140001f32  test    eax, eax
0x140001f34  jnz     loc_14000212A
0x140001f3a  mov     r9, [r13+60h]
0x140001f3e  lea     r12, [r15+r15]
0x140001f42  movups  xmm1, xmmword ptr [r12+r9+12h]
0x140001f48  mov     rcx, [r12+r9+3Ah]
0x140001f4d  lea     r11, [r9+42h]
0x140001f51  movups  xmm0, xmmword ptr [r12+r9+22h]
0x140001f57  add     r11, r12
0x140001f5a  movups  xmm6, xmmword ptr [r12+r9+2]
0x140001f60  mov     [rsp+110h+Src], r11
0x140001f65  movaps  [rbp+57h+var_70], xmm1
0x140001f69  mov     r15d, [r11]
0x140001f6c  movaps  [rbp+57h+var_60], xmm0
0x140001f70  lea     eax, [r15-40h]
0x140001f74  cmp     eax, 3A58h
0x140001f79  ja      loc_140002120
0x140001f7f  movzx   r10d, word ptr [r13+58h]
0x140001f84  lea     eax, [r15+rsi]
0x140001f88  mov     edx, [r11+4]
0x140001f8c  cmp     r10d, eax
0x140001f8f  jb      loc_140002118
0x140001f95  test    dl, 2
0x140001f98  jz      short loc_140001FD9
0x140001f9a  lea     r8d, [r15+7]
0x140001f9e  and     r8d, 0FFFFFFF8h
0x140001fa2  lea     edx, [r8+rsi]
0x140001fa6  add     rdx, 8
0x140001faa  cmp     r10, rdx
0x140001fad  jb      loc_140002118
0x140001fb3  mov     rax, [r8+r11]
0x140001fb7  cmp     eax, 8
0x140001fba  jb      loc_140002118
0x140001fc0  lea     r15d, [r8+rax]
0x140001fc4  cmp     r15d, r8d
0x140001fc7  jb      loc_140002120
0x140001fcd  sub     r10d, esi
0x140001fd0  cmp     r10d, r15d
0x140001fd3  jb      loc_140002118
0x140001fd9  mov     eax, [r12+r9+32h]
0x140001fde  movups  xmm0, [rbp+57h+var_70+8]
0x140001fe2  mov     dword ptr [rbp+57h+var_A0], eax
0x140001fe5  mov     eax, [r12+r9+36h]
0x140001fea  mov     qword ptr [rbp+57h+var_A0+8], rax
0x140001fee  mov     eax, [rbp+57h+arg_10]
0x140001ff1  add     eax, 4Ah ; 'J'
0x140001ff4  mov     [rbp+57h+var_90], rcx
0x140001ff8  movsd   qword ptr [rbp+57h+var_C0], xmm1
0x140001ffd  movsd   xmm1, qword ptr [rbp+57h+var_60+8]
0x140002002  mov     dword ptr [rbp+57h+var_A0+4], 0
0x140002009  lea     ecx, [rax+r15]
0x14000200d  movsd   [rbp+57h+var_A8], xmm1
0x140002012  mov     [rbp+57h+arg_10], ecx
0x140002015  movups  [rbp+57h+var_C0+8], xmm0
0x140002019  cmp     ecx, eax
0x14000201b  jb      loc_140002120
0x140002021  cmp     ecx, 0FFFFh
0x140002027  ja      loc_140002120
0x14000202d  mov     eax, ecx
0x14000202f  mov     r8d, 6474534Bh; Tag
0x140002035  mov     edx, ecx; NumberOfBytes
0x140002037  mov     ecx, 600h; PoolType
0x14000203c  mov     [rsp+110h+Size], rax
0x140002041  call    cs:__imp_ExAllocatePoolWithTag
0x140002048  nop     dword ptr [rax+rax+00h]
0x14000204d  cmp     cs:ExPoolZeroingNativelySupported, 0
0x140002054  mov     rsi, rax
0x140002057  jnz     loc_140002107
0x14000205d  test    rax, rax
0x140002060  jz      loc_140002110
0x140002066  mov     r8, [rsp+110h+Size]; Size
0x14000206b  xor     edx, edx; Val
0x14000206d  mov     rcx, rax; void *
0x140002070  call    memset
0x140002075  mov     r8, r12; Size
0x140002078  mov     rdx, r14; Src
0x14000207b  mov     rcx, rsi; void *
0x14000207e  call    memmove
0x140002083  movaps  xmm0, [rbp+57h+var_C0]
0x140002087  movaps  xmm1, xmmword ptr [rbp-59h]
0x14000208b  mov     rax, [rsp+110h+var_E8]
0x140002090  mov     rdx, [rsp+110h+Src]; Src
0x140002095  add     rax, 25h ; '%'
0x140002099  movups  xmmword ptr [r12+rsi+2], xmm6
0x14000209f  mov     r8d, r15d; Size
0x1400020a2  movups  xmmword ptr [r12+rsi+12h], xmm0
0x1400020a8  lea     rcx, [rsi+rax*2]; void *
0x1400020ac  mov     word ptr [r12+rsi], 5Ch ; '\'
0x1400020b3  movaps  xmm0, [rbp+57h+var_A0]
0x1400020b7  movups  xmmword ptr [r12+rsi+22h], xmm1
0x1400020bd  movsd   xmm1, [rbp+57h+var_90]
0x1400020c2  movups  xmmword ptr [r12+rsi+32h], xmm0
0x1400020c8  movsd   qword ptr [r12+rsi+42h], xmm1
0x1400020cf  call    memmove
0x1400020d4  mov     rcx, [r13+60h]; P
0x1400020d8  call    cs:__imp_ExFreePool
0x1400020df  nop     dword ptr [rax+rax+00h]
0x1400020e4  mov     eax, [rbp+57h+arg_10]
0x1400020e7  mov     r9, rbx
0x1400020ea  mov     rcx, [rbp+57h+arg_0]
0x1400020ee  xor     r8d, r8d
0x1400020f1  mov     [r13+5Ah], ax
0x1400020f6  mov     rdx, rdi
0x1400020f9  mov     [r13+58h], ax
0x1400020fe  mov     [r13+60h], rsi
0x140002102  jmp     loc_140001E36
0x140002107  test    rsi, rsi
0x14000210a  jnz     loc_140002075
0x140002110  mov     dword ptr [rbx], 0C000009Ah
0x140002116  jmp     short loc_140002126
0x140002118  mov     dword ptr [rbx], 0C0000001h
0x14000211e  jmp     short loc_140002126
0x140002120  mov     dword ptr [rbx], 0C000000Dh
0x140002126  xor     eax, eax
0x140002128  jmp     short loc_14000212F
0x14000212a  mov     eax, 1
0x14000212f  lea     r11, [rsp+110h+var_30]
0x140002137  mov     rbx, [r11+48h]
0x14000213b  movaps  xmm6, xmmword ptr [r11-10h]
0x140002140  mov     rsp, r11
0x140002143  pop     r15
0x140002145  pop     r14
0x140002147  pop     r13
0x140002149  pop     r12
0x14000214b  pop     rdi
0x14000214c  pop     rsi
0x14000214d  pop     rbp
0x14000214e  retn
```
