# CWSDPublisher::PublishInitialCollection(IFunctionInstanceCollection *)

- ea: `0x18000399c`
- end: `0x180003adf`
- name: `?PublishInitialCollection@CWSDPublisher@@IEAAJPEAUIFunctionInstanceCollection@@@Z`
- size: `323`
- prototype: `__int64 __fastcall(CWSDPublisher *__hidden this, struct IFunctionInstanceCollection *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800022b4`

## callees

- `0x18000356c`
- `0x18000399c`
- `0x180003ae8`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003ab1`

## pseudocode

```c
__int64 __fastcall CWSDPublisher::PublishInitialCollection(CWSDPublisher *this, struct IFunctionInstanceCollection *a2)
{
  struct IFunctionInstanceCollectionVtbl *lpVtbl; // rax
  unsigned int v6; // ebx
  unsigned int v7; // edi
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  void *v11; // rcx
  const unsigned __int16 *v12; // rdx
  const struct _EVENT_DESCRIPTOR *v13; // rcx
  unsigned int v14; // eax
  unsigned int v15; // [rsp+58h] [rbp+38h] BYREF
  struct IFunctionInstance *v16; // [rsp+60h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+68h] [rbp+48h] BYREF

  if ( !a2 )
    return 2147942487LL;
  lpVtbl = a2->lpVtbl;
  v15 = 0;
  v16 = 0;
  v6 = ((__int64 (__fastcall *)(struct IFunctionInstanceCollection *, unsigned int *))lpVtbl->GetCount)(a2, &v15);
  if ( !v6 )
  {
    v7 = 0;
    if ( v15 )
    {
      while ( 1 )
      {
        v6 = ((__int64 (__fastcall *)(struct IFunctionInstanceCollection *, _QWORD, struct IFunctionInstance **))a2->lpVtbl->Item)(
               a2,
               v7,
               &v16);
        if ( !v6 )
          break;
LABEL_21:
        if ( ++v7 >= v15 )
          return v6;
      }
      v8 = CWSDPublisher::PublishNewInstance(this, v16);
      pv = 0;
      if ( v8 != 1 )
        v6 = v8;
      v9 = ((__int64 (__fastcall *)(struct IFunctionInstance *, LPVOID *))v16->lpVtbl->GetID)(v16, &pv);
      if ( v6 )
      {
        if ( v9 )
        {
          v12 = L"Unknown";
          pv = L"Unknown";
        }
        else
        {
          v12 = (const unsigned __int16 *)pv;
        }
        if ( v6 == -2147024742 )
        {
          v13 = (const struct _EVENT_DESCRIPTOR *)ErrorMetSize;
        }
        else
        {
          v13 = (const struct _EVENT_DESCRIPTOR *)ErrorPubCount;
          if ( v6 != -2147024682 )
            v13 = &ErrorPublish;
        }
        v14 = LogEvent(v13, v12);
        v11 = pv;
        v6 = v14;
        if ( !pv )
          goto LABEL_20;
      }
      else
      {
        v6 = v9;
        if ( v9 )
        {
LABEL_20:
          ((void (__fastcall *)(struct IFunctionInstance *))v16->lpVtbl->Release)(v16);
          goto LABEL_21;
        }
        v10 = LogEvent(&EventPublish, (const unsigned __int16 *)pv);
        v11 = pv;
        v6 = v10;
      }
      CoTaskMemFree(v11);
      goto LABEL_20;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000399c  push    rbp
0x18000399e  push    rbx
0x18000399f  push    rsi
0x1800039a0  push    rdi
0x1800039a1  push    r14
0x1800039a3  mov     rbp, rsp
0x1800039a6  sub     rsp, 20h
0x1800039aa  mov     rsi, rdx
0x1800039ad  mov     r14, rcx
0x1800039b0  test    rdx, rdx
0x1800039b3  jnz     short loc_1800039BF
0x1800039b5  mov     eax, 80070057h
0x1800039ba  jmp     loc_180003AD4
0x1800039bf  mov     rax, [rdx]
0x1800039c2  mov     rcx, rsi
0x1800039c5  lea     rdx, [rbp+arg_8]
0x1800039c9  mov     [rbp+arg_8], 0
0x1800039d0  mov     [rbp+arg_10], 0
0x1800039d8  mov     rax, [rax+18h]
0x1800039dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039e1  mov     ebx, eax
0x1800039e3  test    eax, eax
0x1800039e5  jnz     loc_180003AD2
0x1800039eb  xor     edi, edi
0x1800039ed  cmp     [rbp+arg_8], edi
0x1800039f0  jbe     loc_180003AD2
0x1800039f6  mov     rax, [rsi]
0x1800039f9  lea     r8, [rbp+arg_10]
0x1800039fd  mov     edx, edi
0x1800039ff  mov     rcx, rsi
0x180003a02  mov     rax, [rax+28h]
0x180003a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a0b  mov     ebx, eax
0x180003a0d  test    eax, eax
0x180003a0f  jnz     loc_180003AC7
0x180003a15  mov     rdx, [rbp+arg_10]; struct IFunctionInstance *
0x180003a19  mov     rcx, r14; this
0x180003a1c  call    ?PublishNewInstance@CWSDPublisher@@IEAAJPEAUIFunctionInstance@@@Z; CWSDPublisher::PublishNewInstance(IFunctionInstance *)
0x180003a21  mov     rcx, [rbp+arg_10]
0x180003a25  lea     rdx, [rbp+pv]
0x180003a29  cmp     eax, 1
0x180003a2c  mov     [rbp+pv], 0
0x180003a34  cmovnz  ebx, eax
0x180003a37  mov     rax, [rcx]
0x180003a3a  mov     rax, [rax+20h]
0x180003a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a43  test    ebx, ebx
0x180003a45  jnz     short loc_180003A65
0x180003a47  mov     ebx, eax
0x180003a49  test    eax, eax
0x180003a4b  jnz     short loc_180003AB7
0x180003a4d  mov     rdx, [rbp+pv]; unsigned __int16 *
0x180003a51  lea     rcx, EventPublish; struct _EVENT_DESCRIPTOR *
0x180003a58  call    ?LogEvent@@YAJPEBU_EVENT_DESCRIPTOR@@PEBG@Z; LogEvent(_EVENT_DESCRIPTOR const *,ushort const *)
0x180003a5d  mov     rcx, [rbp+pv]
0x180003a61  mov     ebx, eax
0x180003a63  jmp     short loc_180003AB1
0x180003a65  test    eax, eax
0x180003a67  jz      short loc_180003A76
0x180003a69  lea     rdx, aUnknown; "Unknown"
0x180003a70  mov     [rbp+pv], rdx
0x180003a74  jmp     short loc_180003A7A
0x180003a76  mov     rdx, [rbp+pv]; unsigned __int16 *
0x180003a7a  cmp     ebx, 8007009Ah
0x180003a80  jnz     short loc_180003A8B
0x180003a82  lea     rcx, ErrorMetSize
0x180003a89  jmp     short loc_180003AA1
0x180003a8b  lea     rcx, ErrorPubCount
0x180003a92  cmp     ebx, 800700D6h
0x180003a98  jz      short loc_180003AA1
0x180003a9a  lea     rcx, ErrorPublish; struct _EVENT_DESCRIPTOR *
0x180003aa1  call    ?LogEvent@@YAJPEBU_EVENT_DESCRIPTOR@@PEBG@Z; LogEvent(_EVENT_DESCRIPTOR const *,ushort const *)
0x180003aa6  mov     rcx, [rbp+pv]; pv
0x180003aaa  mov     ebx, eax
0x180003aac  test    rcx, rcx
0x180003aaf  jz      short loc_180003AB7
0x180003ab1  call    cs:__imp_CoTaskMemFree
0x180003ab7  mov     rcx, [rbp+arg_10]
0x180003abb  mov     rax, [rcx]
0x180003abe  mov     rax, [rax+10h]
0x180003ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ac7  inc     edi
0x180003ac9  cmp     edi, [rbp+arg_8]
0x180003acc  jb      loc_1800039F6
0x180003ad2  mov     eax, ebx
0x180003ad4  add     rsp, 20h
0x180003ad8  pop     r14
0x180003ada  pop     rdi
0x180003adb  pop     rsi
0x180003adc  pop     rbx
0x180003add  pop     rbp
0x180003ade  retn
```
