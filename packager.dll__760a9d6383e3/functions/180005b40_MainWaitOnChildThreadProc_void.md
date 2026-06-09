# MainWaitOnChildThreadProc(void *)

- ea: `0x180005b40`
- end: `0x180005c7d`
- name: `?MainWaitOnChildThreadProc@@YAKPEAX@Z`
- size: `317`
- prototype: `__int64 __fastcall(__int64 *lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180005b40`
- `0x18000a718`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005bdf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180005bdf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005c23`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180005bb7`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x180005bb7`

## pseudocode

```c
__int64 __fastcall MainWaitOnChildThreadProc(__int64 *lpThreadParameter)
{
  __int64 v1; // rdi
  HRESULT InterfaceAndReleaseStream; // eax
  int v4; // esi
  IStream *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  LPVOID v8; // rcx
  __int64 v9; // rcx
  LPVOID ppv; // [rsp+50h] [rbp+8h] BYREF

  v1 = *lpThreadParameter;
  ppv = 0;
  if ( !v1 )
    goto LABEL_12;
  *lpThreadParameter = 0;
  if ( *(_DWORD *)(v1 + 24) != 2 )
  {
    v5 = *(IStream **)(v1 + 16);
    *(_QWORD *)(v1 + 16) = 0;
    InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(v5, &GUID_b722bccb_4e68_101b_a2bc_00aa00404770, &ppv);
    goto LABEL_7;
  }
  if ( *(_QWORD *)(v1 + 32) )
  {
    InterfaceAndReleaseStream = (*(__int64 (__fastcall **)(_QWORD, GUID *, LPVOID *))(**(_QWORD **)(v1 + 32) + 24LL))(
                                  *(_QWORD *)(v1 + 32),
                                  &GUID_b722bccb_4e68_101b_a2bc_00aa00404770,
                                  &ppv);
LABEL_7:
    v4 = InterfaceAndReleaseStream;
    goto LABEL_8;
  }
  v4 = -2147024809;
LABEL_8:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  if ( v4 >= 0 )
  {
    v6 = (void *)lpThreadParameter[1];
    if ( v6 == (void *)-1LL || !WaitForSingleObject(v6, 0xFFFFFFFF) )
      (*(void (__fastcall **)(LPVOID, SID *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppv + 32LL))(
        ppv,
        &SID_targetGUID,
        0,
        0,
        0,
        0);
  }
LABEL_12:
  v7 = (void *)lpThreadParameter[1];
  if ( v7 != (void *)-1LL )
    CloseHandle(v7);
  v8 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = *lpThreadParameter;
  if ( *lpThreadParameter )
  {
    *lpThreadParameter = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  operator delete(lpThreadParameter);
  return 0;
}

```

## disassembly

```asm
0x180005b40  mov     r11, rsp
0x180005b43  mov     [r11+10h], rbx
0x180005b47  mov     [r11+18h], rsi
0x180005b4b  push    rdi
0x180005b4c  sub     rsp, 40h
0x180005b50  mov     rdi, [rcx]
0x180005b53  mov     rbx, rcx
0x180005b56  mov     qword ptr [r11+8], 0
0x180005b5e  test    rdi, rdi
0x180005b61  jz      loc_180005C19
0x180005b67  mov     qword ptr [rcx], 0
0x180005b6e  cmp     dword ptr [rdi+18h], 2
0x180005b72  jnz     short loc_180005B9F
0x180005b74  cmp     qword ptr [rdi+20h], 0
0x180005b79  jz      short loc_180005B98
0x180005b7b  mov     rcx, [rdi+20h]
0x180005b7f  lea     r8, [r11+8]
0x180005b83  lea     rdx, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770
0x180005b8a  mov     rax, [rcx]
0x180005b8d  mov     rax, [rax+18h]
0x180005b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b96  jmp     short loc_180005BBD
0x180005b98  mov     esi, 80070057h
0x180005b9d  jmp     short loc_180005BBF
0x180005b9f  mov     rcx, [rdi+10h]; pStm
0x180005ba3  lea     r8, [rsp+48h+ppv]; ppv
0x180005ba8  lea     rdx, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770; iid
0x180005baf  mov     qword ptr [rdi+10h], 0
0x180005bb7  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x180005bbd  mov     esi, eax
0x180005bbf  mov     rdx, [rdi]
0x180005bc2  mov     rcx, rdi
0x180005bc5  mov     rax, [rdx+10h]
0x180005bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bce  test    esi, esi
0x180005bd0  js      short loc_180005C19
0x180005bd2  mov     rcx, [rbx+8]; hHandle
0x180005bd6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180005bda  jz      short loc_180005BE9
0x180005bdc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180005bdf  call    cs:__imp_WaitForSingleObject
0x180005be5  test    eax, eax
0x180005be7  jnz     short loc_180005C19
0x180005be9  mov     rcx, [rsp+48h+ppv]
0x180005bee  lea     rdx, SID_targetGUID
0x180005bf5  mov     [rsp+48h+var_20], 0
0x180005bfe  xor     r9d, r9d
0x180005c01  xor     r8d, r8d
0x180005c04  mov     [rsp+48h+var_28], 0
0x180005c0d  mov     rax, [rcx]
0x180005c10  mov     rax, [rax+20h]
0x180005c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c19  mov     rcx, [rbx+8]; hObject
0x180005c1d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180005c21  jz      short loc_180005C29
0x180005c23  call    cs:__imp_CloseHandle
0x180005c29  mov     rcx, [rsp+48h+ppv]
0x180005c2e  test    rcx, rcx
0x180005c31  jz      short loc_180005C48
0x180005c33  mov     [rsp+48h+ppv], 0
0x180005c3c  mov     rax, [rcx]
0x180005c3f  mov     rax, [rax+10h]
0x180005c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c48  mov     rcx, [rbx]
0x180005c4b  test    rcx, rcx
0x180005c4e  jz      short loc_180005C63
0x180005c50  mov     qword ptr [rbx], 0
0x180005c57  mov     rax, [rcx]
0x180005c5a  mov     rax, [rax+10h]
0x180005c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c63  mov     rcx, rbx; lpMem
0x180005c66  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005c6b  mov     rbx, [rsp+48h+arg_8]
0x180005c70  xor     eax, eax
0x180005c72  mov     rsi, [rsp+48h+arg_10]
0x180005c77  add     rsp, 40h
0x180005c7b  pop     rdi
0x180005c7c  retn
```
