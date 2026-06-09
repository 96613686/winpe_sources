# CWSDPublisher::OnUpdate(tagQueryUpdateAction,unsigned __int64,IFunctionInstance *)

- ea: `0x1800036b0`
- end: `0x180003890`
- name: `?OnUpdate@CWSDPublisher@@UEAAJW4tagQueryUpdateAction@@_KPEAUIFunctionInstance@@@Z`
- size: `480`
- prototype: `__int64 __fastcall(CWSDPublisher *this, enum tagQueryUpdateAction, __int64, struct IFunctionInstance *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180001f24`
- `0x180001f70`
- `0x18000356c`
- `0x1800036b0`
- `0x180003ae8`
- `0x180004498`
- `0x180004640`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003831`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003831`

## pseudocode

```c
__int64 __fastcall CWSDPublisher::OnUpdate(
        CWSDPublisher *this,
        enum tagQueryUpdateAction a2,
        __int64 a3,
        struct IFunctionInstance *a4)
{
  _QWORD *v7; // rcx
  unsigned int updated; // ebx
  __int64 v9; // rdx
  int v10; // edi
  unsigned int v11; // eax
  struct IFunctionInstanceVtbl *lpVtbl; // rax
  const struct _EVENT_DESCRIPTOR *v13; // rcx
  unsigned int v14; // eax
  void *v15; // rcx
  unsigned int v16; // eax
  unsigned int v17; // eax
  const unsigned __int16 *v18; // rdx
  const struct _EVENT_DESCRIPTOR *v19; // rcx
  unsigned int v20; // eax
  int v21; // eax
  bool v22; // cf
  LPVOID pv; // [rsp+88h] [rbp+50h] BYREF

  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a4 )
  {
    updated = -2147024809;
    if ( v7 != &WPP_GLOBAL_Control && *((_BYTE *)v7 + 25) >= 2u )
    {
      v9 = 31;
LABEL_39:
      WPP_SF_sqd(v7[2], v9, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids);
      return updated;
    }
    return updated;
  }
  updated = 0;
  if ( a2 == QUA_ADD )
  {
    v16 = CWSDPublisher::PublishNewInstance(this, a4);
    pv = 0;
    if ( v16 != 1 )
      updated = v16;
    v17 = ((__int64 (__fastcall *)(struct IFunctionInstance *, LPVOID *))a4->lpVtbl->GetID)(a4, &pv);
    if ( updated )
    {
      if ( v17 )
      {
        v18 = L"Unknown";
        pv = L"Unknown";
      }
      else
      {
        v18 = (const unsigned __int16 *)pv;
      }
      if ( updated == -2147024742 )
      {
        v19 = (const struct _EVENT_DESCRIPTOR *)ErrorMetSize;
      }
      else
      {
        v19 = (const struct _EVENT_DESCRIPTOR *)ErrorPubCount;
        if ( updated != -2147024682 )
          v19 = &ErrorPublish;
      }
      v20 = LogEvent(v19, v18);
      v15 = pv;
      updated = v20;
      if ( !pv )
      {
LABEL_32:
        if ( !updated )
        {
          v7 = WPP_GLOBAL_Control;
          goto LABEL_34;
        }
LABEL_35:
        v7 = WPP_GLOBAL_Control;
        v21 = 0;
        v22 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
        goto LABEL_36;
      }
LABEL_31:
      CoTaskMemFree(v15);
      goto LABEL_32;
    }
    updated = v17;
    if ( v17 )
      goto LABEL_35;
    v13 = &EventPublish;
LABEL_17:
    v14 = LogEvent(v13, (const unsigned __int16 *)pv);
    v15 = pv;
    updated = v14;
    goto LABEL_31;
  }
  v10 = a2 - 1;
  if ( !v10 )
  {
    v11 = CWSDPublisher::UnPublishInstance(this, a4);
    if ( v11 != 1 )
      updated = v11;
    if ( updated )
      goto LABEL_35;
    lpVtbl = a4->lpVtbl;
    pv = 0;
    updated = ((__int64 (__fastcall *)(struct IFunctionInstance *, LPVOID *))lpVtbl->GetID)(a4, &pv);
    if ( updated )
      goto LABEL_35;
    v13 = &EventUnPublish;
    goto LABEL_17;
  }
  if ( v10 == 1 )
  {
    updated = CWSDPublisher::UpdatePublishedInstance(this, a4);
    goto LABEL_32;
  }
LABEL_34:
  v21 = 0;
  v22 = *((_BYTE *)v7 + 25) < 4u;
LABEL_36:
  if ( v7 != &WPP_GLOBAL_Control )
  {
    LOBYTE(v21) = !v22;
    if ( v21 )
    {
      v9 = 32;
      goto LABEL_39;
    }
  }
  return updated;
}

```

