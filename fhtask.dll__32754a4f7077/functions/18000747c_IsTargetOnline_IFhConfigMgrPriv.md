# IsTargetOnline(IFhConfigMgrPriv *)

- ea: `0x18000747c`
- end: `0x1800075be`
- name: `?IsTargetOnline@@YA_NPEAUIFhConfigMgrPriv@@@Z`
- size: `322`
- prototype: `char __fastcall(struct IFhConfigMgrPriv *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007ba0`

## callees

- `0x1800067a0`
- `0x18000747c`
- `0x18000b010`

## pseudocode

```c
char __fastcall IsTargetOnline(struct IFhConfigMgrPriv *a1)
{
  int v1; // eax
  int v2; // ebx
  char v3; // di
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  int v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF
  __int64 v9; // [rsp+40h] [rbp+18h] BYREF

  v7 = 0;
  v9 = 0;
  v8 = 0;
  v1 = (*(__int64 (__fastcall **)(struct IFhConfigMgrPriv *, __int64 *))(*(_QWORD *)a1 + 96LL))(a1, &v9);
  v2 = v1;
  v3 = 1;
  if ( v1 >= 0 )
  {
    v1 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v9)(
           v9,
           &GUID_16d085cc_5bf2_11e0_8680_18a90531a85a,
           &v8);
    v2 = v1;
    if ( v1 >= 0 )
    {
      v1 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v8 + 56LL))(v8, &v7);
      v2 = v1;
      if ( v1 < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v5 = 22;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 21;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 20;
LABEL_13:
      WPP_SF_d(v4[2], v5, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids, (unsigned int)v1);
    }
  }
  if ( v2 != -2147220719 && !v7 )
    v3 = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return v3;
}

```

## disassembly

```asm
0x18000747c  mov     rax, rsp
0x18000747f  mov     [rax+20h], rbx
0x180007483  push    rdi
0x180007484  sub     rsp, 20h
0x180007488  mov     dword ptr [rax+8], 0
0x18000748f  mov     qword ptr [rax+18h], 0
0x180007497  mov     qword ptr [rax+10h], 0
0x18000749f  mov     rax, [rcx]
0x1800074a2  lea     rdx, [rsp+28h+arg_10]
0x1800074a7  mov     rax, [rax+60h]
0x1800074ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074b0  mov     ebx, eax
0x1800074b2  mov     dil, 1
0x1800074b5  test    eax, eax
0x1800074b7  jns     short loc_1800074E1
0x1800074b9  lea     rdx, WPP_GLOBAL_Control
0x1800074c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074c7  cmp     rcx, rdx
0x1800074ca  jz      loc_180007570
0x1800074d0  test    [rcx+1Ch], dil
0x1800074d4  jz      loc_180007570
0x1800074da  mov     edx, 14h
0x1800074df  jmp     short loc_18000755D
0x1800074e1  mov     rcx, [rsp+28h+arg_10]
0x1800074e6  mov     rax, [rcx]
0x1800074e9  lea     r8, [rsp+28h+arg_8]
0x1800074ee  lea     rdx, _GUID_16d085cc_5bf2_11e0_8680_18a90531a85a
0x1800074f5  mov     rax, [rax]
0x1800074f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074fd  mov     ebx, eax
0x1800074ff  test    eax, eax
0x180007501  jns     short loc_180007523
0x180007503  lea     rdx, WPP_GLOBAL_Control
0x18000750a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007511  cmp     rcx, rdx
0x180007514  jz      short loc_180007570
0x180007516  test    [rcx+1Ch], dil
0x18000751a  jz      short loc_180007570
0x18000751c  mov     edx, 15h
0x180007521  jmp     short loc_18000755D
0x180007523  mov     rcx, [rsp+28h+arg_8]
0x180007528  mov     rax, [rcx]
0x18000752b  lea     rdx, [rsp+28h+arg_0]
0x180007530  mov     rax, [rax+38h]
0x180007534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007539  mov     ebx, eax
0x18000753b  test    eax, eax
0x18000753d  jns     short loc_180007570
0x18000753f  lea     rdx, WPP_GLOBAL_Control
0x180007546  mov     rcx, cs:WPP_GLOBAL_Control
0x18000754d  cmp     rcx, rdx
0x180007550  jz      short loc_180007570
0x180007552  test    [rcx+1Ch], dil
0x180007556  jz      short loc_180007570
0x180007558  mov     edx, 16h
0x18000755d  mov     r9d, eax
0x180007560  lea     r8, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids
0x180007567  mov     rcx, [rcx+10h]
0x18000756b  call    WPP_SF_d
0x180007570  cmp     ebx, 80040311h
0x180007576  jz      short loc_180007582
0x180007578  cmp     [rsp+28h+arg_0], 0
0x18000757d  jnz     short loc_180007582
0x18000757f  xor     dil, dil
0x180007582  mov     rcx, [rsp+28h+arg_8]
0x180007587  test    rcx, rcx
0x18000758a  jz      short loc_180007599
0x18000758c  mov     rax, [rcx]
0x18000758f  mov     rax, [rax+10h]
0x180007593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007598  nop
0x180007599  mov     rcx, [rsp+28h+arg_10]
0x18000759e  test    rcx, rcx
0x1800075a1  jz      short loc_1800075B0
0x1800075a3  mov     rdx, [rcx]
0x1800075a6  mov     rax, [rdx+10h]
0x1800075aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075af  nop
0x1800075b0  mov     al, dil
0x1800075b3  mov     rbx, [rsp+28h+arg_18]
0x1800075b8  add     rsp, 20h
0x1800075bc  pop     rdi
0x1800075bd  retn
```
