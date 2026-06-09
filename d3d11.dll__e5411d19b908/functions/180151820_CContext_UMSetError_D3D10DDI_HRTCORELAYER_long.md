# CContext::UMSetError_(D3D10DDI_HRTCORELAYER,long)

- ea: `0x180151820`
- end: `0x180151d38`
- name: `?UMSetError_@CContext@@SAXUD3D10DDI_HRTCORELAYER@@J@Z`
- size: `1304`
- prototype: `static void __high(struct D3D10DDI_HRTCORELAYER, int)`
- caller_count: `138`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18010c890`
- `0x18010ca10`
- `0x18010cb90`
- `0x18010cd10`
- `0x18010ce60`
- `0x18010cfe0`
- `0x18010d130`
- `0x18010e720`
- `0x18010e920`
- `0x18010eb30`
- `0x18010ecc0`
- `0x180111c30`
- `0x180111c80`
- `0x180111d10`
- `0x180111d90`
- `0x180111e20`
- `0x180111ea0`
- `0x180111ef0`
- `0x180111f80`
- `0x180111fd0`
- `0x1801126d0`
- `0x1801127d0`
- `0x180112880`
- `0x1801129a0`
- `0x180112a50`
- `0x180113210`
- `0x1801132a0`
- `0x180113360`
- `0x1801133f0`
- `0x180113450`
- `0x180113510`
- `0x180113570`
- `0x180117670`
- `0x180117740`
- `0x180117830`
- `0x180117900`
- `0x1801179a0`
- `0x180117a90`
- `0x180117bb0`
- `0x1801197d0`
- `0x180119980`
- `0x180119be0`
- `0x180122990`
- `0x180122c70`
- `0x180122f60`
- `0x180123240`
- `0x180123500`
- `0x1801237f0`
- `0x180123b30`
- `0x180124490`

## callees

- `0x1800229a0`
- `0x1800bc1e8`
- `0x1800c385c`
- `0x180151820`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180151842`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180151842`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18015195f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18015195f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18015199a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18015199a`

## string_xrefs

- `0x180151a38`: `UMD reported device removed.`
- `0x180151a01`: `UMD reported error while device is removed.`

## pseudocode

