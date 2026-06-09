# ndisCopyPeriodicReceiveNbl

- ea: `0x1400300b0`
- end: `0x1400304a0`
- name: `ndisCopyPeriodicReceiveNbl`
- size: `1008`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14002fef0`

## callees

- `0x1400231d0`
- `0x1400300b0`
- `0x140030d30`
- `0x14005a6b0`
- `0x1400eb380`
- `0x1400eb4c0`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x1400300f4`
- `ntoskrnl!MmSizeOfMdl` at `0x1400300f4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003040e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003043d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003040e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14003043d`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140030187`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140030187`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400301c6`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400301c6`
- `ntoskrnl!ExAllocatePool3` at `0x1400303df`
- `ntoskrnl!ExAllocatePool3` at `0x1400303df`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400301e1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400301e1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140030121`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140030121`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400eeb21`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400eeb21`

## pseudocode

```c
PNET_BUFFER_LIST __fastcall ndisCopyPeriodicReceiveNbl(__int64 a1, int a2, __int64 a3)
{
  __int64 v3; // rdi
  PNET_BUFFER_LIST NetBufferAndNetBufferList; // rbp
  __int64 v6; // r13
  SIZE_T v7; // r15
  __int64 v8; // rax
  __int64 v9; // rsi
  struct _NPAGED_LOOKASIDE_LIST *v10; // r12
  struct _MDL *v11; // rax
  struct _MDL *v12; // r14
  struct _MDL *v14; // r13
  char *MappedSystemVa; // rax
  __int64 v16; // rdx
  unsigned int ByteCount; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // esi
  __int64 v20; // rdi
  const struct _EVENT_DESCRIPTOR *v21; // rdx
  char *i; // rcx
  char *v23; // rcx
  unsigned int v24; // edi
  PVOID v25; // rax
  __int64 v26; // rax
  struct _GUID v27; // xmm0
  __int64 v28; // rax
  unsigned __int8 DataOffset; // [rsp+20h] [rbp-A8h]
  const struct _GUID *DataLength; // [rsp+28h] [rbp-A0h]
  __int64 v31; // [rsp+40h] [rbp-88h]
  char *v32; // [rsp+40h] [rbp-88h]
  struct _GUID v34; // [rsp+50h] [rbp-78h] BYREF
  struct _GUID v35; // [rsp+60h] [rbp-68h] BYREF

  v3 = *(_QWORD *)(a3 + 8);
  NetBufferAndNetBufferList = 0;
  *(_QWORD *)&v35.Data1 = 0;
  v6 = 0;
  v7 = *(unsigned int *)(v3 + 24);
  v8 = ((unsigned int)MmSizeOfMdl((PVOID)0xFFF, v7) + 7) & 0xFFFFFFF8;
  v9 = (unsigned int)v8;
  v31 = (unsigned int)v8;
  if ( (unsigned int)v7 <= 0x64 )
  {
    v10 = &Lookaside;
LABEL_3:
    v11 = (struct _MDL *)ExAllocateFromNPagedLookasideList(v10);
    goto LABEL_4;
  }
  if ( (unsigned int)v7 <= 0x5EE )
  {
    v10 = &stru_140121500;
    goto LABEL_3;
  }
  if ( (v7 + v8) >> 32 )
    return NetBufferAndNetBufferList;
  v34 = 0;
  LOBYTE(v34.Data1) = 1;
  *(_DWORD *)v34.Data4 = 0;
  v10 = 0;
  v11 = (struct _MDL *)ExAllocatePool3(66, (unsigned int)(v8 + v7), 1919960142, &v34, 1);
LABEL_4:
  v12 = v11;
  if ( !v11 )
    return NetBufferAndNetBufferList;
  v11->Next = 0;
  v11->MdlFlags = 0;
  v11->ByteCount = v7;
  v11->ByteOffset = ((_WORD)v9 + (_WORD)v11) & 0xFFF;
  v11->Size = 8 * (((v7 + (((_WORD)v9 + (_WORD)v11) & 0xFFF) + 4095LL) >> 12) + 6);
  v11->StartVa = (PVOID)(((unsigned __int64)v11 + v9) & 0xFFFFFFFFFFFFF000uLL);
  MmBuildMdlForNonPagedPool(v11);
  NetBufferAndNetBufferList = NdisAllocateNetBufferAndNetBufferList(PoolHandle, 0, 0, v12, 0, v7);
  if ( NetBufferAndNetBufferList )
  {
    v14 = *(struct _MDL **)(v3 + 8);
    if ( (v14->MdlFlags & 5) != 0 )
      MappedSystemVa = (char *)v14->MappedSystemVa;
    else
      MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v14, 0, MmCached, 0, 0, 0x40000000u);
    if ( !MappedSystemVa
      || (v16 = *(unsigned int *)(v3 + 16), ByteCount = v14->ByteCount, (unsigned int)v16 > ByteCount) )
    {
LABEL_40:
      NdisFreeNetBufferList(NetBufferAndNetBufferList);
      v6 = *(_QWORD *)&v35.Data1;
      goto LABEL_6;
    }
    v18 = ByteCount - v16;
    v19 = v7;
    if ( v18 < (unsigned int)v7 )
      v19 = v18;
    v20 = v19;
    memmove((char *)v12 + v31, &MappedSystemVa[v16], v19);
    for ( i = (char *)v12 + v31; ; i = v32 )
    {
      v14 = v14->Next;
      v23 = &i[v20];
      LODWORD(v7) = v7 - v19;
      v32 = v23;
      if ( !v14 )
        break;
      v24 = v14->ByteCount;
      if ( (v14->MdlFlags & 5) != 0 )
      {
        v25 = v14->MappedSystemVa;
      }
      else
      {
        v25 = MmMapLockedPagesSpecifyCache(v14, 0, MmCached, 0, 0, 0x40000000u);
        v23 = v32;
      }
      if ( !v25 )
        goto LABEL_40;
      v19 = v7;
      if ( v24 < (unsigned int)v7 )
        v19 = v24;
      v20 = v19;
      memmove(v23, v25, v19);
    }
    LODWORD(NetBufferAndNetBufferList->ProtocolReserved[0]) = a2;
    NetBufferAndNetBufferList->MiniportReserved[1] = v10;
    NetBufferAndNetBufferList->SourceHandle = *(void **)(a3 + 120);
    if ( (*(_DWORD *)(a3 + 136) & 0x80u) != 0 )
    {
      NetBufferAndNetBufferList->Flags |= 0x80u;
      NetBufferAndNetBufferList->NblFlags |= 0x8000u;
    }
    if ( (*(_DWORD *)(a3 + 136) & 0x200) != 0 )
      NetBufferAndNetBufferList->Flags |= 0x200u;
    NetBufferAndNetBufferList->NetBufferListInfo[0] = *(void **)(a3 + 144);
    NetBufferAndNetBufferList->NetBufferListInfo[1] = *(void **)(a3 + 152);
    NetBufferAndNetBufferList->NetBufferListInfo[2] = *(void **)(a3 + 160);
    NetBufferAndNetBufferList->NetBufferListInfo[3] = *(void **)(a3 + 168);
    NetBufferAndNetBufferList->NetBufferListInfo[4] = *(void **)(a3 + 176);
    NetBufferAndNetBufferList->NetBufferListInfo[6] = *(void **)(a3 + 192);
    NetBufferAndNetBufferList->NetBufferListInfo[7] = *(void **)(a3 + 200);
    NetBufferAndNetBufferList->NetBufferListInfo[11] = *(void **)(a3 + 232);
    NetBufferAndNetBufferList->NetBufferListInfo[12] = *(void **)(a3 + 240);
    if ( byte_140123720 )
    {
      NetBufferAndNetBufferList->NetBufferListInfo[13] = *(void **)(a3 + 248);
    }
    else if ( Microsoft_Windows_Networking_CorrelationEnabled )
    {
      v26 = (__int64)NetBufferAndNetBufferList->NetBufferListInfo[13] & 0x7FFFFFFFFFFFFFFFLL;
      *(_QWORD *)v34.Data4 = 0;
      *(_QWORD *)&v34.Data1 = v26;
      v27 = (struct _GUID)(unsigned __int64)v26;
      v28 = *(_QWORD *)(a3 + 248) & 0x7FFFFFFFFFFFFFFFLL;
      *(_QWORD *)v34.Data4 = 0;
      *(_QWORD *)&v34.Data1 = v28;
      v35 = v27;
      EtwEx_tidActivityInfoTransfer(0x7FFFFFFFFFFFFFFFuLL, v21, &v35, &v34, DataOffset, DataLength, 6u);
    }
    return NetBufferAndNetBufferList;
  }
LABEL_6:
  if ( (v12->MdlFlags & 0x20) != 0 )
    MmUnmapLockedPages(v12->MappedSystemVa, v12);
  if ( v10 )
    ExFreeToNPagedLookasideList(v10, v12);
  else
    ExFreePoolWithTag(v12, 0x7270444Eu);
  return (PNET_BUFFER_LIST)v6;
}

```

