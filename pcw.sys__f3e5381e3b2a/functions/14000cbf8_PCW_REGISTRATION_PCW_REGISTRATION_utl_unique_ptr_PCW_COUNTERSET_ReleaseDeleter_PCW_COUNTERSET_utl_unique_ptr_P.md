# _PCW_REGISTRATION::_PCW_REGISTRATION(utl::unique_ptr<PCW_COUNTERSET,ReleaseDeleter<PCW_COUNTERSET>> &&,utl::unique_ptr<PCW_SILO_NEUTRAL_COUNTERSET,ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>> &&,ulong,_PCW_COUNTER_DESCRIPTOR const *,unsigned __int64,ulong,long (*)(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *,void *),void *)

- ea: `0x14000cbf8`
- end: `0x14000cdd5`
- name: `??0_PCW_REGISTRATION@@AEAA@$$QEAV?$unique_ptr@VPCW_COUNTERSET@@U?$ReleaseDeleter@VPCW_COUNTERSET@@@@@utl@@$$QEAV?$unique_ptr@VPCW_SILO_NEUTRAL_COUNTERSET@@U?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@@2@KPEBU_PCW_COUNTER_DESCRIPTOR@@_KKP6AJW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@PEAX@Z6@Z`
- size: `477`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000d2e0`

## callees

- `0x140001450`
- `0x14000cbf8`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000ccdb`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000ccdb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cc78`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ccc6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cc78`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ccc6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cd9d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cdba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cd9d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cdba`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000cd91`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000cd91`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000cc8d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000cc8d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000cdae`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000cdae`

## pseudocode

```c
__int64 __fastcall _PCW_REGISTRATION::_PCW_REGISTRATION(
        __int64 a1,
        __int64 *a2,
        __int64 *a3,
        int a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 v12; // rsi
  __int64 v13; // r14
  _QWORD *v14; // rcx
  __int64 v15; // rbp
  __int64 v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rdi
  __int64 v19; // r8
  void (__fastcall *v20)(_QWORD, __int64 *, __int64); // rax
  _QWORD *v21; // rsi
  _QWORD *i; // rdi
  __int64 v23; // r8
  void (__fastcall *v24)(_QWORD, __int64 *, __int64); // rax
  __int64 v26; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v27; // [rsp+28h] [rbp-50h]
  __int128 v28; // [rsp+30h] [rbp-48h]
  __int64 v29; // [rsp+40h] [rbp-38h]

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = a6;
  *(_DWORD *)(a1 + 28) = a7;
  *(_DWORD *)(a1 + 24) = a4;
  v10 = *a2;
  *a2 = 0;
  *(_QWORD *)(a1 + 32) = v10;
  v11 = *a3;
  *a3 = 0;
  *(_QWORD *)(a1 + 40) = v11;
  v12 = *(_QWORD *)(a1 + 32);
  *(_QWORD *)(a1 + 48) = a8;
  *(_QWORD *)(a1 + 56) = a9;
  *(_QWORD *)(a1 + 64) = a5;
  if ( v12 )
    v11 = *(_QWORD *)(v12 + 80);
  else
    v12 = v11;
  KeEnterCriticalRegion();
  v13 = v11 + 80;
  ExAcquirePushLockExclusiveEx(v11 + 80, 0);
  v14 = *(_QWORD **)(v12 + 48);
  if ( *v14 != v12 + 40 )
    __fastfail(3u);
  *(_QWORD *)a1 = v12 + 40;
  *(_QWORD *)(a1 + 8) = v14;
  *v14 = a1;
  *(_QWORD *)(v12 + 48) = a1;
  if ( *(_QWORD *)(a1 + 48) )
  {
    KeEnterCriticalRegion();
    v15 = v11 + 104;
    ExAcquirePushLockSharedEx(v11 + 104, 0);
    v16 = *(_QWORD *)(a1 + 32);
    if ( v16 )
    {
      v17 = (_QWORD *)(v16 + 88);
      v18 = (_QWORD *)*v17;
      while ( v18 != v17 )
      {
        v19 = *(_QWORD *)(a1 + 56);
        v26 = v18[2];
        v29 = 0;
        v27 = v18 + 7;
        v20 = *(void (__fastcall **)(_QWORD, __int64 *, __int64))(a1 + 48);
        v28 = 0;
        v20(0, &v26, v19);
        v18 = (_QWORD *)*v18;
        v17 = (_QWORD *)(*(_QWORD *)(a1 + 32) + 88LL);
      }
    }
    else
    {
      v21 = (_QWORD *)(v11 + 112);
      for ( i = *(_QWORD **)(v11 + 112); i != v21; i = (_QWORD *)*i )
      {
        v23 = *(_QWORD *)(a1 + 56);
        v26 = i[4];
        v29 = 0;
        v27 = i + 9;
        v24 = *(void (__fastcall **)(_QWORD, __int64 *, __int64))(a1 + 48);
        v28 = 0;
        v24(0, &v26, v23);
      }
    }
    ExReleasePushLockSharedEx(v15, 0);
    KeLeaveCriticalRegion();
  }
  ExReleasePushLockExclusiveEx(v13, 0);
  KeLeaveCriticalRegion();
  return a1;
}

