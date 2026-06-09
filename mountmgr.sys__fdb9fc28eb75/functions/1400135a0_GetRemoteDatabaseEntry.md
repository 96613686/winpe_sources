# GetRemoteDatabaseEntry

- ea: `0x1400135a0`
- end: `0x1400139e1`
- name: `GetRemoteDatabaseEntry`
- size: `1089`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14000a96c`
- `0x14000b5e8`
- `0x14000e340`
- `0x14000ecbc`
- `0x1400119a0`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x1400025d8`
- `0x14000a550`
- `0x140012df0`
- `0x1400135a0`

## import_xrefs

- `ntoskrnl!ZwReadFile` at `0x140013643`
- `ntoskrnl!ZwReadFile` at `0x1400136d0`
- `ntoskrnl!ZwReadFile` at `0x140013643`
- `ntoskrnl!ZwReadFile` at `0x1400136d0`
- `ntoskrnl!KeReleaseMutex` at `0x1400135f3`
- `ntoskrnl!KeReleaseMutex` at `0x1400135f3`
- `ntoskrnl!ExAllocatePool2` at `0x14001367d`
- `ntoskrnl!ExAllocatePool2` at `0x14001367d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400136f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001389a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001394a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400139c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400136f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001389a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001394a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400139c9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140013730`
- `ntoskrnl!KeWaitForSingleObject` at `0x140013730`

## pseudocode

```c
__int64 __fastcall GetRemoteDatabaseEntry(__int64 a1, void *a2, unsigned int a3, unsigned __int16 **a4)
{
  __int64 v4; // r14
  unsigned __int16 *Pool2; // rbx
  union _LARGE_INTEGER v6; // r12
  __int64 v9; // r13
  NTSTATUS v10; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // edi
  __int64 v14; // r8
  __int64 result; // rax
  __int64 v16; // r8
  unsigned int v17; // edi
  ULONG v18; // r12d
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // [rsp+50h] [rbp-58h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-50h] BYREF
  ULONG Buffer; // [rsp+B0h] [rbp+8h] BYREF
  unsigned int v28; // [rsp+C0h] [rbp+18h]
  union _LARGE_INTEGER ByteOffset; // [rsp+C8h] [rbp+20h] BYREF

  v28 = a3;
  v4 = *(_QWORD *)(a1 + 152);
  IoStatusBlock = 0;
  Pool2 = 0;
  v6.QuadPart = a3;
  Buffer = 0;
  ByteOffset.QuadPart = 0;
  v9 = *(_QWORD *)(v4 + 336);
  v25 = *(_QWORD *)(a1 + 176);
  KeReleaseMutex((PRKMUTEX)(v4 + 56), 0);
  ByteOffset = v6;
  v10 = ZwReadFile(a2, 0, 0, 0, &IoStatusBlock, &Buffer, 4u, &ByteOffset, 0);
  v12 = (unsigned int)v10;
  if ( v10 < 0 )
  {
    if ( v10 == -1073741807 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_6;
      v20 = 45;
      v12 = 3221225489LL;
    }
    else
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_6;
      v20 = 44;
    }
    WPP_SF_L(v19->AttachedDevice, v20, v11, v12);
    goto LABEL_6;
  }
  if ( Buffer )
  {
    Pool2 = (unsigned __int16 *)ExAllocatePool2(258, Buffer, 1098149453);
    if ( Pool2 )
    {
      v13 = ZwReadFile(a2, 0, 0, 0, &IoStatusBlock, Pool2, Buffer, &ByteOffset, 0);
      if ( (v13 & 0x80000000) == 0 )
      {
        if ( IoStatusBlock.Information < Buffer )
        {
          TruncateRemoteDatabase(a2);
          ExFreePoolWithTag(Pool2, 0);
          Pool2 = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 49, v21, v13);
          }
        }
        else if ( Buffer < 0x10 )
        {
          TruncateRemoteDatabase(a2);
          ExFreePoolWithTag(Pool2, 0);
          Pool2 = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 50, v22, v13);
          }
        }
        else
        {
          v18 = Pool2[4] + Pool2[5];
          if ( v18 <= Pool2[6] + (unsigned int)Pool2[7] )
            v18 = Pool2[6] + Pool2[7];
          if ( v18 > Buffer )
          {
            TruncateRemoteDatabase(a2);
            ExFreePoolWithTag(Pool2, 0);
            Pool2 = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_ddL(WPP_GLOBAL_Control->AttachedDevice, v23, v24, v18, Buffer, v13);
            }
          }
        }
      }
      else
      {
        TruncateRemoteDatabase(a2);
        ExFreePoolWithTag(Pool2, 0);
        Pool2 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 48, v14, v13);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47);
    }
  }
  else
  {
    TruncateRemoteDatabase(a2);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46);
  }
LABEL_6:
  KeWaitForSingleObject((PVOID)(v4 + 56), Executive, 0, 0, 0);
  result = VerifyEpoch(v4, v9, v25);
  v17 = result;
  if ( (int)result < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 52, v16, (unsigned int)result);
    if ( Pool2 )
      ExFreePoolWithTag(Pool2, 0);
    *a4 = 0;
    return v17;
  }
  else
  {
    *a4 = Pool2;
  }
  return result;
}

```

