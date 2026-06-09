# PmUpdateIdsGpt(_DRIVE_LAYOUT_INFORMATION_EX *,uchar)

- ea: `0x1400215d0`
- end: `0x140021731`
- name: `?PmUpdateIdsGpt@@YAXPEAU_DRIVE_LAYOUT_INFORMATION_EX@@E@Z`
- size: `353`
- prototype: `void __fastcall(struct _DRIVE_LAYOUT_INFORMATION_EX *, unsigned __int8)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1400214fc`

## callees

- `0x1400215d0`
- `0x1400217e8`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140021641`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400216f3`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x140021641`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400216f3`

## pseudocode

```c
void __fastcall PmUpdateIdsGpt(struct _DRIVE_LAYOUT_INFORMATION_EX *a1, char a2)
{
  union _DRIVE_LAYOUT_INFORMATION_EX::$E2E3D8483D032B54611BEB6ADCC46344 *p_Mbr; // rsi
  char *DeviceExtension; // r13
  __int64 v6; // rax
  DWORD PartitionCount; // r8d
  __int64 v8; // rdi
  GUID *p_PartitionId; // r12
  GUID *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 i; // rdx
  __int64 v14; // rcx
  __int64 Buffer; // [rsp+20h] [rbp-78h] BYREF
  __int128 v16; // [rsp+28h] [rbp-70h]
  struct _GUID v17; // [rsp+38h] [rbp-60h]

  Buffer = 0;
  p_Mbr = (union _DRIVE_LAYOUT_INFORMATION_EX::$E2E3D8483D032B54611BEB6ADCC46344 *)&a1->Mbr;
  v16 = 0;
  DeviceExtension = (char *)PmControlObject->DeviceExtension;
  v17 = 0;
  if ( a2 )
    goto LABEL_6;
  v6 = *(_QWORD *)&p_Mbr->Mbr.Signature - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&p_Mbr->Mbr.Signature == *(_QWORD *)&GUID_NULL.Data1 )
    v6 = *(_QWORD *)a1->Gpt.DiskId.Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( !v6
    || (v17 = *(struct _GUID *)&p_Mbr->Mbr.Signature,
        RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(DeviceExtension + 304), &Buffer)) )
  {
LABEL_6:
    PmUuidCreate((struct _GUID *)p_Mbr);
  }
  PartitionCount = a1->PartitionCount;
  if ( PartitionCount )
  {
    v8 = 0;
    p_PartitionId = &a1->PartitionEntry[0].Gpt.PartitionId;
    do
    {
      v10 = &p_PartitionId[9 * v8];
      if ( a2 )
        goto LABEL_24;
      v11 = *(_QWORD *)&v10->Data1 - *(_QWORD *)&GUID_NULL.Data1;
      if ( *(_QWORD *)&v10->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
        v11 = *(_QWORD *)v10->Data4 - *(_QWORD *)GUID_NULL.Data4;
      if ( !v11 )
        goto LABEL_24;
      v12 = *(_QWORD *)&v10->Data1 - *(_QWORD *)&p_Mbr->Mbr.Signature;
      if ( *(_QWORD *)&v10->Data1 == *(_QWORD *)&p_Mbr->Mbr.Signature )
        v12 = *(_QWORD *)v10->Data4 - *(_QWORD *)p_Mbr->Gpt.DiskId.Data4;
      if ( !v12 )
        goto LABEL_24;
      for ( i = (unsigned int)(v8 + 1); (unsigned int)i < PartitionCount; i = (unsigned int)(i + 1) )
      {
        v14 = *(_QWORD *)&v10->Data1 - *(_QWORD *)&a1->PartitionEntry[i].Gpt.PartitionId.Data1;
        if ( *(_QWORD *)&v10->Data1 == *(_QWORD *)&a1->PartitionEntry[i].Gpt.PartitionId.Data1 )
          v14 = *(_QWORD *)v10->Data4 - *(_QWORD *)a1->PartitionEntry[i].Gpt.PartitionId.Data4;
        if ( !v14 )
          goto LABEL_24;
      }
      v17 = *v10;
      if ( RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)(DeviceExtension + 304), &Buffer) )
      {
LABEL_24:
        PmUuidCreate(&p_PartitionId[9 * v8]);
        v8 = (unsigned int)(v8 + 1);
      }
      else
      {
        v8 = (unsigned int)(v8 + 1);
      }
      PartitionCount = a1->PartitionCount;
    }
    while ( (unsigned int)v8 < PartitionCount );
  }
}

```

## disassembly

