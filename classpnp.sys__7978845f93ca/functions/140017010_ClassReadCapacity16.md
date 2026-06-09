# ClassReadCapacity16

- ea: `0x140017010`
- end: `0x1400171c4`
- name: `ClassReadCapacity16`
- size: `436`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14001e86c`

## callees

- `0x14000de10`
- `0x14000f3e0`
- `0x140017010`
- `0x140020258`
- `0x140036db4`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140040ec8`
- `ntoskrnl!ExAllocatePool2` at `0x140040ec8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040fca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040fca`

## pseudocode

```c
__int64 __fastcall ClassReadCapacity16(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  int v5; // ecx
  __int64 i; // rdx
  unsigned __int64 v7; // rcx
  _BYTE *v8; // rdx
  unsigned int v9; // r11d
  __int64 v10; // r8
  __int64 v11; // rcx
  unsigned __int64 v12; // r9
  __int64 v13; // r10
  int v14; // ecx
  int v15; // ecx
  int v16; // eax
  bool v17; // zf
  unsigned int v18; // r10d
  __int64 v19; // rcx
  unsigned __int64 v20; // r8
  __int64 v21; // r9
  int v22; // ecx
  __int64 v23; // r8
  void *Pool2; // r14
  unsigned int v25; // ebp
  int Capacity16Data; // esi
  char v27; // al
  __int64 v28; // rax

  result = *(unsigned int *)(*(_QWORD *)(a1 + 1152) + 100LL);
  if ( (_DWORD)result == -1 )
  {
    if ( (unsigned __int8)ClasspIsObsoletePortDriver(a1) )
    {
      *(_DWORD *)(v23 + 100) = -1073741822;
      return 3221225474LL;
    }
    Pool2 = (void *)ExAllocatePool2(64, 32, 876831571);
    if ( !Pool2 )
      return 3221225626LL;
    if ( *(_BYTE *)(*(_QWORD *)(a1 + 528) + 30LL) == 1 )
    {
      v25 = 0;
      Capacity16Data = InitializeStorageRequestBlock(a2);
      if ( Capacity16Data < 0 )
        goto LABEL_52;
      *(_DWORD *)(a2 + 20) = 0;
    }
    else
    {
      memset((void *)(a2 + 3), 0, 0x55u);
      *(_WORD *)a2 = 88;
      *(_BYTE *)(a2 + 2) = 0;
    }
    v16 = *(_DWORD *)(a1 + 584);
    if ( *(_BYTE *)(a2 + 2) == 40 )
    {
      v17 = *(_DWORD *)(a2 + 20) == 0;
      *(_DWORD *)(a2 + 40) = v16;
      *(_DWORD *)(a2 + 32) = 255;
      *(_WORD *)(a2 + 38) = 32;
      *(_DWORD *)(a2 + 24) = *(_DWORD *)(a1 + 592);
      if ( v17 )
      {
        v18 = *(_DWORD *)(a2 + 56);
        for ( i = 0; (unsigned int)i < v18; i = (unsigned int)(i + 1) )
        {
          v19 = *(unsigned int *)(a2 + 4 * i + 120);
          if ( (unsigned int)v19 < 0x80 )
            continue;
          v20 = *(unsigned int *)(a2 + 16);
          if ( (unsigned int)v19 >= (unsigned int)v20 )
            continue;
          v21 = (unsigned int)v19;
          v22 = *(_DWORD *)(v19 + a2);
          if ( v22 == 64 )
          {
            v7 = v21 + 40;
          }
          else
          {
            v5 = v22 - 65;
            if ( v5 )
            {
              if ( v5 == 1 && v21 + 40 <= v20 )
                break;
              continue;
            }
            v7 = v21 + 56;
          }
          if ( v7 <= v20 )
          {
            *(_BYTE *)(v21 + a2 + 10) = 16;
            break;
          }
        }
      }
    }
    else
    {
      *(_DWORD *)(a2 + 20) = v16;
      *(_WORD *)(a2 + 8) = 8447;
      *(_DWORD *)(a2 + 12) = *(_DWORD *)(a1 + 592);
      *(_BYTE *)(a2 + 10) = 16;
    }
    if ( *(_BYTE *)(a2 + 2) != 40 )
    {
      v8 = (_BYTE *)(a2 + 72);
      goto LABEL_47;
    }
    v8 = 0;
    if ( !*(_DWORD *)(a2 + 20) )
    {
      v9 = *(_DWORD *)(a2 + 56);
      if ( v9 )
      {
        v10 = 0;
        do
        {
          v11 = *(unsigned int *)(a2 + 4 * v10 + 120);
          if ( (unsigned int)v11 >= 0x80 )
          {
            v12 = *(unsigned int *)(a2 + 16);
            if ( (unsigned int)v11 < (unsigned int)v12 )
            {
              v13 = (unsigned int)v11;
              v14 = *(_DWORD *)(v11 + a2);
              if ( v14 == 64 )
              {
                if ( v13 + 40 <= v12 )
                  goto LABEL_26;
              }
              else
              {
                v15 = v14 - 65;
                if ( v15 )
                {
                  if ( v15 == 1 && v13 + 40 <= v12 )
                  {
                    v8 = (_BYTE *)(v13 + a2 + 32);
                    if ( !*(_DWORD *)(v13 + a2 + 12) )
                      v8 = 0;
                    break;
                  }
                }
                else if ( v13 + 56 <= v12 )
                {
LABEL_26:
                  if ( *(_BYTE *)(v13 + a2 + 10) )
                    v8 = (_BYTE *)(v13 + a2 + 24);
                  break;
                }
              }
            }
          }
          v10 = (unsigned int)(v10 + 1);
        }
        while ( (unsigned int)v10 < v9 );
      }
    }
LABEL_47:
    v27 = v8[1];
    *v8 = -98;
    v8[13] = 32;
    v8[1] = v27 & 0xE0 | 0x10;
    Capacity16Data = ClassSendSrbSynchronous(*(PDEVICE_OBJECT *)(a1 + 8), (PSCSI_REQUEST_BLOCK)a2, Pool2, 0x20u, 0);
    v28 = 60;
    if ( *(_BYTE *)(a2 + 2) != 40 )
      v28 = 16;
    v25 = *(_DWORD *)(v28 + a2);
    if ( Capacity16Data >= 0 )
    {
      if ( v25 < 0x10 )
      {
        Capacity16Data = -1073741820;
LABEL_57:
        *(_DWORD *)(*(_QWORD *)(a1 + 1152) + 100LL) = Capacity16Data;
        ExFreePoolWithTag(Pool2, 0);
        return (unsigned int)Capacity16Data;
      }
LABEL_56:
      Capacity16Data = InterpretReadCapacity16Data(a1, Pool2);
      goto LABEL_57;
    }
LABEL_52:
    if ( Capacity16Data != -1073741764 || v25 >= 0x20 )
      goto LABEL_57;
    goto LABEL_56;
  }
  return result;
}

```

