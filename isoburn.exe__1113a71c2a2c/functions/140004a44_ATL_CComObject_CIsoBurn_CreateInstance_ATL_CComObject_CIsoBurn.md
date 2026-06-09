# ATL::CComObject<CIsoBurn>::CreateInstance(ATL::CComObject<CIsoBurn> * *)

- ea: `0x140004a44`
- end: `0x140004b95`
- name: `?CreateInstance@?$CComObject@VCIsoBurn@@@ATL@@SAJPEAPEAV12@@Z`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000aac0`

## callees

- `0x140001c08`
- `0x140004a44`
- `0x14000623c`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CIsoBurn>::CreateInstance(char **a1)
{
  char *v3; // rax
  char *v4; // rbx
  struct ATL::CAtlModule *v5; // rcx
  volatile signed __int32 *v6; // rsi
  signed __int32 v7; // eax
  int v8; // eax
  int v9; // ecx
  unsigned int v10; // edi
  signed __int32 v11; // eax

  if ( !a1 )
    return 2147500035LL;
  *a1 = 0;
  v3 = (char *)operator new(0xA8u);
  v4 = v3;
  if ( v3 )
  {
    v5 = ATL::_pAtlModule;
    *((_DWORD *)v3 + 16) = 0;
    *(_OWORD *)(v3 + 72) = 0;
    *(_OWORD *)(v3 + 88) = 0;
    *((_QWORD *)v3 + 13) = 0;
    v3[112] = 0;
    *((_DWORD *)v3 + 13) = -16843010;
    *((GUID *)v3 + 1) = LIBID_IMAPI2;
    *((_DWORD *)v3 + 12) = 1;
    *((GUID *)v3 + 2) = IID_DDiscFormat2DataEvents;
    *((_QWORD *)v3 + 15) = 0;
    *((_QWORD *)v3 + 16) = 0;
    *((_QWORD *)v3 + 17) = 0;
    *((_QWORD *)v3 + 18) = 0;
    *((_QWORD *)v3 + 19) = 0;
    *(_QWORD *)v3 = &ATL::CComObject<CIsoBurn>::`vftable'{for `ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v3 + 1) = &ATL::CComObject<CIsoBurn>::`vftable'{for `ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v3 + 7) = &ATL::CComObject<CIsoBurn>::`vftable'{for `IIsoBurn'};
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v5 + 8LL))(v5);
    v6 = (volatile signed __int32 *)(v4 + 64);
    do
    {
      if ( *v6 == 0x7FFFFFFF )
        break;
      v7 = *v6;
    }
    while ( v7 != _InterlockedCompareExchange(v6, v7 + 1, v7) );
    v8 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)(v4 + 72));
    if ( v8 >= 0 )
      v4[112] = 1;
    v9 = 0;
    if ( v8 < 0 )
      v9 = v8;
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    do
    {
      if ( *v6 == 0x7FFFFFFF )
        break;
      v11 = *v6;
    }
    while ( v11 != _InterlockedCompareExchange(v6, v11 - 1, v11) );
    if ( !v10 )
      goto LABEL_20;
    (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v4 + 64LL))(v4, 1);
  }
  else
  {
    v10 = -2147024882;
  }
  v4 = 0;
LABEL_20:
  *a1 = v4;
  return v10;
}

