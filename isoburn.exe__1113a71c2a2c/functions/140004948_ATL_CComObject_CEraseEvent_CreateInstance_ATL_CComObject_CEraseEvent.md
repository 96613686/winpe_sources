# ATL::CComObject<CEraseEvent>::CreateInstance(ATL::CComObject<CEraseEvent> * *)

- ea: `0x140004948`
- end: `0x140004a3c`
- name: `?CreateInstance@?$CComObject@VCEraseEvent@@@ATL@@SAJPEAPEAV12@@Z`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140009870`

## callees

- `0x140001c08`
- `0x140004948`
- `0x14000623c`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEraseEvent>::CreateInstance(GUID **a1)
{
  GUID *v3; // rax
  GUID *v4; // rbx
  struct ATL::CAtlModule *v5; // rcx
  int v6; // eax
  int v7; // ecx
  unsigned int v8; // edi

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = (GUID *)operator new(0x78u);
  v4 = v3;
  if ( v3 )
  {
    v5 = ATL::_pAtlModule;
    *(_DWORD *)v3[3].Data4 = 0;
    v3[4] = 0;
    v3[5] = 0;
    *(_QWORD *)&v3[6].Data1 = 0;
    v3[6].Data4[0] = 0;
    *(_DWORD *)&v3[3].Data2 = -16843010;
    v3[1] = LIBID_IMAPI2;
    v3[3].Data1 = 1;
    v3[2] = IID_DDiscFormat2EraseEvents;
    *(_QWORD *)&v3[7].Data1 = 0;
    *(_QWORD *)&v3->Data1 = &ATL::CComObject<CEraseEvent>::`vftable'{for `ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
    *(_QWORD *)v3->Data4 = &ATL::CComObject<CEraseEvent>::`vftable'{for `ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v5 + 8LL))(v5);
    v6 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)&v4[4]);
    if ( v6 >= 0 )
      v4[6].Data4[0] = 1;
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
    v8 = 0;
    if ( v7 < 0 )
      v8 = v7;
    if ( !v8 )
      goto LABEL_14;
    (*(void (__fastcall **)(GUID *, __int64))(*(_QWORD *)&v4->Data1 + 64LL))(v4, 1);
  }
  else
  {
    v8 = -2147024882;
  }
  v4 = 0;
LABEL_14:
  *a1 = v4;
  return v8;
}

```

## disassembly

```asm
0x140004948  push    rbx
0x14000494a  push    rsi
0x14000494b  push    rdi
0x14000494c  push    r14
0x14000494e  sub     rsp, 28h
0x140004952  mov     rsi, rcx
0x140004955  test    rcx, rcx
0x140004958  jnz     short loc_140004964
0x14000495a  mov     eax, 80004003h
0x14000495f  jmp     loc_140004A32
0x140004964  mov     qword ptr [rcx], 0
0x14000496b  mov     ecx, 78h ; 'x'; Size
0x140004970  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140004975  mov     rbx, rax
0x140004978  test    rax, rax
0x14000497b  jz      loc_140004A26
0x140004981  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140004988  xorps   xmm0, xmm0
0x14000498b  mov     dword ptr [rax+38h], 0
0x140004992  xor     eax, eax
0x140004994  movups  xmmword ptr [rbx+40h], xmm0
0x140004998  movups  xmmword ptr [rbx+50h], xmm0
0x14000499c  mov     [rbx+60h], rax
0x1400049a0  lea     r14d, [rax+1]
0x1400049a4  mov     [rbx+68h], al
0x1400049a7  mov     dword ptr [rbx+34h], 0FEFEFEFEh
0x1400049ae  movups  xmm0, xmmword ptr cs:LIBID_IMAPI2.Data1
0x1400049b5  movdqu  xmmword ptr [rbx+10h], xmm0
0x1400049ba  movups  xmm1, xmmword ptr cs:IID_DDiscFormat2EraseEvents.Data1
0x1400049c1  mov     [rbx+30h], r14d
0x1400049c5  movdqu  xmmword ptr [rbx+20h], xmm1
0x1400049ca  mov     [rbx+70h], rax
0x1400049ce  lea     rax, ??_7?$CComObject@VCEraseEvent@@@ATL@@6B?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CEraseEvent>::`vftable'{for `ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x1400049d5  mov     [rbx], rax
0x1400049d8  lea     rax, ??_7?$CComObject@VCEraseEvent@@@ATL@@6B?$IDispEventImpl@$00VCEraseEvent@@$1?IID_DDiscFormat2EraseEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CEraseEvent>::`vftable'{for `ATL::IDispEventImpl<1,CEraseEvent,&_GUID const IID_DDiscFormat2EraseEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x1400049df  mov     [rbx+8], rax
0x1400049e3  mov     rax, [rcx]
0x1400049e6  mov     rax, [rax+8]
0x1400049ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400049ef  lea     rcx, [rbx+40h]; this
0x1400049f3  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1400049f8  test    eax, eax
0x1400049fa  js      short loc_140004A00
0x1400049fc  mov     [rbx+68h], r14b
0x140004a00  xor     ecx, ecx
0x140004a02  test    eax, eax
0x140004a04  cmovs   ecx, eax
0x140004a07  xor     edi, edi
0x140004a09  test    ecx, ecx
0x140004a0b  cmovs   edi, ecx
0x140004a0e  test    edi, edi
0x140004a10  jz      short loc_140004A2D
0x140004a12  mov     rax, [rbx]
0x140004a15  mov     edx, r14d
0x140004a18  mov     rcx, rbx
0x140004a1b  mov     rax, [rax+40h]
0x140004a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a24  jmp     short loc_140004A2B
0x140004a26  mov     edi, 8007000Eh
0x140004a2b  xor     ebx, ebx
0x140004a2d  mov     [rsi], rbx
0x140004a30  mov     eax, edi
0x140004a32  add     rsp, 28h
0x140004a36  pop     r14
0x140004a38  pop     rdi
0x140004a39  pop     rsi
0x140004a3a  pop     rbx
0x140004a3b  retn
```
