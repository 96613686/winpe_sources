# CKsOutputPin2::SetFormat(_AMMediaType *)

- ea: `0x180031360`
- end: `0x1800315ce`
- name: `?SetFormat@CKsOutputPin2@@UEAAJPEAU_AMMediaType@@@Z`
- size: `622`
- prototype: `__int64 __fastcall(CKsOutputPin2 *this, struct CMediaType *, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18001f620`
- `0x18002998c`
- `0x18002dd70`
- `0x18002f814`
- `0x180031360`
- `0x180031844`
- `0x180031d00`
- `0x180038758`
- `0x18003e22c`
- `0x180045010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180031560`
- `ole32!CoTaskMemFree` at `0x18003156f`
- `ole32!CoTaskMemFree` at `0x180031560`
- `ole32!CoTaskMemFree` at `0x18003156f`

## pseudocode

```c
__int64 __fastcall CKsOutputPin2::SetFormat(CKsOutputPin2 *this, struct CMediaType *a2, __int64 a3)
{
  struct _AMMediaType *v3; // rsi
  void *v4; // r12
  int AmTypeFromKsFormat; // ebx
  int v8; // eax
  _QWORD *v9; // rbx
  struct _AMMediaType *v10; // rcx
  bool v11; // zf
  char *v12; // rdx
  __int64 v13; // r8
  struct _AMMediaType *v15; // [rsp+30h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-38h] BYREF
  unsigned int v17; // [rsp+40h] [rbp-30h] BYREF
  void *v18; // [rsp+48h] [rbp-28h] BYREF
  _BYTE v19[16]; // [rsp+50h] [rbp-20h] BYREF

  v3 = 0;
  v4 = 0;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  pv = 0;
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_DirectShow_KernelSupport_Context, SetFormat_Enter, a3, 1, v19);
  if ( *(_DWORD *)(*((_QWORD *)this - 45) + 40LL) )
  {
    AmTypeFromKsFormat = -2147220953;
    goto LABEL_30;
  }
  if ( *((_DWORD *)this + 190)
    || (AmTypeFromKsFormat = CKsOutputPin2::CreateMediaTypeArrays((CKsOutputPin2 *)((char *)this - 440)),
        AmTypeFromKsFormat >= 0) )
  {
    if ( a2 )
    {
      if ( *((_DWORD *)this + 176) )
      {
        v8 = InitializeKsDataFormat(a2, &v18, &v17);
        v4 = v18;
        AmTypeFromKsFormat = v8;
        if ( v8 < 0 )
          goto LABEL_30;
        AmTypeFromKsFormat = (*(__int64 (__fastcall **)(_QWORD, void *, LPVOID *))(**((_QWORD **)this + 86) + 48LL))(
                               *((_QWORD *)this + 86),
                               v18,
                               &pv);
        if ( AmTypeFromKsFormat < 0 )
          goto LABEL_30;
        AmTypeFromKsFormat = CKsOutputPin2::SetPluginMediaType(
                               (CKsOutputPin2 *)((char *)this - 440),
                               (union KSDATAFORMAT *)pv,
                               1);
        if ( AmTypeFromKsFormat < 0 )
          goto LABEL_30;
        AmTypeFromKsFormat = GetAmTypeFromKsFormat((union KSDATAFORMAT *)pv, &v15);
        if ( AmTypeFromKsFormat < 0 )
          goto LABEL_30;
        v3 = v15;
      }
      else
      {
        AmTypeFromKsFormat = CKsOutputPin::CompletePartialMediaType((CKsOutputPin *)((char *)this - 440), a2, &v15);
        if ( AmTypeFromKsFormat < 0 )
          goto LABEL_30;
        v3 = v15;
        AmTypeFromKsFormat = (*(__int64 (__fastcall **)(char *, struct _AMMediaType *))(*((_QWORD *)this - 55) + 64LL))(
                               (char *)this - 440,
                               v15);
        if ( AmTypeFromKsFormat < 0 )
        {
          DeleteMediaType(v3);
          goto LABEL_30;
        }
      }
      v9 = (_QWORD *)((char *)this + 80);
      if ( *((_QWORD *)this + 10)
        && (*(unsigned int (__fastcall **)(_QWORD, struct _AMMediaType *))(**((_QWORD **)this - 49) + 88LL))(
             *((_QWORD *)this - 49),
             v3) )
      {
        DeleteMediaType(a2);
        AmTypeFromKsFormat = -2147220992;
        goto LABEL_30;
      }
    }
    else
    {
      v9 = (_QWORD *)((char *)this + 80);
    }
    v10 = (struct _AMMediaType *)*((_QWORD *)this + 51);
    if ( v10 )
    {
      DeleteMediaType(v10);
      *((_QWORD *)this + 51) = 0;
    }
    if ( v3 )
    {
      v11 = *v9 == 0;
      *((_QWORD *)this + 51) = v3;
      if ( !v11 )
      {
        if ( this == (CKsOutputPin2 *)440 )
          v12 = 0;
        else
          v12 = (char *)this - 416;
        (*(void (__fastcall **)(_QWORD, char *))(**(_QWORD **)(*((_QWORD *)this - 45) + 96LL) + 64LL))(
          *(_QWORD *)(*((_QWORD *)this - 45) + 96LL),
          v12);
      }
    }
    AmTypeFromKsFormat = 0;
  }
LABEL_30:
  CoTaskMemFree(pv);
  CoTaskMemFree(v4);
  if ( (Microsoft_Windows_DirectShow_KernelSupportEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_DirectShow_KernelSupport_Context, SetFormat_Exit, v13, 1, v19);
  return (unsigned int)AmTypeFromKsFormat;
}

```

