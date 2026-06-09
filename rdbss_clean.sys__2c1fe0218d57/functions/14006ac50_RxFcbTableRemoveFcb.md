# RxFcbTableRemoveFcb

- ea: `0x14006ac50`
- end: `0x14006ae60`
- name: `RxFcbTableRemoveFcb`
- size: `528`
- prototype: `NTSTATUS __stdcall(PRX_FCB_TABLE FcbTable, PFCB Fcb)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14006ab80`

## callees

- `0x140014d10`
- `0x14006ac50`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006ae1a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006ae1a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006ac77`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14006ac77`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ac9a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14006ac9a`
- `ntoskrnl!RtlRbRemoveNode` at `0x14006ad4c`
- `ntoskrnl!RtlRbRemoveNode` at `0x14006ad4c`

## pseudocode

```c
NTSTATUS __stdcall RxFcbTableRemoveFcb(PRX_FCB_TABLE FcbTable, PFCB Fcb)
{
  int v2; // ebp
  PMINIRDR_DISPATCH *p_MRxDispatch; // rdi
  struct _RX_FCB_TABLE *i; // r8
  struct _LIST_ENTRY *Flink; // r9
  __int64 v7; // r8
  unsigned __int64 v8; // r8
  __int64 v9; // rsi
  struct _LIST_ENTRY *v10; // rax
  __int64 v11; // rcx
  unsigned __int64 j; // rdx
  _QWORD *v14; // r9
  unsigned __int64 v15; // rax
  PMINIRDR_DISPATCH **v16; // rcx

  v2 = (int)Fcb;
  p_MRxDispatch = &Fcb->MRxDispatch;
  ExAcquirePushLockExclusiveEx(&FcbTable->TableLock, 0);
  for ( i = (struct _RX_FCB_TABLE *)FcbTable->TableLock.SystemResourcesList.Blink;
        i != (struct _RX_FCB_TABLE *)&FcbTable->TableLock.SystemResourcesList.Blink;
        i = *(struct _RX_FCB_TABLE **)&i->NodeTypeCode )
  {
    if ( (PMINIRDR_DISPATCH *)i->TableLock.OwnerTable == p_MRxDispatch )
    {
      j = (unsigned __int64)p_MRxDispatch[1];
      if ( j )
      {
        v14 = *(_QWORD **)j;
        if ( *(_QWORD *)j )
        {
          do
          {
            j = (unsigned __int64)v14;
            v14 = (_QWORD *)*v14;
          }
          while ( v14 );
        }
      }
      else
      {
        v15 = (unsigned __int64)p_MRxDispatch;
        for ( j = (unsigned __int64)p_MRxDispatch[2] & 0xFFFFFFFFFFFFFFFCuLL;
              j;
              j = *(_QWORD *)(j + 16) & 0xFFFFFFFFFFFFFFFCuLL )
        {
          if ( *(_QWORD *)j == v15 )
            break;
          v15 = j;
        }
      }
      i->TableLock.OwnerTable = (POWNER_ENTRY)j;
    }
  }
  ExReleasePushLockExclusiveEx(&FcbTable->TableLock, 0);
  Flink = FcbTable->HashBuckets[2].Flink;
  if ( Flink )
  {
    v7 = *((unsigned int *)p_MRxDispatch + 11);
    v8 = ((((unsigned __int64)(((unsigned __int16)v7
                              ^ (unsigned __int16)((unsigned __int64)(unsigned int)v7 >> 6))
                             & 0x3F00) >> 6)
         ^ *((_DWORD *)p_MRxDispatch + 11)
         & 0xFC) >> 2)
       ^ ((unsigned __int8)((v7 ^ ((unsigned __int64)(unsigned int)v7 >> 6)) >> 20)
        ^ v7
        & 3)
       & 0x3F;
    if ( (PMINIRDR_DISPATCH *)((unsigned __int64)*(&Flink->Flink + v8) & 0xFFFFFFFFFFFFFFFEuLL) == p_MRxDispatch )
      *((_QWORD *)&Flink->Flink + v8) = 0;
    v9 = 0;
    do
    {
      if ( !*((_WORD *)p_MRxDispatch + 20) )
        break;
      v10 = FcbTable->HashBuckets[2].Flink;
      v11 = *((_QWORD *)&v10->Flink + v9);
      if ( v11 )
      {
        if ( (v11 & 1) != 0 )
        {
          v16 = (PMINIRDR_DISPATCH **)(v11 & 0xFFFFFFFFFFFFFFFEuLL);
          if ( *v16 == p_MRxDispatch )
          {
            *((_QWORD *)&v10->Flink + v9) = 0;
            ExFreePoolWithTag(v16, 0);
            --*((_WORD *)p_MRxDispatch + 20);
          }
        }
      }
      v9 = (unsigned int)(v9 + 1);
    }
    while ( (int)v9 < 64 );
  }
  RtlRbRemoveNode(&FcbTable->HashBuckets[1], p_MRxDispatch);
  *(_OWORD *)p_MRxDispatch = 0;
  p_MRxDispatch[2] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      14,
      (unsigned int)&WPP_518c92af35303f374eeedacc3593600d_Traceguids,
      v2,
      (__int64)(p_MRxDispatch + 3));
  }
  --FcbTable->FailedLookups;
  _InterlockedIncrement((volatile signed __int32 *)&FcbTable->Version);
  return 0;
}