## disassembly

```asm
0x1400135a0  mov     rax, rsp
0x1400135a3  mov     [rax+10h], rbx
0x1400135a7  mov     [rax+18h], r8d
0x1400135ab  push    rbp
0x1400135ac  push    rsi
0x1400135ad  push    rdi
0x1400135ae  push    r12
0x1400135b0  push    r13
0x1400135b2  push    r14
0x1400135b4  push    r15
0x1400135b6  sub     rsp, 70h
0x1400135ba  mov     r14, [rcx+98h]
0x1400135c1  xorps   xmm0, xmm0
0x1400135c4  movups  xmmword ptr [rax-50h], xmm0
0x1400135c8  xor     ebx, ebx
0x1400135ca  mov     r12d, r8d
0x1400135cd  mov     [rax+8], ebx
0x1400135d0  mov     rbp, rdx
0x1400135d3  mov     [rax+20h], rbx
0x1400135d7  xor     edx, edx; Wait
0x1400135d9  mov     rax, [rcx+0B0h]
0x1400135e0  mov     rsi, r9
0x1400135e3  mov     r13, [r14+150h]
0x1400135ea  lea     rcx, [r14+38h]; Mutex
0x1400135ee  mov     [rsp+0A8h+var_58], rax
0x1400135f3  call    cs:__imp_KeReleaseMutex
0x1400135fa  nop     dword ptr [rax+rax+00h]
0x1400135ff  mov     [rsp+0A8h+Key], rbx; Key
0x140013604  lea     rax, [rsp+0A8h+arg_18]
0x14001360c  mov     [rsp+0A8h+ByteOffset], rax; ByteOffset
0x140013611  xor     r9d, r9d; ApcContext
0x140013614  lea     rax, [rsp+0A8h+arg_0]
0x14001361c  mov     [rsp+0A8h+Length], 4; Length
0x140013624  mov     [rsp+0A8h+Buffer], rax; Buffer
0x140013629  xor     r8d, r8d; ApcRoutine
0x14001362c  lea     rax, [rsp+0A8h+var_50]
0x140013631  mov     qword ptr [rsp+0A8h+arg_18], r12
0x140013639  xor     edx, edx; Event
0x14001363b  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x140013640  mov     rcx, rbp; FileHandle
0x140013643  call    cs:__imp_ZwReadFile
0x14001364a  nop     dword ptr [rax+rax+00h]
0x14001364f  lea     rdi, WPP_GLOBAL_Control
0x140013656  mov     r9d, eax
0x140013659  test    eax, eax
0x14001365b  js      loc_1400137EF
0x140013661  mov     eax, [rsp+0A8h+arg_0]
0x140013668  test    eax, eax
0x14001366a  jz      loc_1400137C1
0x140013670  mov     edx, eax
0x140013672  mov     ecx, 102h
0x140013677  mov     r8d, 41746E4Dh
0x14001367d  call    cs:__imp_ExAllocatePool2
0x140013684  nop     dword ptr [rax+rax+00h]
0x140013689  mov     rbx, rax
0x14001368c  test    rax, rax
0x14001368f  jz      loc_14001383B
0x140013695  mov     [rsp+0A8h+Key], 0; Key
0x14001369e  lea     rax, [rsp+0A8h+arg_18]
0x1400136a6  mov     [rsp+0A8h+ByteOffset], rax; ByteOffset
0x1400136ab  xor     r9d, r9d; ApcContext
0x1400136ae  mov     eax, [rsp+0A8h+arg_0]
0x1400136b5  xor     r8d, r8d; ApcRoutine
0x1400136b8  mov     [rsp+0A8h+Length], eax; Length
0x1400136bc  xor     edx, edx; Event
0x1400136be  lea     rax, [rsp+0A8h+var_50]
0x1400136c3  mov     [rsp+0A8h+Buffer], rbx; Buffer
0x1400136c8  mov     rcx, rbp; FileHandle
0x1400136cb  mov     [rsp+0A8h+IoStatusBlock], rax; IoStatusBlock
0x1400136d0  call    cs:__imp_ZwReadFile
0x1400136d7  nop     dword ptr [rax+rax+00h]
0x1400136dc  mov     edi, eax
0x1400136de  test    eax, eax
0x1400136e0  jns     loc_140013772
0x1400136e6  mov     edx, r12d
0x1400136e9  mov     rcx, rbp; FileHandle
0x1400136ec  call    TruncateRemoteDatabase
0x1400136f1  xor     edx, edx; Tag
0x1400136f3  mov     rcx, rbx; P
0x1400136f6  call    cs:__imp_ExFreePoolWithTag
0x1400136fd  nop     dword ptr [rax+rax+00h]
0x140013702  xor     ebx, ebx
0x140013704  mov     rcx, cs:WPP_GLOBAL_Control
0x14001370b  lea     rbp, WPP_GLOBAL_Control
0x140013712  cmp     rcx, rbp
0x140013715  jnz     loc_140013869
0x14001371b  xor     r9d, r9d; Alertable
0x14001371e  mov     [rsp+0A8h+IoStatusBlock], 0; Timeout
0x140013727  xor     r8d, r8d; WaitMode
0x14001372a  lea     rcx, [r14+38h]; Object
0x14001372e  xor     edx, edx; WaitReason
0x140013730  call    cs:__imp_KeWaitForSingleObject
0x140013737  nop     dword ptr [rax+rax+00h]
0x14001373c  mov     r8, [rsp+0A8h+var_58]
0x140013741  mov     rdx, r13
0x140013744  mov     rcx, r14
0x140013747  call    VerifyEpoch
0x14001374c  mov     edi, eax
0x14001374e  test    eax, eax
0x140013750  js      loc_14001399A
0x140013756  mov     [rsi], rbx
0x140013759  mov     rbx, [rsp+0A8h+arg_8]
0x140013761  add     rsp, 70h
0x140013765  pop     r15
0x140013767  pop     r14
0x140013769  pop     r13
0x14001376b  pop     r12
0x14001376d  pop     rdi
0x14001376e  pop     rsi
0x14001376f  pop     rbp
0x140013770  retn
0x140013772  mov     r8d, [rsp+0A8h+arg_0]
0x14001377a  cmp     [rsp+0A8h+var_50.Information], r8
0x14001377f  jb      loc_14001388A
0x140013785  cmp     r8d, 10h
0x140013789  jb      loc_1400138E0
0x14001378f  movzx   eax, word ptr [rbx+8]
0x140013793  movzx   r12d, word ptr [rbx+0Ah]
0x140013798  movzx   edx, word ptr [rbx+0Eh]
0x14001379c  add     r12d, eax
0x14001379f  movzx   eax, word ptr [rbx+0Ch]
0x1400137a3  add     edx, eax
0x1400137a5  cmp     r12d, edx
0x1400137a8  cmovbe  r12d, edx
0x1400137ac  cmp     r12d, r8d
0x1400137af  ja      loc_140013936
0x1400137b5  lea     rbp, WPP_GLOBAL_Control
0x1400137bc  jmp     loc_14001371B
0x1400137c1  mov     edx, r12d
0x1400137c4  mov     rcx, rbp; FileHandle
0x1400137c7  call    TruncateRemoteDatabase
0x1400137cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400137d3  cmp     rcx, rdi
0x1400137d6  jz      short loc_1400137B5
0x1400137d8  mov     eax, [rcx+2Ch]
0x1400137db  test    al, 1
0x1400137dd  jz      short loc_1400137B5
0x1400137df  mov     rcx, [rcx+18h]
0x1400137e3  mov     edx, 2Eh ; '.'
0x1400137e8  call    WPP_SF_
0x1400137ed  jmp     short loc_1400137B5
0x1400137ef  cmp     r9d, 0C0000011h
0x1400137f6  jnz     short loc_140013821
0x1400137f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400137ff  cmp     rcx, rdi
0x140013802  jz      short loc_1400137B5
0x140013804  mov     eax, [rcx+2Ch]
0x140013807  test    al, 1
0x140013809  jz      short loc_1400137B5
0x14001380b  mov     edx, 2Dh ; '-'
0x140013810  mov     r9d, 0C0000011h
0x140013816  mov     rcx, [rcx+18h]
0x14001381a  call    WPP_SF_L
0x14001381f  jmp     short loc_1400137B5
0x140013821  mov     rcx, cs:WPP_GLOBAL_Control
0x140013828  cmp     rcx, rdi
0x14001382b  jz      short loc_1400137B5
0x14001382d  mov     eax, [rcx+2Ch]
0x140013830  test    al, 1
0x140013832  jz      short loc_1400137B5
0x140013834  mov     edx, 2Ch ; ','
0x140013839  jmp     short loc_140013816
0x14001383b  mov     rcx, cs:WPP_GLOBAL_Control
0x140013842  cmp     rcx, rdi
0x140013845  jz      loc_1400137B5
0x14001384b  mov     eax, [rcx+2Ch]
0x14001384e  test    al, 4
0x140013850  jz      loc_1400137B5
0x140013856  mov     rcx, [rcx+18h]
0x14001385a  mov     edx, 2Fh ; '/'
0x14001385f  call    WPP_SF_
0x140013864  jmp     loc_1400137B5
0x140013869  mov     eax, [rcx+2Ch]
0x14001386c  test    al, 1
0x14001386e  jz      loc_14001371B
0x140013874  mov     rcx, [rcx+18h]
0x140013878  mov     edx, 30h ; '0'
0x14001387d  mov     r9d, edi
0x140013880  call    WPP_SF_L
0x140013885  jmp     loc_14001371B
0x14001388a  mov     edx, r12d
0x14001388d  mov     rcx, rbp; FileHandle
0x140013890  call    TruncateRemoteDatabase
0x140013895  xor     edx, edx; Tag
0x140013897  mov     rcx, rbx; P
0x14001389a  call    cs:__imp_ExFreePoolWithTag
0x1400138a1  nop     dword ptr [rax+rax+00h]
0x1400138a6  xor     ebx, ebx
0x1400138a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400138af  lea     rbp, WPP_GLOBAL_Control
0x1400138b6  cmp     rcx, rbp
0x1400138b9  jz      loc_14001371B
0x1400138bf  mov     eax, [rcx+2Ch]
0x1400138c2  test    al, 1
0x1400138c4  jz      loc_14001371B
0x1400138ca  mov     rcx, [rcx+18h]
0x1400138ce  mov     edx, 31h ; '1'
0x1400138d3  mov     r9d, edi
0x1400138d6  call    WPP_SF_L
0x1400138db  jmp     loc_14001371B
0x1400138e0  mov     edx, r12d
0x1400138e3  mov     rcx, rbp; FileHandle
0x1400138e6  call    TruncateRemoteDatabase
0x1400138eb  xor     edx, edx; Tag
0x1400138ed  mov     rcx, rbx; P
0x1400138f0  call    cs:__imp_ExFreePoolWithTag
0x1400138f7  nop     dword ptr [rax+rax+00h]
0x1400138fc  xor     ebx, ebx
0x1400138fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140013905  lea     rbp, WPP_GLOBAL_Control
0x14001390c  cmp     rcx, rbp
0x14001390f  jz      loc_14001371B
0x140013915  mov     eax, [rcx+2Ch]
0x140013918  test    al, 1
0x14001391a  jz      loc_14001371B
0x140013920  mov     rcx, [rcx+18h]
0x140013924  mov     edx, 32h ; '2'
0x140013929  mov     r9d, edi
0x14001392c  call    WPP_SF_L
0x140013931  jmp     loc_14001371B
0x140013936  mov     edx, [rsp+0A8h+arg_10]
0x14001393d  mov     rcx, rbp; FileHandle
0x140013940  call    TruncateRemoteDatabase
0x140013945  xor     edx, edx; Tag
0x140013947  mov     rcx, rbx; P
0x14001394a  call    cs:__imp_ExFreePoolWithTag
0x140013951  nop     dword ptr [rax+rax+00h]
0x140013956  xor     ebx, ebx
0x140013958  mov     rcx, cs:WPP_GLOBAL_Control
0x14001395f  lea     rbp, WPP_GLOBAL_Control
0x140013966  cmp     rcx, rbp
0x140013969  jz      loc_14001371B
0x14001396f  mov     eax, [rcx+2Ch]
0x140013972  test    al, 1
0x140013974  jz      loc_14001371B
0x14001397a  mov     eax, [rsp+0A8h+arg_0]
0x140013981  mov     r9d, r12d
0x140013984  mov     rcx, [rcx+18h]
0x140013988  mov     dword ptr [rsp+0A8h+Buffer], edi
0x14001398c  mov     dword ptr [rsp+0A8h+IoStatusBlock], eax
0x140013990  call    WPP_SF_ddL
0x140013995  jmp     loc_14001371B
0x14001399a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400139a1  cmp     rcx, rbp
0x1400139a4  jz      short loc_1400139BF
0x1400139a6  mov     edx, [rcx+2Ch]
0x1400139a9  test    dl, 1
0x1400139ac  jz      short loc_1400139BF
0x1400139ae  mov     rcx, [rcx+18h]
0x1400139b2  mov     edx, 34h ; '4'
0x1400139b7  mov     r9d, edi
0x1400139ba  call    WPP_SF_L
0x1400139bf  test    rbx, rbx
0x1400139c2  jz      short loc_1400139D5
0x1400139c4  xor     edx, edx; Tag
0x1400139c6  mov     rcx, rbx; P
0x1400139c9  call    cs:__imp_ExFreePoolWithTag
0x1400139d0  nop     dword ptr [rax+rax+00h]
0x1400139d5  xor     eax, eax
0x1400139d7  mov     [rsi], rax
0x1400139da  mov     eax, edi
0x1400139dc  jmp     loc_140013759
```
