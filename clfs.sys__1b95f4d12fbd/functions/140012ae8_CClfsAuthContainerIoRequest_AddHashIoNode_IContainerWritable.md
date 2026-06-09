# CClfsAuthContainerIoRequest::AddHashIoNode(IContainerWritable *)

- ea: `0x140012ae8`
- end: `0x140012dc9`
- name: `?AddHashIoNode@CClfsAuthContainerIoRequest@@AEAAJPEAUIContainerWritable@@@Z`
- size: `737`
- prototype: `__int64 __fastcall(CClfsAuthContainerIoRequest *__hidden this, struct IContainerWritable *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140013cd0`

## callees

- `0x1400126f8`
- `0x140012ae8`
- `0x14001352c`
- `0x140017f20`
- `0x140032530`
- `0x14003ce24`
- `0x14003dff0`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140012c7a`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140012c7a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140012b27`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140012b27`

## pseudocode

```c
__int64 __fastcall CClfsAuthContainerIoRequest::AddHashIoNode(
        CClfsAuthContainerIoRequest *this,
        struct IContainerWritable *a2)
{
  CClfsHashIoNode *v4; // rax
  CClfsAuthContainer **v5; // r14
  unsigned int *v6; // rdi
  int v7; // ebx
  unsigned __int64 v8; // rax
  unsigned int v9; // eax
  unsigned int *v10; // r15
  unsigned int *v11; // r12
  unsigned int *v12; // r13
  unsigned int v13; // edx
  struct _CLFS_HASHIO_LOOKUP *inserted; // rax
  unsigned int v15; // eax
  __int64 v16; // rcx
  unsigned int v17; // edx
  unsigned int v18; // r8d
  unsigned int v19; // edx
  struct _CLFS_HASHIO_LOOKUP *v21; // [rsp+50h] [rbp-48h]
  __int128 Buffer; // [rsp+58h] [rbp-40h] BYREF
  unsigned __int8 NewElement; // [rsp+B0h] [rbp+18h] BYREF
  unsigned int v24; // [rsp+B8h] [rbp+20h] BYREF