## disassembly

```asm
0x140017010  push    rbx
0x140017012  push    rdi
0x140017013  sub     rsp, 38h
0x140017017  mov     r8, [rcx+480h]
0x14001701e  mov     rdi, rdx
0x140017021  mov     rbx, rcx
0x140017024  mov     eax, [r8+64h]
0x140017028  cmp     eax, 0FFFFFFFFh
0x14001702b  jz      loc_1400171A5
0x140017031  add     rsp, 38h
0x140017035  pop     rdi
0x140017036  pop     rbx
0x140017037  retn
0x140017039  sub     ecx, 41h ; 'A'
0x14001703c  jz      short loc_140017059
0x14001703e  cmp     ecx, 1
0x140017041  jnz     short loc_14001704C
0x140017043  lea     rcx, [r9+28h]
0x140017047  cmp     rcx, r8
0x14001704a  jbe     short loc_140017080
0x14001704c  inc     edx
0x14001704e  cmp     edx, r10d
0x140017051  jb      loc_140017170
0x140017057  jmp     short loc_140017080
0x140017059  lea     rcx, [r9+38h]
0x14001705d  cmp     rcx, r8
0x140017060  ja      short loc_14001704C
0x140017062  mov     byte ptr [r9+rdi+0Ah], 10h
0x140017068  jmp     short loc_140017080
0x14001706a  mov     [rdi+14h], eax
0x14001706d  mov     word ptr [rdi+8], 20FFh
0x140017073  mov     eax, [rbx+250h]
0x140017079  mov     [rdi+0Ch], eax
0x14001707c  mov     byte ptr [rdi+0Ah], 10h
0x140017080  cmp     byte ptr [rdi+2], 28h ; '('
0x140017084  jnz     loc_140017126
0x14001708a  xor     edx, edx
0x14001708c  cmp     [rdi+14h], edx
0x14001708f  jnz     loc_140040F4D
0x140017095  mov     r11d, [rdi+38h]
0x140017099  test    r11d, r11d
0x14001709c  jz      loc_140040F4D
0x1400170a2  xor     r8d, r8d
0x1400170a5  mov     ecx, [rdi+r8*4+78h]
0x1400170aa  cmp     ecx, 80h
0x1400170b0  jb      short loc_140017119
0x1400170b2  mov     r9d, [rdi+10h]
0x1400170b6  cmp     ecx, r9d
0x1400170b9  jnb     short loc_140017119
0x1400170bb  mov     r10d, ecx
0x1400170be  mov     ecx, [rcx+rdi]
0x1400170c1  cmp     ecx, 40h ; '@'
0x1400170c4  jz      short loc_1400170F0
0x1400170c6  sub     ecx, 41h ; 'A'
0x1400170c9  jz      short loc_140017110
0x1400170cb  cmp     ecx, 1
0x1400170ce  jnz     short loc_140017119
0x1400170d0  lea     rcx, [r10+28h]
0x1400170d4  cmp     rcx, r9
0x1400170d7  ja      short loc_140017119
0x1400170d9  xor     eax, eax
0x1400170db  lea     rdx, [rdi+20h]
0x1400170df  add     rdx, r10
0x1400170e2  cmp     [r10+rdi+0Ch], eax
0x1400170e7  cmovz   rdx, rax
0x1400170eb  jmp     loc_140040F4D
0x1400170f0  lea     rcx, [r10+28h]
0x1400170f4  cmp     rcx, r9
0x1400170f7  ja      short loc_140017119
0x1400170f9  cmp     [r10+rdi+0Ah], dl
0x1400170fe  jbe     loc_140040F4D
0x140017104  lea     rdx, [rdi+18h]
0x140017108  add     rdx, r10
0x14001710b  jmp     loc_140040F4D
0x140017110  lea     rcx, [r10+38h]
0x140017114  cmp     rcx, r9
0x140017117  jbe     short loc_1400170F9
0x140017119  inc     r8d
0x14001711c  cmp     r8d, r11d
0x14001711f  jb      short loc_1400170A5
0x140017121  jmp     loc_140040F4D
0x140017126  lea     rdx, [rdi+48h]
0x14001712a  jmp     loc_140040F4D
0x14001712f  cmp     byte ptr [rdi+2], 28h ; '('
0x140017133  mov     eax, [rbx+248h]
0x140017139  jnz     loc_14001706A
0x14001713f  cmp     dword ptr [rdi+14h], 0
0x140017143  mov     [rdi+28h], eax
0x140017146  mov     dword ptr [rdi+20h], 0FFh
0x14001714d  mov     [rdi+26h], r15w
0x140017152  mov     eax, [rbx+250h]
0x140017158  mov     [rdi+18h], eax
0x14001715b  jnz     loc_140017080
0x140017161  mov     r10d, [rdi+38h]
0x140017165  xor     edx, edx
0x140017167  test    r10d, r10d
0x14001716a  jz      loc_140017080
0x140017170  mov     ecx, [rdi+rdx*4+78h]
0x140017174  cmp     ecx, 80h
0x14001717a  jb      loc_14001704C
0x140017180  mov     r8d, [rdi+10h]
0x140017184  cmp     ecx, r8d
0x140017187  jnb     loc_14001704C
0x14001718d  mov     r9d, ecx
0x140017190  mov     ecx, [rcx+rdi]
0x140017193  cmp     ecx, 40h ; '@'
0x140017196  jnz     loc_140017039
0x14001719c  lea     rcx, [r9+28h]
0x1400171a0  jmp     loc_14001705D
0x1400171a5  call    ClasspIsObsoletePortDriver
0x1400171aa  test    al, al
0x1400171ac  jz      loc_140040EAA
0x1400171b2  mov     dword ptr [r8+64h], 0C0000002h
0x1400171ba  mov     eax, 0C0000002h
0x1400171bf  jmp     loc_140017031
0x140040eaa  mov     [rsp+48h+arg_10], r14
0x140040eaf  mov     r8d, 34436353h
0x140040eb5  mov     [rsp+48h+var_18], r15
0x140040eba  mov     ecx, 40h ; '@'
0x140040ebf  mov     r15d, 20h ; ' '
0x140040ec5  mov     edx, r15d
0x140040ec8  call    cs:__imp_ExAllocatePool2
0x140040ecf  nop     dword ptr [rax+rax+00h]
0x140040ed4  mov     r14, rax
0x140040ed7  test    rax, rax
0x140040eda  jnz     short loc_140040EE6
0x140040edc  mov     eax, 0C000009Ah
0x140040ee1  jmp     loc_140040FE2
0x140040ee6  mov     rax, [rbx+210h]
0x140040eed  mov     [rsp+48h+arg_0], rbp
0x140040ef2  mov     [rsp+48h+arg_8], rsi
0x140040ef7  cmp     byte ptr [rax+1Eh], 1
0x140040efb  jnz     short loc_140040F2E
0x140040efd  xor     eax, eax
0x140040eff  mov     dword ptr [rsp+48h+WriteToDevice], 40h ; '@'
0x140040f07  movzx   edx, ax
0x140040f0a  mov     r9d, 1
0x140040f10  mov     r8d, 0B8h
0x140040f16  mov     rcx, rdi
0x140040f19  xor     ebp, ebp
0x140040f1b  call    InitializeStorageRequestBlock
0x140040f20  mov     esi, eax
0x140040f22  test    eax, eax
0x140040f24  js      short loc_140040F9B
0x140040f26  mov     [rdi+14h], ebp
0x140040f29  jmp     loc_14001712F
0x140040f2e  lea     rcx, [rdi+3]; void *
0x140040f32  xor     edx, edx; Val
0x140040f34  mov     r8d, 55h ; 'U'; Size
0x140040f3a  call    memset
0x140040f3f  mov     word ptr [rdi], 58h ; 'X'
0x140040f44  mov     byte ptr [rdi+2], 0
0x140040f48  jmp     loc_14001712F
0x140040f4d  movzx   eax, byte ptr [rdx+1]
0x140040f51  mov     r9d, r15d; BufferLength
0x140040f54  mov     byte ptr [rdx], 9Eh
0x140040f57  and     al, 0F0h
0x140040f59  mov     [rdx+0Dh], r15b
0x140040f5d  or      al, 10h
0x140040f5f  mov     [rdx+1], al
0x140040f62  mov     r8, r14; BufferAddress
0x140040f65  mov     rcx, [rbx+8]; DeviceObject
0x140040f69  mov     rdx, rdi; Srb
0x140040f6c  mov     [rsp+48h+WriteToDevice], 0; WriteToDevice
0x140040f71  call    ClassSendSrbSynchronous
0x140040f76  cmp     byte ptr [rdi+2], 28h ; '('
0x140040f7a  mov     esi, eax
0x140040f7c  mov     eax, 3Ch ; '<'
0x140040f81  mov     ecx, 10h
0x140040f86  cmovnz  eax, ecx
0x140040f89  mov     ebp, [rax+rdi]
0x140040f8c  test    esi, esi
0x140040f8e  js      short loc_140040F9B
0x140040f90  cmp     ebp, ecx
0x140040f92  jnb     short loc_140040FAE
0x140040f94  mov     esi, 0C0000004h
0x140040f99  jmp     short loc_140040FBB
0x140040f9b  cmp     esi, 0C000003Ch
0x140040fa1  jnz     short loc_140040FAA
0x140040fa3  cmp     ebp, r15d
0x140040fa6  jb      short loc_140040FAE
0x140040fa8  jmp     short loc_140040FBB
0x140040faa  test    esi, esi
0x140040fac  js      short loc_140040FBB
0x140040fae  mov     rdx, r14
0x140040fb1  mov     rcx, rbx
0x140040fb4  call    InterpretReadCapacity16Data
0x140040fb9  mov     esi, eax
0x140040fbb  mov     rax, [rbx+480h]
0x140040fc2  xor     edx, edx; Tag
0x140040fc4  mov     rcx, r14; P
0x140040fc7  mov     [rax+64h], esi
0x140040fca  call    cs:__imp_ExFreePoolWithTag
0x140040fd1  nop     dword ptr [rax+rax+00h]
0x140040fd6  mov     rbp, [rsp+48h+arg_0]
0x140040fdb  mov     eax, esi
0x140040fdd  mov     rsi, [rsp+48h+arg_8]
0x140040fe2  mov     r14, [rsp+48h+arg_10]
0x140040fe7  mov     r15, [rsp+48h+var_18]
0x140040fec  jmp     loc_140017031
```
