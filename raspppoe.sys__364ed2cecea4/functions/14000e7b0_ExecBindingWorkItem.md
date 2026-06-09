# ExecBindingWorkItem

- ea: `0x14000e7b0`
- end: `0x14000e950`
- name: `ExecBindingWorkItem`
- size: `416`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x1400011b4`
- `0x140004abc`
- `0x1400054d4`
- `0x14000e7b0`
- `0x140014e68`
- `0x140015bb0`

## import_xrefs

- `ntoskrnl!MmLockPagableDataSection` at `0x14000e86a`
- `ntoskrnl!MmLockPagableDataSection` at `0x14000e86a`
- `NDIS!NdisCmRegisterSapComplete` at `0x14000e8d5`
- `NDIS!NdisCmRegisterSapComplete` at `0x14000e8d5`

## pseudocode

```c
void __fastcall ExecBindingWorkItem(_QWORD *a1, int a2)
{
  PDEVICE_OBJECT v4; // rcx
  int v5; // ebx
  unsigned int v6; // eax
  __int64 v7; // rbx
  bool v8; // si
  __int64 v9; // rbx
  __int64 v10; // rbx
  void *v11; // rbx
  __int64 v12; // rcx
  NDIS_HANDLE *v13; // rbx
  __int64 v14; // rcx

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  v5 = a2 - 1;
  if ( v5 )
  {
    if ( v5 == 1 )
    {
      v6 = PrSend(*a1, a1[1]);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 93, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids, v6);
    }
  }
  else
  {
    v7 = *a1;
    v8 = *a1 != 3;
    if ( !g_fPagesLocked )
    {
      MmLockPagableDataSection(FsmMakeCall);
      g_fPagesLocked = 1;
    }
    v9 = v7 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 == 1 )
        {
          LOBYTE(v4) = v8;
          ChangePacketFiltersForAdapters(v4);
        }
      }
      else
      {
        v11 = (void *)a1[3];
        PrReEnumerateBindings();
        LOBYTE(v12) = v8;
        ChangePacketFiltersForAdapters(v12);
        ScheduleWorkItem(v11);
      }
    }
    else
    {
      v13 = (NDIS_HANDLE *)a1[1];
      PrReEnumerateBindings();
      LOBYTE(v14) = v8;
      ChangePacketFiltersForAdapters(v14);
      NdisCmRegisterSapComplete(0, v13[17], v13);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
      }
      DereferenceAdapter(v13);
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
}

