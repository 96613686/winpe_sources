# VIDMM_RECYCLE_BLOCK::Allocate(unsigned __int64,VIDMM_HEAP_ALLOCATE_FLAGS,ulong)

- ea: `0x1400f7f20`
- end: `0x1400f832d`
- name: `?Allocate@VIDMM_RECYCLE_BLOCK@@QEAAJ_KW4VIDMM_HEAP_ALLOCATE_FLAGS@@K@Z`
- size: `1037`
- prototype: `__int64 __fastcall(__int64, ULONG_PTR, char, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400f7d28`

## callees

- `0x1400045ec`
- `0x14003bbcc`
- `0x1400c18bc`
- `0x1400f70b4`
- `0x1400f7684`
- `0x1400f7f20`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400f80f7`
- `ntoskrnl!ObfReferenceObject` at `0x1400f80f7`
- `ntoskrnl!MmCreateSection` at `0x1400f80b2`
- `ntoskrnl!MmCreateSection` at `0x1400f80b2`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1400f81aa`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1400f81aa`
- `ntoskrnl!ObInsertObject` at `0x1400f811c`
- `ntoskrnl!ObInsertObject` at `0x1400f811c`
- `watchdog!WdLogSingleEntry2` at `0x1400f813a`
- `watchdog!WdLogSingleEntry2` at `0x1400f813a`
- `watchdog!WdLogSingleEntry1` at `0x1400f8003`
- `watchdog!WdLogSingleEntry1` at `0x1400f80d2`
- `watchdog!WdLogSingleEntry1` at `0x1400f81cc`
- `watchdog!WdLogSingleEntry1` at `0x1400f826a`
- `watchdog!WdLogSingleEntry1` at `0x1400f8003`
- `watchdog!WdLogSingleEntry1` at `0x1400f80d2`
- `watchdog!WdLogSingleEntry1` at `0x1400f81cc`
- `watchdog!WdLogSingleEntry1` at `0x1400f826a`

## pseudocode

```c
__int64 __fastcall VIDMM_RECYCLE_BLOCK::Allocate(__int64 a1, ULONG_PTR a2, char a3, unsigned int a4)
{
  int *v4; // r10
  int v9; // ecx
  char v10; // dl
  int v11; // r9d
  char v12; // al
  int v13; // r11d
  unsigned int v14; // esi
  unsigned int v15; // r8d
  int v16; // eax
  __int64 v17; // rsi
  int v18; // ecx
  int v19; // r8d
  char v20; // r10
  int v21; // ecx
  int v22; // esi
  PVOID *v23; // r14
  void *CurrentPartitionHandle; // rax
  int v25; // eax
  const wchar_t *v26; // r9
  NTSTATUS inserted; // eax
  int v28; // r8d
  NTSTATUS v29; // eax
  ULONG_PTR v30; // rax
  unsigned int v31; // esi
  int v32; // eax
  __int64 v34; // rdx
  __int64 v35; // r9
  ULONG_PTR v36; // [rsp+80h] [rbp+8h] BYREF
  ULONG_PTR ViewSize; // [rsp+88h] [rbp+10h] BYREF

  ViewSize = a2;
  v4 = *(int **)(a1 + 32);
  v9 = *v4;
  if ( (unsigned int)(*v4 - 9) <= 1 )
  {
    *(_DWORD *)(a1 + 144) = 0x800000;
    v31 = 1028;
    if ( *v4 == 10 )
      v31 = 4;
    v32 = VIDMM_PROCESS::MapHostVirtualAddressToGuest(
            *(VIDMM_PROCESS **)(*((_QWORD *)v4 + 1) + 8LL),
            0,
            a2,
            0x800000u,
            v31,
            (void **)(a1 + 128),
            (unsigned __int64 *)(a1 + 136),
            (void **)(a1 + 40));
    v17 = v32;
    if ( v32 < 0 )
    {
      _InterlockedIncrement(&dword_140086708);
      WdLogSingleEntry1(6, v32);
      WdLogGlobalForLineNumber = 6710;
      goto LABEL_33;
    }
    v20 = ViewSize;
    v30 = ViewSize + *(_QWORD *)(a1 + 40);
    *(_BYTE *)(a1 + 148) |= 1u;
    goto LABEL_37;
  }
  v10 = *((_BYTE *)v4 + 16);
  v11 = a3 & 2;
  if ( (unsigned int)(v9 - 3) <= 3 )
  {
    v36 = a2;
    v22 = a4 | (((v9 - 4) & 0xFFFFFFFD) != 0 ? 1208221696 : 134479872);
    if ( v10 && (a3 & 2) == 0 )
      v22 |= 0x80000u;
    v23 = (PVOID *)(a1 + 56);
    CurrentPartitionHandle = VIDMM_PROCESS::GetCurrentPartitionHandle();
    v25 = MmCreateSection(a1 + 56, 0, 0, &v36, 4, v22, CurrentPartitionHandle, 0);
    v17 = v25;
    if ( v25 < 0 )
    {
      _InterlockedIncrement(&dword_1400867D0);
      WdLogSingleEntry1(6, v25);
      v26 = L"Couldn't allocate a backing section for an allocation, Status = 0x%I64p";
      WdLogGlobalForLineNumber = 6816;
LABEL_34:
      DxgkLogInternalTriageEvent(v18, 262145, v19, (_DWORD)v26, v17, 0, 0, 0);
      return (unsigned int)v17;
    }
    ObfReferenceObject(*v23);
    inserted = ObInsertObject(*v23, 0, 0, 0, 0, (PHANDLE)(a1 + 64));
    v17 = inserted;
    if ( inserted < 0 )
    {
      WdLogSingleEntry2(1, *v23, inserted);
      WdLogGlobalForLineNumber = 6837;
      DxgkLogInternalTriageEvent(
        (unsigned int)*v23,
        0x40000,
        v28,
        (unsigned int)L"Unable to insert section object 0x%I64p into handle table, Status = 0x%I64p",
        (__int64)*v23,
        v17,
        0,
        0);
      return (unsigned int)v17;
    }
    if ( (unsigned int)(**(_DWORD **)(a1 + 32) - 5) > 1 )
    {
      v20 = ViewSize;
      *(_QWORD *)(a1 + 48) = ViewSize;
      *(_QWORD *)(a1 + 40) = 0;
      goto LABEL_38;
    }
    v29 = MmMapViewInSystemSpace(*v23, (PVOID *)(a1 + 40), &ViewSize);
    v17 = v29;
    if ( v29 < 0 )
    {
      _InterlockedIncrement(&dword_1400867D0);
      WdLogSingleEntry1(6, v29);
      v26 = L"Couldn't map view of section to kernel space. Status = 0x%I64x";
      WdLogGlobalForLineNumber = 6851;
      goto LABEL_34;
    }
    v20 = ViewSize;
    v30 = ViewSize + *(_QWORD *)(a1 + 40);
LABEL_37:
    *(_QWORD *)(a1 + 48) = v30;
    goto LABEL_38;
  }
  v12 = *((_BYTE *)v4 + 17);
  v13 = a3 & 4;
  if ( v9 == 2 || (v14 = 1028, v9 == 8) )
    v14 = 4;
  v15 = 0x2000;
  *(_DWORD *)(a1 + 144) = 0x2000;
  if ( v12 )
  {
    v15 = 2105344;
    *(_DWORD *)(a1 + 144) = 2105344;
  }
  if ( v10 && !v11 )
  {
    v15 |= 0x20400000u;
    *(_DWORD *)(a1 + 144) = v15;
  }
  if ( v13 && !v10 )
  {
    v15 |= 0x800000u;
    *(_DWORD *)(a1 + 144) = v15;
  }
  v16 = VidMmAllocateVirtualMemory((void **)(a1 + 40), &ViewSize, v15, v14, a4);
  v17 = v16;
  if ( v16 < 0 )
  {
    _InterlockedIncrement(&dword_140086708);
    WdLogSingleEntry1(6, v16);
    WdLogGlobalForLineNumber = 6761;
LABEL_33:
    v26 = L"Couldn't allocate virtual memory range for the block. Status 0x%08X.\n";
    goto LABEL_34;
  }
  v20 = ViewSize;
  v21 = *(_DWORD *)(a1 + 144);
  *(_QWORD *)(a1 + 48) = ViewSize + *(_QWORD *)(a1 + 40);
  *(_BYTE *)(a1 + 148) = *(_BYTE *)(a1 + 148) & 0xFE | ((v21 & 0x800000) != 0);
LABEL_38:
  if ( (byte_140086202 & 4) != 0 )
  {
    v34 = *(_QWORD *)(a1 + 32);
    v35 = 56;
    if ( (unsigned int)(*(_DWORD *)v34 - 3) > 3 )
      v35 = 40;
    McTemplateK0pxqqt_EtwWriteTransfer(
      *(_DWORD *)v34,
      (unsigned int)EventCreateProcessAllocation,
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v34 + 8) + 8LL) + 24LL),
      *(_QWORD *)(v35 + a1),
      v20,
      *(_DWORD *)v34,
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v34 + 8) + 8LL) + 24LL),
      1);
  }
  return 0;
}

