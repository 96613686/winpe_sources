# VIDMM_RECYCLE_BLOCK::Allocate(unsigned __int64,VIDMM_HEAP_ALLOCATE_FLAGS,ulong)

- ea: `0x1400fcf10`
- end: `0x1400fd31d`
- name: `?Allocate@VIDMM_RECYCLE_BLOCK@@QEAAJ_KW4VIDMM_HEAP_ALLOCATE_FLAGS@@K@Z`
- size: `1037`
- prototype: `__int64 __fastcall(__int64, ULONG_PTR, char, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400fcd18`

## callees

- `0x140004268`
- `0x14003a8dc`
- `0x1400c5a68`
- `0x1400fc094`
- `0x1400fc664`
- `0x1400fcf10`

## import_xrefs

- `ntoskrnl!ObfReferenceObject` at `0x1400fd0e7`
- `ntoskrnl!ObfReferenceObject` at `0x1400fd0e7`
- `ntoskrnl!MmCreateSection` at `0x1400fd0a2`
- `ntoskrnl!MmCreateSection` at `0x1400fd0a2`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1400fd19a`
- `ntoskrnl!MmMapViewInSystemSpace` at `0x1400fd19a`
- `ntoskrnl!ObInsertObject` at `0x1400fd10c`
- `ntoskrnl!ObInsertObject` at `0x1400fd10c`
- `watchdog!WdLogSingleEntry2` at `0x1400fd12a`
- `watchdog!WdLogSingleEntry2` at `0x1400fd12a`
- `watchdog!WdLogSingleEntry1` at `0x1400fcff3`
- `watchdog!WdLogSingleEntry1` at `0x1400fd0c2`
- `watchdog!WdLogSingleEntry1` at `0x1400fd1bc`
- `watchdog!WdLogSingleEntry1` at `0x1400fd25a`
- `watchdog!WdLogSingleEntry1` at `0x1400fcff3`
- `watchdog!WdLogSingleEntry1` at `0x1400fd0c2`
- `watchdog!WdLogSingleEntry1` at `0x1400fd1bc`
- `watchdog!WdLogSingleEntry1` at `0x1400fd25a`

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
      _InterlockedIncrement(&dword_1400876E8);
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
      _InterlockedIncrement(&dword_1400877B0);
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
      _InterlockedIncrement(&dword_1400877B0);
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
    _InterlockedIncrement(&dword_1400876E8);
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
  if ( (byte_140087202 & 4) != 0 )
  {
    v34 = *(_QWORD *)(a1 + 32);
    v35 = 56;
    if ( (unsigned int)(*(_DWORD *)v34 - 3) > 3 )
      v35 = 40;
    McTemplateK0pxqqt_EtwWriteTransfer(
      *(_DWORD *)v34,
      (unsigned int)&EventCreateProcessAllocation,
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
0x1400fcf10  mov     [rsp+arg_10], rbx
0x1400fcf15  mov     [rsp+ViewSize], rdx
0x1400fcf1a  push    rbp
0x1400fcf1b  push    rsi
0x1400fcf1c  push    rdi
0x1400fcf1d  push    r14
0x1400fcf1f  push    r15
0x1400fcf21  sub     rsp, 50h
0x1400fcf25  mov     r10, [rcx+20h]
0x1400fcf29  mov     rbx, rcx
0x1400fcf2c  mov     r11d, r8d
0x1400fcf2f  mov     r15d, r9d
0x1400fcf32  mov     r8, rdx; unsigned __int64
0x1400fcf35  mov     ecx, [r10]
0x1400fcf38  lea     eax, [rcx-9]
0x1400fcf3b  cmp     eax, 1
0x1400fcf3e  jbe     loc_1400FD1F2
0x1400fcf44  mov     dl, [r10+10h]
0x1400fcf48  lea     eax, [rcx-3]
0x1400fcf4b  mov     r9d, r11d
0x1400fcf4e  and     r9d, 2
0x1400fcf52  cmp     eax, 3
0x1400fcf55  jbe     loc_1400FD042
0x1400fcf5b  mov     al, [r10+11h]
0x1400fcf5f  mov     ebp, 4
0x1400fcf64  and     r11d, ebp
0x1400fcf67  cmp     ecx, 2
0x1400fcf6a  jz      short loc_1400FCF76
0x1400fcf6c  mov     esi, 404h
0x1400fcf71  cmp     ecx, 8
0x1400fcf74  jnz     short loc_1400FCF78
0x1400fcf76  mov     esi, ebp
0x1400fcf78  xor     edi, edi
0x1400fcf7a  mov     r8d, 2000h
0x1400fcf80  mov     [rbx+90h], r8d
0x1400fcf87  test    al, al
0x1400fcf89  jz      short loc_1400FCF98
0x1400fcf8b  mov     r8d, 202000h
0x1400fcf91  mov     [rbx+90h], r8d
0x1400fcf98  test    dl, dl
0x1400fcf9a  jz      short loc_1400FCFAF
0x1400fcf9c  test    r9d, r9d
0x1400fcf9f  jnz     short loc_1400FCFAF
0x1400fcfa1  or      r8d, 20400000h
0x1400fcfa8  mov     [rbx+90h], r8d
0x1400fcfaf  test    r11d, r11d
0x1400fcfb2  jz      short loc_1400FCFC4
0x1400fcfb4  test    dl, dl
0x1400fcfb6  jnz     short loc_1400FCFC4
0x1400fcfb8  bts     r8d, 17h; unsigned int
0x1400fcfbd  mov     [rbx+90h], r8d
0x1400fcfc4  mov     r9d, esi; unsigned int
0x1400fcfc7  mov     dword ptr [rsp+78h+NewObject], r15d; unsigned int
0x1400fcfcc  lea     rdx, [rsp+78h+ViewSize]; unsigned __int64 *
0x1400fcfd4  lea     rcx, [rbx+28h]; void **
0x1400fcfd8  call    ?VidMmAllocateVirtualMemory@@YAJPEAPEAXPEA_KKKK@Z; VidMmAllocateVirtualMemory(void * *,unsigned __int64 *,ulong,ulong,ulong)
0x1400fcfdd  movsxd  rsi, eax
0x1400fcfe0  test    eax, eax
0x1400fcfe2  jns     short loc_1400FD00E
0x1400fcfe4  lock inc cs:dword_1400876E8
0x1400fcfeb  mov     rdx, rsi
0x1400fcfee  mov     ecx, 6
0x1400fcff3  call    cs:__imp_WdLogSingleEntry1
0x1400fcffa  nop     dword ptr [rax+rax+00h]
0x1400fcfff  mov     cs:WdLogGlobalForLineNumber, 1A69h
0x1400fd009  jmp     loc_1400FD270
0x1400fd00e  mov     rax, [rbx+28h]
0x1400fd012  mov     r10, [rsp+78h+ViewSize]
0x1400fd01a  mov     ecx, [rbx+90h]
0x1400fd020  add     rax, r10
0x1400fd023  mov     [rbx+30h], rax
0x1400fd027  mov     al, [rbx+94h]
0x1400fd02d  shr     ecx, 17h
0x1400fd030  and     al, 0FEh
0x1400fd032  and     cl, 1
0x1400fd035  or      cl, al
0x1400fd037  mov     [rbx+94h], cl
0x1400fd03d  jmp     loc_1400FD2B2
0x1400fd042  lea     eax, [rcx-4]
0x1400fd045  mov     [rsp+78h+arg_0], r8
0x1400fd04d  and     eax, 0FFFFFFFDh
0x1400fd050  neg     eax
0x1400fd052  sbb     esi, esi
0x1400fd054  xor     edi, edi
0x1400fd056  and     esi, 40000000h
0x1400fd05c  add     esi, 8040000h
0x1400fd062  or      esi, r15d
0x1400fd065  test    dl, dl
0x1400fd067  jz      short loc_1400FD072
0x1400fd069  test    r9d, r9d
0x1400fd06c  jnz     short loc_1400FD072
0x1400fd06e  bts     esi, 13h
0x1400fd072  lea     r14, [rbx+38h]
0x1400fd076  call    ?GetCurrentPartitionHandle@VIDMM_PROCESS@@SAPEAXXZ; VIDMM_PROCESS::GetCurrentPartitionHandle(void)
0x1400fd07b  mov     [rsp+78h+var_40], rdi
0x1400fd080  lea     r9, [rsp+78h+arg_0]
0x1400fd088  mov     [rsp+78h+var_48], rax
0x1400fd08d  mov     ebp, 4
0x1400fd092  mov     dword ptr [rsp+78h+Handle], esi
0x1400fd096  xor     r8d, r8d
0x1400fd099  xor     edx, edx
0x1400fd09b  mov     dword ptr [rsp+78h+NewObject], ebp
0x1400fd09f  mov     rcx, r14
0x1400fd0a2  call    cs:__imp_MmCreateSection
0x1400fd0a9  nop     dword ptr [rax+rax+00h]
0x1400fd0ae  movsxd  rsi, eax
0x1400fd0b1  test    eax, eax
0x1400fd0b3  jns     short loc_1400FD0E4
0x1400fd0b5  lock inc cs:dword_1400877B0
0x1400fd0bc  mov     rdx, rsi
0x1400fd0bf  lea     ecx, [rbp+2]
0x1400fd0c2  call    cs:__imp_WdLogSingleEntry1
0x1400fd0c9  nop     dword ptr [rax+rax+00h]
0x1400fd0ce  lea     r9, aCouldnTAllocat_15; "Couldn't allocate a backing section for"...
0x1400fd0d5  mov     cs:WdLogGlobalForLineNumber, 1AA0h
0x1400fd0df  jmp     loc_1400FD277
0x1400fd0e4  mov     rcx, [r14]; Object
0x1400fd0e7  call    cs:__imp_ObfReferenceObject
0x1400fd0ee  nop     dword ptr [rax+rax+00h]
0x1400fd0f3  mov     rcx, [r14]; Object
0x1400fd0f6  lea     rax, [rbx+40h]
0x1400fd0fa  mov     [rsp+78h+Handle], rax; Handle
0x1400fd0ff  xor     r9d, r9d; ObjectPointerBias
0x1400fd102  xor     r8d, r8d; DesiredAccess
0x1400fd105  mov     [rsp+78h+NewObject], rdi; NewObject
0x1400fd10a  xor     edx, edx; PassedAccessState
0x1400fd10c  call    cs:__imp_ObInsertObject
0x1400fd113  nop     dword ptr [rax+rax+00h]
0x1400fd118  movsxd  rsi, eax
0x1400fd11b  test    eax, eax
0x1400fd11d  jns     short loc_1400FD168
0x1400fd11f  mov     rdx, [r14]
0x1400fd122  mov     r8, rsi
0x1400fd125  mov     ecx, 1
0x1400fd12a  call    cs:__imp_WdLogSingleEntry2
0x1400fd131  nop     dword ptr [rax+rax+00h]
0x1400fd136  mov     [rsp+78h+var_40], rdi
0x1400fd13b  lea     r9, aUnableToInsert; "Unable to insert section object 0x%I64p"...
0x1400fd142  mov     [rsp+78h+var_48], rdi
0x1400fd147  mov     edx, 40000h
0x1400fd14c  mov     cs:WdLogGlobalForLineNumber, 1AB5h
0x1400fd156  mov     rcx, [r14]
0x1400fd159  mov     [rsp+78h+Handle], rsi
0x1400fd15e  mov     [rsp+78h+NewObject], rcx
0x1400fd163  jmp     loc_1400FD290
0x1400fd168  mov     rax, [rbx+20h]
0x1400fd16c  mov     ecx, [rax]
0x1400fd16e  sub     ecx, 5
0x1400fd171  cmp     ecx, 1
0x1400fd174  jbe     short loc_1400FD18B
0x1400fd176  mov     r10, [rsp+78h+ViewSize]
0x1400fd17e  mov     [rbx+30h], r10
0x1400fd182  mov     [rbx+28h], rdi
0x1400fd186  jmp     loc_1400FD2B2
0x1400fd18b  mov     rcx, [r14]; Section
0x1400fd18e  lea     r8, [rsp+78h+ViewSize]; ViewSize
0x1400fd196  lea     rdx, [rbx+28h]; MappedBase
0x1400fd19a  call    cs:__imp_MmMapViewInSystemSpace
0x1400fd1a1  nop     dword ptr [rax+rax+00h]
0x1400fd1a6  movsxd  rsi, eax
0x1400fd1a9  test    eax, eax
0x1400fd1ab  jns     short loc_1400FD1DE
0x1400fd1ad  lock inc cs:dword_1400877B0
0x1400fd1b4  mov     rdx, rsi
0x1400fd1b7  mov     ecx, 6
0x1400fd1bc  call    cs:__imp_WdLogSingleEntry1
0x1400fd1c3  nop     dword ptr [rax+rax+00h]
0x1400fd1c8  lea     r9, aCouldnTMapView; "Couldn't map view of section to kernel "...
0x1400fd1cf  mov     cs:WdLogGlobalForLineNumber, 1AC3h
0x1400fd1d9  jmp     loc_1400FD277
0x1400fd1de  mov     rax, [rbx+28h]
0x1400fd1e2  mov     r10, [rsp+78h+ViewSize]
0x1400fd1ea  add     rax, r10
0x1400fd1ed  jmp     loc_1400FD2AE
0x1400fd1f2  mov     r9d, 800000h; unsigned int
0x1400fd1f8  lea     rax, [rbx+88h]
0x1400fd1ff  mov     [rbx+90h], r9d
0x1400fd206  lea     rdx, [rbx+80h]
0x1400fd20d  mov     rcx, [r10+8]
0x1400fd211  lea     r14, [rbx+28h]
0x1400fd215  cmp     dword ptr [r10], 0Ah
0x1400fd219  mov     esi, 404h
0x1400fd21e  mov     [rsp+78h+var_40], r14; void **
0x1400fd223  mov     ebp, 4
0x1400fd228  mov     [rsp+78h+var_48], rax; unsigned __int64 *
0x1400fd22d  cmovz   esi, ebp
0x1400fd230  mov     rcx, [rcx+8]; this
0x1400fd234  mov     [rsp+78h+Handle], rdx; void **
0x1400fd239  xor     edx, edx; void *
0x1400fd23b  mov     dword ptr [rsp+78h+NewObject], esi; unsigned int
0x1400fd23f  call    ?MapHostVirtualAddressToGuest@VIDMM_PROCESS@@QEAAJPEAX_KKKPEAPEAXPEA_K2@Z; VIDMM_PROCESS::MapHostVirtualAddressToGuest(void *,unsigned __int64,ulong,ulong,void * *,unsigned __int64 *,void * *)
0x1400fd244  xor     edi, edi
0x1400fd246  movsxd  rsi, eax
0x1400fd249  test    eax, eax
0x1400fd24b  jns     short loc_1400FD299
0x1400fd24d  lock inc cs:dword_1400876E8
0x1400fd254  mov     rdx, rsi
0x1400fd257  lea     ecx, [rbp+2]
0x1400fd25a  call    cs:__imp_WdLogSingleEntry1
0x1400fd261  nop     dword ptr [rax+rax+00h]
0x1400fd266  mov     cs:WdLogGlobalForLineNumber, 1A36h
0x1400fd270  lea     r9, aCouldnTAllocat_42; "Couldn't allocate virtual memory range "...
0x1400fd277  mov     [rsp+78h+var_40], rdi
0x1400fd27c  mov     edx, 40001h
0x1400fd281  mov     [rsp+78h+var_48], rdi
0x1400fd286  mov     [rsp+78h+Handle], rdi
0x1400fd28b  mov     [rsp+78h+NewObject], rsi
0x1400fd290  call    DxgkLogInternalTriageEvent
0x1400fd295  mov     eax, esi
0x1400fd297  jmp     short loc_1400FD308
0x1400fd299  mov     rax, [r14]
0x1400fd29c  mov     r10, [rsp+78h+ViewSize]
0x1400fd2a4  add     rax, r10
0x1400fd2a7  or      byte ptr [rbx+94h], 1
0x1400fd2ae  mov     [rbx+30h], rax
0x1400fd2b2  test    cs:byte_140087202, bpl
0x1400fd2b9  jz      short loc_1400FD306
0x1400fd2bb  mov     rdx, [rbx+20h]
0x1400fd2bf  mov     dword ptr [rsp+78h+var_40], 1
0x1400fd2c7  mov     rax, [rdx+8]
0x1400fd2cb  mov     rcx, [rax+8]
0x1400fd2cf  mov     r8d, [rcx+18h]
0x1400fd2d3  mov     ecx, [rdx]
0x1400fd2d5  mov     edx, 28h ; '('
0x1400fd2da  mov     dword ptr [rsp+78h+var_48], r8d
0x1400fd2df  mov     dword ptr [rsp+78h+Handle], ecx
0x1400fd2e3  mov     [rsp+78h+NewObject], r10
0x1400fd2e8  lea     r9d, [rdx+10h]
0x1400fd2ec  lea     eax, [rcx-3]
0x1400fd2ef  cmp     eax, 3
0x1400fd2f2  cmova   r9d, edx
0x1400fd2f6  lea     rdx, EventCreateProcessAllocation
0x1400fd2fd  mov     r9, [r9+rbx]
0x1400fd301  call    McTemplateK0pxqqt_EtwWriteTransfer
0x1400fd306  xor     eax, eax
0x1400fd308  mov     rbx, [rsp+78h+arg_10]
0x1400fd310  add     rsp, 50h
0x1400fd314  pop     r15
0x1400fd316  pop     r14
0x1400fd318  pop     rdi
0x1400fd319  pop     rsi
0x1400fd31a  pop     rbp
0x1400fd31b  retn
```