```c
void __fastcall CContext::UMSetError_(__int64 a1, int a2)
{
  RTL_SRWLOCK *v4; // r15
  DWORD CurrentThreadId; // eax
  __int64 v6; // r9
  int v7; // r12d
  char *v8; // r14
  char *v9; // rsi
  int v10; // ebp
  __int64 v11; // rax
  char v12; // [rsp+30h] [rbp-38h] BYREF
  int v13; // [rsp+34h] [rbp-34h]
  DWORD v14; // [rsp+70h] [rbp+8h] BYREF
  char v15; // [rsp+80h] [rbp+18h] BYREF

  v4 = *(RTL_SRWLOCK **)(a1 + 160);
  CurrentThreadId = GetCurrentThreadId();
  v14 = CurrentThreadId;
  v7 = 1;
  v12 = 1;
  v13 = 0;
  v8 = (char *)(a1 + 3692);
  v9 = (char *)(a1 + 3692);
  if ( *(_BYTE *)(a1 + 3709) && *(_DWORD *)(a1 + 3688) != CurrentThreadId )
  {
    AcquireSRWLockShared(v4 + 437);
    v11 = std::_Hash<std::_Umap_traits<unsigned long,SDDIErrorCtx *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,SDDIErrorCtx *>>,0>>::find(
            &v4[438],
            &v15,
            &v14);
    v9 = *(PVOID *)v11 == v4[439].Ptr ? &v12 : *(char **)(*(_QWORD *)v11 + 24LL);
    if ( v4 != (RTL_SRWLOCK *)-3496LL )
      ReleaseSRWLockShared(v4 + 437);
  }
  v10 = -2005270523;
  if ( *v9 != 5 )
  {
    switch ( *v9 )
    {
      case 0:
        if ( a2 == -2005530490 )
          goto LABEL_6;
        goto LABEL_34;
      case 1:
        switch ( a2 )
        {
          case -2147024882:
            goto LABEL_45;
          case -2005530512:
            goto LABEL_32;
          case -2005530491:
            goto LABEL_106;
          case -2005530490:
            goto LABEL_6;
        }
        if ( a2 != -2005530489 )
          goto LABEL_34;
        a2 = -2005270480;
        goto LABEL_6;
      case 2:
        if ( a2 != -2147024882 )
          goto LABEL_31;
        goto LABEL_6;
      case 3:
        switch ( a2 )
        {
          case -2147024882:
            goto LABEL_6;
          case -2005530512:
            goto LABEL_32;
          case -2005530491:
            goto LABEL_106;
          case -2005530490:
            goto LABEL_6;
        }
        if ( a2 != -2005204989 )
          goto LABEL_34;
        a2 = -2005270495;
        goto LABEL_6;
      case 4:
        if ( a2 == -2005204991 )
          goto LABEL_18;
        if ( a2 == -2147024882 )
        {
LABEL_45:
          if ( *(_DWORD *)(a1 + 3712) == 1 )
            goto LABEL_6;
          v7 = a2;
          goto LABEL_35;
        }
LABEL_31:
        if ( a2 == -2005530512 )
          goto LABEL_32;
        if ( a2 == -2005530491 )
          goto LABEL_106;
LABEL_100:
        if ( a2 == -2005530490 )
          goto LABEL_6;
        if ( a2 == -2005530489 )
          goto LABEL_102;
        goto LABEL_34;
      case 6:
        if ( a2 == -2005530491 )
          goto LABEL_106;
        if ( a2 == -2005530490 )
          goto LABEL_6;
        if ( a2 != -2005204990 )
          goto LABEL_34;
        a2 = -2005270524;
        goto LABEL_6;
      case 7:
        switch ( a2 )
        {
          case -2147024809:
            goto LABEL_6;
          case -2005530491:
            goto LABEL_106;
          case -2005530490:
            goto LABEL_6;
        }
        goto LABEL_34;
      case 8:
        if ( a2 > -2005530490 )
        {
          if ( a2 == -2005530489 )
          {
LABEL_102:
            a2 = -2147024882;
            goto LABEL_6;
          }
          if ( a2 == -2005204990 )
            goto LABEL_6;
          goto LABEL_34;
        }
        if ( a2 == -2005530490 || a2 == -2147024882 )
          goto LABEL_6;
        if ( a2 == -2005530512 )
          goto LABEL_32;
        if ( a2 != -2005530491 )
          goto LABEL_34;
        break;
      case 9:
        switch ( a2 )
        {
          case -2147024882:
            goto LABEL_45;
          case -2005530512:
            goto LABEL_32;
          case -2005530491:
            goto LABEL_106;
          case -2005530490:
            goto LABEL_6;
        }
        if ( a2 != -2005204991 )
          goto LABEL_34;
LABEL_18:
        a2 = -2005270518;
        goto LABEL_6;
      case 10:
        if ( a2 > -2005530491 )
          goto LABEL_100;
        switch ( a2 )
        {
          case -2005530491:
            goto LABEL_106;
          case -2147024882:
          case -2147024809:
            goto LABEL_6;
          case -2005530512:
            goto LABEL_32;
        }
        goto LABEL_34;
      case 11:
        switch ( a2 )
        {
          case -2005530512:
            goto LABEL_32;
          case -2005530491:
            goto LABEL_106;
          case -2005270526:
          case -2005270525:
          case 0:
            goto LABEL_6;
        }
        goto LABEL_34;
      default:
        __fastfail(0x25u);
    }
    goto LABEL_106;
  }
  switch ( a2 )
  {
    case -2005204991:
      a2 = 1;
      goto LABEL_6;
    case -2005530512:
LABEL_32:
      CModule::RecordJournal((CModule *)&g_Module, a2, "UMD reported device removed.", v6, 1);
      a2 = -2005270523;
      goto LABEL_6;
    case -2005530491:
LABEL_106:
      CModule::RecordJournal((CModule *)&g_Module, a2, "UMD reported application bug.", v6, 1);
      a2 = -2005270527;
      goto LABEL_6;
  }
  if ( a2 != -2005530490 )
  {
LABEL_34:
    v7 = a2;
    if ( a2 < 0 )
LABEL_35:
      CModule::RecordJournal((CModule *)&g_Module, a2, "Removing device due to bad UMD error.", v6, 1);
    a2 = -2005270496;
  }
LABEL_6:
  if ( v9 != v8 || *(_DWORD *)(a1 + 3712) != 1 )
  {
    if ( a2 != -2005270480 && a2 != -2005270527 && a2 != -2005270523 && a2 != -2005270496 )
      goto LABEL_12;
    if ( v9 != v8 )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*((_QWORD *)v4[154].Ptr + 2) + 264LL))(
        (__int64)v4[154].Ptr + 16,
        (unsigned int)a2);
      goto LABEL_12;
    }
LABEL_26:
    (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 39680) + 32LL))(
      *(_QWORD *)(a1 + 39680),
      (unsigned int)a2);
    goto LABEL_12;
  }
  if ( a2 == -2147024882 || a2 == -2005270527 || a2 == -2005270523 || a2 == -2005270496 || a2 == -2005270480 )
    goto LABEL_26;
LABEL_12:
  if ( *((int *)v4[154].Ptr + 312) >= 0 || a2 == -2005270523 )
  {
    v10 = a2;
  }
  else if ( a2 < 0 )
  {
    CModule::RecordJournal((CModule *)&g_Module, a2, "UMD reported error while device is removed.", v6, 1);
  }
  *((_DWORD *)v9 + 1) = v10;
  if ( a2 == -2005270496 )
    CDevice::DriverInternalErrorCB((CDevice *)v4, v7);
}

```

