# FatUnpinRepinnedBcbs

- ea: `0x14002486c`
- end: `0x140024b36`
- name: `FatUnpinRepinnedBcbs`
- size: `714`
- prototype: ``
- caller_count: `20`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x14000363c`
- `0x140004554`
- `0x140024bd4`
- `0x1400268c0`
- `0x140028cc0`
- `0x140030b04`
- `0x1400333d0`
- `0x140037ab0`
- `0x140038eb4`
- `0x14003960c`
- `0x140039e94`
- `0x14003b9d0`
- `0x14003bea4`
- `0x14003dba0`
- `0x14003e028`
- `0x1400412a8`
- `0x1400498f0`
- `0x14004a7e8`
- `0x14004ab20`
- `0x14004af08`

## callees

- `0x14002486c`

## import_xrefs

- `ntoskrnl!CcUnpinRepinnedBcb` at `0x140024967`
- `ntoskrnl!CcUnpinRepinnedBcb` at `0x140024a05`
- `ntoskrnl!CcUnpinRepinnedBcb` at `0x140024967`
- `ntoskrnl!CcUnpinRepinnedBcb` at `0x140024a05`
- `ntoskrnl!CcPurgeCacheSection` at `0x140024a3a`
- `ntoskrnl!CcPurgeCacheSection` at `0x140024a3a`
- `ntoskrnl!CcGetFileObjectFromBcb` at `0x140024947`
- `ntoskrnl!CcGetFileObjectFromBcb` at `0x1400249e8`
- `ntoskrnl!CcGetFileObjectFromBcb` at `0x140024947`
- `ntoskrnl!CcGetFileObjectFromBcb` at `0x1400249e8`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140024ace`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140024ace`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140024afd`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x140024afd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024a7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140024a7f`
- `ntoskrnl!ExRaiseStatus` at `0x140024b0b`
- `ntoskrnl!ExRaiseStatus` at `0x140024b0b`

## pseudocode

```c
void __fastcall FatUnpinRepinnedBcbs(__int64 a1)
{
  _WORD *v1; // rdi
  struct _FILE_OBJECT *v2; // r13
  char v3; // r14
  __int64 v4; // r8
  struct _IO_STATUS_BLOCK v6; // xmm6
  _QWORD *v7; // rsi
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  _WORD *v11; // rax
  int v12; // eax
  __int64 v13; // rcx
  BOOLEAN v14; // dl
  NTSTATUS v15; // r15d
  __int64 v16; // r12
  __int64 v17; // rbp
  PFILE_OBJECT FileObjectFromBcb; // rax
  unsigned int v19; // ecx
  int v20; // r8d
  __int64 v21; // rdi
  _QWORD *v22; // r14
  void *v23; // rcx
  _QWORD *v24; // rdi
  bool v25; // zf
  struct _IO_STATUS_BLOCK *v26; // rax
  NTSTATUS v27; // eax
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+20h] [rbp-58h] BYREF
  BOOLEAN WriteThrough; // [rsp+80h] [rbp+8h]
  _WORD *v30; // [rsp+88h] [rbp+10h]

  v1 = 0;
  v2 = 0;
  v30 = 0;
  v3 = 0;
  v4 = a1 + 88;
  v6 = 0;
  v7 = (_QWORD *)(a1 + 88);
  if ( !*(_BYTE *)(a1 + 64) )
  {
    v8 = *(_QWORD *)(a1 + 40);
    if ( v8 )
    {
      v9 = *(_QWORD *)(v8 + 184);
      if ( v9 )
      {
        v10 = *(_QWORD *)(v9 + 48);
        if ( v10 )
        {
          v11 = *(_WORD **)(v10 + 24);
          if ( v11 )
            v1 = v11;
          v30 = v1;
        }
      }
    }
  }
  v12 = *(_DWORD *)(a1 + 68);
  v14 = 0;
  if ( (v12 & 8) == 0 )
  {
    v13 = *(_QWORD *)(a1 + 56);
    if ( v13 )
    {
      if ( (v12 & 4) != 0 || (*(_DWORD *)(v13 + 200) & 0x1000) != 0 )
        v14 = 1;
    }
  }
  WriteThrough = v14;
  if ( v4 )
  {
    v15 = _mm_cvtsi128_si32((__m128i)0LL);
    do
    {
      v16 = 0;
      do
      {
        v17 = (unsigned int)v16;
        if ( v7[v16 + 1] )
        {
          IoStatus = 0;
          if ( v14 && (*(_DWORD *)(*(_QWORD *)(a1 + 56) + 200LL) & 0x1000) != 0 )
          {
            FileObjectFromBcb = CcGetFileObjectFromBcb((PVOID)v7[v16 + 1]);
            v14 = WriteThrough;
            v2 = FileObjectFromBcb;
          }
          CcUnpinRepinnedBcb((PVOID)v7[v16 + 1], v14, &IoStatus);
          if ( IoStatus.Status < 0 )
          {
            if ( !v15 )
            {
              v6 = IoStatus;
              v15 = _mm_cvtsi128_si32(*(__m128i *)&IoStatus.Status);
            }
            if ( v2 )
            {
              v19 = *(unsigned __int8 *)(a1 + 64);
              if ( (unsigned __int8)v19 > 0x12u || (v20 = 262720, !_bittest(&v20, v19)) )
              {
                if ( (_BYTE)v19 || IoStatus.Status != -2147483626 || !v1 || *v1 != 1282 )
                {
                  v21 = (unsigned int)(v16 + 1);
                  v22 = v7;
                  if ( v7 )
                  {
                    do
                    {
                      while ( (unsigned int)v21 < 4 )
                      {
                        v23 = (void *)v22[v21 + 1];
                        if ( v23 && CcGetFileObjectFromBcb(v23) == v2 )
                        {
                          CcUnpinRepinnedBcb((PVOID)v22[v21 + 1], 0, &IoStatus);
                          v22[v21 + 1] = 0;
                        }
                        v21 = (unsigned int)(v21 + 1);
                      }
                      v22 = (_QWORD *)*v22;
                      v21 = 0;
                    }
                    while ( v22 );
                    v17 = (unsigned int)v16;
                  }
                  CcPurgeCacheSection(v2->SectionObjectPointer, 0, 0, 0);
                  v1 = v30;
                  v3 = 1;
                }
              }
            }
          }
          v7[v17 + 1] = 0;
        }
        v14 = WriteThrough;
        v16 = (unsigned int)(v16 + 1);
      }
      while ( (unsigned int)v16 < 4 );
      v24 = (_QWORD *)*v7;
      if ( v7 == (_QWORD *)(a1 + 88) )
        *(_QWORD *)(a1 + 88) = 0;
      else
        ExFreePoolWithTag(v7, 0);
      v14 = WriteThrough;
      v7 = v24;
      v25 = v24 == 0;
      v1 = v30;
    }
    while ( !v25 );
    if ( v15 < 0 )
    {
      if ( v3 && v2 )
      {
        v2->DeviceObject->Flags |= 2u;
        IoSetHardErrorOrVerifyDevice(*(PIRP *)(a1 + 40), v2->DeviceObject);
      }
      if ( (*(_DWORD *)(a1 + 68) & 0x800) == 0 )
      {
        v26 = *(struct _IO_STATUS_BLOCK **)(a1 + 40);
        if ( v26 )
          v26[3] = v6;
        *(_DWORD *)(a1 + 72) = v15;
        v27 = FsRtlNormalizeNtstatus(v15, -1073741591);
        ExRaiseStatus(v27);
      }
    }
  }
}

