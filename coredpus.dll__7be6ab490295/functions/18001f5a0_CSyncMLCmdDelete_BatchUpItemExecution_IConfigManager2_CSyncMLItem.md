# CSyncMLCmdDelete::BatchUpItemExecution(IConfigManager2 *,CSyncMLItem *)

- ea: `0x18001f5a0`
- end: `0x18001f798`
- name: `?BatchUpItemExecution@CSyncMLCmdDelete@@EEAAJPEAUIConfigManager2@@PEAVCSyncMLItem@@@Z`
- size: `504`
- prototype: `int(CSyncMLCmdDelete *__hidden this, struct IConfigManager2 *, struct CSyncMLItem *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800034d0`
- `0x1800038a0`
- `0x18001f5a0`
- `0x18002164c`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdDelete::BatchUpItemExecution(
        CSyncMLCmdDelete *this,
        struct IConfigManager2 *a2,
        struct CSyncMLItem *a3)
{
  struct IConfigManager2URI *TargetLocURI; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  struct IConfigManager2URI *v8; // rdi
  int v9; // ebx
  struct IConfigNode *v10; // rcx
  __int64 v11; // rdx
  struct IConfigNode *v12; // rdx
  unsigned int v14; // [rsp+30h] [rbp-30h] BYREF
  int v15; // [rsp+34h] [rbp-2Ch] BYREF
  int v16; // [rsp+38h] [rbp-28h] BYREF
  struct IConfigNode *v17; // [rsp+40h] [rbp-20h] BYREF
  __int64 v18; // [rsp+48h] [rbp-18h] BYREF
  __int64 v19; // [rsp+50h] [rbp-10h] BYREF
  int v20; // [rsp+98h] [rbp+38h] BYREF

  v14 = 0;
  v20 = 0;
  v15 = 0;
  v17 = 0;
  TargetLocURI = CSyncMLItem::GetTargetLocURI(a3);
  v18 = 0;
  v8 = TargetLocURI;
  v19 = 0;
  if ( TargetLocURI )
  {
    v9 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, unsigned int *))(*(_QWORD *)TargetLocURI + 136LL))(
           TargetLocURI,
           &v14);
    if ( v9 >= 0 )
    {
      if ( v14 > 1 )
      {
        v9 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, _QWORD, __int64 *, __int64 *))(*(_QWORD *)v8 + 80LL))(
               v8,
               v14 - 1,
               0,
               &v18,
               &v19);
        if ( v9 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(struct IConfigManager2 *, __int64, struct IConfigNode **))(*(_QWORD *)a2 + 88LL))(
                 a2,
                 v18,
                 &v17);
          if ( v9 >= 0 )
          {
            v9 = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v17 + 144LL))(v17, &v20);
            if ( v9 >= 0 )
            {
              v10 = v17;
              v11 = v19;
              *((_DWORD *)a3 + 8) = v20;
              v9 = (*(__int64 (__fastcall **)(struct IConfigNode *, __int64))(*(_QWORD *)v10 + 80LL))(v10, v11);
              if ( v9 >= 0 )
              {
                v9 = (*(__int64 (__fastcall **)(struct IConfigNode *, int *))(*(_QWORD *)v17 + 144LL))(v17, &v15);
                if ( v9 >= 0 )
                {
                  v12 = v17;
                  *((_DWORD *)a3 + 10) = v15 - v20;
                  v9 = CSyncMLItem::SetCfgNode(a3, v12, 0);
                }
              }
            }
          }
        }
      }
      else
      {
        v9 = -2046820335;
      }
    }
    if ( v18 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v18 = 0;
    }
    if ( v19 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v19 = 0;
    }
    (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  else
  {
    v9 = -2102788095;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(struct IConfigNode *))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v16 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)&word_18003715E,
      v6,
      v7,
      (__int64)&v16);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001f5a0  mov     [rsp-18h+arg_0], rbx
