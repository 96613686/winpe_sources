# _PCW_REGISTRATION::Create(_PCW_REGISTRATION * *,_UNICODE_STRING const *,ulong,_PCW_COUNTER_DESCRIPTOR *,long (*)(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *,void *),void *,PCW_REGISTRATION_FLAGS)

- ea: `0x14000d2e0`
- end: `0x14000d459`
- name: `?Create@_PCW_REGISTRATION@@SAJPEAPEAU1@PEBU_UNICODE_STRING@@KPEAU_PCW_COUNTER_DESCRIPTOR@@P6AJW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@PEAX@Z5W4PCW_REGISTRATION_FLAGS@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(__int64 *, __int64, unsigned int, __int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000dc00`

## callees

- `0x140008140`
- `0x14000cbf8`
- `0x14000cf6c`
- `0x14000d2e0`
- `0x14000d460`
- `0x14000ed84`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000d37a`
- `ntoskrnl!ExAllocatePool2` at `0x14000d37a`

## pseudocode

```c
__int64 __fastcall _PCW_REGISTRATION::Create(
        __int64 *a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char a7)
{
  __int64 v11; // rbx
  __int64 v12; // rdi
  int v13; // eax
  __int64 v14; // rcx
  unsigned int v15; // ebp
  __int64 Pool2; // rax
  __int64 v17; // rcx
  int v18; // r10d
  __int64 v19; // r8
  __int64 v20; // r11
  unsigned int v21; // edx
  __int64 i; // r9
  unsigned int v23; // ecx
  unsigned int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // [rsp+50h] [rbp-48h] BYREF
  _QWORD v28[8]; // [rsp+58h] [rbp-40h] BYREF

  if ( a3 > 0x1FFFFFF6 )
    return 3221225621LL;
  v11 = 0;
  v12 = 0;
  v28[0] = 0;
  v27 = 0;
  if ( (a7 & 1) != 0 )
  {
    v13 = PCW_SILO_NEUTRAL_COUNTERSET::FindOrCreate(v28);
    v11 = v28[0];
  }
  else
  {
    v13 = PCW_COUNTERSET::FindOrCreate(&v27);
    v12 = v27;
  }
  v15 = v13;
  if ( v13 >= 0 )
  {
    Pool2 = ExAllocatePool2(256, 8 * a3 + 72, 1383555920);
    v18 = Pool2;
    if ( Pool2 )
    {
      v19 = 0;
      v20 = Pool2 + 72;
      v21 = 0;
      for ( i = 0; (unsigned int)i < a3; v21 = v24 )
      {
        *(_QWORD *)(v20 + 8 * i) = *(_QWORD *)(a4 + 8 * i);
        v23 = *(unsigned __int16 *)(a4 + 8 * i + 2);
        v19 |= 1LL << *(_WORD *)(a4 + 8 * i);
        v24 = v23 + 1;
        if ( v23 < v21 )
          v24 = v21;
        i = (unsigned int)(i + 1);
      }
      v25 = _PCW_REGISTRATION::_PCW_REGISTRATION(v18, (unsigned int)&v27, (unsigned int)v28, a3, v20, v19, v21, a5, a6);
      v26 = v27;
      *a1 = v25;
      if ( v26 )
        ((void (*)(void))ReleaseDeleter<PCW_COUNTERSET>::operator())();
      if ( v28[0] )
        ((void (*)(void))ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator())();
      return 0;
    }
    else
    {
      if ( v12 )
        ReleaseDeleter<PCW_COUNTERSET>::operator()(v17, v12);
      if ( v11 )
        ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(v17, v11);
      return 3221225495LL;
    }
  }
  else
  {
    if ( v12 )
      ReleaseDeleter<PCW_COUNTERSET>::operator()(v14, v12);
    if ( v11 )
      ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(v14, v11);
    return v15;
  }
}