```

## disassembly

```asm
0x1400f7f20  mov     [rsp+arg_10], rbx
0x1400f7f25  mov     [rsp+ViewSize], rdx
0x1400f7f2a  push    rbp
0x1400f7f2b  push    rsi
0x1400f7f2c  push    rdi
0x1400f7f2d  push    r14
0x1400f7f2f  push    r15
0x1400f7f31  sub     rsp, 50h
0x1400f7f35  mov     r10, [rcx+20h]
0x1400f7f39  mov     rbx, rcx
0x1400f7f3c  mov     r11d, r8d
0x1400f7f3f  mov     r15d, r9d
0x1400f7f42  mov     r8, rdx; unsigned __int64
0x1400f7f45  mov     ecx, [r10]
0x1400f7f48  lea     eax, [rcx-9]
0x1400f7f4b  cmp     eax, 1
0x1400f7f4e  jbe     loc_1400F8202
0x1400f7f54  mov     dl, [r10+10h]
0x1400f7f58  lea     eax, [rcx-3]
0x1400f7f5b  mov     r9d, r11d
0x1400f7f5e  and     r9d, 2
0x1400f7f62  cmp     eax, 3
0x1400f7f65  jbe     loc_1400F8052
0x1400f7f6b  mov     al, [r10+11h]
0x1400f7f6f  mov     ebp, 4
0x1400f7f74  and     r11d, ebp
0x1400f7f77  cmp     ecx, 2
0x1400f7f7a  jz      short loc_1400F7F86
0x1400f7f7c  mov     esi, 404h
0x1400f7f81  cmp     ecx, 8
0x1400f7f84  jnz     short loc_1400F7F88
0x1400f7f86  mov     esi, ebp
0x1400f7f88  xor     edi, edi
0x1400f7f8a  mov     r8d, 2000h
0x1400f7f90  mov     [rbx+90h], r8d
0x1400f7f97  test    al, al
0x1400f7f99  jz      short loc_1400F7FA8
0x1400f7f9b  mov     r8d, 202000h
0x1400f7fa1  mov     [rbx+90h], r8d
0x1400f7fa8  test    dl, dl
0x1400f7faa  jz      short loc_1400F7FBF
0x1400f7fac  test    r9d, r9d
0x1400f7faf  jnz     short loc_1400F7FBF
0x1400f7fb1  or      r8d, 20400000h
0x1400f7fb8  mov     [rbx+90h], r8d
0x1400f7fbf  test    r11d, r11d
0x1400f7fc2  jz      short loc_1400F7FD4
0x1400f7fc4  test    dl, dl
0x1400f7fc6  jnz     short loc_1400F7FD4
0x1400f7fc8  bts     r8d, 17h; unsigned int
0x1400f7fcd  mov     [rbx+90h], r8d
0x1400f7fd4  mov     r9d, esi; unsigned int
0x1400f7fd7  mov     dword ptr [rsp+78h+NewObject], r15d; unsigned int
0x1400f7fdc  lea     rdx, [rsp+78h+ViewSize]; unsigned __int64 *
0x1400f7fe4  lea     rcx, [rbx+28h]; void **
0x1400f7fe8  call    ?VidMmAllocateVirtualMemory@@YAJPEAPEAXPEA_KKKK@Z; VidMmAllocateVirtualMemory(void * *,unsigned __int64 *,ulong,ulong,ulong)
0x1400f7fed  movsxd  rsi, eax
0x1400f7ff0  test    eax, eax
0x1400f7ff2  jns     short loc_1400F801E
0x1400f7ff4  lock inc cs:dword_140086708
0x1400f7ffb  mov     rdx, rsi
0x1400f7ffe  mov     ecx, 6
0x1400f8003  call    cs:__imp_WdLogSingleEntry1
0x1400f800a  nop     dword ptr [rax+rax+00h]
0x1400f800f  mov     cs:WdLogGlobalForLineNumber, 1A69h
0x1400f8019  jmp     loc_1400F8280
0x1400f801e  mov     rax, [rbx+28h]
0x1400f8022  mov     r10, [rsp+78h+ViewSize]
0x1400f802a  mov     ecx, [rbx+90h]
0x1400f8030  add     rax, r10
0x1400f8033  mov     [rbx+30h], rax
0x1400f8037  mov     al, [rbx+94h]
0x1400f803d  shr     ecx, 17h
0x1400f8040  and     al, 0FEh
0x1400f8042  and     cl, 1
0x1400f8045  or      cl, al
0x1400f8047  mov     [rbx+94h], cl
0x1400f804d  jmp     loc_1400F82C2
0x1400f8052  lea     eax, [rcx-4]
0x1400f8055  mov     [rsp+78h+arg_0], r8
0x1400f805d  and     eax, 0FFFFFFFDh
0x1400f8060  neg     eax
0x1400f8062  sbb     esi, esi
0x1400f8064  xor     edi, edi
0x1400f8066  and     esi, 40000000h
0x1400f806c  add     esi, 8040000h
0x1400f8072  or      esi, r15d
0x1400f8075  test    dl, dl
0x1400f8077  jz      short loc_1400F8082
0x1400f8079  test    r9d, r9d
0x1400f807c  jnz     short loc_1400F8082
0x1400f807e  bts     esi, 13h
0x1400f8082  lea     r14, [rbx+38h]
0x1400f8086  call    ?GetCurrentPartitionHandle@VIDMM_PROCESS@@SAPEAXXZ; VIDMM_PROCESS::GetCurrentPartitionHandle(void)
0x1400f808b  mov     [rsp+78h+var_40], rdi
0x1400f8090  lea     r9, [rsp+78h+arg_0]
0x1400f8098  mov     [rsp+78h+var_48], rax
0x1400f809d  mov     ebp, 4
0x1400f80a2  mov     dword ptr [rsp+78h+Handle], esi
0x1400f80a6  xor     r8d, r8d
0x1400f80a9  xor     edx, edx
0x1400f80ab  mov     dword ptr [rsp+78h+NewObject], ebp
0x1400f80af  mov     rcx, r14
0x1400f80b2  call    cs:__imp_MmCreateSection
0x1400f80b9  nop     dword ptr [rax+rax+00h]
0x1400f80be  movsxd  rsi, eax
0x1400f80c1  test    eax, eax
0x1400f80c3  jns     short loc_1400F80F4
0x1400f80c5  lock inc cs:dword_1400867D0
0x1400f80cc  mov     rdx, rsi
0x1400f80cf  lea     ecx, [rbp+2]
0x1400f80d2  call    cs:__imp_WdLogSingleEntry1
0x1400f80d9  nop     dword ptr [rax+rax+00h]
0x1400f80de  lea     r9, aCouldnTAllocat_14; "Couldn't allocate a backing section for"...
0x1400f80e5  mov     cs:WdLogGlobalForLineNumber, 1AA0h
0x1400f80ef  jmp     loc_1400F8287
0x1400f80f4  mov     rcx, [r14]; Object
0x1400f80f7  call    cs:__imp_ObfReferenceObject
0x1400f80fe  nop     dword ptr [rax+rax+00h]
0x1400f8103  mov     rcx, [r14]; Object
0x1400f8106  lea     rax, [rbx+40h]
0x1400f810a  mov     [rsp+78h+Handle], rax; Handle
0x1400f810f  xor     r9d, r9d; ObjectPointerBias
0x1400f8112  xor     r8d, r8d; DesiredAccess
0x1400f8115  mov     [rsp+78h+NewObject], rdi; NewObject
0x1400f811a  xor     edx, edx; PassedAccessState
0x1400f811c  call    cs:__imp_ObInsertObject
0x1400f8123  nop     dword ptr [rax+rax+00h]
0x1400f8128  movsxd  rsi, eax
0x1400f812b  test    eax, eax
0x1400f812d  jns     short loc_1400F8178
0x1400f812f  mov     rdx, [r14]
0x1400f8132  mov     r8, rsi
0x1400f8135  mov     ecx, 1
0x1400f813a  call    cs:__imp_WdLogSingleEntry2
0x1400f8141  nop     dword ptr [rax+rax+00h]
0x1400f8146  mov     [rsp+78h+var_40], rdi
0x1400f814b  lea     r9, aUnableToInsert; "Unable to insert section object 0x%I64p"...
0x1400f8152  mov     [rsp+78h+var_48], rdi
0x1400f8157  mov     edx, 40000h
0x1400f815c  mov     cs:WdLogGlobalForLineNumber, 1AB5h
0x1400f8166  mov     rcx, [r14]
0x1400f8169  mov     [rsp+78h+Handle], rsi
0x1400f816e  mov     [rsp+78h+NewObject], rcx
0x1400f8173  jmp     loc_1400F82A0
0x1400f8178  mov     rax, [rbx+20h]
0x1400f817c  mov     ecx, [rax]
0x1400f817e  sub     ecx, 5
0x1400f8181  cmp     ecx, 1
0x1400f8184  jbe     short loc_1400F819B
0x1400f8186  mov     r10, [rsp+78h+ViewSize]
0x1400f818e  mov     [rbx+30h], r10
0x1400f8192  mov     [rbx+28h], rdi
0x1400f8196  jmp     loc_1400F82C2
0x1400f819b  mov     rcx, [r14]; Section
0x1400f819e  lea     r8, [rsp+78h+ViewSize]; ViewSize
0x1400f81a6  lea     rdx, [rbx+28h]; MappedBase
0x1400f81aa  call    cs:__imp_MmMapViewInSystemSpace
0x1400f81b1  nop     dword ptr [rax+rax+00h]
0x1400f81b6  movsxd  rsi, eax
0x1400f81b9  test    eax, eax
0x1400f81bb  jns     short loc_1400F81EE
0x1400f81bd  lock inc cs:dword_1400867D0
0x1400f81c4  mov     rdx, rsi
0x1400f81c7  mov     ecx, 6
0x1400f81cc  call    cs:__imp_WdLogSingleEntry1
0x1400f81d3  nop     dword ptr [rax+rax+00h]
0x1400f81d8  lea     r9, aCouldnTMapView; "Couldn't map view of section to kernel "...
0x1400f81df  mov     cs:WdLogGlobalForLineNumber, 1AC3h
0x1400f81e9  jmp     loc_1400F8287
0x1400f81ee  mov     rax, [rbx+28h]
0x1400f81f2  mov     r10, [rsp+78h+ViewSize]
0x1400f81fa  add     rax, r10
0x1400f81fd  jmp     loc_1400F82BE
0x1400f8202  mov     r9d, 800000h; unsigned int
0x1400f8208  lea     rax, [rbx+88h]
0x1400f820f  mov     [rbx+90h], r9d
0x1400f8216  lea     rdx, [rbx+80h]
0x1400f821d  mov     rcx, [r10+8]
0x1400f8221  lea     r14, [rbx+28h]
0x1400f8225  cmp     dword ptr [r10], 0Ah
0x1400f8229  mov     esi, 404h
0x1400f822e  mov     [rsp+78h+var_40], r14; void **
0x1400f8233  mov     ebp, 4
0x1400f8238  mov     [rsp+78h+var_48], rax; unsigned __int64 *
0x1400f823d  cmovz   esi, ebp
0x1400f8240  mov     rcx, [rcx+8]; this
0x1400f8244  mov     [rsp+78h+Handle], rdx; void **
0x1400f8249  xor     edx, edx; void *
0x1400f824b  mov     dword ptr [rsp+78h+NewObject], esi; unsigned int
0x1400f824f  call    ?MapHostVirtualAddressToGuest@VIDMM_PROCESS@@QEAAJPEAX_KKKPEAPEAXPEA_K2@Z; VIDMM_PROCESS::MapHostVirtualAddressToGuest(void *,unsigned __int64,ulong,ulong,void * *,unsigned __int64 *,void * *)
0x1400f8254  xor     edi, edi
0x1400f8256  movsxd  rsi, eax
0x1400f8259  test    eax, eax
0x1400f825b  jns     short loc_1400F82A9
0x1400f825d  lock inc cs:dword_140086708
0x1400f8264  mov     rdx, rsi
0x1400f8267  lea     ecx, [rbp+2]
0x1400f826a  call    cs:__imp_WdLogSingleEntry1
0x1400f8271  nop     dword ptr [rax+rax+00h]
0x1400f8276  mov     cs:WdLogGlobalForLineNumber, 1A36h
0x1400f8280  lea     r9, aCouldnTAllocat_40; "Couldn't allocate virtual memory range "...
0x1400f8287  mov     [rsp+78h+var_40], rdi
0x1400f828c  mov     edx, 40001h
0x1400f8291  mov     [rsp+78h+var_48], rdi
0x1400f8296  mov     [rsp+78h+Handle], rdi
0x1400f829b  mov     [rsp+78h+NewObject], rsi
0x1400f82a0  call    DxgkLogInternalTriageEvent
0x1400f82a5  mov     eax, esi
0x1400f82a7  jmp     short loc_1400F8318
0x1400f82a9  mov     rax, [r14]
0x1400f82ac  mov     r10, [rsp+78h+ViewSize]
0x1400f82b4  add     rax, r10
0x1400f82b7  or      byte ptr [rbx+94h], 1
0x1400f82be  mov     [rbx+30h], rax
0x1400f82c2  test    cs:byte_140086202, bpl
0x1400f82c9  jz      short loc_1400F8316
0x1400f82cb  mov     rdx, [rbx+20h]
0x1400f82cf  mov     dword ptr [rsp+78h+var_40], 1
0x1400f82d7  mov     rax, [rdx+8]
0x1400f82db  mov     rcx, [rax+8]
0x1400f82df  mov     r8d, [rcx+18h]
0x1400f82e3  mov     ecx, [rdx]
0x1400f82e5  mov     edx, 28h ; '('
0x1400f82ea  mov     dword ptr [rsp+78h+var_48], r8d
0x1400f82ef  mov     dword ptr [rsp+78h+Handle], ecx
0x1400f82f3  mov     [rsp+78h+NewObject], r10
0x1400f82f8  lea     r9d, [rdx+10h]
0x1400f82fc  lea     eax, [rcx-3]
0x1400f82ff  cmp     eax, 3
0x1400f8302  cmova   r9d, edx
0x1400f8306  lea     rdx, EventCreateProcessAllocation
0x1400f830d  mov     r9, [r9+rbx]
0x1400f8311  call    McTemplateK0pxqqt_EtwWriteTransfer
0x1400f8316  xor     eax, eax
0x1400f8318  mov     rbx, [rsp+78h+arg_10]
0x1400f8320  add     rsp, 50h
0x1400f8324  pop     r15
0x1400f8326  pop     r14
0x1400f8328  pop     rdi
0x1400f8329  pop     rsi
0x1400f832a  pop     rbp
0x1400f832b  retn
```
