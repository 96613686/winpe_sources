# GroupByUntil_UpstreamObserver_OnNextKeyAndItem

- ea: `0x18003b200`
- end: `0x18003b47d`
- name: `GroupByUntil_UpstreamObserver_OnNextKeyAndItem`
- size: `637`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18001ae1c`
- `0x18003a84c`
- `0x18003b200`
- `0x18003bd6c`
- `0x180043eb8`
- `0x180044464`
- `0x18004449c`
- `0x1800444f4`
- `0x18004462c`
- `0x180044880`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b254`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b431`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b254`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b431`

## pseudocode

```c
__int64 __fastcall GroupByUntil_UpstreamObserver_OnNextKeyAndItem(__int64 *a1, int a2, __int64 a3)
{
  __int64 *v3; // rdi
  __int64 v4; // rsi
  __int64 v5; // r12
  unsigned int Bucket; // r13d
  __int64 v9; // rbx
  _QWORD *v10; // r12
  __int64 v11; // rcx
  void (__fastcall *v12)(_QWORD, _QWORD, _QWORD); // rax
  __int64 v13; // rcx
  void (__fastcall *v14)(_QWORD, __int64); // rax
  char v16; // [rsp+30h] [rbp-79h] BYREF
  __int64 v17; // [rsp+38h] [rbp-71h] BYREF
  __int64 v18; // [rsp+40h] [rbp-69h] BYREF
  __int64 v19; // [rsp+48h] [rbp-61h] BYREF
  __int64 v20; // [rsp+50h] [rbp-59h]
  __int64 v21; // [rsp+58h] [rbp-51h] BYREF
  __int128 v22; // [rsp+60h] [rbp-49h]
  __int128 v23; // [rsp+70h] [rbp-39h]
  __int64 v24; // [rsp+80h] [rbp-29h]
  __int64 v25; // [rsp+88h] [rbp-21h]
  __int64 v26; // [rsp+90h] [rbp-19h] BYREF
  __int128 v27; // [rsp+98h] [rbp-11h]
  __int128 v28; // [rsp+A8h] [rbp-1h]
  int v29; // [rsp+B8h] [rbp+Fh]
  __int64 v30; // [rsp+BCh] [rbp+13h]
  int v31; // [rsp+C4h] [rbp+1Bh]

  v20 = a3;
  v19 = 0;
  v3 = a1 + 45;
  v16 = 0;
  v4 = 0;
  v17 = 0;
  v5 = a3;
  v18 = 0;
  if ( a1[50] != GetCurrentThreadId() && (unsigned int)_Pump_BeginDeferringHelper(v3) )
    _Pump_BeginDeferring(v3);
  Bucket = MintValueHashMap_FindOrCreateBucket((int)a1 + 48, a2, 144, (unsigned int)&v16, (__int64)&v19);
  if ( !Bucket )
  {
    v9 = v19;
    if ( v16 )
    {
      v10 = (_QWORD *)(v19 + 48);
      *(_QWORD *)(v19 + 48) = 0;
      *(_QWORD *)(v9 + 40) = 1;
      *(_QWORD *)(v9 + 112) = *a1;
      if ( *((_BYTE *)a1 + 24) )
      {
LABEL_7:
        HashMap_Remove(a1 + 6, v9);
        goto LABEL_16;
      }
      *(_BYTE *)(v9 + 96) = 0;
      *(_QWORD *)(v9 + 104) = 0;
      ((void (__fastcall *)(__int64))s_compositeDisposableFT[0])(v9 + 120);
      Bucket = GroupBase_NewGroup((_DWORD)a1, (int)v9 + 24, (int)v9 + 48, (unsigned int)&v17, (__int64)&v18);
      if ( Bucket )
      {
        HashMap_Remove(a1 + 6, v9);
        v4 = v17;
        goto LABEL_16;
      }
      v11 = a1[5];
      v25 = 0;
      v4 = v17;
      v21 = v17;
      v24 = 15;
      v22 = 0;
      v23 = 0;
      Bucket = DelegateInvoke1(v11, &v21, &GroupByUntil_UntilDelegateResultCallback, v9);
      if ( Bucket )
      {
        v12 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(v9 + 72);
        if ( v12 )
          v12(*v10, Bucket, 0);
        goto LABEL_7;
      }
      v26 = v18;
      v29 = 15;
      v31 = 0;
      v30 = v18 == 0 ? 0x20000000 : 0;
      v13 = *a1;
      v27 = 0;
      v28 = 0;
      ((void (__fastcall *)(__int64, __int64 *))ObserverProtocol_PostNext)(v13, &v26);
      v5 = v20;
    }
    v14 = *(void (__fastcall **)(_QWORD, __int64))(v9 + 56);
    if ( v14 )
      v14(*(_QWORD *)(v9 + 48), v5);
  }
LABEL_16:
  if ( v4 && *(_QWORD *)v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v18 && *(_QWORD *)v18 )
    (*(void (**)(void))(*(_QWORD *)v18 + 16LL))();
  if ( v3[5] != GetCurrentThreadId() && (unsigned int)_Pump_EndDeferringHelper(v3) )
    _Pump_EndDeferring(v3);
  return Bucket;
}

