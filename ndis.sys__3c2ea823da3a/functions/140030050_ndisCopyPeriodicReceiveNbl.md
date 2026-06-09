# ndisCopyPeriodicReceiveNbl

- ea: `0x140030050`
- end: `0x140030440`
- name: `ndisCopyPeriodicReceiveNbl`
- size: `1008`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14002fe90`

## callees

- `0x140009e70`
- `0x140030050`
- `0x1400319e0`
- `0x140055e70`
- `0x1400e6160`
- `0x1400e62c0`

## import_xrefs

- `ntoskrnl!MmSizeOfMdl` at `0x140030094`
- `ntoskrnl!MmSizeOfMdl` at `0x140030094`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400303ae`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400303dd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400303ae`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400303dd`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140030127`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140030127`
- `ntoskrnl!MmUnmapLockedPages` at `0x140030166`
- `ntoskrnl!MmUnmapLockedPages` at `0x140030166`
- `ntoskrnl!ExAllocatePool3` at `0x14003037f`
- `ntoskrnl!ExAllocatePool3` at `0x14003037f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140030181`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140030181`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400300c1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400300c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e97a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400e97a3`

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
    v10 = &stru_14011B500;
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
    if ( byte_14011D730 )
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
0x140030050  push    rbx
0x140030052  push    rbp
0x140030053  push    rsi
0x140030054  push    rdi
0x140030055  push    r12
0x140030057  push    r13
0x140030059  push    r14
0x14003005b  push    r15
0x14003005d  sub     rsp, 88h
0x140030064  mov     rax, cs:__security_cookie
0x14003006b  xor     rax, rsp
0x14003006e  mov     [rsp+0C8h+var_58], rax
0x140030073  mov     rdi, [r8+8]
0x140030077  xor     ebp, ebp
0x140030079  mov     [rsp+0C8h+var_80], edx
0x14003007d  mov     ecx, 0FFFh; Base
0x140030082  mov     rbx, r8
0x140030085  mov     qword ptr [rsp+0C8h+var_68.Data1], rbp
0x14003008a  mov     r13d, ebp
0x14003008d  mov     r15d, [rdi+18h]
0x140030091  mov     edx, r15d; Length
0x140030094  call    cs:__imp_MmSizeOfMdl
0x14003009b  nop     dword ptr [rax+rax+00h]
0x1400300a0  add     eax, 7
0x1400300a3  and     eax, 0FFFFFFF8h
0x1400300a6  mov     esi, eax
0x1400300a8  mov     [rsp+0C8h+var_88], rsi
0x1400300ad  cmp     r15d, 64h ; 'd'
0x1400300b1  ja      loc_140030195
0x1400300b7  lea     r12, Lookaside
0x1400300be  mov     rcx, r12; Lookaside
0x1400300c1  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400300c8  nop     dword ptr [rax+rax+00h]
0x1400300cd  mov     r14, rax
0x1400300d0  test    rax, rax
0x1400300d3  jz      loc_1400302E3
0x1400300d9  lea     r8, [rsi+rax]
0x1400300dd  mov     [rax], rbp
0x1400300e0  mov     edx, r8d
0x1400300e3  mov     [rax+0Ah], bp
0x1400300e7  mov     ecx, edx
0x1400300e9  mov     [r14+28h], r15d
0x1400300ed  and     ecx, 0FFFh
0x1400300f3  and     edx, 0FFFh
0x1400300f9  add     rcx, 0FFFh
0x140030100  mov     [r14+2Ch], edx
0x140030104  add     rcx, r15
0x140030107  shr     rcx, 0Ch
0x14003010b  add     cx, 6
0x14003010f  shl     cx, 3
0x140030113  mov     [rax+8], cx
0x140030117  mov     rax, r8
0x14003011a  and     rax, 0FFFFFFFFFFFFF000h
0x140030120  mov     rcx, r14; MemoryDescriptorList
0x140030123  mov     [r14+20h], rax
0x140030127  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14003012e  nop     dword ptr [rax+rax+00h]
0x140030133  mov     rcx, cs:PoolHandle; PoolHandle
0x14003013a  xor     r8d, r8d; ContextBackFill
0x14003013d  xor     edx, edx; ContextSize
0x14003013f  mov     [rsp+0C8h+DataLength], r15; struct _GUID *
0x140030144  mov     r9, r14; MdlChain
0x140030147  mov     dword ptr [rsp+0C8h+DataOffset], ebp; unsigned __int8
0x14003014b  call    NdisAllocateNetBufferAndNetBufferList
0x140030150  mov     rbp, rax
0x140030153  test    rax, rax
0x140030156  jnz     short loc_1400301AE
0x140030158  test    byte ptr [r14+0Ah], 20h
0x14003015d  jz      short loc_140030172
0x14003015f  mov     rcx, [r14+18h]; BaseAddress
0x140030163  mov     rdx, r14; MemoryDescriptorList
0x140030166  call    cs:__imp_MmUnmapLockedPages
0x14003016d  nop     dword ptr [rax+rax+00h]
0x140030172  test    r12, r12
0x140030175  jz      loc_1400E979B
0x14003017b  mov     rdx, r14; Entry
0x14003017e  mov     rcx, r12; Lookaside
0x140030181  call    cs:__imp_ExFreeToNPagedLookasideList
0x140030188  nop     dword ptr [rax+rax+00h]
0x14003018d  mov     rax, r13
0x140030190  jmp     loc_1400302E6
0x140030195  cmp     r15d, 5EEh
0x14003019c  ja      loc_140030344
0x1400301a2  lea     r12, stru_14011B500
0x1400301a9  jmp     loc_1400300BE
0x1400301ae  mov     r13, [rdi+8]
0x1400301b2  test    byte ptr [r13+0Ah], 5
0x1400301b7  jz      loc_140030390
0x1400301bd  mov     rax, [r13+18h]
0x1400301c1  test    rax, rax
0x1400301c4  jz      loc_14003042E
0x1400301ca  mov     edx, [rdi+10h]
0x1400301cd  mov     ecx, [r13+28h]
0x1400301d1  cmp     edx, ecx
0x1400301d3  ja      loc_14003042E
0x1400301d9  sub     ecx, edx
0x1400301db  mov     esi, r15d
0x1400301de  cmp     ecx, r15d
0x1400301e1  cmovb   esi, ecx
0x1400301e4  mov     rcx, [rsp+0C8h+var_88]
0x1400301e9  add     rcx, r14; void *
0x1400301ec  mov     r8d, esi; Size
0x1400301ef  add     rdx, rax; Src
0x1400301f2  mov     edi, esi
0x1400301f4  call    memmove
0x1400301f9  mov     rcx, [rsp+0C8h+var_88]
0x1400301fe  add     rcx, r14
0x140030201  mov     r13, [r13+0]
0x140030205  add     rcx, rdi; void *
0x140030208  sub     r15d, esi
0x14003020b  mov     [rsp+0C8h+var_88], rcx
0x140030210  test    r13, r13
0x140030213  jnz     loc_140030308
0x140030219  mov     eax, [rsp+0C8h+var_80]
0x14003021d  mov     [rbp+40h], eax
0x140030220  mov     [rbp+68h], r12
0x140030224  mov     rax, [rbx+78h]
0x140030228  mov     [rbp+78h], rax
0x14003022c  mov     eax, [rbx+88h]
0x140030232  test    al, al
0x140030234  js      loc_1400303F3
0x14003023a  test    dword ptr [rbx+88h], 200h
0x140030244  jnz     loc_14003040C
0x14003024a  mov     rax, [rbx+90h]
0x140030251  mov     [rbp+90h], rax
0x140030258  mov     rax, [rbx+98h]
0x14003025f  mov     [rbp+98h], rax
0x140030266  mov     rax, [rbx+0A0h]
0x14003026d  mov     [rbp+0A0h], rax
0x140030274  mov     rax, [rbx+0A8h]
0x14003027b  mov     [rbp+0A8h], rax
0x140030282  mov     rax, [rbx+0B0h]
0x140030289  mov     [rbp+0B0h], rax
0x140030290  mov     rax, [rbx+0C0h]
0x140030297  mov     [rbp+0C0h], rax
0x14003029e  mov     rax, [rbx+0C8h]
0x1400302a5  mov     [rbp+0C8h], rax
0x1400302ac  mov     rax, [rbx+0E8h]
0x1400302b3  mov     [rbp+0E8h], rax
0x1400302ba  mov     rax, [rbx+0F0h]
0x1400302c1  mov     [rbp+0F0h], rax
0x1400302c8  cmp     cs:byte_14011D730, 0
0x1400302cf  jnz     loc_14003041B
0x1400302d5  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400302db  test    eax, eax
0x1400302dd  jnz     loc_1400E9720
0x1400302e3  mov     rax, rbp
0x1400302e6  mov     rcx, [rsp+0C8h+var_58]
0x1400302eb  xor     rcx, rsp; StackCookie
0x1400302ee  call    __security_check_cookie
0x1400302f3  add     rsp, 88h
0x1400302fa  pop     r15
0x1400302fc  pop     r14
0x1400302fe  pop     r13
0x140030300  pop     r12
0x140030302  pop     rdi
0x140030303  pop     rsi
0x140030304  pop     rbp
0x140030305  pop     rbx
0x140030306  retn
0x140030308  test    byte ptr [r13+0Ah], 5
0x14003030d  mov     edi, [r13+28h]
0x140030311  jz      loc_1400303BF
0x140030317  mov     rax, [r13+18h]
0x14003031b  test    rax, rax
0x14003031e  jz      loc_14003042E
0x140030324  cmp     edi, r15d
0x140030327  mov     esi, r15d
0x14003032a  mov     rdx, rax; Src
0x14003032d  cmovb   esi, edi
0x140030330  mov     r8d, esi; Size
0x140030333  mov     edi, esi
0x140030335  call    memmove
0x14003033a  mov     rcx, [rsp+0C8h+var_88]
0x14003033f  jmp     loc_140030201
0x140030344  add     rax, r15
0x140030347  shr     rax, 20h
0x14003034b  test    eax, eax
0x14003034d  jnz     short loc_1400302E3
0x14003034f  xorps   xmm0, xmm0
0x140030352  mov     dword ptr [rsp+0C8h+DataOffset], 1
0x14003035a  movups  xmmword ptr [rsp+0C8h+var_78.Data1], xmm0
0x14003035f  lea     edx, [rsi+r15]
0x140030363  mov     byte ptr [rsp+0C8h+var_78.Data1], 1
0x140030368  lea     r9, [rsp+0C8h+var_78]
0x14003036d  mov     dword ptr [rsp+0C8h+var_78.Data4], ebp
0x140030371  mov     ecx, 42h ; 'B'
0x140030376  mov     r8d, 7270444Eh
0x14003037c  mov     r12, rbp
0x14003037f  call    cs:__imp_ExAllocatePool3
0x140030386  nop     dword ptr [rax+rax+00h]
0x14003038b  jmp     loc_1400300CD
0x140030390  mov     dword ptr [rsp+0C8h+DataLength], 40000000h; Priority
0x140030398  xor     r9d, r9d; RequestedAddress
0x14003039b  xor     edx, edx; AccessMode
0x14003039d  mov     dword ptr [rsp+0C8h+DataOffset], 0; BugCheckOnFailure
0x1400303a5  mov     r8d, 1; CacheType
0x1400303ab  mov     rcx, r13; MemoryDescriptorList
0x1400303ae  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400303b5  nop     dword ptr [rax+rax+00h]
0x1400303ba  jmp     loc_1400301C1
0x1400303bf  mov     dword ptr [rsp+0C8h+DataLength], 40000000h; Priority
0x1400303c7  xor     r9d, r9d; RequestedAddress
0x1400303ca  xor     edx, edx; AccessMode
0x1400303cc  mov     dword ptr [rsp+0C8h+DataOffset], 0; BugCheckOnFailure
0x1400303d4  mov     r8d, 1; CacheType
0x1400303da  mov     rcx, r13; MemoryDescriptorList
0x1400303dd  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400303e4  nop     dword ptr [rax+rax+00h]
0x1400303e9  mov     rcx, [rsp+0C8h+var_88]
0x1400303ee  jmp     loc_14003031B
0x1400303f3  or      dword ptr [rbp+88h], 80h
0x1400303fd  or      dword ptr [rbp+80h], 8000h
0x140030407  jmp     loc_14003023A
0x14003040c  or      dword ptr [rbp+88h], 200h
0x140030416  jmp     loc_14003024A
0x14003041b  mov     rax, [rbx+0F8h]
0x140030422  mov     [rbp+0F8h], rax
0x140030429  jmp     loc_1400302E3
0x14003042e  mov     rcx, rbp; NetBufferList
0x140030431  call    NdisFreeNetBufferList
0x140030436  mov     r13, qword ptr [rsp+0C8h+var_68.Data1]
0x14003043b  jmp     loc_140030158
0x1400e9720  mov     rax, [rbp+0F8h]
0x1400e9727  mov     rcx, 7FFFFFFFFFFFFFFFh; unsigned __int64
0x1400e9731  and     rax, rcx
0x1400e9734  mov     qword ptr [rsp+0C8h+var_78.Data4], 0
0x1400e973d  mov     qword ptr [rsp+0C8h+var_78.Data1], rax
0x1400e9742  movaps  xmm0, xmmword ptr [rsp+0C8h+var_78.Data1]
0x1400e9747  mov     rax, [rbx+0F8h]
0x1400e974e  and     rax, rcx
0x1400e9751  mov     qword ptr [rsp+0C8h+var_78.Data4], 0
0x1400e975a  mov     qword ptr [rsp+0C8h+var_78.Data1], rax
0x1400e975f  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400e9765  movdqa  xmmword ptr [rsp+0C8h+var_68.Data1], xmm0
0x1400e976b  movaps  xmm0, xmmword ptr [rsp+0C8h+var_78.Data1]
0x1400e9770  movdqa  xmmword ptr [rsp+0C8h+var_78.Data1], xmm0
0x1400e9776  test    eax, eax
0x1400e9778  jz      loc_1400302E3
0x1400e977e  lea     r9, [rsp+0C8h+var_78]; struct _GUID *
0x1400e9783  mov     [rsp+0C8h+var_98], 6; unsigned int
0x1400e978b  lea     r8, [rsp+0C8h+var_68]; struct _GUID *
0x1400e9790  call    ?EtwEx_tidActivityInfoTransfer@@YAK_KPEBU_EVENT_DESCRIPTOR@@PEBU_GUID@@2E2K@Z; EtwEx_tidActivityInfoTransfer(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID const *,_GUID const *,uchar,_GUID const *,ulong)
0x1400e9795  nop
0x1400e9796  jmp     loc_1400302E3
0x1400e979b  mov     edx, 7270444Eh; Tag
0x1400e97a0  mov     rcx, r14; P
0x1400e97a3  call    cs:__imp_ExFreePoolWithTag
0x1400e97aa  nop     dword ptr [rax+rax+00h]
0x1400e97af  mov     rax, r13
0x1400e97b2  jmp     loc_1400302E6
```