## disassembly

```asm
0x180031360  mov     [rsp-28h+arg_10], rbx
0x180031365  mov     [rsp-28h+arg_18], rsi
0x18003136a  push    rbp
0x18003136b  push    rdi
0x18003136c  push    r12
0x18003136e  push    r14
0x180031370  push    r15
0x180031372  mov     rbp, rsp
0x180031375  sub     rsp, 70h
0x180031379  mov     rax, cs:__security_cookie
0x180031380  xor     rax, rsp
0x180031383  mov     [rbp+var_10], rax
0x180031387  xor     esi, esi
0x180031389  xor     r12d, r12d
0x18003138c  test    cs:Microsoft_Windows_DirectShow_KernelSupportEnableBits, 1
0x180031393  mov     r15, rdx
0x180031396  mov     rdi, rcx
0x180031399  mov     [rbp+var_40], rsi
0x18003139d  mov     [rbp+var_30], esi
0x1800313a0  mov     [rbp+var_28], r12
0x1800313a4  mov     [rbp+pv], rsi
0x1800313a8  jz      short loc_1800313CA
0x1800313aa  lea     rax, [rbp+var_20]
0x1800313ae  lea     r9d, [rsi+1]
0x1800313b2  mov     [rsp+70h+var_50], rax
0x1800313b7  lea     rdx, SetFormat_Enter
0x1800313be  lea     rcx, Microsoft_Windows_DirectShow_KernelSupport_Context
0x1800313c5  call    McGenEventWrite_EventWriteTransfer
0x1800313ca  lea     r14, [rdi-1B8h]
0x1800313d1  mov     rax, [r14+50h]
0x1800313d5  cmp     [rax+28h], esi
0x1800313d8  jz      short loc_1800313E4
0x1800313da  mov     ebx, 80040227h
0x1800313df  jmp     loc_18003155C
0x1800313e4  cmp     [rdi+2F8h], esi
0x1800313ea  jnz     short loc_1800313FE
0x1800313ec  mov     rcx, r14; this
0x1800313ef  call    ?CreateMediaTypeArrays@CKsOutputPin2@@QEAAJXZ; CKsOutputPin2::CreateMediaTypeArrays(void)
0x1800313f4  mov     ebx, eax
0x1800313f6  test    eax, eax
0x1800313f8  js      loc_18003155C
0x1800313fe  test    r15, r15
0x180031401  jz      loc_180031501
0x180031407  cmp     [rdi+2C0h], esi
0x18003140d  jz      loc_1800314C2
0x180031413  lea     r8, [rbp+var_30]; unsigned int *
0x180031417  mov     rcx, r15; const struct _AMMediaType *
0x18003141a  lea     rdx, [rbp+var_28]; void **
0x18003141e  call    ?InitializeKsDataFormat@@YAJPEBU_AMMediaType@@PEAPEAXPEAK@Z; InitializeKsDataFormat(_AMMediaType const *,void * *,ulong *)
0x180031423  mov     r12, [rbp+var_28]
0x180031427  mov     ebx, eax
0x180031429  test    eax, eax
0x18003142b  js      loc_18003155C
0x180031431  mov     rcx, [rdi+2B0h]
0x180031438  lea     r8, [rbp+pv]
0x18003143c  mov     rdx, r12
0x18003143f  mov     rax, [rcx]
0x180031442  mov     rax, [rax+30h]
0x180031446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003144b  mov     ebx, eax
0x18003144d  test    eax, eax
0x18003144f  js      loc_18003155C
0x180031455  mov     rdx, [rbp+pv]; union KSDATAFORMAT *
0x180031459  mov     r8d, 1; int
0x18003145f  mov     rcx, r14; this
0x180031462  call    ?SetPluginMediaType@CKsOutputPin2@@QEAAJPEATKSDATAFORMAT@@H@Z; CKsOutputPin2::SetPluginMediaType(KSDATAFORMAT *,int)
0x180031467  mov     ebx, eax
0x180031469  test    eax, eax
0x18003146b  js      loc_18003155C
0x180031471  mov     rcx, [rbp+pv]; union KSDATAFORMAT *
0x180031475  lea     rdx, [rbp+var_40]; struct _AMMediaType **
0x180031479  call    ?GetAmTypeFromKsFormat@@YAJPEATKSDATAFORMAT@@PEAPEAU_AMMediaType@@@Z; GetAmTypeFromKsFormat(KSDATAFORMAT *,_AMMediaType * *)
0x18003147e  mov     ebx, eax
0x180031480  test    eax, eax
0x180031482  js      loc_18003155C
0x180031488  mov     rsi, [rbp+var_40]
0x18003148c  lea     rbx, [rdi+50h]
0x180031490  cmp     qword ptr [rbx], 0
0x180031494  jz      short loc_180031505
0x180031496  mov     rcx, [rdi-188h]
0x18003149d  mov     rdx, rsi
0x1800314a0  mov     rax, [rcx]
0x1800314a3  mov     rax, [rax+58h]
0x1800314a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314ac  test    eax, eax
0x1800314ae  jz      short loc_180031505
0x1800314b0  mov     rcx, r15; pv
0x1800314b3  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x1800314b8  mov     ebx, 80040200h
0x1800314bd  jmp     loc_18003155C
0x1800314c2  lea     r8, [rbp+var_40]; struct _AMMediaType **
0x1800314c6  mov     rdx, r15; struct CMediaType *
0x1800314c9  mov     rcx, r14; this
0x1800314cc  call    ?CompletePartialMediaType@CKsOutputPin@@QEAAJPEAVCMediaType@@PEAPEAU_AMMediaType@@@Z; CKsOutputPin::CompletePartialMediaType(CMediaType *,_AMMediaType * *)
0x1800314d1  mov     ebx, eax
0x1800314d3  test    eax, eax
0x1800314d5  js      loc_18003155C
0x1800314db  mov     rax, [r14]
0x1800314de  mov     rcx, r14
0x1800314e1  mov     rsi, [rbp+var_40]
0x1800314e5  mov     rdx, rsi
0x1800314e8  mov     rax, [rax+40h]
0x1800314ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800314f1  mov     ebx, eax
0x1800314f3  test    eax, eax
0x1800314f5  jns     short loc_18003148C
0x1800314f7  mov     rcx, rsi; pv
0x1800314fa  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x1800314ff  jmp     short loc_18003155C
0x180031501  lea     rbx, [rdi+50h]
0x180031505  mov     rcx, [rdi+198h]; pv
0x18003150c  test    rcx, rcx
0x18003150f  jz      short loc_180031521
0x180031511  call    ?DeleteMediaType@@YAXPEAU_AMMediaType@@@Z; DeleteMediaType(_AMMediaType *)
0x180031516  mov     qword ptr [rdi+198h], 0
0x180031521  test    rsi, rsi
0x180031524  jz      short loc_18003155A
0x180031526  cmp     qword ptr [rbx], 0
0x18003152a  mov     [rdi+198h], rsi
0x180031531  jz      short loc_18003155A
0x180031533  mov     rax, [rdi-168h]
0x18003153a  mov     rcx, [rax+60h]
0x18003153e  mov     rax, [rcx]
0x180031541  test    r14, r14
0x180031544  jz      short loc_18003154F
0x180031546  lea     rdx, [rdi-1A0h]
0x18003154d  jmp     short loc_180031551
0x18003154f  xor     edx, edx
0x180031551  mov     rax, [rax+40h]
0x180031555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003155a  xor     ebx, ebx
0x18003155c  mov     rcx, [rbp+pv]; pv
0x180031560  call    cs:__imp_CoTaskMemFree
0x180031567  nop     dword ptr [rax+rax+00h]
0x18003156c  mov     rcx, r12; pv
0x18003156f  call    cs:__imp_CoTaskMemFree
0x180031576  nop     dword ptr [rax+rax+00h]
0x18003157b  test    cs:Microsoft_Windows_DirectShow_KernelSupportEnableBits, 1
0x180031582  jz      short loc_1800315A6
0x180031584  lea     rax, [rbp+var_20]
0x180031588  mov     r9d, 1
0x18003158e  lea     rdx, SetFormat_Exit
0x180031595  mov     [rsp+70h+var_50], rax
0x18003159a  lea     rcx, Microsoft_Windows_DirectShow_KernelSupport_Context
0x1800315a1  call    McGenEventWrite_EventWriteTransfer
0x1800315a6  mov     eax, ebx
0x1800315a8  mov     rcx, [rbp+var_10]
0x1800315ac  xor     rcx, rsp; StackCookie
0x1800315af  call    __security_check_cookie
0x1800315b4  lea     r11, [rsp+70h+var_s0]
0x1800315b9  mov     rbx, [r11+40h]
0x1800315bd  mov     rsi, [r11+48h]
0x1800315c1  mov     rsp, r11
0x1800315c4  pop     r15
0x1800315c6  pop     r14
0x1800315c8  pop     r12
0x1800315ca  pop     rdi
0x1800315cb  pop     rbp
0x1800315cc  retn
```
