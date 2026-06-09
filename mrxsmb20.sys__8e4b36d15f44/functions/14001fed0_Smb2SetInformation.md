# Smb2SetInformation

- ea: `0x14001fed0`
- end: `0x14001ff46`
- name: `Smb2SetInformation`
- size: `118`
- prototype: `__int64 __fastcall(__int64, int, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002f210`
- `0x14002f280`
- `0x14002f790`
- `0x14002f7c0`

## callees

- `0x14001fed0`

## import_xrefs

- `rdbss!RxFcbGetOutstandingBufferingChangeEvent` at `0x14003c413`
- `rdbss!RxFcbGetOutstandingBufferingChangeEvent` at `0x14003c413`
- `rdbss!RxProcessFcbChangeBufferingStateRequest` at `0x14003c41f`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14003c431`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14003c450`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14003c431`
- `mrxsmb!SmbCeWaitForCompletionAndFinalizeExchangeEx` at `0x14003c450`
- `mrxsmb!SmbCeInitiateExchange` at `0x14003c3e7`
- `mrxsmb!SmbCeInitiateExchange` at `0x14003c3e7`
- `mrxsmb!SmbCeInitializeExchange` at `0x14001ff21`
- `mrxsmb!SmbCeInitializeExchange` at `0x14001ff21`

## pseudocode

```c
__int64 __fastcall Smb2SetInformation(__int64 a1, int a2, int a3)
{
  __int64 v4; // rdi
  __int64 result; // rax
  unsigned int v7; // esi
  __int64 v8; // r9
  void (__stdcall *v9)(PFCB); // r8
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // [rsp+28h] [rbp-20h]
  __int64 v13; // [rsp+50h] [rbp+8h] BYREF

  v4 = *(_QWORD *)(a1 + 56);
  v12 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 40LL) + 40LL);
  v13 = 0;
  result = SmbCeInitializeExchange(&v13, a1, 0, 0, 0, v12, 2416, &SetInfoDispatch);
  if ( !(_DWORD)result )
  {
    *(_DWORD *)(v13 + 2412) = a3;
    *(_DWORD *)(v13 + 2408) = a2;
    _InterlockedOr((volatile signed __int32 *)(v13 + 68), 1u);
    v7 = SmbCeInitiateExchange(v13);
    if ( v7 == 259 )
    {
      if ( a3 == 13 || a3 == 10 )
      {
        v11 = RxFcbGetOutstandingBufferingChangeEvent(v4);
        v9 = RxProcessFcbChangeBufferingStateRequest;
        v8 = v4;
        v10 = v11;
      }
      else
      {
        v8 = 0;
        v9 = 0;
        v10 = 0;
      }
      return SmbCeWaitForCompletionAndFinalizeExchangeEx(v13, v10, v9, v8);
    }
    else
    {
      SmbCeWaitForCompletionAndFinalizeExchangeEx(v13, 0, 0, 0);
      return v7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001fed0  mov     r11, rsp
0x14001fed3  mov     [r11+10h], rbx
0x14001fed7  mov     [r11+18h], rsi
0x14001fedb  push    rdi
0x14001fedc  sub     rsp, 40h
0x14001fee0  mov     rax, [rcx+48h]
0x14001fee4  mov     esi, edx
0x14001fee6  mov     rdi, [rcx+38h]
0x14001feea  lea     rdx, SetInfoDispatch
0x14001fef1  mov     [r11-10h], rdx
0x14001fef5  mov     ebx, r8d
0x14001fef8  xor     r8d, r8d
0x14001fefb  mov     [rsp+48h+var_18], 970h
0x14001ff03  mov     r9, [rax+28h]
0x14001ff07  mov     rdx, rcx
0x14001ff0a  lea     rcx, [r11+8]
0x14001ff0e  mov     rax, [r9+28h]
0x14001ff12  xor     r9d, r9d
0x14001ff15  mov     [r11-20h], rax
0x14001ff19  mov     [r11-28h], r8
0x14001ff1d  mov     [r11+8], r8
0x14001ff21  call    cs:__imp_SmbCeInitializeExchange
0x14001ff28  nop     dword ptr [rax+rax+00h]
0x14001ff2d  test    eax, eax
0x14001ff2f  jz      loc_14003C3C2
0x14001ff35  mov     rbx, [rsp+48h+arg_8]
0x14001ff3a  mov     rsi, [rsp+48h+arg_10]
0x14001ff3f  add     rsp, 40h
0x14001ff43  pop     rdi
0x14001ff44  retn
0x14003c3c2  mov     rax, [rsp+48h+arg_0]
0x14003c3c7  mov     [rax+96Ch], ebx
0x14003c3cd  mov     rax, [rsp+48h+arg_0]
0x14003c3d2  mov     [rax+968h], esi
0x14003c3d8  mov     rax, [rsp+48h+arg_0]
0x14003c3dd  lock or dword ptr [rax+44h], 1
0x14003c3e2  mov     rcx, [rsp+48h+arg_0]
0x14003c3e7  call    cs:__imp_SmbCeInitiateExchange
0x14003c3ee  nop     dword ptr [rax+rax+00h]
0x14003c3f3  mov     esi, eax
0x14003c3f5  cmp     eax, 103h
0x14003c3fa  jnz     short loc_14003C443
0x14003c3fc  cmp     ebx, 0Dh
0x14003c3ff  jz      short loc_14003C410
0x14003c401  cmp     ebx, 0Ah
0x14003c404  jz      short loc_14003C410
0x14003c406  xor     r9d, r9d
0x14003c409  xor     r8d, r8d
0x14003c40c  xor     edx, edx
0x14003c40e  jmp     short loc_14003C42C
0x14003c410  mov     rcx, rdi
0x14003c413  call    cs:__imp_RxFcbGetOutstandingBufferingChangeEvent
0x14003c41a  nop     dword ptr [rax+rax+00h]
0x14003c41f  mov     r8, cs:__imp_RxProcessFcbChangeBufferingStateRequest
0x14003c426  mov     r9, rdi
0x14003c429  mov     rdx, rax
0x14003c42c  mov     rcx, [rsp+48h+arg_0]
0x14003c431  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x14003c438  nop     dword ptr [rax+rax+00h]
0x14003c43d  nop
0x14003c43e  jmp     loc_14001FF35
0x14003c443  mov     rcx, [rsp+48h+arg_0]
0x14003c448  xor     r9d, r9d
0x14003c44b  xor     r8d, r8d
0x14003c44e  xor     edx, edx
0x14003c450  call    cs:__imp_SmbCeWaitForCompletionAndFinalizeExchangeEx
0x14003c457  nop     dword ptr [rax+rax+00h]
0x14003c45c  mov     eax, esi
0x14003c45e  jmp     loc_14001FF35
```
