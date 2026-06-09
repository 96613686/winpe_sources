# MRxSmb2ExtendForCache

- ea: `0x140013dc0`
- end: `0x140013f92`
- name: `MRxSmb2ExtendForCache`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140013dc0`
- `0x140014650`
- `0x140014a00`
- `0x14002f850`

## import_xrefs

- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140013ede`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140013eee`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140013ede`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x140013eee`
- `mrxsmb!SmbCeInitiateExchange` at `0x140013ebc`
- `mrxsmb!SmbCeInitiateExchange` at `0x140013ebc`
- `mrxsmb!SmbCeInitializeExchange` at `0x140013e7d`
- `mrxsmb!SmbCeInitializeExchange` at `0x140013e7d`

## pseudocode

```c
__int64 __fastcall MRxSmb2ExtendForCache(__int64 a1, __int64 *a2, __int64 *a3)
{
  __int64 v6; // rdx
  __int64 v7; // rsi
  __int64 v8; // r8
  unsigned int v9; // eax
  __int64 v10; // rbp
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned int v13; // edi
  __int64 v14; // r8
  __int64 v16; // [rsp+28h] [rbp-40h]
  __int64 v17; // [rsp+70h] [rbp+8h] BYREF

  v6 = *a2;
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 56) + 120LL);
  v8 = 2 * v6;
  v9 = *(_DWORD *)(v7 + 104);
  v10 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL) + 40LL);
  if ( v9 < 0x1000 )
    v9 = 4096;
  if ( v6 >= 0x100000 )
    v8 = v6 + 0x100000;
  *a3 = v9 + v8 - 1 - (v9 + v8 - 1) % v9;
  v11 = *(_QWORD *)(a1 + 72);
  *(_QWORD *)(a1 + 456) = a3;
  *(_DWORD *)(a1 + 472) = 8;
  v16 = *(_QWORD *)(*(_QWORD *)(v11 + 40) + 40LL);
  v17 = 0;
  v13 = SmbCeInitializeExchange(&v17, a1, 0, 0, 0, v16, 2416, &SetInfoDispatch);
  if ( !v13 )
  {
    *(_DWORD *)(v17 + 2412) = 19;
    *(_DWORD *)(v17 + 2408) = 1;
    _InterlockedOr((volatile signed __int32 *)(v17 + 68), 1u);
    v13 = SmbCeInitiateExchange(v17);
    if ( v13 == 259 )
      v13 = SmbCeWaitForCompletionAndFinalizeExchangeEx(v17, 0, 0, 0);
    else
      SmbCeWaitForCompletionAndFinalizeExchangeEx(v17, 0, 0, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qiiL(WPP_GLOBAL_Control->AttachedDevice, v12, v14, *(_QWORD *)(a1 + 56), *a2, *a3, v13);
  }
  if ( v13 == -1073741790 )
  {
    v13 = 0;
    *a3 = *a2;
  }
  Smb2InvalidateFileInfoCacheEntry(a1, (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v7 + 40) + 376LL));
  Smb2InvalidateSingleFileInDirInfoCache((_QWORD *)a1, (struct _NAME_CACHE_CONTROL_ *)(*(_QWORD *)(v10 + 424) + 1112LL));
  return v13;
}

