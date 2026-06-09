# Smb2StartPopulateFileInfoCache

- ea: `0x1400054c0`
- end: `0x140005625`
- name: `Smb2StartPopulateFileInfoCache`
- size: `357`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140003a80`

## callees

- `0x1400054c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400055ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400055ef`
- `ntoskrnl!ExAllocatePool2` at `0x1400054ea`
- `ntoskrnl!ExAllocatePool2` at `0x1400054ea`
- `mrxsmb!SmbCeAssociateExchangeWithCompoundingKeyEx` at `0x140005585`
- `mrxsmb!SmbCeAssociateExchangeWithCompoundingKeyEx` at `0x140005585`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14000560d`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14000560d`
- `mrxsmb!SmbCeInitiateExchange` at `0x1400055be`
- `mrxsmb!SmbCeInitiateExchange` at `0x1400055be`
- `mrxsmb!SmbCeInitializeExchange` at `0x14000554b`
- `mrxsmb!SmbCeInitializeExchange` at `0x14000554b`

## pseudocode

```c
__int64 __fastcall Smb2StartPopulateFileInfoCache(__int64 a1, __int64 a2, _QWORD *a3)
{
  void *Pool2; // rsi
  int v6; // ebx
  __int64 v7; // rax
  __int64 v9; // [rsp+78h] [rbp+10h] BYREF

  v9 = 0;
  Pool2 = (void *)ExAllocatePool2(66, 56, 1834174790);
  if ( Pool2 )
  {
    v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL) + 40LL);
    _InterlockedIncrement64((volatile signed __int64 *)(v7 + 520));
    v6 = SmbCeInitializeExchange(&v9, a1, 0, 0, 0, v7, 2600, &QueryInfoDispatch);
    if ( !v6 )
    {
      *(_QWORD *)(v9 + 2408) = Pool2;
      *(_DWORD *)(v9 + 2416) = 56;
      SmbCeAssociateExchangeWithCompoundingKeyEx(v9, 0, 0xFFFF);
      *(_DWORD *)(v9 + 2424) = 34;
      *(_DWORD *)(v9 + 2420) = 1;
      _InterlockedOr((volatile signed __int32 *)(v9 + 68), 1u);
      v6 = SmbCeInitiateExchange(v9);
    }
    if ( v6 >= 0 )
    {
      *a3 = v9;
      return (unsigned int)v6;
    }
    *a3 = 0;
    ExFreePoolWithTag(Pool2, 0x6D534946u);
  }
  else
  {
    v6 = -1073741670;
    *a3 = 0;
  }
  if ( v9 )
    SmbCeWaitForCompletionAndFinalizeExchangeEx(v9, 0, 0, 0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400054c0  mov     [rsp+arg_8], rdx
0x1400054c5  push    rbx
0x1400054c6  push    rbp
0x1400054c7  push    rsi
0x1400054c8  push    rdi
0x1400054c9  sub     rsp, 48h
0x1400054cd  mov     rdi, r8
0x1400054d0  mov     rbx, rcx
0x1400054d3  xor     ebp, ebp
0x1400054d5  mov     ecx, 42h ; 'B'
0x1400054da  mov     r8d, 6D534946h
0x1400054e0  mov     [rsp+68h+arg_8], rbp
0x1400054e5  mov     edx, 38h ; '8'
0x1400054ea  call    cs:__imp_ExAllocatePool2
0x1400054f1  nop     dword ptr [rax+rax+00h]
0x1400054f6  mov     rsi, rax
0x1400054f9  test    rax, rax
0x1400054fc  jnz     short loc_14000550B
0x1400054fe  mov     ebx, 0C000009Ah
0x140005503  mov     [rdi], rbp
0x140005506  jmp     loc_1400055FB
0x14000550b  mov     rax, [rbx+48h]
0x14000550f  mov     rcx, [rax+28h]
0x140005513  mov     rax, [rcx+28h]
0x140005517  lock inc qword ptr [rax+208h]
0x14000551f  lea     rcx, QueryInfoDispatch
0x140005526  xor     r9d, r9d
0x140005529  mov     [rsp+68h+var_30], rcx
0x14000552e  xor     r8d, r8d
0x140005531  mov     [rsp+68h+var_38], 0A28h
0x140005539  lea     rcx, [rsp+68h+arg_8]
0x14000553e  mov     [rsp+68h+var_40], rax
0x140005543  mov     rdx, rbx
0x140005546  mov     [rsp+68h+var_48], rbp
0x14000554b  call    cs:__imp_SmbCeInitializeExchange
0x140005552  nop     dword ptr [rax+rax+00h]
0x140005557  mov     ebx, eax
0x140005559  test    eax, eax
0x14000555b  jnz     short loc_1400055CC
0x14000555d  mov     rax, [rsp+68h+arg_8]
0x140005562  xor     edx, edx
0x140005564  mov     r8d, 0FFFFh
0x14000556a  mov     [rax+968h], rsi
0x140005571  mov     rax, [rsp+68h+arg_8]
0x140005576  mov     dword ptr [rax+970h], 38h ; '8'
0x140005580  mov     rcx, [rsp+68h+arg_8]
0x140005585  call    cs:__imp_SmbCeAssociateExchangeWithCompoundingKeyEx
0x14000558c  nop     dword ptr [rax+rax+00h]
0x140005591  mov     rax, [rsp+68h+arg_8]
0x140005596  mov     dword ptr [rax+978h], 22h ; '"'
0x1400055a0  mov     rax, [rsp+68h+arg_8]
0x1400055a5  mov     dword ptr [rax+974h], 1
0x1400055af  mov     rax, [rsp+68h+arg_8]
0x1400055b4  lock or dword ptr [rax+44h], 1
0x1400055b9  mov     rcx, [rsp+68h+arg_8]
0x1400055be  call    cs:__imp_SmbCeInitiateExchange
0x1400055c5  nop     dword ptr [rax+rax+00h]
0x1400055ca  mov     ebx, eax
0x1400055cc  test    ebx, ebx
0x1400055ce  js      short loc_1400055E4
0x1400055d0  mov     rax, [rsp+68h+arg_8]
0x1400055d5  mov     [rdi], rax
0x1400055d8  mov     eax, ebx
0x1400055da  add     rsp, 48h
0x1400055de  pop     rdi
0x1400055df  pop     rsi
0x1400055e0  pop     rbp
0x1400055e1  pop     rbx
0x1400055e2  retn
0x1400055e4  mov     edx, 6D534946h; Tag
0x1400055e9  mov     [rdi], rbp
0x1400055ec  mov     rcx, rsi; P
0x1400055ef  call    cs:__imp_ExFreePoolWithTag
0x1400055f6  nop     dword ptr [rax+rax+00h]
0x1400055fb  mov     rcx, [rsp+68h+arg_8]
0x140005600  test    rcx, rcx
0x140005603  jz      short loc_140005619
0x140005605  xor     r9d, r9d
0x140005608  xor     r8d, r8d
0x14000560b  xor     edx, edx
0x14000560d  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140005614  nop     dword ptr [rax+rax+00h]
0x140005619  mov     eax, ebx
0x14000561b  add     rsp, 48h
0x14000561f  pop     rdi
0x140005620  pop     rsi
0x140005621  pop     rbp
0x140005622  pop     rbx
0x140005623  retn
```
