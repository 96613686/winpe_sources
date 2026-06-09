# RxOrphanSrvOpensForFcb

- ea: `0x14006a520`
- end: `0x14006a831`
- name: `RxOrphanSrvOpensForFcb`
- size: `785`
- prototype: `__int64 __fastcall(PVOID Instance)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400441c0`
- `0x14006a4c0`

## callees

- `0x140009b80`
- `0x140015230`
- `0x14001820c`
- `0x140022c68`
- `0x140057660`
- `0x140058540`
- `0x140059d10`
- `0x14006a520`
- `0x14006a840`
- `0x14006ab80`

## import_xrefs

- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14006a586`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x14006a586`
- `ntoskrnl!KeBugCheckEx` at `0x14006a73b`
- `ntoskrnl!KeBugCheckEx` at `0x14006a73b`

## pseudocode

```c
__int64 __fastcall RxOrphanSrvOpensForFcb(char *Instance, UNICODE_STRING *a2)
{
  unsigned __int8 v4; // r12
  char v5; // r14
  __int64 v6; // r8
  const CHAR *v7; // r9
  int v8; // eax
  wchar_t **v9; // rsi
  wchar_t **v10; // rax
  struct _SRV_CALL *v11; // rcx
  int v12; // edi
  wchar_t **p_Buffer; // rax
  struct _SRV_CALL *v14; // rbp
  int v15; // ebp
  int v16; // ecx
  char v17; // al
  unsigned __int8 v18; // si
  const CHAR *v19; // r9
  struct _FCB *v20; // r14
  const CHAR *v22; // r9
  const CHAR *BugCheckParameter4; // [rsp+20h] [rbp-38h]
  const CHAR *BugCheckParameter4a; // [rsp+20h] [rbp-38h]
  ULONG BugCheckParameter4b; // [rsp+20h] [rbp-38h]
  ULONG v26; // [rsp+28h] [rbp-30h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 80, &WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids, Instance, a2);
  }
  if ( _InterlockedIncrement((volatile signed __int32 *)Instance + 38) == 1 )
    KeBugCheckEx(0x27u, 0xFCB003A5, (ULONG_PTR)Instance, 1u, 0);
  v4 = 1;
  v5 = 0;
  if ( !(unsigned __int8)ExIsResourceAcquiredSharedLite(*((PERESOURCE *)Instance + 1)) )
  {
    _RxAcquireFcb((PFCB)Instance, (PRX_CONTEXT)0xFFFFFFFFFFFFFFFELL, 1u, 0, BugCheckParameter4, v26);
    v5 = 1;
  }
  v8 = *((_DWORD *)Instance + 39);
  if ( (v8 & 0x80u) != 0 )
  {
    v15 = 1;
  }
  else
  {
    v9 = (wchar_t **)(Instance + 264);
    *((_DWORD *)Instance + 39) = v8 | 0x1000000;
    v10 = (wchar_t **)(Instance + 264);
    do
    {
      v10 = (wchar_t **)*v10;
      if ( v10 == v9 )
      {
        *((_DWORD *)Instance + 39) &= ~0x1000000u;
        v15 = 0;
        goto LABEL_16;
      }
      v11 = (struct _SRV_CALL *)(v10 - 17);
    }
    while ( *((_WORD *)v10 - 68) == 0xEBAA );
    v12 = 0;
    if ( v10 != (wchar_t **)136 )
    {
      do
      {
        p_Buffer = &v11->PrefixEntry.Prefix.Buffer;
        while ( 1 )
        {
          p_Buffer = (wchar_t **)*p_Buffer;
          if ( p_Buffer == v9 )
            break;
          v14 = (struct _SRV_CALL *)(p_Buffer - 17);
          if ( *((_WORD *)p_Buffer - 68) != 0xEBAA )
            goto LABEL_34;
        }
        v14 = 0;
LABEL_34:
        if ( !a2 || v11->pPrincipalName == a2 )
          RxOrphanSrvOpen(v11);
        else
          v4 = 0;
        v11 = v14;
      }
      while ( v14 );
    }
    *((_DWORD *)Instance + 39) &= ~0x1000000u;
    v15 = 0;
    if ( !v4 )
    {
      _InterlockedDecrement((volatile signed __int32 *)Instance + 38);
      v18 = 0;
      if ( v5 )
        _RxReleaseFcb(0, (PMRX_FCB)Instance, v6, v7, (ULONG)BugCheckParameter4);
      goto LABEL_27;
    }
  }
LABEL_16:
  RxDeregisterFcbWithBufferingManager(Instance);
  RxRemoveNameNetFcb((PFCB)Instance);
  if ( v17 )
    _InterlockedDecrement((volatile signed __int32 *)Instance + 38);
  *((_DWORD *)Instance + 39) |= 0x80u;
  v18 = 1;
  if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 0x10) != 0 )
    McTemplateK0ppp_EtwWriteTransfer(v16, (unsigned int)&RxOrphaning, 0, (_DWORD)Instance, 0, 0);
  *((_QWORD *)Instance + 20) = 0;
  if ( !RxpDereferenceAndFinalizeNetFcb((PFCB)Instance, 0, 0, 0) )
  {
    if ( v5 )
    {
      v20 = (struct _FCB *)*((_QWORD *)Instance + 36);
      *((_QWORD *)Instance + 36) = 0;
      _RxReleaseFcb(0, (PMRX_FCB)Instance, v6, v19, (ULONG)BugCheckParameter4);
      if ( v20 )
      {
        _RxAcquireFcb(v20, 0, 1u, 0, BugCheckParameter4a, v26);
        if ( !RxpDereferenceAndFinalizeNetFcb(v20, 0, 0, 0) )
          _RxReleaseFcb(0, (PMRX_FCB)&v20->Header, v6, v22, BugCheckParameter4b);
      }
    }
    else if ( *((_QWORD *)Instance + 36) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return v18;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_qq(
          WPP_GLOBAL_Control->AttachedDevice,
          81,
          &WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids,
          Instance,
          *((_QWORD *)Instance + 36));
    }
  }
  v12 = v15;
LABEL_27:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_ddd(WPP_GLOBAL_Control->AttachedDevice, v18, v6, v4, v12, v18);
  }
  return v18;
}

```