  Buffer = 0;
  NewElement = 0;
  v24 = 0;
  v4 = (CClfsHashIoNode *)ExAllocateFromNPagedLookasideList(&CClfsHashIoNode::m_laList);
  v5 = (CClfsAuthContainer **)((char *)this + 24);
  if ( v4 )
    v6 = (unsigned int *)CClfsHashIoNode::CClfsHashIoNode(
                           v4,
                           *((_DWORD *)*v5 + 14),
                           *((struct _DEVICE_OBJECT **)this + 21));
  else
    v6 = 0;
  if ( v6 )
  {
    (**(void (__fastcall ***)(unsigned int *))v6)(v6);
    v8 = (*(__int64 (__fastcall **)(struct IContainerWritable *))(*(_QWORD *)a2 + 32LL))(a2);
    v7 = CClfsAuthContainer::OffsetToSector(v8, &v24);
    if ( v7 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(struct IContainerWritable *))(*(_QWORD *)a2 + 24LL))(a2);
      v10 = v6 + 7;
      v11 = v6 + 5;
      v7 = CClfsAuthContainer::HashTableRangeToUpdate(*v5, v24, v9, v6 + 5, v6 + 7, v6 + 8, v6 + 9);
      if ( v7 >= 0 )
      {
        v12 = v6 + 2;
        v7 = CClfsAuthContainer::HashToDataSectorMapping(*v5, *v11, *v10, v6 + 2, v6 + 4);
        if ( v7 >= 0 )
        {
          v6[3] = *v12 - 1 + v6[4];
          v13 = *v11;
          v6[6] = *v11 + *v10 - 1;
          LODWORD(Buffer) = v13;
          DWORD1(Buffer) = v6[6];
          *((_QWORD *)&Buffer + 1) = v6;
          while ( !NewElement )
          {
            inserted = (struct _CLFS_HASHIO_LOOKUP *)RtlInsertElementGenericTableAvl(
                                                       (PRTL_AVL_TABLE)((char *)this + 32),
                                                       &Buffer,
                                                       0x10u,
                                                       &NewElement);
            v21 = inserted;
            if ( !inserted )
            {
              v7 = -1073741672;
              break;
            }
            if ( NewElement )
            {
              v6 = 0;
              v15 = *((_DWORD *)this + 34);
              if ( v15 + 1 < v15 )
              {
                *((_DWORD *)this + 34) = -1;
                v7 = -1073741675;
              }
              else
              {
                *((_DWORD *)this + 34) = v15 + 1;
                v7 = 0;
              }
              break;
            }
            v16 = *((_QWORD *)inserted + 1);
            v17 = *v12;
            if ( *v12 >= *(_DWORD *)(v16 + 8) )
              v17 = *(_DWORD *)(v16 + 8);
            v24 = v17;
            v18 = v6[3];
            if ( v18 <= *(_DWORD *)(v16 + 12) )
              v18 = *(_DWORD *)(v16 + 12);
            v7 = CClfsAuthContainer::HashTableRangeToUpdate(*v5, v17, v18 - v17 + 1, v6 + 5, v6 + 7, v6 + 8, v6 + 9);
            if ( v7 < 0 )
              break;
            v7 = CClfsAuthContainer::HashToDataSectorMapping(*v5, *v11, *v10, v6 + 2, v6 + 4);
            if ( v7 < 0 )
              break;
            v7 = CClfsAuthContainerIoRequest::DeleteHashIoNode(this, v21);
            if ( v7 < 0 )
              break;
            v6[3] = *v12 - 1 + v6[4];
            v19 = *v11;
            v6[6] = *v11 + *v10 - 1;
            LODWORD(Buffer) = v19;
            DWORD1(Buffer) = v6[6];
          }
        }
      }
    }
  }
  else
  {
    v7 = -1073741670;
  }
  if ( v6 )
    (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v6 + 8LL))(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140012ae8  mov     rax, rsp
0x140012aeb  mov     [rax+8], rbx
0x140012aef  mov     [rax+10h], rsi
0x140012af3  push    rdi
0x140012af4  push    r12
0x140012af6  push    r13
0x140012af8  push    r14
0x140012afa  push    r15
0x140012afc  sub     rsp, 70h
0x140012b00  mov     r15, rdx
0x140012b03  mov     rsi, rcx
0x140012b06  xorps   xmm0, xmm0
0x140012b09  movups  xmmword ptr [rax-40h], xmm0
0x140012b0d  mov     qword ptr [rax-50h], 0
0x140012b15  mov     byte ptr [rax+18h], 0
0x140012b19  mov     dword ptr [rax+20h], 0
0x140012b20  lea     rcx, ?m_laList@CClfsHashIoNode@@0U_NPAGED_LOOKASIDE_LIST@@A; Lookaside
0x140012b27  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140012b2e  nop     dword ptr [rax+rax+00h]
0x140012b33  lea     r14, [rsi+18h]
0x140012b37  test    rax, rax
0x140012b3a  jz      short loc_140012B56
0x140012b3c  mov     rdx, [r14]
0x140012b3f  mov     r8, [rsi+0A8h]; struct _DEVICE_OBJECT *
0x140012b46  mov     edx, [rdx+38h]; unsigned int
0x140012b49  mov     rcx, rax; this
0x140012b4c  call    ??0CClfsHashIoNode@@QEAA@KPEAU_DEVICE_OBJECT@@@Z; CClfsHashIoNode::CClfsHashIoNode(ulong,_DEVICE_OBJECT *)
0x140012b51  mov     rdi, rax
0x140012b54  jmp     short loc_140012B58
0x140012b56  xor     edi, edi
0x140012b58  mov     [rsp+98h+var_50], rdi
0x140012b5d  test    rdi, rdi
0x140012b60  jnz     short loc_140012B70
0x140012b62  mov     ebx, 0C000009Ah
0x140012b67  mov     [rsp+98h+var_58], ebx
0x140012b6b  jmp     loc_140012D98
0x140012b70  mov     rax, [rdi]
0x140012b73  mov     rax, [rax]
0x140012b76  mov     rcx, rdi
0x140012b79  call    _guard_dispatch_icall
0x140012b7e  mov     rax, [r15]
0x140012b81  mov     rax, [rax+20h]
0x140012b85  mov     rcx, r15
0x140012b88  call    _guard_dispatch_icall
0x140012b8d  mov     rcx, rax; unsigned __int64
0x140012b90  lea     rdx, [rsp+98h+arg_18]; unsigned int *
0x140012b98  call    ?OffsetToSector@CClfsAuthContainer@@CAJ_KAEAK@Z; CClfsAuthContainer::OffsetToSector(unsigned __int64,ulong &)
0x140012b9d  mov     ebx, eax
0x140012b9f  mov     [rsp+98h+var_58], eax
0x140012ba3  test    eax, eax
0x140012ba5  js      loc_140012D98
0x140012bab  mov     rax, [r15]
0x140012bae  mov     rax, [rax+18h]
0x140012bb2  mov     rcx, r15
0x140012bb5  call    _guard_dispatch_icall
0x140012bba  lea     rcx, [rdi+24h]
0x140012bbe  lea     rdx, [rdi+20h]
0x140012bc2  lea     r15, [rdi+1Ch]
0x140012bc6  lea     r12, [rdi+14h]
0x140012bca  mov     [rsp+98h+var_68], rcx; unsigned int *
0x140012bcf  mov     [rsp+98h+var_70], rdx; unsigned int *
0x140012bd4  mov     [rsp+98h+var_78], r15; unsigned int *
0x140012bd9  mov     r9, r12; unsigned int *
0x140012bdc  mov     r8d, eax; unsigned int
0x140012bdf  mov     edx, [rsp+98h+arg_18]; unsigned int
0x140012be6  mov     rcx, [r14]; this
0x140012be9  call    ?HashTableRangeToUpdate@CClfsAuthContainer@@AEAAJKKAEAK000@Z; CClfsAuthContainer::HashTableRangeToUpdate(ulong,ulong,ulong &,ulong &,ulong &,ulong &)
0x140012bee  mov     ebx, eax
0x140012bf0  mov     [rsp+98h+var_58], eax
0x140012bf4  test    eax, eax
0x140012bf6  js      loc_140012D98
0x140012bfc  lea     rax, [rdi+10h]
0x140012c00  lea     r13, [rdi+8]
0x140012c04  mov     [rsp+98h+var_78], rax; unsigned int *
0x140012c09  mov     r9, r13; unsigned int *
0x140012c0c  mov     r8d, [r15]; unsigned int
0x140012c0f  mov     edx, [r12]; unsigned int
0x140012c13  mov     rcx, [r14]; this
0x140012c16  call    ?HashToDataSectorMapping@CClfsAuthContainer@@AEAAJKKAEAK0@Z; CClfsAuthContainer::HashToDataSectorMapping(ulong,ulong,ulong &,ulong &)
0x140012c1b  mov     ebx, eax
0x140012c1d  mov     [rsp+98h+var_58], eax
0x140012c21  test    eax, eax
0x140012c23  js      loc_140012D98
0x140012c29  mov     ecx, [rdi+10h]
0x140012c2c  mov     eax, [r13+0]
0x140012c30  dec     eax
0x140012c32  add     ecx, eax
0x140012c34  mov     [rdi+0Ch], ecx
0x140012c37  mov     edx, [r12]
0x140012c3b  mov     ecx, [r15]
0x140012c3e  dec     ecx
0x140012c40  add     ecx, edx
0x140012c42  mov     [rdi+18h], ecx
0x140012c45  mov     [rsp+98h+Buffer], edx
0x140012c49  mov     eax, [rdi+18h]
0x140012c4c  mov     [rsp+98h+var_3C], eax
0x140012c50  mov     [rsp+98h+var_38], rdi
0x140012c55  cmp     [rsp+98h+NewElement], 0
0x140012c5d  jnz     loc_140012D98
0x140012c63  lea     rcx, [rsi+20h]; Table
0x140012c67  lea     r9, [rsp+98h+NewElement]; NewElement
0x140012c6f  mov     r8d, 10h; BufferSize
0x140012c75  lea     rdx, [rsp+98h+Buffer]; Buffer
0x140012c7a  call    cs:__imp_RtlInsertElementGenericTableAvl
0x140012c81  nop     dword ptr [rax+rax+00h]
0x140012c86  mov     [rsp+98h+var_48], rax
0x140012c8b  test    rax, rax
0x140012c8e  jnz     short loc_140012C9A
0x140012c90  mov     ebx, 0C0000098h
0x140012c95  jmp     loc_140012B67
0x140012c9a  cmp     [rsp+98h+NewElement], 0
0x140012ca2  jz      short loc_140012CD9
0x140012ca4  xor     edi, edi
0x140012ca6  mov     [rsp+98h+var_50], rdi
0x140012cab  mov     eax, [rsi+88h]
0x140012cb1  lea     ecx, [rax+1]
0x140012cb4  cmp     ecx, eax
0x140012cb6  jb      short loc_140012CC5
0x140012cb8  mov     [rsi+88h], ecx
0x140012cbe  xor     ebx, ebx
0x140012cc0  jmp     loc_140012B67
0x140012cc5  mov     dword ptr [rsi+88h], 0FFFFFFFFh
0x140012ccf  mov     ebx, 0C0000095h
0x140012cd4  jmp     loc_140012B67
0x140012cd9  mov     rcx, [rax+8]
0x140012cdd  mov     eax, [rcx+8]
0x140012ce0  mov     edx, [r13+0]
0x140012ce4  cmp     edx, eax
0x140012ce6  cmovnb  edx, eax; unsigned int
0x140012ce9  mov     [rsp+98h+arg_18], edx
0x140012cf0  mov     eax, [rcx+0Ch]
0x140012cf3  mov     r8d, [rdi+0Ch]
0x140012cf7  cmp     r8d, eax
0x140012cfa  cmovbe  r8d, eax
0x140012cfe  sub     r8d, edx
0x140012d01  inc     r8d; unsigned int
0x140012d04  lea     rax, [rdi+24h]
0x140012d08  mov     [rsp+98h+var_68], rax; unsigned int *
0x140012d0d  lea     rax, [rdi+20h]
0x140012d11  mov     [rsp+98h+var_70], rax; unsigned int *
0x140012d16  mov     [rsp+98h+var_78], r15; unsigned int *
0x140012d1b  mov     r9, r12; unsigned int *
0x140012d1e  mov     rcx, [r14]; this
0x140012d21  call    ?HashTableRangeToUpdate@CClfsAuthContainer@@AEAAJKKAEAK000@Z; CClfsAuthContainer::HashTableRangeToUpdate(ulong,ulong,ulong &,ulong &,ulong &,ulong &)
0x140012d26  mov     ebx, eax
0x140012d28  mov     [rsp+98h+var_58], eax
0x140012d2c  test    eax, eax
0x140012d2e  js      short loc_140012D98
0x140012d30  lea     rax, [rdi+10h]
0x140012d34  mov     [rsp+98h+var_78], rax; unsigned int *
0x140012d39  mov     r9, r13; unsigned int *
0x140012d3c  mov     r8d, [r15]; unsigned int
0x140012d3f  mov     edx, [r12]; unsigned int
0x140012d43  mov     rcx, [r14]; this
0x140012d46  call    ?HashToDataSectorMapping@CClfsAuthContainer@@AEAAJKKAEAK0@Z; CClfsAuthContainer::HashToDataSectorMapping(ulong,ulong,ulong &,ulong &)
0x140012d4b  mov     ebx, eax
0x140012d4d  mov     [rsp+98h+var_58], eax
0x140012d51  test    eax, eax
0x140012d53  js      short loc_140012D98
0x140012d55  mov     rdx, [rsp+98h+var_48]; struct _CLFS_HASHIO_LOOKUP *
0x140012d5a  mov     rcx, rsi; this
0x140012d5d  call    ?DeleteHashIoNode@CClfsAuthContainerIoRequest@@AEAAJPEAU_CLFS_HASHIO_LOOKUP@@@Z; CClfsAuthContainerIoRequest::DeleteHashIoNode(_CLFS_HASHIO_LOOKUP *)
0x140012d62  mov     ebx, eax
0x140012d64  mov     [rsp+98h+var_58], eax
0x140012d68  test    eax, eax
0x140012d6a  js      short loc_140012D98
0x140012d6c  mov     ecx, [rdi+10h]
0x140012d6f  mov     eax, [r13+0]
0x140012d73  dec     eax
0x140012d75  add     ecx, eax
0x140012d77  mov     [rdi+0Ch], ecx
0x140012d7a  mov     edx, [r12]
0x140012d7e  mov     ecx, [r15]
0x140012d81  dec     ecx
0x140012d83  add     ecx, edx
0x140012d85  mov     [rdi+18h], ecx
0x140012d88  mov     [rsp+98h+Buffer], edx
0x140012d8c  mov     eax, [rdi+18h]
0x140012d8f  mov     [rsp+98h+var_3C], eax
0x140012d93  jmp     loc_140012C55
0x140012d98  test    rdi, rdi
0x140012d9b  jz      short loc_140012DAC
0x140012d9d  mov     rax, [rdi]
0x140012da0  mov     rax, [rax+8]
0x140012da4  mov     rcx, rdi
0x140012da7  call    _guard_dispatch_icall
0x140012dac  mov     eax, ebx
0x140012dae  lea     r11, [rsp+98h+var_28]
0x140012db3  mov     rbx, [r11+30h]
0x140012db7  mov     rsi, [r11+38h]
0x140012dbb  mov     rsp, r11
0x140012dbe  pop     r15
0x140012dc0  pop     r14
0x140012dc2  pop     r13
0x140012dc4  pop     r12
0x140012dc6  pop     rdi
0x140012dc7  retn
0x14001950d  push    rbp
0x14001950f  sub     rsp, 40h
0x140019513  mov     rbp, rdx
0x140019516  mov     rcx, [rbp+48h]
0x14001951a  test    rcx, rcx
0x14001951d  jz      short loc_140019533
0x14001951f  mov     rax, [rcx]
0x140019522  mov     rax, [rax+8]
0x140019526  call    _guard_dispatch_icall
0x14001952b  mov     qword ptr [rbp+48h], 0
0x140019533  add     rsp, 40h
0x140019537  pop     rbp
0x140019538  retn
```
