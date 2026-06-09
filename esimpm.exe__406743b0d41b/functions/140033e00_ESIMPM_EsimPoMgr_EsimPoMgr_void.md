# ESIMPM::EsimPoMgr::EsimPoMgr(void)

- ea: `0x140033e00`
- end: `0x1400341ea`
- name: `??0EsimPoMgr@ESIMPM@@QEAA@XZ`
- size: `1002`
- prototype: `ESIMPM::EsimPoMgr *__fastcall(ESIMPM::EsimPoMgr *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140034cf8`

## callees

- `0x140001278`
- `0x140002f84`
- `0x140003244`
- `0x140003b64`
- `0x140013df8`
- `0x14001eb14`
- `0x140032a44`
- `0x140033e00`
- `0x140034444`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140034102`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140034102`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140034120`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140034120`

## pseudocode

```c
ESIMPM::EsimPoMgr *__fastcall ESIMPM::EsimPoMgr::EsimPoMgr(ESIMPM::EsimPoMgr *this)
{
  char *v2; // rdi
  _QWORD *v3; // rax
  _QWORD *v4; // rax
  HANDLE EventW; // rax
  void *v6; // rcx
  __int128 *v7; // rbx
  __int64 v8; // rdx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  void *v12; // rdi
  _BYTE pExceptionObject[72]; // [rsp+30h] [rbp-48h] BYREF
  const char *v15; // [rsp+80h] [rbp+8h] BYREF
  char *v16; // [rsp+88h] [rbp+10h]
  char *v17; // [rsp+90h] [rbp+18h]

  v15 = (const char *)this;
  *(_QWORD *)this = &ESIMPM::EsimPoMgr::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_OWORD *)this + 4) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 7;
  *((_WORD *)this + 32) = 0;
  *((_OWORD *)this + 6) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 7;
  *((_WORD *)this + 48) = 0;
  v2 = (char *)this + 128;
  v16 = (char *)this + 128;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  v3 = operator new(0x48u);
  *v3 = v3;
  v3[1] = v3;
  v3[2] = v3;
  *((_WORD *)v3 + 12) = 257;
  *((_QWORD *)v2 + 3) = v3;
  v17 = v2 + 40;
  *((_DWORD *)v2 + 10) = 0;
  *((_QWORD *)v2 + 6) = 0;
  *((_QWORD *)v2 + 7) = 0;
  v4 = operator new(0x30u);
  *v4 = v4;
  v4[1] = v4;
  *((_QWORD *)v2 + 6) = v4;
  *((_QWORD *)v2 + 8) = 0;
  *((_QWORD *)v2 + 9) = 0;
  *((_QWORD *)v2 + 10) = 0;
  *((_QWORD *)v2 + 11) = 7;
  *((_QWORD *)v2 + 12) = 8;
  *((_DWORD *)v2 + 10) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    v2 + 64,
    16,
    *((_QWORD *)v2 + 6));
  *(_OWORD *)(v2 + 104) = 0;
  *((_QWORD *)v2 + 15) = 0;
  *((_QWORD *)v2 + 16) = 7;
  *((_WORD *)v2 + 52) = 0;
  *(_OWORD *)(v2 + 136) = 0;
  *((_QWORD *)v2 + 19) = 0;
  *((_QWORD *)v2 + 20) = 7;
  *((_WORD *)v2 + 68) = 0;
  *(_OWORD *)(v2 + 168) = 0;
  *((_QWORD *)v2 + 23) = 0;
  *((_QWORD *)v2 + 24) = 7;
  *((_WORD *)v2 + 84) = 0;
  *(_OWORD *)(v2 + 200) = 0;
  *((_QWORD *)v2 + 27) = 0;
  *((_QWORD *)v2 + 28) = 7;
  *((_WORD *)v2 + 100) = 0;
  *((_QWORD *)v2 + 29) = 0;
  *((_DWORD *)this + 92) = 0;
  *((_DWORD *)this + 93) = 17;
  *((_DWORD *)this + 94) = 29;
  *((_DWORD *)this + 124) = 0;
  *(_OWORD *)((char *)this + 552) = 0;
  *(_OWORD *)((char *)this + 568) = 0;
  *((_QWORD *)this + 73) = 0;
  *((_QWORD *)this + 74) = 0;
  *(_OWORD *)((char *)this + 600) = 0;
  *((_QWORD *)this + 77) = 0;
  *((_QWORD *)this + 78) = 7;
  *((_WORD *)this + 300) = 0;
  *(_OWORD *)((char *)this + 632) = 0;
  *((_QWORD *)this + 81) = 0;
  *((_QWORD *)this + 82) = 7;
  *((_WORD *)this + 316) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_DWORD *)this + 168) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 86) = 0;
  *((_DWORD *)this + 174) = 0;
  *(_QWORD *)((char *)this + 700) = 1;
  *((_BYTE *)this + 708) = 0;
  *((_DWORD *)this + 178) = 0;
  *((_QWORD *)this + 90) = 0;
  *((_QWORD *)this + 91) = 0;
  *((_DWORD *)this + 184) = 0;
  *(_OWORD *)((char *)this + 744) = 0;
  *((_QWORD *)this + 95) = 0;
  *((_QWORD *)this + 96) = 7;
  *((_WORD *)this + 372) = 0;
  *((_BYTE *)this + 776) = 0;
  *((_OWORD *)this + 49) = 0;
  *((_QWORD *)this + 100) = 0;
  *((_QWORD *)this + 101) = 7;
  *((_WORD *)this + 392) = 0;
  *((_OWORD *)this + 51) = 0;
  *((_QWORD *)this + 104) = 0;
  *((_QWORD *)this + 105) = 7;
  *((_WORD *)this + 408) = 0;
  *((_QWORD *)this + 106) = 0;
  *(_OWORD *)((char *)this + 856) = 0;
  *((_QWORD *)this + 109) = 0;
  *((_QWORD *)this + 110) = 7;
  *((_WORD *)this + 428) = 0;
  *((_DWORD *)this + 222) = 0;
  *((_OWORD *)this + 56) = 0;
  *((_QWORD *)this + 114) = 0;
  *((_QWORD *)this + 115) = 7;
  *((_WORD *)this + 448) = 0;
  *((_OWORD *)this + 58) = 0;
  *((_QWORD *)this + 118) = 0;
  *((_QWORD *)this + 119) = 7;
  *((_WORD *)this + 464) = 0;
  *((_QWORD *)this + 120) = 0;
  *((_QWORD *)this + 121) = 0;
  *((_QWORD *)this + 122) = 0;
  *((_BYTE *)this + 984) = 1;
  *((_QWORD *)this + 124) = 0;
  *((_QWORD *)this + 125) = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  v6 = (void *)*((_QWORD *)this + 125);
  *((_QWORD *)this + 125) = EventW;
  if ( (unsigned __int64)v6 + 1 > 1 )
    CloseHandle(v6);
  v7 = (__int128 *)operator new(0x20u);
  v16 = (char *)v7;
  *v7 = 0;
  *((_QWORD *)v7 + 2) = 0;
  *((_QWORD *)v7 + 3) = 7;
  *(_WORD *)v7 = 0;
  if ( (unsigned int)GetPersistentRegPathWstring(0x27u, v8, v7) )
  {
    std::exception::exception((std::exception *)pExceptionObject, "failed to get persistent root string");
    throw (std::exception *)pExceptionObject;
  }
  v12 = (void *)*((_QWORD *)this + 120);
  *((_QWORD *)this + 120) = v7;
  if ( v12 )
  {
    std::wstring::_Tidy_deallocate(v12);
    operator delete(v12);
  }
  if ( (unsigned int)dword_140075078 > 5 )
  {
    v15 = "ESIMPM::EsimPoMgr::EsimPoMgr";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v9,
      (unsigned int)&dword_14006C86C,
      v10,
      v11,
      (__int64)&v15);
  }
  return this;
}

```