0x18001f5a5  mov     [rsp-18h+arg_8], rsi
0x18001f5aa  push    rbp
0x18001f5ab  push    rdi
0x18001f5ac  push    r14
0x18001f5ae  mov     rbp, rsp
0x18001f5b1  sub     rsp, 60h
0x18001f5b5  mov     rcx, r8; this
0x18001f5b8  mov     [rbp+var_30], 0
0x18001f5bf  mov     rsi, r8
0x18001f5c2  mov     [rbp+arg_18], 0
0x18001f5c9  mov     r14, rdx
0x18001f5cc  mov     [rbp+var_2C], 0
0x18001f5d3  mov     [rbp+var_20], 0
0x18001f5db  call    ?GetTargetLocURI@CSyncMLItem@@QEAAPEAUIConfigManager2URI@@XZ; CSyncMLItem::GetTargetLocURI(void)
0x18001f5e0  mov     [rbp+var_18], 0
0x18001f5e8  mov     rdi, rax
0x18001f5eb  mov     [rbp+var_10], 0
0x18001f5f3  test    rax, rax
0x18001f5f6  jnz     short loc_18001F602
0x18001f5f8  mov     ebx, 82AA0001h
0x18001f5fd  jmp     loc_18001F739
0x18001f602  mov     rax, [rax]
0x18001f605  lea     rdx, [rbp+var_30]
0x18001f609  mov     rcx, rdi
0x18001f60c  mov     rax, [rax+88h]
0x18001f613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f618  mov     ebx, eax
0x18001f61a  test    eax, eax
0x18001f61c  js      loc_18001F6F0
0x18001f622  mov     edx, [rbp+var_30]
0x18001f625  cmp     edx, 1
0x18001f628  ja      short loc_18001F634
0x18001f62a  mov     ebx, 86000011h
0x18001f62f  jmp     loc_18001F6F0
0x18001f634  mov     rax, [rdi]
0x18001f637  lea     rcx, [rbp+var_10]
0x18001f63b  mov     [rsp+60h+var_40], rcx
0x18001f640  lea     r9, [rbp+var_18]
0x18001f644  dec     edx
0x18001f646  xor     r8d, r8d
0x18001f649  mov     rcx, rdi
0x18001f64c  mov     rax, [rax+50h]
0x18001f650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f655  mov     ebx, eax
0x18001f657  test    eax, eax
0x18001f659  js      loc_18001F6F0
0x18001f65f  mov     rax, [r14]
0x18001f662  lea     r8, [rbp+var_20]
0x18001f666  mov     rdx, [rbp+var_18]
0x18001f66a  mov     rcx, r14
0x18001f66d  mov     rax, [rax+58h]
0x18001f671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f676  mov     ebx, eax
0x18001f678  test    eax, eax
0x18001f67a  js      short loc_18001F6F0
0x18001f67c  mov     rcx, [rbp+var_20]
0x18001f680  lea     rdx, [rbp+arg_18]
0x18001f684  mov     rax, [rcx]
0x18001f687  mov     rax, [rax+90h]
0x18001f68e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f693  mov     ebx, eax
0x18001f695  test    eax, eax
0x18001f697  js      short loc_18001F6F0
0x18001f699  mov     eax, [rbp+arg_18]
0x18001f69c  mov     rcx, [rbp+var_20]
0x18001f6a0  mov     rdx, [rbp+var_10]
0x18001f6a4  mov     [rsi+20h], eax
0x18001f6a7  mov     rax, [rcx]
0x18001f6aa  mov     rax, [rax+50h]
0x18001f6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6b3  mov     ebx, eax
0x18001f6b5  test    eax, eax
0x18001f6b7  js      short loc_18001F6F0
0x18001f6b9  mov     rcx, [rbp+var_20]
0x18001f6bd  lea     rdx, [rbp+var_2C]
0x18001f6c1  mov     rax, [rcx]
0x18001f6c4  mov     rax, [rax+90h]
0x18001f6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6d0  mov     ebx, eax
0x18001f6d2  test    eax, eax
0x18001f6d4  js      short loc_18001F6F0
0x18001f6d6  mov     eax, [rbp+var_2C]
0x18001f6d9  xor     r8d, r8d; unsigned int
0x18001f6dc  sub     eax, [rbp+arg_18]
0x18001f6df  mov     rcx, rsi; this
0x18001f6e2  mov     rdx, [rbp+var_20]; struct IConfigNode *
0x18001f6e6  mov     [rsi+28h], eax
0x18001f6e9  call    ?SetCfgNode@CSyncMLItem@@QEAAJPEAUIConfigNode@@K@Z; CSyncMLItem::SetCfgNode(IConfigNode *,ulong)
0x18001f6ee  mov     ebx, eax
0x18001f6f0  mov     rcx, [rbp+var_18]
0x18001f6f4  test    rcx, rcx
0x18001f6f7  jz      short loc_18001F70D
0x18001f6f9  mov     rax, [rcx]
0x18001f6fc  mov     rax, [rax+10h]
0x18001f700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f705  mov     [rbp+var_18], 0
0x18001f70d  mov     rcx, [rbp+var_10]
0x18001f711  test    rcx, rcx
0x18001f714  jz      short loc_18001F72A
0x18001f716  mov     rax, [rcx]
0x18001f719  mov     rax, [rax+10h]
0x18001f71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f722  mov     [rbp+var_10], 0
0x18001f72a  mov     rax, [rdi]
0x18001f72d  mov     rcx, rdi
0x18001f730  mov     rax, [rax+10h]
0x18001f734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f739  mov     rcx, [rbp+var_20]
0x18001f73d  test    rcx, rcx
0x18001f740  jz      short loc_18001F756
0x18001f742  mov     rax, [rcx]
0x18001f745  mov     rax, [rax+10h]
0x18001f749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f74e  mov     [rbp+var_20], 0
0x18001f756  mov     eax, cs:dword_18003E048
0x18001f75c  cmp     eax, 5
0x18001f75f  jbe     short loc_18001F780
0x18001f761  lea     rax, [rbp+var_28]
0x18001f765  mov     [rbp+var_28], ebx
0x18001f768  lea     rdx, word_18003715E
0x18001f76f  mov     [rsp+60h+var_40], rax
0x18001f774  lea     rcx, dword_18003E048
0x18001f77b  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001f780  lea     r11, [rsp+60h+var_s0]
0x18001f785  mov     eax, ebx
0x18001f787  mov     rbx, [r11+20h]
0x18001f78b  mov     rsi, [r11+28h]
0x18001f78f  mov     rsp, r11
0x18001f792  pop     r14
0x18001f794  pop     rdi
0x18001f795  pop     rbp
0x18001f796  retn
```
