# SmbWskIndicateFullMessageToRdr

- ea: `0x1400137f0`
- end: `0x140013ca2`
- name: `SmbWskIndicateFullMessageToRdr`
- size: `1202`
- prototype: `__int64 __fastcall(__int64, _DWORD *, unsigned int, __int64)`
- caller_count: `5`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x140012650`
- `0x140035f90`
- `0x140050fe0`
- `0x140051b60`
- `0x14008d030`

## callees

- `0x1400137f0`
- `0x140019470`
- `0x14002d320`
- `0x140035bb0`
- `0x14003838c`
- `0x140039fa8`
- `0x14003fa24`
- `0x1400400c4`
- `0x14004a840`
- `0x14005446c`
- `0x140054e0c`
- `0x140059f00`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x140013917`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013917`
- `ntoskrnl!ExAllocatePool2` at `0x140013aff`
- `ntoskrnl!ExAllocatePool2` at `0x140013b32`
- `ntoskrnl!ExAllocatePool2` at `0x140013aff`
- `ntoskrnl!ExAllocatePool2` at `0x140013b32`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013972`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013b4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013c7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013972`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013b4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013c7b`
- `rdbss!RxPostToWorkerThread` at `0x140013c16`
- `rdbss!RxPostToWorkerThread` at `0x140013c16`

## pseudocode

```c
__int64 __fastcall SmbWskIndicateFullMessageToRdr(__int64 a1, _DWORD *a2, unsigned int a3, __int64 a4)
{
  char v5; // r13
  unsigned int v6; // esi
  bool v9; // bp
  __int64 v10; // rdx
  int v11; // ebx
  __int64 v12; // r8
  bool v13; // zf
  ULONG v14; // edx
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  _QWORD *Pool2; // rbx
  _DWORD *v19; // rax
  _DWORD *v20; // rbp
  ULONG v21; // edx
  PVOID pContext; // [rsp+20h] [rbp-58h]
  unsigned int v23; // [rsp+90h] [rbp+18h] BYREF
  _DWORD *v24; // [rsp+98h] [rbp+20h] BYREF

  v23 = a3;
  v5 = *(_BYTE *)(a4 + 52) & 1;
  v6 = a3;
  *(_DWORD *)(a4 + 4) = 0;
  while ( 1 )
  {
    while ( 1 )
    {
      v9 = (*(_BYTE *)(a4 + 52) & 2) != 0;
      if ( v6 < 4 )
        goto LABEL_60;
      if ( *a2 != 1112364028 )
        break;
      v13 = (*(_DWORD *)a4 & 0x20000000) == 0;
      v24 = 0;
      v23 = 0;
      if ( !v13 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          v16 = 19;
LABEL_59:
          WPP_SF_(v15->AttachedDevice, v16, WPP_0d49653a9ac732ed3d344abd53855d0a_Traceguids);
        }
LABEL_60:
        v11 = -1073741629;
        goto LABEL_61;
      }
      if ( KeGetCurrentIrql() >= 2u )
        goto LABEL_41;
      v11 = RxCeDecompressData(a1, (_DWORD)a2, v6, (unsigned int)&v24, (__int64)&v23);
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            20,
            WPP_0d49653a9ac732ed3d344abd53855d0a_Traceguids,
            (unsigned int)v11);
        }
        goto LABEL_61;
      }
      if ( v9 )
      {
        v14 = 1834184261;
        if ( (*(_DWORD *)a4 & 0x10000000) == 0 )
          v14 = 1834181966;
        ExFreePoolWithTag(a2, v14);
      }
      *(_DWORD *)a4 |= 0x20000000u;
      *(_BYTE *)(a4 + 52) |= 2u;
      a2 = v24;
      *(_DWORD *)(a4 + 4) = v6;
      v6 = v23;
    }
    if ( *a2 != 1112364029 )
    {
      if ( (unsigned int)(*a2 - 1112364030) < 2 )
        return SmbWskIndicateFullMessageToRdrTail(a1, a2, v6, a4);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_0d49653a9ac732ed3d344abd53855d0a_Traceguids);
      }
      goto LABEL_60;
    }
    if ( (*(_DWORD *)a4 & 0x30000000) != 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v16 = 16;
        goto LABEL_59;
      }
      goto LABEL_60;
    }
    if ( !v5 && v6 >= dword_14007D0A4 && (*(_BYTE *)(a4 + 52) & 2) != 0 )
      break;
    v11 = RxCeDecryptData(a1, a2, v6, &v23, a4 + 8);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qLqL(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          (unsigned int)WPP_0d49653a9ac732ed3d344abd53855d0a_Traceguids,
          (_DWORD)a2,
          v23,
          a1,
          v11);
      }
      goto LABEL_61;
    }
    v6 = v23;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      LODWORD(pContext) = v23;
      WPP_SF_qDiq(WPP_GLOBAL_Control->AttachedDevice, v10, v12, a2, pContext, *(_QWORD *)(a4 + 8), a1);
    }
    *(_DWORD *)a4 |= 0x10000000u;
  }
LABEL_41:
  if ( !(unsigned __int8)VctReferenceEndpointSafe(a1) )
  {
    v11 = -1073741300;
    goto LABEL_61;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(66, 144, 1682143314);
  if ( !Pool2 )
  {
    v11 = -1073741670;
LABEL_61:
    if ( v9 )
    {
      v21 = 1834184772;
      if ( (*(_DWORD *)a4 & 0x20000000) == 0 )
        v21 = 1834181966;
      ExFreePoolWithTag(a2, v21);
    }
    return (unsigned int)v11;
  }
  if ( v9 )
  {
    v20 = a2;
  }
  else
  {
    v19 = (_DWORD *)ExAllocatePool2(66, v6, 1834181966);
    v20 = v19;
    if ( !v19 )
    {
      ExFreePoolWithTag(Pool2, 0x64437852u);
      return 3221225626LL;
    }
    memmove(v19, a2, v6);
  }
  Pool2[16] = v20;
  *((_DWORD *)Pool2 + 34) = v6;
  *Pool2 = a1;
  *(_BYTE *)(a4 + 52) |= 3u;
  *(_OWORD *)(Pool2 + 1) = *(_OWORD *)a4;
  *(_OWORD *)(Pool2 + 3) = *(_OWORD *)(a4 + 16);
  *(_OWORD *)(Pool2 + 5) = *(_OWORD *)(a4 + 32);
  Pool2[7] = *(_QWORD *)(a4 + 48);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qDq(
      WPP_GLOBAL_Control->AttachedDevice,
      22,
      WPP_0d49653a9ac732ed3d344abd53855d0a_Traceguids,
      Pool2[16],
      *((_DWORD *)Pool2 + 34),
      a1);
  }
  RxPostToWorkerThread(
    MRxSmbDeviceObject,
    NormalWorkQueue,
    (PRX_WORK_QUEUE_ITEM)(Pool2 + 8),
    SmbWskIndicateFullMessageToRdrWorkerRoutine,
    Pool2);
  return 0;
}

```