## disassembly

```asm
0x140033e00  mov     r11, rsp
0x140033e03  mov     [r11+8], rcx
0x140033e07  push    rbx
0x140033e08  push    rbp
0x140033e09  push    rsi
0x140033e0a  push    rdi
0x140033e0b  push    r15
0x140033e0d  sub     rsp, 50h
0x140033e11  mov     rsi, rcx
0x140033e14  xor     ebp, ebp
0x140033e16  lea     rax, ??_7EsimPoMgr@ESIMPM@@6B@; const ESIMPM::EsimPoMgr::`vftable'
0x140033e1d  mov     [rcx], rax
0x140033e20  mov     [rcx+8], rbp
0x140033e24  xorps   xmm0, xmm0
0x140033e27  movups  xmmword ptr [rcx+40h], xmm0
0x140033e2b  mov     [rcx+50h], rbp
0x140033e2f  lea     r15d, [rbp+7]
0x140033e33  mov     [rcx+58h], r15
0x140033e37  mov     [rcx+40h], bp
0x140033e3b  movups  xmmword ptr [rcx+60h], xmm0
0x140033e3f  mov     [rcx+70h], rbp
0x140033e43  mov     [rcx+78h], r15
0x140033e47  mov     [rcx+60h], bp
0x140033e4b  lea     rdi, [rcx+80h]
0x140033e52  mov     [r11+10h], rdi
0x140033e56  mov     [rdi], rbp
0x140033e59  mov     [rdi+8], rbp
0x140033e5d  mov     [rdi+10h], rbp
0x140033e61  mov     [rdi+18h], rbp
0x140033e65  mov     [rdi+20h], rbp
0x140033e69  lea     ecx, [rbp+48h]; Size
0x140033e6c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140033e71  mov     [rax], rax
0x140033e74  mov     [rax+8], rax
0x140033e78  mov     [rax+10h], rax
0x140033e7c  mov     word ptr [rax+18h], 101h
0x140033e82  mov     [rdi+18h], rax
0x140033e86  lea     rbx, [rdi+28h]
0x140033e8a  mov     [rsp+78h+arg_10], rbx
0x140033e92  mov     [rbx], ebp
0x140033e94  mov     [rbx+8], rbp
0x140033e98  mov     [rbx+10h], rbp
0x140033e9c  lea     ecx, [rbp+30h]; Size
0x140033e9f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140033ea4  mov     [rax], rax
0x140033ea7  mov     [rax+8], rax
0x140033eab  mov     [rbx+8], rax
0x140033eaf  lea     rcx, [rbx+18h]
0x140033eb3  mov     [rcx], rbp
0x140033eb6  mov     [rcx+8], rbp
0x140033eba  mov     [rcx+10h], rbp
0x140033ebe  mov     [rbx+30h], r15
0x140033ec2  mov     qword ptr [rbx+38h], 8
0x140033eca  mov     dword ptr [rbx], 3F800000h
0x140033ed0  mov     r8, [rbx+8]
0x140033ed4  lea     edx, [rbp+10h]
0x140033ed7  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x140033edc  nop
0x140033edd  xorps   xmm0, xmm0
0x140033ee0  movups  xmmword ptr [rdi+68h], xmm0
0x140033ee4  mov     [rdi+78h], rbp
0x140033ee8  mov     [rdi+80h], r15
0x140033eef  mov     [rdi+68h], bp
0x140033ef3  movups  xmmword ptr [rdi+88h], xmm0
0x140033efa  mov     [rdi+98h], rbp
0x140033f01  mov     [rdi+0A0h], r15
0x140033f08  mov     [rdi+88h], bp
0x140033f0f  movups  xmmword ptr [rdi+0A8h], xmm0
0x140033f16  mov     [rdi+0B8h], rbp
0x140033f1d  mov     [rdi+0C0h], r15
0x140033f24  mov     [rdi+0A8h], bp
0x140033f2b  movups  xmmword ptr [rdi+0C8h], xmm0
0x140033f32  mov     [rdi+0D8h], rbp
0x140033f39  mov     [rdi+0E0h], r15
0x140033f40  mov     [rdi+0C8h], bp
0x140033f47  mov     [rdi+0E8h], rbp
0x140033f4e  mov     [rsi+170h], ebp
0x140033f54  mov     dword ptr [rsi+174h], 11h
0x140033f5e  mov     dword ptr [rsi+178h], 1Dh
0x140033f68  mov     [rsi+1F0h], ebp
0x140033f6e  movups  xmmword ptr [rsi+228h], xmm0
0x140033f75  movups  xmmword ptr [rsi+238h], xmm0
0x140033f7c  xor     eax, eax
0x140033f7e  mov     [rsi+248h], rax
0x140033f85  mov     [rsi+250h], rax
0x140033f8c  movups  xmmword ptr [rsi+258h], xmm0
0x140033f93  mov     [rsi+268h], rbp
0x140033f9a  mov     [rsi+270h], r15
0x140033fa1  mov     [rsi+258h], bp
0x140033fa8  movups  xmmword ptr [rsi+278h], xmm0
0x140033faf  mov     [rsi+288h], rbp
0x140033fb6  mov     [rsi+290h], r15
0x140033fbd  mov     [rsi+278h], bp
0x140033fc4  mov     [rsi+298h], rax
0x140033fcb  mov     [rsi+2A0h], ebp
0x140033fd1  mov     [rsi+2A8h], rbp
0x140033fd8  mov     [rsi+2B0h], rbp
0x140033fdf  mov     [rsi+2B8h], ebp
0x140033fe5  mov     qword ptr [rsi+2BCh], 1
0x140033ff0  mov     [rsi+2C4h], bpl
0x140033ff7  mov     [rsi+2C8h], ebp
0x140033ffd  mov     [rsi+2D0h], rax
0x140034004  mov     [rsi+2D8h], rbp
0x14003400b  mov     [rsi+2E0h], ebp
0x140034011  movups  xmmword ptr [rsi+2E8h], xmm0
0x140034018  mov     [rsi+2F8h], rbp
0x14003401f  mov     [rsi+300h], r15
0x140034026  mov     [rsi+2E8h], bp
0x14003402d  mov     [rsi+308h], bpl
0x140034034  movups  xmmword ptr [rsi+310h], xmm0
0x14003403b  mov     [rsi+320h], rbp
0x140034042  mov     [rsi+328h], r15
0x140034049  mov     [rsi+310h], bp
0x140034050  movups  xmmword ptr [rsi+330h], xmm0
0x140034057  mov     [rsi+340h], rbp
0x14003405e  mov     [rsi+348h], r15
0x140034065  mov     [rsi+330h], bp
0x14003406c  mov     [rsi+350h], rbp
0x140034073  movups  xmmword ptr [rsi+358h], xmm0
0x14003407a  mov     [rsi+368h], rbp
0x140034081  mov     [rsi+370h], r15
0x140034088  mov     [rsi+358h], bp
0x14003408f  mov     [rsi+378h], ebp
0x140034095  movups  xmmword ptr [rsi+380h], xmm0
0x14003409c  mov     [rsi+390h], rbp
0x1400340a3  mov     [rsi+398h], r15
0x1400340aa  mov     [rsi+380h], bp
0x1400340b1  movups  xmmword ptr [rsi+3A0h], xmm0
0x1400340b8  mov     [rsi+3B0h], rbp
0x1400340bf  mov     [rsi+3B8h], r15
0x1400340c6  mov     [rsi+3A0h], bp
0x1400340cd  mov     [rsi+3C0h], rbp
0x1400340d4  mov     [rsi+3C8h], rbp
0x1400340db  mov     [rsi+3D0h], rbp
0x1400340e2  mov     byte ptr [rsi+3D8h], 1
0x1400340e9  mov     [rsi+3E0h], rbp
0x1400340f0  mov     [rsi+3E8h], rbp
0x1400340f7  xor     r9d, r9d; lpName
0x1400340fa  xor     r8d, r8d; bInitialState
0x1400340fd  lea     edx, [rbp+1]; bManualReset
0x140034100  xor     ecx, ecx; lpEventAttributes
0x140034102  call    cs:__imp_CreateEventW
0x140034108  mov     rcx, [rsi+3E8h]; hObject
0x14003410f  mov     [rsi+3E8h], rax
0x140034116  lea     rax, [rcx+1]
0x14003411a  cmp     rax, 1
0x14003411e  jbe     short loc_140034126
0x140034120  call    cs:__imp_CloseHandle
0x140034126  mov     ecx, 20h ; ' '; Size
0x14003412b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140034130  mov     rbx, rax
0x140034133  mov     [rsp+78h+arg_8], rax
0x14003413b  xorps   xmm0, xmm0
0x14003413e  movups  xmmword ptr [rax], xmm0
0x140034141  mov     [rax+10h], rbp
0x140034145  mov     [rax+18h], r15
0x140034149  mov     [rax], bp
0x14003414c  mov     r8, rax
0x14003414f  mov     ecx, 27h ; '''
0x140034154  call    ?GetPersistentRegPathWstring@@YAKW4_REG_ROOT_PATH@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetPersistentRegPathWstring(_REG_ROOT_PATH,ushort const *,std::wstring *)
0x140034159  test    eax, eax
0x14003415b  jnz     short loc_1400341C7
0x14003415d  mov     rdi, [rsi+3C0h]
0x140034164  mov     [rsi+3C0h], rbx
0x14003416b  test    rdi, rdi
0x14003416e  jz      short loc_140034185
0x140034170  mov     rcx, rdi
0x140034173  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140034178  mov     edx, 20h ; ' '
0x14003417d  mov     rcx, rdi; Block
0x140034180  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140034185  mov     eax, cs:dword_140075078
0x14003418b  cmp     eax, 5
0x14003418e  jbe     short loc_1400341B9
0x140034190  lea     rax, aEsimpmEsimpomg_9; "ESIMPM::EsimPoMgr::EsimPoMgr"
0x140034197  mov     [rsp+78h+arg_0], rax
0x14003419f  lea     rax, [rsp+78h+arg_0]
0x1400341a7  mov     [rsp+78h+var_58], rax
0x1400341ac  lea     rdx, dword_14006C86C
0x1400341b3  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1400341b8  nop
0x1400341b9  mov     rax, rsi
0x1400341bc  add     rsp, 50h
0x1400341c0  pop     r15
0x1400341c2  pop     rdi
0x1400341c3  pop     rsi
0x1400341c4  pop     rbp
0x1400341c5  pop     rbx
0x1400341c6  retn
0x1400341c7  lea     rdx, aFailedToGetPer; "failed to get persistent root string"
0x1400341ce  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1400341d3  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x1400341d8  lea     rdx, _TI1?AVexception@std@@; pThrowInfo
0x1400341df  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1400341e4  call    _CxxThrowException_0
```