```

## disassembly

```asm
0x14006ac50  mov     [rsp+arg_10], rbx
0x14006ac55  mov     [rsp+arg_18], rbp
0x14006ac5a  push    rdi
0x14006ac5b  sub     rsp, 30h
0x14006ac5f  mov     rbp, rdx
0x14006ac62  mov     [rsp+38h+arg_0], rsi
0x14006ac67  mov     rbx, rcx
0x14006ac6a  lea     rdi, [rdx+138h]
0x14006ac71  xor     edx, edx
0x14006ac73  add     rcx, 18h
0x14006ac77  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14006ac7e  nop     dword ptr [rax+rax+00h]
0x14006ac83  mov     r8, [rbx+20h]
0x14006ac87  lea     rcx, [rbx+20h]
0x14006ac8b  cmp     r8, rcx
0x14006ac8e  jnz     loc_14006ADB3
0x14006ac94  xor     edx, edx
0x14006ac96  lea     rcx, [rbx+18h]
0x14006ac9a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14006aca1  nop     dword ptr [rax+rax+00h]
0x14006aca6  mov     r9, [rbx+0A8h]
0x14006acad  test    r9, r9
0x14006acb0  jz      loc_14006AD42
0x14006acb6  mov     r8d, [rdi+2Ch]
0x14006acba  mov     ecx, r8d
0x14006acbd  mov     [rsp+38h+arg_8], r15
0x14006acc2  mov     edx, r8d
0x14006acc5  and     ecx, 0FCh
0x14006accb  shr     rdx, 6
0x14006accf  mov     rax, rdx
0x14006acd2  xor     rdx, r8
0x14006acd5  xor     rax, r8
0x14006acd8  shr     rdx, 14h
0x14006acdc  and     eax, 3F00h
0x14006ace1  and     r8d, 3
0x14006ace5  shr     rax, 6
0x14006ace9  xor     r8, rdx
0x14006acec  xor     rcx, rax
0x14006acef  and     r8d, 3Fh
0x14006acf3  shr     rcx, 2
0x14006acf7  xor     r8, rcx
0x14006acfa  mov     rax, [r9+r8*8]
0x14006acfe  and     rax, 0FFFFFFFFFFFFFFFEh
0x14006ad02  cmp     rax, rdi
0x14006ad05  jnz     short loc_14006AD0F
0x14006ad07  mov     qword ptr [r9+r8*8], 0
0x14006ad0f  xor     esi, esi
0x14006ad11  mov     r15d, 0FFFFh
0x14006ad17  cmp     word ptr [rdi+28h], 0
0x14006ad1c  jbe     short loc_14006AD3D
0x14006ad1e  mov     rax, [rbx+0A8h]
0x14006ad25  mov     rcx, [rax+rsi*8]
0x14006ad29  lea     rdx, [rax+rsi*8]
0x14006ad2d  test    rcx, rcx
0x14006ad30  jnz     loc_14006ADFB
0x14006ad36  inc     esi
0x14006ad38  cmp     esi, 40h ; '@'
0x14006ad3b  jl      short loc_14006AD17
0x14006ad3d  mov     r15, [rsp+38h+arg_8]
0x14006ad42  lea     rcx, [rbx+98h]
0x14006ad49  mov     rdx, rdi
0x14006ad4c  call    cs:__imp_RtlRbRemoveNode
0x14006ad53  nop     dword ptr [rax+rax+00h]
0x14006ad58  xorps   xmm0, xmm0
0x14006ad5b  xor     eax, eax
0x14006ad5d  movups  xmmword ptr [rdi], xmm0
0x14006ad60  mov     [rdi+10h], rax
0x14006ad64  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ad6b  lea     rax, WPP_GLOBAL_Control
0x14006ad72  mov     rsi, [rsp+38h+arg_0]
0x14006ad77  cmp     rcx, rax
0x14006ad7a  jz      short loc_14006AD89
0x14006ad7c  test    dword ptr [rcx+2Ch], 100h
0x14006ad83  jnz     loc_14006AE30
0x14006ad89  dec     dword ptr [rbx+10h]
0x14006ad8c  lock inc dword ptr [rbx+4]
0x14006ad90  mov     rbx, [rsp+38h+arg_10]
0x14006ad95  xor     eax, eax
0x14006ad97  mov     rbp, [rsp+38h+arg_18]
0x14006ad9c  add     rsp, 30h
0x14006ada0  pop     rdi
0x14006ada1  retn
0x14006ada3  mov     [r8+28h], rdx
0x14006ada7  mov     r8, [r8]
0x14006adaa  cmp     r8, rcx
0x14006adad  jz      loc_14006AC94
0x14006adb3  cmp     [r8+28h], rdi
0x14006adb7  jnz     short loc_14006ADA7
0x14006adb9  mov     rdx, [rdi+8]
0x14006adbd  test    rdx, rdx
0x14006adc0  jz      short loc_14006ADDA
0x14006adc2  mov     r9, [rdx]
0x14006adc5  test    r9, r9
0x14006adc8  jz      short loc_14006ADA3
0x14006adca  mov     rax, [r9]
0x14006adcd  mov     rdx, r9
0x14006add0  mov     r9, rax
0x14006add3  test    rax, rax
0x14006add6  jnz     short loc_14006ADCA
0x14006add8  jmp     short loc_14006ADA3
0x14006adda  mov     rdx, [rdi+10h]
0x14006adde  mov     rax, rdi
0x14006ade1  and     rdx, 0FFFFFFFFFFFFFFFCh
0x14006ade5  jz      short loc_14006ADA3
0x14006ade7  cmp     [rdx], rax
0x14006adea  jz      short loc_14006ADA3
0x14006adec  mov     rax, rdx
0x14006adef  mov     rdx, [rdx+10h]
0x14006adf3  and     rdx, 0FFFFFFFFFFFFFFFCh
0x14006adf7  jnz     short loc_14006ADE7
0x14006adf9  jmp     short loc_14006ADA3
0x14006adfb  test    cl, 1
0x14006adfe  jz      loc_14006AD36
0x14006ae04  and     rcx, 0FFFFFFFFFFFFFFFEh; P
0x14006ae08  cmp     [rcx], rdi
0x14006ae0b  jnz     loc_14006AD36
0x14006ae11  mov     qword ptr [rdx], 0
0x14006ae18  xor     edx, edx; Tag
0x14006ae1a  call    cs:__imp_ExFreePoolWithTag
0x14006ae21  nop     dword ptr [rax+rax+00h]
0x14006ae26  add     [rdi+28h], r15w
0x14006ae2b  jmp     loc_14006AD36
0x14006ae30  cmp     byte ptr [rcx+29h], 4
0x14006ae34  jb      loc_14006AD89
0x14006ae3a  mov     rcx, [rcx+18h]
0x14006ae3e  lea     rax, [rdi+18h]
0x14006ae42  mov     edx, 0Eh
0x14006ae47  mov     [rsp+38h+var_18], rax
0x14006ae4c  mov     r9, rbp
0x14006ae4f  lea     r8, WPP_518c92af35303f374eeedacc3593600d_Traceguids
0x14006ae56  call    WPP_SF_qZ
0x14006ae5b  jmp     loc_14006AD89
```
