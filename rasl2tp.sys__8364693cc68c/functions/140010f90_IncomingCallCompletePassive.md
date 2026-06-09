# IncomingCallCompletePassive

- ea: `0x140010f90`
- end: `0x140011055`
- name: `IncomingCallCompletePassive`
- size: `197`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1400013f0`
- `0x140003230`
- `0x140010f90`
- `0x140011f9c`
- `0x14001b830`
- `0x14001c860`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140010fb6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140010fb6`

## pseudocode

```c
__int64 __fastcall IncomingCallCompletePassive(PVOID Entry, __int64 a2, __int64 a3, int *a4)
{
  int v4; // edi
  __int64 v7; // rcx
  __int64 v8; // r8

  v4 = *a4;
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(a3 + 24) + 960LL), Entry);
  if ( (*(_DWORD *)(a3 + 60) & 0x100000) != 0 )
  {
    ClearFlags(a3 + 60, 0x100000);
    if ( v4 )
    {
      *(_DWORD *)(a3 + 200) = 8;
      ClearFlags(v7, 1024);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 32, v8, a3, v4);
      }
    }
    SetupVcComplete(a2, a3);
  }
  else
  {
    ++g_ulUnexpectedInCallCompletes;
  }
  DereferenceCall(a3);
  return DereferenceVc(a3);
}

```

## disassembly

```asm
0x140010f90  mov     [rsp+arg_0], rbx
0x140010f95  mov     [rsp+arg_8], rsi
0x140010f9a  push    rdi
0x140010f9b  sub     rsp, 30h
0x140010f9f  mov     edi, [r9]
0x140010fa2  mov     rsi, rdx
0x140010fa5  mov     rdx, rcx; Entry
0x140010fa8  mov     rbx, r8
0x140010fab  mov     rcx, [r8+18h]
0x140010faf  add     rcx, 3C0h; Lookaside
0x140010fb6  call    cs:__imp_ExFreeToNPagedLookasideList
0x140010fbd  nop     dword ptr [rax+rax+00h]
0x140010fc2  lea     rcx, [rbx+3Ch]
0x140010fc6  mov     edx, 100000h
0x140010fcb  test    [rcx], edx
0x140010fcd  jz      short loc_14001102E
0x140010fcf  call    ClearFlags
0x140010fd4  test    edi, edi
0x140010fd6  jz      short loc_140011021
0x140010fd8  mov     edx, 400h
0x140010fdd  mov     dword ptr [rbx+0C8h], 8
0x140010fe7  call    ClearFlags
0x140010fec  mov     rcx, cs:WPP_GLOBAL_Control
0x140010ff3  lea     rax, WPP_GLOBAL_Control
0x140010ffa  cmp     rcx, rax
0x140010ffd  jz      short loc_140011021
0x140010fff  mov     eax, [rcx+2Ch]
0x140011002  test    al, 4
0x140011004  jz      short loc_140011021
0x140011006  cmp     byte ptr [rcx+29h], 1
0x14001100a  jb      short loc_140011021
0x14001100c  mov     rcx, [rcx+18h]
0x140011010  mov     edx, 20h ; ' '
0x140011015  mov     r9, rbx
0x140011018  mov     [rsp+38h+var_18], edi
0x14001101c  call    WPP_SF_qD
0x140011021  mov     rdx, rbx
0x140011024  mov     rcx, rsi
0x140011027  call    SetupVcComplete
0x14001102c  jmp     short loc_140011034
0x14001102e  inc     cs:g_ulUnexpectedInCallCompletes
0x140011034  mov     rcx, rbx
0x140011037  call    DereferenceCall
0x14001103c  mov     rcx, rbx
0x14001103f  call    DereferenceVc
0x140011044  mov     rbx, [rsp+38h+arg_0]
0x140011049  mov     rsi, [rsp+38h+arg_8]
0x14001104e  add     rsp, 30h
0x140011052  pop     rdi
0x140011053  retn
```