```

## disassembly

```asm
0x140013dc0  mov     r11, rsp
0x140013dc3  mov     [r11+10h], rbx
0x140013dc7  mov     [r11+18h], rbp
0x140013dcb  push    rsi
0x140013dcc  push    rdi
0x140013dcd  push    r12
0x140013dcf  push    r14
0x140013dd1  push    r15
0x140013dd3  sub     rsp, 40h
0x140013dd7  mov     rax, [rcx+38h]
0x140013ddb  mov     rbx, rcx
0x140013dde  mov     r14, r8
0x140013de1  mov     r15, rdx
0x140013de4  mov     rdx, [rdx]
0x140013de7  mov     rsi, [rax+78h]
0x140013deb  mov     rax, [rcx+48h]
0x140013def  lea     r8, [rdx+rdx]
0x140013df3  mov     rcx, [rax+28h]
0x140013df7  mov     eax, [rsi+68h]
0x140013dfa  mov     rbp, [rcx+28h]
0x140013dfe  mov     ecx, 1000h
0x140013e03  cmp     eax, ecx
0x140013e05  cmovb   eax, ecx
0x140013e08  cmp     rdx, 100000h
0x140013e0f  mov     r9d, eax
0x140013e12  lea     rax, [rdx+100000h]
0x140013e19  cmovge  r8, rax
0x140013e1d  xor     r12d, r12d
0x140013e20  dec     r8
0x140013e23  add     r8, r9
0x140013e26  mov     rax, r8
0x140013e29  cqo
0x140013e2b  idiv    r9
0x140013e2e  xor     r9d, r9d
0x140013e31  sub     r8, rdx
0x140013e34  mov     rdx, rbx
0x140013e37  mov     [r14], r8
0x140013e3a  xor     r8d, r8d
0x140013e3d  mov     rax, [rbx+48h]
0x140013e41  mov     [rbx+1C8h], r14
0x140013e48  mov     dword ptr [rbx+1D8h], 8
0x140013e52  mov     rcx, [rax+28h]
0x140013e56  mov     rax, [rcx+28h]
0x140013e5a  lea     rcx, SetInfoDispatch
0x140013e61  mov     [r11-30h], rcx
0x140013e65  lea     rcx, [r11+8]
0x140013e69  mov     [rsp+68h+var_38], 970h
0x140013e71  mov     [r11-40h], rax
0x140013e75  mov     [r11-48h], r12
0x140013e79  mov     [r11+8], r12
0x140013e7d  call    cs:__imp_SmbCeInitializeExchange
0x140013e84  nop     dword ptr [rax+rax+00h]
0x140013e89  mov     edi, eax
0x140013e8b  test    eax, eax
0x140013e8d  jnz     short loc_140013EFA
0x140013e8f  mov     rax, [rsp+68h+arg_0]
0x140013e94  mov     dword ptr [rax+96Ch], 13h
0x140013e9e  mov     rax, [rsp+68h+arg_0]
0x140013ea3  mov     dword ptr [rax+968h], 1
0x140013ead  mov     rax, [rsp+68h+arg_0]
0x140013eb2  lock or dword ptr [rax+44h], 1
0x140013eb7  mov     rcx, [rsp+68h+arg_0]
0x140013ebc  call    cs:__imp_SmbCeInitiateExchange
0x140013ec3  nop     dword ptr [rax+rax+00h]
0x140013ec8  mov     rcx, [rsp+68h+arg_0]
0x140013ecd  xor     r9d, r9d
0x140013ed0  xor     r8d, r8d
0x140013ed3  xor     edx, edx
0x140013ed5  mov     edi, eax
0x140013ed7  cmp     eax, 103h
0x140013edc  jnz     short loc_140013EEE
0x140013ede  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140013ee5  nop     dword ptr [rax+rax+00h]
0x140013eea  mov     edi, eax
0x140013eec  jmp     short loc_140013EFA
0x140013eee  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x140013ef5  nop     dword ptr [rax+rax+00h]
0x140013efa  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140013f01  lea     rax, WPP_GLOBAL_Control
0x140013f08  cmp     rcx, rax
0x140013f0b  jz      short loc_140013F3B
0x140013f0d  mov     eax, [rcx+2Ch]
0x140013f10  test    al, 20h
0x140013f12  jz      short loc_140013F3B
0x140013f14  cmp     byte ptr [rcx+29h], 2
0x140013f18  jb      short loc_140013F3B
0x140013f1a  mov     rax, [r14]
0x140013f1d  mov     r9, [rbx+38h]
0x140013f21  mov     rcx, [rcx+18h]
0x140013f25  mov     [rsp+68h+var_38], edi
0x140013f29  mov     [rsp+68h+var_40], rax
0x140013f2e  mov     rax, [r15]
0x140013f31  mov     [rsp+68h+var_48], rax
0x140013f36  call    WPP_SF_qiiL
0x140013f3b  cmp     edi, 0C0000022h
0x140013f41  jnz     short loc_140013F4C
0x140013f43  mov     rax, [r15]
0x140013f46  mov     edi, r12d
0x140013f49  mov     [r14], rax
0x140013f4c  mov     rdx, [rsi+28h]
0x140013f50  mov     rcx, rbx
0x140013f53  add     rdx, 178h
0x140013f5a  call    Smb2InvalidateFileInfoCacheEntry
0x140013f5f  mov     rdx, [rbp+1A8h]
0x140013f66  mov     rcx, rbx
0x140013f69  add     rdx, 458h
0x140013f70  call    Smb2InvalidateSingleFileInDirInfoCache
0x140013f75  mov     rbx, [rsp+68h+arg_8]
0x140013f7a  mov     eax, edi
0x140013f7c  mov     rbp, [rsp+68h+arg_10]
0x140013f84  add     rsp, 40h
0x140013f88  pop     r15
0x140013f8a  pop     r14
0x140013f8c  pop     r12
0x140013f8e  pop     rdi
0x140013f8f  pop     rsi
0x140013f90  retn
```
