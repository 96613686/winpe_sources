# FinalElevationPage::SortRootCauses(DirectUI::Element *)

- ea: `0x14001bbe0`
- end: `0x14001be79`
- name: `?SortRootCauses@FinalElevationPage@@EEAAJPEAVElement@DirectUI@@@Z`
- size: `665`
- prototype: `__int64 __fastcall(FinalElevationPage *__hidden this, struct DirectUI::Element *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400054f4`
- `0x140019f68`
- `0x14001b494`
- `0x14001bbe0`
- `0x140020420`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x14001bcbe`
- `KERNEL32!HeapAlloc` at `0x14001bcbe`
- `KERNEL32!HeapFree` at `0x14001bdf2`
- `KERNEL32!HeapFree` at `0x14001bdf2`
- `KERNEL32!GetProcessHeap` at `0x14001bca7`
- `KERNEL32!GetProcessHeap` at `0x14001bdde`
- `KERNEL32!GetProcessHeap` at `0x14001bca7`
- `KERNEL32!GetProcessHeap` at `0x14001bdde`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x14001bd3e`
- `DUI70!?GetVisible@Element@DirectUI@@QEAA_NXZ` at `0x14001bd3e`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001bd59`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001bda2`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001bd59`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x14001bda2`
- `DUI70!?RemoveAll@Element@DirectUI@@QEAAJXZ` at `0x14001bc78`
- `DUI70!?RemoveAll@Element@DirectUI@@QEAAJXZ` at `0x14001bc78`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x14001be31`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x14001be31`
- `DUI70!StrToID` at `0x14001bd18`
- `DUI70!StrToID` at `0x14001bd18`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14001bd2f`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x14001bd2f`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x14001bc08`
- `DUI70!?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z` at `0x14001bc08`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FinalElevationPage::SortRootCauses(FinalElevationPage *this, struct DirectUI::Element *a2)
{
  __int64 Children; // rax
  DirectUI::Element *v4; // rsi
  unsigned int v5; // edi
  int v6; // r9d
  int v7; // eax
  int v8; // eax
  unsigned int v9; // r14d
  HANDLE ProcessHeap; // rax
  _DWORD *v11; // r12
  __int64 v12; // rbp
  _QWORD *v13; // rbx
  _QWORD *v14; // rax
  unsigned __int16 v15; // ax
  DirectUI::Element *Descendent; // rax
  int v17; // eax
  int v18; // r9d
  __int64 v19; // rbp
  HANDLE v20; // rax
  void *v21; // rdx
  DirectUI::Value *v23; // [rsp+90h] [rbp+18h] BYREF
  DirectUI::Element *v24; // [rsp+98h] [rbp+20h] BYREF

  v23 = 0;
  Children = DirectUI::Element::GetChildren(a2, &v23);
  if ( !Children )
  {
    v4 = 0;
    v5 = -2147418113;
    v6 = 1195;
LABEL_3:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalElevationPage::SortRootCauses", v6, v5);
    goto LABEL_31;
  }
  v24 = 0;
  v7 = DirectUI::DynamicArrayBase<DirectUI::Element *,DirectUI::DoubleAllocationPolicy<DirectUI::Element *>,1,0>::Clone(
         Children,
         &v24);
  v5 = v7;
  if ( v7 < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalElevationPage::SortRootCauses", 1198, v7);
    v4 = 0;
    goto LABEL_31;
  }
  v4 = v24;
  v8 = DirectUI::Element::RemoveAll(a2);
  v5 = v8;
  if ( v8 < 0 )
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalElevationPage::SortRootCauses", 1201, v8);
    goto LABEL_31;
  }
  v9 = *(_DWORD *)v4 & 0xFFFFFFF;
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, 4LL * v9);
  if ( !v11 )
  {
    v5 = -2147024882;
    v6 = 1206;
    goto LABEL_3;
  }
  v12 = 0;
  v13 = (_QWORD *)((char *)v4 + 8);
  while ( (unsigned int)v12 < v9 )
  {
    v13 = (_QWORD *)((char *)v4 + 8);
    if ( (*(_DWORD *)v4 & 0x10000000) != 0 )
      v14 = (_QWORD *)*v13;
    else
      v14 = (_QWORD *)((char *)v4 + 8);
    v24 = (DirectUI::Element *)v14[v12];
    v15 = StrToID(L"rcpic");
    Descendent = DirectUI::Element::FindDescendent(v24, v15);
    if ( DirectUI::Element::GetVisible(Descendent) )
    {
      v17 = DirectUI::Element::Add(a2, v24);
      v5 = v17;
      if ( v17 < 0 )
      {
        v18 = 1217;
LABEL_28:
        SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "FinalElevationPage::SortRootCauses", v18, v17);
        goto LABEL_29;
      }
      v11[v12] = 1;
    }
    v12 = (unsigned int)(v12 + 1);
  }
  v19 = 0;
  while ( (unsigned int)v19 < v9 )
  {
    if ( !v11[v19] )
    {
      if ( (*(_DWORD *)v4 & 0x10000000) != 0 )
        v13 = (_QWORD *)*v13;
      v17 = DirectUI::Element::Add(a2, (struct DirectUI::Element *)v13[v19]);
      v5 = v17;
      if ( v17 < 0 )
      {
        v18 = 1231;
        goto LABEL_28;
      }
    }
    v19 = (unsigned int)(v19 + 1);
    v13 = (_QWORD *)((char *)v4 + 8);
  }
LABEL_29:
  v20 = GetProcessHeap();
  HeapFree(v20, 0, v11);
LABEL_31:
  if ( v23 )
  {
    DirectUI::Value::Release(v23);
    v23 = 0;
  }
  if ( v4 )
  {
    DirectUI::DynamicArrayBase<DirectUI::Element *,DirectUI::DoubleAllocationPolicy<DirectUI::Element *>,1,0>::Release(v4);
    DirectUI::HFree(v4, v21);
  }
  return v5;
}

```