```

## disassembly

```asm
0x18003b200  mov     [rsp-8+arg_18], rbx
0x18003b205  push    rbp
0x18003b206  push    rsi
0x18003b207  push    rdi
0x18003b208  push    r12
0x18003b20a  push    r13
0x18003b20c  push    r14
0x18003b20e  push    r15
0x18003b210  lea     rbp, [rsp-27h]
0x18003b215  sub     rsp, 0D0h
0x18003b21c  mov     rax, cs:__security_cookie
0x18003b223  xor     rax, rsp
0x18003b226  mov     [rbp+57h+var_38], rax
0x18003b22a  xor     r15d, r15d
0x18003b22d  mov     [rbp+57h+var_B0], r8
0x18003b231  mov     [rbp+57h+var_B8], r15
0x18003b235  lea     rdi, [rcx+168h]
0x18003b23c  mov     [rbp+57h+var_D0], r15b
0x18003b240  mov     esi, r15d
0x18003b243  mov     [rbp+57h+var_C8], r15
0x18003b247  mov     r12, r8
0x18003b24a  mov     [rbp+57h+var_C0], r15
0x18003b24e  mov     rbx, rdx
0x18003b251  mov     r14, rcx
0x18003b254  call    cs:__imp_GetCurrentThreadId
0x18003b25a  mov     eax, eax
0x18003b25c  cmp     [rdi+28h], rax
0x18003b260  jz      short loc_18003B276
0x18003b262  mov     rcx, rdi
0x18003b265  call    __Pump_BeginDeferringHelper
0x18003b26a  test    eax, eax
0x18003b26c  jz      short loc_18003B276
0x18003b26e  mov     rcx, rdi
0x18003b271  call    __Pump_BeginDeferring
0x18003b276  lea     rax, [rbp+57h+var_B8]
0x18003b27a  mov     r8d, 90h
0x18003b280  lea     r15, [r14+30h]
0x18003b284  mov     [rsp+100h+var_E0], rax
0x18003b289  mov     rcx, r15
0x18003b28c  lea     r9, [rbp+57h+var_D0]
0x18003b290  mov     rdx, rbx
0x18003b293  call    MintValueHashMap_FindOrCreateBucket
0x18003b298  mov     r13d, eax
0x18003b29b  test    eax, eax
0x18003b29d  jnz     loc_18003B3FE
0x18003b2a3  mov     rbx, [rbp+57h+var_B8]
0x18003b2a7  cmp     [rbp+57h+var_D0], sil
0x18003b2ab  jz      loc_18003B3E9
0x18003b2b1  lea     r12, [rbx+30h]
0x18003b2b5  mov     [r12], rsi
0x18003b2b9  mov     qword ptr [rbx+28h], 1
0x18003b2c1  mov     rcx, [r14]
0x18003b2c4  mov     [rbx+70h], rcx
0x18003b2c8  cmp     [r14+18h], sil
0x18003b2cc  jz      short loc_18003B2DE
0x18003b2ce  mov     rdx, rbx
0x18003b2d1  mov     rcx, r15
0x18003b2d4  call    HashMap_Remove
0x18003b2d9  jmp     loc_18003B3FE
0x18003b2de  mov     [rbx+60h], sil
0x18003b2e2  lea     rcx, [rbx+78h]
0x18003b2e6  mov     [rbx+68h], rsi
0x18003b2ea  mov     rax, cs:off_180047BA8
0x18003b2f1  mov     rax, [rax]
0x18003b2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b2f9  lea     rax, [rbp+57h+var_C0]
0x18003b2fd  mov     r8, r12
0x18003b300  lea     rdx, [rbx+18h]
0x18003b304  mov     [rsp+100h+var_E0], rax
0x18003b309  lea     r9, [rbp+57h+var_C8]
0x18003b30d  mov     rcx, r14
0x18003b310  call    GroupBase_NewGroup
0x18003b315  mov     r13d, eax
0x18003b318  test    eax, eax
0x18003b31a  jz      short loc_18003B330
0x18003b31c  mov     rdx, rbx
0x18003b31f  mov     rcx, r15
0x18003b322  call    HashMap_Remove
0x18003b327  mov     rsi, [rbp+57h+var_C8]
0x18003b32b  jmp     loc_18003B3FE
0x18003b330  mov     rcx, [r14+28h]
0x18003b334  lea     r8, GroupByUntil_UntilDelegateResultCallback
0x18003b33b  mov     [rbp+57h+var_78], rsi
0x18003b33f  lea     rdx, [rbp+57h+var_A8]
0x18003b343  mov     rsi, [rbp+57h+var_C8]
0x18003b347  xorps   xmm0, xmm0
0x18003b34a  xorps   xmm1, xmm1
0x18003b34d  mov     [rbp+57h+var_A8], rsi
0x18003b351  mov     r9, rbx
0x18003b354  mov     [rbp+57h+var_80], 0Fh
0x18003b35c  movdqu  [rbp+57h+var_A0], xmm0
0x18003b361  movdqu  [rbp+57h+var_90], xmm1
0x18003b366  call    DelegateInvoke1
0x18003b36b  mov     r13d, eax
0x18003b36e  test    eax, eax
0x18003b370  jz      short loc_18003B394
0x18003b372  mov     rax, [r12+18h]
0x18003b377  test    rax, rax
0x18003b37a  jz      loc_18003B2CE
0x18003b380  mov     rcx, [r12]
0x18003b384  xor     r8d, r8d
0x18003b387  mov     edx, r13d
0x18003b38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b38f  jmp     loc_18003B2CE
0x18003b394  mov     rdx, [rbp+57h+var_C0]
0x18003b398  xorps   xmm0, xmm0
0x18003b39b  mov     rax, rdx
0x18003b39e  mov     [rbp+57h+var_70], rdx
0x18003b3a2  neg     rax
0x18003b3a5  mov     [rbp+57h+var_48], 0Fh
0x18003b3ac  mov     rax, cs:off_180047BB0
0x18003b3b3  lea     rdx, [rbp+57h+var_70]
0x18003b3b7  sbb     ecx, ecx
0x18003b3b9  mov     [rbp+57h+var_40], 0
0x18003b3c1  not     ecx
0x18003b3c3  xorps   xmm1, xmm1
0x18003b3c6  and     ecx, 20000000h
0x18003b3cc  mov     [rbp+57h+var_44], ecx
0x18003b3cf  mov     rcx, [r14]
0x18003b3d2  movdqu  [rbp+57h+var_68], xmm0
0x18003b3d7  movdqu  [rbp+57h+var_58], xmm1
0x18003b3dc  mov     rax, [rax+20h]
0x18003b3e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3e5  mov     r12, [rbp+57h+var_B0]
0x18003b3e9  mov     rax, [rbx+38h]
0x18003b3ed  test    rax, rax
0x18003b3f0  jz      short loc_18003B3FE
0x18003b3f2  mov     rcx, [rbx+30h]
0x18003b3f6  mov     rdx, r12
0x18003b3f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3fe  test    rsi, rsi
0x18003b401  jz      short loc_18003B417
0x18003b403  mov     rax, [rsi]
0x18003b406  test    rax, rax
0x18003b409  jz      short loc_18003B417
0x18003b40b  mov     rax, [rax+10h]
0x18003b40f  mov     rcx, rsi
0x18003b412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b417  mov     rcx, [rbp+57h+var_C0]
0x18003b41b  test    rcx, rcx
0x18003b41e  jz      short loc_18003B431
0x18003b420  mov     rax, [rcx]
0x18003b423  test    rax, rax
0x18003b426  jz      short loc_18003B431
0x18003b428  mov     rax, [rax+10h]
0x18003b42c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b431  call    cs:__imp_GetCurrentThreadId
0x18003b437  mov     eax, eax
0x18003b439  cmp     [rdi+28h], rax
0x18003b43d  jz      short loc_18003B453
0x18003b43f  mov     rcx, rdi
0x18003b442  call    __Pump_EndDeferringHelper
0x18003b447  test    eax, eax
0x18003b449  jz      short loc_18003B453
0x18003b44b  mov     rcx, rdi
0x18003b44e  call    __Pump_EndDeferring
0x18003b453  mov     eax, r13d
0x18003b456  mov     rcx, [rbp+57h+var_38]
0x18003b45a  xor     rcx, rsp; StackCookie
0x18003b45d  call    __security_check_cookie
0x18003b462  mov     rbx, [rsp+100h+arg_18]
0x18003b46a  add     rsp, 0D0h
0x18003b471  pop     r15
0x18003b473  pop     r14
0x18003b475  pop     r13
0x18003b477  pop     r12
0x18003b479  pop     rdi
0x18003b47a  pop     rsi
0x18003b47b  pop     rbp
0x18003b47c  retn
```