```

## disassembly

```asm
0x14000e7b0  push    rbx
0x14000e7b2  push    rsi
0x14000e7b3  push    rdi
0x14000e7b4  push    r15
0x14000e7b6  sub     rsp, 28h
0x14000e7ba  mov     ebx, edx
0x14000e7bc  mov     rdi, rcx
0x14000e7bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e7c6  lea     r15, WPP_GLOBAL_Control
0x14000e7cd  cmp     rcx, r15
0x14000e7d0  jz      short loc_14000E7F4
0x14000e7d2  mov     eax, [rcx+2Ch]
0x14000e7d5  test    al, 4
0x14000e7d7  jz      short loc_14000E7F4
0x14000e7d9  cmp     byte ptr [rcx+29h], 4
0x14000e7dd  jb      short loc_14000E7F4
0x14000e7df  mov     rcx, [rcx+18h]
0x14000e7e3  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000e7ea  mov     edx, 5Bh ; '['
0x14000e7ef  call    WPP_SF_
0x14000e7f4  sub     ebx, 1
0x14000e7f7  jz      short loc_14000E84F
0x14000e7f9  cmp     ebx, 1
0x14000e7fc  jnz     loc_14000E917
0x14000e802  mov     rdx, [rdi+8]
0x14000e806  mov     rcx, [rdi]
0x14000e809  call    PrSend
0x14000e80e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e815  cmp     rcx, r15
0x14000e818  jz      loc_14000E945
0x14000e81e  mov     edx, [rcx+2Ch]
0x14000e821  test    dl, 4
0x14000e824  jz      loc_14000E917
0x14000e82a  cmp     byte ptr [rcx+29h], 3
0x14000e82e  jb      loc_14000E917
0x14000e834  mov     rcx, [rcx+18h]
0x14000e838  lea     edx, [rbx+5Ch]
0x14000e83b  mov     r9d, eax
0x14000e83e  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000e845  call    WPP_SF_d
0x14000e84a  jmp     loc_14000E917
0x14000e84f  mov     rbx, [rdi]
0x14000e852  cmp     rbx, 3
0x14000e856  setnz   sil
0x14000e85a  cmp     cs:g_fPagesLocked, 0
0x14000e861  jnz     short loc_14000E87D
0x14000e863  lea     rcx, FsmMakeCall; AddressWithinSection
0x14000e86a  call    cs:__imp_MmLockPagableDataSection
0x14000e871  nop     dword ptr [rax+rax+00h]
0x14000e876  mov     cs:g_fPagesLocked, 1
0x14000e87d  sub     rbx, 1
0x14000e881  jz      short loc_14000E8B8
0x14000e883  sub     rbx, 1
0x14000e887  jz      short loc_14000E89D
0x14000e889  cmp     rbx, 1
0x14000e88d  jnz     loc_14000E917
0x14000e893  mov     cl, sil
0x14000e896  call    ChangePacketFiltersForAdapters
0x14000e89b  jmp     short loc_14000E917
0x14000e89d  mov     rbx, [rdi+18h]
0x14000e8a1  call    PrReEnumerateBindings
0x14000e8a6  mov     cl, sil
0x14000e8a9  call    ChangePacketFiltersForAdapters
0x14000e8ae  mov     rcx, rbx; WorkItemContext
0x14000e8b1  call    ScheduleWorkItem
0x14000e8b6  jmp     short loc_14000E917
0x14000e8b8  mov     rbx, [rdi+8]
0x14000e8bc  call    PrReEnumerateBindings
0x14000e8c1  mov     cl, sil
0x14000e8c4  call    ChangePacketFiltersForAdapters
0x14000e8c9  mov     rdx, [rbx+88h]; NdisSapHandle
0x14000e8d0  mov     r8, rbx; CallMgrSapContext
0x14000e8d3  xor     ecx, ecx; Status
0x14000e8d5  call    cs:__imp_NdisCmRegisterSapComplete
0x14000e8dc  nop     dword ptr [rax+rax+00h]
0x14000e8e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e8e8  cmp     rcx, r15
0x14000e8eb  jz      short loc_14000E90F
0x14000e8ed  mov     eax, [rcx+2Ch]
0x14000e8f0  test    al, 4
0x14000e8f2  jz      short loc_14000E90F
0x14000e8f4  cmp     byte ptr [rcx+29h], 4
0x14000e8f8  jb      short loc_14000E90F
0x14000e8fa  mov     rcx, [rcx+18h]
0x14000e8fe  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000e905  mov     edx, 5Ch ; '\'
0x14000e90a  call    WPP_SF_
0x14000e90f  mov     rcx, rbx
0x14000e912  call    DereferenceAdapter
0x14000e917  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e91e  cmp     rcx, r15
0x14000e921  jz      short loc_14000E945
0x14000e923  mov     eax, [rcx+2Ch]
0x14000e926  test    al, 4
0x14000e928  jz      short loc_14000E945
0x14000e92a  cmp     byte ptr [rcx+29h], 4
0x14000e92e  jb      short loc_14000E945
0x14000e930  mov     rcx, [rcx+18h]
0x14000e934  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x14000e93b  mov     edx, 5Eh ; '^'
0x14000e940  call    WPP_SF_
0x14000e945  add     rsp, 28h
0x14000e949  pop     r15
0x14000e94b  pop     rdi
0x14000e94c  pop     rsi
0x14000e94d  pop     rbx
0x14000e94e  retn
```