## disassembly

```asm
0x180151820  mov     [rsp+arg_8], rbx
0x180151825  mov     [rsp+arg_18], rbp
0x18015182a  push    rsi
0x18015182b  push    rdi
0x18015182c  push    r12
0x18015182e  push    r14
0x180151830  push    r15
0x180151832  sub     rsp, 40h
0x180151836  mov     edi, edx
0x180151838  mov     rbx, rcx
0x18015183b  mov     r15, [rcx+0A0h]
0x180151842  call    cs:__imp_GetCurrentThreadId
0x180151848  mov     [rsp+68h+arg_0], eax
0x18015184c  mov     r12d, 1
0x180151852  mov     [rsp+68h+var_38], r12b
0x180151857  mov     [rsp+68h+var_34], 0
0x18015185f  lea     r14, [rbx+0E6Ch]
0x180151866  mov     rsi, r14
0x180151869  cmp     byte ptr [rbx+0E7Dh], 0
0x180151870  jz      short loc_180151880
0x180151872  mov     ecx, [rbx+0E68h]
0x180151878  cmp     ecx, eax
0x18015187a  jnz     loc_180151955
0x180151880  movzx   eax, byte ptr [rsi]
0x180151883  mov     ebp, 887A0005h
0x180151888  cmp     eax, 5
0x18015188b  jnz     loc_180151923
0x180151891  cmp     edi, 887B0001h
0x180151897  jnz     loc_180151C92
0x18015189d  mov     edi, r12d
0x1801518a0  cmp     rsi, r14
0x1801518a3  jnz     short loc_1801518B2
0x1801518a5  cmp     dword ptr [rbx+0E80h], 1
0x1801518ac  jz      loc_180151CBB
0x1801518b2  cmp     edi, 887A0030h
0x1801518b8  jz      loc_1801519AC
0x1801518be  cmp     edi, 887A0001h
0x1801518c4  jz      loc_1801519AC
0x1801518ca  cmp     edi, ebp
0x1801518cc  jz      loc_1801519AC
0x1801518d2  cmp     edi, 887A0020h
0x1801518d8  jz      loc_1801519AC
0x1801518de  mov     rax, [r15+4D0h]
0x1801518e5  mov     edx, [rax+4E0h]
0x1801518eb  test    edx, edx
0x1801518ed  js      loc_1801519EC
0x1801518f3  mov     ebp, edi
0x1801518f5  mov     eax, 4
0x1801518fa  mov     [rax+rsi], ebp
0x1801518fd  cmp     edi, 887A0020h
0x180151903  jz      loc_180151CF8
0x180151909  mov     rbx, [rsp+68h+arg_8]
0x18015190e  mov     rbp, [rsp+68h+arg_18]
0x180151916  add     rsp, 40h
0x18015191a  pop     r15
0x18015191c  pop     r14
0x18015191e  pop     r12
0x180151920  pop     rdi
0x180151921  pop     rsi
0x180151922  retn
0x180151923  cmp     eax, 0Bh; switch 12 cases
0x180151926  ja      def_18015193D; jumptable 000000018015193D default case, case 5
0x18015192c  lea     rdx, __ImageBase
0x180151933  mov     ecx, ds:(jpt_18015193D - 180000000h)[rdx+rax*4]
0x18015193a  add     rcx, rdx
0x18015193d  jmp     rcx; switch jump
0x18015193f  cmp     edi, 887B0001h; jumptable 000000018015193D case 4
0x180151945  jnz     loc_180151A1B
0x18015194b  mov     edi, 887A000Ah
0x180151950  jmp     loc_1801518A0
0x180151955  lea     rbp, [r15+0DA8h]
0x18015195c  mov     rcx, rbp; SRWLock
0x18015195f  call    cs:__imp_AcquireSRWLockShared
0x180151965  lea     r8, [rsp+68h+arg_0]
0x18015196a  lea     rdx, [rsp+68h+arg_10]
0x180151972  lea     rcx, [r15+0DB0h]
0x180151979  call    ?find@?$_Hash@V?$_Umap_traits@KPEAUSDDIErrorCtx@@V?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAUSDDIErrorCtx@@@std@@@3@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKPEAUSDDIErrorCtx@@@std@@@std@@@std@@@2@AEBK@Z; std::_Hash<std::_Umap_traits<ulong,SDDIErrorCtx *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,SDDIErrorCtx *>>,0>>::find(ulong const &)
0x18015197e  mov     rcx, [rax]
0x180151981  cmp     rcx, [r15+0DB8h]
0x180151988  jz      short loc_1801519A5
0x18015198a  mov     rsi, [rcx+18h]
0x18015198e  test    rbp, rbp
0x180151991  jz      loc_180151880
0x180151997  mov     rcx, rbp; SRWLock
0x18015199a  call    cs:__imp_ReleaseSRWLockShared
0x1801519a0  jmp     loc_180151880
0x1801519a5  lea     rsi, [rsp+68h+var_38]
0x1801519aa  jmp     short loc_18015198E
0x1801519ac  cmp     rsi, r14
0x1801519af  jz      short loc_1801519D2
0x1801519b1  mov     rcx, [r15+4D0h]
0x1801519b8  add     rcx, 10h
0x1801519bc  mov     rax, [rcx]
0x1801519bf  mov     rax, [rax+108h]
0x1801519c6  mov     edx, edi
0x1801519c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801519cd  jmp     loc_1801518DE
0x1801519d2  mov     rcx, [rbx+9B00h]
0x1801519d9  mov     rax, [rcx]
0x1801519dc  mov     rax, [rax+20h]
0x1801519e0  mov     edx, edi
0x1801519e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801519e7  jmp     loc_1801518DE
0x1801519ec  cmp     edi, ebp
0x1801519ee  jz      loc_1801518F3
0x1801519f4  test    edi, edi
0x1801519f6  jns     loc_1801518F5
0x1801519fc  mov     [rsp+68h+var_48], 1; bool
0x180151a01  lea     r8, aUmdReportedErr; "UMD reported error while device is remo"...
0x180151a08  mov     edx, edi; unsigned int
0x180151a0a  lea     rcx, ?g_Module@@3VCModule@@A; this
0x180151a11  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x180151a16  jmp     loc_1801518F5
0x180151a1b  cmp     edi, 8007000Eh
0x180151a21  jz      loc_180151ACD
0x180151a27  cmp     edi, 88760870h
0x180151a2d  jnz     loc_180151AF0
0x180151a33  mov     [rsp+68h+var_48], r12b; bool
0x180151a38  lea     r8, aUmdReportedDev; "UMD reported device removed."
0x180151a3f  mov     edx, edi; unsigned int
0x180151a41  lea     rcx, ?g_Module@@3VCModule@@A; this
0x180151a48  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x180151a4d  mov     edi, ebp
0x180151a4f  jmp     loc_1801518A0
0x180151a54  mov     ecx, 25h ; '%'; jumptable 000000018015193D default case, case 5
0x180151a59  int     29h; Win8: RtlFailFast(ecx)
0x180151a5b  mov     r12d, edi
0x180151a5e  test    edi, edi
0x180151a60  jns     short loc_180151A7C
0x180151a62  mov     [rsp+68h+var_48], 1; bool
0x180151a67  lea     r8, aRemovingDevice; "Removing device due to bad UMD error."
0x180151a6e  mov     edx, edi; unsigned int
0x180151a70  lea     rcx, ?g_Module@@3VCModule@@A; this
0x180151a77  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x180151a7c  mov     edi, 887A0020h
0x180151a81  jmp     loc_1801518A0
0x180151a86  cmp     edi, 88760886h; jumptable 000000018015193D case 0
0x180151a8c  jnz     short loc_180151A5B
0x180151a8e  jmp     loc_1801518A0
0x180151a93  cmp     edi, 8007000Eh; jumptable 000000018015193D case 1
0x180151a99  jz      short loc_180151ACD
0x180151a9b  cmp     edi, 88760870h
0x180151aa1  jz      short loc_180151A33
0x180151aa3  cmp     edi, 88760885h
0x180151aa9  jz      loc_1801C55BD
0x180151aaf  cmp     edi, 88760886h
0x180151ab5  jz      loc_1801518A0
0x180151abb  cmp     edi, 88760887h
0x180151ac1  jnz     short loc_180151A5B
0x180151ac3  mov     edi, 887A0030h
0x180151ac8  jmp     loc_1801518A0
0x180151acd  cmp     [rbx+0E80h], r12d
0x180151ad4  jz      loc_1801518A0
0x180151ada  mov     r12d, edi
0x180151add  jmp     short loc_180151A62
0x180151adf  cmp     edi, 8007000Eh; jumptable 000000018015193D case 2
0x180151ae5  jz      loc_1801518A0
0x180151aeb  jmp     loc_180151A27
0x180151af0  cmp     edi, 88760885h
0x180151af6  jnz     loc_1801C5582
0x180151afc  jmp     loc_1801C55BD
0x180151b01  cmp     edi, 8007000Eh; jumptable 000000018015193D case 3
0x180151b07  jz      loc_1801518A0
0x180151b0d  cmp     edi, 88760870h
0x180151b13  jz      loc_180151A33
0x180151b19  cmp     edi, 88760885h
0x180151b1f  jz      loc_1801C55BD
0x180151b25  cmp     edi, 88760886h
0x180151b2b  jz      loc_1801518A0
0x180151b31  cmp     edi, 887B0003h
0x180151b37  jnz     loc_180151A5B
0x180151b3d  mov     edi, 887A0021h
0x180151b42  jmp     loc_1801518A0
0x180151b47  cmp     edi, 88760885h; jumptable 000000018015193D case 6
0x180151b4d  jz      loc_1801C55BD
0x180151b53  cmp     edi, 88760886h
0x180151b59  jz      loc_1801518A0
0x180151b5f  cmp     edi, 887B0002h
0x180151b65  jnz     loc_180151A5B
0x180151b6b  mov     edi, 887A0004h
0x180151b70  jmp     loc_1801518A0
0x180151b75  cmp     edi, 80070057h; jumptable 000000018015193D case 7
0x180151b7b  jz      loc_1801518A0
0x180151b81  cmp     edi, 88760885h
0x180151b87  jz      loc_1801C55BD
0x180151b8d  cmp     edi, 88760886h
0x180151b93  jnz     loc_180151A5B
0x180151b99  jmp     loc_1801518A0
0x180151b9e  cmp     edi, 88760886h; jumptable 000000018015193D case 8
0x180151ba4  jg      loc_1801C55A4
0x180151baa  jz      loc_1801518A0
0x180151bb0  cmp     edi, 8007000Eh
0x180151bb6  jz      loc_1801518A0
0x180151bbc  cmp     edi, 88760870h
0x180151bc2  jz      loc_180151A33
0x180151bc8  cmp     edi, 88760885h
0x180151bce  jnz     loc_180151A5B
0x180151bd4  jmp     loc_1801C55BD
0x180151bd9  cmp     edi, 8007000Eh; jumptable 000000018015193D case 9
0x180151bdf  jz      loc_180151ACD
0x180151be5  cmp     edi, 88760870h
0x180151beb  jz      loc_180151A33
0x180151bf1  cmp     edi, 88760885h
0x180151bf7  jz      loc_1801C55BD
0x180151bfd  cmp     edi, 88760886h
0x180151c03  jz      loc_1801518A0
0x180151c09  cmp     edi, 887B0001h
0x180151c0f  jnz     loc_180151A5B
0x180151c15  jmp     loc_18015194B
0x180151c1a  cmp     edi, 88760885h; jumptable 000000018015193D case 10
0x180151c20  jg      loc_1801C5582
0x180151c26  jz      loc_1801C55BD
0x180151c2c  cmp     edi, 8007000Eh
0x180151c32  jz      loc_1801518A0
0x180151c38  cmp     edi, 80070057h
0x180151c3e  jz      loc_1801518A0
0x180151c44  cmp     edi, 88760870h
0x180151c4a  jnz     loc_180151A5B
0x180151c50  jmp     loc_180151A33
0x180151c55  cmp     edi, 88760870h; jumptable 000000018015193D case 11
0x180151c5b  jz      loc_180151A33
0x180151c61  cmp     edi, 88760885h
0x180151c67  jz      loc_1801C55BD
0x180151c6d  cmp     edi, 887A0002h
0x180151c73  jz      loc_1801518A0
0x180151c79  cmp     edi, 887A0003h
0x180151c7f  jz      loc_1801518A0
0x180151c85  test    edi, edi
0x180151c87  jnz     loc_180151A5B
0x180151c8d  jmp     loc_1801518A0
0x180151c92  cmp     edi, 88760870h
0x180151c98  jz      loc_180151A33
0x180151c9e  cmp     edi, 88760885h
0x180151ca4  jz      loc_1801C55BD
0x180151caa  cmp     edi, 88760886h
0x180151cb0  jz      loc_1801518A0
0x180151cb6  jmp     loc_180151A5B
0x180151cbb  cmp     edi, 8007000Eh
0x180151cc1  jz      loc_1801C55E1
0x180151cc7  cmp     edi, 887A0001h
0x180151ccd  jz      loc_1801C55E1
0x180151cd3  cmp     edi, ebp
0x180151cd5  jz      loc_1801C55E1
0x180151cdb  cmp     edi, 887A0020h
0x180151ce1  jz      loc_1801C55E1
0x180151ce7  cmp     edi, 887A0030h
0x180151ced  jnz     loc_1801518DE
0x180151cf3  jmp     loc_1801C55E1
0x180151cf8  mov     edx, r12d; int
0x180151cfb  mov     rcx, r15; this
0x180151cfe  call    ?DriverInternalErrorCB@CDevice@@QEAAXJ@Z; CDevice::DriverInternalErrorCB(long)
0x180151d03  jmp     loc_180151909
0x1801c5582  cmp     edi, 88760886h
0x1801c5588  jz      loc_1801518A0
0x1801c558e  cmp     edi, 88760887h
0x1801c5594  jnz     loc_180151A5B
0x1801c559a  mov     edi, 8007000Eh
0x1801c559f  jmp     loc_1801518A0
0x1801c55a4  cmp     edi, 88760887h
0x1801c55aa  jz      short loc_1801C559A
0x1801c55ac  cmp     edi, 887B0002h
0x1801c55b2  jz      loc_1801518A0
0x1801c55b8  jmp     loc_180151A5B
0x1801c55bd  mov     [rsp+68h+var_48], r12b; bool
0x1801c55c2  lea     r8, aUmdReportedApp; "UMD reported application bug."
0x1801c55c9  mov     edx, edi; unsigned int
0x1801c55cb  lea     rcx, ?g_Module@@3VCModule@@A; this
0x1801c55d2  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x1801c55d7  mov     edi, 887A0001h
0x1801c55dc  jmp     loc_1801518A0
0x1801c55e1  mov     rcx, [rbx+9B00h]
0x1801c55e8  mov     rax, [rcx]
0x1801c55eb  mov     rax, [rax+20h]
0x1801c55ef  jmp     loc_1801519C6
```
