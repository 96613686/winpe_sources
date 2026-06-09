# CSurrogateFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140003190`
- end: `0x140003319`
- name: `?CreateInstance@CSurrogateFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `393`
- prototype: `__int64 __fastcall(const IID *this, struct IUnknown *, const struct _GUID *, void **ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400010fc`
- `0x140003190`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400031f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400031f2`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1400032d5`
- `api-ms-win-core-com-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x1400032d5`
- `SHLWAPI!__imp_SHCreateThread` at `0x140003269`
- `SHLWAPI!__imp_SHCreateThread` at `0x140003269`

## pseudocode

```c
__int64 __fastcall CSurrogateFactory::CreateInstance(
        const IID *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **ppv)
{
  unsigned int v7; // edi
  const IID *v8; // rsi
  char *v9; // rbx
  IID v10; // xmm1
  __int64 v11; // rax
  IID v12; // xmm0
  int v13; // ebp
  __int64 v14; // rsi
  HRESULT InterfaceAndReleaseStream; // eax
  IStream *v16; // rcx

  v7 = -2147024809;
  if ( ppv && !a2 )
  {
    *ppv = 0;
    v8 = this + 1;
    if ( *(_OWORD *)&this[1] == *(_OWORD *)&CLSID_PreviewWindowCreator )
      return (unsigned int)CoCreateInstance(this + 1, 0, 1u, a3, ppv);
    v9 = (char *)operator new(0x50u);
    if ( !v9 )
      return (unsigned int)-2147024882;
    v10 = *a3;
    v11 = *(_QWORD *)&this[2].Data1;
    v12 = *v8;
    *(_QWORD *)v9 = &CThreadParams::`vftable';
    *(IID *)(v9 + 28) = v10;
    *((_DWORD *)v9 + 2) = 1;
    *(IID *)(v9 + 12) = v12;
    *((_QWORD *)v9 + 9) = 0;
    *((_QWORD *)v9 + 6) = v11;
    *((_DWORD *)v9 + 14) = 0;
    *((_DWORD *)v9 + 15) = -2147418113;
    *((_QWORD *)v9 + 8) = 0;
    if ( !SHCreateThread(ThreadProc, v9, 0xCu, SyncThreadProc) )
    {
LABEL_20:
      (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9);
      return v7;
    }
    if ( *((int *)v9 + 15) < 0 )
    {
      v7 = *((_DWORD *)v9 + 15);
      goto LABEL_20;
    }
    v13 = -2147467259;
    if ( !*((_DWORD *)v9 + 14) || !*((_QWORD *)v9 + 9) || (*ppv = 0, !*((_QWORD *)v9 + 9)) )
    {
LABEL_18:
      v7 = v13;
      goto LABEL_20;
    }
    v14 = *((_QWORD *)v9 + 9);
    *((_QWORD *)v9 + 9) = 0;
    *ppv = 0;
    if ( *(_DWORD *)(v14 + 24) == 2 )
    {
      if ( !*(_QWORD *)(v14 + 32) )
      {
        v13 = -2147024809;
LABEL_17:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        goto LABEL_18;
      }
      InterfaceAndReleaseStream = (*(__int64 (__fastcall **)(_QWORD, const struct _GUID *, void **))(**(_QWORD **)(v14 + 32) + 24LL))(
                                    *(_QWORD *)(v14 + 32),
                                    a3,
                                    ppv);
    }
    else
    {
      v16 = *(IStream **)(v14 + 16);
      *(_QWORD *)(v14 + 16) = 0;
      InterfaceAndReleaseStream = CoGetInterfaceAndReleaseStream(v16, a3, ppv);
    }
    v13 = InterfaceAndReleaseStream;
    goto LABEL_17;
  }
  return v7;
}

```

## disassembly

```asm
0x140003190  push    rbx
0x140003192  push    rbp
0x140003193  push    rsi
0x140003194  push    rdi
0x140003195  push    r12
0x140003197  push    r14
0x140003199  push    r15
0x14000319b  sub     rsp, 30h
0x14000319f  xor     r12d, r12d
0x1400031a2  mov     r14, r9
0x1400031a5  mov     r15, r8
0x1400031a8  mov     rbp, rcx
0x1400031ab  mov     edi, 80070057h
0x1400031b0  test    r9, r9
0x1400031b3  jz      loc_140003308
0x1400031b9  test    rdx, rdx
0x1400031bc  jnz     loc_140003308
0x1400031c2  mov     [r9], r12
0x1400031c5  lea     rsi, [rcx+10h]
0x1400031c9  mov     rax, [rsi]
0x1400031cc  cmp     rax, qword ptr cs:CLSID_PreviewWindowCreator.Data1
0x1400031d3  jnz     short loc_1400031FF
0x1400031d5  mov     rax, [rsi+8]
0x1400031d9  cmp     rax, qword ptr cs:CLSID_PreviewWindowCreator.Data4
0x1400031e0  jnz     short loc_1400031FF
0x1400031e2  mov     [rsp+68h+ppv], r9; ppv
0x1400031e7  mov     rcx, rsi; rclsid
0x1400031ea  mov     r9, r8; riid
0x1400031ed  lea     r8d, [r12+1]; dwClsContext
0x1400031f2  call    cs:__imp_CoCreateInstance
0x1400031f8  mov     edi, eax
0x1400031fa  jmp     loc_140003308
0x1400031ff  mov     ecx, 50h ; 'P'; Size
0x140003204  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140003209  mov     rbx, rax
0x14000320c  test    rax, rax
0x14000320f  jz      loc_140003303
0x140003215  movups  xmm1, xmmword ptr [r15]
0x140003219  mov     rax, [rbp+20h]
0x14000321d  lea     rcx, ??_7CThreadParams@@6B@; const CThreadParams::`vftable'
0x140003224  movups  xmm0, xmmword ptr [rsi]
0x140003227  mov     [rbx], rcx
0x14000322a  lea     r9, ?SyncThreadProc@@YAKPEAX@Z; pfnCallback
0x140003231  movdqu  xmmword ptr [rbx+1Ch], xmm1
0x140003236  mov     dword ptr [rbx+8], 1
0x14000323d  mov     r8d, 0Ch; flags
0x140003243  movdqu  xmmword ptr [rbx+0Ch], xmm0
0x140003248  mov     rdx, rbx; pData
0x14000324b  mov     [rbx+48h], r12
0x14000324f  lea     rcx, ?ThreadProc@@YAKPEAX@Z; pfnThreadProc
0x140003256  mov     [rbx+30h], rax
0x14000325a  mov     [rbx+38h], r12d
0x14000325e  mov     dword ptr [rbx+3Ch], 8000FFFFh
0x140003265  mov     [rbx+40h], r12
0x140003269  call    cs:__imp_SHCreateThread
0x14000326f  test    eax, eax
0x140003271  jz      short loc_1400032F2
0x140003273  mov     eax, [rbx+3Ch]
0x140003276  test    eax, eax
0x140003278  js      short loc_1400032F0
0x14000327a  mov     ebp, 80004005h
0x14000327f  cmp     [rbx+38h], r12d
0x140003283  jz      short loc_1400032EC
0x140003285  cmp     [rbx+48h], r12
0x140003289  jz      short loc_1400032EC
0x14000328b  mov     [r14], r12
0x14000328e  cmp     [rbx+48h], r12
0x140003292  jz      short loc_1400032EC
0x140003294  mov     rsi, [rbx+48h]
0x140003298  mov     [rbx+48h], r12
0x14000329c  mov     [r14], r12
0x14000329f  cmp     dword ptr [rsi+18h], 2
0x1400032a3  jnz     short loc_1400032C7
0x1400032a5  cmp     [rsi+20h], r12
0x1400032a9  jz      short loc_1400032C3
0x1400032ab  mov     rcx, [rsi+20h]
0x1400032af  mov     r8, r14
0x1400032b2  mov     rdx, r15
0x1400032b5  mov     rax, [rcx]
0x1400032b8  mov     rax, [rax+18h]
0x1400032bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032c1  jmp     short loc_1400032DB
0x1400032c3  mov     ebp, edi
0x1400032c5  jmp     short loc_1400032DD
0x1400032c7  mov     rcx, [rsi+10h]; pStm
0x1400032cb  mov     r8, r14; ppv
0x1400032ce  mov     rdx, r15; iid
0x1400032d1  mov     [rsi+10h], r12
0x1400032d5  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x1400032db  mov     ebp, eax
0x1400032dd  mov     rdx, [rsi]
0x1400032e0  mov     rcx, rsi
0x1400032e3  mov     rax, [rdx+10h]
0x1400032e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032ec  mov     edi, ebp
0x1400032ee  jmp     short loc_1400032F2
0x1400032f0  mov     edi, eax
0x1400032f2  mov     rax, [rbx]
0x1400032f5  mov     rcx, rbx
0x1400032f8  mov     rax, [rax+10h]
0x1400032fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003301  jmp     short loc_140003308
0x140003303  mov     edi, 8007000Eh
0x140003308  mov     eax, edi
0x14000330a  add     rsp, 30h
0x14000330e  pop     r15
0x140003310  pop     r14
0x140003312  pop     r12
0x140003314  pop     rdi
0x140003315  pop     rsi
0x140003316  pop     rbp
0x140003317  pop     rbx
0x140003318  retn
```