## disassembly

```asm
0x1800036b0  push    rbp
0x1800036b2  push    rbx
0x1800036b3  push    rsi
0x1800036b4  push    rdi
0x1800036b5  push    r12
0x1800036b7  push    r14
0x1800036b9  mov     rbp, rsp
0x1800036bc  sub     rsp, 38h
0x1800036c0  mov     rsi, r9
0x1800036c3  mov     edi, edx
0x1800036c5  mov     r14, rcx
0x1800036c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036cf  lea     r12, WPP_GLOBAL_Control
0x1800036d6  cmp     rcx, r12
0x1800036d9  jz      short loc_180003702
0x1800036db  cmp     byte ptr [rcx+19h], 4
0x1800036df  jb      short loc_180003702
0x1800036e1  mov     rcx, [rcx+10h]
0x1800036e5  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x1800036ec  mov     edx, 1Eh
0x1800036f1  mov     [rsp+38h+var_18], r14
0x1800036f6  call    WPP_SF_sq
0x1800036fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180003702  test    rsi, rsi
0x180003705  jnz     short loc_180003727
0x180003707  mov     ebx, 80070057h
0x18000370c  cmp     rcx, r12
0x18000370f  jz      loc_180003881
0x180003715  cmp     byte ptr [rcx+19h], 2
0x180003719  jb      loc_180003881
0x18000371f  lea     edx, [rsi+1Fh]
0x180003722  jmp     loc_180003868
0x180003727  xor     ebx, ebx
0x180003729  test    edi, edi
0x18000372b  jz      short loc_1800037A6
0x18000372d  sub     edi, 1
0x180003730  jz      short loc_18000374D
0x180003732  cmp     edi, 1
0x180003735  jnz     loc_180003842
0x18000373b  mov     rdx, rsi; struct IFunctionInstance *
0x18000373e  mov     rcx, r14; this
0x180003741  call    ?UpdatePublishedInstance@CWSDPublisher@@IEAAJPEAUIFunctionInstance@@@Z; CWSDPublisher::UpdatePublishedInstance(IFunctionInstance *)
0x180003746  mov     ebx, eax
0x180003748  jmp     loc_180003837
0x18000374d  mov     rdx, rsi; struct IFunctionInstance *
0x180003750  mov     rcx, r14; this
0x180003753  call    ?UnPublishInstance@CWSDPublisher@@IEAAJPEAUIFunctionInstance@@@Z; CWSDPublisher::UnPublishInstance(IFunctionInstance *)
0x180003758  cmp     eax, 1
0x18000375b  cmovnz  ebx, eax
0x18000375e  test    ebx, ebx
0x180003760  jnz     loc_18000384A
0x180003766  mov     rax, [rsi]
0x180003769  lea     rdx, [rbp+pv]
0x18000376d  mov     rcx, rsi
0x180003770  mov     [rbp+pv], 0
0x180003778  mov     rax, [rax+20h]
0x18000377c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003781  mov     ebx, eax
0x180003783  test    eax, eax
0x180003785  jnz     loc_18000384A
0x18000378b  lea     rcx, EventUnPublish; struct _EVENT_DESCRIPTOR *
0x180003792  mov     rdx, [rbp+pv]; unsigned __int16 *
0x180003796  call    ?LogEvent@@YAJPEBU_EVENT_DESCRIPTOR@@PEBG@Z; LogEvent(_EVENT_DESCRIPTOR const *,ushort const *)
0x18000379b  mov     rcx, [rbp+pv]
0x18000379f  mov     ebx, eax
0x1800037a1  jmp     loc_180003831
0x1800037a6  mov     rdx, rsi; struct IFunctionInstance *
0x1800037a9  mov     rcx, r14; this
0x1800037ac  call    ?PublishNewInstance@CWSDPublisher@@IEAAJPEAUIFunctionInstance@@@Z; CWSDPublisher::PublishNewInstance(IFunctionInstance *)
0x1800037b1  cmp     eax, 1
0x1800037b4  mov     [rbp+pv], 0
0x1800037bc  lea     rdx, [rbp+pv]
0x1800037c0  mov     rcx, rsi
0x1800037c3  cmovnz  ebx, eax
0x1800037c6  mov     rax, [rsi]
0x1800037c9  mov     rax, [rax+20h]
0x1800037cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037d2  test    ebx, ebx
0x1800037d4  jnz     short loc_1800037E5
0x1800037d6  mov     ebx, eax
0x1800037d8  test    eax, eax
0x1800037da  jnz     short loc_18000384A
0x1800037dc  lea     rcx, EventPublish
0x1800037e3  jmp     short loc_180003792
0x1800037e5  test    eax, eax
0x1800037e7  jz      short loc_1800037F6
0x1800037e9  lea     rdx, aUnknown; "Unknown"
0x1800037f0  mov     [rbp+pv], rdx
0x1800037f4  jmp     short loc_1800037FA
0x1800037f6  mov     rdx, [rbp+pv]; unsigned __int16 *
0x1800037fa  cmp     ebx, 8007009Ah
0x180003800  jnz     short loc_18000380B
0x180003802  lea     rcx, ErrorMetSize
0x180003809  jmp     short loc_180003821
0x18000380b  lea     rcx, ErrorPubCount
0x180003812  cmp     ebx, 800700D6h
0x180003818  jz      short loc_180003821
0x18000381a  lea     rcx, ErrorPublish; struct _EVENT_DESCRIPTOR *
0x180003821  call    ?LogEvent@@YAJPEBU_EVENT_DESCRIPTOR@@PEBG@Z; LogEvent(_EVENT_DESCRIPTOR const *,ushort const *)
0x180003826  mov     rcx, [rbp+pv]; pv
0x18000382a  mov     ebx, eax
0x18000382c  test    rcx, rcx
0x18000382f  jz      short loc_180003837
0x180003831  call    cs:__imp_CoTaskMemFree
0x180003837  test    ebx, ebx
0x180003839  jnz     short loc_18000384A
0x18000383b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003842  xor     eax, eax
0x180003844  cmp     byte ptr [rcx+19h], 4
0x180003848  jmp     short loc_180003857
0x18000384a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003851  xor     eax, eax
0x180003853  cmp     byte ptr [rcx+19h], 2
0x180003857  setnb   al
0x18000385a  cmp     rcx, r12
0x18000385d  jz      short loc_180003881
0x18000385f  test    eax, eax
0x180003861  jz      short loc_180003881
0x180003863  mov     edx, 20h ; ' '
0x180003868  mov     rcx, [rcx+10h]
0x18000386c  lea     r8, WPP_f41d40c9e3fd377be4a162125b6d1337_Traceguids
0x180003873  mov     [rsp+38h+var_10], ebx
0x180003877  mov     [rsp+38h+var_18], r14
0x18000387c  call    WPP_SF_sqd
0x180003881  mov     eax, ebx
0x180003883  add     rsp, 38h
0x180003887  pop     r14
0x180003889  pop     r12
0x18000388b  pop     rdi
0x18000388c  pop     rsi
0x18000388d  pop     rbx
0x18000388e  pop     rbp
0x18000388f  retn
```