```asm
0x1400215d0  push    rbx
0x1400215d2  push    rbp
0x1400215d3  push    rsi
0x1400215d4  push    rdi
0x1400215d5  push    r12
0x1400215d7  push    r13
0x1400215d9  push    r14
0x1400215db  push    r15
0x1400215dd  sub     rsp, 58h
0x1400215e1  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x1400215e8  xorps   xmm0, xmm0
0x1400215eb  mov     [rsp+98h+Buffer], 0
0x1400215f4  mov     r15b, dl
0x1400215f7  lea     rsi, [rcx+8]
0x1400215fb  mov     rbp, rcx
0x1400215fe  movups  [rsp+98h+var_70], xmm0
0x140021603  mov     r13, [rax+40h]
0x140021607  movups  [rsp+98h+var_60], xmm0
0x14002160c  test    dl, dl
0x14002160e  jnz     short loc_140021652
0x140021610  mov     rax, [rsi]
0x140021613  sub     rax, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x14002161a  jnz     short loc_140021627
0x14002161c  mov     rax, [rsi+8]
0x140021620  sub     rax, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data4; _GUID const GUID_NULL ...
0x140021627  test    rax, rax
0x14002162a  jz      short loc_140021652
0x14002162c  movups  xmm0, xmmword ptr [rsi]
0x14002162f  lea     rcx, [r13+130h]; Table
0x140021636  lea     rdx, [rsp+98h+Buffer]; Buffer
0x14002163b  movdqu  [rsp+98h+var_60], xmm0
0x140021641  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140021648  nop     dword ptr [rax+rax+00h]
0x14002164d  test    rax, rax
0x140021650  jz      short loc_14002165A
0x140021652  mov     rcx, rsi; struct _GUID *
0x140021655  call    ?PmUuidCreate@@YAXPEAU_GUID@@@Z; PmUuidCreate(_GUID *)
0x14002165a  mov     r8d, [rbp+4]
0x14002165e  test    r8d, r8d
0x140021661  jz      loc_14002171F
0x140021667  xor     edi, edi
0x140021669  lea     r12, [rbp+60h]
0x14002166d  lea     rbx, [rdi+rdi*8]
0x140021671  shl     rbx, 4
0x140021675  add     rbx, r12
0x140021678  test    r15b, r15b
0x14002167b  jnz     loc_140021708
0x140021681  mov     rax, [rbx]
0x140021684  sub     rax, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data1; _GUID const GUID_NULL ...
0x14002168b  jnz     short loc_140021698
0x14002168d  mov     rax, [rbx+8]
0x140021691  sub     rax, qword ptr cs:?GUID_NULL@@3U_GUID@@B.Data4; _GUID const GUID_NULL ...
0x140021698  test    rax, rax
0x14002169b  jz      short loc_140021708
0x14002169d  mov     rcx, [rbx]
0x1400216a0  sub     rcx, [rsi]
0x1400216a3  jnz     short loc_1400216AD
0x1400216a5  mov     rcx, [rbx+8]
0x1400216a9  sub     rcx, [rsi+8]
0x1400216ad  test    rcx, rcx
0x1400216b0  jz      short loc_140021708
0x1400216b2  lea     edx, [rdi+1]
0x1400216b5  cmp     edx, r8d
0x1400216b8  jnb     short loc_1400216DE
0x1400216ba  mov     rcx, [rbx]
0x1400216bd  lea     r9, [rdx+rdx*8]
0x1400216c1  shl     r9, 4
0x1400216c5  sub     rcx, [r9+rbp+60h]
0x1400216ca  jnz     short loc_1400216D5
0x1400216cc  mov     rcx, [rbx+8]
0x1400216d0  sub     rcx, [r9+rbp+68h]
0x1400216d5  test    rcx, rcx
0x1400216d8  jz      short loc_140021708
0x1400216da  inc     edx
0x1400216dc  jmp     short loc_1400216B5
0x1400216de  movups  xmm0, xmmword ptr [rbx]
0x1400216e1  lea     rcx, [r13+130h]; Table
0x1400216e8  lea     rdx, [rsp+98h+Buffer]; Buffer
0x1400216ed  movdqu  [rsp+98h+var_60], xmm0
0x1400216f3  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1400216fa  nop     dword ptr [rax+rax+00h]
0x1400216ff  test    rax, rax
0x140021702  jnz     short loc_140021708
0x140021704  inc     edi
0x140021706  jmp     short loc_140021712
0x140021708  mov     rcx, rbx; struct _GUID *
0x14002170b  call    ?PmUuidCreate@@YAXPEAU_GUID@@@Z; PmUuidCreate(_GUID *)
0x140021710  inc     edi
0x140021712  mov     r8d, [rbp+4]
0x140021716  cmp     edi, r8d
0x140021719  jb      loc_14002166D
0x14002171f  add     rsp, 58h
0x140021723  pop     r15
0x140021725  pop     r14
0x140021727  pop     r13
0x140021729  pop     r12
0x14002172b  pop     rdi
0x14002172c  pop     rsi
0x14002172d  pop     rbp
0x14002172e  pop     rbx
0x14002172f  retn
```