```

## disassembly

```asm
0x14002486c  mov     [rsp+arg_10], rbx
0x140024871  push    rbp
0x140024872  push    rsi
0x140024873  push    rdi
0x140024874  push    r12
0x140024876  push    r13
0x140024878  push    r14
0x14002487a  push    r15
0x14002487c  sub     rsp, 40h
0x140024880  xor     edi, edi
0x140024882  movaps  [rsp+78h+var_48], xmm6
0x140024887  xor     r13d, r13d
0x14002488a  mov     [rsp+78h+arg_8], rdi
0x140024892  xor     r14b, r14b
0x140024895  lea     r8, [rcx+58h]
0x140024899  mov     rbx, rcx
0x14002489c  xorps   xmm6, xmm6
0x14002489f  mov     rsi, r8
0x1400248a2  cmp     [rcx+40h], dil
0x1400248a6  jnz     short loc_1400248D9
0x1400248a8  mov     rax, [rcx+28h]
0x1400248ac  test    rax, rax
0x1400248af  jz      short loc_1400248D9
0x1400248b1  mov     rcx, [rax+0B8h]
0x1400248b8  test    rcx, rcx
0x1400248bb  jz      short loc_1400248D9
0x1400248bd  mov     rax, [rcx+30h]
0x1400248c1  test    rax, rax
0x1400248c4  jz      short loc_1400248D9
0x1400248c6  mov     rax, [rax+18h]
0x1400248ca  test    rax, rax
0x1400248cd  cmovnz  rdi, rax
0x1400248d1  mov     [rsp+78h+arg_8], rdi
0x1400248d9  mov     eax, [rbx+44h]
0x1400248dc  test    al, 8
0x1400248de  jnz     short loc_1400248FD
0x1400248e0  mov     rcx, [rbx+38h]
0x1400248e4  test    rcx, rcx
0x1400248e7  jz      short loc_1400248FD
0x1400248e9  test    al, 4
0x1400248eb  jnz     short loc_1400248F9
0x1400248ed  mov     eax, [rcx+0C8h]
0x1400248f3  bt      eax, 0Ch
0x1400248f7  jnb     short loc_1400248FD
0x1400248f9  mov     dl, 1
0x1400248fb  jmp     short loc_1400248FF
0x1400248fd  xor     dl, dl
0x1400248ff  mov     [rsp+78h+WriteThrough], dl
0x140024906  test    r8, r8
0x140024909  jz      loc_140024B18
0x14002490f  movd    r15d, xmm6
0x140024914  xor     r12d, r12d
0x140024917  cmp     qword ptr [rsi+r12*8+8], 0
0x14002491d  mov     ebp, r12d
0x140024920  jz      loc_140024A5A
0x140024926  xorps   xmm0, xmm0
0x140024929  movups  xmmword ptr [rsp+78h+IoStatus], xmm0
0x14002492e  test    dl, dl
0x140024930  jz      short loc_14002495D
0x140024932  mov     rax, [rbx+38h]
0x140024936  mov     ecx, [rax+0C8h]
0x14002493c  bt      ecx, 0Ch
0x140024940  jnb     short loc_14002495D
0x140024942  mov     rcx, [rsi+r12*8+8]; Bcb
0x140024947  call    cs:__imp_CcGetFileObjectFromBcb
0x14002494e  nop     dword ptr [rax+rax+00h]
0x140024953  mov     dl, [rsp+78h+WriteThrough]; WriteThrough
0x14002495a  mov     r13, rax
0x14002495d  mov     rcx, [rsi+r12*8+8]; Bcb
0x140024962  lea     r8, [rsp+78h+IoStatus]; IoStatus
0x140024967  call    cs:__imp_CcUnpinRepinnedBcb
0x14002496e  nop     dword ptr [rax+rax+00h]
0x140024973  mov     edx, dword ptr [rsp+78h+IoStatus]
0x140024977  test    edx, edx
0x140024979  jns     loc_140024A51
0x14002497f  test    r15d, r15d
0x140024982  jnz     short loc_14002498E
0x140024984  movaps  xmm6, xmmword ptr [rsp+78h+IoStatus]
0x140024989  movd    r15d, xmm6
0x14002498e  test    r13, r13
0x140024991  jz      loc_140024A51
0x140024997  movzx   ecx, byte ptr [rbx+40h]
0x14002499b  cmp     cl, 12h
0x14002499e  ja      short loc_1400249B0
0x1400249a0  mov     r8d, 40240h
0x1400249a6  bt      r8d, ecx
0x1400249aa  jb      loc_140024A51
0x1400249b0  test    cl, cl
0x1400249b2  jnz     short loc_1400249CF
0x1400249b4  cmp     edx, 80000016h
0x1400249ba  jnz     short loc_1400249CF
0x1400249bc  test    rdi, rdi
0x1400249bf  jz      short loc_1400249CF
0x1400249c1  mov     eax, 502h
0x1400249c6  cmp     [rdi], ax
0x1400249c9  jz      loc_140024A51
0x1400249cf  lea     edi, [r12+1]
0x1400249d4  mov     r14, rsi
0x1400249d7  test    rsi, rsi
0x1400249da  jz      short loc_140024A2E
0x1400249dc  jmp     short loc_140024A1C
0x1400249de  mov     rcx, [r14+rdi*8+8]; Bcb
0x1400249e3  test    rcx, rcx
0x1400249e6  jz      short loc_140024A1A
0x1400249e8  call    cs:__imp_CcGetFileObjectFromBcb
0x1400249ef  nop     dword ptr [rax+rax+00h]
0x1400249f4  cmp     rax, r13
0x1400249f7  jnz     short loc_140024A1A
0x1400249f9  mov     rcx, [r14+rdi*8+8]; Bcb
0x1400249fe  lea     r8, [rsp+78h+IoStatus]; IoStatus
0x140024a03  xor     edx, edx; WriteThrough
0x140024a05  call    cs:__imp_CcUnpinRepinnedBcb
0x140024a0c  nop     dword ptr [rax+rax+00h]
0x140024a11  mov     qword ptr [r14+rdi*8+8], 0
0x140024a1a  inc     edi
0x140024a1c  cmp     edi, 4
0x140024a1f  jb      short loc_1400249DE
0x140024a21  mov     r14, [r14]
0x140024a24  xor     edi, edi
0x140024a26  test    r14, r14
0x140024a29  jnz     short loc_140024A1C
0x140024a2b  mov     ebp, r12d
0x140024a2e  mov     rcx, [r13+28h]; SectionObjectPointer
0x140024a32  xor     r9d, r9d; Flags
0x140024a35  xor     r8d, r8d; Length
0x140024a38  xor     edx, edx; FileOffset
0x140024a3a  call    cs:__imp_CcPurgeCacheSection
0x140024a41  nop     dword ptr [rax+rax+00h]
0x140024a46  mov     rdi, [rsp+78h+arg_8]
0x140024a4e  mov     r14b, 1
0x140024a51  mov     qword ptr [rsi+rbp*8+8], 0
0x140024a5a  mov     dl, [rsp+78h+WriteThrough]
0x140024a61  inc     r12d
0x140024a64  cmp     r12d, 4
0x140024a68  jb      loc_140024917
0x140024a6e  mov     rdi, [rsi]
0x140024a71  lea     r8, [rbx+58h]
0x140024a75  cmp     rsi, r8
0x140024a78  jz      short loc_140024A8D
0x140024a7a  xor     edx, edx; Tag
0x140024a7c  mov     rcx, rsi; P
0x140024a7f  call    cs:__imp_ExFreePoolWithTag
0x140024a86  nop     dword ptr [rax+rax+00h]
0x140024a8b  jmp     short loc_140024A94
0x140024a8d  mov     qword ptr [r8], 0
0x140024a94  mov     dl, [rsp+78h+WriteThrough]
0x140024a9b  mov     rsi, rdi
0x140024a9e  test    rdi, rdi
0x140024aa1  mov     rdi, [rsp+78h+arg_8]
0x140024aa9  jnz     loc_140024914
0x140024aaf  test    r15d, r15d
0x140024ab2  jns     short loc_140024B18
0x140024ab4  test    r14b, r14b
0x140024ab7  jz      short loc_140024ADA
0x140024ab9  test    r13, r13
0x140024abc  jz      short loc_140024ADA
0x140024abe  mov     rax, [r13+8]
0x140024ac2  or      dword ptr [rax+30h], 2
0x140024ac6  mov     rdx, [r13+8]; DeviceObject
0x140024aca  mov     rcx, [rbx+28h]; Irp
0x140024ace  call    cs:__imp_IoSetHardErrorOrVerifyDevice
0x140024ad5  nop     dword ptr [rax+rax+00h]
0x140024ada  test    dword ptr [rbx+44h], 800h
0x140024ae1  jnz     short loc_140024B18
0x140024ae3  mov     rax, [rbx+28h]
0x140024ae7  test    rax, rax
0x140024aea  jz      short loc_140024AF1
0x140024aec  movdqu  xmmword ptr [rax+30h], xmm6
0x140024af1  mov     edx, 0C00000E9h; GenericException
0x140024af6  mov     [rbx+48h], r15d
0x140024afa  mov     ecx, r15d; Exception
0x140024afd  call    cs:__imp_FsRtlNormalizeNtstatus
0x140024b04  nop     dword ptr [rax+rax+00h]
0x140024b09  mov     ecx, eax; Status
0x140024b0b  call    cs:__imp_ExRaiseStatus
0x140024b18  mov     rbx, [rsp+78h+arg_10]
0x140024b20  movaps  xmm6, [rsp+78h+var_48]
0x140024b25  add     rsp, 40h
0x140024b29  pop     r15
0x140024b2b  pop     r14
0x140024b2d  pop     r13
0x140024b2f  pop     r12
0x140024b31  pop     rdi
0x140024b32  pop     rsi
0x140024b33  pop     rbp
0x140024b34  retn
```