## disassembly

```asm
0x14001bbe0  mov     rax, rsp
0x14001bbe3  mov     [rax+8], rbx
0x14001bbe7  push    rbp
0x14001bbe8  push    rsi
0x14001bbe9  push    rdi
0x14001bbea  push    r12
0x14001bbec  push    r13
0x14001bbee  push    r14
0x14001bbf0  push    r15
0x14001bbf2  sub     rsp, 40h
0x14001bbf6  mov     r15, rdx
0x14001bbf9  mov     qword ptr [rax+18h], 0
0x14001bc01  mov     rcx, r15
0x14001bc04  lea     rdx, [rax+18h]
0x14001bc08  call    cs:__imp_?GetChildren@Element@DirectUI@@QEAAPEAV?$DynamicArray@PEAVElement@DirectUI@@$0A@@2@PEAPEAVValue@2@@Z; DirectUI::Element::GetChildren(DirectUI::Value * *)
0x14001bc0f  nop     dword ptr [rax+rax+00h]
0x14001bc14  test    rax, rax
0x14001bc17  jnz     short loc_14001BC47
0x14001bc19  xor     esi, esi
0x14001bc1b  mov     edi, 8000FFFFh
0x14001bc20  mov     r9d, 4ABh
0x14001bc26  mov     [rsp+78h+var_58], edi
0x14001bc2a  lea     r8, aFinalelevation_0; "FinalElevationPage::SortRootCauses"
0x14001bc31  mov     ecx, 1; Level
0x14001bc36  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14001bc3d  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001bc42  jmp     loc_14001BE24
0x14001bc47  lea     rdx, [rsp+78h+arg_18]
0x14001bc4f  mov     [rsp+78h+arg_18], 0
0x14001bc5b  mov     rcx, rax
0x14001bc5e  call    ?Clone@?$DynamicArrayBase@PEAVElement@DirectUI@@V?$DoubleAllocationPolicy@PEAVElement@DirectUI@@@2@$00$0A@@DirectUI@@QEBAJPEAPEAV12@@Z; DirectUI::DynamicArrayBase<DirectUI::Element *,DirectUI::DoubleAllocationPolicy<DirectUI::Element *>,1,0>::Clone(DirectUI::DynamicArrayBase<DirectUI::Element *,DirectUI::DoubleAllocationPolicy<DirectUI::Element *>,1,0> * *)
0x14001bc63  mov     edi, eax
0x14001bc65  test    eax, eax
0x14001bc67  js      loc_14001BE00
0x14001bc6d  mov     rsi, [rsp+78h+arg_18]
0x14001bc75  mov     rcx, r15
0x14001bc78  call    cs:__imp_?RemoveAll@Element@DirectUI@@QEAAJXZ; DirectUI::Element::RemoveAll(void)
0x14001bc7f  nop     dword ptr [rax+rax+00h]
0x14001bc84  mov     edi, eax
0x14001bc86  test    eax, eax
0x14001bc88  jns     short loc_14001BC96
0x14001bc8a  mov     [rsp+78h+var_58], eax
0x14001bc8e  mov     r9d, 4B1h
0x14001bc94  jmp     short loc_14001BC2A
0x14001bc96  mov     r14d, [rsi]
0x14001bc99  and     r14d, 0FFFFFFFh
0x14001bca0  mov     ebx, r14d
0x14001bca3  shl     rbx, 2
0x14001bca7  call    cs:__imp_GetProcessHeap
0x14001bcae  nop     dword ptr [rax+rax+00h]
0x14001bcb3  mov     r8, rbx; dwBytes
0x14001bcb6  mov     edx, 8; dwFlags
0x14001bcbb  mov     rcx, rax; hHeap
0x14001bcbe  call    cs:__imp_HeapAlloc
0x14001bcc5  nop     dword ptr [rax+rax+00h]
0x14001bcca  mov     r12, rax
0x14001bccd  test    rax, rax
0x14001bcd0  jnz     short loc_14001BCE2
0x14001bcd2  mov     edi, 8007000Eh
0x14001bcd7  mov     r9d, 4B6h
0x14001bcdd  jmp     loc_14001BC26
0x14001bce2  xor     ebp, ebp
0x14001bce4  lea     rbx, [rsi+8]
0x14001bce8  cmp     ebp, r14d
0x14001bceb  jnb     loc_14001BD82
0x14001bcf1  test    dword ptr [rsi], 10000000h
0x14001bcf7  lea     rbx, [rsi+8]
0x14001bcfb  jz      short loc_14001BD02
0x14001bcfd  mov     rax, [rbx]
0x14001bd00  jmp     short loc_14001BD05
0x14001bd02  mov     rax, rbx
0x14001bd05  mov     rax, [rax+rbp*8]
0x14001bd09  lea     rcx, aRcpic; "rcpic"
0x14001bd10  mov     [rsp+78h+arg_18], rax
0x14001bd18  call    cs:__imp_StrToID
0x14001bd1f  nop     dword ptr [rax+rax+00h]
0x14001bd24  mov     rcx, [rsp+78h+arg_18]
0x14001bd2c  movzx   edx, ax
0x14001bd2f  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x14001bd36  nop     dword ptr [rax+rax+00h]
0x14001bd3b  mov     rcx, rax
0x14001bd3e  call    cs:__imp_?GetVisible@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetVisible(void)
0x14001bd45  nop     dword ptr [rax+rax+00h]
0x14001bd4a  test    al, al
0x14001bd4c  jz      short loc_14001BD73
0x14001bd4e  mov     rdx, [rsp+78h+arg_18]
0x14001bd56  mov     rcx, r15
0x14001bd59  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x14001bd60  nop     dword ptr [rax+rax+00h]
0x14001bd65  mov     edi, eax
0x14001bd67  test    eax, eax
0x14001bd69  js      short loc_14001BD7A
0x14001bd6b  mov     dword ptr [r12+rbp*4], 1
0x14001bd73  inc     ebp
0x14001bd75  jmp     loc_14001BCE8
0x14001bd7a  mov     r9d, 4C1h
0x14001bd80  jmp     short loc_14001BDC2
0x14001bd82  xor     ebp, ebp
0x14001bd84  cmp     ebp, r14d
0x14001bd87  jnb     short loc_14001BDDE
0x14001bd89  cmp     dword ptr [r12+rbp*4], 0
0x14001bd8e  jnz     short loc_14001BDB4
0x14001bd90  test    dword ptr [rsi], 10000000h
0x14001bd96  jz      short loc_14001BD9B
0x14001bd98  mov     rbx, [rbx]
0x14001bd9b  mov     rdx, [rbx+rbp*8]
0x14001bd9f  mov     rcx, r15
0x14001bda2  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x14001bda9  nop     dword ptr [rax+rax+00h]
0x14001bdae  mov     edi, eax
0x14001bdb0  test    eax, eax
0x14001bdb2  js      short loc_14001BDBC
0x14001bdb4  inc     ebp
0x14001bdb6  lea     rbx, [rsi+8]
0x14001bdba  jmp     short loc_14001BD84
0x14001bdbc  mov     r9d, 4CFh
0x14001bdc2  lea     r8, aFinalelevation_0; "FinalElevationPage::SortRootCauses"
0x14001bdc9  mov     [rsp+78h+var_58], eax
0x14001bdcd  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14001bdd4  mov     ecx, 1; Level
0x14001bdd9  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001bdde  call    cs:__imp_GetProcessHeap
0x14001bde5  nop     dword ptr [rax+rax+00h]
0x14001bdea  mov     r8, r12; lpMem
0x14001bded  xor     edx, edx; dwFlags
0x14001bdef  mov     rcx, rax; hHeap
0x14001bdf2  call    cs:__imp_HeapFree
0x14001bdf9  nop     dword ptr [rax+rax+00h]
0x14001bdfe  jmp     short loc_14001BE24
0x14001be00  mov     r9d, 4AEh
0x14001be06  mov     [rsp+78h+var_58], eax
0x14001be0a  lea     r8, aFinalelevation_0; "FinalElevationPage::SortRootCauses"
0x14001be11  mov     ecx, 1; Level
0x14001be16  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14001be1d  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001be22  xor     esi, esi
0x14001be24  mov     rcx, [rsp+78h+arg_10]
0x14001be2c  test    rcx, rcx
0x14001be2f  jz      short loc_14001BE49
0x14001be31  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x14001be38  nop     dword ptr [rax+rax+00h]
0x14001be3d  mov     [rsp+78h+arg_10], 0
0x14001be49  test    rsi, rsi
0x14001be4c  jz      short loc_14001BE5E
0x14001be4e  mov     rcx, rsi
0x14001be51  call    ?Release@?$DynamicArrayBase@PEAVElement@DirectUI@@V?$DoubleAllocationPolicy@PEAVElement@DirectUI@@@2@$00$0A@@DirectUI@@QEAAXXZ; DirectUI::DynamicArrayBase<DirectUI::Element *,DirectUI::DoubleAllocationPolicy<DirectUI::Element *>,1,0>::Release(void)
0x14001be56  mov     rcx, rsi; this
0x14001be59  call    ?HFree@DirectUI@@YAXPEAX@Z; DirectUI::HFree(void *)
0x14001be5e  mov     rbx, [rsp+78h+arg_0]
0x14001be66  mov     eax, edi
0x14001be68  add     rsp, 40h
0x14001be6c  pop     r15
0x14001be6e  pop     r14
0x14001be70  pop     r13
0x14001be72  pop     r12
0x14001be74  pop     rdi
0x14001be75  pop     rsi
0x14001be76  pop     rbp
0x14001be77  retn
```