```

## disassembly

```asm
0x14000d2e0  push    rbx
0x14000d2e2  push    rbp
0x14000d2e3  push    rsi
0x14000d2e4  push    rdi
0x14000d2e5  push    r14
0x14000d2e7  push    r15
0x14000d2e9  sub     rsp, 68h
0x14000d2ed  mov     r14, r9
0x14000d2f0  mov     esi, r8d
0x14000d2f3  mov     r15, rcx
0x14000d2f6  cmp     r8d, 1FFFFFF6h
0x14000d2fd  jbe     short loc_14000D309
0x14000d2ff  mov     eax, 0C0000095h
0x14000d304  jmp     loc_14000D44B
0x14000d309  xor     ebx, ebx
0x14000d30b  xor     edi, edi
0x14000d30d  test    [rsp+98h+arg_30], 1
0x14000d315  mov     [rsp+98h+var_40], rbx
0x14000d31a  mov     [rsp+98h+var_48], rdi
0x14000d31f  jz      short loc_14000D332
0x14000d321  lea     rcx, [rsp+98h+var_40]
0x14000d326  call    ?FindOrCreate@PCW_SILO_NEUTRAL_COUNTERSET@@SAJPEAV?$unique_ptr@VPCW_SILO_NEUTRAL_COUNTERSET@@U?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@@utl@@PEBU_UNICODE_STRING@@@Z; PCW_SILO_NEUTRAL_COUNTERSET::FindOrCreate(utl::unique_ptr<PCW_SILO_NEUTRAL_COUNTERSET,ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>> *,_UNICODE_STRING const *)
0x14000d32b  mov     rbx, [rsp+98h+var_40]
0x14000d330  jmp     short loc_14000D341
0x14000d332  lea     rcx, [rsp+98h+var_48]
0x14000d337  call    ?FindOrCreate@PCW_COUNTERSET@@SAJPEAV?$unique_ptr@VPCW_COUNTERSET@@U?$ReleaseDeleter@VPCW_COUNTERSET@@@@@utl@@PEBU_UNICODE_STRING@@@Z; PCW_COUNTERSET::FindOrCreate(utl::unique_ptr<PCW_COUNTERSET,ReleaseDeleter<PCW_COUNTERSET>> *,_UNICODE_STRING const *)
0x14000d33c  mov     rdi, [rsp+98h+var_48]
0x14000d341  mov     ebp, eax
0x14000d343  test    eax, eax
0x14000d345  jns     short loc_14000D368
0x14000d347  test    rdi, rdi
0x14000d34a  jz      short loc_14000D354
0x14000d34c  mov     rdx, rdi
0x14000d34f  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x14000d354  test    rbx, rbx
0x14000d357  jz      short loc_14000D361
0x14000d359  mov     rdx, rbx
0x14000d35c  call    ??R?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@QEBAXPEAVPCW_SILO_NEUTRAL_COUNTERSET@@@Z; ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(PCW_SILO_NEUTRAL_COUNTERSET *)
0x14000d361  mov     eax, ebp
0x14000d363  jmp     loc_14000D44B
0x14000d368  lea     edx, ds:48h[rsi*8]
0x14000d36f  mov     ecx, 100h
0x14000d374  mov     r8d, 52776350h
0x14000d37a  call    cs:__imp_ExAllocatePool2
0x14000d381  nop     dword ptr [rax+rax+00h]
0x14000d386  mov     r10, rax
0x14000d389  test    rax, rax
0x14000d38c  jnz     short loc_14000D3B2
0x14000d38e  test    rdi, rdi
0x14000d391  jz      short loc_14000D39B
0x14000d393  mov     rdx, rdi
0x14000d396  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x14000d39b  test    rbx, rbx
0x14000d39e  jz      short loc_14000D3A8
0x14000d3a0  mov     rdx, rbx
0x14000d3a3  call    ??R?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@QEBAXPEAVPCW_SILO_NEUTRAL_COUNTERSET@@@Z; ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(PCW_SILO_NEUTRAL_COUNTERSET *)
0x14000d3a8  mov     eax, 0C0000017h
0x14000d3ad  jmp     loc_14000D44B
0x14000d3b2  xor     r8d, r8d
0x14000d3b5  lea     r11, [rax+48h]
0x14000d3b9  xor     edx, edx
0x14000d3bb  xor     r9d, r9d
0x14000d3be  test    esi, esi
0x14000d3c0  jz      short loc_14000D3EB
0x14000d3c2  mov     rax, [r14+r9*8]
0x14000d3c6  mov     [r11+r9*8], rax
0x14000d3ca  movzx   eax, word ptr [r14+r9*8]
0x14000d3cf  movzx   ecx, word ptr [r14+r9*8+2]
0x14000d3d5  bts     r8, rax
0x14000d3d9  cmp     ecx, edx
0x14000d3db  lea     eax, [rcx+1]
0x14000d3de  cmovb   eax, edx
0x14000d3e1  inc     r9d
0x14000d3e4  mov     edx, eax
0x14000d3e6  cmp     r9d, esi
0x14000d3e9  jb      short loc_14000D3C2
0x14000d3eb  mov     rax, [rsp+98h+arg_28]
0x14000d3f3  mov     r9d, esi
0x14000d3f6  mov     [rsp+98h+var_58], rax
0x14000d3fb  mov     rcx, r10
0x14000d3fe  mov     rax, [rsp+98h+arg_20]
0x14000d406  mov     [rsp+98h+var_60], rax
0x14000d40b  mov     [rsp+98h+var_68], edx
0x14000d40f  lea     rdx, [rsp+98h+var_48]
0x14000d414  mov     [rsp+98h+var_70], r8
0x14000d419  lea     r8, [rsp+98h+var_40]
0x14000d41e  mov     [rsp+98h+var_78], r11
0x14000d423  call    ??0_PCW_REGISTRATION@@AEAA@$$QEAV?$unique_ptr@VPCW_COUNTERSET@@U?$ReleaseDeleter@VPCW_COUNTERSET@@@@@utl@@$$QEAV?$unique_ptr@VPCW_SILO_NEUTRAL_COUNTERSET@@U?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@@2@KPEBU_PCW_COUNTER_DESCRIPTOR@@_KKP6AJW4_PCW_CALLBACK_TYPE@@PEAT_PCW_CALLBACK_INFORMATION@@PEAX@Z6@Z; _PCW_REGISTRATION::_PCW_REGISTRATION(utl::unique_ptr<PCW_COUNTERSET,ReleaseDeleter<PCW_COUNTERSET>> &&,utl::unique_ptr<PCW_SILO_NEUTRAL_COUNTERSET,ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>> &&,ulong,_PCW_COUNTER_DESCRIPTOR const *,unsigned __int64,ulong,long (*)(_PCW_CALLBACK_TYPE,_PCW_CALLBACK_INFORMATION *,void *),void *)
0x14000d428  mov     rdx, [rsp+98h+var_48]
0x14000d42d  mov     [r15], rax
0x14000d430  test    rdx, rdx
0x14000d433  jz      short loc_14000D43A
0x14000d435  call    ??R?$ReleaseDeleter@VPCW_COUNTERSET@@@@QEBAXPEAVPCW_COUNTERSET@@@Z; ReleaseDeleter<PCW_COUNTERSET>::operator()(PCW_COUNTERSET *)
0x14000d43a  mov     rdx, [rsp+98h+var_40]
0x14000d43f  test    rdx, rdx
0x14000d442  jz      short loc_14000D449
0x14000d444  call    ??R?$ReleaseDeleter@VPCW_SILO_NEUTRAL_COUNTERSET@@@@QEBAXPEAVPCW_SILO_NEUTRAL_COUNTERSET@@@Z; ReleaseDeleter<PCW_SILO_NEUTRAL_COUNTERSET>::operator()(PCW_SILO_NEUTRAL_COUNTERSET *)
0x14000d449  xor     eax, eax
0x14000d44b  add     rsp, 68h
0x14000d44f  pop     r15
0x14000d451  pop     r14
0x14000d453  pop     rdi
0x14000d454  pop     rsi
0x14000d455  pop     rbp
0x14000d456  pop     rbx
0x14000d457  retn
```