## disassembly

```asm
0x1400300b0  push    rbx
0x1400300b2  push    rbp
0x1400300b3  push    rsi
0x1400300b4  push    rdi
0x1400300b5  push    r12
0x1400300b7  push    r13
0x1400300b9  push    r14
0x1400300bb  push    r15
0x1400300bd  sub     rsp, 88h
0x1400300c4  mov     rax, cs:__security_cookie
0x1400300cb  xor     rax, rsp
0x1400300ce  mov     [rsp+0C8h+var_58], rax
0x1400300d3  mov     rdi, [r8+8]
0x1400300d7  xor     ebp, ebp
0x1400300d9  mov     [rsp+0C8h+var_80], edx
0x1400300dd  mov     ecx, 0FFFh; Base
0x1400300e2  mov     rbx, r8
0x1400300e5  mov     qword ptr [rsp+0C8h+var_68.Data1], rbp
0x1400300ea  mov     r13d, ebp
0x1400300ed  mov     r15d, [rdi+18h]
0x1400300f1  mov     edx, r15d; Length
0x1400300f4  call    cs:__imp_MmSizeOfMdl
0x1400300fb  nop     dword ptr [rax+rax+00h]
0x140030100  add     eax, 7
0x140030103  and     eax, 0FFFFFFF8h
0x140030106  mov     esi, eax
0x140030108  mov     [rsp+0C8h+var_88], rsi
0x14003010d  cmp     r15d, 64h ; 'd'
0x140030111  ja      loc_1400301F5
0x140030117  lea     r12, Lookaside
0x14003011e  mov     rcx, r12; Lookaside
0x140030121  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140030128  nop     dword ptr [rax+rax+00h]
0x14003012d  mov     r14, rax
0x140030130  test    rax, rax
0x140030133  jz      loc_140030343
0x140030139  lea     r8, [rsi+rax]
0x14003013d  mov     [rax], rbp
0x140030140  mov     edx, r8d
0x140030143  mov     [rax+0Ah], bp
0x140030147  mov     ecx, edx
0x140030149  mov     [r14+28h], r15d
0x14003014d  and     ecx, 0FFFh
0x140030153  and     edx, 0FFFh
0x140030159  add     rcx, 0FFFh
0x140030160  mov     [r14+2Ch], edx
0x140030164  add     rcx, r15
0x140030167  shr     rcx, 0Ch
0x14003016b  add     cx, 6
0x14003016f  shl     cx, 3
0x140030173  mov     [rax+8], cx
0x140030177  mov     rax, r8
0x14003017a  and     rax, 0FFFFFFFFFFFFF000h
0x140030180  mov     rcx, r14; MemoryDescriptorList
0x140030183  mov     [r14+20h], rax
0x140030187  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14003018e  nop     dword ptr [rax+rax+00h]
0x140030193  mov     rcx, cs:PoolHandle; PoolHandle
0x14003019a  xor     r8d, r8d; ContextBackFill
0x14003019d  xor     edx, edx; ContextSize
0x14003019f  mov     [rsp+0C8h+DataLength], r15; struct _GUID *
0x1400301a4  mov     r9, r14; MdlChain
0x1400301a7  mov     dword ptr [rsp+0C8h+DataOffset], ebp; unsigned __int8
0x1400301ab  call    NdisAllocateNetBufferAndNetBufferList
0x1400301b0  mov     rbp, rax
0x1400301b3  test    rax, rax
0x1400301b6  jnz     short loc_14003020E
0x1400301b8  test    byte ptr [r14+0Ah], 20h
0x1400301bd  jz      short loc_1400301D2
0x1400301bf  mov     rcx, [r14+18h]; BaseAddress
0x1400301c3  mov     rdx, r14; MemoryDescriptorList
0x1400301c6  call    cs:__imp_MmUnmapLockedPages
0x1400301cd  nop     dword ptr [rax+rax+00h]
0x1400301d2  test    r12, r12
0x1400301d5  jz      loc_1400EEB19
0x1400301db  mov     rdx, r14; Entry
0x1400301de  mov     rcx, r12; Lookaside
0x1400301e1  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400301e8  nop     dword ptr [rax+rax+00h]
0x1400301ed  mov     rax, r13
0x1400301f0  jmp     loc_140030346
0x1400301f5  cmp     r15d, 5EEh
0x1400301fc  ja      loc_1400303A4
0x140030202  lea     r12, stru_140121500
0x140030209  jmp     loc_14003011E
0x14003020e  mov     r13, [rdi+8]
0x140030212  test    byte ptr [r13+0Ah], 5
0x140030217  jz      loc_1400303F0
0x14003021d  mov     rax, [r13+18h]
0x140030221  test    rax, rax
0x140030224  jz      loc_14003048E
0x14003022a  mov     edx, [rdi+10h]
0x14003022d  mov     ecx, [r13+28h]
0x140030231  cmp     edx, ecx
0x140030233  ja      loc_14003048E
0x140030239  sub     ecx, edx
0x14003023b  mov     esi, r15d
0x14003023e  cmp     ecx, r15d
0x140030241  cmovb   esi, ecx
0x140030244  mov     rcx, [rsp+0C8h+var_88]
0x140030249  add     rcx, r14; void *
0x14003024c  mov     r8d, esi; Size
0x14003024f  add     rdx, rax; Src
0x140030252  mov     edi, esi
0x140030254  call    memmove
0x140030259  mov     rcx, [rsp+0C8h+var_88]
0x14003025e  add     rcx, r14
0x140030261  mov     r13, [r13+0]
0x140030265  add     rcx, rdi; void *
0x140030268  sub     r15d, esi
0x14003026b  mov     [rsp+0C8h+var_88], rcx
0x140030270  test    r13, r13
0x140030273  jnz     loc_140030368
0x140030279  mov     eax, [rsp+0C8h+var_80]
0x14003027d  mov     [rbp+40h], eax
0x140030280  mov     [rbp+68h], r12
0x140030284  mov     rax, [rbx+78h]
0x140030288  mov     [rbp+78h], rax
0x14003028c  mov     eax, [rbx+88h]
0x140030292  test    al, al
0x140030294  js      loc_140030453
0x14003029a  test    dword ptr [rbx+88h], 200h
0x1400302a4  jnz     loc_14003046C
0x1400302aa  mov     rax, [rbx+90h]
0x1400302b1  mov     [rbp+90h], rax
0x1400302b8  mov     rax, [rbx+98h]
0x1400302bf  mov     [rbp+98h], rax
0x1400302c6  mov     rax, [rbx+0A0h]
0x1400302cd  mov     [rbp+0A0h], rax
0x1400302d4  mov     rax, [rbx+0A8h]
0x1400302db  mov     [rbp+0A8h], rax
0x1400302e2  mov     rax, [rbx+0B0h]
0x1400302e9  mov     [rbp+0B0h], rax
0x1400302f0  mov     rax, [rbx+0C0h]
0x1400302f7  mov     [rbp+0C0h], rax
0x1400302fe  mov     rax, [rbx+0C8h]
0x140030305  mov     [rbp+0C8h], rax
0x14003030c  mov     rax, [rbx+0E8h]
0x140030313  mov     [rbp+0E8h], rax
0x14003031a  mov     rax, [rbx+0F0h]
0x140030321  mov     [rbp+0F0h], rax
0x140030328  cmp     cs:byte_140123720, 0
0x14003032f  jnz     loc_14003047B
0x140030335  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14003033b  test    eax, eax
0x14003033d  jnz     loc_1400EEA9E
0x140030343  mov     rax, rbp
0x140030346  mov     rcx, [rsp+0C8h+var_58]
0x14003034b  xor     rcx, rsp; StackCookie
0x14003034e  call    __security_check_cookie
0x140030353  add     rsp, 88h
0x14003035a  pop     r15
0x14003035c  pop     r14
0x14003035e  pop     r13
0x140030360  pop     r12
0x140030362  pop     rdi
0x140030363  pop     rsi
0x140030364  pop     rbp
0x140030365  pop     rbx
0x140030366  retn
0x140030368  test    byte ptr [r13+0Ah], 5
0x14003036d  mov     edi, [r13+28h]
0x140030371  jz      loc_14003041F
0x140030377  mov     rax, [r13+18h]
0x14003037b  test    rax, rax
0x14003037e  jz      loc_14003048E
0x140030384  cmp     edi, r15d
0x140030387  mov     esi, r15d
0x14003038a  mov     rdx, rax; Src
0x14003038d  cmovb   esi, edi
0x140030390  mov     r8d, esi; Size
0x140030393  mov     edi, esi
0x140030395  call    memmove
0x14003039a  mov     rcx, [rsp+0C8h+var_88]
0x14003039f  jmp     loc_140030261
0x1400303a4  add     rax, r15
0x1400303a7  shr     rax, 20h
0x1400303ab  test    eax, eax
0x1400303ad  jnz     short loc_140030343
0x1400303af  xorps   xmm0, xmm0
0x1400303b2  mov     dword ptr [rsp+0C8h+DataOffset], 1
0x1400303ba  movups  xmmword ptr [rsp+0C8h+var_78.Data1], xmm0
0x1400303bf  lea     edx, [rsi+r15]
0x1400303c3  mov     byte ptr [rsp+0C8h+var_78.Data1], 1
0x1400303c8  lea     r9, [rsp+0C8h+var_78]
0x1400303cd  mov     dword ptr [rsp+0C8h+var_78.Data4], ebp
0x1400303d1  mov     ecx, 42h ; 'B'
0x1400303d6  mov     r8d, 7270444Eh
0x1400303dc  mov     r12, rbp
0x1400303df  call    cs:__imp_ExAllocatePool3
0x1400303e6  nop     dword ptr [rax+rax+00h]
0x1400303eb  jmp     loc_14003012D
0x1400303f0  mov     dword ptr [rsp+0C8h+DataLength], 40000000h; Priority
0x1400303f8  xor     r9d, r9d; RequestedAddress
0x1400303fb  xor     edx, edx; AccessMode
0x1400303fd  mov     dword ptr [rsp+0C8h+DataOffset], 0; BugCheckOnFailure
0x140030405  mov     r8d, 1; CacheType
0x14003040b  mov     rcx, r13; MemoryDescriptorList
0x14003040e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140030415  nop     dword ptr [rax+rax+00h]
0x14003041a  jmp     loc_140030221
0x14003041f  mov     dword ptr [rsp+0C8h+DataLength], 40000000h; Priority
0x140030427  xor     r9d, r9d; RequestedAddress
0x14003042a  xor     edx, edx; AccessMode
0x14003042c  mov     dword ptr [rsp+0C8h+DataOffset], 0; BugCheckOnFailure
0x140030434  mov     r8d, 1; CacheType
0x14003043a  mov     rcx, r13; MemoryDescriptorList
0x14003043d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140030444  nop     dword ptr [rax+rax+00h]
0x140030449  mov     rcx, [rsp+0C8h+var_88]
0x14003044e  jmp     loc_14003037B
0x140030453  or      dword ptr [rbp+88h], 80h
0x14003045d  or      dword ptr [rbp+80h], 8000h
0x140030467  jmp     loc_14003029A
0x14003046c  or      dword ptr [rbp+88h], 200h
0x140030476  jmp     loc_1400302AA
0x14003047b  mov     rax, [rbx+0F8h]
0x140030482  mov     [rbp+0F8h], rax
0x140030489  jmp     loc_140030343
0x14003048e  mov     rcx, rbp; NetBufferList
0x140030491  call    NdisFreeNetBufferList
0x140030496  mov     r13, qword ptr [rsp+0C8h+var_68.Data1]
0x14003049b  jmp     loc_1400301B8
0x1400eea9e  mov     rax, [rbp+0F8h]
0x1400eeaa5  mov     rcx, 7FFFFFFFFFFFFFFFh; unsigned __int64
0x1400eeaaf  and     rax, rcx
0x1400eeab2  mov     qword ptr [rsp+0C8h+var_78.Data4], 0
0x1400eeabb  mov     qword ptr [rsp+0C8h+var_78.Data1], rax
0x1400eeac0  movaps  xmm0, xmmword ptr [rsp+0C8h+var_78.Data1]
0x1400eeac5  mov     rax, [rbx+0F8h]
0x1400eeacc  and     rax, rcx
0x1400eeacf  mov     qword ptr [rsp+0C8h+var_78.Data4], 0
0x1400eead8  mov     qword ptr [rsp+0C8h+var_78.Data1], rax
0x1400eeadd  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400eeae3  movdqa  xmmword ptr [rsp+0C8h+var_68.Data1], xmm0
0x1400eeae9  movaps  xmm0, xmmword ptr [rsp+0C8h+var_78.Data1]
0x1400eeaee  movdqa  xmmword ptr [rsp+0C8h+var_78.Data1], xmm0
0x1400eeaf4  test    eax, eax
0x1400eeaf6  jz      loc_140030343
0x1400eeafc  lea     r9, [rsp+0C8h+var_78]; struct _GUID *
0x1400eeb01  mov     [rsp+0C8h+var_98], 6; unsigned int
0x1400eeb09  lea     r8, [rsp+0C8h+var_68]; struct _GUID *
0x1400eeb0e  call    ?EtwEx_tidActivityInfoTransfer@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2E2K@Z; EtwEx_tidActivityInfoTransfer(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,uchar,_GUID const *,ulong)
0x1400eeb13  nop
0x1400eeb14  jmp     loc_140030343
0x1400eeb19  mov     edx, 7270444Eh; Tag
0x1400eeb1e  mov     rcx, r14; P
0x1400eeb21  call    cs:__imp_ExFreePoolWithTag
0x1400eeb28  nop     dword ptr [rax+rax+00h]
0x1400eeb2d  mov     rax, r13
0x1400eeb30  jmp     loc_140030346
```
