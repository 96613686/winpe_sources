# NfsSendWaitReply

- ea: `0x140013ac0`
- end: `0x140013c14`
- name: `NfsSendWaitReply`
- size: `340`
- prototype: `__int64 __fastcall(int, __int64, __int64, int, __int64, __int64, __int64, _QWORD *, int)`
- caller_count: `24`
- callee_count: `3`
- tags: ``

## callers

- `0x140004530`
- `0x14000c8d8`
- `0x14000cf04`
- `0x14000da84`
- `0x14000df64`
- `0x14000e4ec`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x140010904`
- `0x140011298`
- `0x140011984`
- `0x1400124ec`
- `0x1400132cc`
- `0x14001ea54`
- `0x14001f178`
- `0x140020fa8`
- `0x1400219e8`
- `0x14002372c`
- `0x140023dd0`
- `0x140028d14`
- `0x14002a5f0`
- `0x14002a9e0`
- `0x14002b138`

## callees

- `0x140001760`
- `0x140013ac0`
- `0x140022270`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140013ba9`
- `ntoskrnl!KeWaitForSingleObject` at `0x140013ba9`
- `ntoskrnl!KeReleaseMutex` at `0x140013bd1`
- `ntoskrnl!KeReleaseMutex` at `0x140013bd1`
- `rpcxdr!OncRpcDestroy` at `0x140013be0`
- `rpcxdr!OncRpcDestroy` at `0x140013be0`

## pseudocode

```c
__int64 __fastcall NfsSendWaitReply(
        int a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8,
        int a9)
{
  __int64 result; // rax
  unsigned int v11; // r9d
  _DWORD *v12; // rcx
  int v13; // r8d
  int v14; // edx
  int v15; // eax
  __int64 v16; // rdi

  result = NfsSendWaitReplyWaitInternal(
             a1,
             *(_BYTE *)(a5 + 16) == 2,
             a4,
             a5,
             a6,
             a7,
             (__int64)a8,
             *(_BYTE *)(a5 + 16) == 2,
             a9);
  v11 = result;
  if ( (int)result >= 0 )
  {
    v12 = (_DWORD *)*a8;
    if ( *a8 )
    {
      v13 = v12[68];
      if ( v13 )
      {
        if ( v13 != 1 )
          return result;
        v14 = v12[72];
        if ( v14 )
        {
          if ( v14 == 1 )
            v15 = -1073741790;
          else
            v15 = -1073741823;
        }
        else
        {
          v15 = -1073741628;
        }
      }
      else
      {
        v15 = OncRpcpMapRpcAcceptedStatusToNtStatus((unsigned int)v12[160]);
      }
      if ( v15 == -1073741790 && a3 )
      {
        v16 = *(_QWORD *)(a3 + 40);
        KeWaitForSingleObject(*(PVOID *)(v16 + 184), Executive, 0, 0, 0);
        if ( *(_DWORD *)(v16 + 200) != 1 )
          *(_DWORD *)(v16 + 200) = 2;
        KeReleaseMutex(*(PRKMUTEX *)(v16 + 184), 0);
        OncRpcDestroy(*a8);
        *a8 = 0;
        return 3225485313LL;
      }
      else
      {
        return v11;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140013ac0  mov     [rsp+arg_8], rbx
0x140013ac5  push    rdi
0x140013ac6  sub     rsp, 50h
0x140013aca  mov     eax, [rsp+58h+arg_40]
0x140013ad1  mov     r10, r9
0x140013ad4  mov     r9, [rsp+58h+arg_20]
0x140013adc  mov     rdi, r8
0x140013adf  mov     rbx, [rsp+58h+arg_38]
0x140013ae7  mov     r8, r10
0x140013aea  mov     [rsp+58h+var_18], eax
0x140013aee  mov     rax, [rsp+58h+arg_30]
0x140013af6  cmp     byte ptr [r9+10h], 2
0x140013afb  setz    dl
0x140013afe  mov     [rsp+58h+var_20], dl
0x140013b02  mov     [rsp+58h+var_28], rbx
0x140013b07  mov     [rsp+58h+var_30], rax
0x140013b0c  mov     rax, [rsp+58h+arg_28]
0x140013b14  mov     [rsp+58h+Timeout], rax
0x140013b19  call    NfsSendWaitReplyWaitInternal
0x140013b1e  mov     r9d, eax
0x140013b21  test    eax, eax
0x140013b23  js      loc_140013C08
0x140013b29  mov     rcx, [rbx]
0x140013b2c  test    rcx, rcx
0x140013b2f  jz      loc_140013C08
0x140013b35  mov     r8d, [rcx+110h]
0x140013b3c  test    r8d, r8d
0x140013b3f  jz      short loc_140013B6F
0x140013b41  cmp     r8d, 1
0x140013b45  jnz     loc_140013C08
0x140013b4b  mov     edx, [rcx+120h]
0x140013b51  test    edx, edx
0x140013b53  jz      short loc_140013B68
0x140013b55  cmp     edx, r8d
0x140013b58  jz      short loc_140013B61
0x140013b5a  mov     eax, 0C0000001h
0x140013b5f  jmp     short loc_140013B7A
0x140013b61  mov     eax, 0C0000022h
0x140013b66  jmp     short loc_140013B7A
0x140013b68  mov     eax, 0C00000C4h
0x140013b6d  jmp     short loc_140013B7A
0x140013b6f  mov     ecx, [rcx+280h]
0x140013b75  call    OncRpcpMapRpcAcceptedStatusToNtStatus
0x140013b7a  cmp     eax, 0C0000022h
0x140013b7f  jnz     loc_140013C05
0x140013b85  test    rdi, rdi
0x140013b88  jz      short loc_140013C05
0x140013b8a  mov     rdi, [rdi+28h]
0x140013b8e  xor     r9d, r9d; Alertable
0x140013b91  mov     [rsp+58h+arg_0], rsi
0x140013b96  xor     r8d, r8d; WaitMode
0x140013b99  xor     esi, esi
0x140013b9b  xor     edx, edx; WaitReason
0x140013b9d  mov     [rsp+58h+Timeout], rsi; Timeout
0x140013ba2  mov     rcx, [rdi+0B8h]; Object
0x140013ba9  call    cs:__imp_KeWaitForSingleObject
0x140013bb0  nop     dword ptr [rax+rax+00h]
0x140013bb5  cmp     dword ptr [rdi+0C8h], 1
0x140013bbc  jz      short loc_140013BC8
0x140013bbe  mov     dword ptr [rdi+0C8h], 2
0x140013bc8  mov     rcx, [rdi+0B8h]; Mutex
0x140013bcf  xor     edx, edx; Wait
0x140013bd1  call    cs:__imp_KeReleaseMutex
0x140013bd8  nop     dword ptr [rax+rax+00h]
0x140013bdd  mov     rcx, [rbx]
0x140013be0  call    cs:__imp_OncRpcDestroy
0x140013be7  nop     dword ptr [rax+rax+00h]
0x140013bec  mov     [rbx], rsi
0x140013bef  mov     eax, 0C0410001h
0x140013bf4  mov     rsi, [rsp+58h+arg_0]
0x140013bf9  mov     rbx, [rsp+58h+arg_8]
0x140013bfe  add     rsp, 50h
0x140013c02  pop     rdi
0x140013c03  retn
0x140013c05  mov     eax, r9d
0x140013c08  mov     rbx, [rsp+58h+arg_8]
0x140013c0d  add     rsp, 50h
0x140013c11  pop     rdi
0x140013c12  retn
```
