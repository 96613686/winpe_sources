# MRxSmb2SetSecurityInformation

- ea: `0x1400144c0`
- end: `0x140014584`
- name: `MRxSmb2SetSecurityInformation`
- size: `196`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x1400144c0`
- `0x140014650`
- `0x140014a00`
- `0x140056930`

## import_xrefs

- `rdbss!RxFcbGetOutstandingBufferingChangeEvent` at `0x14003b34a`
- `rdbss!RxFcbGetOutstandingBufferingChangeEvent` at `0x14003b34a`
- `rdbss!RxProcessFcbChangeBufferingStateRequest` at `0x14003b356`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14003b36b`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14003b38e`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14003b36b`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14003b38e`
- `mrxsmb!SmbCeInitiateExchange` at `0x14003b31c`
- `mrxsmb!SmbCeInitiateExchange` at `0x14003b31c`
- `mrxsmb!SmbCeInitializeExchange` at `0x14001451b`
- `mrxsmb!SmbCeInitializeExchange` at `0x14001451b`

## pseudocode

```c
__int64 __fastcall MRxSmb2SetSecurityInformation(__int64 a1)
{
  __int64 v2; // r14
  __int64 v3; // rsi
  int v4; // r15d
  __int64 v5; // rbp
  int v6; // edi
  __int64 v7; // r8
  __int64 v9; // r9
  void (__stdcall *v10)(PFCB); // r8
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // [rsp+80h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 56);
  v3 = *(_QWORD *)(v2 + 120);
  v4 = *(_DWORD *)(a1 + 512);
  v5 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL) + 40LL);
  v13 = 0;
  v6 = SmbCeInitializeExchange(&v13, a1, 0, 0, 0, v5, 2416, &SetInfoDispatch);
  if ( !v6 )
  {
    *(_DWORD *)(v13 + 2412) = v4;
    *(_DWORD *)(v13 + 2408) = 3;
    _InterlockedOr((volatile signed __int32 *)(v13 + 68), 1u);
    v6 = SmbCeInitiateExchange(v13);
    if ( v6 == 259 )
    {
      if ( v4 == 13 || v4 == 10 )
      {
        v12 = RxFcbGetOutstandingBufferingChangeEvent(v2);
        v10 = RxProcessFcbChangeBufferingStateRequest;
        v9 = v2;
        v11 = v12;
      }
      else
      {
        v9 = 0;
        v10 = 0;
        v11 = 0;
      }
      v6 = SmbCeWaitForCompletionAndFinalizeExchangeEx(v13, v11, v10, v9);
    }
    else
    {
      SmbCeWaitForCompletionAndFinalizeExchangeEx(v13, 0, 0, 0);
    }
  }
  if ( v6 >= 0 )
  {
    Smb2InvalidateFileInfoCacheEntry(a1, *(_QWORD *)(v3 + 40) + 376LL);
    Smb2InvalidateSingleFileInDirInfoCache(a1, *(_QWORD *)(v5 + 424) + 1112LL);
    LOBYTE(v7) = 1;
    Smb2InvalidateFileAbeStatusCacheEntry(a1, *(_QWORD *)(v3 + 40) + 1296LL, v7);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400144c0  mov     r11, rsp
0x1400144c3  push    rbx
0x1400144c4  push    rbp
0x1400144c5  push    rsi
0x1400144c6  push    rdi
0x1400144c7  push    r14
0x1400144c9  push    r15
0x1400144cb  sub     rsp, 48h
0x1400144cf  mov     rax, [rcx+48h]
0x1400144d3  mov     rbx, rcx
0x1400144d6  mov     r14, [rcx+38h]
0x1400144da  xor     r9d, r9d
0x1400144dd  xor     r8d, r8d
0x1400144e0  mov     rdx, rbx
0x1400144e3  mov     rcx, [rax+28h]
0x1400144e7  lea     rax, SetInfoDispatch
0x1400144ee  mov     rsi, [r14+78h]
0x1400144f2  mov     r15d, [rbx+200h]
0x1400144f9  mov     [r11-40h], rax
0x1400144fd  mov     rbp, [rcx+28h]
0x140014501  xor     ecx, ecx
0x140014503  mov     [rsp+78h+var_48], 970h
0x14001450b  mov     [r11-50h], rbp
0x14001450f  mov     [r11+8], rcx
0x140014513  mov     [r11-58h], rcx
0x140014517  lea     rcx, [r11+8]
0x14001451b  call    cs:__imp_SmbCeInitializeExchange
0x140014522  nop     dword ptr [rax+rax+00h]
0x140014527  mov     edi, eax
0x140014529  test    eax, eax
0x14001452b  jz      loc_14003B2E6
0x140014531  test    edi, edi
0x140014533  js      short loc_140014574
0x140014535  mov     rdx, [rsi+28h]
0x140014539  mov     rcx, rbx
0x14001453c  add     rdx, 178h
0x140014543  call    Smb2InvalidateFileInfoCacheEntry
0x140014548  mov     rdx, [rbp+1A8h]
0x14001454f  mov     rcx, rbx
0x140014552  add     rdx, 458h
0x140014559  call    Smb2InvalidateSingleFileInDirInfoCache
0x14001455e  mov     rdx, [rsi+28h]
0x140014562  mov     r8b, 1
0x140014565  add     rdx, 510h
0x14001456c  mov     rcx, rbx
0x14001456f  call    Smb2InvalidateFileAbeStatusCacheEntry
0x140014574  mov     eax, edi
0x140014576  add     rsp, 48h
0x14001457a  pop     r15
0x14001457c  pop     r14
0x14001457e  pop     rdi
0x14001457f  pop     rsi
0x140014580  pop     rbp
0x140014581  pop     rbx
0x140014582  retn
0x14003b2e6  mov     rax, [rsp+78h+arg_0]
0x14003b2ee  mov     [rax+96Ch], r15d
0x14003b2f5  mov     rax, [rsp+78h+arg_0]
0x14003b2fd  mov     dword ptr [rax+968h], 3
0x14003b307  mov     rax, [rsp+78h+arg_0]
0x14003b30f  lock or dword ptr [rax+44h], 1
0x14003b314  mov     rcx, [rsp+78h+arg_0]
0x14003b31c  call    cs:__imp_SmbCeInitiateExchange
0x14003b323  nop     dword ptr [rax+rax+00h]
0x14003b328  mov     edi, eax
0x14003b32a  cmp     eax, 103h
0x14003b32f  jnz     short loc_14003B37E
0x14003b331  cmp     r15d, 0Dh
0x14003b335  jz      short loc_14003B347
0x14003b337  cmp     r15d, 0Ah
0x14003b33b  jz      short loc_14003B347
0x14003b33d  xor     r9d, r9d
0x14003b340  xor     r8d, r8d
0x14003b343  xor     edx, edx
0x14003b345  jmp     short loc_14003B363
0x14003b347  mov     rcx, r14
0x14003b34a  call    cs:__imp_RxFcbGetOutstandingBufferingChangeEvent
0x14003b351  nop     dword ptr [rax+rax+00h]
0x14003b356  mov     r8, cs:__imp_RxProcessFcbChangeBufferingStateRequest
0x14003b35d  mov     r9, r14
0x14003b360  mov     rdx, rax
0x14003b363  mov     rcx, [rsp+78h+arg_0]
0x14003b36b  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x14003b372  nop     dword ptr [rax+rax+00h]
0x14003b377  mov     edi, eax
0x14003b379  jmp     loc_140014531
0x14003b37e  mov     rcx, [rsp+78h+arg_0]
0x14003b386  xor     r9d, r9d
0x14003b389  xor     r8d, r8d
0x14003b38c  xor     edx, edx
0x14003b38e  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x14003b395  nop     dword ptr [rax+rax+00h]
0x14003b39a  nop
0x14003b39b  jmp     loc_140014531
```
