# CWSDPublisher::UpdatePublishedInstance(IFunctionInstance *)

- ea: `0x180004640`
- end: `0x18000476a`
- name: `?UpdatePublishedInstance@CWSDPublisher@@IEAAJPEAUIFunctionInstance@@@Z`
- size: `298`
- prototype: `__int64 __fastcall(CWSDPublisher *__hidden this, struct IFunctionInstance *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800036b0`

## callees

- `0x18000356c`
- `0x180003ae8`
- `0x180004498`
- `0x180004640`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800046b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004759`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800046b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004759`

## pseudocode

```c
__int64 __fastcall CWSDPublisher::UpdatePublishedInstance(CWSDPublisher *this, struct IFunctionInstance *a2)
{
  unsigned int v4; // ebx
  unsigned int v5; // eax
  struct IFunctionInstanceVtbl *lpVtbl; // rax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  void *v10; // rcx
  const unsigned __int16 *v11; // rdx
  const struct _EVENT_DESCRIPTOR *v12; // rcx
  unsigned int v13; // eax
  LPVOID pv; // [rsp+58h] [rbp+30h] BYREF

  if ( !a2 )
    return (unsigned int)-2147024809;
  v5 = CWSDPublisher::UnPublishInstance(this, a2);
  v4 = 0;
  if ( v5 != 1 )
    v4 = v5;
  if ( !v4 )
  {
    lpVtbl = a2->lpVtbl;
    pv = 0;
    v4 = ((__int64 (__fastcall *)(struct IFunctionInstance *, LPVOID *))lpVtbl->GetID)(a2, &pv);
    if ( !v4 )
    {
      v4 = LogEvent(&EventUnPublish, (const unsigned __int16 *)pv);
      CoTaskMemFree(pv);
      if ( !v4 )
      {
        v7 = CWSDPublisher::PublishNewInstance(this, a2);
        pv = 0;
        if ( v7 != 1 )
          v4 = v7;
        v8 = ((__int64 (__fastcall *)(struct IFunctionInstance *, LPVOID *))a2->lpVtbl->GetID)(a2, &pv);
        if ( !v4 )
        {
          v4 = v8;
          if ( v8 )
            return v4;
          v9 = LogEvent(&EventPublish, (const unsigned __int16 *)pv);
          v10 = pv;
          v4 = v9;
LABEL_21:
          CoTaskMemFree(v10);
          return v4;
        }
        if ( v8 )
        {
          v11 = L"Unknown";
          pv = L"Unknown";
        }
        else
        {
          v11 = (const unsigned __int16 *)pv;
        }
        if ( v4 == -2147024742 )
        {
          v12 = (const struct _EVENT_DESCRIPTOR *)ErrorMetSize;
        }
        else
        {
          v12 = (const struct _EVENT_DESCRIPTOR *)ErrorPubCount;
          if ( v4 != -2147024682 )
            v12 = &ErrorPublish;
        }
        v13 = LogEvent(v12, v11);
        v10 = pv;
        v4 = v13;
        if ( pv )
          goto LABEL_21;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180004640  push    rbp
0x180004642  push    rbx
0x180004643  push    rsi
0x180004644  push    rdi
0x180004645  mov     rbp, rsp
0x180004648  sub     rsp, 28h
0x18000464c  mov     rdi, rdx
0x18000464f  mov     rsi, rcx
0x180004652  test    rdx, rdx
0x180004655  jnz     short loc_180004661
0x180004657  mov     ebx, 80070057h
0x18000465c  jmp     loc_18000475F
0x180004661  call    ?UnPublishInstance@CWSDPublisher@@IEAAJPEAUIFunctionInstance@@@Z; CWSDPublisher::UnPublishInstance(IFunctionInstance *)
0x180004666  xor     ebx, ebx
0x180004668  cmp     eax, 1
0x18000466b  cmovnz  ebx, eax
0x18000466e  test    ebx, ebx
0x180004670  jnz     loc_18000475F
0x180004676  mov     rax, [rdi]
0x180004679  lea     rdx, [rbp+pv]
0x18000467d  mov     rcx, rdi
0x180004680  mov     [rbp+pv], 0
0x180004688  mov     rax, [rax+20h]
0x18000468c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004691  mov     ebx, eax
0x180004693  test    eax, eax
0x180004695  jnz     loc_18000475F
0x18000469b  mov     rdx, [rbp+pv]; unsigned __int16 *
0x18000469f  lea     rcx, EventUnPublish; struct _EVENT_DESCRIPTOR *
0x1800046a6  call    ?LogEvent@@YAJPEBU_EVENT_DESCRIPTOR@@PEBG@Z; LogEvent(_EVENT_DESCRIPTOR const *,ushort const *)
0x1800046ab  mov     rcx, [rbp+pv]; pv
0x1800046af  mov     ebx, eax
0x1800046b1  call    cs:__imp_CoTaskMemFree
0x1800046b7  test    ebx, ebx
0x1800046b9  jnz     loc_18000475F
0x1800046bf  mov     rdx, rdi; struct IFunctionInstance *
0x1800046c2  mov     rcx, rsi; this
0x1800046c5  call    ?PublishNewInstance@CWSDPublisher@@IEAAJPEAUIFunctionInstance@@@Z; CWSDPublisher::PublishNewInstance(IFunctionInstance *)
0x1800046ca  cmp     eax, 1
0x1800046cd  mov     [rbp+pv], 0
0x1800046d5  lea     rdx, [rbp+pv]
0x1800046d9  mov     rcx, rdi
0x1800046dc  cmovnz  ebx, eax
0x1800046df  mov     rax, [rdi]
0x1800046e2  mov     rax, [rax+20h]
0x1800046e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046eb  test    ebx, ebx
0x1800046ed  jnz     short loc_18000470D
0x1800046ef  mov     ebx, eax
0x1800046f1  test    eax, eax
0x1800046f3  jnz     short loc_18000475F
0x1800046f5  mov     rdx, [rbp+pv]; unsigned __int16 *
0x1800046f9  lea     rcx, EventPublish; struct _EVENT_DESCRIPTOR *
0x180004700  call    ?LogEvent@@YAJPEBU_EVENT_DESCRIPTOR@@PEBG@Z; LogEvent(_EVENT_DESCRIPTOR const *,ushort const *)
0x180004705  mov     rcx, [rbp+pv]
0x180004709  mov     ebx, eax
0x18000470b  jmp     short loc_180004759
0x18000470d  test    eax, eax
0x18000470f  jz      short loc_18000471E
0x180004711  lea     rdx, aUnknown; "Unknown"
0x180004718  mov     [rbp+pv], rdx
0x18000471c  jmp     short loc_180004722
0x18000471e  mov     rdx, [rbp+pv]; unsigned __int16 *
0x180004722  cmp     ebx, 8007009Ah
0x180004728  jnz     short loc_180004733
0x18000472a  lea     rcx, ErrorMetSize
0x180004731  jmp     short loc_180004749
0x180004733  lea     rcx, ErrorPubCount
0x18000473a  cmp     ebx, 800700D6h
0x180004740  jz      short loc_180004749
0x180004742  lea     rcx, ErrorPublish; struct _EVENT_DESCRIPTOR *
0x180004749  call    ?LogEvent@@YAJPEBU_EVENT_DESCRIPTOR@@PEBG@Z; LogEvent(_EVENT_DESCRIPTOR const *,ushort const *)
0x18000474e  mov     rcx, [rbp+pv]; pv
0x180004752  mov     ebx, eax
0x180004754  test    rcx, rcx
0x180004757  jz      short loc_18000475F
0x180004759  call    cs:__imp_CoTaskMemFree
0x18000475f  mov     eax, ebx
0x180004761  add     rsp, 28h
0x180004765  pop     rdi
0x180004766  pop     rsi
0x180004767  pop     rbx
0x180004768  pop     rbp
0x180004769  retn
```