## disassembly

```asm
0x1400137f0  mov     [rsp+arg_0], rbx
0x1400137f5  mov     [rsp+arg_10], r8d
0x1400137fa  push    rbp
0x1400137fb  push    rsi
0x1400137fc  push    rdi
0x1400137fd  push    r12
0x1400137ff  push    r13
0x140013801  push    r14
0x140013803  push    r15
0x140013805  sub     rsp, 40h
0x140013809  movzx   r13d, byte ptr [r9+34h]
0x14001380e  mov     rdi, r9
0x140013811  and     r13b, 1
0x140013815  mov     esi, r8d
0x140013818  xor     r15d, r15d
0x14001381b  mov     r14, rdx
0x14001381e  mov     [r9+4], r15d
0x140013822  mov     r12, rcx
0x140013825  lea     rbx, WPP_GLOBAL_Control
0x14001382c  nop     dword ptr [rax+00h]
0x140013830  movzx   ebp, byte ptr [rdi+34h]
0x140013834  shr     bpl, 1
0x140013837  and     bpl, 1
0x14001383b  cmp     esi, 4
0x14001383e  jb      loc_140013C5C
0x140013844  mov     r9d, [r14]
0x140013847  mov     eax, r9d
0x14001384a  sub     eax, 424D53FCh
0x14001384f  jz      loc_1400138FB
0x140013855  sub     eax, 1
0x140013858  jnz     loc_140013A32
0x14001385e  test    dword ptr [rdi], 30000000h
0x140013864  jnz     loc_140013A03
0x14001386a  test    r13b, r13b
0x14001386d  jnz     short loc_140013880
0x14001386f  cmp     esi, cs:dword_14007D0A4
0x140013875  jb      short loc_140013880
0x140013877  test    bpl, bpl
0x14001387a  jnz     loc_140013ADF
0x140013880  lea     r15, [rdi+8]
0x140013884  mov     r8d, esi
0x140013887  lea     r9, [rsp+78h+arg_10]
0x14001388f  mov     [rsp+78h+pContext], r15
0x140013894  mov     rdx, r14
0x140013897  mov     rcx, r12
0x14001389a  call    RxCeDecryptData
0x14001389f  mov     ebx, eax
0x1400138a1  test    eax, eax
0x1400138a3  js      loc_1400139A6
0x1400138a9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400138b0  lea     rbx, WPP_GLOBAL_Control
0x1400138b7  mov     esi, [rsp+78h+arg_10]
0x1400138be  cmp     rcx, rbx
0x1400138c1  jz      short loc_1400138ED
0x1400138c3  mov     eax, [rcx+2Ch]
0x1400138c6  test    al, 4
0x1400138c8  jz      short loc_1400138ED
0x1400138ca  cmp     byte ptr [rcx+29h], 4
0x1400138ce  jb      short loc_1400138ED
0x1400138d0  mov     rax, [r15]
0x1400138d3  mov     r9, r14
0x1400138d6  mov     rcx, [rcx+18h]
0x1400138da  mov     [rsp+78h+var_48], r12
0x1400138df  mov     [rsp+78h+var_50], rax
0x1400138e4  mov     dword ptr [rsp+78h+pContext], esi
0x1400138e8  call    WPP_SF_qDiq
0x1400138ed  or      dword ptr [rdi], 10000000h
0x1400138f3  xor     r15d, r15d
0x1400138f6  jmp     loc_140013830
0x1400138fb  test    dword ptr [rdi], 20000000h
0x140013901  mov     [rsp+78h+arg_18], r15
0x140013909  mov     [rsp+78h+arg_10], r15d
0x140013911  jnz     loc_140013C2E
0x140013917  call    cs:__imp_KeGetCurrentIrql
0x14001391e  nop     dword ptr [rax+rax+00h]
0x140013923  cmp     al, 2
0x140013925  jnb     loc_140013ADF
0x14001392b  lea     rax, [rsp+78h+arg_10]
0x140013933  mov     r8d, esi
0x140013936  lea     r9, [rsp+78h+arg_18]
0x14001393e  mov     [rsp+78h+pContext], rax
0x140013943  mov     rdx, r14
0x140013946  mov     rcx, r12
0x140013949  call    RxCeDecompressData
0x14001394e  mov     ebx, eax
0x140013950  test    eax, eax
0x140013952  js      loc_140013A96
0x140013958  test    bpl, bpl
0x14001395b  jz      short loc_14001397E
0x14001395d  test    dword ptr [rdi], 10000000h
0x140013963  mov     rcx, r14; P
0x140013966  mov     edx, 6D536E45h
0x14001396b  jnz     short loc_140013972
0x14001396d  mov     edx, 6D53654Eh; Tag
0x140013972  call    cs:__imp_ExFreePoolWithTag
0x140013979  nop     dword ptr [rax+rax+00h]
0x14001397e  or      dword ptr [rdi], 20000000h
0x140013984  or      byte ptr [rdi+34h], 2
0x140013988  mov     r14, [rsp+78h+arg_18]
0x140013990  mov     [rdi+4], esi
0x140013993  mov     esi, [rsp+78h+arg_10]
0x14001399a  mov     [rsp+78h+arg_10], esi
0x1400139a1  jmp     loc_140013825
0x1400139a6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400139ad  lea     rax, WPP_GLOBAL_Control
0x1400139b4  cmp     rcx, rax
0x1400139b7  jz      loc_140013C61
0x1400139bd  mov     eax, [rcx+2Ch]
0x1400139c0  test    al, 1
0x1400139c2  jz      loc_140013C61
0x1400139c8  cmp     byte ptr [rcx+29h], 1
0x1400139cc  jb      loc_140013C61
0x1400139d2  mov     eax, [rsp+78h+arg_10]
0x1400139d9  lea     r8, WPP_0d49653a9ac732ed3d344abd53855d0a_Traceguids
0x1400139e0  mov     rcx, [rcx+18h]
0x1400139e4  mov     edx, 11h
0x1400139e9  mov     dword ptr [rsp+78h+var_48], ebx
0x1400139ed  mov     r9, r14
0x1400139f0  mov     [rsp+78h+var_50], r12
0x1400139f5  mov     dword ptr [rsp+78h+pContext], eax
0x1400139f9  call    WPP_SF_qLqL
0x1400139fe  jmp     loc_140013C61
0x140013a03  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140013a0a  cmp     rcx, rbx
0x140013a0d  jz      loc_140013C5C
0x140013a13  mov     eax, [rcx+2Ch]
0x140013a16  test    al, 4
0x140013a18  jz      loc_140013C5C
0x140013a1e  cmp     byte ptr [rcx+29h], 1
0x140013a22  jb      loc_140013C5C
0x140013a28  mov     edx, 10h
0x140013a2d  jmp     loc_140013C4C
0x140013a32  sub     eax, 1
0x140013a35  jz      short loc_140013A80
0x140013a37  cmp     eax, 1
0x140013a3a  jz      short loc_140013A80
0x140013a3c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140013a43  cmp     rcx, rbx
0x140013a46  jz      loc_140013C5C
0x140013a4c  mov     eax, [rcx+2Ch]
0x140013a4f  test    al, 1
0x140013a51  jz      loc_140013C5C
0x140013a57  cmp     byte ptr [rcx+29h], 1
0x140013a5b  jb      loc_140013C5C
0x140013a61  mov     rcx, [rcx+18h]
0x140013a65  lea     r8, WPP_0d49653a9ac732ed3d344abd53855d0a_Traceguids
0x140013a6c  mov     edx, 15h
0x140013a71  mov     [rsp+78h+pContext], r12
0x140013a76  call    WPP_SF_dq
0x140013a7b  jmp     loc_140013C5C
0x140013a80  mov     r9, rdi
0x140013a83  mov     r8d, esi
0x140013a86  mov     rdx, r14
0x140013a89  mov     rcx, r12
0x140013a8c  call    SmbWskIndicateFullMessageToRdrTail
0x140013a91  jmp     loc_140013C89
0x140013a96  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140013a9d  lea     rax, WPP_GLOBAL_Control
0x140013aa4  cmp     rcx, rax
0x140013aa7  jz      loc_140013C61
0x140013aad  mov     eax, [rcx+2Ch]
0x140013ab0  test    al, 4
0x140013ab2  jz      loc_140013C61
0x140013ab8  cmp     byte ptr [rcx+29h], 4
0x140013abc  jb      loc_140013C61
0x140013ac2  mov     rcx, [rcx+18h]
0x140013ac6  lea     r8, WPP_0d49653a9ac732ed3d344abd53855d0a_Traceguids
0x140013acd  mov     edx, 14h
0x140013ad2  mov     r9d, ebx
0x140013ad5  call    WPP_SF_d
0x140013ada  jmp     loc_140013C61
0x140013adf  mov     rcx, r12
0x140013ae2  call    VctReferenceEndpointSafe
0x140013ae7  test    al, al
0x140013ae9  jz      loc_140013C27
0x140013aef  mov     edx, 90h
0x140013af4  mov     ecx, 42h ; 'B'
0x140013af9  mov     r8d, 64437852h
0x140013aff  call    cs:__imp_ExAllocatePool2
0x140013b06  nop     dword ptr [rax+rax+00h]
0x140013b0b  mov     rbx, rax
0x140013b0e  test    rax, rax
0x140013b11  jnz     short loc_140013B1D
0x140013b13  mov     ebx, 0C000009Ah
0x140013b18  jmp     loc_140013C61
0x140013b1d  test    bpl, bpl
0x140013b20  jnz     short loc_140013B77
0x140013b22  mov     r8d, 6D53654Eh
0x140013b28  mov     edx, esi
0x140013b2a  mov     ecx, 42h ; 'B'
0x140013b2f  mov     r15d, esi
0x140013b32  call    cs:__imp_ExAllocatePool2
0x140013b39  nop     dword ptr [rax+rax+00h]
0x140013b3e  mov     rbp, rax
0x140013b41  test    rax, rax
0x140013b44  jnz     short loc_140013B64
0x140013b46  mov     edx, 64437852h; Tag
0x140013b4b  mov     rcx, rbx; P
0x140013b4e  call    cs:__imp_ExFreePoolWithTag
0x140013b55  nop     dword ptr [rax+rax+00h]
0x140013b5a  mov     eax, 0C000009Ah
0x140013b5f  jmp     loc_140013C89
0x140013b64  mov     r8, r15; Size
0x140013b67  mov     rdx, r14; Src
0x140013b6a  mov     rcx, rax; void *
0x140013b6d  call    memmove
0x140013b72  xor     r15d, r15d
0x140013b75  jmp     short loc_140013B7A
0x140013b77  mov     rbp, r14
0x140013b7a  mov     [rbx+80h], rbp
0x140013b81  mov     [rbx+88h], esi
0x140013b87  mov     [rbx], r12
0x140013b8a  or      byte ptr [rdi+34h], 3
0x140013b8e  movups  xmm0, xmmword ptr [rdi]
0x140013b91  movups  xmmword ptr [rbx+8], xmm0
0x140013b95  movups  xmm1, xmmword ptr [rdi+10h]
0x140013b99  movups  xmmword ptr [rbx+18h], xmm1
0x140013b9d  movups  xmm0, xmmword ptr [rdi+20h]
0x140013ba1  movups  xmmword ptr [rbx+28h], xmm0
0x140013ba5  movsd   xmm1, qword ptr [rdi+30h]
0x140013baa  movsd   qword ptr [rbx+38h], xmm1
0x140013baf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140013bb6  lea     rax, WPP_GLOBAL_Control
0x140013bbd  cmp     rcx, rax
0x140013bc0  jz      short loc_140013BFA
0x140013bc2  mov     eax, [rcx+2Ch]
0x140013bc5  test    al, 4
0x140013bc7  jz      short loc_140013BFA
0x140013bc9  cmp     byte ptr [rcx+29h], 4
0x140013bcd  jb      short loc_140013BFA
0x140013bcf  mov     eax, [rbx+88h]
0x140013bd5  lea     r8, WPP_0d49653a9ac732ed3d344abd53855d0a_Traceguids
0x140013bdc  mov     r9, [rbx+80h]
0x140013be3  mov     edx, 16h
0x140013be8  mov     rcx, [rcx+18h]
0x140013bec  mov     [rsp+78h+var_50], r12
0x140013bf1  mov     dword ptr [rsp+78h+pContext], eax
0x140013bf5  call    WPP_SF_qDq
0x140013bfa  mov     rcx, cs:MRxSmbDeviceObject; pMRxDeviceObject
0x140013c01  lea     r8, [rbx+40h]; pWorkQueueItem
0x140013c05  lea     r9, SmbWskIndicateFullMessageToRdrWorkerRoutine; Routine
0x140013c0c  mov     [rsp+78h+pContext], rbx; pContext
0x140013c11  mov     edx, 3; WorkQueueType
0x140013c16  call    cs:__imp_RxPostToWorkerThread
0x140013c1d  nop     dword ptr [rax+rax+00h]
0x140013c22  mov     eax, r15d
0x140013c25  jmp     short loc_140013C89
0x140013c27  mov     ebx, 0C000020Ch
0x140013c2c  jmp     short loc_140013C61
0x140013c2e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140013c35  cmp     rcx, rbx
0x140013c38  jz      short loc_140013C5C
0x140013c3a  mov     eax, [rcx+2Ch]
0x140013c3d  test    al, 4
0x140013c3f  jz      short loc_140013C5C
0x140013c41  cmp     byte ptr [rcx+29h], 1
0x140013c45  jb      short loc_140013C5C
0x140013c47  mov     edx, 13h
0x140013c4c  mov     rcx, [rcx+18h]
0x140013c50  lea     r8, WPP_0d49653a9ac732ed3d344abd53855d0a_Traceguids
0x140013c57  call    WPP_SF_
0x140013c5c  mov     ebx, 0C00000C3h
0x140013c61  test    bpl, bpl
0x140013c64  jz      short loc_140013C87
0x140013c66  test    dword ptr [rdi], 20000000h
0x140013c6c  mov     rcx, r14; P
0x140013c6f  mov     edx, 6D537044h
0x140013c74  jnz     short loc_140013C7B
0x140013c76  mov     edx, 6D53654Eh; Tag
0x140013c7b  call    cs:__imp_ExFreePoolWithTag
0x140013c82  nop     dword ptr [rax+rax+00h]
0x140013c87  mov     eax, ebx
0x140013c89  mov     rbx, [rsp+78h+arg_0]
0x140013c91  add     rsp, 40h
0x140013c95  pop     r15
0x140013c97  pop     r14
0x140013c99  pop     r13
0x140013c9b  pop     r12
0x140013c9d  pop     rdi
0x140013c9e  pop     rsi
0x140013c9f  pop     rbp
0x140013ca0  retn
```