```

## disassembly

```asm
0x14000cbf8  push    rbx
0x14000cbfa  push    rbp
0x14000cbfb  push    rsi
0x14000cbfc  push    rdi
0x14000cbfd  push    r14
0x14000cbff  sub     rsp, 50h
0x14000cc03  mov     rax, [rsp+78h+arg_28]
0x14000cc0b  xorps   xmm0, xmm0
0x14000cc0e  movups  xmmword ptr [rcx], xmm0
0x14000cc11  mov     [rcx+10h], rax
0x14000cc15  mov     rbx, rcx
0x14000cc18  mov     eax, [rsp+78h+arg_30]
0x14000cc1f  mov     [rcx+1Ch], eax
0x14000cc22  mov     [rcx+18h], r9d
0x14000cc26  mov     rax, [rdx]
0x14000cc29  mov     qword ptr [rdx], 0
0x14000cc30  mov     [rcx+20h], rax
0x14000cc34  mov     rdi, [r8]
0x14000cc37  mov     rax, [rsp+78h+arg_38]
0x14000cc3f  mov     qword ptr [r8], 0
0x14000cc46  mov     [rcx+28h], rdi
0x14000cc4a  mov     rsi, [rcx+20h]
0x14000cc4e  mov     [rcx+30h], rax
0x14000cc52  mov     rax, [rsp+78h+arg_40]
0x14000cc5a  mov     [rcx+38h], rax
0x14000cc5e  mov     rax, [rsp+78h+arg_20]
0x14000cc66  mov     [rcx+40h], rax
0x14000cc6a  test    rsi, rsi
0x14000cc6d  jz      short loc_14000CC75
0x14000cc6f  mov     rdi, [rsi+50h]
0x14000cc73  jmp     short loc_14000CC78
0x14000cc75  mov     rsi, rdi
0x14000cc78  call    cs:__imp_KeEnterCriticalRegion
0x14000cc7f  nop     dword ptr [rax+rax+00h]
0x14000cc84  lea     r14, [rdi+50h]
0x14000cc88  xor     edx, edx
0x14000cc8a  mov     rcx, r14
0x14000cc8d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000cc94  nop     dword ptr [rax+rax+00h]
0x14000cc99  lea     rax, [rsi+28h]
0x14000cc9d  mov     rcx, [rax+8]
0x14000cca1  cmp     [rcx], rax
0x14000cca4  jz      short loc_14000CCAD
0x14000cca6  mov     ecx, 3
0x14000ccab  int     29h; Win8: RtlFailFast(ecx)
0x14000ccad  mov     [rbx], rax
0x14000ccb0  mov     [rbx+8], rcx
0x14000ccb4  mov     [rcx], rbx
0x14000ccb7  mov     [rax+8], rbx
0x14000ccbb  cmp     qword ptr [rbx+30h], 0
0x14000ccc0  jz      loc_14000CDA9
0x14000ccc6  call    cs:__imp_KeEnterCriticalRegion
0x14000cccd  nop     dword ptr [rax+rax+00h]
0x14000ccd2  lea     rbp, [rdi+68h]
0x14000ccd6  xor     edx, edx
0x14000ccd8  mov     rcx, rbp
0x14000ccdb  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000cce2  nop     dword ptr [rax+rax+00h]
0x14000cce7  mov     rax, [rbx+20h]
0x14000cceb  test    rax, rax
0x14000ccee  jz      short loc_14000CD43
0x14000ccf0  add     rax, 58h ; 'X'
0x14000ccf4  mov     rdi, [rax]
0x14000ccf7  jmp     short loc_14000CD3C
0x14000ccf9  mov     rax, [rdi+10h]
0x14000ccfd  lea     rdx, [rsp+78h+var_58]
0x14000cd02  mov     r8, [rbx+38h]
0x14000cd06  xorps   xmm0, xmm0
0x14000cd09  mov     [rsp+78h+var_58], rax
0x14000cd0e  xor     ecx, ecx
0x14000cd10  lea     rax, [rdi+38h]
0x14000cd14  mov     [rsp+78h+var_38], 0
0x14000cd1d  mov     [rsp+78h+var_50], rax
0x14000cd22  mov     rax, [rbx+30h]
0x14000cd26  movdqu  [rsp+78h+var_48], xmm0
0x14000cd2c  call    _guard_dispatch_icall
0x14000cd31  mov     rax, [rbx+20h]
0x14000cd35  mov     rdi, [rdi]
0x14000cd38  add     rax, 58h ; 'X'
0x14000cd3c  cmp     rdi, rax
0x14000cd3f  jnz     short loc_14000CCF9
0x14000cd41  jmp     short loc_14000CD8C
0x14000cd43  lea     rsi, [rdi+70h]
0x14000cd47  mov     rdi, [rsi]
0x14000cd4a  jmp     short loc_14000CD87
0x14000cd4c  mov     rax, [rdi+20h]
0x14000cd50  lea     rdx, [rsp+78h+var_58]
0x14000cd55  mov     r8, [rbx+38h]
0x14000cd59  xorps   xmm0, xmm0
0x14000cd5c  mov     [rsp+78h+var_58], rax
0x14000cd61  xor     ecx, ecx
0x14000cd63  lea     rax, [rdi+48h]
0x14000cd67  mov     [rsp+78h+var_38], 0
0x14000cd70  mov     [rsp+78h+var_50], rax
0x14000cd75  mov     rax, [rbx+30h]
0x14000cd79  movdqu  [rsp+78h+var_48], xmm0
0x14000cd7f  call    _guard_dispatch_icall
0x14000cd84  mov     rdi, [rdi]
0x14000cd87  cmp     rdi, rsi
0x14000cd8a  jnz     short loc_14000CD4C
0x14000cd8c  xor     edx, edx
0x14000cd8e  mov     rcx, rbp
0x14000cd91  call    cs:__imp_ExReleasePushLockSharedEx
0x14000cd98  nop     dword ptr [rax+rax+00h]
0x14000cd9d  call    cs:__imp_KeLeaveCriticalRegion
0x14000cda4  nop     dword ptr [rax+rax+00h]
0x14000cda9  xor     edx, edx
0x14000cdab  mov     rcx, r14
0x14000cdae  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000cdb5  nop     dword ptr [rax+rax+00h]
0x14000cdba  call    cs:__imp_KeLeaveCriticalRegion
0x14000cdc1  nop     dword ptr [rax+rax+00h]
0x14000cdc6  mov     rax, rbx
0x14000cdc9  add     rsp, 50h
0x14000cdcd  pop     r14
0x14000cdcf  pop     rdi
0x14000cdd0  pop     rsi
0x14000cdd1  pop     rbp
0x14000cdd2  pop     rbx
0x14000cdd3  retn
```