```

## disassembly

```asm
0x140004a44  push    rbx
0x140004a46  push    rsi
0x140004a47  push    rdi
0x140004a48  push    r12
0x140004a4a  push    r14
0x140004a4c  push    r15
0x140004a4e  sub     rsp, 28h
0x140004a52  mov     r14, rcx
0x140004a55  test    rcx, rcx
0x140004a58  jnz     short loc_140004A64
0x140004a5a  mov     eax, 80004003h
0x140004a5f  jmp     loc_140004B87
0x140004a64  mov     qword ptr [rcx], 0
0x140004a6b  mov     ecx, 0A8h; Size
0x140004a70  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140004a75  mov     rbx, rax
0x140004a78  test    rax, rax
0x140004a7b  jz      loc_140004B7B
0x140004a81  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140004a88  xorps   xmm0, xmm0
0x140004a8b  mov     dword ptr [rax+40h], 0
0x140004a92  xor     eax, eax
0x140004a94  movups  xmmword ptr [rbx+48h], xmm0
0x140004a98  movups  xmmword ptr [rbx+58h], xmm0
0x140004a9c  mov     [rbx+68h], rax
0x140004aa0  lea     r12d, [rax+1]
0x140004aa4  mov     [rbx+70h], al
0x140004aa7  mov     dword ptr [rbx+34h], 0FEFEFEFEh
0x140004aae  movups  xmm0, xmmword ptr cs:LIBID_IMAPI2.Data1
0x140004ab5  movdqu  xmmword ptr [rbx+10h], xmm0
0x140004aba  movups  xmm1, xmmword ptr cs:IID_DDiscFormat2DataEvents.Data1
0x140004ac1  mov     [rbx+30h], r12d
0x140004ac5  movdqu  xmmword ptr [rbx+20h], xmm1
0x140004aca  mov     [rbx+78h], rax
0x140004ace  mov     [rbx+80h], rax
0x140004ad5  mov     [rbx+88h], rax
0x140004adc  mov     [rbx+90h], rax
0x140004ae3  mov     [rbx+98h], rax
0x140004aea  lea     rax, ??_7?$CComObject@VCIsoBurn@@@ATL@@6B?$IDispatchImpl@UIDispatch@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CIsoBurn>::`vftable'{for `ATL::IDispatchImpl<IDispatch,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x140004af1  mov     [rbx], rax
0x140004af4  lea     rax, ??_7?$CComObject@VCIsoBurn@@@ATL@@6B?$IDispEventImpl@$00VCIsoBurn@@$1?IID_DDiscFormat2DataEvents@@3U_GUID@@B$1?LIBID_IMAPI2@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CIsoBurn>::`vftable'{for `ATL::IDispEventImpl<1,CIsoBurn,&_GUID const IID_DDiscFormat2DataEvents,&_GUID const LIBID_IMAPI2,1,0,ATL::CComTypeInfoHolder>'}
0x140004afb  mov     [rbx+8], rax
0x140004aff  lea     rax, ??_7?$CComObject@VCIsoBurn@@@ATL@@6BIIsoBurn@@@; const ATL::CComObject<CIsoBurn>::`vftable'{for `IIsoBurn'}
0x140004b06  mov     [rbx+38h], rax
0x140004b0a  mov     rax, [rcx]
0x140004b0d  mov     rax, [rax+8]
0x140004b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b16  lea     rsi, [rbx+40h]
0x140004b1a  mov     r15d, 7FFFFFFFh
0x140004b20  jmp     short loc_140004B2B
0x140004b22  lea     ecx, [rax+1]
0x140004b25  lock cmpxchg [rsi], ecx
0x140004b29  jz      short loc_140004B32
0x140004b2b  mov     eax, [rsi]
0x140004b2d  cmp     eax, r15d
0x140004b30  jnz     short loc_140004B22
0x140004b32  lea     rcx, [rsi+8]; this
0x140004b36  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140004b3b  test    eax, eax
0x140004b3d  js      short loc_140004B43
0x140004b3f  mov     [rsi+30h], r12b
0x140004b43  xor     ecx, ecx
0x140004b45  test    eax, eax
0x140004b47  cmovs   ecx, eax
0x140004b4a  xor     edi, edi
0x140004b4c  test    ecx, ecx
0x140004b4e  cmovs   edi, ecx
0x140004b51  jmp     short loc_140004B5C
0x140004b53  lea     ecx, [rax-1]
0x140004b56  lock cmpxchg [rsi], ecx
0x140004b5a  jz      short loc_140004B63
0x140004b5c  mov     eax, [rsi]
0x140004b5e  cmp     eax, r15d
0x140004b61  jnz     short loc_140004B53
0x140004b63  test    edi, edi
0x140004b65  jz      short loc_140004B82
0x140004b67  mov     rax, [rbx]
0x140004b6a  mov     edx, r12d
0x140004b6d  mov     rcx, rbx
0x140004b70  mov     rax, [rax+40h]
0x140004b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004b79  jmp     short loc_140004B80
0x140004b7b  mov     edi, 8007000Eh
0x140004b80  xor     ebx, ebx
0x140004b82  mov     [r14], rbx
0x140004b85  mov     eax, edi
0x140004b87  add     rsp, 28h
0x140004b8b  pop     r15
0x140004b8d  pop     r14
0x140004b8f  pop     r12
0x140004b91  pop     rdi
0x140004b92  pop     rsi
0x140004b93  pop     rbx
0x140004b94  retn
```