## disassembly

```asm
0x14006a520  push    rbx
0x14006a522  push    r13
0x14006a524  push    r15
0x14006a526  sub     rsp, 40h
0x14006a52a  mov     r15, rdx
0x14006a52d  mov     rbx, rcx
0x14006a530  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a537  lea     r13, WPP_GLOBAL_Control
0x14006a53e  cmp     rcx, r13
0x14006a541  jz      short loc_14006A550
0x14006a543  test    dword ptr [rcx+2Ch], 100h
0x14006a54a  jnz     loc_14006A7B0
0x14006a550  mov     [rsp+58h+arg_10], rdi
0x14006a555  mov     eax, 1
0x14006a55a  lock xadd [rbx+98h], eax
0x14006a562  inc     eax
0x14006a564  cmp     eax, 1
0x14006a567  jz      loc_14006A721
0x14006a56d  mov     rcx, [rbx+8]; Resource
0x14006a571  mov     [rsp+58h+arg_8], rsi
0x14006a576  mov     [rsp+58h+var_20], r12
0x14006a57b  mov     r12b, 1
0x14006a57e  mov     [rsp+58h+var_28], r14
0x14006a583  xor     r14b, r14b
0x14006a586  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x14006a58d  nop     dword ptr [rax+rax+00h]
0x14006a592  test    al, al
0x14006a594  jnz     short loc_14006A5B2
0x14006a596  xor     r9d, r9d; LineNumber
0x14006a599  mov     rdx, 0FFFFFFFFFFFFFFFEh; RxContext
0x14006a5a0  mov     r8d, 1; Mode
0x14006a5a6  mov     rcx, rbx; Fcb
0x14006a5a9  call    __RxAcquireFcb
0x14006a5ae  movzx   r14d, r12b
0x14006a5b2  mov     eax, [rbx+9Ch]
0x14006a5b8  mov     [rsp+58h+arg_0], rbp
0x14006a5bd  test    al, al
0x14006a5bf  js      loc_14006A7DC
0x14006a5c5  bts     eax, 18h
0x14006a5c9  lea     rsi, [rbx+108h]
0x14006a5d0  mov     [rbx+9Ch], eax
0x14006a5d6  mov     edx, 0EBAAh
0x14006a5db  mov     rax, rsi
0x14006a5de  mov     rax, [rax]
0x14006a5e1  cmp     rax, rsi
0x14006a5e4  jz      short loc_14006A622
0x14006a5e6  lea     rcx, [rax-88h]; SrvCall
0x14006a5ed  cmp     [rcx], dx
0x14006a5f0  jz      short loc_14006A5DE
0x14006a5f2  xor     edi, edi
0x14006a5f4  test    rcx, rcx
0x14006a5f7  jz      loc_14006A6B2
0x14006a5fd  lea     rax, [rcx+88h]
0x14006a604  mov     rax, [rax]
0x14006a607  cmp     rax, rsi
0x14006a60a  jz      loc_14006A782
0x14006a610  lea     rbp, [rax-88h]
0x14006a617  cmp     [rbp+0], dx
0x14006a61b  jz      short loc_14006A604
0x14006a61d  jmp     loc_14006A785
0x14006a622  and     dword ptr [rbx+9Ch], 0FEFFFFFFh
0x14006a62c  xor     edi, edi
0x14006a62e  mov     ebp, edi
0x14006a630  mov     rcx, rbx; Instance
0x14006a633  call    RxDeregisterFcbWithBufferingManager
0x14006a638  mov     rcx, rbx; ThisFcb
0x14006a63b  call    RxRemoveNameNetFcb
0x14006a640  test    al, al
0x14006a642  jz      short loc_14006A64B
0x14006a644  lock dec dword ptr [rbx+98h]
0x14006a64b  or      dword ptr [rbx+9Ch], 80h
0x14006a655  mov     sil, 1
0x14006a658  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 10h
0x14006a65f  jnz     loc_14006A7E8
0x14006a665  xor     r9d, r9d; ForceFinalize
0x14006a668  mov     qword ptr [rbx+0A0h], 0
0x14006a673  xor     r8d, r8d; RecursiveFinalize
0x14006a676  xor     edx, edx; RxContext
0x14006a678  mov     rcx, rbx; ThisFcb
0x14006a67b  call    RxpDereferenceAndFinalizeNetFcb
0x14006a680  test    al, al
0x14006a682  jnz     short loc_14006A6AE
0x14006a684  test    r14b, r14b
0x14006a687  jz      loc_14007EB0E
0x14006a68d  mov     r14, [rbx+120h]
0x14006a694  mov     rdx, rbx; MrxFcb
0x14006a697  xor     ecx, ecx; RxContext
0x14006a699  mov     [rbx+120h], rdi
0x14006a6a0  call    __RxReleaseFcb
0x14006a6a5  test    r14, r14
0x14006a6a8  jnz     loc_14006A748
0x14006a6ae  mov     edi, ebp
0x14006a6b0  jmp     short loc_14006A6E0
0x14006a6b2  and     dword ptr [rbx+9Ch], 0FEFFFFFFh
0x14006a6bc  mov     ebp, edi
0x14006a6be  test    r12b, r12b
0x14006a6c1  jnz     loc_14006A630
0x14006a6c7  lock dec dword ptr [rbx+98h]
0x14006a6ce  xor     sil, sil
0x14006a6d1  test    r14b, r14b
0x14006a6d4  jz      short loc_14006A6E0
0x14006a6d6  mov     rdx, rbx; MrxFcb
0x14006a6d9  xor     ecx, ecx; RxContext
0x14006a6db  call    __RxReleaseFcb
0x14006a6e0  mov     rcx, cs:WPP_GLOBAL_Control
0x14006a6e7  cmp     rcx, r13
0x14006a6ea  jz      short loc_14006A6F9
0x14006a6ec  test    dword ptr [rcx+2Ch], 100h
0x14006a6f3  jnz     loc_14006A809
0x14006a6f9  mov     r14, [rsp+58h+var_28]
0x14006a6fe  movzx   eax, sil
0x14006a702  mov     rsi, [rsp+58h+arg_8]
0x14006a707  mov     r12, [rsp+58h+var_20]
0x14006a70c  mov     rbp, [rsp+58h+arg_0]
0x14006a711  mov     rdi, [rsp+58h+arg_10]
0x14006a716  add     rsp, 40h
0x14006a71a  pop     r15
0x14006a71c  pop     r13
0x14006a71e  pop     rbx
0x14006a71f  retn
0x14006a721  xor     edi, edi
0x14006a723  mov     r9d, 1; BugCheckParameter3
0x14006a729  mov     r8, rbx; BugCheckParameter2
0x14006a72c  mov     [rsp+58h+BugCheckParameter4], rdi; BugCheckParameter4
0x14006a731  mov     edx, 0FCB003A5h; BugCheckParameter1
0x14006a736  mov     ecx, 27h ; '''; BugCheckCode
0x14006a73b  call    cs:__imp_KeBugCheckEx
0x14006a748  xor     r9d, r9d; LineNumber
0x14006a74b  xor     edx, edx; RxContext
0x14006a74d  mov     r8d, 1; Mode
0x14006a753  mov     rcx, r14; Fcb
0x14006a756  call    __RxAcquireFcb
0x14006a75b  xor     r9d, r9d; ForceFinalize
0x14006a75e  xor     r8d, r8d; RecursiveFinalize
0x14006a761  xor     edx, edx; RxContext
0x14006a763  mov     rcx, r14; ThisFcb
0x14006a766  call    RxpDereferenceAndFinalizeNetFcb
0x14006a76b  test    al, al
0x14006a76d  jnz     loc_14006A6AE
0x14006a773  mov     rdx, r14; MrxFcb
0x14006a776  xor     ecx, ecx; RxContext
0x14006a778  call    __RxReleaseFcb
0x14006a77d  jmp     loc_14006A6AE
0x14006a782  mov     rbp, rdi
0x14006a785  test    r15, r15
0x14006a788  jz      short loc_14006A7A4
0x14006a78a  cmp     [rcx+28h], r15
0x14006a78e  jz      short loc_14006A7A4
0x14006a790  xor     r12b, r12b
0x14006a793  mov     rcx, rbp
0x14006a796  test    rbp, rbp
0x14006a799  jnz     loc_14006A5FD
0x14006a79f  jmp     loc_14006A6B2
0x14006a7a4  call    RxOrphanSrvOpen
0x14006a7a9  mov     edx, 0EBAAh
0x14006a7ae  jmp     short loc_14006A793
0x14006a7b0  cmp     byte ptr [rcx+29h], 2
0x14006a7b4  jb      loc_14006A550
0x14006a7ba  mov     rcx, [rcx+18h]
0x14006a7be  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x14006a7c5  mov     edx, 50h ; 'P'
0x14006a7ca  mov     [rsp+58h+BugCheckParameter4], r15
0x14006a7cf  mov     r9, rbx
0x14006a7d2  call    WPP_SF_qq
0x14006a7d7  jmp     loc_14006A550
0x14006a7dc  mov     ebp, 1
0x14006a7e1  xor     edi, edi
0x14006a7e3  jmp     loc_14006A630
0x14006a7e8  mov     [rsp+58h+var_30], rdi
0x14006a7ed  lea     rdx, RxOrphaning
0x14006a7f4  mov     r9, rbx
0x14006a7f7  mov     [rsp+58h+BugCheckParameter4], rdi
0x14006a7fc  xor     r8d, r8d
0x14006a7ff  call    McTemplateK0ppp_EtwWriteTransfer
0x14006a804  jmp     loc_14006A665
0x14006a809  cmp     byte ptr [rcx+29h], 2
0x14006a80d  jb      loc_14006A6F9
0x14006a813  mov     rcx, [rcx+18h]
0x14006a817  movzx   edx, sil
0x14006a81b  mov     dword ptr [rsp+58h+var_30], edx
0x14006a81f  movzx   r9d, r12b
0x14006a823  mov     dword ptr [rsp+58h+BugCheckParameter4], edi
0x14006a827  call    WPP_SF_ddd
0x14006a82c  jmp     loc_14006A6F9
0x14007eb0e  mov     r9, [rbx+120h]
0x14007eb15  test    r9, r9
0x14007eb18  jz      loc_14006A6AE
0x14007eb1e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007eb25  cmp     rcx, r13
0x14007eb28  jz      loc_14006A6F9
0x14007eb2e  test    dword ptr [rcx+2Ch], 100h
0x14007eb35  jz      loc_14006A6AE
0x14007eb3b  cmp     byte ptr [rcx+29h], 2
0x14007eb3f  jb      loc_14006A6AE
0x14007eb45  mov     rcx, [rcx+18h]
0x14007eb49  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x14007eb50  mov     [rsp+58h+BugCheckParameter4], r9
0x14007eb55  mov     edx, 51h ; 'Q'
0x14007eb5a  mov     r9, rbx
0x14007eb5d  call    WPP_SF_qq
0x14007eb62  nop
0x14007eb63  jmp     loc_14006A6AE
```
