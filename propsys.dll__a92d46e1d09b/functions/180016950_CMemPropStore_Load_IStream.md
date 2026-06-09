# CMemPropStore::Load(IStream *)

- ea: `0x180016950`
- end: `0x180016a4a`
- name: `?Load@CMemPropStore@@UEAAJPEAUIStream@@@Z`
- size: `250`
- prototype: `int(CMemPropStore *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180080020`

## callees

- `0x180007f40`
- `0x180016950`
- `0x1800170b0`
- `0x18006ed20`
- `0x18006fb98`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016a1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016a1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800169b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800169b8`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180016995`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800169eb`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x180016995`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x1800169eb`

## pseudocode

```c
__int64 __fastcall CMemPropStore::Load(RTL_SRWLOCK *this, struct IStream *a2)
{
  HRESULT v4; // ebx
  struct tagSERIALIZEDPROPSTORAGE *v5; // rax
  struct tagSERIALIZEDPROPSTORAGE *v6; // rdi
  size_t v7; // rax
  HRESULT v8; // eax
  struct tagSERIALIZEDPROPSTORAGE *v10; // [rsp+20h] [rbp-38h] BYREF
  unsigned int pv; // [rsp+28h] [rbp-30h] BYREF

  v4 = -2147467261;
  if ( a2 )
  {
    pv = 0;
    v4 = IStream_Read(a2, &pv, 4u);
    if ( v4 >= 0 )
    {
      if ( pv > 0x8000000 )
      {
        return (unsigned int)-2147023604;
      }
      else
      {
        v4 = 0;
        if ( pv )
        {
          v5 = (struct tagSERIALIZEDPROPSTORAGE *)CoTaskMemAlloc(pv);
          v10 = v5;
          v6 = v5;
          if ( v5 )
          {
            v7 = CTCoAllocPolicy::_CoTaskMemSize(v5);
            memset_0(v6, 0, v7);
            v4 = IStream_Read(a2, v6, pv);
            if ( v4 >= 0 )
            {
              v8 = CMemPropStore::_SetPropertyStorageMaybeStealBuffer(this - 4, &v10, pv, 1);
              v6 = v10;
              v4 = v8;
            }
            CoTaskMemFree(v6);
          }
          else
          {
            return (unsigned int)-2147024882;
          }
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180016950  mov     [rsp+arg_10], rbx
0x180016955  push    rbp
0x180016956  push    rsi
0x180016957  push    rdi
0x180016958  sub     rsp, 40h
0x18001695c  mov     rax, cs:__security_cookie
0x180016963  xor     rax, rsp
0x180016966  mov     [rsp+58h+var_28], rax
0x18001696b  mov     rsi, rdx
0x18001696e  mov     rbp, rcx
0x180016971  mov     ebx, 80004003h
0x180016976  test    rdx, rdx
0x180016979  jz      loc_180016A20
0x18001697f  mov     r8d, 4; cb
0x180016985  mov     [rsp+58h+pv], 0
0x18001698d  lea     rdx, [rsp+58h+pv]; pv
0x180016992  mov     rcx, rsi; pstm
0x180016995  call    cs:__imp_IStream_Read
0x18001699b  mov     ebx, eax
0x18001699d  test    eax, eax
0x18001699f  js      short loc_180016A20
0x1800169a1  mov     eax, [rsp+58h+pv]
0x1800169a5  cmp     eax, 8000000h
0x1800169aa  ja      loc_180016A43
0x1800169b0  xor     ebx, ebx
0x1800169b2  test    eax, eax
0x1800169b4  jz      short loc_180016A20
0x1800169b6  mov     ecx, eax; cb
0x1800169b8  call    cs:__imp_CoTaskMemAlloc
0x1800169be  mov     [rsp+58h+var_38], rax
0x1800169c3  mov     rdi, rax
0x1800169c6  test    rax, rax
0x1800169c9  jz      short loc_180016A3C
0x1800169cb  mov     rcx, rax; void *
0x1800169ce  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x1800169d3  mov     r8, rax; Size
0x1800169d6  xor     edx, edx; Val
0x1800169d8  mov     rcx, rdi; void *
0x1800169db  call    memset_0
0x1800169e0  mov     r8d, [rsp+58h+pv]; cb
0x1800169e5  mov     rdx, rdi; pv
0x1800169e8  mov     rcx, rsi; pstm
0x1800169eb  call    cs:__imp_IStream_Read
0x1800169f1  mov     ebx, eax
0x1800169f3  test    eax, eax
0x1800169f5  js      short loc_180016A17
0x1800169f7  mov     r8d, [rsp+58h+pv]; unsigned int
0x1800169fc  lea     rcx, [rbp-20h]; this
0x180016a00  mov     r9d, 1; int
0x180016a06  lea     rdx, [rsp+58h+var_38]; struct tagSERIALIZEDPROPSTORAGE **
0x180016a0b  call    ?_SetPropertyStorageMaybeStealBuffer@CMemPropStore@@AEAAJPEAPEFAUtagSERIALIZEDPROPSTORAGE@@KH@Z; CMemPropStore::_SetPropertyStorageMaybeStealBuffer(tagSERIALIZEDPROPSTORAGE * *,ulong,int)
0x180016a10  mov     rdi, [rsp+58h+var_38]
0x180016a15  mov     ebx, eax
0x180016a17  mov     rcx, rdi; pv
0x180016a1a  call    cs:__imp_CoTaskMemFree
0x180016a20  mov     eax, ebx
0x180016a22  mov     rcx, [rsp+58h+var_28]
0x180016a27  xor     rcx, rsp; StackCookie
0x180016a2a  call    __security_check_cookie
0x180016a2f  mov     rbx, [rsp+58h+arg_10]
0x180016a34  add     rsp, 40h
0x180016a38  pop     rdi
0x180016a39  pop     rsi
0x180016a3a  pop     rbp
0x180016a3b  retn
0x180016a3c  mov     ebx, 8007000Eh
0x180016a41  jmp     short loc_180016A20
0x180016a43  mov     ebx, 8007050Ch
0x180016a48  jmp     short loc_180016A20
```
